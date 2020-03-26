

# 使用包管理器

对于您和您的团队来说，npm和yarn这样的软件包管理器可能是熟悉的工具。 有了它们，您可以轻松地升级到新版本的Font Awesome。

## Font Awesome包中有什么？

面向Web的Font Awesome软件包包含以下目录和文件：



![table](/images/fontawesome/fa5/package-1.png)



## 安装免费版的Font Awesome

您可以通过npm或yarn轻松安装Font Awesome的最新免费版本：

       
         npm install --save-dev @fortawesome/fontawesome-free
        
    

       
         yarn add --dev @fortawesome/fontawesome-free
        
    

## 安装专业版的Font Awesome

要访问包含更多图标和样式的专业版软件包，需要您配置@fortawesome范围以使用我们的Pro NPM注册表。

###  您需要专业订阅才能使用它们！

专业版软件包是通过专业版订阅获得的额外服务的一部分。 通过获得对它们的使用权，来得到更多不同样式的图标、额外服务以及专业支持。

关于如何配置@fortawesome范围以使用我们的Pro NPM注册表，您有两个选择：

全局设置-全局设置这些值，使其可以在任何项目中使用：

       
         npm config set "@fortawesome:registry" https://npm.fontawesome.com/ &amp;&amp; \
         npm config set "//npm.fontawesome.com/:_authToken" TOKEN
        
    

单个项目-如果您希望对单个项目进行设置（对于团队和CI/CD来说是很不错的选择），请在项目的根目录（或您的package.json文件所在的位置）中创建一个.npmrc文件：

       
         @fortawesome:registry=https://npm.fontawesome.com/
         //npm.fontawesome.com/:_authToken=TOKEN
        
    

配置完成后，您可以通过npm或yarn安装最新的Pro Awesome Pro版本：

       
         npm install --save-dev @fortawesome/fontawesome-pro
        
    

       
         yarn add --dev @fortawesome/fontawesome-pro
        
    

环境变量-您还可以利用NPM的环境变量替换：

       `
         @fortawesome:registry=https://npm.fontawesome.com/
         //npm.fontawesome.com/:_authToken=${FONTAWESOME_NPM_AUTH_TOKEN}
        `
    

       `
         FONTAWESOME_NPM_AUTH_TOKEN=TOKEN npm install --save-dev @fortawesome/fontawesome-pro
        `
    

### 我们正在逐步淘汰npm注册表身份验证的旧方法

旧方法只设置了一个将服务器地址和令牌组合在一起的配置密钥。 这种新方法设置了两个不同的配置密钥：一个用于服务器地址，第二个用于令牌。 如果您当前正在使用旧方法，请将您的配置更新为新方法。

## 下一步

引用`/css/all.css`或`/js/all.js`，要使用Font Awesome的每个模板或页面的&lt;head&gt;中使用Font Awesome所需的所有内容都包含在内。 执行此操作时，请注意安装软件包的路径。



如果您只想使用特定样式，而不是我们在Web字体和SVG框架中包含的默认所有选项，请参考要使用的特定样式，例如fa-brands或fa-regular。

安装完毕后，请查看我们的图标，并了解如何在HTML中引用它们。
