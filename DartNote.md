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

​		这个网址也可以[链接](https://icon.wuruihong.com/)

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

样例代码在github中发布，[链接](https://github.com/londonappbrewery/mi_card_flutter.git)

## Hot Reload

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(
    MyApp()
  );
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        backgroundColor: Colors.blueGrey,
        body: Container(),
      ),
    );
  }
}
```

Hot reload 必须要定义一个build函数，因此这里的函数被拆开成了两半部分。

## Container

Very similar  to a Div.

![image-20220718194752893](https://raw.githubusercontent.com/Karllzy/imagebed/main/img/image-20220718194752893.png)

在开始前，建议从flutter的官方文档开始，[链接](https://docs.flutter.dev/development/ui/widgets)

## Columns() and Rows()

```dart
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        backgroundColor: Colors.blueGrey,
        body: SafeArea(
          child: Row(
            crossAxisAlignment: CrossAxisAlignment.start,
            // verticalDirection: VerticalDirection.up,
            // mainAxisAlignment: MainAxisAlignment.spaceEvenly,
            // center, end, start, spaceBetween
            children: <Widget>[
              Container(
                height: 100.0,
                width: 100.0,
                color: Colors.white,
                child: Text("Container 1"),
// margin: EdgeInsets.symmetric(vertical: 50.0, horizontal: 10.0),
//                 margin: EdgeInsets.fromLTRB(30.0, 10.0, 10.0, 30),
//                 padding: EdgeInsets.all(20.0),
              ),
              Container(width: 100.0, height: 100.0,
              color: Colors.red,
              child: Text('Container 2'),
              ),
              Container(width: 100.0, height: 100.0,
                color: Colors.orange,
                child: Text('Container 2'),
              ),
            ],
          ),
        ),
      ),
    );
  }
}

```

可以参考这个网址上的[cheatsheet](https://medium.com/flutter-community/flutter-layout-cheat-sheet-5363348d037e)

## Tapping into Widget Properties

在mac下使用`ctrl+J`，在win下使用`ctrl+q`,可以查看到相应widget的属性并进行设置。

以CircleAvatar为例就可以使用这种方式找到相应的属性。

## Fonts

可以使用这个网站来获取免费的字体：[网址](https://fonts.google.com/)

新建立一个文件夹`fonts`用来存放相应的字体。并且在相应的yaml文件中进行如下修改：

```dart
  fonts:
    - family: Pacifico
      fonts:
        - asset: fonts/Pacifico.ttf
```

## Icons

图标浏览的[网站](https://www.materialpalette.com/icons)

## Card and ListTile

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(
    MyApp()
  );
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        backgroundColor: Colors.blueGrey,
        body: SafeArea(
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: <Widget>[
              CircleAvatar(
                radius: 50.0,
                foregroundImage: AssetImage('images/id_photo.jpg'),
            ),
              Text("Zhenye Li",
                style: TextStyle(fontFamily: 'Pacifico', fontSize: 30),),
              Text("FLUTTER DEVELOPER",
                style: TextStyle(
                    fontFamily: 'SourceSansPro',
                    fontSize: 15,
                    color: Colors.white70,
                    letterSpacing: 2.5,
                    fontWeight: FontWeight.bold
                ),
              ),
              SizedBox(
                height: 30.0,
                width: 150.0,
                child: Divider(
                  color: Colors.white,
              ),),
              Card(
                margin: EdgeInsets.symmetric(vertical: 5.0, horizontal: 25.0),
                color: Colors.white,
                child: ListTile(
                  leading: Icon(
                    Icons.phone,
                    color: Colors.blueGrey,
                    size: 20,
                  ),
                  title: Text(
                    '+86 132 2266 8478',
                    style: TextStyle(
                        color: Colors.blueGrey,
                        fontSize: 20,
                        fontFamily: 'SourceSansPro'
                    ),
                  ),
                )
              ),
              Card(
                margin: EdgeInsets.symmetric(vertical: 5.0, horizontal: 25.0),
                color: Colors.white,
                child: ListTile(
                  leading: Icon(
                    Icons.email,
                    color: Colors.blueGrey,
                    size: 20,
                  ),
                  title: Text(
                    'li.zhenye@qq.com',
                    style: TextStyle(
                        color: Colors.blueGrey,
                        fontSize: 20,
                        fontFamily: 'SourceSansPro'
                    ),
                  ),
                ),
              )
            ]
          )
        ),
      ),
    );
  }
}
```

