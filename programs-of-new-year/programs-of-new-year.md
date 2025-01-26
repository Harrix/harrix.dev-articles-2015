---
date: 2015-12-31
categories:
  - it
  - programming
tags:
  - Java
  - C++
  - Qt
  - Visual Studio
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
permalink-source: https://github.com/Harrix/harrix.dev-articles-2015/blob/main/programs-of-new-year/programs-of-new-year.md
permalink: https://harrix.dev/ru/articles/2015/programs-of-new-year/
lang: ru
---

# Поздравления с Новым годом в виде программ

![Featured image](featured-image.svg)

С Новым годом! Желаю, чтобы все программы компилировались и всё у вас было хорошо!

- [Visual Studio C++](#visual-studio-c)
- [Qt C++](#qt-c)
- [Java](#java)

И это поздравление я написал в виде трех консольных программ.

## Visual Studio C++

```cpp
#include "stdafx.h"
#include <iostream>
using namespace std;

void _tmain(int argc, _TCHAR* argv[])
{
  setlocale(LC_ALL, "RUSSIAN");
  system("color 27");
  cout << "C Новым годом!" << endl;
  cout << "Желаю, чтобы всё было хорошо!" << endl;
  cout << "А программы компилировались с первого раза и правильно!" << endl;
  cin.ignore();
}
```

## Qt C++

```cpp
#include <QCoreApplication>
#include <QTextCodec>
#include <iostream>
using namespace std;

int main(int argc, char *argv[])
{
    QCoreApplication a(argc, argv);

#ifdef Q_OS_WIN32
    QTextCodec::setCodecForLocale(QTextCodec::codecForName("IBM 866"));
#endif

#ifdef Q_OS_LINUX
    QTextCodec::setCodecForLocale(QTextCodec::codecForName("UTF-8"));
#endif

    system("color 27");
    cout << QString::fromUtf8("C Новым годом!").toLocal8Bit().data() << endl;
    cout << QString::fromUtf8("Желаю, чтобы всё было хорошо!").toLocal8Bit().data() << endl;
    cout << QString::fromUtf8("А программы компилировались с первого раза и правильно!")
            .toLocal8Bit().data() << endl;

    return a.exec();
}
```

## Java

```java
package com.company;

import java.io.PrintStream;

public class Main {
    public static PrintStream out = System.out;

    public static void main(String[] args) {
        out.println("C Новым годом!");
        out.println("Желаю, чтобы всё было хорошо!");
        out.println("А программы компилировались с первого раза и правильно!");
    }
}
```
