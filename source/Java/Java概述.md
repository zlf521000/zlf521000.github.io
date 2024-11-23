---
title: Java 简介
date: 2024-11-04 21:08:38
tags: Java
#cover: https://s1.imagehub.cc/images/2024/11/04/67c84c24b123473b27c83cee9fd52f72.png
---

# Java 简介

## 什么是 Java？
Java 是由 Sun Microsystems 公司于 1995 年 5 月推出的面向对象程序设计语言和 Java 平台的总称。由 James Gosling 和他的团队研发，并于 1995 年正式推出。后来，Sun 公司被 Oracle（甲骨文）公司收购，Java 也成为 Oracle 公司的产品。

### Java 的三个体系：
1. **Java SE（Standard Edition）**：标准版，用于开发桌面应用和基本工具。
2. **Java EE（Enterprise Edition）**：企业版，用于开发企业级分布式系统和 Web 应用。
3. **Java ME（Micro Edition）**：微型版，用于开发嵌入式系统和移动设备。

### Java 的发展历史：
- 1995 年：Java 语言诞生。
- 1996 年：第一个 JDK（JDK1.0）发布。
- 2005 年：Java 各版本命名规范更改（如 J2EE 更名为 Java EE）。
- 2009 年：甲骨文收购 Sun 公司。
- 2014 年：Java SE 8 发布，带来 Lambda 表达式和 Stream API 等重要特性。
- 2018 年起：Java 开始每六个月发布一次新版本。

---

## Java 的主要特性

1. **简单性**：Java 丢弃了 C++ 的一些复杂特性（如操作符重载、指针），并提供自动内存管理。
2. **面向对象**：支持类、接口、继承和动态绑定。
3. **分布式**：内置网络编程支持，如 `java.net` 包和 RMI（远程方法调用）。
4. **健壮性**：通过强类型检查、异常处理、垃圾回收等保证程序可靠。
5. **安全性**：提供安全机制，防止恶意代码攻击（如 `ClassLoader` 和 `SecurityManager`）。
6. **可移植性**：Java 程序通过 JVM 实现“编译一次，运行无处不在”。
7. **多线程**：支持多线程编程，提供线程同步机制。
8. **高性能**：结合 JIT（即时编译器）优化，运行速度接近 C++。
9. **动态性**：Java 支持动态加载类和运行时类型检查。

---

## Java 开发工具
### 系统要求
- **推荐内存**：1GB 以上。
- **操作系统**：支持 Linux、MacOS、Windows（如 Win7、Win10）。
- **JDK**：建议安装 JDK 8 或更高版本。

### 常用工具
1. **文本编辑器**：
   - `vscode`、`Notepad++` 或其他简单编辑器。
2. **集成开发环境（IDE）**：
   - `Eclipse`
   - `IntelliJ IDEA`（推荐）
   - `NetBeans`

---

## 第一个 Java 程序

1. 安装 JDK 并配置环境变量。
2. 使用文本编辑器或 IDE 编写代码。
3. 运行并输出结果。

### 代码示例：Hello, World!
```java
// HelloWorld.java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```
### 执行步骤
```java
HelloWorld.java
```

### 编译代码：
```bash
javac HelloWorld.java
```
### 运行程序：
```bash
java HelloWorld
``` 
### 运行结果

```java
Hello, World!
```

