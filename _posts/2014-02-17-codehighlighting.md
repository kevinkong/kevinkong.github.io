---
layout: post
category : jeykll
tagline: ""
tags: [jekyll]
title: Jekyll设置代码高亮
---
{% include JB/setup %}


![](http://image.beekka.com/blog/201208/bg2012082505.jpg)

<br>

使用github的pages搭建了个人网站，作为码农，在文章中粘贴一些代码是必须的，那么如何设置支持代码高亮？

<!--more-->

##如何基于Jekyll设置代码高亮
这里使用到了[google-code-prettify][1]这个工具

1、首先去google-code-prettify下载需要的js以及css文件，下载下来后只有一个文件夹

2、把文件夹加入到基于Jekyll的源代码的assets\themes\twitter\js文件夹下

3、同时在assets\themes\twitter\js文件夹下新建一个jquery-1.8.0.min.js文件，加入jquery的代码，具体可以去我的[github][2]中下载

4、在_includes\themes\twitter的default.html文件夹下新增一下代码

	//在文件头引入css样式
	<link href="{{ ASSET_PATH }}/js/google-code-prettify/prettify.css"  rel="stylesheet" type="text/css" media="all"></link>
	//在文件末尾加入以下js代码
	<script type="text/javascript" src="/assets/themes/twitter/js/google-code-prettify/prettify.js"></script>
    <script type="text/javascript" src="/assets/themes/twitter/js/jquery-1.8.0.min.js"></script>
    <script type="text/javascript">
       $(function(){
          $("pre").addClass("prettyprint");//linenums
          prettyPrint();
        });
	</script>



  [1]: https://code.google.com/p/google-code-prettify/
  [2]: https://github.com/kevinkong/kevinkong.github.io/blob/master/assets/themes/twitter/js/jquery-1.8.0.min.js