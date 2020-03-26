

# 双色图标


双色图标就像我们所有其他图标一样工作。 最重要的是，它们提供了Font Awesome中每个图标的版本，该图标具有两种不同的颜色。 它们非常适合为您的项目中的图标添加更多品牌或插图品质。

## 基本用法

双色图标使用相同的语法Font Awesome图标，并且可以使用其特定样式前缀（fad）像其他任何图标一样进行引用。

          <div class="fa-3x">
            <i class="fad fa-camera"></i> <!-- a duotone style camera icon -->
            <i class="fad fa-fire-alt"></i> <!-- a duotone style fire-alt icon -->
            <i class="fad fa-bus-alt"></i> <!-- a duotone style bus-alt icon -->
            <i class="fad fa-fill-drip"></i> <!-- a duotone style fill-drip icon -->
          </div>
    

## 交换图层透明度

您可以交换每个双色图标图层的默认透明度。 这将使图标的主要层的默认不透明度为40％。

          <div class="fa-3x">
            <i class="fad fa-camera"></i> <!-- a duotone style camera icon -->
            <i class="fad fa-camera fa-swap-opacity"></i> <!-- a duotone style camera icon with swapped opacity -->

            <i class="fad fa-fire-alt"></i> <!-- a duotone style fire-alt icon -->
            <i class="fad fa-fire-alt fa-swap-opacity"></i> <!-- a duotone style fire-alt icon with swapped opacity -->

            <i class="fad fa-bus-alt"></i> <!-- a duotone style bus-alt icon -->
            <i class="fad fa-bus-alt fa-swap-opacity"></i> <!-- a duotone style bus-alt icon with swapped opacity -->
          </div>
        



## 改变透明度

默认情况下，双色图标中的辅助图层设置为40％不透明度（通过Font Awesome支持CSS规则 opacity 0.4； ）。 您可以使用下面的CSS自定义属性来明确设置双色调图标图层的透明度。 这是一些设置它们的地方。



设置主要层透明度
> --fa-primary-opacity
>
> 0 1.0


设置次要层透明度
> --fa-secondary-opacity
> 
> 0 1.0

          <div class="fa-3x">
            <i class="fad fa-bus-alt" style="--fa-secondary-opacity: 0.20"></i> <!--  secondary layer's opacity set to 20% -->
            <i class="fad fa-bus-alt" style="--fa-secondary-opacity: 0.40"></i> <!--  secondary layer's opacity set to 40% -->
            <i class="fad fa-bus-alt" style="--fa-secondary-opacity: 0.60"></i> <!--  secondary layer's opacity set to 60% -->
            <i class="fad fa-bus-alt" style="--fa-secondary-opacity: 0.80"></i> <!--  secondary layer's opacity set to 80% -->
            <i class="fad fa-bus-alt" style="--fa-secondary-opacity: 1.0"></i> <!--  secondary layer's opacity set to 100% -->
          </div>
        
    
          <div class="fa-3x">
            <i class="fad fa-bus-alt" style="--fa-primary-opacity: 0.20"></i> <!--  primary layer's opacity set to 20% -->
            <i class="fad fa-bus-alt" style="--fa-primary-opacity: 0.40"></i> <!--  primary layer's opacity set to 40% -->
            <i class="fad fa-bus-alt" style="--fa-primary-opacity: 0.60"></i> <!--  primary layer's opacity set to 60% -->
            <i class="fad fa-bus-alt" style="--fa-primary-opacity: 0.80"></i> <!--  primary layer's opacity set to 80% -->
            <i class="fad fa-bus-alt" style="--fa-primary-opacity: 1.0"></i> <!--  primary layer's opacity set to 100% -->
          </div>
        
    



### 轮到你了！

让我们确保这个概念是超级“透明的”。 尝试修改这些不同的不透明度示例。 **让我们确保这个概念是超级“透明的”。 尝试修改这些不同的不透明度示例。**



## 为双色图标着色

像所有其他“Font Awesome”图标一样，双色图标会自动继承CSS大小和颜色。 双色图标由主要层和次要层组成。 默认情况下，次要层的不透明度为40％，因此它会以图标继承或直接设置的颜色的浅色显示。

使用CSS自定义属性，我们还在双色图标的主要层和辅助图层上添加了一些颜色钩子。 这是一些设置它们的地方。



