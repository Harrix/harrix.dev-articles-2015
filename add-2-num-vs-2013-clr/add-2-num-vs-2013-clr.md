---
date: 2015-02-15
categories: [it, programming]
tags: [Visual Studio, C++, Сложение двух чисел]
---

# Сложение двух чисел в Visual Studio 2013 на C++ (CLR приложение)

В статье рассказывается как создать CLR приложение сложения двух чисел в Visual Studio 2013 на C++.

## Создание проекта

![Создание нового проекта](img/new-project_01.png)

![Выбор типа проекта](img/new-project_02.png)

![Созданный проект](img/new-project_03.png)

## Подготовка проекта

В отличии от Visual Studio 2010 тут CLR приложения создаются пустыми без формы. Зачем они это сделали — непонятно. Будем добавлять форму самостоятельно.

Щелкаем по проекту правой кнопкой и следуем иллюстрациям:

![Клик правой кнопкой по проекту](img/prepare-form_01.png)

![Добавление нового элемента](img/prepare-form_02.png)

![Добавление новой формы](img/prepare-form_03.png)

![Созданная форма](img/prepare-form_04.png)

Далее перейдем в файл `cpp` нашей формы:

![Переход в исходный файл формы](img/prepare-form_05.png)

Допишем там вот такой код после единственной строчки:

```cpp
using namespace System;
using namespace System::Windows::Forms;

[STAThread]
void Main(array<String^>^args)
{
  Application::EnableVisualStyles();
  Application::SetCompatibleTextRenderingDefault(false);

  Additions2numbers::MyForm form;
  Application::Run(%form);
}:
```

**Внимание!** Обратите внимание, что `Additions2numbers` — это название вашего проекта в коде выше. Поэтому, если ваш проект называется по-другому, то вставьте своё название проекта:

![Внешний вид кода программы](img/prepare-form_06.png)

Щелкнем по проекту правой кнопкой и перейдем в его свойства:

![Выбор свойств проекта](img/prepare-form_07.png)

В настройках компоновщика нужно в двух местах поменять настройки:

![Настройки компоновщика](img/prepare-form_08.png)

![Редактирование точки входа приложения](img/prepare-form_09.png)

Жмем `OK`, и мы закончили прикручивать форму к нашему приложению.

Можете запустить приложение и проверить работоспособность. Если приложение скомпилируется и запустится, то всё норм. Иначе проверьте все шаги до этого:

![Запуск приложения](img/run_01.png)

## Интерфейс приложения

Перейдем на форму. Можно сделать двумя способами:

![Переход на форму](img/form_01.png)

Обратите внимание, что код кнопок и сама форма прописывается в `h` файле, а не `cpp`.

Перетащите два `textBox` на форму, в которые будем записывать наши числа:

![Перетаскивание textBox](img/form_02.png)

![Первый textBox](img/form_03.png)

![Второй textBox](img/form_04.png)

Перетащите кнопку на форму:

![Перетаскивание кнопки](img/form_05.png)

Перетащите третий `textBox` на форму, в которую мы будем выводить информацию:

![Перетаскивание textBox](img/form_06.png)

![Третий textBox](img/form_07.png)

Однострочные и многострочные текстовые поля задаются одним компонентом. Поэтому мы должны изменить параметры нашего `textBox3`, чтобы в нем можно было выводить много строк. Выделим наш `textBox3` и изменим его параметры:

![Изменение свойства Multiline на true](img/form_08.png)

Теперь мы можем его растянуть вниз:

![Начальные размеры textBox](img/form_09.png)

![Конечные размеры textBox](img/form_10.png)

## Написание кода основной программы

Щелкнете по кнопке двойным кликом:

![Двойной клик по кнопке](img/form_11.png)

Мы получили метод, в котором прописываем реакцию на клик нашей мыши:

![Созданный метод обработки клика кнопки](img/cpp_01.png)

В фигурных скобках пропишем код нашей программы по считыванию двух чисел, их сложении и выводе результата:

```cpp
int x, y, z;

//Считаем значение из первого lineEdit
String^ S1 = textBox1->Text;
//Переведем значение в число
x = Convert::ToInt32(S1);

//Считаем значение из второго lineEdit
String^ S2 = textBox2->Text;
//Переведем значение в число
y = Convert::ToInt32(S2);

//Посчитаем сумму
z = x + y;

//Выведем результат
textBox3->Text = z.ToString();
```

![Код в методе обработки клика кнопки](img/cpp_02.png)

## Запуск программы

Немного поменял размеры компонентов и изменил текст на кнопке. Поэтому ниже на скринах компоненты чуть по-другому будут выглядеть:

![Запуск приложения](img/run_02.png)

Получаем наше приложение:

![Запущенное приложение](img/run_03.png)

При вводе наших чисел получим вот это:

![Результат выполнения приложения](img/run_04.png)