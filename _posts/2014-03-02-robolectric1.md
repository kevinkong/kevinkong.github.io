---
layout: post
category : android
tagline: ""
tags: [android,robolectric,单元测试]
title: Android单元测试工具robolectric--环境搭建
---
{% include JB/setup %}


![](http://www.yaco.cc/uploadfile//2011051021/201105102137403208.jpg)


<br>

robolectric是android端的单元测试工具，优势是可以不需要android模拟器、真机环境，只需要JVM环境就可以运行单元测试用例，节省了代码编译、启动模拟器、安装应用等时间，所以运行速度会快非常多，通过robolectric来编写单元测试用例的话和持续集成整合还是比较不错的，可以做到有代码变更，快速运行单元测试用例，快速反馈结果。


针对robolectric的使用打算用我们开源的Android性能测试工具[Emmagee][1]做个demo，尝试如何来编写测试用例。


那第一篇只要就介绍相关的环境搭建，以及运行第一个测试用例了。

<!--more-->

前提：
虽然robolectric运行用例不需要android环境，但是你要测试android应用还是需要搭建相关开发环境的，但是这里就不介绍了，另外下载Emmagee的源代码也需要Git相关知识，这些内容大家自行Google解决。

##下载被测Android工程
1. Github中clone Emmagee的源代码
   	git clone https://github.com/Netease/Emmagee
2. Eclipse中导入Emmagee的Android工程
3. 在Emmagee工程的根目录下新建test文件夹（用于放置测试代码）

##新建Java测试工程
2. Eclipse中File -> New -> Java Project
3. 输入EmmageeTest的项目名称，点击Next
4. 出现工程设置页面，右键src，点击“Removefrom build path”
5. 点击下方的“Link additional source”，选择Emmagee工程中当前新建的test文件夹，点击finish
6. 点击新建Java工程设置页面的“projects” Tab,点击“Add”，把Emmagee工程关联进来，点击Finish，创建Java工程结束，通过这些步骤，将测试工程和被测工程的关联

![](http://lcoalhost:4000/assets/images/1.png)

##配置Java测试工程
1. 在EmmageeTest工程中新建lib文件夹
2. 下载[robolectric-X.X.X-jar-with-dependencies.jar](http://robolectric.org/download/)加入到lib文件夹中
3. 右键EmmageeTest -> Build Path -> Configure Build Path
4. 点击Libraries -> Add Library 选择Junit4，这里需要注意，当前只支持Junit4
5. 点击Libraries -> Add Jars 引入当前加入lib文件夹的robolectric的jar包
6. 点击Libraries -> Add External Jars 引入android.jar和map.jar（这两个jar在android安装路径下会有）
7. jar包引入完成后点击ok，完成配置

##编写第一个测试用例
右键EmmageeTest工程下的test文件夹，新建一个测试类

```java
package com.netease.emmagee.test;

import org.junit.Assert;
import org.junit.Test;
import org.robolectric.RobolectricTestRunner;
import org.junit.runner.RunWith;

import com.netease.qa.emmagee.R;
import com.netease.qa.emmagee.activity.MainPageActivity;

@RunWith(RobolectricTestRunner.class)
public class MainPageActivityTest {
	@Test
	public void beginingTest() throws Exception {
	    String hello = new MainPageActivity().getResources().getString(R.string.bg);
	    Assert.assertEquals(hello, "开始测试");
	}
}

```


##Eclipse中运行第一个测试用例

如果需要通过Eclipse中运行测试用例，必须经过以下配置

1. 右键EmmageeTest -> Run as -> Run configurations
2. 双击 Junit
3. 选择Run all tests in the selected project, package or source folder，点击 search选择 EmmageeTest
4. TestRunner选择Junit4
5. 点击下方的Multiple launchers available Select one…，选择Eclipse Junit Launcher
6. 点击“Arguments” tab，在“Working directory:”中点击“Other”，点击“Workspace”，选择Emmagee工程（不是EmmageeTest工程）
7. 点击ok完成设置
8. 设置完成后右键MainPageActivityTest -> Run as -> Junit Test






  

参考文章：[robolectric](http://robolectric.org/eclipse-quick-start/)官网

  [1]: https://github.com/Netease/Emmagee
  