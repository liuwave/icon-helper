

# 堆叠

您可以通过Font Awesome附带的支持样式轻松地堆叠图标。

要堆叠多个图标，请在要堆叠的2个图标的父HTML元素上使用fa-stack类。 然后为常规尺寸的图标添加fa-stack-1x类，为较大的图标添加fa-stack-2x类。 fa-inverse可以与fa-stack-1x一起添加到图标中，以帮助实现剔除效果。 您甚至可以在父级上抛出较大的图标类，以进一步控制大小。

<span class="fa-stack fa-2x">
            <i class="fas fa-square fa-stack-2x"></i>
            <i class="fab fa-twitter fa-stack-1x fa-inverse"></i>
</span>
<span class="fa-stack fa-2x">
            <i class="fas fa-circle fa-stack-2x"></i>
            <i class="fas fa-flag fa-stack-1x fa-inverse"></i>
          </span>
          <span class="fa-stack fa-2x">
            <i class="fas fa-square fa-stack-2x"></i>
            <i class="fas fa-terminal fa-stack-1x fa-inverse"></i>
          </span>
          <span class="fa-stack fa-4x">
            <i class="fas fa-square fa-stack-2x"></i>
            <i class="fas fa-terminal fa-stack-1x fa-inverse"></i>
          </span>
          <span class="fa-stack fa-2x">
            <i class="fas fa-camera fa-stack-1x"></i>
            <i class="fas fa-ban fa-stack-2x" style="color:Tomato"></i>
</span>









          <span class="fa-stack fa-2x">
            <i class="fas fa-square fa-stack-2x"></i>
            <i class="fab fa-twitter fa-stack-1x fa-inverse"></i>
          </span>
          <span class="fa-stack fa-2x">
            <i class="fas fa-circle fa-stack-2x"></i>
            <i class="fas fa-flag fa-stack-1x fa-inverse"></i>
          </span>
          <span class="fa-stack fa-2x">
            <i class="fas fa-square fa-stack-2x"></i>
            <i class="fas fa-terminal fa-stack-1x fa-inverse"></i>
          </span>
          <span class="fa-stack fa-4x">
            <i class="fas fa-square fa-stack-2x"></i>
            <i class="fas fa-terminal fa-stack-1x fa-inverse"></i>
          </span>
          <span class="fa-stack fa-2x">
            <i class="fas fa-camera fa-stack-1x"></i>
            <i class="fas fa-ban fa-stack-2x" style="color:Tomato"></i>
          </span>

## 对齐堆叠和常规图标

您可以在单个图标旁边使用堆叠的图标。 由于堆叠图标由我们框架随附的CSS设置为单个图标大小的两倍，因此您需要缩小堆叠图标的大小或放大单个图标的大小。

<i class="far fa-circle fa-2x"></i>
          <span class="fa-stack" style="vertical-align: top;">
            <i class="far fa-circle fa-stack-2x"></i>
            <i class="fas fa-flag fa-stack-1x"></i>
          </span>
          <span class="fa-stack" style="vertical-align: top;">
            <i class="fas fa-circle fa-stack-2x"></i>
            <i class="fas fa-flag fa-stack-1x fa-inverse"></i>
          </span>
<i class="far fa-circle fa-2x"></i>
        




          <i class="far fa-circle fa-2x"></i>
          <span class="fa-stack" style="vertical-align: top;">
            <i class="far fa-circle fa-stack-2x"></i>
            <i class="fas fa-flag fa-stack-1x"></i>
          </span>
          <span class="fa-stack" style="vertical-align: top;">
            <i class="fas fa-circle fa-stack-2x"></i>
            <i class="fas fa-flag fa-stack-1x fa-inverse"></i>
          </span>
          <i class="far fa-circle fa-2x"></i>
        

### 需要一些自定义CSS

如果需要更改堆叠图标的默认字体大小，则需要编写自己的自定义规则（默认情况下，堆叠图标设置为display：inline-block; vertical-align：middle; ）。


<style>
            .fa-stack { font-size: 0.5em; }
            i { vertical-align: middle; }
          </style>
<i class="far fa-circle"></i>
          <span class="fa-stack">
            <i class="far fa-circle fa-stack-2x"></i>
            <i class="fas fa-flag fa-stack-1x"></i>
          </span>
          <span class="fa-stack">
            <i class="fas fa-circle fa-stack-2x"></i>
            <i class="fas fa-flag fa-stack-1x fa-inverse"></i>
          </span>
<i class="far fa-circle"></i>
        






          <style>
            .fa-stack { font-size: 0.5em; }
            i { vertical-align: middle; }
          </style>

          <i class="far fa-circle"></i>
          <span class="fa-stack">
            <i class="far fa-circle fa-stack-2x"></i>
            <i class="fas fa-flag fa-stack-1x"></i>
          </span>
          <span class="fa-stack">
            <i class="fas fa-circle fa-stack-2x"></i>
            <i class="fas fa-flag fa-stack-1x fa-inverse"></i>
          </span>
          <i class="far fa-circle"></i>
        




### 堆叠时需要更多加强效果吗？

我们的SVG + JS框架提供了强大的遮罩和分层方法，可以更精细地旋转图标！ 如果您打算这样使用Font Awesome，那就试试看。

<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@5.13.0/css/all.min.css">
