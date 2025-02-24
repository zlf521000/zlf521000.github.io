---
title: Spring
date: 2024-11-04 21:08:38
tags: Java面试题
---

# Java面试指导

我们是做就业服务的工作室，没有任何培训机构性质！！
主做Java、python、c++，前端vue，react等，
全国各地，简历包装，投递邀约，视频面试，技术面试包通过，离职背调等，
通过正常上班，不拿offer不收费，
不要浪费投递简历的机会和面试机会，
如果已经在职的话，并且不满意目前薪资也可以联系我们。关注公众号回复“**就业**”即可。

<img src="\img\公众号.png" alt="image-20241203185525611" style="zoom:50%;" />

或者添加微信咨询:
[![添加微信](https://s1.imagehub.cc/images/2024/11/14/8d89a045c06bcd516471d082e65b7557.th.jpg)](https://www.imagehub.cc/image/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87%E7%BC%96%E8%BE%91-20241114203416.CnGGD6)


# 开发框架

## Spring是什么？

轻量级的开源的J2EE框架。它是⼀个容器框架，⽤来装javabean（java对象），中间层框架（万能胶） 可以起⼀个连接作⽤，⽐如说把Struts和hibernate粘合在⼀起运⽤，可以让我们的企业开发更快、更简 洁，Spring是⼀个轻量级的控制反转（IoC)和⾯向切⾯（AOP）的容器框架：

- 从⼤⼩与开销两⽅⾯⽽⾔Spring都是轻量级的。
- 通过控制反转(IoC)的技术达到松耦合的⽬的
- 提供了⾯向切⾯编程的丰富⽀持，允许通过分离应⽤的业务逻辑与系统级服务进⾏内聚性的开发
- 包含并管理应⽤对象(Bean)的配置和⽣命周期，这个意义上是⼀个容器。
- 将简单的组件配置、组合成为复杂的应⽤，这个意义上是⼀个框架。

Spring框架的主要特点包括：

简化Java应用程序的开发过程：Spring框架通过提供丰富的功能和工具，例如依赖注入、AOP、ORM等，使得开发者能够更快速地构建和开发Java应用程序。

模块化设计：Spring框架被设计为一系列模块，每个模块都专注于特定的功能，例如Spring MVC、Spring Boot、Spring Security等。这些模块可以独立使用或者组合使用，以满足不同的需求。

依赖注入：Spring框架提供了依赖注入的功能，这是一种设计模式，旨在帮助开发者解耦代码和减少代码之间的依赖关系。通过依赖注入，Spring框架可以自动管理对象之间的依赖关系，使得开发者能够更轻松地维护和扩展应用程序。

面向切面编程（AOP）：Spring框架还提供了面向切面编程（AOP）的功能，这使得开发者能够轻松地实现跨多个对象的交叉功能，例如日志记录、安全性和事务管理。

可扩展性和可集成性：Spring框架的设计使得它非常容易扩展和集成其他组件和框架，例如数据库访问、消息传递、云服务等。





## **Spring的两大核心概念**

1. **IOC（控制反转）**
2. **AOP（面向切面编程）：**

## 谈谈你对AOP的理解

系统是由许多不同的组件所组成的，每⼀个组件各负责⼀块特定功能。除了实现⾃身核⼼功能之外，这 些组件还经常承担着额外的职责。例如⽇志、事务管理和安全这样的核⼼服务经常融⼊到⾃身具有核⼼ 业务逻辑的组件中去。这些系统服务经常被称为横切关注点，因为它们会跨越系统的多个组件。

当我们需要为分散的对象引⼊公共⾏为的时候，OOP则显得⽆能为⼒。也就是说，OOP允许你定义从上 到下的关系，但并不适合定义从左到右的关系。例如⽇志功能。

⽇志代码往往⽔平地散布在所有对象层次中，⽽与它所散布到的对象的核⼼功能毫⽆关系。

在OOP设计中，它导致了⼤量代码的重复，⽽不利于各个模块的重⽤。

AOP：将程序中的交叉业务逻辑（⽐如安全，⽇志，事务等），封装成⼀个切⾯，然后注⼊到⽬标对象 （具体业务逻辑）中去。AOP可以对某个对象或某些对象的功能进⾏增强，⽐如对象中的⽅法进⾏增 强，可以在执⾏某个⽅法之前额外的做⼀些事情，在某个⽅法执⾏之后额外的做⼀些事情





## 谈谈你对IOC的理解

容器概念、控制反转、依赖注⼊

**ioc容器：**实际上就是个map（key，value），⾥⾯存的是各种对象（在xml⾥配置的bean节点、 @repository、@service、@controller、@component），在项⽬启动的时候会读取配置⽂件⾥⾯的 bean节点，根据全限定类名使⽤反射创建对象放到map⾥、扫描到打上上述注解的类还是通过反射创建 对象放到map⾥。

这个时候map⾥就有各种对象了，接下来我们在代码⾥需要⽤到⾥⾯的对象时，再通过DI注⼊ （autowired、resource等注解，xml⾥bean节点内的ref属性，项⽬启动的时候会读取xml节点ref属性 根据id注⼊，也会扫描这些注解，根据类型或id注⼊；id就是对象名）。

**控制反转：**

没有引⼊IOC容器之前，对象A依赖于对象B，那么对象A在初始化或者运⾏到某⼀点的时候，⾃⼰必须 主动去创建对象B或者使⽤已经创建的对象B。⽆论是创建还是使⽤对象B，控制权都在⾃⼰⼿上。

引⼊IOC容器之后，对象A与对象B之间失去了直接联系，当对象A运⾏到需要对象B的时候，IOC容器会 主动创建⼀个对象B注⼊到对象A需要的地⽅。

通过前后的对⽐，不难看出来：对象A获得依赖对象B的过程,由主动⾏为变为了被动⾏为，控制权颠倒 过来了，这就是“控制反转”这个名称的由来。

全部对象的控制权全部上缴给“第三⽅”IOC容器，所以，IOC容器成了整个系统的关键核⼼，它起到了 ⼀种类似“粘合剂”的作⽤，把系统中的所有对象粘合在⼀起发挥作⽤，如果没有这个“粘合剂”，对象与 对象之间会彼此失去联系，这就是有⼈把IOC容器⽐喻成“粘合剂”的由来。

**依赖注⼊：**

“获得依赖对象的过程被反转了”。控制被反转之后，获得依赖对象的过程由⾃身管理变为了由IOC容器 主动注⼊。依赖注⼊是实现IOC的⽅法，就是由IOC容器在运⾏期间，动态地将某种依赖关系注⼊到对象 之中。





## **Spring框架的设计目标，设计理念，和核心是什么**

- **Spring设计目标：**Spring为开发者提供一个一站式轻量级应用开发平台； 
- **Spring设计理念：**在JavaEE开发中，支持POJO和JavaBean开发方式，使应用面向接口开发，充分 支持OOP（面向对象）设计方法；Spring通过IOC容器实现对象耦合关系的管理，并实现依赖反 转，将对象之间的依赖关系交给IOC容器，实现解耦；
- **Spring框架的核心：**IOC容器和AOP模块。通过IOC容器管理POJO对象以及他们之间的耦合关系； 通过AOP以动态非侵入的方式增强服务。
- IOC让相互协作的组件保持松散的耦合，而AOP编程允许你把遍布于应用各层的功能分离出来形成 可重用的功能组件。



## Spring由哪些模块组成？



- Spring 总共大约有 20 个模块， 由 1300 多个不同的文件构成。 而这些组件被分别整合在器（Core     Container）、核心容 AOP（Aspect     Oriented Programming）和设备支持（Instrmentation）、数据访问与集成（Data Access/Integeration）、Web、消息（Messaging）、Test 等 6 个模块中。 以下是 Spring 5 的模块结构图：

![img](\img\java\clip_image002.jpg)

- **Core Container (核心容器)**：

​			包括 Beans、Core、Context 和 Expression Language 模块。

​			提供了依赖注入（DI）的基本功能。

- **AOP（面向切面编程）**：

​	        提供支持面向切面的编程能力，例如日志、权限检查等横切关注点的分离。

- **Aspects**：

​			与 AOP 协同工作，支持 AspectJ 集成。

- **Data Access/Integration（数据访问与集成模块）**：

​			包括 JDBC、ORM、JMS 和事务管理模块。

​			提供了对数据访问技术（如 Hibernate、JPA）和消息服务的集成支持。

- **Web** **模块**：

​			提供了创建基于 Servlet 和基于 Web 的应用程序的支持。

​			包括 Spring MVC 和 WebSocket 模块。

- **Security（安全模块）**：

​			用于保护应用程序的安全性，支持身份验证和授权。

- **Test（测试模块）**：

​			提供对 JUnit 和 TestNG 的集成支持，用于单元测试和集成测试。



## 解释下Spring⽀持的⼏种bean的作⽤域。

- singleton：默认，每个容器中只有⼀个bean的实例，单例的模式由BeanFactory⾃身来维护。该 对象的⽣命周期是与Spring IOC容器⼀致的（但在第⼀次被注⼊时才会创建）。
- prototype：为每⼀个bean请求提供⼀个实例。在每次注⼊时都会创建⼀个新的对象 
- request：bean被定义为在每个HTTP请求中创建⼀个单例对象，也就是说在单个请求中都会复⽤ 这⼀个单例对象。
- session：与request范围类似，确保每个session中有⼀个bean的实例，在session过期后，bean 会随之失效。 
- application：bean被定义为在ServletContext的⽣命周期中复⽤⼀个单例对象。
- websocket：bean被定义为在websocket的⽣命周期中复⽤⼀个单例对象。

global-session：全局作⽤域，global-session和Portlet应⽤相关。当你的应⽤部署在Portlet容器 中⼯作时，它包含很多portlet。如果你想要声明让所有的portlet共⽤全局的存储变量的话，那么这 全局变量需要存储在global-session中。全局作⽤域与Servlet中的session作⽤域效果相同。 





## Spring事务的实现⽅式和原理以及隔离级别？

在使⽤Spring框架时，可以有两种使⽤事务的⽅式，⼀种是编程式的，⼀种是申明式的， 

@Transactional注解就是申明式的。

⾸先，事务这个概念是数据库层⾯的，Spring只是基于数据库中的事务进⾏了扩展，以及提供了⼀些能 让程序员更加⽅便操作事务的⽅式。

⽐如我们可以通过在某个⽅法上增加@Transactional注解，就可以开启事务，这个⽅法中所有的sql都 会在⼀个事务中执⾏，统⼀成功或失败。

在⼀个⽅法上加了@Transactional注解后，Spring会基于这个类⽣成⼀个代理对象，会将这个代理对象 作为bean，当在使⽤这个代理对象的⽅法时，如果这个⽅法上存在@Transactional注解，那么代理逻辑 会先把事务的⾃动提交设置为false，然后再去执⾏原本的业务逻辑⽅法，如果执⾏业务逻辑⽅法没有出 现异常，那么代理逻辑中就会将事务进⾏提交，如果执⾏业务逻辑⽅法出现了异常，那么则会将事务进行回滚。

当然，针对哪些异常回滚事务是可以配置的，可以利⽤@Transactional注解中的rollbackFor属性进⾏配 置，默认情况下会对RuntimeException和Error进⾏回滚。

spring事务隔离级别就是数据库的隔离级别：外加⼀个默认级别

- read uncommitted（未提交读）
- read committed（提交读、不可重复读）
- repeatable read（可重复读）
- serializable（可串⾏化）

```tex
数据库的配置隔离级别是Read Commited,
⽽Spring配置的隔离级别是Repeatable Read，
请问这时隔离级别是以哪⼀个为准？

以Spring配置的为准，如果spring设置的隔离级别数据库不⽀持，效果取决于数据库
```





## Spring事务传播机制

多个事务⽅法相互调⽤时，事务如何在这些⽅法间传播，⽅法A是⼀个事务的⽅法，⽅法A执⾏过程中调⽤了⽅法B，那么⽅法B有⽆事务以及⽅法B对事务的要求不同都会对⽅法A的事务具体执⾏造成影响， 同时⽅法A的事务对⽅法B的事务执⾏也有影响，这种影响具体是什么就由两个⽅法所定义的事务传播类 型所决定。

1. REQUIRED(Spring默认的事务传播类型)：如果当前没有事务，则⾃⼰新建⼀个事务，如果当前存在事务，则加⼊这个事务
2. SUPPORTS：当前存在事务，则加⼊当前事务，如果当前没有事务，就以⾮事务⽅法执⾏
3. MANDATORY：当前存在事务，则加⼊当前事务，如果当前事务不存在，则抛出异常。
4. MANDATORY：当前存在事务，则加⼊当前事务，如果当前事务不存在，则抛出异常。
5. NOT_SUPPORTED：以⾮事务⽅式执⾏,如果当前存在事务，则挂起当前事务
6. NEVER：不使⽤事务，如果当前事务存在，则抛出异常
7. NESTED：如果当前事务存在，则在嵌套事务中执⾏，否则REQUIRED的操作⼀样（开启⼀个事务）





## Spring事务什么时候会失效?

 spring事务的原理是AOP，进⾏了切⾯增强，那么失效的根本原因是这个AOP不起作⽤了！常⻅情况有 如下⼏种

1. 发⽣⾃调⽤，类⾥⾯使⽤this调⽤本类的⽅法（this通常省略），此时这个this对象不是代理类，⽽是 UserService对象本身！

   解决⽅法很简单，让那个this变成UserService的代理类即可！

2. ⽅法不是public的：@Transactional 只能⽤于 public 的⽅法上，否则事务不会失效，如果要⽤在⾮  public ⽅法上，可以开启 AspectJ 代理模式。

3. 数据库不⽀持事务

4. 没有被spring管理

5. 异常被吃掉，事务不会回滚(或者抛出的异常没有被定义，默认为RuntimeException)





## 什么是bean的⾃动装配，有哪些⽅式？

开启⾃动装配，只需要在xml配置⽂件中定义“autowire”属性。

```te
 <bean id="cutomer" class="com.xxx.xxx.Customer" autowire="" />
```

autowire属性有五种装配的⽅式：

- no – 缺省情况下，⾃动配置是通过“ref”属性⼿动设定 。 

  

  ```te
  ⼿动装配：以value或ref的⽅式明确指定属性值都是⼿动装配。
  需要通过‘ref’属性来连接bean。
  ```

  

- byName-根据bean的属性名称进⾏⾃动装配。

  ```te
  Cutomer的属性名称是person，Spring会将bean id为person的bean通过setter⽅法进⾏⾃动装配。
  <bean id="cutomer" class="com.xxx.xxx.Cutomer" autowire="byName"/>
  <bean id="person" class="com.xxx.xxx.Person"/>
  ```

  

- byType-根据bean的类型进⾏⾃动装配。

  ```te
  Cutomer的属性person的类型为Person，Spirng会将Person类型通过setter⽅法进⾏⾃动装配。
  <bean id="cutomer" class="com.xxx.xxx.Cutomer" autowire="byType"/>
  <bean id="person" class="com.xxx.xxx.Person"/>
  ```

  

- constructor-类似byType，不过是应⽤于构造器的参数。如果⼀个bean与构造器参数的类型形 同，则进⾏⾃动装配，否则导致异常。

  ```te
  Cutomer构造函数的参数person的类型为Person，Spirng会将Person类型通过构造⽅法进⾏⾃动装配。
  <bean id="cutomer" class="com.xxx.xxx.Cutomer" autowire="construtor"/>
  <bean id="person" class="com.xxx.xxx.Person"/>
  ```

  

- autodetect-如果有默认的构造器，则通过constructor⽅式进⾏⾃动装配，否则使⽤byType⽅式 进⾏⾃动装配。

  ```te
  如果有默认的构造器，则通过constructor⽅式进⾏⾃动装配，否则使⽤byType⽅式进⾏⾃动装配。
  ```

  @Autowired⾃动装配bean，可以在字段、setter⽅法、构造函数上使⽤。





## Spring中的Bean创建的⽣命周期有哪些步骤

Spring中⼀个Bean的创建⼤概分为以下⼏个步骤：

1. 推断构造⽅法
2. 实例化
3. 填充属性，也就是依赖注⼊
4. 处理Aware回调
5. 初始化前，处理@PostConstruct注解
6. 初始化，处理InitializingBean接⼝
7. 初始化后，进⾏AOP





## Spring中Bean是线程安全的吗

Spring本身并没有针对Bean做线程安全的处理，所以：

1. 如果Bean是⽆状态的，那么Bean则是线程安全的
2. 如果Bean是有状态的，那么Bean则不是线程安全的

另外，Bean是不是线程安全，跟Bean的作⽤域没有关系，Bean的作⽤域只是表示Bean的⽣命周期范 围，对于任何⽣命周期的Bean都是⼀个对象，这个对象是不是线程安全的，还是得看这个Bean对象本 身。





## ApplicationContext和BeanFactory有什么区别

BeanFactory是Spring中⾮常核⼼的组件，表示Bean⼯⼚，可以⽣成Bean，维护Bean，⽽ ApplicationContext继承了BeanFactory，所以ApplicationContext拥有BeanFactory所有的特点，也 是⼀个Bean⼯⼚，但是ApplicationContext除开继承了BeanFactory之外，还继承了诸如 EnvironmentCapable、MessageSource、ApplicationEventPublisher等接⼝，从⽽ ApplicationContext还有获取系统环境变量、国际化、事件发布等功能，这是BeanFactory所不具备的





## Spring中的事务是如何实现的

1. Spring事务底层是基于数据库事务和AOP机制的
2. 首先对于使用了@Transactional注解的Bean,Spring会创建一个代理对象作为Bean
3. 当调用代理对象的方法时，会先判断该方法上是否加了@Transactional注解
4. 如果加了，那么则利用事务管理器创建一个数据库连接
5. 并且修改数据库连接的autocommit/属性为false,禁止此连接的自动提交，这是实现Spring事务非常重要的一步
6. 然后执行当前方法，方法中会执行sql
7. 执行完当前方法后，如果没有出现异常就直接提交事务
8. 如果出现了异常，并且这个异常是需要回滚的就会回滚事务，否则仍然提交事务
9. Spring事务的隔离级别对应的就是数据库的隔离级别
10. Spring事务的传播机制是Spring事务自己实现的，也是Spring事务中最复杂的
11. Spring事务的传播机制是基于数据库连接来做的，一个数据库连接一个事务，如果传播机制配置为需要新开一个事务，那么实际上就是先建立一个数据库连接，在此新数据库连接上执行sql





## Spring中什么时候@Transactional会失效

因为Spring事务是基于代理来实现的，所以某个加了@Transactional的⽅法只有是被代理对象调⽤时， 那么这个注解才会⽣效，所以如果是被代理对象来调⽤这个⽅法，那么@Transactional是不会失效的。

同时如果某个⽅法是private的，那么@Transactional也会失效，因为底层cglib是基于⽗⼦类来实现 的，⼦类是不能重载⽗类的private⽅法的，所以⽆法很好的利⽤代理，也会导致@Transactianal失效





## Spring容器启动流程是怎样的

在创建Spring容器，也就是启动Spring时：

⾸先会进⾏扫描，扫描得到所有的BeanDefinition对象，并存在⼀个Map中

然后筛选出⾮懒加载的单例BeanDefinition进⾏创建Bean，对于多例Bean不需要在启动过程中去 进⾏创建，对于多例Bean会在每次获取Bean时利⽤BeanDefinition去创建

利⽤BeanDefinition创建Bean就是Bean的创建⽣命周期，这期间包括了合并BeanDefinition、推断 构造⽅法、实例化、属性填充、初始化前、初始化、初始化后等步骤，其中AOP就是发⽣在初始化 后这⼀步骤中

单例Bean创建完了之后，Spring会发布⼀个容器启动事件

Spring启动结束

在源码中会更复杂，⽐如源码中会提供⼀些模板⽅法，让⼦类来实现，⽐如源码中还涉及到⼀些 BeanFactoryPostProcessor和BeanPostProcessor的注册，Spring的扫描就是通过 BenaFactoryPostProcessor来实现的，依赖注⼊就是通过BeanPostProcessor来实现的

在Spring启动过程中还会去处理@Import等注解





## Spring⽤到了哪些设计模式

### 

**工厂模式（Factory Pattern）**

- **BeanFactory** 和 **ApplicationContext** 是 Spring 的核心容器，负责创建和管理 Bean 的实例。

- 通过 `getBean()` 方法动态获取 Bean 实例。

  作用：

  ​	通过配置文件或注解动态创建对象，解耦对象创建与使用。

**适配器模式（Adapter Pattern）**

- Spring MVC 中的 **HandlerAdapter**，适配不同类型的控制器（如注解控制器、接口实现控制器）。

- Spring 集成其他框架（如 HibernateTemplate、RedisTemplate）时，提供统一接口。

  作用：

  ​	在不同接口之间进行转换，实现兼容性。

**装饰者模式（Decorator Pattern）**

- Bean 的增强机制，比如通过 `@Primary` 或 `@Qualifier` 注解实现不同版本的 Bean 装饰。

- AOP 的实现本质上也可以看作装饰者模式的应用。

  作用：

  ​	动态为对象添加新功能。

**代理模式（Proxy Pattern）**

- Spring AOP（面向切面编程）使用动态代理实现功能增强，例如事务管理、日志记录。

- JDK 动态代理（接口）和 CGLIB 动态代理（类继承）。

  作用：

  ​	在不修改目标对象代码的情况下增强其功能。

**观察者模式（Observer Pattern）**

- Spring 的事件机制（`ApplicationEvent` 和 `ApplicationListener`）。

- Bean 的生命周期事件，如容器刷新或关闭通知。

  作用：

  ​	实现组件之间的解耦，通过事件驱动进行通信。

**策略模式（Strategy Pattern）**

- Spring 的 **TaskExecutor** 和 **Transaction Management**，根据不同场景选择具体的执行策略。

- 数据访问策略（如 Hibernate、JPA 的实现选择）。

  作用：

  ​	动态选择合适的算法或策略实现。

**职责链模式（Chain of Responsibility Pattern）**

- Spring Security 的过滤器链。

- Spring MVC 的拦截器链（`HandlerInterceptor`）。

  作用：

  ​	将请求在多个对象之间传递，动态分配职责。





## Spring Boot、Spring MVC 和 Spring 有什么区别

spring是⼀个IOC容器，⽤来管理Bean，使⽤依赖注⼊实现控制反转，可以很⽅便的整合各种框架，提 供AOP机制弥补OOP的代码重复问题、更⽅便将不同类不同⽅法中的共同处理抽取成切⾯、⾃动注⼊给 ⽅法执⾏，⽐如⽇志、异常等

springmvc是spring对web框架的⼀个解决⽅案，提供了⼀个总的前端控制器Servlet，⽤来接收请求， 然后定义了⼀套路由策略（url到handle的映射）及适配执⾏handle，将handle结果使⽤视图解析技术⽣ 成视图展现给前端

springboot是spring提供的⼀个快速开发⼯具包，让程序员能更⽅便、更快速的开发spring+springmvc 应⽤，简化了配置（约定了默认配置），整合了⼀系列的解决⽅案（starter机制）、redis、 mongodb、es，可以开箱即⽤







## Spring MVC ⼯作流程

1. 用户发送请求至前端控制器DispatcherServlet。
2. DispatcherServlet收到请求调用HandlerMapping处理器映射器。
3. 处理器映射器找到具体的处理器（可以根据l配置、注解进行查找），生成处理器及处理器拦截器(如果有则生成)一并返回给DispatcherServlet.。
4. DispatcherServlet调用HandlerAdapter处理器适配器。
5. HandlerAdapter经过适配调用具体的处理器(Controller,也叫后端控制器)
6. Controller执行完成返▣ModelAndView。
7. HandlerAdapter将controller执行结果ModelAndView返▣给DispatcherServlet。8)DispatcherServlet将ModelAndView传给ViewReslover视图解析器。学院周
8. ViewReslover解析后返回具体View。
9. DispatcherServlet根据View进行渲染视图（即将模型数据填充至视图中）。
10. DispatcherServlet响应用户。





