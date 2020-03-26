# 从4.x版本升级

如果您已经在一个项目中使用了Font Awesome 4，那您准备好升级了吗？5.x版是完全重新设计和编码的。我们已经尽量保持与版本4的相似性，但是在升级时需要注意一些差异。下面将介绍如何让您的图标保持最新和最棒。

## 使用套件快速轻松地升级

我们的套件包含了4.x版本兼容性工具-该套件可自动为您管理最困难的升级部分。 创建一个工具包，将其嵌入代码添加到您的项目中，我们将处理以下事项：

## 自动映射旧图标名称

套件的4.x版本兼容性工具可处理对旧版本图标名称或已更改别名的任何引用。

## 始终加载您套件指定的Font Awesome版本

您的项目可能仍具有引用旧字体系列名称的CSS，这是一种较为常见的情况。当您的项目依赖于其他主题或加载了自己的较早版本的Font Awesome插件时，我们将覆盖它们以使用您配置的较新版本的Font Awesome。 这也可以确保您设置的所有CSS伪元素规则都使用正确的图标。

## 从4.x版本到5.x版本有什么变化？

### 3种不同的图标样式

我们为Font Awesome中的每个图标引入了实心、常规和细体的样式。 我们还将品牌图标分为自己的样式/类别，以方便使用。 我们需要一种在标记中调用图标时引用特定样式的方法。 对于您要使用的每个图标，仍然需要1）指定图标的名称，以及2）使用适当的前缀。 4.x版本仅带有一个前缀-fa。 5.x版本具有四个前缀，可让我们轻松设置任何图标的样式：

![3种不同的图标样式](/images/fontawesome/fa5/update-1.png)

       

          <i class="fa fa-camera-retro"></i>  <!-- version 4's syntax -->

          <i class="fas fa-camera-retro"></i> <!-- version 5's syntax -->
          <i class="far fa-camera-retro"></i> <!-- example: regular style of camera-retro -->
          <i class="fal fa-camera-retro"></i> <!-- example: light style of camera-retro -->
        

    
### 图标名称变更

在5.x版本中，我们删除了别名。每个图标都只有一个正式名称，其中一些名称已经根据我们的新标准和约定进行了调整。

### 线框图标

同样地，所有具有线框样式（通常以-o结尾）的图标现在都有一个far前缀，并且删除了它们的-o后缀。

## 手动升级

在5.x版本中，我们删除了别名。每个图标都只有一个正式名称，其中一些名称已经根据我们的新标准和约定进行了调整。

1、从您的项目中删除Font Awesome 4.x版所有资源和引用，包含整个 fontawesome/ 目录——其中包括网络字体(fontawesome/fonts/), CSS (fontawesome/css), 和预处理选项(fontawesome/less and fontawesome/scss)。如果您的4.x版本使用了CDN，则可以忽略该步骤。接下来，从模板/页面HTML的`<head>`中删除对4.x版本的CSS或JS的引用，包括对版本4的CDN的所有引用。

2、 参考查阅我们的入门详细信息，设置和添加5.x版本的资源和引用。您现在可以使用我们的工具包、下载并自行托管到服务器，或者通过包管理器安装Font Awesome。

3、 我们为您已经创建了填充文件以用作临时解决方案，直到您有时间进行升级。 我们的v4填充程序允许您在将5.x版本的图标映射到当前引用时保留旧4.x版本图标的名称、别名和语法。
如果要使用它们，则需要在5.x版本参考中添加额外的一行。 这是使用5.x版本的CDN的示例：

       

            <head>
              <link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.11.2/css/all.css">
              <link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.11.2/css/v4-shims.css">
            </head>
            <body>
              <!-- "close" is an alias to "times", V5 is <i class="fa fa-times"></i> -->
              <i class="fa fa-close"></i>

              <!-- Renamed to "image", V5 is <i class="fa fa-image"></i> -->
              <i class="fa fa-picture"></i>

              <!-- Needs the "fab" prefix, V5 <i class="fab fa-twitter"></i> -->
              <i class="fa fa-twitter"></i>

              <!-- "far" prefix, lose the "-o", V5 <i class="far fa-circle"></i> -->
              <i class="fa fa-circle-o"></i>
            </body>
        

    
