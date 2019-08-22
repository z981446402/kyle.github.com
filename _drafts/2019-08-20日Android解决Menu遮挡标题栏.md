---
layout: post
title: Gradle 配置技巧
published: true
categories: [Android]
author: Kyle
tags: gradle
---

    <style name="OverflowMenu" parent="Base.Widget.AppCompat.PopupMenu.Overflow">
        <item name="overlapAnchor">false</item>
    </style>


    <style name="AppTheme.Base" parent="Theme.AppCompat.Light.NoActionBar">
        <!-- Customize your theme here. -->
        <item name="colorPrimary">@color/material_white</item>
        <item name="colorPrimaryDark">@color/material_white</item>
        <item name="colorAccent">@color/c_dark</item>
        <item name="android:windowBackground">@color/c_page_bg</item>
        <item name="windowActionBar">false</item>
        <item name="android:windowNoTitle">true</item>
        <item name="android:actionMenuTextAppearance">@style/MenuTextStyle</item>
        <item name="android:windowAnimationStyle">@style/GolfAnimation</item>
        <!-- 使用 API Level 22 編譯的話，要拿掉前綴字 -->
        <item name="windowNoTitle">true</item>

        <!--设置menu中item的图标颜色-->
        <item name="autoCompleteTextViewStyle">@style/cursorColor</item>
        <item name="android:textColorSecondary">#ffffff</item>
        <item name="selectableItemBackground">@drawable/select_white</item>
        <item name="android:textColorHint">@color/main_grey</item>
        <item name="actionOverflowMenuStyle">@style/OverflowMenu</item>
    </style>