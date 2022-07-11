# Flutter Note

![封面](https://raw.githubusercontent.com/Karllzy/imagebed/main/img/%E6%88%AA%E5%B1%8F2022-07-11%2000.49.37-20220711011420090.png)

课程链接:[【Udemy付费课程】The Complete 2021 Flutter Development](https://www.bilibili.com/video/BV1ku411v71e?p=2&vd_source=67ddbc392c924ceab4554b5bc519d39a)

# What is Flutter

A tool kit that makes it easy for developers to design beautiful interfaces for all sorts of screen sizes and devices.

It comes with a whole bunch of pre-bulit widgets that make it easy to layout your app.	

# Antomy of Flutter App

一切皆widgets,一个App就是一个WidgetTree

![截屏2022-07-11 01.21.17](https://raw.githubusercontent.com/Karllzy/imagebed/main/img/%E6%88%AA%E5%B1%8F2022-07-11%2001.21.17.png)

Tips:

- Stop typing along about 10 minute, try and understand the purpose of the code. Try to replicate what happened  instead of copying code.
- Type fast praticing [url](keybr.com)
- Cornell Note Taking System
- Double speed

# I am rich

## Creating a Flutter Project

创建一个简单的APP，这个APP的名字叫I am rich.这里是在flutter当中创建的过程。

![截屏2022-07-11 14.27.48](https://raw.githubusercontent.com/Karllzy/imagebed/main/img/%E6%88%AA%E5%B1%8F2022-07-11%2014.27.48.png)

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(
    MaterialApp(
      home: Center(
        child: Text("Hello World"),
      ),
    ),
  );
}
```

## Scaffold App

一种预先制作好的Widget，用来放item的。

关于它的[doc](https://docs-flutter-io.firebaseapp.com/flutter/material/Scaffold-class.html)

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(
    MaterialApp(
        home: Scaffold(
      appBar: AppBar(
        title: Text("I am rich"),
        backgroundColor: Colors.brown,
      ),
      body: Center(
        child: Image(
          image: NetworkImage(
              'https://images.quanjing.com/chineseview010/thu/177-0895.jpg'),
        ),
      ),
      backgroundColor: Colors.blueGrey,
    )),
  );
}
```

程序结构

![下载](https://raw.githubusercontent.com/Karllzy/imagebed/main/img/%E4%B8%8B%E8%BD%BD.png)

