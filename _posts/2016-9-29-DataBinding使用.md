---

layout: post
title: 'Android DataBinding使用（一）'
author: Kyle
published: true
tags: [dataBinding]
categories: [Android]

---

### 配置DataBinding框架 ###

----------
在gradle（1.5+）只需在app gradle中配置以下代码即可使用

	android{
	...
	dataBinding{
	        enabled true
	    }
	}

### 简单数据绑定使用###

----------
在下面例子中，控件`tv_name`,`tv_age`分别用来显示`user`的`name`,`age`属性,`et_input`获取用户输入的数据，`tv_input`显示用户输入的数据。


	<?xml version="1.0" encoding="utf-8"?>
	<layout xmlns:android="http://schemas.android.com/apk/res/android"
	        xmlns:tools="http://schemas.android.com/tools">
	
	    <data>
	
	        <variable
	            name="userInput"
	            type="String"/>
	
	        <variable
	            name="user"
	            type="com.kyle.databindingdemo.bean.User"/>
	    </data>
	
	    <LinearLayout
	        android:id="@+id/activity_main"
	        android:layout_width="match_parent"
	        android:layout_height="match_parent"
	        android:orientation="vertical"
	        android:paddingBottom="@dimen/activity_vertical_margin"
	        android:paddingLeft="@dimen/activity_horizontal_margin"
	        android:paddingRight="@dimen/activity_horizontal_margin"
	        android:paddingTop="@dimen/activity_vertical_margin"
	        tools:context="com.kyle.databindingdemo.MainActivity">
	
	        <TextView
				android:id="@+id/tv_name"
	            android:layout_width="wrap_content"
	            android:layout_height="wrap_content"
	            android:text="@{user.name}"/>
	
	        <TextView
				android:id="@+id/tv_age"
	            android:layout_width="wrap_content"
	            android:layout_height="wrap_content"
	            android:text="@{user.age}"/>
	
	        <EditText
				android:id="@+id/et_input"
	            android:layout_width="match_parent"
	            android:layout_height="wrap_content"
	            android:text="@={userInput}"/>
	
	        <TextView
				android:id="@+id/tv_input"
	            android:layout_width="wrap_content"
	            android:layout_height="wrap_content"
	            android:text="@{userInput}"/>
	    </LinearLayout>
	</layout>


#### 布局文件修改 ####


- 根布局修改为`<layout>`，表明这个是数据绑定的布局，数据绑定框架会自动生成{布局文件名}Binding类，例如`activity_main.xml`会生成一个`ActivityMainBinding`类，官方默认命名规则：单词首字母大写，移除下划线，并在最后添加上Binding。
- 添加`<data>`标签，声明绑定数据，支持基本数据类型和自定义类类型
	
		<data>
        <variable
            name="userInput"
            type="String"/>

        <variable
            name="user"
            type="com.kyle.databindingdemo.bean.User"/>
    	</data>
- 通过`@{}`进行数据绑定，通过`@={}`进行双向绑定。

#### Activity文件修改 ####

	ActivityMainBinding mainBinding = DataBindingUtil.setContentView(this,R.layout.activity_main);
	User user = new User("18","jack");
	mainBinding.setUser(user);
- 通过`DataBindingUtil.setContentView()`绑定视图。
- 通过`ActivityMainBinding`可以对视图里的数据进行`get`、`set`操作；布局中View 定义一个 ID，Data Binding 就会为我们生成一个对应的 final 变量。