## Spring MVC的主要组件？

Handler：也就是处理器。它直接应对着MVC中的C也就是Controller层，它的具体表现形式有很多，可 以是类，也可以是⽅法。在Controller层中@RequestMapping标注的所有⽅法都可以看成是⼀个 Handler，只要可以实际处理请求就可以是Handler

1. **HandlerMapping**

   initHandlerMappings(context)，处理器映射器，根据⽤户请求的资源uri来查找Handler的。在 SpringMVC中会有很多请求，每个请求都需要⼀个Handler处理，具体接收到⼀个请求之后使⽤哪个 Handler进⾏，这就是HandlerMapping需要做的事。

2. **HandlerAdapter**

   initHandlerAdapters(context)，适配器。因为SpringMVC中的Handler可以是任意的形式，只要能处理 请求就ok，但是Servlet需要的处理⽅法的结构却是固定的，都是以request和response为参数的⽅法。 如何让固定的Servlet处理⽅法调⽤灵活的Handler来进⾏处理呢？这就是HandlerAdapter要做的事情。 Handler是⽤来⼲活的⼯具；HandlerMapping⽤于根据需要⼲的活找到相应的⼯具；HandlerAdapter 是使⽤⼯具⼲活的⼈。

3. **HandlerExceptionResolver**

   initHandlerExceptionResolvers(context)， 其它组件都是⽤来⼲活的。在⼲活的过程中难免会出现问 题，出问题后怎么办呢？这就需要有⼀个专⻔的⻆⾊对异常情况进⾏处理，在SpringMVC中就是 HandlerExceptionResolver。具体来说，此组件的作⽤是根据异常设置ModelAndView，之后再交给 render⽅法进⾏渲染。

