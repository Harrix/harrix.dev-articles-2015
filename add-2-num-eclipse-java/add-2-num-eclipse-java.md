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
url-src: https://github.com/Harrix/harrix.dev-blog-2015/blob/main/add-2-num-eclipse-java/add-2-num-eclipse-java.md
---

# Сложение двух чисел в Eclipse на Java (консольное приложение)

В статье рассказывается как создать консольного приложения сложения двух чисел под Java в Eclipse.

## Приготовления

В статье [Установка Eclipse в Windows](https://github.com/Harrix/harrix.dev-blog-2014/blob/main/install-eclipse-java/install-eclipse-java.md) узнаете, как всё установить и настроить.

## Создание проекта

Итак, открываем Eclipse. У меня приложение находится по адресу `C:\Android\eclipse\eclipse.exe`.

При старте спросят о папке, куда сохранять будем проекты:

![Выбор места для сохранения проектов](img/workspace.png)

И закройте окно приветствия:

![Закрытие окна приветствия](img/welcome.png)

Создадим новый проект:

![Создание нового Java проекта](img/new-project_01.png)

![Ввод названия проекта](img/new-project_02.png)

Правой кнопкой по папке `src` создаем новый класс:

![Создаем новый класс](img/new-project_03.png)

![Ввод имени класса и его параметров](img/new-project_04.png)

![Созданный проект](img/new-project_05.png)

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

При вводе наших чисел получим вот это:

![Вывод программы](img/run_02.png)

Вот наше приложение и написано.
