---
layout: post
title: Activity设置为singtask时，startActivityForResult直接回调cancel 
published: true
categories: [开发中遇到的问题]
author: Kyle
---

1.在查看Activity中去源码时，我们可以在startActivityForResult方法中就可以得到答案

    * <p>Note that this method should only be used with Intent protocols
    * that are defined to return a result.  In other protocols (such as
    * {@link Intent#ACTION_MAIN} or {@link Intent#ACTION_VIEW}), you may
    * not get the result when you expect.  For example, if the activity you
    * are launching uses {@link Intent#FLAG_ACTIVITY_NEW_TASK}, it will not
    * run in your task and thus you will immediately receive a cancel result.

2.总结下，我们可以得出结论：不同栈的Activity不能通过startActivityForResult这种形式获取数据