4. **ViewResolver**

   initViewResolvers(context)，ViewResolver⽤来将String类型的视图名和Locale解析为View类型的视 图。View是⽤来渲染⻚⾯的，也就是将程序返回的参数填⼊模板⾥，⽣成html（也可能是其它类型）⽂ 件。这⾥就有两个关键问题：使⽤哪个模板？⽤什么技术（规则）填⼊参数？这其实是ViewResolver主 要要做的⼯作，ViewResolver需要找到渲染所⽤的模板和所⽤的技术（也就是视图的类型）进⾏渲染， 具体的渲染过程则交由不同的视图⾃⼰完成。

5. **RequestToViewNameTranslator**

   initRequestToViewNameTranslator(context)，ViewResolver是根据ViewName查找View，但有的 Handler处理完后并没有设置View也没有设置ViewName，这时就需要从request获取ViewName了，如 何从request中获取ViewName就是RequestToViewNameTranslator要做的事情了。 RequestToViewNameTranslator在Spring MVC容器⾥只可以配置⼀个，所以所有request到 ViewName的转换规则都要在⼀个Translator⾥⾯全部实现。

6. **LocaleResolver**

   initLocaleResolver(context)， 解析视图需要两个参数：⼀是视图名，另⼀个是Locale。视图名是处理 器返回的，Locale是从哪⾥来的？这就是LocaleResolver要做的事情。LocaleResolver⽤于从request 解析出Locale，Locale就是zh-cn之类，表示⼀个区域，有了这个就可以对不同区域的⽤户显示不同的 结果。SpringMVC主要有两个地⽅⽤到了Locale：⼀是ViewResolver视图解析的时候；⼆是⽤到国际 化资源或者主题的时候。

