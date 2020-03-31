
# Vuepress pwa插件 采坑记录


最近，我终于完成了Icon助手(iconhelper.cn)这个项目。这个项目是采用的Vuepress静态生成的，使用了pwa插件，以优化用户体验。

开发过程都很顺利，但在部署的时候遇到一个问题，[material中文搜索 ](https://material.iconhelper.cn)这个子站，首次加载特别慢。甚至在某些手机浏览器(QQ手机浏览器)中会黑屏，使浏览器崩溃。下面就把遇到的问题和解决过程记录下来。

先把项目的Vuepress配置贴出来：

    // /.vuepress/config.js
    module.exports = {
    ...
    
        plugins:[
            ['@vuepress/pwa', {
              serviceWorker: true,  
              updatePopup:  {
                message: "发现新内容可用",
                buttonText: "刷新"
              }
            }],
        ]
    }
    
    
`serviceWorker`选项的值为`true`，那么vuepress编译的时候会在根目录生成`service-worker.js`文件。    

## CDN加载问题

Vuepress生成的`service-worker.js`使用的是storage.googleapis.com的CDN，但这个这个CDN在国内经常访问不了，那么就会导致报错，不能正常加载缓存。

![cdn](/images/blog/log/vuepress-pwa-plugin/cdn-1.png)


    importScripts("https://storage.googleapis.com/workbox-cdn/releases/4.3.1/workbox-sw.js");


需要把`storage.googleapis.com`替换掉，可以替换成下面的代码：


    const version = '4.3.1'
    importScripts(`https://cdn.jsdelivr.net/npm/workbox-sw@${version}`)
    workbox.setConfig({
      modulePathCb(name, debug) {
        const env = debug ? 'dev' : 'prod'
        return `https://cdn.jsdelivr.net/npm/${name}@${version}/build/${name}.${env}.js`
      },
    })


替换后，访问基本正常了。 如果你不喜欢jsdelivr，可以按照上面的方法进行替换。


## 减少网页首次打开加载的缓存文件数量

Vuepress编译后的`service-worker.js`文件中，会生成一个数组self.__precacheManifest，里面包含了这个项目的所有静态文件url。浏览器加载`service-worker.js`会按照这个数组进行加载静态缓存。


![browser-loading](/images/blog/log/vuepress-pwa-plugin/browser-loading.png)


[material中文搜索 ](https://material.iconhelper.cn)是从material design icon中搜集到的，有5000多个图标，对应的就有5000多个md文件。Vuepress编译后，一个md文件会生成2个文件：.html和.js，再加上其他静态图片和必要的css文件，整个precacheManifest的数量有12000多个。编译后的`service-worker.js`文件大小在1MB左右。


这么多的文件在首次访问的时候都要加载，确实会让浏览器负载不起，在网络差的时候，浏览器加载`service-worker.js`都会耗费较长的时间。

那么，势必要减少缓存文件的数量。

在Vuepress 的[PWA插件文档](https://www.vuepress.cn/zh/plugin/official/plugin-pwa.html#generateswconfig)中，有一个`generateSWConfig`参数，可以设置`globPatterns` 和 `globIgnores`，以减少缓存的数量。

Vuepress中 `globPatterns`的默认值是：

       globPatterns: [
              '**\/*.{css,js,html,png,jpg,jpeg,gif,svg,woff,woff2,eot,ttf,otf}',
            ],
            
这条规则的的含义是匹配所有以css,js,html,png,jpg,jpeg,gif,svg,woff,woff2,eot,ttf,otf为后缀的静态文件。html文件在vuepress中跳转中不会加载，所有我们可以去掉html后缀：

    globPatterns: [
              '**\/*.{css,js,png,jpg,jpeg,gif,svg,woff,woff2,eot,ttf,otf}',
            ],
            
更改后，生成的缓存列表减少了几乎一半，`service-worker.js`的大小以及降到500KB左右。浏览器首次访问还是会加载5000+的缓存。这里，可以设置`globIgnores`:



     //忽略编号为2000以上的的js文件
            globIgnores: ['**\/[2-9][0-9][0-9][0-9].*.js'],
            
            
Vuepress编译产生的js文件大部分是从1递增，这里，直接忽略都编号大于2000的js文件。


重新编译后，部署浏览器首次访问的加载量可以接受，浏览器不会明显的卡顿。当然 globIgnores 可以设置成忽略所有的静态文件，这个需要根据实际情况进行取舍。


## 减小`service-worker.js`的体积


经过上一步的处理，Vuepress生成的`service-worker.js`文件大小也降到了180KB,Gzip之后只有30KB。30KB对现在的网速来说不随什么，但还有进一步降低的办法。

![revision](/images/blog/log/vuepress-pwa-plugin/revision.png)


我们可以看到，生成的url有个revision字段，这是为了判断是否需要更新页面。但生成的大部分js文件都带有hash，如`assets/js/1.bb8df20c.js`,修改文件后再次编译生成的文件hash也会跟着变化。

那么我们就可以通过以下设置去掉这个revision字段：

    dontCacheBustUrlsMatching: /\.\w{8}\./

即，路径中含有.[hash(8个字符)].的不生成唯一控制版本的revision字段。

这样处理后，生成的`service-worker.js`文件大小降到了98KB,Gzip之后只有18KB。


## pwa插件完整设置：

    // /.vuepress/config.js
    module.exports = {
    ...
    
        plugins:[
            ['@vuepress/pwa', {
              serviceWorker: true,  
              generateSWConfig:{
                globPatterns: [
                  '**\/*.{css,js,png,jpg,jpeg,gif,svg,woff,woff2,eot,ttf,otf}',
                ],
                //忽略编号为2000以上的的js文件
                globIgnores: ['**\/[2-9][0-9][0-9][0-9].*.js'],
                dontCacheBustUrlsMatching: /\.\w{8}\./
              },
              updatePopup:  {
                message: "发现新内容可用",
                buttonText: "刷新"
              }
            }],
        ]
    }


    
参考

- Vuepress [PWA插件](https://www.vuepress.cn/zh/plugin/official/plugin-pwa.html#generateswconfig)    
- workbox-build 的 [generateSW config](https://developers.google.com/web/tools/workbox/modules/workbox-build#full_generatesw_config) 
- icon助手 ：  
    - 主页 [https://iconhelper.cn/](https://iconhelper.cn/) 
    - github [https://github.com/liuwave/icon-helper](https://github.com/liuwave/icon-helper)
    - gitee [https://gitee.com/liuwave/icon-helper](https://gitee.com/liuwave/icon-helper)
   