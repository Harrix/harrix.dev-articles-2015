---
date: 2015-02-08
categories: [it, programming]
tags: [Eclipse, Java, Сложение двух чисел]
related-id: start-java
update: 2018
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
permalink-source: https://github.com/Harrix/harrix.dev-blog-2015/blob/main/add-2-num-eclipse-java/add-2-num-eclipse-java.md
permalink: https://harrix.dev/ru/blog/2015/add-2-num-eclipse-java/
lang: ru
attribution:
  - {
      author: Eclipse Foundation,
      author-site: "http://www.eclipse.org/",
      license: Public
        domain,
      license-url: "https://en.wikipedia.org/wiki/Public_domain",
      permalink: "https://commons.wikimedia.org/wiki/File:Eclipse-Luna-Logo.svg",
      permalink-date: 2019-06-07,
      name: Eclipse-Luna-Logo.svg,
    }
---

# Сложение двух чисел в Eclipse на Java (консольное приложение)

![Featured image](featured-image.svg)

В статье рассказывается как создать консольного приложения сложения двух чисел под Java в Eclipse.

## Приготовления

В статье [Установка Eclipse в Windows](https://github.com/Harrix/harrix.dev-blog-2014/blob/main/install-eclipse-java/install-eclipse-java.md) <!-- https://harrix.dev/ru/blog/2014/install-eclipse-java/ --> узнаете, как всё установить и настроить.

## Создание проекта

Итак, открываем Eclipse. У меня приложение находится по адресу `C:\Android\eclipse\eclipse.exe`.

При старте спросят о папке, куда сохранять будем проекты:

![Выбор места для сохранения проектов](img/workspace.png)

_Рисунок 1 — Выбор места для сохранения проектов_

И закройте окно приветствия:

![Закрытие окна приветствия](img/welcome.png)

_Рисунок 2 — Закрытие окна приветствия_

Создадим новый проект:

![Создание нового Java проекта](img/new-project_01.png)

_Рисунок 3 — Создание нового Java проекта_

![Ввод названия проекта](img/new-project_02.png)

_Рисунок 4 — Ввод названия проекта_

Правой кнопкой по папке `src` создаем новый класс:

![Создаем новый класс](img/new-project_03.png)

_Рисунок 5 — Создаем новый класс_

![Ввод имени класса и его параметров](img/new-project_04.png)

_Рисунок 6 — Ввод имени класса и его параметров_

![Созданный проект](img/new-project_05.png)

_Рисунок 7 — Созданный проект_

## Болванка приложения Java

Пропишем создание экземпляра класса `Scanner` для считывания данных с консоли a функции `main`:

```java
Scanner sc = new Scanner(System.in);
```

И нажимаем `Ctrl` + `Shift` + `O`, чтобы подключить нужные библиотеки.

В итоге получаем болванку программы на Java, которую потом удобно использовать для других приложений учебного толка:

```java
import java.util.Scanner;

public class MainClass {

  public static void main(String[] args) {
    // TODO Auto-generated method stub
    //Для считывания данных с консоли
    Scanner sc = new Scanner(System.in);

  }
}
```

## Написание кода основной программы

А теперь пропишем основной код нашей программы:

```java
int a, b, c;

System.out.println("Введите первое число");
a = sc.nextInt();//Считываем первое число

System.out.println("Введите второе число");
b = sc.nextInt();//Считываем второе число

c = a + b;

System.out.println("c = " + c);
```

Полная программа будет выглядеть так:

```java
import java.util.Scanner;

public class MainClass {

  public static void main(String[] args) {
    // TODO Auto-generated method stub
    //Для считывания данных с консоли
    Scanner sc = new Scanner(System.in);

    int a, b, c;

    System.out.println("Введите первое число");
    a = sc.nextInt();//Считываем первое число

    System.out.println("Введите второе число");
    b = sc.nextInt();//Считываем второе число

    c = a + b;

    System.out.println("c = " + c);
  }
}
```

Нажмите `Ctrl` + `S` для сохранения изменений.

## Запуск программы

![Запуск приложения](img/run_01.png)

_Рисунок 8 — Запуск приложения_

При вводе наших чисел получим вот это:

![Вывод программы](img/run_02.png)

_Рисунок 9 — Вывод программы_

Вот наше приложение и написано.
