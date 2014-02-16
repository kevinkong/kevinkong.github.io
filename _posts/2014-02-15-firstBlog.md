---
layout: post
category : 生活
tagline: "个人博客的起步"
tags: [生活]
title: 第一篇博客
---
{% include JB/setup %}

## 个人博客起步
去年就一直想着搭建个人博客，一直拖了好久，过年回来抽个周末争取把这件事情搞定。
博客的搭建使用Github的Pages功能。

<!--more-->
测试代码模块的展示
```java
    public classIOException extends Exception{  
        //定义异常的原因  
        publicIOException(String message){  
            super(message);  
        }  
      
        //定义异常原因，并携带原始的异常  
        publicIOException(String message,Throwable cause){  
            super(message,cause);  
        }  
      
        //保留原始异常信息  
        publicIOExcepiton(Throwable cause){  
            super(cause);  
        }  
    }  
```