7. **ThemeResolver**

   initThemeResolver(context)，⽤于解析主题。SpringMVC中⼀个主题对应⼀个properties⽂件，⾥⾯ 存放着跟当前主题相关的所有资源、如图⽚、css样式等。SpringMVC的主题也⽀持国际化，同⼀个主 题不同区域也可以显示不同的⻛格。SpringMVC中跟主题相关的类有 ThemeResolver、ThemeSource 和Theme。主题是通过⼀系列资源来具体体现的，要得到⼀个主题的资源，⾸先要得到资源的名称，这 是ThemeResolver的⼯作。然后通过主题名称找到对应的主题（可以理解为⼀个配置）⽂件，这是 ThemeSource的⼯作。最后从主题中获取资源就可以了。

8. **MultipartResolver**

   initMultipartResolver(context)，⽤于处理上传请求。处理⽅法是将普通的request包装成 MultipartHttpServletRequest，后者可以直接调⽤getFile⽅法获取File，如果上传多个⽂件，还可以调 ⽤getFileMap得到FileName->File结构的Map。此组件中⼀共有三个⽅法，作⽤分别是判断是不是上传 请求，将request包装成MultipartHttpServletRequest、处理完后清理上传过程中产⽣的临时资源。

9. **FlashMapManager**

   initFlashMapManager(context)，⽤来管理FlashMap的，FlashMap主要⽤在redirect中传递参数。





