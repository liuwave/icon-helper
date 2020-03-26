# Sass (SCSS)

在项目中使用SCSS作为CSS预处理程序？ 没问题，如果您希望将我们的样式导入工作流程，Font Awesome提供了一个SCSS版本。


## 工具包内部是什么结构？

以下SCSS对应的mixin和文件的一些详细信息。

![table](/images/fontawesome/fa5/sass-1.png)


## 在您的编译中添加Font Awesome

将scss文件夹复制到您的项目中。 然后将整个webfonts文件夹复制到提供静态文件的项目中。

打开项目的scss/variables.scss，然后编辑@fa-font-path变量，指向放置webfonts文件夹的位置。

       

          $fa-font-path:        "../webfonts";
        

    
通过在主SCSS文件中添加@import "scss/fontawesome.scss" 来导入Font Awesome。 另外，在您的主SCSS文件中导入一种或多种样式 @import "scss/solid.scss"。

编译代码并开始在项目中使用这些新图标！

> 您需要记得，字体路径是相对于已编译CSS目录的相对路径。 确保将webfonts目录放置在相对于最终CSS所在的位置。

## 使用我们的Mixin

您可以使用@include fa-icon; 将其设置为图标。 使用@extend .fas; 以实心样式创建图标。 导入其他样式以使用其他前缀。 使用fa-content和变量名称可以使包含内容值更加容易。

       

          @import "./fontawesome/scss/fontawesome.scss";
          @import "./fontawesome/scss/solid.scss";
          @import "./fontawesome/scss/brands.scss";

          .user {
            @extend %fa-icon;
            @extend .fas;

            &:before {
              content: fa-content($fa-var-user);
            }
          }

          .twitter {
            @extend %fa-icon;
            @extend .fab;

            &:before {
              content: fa-content($fa-var-twitter);
            }
          }
        

    