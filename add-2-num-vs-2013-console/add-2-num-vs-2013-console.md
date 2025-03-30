---
date: 2015-02-08
categories:
  - it
  - programming
tags:
  - Visual Studio
  - C++
  - Сложение двух чисел
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
permalink-source: https://github.com/Harrix/harrix.dev-articles-2015/blob/main/add-2-num-vs-2013-console/add-2-num-vs-2013-console.md
permalink: https://harrix.dev/ru/articles/2015/add-2-num-vs-2013-console/
lang: ru
attribution:
  - author: Microsoft Corporation
    author-site: https://www.microsoft.com/
    license: Public domain
    license-url: https://en.wikipedia.org/wiki/Public_domain
    permalink: https://commons.wikimedia.org/wiki/File:Visual_Studio_2017_Logo.svg
    permalink-date: 2019-06-08
    name: Visual Studio 2017 Logo.svg
---

# Сложение двух чисел в Visual Studio 2013 (консольное Win32 приложение)

![Featured image](featured-image.svg)

В статье рассказывается как создать консольное приложения сложения двух чисел Win32 в Visual Studio 2013.

## Содержание

- [Создание проекта](#создание-проекта)
- [Болванка приложения C++](#болванка-приложения-c)
- [Написание кода основной программы](#написание-кода-основной-программы)
- [Запуск программы](#запуск-программы)

## Создание проекта

![Создание нового проекта](img/new-project_01.png)

_Рисунок 1 — Создание нового проекта_

![Выбор типа нового проекта](img/new-project_02.png)

_Рисунок 2 — Выбор типа нового проекта_

![Мастер создания проекта](img/new-project_03.png)

_Рисунок 3 — Мастер создания проекта_

![Мастер создания проекта](img/new-project_04.png)

_Рисунок 4 — Мастер создания проекта_

![Созданный новый проект](img/new-project_05.png)

_Рисунок 5 — Созданный новый проект_

## Болванка приложения C++

Пропишем подключение библиотек:

```cpp
#include <iostream>//Для cout и cin
#include <windows.h>//Для setlocale
```

Пропишем пространство имен стандартной библиотеки, чтобы потом было меньше прописывать кода:

```cpp
using namespace std;//Подключение стандартной библиотеки функций
```

![Внешний вид кода](img/code.png)

_Рисунок 6 — Внешний вид кода_

В функции `_tmain` пропишем строчки кода, чтобы русский язык отображался корректно:

```cpp
setlocale(LC_ALL, "RUSSIAN");//Для корректного отображения русского языка
//Раскомментировать строчки ниже, если с русским будут проблемы
//setlocale(LC_ALL, "ru_RU.UTF-8");
//setlocale(LC_ALL, "");
```

В конце функции перед `return` пропишем функцию, чтобы программа автоматически не закрывалась:

```cpp
system("pause");//Чтобы приложение не закрылось автоматически
```

В итоге получаем болванку программы на C++, которую потом удобно использовать для других приложений учебного толка:

```cpp
// Addition2numbers.cpp : Defines the entry point for the console application.
//

#include "stdafx.h"

#include <iostream>//Для cout и cin
#include <windows.h>//Для setlocale

using namespace std;//Подключение стандартной библиотеки функций

int _tmain(int argc, _TCHAR* argv[])
{
  setlocale(LC_ALL, "RUSSIAN");//Для корректного отображения русского языка
  //Раскомментировать строчки ниже, если с русским будут проблемы
  //setlocale(LC_ALL, "ru_RU.UTF-8");
  //setlocale(LC_ALL, "");

  //Тут пишем код программы

  system("pause");//Чтобы приложение не закрылось автоматически
  return 0;
}
```

## Написание кода основной программы

А теперь пропишем основной код нашей программы, где через `cin` мы считываем в переменные наши числа, а через `cout` выводим текст в консоль:

```cpp
int a, b, c;

//Считаем первое число
cout << "Введите первое число:" << endl;
cin >> a;

//Считаем второе число
cout << "Введите второе число:" << endl;
cin >> b;

//Посчитаем сумму
c = a + b;

//Выведем результат
cout << "Сумма: " << c << endl;
```

Полная программа будет выглядеть так:

```cpp
// Addition2numbers.cpp : Defines the entry point for the console application.
//

#include "stdafx.h"

#include <iostream>//Для cout и cin
#include <windows.h>//Для setlocale

using namespace std;//Подключение стандартной библиотеки функций

int _tmain(int argc, _TCHAR* argv[])
{
  setlocale(LC_ALL, "RUSSIAN");//Для корректного отображения русского языка
  //Раскомментировать строчки ниже, если с русским будут проблемы
  //setlocale(LC_ALL, "ru_RU.UTF-8");
  //setlocale(LC_ALL, "");

  //Тут пишем код программы

  int a, b, c;

  //Считаем первое число
  cout << "Введите первое число:" << endl;
  cin >> a;

  //Считаем второе число
  cout << "Введите второе число:" << endl;
  cin >> b;

  //Посчитаем сумму
  c = a + b;

  //Выведем результат
  cout << "Сумма: " << c << endl;

  system("pause");//Чтобы приложение не закрылось автоматически
  return 0;
}
```

## Запуск программы

![Запуск приложения](img/run_01.png)

_Рисунок 7 — Запуск приложения_

Получаем наше приложение:

![Запущенное приложение](img/run_02.png)

_Рисунок 8 — Запущенное приложение_

При вводе наших чисел получим вот это:

![Вывод программы](img/run_03.png)

_Рисунок 9 — Вывод программы_
