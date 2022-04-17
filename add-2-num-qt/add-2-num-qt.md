---
date: 2015-02-15
categories: [it, programming]
tags: [Qt, C++, Сложение двух чисел]
---

# Сложение двух чисел в Qt 5.4.0 на C++

В статье рассказывается как создать приложение сложения двух чисел в Qt 5.4.0.

## Приготовления

В статье [Установка Qt](https://github.com/Harrix/harrix.dev-blog-2018/blob/main/2018-08-19-install-qt-mingw/2018-08-19-install-qt-mingw.md) и в статье [Установка Qt под Visual Studio, MinGW и для разработки под Android](https://github.com/Harrix/harrix.dev-blog-2018/blob/main/2018-08-19-install-qt-advanced/2018-08-19-install-qt-advanced.md) узнаете, как всё установить и настроить.

## Создание проекта

![Создание нового проекта](img/new-project_01.png)

![Выбор типа проекта](img/new-project_02.png)

![Выбор имени и папки проекта](img/new-project_03.png)

![Выбор компилятора](img/new-project_04.png)

![Выбор названий класса и главных файлов проекта](img/new-project_05.png)

![Дополнительная настройка проекта](img/new-project_06.png)

![Созданный проект](img/new-project_07.png)

## Интерфейс приложения

Перейдем двойным кликом на форму:

![Переход на форму](img/form_01.png)

Перетащите два `QLineEdit` на форму, в которые будем записывать наши числа:

![Перетаскивание на форму QLineEdit](img/form_02.png)

Перетащите кнопку на форму:

![Перетаскивание на форму кнопки](img/form_03.png)

Перетащите `QTextView` на форму, в которую мы будем выводить информацию:

![Перетаскивание на форму QTextView](img/form_04.png)

## Написание кода основной программы

Щелкнете по кнопке правой кнопкой и выберите `Goto slot…`:

![Переход к слоту кнопки](img/slot_01.png)

Щелкаем `OK`:

![Выбор слота clicked](img/slot_02.png)

Мы получили метод, в котором прописываем реакцию на клик нашей мыши:

![Метод слота в файле класса формы](img/slot_03.png)

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

Получаем наше приложение:

![Запущенное приложение](img/run_02.png)

При вводе наших чисел получим вот это:

![Результат выполнения программы](img/run_03.png)
