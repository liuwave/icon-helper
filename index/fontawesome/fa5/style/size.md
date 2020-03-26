

# 图标尺寸

我们的Web字体 + CSS和SVG + JS框架都包含一些基本控件，可用于在页面UI中调整图标的大小。

## 相对尺寸

图标继承了其父容器的字体大小，从而使它们可以匹配您所呈现的任何文本。 通过以下类，我们可以相对于继承的font-size增大或减小图标的大小。

<i class="fas fa-camera fa-xs"></i>
<i class="fas fa-camera fa-sm"></i>
<i class="fas fa-camera fa-lg"></i>
<i class="fas fa-camera fa-2x"></i>
<i class="fas fa-camera fa-3x"></i>
<i class="fas fa-camera fa-5x"></i>
<i class="fas fa-camera fa-7x"></i>
<i class="fas fa-camera fa-10x"></i>


          <i class="fas fa-camera fa-xs"></i>
          <i class="fas fa-camera fa-sm"></i>
          <i class="fas fa-camera fa-lg"></i>
          <i class="fas fa-camera fa-2x"></i>
          <i class="fas fa-camera fa-3x"></i>
          <i class="fas fa-camera fa-5x"></i>
          <i class="fas fa-camera fa-7x"></i>
          <i class="fas fa-camera fa-10x"></i>

    

这里还有一些示例，您可以在其中查看相对比例。

<div style="font-size: 0.5rem;">
            <i class="fas fa-camera fa-xs"></i>
            <i class="fas fa-camera fa-sm"></i>
            <i class="fas fa-camera fa-lg"></i>
            <i class="fas fa-camera fa-2x"></i>
            <i class="fas fa-camera fa-3x"></i>
            <i class="fas fa-camera fa-5x"></i>
            <i class="fas fa-camera fa-7x"></i>
            <i class="fas fa-camera fa-10x"></i>
</div>
        


          <div style="font-size: 0.5rem;">
            <i class="fas fa-camera fa-xs"></i>
            <i class="fas fa-camera fa-sm"></i>
            <i class="fas fa-camera fa-lg"></i>
            <i class="fas fa-camera fa-2x"></i>
            <i class="fas fa-camera fa-3x"></i>
            <i class="fas fa-camera fa-5x"></i>
            <i class="fas fa-camera fa-7x"></i>
            <i class="fas fa-camera fa-10x"></i>
          </div>
 
    



### 您知道吗？

通过在目标图标的项目CSS中、或直接在引用图标的HTML元素的style属性中设置字体大小，您还可以直接设置图标的大小。



![table](/images/fontawesome/fa5/size-1.png)




## 进阶尺寸定制

如果您使用的是我们的SCSS或Less CSS预处理器，则可以根据自己的比例调整_larger.scss或_larger.less部分。


<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@5.13.0/css/all.min.css">
