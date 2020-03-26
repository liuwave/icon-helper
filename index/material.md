

#  Material Design Icons 使用教程




## 通过网页字体/SCSS (Webfont / SCSS	) :<a target="_blank" href="https://github.com/Templarian/MaterialDesign-Webfont">	MaterialDesign-Webfont</a>



首先引入 CSS文件

    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@mdi/font@5.0.45/css/materialdesignicons.min.css">
    
    
在页面中加入代码(用`span`或者 `i`包裹)：

    <span class="mdi mdi-name"></span>
    
效果如下：

<span class="mdi mdi-book-account mdi-48px"></span>


### 大小

<span class="mdi mdi-book-account mdi-18px ml-3"></span> mdi-18px
<span class="mdi mdi-book-account mdi-24px ml-3"></span> mdi-24px
<span class="mdi mdi-book-account mdi-36px ml-3"></span> mdi-36px
<span class="mdi mdi-book-account mdi-48px ml-3"></span> mdi-48px


### 角度


<span class="mdi mdi-book-account mdi-rotate-45 mdi-36px ml-3"></span>mdi-rotate-45
<span class="mdi mdi-book-account mdi-rotate-90 mdi-36px ml-3"></span>mdi-rotate-90
<span class="mdi mdi-book-account mdi-rotate-135 mdi-36px ml-3"></span>mdi-rotate-135
<span class="mdi mdi-book-account mdi-rotate-180 mdi-36px ml-3"></span>mdi-rotate-180
<span class="mdi mdi-book-account mdi-rotate-225 mdi-36px ml-3"></span>mdi-rotate-225
<span class="mdi mdi-book-account mdi-rotate-170 mdi-36px ml-3"></span>mdi-rotate-270
<span class="mdi mdi-book-account mdi-rotate-315 mdi-36px ml-3">mdi-rotate-315</span>


### 翻转


<span class="mdi mdi-book-account mdi-flip-h mdi-36px ml-3">mdi-flip-h</span>
<span class="mdi mdi-book-account mdi-flip-v mdi-36px ml-3"></span>mdi-flip-v



### 旋转

<span class="mdi mdi-book-account mdi-spin mdi-36px ml-3">mdi-spin</span>
<span class="mdi mdi-spin mdi-loading mdi-spin  mdi-36px ml-3">mdi-spin</span>


### 颜色

<div style="background:#212529" >
<span class="mdi mdi-book-account mdi-light mdi-36px ml-3">mdi-light</span>
<span 
class="mdi mdi-book-account mdi-light mdi-inactive mdi-36px ml-3">mdi-light mdi-inactive</span>
</div>
<div>
<span class="mdi mdi-book-account mdi-dark mdi-36px ml-3">mdi-dark</span>
<span class="mdi mdi-book-account mdi-dark mdi-inactive mdi-36px ml-3">mdi-dark mdi-inactive</span>
</div>


## 通过 JavaScript/TypeScript:<a target="_blank" href="https://github.com/Templarian/MaterialDesign-JS">	MaterialDesign-JS</a>




首先安装`@mdi/js`

  npm install @mdi/js

用法：

  import { mdiAccount } from '@mdi/js'

  console.log(mdiAccount); // "M...Z"
  
  
 ## ReactJS :<a target="_blank" href="https://github.com/Templarian/MaterialDesign-React">MaterialDesign-React</a>
 
通过这个模块，在React中，Material Design Icons可以被当成自定义组件使用。

安装`@mdi/react`


  npm install @mdi/react --save-dev

示例

	import React, { Component } from 'react';
	import Icon from '@mdi/react';
	import { mdiAccount } from '@mdi/js';

	class App extends Component {
	  render() {
		return (
		  <Icon path={mdiAccount}
			size={1}
			horizontal
			vertical
			rotate={90}
			color="red"/>
		);
	  }
	} 
	
Stack用法
	
		import React, { Component } from 'react';
    	import Icon, { Stack } from '@mdi/react';
    	import { mdiAccount, mdiBlockHelper } from '@mdi/js';
    
    	class App extends Component {
    	  render() {
    		return (
    		  <Stack color="#444">
    			<Icon path={mdiAccount}/>
    			<Icon path={mdiBlockHelper}
    			  color="red"/>
    		  </Stack>
    		);
    	  }
    	} 
    	
## SVG / Meta.json	:    	<a target="_blank" href="https://github.com/Templarian/MaterialDesign-SVG">	MaterialDesign-SVG</a>
      
直接安装下载即可使用svg
     
      npm install @mdi/svg          
               
               
## Desktop Font	:    	<a target="_blank" href="https://github.com/Templarian/MaterialDesign-Font">MaterialDesign-Font</a>


 ![](/images/material/desktop-font.png)   

通过<a target="_blank" href="https://material.iconhelper.cn">Material Design Icon助手</a>可以复制字体字符、SVG、codepoint、字符名称，也可以选择尺寸、颜色后进行导出，支持svg/png格式。


        