# Dicee

![image-20220719195110155](https://raw.githubusercontent.com/Karllzy/imagebed/main/img/image-20220719195110155.png)

## Expanded Widget

为了能够拓展到整个整个页面，需要使用Expanded， 其中flex是比较重要的属性。

```dart
class DicePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Row(
      children: <Widget>[
        Expanded(
          flex: 2,
          child: Image(
            image: AssetImage('images/dice1.png'),
          ),
        ),
        Expanded(
          flex: 1,
          child: Image(
            image: AssetImage('images/dice1.png'),
          ),
        ),
      ],
    );
  }
}
```

![image-20220719202110594](https://raw.githubusercontent.com/Karllzy/imagebed/main/img/image-20220719202110594.png)

关于image

```dart
Image(image: AssetImage('images/dice1.png'),),
```

和这个一样：

```dart
Image.asset('images/dice1.png'),
```



## Insert Widget

- 方法一： 使用Flutter Outline， 然后使用widget tree进行居中

- 方法二： 使用Warp with New Widget

## TextButton

加入按钮时，可以让图片被更换。

需要给出 onPressed方法

```dart
import 'package:flutter/material.dart';

void main() {
  return runApp(
    MaterialApp(
      home: Scaffold(
        backgroundColor: Colors.red,
        appBar: AppBar(
          title: Text('Dicee'),
          backgroundColor: Colors.red,
        ),
        body: DicePage(),
      ),
    ),
  );
}

class DicePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Center(
      child: Row(
        children: <Widget>[
          Expanded(
            flex: 1,
            child: TextButton(
              onPressed: (){
                print("Left Button pressed");
              },
              child: Image.asset('images/dice6.png')),
          ),
          Expanded(
            flex: 1,
            child: TextButton(
              onPressed: (){
                print("Left Button pressed");
              },
              child: Image.asset('images/dice1.png')),
            ),
        ],
      ),
    );
  }
}
```

## Dart Function

Dart 当中匿名函数和函数的写法：

```dart
(){}
void change () {}
```

## Set State

使用设置状态的方式，可以修改页面树当中脏了的部分

```dart
class DicePage extends StatefulWidget {
  @override
  State<DicePage> createState() => _DicePageState();
}

class _DicePageState extends State<DicePage> {
  int leftDiceNumber = 6;
  int rightDiceNumber = 1;

  @override
  Widget build(BuildContext context) {
    return Center(
      child: Row(
        children: <Widget>[
          Expanded(
            flex: 1,
            child: TextButton(
                onPressed: (){
                  setState(() {
                    leftDiceNumber = 1;
                    print('leftDiceNumber = $leftDiceNumber');
                  });
                },
                child: Image.asset('images/dice$leftDiceNumber.png')),
          ),
          Expanded(
            flex: 1,
            child: TextButton(
                onPressed: (){
                  rightDiceNumber = 1;
                },
                child: Image.asset('images/dice$rightDiceNumber.png')),
          ),
        ],
      ),
    );
  }
}
```

就像上边那样，使用`setState((){})`那么这个匿名函数里头的东西就会被改变了。

# Magic 8 Ball

## code

```dart
import 'package:flutter/material.dart';
import 'dart:math';

void main() => runApp(
      MaterialApp(
        home: Scaffold(
          appBar: AppBar(
            backgroundColor: Colors.blue.shade900,
            title: Text(
                "Ask Me Anything",
            ),
          ),
          body: BallPage(),
        )
      ),
    );

class BallPage extends StatefulWidget {
  @override
  State<BallPage> createState() => _BallPageState();
}

class _BallPageState extends State<BallPage> {
  int ballIdx = 1;
  @override
  Widget build(BuildContext context) {
    return Container(
      color: Colors.blue,
      child: Center(
        child: TextButton(
            onPressed: (){
              setState(() {
                ballIdx = Random().nextInt(5) + 1;
              });
            },
            child: Image.asset('images/ball$ballIdx.png',)
        ),
      ),
    );
  }
}
```

## 效果

![截屏2022-07-20 14.30.38](https://raw.githubusercontent.com/Karllzy/imagebed/main/img/%E6%88%AA%E5%B1%8F2022-07-20%2014.30.38.png)

# Xylophone

项目材料地址： [链接](https://github.com/londonappbrewery/xylophone-flutter.git)

## Flutter Packages

**What is Packages?**

>  是别人创造的开源代码，你可以添加到你自己的项目当中去。

**Where to Find ?**

> 可以从这个链接去找[🔗](https://pub.dev/)

在主要版本前加入^可以限制版本不变

在网站上点击install页面，把东西拷贝进yaml文件里，然后pub get，结束。

在你的main.dart里头就可以直接使用了。

## Play Sound

```dart
import 'package:audioplayers/audioplayers.dart';
final player = AudioPlayer();
player.play(AssetSource('note.wav'));
```

## Repeat Version

```dart
SafeArea(
          child: Expanded(
            child: Column(
              mainAxisAlignment: MainAxisAlignment.center,
              children: <Widget>[
                Expanded(child: TextButton(
                  onPressed: (){
                    final player = AudioPlayer();
                    player.play(AssetSource('note1.wav'));
                  },
                  child: Container(
                    color: Colors.red,
                    child: Center(
                      child: Text(
                        "Do",
                        textAlign: TextAlign.center,
                        style: TextStyle(
                          fontFamily: 'Pica',
                          color: Colors.black,
                        ),
                      ),
                    ),
                  ),
                ),),
                Expanded(child: TextButton(
                  onPressed: (){
                    final player = AudioPlayer();
                    player.play(AssetSource('note2.wav'));
                  },
                  child: Container(
                    color: Colors.orange,
                    child: Center(
                      child: Text(
                        "Re",
                        textAlign: TextAlign.center,
                        style: TextStyle(
                          fontFamily: 'Pica',
                          color: Colors.black,
                        ),
                      ),
                    ),
                  ),
                ),),
                Expanded(child: TextButton(
                  onPressed: (){
                    final player = AudioPlayer();
                    player.play(AssetSource('note3.wav'));
                  },
                  child: Container(
                    color: Colors.yellow,
                    child: Center(
                      child: Text(
                        "Mi",
                        textAlign: TextAlign.center,
                        style: TextStyle(
                          fontFamily: 'Pica',
                          color: Colors.black,
                        ),
                      ),
                    ),
                  ),
                ),),
                Expanded(child: TextButton(
                  onPressed: (){
                    final player = AudioPlayer();
                    player.play(AssetSource('note4.wav'));
                  },
                  child: Container(
                    color: Colors.green,
                    child: Center(
                      child: Text(
                        "Fa",
                        textAlign: TextAlign.center,
                        style: TextStyle(
                          fontFamily: 'Pica',
                          color: Colors.black,
                        ),
                      ),
                    ),
                  ),
                ),),
                Expanded(child: TextButton(
                  onPressed: (){
                    final player = AudioPlayer();
                    player.play(AssetSource('note5.wav'));
                  },
                  child: Container(
                    color: Colors.indigo,
                    child: Center(
                      child: Text(
                        "So",
                        textAlign: TextAlign.center,
                        style: TextStyle(
                          fontFamily: 'Pica',
                          color: Colors.black,
                        ),
                      ),
                    ),
                  ),
                ),),
                Expanded(child: TextButton(
                  onPressed: (){
                    final player = AudioPlayer();
                    player.play(AssetSource('note6.wav'));
                  },
                  child: Container(
                    color: Colors.blue,
                    child: Center(
                      child: Text(
                        "La",
                        textAlign: TextAlign.center,
                        style: TextStyle(
                          fontFamily: 'Pica',
                          color: Colors.black,
                        ),
                      ),
                    ),
                  ),
                ),),
                Expanded(child: TextButton(
                  onPressed: (){
                    final player = AudioPlayer();
                    player.play(AssetSource('note7.wav'));
                  },
                  child: Container(
                    color: Colors.purple,
                    child: Center(
                      child: Text(
                        "Ti",
                        textAlign: TextAlign.center,
                        style: TextStyle(
                          fontFamily: 'Pica',
                          color: Colors.black,
                        ),
                      ),
                    ),
                  ),
                ),),
              ]
            ),
          ),
        ),
```

## Function Version

![IMG_B424F31C1D04-1](https://raw.githubusercontent.com/Karllzy/imagebed/main/img/IMG_B424F31C1D04-1.jpeg)

![IMG_FE28D411E8B6-1](https://raw.githubusercontent.com/Karllzy/imagebed/main/img/IMG_FE28D411E8B6-1.jpeg)

## Arrow Function (lambda)

```dart
void main() => runApp(LittleSondPage());

void main(){
    LittleSoundPage();
}
```

## Final Version

```dart
import 'package:flutter/material.dart';
import 'package:audioplayers/audioplayers.dart';

void main() => runApp(LittleSondPage());

class LittleSondPage extends StatelessWidget {
  void playSound(int soundIdx){
    final player = AudioPlayer();
    player.play(
      AssetSource('note$soundIdx.wav'),
    );
  }

  Widget buildKey({Color? buttonColor, buttonStr, soundIdx}){
    return TextButton(
      onPressed: (){
        playSound(soundIdx);
      },
      child: Container(
        width: double.infinity,
        height: 70,
        color: buttonColor,
        child: Center(
          child:Text(
              buttonStr,
              textAlign: TextAlign.center,
              style: TextStyle(
                fontFamily: 'Pica',
                color: Colors.black,
              ),
            ),
          ),
      ),
    );
  }

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: Text(
            "Little Sound",
            style: TextStyle(
              fontFamily: "Pica",
            ),
        ),
          backgroundColor: Colors.blueAccent.shade400,
        ),
        body: SafeArea(
          child: Column(
              mainAxisAlignment: MainAxisAlignment.center,
              children: <Widget>[
                buildKey(buttonColor: Colors.red, buttonStr: 'Do', soundIdx: 1),
                buildKey(buttonColor: Colors.orange, buttonStr: 'Re', soundIdx: 2),
                buildKey(buttonColor: Colors.yellow, buttonStr: 'Mi', soundIdx: 3),
                buildKey(buttonColor: Colors.green, buttonStr: 'Fa', soundIdx: 4),
                buildKey(buttonColor: Colors.indigo, buttonStr: 'So', soundIdx: 5),
                buildKey(buttonColor: Colors.blue, buttonStr: 'La', soundIdx: 6),
                buildKey(buttonColor: Colors.purple, buttonStr: 'Ti', soundIdx: 7)
              ]
            ),
          ),
        ),
    );
  }
}
```

# Quizzler

起始项目， [链接](https://github.com/londonappbrewery/quizzler-flutter.git)

## List

```dart
List<Icon> scoreKeeper = [];
```

## Class

```dart
class Question {
  String questionText;
  bool questionAnswer;

  Question({String q, bool a}) {
    questionText = q;
    questionAnswer = a;
  }
}

List<Question> questionBank = [
    Question(q: 'You can lead a cow down stairs but not up stairs.', a: false),
    Question(q: 'Approximately one quarter of human bones are in the feet.', a: true),
    Question(q: 'A slug\'s blood is green.', a: true),
  ];
```

## 私有变量

```dart
_questionBank = []
```

## 类的4大支柱

- 抽象Abstraction

- 封装Encapsulation

  使用私有变量_private

- 继承Inheritance

  使用extends

- 多态Polymorphism

​		使用@override

## Class Constructors

- dart存在默认的构造函数

- Dart当中的构造函数和类别名称相同
- 有一些语法糖

```dart
void main() {
    Human jenny = Human(height: 15);
}

class Human {
    double height;
    
    Human({double height}) {
        this.height = height
    };
    
    Human({this.height, this.weight});
}
```

# BMI Calculator

主题网站推荐： [dribble](https://dribbble.com/)

## Flutter Themes

取色工具ColorZilla

```dart
import 'package:flutter/material.dart';
import 'input_page.dart';

void main() => runApp(BMICalculator());

class BMICalculator extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      theme: ThemeData.dark().copyWith(
        scaffoldBackgroundColor: Color(0xFF090D22),
        colorScheme: ColorScheme.light().copyWith(
          primary: Color(0xFF020A18),
          background: Color(0xFF090D22),
          onBackground: Colors.red,
        ),
        ),
      home: InputPage(),
    );
  }
}
```

## Refactor Widget

