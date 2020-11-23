---
layout: post
title: EditText在代码中设置调用setFilters后，导致xml中maxLength属性失效
published: true
categories: [开发中遇到的问题]
author: Onceok
---
## EditText在代码中设置调用setFilters后，导致xml中maxLength属性失效分析 ##

1.通过源码我们发现maxLength属性来自于TextView中，在初始化可以看到下面一段代码，maxLength最终通过调用setFilters来传入InputFilter实现的


    if (maxlength >= 0) {
        setFilters(new InputFilter[] { new InputFilter.LengthFilter(maxlength) });
	} else {
        setFilters(NO_FILTERS);
    }

2.接下来我们看下setFilters（） 方法，里头接收一个filter数组，每次调用之后就会覆盖之前设置的filter,这也就解释了为什么会出现这个问题

    public void setFilters(InputFilter[] filters) {
        if (filters == null) {
            throw new IllegalArgumentException();
        }

        mFilters = filters;

        if (mText instanceof Editable) {
            setFilters((Editable) mText, filters);
        }
    }