![table](/images/fontawesome/fa5/duotone-1.png)


          <div class="fa-3x">
            <i class="fad fa-bus-alt" style="--fa-primary-color: gold;"></i>  <!-- primary layer color defined -->
            <i class="fad fa-bus-alt" style="--fa-primary-color: orangered;"></i> <!-- primary layer color defined -->
            <i class="fad fa-fill-drip" style="--fa-secondary-color: limegreen;"></i>  <!-- secondary layer color defined -->
            <i class="fad fa-fill-drip" style="--fa-secondary-color: rebeccapurple;"></i> <!-- secondary layer color defined -->
            <i class="fad fa-battery-full" style="--fa-primary-color: limegreen; --fa-secondary-color: dimgray;"></i> <!-- secondary + primary layer color defined -->
            <i class="fad fa-battery-quarter" style="--fa-primary-color: orange; --fa-secondary-color: dimgray;"></i> <!-- secondary + primary layer color defined -->
          </div>
        




## 进阶使用

当您将所有着色、不透明度和其他选项组合在一起时，“Font Awesome”图标将变得更赞。 这里有一些关于双色图标如何将您的项目带入更高领域的想法。

### 使用颜色突出显示图标的一部分或注释状态

          <div class="fa-3x">
            <i class="fad fa-book" style="--fa-primary-color: lightseagreen; --fa-secondary-color: linen; --fa-secondary-opacity: 1.0;"></i>
            <i class="fad fa-book-spells" style="--fa-primary-color: mediumpurple; --fa-secondary-color: linen; --fa-secondary-opacity: 1.0;"></i>
            <i class="fad fa-book-medical" style="--fa-primary-color: crimson; --fa-secondary-color: linen; --fa-secondary-opacity: 1.0;"></i>
            <i class="fad fa-book-user" style="--fa-primary-color: peru; --fa-secondary-color: linen; --fa-secondary-opacity: 1.0;"></i>

            <i class="fad fa-toggle-off" style="--fa-primary-color: white; --fa-secondary-color: gray; --fa-secondary-opacity: 1.0;"></i>
            <i class="fad fa-toggle-on" style="--fa-primary-color: dodgerblue; --fa-secondary-color: white; --fa-secondary-opacity: 1.0;"></i>

            <i class="fad fa-file-plus" style="--fa-primary-color: white; --fa-secondary-color: limegreen; --fa-secondary-opacity: 1.0;"></i>
            <i class="fad fa-file-exclamation" style="--fa-primary-color: white; --fa-secondary-color: gold; --fa-secondary-opacity: 1.0;"></i>
            <i class="fad fa-file-times" style="--fa-primary-color: white; --fa-secondary-color: tomato; --fa-secondary-opacity: 1.0;"></i>
          </div>
        
    

## 创建看起来像插图的全彩图标

          <div class="fa-3x">
            <i class="fad fa-crow" style="--fa-secondary-opacity: 1.0; --fa-primary-color: dodgerblue; --fa-secondary-color: gold;"></i>
            <i class="fad fa-campfire" style="--fa-secondary-opacity: 1.0; --fa-primary-color: sienna; --fa-secondary-color: red;"></i>
            <i class="fad fa-birthday-cake" style="--fa-secondary-opacity: 1.0; --fa-primary-color: pink; --fa-secondary-color: palevioletred;"></i>
            <i class="fad fa-ear" style="--fa-secondary-opacity: 1.0; --fa-primary-color: sandybrown; --fa-secondary-color: bisque;"></i>
            <i class="fad fa-corn" style="--fa-secondary-opacity: 1.0; --fa-primary-color: mediumseagreen; --fa-secondary-color: gold;"></i>
            <i class="fad fa-cookie-bite" style="--fa-secondary-opacity: 1.0; --fa-primary-color: saddlebrown; --fa-secondary-color: burlywood;"></i>
          </div>
    

## 带有品牌视觉色彩的主题图标


          <style>
            .theme-ravenclaw {
              --fa-secondary-opacity: 1.0;
              --fa-primary-color: rgb(4, 56, 161);
              --fa-secondary-color: rgb(108, 108, 108);
            }
          </style>

          <div class="fa-3x">
            <i class="fad fa-hat-wizard theme-ravenclaw"></i>
            <i class="fad fa-flask-potion theme-ravenclaw"></i>
            <i class="fad fa-wand-magic theme-ravenclaw"></i>
            <i class="fad fa-scarf theme-ravenclaw"></i>
            <i class="fad fa-book-spells theme-ravenclaw"></i>
          </div>
        
    

