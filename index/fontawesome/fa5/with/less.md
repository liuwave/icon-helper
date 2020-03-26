# Less

在项目中使用Less作为CSS预处理程序？ 没问题，如果您希望将我们的样式导入工作流程，Font Awesome提供了一个Less版本。

> ## 您已经下载了副本，对吗？
>
> 确保您已下载了所需文件的副本。 您需要它来完成我们将要完成的以下任何操作。

## 工具包内部是什么结构？

以下Less对应的mixin和文件的一些详细信息。

![table](/images/fontawesome/fa5/less-1.png)


## 在您的编译中添加Font Awesome

将less文件夹复制到您的项目中。 然后将整个webfonts文件夹复制到提供静态文件的项目中。

打开项目的less/variables.less，然后编辑@fa-font-path变量，指向放置webfonts文件夹的位置。

       

          @fa-font-path:        "../webfonts";
        

    
通过在主Less文件中添加@import "less/fontawesome.less" 来导入Font Awesome。 另外，在您的主Less文件中导入一种或多种样式 @import "less/solid.less"。

编译代码并开始在项目中使用这些新图标！

> 您需要记得，字体路径是相对于已编译CSS目录的相对路径。 确保将webfonts目录放置在相对于最终CSS所在的位置。

## 使用我们的Mixin

您可以使用.fa-icon; 将其设置为图标。 使用.fas; 以实心样式创建图标。 导入其他样式以使用其他前缀。 使用变量可以使引入内容值更加容易。

       

          @import "./fontawesome/less/fontawesome";
          @import "./fontawesome/less/solid";
          @import "./fontawesome/less/brands";

          .user {
            .fa-icon;
            .fas;

            &:before {
              content: @fa-var-user;
            }
          }

          .twitter {
            .fa-icon;
            .fab;

            &:before {
              content: @fa-var-twitter;
            }
          }
        

    