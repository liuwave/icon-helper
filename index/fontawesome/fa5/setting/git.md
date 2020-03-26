# 自主托管Font Awesome

在本地构建和投入生产时，您是否更需要获得Font Awesome副本并在您自己项目的源代码中使用？ 如果您在一个代码库中有许多站点或应用程序，或者想要为工作流程自定义Font Awesome的某些部分，那么自己下载和托管Font Awesome则非常实用。

## 您已经下载了一份副本？

确保您已下载针对特定网站的文件副本。 您需要它来完成我们将要完成以下的操作。

## 您的下载包含了些什么？

面向Web的Font Awesome软件包包含以下目录和文件：

![table](/images/fontawesome/fa5/git-1.png)

## 在CSS中使用Web字体

`/css/all.css`文件包含核心样式以及使用Font Awesome时所需的所有图标样式。 `/webfonts`文件夹包含上述CSS引用并依赖的所有字体文件。

将整个/webfonts文件夹和/css/all.css复制到项目的静态资源目录（或您希望保留前端资源或vendor的文件夹）中。

将对复制的`/css/all.css`文件的引用添加到要在其上使用Font Awesome的每个模板或页面的 `<head>`中。

       

          <head>
            <link href="/your-path-to-fontawesome/css/all.css" rel="stylesheet"> <!--load all styles -->
          </head>
          <body>
            <i class="fas fa-user"></i> <!-- uses solid style -->
            <i class="far fa-user"></i> <!-- uses regular style -->
            <i class="fal fa-user"></i> <!-- uses light style -->
            <!--brand icon-->
            <i class="fab fa-github-square"></i> <!-- uses brands style -->
          </body>
        

    
## 需要使用CSS预处理程序？

需要使用我们捆绑在下载中的/scss或/less版本的Font Awesome吗？ 请查看我们的Sass和Less文档，以获取有关其内容的详细信息。 将它们编译成CSS后，您可以按照此处所述的以CSS为重点的步骤来处理托管和引用图标。

## 将SVG与JavaScript结合使用

/js/all.js会加载所有基本功能，以及使用Font Awesome时所需的所有图标样式。 将其复制到项目的静态资源目录（或者您希望保留前端资源或vender的文件夹）。

在要使用Awesome的每个模板或页面的`<head>`内，添加对复制的`/js/all.js`文件的引用。

       

          <head>
            <script defer src="/your-path-to-fontawesome/js/all.js"></script> <!--load all styles -->
          </head>
          <body>
            <i class="fas fa-user"></i> <!-- uses solid style -->
            <i class="far fa-user"></i> <!-- uses regular style -->
            <i class="fal fa-user"></i> <!-- uses light style -->
            <!--brand icon-->
            <i class="fab fa-github-square"></i> <!-- uses brands style -->
          </body>
        

    
> 仔细检查您的路径
>
> 由于您自己管理所有下载的文件，因此请确保页面`<head>`中的引用与您在项目中移动了Font Awesome所有文件的正确位置。

## 仅使用某些样式

在将Web字体与CSS框架一起使用时，是否只想使用某些样式的图标？ /css文件夹包含Font Awesome的所有样式选项（实心、常规、细体和品牌）的核心样式和其他文件。 /webfonts文件夹包含上述CSS引用并依赖的所有字体文件。

![table](/images/fontawesome/fa5/git-2.png)

将`/webfonts`和`/css`文件夹都复制到项目的静态资源目录（或者您希望保留前端资源或vendor的位置）中。 您可以根据需要删除不打算使用的任何样式的.css和网络字体文件。

在要使用Font Awesome的每个模板或页面的`<head>`中，添加对核心样式文件（`/css/fontawesome.css`）和单个样式的CSS（例如`/css/brands.css`）的引用。 请留意项目的路径以及上一步中将文件移动到的位置。

       

          <head>
            <!-- Our project just needs Font Awesome Solid + Brands -->
            <link href="/your-path-to-fontawesome/css/fontawesome.css" rel="stylesheet">
            <link href="/your-path-to-fontawesome/css/brands.css" rel="stylesheet">
            <link href="/your-path-to-fontawesome/css/solid.css" rel="stylesheet">
          </head>
          <body>
            <i class="fas fa-user"></i> <!-- uses solid style -->
            <i class="fab fa-github-square"></i> <!-- uses brand style -->
          </body>
        

    
> 注意网络字体的路径
>
>我们建议将`/webfonts`和`/css`文件夹保留在同一目录中。 因为如果不这样做，则需要更改每种样式的CSS文件中提到的网络字体的路径。

在将我们的SVG与JS框架一起使用时，是否只想使用某些样式？ /js文件夹包含Font Awesome的所有样式选项（实心，常规，细体和品牌）的核心样式和其他文件。

![table](/images/fontawesome/fa5/git-3.png)


将您要使用的fontawesome.js加载程序和任何图标样式的.js文件复制到项目的静态资源目录（或者您希望保留前端资源或vendor的位置）中。 我们建议最后引用fontawesome.js加载程序。

       

          <head>
            <!-- Our project just needs Font Awesome Solid + Brands -->
            <script defer src="/your-path-to-fontawesome/js/brands.js"></script>
            <script defer src="/your-path-to-fontawesome/js/solid.js"></script>
            <script defer src="/your-path-to-fontawesome/js/fontawesome.js"></script>
          </head>
          <body>
            <i class="fas fa-user"></i> <!-- uses solid style -->
            <i class="fab fa-github-square"></i> <!-- uses brand style -->
          </body>
        

    
> 仔细检查路径
>
> 由于您自己管理所有下载的文件，因此请确保页面`<head>`中的引用与您在项目中移动了Font Awesome的所有文件的位置正确。

## 下一步

完成引用以后，您现在可以开始引用模板或页面的`<body>`中的图标，然后查看我们打包到已加载的支持文件中的所有样式支持。