## Spring Boot ⾃动配置原理？

@Import  + @Configuration   +  Spring spi 

⾃动配置类由各个starter提供，使⽤@Configuration  + @Bean定义配置类，放到META INF/spring.factories下

使⽤Spring spi扫描META-INF/spring.factories下的配置类

使⽤@Import导⼊⾃动配置类





## 如何理解 Spring Boot 中的 Starter

使⽤spring + springmvc使⽤，如果需要引⼊mybatis等框架，需要到xml中定义mybatis需要的bean

starter就是定义⼀个starter的jar包，写⼀个@Configuration配置类、将这些bean定义在⾥⾯，然后在 starter包的META-INF/spring.factories中写⼊该配置类，springboot会按照约定来加载该配置类

开发⼈员只需要将相应的starter包依赖进应⽤，进⾏相应的属性配置（使⽤默认配置时，不需要配 置），就可以直接进⾏代码开发，使⽤对应的功能了，⽐如mybatis-spring-boot--starter，spring boot-starter-redis





## 什么是嵌⼊式服务器？为什么要使⽤嵌⼊式服务器?

节省了下载安装tomcat，应⽤也不需要再打war包，然后放到webapp⽬录下再运⾏

只需要⼀个安装了 Java 的虚拟机，就可以直接在上⾯部署应⽤程序了

