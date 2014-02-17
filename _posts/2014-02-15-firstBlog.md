---
layout: post
category : kevin
tagline: "个人博客的起步"
tags: [kevin]
title: 第一篇博客
---
{% include JB/setup %}

## 个人博客起步
去年就一直想着搭建个人博客，一直拖了好久，过年回来抽个周末争取把这件事情搞定。
博客的搭建使用Github的Pages功能。

<!--more-->
#Java样式测试代码如下

	public classIOException extends Exception{  
    //定义异常的原因  
    publicIOException(String message){  
        super(message);  
	  
      
        //定义异常原因，并携带原始的异常  
        publicIOException(String message,Throwable cause){  
            super(message,cause);  
        }  
      
        //保留原始异常信息  
        publicIOExcepiton(Throwable cause){  
            super(cause);  
        }  
    }
	
#js测试代码如下
	
	<script type="text/javascript" src="js/code/prettify.js"></script>
	<script type="text/javascript" src="js/jquery-1.8.0.min.js"></script>
	<script type="text/javascript">
	$(function(){
		$("pre").addClass("prettyprint linenums");
		prettyPrint();
		$('.entry a').each(function(){
      if($(this).attr("href").indexOf("heiniuhaha") == -1){
        $(this).attr("target", "_blank");
		}
		})
	});
	</script>
	
#Ruby测试代码如下

	# Say hi to everybody
	def say_hi
	if @names.nil?
	puts "..."
	elsif @names.respond_to?("each")
    # @names is a list of some kind, iterate!
    @names.each do |name|
      puts "Hello #{name}!"
    end
	else
    puts "Hello #{@names}!"
	end
	end