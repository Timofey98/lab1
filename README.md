# Лабораторная работа 1

## Задание
1. Создать исполняемый java класс, который выводит "Hello, World!" на экран.
2. Разработать два класса. Первый класс выводит на экран строку "Hello, " и строку из
второго класса.
3. Создать jar-файл, хранящий элементы из предыдущего задания.

## Разработка

## Структура проекта 

#### Структура проекта первого задания

```
├── classes
|   └── mypackage
|      └── HelloWorld.class
└── src
    └── mypackage
       └── HelloWorld.java

```

#### Структура проекта второго задания

```
├── classes
|   ├── mypackage
|   |  └── HelloWorld.class
|   └── ru
|      └── rsatu
|         └── Class2.class
└── src
    ├── mypackage
    |  └── HelloWorld.java
    └── ru
       └── rsatu
          └── Class2.java

```

#### Структура проекта третьего задания

```
├── HelloWorld.jar
├── minifest.mf
├── classes
|   ├── mypackage
|   |  └── HelloWorld.class
|   └── ru
|      └── rsatu
|         └── Class2.class
└── src
    ├── mypackage
    |  └── HelloWorld.java
    └── ru
       └── rsatu
          └── Class2.java

```

### Задание 1

Класса [``HelloWorld``](task1/src/mypackage/HelloWorld.java)

```java
package mypackage;
public class HelloWorld {
    public static void main(String args[]) {
        System.out.println("Hello, World!");
    }
}
```
Для компиляции используется команда javac:

```
javac -classpath ./classes -d ./classes src/mypackage/HelloWorld.java
```

Для запуска файла используется команда java.

```
java -classpath ./classes mypackage.HelloWorld
```

В результате выводится строка "Hello, World!"

### Задание 2

В директории rsatu создаём класс [``Class2``](task2/src/ru/rsatu/Class2.java)
```java
package ru.rsatu;
public class Class2 {
    public static String s = "RSATU";
}
```

Изменяем класс [``HelloWorld``](task2/src/mypackage/HelloWorld.java)

```java
package mypackage;
import ru.rsatu.Class2;
public class HelloWorld{
    public static void main(String args[]) {
        System.out.println("Hello, "+ Class2.s + "!");
    }
}
```

Компелируем данные файлы командой javac. Запускаем HelloWorld командой java. В результате выводится строка "Hello, RSATU!"

### Задание 3

Создаём файл [``manifest.mf``](task3/manifest.mf), в котором указываем глваный исполняемый класс HelloWorld.

```
Manifest-Version: 1.0
Created-By: 1.6.0_19 (Sun Microsystems Inc.)
Main-Class: mypackage.HelloWorld
```
Выполняем команду сборки архива jar:

```
jar cvfm HelloWorld.jar manifest.mf -C classes/ .
```

Запускаем jar-файл:
```
java -jar HelloWorld.jar
```

В результате выводится строка "Hello, RSATU!".

##Вывод

В рузультате выполнения лабораторной работы получили навыки работы с командами для компиляции классов, запуска проектов и создания jar-файлов.

## Работа выполнена

[Ащеулов Михаил ПИМ-21](https://github.com/VergiliusAW)

[Кравцов Тимофей ПИМ-21](https://github.com/Timofey98)
