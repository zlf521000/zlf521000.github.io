---
title: Java基础语法
date: 2024-11-04 21:08:38
tags: Java
#cover: https://s1.imagehub.cc/images/2024/11/04/67c84c24b123473b27c83cee9fd52f72.png
---

# Java基础语法详解

Java 的基础语法是学习 Java 编程的第一步。通过掌握基本语法，能让你顺利编写和运行简单的 Java 程序。本文将详细介绍 Java 的基础语法及示例代码。

## Java 的基本结构

一个完整的 Java 程序结构如下：
```java
public class ClassName {
    public static void main(String[] args) {
        // 程序入口
        System.out.println("Hello, Java!");
    }
}
```

### 结构说明
1. `public class ClassName`：定义一个公共类，文件名必须与类名相同。
2. `public static void main(String[] args)`：主方法（程序入口），运行时 JVM 调用此方法。
3. `System.out.println`：用于输出内容到控制台。

---

## 注释

Java 提供三种注释方式：
- 单行注释：使用 `//` 表示。
- 多行注释：使用 `/* ... */` 包裹多行内容。
- 文档注释：使用 `/** ... */`，用于生成 API 文档。

示例：
```java
// 这是单行注释
/*
这是多行注释
可以换行
*/
/**
 * 这是文档注释
 * 用于描述类、方法或变量
 */
```

---

## 数据类型

Java 的基本数据类型分为四类共八种：

```java
// 整数类型
byte b = 127;       // 1字节，范围：-128~127
short s = 32000;    // 2字节，范围：-32,768~32,767
int i = 100000;     // 4字节，范围：-2^31 ~ 2^31-1
long l = 100000L;   // 8字节，范围：-2^63 ~ 2^63-1

// 浮点类型
float f = 3.14f;    // 4字节，精度小
double d = 3.14159; // 8字节，精度高

// 字符类型
char c = 'A';       // 2字节，表示单个字符

// 布尔类型
boolean flag = true; // 1字节，true 或 false
```

---

## 变量与常量

### 变量
变量的声明方式：
```java
数据类型 变量名 = 初始值;
```

示例：
```java
int age = 25; // 定义一个整型变量
String name = "Java"; // 定义一个字符串变量
```

### 常量
使用 `final` 关键字定义常量，值不可修改：
```java
final double PI = 3.14159;
```

---

## 运算符

### 算术运算符
```java
int a = 10, b = 3;
System.out.println(a + b); // 加法：13
System.out.println(a - b); // 减法：7
System.out.println(a * b); // 乘法：30
System.out.println(a / b); // 除法：3
System.out.println(a % b); // 取模：1
```

### 关系运算符
```java
System.out.println(a > b);  // true
System.out.println(a < b);  // false
System.out.println(a == b); // false
System.out.println(a != b); // true
```

### 逻辑运算符
```java
boolean x = true, y = false;
System.out.println(x && y); // 与（AND）：false
System.out.println(x || y); // 或（OR）：true
System.out.println(!x);     // 非（NOT）：false
```

---

## 流程控制

### 条件语句
```java
int score = 85;
// if-else 语句
if (score >= 90) {
    System.out.println("优秀");
} else if (score >= 60) {
    System.out.println("及格");
} else {
    System.out.println("不及格");
}

// switch-case 语句
int day = 3;
switch (day) {
    case 1:
        System.out.println("星期一");
        break;
    case 2:
        System.out.println("星期二");
        break;
    default:
        System.out.println("其他日子");
}
```

### 循环语句
```java
// for 循环
for (int i = 0; i < 5; i++) {
    System.out.println("i = " + i);
}

// while 循环
int i = 0;
while (i < 5) {
    System.out.println("i = " + i);
    i++;
}

// do-while 循环
int j = 0;
do {
    System.out.println("j = " + j);
    j++;
} while (j < 5);
```
---

## Java 的主方法和执行步骤

### 示例代码
```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

### 执行步骤
1. 将代码保存为 `HelloWorld.java`。
2. 编译代码：
   ```bash
   javac HelloWorld.java
   ```
3. 运行程序：
   ```bash
   java HelloWorld
   ```

### 输出结果
```plaintext
Hello, World!
```

---

## 总结

通过学习本文内容，你已经掌握了 Java 基础语法，包括 Java 程序的基本结构、注释、数据类型、变量与常量、运算符以及流程控制语句。接下来，可以尝试编写自己的 Java 程序，进一步巩固所学知识。
