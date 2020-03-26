






# 使用jQuery和带有JavaScript的SVG

带有JavaScript的Font Awesome SVG与jQuery兼容，但需要一些知识基础。 了解SVG的工作原理以及成功与jQuery集成所需要做的工作。

>  小心！
>
> 此功能要求您使用我们的SVG + JS版本的Font Awesome。


### 从4.x版本升级？

如果这看起来太复杂，也可以考虑使用CSS切换到Web字体。 Font Awesome 5中的每种技术都有其优势，与jQuery集成可能会有些繁琐。 将SVG标记嵌套在&lt;i&gt;标记内可能也会有所帮助。



## 在其父级中嵌套SVG标签

撇开jQuery之类库问题的一种快速方法是允许SVG标签嵌套在父标签中。 这使得事件绑定和其他DOM操作起作用。

首先，我们需要使用JavaScript配置Font Awesome SVG进行嵌套：

               <script src="https://use.fontawesome.com/releases/v5.11.2/js/all.js" data-auto-replace-svg="nest"></script>
    

如果我们在页面上添加&lt;i&gt;标记：

          <i class="fas fa-camera"></i>
    

SVG图标呈现在&lt;i&gt;标签内：

          <i data-fa-i2svg>
            <svg class="svg-inline--fa fa-camera fa-w-16" aria-hidden="true" data-prefix="fas" data-icon="camera" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512" data-fa-i2svg="">
              <path fill="currentColor" d="M188.12 210.74L142.86 256l45.25 45.25L233.37 256l-45.25-45.26zm113.13-22.62L256 142.86l-45.25 45.25L256 233.37l45.25-45.25zm-90.5 135.76L256 369.14l45.26-45.26L256 278.63l-45.25 45.25zM256 0C114.62 0 0 114.62 0 256s114.62 256 256 256 256-114.62 256-256S397.38 0 256 0zm186.68 295.6l-11.31 11.31c-3.12 3.12-8.19 3.12-11.31 0l-28.29-28.29-45.25 45.25 33.94 33.94 16.97-16.97c3.12-3.12 8.19-3.12 11.31 0l11.31 11.31c3.12 3.12 3.12 8.19 0 11.31l-16.97 16.97 16.97 16.97c3.12 3.12 3.12 8.19 0 11.31l-11.31 11.31c-3.12 3.12-8.19 3.12-11.31 0l-16.97-16.97-16.97 16.97c-3.12 3.12-8.19 3.12-11.31 0l-11.31-11.31c-3.12-3.12-3.12-8.19 0-11.31l16.97-16.97-33.94-33.94-45.26 45.26 28.29 28.29c3.12 3.12 3.12 8.19 0 11.31l-11.31 11.31c-3.12 3.12-8.19 3.12-11.31 0L256 414.39l-28.29 28.29c-3.12 3.12-8.19 3.12-11.31 0l-11.31-11.31c-3.12-3.12-3.12-8.19 0-11.31l28.29-28.29-45.25-45.26-33.94 33.94 16.97 16.97c3.12 3.12 3.12 8.19 0 11.31l-11.31 11.31c-3.12 3.12-8.19 3.12-11.31 0l-16.97-16.97-16.97 16.97c-3.12 3.12-8.19 3.12-11.31 0l-11.31-11.31c-3.12-3.12-3.12-8.19 0-11.31l16.97-16.97-16.97-16.97c-3.12-3.12-3.12-8.19 0-11.31l11.31-11.31c3.12-3.12 8.19-3.12 11.31 0l16.97 16.97 33.94-33.94-45.25-45.25-28.29 28.29c-3.12 3.12-8.19 3.12-11.31 0L69.32 295.6c-3.12-3.12-3.12-8.19 0-11.31L97.61 256l-28.29-28.29c-3.12-3.12-3.12-8.19 0-11.31l11.31-11.31c3.12-3.12 8.19-3.12 11.31 0l28.29 28.29 45.25-45.26-33.94-33.94-16.97 16.97c-3.12 3.12-8.19 3.12-11.31 0l-11.31-11.31c-3.12-3.12-3.12-8.19 0-11.31l16.97-16.97-16.97-16.97c-3.12-3.12-3.12-8.19 0-11.31l11.31-11.31c3.12-3.12 8.19-3.12 11.31 0l16.97 16.97 16.97-16.97c3.12-3.12 8.19-3.12 11.31 0l11.31 11.31c3.12 3.12 3.12 8.19 0 11.31l-16.97 16.97 33.94 33.94 45.26-45.25-28.29-28.29c-3.12-3.12-3.12-8.19 0-11.31l11.31-11.31c3.12-3.12 8.19-3.12 11.31 0L256 97.61l28.29-28.29c3.12-3.12 8.19-3.12 11.31 0l11.31 11.31c3.12 3.12 3.12 8.19 0 11.31l-28.29 28.29 45.26 45.25 33.94-33.94-16.97-16.97c-3.12-3.12-3.12-8.19 0-11.31l11.31-11.31c3.12-3.12 8.19-3.12 11.31 0l16.97 16.97 16.97-16.97c3.12-3.12 8.19-3.12 11.31 0l11.31 11.31c3.12 3.12 3.12 8.19 0 11.31l-16.97 16.97 16.97 16.97c3.12 3.12 3.12 8.19 0 11.31l-11.31 11.31c-3.12 3.12-8.19 3.12-11.31 0l-16.97-16.97-33.94 33.94 45.25 45.26 28.29-28.29c3.12-3.12 8.19-3.12 11.31 0l11.31 11.31c3.12 3.12 3.12 8.19 0 11.31L414.39 256l28.29 28.28a8.015 8.015 0 0 1 0 11.32zM278.63 256l45.26 45.25L369.14 256l-45.25-45.26L278.63 256z">
              </path>
            </svg>
          </i>
    

