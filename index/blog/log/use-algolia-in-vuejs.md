
# Vue.js（VuePress.js）中使用Algolia Search

VuePress的默认主题中集成了Algolia插件，使用的是Algolia DocSearch，使用之前需要将网站提交给Algolia创建索引。Algolia在收到请求后会抓取网站内容建立好内容索引后，你的网站就可以使用Algolia提供的api进行搜索。
这种方式能满足文档的搜索要求，但不能自定义搜索的数据结构以及展示的形式。

为了对更多自定义的需要，我们对接Algolia Search API。Algolia提供免费的社区套餐，限1万条记录、5万次数据操作，能够满足基本的需求。


## 准备数据

根据项目需求，这里准备的是json格式的数据，样例如下：

      [
          {
            "name": "heart",
            "title": "Heart",
            "zhTips": "心脏,收藏夹,喜欢,爱情,关系,情人节,心镂空,love,心,爱心,favorite,like,relationship,valentine,最爱,favourite",
            "channel": [
              {
                "domain": "https://fontawesome.iconhelper.cn",
                "title": "Fontawesome Icon 免费图标",
                "svgDomain": "https://iconhelper.cn",
                "name": "fontawesome",
                "svg": "https://iconhelper.cn/svg/fontawesome/regular/heart.svg",
                "url": "https://fontawesome.iconhelper.cn/icon/regular/heart.html"
              },
              {
                "domain": "https://material.iconhelper.cn",
                "title": "Material Design Icon 免费图标",
                "svgDomain": "https://iconhelper.cn",
                "name": "material",
                "svg": "https://iconhelper.cn/svg/material/heart.svg",
                "url": "https://material.iconhelper.cn/icon/heart.html"
              }
            ]
          },
      /...
      ]
      
      
保存为json格式的文件。


## Algolia 服务器端的操作


首先，在[Algolia](https://www.algolia.com)注册一个账号,并登录：

![登录](/images/blog/log/create-algolia/1-login.png)


登录后，进入控制面板，新建一个应用。

![新建应用](/images/blog/log/create-algolia/2-create-app.png)

输入应用的名称，这里我们输入 `iconhelper-cn-test`，套餐选择免费的社区套餐。

![新建应用详情](/images/blog/log/create-algolia/3-create-app-detail.png)

选择主要地域，algolia在中国大陆没有节点，一般我们选择地理位置离中国大陆最近的香港节点或日本节点。

![选择区域](/images/blog/log/create-algolia/4-select-main-region.png)


创建应用后，Algolia会要求你建立一个索引。


![创建索引](/images/blog/log/create-algolia/5-create-index.png)


输入索引名称，这里输入 `my-test-index`（这个索引名称后续会用到）。

![输入索引名称](/images/blog/log/create-algolia/6-create-index.png)

第二步是上传记录，可以通过文件、API或者手动上传记录。

![选择上传记录](/images/blog/log/create-algolia/7-upload-records.png)

我们这里选择文件上传，选择上午准备的json格式的文件，点击上传。 除了JSON格式，你还可以选择Algolia支持的CSV和TSV格式文件。


![上传记录](/images/blog/log/create-algolia/8-upload-records-detail.png)

上传记录后，需要设置可搜索属性。

![设置可搜索属性](/images/blog/log/create-algolia/9-config-attribute.png)


根据项目需求，我们这里设置了name/zhTips/chanel.title三个可搜索属性。这代表搜索接口只在这三个属性的值中进行搜索，返回的高亮数据中也只限三个属性。

![保存可搜索属性](/images/blog/log/create-algolia/10-config-attribute-save.png)

最后一步，设置排序。

![设置排序属性](/images/blog/log/create-algolia/11-config-ranking.png)

除了默认的几个排序字段，这里设置了name，升序排列。

![保存排序属性](/images/blog/log/create-algolia/12-config-ranking-detail.png)


最后获取 Application ID 和 Search-Only API key，以供前端接口中使用。

![获取API Key](/images/blog/log/create-algolia/13-get-api-keys.png)


## Vue组件中的操作


### 首先我们先安装 algoliasearch

    npm install algoliasearch
    
    或者
    
    yarn add algoliasearch
    

### 组件中使用（示例代码）


    import algoliasearch from 'algoliasearch/lite';


    export default {
        name: "AlgoliaSearch",        
        methods: {
            search: function (q) {
                const client = algoliasearch("YourApplicationID", "YourSearchOnlyAPIKey");                
                const index = client.initIndex("iconhelper-cn-test");
                index.search(q,{
                          hitsPerPage:20//每页数量
                        }).then(({hits,nbHits,nbPages,hitsPerPage,processingTimeMS}) => {
                            //操作数据更新
                        });
            }
        
        }
    }



### 效果展示

[icon助手](https://iconhelper.cn)

    

            
            

    