

# 强化变形


> 小心！
> 此功能要求您使用我们的SVG + JS版本的Font Awesome。


借助Font Awesome 5中SVG的强大功能，现在您可以使用data-fa-transform元素属性任意缩放、定位、翻转和旋转图标。 您甚至可以将它们组合起来以获得一些超级有用的效果。

## 缩放比例

强化变形的缩放会影响图标大小，而无需更改或移动容器。 要按比例放大或缩小图标，请使用带有任意值（包括小数）的grow-＃和shrink-＃。 单位是1/16em。 为了清晰，在示例中，我们在图标上添加了背景色，以便您可以看到效果。


![table](/images/fontawesome/fa5/power-transforms-demo-1.png)
    

          <div class="fa-4x">
            <i class="fas fa-seedling" data-fa-transform="shrink-8" style="background:MistyRose"></i>
            <i class="fas fa-seedling" style="background:MistyRose"></i>
            <i class="fas fa-seedling" data-fa-transform="grow-6" style="background:MistyRose"></i>
          </div>
        

## 定位

强化变形的位置会影响图标的位置，而无需更改或移动容器。 要向上，向下，向左或向右移动图标，请使用up-#，down-#，left-＃和right-＃及其任意值，包括小数。 单位是1/16em。 为了清晰，在示例中，我们在图标上添加了背景色，以便您可以看到效果。

![table](/images/fontawesome/fa5/power-transforms-demo-2.png)


          <div class="fa-4x">
            <i class="fas fa-seedling" data-fa-transform="shrink-8" style="background:MistyRose"></i>
            <i class="fas fa-seedling" data-fa-transform="shrink-8 up-6" style="background:MistyRose"></i>
            <i class="fas fa-seedling" data-fa-transform="shrink-8 right-6" style="background:MistyRose"></i>
            <i class="fas fa-seedling" data-fa-transform="shrink-8 down-6" style="background:MistyRose"></i>
            <i class="fas fa-seedling" data-fa-transform="shrink-8 left-6" style="background:MistyRose"></i>
          </div>
        

## 旋转和翻转

强化变形的旋转和翻转会影响图标的角度和反射，而无需更改或移动容器。 要旋转或翻转图标，请使用带有任意值的rotation-＃，flip-v和flip-h的任意组合。 单位是允许带负数的度（请参见示例中的第五个图标）。为了清晰，在示例中，我们在图标上添加了背景色，以便您可以看到效果。

![table](/images/fontawesome/fa5/power-transforms-demo-3.png)

        

          <div class="fa-4x">
            <i class="fas fa-seedling" data-fa-transform="rotate-90" style="background:MistyRose"></i>
            <i class="fas fa-seedling" data-fa-transform="rotate-180" style="background:MistyRose"></i>
            <i class="fas fa-seedling" data-fa-transform="rotate-270" style="background:MistyRose"></i>
            <i class="fas fa-seedling" data-fa-transform="rotate-30" style="background:MistyRose"></i>
            <i class="fas fa-seedling" data-fa-transform="rotate--30" style="background:MistyRose"></i>
            <i class="fas fa-seedling" data-fa-transform="flip-v" style="background:MistyRose"></i>
            <i class="fas fa-seedling" data-fa-transform="flip-h" style="background:MistyRose"></i>
            <i class="fas fa-seedling" data-fa-transform="flip-v flip-h" style="background:MistyRose"></i>
          </div>
        
    



### 您知道吗？

您可以在单个图标上混合并匹配上面提到的强化变形。

