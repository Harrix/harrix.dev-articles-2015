---
date: 2015-02-15
categories: [it, programming]
tags: [Qt, C++, Сложение двух чисел]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
url-src: https://github.com/Harrix/harrix.dev-blog-2015/blob/main/add-2-num-qt/add-2-num-qt.md
url: https://harrix.dev/ru/blog/2015/add-2-num-qt/
lang: ru
---

# Сложение двух чисел в Qt 5.4.0 на C++

![Featured image](featured-image.svg)

В статье рассказывается как создать приложение сложения двух чисел в Qt 5.4.0.

## Приготовления

В статье [Установка Qt](https://github.com/Harrix/harrix.dev-blog-2018/blob/main/install-qt-mingw/install-qt-mingw.md) и в статье [Установка Qt под Visual Studio, MinGW и для разработки под Android](https://github.com/Harrix/harrix.dev-blog-2018/blob/main/install-qt-advanced/install-qt-advanced.md) узнаете, как всё установить и настроить.

## Создание проекта

![Создание нового проекта](img/new-project_01.png)

_Рисунок 1 — Создание нового проекта_

![Выбор типа проекта](img/new-project_02.png)

_Рисунок 2 — Выбор типа проекта_

![Выбор имени и папки проекта](img/new-project_03.png)

_Рисунок 3 — Выбор имени и папки проекта_

![Выбор компилятора](img/new-project_04.png)

_Рисунок 4 — Выбор компилятора_

![Выбор названий класса и главных файлов проекта](img/new-project_05.png)

_Рисунок 5 — Выбор названий класса и главных файлов проекта_

![Дополнительная настройка проекта](img/new-project_06.png)

_Рисунок 6 — Дополнительная настройка проекта_

![Созданный проект](img/new-project_07.png)

_Рисунок 7 — Созданный проект_

## Интерфейс приложения

Перейдем двойным кликом на форму:

![Переход на форму](img/form_01.png)

_Рисунок 8 — Переход на форму_

Перетащите два `QLineEdit` на форму, в которые будем записывать наши числа:

![Перетаскивание на форму QLineEdit](img/form_02.png)

_Рисунок 9 — Перетаскивание на форму QLineEdit_

Перетащите кнопку на форму:

![Перетаскивание на форму кнопки](img/form_03.png)

_Рисунок 10 — Перетаскивание на форму кнопки_

Перетащите `QTextView` на форму, в которую мы будем выводить информацию:

![Перетаскивание на форму QTextView](img/form_04.png)

_Рисунок 11 — Перетаскивание на форму QTextView_

## Написание кода основной программы

Щелкнете по кнопке правой кнопкой и выберите `Goto slot…`:

![Переход к слоту кнопки](img/slot_01.png)

_Рисунок 12 — Переход к слоту кнопки_

Щелкаем `OK`:

![Выбор слота clicked](img/slot_02.png)

_Рисунок 13 — Выбор слота clicked_

Мы получили метод, в котором прописываем реакцию на клик нашей мыши:

![Метод слота в файле класса формы](img/slot_03.png)

_Рисунок 14 — Метод слота в файле класса формы_

В фигурных скобках пропишем код нашей программы по считыванию двух чисел, их сложении и выводе результата:

```cpp
int x, y, z;

//Считаем значение из первого lineEdit
QString S1 = ui->lineEdit->text();
//Переведем значение в число
x = S1.toInt();

//Считаем значение из второго lineEdit
QString S2 = ui->lineEdit_2->text();
//Переведем значение в число
y = S2.toInt();

//Посчитаем сумму
z = x + y;

//Выведем результат
ui->textEdit->insertPlainText(QString::number(z));
```

![Исходный код программы](img/cpp.png)

_Рисунок 15 — Исходный код программы_

Полная программа будет выглядеть так:

```cpp
#include "mainwindow.h"
#include "ui_mainwindow.h"

MainWindow::MainWindow(QWidget *parent) :
    QMainWindow(parent),
    ui(new Ui::MainWindow)
{
    ui->setupUi(this);
}

MainWindow::~MainWindow()
{
    delete ui;
}

void MainWindow::on_pushButton_clicked()
{
    int x, y, z;

    //Считаем значение из первого lineEdit
    QString S1 = ui->lineEdit->text();
    //Переведем значение в число
    x = S1.toInt();

    //Считаем значение из второго lineEdit
    QString S2 = ui->lineEdit_2->text();
    //Переведем значение в число
    y = S2.toInt();

    //Посчитаем сумму
    z = x + y;

    //Выведем результат
    ui->textEdit->insertPlainText(QString::number(z));
}
```

## Запуск программы

![Запуск программы](img/run_01.png)

_Рисунок 16 — Запуск программы_

Получаем наше приложение:

![Запущенное приложение](img/run_02.png)

_Рисунок 17 — Запущенное приложение_

При вводе наших чисел получим вот это:

![Результат выполнения программы](img/run_03.png)

_Рисунок 18 — Результат выполнения программы_
