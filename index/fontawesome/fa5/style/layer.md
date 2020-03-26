







# 分层、文本和计数器

> ## 小心！
> 
> 此功能要求您使用我们的SVG + JS版本的Font Awesome。

图层是一种将图标和文本视觉上彼此叠加的新方法，取代了我们的经典图标堆栈。 通过这种新方法，您可以使用2个以上的图标。

当您不希望显示页面背景时，或者当您想使用多种颜色，在图标上分层放置多个图标，在文本上放置文本或在计数器上使用多个图层计数器时，这些图层就非常有用。 为了清晰，在示例中，我们在图层上添加了背景色，以便您可以看到效果。




![demo](/images/fontawesome/fa5/layer-demo-1.png)

        






          <div class="fa-4x">
            <span class="fa-layers fa-fw" style="background:MistyRose">
              <i class="fas fa-circle" style="color:Tomato"></i>
              <i class="fa-inverse fas fa-times" data-fa-transform="shrink-6"></i>
            </span>

            <span class="fa-layers fa-fw" style="background:MistyRose">
              <i class="fas fa-bookmark"></i>
              <i class="fa-inverse fas fa-heart" data-fa-transform="shrink-10 up-2" style="color:Tomato"></i>
            </span>

            <span class="fa-layers fa-fw" style="background:MistyRose">
              <i class="fas fa-play" data-fa-transform="rotate--90 grow-2"></i>
              <i class="fas fa-sun fa-inverse" data-fa-transform="shrink-10 up-2"></i>
              <i class="fas fa-moon fa-inverse" data-fa-transform="shrink-11 down-4.2 left-4"></i>
              <i class="fas fa-star fa-inverse" data-fa-transform="shrink-11 down-4.2 right-4"></i>
            </span>

            <span class="fa-layers fa-fw" style="background:MistyRose">
              <i class="fas fa-calendar"></i>
              <span class="fa-layers-text fa-inverse" data-fa-transform="shrink-8 down-3" style="font-weight:900">27</span>
            </span>

            <span class="fa-layers fa-fw" style="background:MistyRose">
              <i class="fas fa-certificate"></i>
              <span class="fa-layers-text fa-inverse" data-fa-transform="shrink-11.5 rotate--30" style="font-weight:900">NEW</span>
            </span>

            <span class="fa-layers fa-fw" style="background:MistyRose">
              <i class="fas fa-envelope"></i>
              <span class="fa-layers-counter" style="background:Tomato">1,419</span>
            </span>
          </div>
        





- fa-layers
包装您的图标或文字堆栈。 您可能还希望添加fa-fw类，以便您的图层对齐。


- Inner icons
直接在fa-layers元素内添加任意数量的图标。 图标与顶部的最后一个图标堆叠在一起。


- fa-layers-text
在fa-layers元素内添加以将文本放在图标顶部。 与data-fa-transform结合使用可实现完全控制。


- fa-layers-counter
在图标的右上方添加一个计数器。 可以使用fa-layers-bottom-left，fa-layers-bottom-right，fa-layers-top-left和默认的fa-layers-top-right来定位。 溢出文本用省略号截断。