springboot已经内置了tomcat.jar，运⾏main⽅法时会去启动tomcat，并利⽤tomcat的spi机制加载 springmvc





## Spring Boot中常⽤注解及其底层实现

1. @SpringBootApplication注解：这个注解标识了⼀个SpringBoot⼯程，它实际上是另外三个注解 的组合，这三个注解是：

   a.  @SpringBootConfiguration：这个注解实际就是⼀个@Configuration，表示启动类也是⼀个 配置类

   b.  @EnableAutoConfiguration：向Spring容器中导⼊了⼀个Selector，⽤来加载ClassPath下 SpringFactories中所定义的⾃动配置类，将这些⾃动加载为配置Bean

   c.  @ComponentScan：标识扫描路径，因为默认是没有配置实际扫描路径，所以SpringBoot扫 描的路径是启动类所在的当前⽬录

2. @Bean注解：⽤来定义Bean，类似于XML中的标签，Spring在启动时，会对加了@Bean注 解的⽅法进⾏解析，将⽅法的名字做为beanName，并通过执⾏⽅法得到bean对象

3. @Controller、@Service、@ResponseBody、@Autowired都可以说





## Spring Boot是如何启动Tomcat的

1. ⾸先，SpringBoot在启动时会先创建⼀个Spring容器
2. 在创建Spring容器过程中，会利⽤@ConditionalOnClass技术来判断当前classpath中是否存在 Tomcat依赖，如果存在则会⽣成⼀个启动Tomcat的Bean
3. Spring容器创建完之后，就会获取启动Tomcat的Bean，并创建Tomcat对象，并绑定端⼝等，然后 启动Tomcat





