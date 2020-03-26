

# 基本用法

您可以使用样式前缀和图标名称将“Font Awesome”图标放置在几乎任何地方。 我们努力达到这一目标，以使图标具有这些特征并自然地与文本显示在一起。

Font Awesome旨在与内联元素一起使用，我们建议使用一致的HTML元素以在项目中引用它们。 我们喜欢&lt;i&gt;标签的简洁性，因为最近大多数人都在使用&lt;em&gt; &lt;/em&gt;来强调/斜体化语义文本。 如果那不是您的理想之选，那么在语义上使用&lt;span&gt;更为正确。

您需要知道两点信息才能引用一个图标：1.以fa-为前缀的名称；2.要使用的相应前缀的样式。

          <div></div>
          <i class="fas fa-camera"></i> <!-- this icon's 1) style prefix == fas and 2) icon name == camera -->
          <i class="fas fa-camera"></i> <!-- using an <i> element to reference the icon -->
          <span class="fas fa-camera"></span> <!-- using a <span> element to reference the icon -->
        

![table](/images/fontawesome/fa5/base-1.png)




> fa前缀在5.x版本中已弃用。新的默认设置是实心的fas样式和品牌的fab样式。



由于Font Awesome首次实现并继续支持使用CSS @font-face方法进行渲染，因此其每种样式都对应于特定的字体粗细：


![table](/images/fontawesome/fa5/base-2.png)




### 为什么需要字体粗细值？

尽管使用&lt;i&gt;或其他HTML元素是呈现图标的最流行和最简便的方法，但是如果您希望具有额外的标记，我们确实有使用自定义书面CSS伪元素的高级方法。 字体粗细与该技术一起使用，是设置图标样式的最佳方式。





### 使用Font Awesome中的连字

尽管我们的桌面工作流程利用连字功能使您可以轻松地将图标插入您喜欢的设计和演示应用程序以及SVG + JS框架中，但连字查找表会占用额外的文件空间，并可能导致性能问题。 在获得用于子集图标的选项和解决方案之前，我们不愿意考虑使用Web字体+ CSS的连字。



## Font Awesome图标+您项目的样式

Font Awesome图标会自动继承CSS大小和颜色。 这意味着无论您将它们放在何处，它们都与内联文本混合在一起。 Font Awesome会尽量不增加复杂的设置，只在上下文中正确呈现的基本样式规则。
        

<span style="font-size: 3em; color: Tomato;">
           <i class="fas fa-camera"></i>
           </span> 
           <span style="font-size: 48px; color: Dodgerblue;">
           <i class="fas fa-camera"></i>
           </span> 
           <span style="font-size: 3rem;">
           <span style="color: Mediumslateblue;">
           <i class="fas fa-camera"></i>
           </span>
</span>


        <span style="font-size: 3em; color: Tomato;">
           <i class="fas fa-camera"></i>
           </span>
 
           <span style="font-size: 48px; color: Dodgerblue;">
           <i class="fas fa-camera"></i>
           </span>
 
           <span style="font-size: 3rem;">
           <span style="color: Mediumslateblue;">
           <i class="fas fa-camera"></i>
           </span>
           </span>
           
    

## 其他样式选项

虽然引用图标的基本方法很简单，那是希望它足够简单明了，但我们也为图标的大小、对齐、旋转和变换图标提供了支持。

您还可以通过在项目代码中添加自己的CSS规则，将自己的自定义样式添加到Font Awesome图标中。 这是一个简单的例子。

            <head>
            <!-- reference your copy Font Awesome here (from our CDN or by hosting yourself) -->
            <link href="/your-path-to-fontawesome/css/fontawesome.css" rel="stylesheet">
            <link href="/your-path-to-fontawesome/css/brands.css" rel="stylesheet">
            <link href="/your-path-to-fontawesome/css/solid.css" rel="stylesheet">

            <!-- custom styling for all icons -->
            i.fas,
            i.fab {
              border: 1px solid red;
            }

            <!-- custom styling for specific icons -->
            .fa-fish {
              color: salmon;
            }

            .fa-frog {
              color: green;
            }

            .fa-user-ninja.vanished {
              opacity: 0.0;
            }

            .fa-facebook {
              color: rgb(59, 91, 152);
            }
          </head>
          <body>
            <i class="fas fa-fish"></i>
            <i class="fas fa-frog"></i>
            <i class="fas fa-user-ninja vanished"></i>
            <i class="fab fa-facebook"></i>
          </body>



### 使用SVG + JS框架编写自定义CSS

使用我们的SVG框架时，请记住，默认情况下，基于Font Awesome的&lt;i&gt; DOM元素将替换为新的&lt;svg&gt;元素。 请确保您的CSS规则对应正确的元素。

<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@5.13.0/css/all.min.css">
