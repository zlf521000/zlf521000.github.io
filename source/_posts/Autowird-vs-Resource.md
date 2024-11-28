---
title: Autowird_vs_Resource
date: 2024-11-28 19:09:48
tags: Java
cover: https://s1.imagehub.cc/images/2024/11/28/bab171eb86cb158d84460d755e65e039.jpg
---

# 深入解析 @Autowired 和 @Resource 的区别

在 Spring 开发中，**依赖注入（DI）** 是核心概念之一。我们通常使用注解来简化配置，其中最常见的两个注解是 `@Autowired` 和 `@Resource`。虽然它们的功能看起来相似，实际却有本质的区别。本篇博客将从**原理**、**使用方式**、**场景对比**等方面深入解析两者的区别，帮助开发者在实际项目中选择合适的注解。

---
# 推荐正在找工作的朋友们：
[就业指导](https://github.com/zlf521000/JavaOfferToYou)   或 [面试指导](https://gitee.com/luffy521000/JavaOfferToYou) （没有任何培训机构性质）
公众号：**Java直达Offer**
微信：
[![添加微信](https://s1.imagehub.cc/images/2024/11/10/32be5f45c45cf77547ca4b1315febf1d.th.jpg)](https://www.imagehub.cc/image/wechatCode.C09gn4)
## 一、基础概念

### 1. @Autowired

- **定义**：`@Autowired` 是 Spring 框架提供的注解，用于实现自动注入。
- **依赖**：基于 **Spring 框架**。
- **功能**：通过**类型匹配**（byType）实现依赖注入。

```java
@Autowired
private UserService userService;
```

### 2. @Resource

- **定义**：`@Resource` 是 Java 自带的注解，由 **J2EE**（JSR-250）标准提供。
- **依赖**：与框架无关，可用于任何支持 JSR-250 的框架（如 Spring、Java EE）。
- **功能**：通过**名称匹配**（byName）注入，若名称无法匹配，则退回到**类型匹配**。

```java
@Resource
private UserService userService;
```

---

## 二、两者的使用场景与差异

| 特性               | @Autowired                           | @Resource                                      |
|--------------------|---------------------------------------|-----------------------------------------------|
| **所属规范**       | Spring 特有                          | JSR-250 标准                                  |
| **默认匹配方式**   | 类型匹配（byType）                   | 名称匹配（byName）                            |
| **支持注解属性**   | `@Qualifier` 指定具体的 bean         | `name` 或 `type` 指定具体的 bean             |
| **是否强制依赖**   | 默认必须注入，可使用 `required=false` | 默认必须注入，不支持直接修改必需性           |
| **适用范围**       | 仅在 Spring 容器中工作               | 跨框架适用，兼容性更好                        |

---

## 三、注入过程详解

### 1. @Autowired 的注入过程

- **默认行为**：通过类型匹配注入依赖。如果容器中有多个同类型的 Bean，则需要结合 `@Qualifier` 指定 Bean 名称。
- **处理器**：由 `AutowiredAnnotationBeanPostProcessor` 处理。

#### 示例 1：按类型注入

```java
@Autowired
private UserService userService;
```

#### 示例 2：按名称注入（配合 @Qualifier）

```java
@Autowired
@Qualifier("specificUserService")
private UserService userService;
```

#### 注入失败的处理

- 默认情况下，Spring 会抛出异常：`NoSuchBeanDefinitionException`。
- 可以通过 `required=false` 标记为非必需。

```java
@Autowired(required = false)
private UserService userService;
```

### 2. @Resource 的注入过程

- **默认行为**：首先按照名称匹配注入 Bean。如果名称匹配失败，则退回到类型匹配。
- **处理器**：由 `CommonAnnotationBeanPostProcessor` 处理。

#### 示例 1：默认按名称注入

```java
@Resource
private UserService userService;
```

#### 示例 2：按名称指定

```java
@Resource(name = "specificUserService")
private UserService userService;
```

---

## 四、实际开发中的选择

### 1. 使用建议

- **优先考虑 @Autowired**：
  - 如果项目是基于 Spring 开发的，推荐使用 `@Autowired`，配合 `@Qualifier` 灵活性更高。
  - 提供更丰富的配置项（如 `required=false`）。

- **跨框架时选择 @Resource**：
  - 如果项目需要兼容其他框架（如 Java EE），推荐使用 `@Resource`。
  - 更符合 JSR 标准，代码移植性强。

### 2. 项目中的混用策略

在实际项目中，建议团队统一依赖注入的注解使用规范。若项目中大量依赖 Spring，可以只使用 `@Autowired`；若需要跨框架支持，则统一使用 `@Resource`。

---

## 五、总结

`@Autowired` 和 `@Resource` 都是实现依赖注入的重要工具，关键在于理解它们的匹配规则和适用场景。在 Spring 项目中，`@Autowired` 更加灵活，配合 `@Qualifier` 和 `required` 属性能够满足大部分复杂需求。而 `@Resource` 则更适合需要标准化、跨框架的项目。选择正确的注解，能够提高代码的可维护性和兼容性。
