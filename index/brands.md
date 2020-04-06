# 品牌图标(Simple Icons) 使用教程


Simple Icon收录了超过1000个免费品牌SVG图标。项目地址：[simple-icons/simple-icons](https://github.com/simple-icons/simple-icons)，这个项目由[Dan Leech](https://twitter.com/bathtype)发起。
[IconHelper.cn](https://iconhelper.cn)对其进行了整理，可以用中文搜索相同图标，项目地址：<a href="https://brands.iconhelper.cn" target="_blank">品牌图标(Simple Icon)中文搜索</a>。



## 用法

### 一般用法

可以直接在[brands.iconHelper.cn](https://brands.iconhelper.cn)搜索对应的图标，通过下载或复制按钮下载或复制图标，支持Png或svg格式。下载之前可以更改图标的大小和颜色。


### CDN Usage

你也可以通过[JSDelivr](https://www.jsdelivr.com/package/npm/simple-icons)、[Unpkg](https://unpkg.com)来使用：


```html

<img height="32" width="32" src="https://cdn.jsdelivr.net/npm/simple-icons@latest/icons/[ICON NAME].svg" />
<img height="32" width="32" src="https://unpkg.com/simple-icons@latest/icons/[ICON NAME].svg" />

```

其中的`[ICON NAME]`需要替换成图标名称：

```html

<img height="32" width="32" src="https://cdn.jsdelivr.net/npm/simple-icons@latest/icons/simpleicons.svg" />
<img height="32" width="32" src="https://unpkg.com/simple-icons@latest/icons/simpleicons.svg" />

```

### Node 用法

你也可以通过NPM包安装使用：

```
$ npm install simple-icons
```

使用方法:

```javascript
const simpleIcons = require('simple-icons');

console.log(simpleIcons.get('Simple Icons'));

/*
{
    title: 'Simple Icons',
    slug: 'simpleicons',
    hex: '111111',
    source: 'https://simpleicons.org/',
    svg: '<svg role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">...</svg>',
    path: 'M12 12v-1.5c-2.484 ...'
}
*/
```

你也可以单独导入所需的图标。如果你是正在使用[webpack](https://webpack.js.org/)编译代码的话，这样对减小包的大小非常有用：

```javascript
const icon = require('simple-icons/icons/simpleicons');

console.log(icon);

/*
{
    title: 'Simple Icons',
    slug: 'simpleicons',
    hex: '111111',
    source: 'https://simpleicons.org/',
    svg: '<svg role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">...</svg>',
    path: 'M12 12v-1.5c-2.484 ...'
}
*/
```

#### TypeScript 用法

Simple Icon包还有TypeScript类型定义，按以下方法使用：


```
$ npm install @types/simple-icons
```

### PHP 用法

可以通过Packagist包进行安装：

```
$ composer require simple-icons/simple-icons
```

这样使用:

```php
<?php

echo file_get_contents('path/to/package/icons/simple-icons.svg');

// <svg role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">...</svg>
?>
```

## 第三方扩展

### WordPress

在WordPress中,你可以通过一个简单的插件来使用，由[@tjtaylo](https://github.com/tjtaylo)创建，在[这里](https://wordpress.org/plugins/simple-icons/)可以找到。


### Drupal

你可以通过一个模块来使用，由[Phil Wolstenholme](https://www.drupal.org/u/phil-wolstenholme)创建，在[这里](https://www.drupal.org/project/simple_icons)可以找到。

### Kirby

在Kirby中,你可以通过一个简单的插件来使用，由[@runxel](https://github.com/runxel)创建，在[这里](https://github.com/runxel/kirby3-simpleicons)可以找到。


### React

在React中,你可以通过一个简单的包来使用，由[@wootsbot](https://github.com/wootsbot)创建，在[这里](https://github.com/mamut-dev/icons-pack/tree/master/packages/react-simple-icons)可以找到。


## icon助手

<a href="https://brands.iconhelper.cn" target="_blank">品牌图标(Simple Icon)中文搜索</a>
