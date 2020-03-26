

# 图标动画

需要加载或状态通信图标来旋转吗？ 那就对了。 我们在支持样式中包括了一些基本的动画供您使用。

使用fa-spin类使任何图标旋转，或者使用fa-pulse使其进行8方向旋转。 特别适用于fa-spinner和旋转图标类别中的所有内容。

<div class="fa-3x">
            <i class="fas fa-spinner fa-spin"></i>
            <i class="fas fa-circle-notch fa-spin"></i>
            <i class="fas fa-sync fa-spin"></i>
            <i class="fas fa-cog fa-spin"></i>
            <i class="fas fa-spinner fa-pulse"></i>
            <i class="fas fa-stroopwafel fa-spin"></i>
</div>

          <div class="fa-3x">
            <i class="fas fa-spinner fa-spin"></i>
            <i class="fas fa-circle-notch fa-spin"></i>
            <i class="fas fa-sync fa-spin"></i>
            <i class="fas fa-cog fa-spin"></i>
            <i class="fas fa-spinner fa-pulse"></i>
            <i class="fas fa-stroopwafel fa-spin"></i>
          </div>

## 图标动画+摆动

我们一直在努力使图标在旋转或搏动时保持完美居中。 但是，我们发现一些浏览器和Web字体 + Font Awesome的CSS版本存在问题。 经过大量调查，这似乎是Web字体的普遍问题，而不是我们可以直接解决的问题。 我们确实有几种方法可以解决此问题：

*   切换框架-切换到带有JavaScript版本的SVG，这样做效果更好。
*   设置动画图标的显示-使用 display: block; 。 这似乎对解决此问题有很大帮助。


<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@5.13.0/css/all.min.css">