## Spring Boot中配置⽂件的加载顺序是怎样的？

优先级从⾼到低，⾼优先级的配置覆盖低优先级的配置，所有配置会形成互补配置。

1. 命令⾏参数。所有的配置都可以在命令⾏上进⾏指定；
2. Java系统属性（System.getProperties()）；
3. 操作系统环境变量 ；
4. jar包外部的application-{profile}.properties或application.yml(带spring.profile)配置⽂件
5. jar包内部的application-{profile}.properties或application.yml(带spring.profile)配置⽂件 再来加 载不带profile
6. jar包外部的application.properties或application.yml(不带spring.profile)配置⽂件
7. jar包内部的application.properties或application.yml(不带spring.profile)配置⽂件
8. @Configuration注解类上的@PropertySource





##  Mybatis的优缺点

优点：

1. 基于 SQL 语句编程，相当灵活，不会对应⽤程序或者数据库的现有设计造成任何影响，SQL 写在  XML ⾥，解除 sql 与程序代码的耦合，便于统⼀管理；提供 XML 标签， ⽀持编写动态 SQL 语 句， 并可重⽤。
2. 与 JDBC 相⽐，减少了 50%以上的代码量，消除了 JDBC ⼤量冗余的代码，不需要⼿动开关连 接；
3. 很好的与各种数据库兼容（ 因为 MyBatis 使⽤ JDBC 来连接数据库，所以只要JDBC ⽀持的数据 库 MyBatis 都⽀持）。
4. 能够与 Spring 很好的集成；
5. 提供映射标签， ⽀持对象与数据库的 ORM 字段关系映射； 提供对象关系映射标签， ⽀持对象关 系组件维护。

缺点：

1. SQL 语句的编写⼯作量较⼤， 尤其当字段多、关联表多时， 对开发⼈员编写SQL 语句的功底有⼀ 定要求。
2. SQL 语句依赖于数据库， 导致数据库移植性差， 不能随意更换数据库。





## MyBatis 与Hibernate 有哪些不同？

SQL 和 ORM 的争论，永远都不会终⽌

**开发速度的对⽐：**

Hibernate的真正掌握要⽐Mybatis难些。Mybatis框架相对简单很容易上⼿，但也相对简陋些。 ⽐起两者的开发速度，不仅仅要考虑到两者的特性及性能，更要根据项⽬需求去考虑究竟哪⼀个更适合 项⽬开发，⽐如：⼀个项⽬中⽤到的复杂查询基本没有，就是简单的增删改查，这样选择hibernate效率 就很快了，因为基本的sql语句已经被封装好了，根本不需要你去写sql语句，这就节省了⼤量的时间， 但是对于⼀个⼤型项⽬，复杂语句较多，这样再去选择hibernate就不是⼀个太好的选择，选择mybatis 就会加快许多，⽽且语句的管理也⽐较⽅便。

**开发⼯作量的对⽐：**

Hibernate的查询会将表中的所有字段查询出来，这⼀点会有性能消耗。Hibernate也可以⾃⼰写SQL来 指定需要查询的字段，但这样就破坏了Hibernate开发的简洁性。⽽Mybatis的SQL是⼿动编写的，所以 可以按需求指定查询的字段。 Hibernate HQL语句的调优需要将SQL打印出来，⽽Hibernate的SQL被很多⼈嫌弃因为太丑了。 MyBatis的SQL是⾃⼰⼿动写的所以调整⽅便。但Hibernate具有⾃⼰的⽇志统计。Mybatis本身不带⽇ 志统计，使⽤Log4j进⾏⽇志记录。

