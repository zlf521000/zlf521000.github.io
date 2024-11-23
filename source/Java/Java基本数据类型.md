---
title: Java基本数据类型
date: 2024-11-04 21:08:38
tags: Java
#cover: https://s1.imagehub.cc/images/2024/11/04/67c84c24b123473b27c83cee9fd52f72.png
---


# Java基本数据类型详解

Java 是一种强类型语言，所有变量必须先声明其类型后才能使用。Java 的数据类型分为两大类：基本数据类型和引用数据类型。本篇主要介绍 Java 的基本数据类型。

---

## 基本数据类型分类

Java 的基本数据类型分为四类共八种：

| 类型       | 关键字    | 字节大小 | 默认值  | 范围                                  |
|------------|-----------|----------|---------|---------------------------------------|
| **整数类型** | `byte`    | 1        | 0       | -128 ~ 127                           |
|            | `short`   | 2        | 0       | -32,768 ~ 32,767                     |
|            | `int`     | 4        | 0       | -2^31 ~ 2^31-1                       |
|            | `long`    | 8        | 0L      | -2^63 ~ 2^63-1                       |
| **浮点类型** | `float`   | 4        | 0.0f    | 3.4e-038 ~ 3.4e+038                  |
|            | `double`  | 8        | 0.0d    | 1.7e-308 ~ 1.7e+308                  |
| **字符类型** | `char`    | 2        | '\u0000' | 单个字符（UTF-16 编码）              |
| **布尔类型** | `boolean` | 1        | false   | `true` 或 `false`                    |

---

## 各类型示例

### 1. 整数类型

```java
public class IntegerTypes {
    public static void main(String[] args) {
        byte b = 127; // 最大值
        short s = 32000; // 常见范围值
        int i = 100000; // 默认整数类型
        long l = 10000000000L; // 使用 L 指定 long 类型

        System.out.println("byte: " + b);
        System.out.println("short: " + s);
        System.out.println("int: " + i);
        System.out.println("long: " + l);
    }
}
```

#### 输出结果
```plaintext
byte: 127
short: 32000
int: 100000
long: 10000000000
```

---

### 2. 浮点类型

```java
public class FloatingTypes {
    public static void main(String[] args) {
        float f = 3.14f; // 使用 f 指定 float 类型
        double d = 3.141592653589793; // 默认浮点数类型为 double

        System.out.println("float: " + f);
        System.out.println("double: " + d);
    }
}
```

#### 输出结果
```plaintext
float: 3.14
double: 3.141592653589793
```

---

### 3. 字符类型

```java
public class CharType {
    public static void main(String[] args) {
        char c1 = 'A'; // 字母
        char c2 = '中'; // 中文字符
        char c3 = 'a'; // Unicode 表示法

        System.out.println("char c1: " + c1);
        System.out.println("char c2: " + c2);
        System.out.println("char c3: " + c3);
    }
}
```

#### 输出结果
```plaintext
char c1: A
char c2: 中
char c3: a
```

---

### 4. 布尔类型

```java
public class BooleanType {
    public static void main(String[] args) {
        boolean isJavaFun = true;
        boolean isFishTasty = false;

        System.out.println("Is Java fun? " + isJavaFun);
        System.out.println("Is fish tasty? " + isFishTasty);
    }
}
```

#### 输出结果
```plaintext
Is Java fun? true
Is fish tasty? false
```

---

## 类型转换

Java 支持隐式和显式类型转换。

### 1. 隐式类型转换（自动转换）
低精度类型可以自动转换为高精度类型。
```java
public class ImplicitConversion {
    public static void main(String[] args) {
        int i = 100;
        double d = i; // int 自动转换为 double

        System.out.println("int: " + i);
        System.out.println("double: " + d);
    }
}
```

### 2. 显式类型转换（强制转换）
高精度类型需强制转换为低精度类型。
```java
public class ExplicitConversion {
    public static void main(String[] args) {
        double d = 100.99;
        int i = (int) d; // 强制转换

        System.out.println("double: " + d);
        System.out.println("int: " + i);
    }
}
```

#### 输出结果
```plaintext
double: 100.99
int: 100
```

---

## 总结

通过本文，你已经掌握了 Java 的基本数据类型及其用法，包括整数、浮点、字符和布尔类型。并学习了类型转换的基本操作。这些知识是编写 Java 程序的基础，建议在实践中多加练习。