## 在项目中使用

对于大多数人来说，CSS定制属性仍然是一件比较陌生的事情。 您可以通过以下几种方法在项目中定义它们…

## 使用CSS设置属性：root

您可以在CSS：root伪类级别定义双色图标的自定义属性。 默认情况下，这将使您包括的任何双色图标都继承属性。

          <!-- by default, everything will be in the holiday spirit -->
          <style>
            :root {
              --fa-primary-color: green;
              --fa-secondary-color: red;
            }
          </style>

          <i class="fad fa-holly-berry"></i>
          <i class="fad fa-wreath"></i>
          <i class="fad fa-candy-cane"></i>
        
    

## 使用基于项目的CSS规则设置属性

您还可以在项目的CSS中，页面的&lt;head&gt;或单独的样式表中设置自定义属性。 这些属性的作用域仅限于与您所包含的规则选择器匹配的元素。当您可能无法轻松访问项目的原始HTML时，此技术非常适合主题化。

     <!-- setting a rule for house styling -->
          <style>
            .theme-slytherin {
              --fa-primary-color: darkgreen;
              --fa-secondary-color: silver;
            }
          </style>

          <i class="fad fa-wand-magic theme-slytherin"></i>
          <i class="fad fa-scarf theme-slytherin"></i>
          <i class="fad fa-book-spells theme-slytherin"></i>
    

## 使用内联样式设置属性

文档中的许多示例都通过向元素添加样式属性来使用内联样式定义CSS自定义属性。 这最适合一次性使用或非常自定义的彩色/样式双色图标，您无需进行全局更改。

          <!-- using inline styles to define duotone icon custom properties -->
          <i class="fad fa-crow" style="--fa-primary-color: dodgerblue; --fa-secondary-color: gold;"></i>


### 注意特异性和级联！

重新定义的CSS自定义属性将彼此覆盖。 在：root {}中定义属性，然后在规则或内联中定义相同的属性将导致：root样式被覆盖。



## 双色图标备忘表


![table](/images/fontawesome/fa5/duotone-2.png)




## 疑难解答

### 我可以通过使用CSS伪元素来使用双色图标吗？

是的，双色图标样式可以与CSS伪元素一起使用。 不过这样做比使用CSS伪元素渲染图标的基本难度还要复杂。

## 我要使用的图标未显示为双色风格！

让我们仔细检查几件事...

*   您是否使用了双色图标的fad前缀？

*   双色图标仅在Font Awesome专业版中可用-确保您具备有效的专业版。

*   最近我们非常频繁地发布图标。 确保您使用的是最新和最佳版本，以便随时使用想要使用的任何新图标。

*   如果您决定托管自己的Font Awesome副本，请检查是否已移动所有使用所需图标所需的文件。 另外，请在HTML的&lt;head&gt;中再次检查这些文件的路径。

## 救命！ 我无法定位各个图层！

确保您使用的是我们定义的正确的自定义属性值。 另外，请确保您尚未定义可能会覆盖所有内容的自定义属性（检查内联和自定义CSS中的内容）。 我们不建议编写针对特定类或伪元素的自定义CSS，因为我们的网络字体和SVG版本的Font Awesome之间存在一些差异，因此可能会出现一些问题。

## 我可以在双色图标旁边使用其他Font Awesome样式吗？

当然！调整大小、固定宽度和动画之类的东西都可以与双色图标一起使用。 如果您使用的是Font Awesome的SVG + JS版本，那么我们强大的转换功能和分层功能可以完成一些令人惊奇的事情。

## 双色图标可以在哪些浏览器中运行？

双色图标在所有现代Web浏览器中均呈现了出色的效果。 由于Internet Explorer（版本10和11）不支持CSS自定义属性，因此虽然双色图标可以呈现，但您将无法为单个图层定义颜色或透明度。 如果您必须支持该过时的浏览器，建议您在图标或其父元素上定义颜色。



### 开始使用双色图标！

使用我们的托管工具包即可在您的站点上获得彩色图标，从而实现轻松拆分！ 需要自己托管事物还是需要使用特定语言工作？ 我们还有其他选择。 哦，请确保您仔细阅读整个双色图标目录，以找到适合该工作的图标。