Hibernate HQL语句的调优需要将SQL打印出来，⽽Hibernate的SQL被很多⼈嫌弃因为太丑了。 MyBatis的SQL是⾃⼰⼿动写的所以调整⽅便。但Hibernate具有⾃⼰的⽇志统计。Mybatis本身不带⽇ 志统计，使⽤Log4j进⾏⽇志记录。

**对象管理的对⽐：**

Hibernate 是完整的对象/关系映射解决⽅案，它提供了对象状态管理（state management）的功能， 使开发者不再需要理会底层数据库系统的细节。也就是说，相对于常⻅的 JDBC/SQL 持久层⽅案中需 要管理 SQL 语句，Hibernate采⽤了更⾃然的⾯向对象的视⻆来持久化 Java 应⽤中的数据。

换句话说，使⽤ Hibernate 的开发者应该总是关注对象的状态（state），不必考虑 SQL 语句的执⾏。 这部分细节已经由 Hibernate 掌管妥当，只有开发者在进⾏系统性能调优的时候才需要进⾏了解。⽽ MyBatis在这⼀块没有⽂档说明，⽤户需要对对象⾃⼰进⾏详细的管理。

**缓存机制对⽐：**

相同点：都可以实现⾃⼰的缓存或使⽤其他第三⽅缓存⽅案，创建适配器来完全覆盖缓存⾏为。

不同点：Hibernate的⼆级缓存配置在SessionFactory⽣成的配置⽂件中进⾏详细配置，然后再在具体 的表-对象映射中配置是哪种缓存。

MyBatis的⼆级缓存配置都是在每个具体的表-对象映射中进⾏详细配置，这样针对不同的表可以⾃定义 不同的缓存机制。并且Mybatis可以在命名空间中共享相同的缓存配置和实例，通过Cache-ref来实现。

两者⽐较：因为Hibernate对查询对象有着良好的管理机制，⽤户⽆需关⼼SQL。所以在使⽤⼆级缓存 时如果出现脏数据，系统会报出错误并提示。

⽽MyBatis在这⼀⽅⾯，使⽤⼆级缓存时需要特别⼩⼼。如果不能完全确定数据更新操作的波及范围， 避免Cache的盲⽬使⽤。否则，脏数据的出现会给系统的正常运⾏带来很⼤的隐患。

Hibernate功能强⼤，数据库⽆关性好，O/R映射能⼒强，如果你对Hibernate相当精通，⽽且对 Hibernate进⾏了适当的封装，那么你的项⽬整个持久层代码会相当简单，需要写的代码很少，开发速度很快，⾮常爽。

Hibernate的缺点就是学习⻔槛不低，要精通⻔槛更⾼，⽽且怎么设计O/R映射，在性能和对象模型之间 如何权衡取得平衡，以及怎样⽤好Hibernate⽅⾯需要你的经验和能⼒都很强才⾏。

iBATIS⼊⻔简单，即学即⽤，提供了数据库查询的⾃动对象绑定功能，⽽且延续了很好的SQL使⽤经 验，对于没有那么⾼的对象模型要求的项⽬来说，相当完美。

iBATIS的缺点就是框架还是⽐较简陋，功能尚有缺失，虽然简化了数据绑定代码，但是整个底层数据库 查询实际还是要⾃⼰写的，⼯作量也⽐较⼤，⽽且不太容易适应快速数据库修改。





## \#{ }和${ }的区别是什么？

\#{}是预编译处理、是占位符， ${}是字符串替换、是拼接符。

Mybatis 在处理#{}时，会将 sql 中的#{}替换为?号，调⽤ PreparedStatement 来赋值；

Mybatis 在处理 时，就是把 {}替换成变量的值，调⽤ Statement 来赋值；

\#{} 的变量替换是在DBMS 中、变量替换后，#{} 对应的变量⾃动加上单引号，{} 的变量替换是在  DBMS 外、变量替换后，{} 对应的变量不会加上单引号

使⽤#{}可以有效的防⽌ SQL 注⼊， 提⾼系统安全性。





## 简述 Mybatis 的插件运⾏原理，如何编写⼀个插件。

Mybatis 只⽀持针对 ParameterHandler、ResultSetHandler、StatementHandler、Executor 这 4 种 接⼝的插件， Mybatis 使⽤ JDK 的动态代理， 为需要拦截的接⼝⽣成代理对象以实现接⼝⽅法拦截功 能， 每当执⾏这 4 种接⼝对象的⽅法时，就会进⼊拦截⽅法，具体就是 InvocationHandler 的  invoke() ⽅法， 拦截那些你指定需要拦截的⽅法。

编写插件： 实现 Mybatis 的 Interceptor 接⼝并复写 intercept()⽅法， 然后在给插件编写注解， 指定 要拦截哪⼀个接⼝的哪些⽅法即可， 在配置⽂件中配置编写的插件。

```java
 @Intercepts({@Signature(type = StatementHandler.class, method = "query", 
 args = {Statement.class, ResultHandler.class}),
 @Signature(type = StatementHandler.class, method = "update", 
 args = {Statement.class}),
 @Signature(type = StatementHandler.class, method = "batch", 
 args = { Statement.class })})
 @Component
 invocation.proceed()执⾏具体的业务逻辑
```