v4填充程序可在我们的Web字体+ CSS和SVG + JS框架中使用。 如果您使用我们新颖的SVG + JS呈现图标方式，只需将/css/all.css引用切换到/js/all.js以及将/css/v4-shims.css切换到/ js / v4 -shims.js。 上面的示例切换为改用我们的SVG + JS框架。

       

          <head>
            <script defer src="https://use.fontawesome.com/releases/v5.11.2/js/all.js"></script>
            <script defer src="https://use.fontawesome.com/releases/v5.11.2/js/v4-shims.js"></script>
          </head>
          <body>
            <!-- your existing version 4 icon references here... -->
          </body>
        

    
4、 更新您在Font Awesome图标周围添加的所有自定义样式，包括您设置的定义Unicode值的规则，这些规则可能会随着CSS伪元素而发生变化。

5、 仔细检查项目的用户界面，不要忘了请工作伙伴喝杯咖啡，让他们浏览项目的页面和视图，以确保所有图标均按预期方式呈现。 同样，您的项目的暂存或开发版本也是执行此操作的好地方。

> 请记住，不要交叉或跨版本使用！与Spengler博士商量之后，我们不建议在项目中同时使用Font Awesome 4和5。 它将导致CSS过大以及路径冲突，我们不能保证图标会按照您或我们的期望进行渲染。如果您无法删除旧版本的引用，我们建议使用启用了4.x版本兼容性的工具包来帮助解决冲突。

6、 更新CSS伪元素规则如果您在4.x版本中使用CSS伪元素，则升级到5.x版本需要大量的手工工作。 您需要执行以下步骤：

- 更新字体值-您需要确保更改字体以引用新版本的Font Awesome 5。
- 使用每个基于图标的规则设置字体粗细-您还需要设置字体粗细，因为第5版将多种样式映射为不同的粗细。
       

          /* general styling shared between versions */
          .icon::before {
            display: inline-block;
            font-style: normal;
            font-variant: normal;
            text-rendering: auto;
            -webkit-font-smoothing: antialiased;
          }

          /* version 4's styling (using calendar-o) */
          .calendar::before {
            font-family: FontAwesome;
            content: "\f133";
          }

          /* version 5's styling (using updated regular style of calendar) */
          .calendar::before {
            font-family: "Font Awesome 5 Free";  /* updated font-family */
            font-weight: 400; /* regular style/weight */
            content: "\f133";
          }
        

    
## 使用SVG + JS时需要额外的步骤

如果您正在使用带有JavaScript框架的SVG，则需要了解并完成几个步骤来启动和运行。

### 图标名称在4.x版本和5.x版本之间更改

这是根据5.x版本的标准和约定重命名的所有图标的列表。 请记住，您需要将4.x版本中的所有品牌图标更改为使用新的fab前缀而不是旧的fa前缀。

![table](/images/fontawesome/fa5/update-table-1.png)
![table](/images/fontawesome/fa5/update-table-2.png)
![table](/images/fontawesome/fa5/update-table-3.png)
![table](/images/fontawesome/fa5/update-table-4.png)
![table](/images/fontawesome/fa5/update-table-5.png)
![table](/images/fontawesome/fa5/update-table-6.png)
![table](/images/fontawesome/fa5/update-table-7.png)
![table](/images/fontawesome/fa5/update-table-8.png)
![table](/images/fontawesome/fa5/update-table-9.png)

## 下一步

遇到麻烦了吗？ 请查看我们的疑难解答指南，以获取有关在网络上使用Font Awesome的常见问题的答案。 可以了？ 那请享受添加到5.x版本中的所有新图标。