## 什么是data-fa-i2svg？

Font Awesome使用此特殊标记来标记已渲染为SVG图标的元素。 字符“ i2svg”是“ SVG的i标签”的缩写。

## 如果不嵌套，这就是您需要知道的:

该库查找看起来像图标的标签：

  <i class="fas fa-coffee" data-fa-mask="fas fa-circle"></i>

它们被替换为新的svg元素：

          <svg class="svg-inline--fa fa-coffee fa-w-20" aria-hidden="true" data-fa-i2svg="" data-prefix="fas" data-icon="coffee" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 640 512"><path fill="currentColor" d="M192 384h192c53 0 96-43 96-96h32c70.6 0 128-57.4 128-128S582.6 32 512 32H120c-13.3 0-24 10.7-24 24v232c0 53 43 96 96 96zM512 96c35.3 0 64 28.7 64 64s-28.7 64-64 64h-32V96h32zm47.7 384H48.3c-47.6 0-61-64-36-64h583.3c25 0 11.8 64-35.9 64z"></path></svg>
          <!-- <i class="fas fa-coffee"></i> -->
        
    

## 它是怎么运作的？

*   1.它寻找类似于fas fa-coffee的DOM元素

*   2.它找出前缀（fas），图标（coffee）之类的东西

*   3.它计划在下一个合适的时间点替换&lt;i&gt;元素

*   4.当浏览器准备就绪时，&lt;i&gt; DOM元素将替换为新的&lt;svg&gt;元素

*   5.为了方便起见，在新的&lt;svg&gt;元素下方添加了表示原始HTML的注释。

## 为什么这很重要？

由于替换了元素，因此对该元素的所有绑定都将丢失，并且此示例无法正常工作：

          <nav>
            <ul style="list-style: none; margin: 0; padding: 0;">
              <li><i class="fa fa-user fa-2x"></i></li>
            </ul>
          </nav>

          <script>
            document.addEventListener('DOMContentLoaded', function () {
              $('nav i').on('click', function () {  // the i element will not exist once the icon is rendered
                alert('You will never see this');
              });
            });
          </script>
    

## 该示例有效，是因为它不依赖于&lt;i&gt;元素：

            <ul style="list-style: none; margin: 0; padding: 0;">
              <li><i class="fa fa-user fa-2x"></i></li>
            </ul>
          </nav>

          <script>
            document.addEventListener('DOMContentLoaded', function () {
              $('nav li').on('click', function () {  // we are letting the li bind to the event
                alert('This works, though');
              });
            });
          </script>
        

    
    

如果确实需要将事件附加到图标，则可以使用data-fa-i2svg属性，但需要允许动态创建svg元素。

将事件附加到父级或更高并过滤图标：

          <nav>
            <ul style="list-style: none; margin: 0; padding: 0;">
              <li><i class="fa fa-user fa-2x"></i></li>
            </ul>
          </nav>

          <script>
            document.addEventListener('DOMContentLoaded', function () {
              $('nav').on('click', '[data-fa-i2svg]', function () {
                alert('You clicked the icon itself');
              });
            });
          </script>
        



### 避免创建对图标的JavaScript变量引用

由于Font Awesome正在动态替换和修改您的图标，因此对图标的任何保留引用都无法按预期工作。



 这样行不通：

          <nav>
            <ul>
              <li><i class="fa fa-user fa-2x"></i></li>
            </ul>
          </nav>

          <script>
            document.addEventListener('DOMContentLoaded', function () {
              var icon = $('nav i')

              $('nav li').on('click', '[data-fa-i2svg]', function () {
                icon.addClass('active');  // This has no effect, the original icon has been replaced
              });
            });
          </script>
        

    
## 通过更改类来更改图标


          <button>Open up <i class="fa fa-angle-right"></i></button>

          <script>
            document.addEventListener('DOMContentLoaded', function () {
              $('button').on('click', function () {
                $(this)
                  .find('[data-fa-i2svg]')
                  .toggleClass('fa-angle-down')
                  .toggleClass('fa-angle-right');
              });
            });
          </script>
        