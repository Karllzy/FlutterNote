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

## Local Image and YAML

Modify the YAML file， 同时可以被人类和机器理解的语言，用两个空格表示层级。

```yaml
# The following section is specific to Flutter.
flutter:

  # The following line ensures that the Material Icons font is
  # included with your application, so that you can use the icons in
  # the material Icons class.
  uses-material-design: true

  # To add assets to your application, add an assets section, like this:
  assets:
    - images/
```

添加图片到文件夹下

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
          image: AssetImage('images/diamond.jpeg')
      ),
      ),
      backgroundColor: Colors.blueGrey,
    )),
  );
}
```

## App Icon

1. 图标文件的生成：

​		在这个网站上能够产生appicon,网址是[链接](https://appicon.co)

2. 替换掉一些图标文件：

   安卓的替换位置是`android/appp/src/main/res/mipmap*`

​		ios的替换位置是`ios/Runner/Assets.xcassets/`

3. 生成相应的APP即可

## Deploying to an Android Phone

![截屏2022-07-17 23.44.00](https://raw.githubusercontent.com/Karllzy/imagebed/main/img/%E6%88%AA%E5%B1%8F2022-07-17%2023.44.00.png)

## Deploying to an iPhone

![image-20220718120951956](https://raw.githubusercontent.com/Karllzy/imagebed/main/img/image-20220718120951956.png)

## Some Useful Websites

- [Icons8](https://icons8.com/)
- [Vecteezy](https://www.vecteezy.com/)
- [Canva](canva.com)

# MiCard
