---
title: SpringBoot
tags:
  - Java
---


**本文作者** [郭圣_Guo](https://blog.csdn.net/qq_41978509?type=blog)

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)从今天开始就进入微服务阶段
=================================================================================================================================================================================================================================================================================================================================================================================================================================================================



[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)1.HelloWorld
================================================================================================================================================================================================================================================================================================================================================================================================================================================================

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)1.1回顾什么是Spring
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Spring是一个开源框架，2003 年兴起的一个轻量级的Java 开发框架，作者：Rod Johnson 。

**Spring是为了解决企业级应用开发的复杂性而创建的，简化开发。**

Spring是如何简化Java开发的

为了降低Java开发的复杂性，Spring采用了以下4种关键策略：

1、基于POJO的轻量级和最小侵入性编程，所有东西都是bean；

2、通过IOC，依赖注入（DI）和面向接口实现松耦合；

3、基于切面（AOP）和惯例进行声明式编程；

4、通过切面和模版减少样式代码，RedisTemplate，xxxTemplate；

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)1.2什么是SpringBoot
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

​ 学过javaweb的同学就知道，开发一个web应用，从最初开始接触Servlet结合Tomcat, 跑出一个Hello Wolrld程序，是要经历特别多的步骤；后来就用了框架Struts，再后来是SpringMVC，到了现在的SpringBoot，过一两年又会有其他web框架出现；你们有经历过框架不断的演进，然后自己开发项目所有的技术也在不断的变化、改造吗？建议都可以去经历一遍；

​ 言归正传，什么是SpringBoot呢，**就是一个javaweb的开发框架**，和SpringMVC类似，对比其他javaweb框架的好处，官方说是简化开发，约定大于配置， you can “just run”，能迅速的开发web应用，几行代码开发一个http接口。

​ 所有的技术框架的发展似乎都遵循了一条主线规律：从一个复杂应用场景 衍生 一种规范框架，人们只需要进行各种配置而不需要自己去实现它，这时候强大的配置功能成了优点；发展到一定程度之后，人们根据实际生产应用情况，选取其中实用功能和设计精华，重构出一些轻量级的框架；之后为了提高开发效率，嫌弃原先的各类配置过于麻烦，于是开始提倡“约定大于配置”，进而衍生出一些一站式的解决方案。

​ 是的这就是Java企业级应用->J2EE->spring->springboot的过程。

​ 随着 Spring 不断的发展，涉及的领域越来越多，项目整合开发需要配合各种各样的文件，慢慢变得不那么易用简单，违背了最初的理念，甚至人称配置地狱。Spring Boot 正是在这样的一个背景下被抽象出来的开发框架，目的为了让大家更容易的使用 Spring 、更容易的集成各种常用的中间件、开源软件；

​ Spring Boot 基于 Spring 开发，Spirng Boot 本身并不提供 Spring 框架的核心特性以及扩展功能，只是用于快速、敏捷地开发新一代基于 Spring 框架的应用程序。也就是说，它并不是用来替代 Spring 的解决方案，而是和 Spring 框架紧密结合用于提升 Spring 开发者体验的工具。Spring Boot 以**约定大于配置的核心思想**，默认帮我们进行了很多设置，多数 Spring Boot 应用只需要很少的 Spring 配置。同时它集成了大量常用的第三方库配置（例如 Redis、MongoDB、Jpa、RabbitMQ、Quartz 等等），Spring Boot 应用中这些第三方库几乎可以零配置的开箱即用。

​ 简单来说就是SpringBoot其实不是什么新的框架，它默认配置了很多框架的使用方式，就像maven整合了所有的jar包，spring boot整合了所有的框架 。

​ Spring Boot 出生名门，从一开始就站在一个比较高的起点，又经过这几年的发展，生态足够完善，Spring Boot 已经当之无愧成为 Java 领域最热门的技术。

**Spring Boot的主要优点：**

*   为所有Spring开发者更快的入门
*   **开箱即用**，提供各种默认配置来简化项目配置
*   内嵌式容器简化Web项目
*   没有冗余代码生成和XML配置的要求

真的很爽，我们快速去体验开发个接口的感觉吧！

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)1.3微服务架构
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

​ 微服务是一种架构风格，他要求我们在开发一个应用的时候，这个应用必须建成一系列小服务组合，可以通过http方式进行通信。

​ 所谓微服务加购，就是打破之前all in one的架构方式，把每个功能元素独立出来，把独立出来的功能元素的动态组合，需要的功能元素才去拿来组合，需要多一些可以整合多个功能元素，所以微服务架构是对功能元素进行赋值，而没有对整个应用进行复制，这样做的好处是：

*   节省了调用资源
*   每个功能元素的服务都是一个可替换的，可独立升级的软件代码

程序核心：高内聚（在划分模块时，要把功能关系紧密的放到一个模块中）  
低耦合（模块之间的联系越少越好，接口越简单越好）

论文地址：https://martinfowler.com/articles/microservices.html#CharacteristicsOfAMicroserviceArchitecture

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424204523940.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

*   构建一个个功能独立的微服务应用单元，可以使用springboot，可以帮我们快速构建一个应用
*   大型分布式网络服务的调用，这部分springcloud来完成，实现分布式
*   在分布式中间，进行流式数据计算，批处理，我们有spring cloud data flow
*   spring为我们想清楚了整个开始构建应用到大型分布式应用全流程方案

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424204555921.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)2.第一个SpringBoot程序
=====================================================================================================================================================================================================================================================================================================================================================================================================================================================================

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)2.1环境配置
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

我们将学习如何快速的创建一个Spring Boot应用，并且实现一个简单的Http请求处理。通过这个例子对Spring Boot有一个初步的了解，并体验其结构简单、开发快速的特性。

我的环境准备：

*   java version “1.8.0\_181”
*   Maven-3.6.1
*   SpringBoot 2.x 最新版

开发工具：

*   IDEA

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)2.2创建基础项目说明
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Spring官方提供了非常方便的工具让我们快速构建应用，IDEA也集成了这个网站

Spring Initializr：https://start.spring.io/

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)2.3.1项目创建方式一

**使用Spring Initializr 的 Web页面创建项目**

①打开 https://start.spring.io/

②填写项目信息

③点击”Generate Project“按钮生成项目；下载此项目

④解压项目包，并用IDEA以Maven项目导入，一路下一步即可，直到项目导入完毕。

⑤如果是第一次使用，可能速度会比较慢，包比较多、需要耐心等待一切就绪。

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)2.3.2项目创建方式二

使用 IDEA 直接创建项目

①创建一个新项目

②选择spring initalizr ， 可以看到默认就是去官网的快速构建工具那里实现

③填写项目信息

④选择初始化的组件（初学勾选 Web 即可）

⑤填写项目路径

⑥等待项目构建成功

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)2.3.3项目结构分析：

通过上面步骤完成了基础项目的创建。就会自动生成以下文件。

1、程序的主启动类（程序的主入口）

2、一个 application.properties 配置文件（SpringBoot的核心配置文件）

3、一个 测试类

4、一个 pom.xml

pom.xml文件分析：  
打开pom.xml，看看Spring Boot项目的依赖：

```
<!-- 父依赖 -->
<parent>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-parent</artifactId>
    <version>2.2.5.RELEASE</version>
    <relativePath/>
</parent>

<dependencies>
    <!-- web场景启动器 -->
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-web</artifactId>
    </dependency>
    <!-- springboot单元测试 -->
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-test</artifactId>
        <scope>test</scope>
        <!-- 剔除依赖 -->
        <exclusions>
            <exclusion>
                <groupId>org.junit.vintage</groupId>
                <artifactId>junit-vintage-engine</artifactId>
            </exclusion>
        </exclusions>
    </dependency>
</dependencies>

<build>
    <plugins>
        <!-- 打包插件 -->
        <plugin>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-maven-plugin</artifactId>
        </plugin>
    </plugins>
</build>

```

编写一个http接口

①在主程序的同级目录下，新建一个controller包，一定要在同级目录下，否则识别不到  
②在包中新建一个HelloController类

```
@RestController
public class HelloController {

   @RequestMapping("/hello")
   public String hello() {
       return "Hello World";
   }
   
}

```

③编写完毕后，从主程序启动项目，浏览器发起请求，看页面返回；控制台输出了 Tomcat 访问的端口号！

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424204618304.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

更改端口号：在application资源文件中配置

```
 server.port = xxxx

```

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)2.3SpringBoot特点
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)2.3.1依赖管理

*   父项目做依赖管理

```
依赖管理    
<parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>2.3.4.RELEASE</version>
</parent>

他的父项目
 <parent>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-dependencies</artifactId>
    <version>2.3.4.RELEASE</version>
  </parent>

几乎声明了所有开发中常用的依赖的版本号,自动版本仲裁机制

```

*   开发导入starter场景启动器

```
1、见到很多 spring-boot-starter-* ： *就某种场景
2、只要引入starter，这个场景的所有常规需要的依赖我们都自动引入
3、SpringBoot所有支持的场景
https://docs.spring.io/spring-boot/docs/current/reference/html/using-spring-boot.html#using-boot-starter
4、见到的  *-spring-boot-starter： 第三方为我们提供的简化开发的场景启动器。
5、所有场景启动器最底层的依赖
<dependency>
  <groupId>org.springframework.boot</groupId>
  <artifactId>spring-boot-starter</artifactId>
  <version>2.3.4.RELEASE</version>
  <scope>compile</scope>
</dependency>

```

*   无需关注版本号，自动版本仲裁

```
1、引入依赖默认都可以不写版本
2、引入非版本仲裁的jar，要写版本号。

```

*   可以修改默认版本号

```
1、查看spring-boot-dependencies里面规定当前依赖的版本 用的 key。
2、在当前项目里面重写配置
    <properties>
        <mysql.version>5.1.43</mysql.version>
    </properties>

```

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)2.3.2自动配置

*   自动配好Tomcat
    
    *   引入Tomcat依赖。
        
    *   配置Tomcat
        

```
 <dependency>
       <groupId>org.springframework.boot</groupId>
       <artifactId>spring-boot-starter-tomcat</artifactId>
       <version>2.3.4.RELEASE</version>
       <scope>compile</scope>
     </dependency>

```

自动配好SpringMVC

*   引入SpringMVC全套组件
    
*   自动配好SpringMVC常用组件（功能）
    
*   自动配好Web常见功能，如：字符编码问题
    
*   SpringBoot帮我们配置好了所有web开发的常见场景
    
*   默认的包结构
    
*   主程序所在包及其下面的所有子包里面的组件都会被默认扫描进来
    
*   无需以前的包扫描配置
    
*   想要改变扫描路径，@SpringBootApplication(scanBasePackages=**“com.guo”**)
    

或者@ComponentScan 指定扫描路径

*   @SpringBootAppliction注解

```
 @SpringBootApplication
 等同于
 @SpringBootConfiguration
 @EnableAutoConfiguration
 @ComponentScan("com.guo.boot")

```

*   各种配置拥有默认值
    *   默认配置最终都是映射到某个类上，如：MultipartProperties
        
    *   配置文件的值最终会绑定每个类上，这个类会在容器中创建对象
        
    *   按需加载所有自动配置项
        
        *   非常多的starter
        *   引入了哪些场景这个场景的自动配置才会开启
        *   SpringBoot所有的自动配置功能都在 **spring-boot-autoconfigure** 包里面

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)2.4容器功能
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)2.4.1组件添加

1.@Configuration 给类添加这个注解后相当于原来的向bean注入的bean.xml文件

*   基本使用
    *   Full模式(全配置)和Lite模式（轻量级配置）

代码示例：

```
#############################Configuration使用示例######################################################
/**
 * 1、配置类里面使用@Bean标注在方法上给容器注册组件，默认也是单实例的
 * 2、配置类本身也是组件
 * 3、proxyBeanMethods：代理bean的方法
 *      Full(proxyBeanMethods = true)、【保证每个@Bean方法被调用多少次返回的组件都是单实例的】
 *      Lite(proxyBeanMethods = false)【每个@Bean方法被调用多少次返回的组件都是新创建的】
 *      组件依赖必须使用Full模式默认,proxyBeanMethods = true。
 		其他默认是否Lite模式：proxyBeanMethods = flase
 *
 *
 *
 */
@Configuration(proxyBeanMethods = true) //告诉SpringBoot这是一个配置类 == 配置文件
public class MyConfig {

    /**
     * Full:外部无论对配置类中的这个组件注册方法调用多少次获取的都是之前注册容器中的单实例对象
     * @return
     */
    @Bean //给容器中添加组件。以方法名作为组件的id。返回类型就是组件类型。返回的值，就是组件在容器中的实例
    public User user01(){
        User zhangsan = new User("zhangsan", 18);
        //user组件依赖了Pet组件
        zhangsan.setPet(tomcatPet());
        return zhangsan;
    }

    @Bean("tom")
    public Pet tomcatPet(){
        return new Pet("tomcat");
    }
}

################################@Configuration测试代码如下########################################
@SpringBootConfiguration
@EnableAutoConfiguration
@ComponentScan("com.atguigu.boot")
public class MainApplication {

    public static void main(String[] args) {
        //1、返回我们IOC容器
        ConfigurableApplicationContext run = SpringApplication.run(MainApplication.class, args);

        //2、查看容器里面的组件
        String[] names = run.getBeanDefinitionNames();
        for (String name : names) {
            System.out.println(name);
        }

        //3、从容器中获取组件

        Pet tom01 = run.getBean("tom", Pet.class);

        Pet tom02 = run.getBean("tom", Pet.class);

        System.out.println("组件："+(tom01 == tom02));

        //4、com.atguigu.boot.config.MyConfig$$EnhancerBySpringCGLIB$$51f1e1ca@1654a892
        MyConfig bean = run.getBean(MyConfig.class);
        System.out.println(bean);

        //如果@Configuration(proxyBeanMethods = true)代理对象调用方法。SpringBoot总会检查这个组件是否在容器中有。
        //保持组件单实例
        User user = bean.user01();
        User user1 = bean.user01();
        System.out.println(user == user1);

        User user01 = run.getBean("user01", User.class);
        Pet tom = run.getBean("tom", Pet.class);

        System.out.println("用户的宠物："+(user01.getPet() == tom));

    }
}

```

2、@Bean、@Component、@Controller、@Service、@Repository

3、@ComponentScan、@Import  
@Import会给容器中自动创建这两个类型的组件

```
 * 4、@Import({User.class, DBHelper.class})
 *      给容器中自动创建出这两个类型的组件、默认组件的名字就是全类名
 */

@Import({User.class, DBHelper.class})
@Configuration(proxyBeanMethods = false) //告诉SpringBoot这是一个配置类 == 配置文件
public class MyConfig {
}

```

4.@Conditional（条件装配注解）

条件装配：当满足Conditional指定的条件，则进行组件注入

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424204635942.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

先看结论：当这个注解配置在类上时，只有这个类内注入了响应名称的组件才会生成相应的实体，

当配置在部分方法时，只有相应的被注入才可以生成实体，否则就不生效

```
=====================测试条件装配==========================
@Configuration(proxyBeanMethods = false) //告诉SpringBoot这是一个配置类 == 配置文件
//@ConditionalOnBean(name = "tom")
@ConditionalOnMissingBean(name = "tom")
public class MyConfig {

    /**
     * Full:外部无论对配置类中的这个组件注册方法调用多少次获取的都是之前注册容器中的单实例对象
     * @return
     */

    @Bean //给容器中添加组件。以方法名作为组件的id。返回类型就是组件类型。返回的值，就是组件在容器中的实例
    public User user01(){
        User zhangsan = new User("zhangsan", 18);
        //user组件依赖了Pet组件
        zhangsan.setPet(tomcatPet());
        return zhangsan;
    }

    @Bean("tom22")
    public Pet tomcatPet(){
        return new Pet("tomcat");
    }
}

public static void main(String[] args) {
        //1、返回我们IOC容器
        ConfigurableApplicationContext run = SpringApplication.run(MainApplication.class, args);

        //2、查看容器里面的组件
        String[] names = run.getBeanDefinitionNames();
        for (String name : names) {
            System.out.println(name);
        }

        boolean tom = run.containsBean("tom");
        System.out.println("容器中Tom组件："+tom);

        boolean user01 = run.containsBean("user01");
        System.out.println("容器中user01组件："+user01);

        boolean tom22 = run.containsBean("tom22");
        System.out.println("容器中tom22组件："+tom22);

    }

```

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)2.4.2原生配置文件引入

@ImportResource

```
======================beans.xml=========================
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:context="http://www.springframework.org/schema/context"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd http://www.springframework.org/schema/context https://www.springframework.org/schema/context/spring-context.xsd">

    <bean id="haha" class="com.atguigu.boot.bean.User">
        <property name="name" value="zhangsan"></property>
        <property name="age" value="18"></property>
    </bean>

    <bean id="hehe" class="com.atguigu.boot.bean.Pet">
        <property name="name" value="tomcat"></property>
    </bean>
</beans>

```

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)2.4.3配置绑定

如何使用Java读取到properties文件中的内容，并且把它封装到JavaBean中，以供随时使用；

```
public class getProperties {
     public static void main(String[] args) throws FileNotFoundException, IOException {
         Properties pps = new Properties();
         pps.load(new FileInputStream("a.properties"));
         Enumeration enum1 = pps.propertyNames();//得到配置文件的名字
         while(enum1.hasMoreElements()) {
             String strKey = (String) enum1.nextElement();
             String strValue = pps.getProperty(strKey);
             System.out.println(strKey + "=" + strValue);
             //封装到JavaBean。
         }
     }
 }

```

**1.@ConfigurationProperties**  
注意想要使用这个注解必须声明组件注解@Component

```
/**
 * 只有在容器中的组件，才会拥有SpringBoot提供的强大功能
 */
@Component
@ConfigurationProperties(prefix = "mycar")
public class Car {

    private String brand;
    private Integer price;

    public String getBrand() {
        return brand;
    }

    public void setBrand(String brand) {
        this.brand = brand;
    }

    public Integer getPrice() {
        return price;
    }

    public void setPrice(Integer price) {
        this.price = price;
    }

    @Override
    public String toString() {
        return "Car{" +
                "brand='" + brand + '\'' +
                ", price=" + price +
                '}';
    }
}

```

对应的application.property文件：

```
mycar.price = 100000
mycar.brand = BYD

```

@Component + @ConfigurationProperties

```
@EnableConfigurationProperties(Car.class)
//1、开启Car配置绑定功能
//2、把这个Car这个组件自动注册到容器中
public class MyConfig {
}

```

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)3.自动配置原理初探
==============================================================================================================================================================================================================================================================================================================================================================================================================================================================

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)3.1pom.xml
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   Spring-boot-dependencies:核心依赖在父工程中
*   我们在写或者引入springboot依赖的时候，不需要指定版本，因为有这些版本仓库

**启动器**

```
<!--启动器-->
<dependency>
  <groupId>org.springframework.boot</groupId>
  <artifactId>spring-boot-starter</artifactId>
</dependency>

```

*   启动器：说白了就是Springboot的启动场景
*   比如spring-boot-starter-web，他就会帮我们自动导入web环境所有的依赖
*   springboot会将所有的功能场景，都变成一个个的启动器
*   我们要使用什么功能，就值需要找到对应的启动器`starter`

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)3.2主程序
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

```
//标注这个类是一个springboot的应用
@SpringBootApplication
public class SpringbootStudyApplication {

    public static void main(String[] args) {
        //将springboot应用启动
        SpringApplication.run(SpringbootStudyApplication.class, args);
    }
}

```

在这个里面最重要的就是@SpringBootApplication这个注解了让我们点进去看看，发现他是一个派生注

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424204652788.png)

而这个注解也是一个派生注解，其中的关键功能由@Import提供，其导入的AutoConfigurationImportSelector的selectImports()方法通过SpringFactoriesLoader.loadFactoryNames()扫描所有具有META-INF/spring.factories的jar包。spring-boot-autoconfigure-x.x.x.x.jar里就有一个这样的spring.factories文件。

**注解**

```
//springboot的配置
@SpringBootConfiguration

	//spring配置类
  @Configuration 

	//说明这也是一个spring的组件
  @Component	

//自动配置
@EnableAutoConfiguration

	//自动配置包
	@AutoConfigurationPackage 

	//自动配置	
		@Import(AutoConfigurationPackages.Registrar.class)

	//自动配置导入选择
	@Import(AutoConfigurationImportSelector.class)

//获取所有的配置
List<String> configurations = getCandidateConfigurations(annotationMetadata, attributes);


```

获取候选的配置：

```
protected List<String> getCandidateConfigurations(AnnotationMetadata metadata, AnnotationAttributes attributes) {
  List<String> configurations = SpringFactoriesLoader.loadFactoryNames(getSpringFactoriesLoaderFactoryClass(),
                                                                       getBeanClassLoader());
  Assert.notEmpty(configurations, "No auto configuration classes found in META-INF/spring.factories. If you "
                  + "are using a custom packaging, make sure that file is correct.");
  return configurations;
}

```

但是\*\*一个简单的启动类并不简单！\*\*我们来分析一下这些注解都干了什么

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)3.3@SpringBootApplication
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

作用：标注在某个类上说明这个类是SpringBoot的主配置类 ， SpringBoot就应该运行这个类的main方法来启动SpringBoot应用

```
@SpringBootConfiguration
@EnableAutoConfiguration
@ComponentScan(
    excludeFilters = {@Filter(
    type = FilterType.CUSTOM,
    classes = {TypeExcludeFilter.class}
), @Filter(
    type = FilterType.CUSTOM,
    classes = {AutoConfigurationExcludeFilter.class}
)}
)
public @interface SpringBootApplication {
    // ......
}

```

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)3.3.1@ComponentScan

这个注解在Spring中很重要 ,它对应XML配置中的元素。

作用：自动扫描并加载符合条件的组件或者bean ， 将这个bean定义加载到IOC容器中

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)3.3.2@SpringBootConfiguration

作用：SpringBoot的配置类 ，标注在某个类上 ， 表示这是一个SpringBoot的配置类；

我们继续进去这个注解查看

```
// 点进去得到下面的 @Component
@Configuration
public @interface SpringBootConfiguration {}

@Component
public @interface Configuration {}

```

这里的 @Configuration，说明这是一个配置类 ，配置类就是对应Spring的xml 配置文件；

里面的 @Component 这就说明，启动类本身也是Spring中的一个组件而已，负责启动应用！

我们回到 SpringBootApplication 注解中继续看，而在这些个注解中最重要的就是@EnableAutoConfiguration，我们继续点进去看，在这些个注解中最重要的就是@EnableAutoConfiguration，我们继续点进去看

![](https://img-blog.csdnimg.cn/2021042420473755.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)3.3.3@EnableAutoConfiguration

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)3.4@EnableAutoConfiguration
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**@EnableAutoConfiguration ：开启自动配置功能**

以前我们需要自己配置的东西，而现在SpringBoot可以自动帮我们配置 ；@EnableAutoConfiguration告诉SpringBoot开启自动配置功能，这样自动配置才能生效；

点进注解继续查看：  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424204750291.png)

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)3.4.1@AutoConfigurationPackage

**翻译：自动配置包**

```
@Import({Registrar.class})
//利用Registrar导入一系列组件
//将指定的一个包下的所有组件导入进来？是主程序所在的包下
public @interface AutoConfigurationPackage {
}

```

**@import** ：Spring底层注解@import ， 给容器中导入一个组件

Registrar.class 作用：将主启动类的所在包及包下面所有子包里面的所有组件扫描到Spring容器 ；

这个分析完了，退到上一步，继续看

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)3.4.2@Import({AutoConfigurationImportSelector.class})

**给容器导入组件 ；**

​ 而这个注解也是一个派生注解，其中的关键功能由\*\*@Import\*\*提供，其导入的AutoConfigurationImportSelector的selectImports()方法通过SpringFactoriesLoader.loadFactoryNames()扫描所有具有META-INF/spring.factories的jar包。spring-boot-autoconfigure-x.x.x.x.jar里就有一个这样的spring.factories文件。

​ AutoConfigurationImportSelector ：自动配置导入选择器，那么它会导入哪些组件的选择器呢？我们点击去这个类看源码：

1、这个类中有一个这样的方法

```
// 获得候选的配置
protected List<String> getCandidateConfigurations(AnnotationMetadata metadata, AnnotationAttributes attributes) {
    //这里的getSpringFactoriesLoaderFactoryClass（）方法
    //返回的就是我们最开始看的启动自动导入配置文件的注解类；EnableAutoConfiguration
    List<String> configurations = SpringFactoriesLoader.loadFactoryNames(this.getSpringFactoriesLoaderFactoryClass(), this.getBeanClassLoader());
    Assert.notEmpty(configurations, "No auto configuration classes found in META-INF/spring.factories. If you are using a custom packaging, make sure that file is correct.");
    return configurations;
}

```

2、这个方法又调用了SpringFactoriesLoader 类的静态方法！我们进入SpringFactoriesLoader类loadFactoryNames() 方法

```

public static List<String> loadFactoryNames(Class<?> factoryClass, @Nullable ClassLoader classLoader) {
    String factoryClassName = factoryClass.getName();
    //这里它又调用了 loadSpringFactories 方法
    return (List)loadSpringFactories(classLoader).getOrDefault(factoryClassName, 						Collections.emptyList());
}

```

3、我们继续点击查看 loadSpringFactories 方法

```
private static Map<String, List<String>> loadSpringFactories(@Nullable ClassLoader classLoader) {
    //获得classLoader ， 我们返回可以看到这里得到的就是EnableAutoConfiguration标注的类本身
    MultiValueMap<String, String> result = (MultiValueMap)cache.get(classLoader);
    if (result != null) {
        return result;
    } else {
        try {
            //去获取一个资源 "META-INF/spring.factories"
            Enumeration<URL> urls = classLoader != null ? classLoader.getResources("META-INF/spring.factories") : ClassLoader.getSystemResources("META-INF/spring.factories");
            LinkedMultiValueMap result = new LinkedMultiValueMap();

            //将读取到的资源遍历，封装成为一个Properties
            while(urls.hasMoreElements()) {
                URL url = (URL)urls.nextElement();
                UrlResource resource = new UrlResource(url);
                Properties properties = PropertiesLoaderUtils.loadProperties(resource);
                Iterator var6 = properties.entrySet().iterator();

                while(var6.hasNext()) {
                    Entry<?, ?> entry = (Entry)var6.next();
                    String factoryClassName = ((String)entry.getKey()).trim();
                    String[] var9 = StringUtils.commaDelimitedListToStringArray((String)entry.getValue());
                    int var10 = var9.length;

                    for(int var11 = 0; var11 < var10; ++var11) {
                        String factoryName = var9[var11];
                        result.add(factoryClassName, factoryName.trim());
                    }
                }
            }
            
            cache.put(classLoader, result);
            return result;
        } catch (IOException var13) {
            throw new IllegalArgumentException("Unable to load factories from location [META-INF/spring.factories]", var13);
        }
    }
}

```

4.发现一个多次出现的文件：spring.factories，全局搜索它

spring.factories  
文件里面写死了spring-boot一启动就要给容器中加载的所有配置类

我们根据源头打开spring.factories ， 看到了很多自动配置的文件；这就是自动配置根源所在！  
这个spring.factories文件也是一组一组的key=value的形式，其中一个key是EnableAutoConfiguration类的全类名，而它的value是一个xxxxAutoConfiguration的类名的列表，这些类名以逗号分隔，如下图所示：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424204811530.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

​ 这个@EnableAutoConfiguration注解通过@SpringBootApplication被间接的标记在了Spring Boot的启动类上。在SpringApplication.run(…)的内部就会执行selectImports()方法，找到所有JavaConfig自动配置类的全限定名对应的class，然后将所有自动配置类加载到Spring容器中。

**WebMvcAutoConfiguration**  
![在这里插入图片描述](https://img-blog.csdnimg.cn/2021042420482575.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

可以看到这些一个个的都是JavaConfig配置类，而且都注入了一些Bean，可以找一些自己认识的类，看着熟悉一下！

所以，自动配置真正实现是从classpath中搜寻所有的META-INF/spring.factories配置文件 ，并将其中对应的 org.springframework.boot.autoconfigure. 包下的配置项，通过反射实例化为对应标注了 @Configuration的JavaConfig形式的IOC容器配置类 ， 然后将这些都汇总成为一个实例并加载到IOC容器中。

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)3.5自动配置生效
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

每一个XxxxAutoConfiguration自动配置类都是在某些条件之下才会生效的，这些条件的限制在Spring Boot中以注解的形式体现，常见的**条件注解**有如下几项：

```
@ConditionalOnBean：当容器里有指定的bean的条件下。

@ConditionalOnMissingBean：当容器里不存在指定bean的条件下。

@ConditionalOnClass：当类路径下有指定类的条件下。

@ConditionalOnMissingClass：当类路径下不存在指定类的条件下。

@ConditionalOnProperty：指定的属性是否有指定的值，比如@ConditionalOnProperties(prefix=”xxx.xxx”, value=”enable”, matchIfMissing=true)，代表当xxx.xxx为enable时条件的布尔值为true，如果没有设置的情况下也为true。

```

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)3.6例子
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

以ServletWebServerFactoryAutoConfiguration配置类为例，解释一下全局配置文件中的属性如何生效，比如：server.port=8081，是如何生效的（当然不配置也会有默认值，这个默认值来自于org.apache.catalina.startup.Tomcat）。  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424204837478.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

在ServletWebServerFactoryAutoConfiguration类上，有一个@EnableConfigurationProperties注解：**开启配置属性**，而它后面的参数是一个ServerProperties类，这就是约定大于配置的最终落地点。

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)3.7结论
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

springboot所有的自动配置都是在启动的时候扫描并加载，扫描了`spring.properties`配置文件，所有的自动配置类都在这里面，但是不定生效，因为要判断条件是否成立，只要导入了对应的start，就有对应的启动器，有了启动器我们自动装配就会生效，然后就配置成功

**步骤：**

1.  SpringBoot在启动的时候从类路径下的META-INF/spring.factories中获取EnableAutoConfiguration指定的值
2.  将这些值作为自动配置类导入容器 ， 自动配置类就生效 ， 帮我们进行自动配置工作；
3.  以前需要我们配置的文件，springboot帮我们配置了！
4.  整个J2EE的整体解决方案和自动配置都在springboot-autoconfigure的jar包中；
5.  整个J2EE的整体解决方案和自动配置都在springboot-autoconfigure的jar包中；
6.  它会给容器中导入非常多的自动配置类 （xxxAutoConfiguration）@Bean, 就是给容器中导入这个场景需要的所有组件 ， 并配置好这些组件 @Configuration；
7.  有了自动配置类 ， 免去了我们手动编写配置注入功能组件等的工作；

**SpringApplication**

我们最初以为就是运行了一个main方法，没想到却开启了一个服务；

```
@SpringBootApplication
public class SpringbootApplication {
    public static void main(String[] args) {
        SpringApplication.run(SpringbootApplication.class, args);
    }
}

```

**SpringApplication.run分析**

分析该方法主要分两部分，一部分是SpringApplication的实例化，二是run方法的执行；

SpringApplication

**这个类主要做了以下四件事情：**

1、推断应用的类型是普通的项目还是Web项目

2、查找并加载所有可用初始化器 ， 设置到initializers属性中

3、找出所有的应用程序监听器，设置到listeners属性中

4、推断并设置main方法的定义类，找到运行的主类

查看构造器：

```
public SpringApplication(ResourceLoader resourceLoader, Class... primarySources) {
    // ......
    this.webApplicationType = WebApplicationType.deduceFromClasspath();
    this.setInitializers(this.getSpringFactoriesInstances();
    this.setListeners(this.getSpringFactoriesInstances(ApplicationListener.class));
    this.mainApplicationClass = this.deduceMainApplicationClass();
}

```

关于springboot，谈谈你的理解：

*   springboot的自动装配
*   run()：  
    ①判断当前项目是普通项目还是web项目  
    ②推断并设置main方法的定义类，找到运行的主类  
    ③run方法里面有一些监听器，这些监听器是全局存在的，它的作用是获取上下文处理一些bean，所有的bean无论是加载还是生产初始化多存在。

![img](https://img-service.csdnimg.cn/img_convert/82b94b960a5c946bad5512f51d95262b.png)

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)4.Springboot配置文件
====================================================================================================================================================================================================================================================================================================================================================================================================================================================================

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)4.1配置文件
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

SpringBoot使用一个全局的配置文件 ， 配置文件名称是固定的

*   application.properties
    *   语法结构 ：key=value

```
server.port=8081

```

*   application.yaml
    *   语法结构 ：key:空格value

```
server:
  port: 8081

```

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)4.2yaml概述
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

YAML是 “YAML Ain’t a Markup Language” （YAML不是一种标记语言）的递归缩写。在开发的这种语言时，YAML 的意思其实是：“Yet Another Markup Language”（仍是一种标记语言）

**这种语言以数据作为中心，而不是以标记语言为重点！**

以前的配置文件，大多数都是使用xml来配置；比如一个简单的端口配置，我们来对比下yaml和xml

传统xml配置：

```
<server>
    <port>8081<port>
</server>

```

yaml配置：

```
server：
  prot: 8080

```

**yaml基础语法**

说明：语法要求严格！

1、空格不能省略

2、以缩进来控制层级关系，只要是左边对齐的一列数据都是同一个层级的。

3、属性和值的大小写都是十分敏感的。

**字面量：普通的值 \[ 数字，布尔值，字符串 \]**

字面量直接写在后面就可以 ， 字符串默认不用加上双引号或者单引号；

```
k: v

```

**注意**：

*   “ ” 双引号，不会转义字符串里面的特殊字符 ， 特殊字符会作为本身想表示的意思；
    
    比如 ：name: “kuang \\n shen” 输出 ：kuang 换行 shen
    
*   ‘’ 单引号，会转义特殊字符 ， 特殊字符最终会变成和普通字符一样输出
    
    比如 ：name: ‘kuang \\n shen’ 输出 ：kuang \\n shen
    

**对象、Map（键值对）**

```
#对象、Map格式
key: 
    value1:
    value2:

```

在下一行来写对象的属性和值得关系，注意缩进；比如：

```
student:
    name: qinjiang
    age: 3

```

行内写法

```
student: {name: qinjiang,age: 3}

```

**数组（ List、set ）**

用 - 值表示数组中的一个元素,比如：

```
pets:
 - cat
 - dog
 - pig

```

行内写法

```
pets: [cat,dog,pig]

```

**修改SpringBoot的默认端口号**

配置文件中添加，端口号的参数，就可以切换端口；

```
server:
 port: 8082

```

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)4.3yaml注入配置文件
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

yaml文件更强大的地方在于，他可以给我们的实体类直接注入匹配值！

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)4.3.1原始的给实体对象赋值

1、在springboot项目中的resources目录下新建一个文件 application.yml

2、编写一个实体类 User；

```
@Component  //注册bean到容器中,使得这个类可以被扫描到
public class Dog {
    private String name;
    private Integer age;
    
    //有参无参构造、get、set方法、toString()方法  
}

```

3、思考，我们原来是如何给bean注入属性值的！@Value，给User类测试一下：

```
@Component //注册bean
public class Dog {
    @Value("阿黄")
    private String name;
    @Value("18")
    private Integer age;
}

```

4、在SpringBoot的测试类下注入user输出一下；

```
@SpringBootTest
class DemoApplicationTests {

    @Autowired //将狗狗自动注入进来
    Dog dog;

    @Test
    public void contextLoads() {
        System.out.println(dog); //打印看下狗狗对象
    }

}

```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424204904228.png)

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)4.3.2通过yaml文件赋值

1、我们在编写一个复杂一点的实体类：Person 类

```

@Component //注册bean到容器中
public class Person {
    private String name;
    private Integer age;
    private Boolean happy;
    private Date birth;
    private Map<String,Object> maps;
    private List<Object> lists;
    private Dog dog;
    
    //有参无参构造、get、set方法、toString()方法  
}

```

2、我们来使用yaml配置的方式进行注入，大家写的时候注意区别和优势，我们编写一个yaml配置！

```
person:
  name: qinjiang
  age: 3
  happy: false
  birth: 2000/01/01
  maps: {k1: v1,k2: v2}
  lists:
   - code
   - girl
   - music
  dog:
    name: 旺财
    age: 1

```

3、我们刚才已经把person这个对象的所有值都写好了，我们现在来注入到我们的类中！

```
/*
@ConfigurationProperties作用：
将配置文件中配置的每一个属性的值，映射到这个组件中；
告诉SpringBoot将本类中的所有属性和配置文件中相关的配置进行绑定
参数 prefix = “person” : 将配置文件中的person下面的所有属性一一对应
*/
@Component //注册bean
@ConfigurationProperties(prefix = "person")
public class Person {
    private String name;
    private Integer age;
    private Boolean happy;
    private Date birth;
    private Map<String,Object> maps;
    private List<Object> lists;
    private Dog dog;
}

```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424204929488.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

4、IDEA 提示，springboot配置注解处理器没有找到，让我们看文档，我们可以查看文档，找到一个依赖！

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424204940623.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

```
<!-- 导入配置文件处理器，配置文件进行绑定就会有提示，需要重启 -->
<dependency>
  <groupId>org.springframework.boot</groupId>
  <artifactId>spring-boot-configuration-processor</artifactId>
  <optional>true</optional>
</dependency>

```

5、确认以上配置都OK之后，我们去测试类中测试一下：

```
@SpringBootTest
class DemoApplicationTests {

    @Autowired
    Person person; //将person自动注入进来

    @Test
    public void contextLoads() {
        System.out.println(person); //打印person信息
    }

}

```

结果：所有值全部注入成功！

**yaml配置注入到实体类完全OK！**

![(C:\Users\GuoSheng\AppData\Roaming\Typora\typora-user-images\image-20210411235105414.png)]](https://img-blog.csdnimg.cn/20210424204953707.png)

课堂测试：

1、将配置文件的key 值 和 属性的值设置为不一样，则结果输出为null，注入失败

2、在配置一个person2，然后将 @ConfigurationProperties(prefix = “person2”) 指向我们的person2；

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)4.4加载指定的配置文件
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

\*\*@PropertySource ：\*\*加载指定的配置文件；

**@configurationProperties**：默认从全局配置文件中获取值；

1、我们去在resources目录下新建一个**person.properties**文件

注意在使用之前要去setting把字符集调整为UTF-8否则会乱码(在后面的回顾properties配置中有具体写到)

```
name=guoshuai

```

2、然后在我们的代码中指定加载person.properties文件

```
@PropertySource(value = "classpath:person.properties")
@Component //注册bean
public class Person {

    @Value("${name}")//有点像jsp了哦，EL表达式
    private String name;

    ......  
}

```

![](https://img-blog.csdnimg.cn/20210424205019425.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

3.再次输出测试一下：指定配置文件绑定成功！

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424205032615.png)

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)4.5配置文件占位符
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

配置文件还可以编写占位符生成随机数

```
person:
    name: qinjiang${random.uuid} # 随机uuid
    age: ${random.int}  # 随机int
    happy: false
    birth: 2000/01/01
    maps: {k1: v1,k2: v2}
    lists:
      - code
      - girl
      - music
    dog:
      name: ${person.hello:other}_旺财
      age: 1

```

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)4.6回顾properties配置
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

我们上面采用的yaml方法都是最简单的方式，开发中最常用的；也是springboot所推荐的！那我们来唠唠其他的实现方式，道理都是相同的；写还是那样写；配置文件除了yml还有我们之前常用的properties ， 我们没有讲，我们来唠唠！

【注意】properties配置文件在写中文的时候，会有乱码 ， 我们需要去IDEA中设置编码格式为UTF-8；

settings–>FileEncodings 中配置：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424205045147.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)4.7Properties和Yaml的对比小结
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

@Value这个使用起来并不友好！我们需要为每个属性单独注解赋值，比较麻烦；我们来看个功能对比图

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424205056277.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

1、@ConfigurationProperties只需要写一次即可 ， @Value则需要每个字段都添加

2、松散绑定：这个什么意思呢? 比如我的yaml中写的last-name，这个和lastName是一样的， - 后面跟着的字母默认是大写的。这就是松散绑定。可以测试一下

3、JSR303数据校验 ， 这个就是我们可以在字段是增加一层过滤器验证 ， 可以保证数据的合法性

4、复杂类型封装，yaml中可以封装对象 ， 使用value就不支持。

**结论**

配置yaml和配置properties都可以获取到值 ， 但是强烈推荐 yaml；

如果我们在某个业务中，只需要获取配置文件中的**某个值**，可以使用一下 @value；

如果说，我们**专门编写了一个JavaBean来和配置文件进行**一一映射，就直接@configurationProperties，不要犹豫！

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)5.JSR303数据校验及多环境切换
======================================================================================================================================================================================================================================================================================================================================================================================================================================================================

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)5.1JSR303
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

JSR303数据校验是用来校验输入内容的

Springboot中可以用@validated来校验数据，如果数据异常则会统一抛出异常，方便异常中心统一处理。我们这里来写个注解让我们的name只能支持Email格式；

```
@Component //注册bean
@ConfigurationProperties(prefix = "person")
@Validated  //数据校验
public class Person {

    @Email(message="邮箱格式错误") //name必须是邮箱格式
    private String name;
}

```

如果没有@Email注解，需要在pom.xml文件中添加依赖：

```
        <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-validation</artifactId>
        </dependency>

```

**使用数据校验，可以保证数据的正确性**

```
@NotNull(message="名字不能为空")
private String userName;
@Max(value=120,message="年龄最大不能查过120")
private int age;
@Email(message="邮箱格式错误")
private String email;

空检查
@Null       验证对象是否为null
@NotNull    验证对象是否不为null, 无法查检长度为0的字符串
@NotBlank   检查约束字符串是不是Null还有被Trim的长度是否大于0,只对字符串,且会去掉前后空格.
@NotEmpty   检查约束元素是否为NULL或者是EMPTY.
    
Booelan检查
@AssertTrue     验证 Boolean 对象是否为 true  
@AssertFalse    验证 Boolean 对象是否为 false  
    
长度检查
@Size(min=, max=) 验证对象（Array,Collection,Map,String）长度是否在给定的范围之内  
@Length(min=, max=) string is between min and max included.

日期检查
@Past       验证 Date 和 Calendar 对象是否在当前时间之前  
@Future     验证 Date 和 Calendar 对象是否在当前时间之后  
@Pattern    验证 String 对象是否符合正则表达式的规则

.......等等
除此以外，我们还可以自定义一些数据校验规则

```

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)5.2多环境切换
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

profile是Spring对不同环境提供不同配置功能的支持，可以通过激活不同的环境版本，实现快速切换环境；

我们在主配置文件编写的时候，文件名可以是 application-{profile}.properties/yml , 用来指定多个环境版本；

**例如：**

application-test.properties 代表测试环境配置

application-dev.properties 代表开发环境配置

但是Springboot并不会直接启动这些配置文件，它**默认使用application.properties主配置文件**；

我们需要通过一个配置来选择需要激活的环境：

```
#比如在配置文件中指定使用dev环境，我们可以通过设置不同的端口号进行测试；#我们启动SpringBoot，就可以看到已经切换到dev下的配置了；
spring.profiles.active=dev

```

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)5.3yaml的多文档块
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

和properties配置文件中一样，但是使用yml去实现不需要创建多个配置文件，更加方便了 !

通过—来分割模块

```
server:
  port: 8081
#选择要激活那个环境块
spring:
  profiles:
    active: prod

---
server:
  port: 8083
spring:
  profiles: dev #配置环境的名称

---

server:
  port: 8084
spring:
  profiles: prod  #配置环境的名称

```

**注意：如果yml和properties同时都配置了端口，并且没有激活其他环境 ， 默认会使用properties配置文件的！**

配置文件加载位置

**外部加载配置文件的方式十分多，我们选择最常用的即可，在开发的资源文件中进行配置！**

官方外部配置文件说明参考文档

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424205109389.png)

springboot 启动会扫描以下位置的application.properties或者application.yml文件作为Spring boot的默认配置文件：

```
优先级1：项目路径下的config文件夹配置文件
优先级2：项目路径下配置文件
优先级3：资源路径下的config文件夹配置文件
优先级4：资源路径下配置文件

```

优先级由高到底，高优先级的配置会覆盖低优先级的配置；

**SpringBoot会从这四个位置全部加载主配置文件；互补配置；**

我们在最低级的配置文件中设置一个项目访问路径的配置来测试互补问题；

```
#配置项目的访问路径
server.servlet.context-path=/guo

```

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)5.4拓展，运维小技巧
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

指定位置加载配置文件

我们还可以通过spring.config.location来改变默认的配置文件位置

项目打包好以后，我们可以使用命令行参数的形式，启动项目的时候来指定配置文件的新位置；这种情况，一般是后期运维做的多，相同配置，外部指定的配置文件优先级最高

```
java -jar spring-boot-config.jar --spring.config.location=F:/application.properties

```

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)6.※自动配置原理
=============================================================================================================================================================================================================================================================================================================================================================================================================================================================

配置文件到底能写什么？怎么写？

SpringBoot官方文档中有大量的配置，我们无法全部记住

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)6.1分析自动配置原理
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

我们以\*\*HttpEncodingAutoConfiguration（Http编码自动配置）\*\*为例解释自动配置原理；

```
@Configuration //表示这是一个配置类，和以前编写的配置文件一样，也可以给容器中添加组件；

//启动指定类的ConfigurationProperties功能；
  //进入这个HttpProperties查看，将配置文件中对应的值和HttpProperties绑定起来；
  //并把HttpProperties加入到ioc容器中
@EnableConfigurationProperties({HttpProperties.class}) 

//Spring底层@Conditional注解
  //根据不同的条件判断，如果满足指定的条件，整个配置类里面的配置就会生效；
  //这里的意思就是判断当前应用是否是web应用，如果是，当前配置类生效
@ConditionalOnWebApplication(type = Type.SERVLET)

//判断当前项目有没有这个类CharacterEncodingFilter；SpringMVC中进行乱码解决的过滤器；
@ConditionalOnClass({CharacterEncodingFilter.class})

//判断配置文件中是否存在某个配置：spring.http.encoding.enabled；
  //如果不存在，判断也是成立的
  //即使我们配置文件中不配置spring.http.encoding.enabled=true，也是默认生效的；
@ConditionalOnProperty(
    prefix = "spring.http.encoding",
    value = {"enabled"},
    matchIfMissing = true
)

public class HttpEncodingAutoConfiguration {
    //他已经和SpringBoot的配置文件映射了
    private final Encoding properties;
    //只有一个有参构造器的情况下，参数的值就会从容器中拿
    public HttpEncodingAutoConfiguration(HttpProperties properties) {
        this.properties = properties.getEncoding();
    }
    
    //给容器中添加一个组件，这个组件的某些值需要从properties中获取
    @Bean
    @ConditionalOnMissingBean //判断容器没有这个组件？
    public CharacterEncodingFilter characterEncodingFilter() {
        CharacterEncodingFilter filter = new OrderedCharacterEncodingFilter();
        filter.setEncoding(this.properties.getCharset().name());
        filter.setForceRequestEncoding(this.properties.shouldForce(org.springframework.boot.autoconfigure.http.HttpProperties.Encoding.Type.REQUEST));
        filter.setForceResponseEncoding(this.properties.shouldForce(org.springframework.boot.autoconfigure.http.HttpProperties.Encoding.Type.RESPONSE));
        return filter;
    }
    //。。。。。。。
}

```

**一句话总结 ：根据当前不同的条件判断，决定这个配置类是否生效！**

*   一但这个配置类生效；这个配置类就会给容器中添加各种组件；
*   这些组件的属性是从对应的properties类中获取的，这些类里面的每一个属性又是和配置文件绑定的；  
    这样就可以形成我们的配置文件可以动态的修改springboot的内容。
*   所有在配置文件中能配置的属性都是在xxxxProperties类中封装着；
*   配置文件能配置什么就可以参照某个功能对应的这个属性类

通俗理解：把我们原先需要在bean中手打的属性（property）封装成了一个类，然后通过yaml文件进行自动注入，而我们也可以在application.yaml文件中对这些property进行赋值。

```
//从配置文件中获取指定的值和bean的属性进行绑定
@ConfigurationProperties(prefix = "spring.http") 
public class HttpProperties {
    // .....
}

```

我们去配置文件里面试试前缀，看提示！

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)6.2精髓
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

1.SpringBoot启动时会加载大量的自动配置类  
2.我们看我们需要的功能有没有在SpringBoot默认写好的自动配置类当中  
3.我们再来看这个自动配置类中到底配置了哪些组件；（只要我们要用的组件存在其中，我们就不需要再去手动配置了，如果不存在我们再手动配置）  
4.给容器中自动配置类添加组件的时候，会从properties类中获取某些属性，我们只需要在配置文件中指定这些属性即可；

XXXXAutoConfiguration：自动配置类:给容器添加组件，这些组件要赋值就需要绑定一个XXXXProperties类  
XXXXProperties：里面封装配置文件中相关属性；

怎么去修改这些属性呢：说白了就是SpringBoot配置，---->.yaml、.properties这些文件

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)6.3了解：@Conditional
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

了解完自动装配的原理后，我们来关注一个细节问题，\*_自动配置类必须在一定的条件下才能生效；_

**@Conditional派生注解（Spring注解版原生的@Conditional作用）**

作用：必须是@Conditional指定的条件成立，才给容器中添加组件，配置配里面的所有内容才生效；  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424205122117.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

**那么多的自动配置类，必须在一定的条件下才能生效；也就是说，我们加载了这么多的配置类，但不是所有的都生效了。**

我们怎么知道哪些自动配置类生效？

**我们可以通过启用 debug=true属性；来让控制台打印自动配置报告，这样我们就可以很方便的知道哪些自动配置类生效；**

```
#开启springboot的调试类
debug=true

```

**Positive matches:（自动配置类启用的：正匹配）**

**Negative matches:（没有启动，没有匹配成功的自动配置类：负匹配）**

**Unconditional classes: （没有条件的类）**

【演示：查看输出的日志】

掌握吸收理解原理，即可以不变应万变！

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)6.4自定义Starter启动器
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

我们分析完毕了源码以及自动装配的过程，我们可以尝试自定义一个启动器来玩玩！

说明

启动器模块是一个 空 jar 文件，仅提供辅助性依赖管理，这些依赖可能用于自动装配或者其他类库；

**命名归约：**

官方命名：

*   前缀：spring-boot-starter-xxx
*   比如：spring-boot-starter-web…

自定义命名：

*   xxx-spring-boot-starter
*   比如：mybatis-spring-boot-starter

**编写启动器**

1、在IDEA中新建一个空项目 spring-boot-starter-diy

2、新建一个普通Maven模块：kuang-spring-boot-starter

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424205143229.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

3、新建一个Springboot模块：kuang-spring-boot-starter-autoconfigure  
![在这里插入图片描述](https://img-blog.csdnimg.cn/2021042420582858.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

4、点击apply即可，基本结构

![在这里插入图片描述](https://img-blog.csdnimg.cn/2021042420584098.png)

5、在我们的 starter 中 导入 autoconfigure 的依赖！

```
<!-- 启动器 -->
<dependencies>
    <!--  引入自动配置模块 -->
    <dependency>
        <groupId>com.kuang</groupId>
        <artifactId>kuang-spring-boot-starter-autoconfigure</artifactId>
        <version>0.0.1-SNAPSHOT</version>
    </dependency>
</dependencies>

```

6.将 autoconfigure 项目下多余的文件都删掉，Pom中只留下一个 starter，这是所有的启动器基本配置！

![[议将图片保存下来直接上传(img-K7xKdL1b-1619268160779)(C:\Users\GuoSheng\AppData\Roaming\Typora\typora-user-images\image-20210412210702028.png)]](https://img-blog.csdnimg.cn/20210424205853906.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

7、我们编写一个自己的服务

```
package com.kuang;

public class HelloService {

    HelloProperties helloProperties;

    public HelloProperties getHelloProperties() {
        return helloProperties;
    }

    public void setHelloProperties(HelloProperties helloProperties) {
        this.helloProperties = helloProperties;
    }

    public String sayHello(String name){
        return helloProperties.getPrefix() + name + helloProperties.getSuffix();
    }

}

```

8、编写HelloProperties 配置类

```
package com.kuang;

import org.springframework.boot.context.properties.ConfigurationProperties;

// 前缀 kuang.hello
@ConfigurationProperties(prefix = "kuang.hello")
public class HelloProperties {

    private String prefix;
    private String suffix;

    public String getPrefix() {
        return prefix;
    }

    public void setPrefix(String prefix) {
        this.prefix = prefix;
    }

    public String getSuffix() {
        return suffix;
    }

    public void setSuffix(String suffix) {
        this.suffix = suffix;
    }
}

```

9、编写我们的自动配置类并注入bean，测试！

```

package com.kuang;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.autoconfigure.condition.ConditionalOnWebApplication;
import org.springframework.boot.context.properties.EnableConfigurationProperties;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

@Configuration
@ConditionalOnWebApplication //web应用生效
@EnableConfigurationProperties(HelloProperties.class)
public class HelloServiceAutoConfiguration {

    @Autowired
    HelloProperties helloProperties;

    @Bean
    public HelloService helloService(){
        HelloService service = new HelloService();
        service.setHelloProperties(helloProperties);
        return service;
    }

}

```

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)7.SpringBoot Web开发总览
========================================================================================================================================================================================================================================================================================================================================================================================================================================================================

在之前我们的项目都是以jar包结尾的，没有放webapp的地方。  
springboot最大的特点：自动装配

1.创建应用，选择模块导入starter，只需要专注于业务代码

springboot到底帮我们配置了什么，我们能不能修改？能修改哪些东西？能不能扩展

*   xxxAutoConfiguration：向容器中自动配置组件
*   xxxProperties：自动配置类，装配配置文件中自定义的一些内容

要解决的问题：

*   导入静态资源html，css，js
*   首页
*   写jsp的地方，模板引擎Thymeleaf
*   装配和扩展SpringMVC
*   增删改查
*   拦截器

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)7.1Web开发静态资源处理
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

静态资源映射规则

**首先，我们搭建一个普通的SpringBoot项目，回顾一下HelloWorld程序！**

写请求非常简单，那我们要引入我们前端资源，我们项目中有许多的静态资源，比如css，js等文件，这个SpringBoot怎么处理呢？

如果我们是一个web应用，我们的main下会有一个webapp，我们以前都是将所有的页面导在这里面的，对吧！但是我们现在的pom呢，打包方式是为jar的方式，那么这种方式SpringBoot能不能来给我们写页面呢？当然是可以的，但是SpringBoot对于静态资源放置的位置，是有规定的！

**我们先来聊聊这个静态资源映射规则：**

SpringBoot中，SpringMVC的web配置都在 WebMvcAutoConfiguration 这个配置类里面；

我们可以去看看 WebMvcAutoConfigurationAdapter 中有很多配置方法；

有一个方法：addResourceHandlers 添加资源处理

```
@Override
public void addResourceHandlers(ResourceHandlerRegistry registry) {
    if (!this.resourceProperties.isAddMappings()) {
        // 已禁用默认资源处理
        logger.debug("Default resource handling disabled");
        return;
    }
    // 缓存控制
    Duration cachePeriod = this.resourceProperties.getCache().getPeriod();
    CacheControl cacheControl = this.resourceProperties.getCache().getCachecontrol().toHttpCacheControl();
    // webjars 配置
    if (!registry.hasMappingForPattern("/webjars/**")) {
        customizeResourceHandlerRegistration(registry.addResourceHandler("/webjars/**")
                                             .addResourceLocations("classpath:/META-INF/resources/webjars/")
                                             .setCachePeriod(getSeconds(cachePeriod)).setCacheControl(cacheControl));
    }
    // 静态资源配置
    String staticPathPattern = this.mvcProperties.getStaticPathPattern();
    if (!registry.hasMappingForPattern(staticPathPattern)) {
        customizeResourceHandlerRegistration(registry.addResourceHandler(staticPathPattern)
                                             .addResourceLocations(getResourceLocations(this.resourceProperties.getStaticLocations()))
                                             .setCachePeriod(getSeconds(cachePeriod)).setCacheControl(cacheControl));
    }
}

```

读一下源代码：比如所有的 /webjars/\*\* ， 都需要去 classpath:/META-INF/resources/webjars/ 找对应的资源；

**什么是webjars 呢？**

Webjars本质就是以jar包的方式引入我们的静态资源 ， 我们以前要导入一个静态资源文件，直接导入即可。

使用SpringBoot需要使用Webjars，我们可以去搜索一下：

网站：https://www.webjars.org

要使用jQuery，我们只要要引入jQuery对应版本的pom依赖即可！

```
<dependency>
    <groupId>org.webjars</groupId>
    <artifactId>jquery</artifactId>
    <version>3.4.1</version>
</dependency>

```

导入完毕，查看webjars目录结构，并访问Jquery.js文件！

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424205912340.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

访问：只要是静态资源，SpringBoot就会去对应的路径寻找资源，我们这里访问：http://localhost:8080/webjars/jquery/3.4.1/jquery.js

**第二种静态资源映射规则**

那我们项目中要是使用自己的静态资源该怎么导入呢？我们看下一行代码；

我们去找staticPathPattern发现第二种映射规则 ：/\*\* , 访问当前的项目任意资源，它会去找 resourceProperties 这个类，我们可以点进去看一下分析：

```
// 进入方法
public String[] getStaticLocations() {
    return this.staticLocations;
}
// 找到对应的值
private String[] staticLocations = CLASSPATH_RESOURCE_LOCATIONS;
// 找到路径
private static final String[] CLASSPATH_RESOURCE_LOCATIONS = { 
    "classpath:/META-INF/resources/",
  "classpath:/resources/", 
    "classpath:/static/", 
    "classpath:/public/" 
};

```

ResourceProperties 可以设置和我们静态资源有关的参数；这里面指向了它会去寻找资源的文件夹，即上面数组的内容。

所以得出结论，以下四个目录存放的静态资源可以被我们识别：

```
"classpath:/META-INF/resources/"
"classpath:/resources/"
"classpath:/static/"
"classpath:/public/"

```

我们可以在resources根目录下新建对应的文件夹，都可以存放我们的静态文件；

比如我们访问 http://localhost:8080/1.js , 他就会去这些文件夹中寻找对应的静态资源文件；

自定义静态资源路径

我们也可以自己通过配置文件来指定一下，哪些文件夹是需要我们放静态资源文件的，在application.properties中配置；

```
spring.resources.static-locations=classpath:/coding/,classpath:/kuang/

```

一旦自己定义了静态文件夹的路径，原来的自动配置就都会失效了！

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)7.2首页处理
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

静态资源文件夹说完后，我们继续向下看源码！可以看到一个欢迎页的映射，就是我们的首页！

```
@Bean
public WelcomePageHandlerMapping welcomePageHandlerMapping(ApplicationContext applicationContext,
                                                           FormattingConversionService mvcConversionService,
                                                           ResourceUrlProvider mvcResourceUrlProvider) {
    WelcomePageHandlerMapping welcomePageHandlerMapping = new WelcomePageHandlerMapping(
        new TemplateAvailabilityProviders(applicationContext), applicationContext, getWelcomePage(), // getWelcomePage 获得欢迎页
        this.mvcProperties.getStaticPathPattern());
    welcomePageHandlerMapping.setInterceptors(getInterceptors(mvcConversionService, mvcResourceUrlProvider));
    return welcomePageHandlerMapping;
}

```

点进去继续看

```
private Optional<Resource> getWelcomePage() {
    String[] locations = getResourceLocations(this.resourceProperties.getStaticLocations());
    // ::是java8 中新引入的运算符
    // Class::function的时候function是属于Class的，应该是静态方法。
    // this::function的funtion是属于这个对象的。
    // 简而言之，就是一种语法糖而已，是一种简写
    return Arrays.stream(locations).map(this::getIndexHtml).filter(this::isReadable).findFirst();
}
// 欢迎页就是一个location下的的 index.html 而已
private Resource getIndexHtml(String location) {
    return this.resourceLoader.getResource(location + "index.html");
}

```

欢迎页，静态资源文件夹下的所有 index.html 页面；被 /\*\* 映射。

比如我访问 http://localhost:8080/ ，就会找静态资源文件夹下的 index.html

新建一个 index.html ，在我们上面的3个目录中任意一个；然后访问测试 http://localhost:8080/ 看结果！

**关于网站图标说明**：

![](https://img-blog.csdnimg.cn/20210424205924248.png)

与其他静态资源一样，Spring Boot在配置的静态内容位置中查找 favicon.ico。如果存在这样的文件，它将自动用作应用程序的favicon。

1、关闭SpringBoot默认图标

```
#关闭默认图标
spring.mvc.favicon.enabled=false

```

2、自己放一个图标在静态资源目录下，我放在 public 目录下

3、清除浏览器缓存！刷新网页，发现图标已经变成自己的了！

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)8.Thymeleaf模板引擎
===================================================================================================================================================================================================================================================================================================================================================================================================================================================================

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)8.1模板引擎
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

​ 前端交给我们的页面，是html页面。如果是我们以前开发，我们需要把他们转成jsp页面，jsp好处就是当我们查出一些数据转发到JSP页面以后，我们可以用jsp轻松实现数据的显示，及交互等。

​ jsp支持非常强大的功能，包括能写Java代码，但是呢，我们现在的这种情况，SpringBoot这个项目首先是以jar的方式，不是war，像第二，我们用的还是嵌入式的Tomcat，所以呢，**他现在默认是不支持jsp的**。

那不支持jsp，如果我们直接用纯静态页面的方式，那给我们开发会带来非常大的麻烦，那怎么办呢？

**SpringBoot推荐你可以来使用模板引擎：**

​ 模板引擎，我们其实大家听到很多，其实jsp就是一个模板引擎，还有用的比较多的freemarker，包括SpringBoot给我们推荐的Thymeleaf，模板引擎有非常多，但再多的模板引擎，他们的思想都是一样的，什么样一个思想呢我们来看一下这张图：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424205940573.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

​ 模板引擎的作用就是我们来写一个页面模板，比如有些值呢，是动态的，我们写一些表达式。而这些值，从哪来呢，就是我们在后台封装一些数据。然后把这个模板和这个数据交给我们模板引擎，模板引擎按照我们这个数据帮你把这表达式解析、填充到我们指定的位置，然后把这个数据最终生成一个我们想要的内容给我们写出去，这就是我们这个模板引擎，不管是jsp还是其他模板引擎，都是这个思想。只不过呢，就是说不同模板引擎之间，他们可能这个语法有点不一样。其他的我就不介绍了，我主要来介绍一下SpringBoot给我们推荐的Thymeleaf模板引擎，这模板引擎呢，是一个高级语言的模板引擎，他的这个语法更简单。而且呢，功能更强大。

​ 我们呢，就来看一下这个模板引擎，那既然要看这个模板引擎。首先，我们来看SpringBoot里边怎么用。

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)8.2引入Thymeleaf
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

怎么引入呢，对于springboot来说，什么事情不都是一个start的事情嘛，我们去在项目中引入一下。给大家三个网址：

Thymeleaf 官网：https://www.thymeleaf.org/

Thymeleaf 在Github 的主页：https://github.com/thymeleaf/thymeleaf

Spring官方文档：找到我们对应的版本

https://docs.spring.io/spring-boot/docs/2.2.5.RELEASE/reference/htmlsingle/#using-boot-starter

找到对应的pom依赖：可以适当点进源码看下本来的包！

```
<!--thymeleaf-->
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-thymeleaf</artifactId>
</dependency>

```

Maven会自动下载jar包，我们可以去看下下载的东西；  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424210022247.png)

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)8.3Thymeleaf分析
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

前面呢，我们已经引入了Thymeleaf，那这个要怎么使用呢？

我们首先得按照SpringBoot的自动配置原理看一下我们这个Thymeleaf的自动配置规则，在按照那个规则，我们进行使用。

我们去找一下Thymeleaf的自动配置类：ThymeleafProperties

```
@ConfigurationProperties(
    prefix = "spring.thymeleaf"
)
public class ThymeleafProperties {
    private static final Charset DEFAULT_ENCODING;
    public static final String DEFAULT_PREFIX = "classpath:/templates/";
    public static final String DEFAULT_SUFFIX = ".html";
    private boolean checkTemplate = true;
    private boolean checkTemplateLocation = true;
    private String prefix = "classpath:/templates/";
    private String suffix = ".html";
    private String mode = "HTML";
    private Charset encoding;
}

```

我们可以在其中看到默认的前缀和后缀！

我们只需要把我们的html页面放在类路径下的templates下，thymeleaf就可以帮我们自动渲染了。

使用thymeleaf什么都不需要配置，只需要将他放在指定的文件夹下即可！

**测试**

1、编写一个TestController

```
@Controller
public class TestController {
    
    @RequestMapping("/t1")
    public String test1(){
        //classpath:/templates/test.html
        return "test";
    }
    
}

```

2、编写一个测试页面 test.html 放在 templates 目录下

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<h1>test</h1>
</body>
</html>

```

3、启动项目请求测试

结果：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424210039790.png)

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)8.4Thymeleaf 语法学习
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

要学习语法，还是参考官网文档最为准确，我们找到对应的版本看一下；

Thymeleaf 官网：https://www.thymeleaf.org/ ， 简单看一下官网！我们去下载Thymeleaf的官方文档！

**我们做个最简单的练习 ：我们需要查出一些数据，在页面中展示**

1、修改测试请求，增加数据传输；

```
@RequestMapping("/t1")
public String test1(Model model){
    //存入数据
    model.addAttribute("msg","Hello,Thymeleaf");
    //classpath:/templates/test.html
    return "test";
}

```

2、我们要使用thymeleaf，需要在html文件中导入命名空间的约束，方便提示。

我们可以去官方文档的#3中看一下命名空间拿来过来：

```
 xmlns:th="http://www.thymeleaf.org"

```

3、我们去编写下前端页面

```
<!DOCTYPE html>
<html lang="en" xmlns:th="http://www.thymeleaf.org">
<head>
    <meta charset="UTF-8">
    <title>Guo</title>
</head>
<body>
<h1>测试页面</h1>

<!--th:text就是将div中的内容设置为它指定的值，和之前学习的Vue一样-->
<div th:text="${msg}"></div>
</body>
</html>

```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424210138301.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

**OK，入门搞定，我们来认真研习一下Thymeleaf的使用语法！**

**1、我们可以使用任意的 th:attr 来替换Html中原生属性的值！**  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424210150281.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

**2、我们能写哪些表达式呢？**

```
Simple expressions:（表达式语法）
Variable Expressions: ${...}：获取变量值；OGNL；
    1）、获取对象的属性、调用方法
    2）、使用内置的基本对象：#18
         #ctx : the context object.
         #vars: the context variables.
         #locale : the context locale.
         #request : (only in Web Contexts) the HttpServletRequest object.
         #response : (only in Web Contexts) the HttpServletResponse object.
         #session : (only in Web Contexts) the HttpSession object.
         #servletContext : (only in Web Contexts) the ServletContext object.

    3）、内置的一些工具对象：
　　　　　　#execInfo : information about the template being processed.
　　　　　　#uris : methods for escaping parts of URLs/URIs
　　　　　　#conversions : methods for executing the configured conversion service (if any).
　　　　　　#dates : methods for java.util.Date objects: formatting, component extraction, etc.
　　　　　　#calendars : analogous to #dates , but for java.util.Calendar objects.
　　　　　　#numbers : methods for formatting numeric objects.
　　　　　　#strings : methods for String objects: contains, startsWith, prepending/appending, etc.
　　　　　　#objects : methods for objects in general.
　　　　　　#bools : methods for boolean evaluation.
　　　　　　#arrays : methods for arrays.
　　　　　　#lists : methods for lists.
　　　　　　#sets : methods for sets.
　　　　　　#maps : methods for maps.
　　　　　　#aggregates : methods for creating aggregates on arrays or collections.
==================================================================================

  Selection Variable Expressions: *{...}：选择表达式：和${}在功能上是一样；
  Message Expressions: #{...}：获取国际化内容
  Link URL Expressions: @{...}：定义URL；
  Fragment Expressions: ~{...}：片段引用表达式

Literals（字面量）
      Text literals: 'one text' , 'Another one!' ,…
      Number literals: 0 , 34 , 3.0 , 12.3 ,…
      Boolean literals: true , false
      Null literal: null
      Literal tokens: one , sometext , main ,…
      
Text operations:（文本操作）
    String concatenation: +
    Literal substitutions: |The name is ${name}|
    
Arithmetic operations:（数学运算）
    Binary operators: + , - , * , / , %
    Minus sign (unary operator): -
    
Boolean operations:（布尔运算）
    Binary operators: and , or
    Boolean negation (unary operator): ! , not
    
Comparisons and equality:（比较运算）
    Comparators: > , < , >= , <= ( gt , lt , ge , le )
    Equality operators: == , != ( eq , ne )
    
Conditional operators:条件运算（三元运算符）
    If-then: (if) ? (then)
    If-then-else: (if) ? (then) : (else)
    Default: (value) ?: (defaultvalue)
    
Special tokens:
    No-Operation: _

```

**练习测试：**

1、 我们编写一个Controller，放一些数据

```
@RequestMapping("/t2")
public String test2(Map<String,Object> map){
    //存入数据
    map.put("msg","<h1>Hello</h1>");
    map.put("users", Arrays.asList("qinjiang","kuangshen"));
    //classpath:/templates/test.html
    return "test";
}

```

2、测试页面取出数据.

```
<!DOCTYPE html>
<html lang="en" xmlns:th="http://www.thymeleaf.org">
<head>
    <meta charset="UTF-8">
    <title>狂神说</title>
</head>
<body>
<h1>测试页面</h1>

<div th:text="${msg}"></div>
<!--不转义-->
<div th:utext="${msg}"></div>

<!--遍历数据-->
<!--th:each每次遍历都会生成当前这个标签：官网#9-->
<h4 th:each="user :${users}" th:text="${user}"></h4>

<h4>
    <!--行内写法：官网#12-->
    <span th:each="user:${users}">[[${user}]]</span>
</h4>

</body>
</html>

```

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)9.SpringMVC自动配置原理
=====================================================================================================================================================================================================================================================================================================================================================================================================================================================================

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)9.1自动配置原理
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

​ 在进行项目编写前，我们还需要知道一个东西，就是SpringBoot对我们的SpringMVC还做了哪些配置，包括如何扩展，如何定制。

​ 只有把这些都搞清楚了，我们在之后使用才会更加得心应手。途径一：源码分析，途径二：官方文档！

​ [官网地址链接](https://docs.spring.io/spring-boot/docs/2.2.5.RELEASE/reference/htmlsingle/#boot-features-spring-mvc-auto-configuration)

```
Spring MVC Auto-configuration
// Spring Boot为Spring MVC提供了自动配置，它可以很好地与大多数应用程序一起工作。
Spring Boot provides auto-configuration for Spring MVC that works well with most applications.
// 自动配置在Spring默认设置的基础上添加了以下功能：
The auto-configuration adds the following features on top of Spring’s defaults:
// 包含视图解析器
Inclusion of ContentNegotiatingViewResolver and BeanNameViewResolver beans.
// 支持静态资源文件夹的路径，以及webjars
Support for serving static resources, including support for WebJars 
// 自动注册了Converter：
// 转换器，这就是我们网页提交数据到后台自动封装成为对象的东西，比如把"1"字符串自动转换为int类型
// Formatter：【格式化器，比如页面给我们了一个2019-8-10，它会给我们自动格式化为Date对象】
Automatic registration of Converter, GenericConverter, and Formatter beans.
// HttpMessageConverters
// SpringMVC用来转换Http请求和响应的的，比如我们要把一个User对象转换为JSON字符串，可以去看官网文档解释；
Support for HttpMessageConverters (covered later in this document).
// 定义错误代码生成规则的
Automatic registration of MessageCodesResolver (covered later in this document).
// 首页定制
Static index.html support.
// 图标定制
Custom Favicon support (covered later in this document).
// 初始化数据绑定器：帮我们把请求数据绑定到JavaBean中！
Automatic use of a ConfigurableWebBindingInitializer bean (covered later in this document).

/*
如果您希望保留Spring Boot MVC功能，并且希望添加其他MVC配置（拦截器、格式化程序、视图控制器和其他功能），则可以添加自己
的@configuration类，类型为webmvcconfiguer，但不添加@EnableWebMvc。如果希望提供
RequestMappingHandlerMapping、RequestMappingHandlerAdapter或ExceptionHandlerExceptionResolver的自定义
实例，则可以声明WebMVCregistrationAdapter实例来提供此类组件。
*/
If you want to keep Spring Boot MVC features and you want to add additional MVC configuration 
(interceptors, formatters, view controllers, and other features), you can add your own 
@Configuration class of type WebMvcConfigurer but without @EnableWebMvc. If you wish to provide 
custom instances of RequestMappingHandlerMapping, RequestMappingHandlerAdapter, or 
ExceptionHandlerExceptionResolver, you can declare a WebMvcRegistrationsAdapter instance to provide such components.

// 如果您想完全控制Spring MVC，可以添加自己的@Configuration，并用@EnableWebMvc进行注释。
If you want to take complete control of Spring MVC, you can add your own @Configuration annotated with @EnableWebMvc.

```

我们来仔细对照，看一下它怎么实现的，它告诉我们SpringBoot已经帮我们自动配置好了SpringMVC，然后自动配置了哪些东西呢？

**ContentNegotiatingViewResolver 内容协商视图解析器**

自动配置了ViewResolver，就是我们之前学习的SpringMVC的视图解析器；

即根据方法的返回值取得视图对象（View），然后由视图对象决定如何渲染（转发，重定向）。

我们去看看这里的源码：我们找到 WebMvcAutoConfiguration ， 然后搜索ContentNegotiatingViewResolver。找到如下方法！

```
@Bean
@ConditionalOnBean(ViewResolver.class)
@ConditionalOnMissingBean(name = "viewResolver", value = ContentNegotiatingViewResolver.class)
public ContentNegotiatingViewResolver viewResolver(BeanFactory beanFactory) {
    ContentNegotiatingViewResolver resolver = new ContentNegotiatingViewResolver();
    resolver.setContentNegotiationManager(beanFactory.getBean(ContentNegotiationManager.class));
    // ContentNegotiatingViewResolver使用所有其他视图解析器来定位视图，因此它应该具有较高的优先级
    resolver.setOrder(Ordered.HIGHEST_PRECEDENCE);
    return resolver;
}

```

我们可以点进这类看看！找到对应的解析视图的代码；

```
@Nullable // 注解说明：@Nullable 即参数可为null
public View resolveViewName(String viewName, Locale locale) throws Exception {
    RequestAttributes attrs = RequestContextHolder.getRequestAttributes();
    Assert.state(attrs instanceof ServletRequestAttributes, "No current ServletRequestAttributes");
    List<MediaType> requestedMediaTypes = this.getMediaTypes(((ServletRequestAttributes)attrs).getRequest());
    if (requestedMediaTypes != null) {
        // 获取候选的视图对象
        List<View> candidateViews = this.getCandidateViews(viewName, locale, requestedMediaTypes);
        // 选择一个最适合的视图对象，然后把这个对象返回
        View bestView = this.getBestView(candidateViews, requestedMediaTypes, attrs);
        if (bestView != null) {
            return bestView;
        }
    }
    // .....
}

```

我们继续点进去看，他是怎么获得候选的视图的呢？

getCandidateViews中看到他是把所有的视图解析器拿来，进行while循环，挨个解析！

```
Iterator var5 = this.viewResolvers.iterator();

```

所以得出结论：**ContentNegotiatingViewResolver 这个视图解析器就是用来组合所有的视图解析器的**

我们再去研究下他的组合逻辑，看到有个属性viewResolvers，看看它是在哪里进行赋值的！

```
protected void initServletContext(ServletContext servletContext) {
    // 这里它是从beanFactory工具中获取容器中的所有视图解析器
    // ViewRescolver.class 把所有的视图解析器来组合的
    Collection<ViewResolver> matchingBeans = BeanFactoryUtils.beansOfTypeIncludingAncestors(this.obtainApplicationContext(), ViewResolver.class).values();
    ViewResolver viewResolver;
    if (this.viewResolvers == null) {
        this.viewResolvers = new ArrayList(matchingBeans.size());
    }
    // ...............
}

```

既然它是在容器中去找视图解析器，我们是否可以猜想，我们就可以去实现一个视图解析器了呢？

我们可以自己给容器中去添加一个视图解析器；这个类就会帮我们自动的将它组合进来；**我们去实现一下**

1、我们在我们的主程序中去写一个视图解析器来试试；

```
@Bean //放到bean中
public ViewResolver myViewResolver(){
    return new MyViewResolver();
}

//我们写一个静态内部类，视图解析器就需要实现ViewResolver接口
private static class MyViewResolver implements ViewResolver{
    @Override
    public View resolveViewName(String s, Locale locale) throws Exception {
        return null;
    }
}

```

2、怎么看我们自己写的视图解析器有没有起作用呢？

我们给 DispatcherServlet 中的 doDispatch方法 加个断点进行调试一下，因为所有的请求都会走到这个方法中

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424210214708.png)

3、我们启动我们的项目，然后随便访问一个页面，看一下Debug信息；  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424210225463.png)

找到视图解析器，我们看到我们自己定义的就在这里了；

![[](https://img-blog.csdnimg.cn/20210424210239748.png)

所以说，我们如果想要使用自己定制化的东西，我们只需要给容器中添加这个组件就好了！剩下的事情SpringBoot就会帮我们做了！

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)9.2转换器和格式化器
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

找到格式化转换器：

```
@Bean
@Override
public FormattingConversionService mvcConversionService() {
    // 拿到配置文件中的格式化规则
    WebConversionService conversionService = 
        new WebConversionService(this.mvcProperties.getDateFormat());
    addFormatters(conversionService);
    return conversionService;
}

```

点击去：

```
public String getDateFormat() {
    return this.dateFormat;
}
/**
* Date format to use. For instance, `dd/MM/yyyy`. 默认的
 */
private String dateFormat;

```

可以看到在我们的Properties文件中，我们可以进行自动配置它！

如果配置了自己的格式化方式，就会注册到Bean中生效，我们可以在配置文件中配置日期格式化的规则：  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424210302329.png)

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)9.3修改SpringBoot的默认配置
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

​ 这么多的自动配置，原理都是一样的，通过这个WebMVC的自动配置原理分析，我们要学会一种学习方式，通过源码探究，得出结论；这个结论一定是属于自己的，而且一通百通。

​ SpringBoot的底层，大量用到了这些设计细节思想，所以，没事需要多阅读源码！得出结论；

​ SpringBoot在自动配置很多组件的时候，先看容器中有没有用户自己配置的（如果用户自己配置@bean），如果有就用用户配置的，如果没有就用自动配置的；

​ 如果有些组件可以存在多个，比如我们的视图解析器，就将用户配置的和自己默认的组合起来！

**扩展使用SpringMVC** 官方文档如下：

​ If you want to keep Spring Boot MVC features and you want to add additional MVC configuration (interceptors, formatters, view controllers, and other features), you can add your own @Configuration class of type WebMvcConfigurer but without @EnableWebMvc. If you wish to provide custom instances of RequestMappingHandlerMapping, RequestMappingHandlerAdapter, or ExceptionHandlerExceptionResolver, you can declare a WebMvcRegistrationsAdapter instance to provide such components.

我们要做的就是编写一个@Configuration注解类，并且类型要为WebMvcConfigurer，还不能标注@EnableWebMvc注解；我们去自己写一个；我们新建一个包叫config，写一个类MyMvcConfig；

```
//应为类型要求为WebMvcConfigurer，所以我们实现其接口
//可以使用自定义类扩展MVC的功能
@Configuration
public class MyMvcConfig implements WebMvcConfigurer {

    @Override
    public void addViewControllers(ViewControllerRegistry registry) {
        // 浏览器发送/test ， 就会跳转到test页面；
        registry.addViewController("/test").setViewName("test");
    }
}

```

我们去浏览器访问一下：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424210341417.png)

**确实也跳转过来了！所以说，我们要扩展SpringMVC，官方就推荐我们这么去使用，既保SpringBoot留所有的自动配置，也能用我们扩展的配置！**

我们可以去分析一下原理：

1、WebMvcAutoConfiguration 是 SpringMVC的自动配置类，里面有一个类WebMvcAutoConfigurationAdapter

2、这个类上有一个注解，在做其他自动配置时会导入：@Import(EnableWebMvcConfiguration.class)

3、我们点进EnableWebMvcConfiguration这个类看一下，它继承了一个父类：DelegatingWebMvcConfiguration

这个父类中有这样一段代码：

```
public class DelegatingWebMvcConfiguration extends WebMvcConfigurationSupport {
    private final WebMvcConfigurerComposite configurers = new WebMvcConfigurerComposite();
    
  // 从容器中获取所有的webmvcConfigurer
    @Autowired(required = false)
    public void setConfigurers(List<WebMvcConfigurer> configurers) {
        if (!CollectionUtils.isEmpty(configurers)) {
            this.configurers.addWebMvcConfigurers(configurers);
        }
    }
}

```

4、我们可以在这个类中去寻找一个我们刚才设置的viewController当做参考，发现它调用了一个

```
protected void addViewControllers(ViewControllerRegistry registry) {
    this.configurers.addViewControllers(registry);
}

```

5、我们点进去看一下

```
public void addViewControllers(ViewControllerRegistry registry) {
    Iterator var2 = this.delegates.iterator();

    while(var2.hasNext()) {
        // 将所有的WebMvcConfigurer相关配置来一起调用！包括我们自己配置的和Spring给我们配置的
        WebMvcConfigurer delegate = (WebMvcConfigurer)var2.next();
        delegate.addViewControllers(registry);
    }

}

```

​ 所以得出结论：所有的WebMvcConfiguration都会被作用，不止Spring自己的配置类，我们自己的配置类当然也会被调用；

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)9.4全面接管SpringMVC
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

官方文档：

```
If you want to take complete control of Spring MVC
you can add your own @Configuration annotated with @EnableWebMvc.

```

全面接管即：SpringBoot对SpringMVC的自动配置不需要了，所有都是我们自己去配置！

只需在我们的配置类中要加一个@EnableWebMvc。

我们看下如果我们全面接管了SpringMVC了，我们之前SpringBoot给我们配置的静态资源映射一定会无效，我们可以去测试一下；

不加注解之前，访问首页：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424210405286.png)

给配置类加上注解：@EnableWebMvc

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424210428137.png)

我们发现所有的SpringMVC自动配置都失效了！回归到了最初的样子；

**当然，我们开发中，不推荐使用全面接管SpringMVC**

思考问题？为什么加了一个注解，自动配置就失效了！我们看下源码：

1、这里发现它是导入了一个类，我们可以继续进去看

```
@Import({DelegatingWebMvcConfiguration.class})
public @interface EnableWebMvc {
}

```

2、它继承了一个父类 WebMvcConfigurationSupport

```
public class DelegatingWebMvcConfiguration extends WebMvcConfigurationSupport {
  // ......
}

```

3、我们来回顾一下Webmvc自动配置类

```
@Configuration(proxyBeanMethods = false)
@ConditionalOnWebApplication(type = Type.SERVLET)
@ConditionalOnClass({ Servlet.class, DispatcherServlet.class, WebMvcConfigurer.class })
// 这个注解的意思就是：容器中没有这个组件的时候，这个自动配置类才生效
@ConditionalOnMissingBean(WebMvcConfigurationSupport.class)
@AutoConfigureOrder(Ordered.HIGHEST_PRECEDENCE + 10)
@AutoConfigureAfter({ DispatcherServletAutoConfiguration.class, TaskExecutionAutoConfiguration.class,
    ValidationAutoConfiguration.class })
public class WebMvcAutoConfiguration {
    
}

```

总结一句话：@EnableWebMvc将WebMvcConfigurationSupport组件导入进来了；

而导入的WebMvcConfigurationSupport只是SpringMVC最基本的功能！

**在SpringBoot中会有非常多的扩展配置，只要看见了这个，我们就应该多留心注意~**

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)聊一聊怎么写一个网页
==============================================================================================================================================================================================================================================================================================================================================================================================================================================================

*   前端必须使用推荐模板：别人写好的，我们拿来改成自己需要的
*   框架：组件：需要自己手动组合拼接 layui，elementui
    *   栅格系统
    *   导航栏
    *   侧边栏

1.前端搞定：页面长什么样子：数据

2.设计数据库

3.前端让他能够自动运行，独立化工程

4.数据接口如何对接，json，对象all in one

5.前后端联调测试

后台框架：xadmin

前端界面：至少自己能够通过前端框架，组合出来一个网站页面

注意资源导出问题：

在build标签下添加：

```
        <resources>
            <resource>
                <directory>src/main/java</directory>
                <includes>
                    <include>**/*.*</include>
                </includes>
            </resource>
            <resource>
                <directory>src/main/resources</directory>
                <includes>
                    <include>**/*.*</include>
                </includes>
            </resource>
        </resources>

```

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)10.SpringBoot整合数据库操作
========================================================================================================================================================================================================================================================================================================================================================================================================================================================================

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)10.1整合JDBC
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)10.1.1SpringData简介

对于数据访问层，无论是 SQL(关系型数据库) 还是 NOSQL(非关系型数据库)，Spring Boot 底层都是采用 Spring Data 的方式进行统一处理。

Spring Boot 底层都是采用 Spring Data 的方式进行统一处理各种数据库，Spring Data 也是 Spring 中与 Spring Boot、Spring Cloud 等齐名的知名项目。

Sping Data 官网：https://spring.io/projects/spring-data

数据库相关的启动器 ：可以参考官方文档：

https://docs.spring.io/spring-boot/docs/2.2.5.RELEASE/reference/htmlsingle/#using-boot-starter

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)10.1.2整合JDBC

创建测试项目测试数据源

1、我去新建一个项目测试：springboot-data-jdbc ; 引入相应的模块！基础模块

![在这里插入图片描述](https://img-blog.csdnimg.cn/2021042421051113.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

2、项目建好之后，发现自动帮我们导入了如下的启动器

```
<dependency>    
    <groupId>org.springframework.boot</groupId>    
    <artifactId>spring-boot-starter-jdbc</artifactId>
</dependency>
<dependency>    
    <groupId>mysql</groupId>    
    <artifactId>mysql-connector-java</artifactId>    
    <scope>runtime</scope>
</dependency>

```

3、编写yaml配置文件连接数据库；

```
spring:
  datasource:
    username: root
    password: "000000"
    driver-class-name: com.mysql.cj.jdbc.Driver
    url: jdbc:mysql://localhost:3306/mybatis?serverTimezone=GMT%2B8&useSSL=false&useUnicode=true&characterEncoding=UTF-8

```

4、配置完这一些东西后，我们就可以直接去使用了，因为SpringBoot已经默认帮我们进行了自动配置；去测试类测试一下

```
@SpringBootTest
class Springboot03JdbcApplicationTests {

    @Autowired
    DataSource dataSource;

    @Test
    void contextLoads() throws SQLException {

        System.out.println(dataSource.getClass());

        Connection connection = dataSource.getConnection();
        
        System.out.println(connection);
        
        connection.close();

    }

```

执行结果：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424210529886.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

这里注意小坑，密码要用引号引起来，不引起来会报错：

```
java.sql.SQLException: Access denied for user 'root'@'localhost' (using password: YES)

```

结果：我们可以看到他默认给我们配置的数据源为 : class com.zaxxer.hikari.HikariDataSource ， 我们并没有手动配置

我们来全局搜索一下，找到数据源的所有自动配置都在 ：DataSourceAutoConfiguration文件：

```
@Import(
    {Hikari.class, Tomcat.class, Dbcp2.class, Generic.class, DataSourceJmxConfiguration.class}
)
protected static class PooledDataSourceConfiguration {
    protected PooledDataSourceConfiguration() {
    }
}

```

这里导入的类都在 DataSourceConfiguration 配置类下，可以看出 Spring Boot 2.2.5 默认使用HikariDataSource 数据源，而以前版本，如 Spring Boot 1.5 默认使用 org.apache.tomcat.jdbc.pool.DataSource 作为数据源；

**HikariDataSource 号称 Java WEB 当前速度最快的数据源，相比于传统的 C3P0 、DBCP、Tomcat jdbc 等连接池更加优秀；**

**可以使用 spring.datasource.type 指定自定义的数据源类型，值为 要使用的连接池实现的完全限定名。**

关于数据源我们并不做介绍，有了数据库连接，显然就可以 CRUD 操作数据库了。但是我们需要先了解一个对象 JdbcTemplate

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)10.1.3JDBCTemplate

1、有了数据源(com.zaxxer.hikari.HikariDataSource)，然后可以拿到数据库连接(java.sql.Connection)，有了连接，就可以使用原生的 JDBC 语句来操作数据库；

2、即使不使用第三方第数据库操作框架，如 MyBatis等，Spring 本身也对原生的JDBC 做了轻量级的封装，即JdbcTemplate。

3、数据库操作的所有 CRUD 方法都在 JdbcTemplate 中。

4、Spring Boot 不仅提供了默认的数据源，同时默认已经配置好了 JdbcTemplate 放在了容器中，程序员只需自己注入即可使用

5、JdbcTemplate 的自动配置是依赖 org.springframework.boot.autoconfigure.jdbc 包下的 JdbcTemplateConfiguration 类

**JdbcTemplate主要提供以下几类方法：**

*   execute方法：可以用于执行任何SQL语句，一般用于执行DDL语句；
*   update方法及batchUpdate方法：update方法用于执行新增、修改、删除等语句；batchUpdate方法用于执行批处理相关语句；
*   query方法及queryForXXX方法：用于执行查询相关语句；
*   call方法：用于执行存储过程、函数相关语句。

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)10.1.4测试

编写一个Controller，注入 jdbcTemplate，编写测试方法进行访问测试；

```
@RestController
@RequestMapping("/jdbc")
public class JdbcController {

    /**
     * Spring Boot 默认提供了数据源，默认提供了 org.springframework.jdbc.core.JdbcTemplate
     * JdbcTemplate 中会自己注入数据源，用于简化 JDBC操作
     * 还能避免一些常见的错误,使用起来也不用再自己来关闭数据库连接
     */
    @Autowired
    JdbcTemplate jdbcTemplate;

    //查询employee表中所有数据
    //List 中的1个 Map 对应数据库的 1行数据
    //Map 中的 key 对应数据库的字段名，value 对应数据库的字段值
    @GetMapping("/list")
    public List<Map<String, Object>> userList(){
        String sql = "select * from employee";
        List<Map<String, Object>> maps = jdbcTemplate.queryForList(sql);
        return maps;
    }
    
    //新增一个用户
    @GetMapping("/add")
    public String addUser(){
        //插入语句，注意时间问题
        String sql = "insert into employee(last_name, email,gender,department,birth)" +
                " values ('狂神说','24736743@qq.com',1,101,'"+ new Date().toLocaleString() +"')";
        jdbcTemplate.update(sql);
        //查询
        return "addOk";
    }

    //修改用户信息
    @GetMapping("/update/{id}")
    public String updateUser(@PathVariable("id") int id){
        //插入语句
        String sql = "update employee set last_name=?,email=? where id="+id;
        //数据
        Object[] objects = new Object[2];
        objects[0] = "秦疆";
        objects[1] = "24736743@sina.com";
        jdbcTemplate.update(sql,objects);
        //查询
        return "updateOk";
    }

    //删除用户
    @GetMapping("/delete/{id}")
    public String delUser(@PathVariable("id") int id){
        //插入语句
        String sql = "delete from employee where id=?";
        jdbcTemplate.update(sql,id);
        //查询
        return "deleteOk";
    }
    
}

```

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)10.2整合Druid数据源
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)10.2.1Druid简介

Java程序很大一部分要操作数据库，为了提高性能操作数据库的时候，又不得不使用数据库连接池。

Druid 是阿里巴巴开源平台上一个数据库连接池实现，结合了 C3P0、DBCP 等 DB 池的优点，同时加入了**日志监控**。

Druid 可以很好的监控 DB 池连接和 SQL 的执行情况，**天生就是针对监控而生**的 DB 连接池。

Druid已经在阿里巴巴部署了超过600个应用，经过一年多生产环境大规模部署的严苛考验。

Spring Boot 2.0 以上默认使用 Hikari 数据源，可以说 Hikari 与 Driud 都是当前 Java Web 上最优秀的数据源，我们来重点介绍 Spring Boot 如何集成 Druid 数据源，如何实现数据库监控。

Github地址：https://github.com/alibaba/druid/

**com.alibaba.druid.pool.DruidDataSource 基本配置参数如下：**

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)10.2.2配置数据源

1、添加上 Druid 数据源依赖

```
<!-- https://mvnrepository.com/artifact/com.alibaba/druid -->
<dependency>
    <groupId>com.alibaba</groupId>
    <artifactId>druid</artifactId>
    <version>1.1.21</version>
</dependency>

```

2、切换数据源；之前已经说过 Spring Boot 2.0 以上默认使用 com.zaxxer.hikari.HikariDataSource 数据源，但可以 通过 spring.datasource.type 指定数据源。

```
spring:
  datasource:
    username: root
    password: "000000"
    driver-class-name: com.mysql.cj.jdbc.Driver
    url: jdbc:mysql://localhost:3306/mybatis?serverTimezone=GMT%2B8&useSSL=false&useUnicode=true&characterEncoding=UTF-8&allowPublicKeyRetrieval=true
    type: com.alibaba.druid.pool.DruidDataSource

```

3、数据源切换之后，在测试类中注入 DataSource，然后获取到它，输出一看便知是否成功切换；

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424210546502.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

4、切换成功！既然切换成功，就可以设置数据源连接初始化大小、最大连接数、等待时间、最小连接数 等设置项；可以查看源码

```
#Spring Boot 默认是不注入这些属性值的，需要自己绑定
    #druid 数据源专有配置
    initialSize: 5
    minIdle: 5
    maxActive: 20
    maxWait: 60000
    timeBetweenEvictionRunsMillis: 60000
    minEvictableIdleTimeMillis: 300000
    validationQuery: SELECT 1 FROM DUAL
    testWhileIdle: true
    testOnBorrow: false
    testOnReturn: false
    poolPreparedStatements: true

    #配置监控统计拦截的filters，stat:监控统计、log4j：日志记录、wall：防御sql注入
    #如果允许时报错  java.lang.ClassNotFoundException: org.apache.log4j.Priority
    #则导入 log4j 依赖即可，Maven 地址：https://mvnrepository.com/artifact/log4j/log4j
    filters: stat,wall,log4j
    maxPoolPreparedStatementPerConnectionSize: 20
    useGlobalDataSourceStat: true
    connectionProperties: druid.stat.mergeSql=true;druid.stat.slowSqlMillis=500

```

这些配置是核心：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424210603874.png)

5.看到需要用到log4j，所以需要在pom中导入log4j的依赖

```
<!-- https://mvnrepository.com/artifact/log4j/log4j -->
<dependency>
    <groupId>log4j</groupId>
    <artifactId>log4j</artifactId>
    <version>1.2.17</version>
</dependency>

```

6、现在需要程序员自己为 DruidDataSource 绑定全局配置文件中的参数，再添加到容器中，而不再使用 Spring Boot 的自动生成了；我们需要 自己添加 DruidDataSource 组件到容器中，并绑定属性；

```
@Configuration
public class DruidConfig {

    /*
       将自定义的 Druid数据源添加到容器中，不再让 Spring Boot 自动创建
       绑定全局配置文件中的 druid 数据源属性到 com.alibaba.druid.pool.DruidDataSource从而让它们生效
       @ConfigurationProperties(prefix = "spring.datasource")：作用就是将 全局配置文件中
       前缀为 spring.datasource的属性值注入到 com.alibaba.druid.pool.DruidDataSource 的同名参数中
     */
    @ConfigurationProperties(prefix = "spring.datasource")
    @Bean
    public DataSource druidDataSource() {
        return new DruidDataSource();
    }

}

```

7、去测试类中测试一下；看是否成功！

```
@SpringBootTest
class SpringbootDataJdbcApplicationTests {

    //DI注入数据源
    @Autowired
    DataSource dataSource;

    @Test
    public void contextLoads() throws SQLException {
        //看一下默认数据源
        System.out.println(dataSource.getClass());
        //获得连接
        Connection connection =   dataSource.getConnection();
        System.out.println(connection);

        DruidDataSource druidDataSource = (DruidDataSource) dataSource;
        System.out.println("druidDataSource 数据源最大连接数：" + druidDataSource.getMaxActive());
        System.out.println("druidDataSource 数据源初始化连接数：" + druidDataSource.getInitialSize());

        //关闭连接
        connection.close();
    }
}

```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424210615227.png)

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)10.2.3配置Druid数据源监控

```

//配置 Druid 监控管理后台的Servlet；
//内置 Servlet 容器时没有web.xml文件，所以使用 Spring Boot 的注册 Servlet 方式
@Bean
public ServletRegistrationBean statViewServlet() {
    ServletRegistrationBean bean = new ServletRegistrationBean(new StatViewServlet(), "/druid/*");

    // 这些参数可以在 com.alibaba.druid.support.http.StatViewServlet 
    // 的父类 com.alibaba.druid.support.http.ResourceServlet 中找到
    Map<String, String> initParams = new HashMap<>();
    initParams.put("loginUsername", "admin"); //后台管理界面的登录账号
    initParams.put("loginPassword", "123456"); //后台管理界面的登录密码

    //后台允许谁可以访问
    //initParams.put("allow", "localhost")：表示只有本机可以访问
    //initParams.put("allow", "")：为空或者为null时，表示允许所有访问
    initParams.put("allow", "");
    //deny：Druid 后台拒绝谁访问
    //initParams.put("kuangshen", "192.168.1.20");表示禁止此ip访问

    //设置初始化参数
    bean.setInitParameters(initParams);
    return bean;
}

```

配置完毕后，我们可以选择访问 ：http://localhost:8080/druid/login.html

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424210626237.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

在访问http://localhost:8080/userList 后：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424210636573.png)

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)10.2.4配置 Druid web 监控 filter 过滤器

```
//配置 Druid 监控 之  web 监控的 filter
//WebStatFilter：用于配置Web和Druid数据源之间的管理关联监控统计
@Bean
public FilterRegistrationBean webStatFilter() {
    FilterRegistrationBean bean = new FilterRegistrationBean();
    bean.setFilter(new WebStatFilter());

    //exclusions：设置哪些请求进行过滤排除掉，从而不进行统计
    Map<String, String> initParams = new HashMap<>();
    initParams.put("exclusions", "*.js,*.css,/druid/*,/jdbc/*");
    bean.setInitParameters(initParams);

    //"/*" 表示过滤所有请求
    bean.setUrlPatterns(Arrays.asList("/*"));
    return bean;
}

```

注意点：DruidConfig文件一定要添加配置注解，在里面配置的一些servlet和filter都要添加@Bean注解

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)10.3整合Mybatis
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

官方文档：http://mybatis.org/spring-boot-starter/mybatis-spring-boot-autoconfigure/

Maven仓库地址：https://mvnrepository.com/artifact/org.mybatis.spring.boot/mybatis-spring-boot-starter/2.1.1

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)10.3.1整合测试

1、导入 MyBatis 所需要的依赖

```
<dependency>
    <groupId>org.mybatis.spring.boot</groupId>
    <artifactId>mybatis-spring-boot-starter</artifactId>
    <version>2.1.1</version>
</dependency>

```

2.配置数据库连接信息（不变）

```
spring:
  datasource:
    username: root
    password: "000000"
    #?serverTimezone=UTC解决时区的报错
    url: jdbc:mysql://localhost:3306/mybatis?serverTimezone=GMT%2B8&useSSL=false&useUnicode=true&characterEncoding=UTF-8&allowPublicKeyRetrieval=true
    driver-class-name: com.mysql.cj.jdbc.Driver
    type: com.alibaba.druid.pool.DruidDataSource

    #Spring Boot 默认是不注入这些属性值的，需要自己绑定
    #druid 数据源专有配置
    initialSize: 5
    minIdle: 5
    maxActive: 20
    maxWait: 60000
    timeBetweenEvictionRunsMillis: 60000
    minEvictableIdleTimeMillis: 300000
    validationQuery: SELECT 1 FROM DUAL
    testWhileIdle: true
    testOnBorrow: false
    testOnReturn: false
    poolPreparedStatements: true

    #配置监控统计拦截的filters，stat:监控统计、log4j：日志记录、wall：防御sql注入
    #如果允许时报错  java.lang.ClassNotFoundException: org.apache.log4j.Priority
    #则导入 log4j 依赖即可，Maven 地址：https://mvnrepository.com/artifact/log4j/log4j
    filters: stat,wall,log4j
    maxPoolPreparedStatementPerConnectionSize: 20
    useGlobalDataSourceStat: true
    connectionProperties: druid.stat.mergeSql=true;druid.stat.slowSqlMillis=500

mybatis:
  type-aliases-package: com.guo.pojo
  mapper-locations: classpath:mybatis/mapper/*.xml
server:
  port: 8081

```

3、测试数据库是否连接成功！

4、创建实体类，导入 Lombok!

User.java

```
@Data
@AllArgsConstructor
@NoArgsConstructor
public class User {

    private Integer id;
    private String name;
    private String pwd;

}


```

5、创建mapper目录以及对应的 Mapper 接口

UserMapper.java

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424210651202.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

```
@Mapper
@Repository
public interface UserMapper {

    public static final int age=18;

    List<User> queryUserList();

    User queryUserById(Integer id);

    int addUser(User user);

    int updateUser(User user);

    int deleteUserById(Integer id);

}

```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424210659756.png)

接下来该去配置mapper.xml文件了，这里建议创建在resources的目录下：

![](https://img-blog.csdnimg.cn/20210424210710643.png)

UserMapper.xml文件：

```
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE mapper
        PUBLIC "-//mybatis.org//DTD Config 3.0//EN"
        "http://mybatis.org/dtd/mybatis-3-mapper.dtd">
<!--configuration core file-->
<mapper namespace="com.guo.mapper.UserMapper">

    <select id="queryUserList" resultType="User">
        
    </select>

</mapper>


```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424210721230.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

暂时先不写service层，直接写controller调用mapper

```
@RestController
public class UserController {

    @Autowired
    private UserMapper userMapper;

    @RequestMapping("/list")
    public List<User> List(){

        return userMapper.queryUserList();

    }
}

```

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)11.SpringSecurity(安全)
=========================================================================================================================================================================================================================================================================================================================================================================================================================================================================

一个安全的框架，其实通过过滤器和拦截器也可以实现

首先我们看下它的官网介绍：Spring Security官网地址

Spring Security is a powerful and highly customizable authentication and access-control framework. It is the de-facto standard for securing Spring-based applications.

Spring Security is a framework that focuses on providing both authentication and authorization to Java applications. Like all Spring projects, the real power of Spring Security is found in how easily it can be extended to meet custom requirements

Spring Security是一个功能强大且高度可定制的身份验证和访问控制框架。它实际上是保护基于spring的应用程序的标准。

Spring Security是一个框架，侧重于为Java应用程序提供身份验证和授权。与所有Spring项目一样，Spring安全性的真正强大之处在于它可以轻松地扩展以满足定制需求

在用户认证方面，Spring Security 框架支持主流的认证方式，包括 HTTP 基本认证、HTTP 表单验证、HTTP 摘要认证、OpenID 和 LDAP 等。在用户授权方面，Spring Security 提供了基于角色的访问控制和访问控制列表（Access Control List，ACL），可以对应用中的领域对象进行细粒度的控制。

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)11.1认识SpringSecurity
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Spring Security 是针对Spring项目的安全框架，也是Spring Boot底层安全模块默认的技术选型，他可以实现强大的Web安全控制，对于安全控制，我们仅需要引入 spring-boot-starter-security 模块，进行少量的配置，即可实现强大的安全管理！

记住几个类：

*   WebSecurityConfigurerAdapter：自定义Security策略
*   AuthenticationManagerBuilder：自定义认证策略
*   @EnableWebSecurity：开启WebSecurity模式

Spring Security的两个主要目标是 “认证” 和 “授权”（访问控制）。

**“认证”（Authentication）**

身份验证是关于验证您的凭据，如用户名/用户ID和密码，以验证您的身份。

身份验证通常通过用户名和密码完成，有时与身份验证因素结合使用。

**“授权” （Authorization）**

授权发生在系统成功验证您的身份后，最终会授予您访问资源（如信息，文件，数据库，资金，位置，几乎任何内容）的完全权限。

这个概念是通用的，而不是只在Spring Security 中存在。

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)11.2实战使用
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)11.2.1配置页面的访问权限

1.首先导入需要的静态资源：

链接：https://pan.baidu.com/s/1oB9-VKrN4tzh61MtdW5Dow  
提取码：clsq  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424210825830.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

2.引入 SpringSecurity 依赖

```
<!--SpringSecurity -->
<dependency>
     <groupId>org.springframework.boot</groupId>
     <artifactId>spring-boot-starter-security</artifactId>
</dependency>

```

3.新建一个配置文件，并且继承 WebSecurityConfigurerAdapter,并且要添加@EnableWebSecurity注解

```
@EnableWebSecurity
public class SecurityConfig extends WebSecurityConfigurerAdapter {

    @Override
    protected void configure(HttpSecurity http) throws Exception {
        http.authorizeRequests()
                .antMatchers("/").permitAll()
                .antMatchers("/level1/**").hasAnyRole("vip1")
                .antMatchers("/level2/**").hasAnyRole("vip2")
                .antMatchers("/level3/**").hasAnyRole("vip3");

    }
}


```

注意这里用到了链式

4、测试一下：发现除了首页都进不去了！因为我们目前没有登录的角色，因为请求需要登录的角色拥有对应的权限才可以！

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424210836681.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

5、在configure()方法中加入以下配置，开启自动配置的登录功能！

```
// 开启自动配置的登录功能
// /login 请求来到登录页
// /login?error 重定向到这里表示登录失败
http.formLogin();

```

测试发现没有权限的时候，会跳转到登录的页面：  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424210850767.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

6、查看刚才登录页的注释信息；

我们可以定义认证规则，重写configure(AuthenticationManagerBuilder auth)方法

也可以去jdbc中去取

```
//定义认证规则
@Override
protected void configure(AuthenticationManagerBuilder auth) throws Exception {
   
   //在内存中定义，也可以在jdbc中去拿....
   auth.inMemoryAuthentication()
          .withUser("kuangshen").password("123456").roles("vip2","vip3")
          .and()
          .withUser("root").password("123456").roles("vip1","vip2","vip3")
          .and()
          .withUser("guest").password("123456").roles("vip1");
}

```

7.测试，我们可以使用这些账号登录进行测试！发现会报错！

![在这里插入图片描述](https://img-blog.csdnimg.cn/2021042421090378.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

8.原因，我们要将前端传过来的密码进行某种方式加密，否则就无法登录，修改代码

```
//定义认证规则
@Override
protected void configure(AuthenticationManagerBuilder auth) throws Exception {
   //在内存中定义，也可以在jdbc中去拿....
   //Spring security 5.0中新增了多种加密方式，也改变了密码的格式。
   //要想我们的项目还能够正常登陆，需要修改一下configure中的代码。我们要将前端传过来的密码进行某种方式加密
   //spring security 官方推荐的是使用bcrypt加密方式。
   
   auth.inMemoryAuthentication().passwordEncoder(new BCryptPasswordEncoder())
          .withUser("admin").password(new BCryptPasswordEncoder().encode("123456")).roles("vip2","vip3")
          .and()
          .withUser("root").password(new BCryptPasswordEncoder().encode("123456")).roles("vip1","vip2","vip3")
          .and()
          .withUser("guest").password(new BCryptPasswordEncoder().encode("123456")).roles("vip1","vip2");
}

```

测试，发现，登录成功，并且每个角色只能访问自己认证下的规则！搞定

受权从数据库里读数据：

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)11.2.2权限控制和注销

1、开启自动配置的注销的功能

```
//定制请求的授权规则
@Override
protected void configure(HttpSecurity http) throws Exception {
   //....
   //开启自动配置的注销的功能
      // /logout 注销请求
   http.logout();
}

```

2、我们在前端，增加一个注销的按钮，index.html 导航栏中

```
                <a class="item" th:href="@{/logout}">
                    <i class="sign-out icon"></i> 注销
                </a>

```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424211000715.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

3、我们可以去测试一下，登录成功后点击注销，发现注销完毕会跳转到登录页面！

4、但是，我们想让他注销成功后，依旧可以跳转到首页，该怎么处理呢？

```
// .logoutSuccessUrl("/"); 注销成功来到首页
http.logout().logoutSuccessUrl("/");

```

5、测试，注销完毕后，发现跳转到首页OK

6、我们现在又来一个需求：用户没有登录的时候，导航栏上只显示登录按钮，用户登录之后，导航栏可以显示登录的用户信息及注销按钮！还有就是，比如kuangshen这个用户，它只有 vip2，vip3功能，那么登录则只显示这两个功能，而vip1的功能菜单不显示！这个就是真实的网站情况了！该如何做呢？

我们需要结合thymeleaf中的一些功能

sec：authorize=“isAuthenticated()”:是否认证登录！来显示不同的页面

导入thymeleaf和security结合的Maven依赖：

```
<!-- https://mvnrepository.com/artifact/org.thymeleaf.extras/thymeleaf-extras-springsecurity4 -->
<dependency>
   <groupId>org.thymeleaf.extras</groupId>
   <artifactId>thymeleaf-extras-springsecurity5</artifactId>
   <version>3.0.4.RELEASE</version>
</dependency>

```

7、修改我们的 前端页面

导入命名空间

```
xmlns:sec="http://www.thymeleaf.org/thymeleaf-extras-springsecurity5"

```

修改导航栏，增加认证判断

```
<!--登录注销-->
<div class="right menu">

   <!--如果未登录-->
   <div sec:authorize="!isAuthenticated()">
       <a class="item" th:href="@{/login}">
           <i class="address card icon"></i> 登录
       </a>
   </div>

   <!--如果已登录-->
   <div sec:authorize="isAuthenticated()">
       <a class="item">
           <i class="address card icon"></i>
          用户名：<span sec:authentication="principal.username"></span>
          角色：<span sec:authentication="principal.authorities"></span>
       </a>
   </div>

   <div sec:authorize="isAuthenticated()">
       <a class="item" th:href="@{/logout}">
           <i class="address card icon"></i> 注销
       </a>
   </div>
</div>

```

8、重启测试，我们可以登录试试看，登录成功后确实，显示了我们想要的页面；

9、如果注销404了，就是因为它默认防止csrf跨站请求伪造，因为会产生安全问题，我们可以将请求改为post表单提交，或者在spring security中关闭csrf功能；我们试试：在 配置中增加 `http.csrf().disable();`

SecurityConfig.java

```
        http.csrf().disable();//关闭csrf功能:跨站请求伪造,默认只能通过post方式提交logout请求

```

到目前为止已近实现了权限的访问资源不同，接下来还想实现对不同用户的页面显示内容不同：

关键代码：sec:authorize=“hasRole()” //判断当前的权限是否有这个权限直接加在想要设置权限的标签内即可

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)11.2.3记住我及首页定制

现在的情况，我们只要登录之后，关闭浏览器，再登录，就会让我们重新登录，但是很多网站的情况，就是有一个记住密码的功能，这个该如何实现呢？很简单

1、开启记住我功能

```
//定制请求的授权规则
@Override
protected void configure(HttpSecurity http) throws Exception {
//...
   //记住我
   http.rememberMe();
}

```

2、我们再次启动项目测试一下，发现登录页多了一个记住我功能，我们登录之后关闭 浏览器，然后重新打开浏览器访问，发现用户依旧存在！

思考：如何实现的呢？其实非常简单

我们可以查看浏览器的cookie

![](https://img-blog.csdnimg.cn/20210424211053286.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

并且可以知道这个cookie的保存日期默认为14天

3、我们点击注销的时候，可以发现，spring security 帮我们自动删除了这个 cookie

4、结论：登录成功后，将cookie发送给浏览器保存，以后登录带上这个cookie，只要通过检查就可以免登录了。如果点击注销，则会删除这个cookie，具体的原理我们在JavaWeb阶段都讲过了，这里就不在多说了！

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)11.2.4定制登录页

现在这个登录页面都是spring security 默认的，怎么样可以使用我们自己写的Login界面呢？

1、在刚才的登录页配置后面指定 loginpage

```
http.formLogin().loginPage("/toLogin");

```

2、然后前端也需要指向我们自己定义的 login请求

```
<a class="item" th:href="@{/toLogin}">
   <i class="address card icon"></i> 登录
</a>

```

3、我们登录，需要将这些信息发送到哪里，我们也需要配置，login.html 配置提交请求及方式，方式必须为post:

```
<form th:action="@{/toLogin}" method="post">

```

图示解析：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424211107672.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

4、这个请求提交上来，我们还需要验证处理，怎么做呢？我们可以查看formLogin()方法的源码！我们配置接收登录的用户名和密码的参数！

例子：比如下列就会出现报错：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424211119581.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

这时就需要去config中设置一下，将对应的字段进行连接

```
 http.formLogin().usernameParameter("name").passwordParameter("pwd").loginPage("/toLogin1");

```

5、在登录页增加记住我的选择框

```
<input type="checkbox" name="remember"> 记住我

```
```
        http.rememberMe().rememberMeParameter("remember");

```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424211133670.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)12.Shiro
============================================================================================================================================================================================================================================================================================================================================================================================================================================================

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)12.1概述
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)12.1.1简介

Apache Shiro是一个强大且易用的Java安全框架

可以完成身份验证、授权、密码和会话管理

Shiro 不仅可以用在 JavaSE 环境中，也可以用在 JavaEE 环境中

官网： http://shiro.apache.org/

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)12.1.2 功能

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424211147776.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

Authentication：身份认证/登录，验证用户是不是拥有相应的身份；

Authorization：授权，即权限验证，验证某个已认证的用户是否拥有某个权限；即判断用户是否能做事情，常见的如：验证某个用户是否拥有某个角色。或者细粒度的验证某个用户对某个资源是否具有某个权限；

Session Manager：会话管理，即用户登录后就是一次会话，在没有退出之前，它的所有信息都在会话中；会话可以是普通JavaSE环境的，也可以是如Web环境的；

Cryptography：加密，保护数据的安全性，如密码加密存储到数据库，而不是明文存储；

Web Support：Web支持，可以非常容易的集成到Web环境；

Caching：缓存，比如用户登录后，其用户信息、拥有的角色/权限不必每次去查，这样可以提高效率；

Concurrency：shiro支持多线程应用的并发验证，即如在一个线程中开启另一个线程，能把权限自动传播过去；

Testing：提供测试支持；

Run As：允许一个用户假装为另一个用户（如果他们允许）的身份进行访问；

Remember Me：记住我，这个是非常常见的功能，即一次登录后，下次再来的话不用登录了。

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)12.1.3从外部看

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424211158270.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

应用代码直接交互的对象是Subject，也就是说Shiro的对外API核心就是Subject；其每个API的含义：

​ Subject：主体，代表了当前“用户”，这个用户不一定是一个具体的人，与当前应用交互的任何东西都是Subject，如网络爬虫，机器人等；即一个抽象概念；所有Subject都绑定到SecurityManager，与Subject的所有交互都会委托给SecurityManager；可以把Subject认为是一个门面；SecurityManager才是实际的执行者；

​ SecurityManager：安全管理器；即所有与安全有关的操作都会与SecurityManager交互；且它管理着所有Subject；可以看出它是Shiro的核心，它负责与后边介绍的其他组件进行交互，如果学习过SpringMVC，你可以把它看成DispatcherServlet前端控制器；

​ Realm：域，Shiro从从Realm获取安全数据（如用户、角色、权限），就是说SecurityManager要验证用户身份，那么它需要从Realm获取相应的用户进行比较以确定用户身份是否合法；也需要从Realm得到用户相应的角色/权限进行验证用户是否能进行操作；可以把Realm看成DataSource，即安全数据源。

也就是说对于我们而言，最简单的一个Shiro应用：

1.  应用代码通过Subject来进行认证和授权，而Subject又委托给SecurityManager；
2.  我们需要给Shiro的SecurityManager注入Realm，从而让SecurityManager能得到合法的用户及其权限进行判断。

从以上也可以看出，Shiro不提供维护用户/权限，而是通过Realm让开发人员自己注入

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)12.1.4外部架构

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424211208553.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

Subject：主体，可以看到主体可以是任何可以与应用交互的“用户”；

SecurityManager：相当于SpringMVC中的DispatcherServlet或者Struts2中的FilterDispatcher；是Shiro的心脏；所有具体的交互都通过SecurityManager进行控制；它管理着所有Subject、且负责进行认证和授权、及会话、缓存的管理。

Authenticator：认证器，负责主体认证的，这是一个扩展点，如果用户觉得Shiro默认的不好，可以自定义实现；其需要认证策略（Authentication Strategy），即什么情况下算用户认证通过了；

Authrizer：授权器，或者访问控制器，用来决定主体是否有权限进行相应的操作；即控制着用户能访问应用中的哪些功能；

Realm：可以有1个或多个Realm，可以认为是安全实体数据源，即用于获取安全实体的；可以是JDBC实现，也可以是LDAP实现，或者内存实现等等；由用户提供；注意：Shiro不知道你的用户/权限存储在哪及以何种格式存储；所以我们一般在应用中都需要实现自己的Realm；

SessionManager：如果写过Servlet就应该知道Session的概念，Session呢需要有人去管理它的生命周期，这个组件就是SessionManager；而Shiro并不仅仅可以用在Web环境，也可以用在如普通的JavaSE环境、EJB等环境；所有呢，Shiro就抽象了一个自己的Session来管理主体与应用之间交互的数据；这样的话，比如我们在Web环境用，刚开始是一台Web服务器；接着又上了台EJB服务器；这时想把两台服务器的会话数据放到一个地方，这个时候就可以实现自己的分布式会话（如把数据放到Memcached服务器）；

SessionDAO：DAO大家都用过，数据访问对象，用于会话的CRUD，比如我们想把Session保存到数据库，那么可以实现自己的SessionDAO，通过如JDBC写到数据库；比如想把Session放到Memcached中，可以实现自己的Memcached SessionDAO；另外SessionDAO中可以使用Cache进行缓存，以提高性能；

CacheManager：缓存控制器，来管理如用户、角色、权限等的缓存的；因为这些数据基本上很少去改变，放到缓存中后可以提高访问的性能

Cryptography：密码模块，Shiro提高了一些常见的加密组件用于如密码加密/解密的

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)12.1.5认证流程

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424211221291.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

**用户** 提交 **身份信息、凭证信息** 封装成 **令牌** 交由 **安全管理器** 认证

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)12.2. 快速入门
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

将案例拷贝：

按照官网提示找到 快速入门案例

GitHub地址：[shiro/samples/quickstart/](https://github.com/apache/shiro/tree/master/samples/quickstart)

从GitHub 的文件中可以看出这个快速入门案例是一个 Maven 项目

1.新建一个 Maven 工程，删除其 src 目录，将其作为父工程

2.在父工程中新建一个 Maven 模块

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424211233100.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

复制快速入门案例 POM.xml 文件中的依赖 （版本号自选）

把快速入门案例中的 resource 下的`log4j.properties` 复制下来

```
log4j.rootLogger=INFO, stdout

log4j.appender.stdout=org.apache.log4j.ConsoleAppender
log4j.appender.stdout.layout=org.apache.log4j.PatternLayout
log4j.appender.stdout.layout.ConversionPattern=%d %p [%c] - %m %n

# General Apache libraries
log4j.logger.org.apache=WARN

# Spring
log4j.logger.org.springframework=WARN

# Default Shiro logging
log4j.logger.org.apache.shiro=INFO

# Disable verbose logging
log4j.logger.org.apache.shiro.util.ThreadContext=WARN
log4j.logger.org.apache.shiro.cache.ehcache.EhCache=WARN

```

复制一下 `shiro.ini` 文件

ok需要下载ini插件，如果在setting中无法下载，就去官网下载对应版本的然后导入

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)ini插件安装和配置

![](https://img-blog.csdnimg.cn/20210424211243914.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424211254499.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424211304708.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424211321351.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

```
[users]
# user 'root' with password 'secret' and the 'admin' role
root = secret, admin
# user 'guest' with the password 'guest' and the 'guest' role
guest = guest, guest
# user 'presidentskroob' with password '12345' ("That's the same combination on
# my luggage!!!" ;)), and role 'president'
presidentskroob = 12345, president
# user 'darkhelmet' with password 'ludicrousspeed' and roles 'darklord' and 'schwartz'
darkhelmet = ludicrousspeed, darklord, schwartz
# user 'lonestarr' with password 'vespa' and roles 'goodguy' and 'schwartz'
lonestarr = vespa, goodguy, schwartz

# -----------------------------------------------------------------------------
# Roles with assigned permissions
#
# Each line conforms to the format defined in the
# org.apache.shiro.realm.text.TextConfigurationRealm#setRoleDefinitions JavaDoc
# -----------------------------------------------------------------------------
[roles]
# 'admin' role has all permissions, indicated by the wildcard '*'
admin = *
# The 'schwartz' role can do anything (*) with any lightsaber:
schwartz = lightsaber:*
# The 'goodguy' role is allowed to 'drive' (action) the winnebago (type) with
# license plate 'eagle5' (instance specific id)
goodguy = winnebago:drive:eagle5

```

导入quickstart.java

```
import org.apache.shiro.SecurityUtils;
import org.apache.shiro.authc.*;
import org.apache.shiro.config.IniSecurityManagerFactory;
import org.apache.shiro.mgt.DefaultSecurityManager;
import org.apache.shiro.realm.text.IniRealm;
import org.apache.shiro.session.Session;
import org.apache.shiro.subject.Subject;
import org.apache.shiro.util.Factory;
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;

/**
 * @ClassName Quickstart
 * @Description TODO
 * @Author GuoSheng
 * @Date 2021/4/20  17:28
 * @Version 1.0
 **/
public class Quickstart {

    private static final transient Logger log = LoggerFactory.getLogger(Quickstart.class);

    public static void main(String[] args) {

        // The easiest way to create a Shiro SecurityManager with configured
        // realms, users, roles and permissions is to use the simple INI config.
        // We'll do that by using a factory that can ingest a .ini file and
        // return a SecurityManager instance:

        // Use the shiro.ini file at the root of the classpath
        // (file: and url: prefixes load from files and urls respectively):
        DefaultSecurityManager defaultSecurityManager=new DefaultSecurityManager();
        IniRealm iniRealm=new IniRealm("classpath:shiro.ini");
        defaultSecurityManager.setRealm(iniRealm);

        // for this simple example quickstart, make the SecurityManager
        // accessible as a JVM singleton.  Most applications wouldn't do this
        // and instead rely on their container configuration or web.xml for
        // webapps.  That is outside the scope of this simple quickstart, so
        // we'll just do the bare minimum so you can continue to get a feel
        // for things.
        SecurityUtils.setSecurityManager(defaultSecurityManager);

        // Now that a simple Shiro environment is set up, let's see what you can do:

        // get the currently executing user:
        Subject currentUser = SecurityUtils.getSubject();

        // Do some stuff with a Session (no need for a web or EJB container!!!)
        Session session = currentUser.getSession();
        session.setAttribute("someKey", "aValue");
        String value = (String) session.getAttribute("someKey");
        if (value.equals("aValue")) {
            log.info("Retrieved the correct value! [" + value + "]");
        }

        // let's login the current user so we can check against roles and permissions:
        if (!currentUser.isAuthenticated()) {
            UsernamePasswordToken token = new UsernamePasswordToken("lonestarr", "vespa");
            token.setRememberMe(true);
            try {
                currentUser.login(token);
            } catch (UnknownAccountException uae) {
                log.info("There is no user with username of " + token.getPrincipal());
            } catch (IncorrectCredentialsException ice) {
                log.info("Password for account " + token.getPrincipal() + " was incorrect!");
            } catch (LockedAccountException lae) {
                log.info("The account for username " + token.getPrincipal() + " is locked.  " +
                        "Please contact your administrator to unlock it.");
            }
            // ... catch more exceptions here (maybe custom ones specific to your application?
            catch (AuthenticationException ae) {
                //unexpected condition?  error?
            }
        }

        //say who they are:
        //print their identifying principal (in this case, a username):
        log.info("User [" + currentUser.getPrincipal() + "] logged in successfully.");

        //test a role:
        if (currentUser.hasRole("schwartz")) {
            log.info("May the Schwartz be with you!");
        } else {
            log.info("Hello, mere mortal.");
        }

        //test a typed permission (not instance-level)
        if (currentUser.isPermitted("lightsaber:wield")) {
            log.info("You may use a lightsaber ring.  Use it wisely.");
        } else {
            log.info("Sorry, lightsaber rings are for schwartz masters only.");
        }

        //a (very powerful) Instance Level permission:
        if (currentUser.isPermitted("winnebago:drive:eagle5")) {
            log.info("You are permitted to 'drive' the winnebago with license plate (id) 'eagle5'.  " +
                    "Here are the keys - have fun!");
        } else {
            log.info("Sorry, you aren't allowed to drive the 'eagle5' winnebago!");
        }

        //all done - log out!
        currentUser.logout();

        System.exit(0);
    }
}


```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424211345678.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424211354312.png)

执行一下main方法：  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424211404844.png)

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)12.2.2. 分析案例

先分析一些方法混个脸熟

1.通过 SecurityUtils 获取当前执行的用户 Subject

```
Subject currentUser = SecurityUtils.getSubject();

```

2.通过 当前用户拿到 Session,shiro的session

```
Session session = currentUser.getSession();

```

3.用 Session 存值取值

```
session.setAttribute("someKey", "aValue");
        String value = (String) session.getAttribute("someKey");

```

4.判断用户是否被认证

```
currentUser.isAuthenticated()

```

5.执行登录操作

```
 currentUser.login(token);

```

6.打印其标识主体

```
currentUser.getPrincipal()

```

7.注销

```
currentUser.logout();

```

全部代码：

```
/**
 * @ClassName Quickstart
 * @Description TODO
 * @Author GuoSheng
 * @Date 2021/4/20  17:28
 * @Version 1.0
 **/
public class Quickstart {

    private static final transient Logger log = LoggerFactory.getLogger(Quickstart.class);

    public static void main(String[] args) {

        // The easiest way to create a Shiro SecurityManager with configured
        // realms, users, roles and permissions is to use the simple INI config.
        // We'll do that by using a factory that can ingest a .ini file and
        // return a SecurityManager instance:

        // Use the shiro.ini file at the root of the classpath
        // (file: and url: prefixes load from files and urls respectively):
        DefaultSecurityManager defaultSecurityManager=new DefaultSecurityManager();
        IniRealm iniRealm=new IniRealm("classpath:shiro.ini");
        defaultSecurityManager.setRealm(iniRealm);

        SecurityUtils.setSecurityManager(defaultSecurityManager);

        // Now that a simple Shiro environment is set up, let's see what you can do:

        // get the currently executing user:
        Subject currentUser = SecurityUtils.getSubject();

        // Do some stuff with a Session (no need for a web or EJB container!!!)
        Session session = currentUser.getSession();
        session.setAttribute("someKey", "aValue");
        String value = (String) session.getAttribute("someKey");
        if (value.equals("aValue")) {
            log.info("Retrieved the correct value! [" + value + "]");
        }

        // let's login the current user so we can check against roles and permissions:
        if (!currentUser.isAuthenticated()) {
            UsernamePasswordToken token = new UsernamePasswordToken("lonestarr", "vespa");
            token.setRememberMe(true);
            try {
                currentUser.login(token);
            } catch (UnknownAccountException uae) {
                log.info("There is no user with username of " + token.getPrincipal());
            } catch (IncorrectCredentialsException ice) {
                log.info("Password for account " + token.getPrincipal() + " was incorrect!");
            } catch (LockedAccountException lae) {
                log.info("The account for username " + token.getPrincipal() + " is locked.  " +
                        "Please contact your administrator to unlock it.");
            }
            // ... catch more exceptions here (maybe custom ones specific to your application?
            catch (AuthenticationException ae) {
                //unexpected condition?  error?
            }
        }

        //say who they are:
        //print their identifying principal (in this case, a username):
        log.info("User [" + currentUser.getPrincipal() + "] logged in successfully.");

        //test a role:
        if (currentUser.hasRole("schwartz")) {
            log.info("May the Schwartz be with you!");
        } else {
            log.info("Hello, mere mortal.");
        }

        //test a typed permission (not instance-level)
        if (currentUser.isPermitted("lightsaber:wield")) {
            log.info("You may use a lightsaber ring.  Use it wisely.");
        } else {
            log.info("Sorry, lightsaber rings are for schwartz masters only.");
        }

        //a (very powerful) Instance Level permission:
        if (currentUser.isPermitted("winnebago:drive:eagle5")) {
            log.info("You are permitted to 'drive' the winnebago with license plate (id) 'eagle5'.  " +
                    "Here are the keys - have fun!");
        } else {
            log.info("Sorry, you aren't allowed to drive the 'eagle5' winnebago!");
        }

        //all done - log out!
        currentUser.logout();

        System.exit(0);
    }
}


```

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)12.3Springboot集成Shiro
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

1.  在刚刚的父项目中新建一个 springboot 模块
2.  导入 SpringBoot 和 Shiro 整合包的依赖

```
<!--SpringBoot 和 Shiro 整合包-->
		<!-- https://mvnrepository.com/artifact/org.apache.shiro/shiro-spring-boot-web-starter -->
		<dependency>
			<groupId>org.apache.shiro</groupId>
			<artifactId>shiro-spring-boot-web-starter</artifactId>
			<version>1.6.0</version>
		</dependency>

```

下面是编写配置文件  
Shiro 三大要素

subject -> ShiroFilterFactoryBean ----当前用户  
securityManager -> DefaultWebSecurityManager ----管理所有用户  
Realm  
实际操作中对象创建的顺序 ： realm -> securityManager -> subject ----连接数据

3.创建config文件，编写UserRealm.java继承AuthorizingRealm并实现方法

```
public class UserRealm extends AuthorizingRealm {

    //授权
    @Override
    protected AuthorizationInfo doGetAuthorizationInfo(PrincipalCollection principalCollection) {
        System.out.println("执行了授权方法");
        return null;
    }

    //认证
    @Override
    protected AuthenticationInfo doGetAuthenticationInfo(AuthenticationToken authenticationToken) throws AuthenticationException {
        System.out.println("执行了认证方法");

        return null;
    }
}

```

可以两个方法的功能主要实现了授权和认证，我们添加两个输出一会看看效果

4.在Config文件夹下编写ShiroConfig.java文件，将三大Bean注入到spring中

①根据前面提供的顺序，先编写realm类：

```
    //1：创建realm对象，需要自定义
    @Bean(name = "userRealm")
    public UserRealm userRealm(){
        return new UserRealm();
    }

```

②创建用户管理，这里需要用到前面创建的realm，因此在realm之后进行编写

```
    //2：创建管理用户需要用到
    @Bean
    public DefaultWebSecurityManager defaultWebSecurityManager(@Qualifier("userRealm") UserRealm userRealm){
        DefaultWebSecurityManager securityManager = new DefaultWebSecurityManager();
        securityManager.setRealm(userRealm);

        return securityManager;

    }

```

图示解析：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424211527689.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

③创建subject，需要传入一个securityManager，因此最后进行编写（是不是很像套娃）

```
    @Bean
    public ShiroFilterFactoryBean shiroFilterFactoryBean(@Qualifier("defaultWebSecurityManager") DefaultWebSecurityManager securityManager){
        ShiroFilterFactoryBean subject = new ShiroFilterFactoryBean();
        //设置安全管理器
        bean.setSecurityManager(securityManager);

        return subject;
    }

```

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)12.3.1搭建简单测试环境

1.  新建一个登录页面
2.  新建一个首页  
    首页上有三个链接，一个登录，一个增加用户，一个删除用户
3.  新建一个增加用户页面
4.  新建一个删除用户页面
5.  编写对应的 Controller

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)12.3.2实现登录拦截

```
        //添加shiro的内置过滤器
        /**
         anon:无需认证就可以访问
         authc:必须认证才可访问
         user：必须拥有   记住我才能用
         perms：拥有对某个资源的权限才能访问
         role:拥有某个角色权限才能访问
        **/
    @Bean
    public ShiroFilterFactoryBean shiroFilterFactoryBean(@Qualifier("defaultWebSecurityManager") DefaultWebSecurityManager securityManager){
        ShiroFilterFactoryBean bean = new ShiroFilterFactoryBean();
        //设置安全管理器
        bean.setSecurityManager(securityManager);

        Map<String, String> filterMap =new LinkedHashMap<String,String>();

        filterMap.put("/user/add","anon");//表示/user/add这个请求所有人可以访问

        filterMap.put("/user/update","authc");//表示/user/update这个请求只有登录后可以访问

        bean.setLoginUrl("/toLogin");

        bean.setFilterChainDefinitionMap(filterMap);

        return bean;
    }

```

图示解析：  
![在这里插入图片描述](https://img-blog.csdnimg.cn/2021042421142418.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

当然在拦截请求中也支持通配符：如拦截指定/user下的所有请求：/user/\*

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)12.3.3实现用户认证

实现用户认证需要去realm类的认证方法中去配置

这里我们先把用户名和密码写死，实际中是要去数据库中去取的

去到UserRealm.java中

```
    @Override
    protected AuthenticationInfo doGetAuthenticationInfo(AuthenticationToken token) throws AuthenticationException {
        System.out.println("执行了认证方法");

        String name="root";
        String password="123456";
        UsernamePasswordToken userToken = (UsernamePasswordToken)token;

        if(!userToken.getUsername().equals(name)){
            return null;
        }
        
        return new SimpleAuthenticationInfo("",password,"");
    }

```

编写Controller中的登录方法：

```
    @RequestMapping("/login")
    public String login(@RequestParam("username") String username,@RequestParam("password") String password,Model model) {
        //获取当前的用户
        Subject subject = SecurityUtils.getSubject();
        //封装用户的登录数据
        UsernamePasswordToken token = new UsernamePasswordToken(username, password);

        try {
            subject.login(token);//执行登录的方法，如果没有异常
            return "index";
        } catch (UnknownAccountException e) {
            model.addAttribute("msg", "用户名错误");
            return "login";
        } catch (IncorrectCredentialsException e) {
            model.addAttribute("msg", "密码错误");
            return "login";
        }
    }

```

图示解析：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424211436578.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)12.3.4Shiro整合Mybatis

1.首先导入需要的所有的mavem依赖

①mysql-connect ②druid ③log4j ④mybtis-spring-boot-starter

```
        <dependency>
            <groupId>org.mybatis.spring.boot</groupId>
            <artifactId>mybatis-spring-boot-starter</artifactId>
            <version>2.1.1</version>
        </dependency>
        <dependency>
            <groupId>mysql</groupId>
            <artifactId>mysql-connector-java</artifactId>
            <version>8.0.22</version>
        </dependency>

        <dependency>
            <groupId>com.alibaba</groupId>
            <artifactId>druid</artifactId>
            <version>1.1.21</version>
        </dependency>
        <dependency>
            <groupId>log4j</groupId>
            <artifactId>log4j</artifactId>
            <version>1.2.17</version>
        </dependency>

```

2.编写配置文件application.properties或者application.yaml

3.编写guo文件下的pojo，controller，service，mapper文件夹参考前面的springboot整合mybatis代码哦！

整合完毕的文件目录：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424211622642.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

在mapper中添加了一个queryUserByName的方法：

整合完毕后先去测试类中进行测试：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424211637129.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

测试结果：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424211649264.png)

ok到目前为止整合完毕，没有问题，业务都是正常的接下来去之前的用户认证把之前写死的用户改为数据库中的用户

```
    @Override
    protected AuthenticationInfo doGetAuthenticationInfo(AuthenticationToken token) throws AuthenticationException {
        System.out.println("执行了认证方法");
        UsernamePasswordToken userToken = (UsernamePasswordToken)token;

        User user = userService.queryUserByName(userToken.getUsername());

        if(user==null){
            return null;
        }

        return new SimpleAuthenticationInfo("",user.getPwd(),"");
    }

```

测试一下bingo搞定

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)12.3.5授权功能的实现

去到ShiroConfig.java中,添加代码，注意要添加在（顺序）

```
 filterMap.put("/user/add","perms[user:add]");

```

之后我们执行I一下发现登陆后add标签也无权访问

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424211705200.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

当然正常的是要访问无权限页面的

接下来我们去UserRealm中给添加权限,注意不要导错类SimpleAuthorizationInfo

```
    @Override
    protected AuthorizationInfo doGetAuthorizationInfo(PrincipalCollection principalCollection) {
        System.out.println("执行了授权方法");

        SimpleAuthorizationInfo info = new SimpleAuthorizationInfo();

        info.addStringPermission("user:add");

        return info;
    }

```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424211723542.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

诶，接下来所有用户就都有这个权限了

但是不想让所有用户都有某个权限要怎么实现呢？

首先先去数据表中添加一个权限字段

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424211736528.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

紧接着去pojo中添加字段，再去手动添加一些用户的权限

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424211747957.png)

ok数据层完毕，接下来要思考，我们想要获取到用户的权限，但是获取用户是在刚刚认证中通过userservice获取的，  
在认证里面查到的东西我们怎么放到授权中去呢？

想到了两个：①session ②用户当前对象的属性来取get方法或（点属性）

我们在认证中，最后new了一个SimpleAuthenticationInfo的当前认证对象，之前里面要传递三个参数分别为：  
（资源，密码，realmName）

我们把获取到的user传入到资源中去。

```
return new SimpleAuthenticationInfo(user,user.getPwd(),"");

```

这样一来，user这个资源就传递到了当前用户subject整体资源中，通过当前subject获取资源来获取到这个user

所以在授权的功能中要先获取subject当前用户

```
Subject subject = SecurityUtils.getSubject();

```

然后通过subject获取到资源

```
User currentUser = (User) subject.getPrincipal();

```

再给当前用户添加user中对应的权限名,注意方法名是`addStringPermission`权限

```
 info.addStringPermission(currentUser.getPerms());

```

最后返回当前权限info

整体授权代码：

```
    //授权
    @Override
    protected AuthorizationInfo doGetAuthorizationInfo(PrincipalCollection principalCollection) {
        System.out.println("执行了授权方法");

        SimpleAuthorizationInfo info = new SimpleAuthorizationInfo();

        Subject subject = SecurityUtils.getSubject();

        User currentUser = (User) subject.getPrincipal();
        //设置当前用户的权限
        info.addStringPermission(currentUser.getPerms());

        return info;
    }

```

退出功能就和之前security的logout一样，设置一下退出的路径就可

好现在基本需求都完了，但是想和之前security一样实现没有权限的就不要显示，就需要和thymeleaf结合

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)12.3.6Shiro和thymeleaf整合

首先要导入shrio和thymeleaf结合的依赖

```
<!-- https://mvnrepository.com/artifact/com.github.theborakompanioni/thymeleaf-extras-shiro -->
<dependency>
    <groupId>com.github.theborakompanioni</groupId>
    <artifactId>thymeleaf-extras-shiro</artifactId>
    <version>2.0.0</version>
</dependency>

```

ok接下来就要去前端页面编写标签了，之前在security中用到的是sec，这里用的shiro，当然也要导入命名空间

下面是spring-security的命名空间

```
xmlns:sec="http://www.thymeleaf.org/thymeleaf-extras-springsecurity5"

```

shiro的：

```
xmlns:shiro="http://www.thymeleaf.org/thymeleaf-extras-shiro"

```

前端代码：

```
<p th:text="${msg}"></p>
<hr>
<a><a th:href="@{/toLogin}">登录</a>
<div shiro:hasPermission="user:add">
    <a th:href="@{/user/add}">add</a>
</div>
    
<div shiro:hasPermission="user:update">
<a th:href="@{/user/update}">update</a>
</div>

```

解释一下就是判断一下当前的用户是否有当前的权限，如果有则显示，没有不显示

登录按钮无权限时显示：

```
<div shiro:notAuthenticated>
    <a th:href="@{/toLogin}">登录</a>
</div>

```

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)13.Swagger
==============================================================================================================================================================================================================================================================================================================================================================================================================================================================

学习目标：

*   了解Swagger的概念及作用
*   掌握在项目中集成Swagger自动生成API文档

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)13.1Swagger简介
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**前后端分离**

*   前端 -> 前端控制层、视图层
*   后端 -> 后端控制层、服务层、数据访问层
*   前后端通过API进行交互
*   前后端相对独立，且松耦合

**产生的问题**

*   前后端集成，前端或者后端无法做到“及时协商，尽早解决”，最终导致问题集中爆发

**解决方案**

*   首先定义schema \[ 计划的提纲 \]，并实时跟踪最新的API，降低集成风险
*   早些年制定word计划文档
*   前后端分离：前端测试后端接口：postman  
    后端提供接口，需要实时更新最新的消息及改动！

**Swagger**

*   号称世界上最流行的API框架
*   Restful Api 文档在线自动生成器 => **API 文档 与API 定义同步更新**
*   直接运行，在线测试API接口（其实就是controller requsetmapping）
*   支持多种语言 （如：Java，PHP等）
*   官网：https://swagger.io/

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)13.2Springboot集成Swagger
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**SpringBoot集成Swagger** => **springfox**，两个jar包

*   **Springfox-swagger2**
*   swagger-springmvc

**使用Swagger**

要求：jdk 1.8 + 否则swagger2无法运行

步骤：

1、新建一个SpringBoot-web项目

2、添加Maven依赖

```
<!-- https://mvnrepository.com/artifact/io.springfox/springfox-swagger2 -->
<dependency>
   <groupId>io.springfox</groupId>
   <artifactId>springfox-swagger2</artifactId>
   <version>2.9.2</version>
</dependency>
<!-- https://mvnrepository.com/artifact/io.springfox/springfox-swagger-ui -->
<dependency>
   <groupId>io.springfox</groupId>
   <artifactId>springfox-swagger-ui</artifactId>
   <version>2.9.2</version>
</dependency>

```

3、编写HelloController，测试确保运行成功！

4、要使用Swagger，我们需要编写一个配置类-SwaggerConfig来配置 Swagger

```
@Configuration //配置类
@EnableSwagger2// 开启Swagger2的自动配置
public class SwaggerConfig {  
}

```

5、访问测试 ：http://localhost:8080/swagger-ui.html ，可以看到swagger的界面；

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424211828997.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)13.2.2配置Swagger

1、Swagger实例Bean是Docket，所以通过配置Docket实例来配置Swagger,通过Docket对象接管了原来默认的配置

```
@Bean //配置docket以配置Swagger具体参数
public Docket docket() {
   return new Docket(DocumentationType.SWAGGER_2);
}

```

2、可以通过apiInfo()属性配置文档信息

```
//配置文档信息
private ApiInfo apiInfo() {
   Contact contact = new Contact("联系人名字", "http://xxx.xxx.com/联系人访问链接", "联系人邮箱");
   return new ApiInfo(
           "Swagger学习", // 标题
           "学习演示如何配置Swagger", // 描述
           "v1.0", // 版本
           "http://terms.service.url/组织链接", // 组织链接
           contact, // 联系人信息
           "Apach 2.0 许可", // 许可
           "许可链接", // 许可连接
           new ArrayList<>()// 扩展
  );
}

```

3、Docket 实例关联上 apiInfo()

```
@Bean
public Docket docket() {
   return new Docket(DocumentationType.SWAGGER_2).apiInfo(apiInfo());
}

```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424212045965.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)13.2.3配置扫描接口

1、构建Docket时通过select()方法配置怎么扫描接口。

```
@Bean
public Docket docket() {
   return new Docket(DocumentationType.SWAGGER_2)
      .apiInfo(apiInfo())
      .select()// 通过.select()方法，去配置扫描接口,RequestHandlerSelectors配置如何扫描接口
      .apis(RequestHandlerSelectors.basePackage("com.guo.controller"))
      .build();
}

```

2、重启项目测试，由于我们配置根据包的路径扫描接口，所以我们只能看到一个类

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424211926790.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

3、除了通过包路径配置扫描接口外，还可以通过配置其他方式扫描接口，这里注释一下所有的配置方式：

```
any() // 扫描所有，项目中的所有接口都会被扫描到
none() // 不扫描接口
// 通过方法上的注解扫描，如withMethodAnnotation(GetMapping.class)只扫描get请求
withMethodAnnotation(final Class<? extends Annotation> annotation)
// 通过类上的注解扫描，如.withClassAnnotation(Controller.class)只扫描有controller注解的类中的接口
withClassAnnotation(final Class<? extends Annotation> annotation)
basePackage(final String basePackage) // 根据包路径扫描接口
paths(PathSelectors.ant("/guo/**"))  //过滤什么路径：过滤/guo下的所有路径

```

4、除此之外，我们还可以配置接口扫描过滤：

```
@Bean
public Docket docket() {
   return new Docket(DocumentationType.SWAGGER_2)
      .apiInfo(apiInfo())
      .select()// 通过.select()方法，去配置扫描接口,RequestHandlerSelectors配置如何扫描接口
      .apis(RequestHandlerSelectors.basePackage("com.kuang.swagger.controller"))
       // 配置如何通过path过滤,即这里只扫描请求以/kuang开头的接口
      .paths(PathSelectors.ant("/kuang/**"))
      .build();
}

```

5、这里的可选值有

```
any() // 任何请求都扫描
none() // 任何请求都不扫描
regex(final String pathRegex) // 通过正则表达式控制
ant(final String antPattern) // 通过ant()控制

```

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)13.2.4配置Swagger开关

可以指定相应的环境是否开启swagger功能

1、通过enable()方法配置是否启用swagger，如果是false，swagger将不能在浏览器中访问了

```
@Bean
public Docket docket() {
   return new Docket(DocumentationType.SWAGGER_2)
      .apiInfo(apiInfo())
      .enable(false) //配置是否启用Swagger，如果是false，在浏览器将无法访问
      .select()// 通过.select()方法，去配置扫描接口,RequestHandlerSelectors配置如何扫描接口
      .apis(RequestHandlerSelectors.basePackage("com.kuang.swagger.controller"))
       // 配置如何通过path过滤,即这里只扫描请求以/kuang开头的接口
      .paths(PathSelectors.ant("/kuang/**"))
      .build();
}

```

2、如何动态配置当项目处于test、dev环境时显示swagger，处于prod时不显示？

```
@Bean
public Docket docket(Environment environment) {
   // 设置要显示swagger的环境
   Profiles of = Profiles.of("dev", "test");
   // 判断当前是否处于该环境
   // 通过 enable() 接收此参数判断是否要显示
   boolean flag = environment.acceptsProfiles(of);
   
   return new Docket(DocumentationType.SWAGGER_2)
      .apiInfo(apiInfo())
      .enable(flag) //配置是否启用Swagger，如果是false，在浏览器将无法访问
      .select()// 通过.select()方法，去配置扫描接口,RequestHandlerSelectors配置如何扫描接口
      .apis(RequestHandlerSelectors.basePackage("com.kuang.swagger.controller"))
       // 配置如何通过path过滤,即这里只扫描请求以/kuang开头的接口
      .paths(PathSelectors.ant("/kuang/**"))
      .build();
}

```

3、可以在项目中增加一个dev的配置文件查看效果！

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)13.2.5配置API分组

1、如果没有配置分组，默认是default。通过groupName()方法即可配置分组：

```
@Bean
public Docket docket(Environment environment) {
   return new Docket(DocumentationType.SWAGGER_2).apiInfo(apiInfo())
      .groupName("hello") // 配置分组
       // 省略配置....
}

```

2、重启项目查看分组

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424211940302.png)

3、如何配置多个分组？配置多个分组只需要配置多个docket即可：

```
@Bean
public Docket docket1(){
   return new Docket(DocumentationType.SWAGGER_2).groupName("group1");
}
@Bean
public Docket docket2(){
   return new Docket(DocumentationType.SWAGGER_2).groupName("group2");
}
@Bean
public Docket docket3(){
   return new Docket(DocumentationType.SWAGGER_2).groupName("group3");
}

```

4、重启项目查看即可

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)13.2.6实体配置

1、新建一个实体类

```
@ApiModel("用户实体")
public class User {
   @ApiModelProperty("用户名")
   public String username;
   @ApiModelProperty("密码")
   public String password;
}

```

2、只要这个实体在**请求接口**的返回值上（即使是泛型），都能映射到实体项中：

```
@RequestMapping("/getUser")
public User getUser(){
   return new User();
}

```

3、重启查看测试

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424211953909.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

注：并不是因为@ApiModel这个注解让实体显示在这里了，而是只要出现在接口方法的返回值上的实体都会显示在这里，而@ApiModel和@ApiModelProperty这两个注解只是为实体添加注释的。

@ApiModel为类添加注释

@ApiModelProperty为类属性添加注释

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)13.3常用注解
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Swagger的所有注解定义在io.swagger.annotations包下

下面列一些经常用到的，未列举出来的可以另行查阅说明：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424212019807.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

我们也可以给请求的接口配置一些注释

```
@ApiOperation("这是一个接口")
@PostMapping("/guo")
@ResponseBody
public String guo(@ApiParam("这个名字会被返回")String username){
   return username;
}

```

这样的话，可以给一些比较难理解的属性或者接口，增加一些配置信息，让人更容易阅读！

相较于传统的Postman或Curl方式测试接口，使用swagger简直就是傻瓜式操作，不需要额外说明文档(写得好本身就是文档)而且更不容易出错，只需要录入数据然后点击Execute，如果再配合自动化框架，可以说基本就不需要人为操作了。

Swagger是个优秀的工具，现在国内已经有很多的中小型互联网公司都在使用它，相较于传统的要先出Word接口文档再测试的方式，显然这样也更符合现在的快速迭代开发行情。当然了，提醒下大家在正式环境要记得关闭Swagger，一来出于安全考虑二来也可以节省运行时内存。

最后我学会的：

①给swagger中添加注释  
②修改页面的标题等内容  
③简单的操作一些请求测试

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)14.任务
=========================================================================================================================================================================================================================================================================================================================================================================================================================================================

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)14.1异步任务
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

所谓异步，在某些功能实现时可能要花费一定的时间，但是为了不影响客户端的体验，选择异步执行

案例：

首先创建一个service：

```
@Service
public class AsyncService {

    public void hello(){
        try {
            Thread.sleep(3000);
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
        System.out.println("数据正在传输...");
    }
}

```

Controller:

```
@RestController
public class AsyncController {

    @Autowired
    AsyncService asyncService;

    @RequestMapping("/async")
    public String async(){
        asyncService.hello();
        return "ok";
    }
}

```

这样在执行/async请求时，网站会延时三秒再显示ok，后台数据也会三秒后显示数据正在传输

![在这里插入图片描述](https://img-blog.csdnimg.cn/2021042421210855.png)

现在想要做到前端快速响应我们的页面，后台去慢慢的传输数据，就要用到springboot自带的功

①想办法告诉spring我们的异步方法是异步的，所以要在方法上添加注解

```
    @Async
    public void hello(){
        try {
            Thread.sleep(3000);
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
        System.out.println("数据正在传输...");
    }

```

②去springboot主程序中开启异步注解功能

```
@EnableAsync
@SpringBootApplication
public class SwaggerDemoApplication {

    public static void main(String[] args) {
        SpringApplication.run(SwaggerDemoApplication.class, args);
    }

}

```

重启即可

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)14.2邮件任务
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

邮件发送，在我们的日常开发中，也非常的多，Springboot也帮我们做了支持

*   邮件发送需要引入spring-boot-start-mail
*   SpringBoot 自动配置MailSenderAutoConfiguration
*   定义MailProperties内容，配置在application.yml中
*   自动装配JavaMailSender
*   测试邮件发送

**测试：**

1、引入pom依赖

```
<dependency>
   <groupId>org.springframework.boot</groupId>
   <artifactId>spring-boot-starter-mail</artifactId>
</dependency>

```

看它引入的依赖，可以看到 jakarta.mail

```
<dependency>
   <groupId>com.sun.mail</groupId>
   <artifactId>jakarta.mail</artifactId>
   <version>1.6.4</version>
   <scope>compile</scope>
</dependency>

```

2、查看自动配置类：MailSenderAutoConfiguration

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424212120552.png)

ok我们点进去，看到里面存在bean，JavaMailSenderImpl  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424212130395.png)

然后我们去看下配置文件

```
@ConfigurationProperties(
   prefix = "spring.mail"
)
public class MailProperties {
   private static final Charset DEFAULT_CHARSET;
   private String host;
   private Integer port;
   private String username;
   private String password;
   private String protocol = "smtp";
   private Charset defaultEncoding;
   private Map<String, String> properties;
   private String jndiName;
}

```

3、配置文件：

```
spring.mail.username=你的邮箱
spring.mail.password=你的邮箱授权码
spring.mail.host=smtp.163.com
# qq需要配置ssl，其他邮箱不需要
spring.mail.properties.mail.smtp.ssl.enable=true

```

首先你需要去邮箱网站开启POP3/SMTP

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424212144863.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

4、Spring单元测试

```
@SpringBootTest
class SwaggerDemoApplicationTests {

    @Autowired
    JavaMailSenderImpl mailSender;

    @Test
    public void contextLoads() {
        //邮件设置1：一个简单的邮件
        SimpleMailMessage message = new SimpleMailMessage();
        message.setSubject("这是一个测试邮件发送标题");
        message.setText("这是一个测试邮件发送内容");

        message.setTo("15235771906@163.com");
        message.setFrom("15235771906@163.com");
        mailSender.send(message);
    }
    
}

```

发送一个较为复杂的邮件：

```
@Test
public void contextLoads2() throws MessagingException {
   //邮件设置2：一个复杂的邮件
   MimeMessage mimeMessage = mailSender.createMimeMessage();
   MimeMessageHelper helper = new MimeMessageHelper(mimeMessage, true);

   helper.setSubject("通知-明天来狂神这听课");
   helper.setText("<b style='color:red'>今天 7:30来开会</b>",true);

   //发送附件
   helper.addAttachment("1.jpg",new File("绝对路径地址"));
   helper.addAttachment("2.jpg",new File(""));

   helper.setTo("15235771906@163.com");
   helper.setFrom("15235771906@163.com");

   mailSender.send(mimeMessage);
}

```

查看邮箱，邮件接收成功！

我们只需要使用Thymeleaf进行前后端结合即可开发自己网站邮件收发功能了！

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)14.3定时任务
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

项目开发中经常需要执行一些定时任务，比如需要在每天凌晨的时候，分析一次前一天的日志信息，Spring为我们提供了异步执行任务调度的方式，提供了两个接口。

*   TaskExecutor接口
*   TaskScheduler接口

两个注解：

*   @EnableScheduling
*   @Scheduled

**cron表达式：**

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424212210550.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

**测试步骤：**

1、创建一个ScheduledService

我们里面存在一个hello方法，他需要定时执行，怎么处理呢？

```
@Service
public class ScheduledService {
   
   //秒   分   时     日   月   周几
   //0 * * * * MON-FRI
   //注意cron表达式的用法；
   @Scheduled(cron = "0 * * * * 0-7")
   public void hello(){
       System.out.println("hello.....");
  }
}

```

2、这里写完定时任务之后，我们需要在主程序上增加@EnableScheduling 开启定时任务功能

```
@EnableAsync //开启异步注解功能
@EnableScheduling //开启基于注解的定时任务
@SpringBootApplication
public class SpringbootTaskApplication {

   public static void main(String[] args) {
       SpringApplication.run(SpringbootTaskApplication.class, args);
  }

}

```

3、我们来详细了解下cron表达式；

http://www.bejson.com/othertools/cron/4、常用的表达式

4.常用表达式

```
（1）0/2 * * * * ?   表示每2秒 执行任务
（1）0 0/2 * * * ?   表示每2分钟 执行任务
（1）0 0 2 1 * ?   表示在每月的1日的凌晨2点调整任务
（2）0 15 10 ? * MON-FRI   表示周一到周五每天上午10:15执行作业
（3）0 15 10 ? 6L 2002-2006   表示2002-2006年的每个月的最后一个星期五上午10:15执行作
（4）0 0 10,14,16 * * ?   每天上午10点，下午2点，4点
（5）0 0/30 9-17 * * ?   朝九晚五工作时间内每半小时
（6）0 0 12 ? * WED   表示每个星期三中午12点
（7）0 0 12 * * ?   每天中午12点触发
（8）0 15 10 ? * *   每天上午10:15触发
（9）0 15 10 * * ?     每天上午10:15触发
（10）0 15 10 * * ?   每天上午10:15触发
（11）0 15 10 * * ? 2005   2005年的每天上午10:15触发
（12）0 * 14 * * ?     在每天下午2点到下午2:59期间的每1分钟触发
（13）0 0/5 14 * * ?   在每天下午2点到下午2:55期间的每5分钟触发
（14）0 0/5 14,18 * * ?     在每天下午2点到2:55期间和下午6点到6:55期间的每5分钟触发
（15）0 0-5 14 * * ?   在每天下午2点到下午2:05期间的每1分钟触发
（16）0 10,44 14 ? 3 WED   每年三月的星期三的下午2:10和2:44触发
（17）0 15 10 ? * MON-FRI   周一至周五的上午10:15触发
（18）0 15 10 15 * ?   每月15日上午10:15触发
（19）0 15 10 L * ?   每月最后一日的上午10:15触发
（20）0 15 10 ? * 6L   每月的最后一个星期五上午10:15触发
（21）0 15 10 ? * 6L 2002-2005   2002年至2005年的每月的最后一个星期五上午10:15触发
（22）0 15 10 ? * 6#3   每月的第三个星期五上午10:15触发

```

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)15.Dubbo和Zookeeper集成
========================================================================================================================================================================================================================================================================================================================================================================================================================================================================

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)15.1分布式理论
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

​ 在《分布式系统原理与范型》一书中有如下定义：“分布式系统是若干独立计算机的集合，这些计算机对于用户来说就像单个相关系统”；

​ 分布式系统是由一组通过网络进行通信、为了完成共同的任务而协调工作的计算机节点组成的系统。分布式系统的出现是为了用廉价的、普通的机器完成单个计算机无法完成的计算、存储任务。其目的是**利用更多的机器，处理更多的数据**。

​ 分布式系统（distributed system）是建立在网络之上的软件系统。

​ 首先需要明确的是，只有当单个节点的处理能力无法满足日益增长的计算、存储任务的时候，且硬件的提升（加内存、加磁盘、使用更好的CPU）高昂到得不偿失的时候，应用程序也不能进一步优化的时候，我们才需要考虑分布式系统。（所以分布式不应该在一开始设计系统时就考虑到）因为，分布式系统要解决的问题本身就是和单机系统一样的，而由于分布式系统多节点、通过网络通信的拓扑结构，会引入很多单机系统没有的问题，为了解决这些问题又会引入更多的机制、协议，带来更多的问题。。。

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)15.1.1Dubbo文档

随着互联网的发展，网站应用的规模不断扩大，常规的垂直应用架构已无法应对，分布式服务架构以及流动计算架构势在必行，急需**一个治理系统**确保架构有条不紊的演进。

在Dubbo的官网文档有这样一张图

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424212225416.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

单一应用架构

当网站流量很小时，只需一个应用，将所有功能都部署在一起，以减少部署节点和成本。此时，用于简化增删改查工作量的数据访问框架(ORM)是关键。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424212244443.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

适用于小型网站，小型管理系统，将所有功能都部署到一个功能里，简单易用。

**缺点：**

1、性能扩展比较难

2、协同开发问题

3、不利于升级维护

垂直应用架构

当访问量逐渐增大，单一应用增加机器带来的加速度越来越小，将应用拆成互不相干的几个应用，以提升效率。此时，用于加速前端页面开发的Web框架(MVC)是关键。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424212259122.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

通过切分业务来实现各个模块独立部署，降低了维护和部署的难度，团队各司其职更易管理，性能扩展也更方便，更有针对性。

缺点：公用模块无法重复利用，开发性的浪费

分布式服务架构

当垂直应用越来越多，应用之间交互不可避免，将核心业务抽取出来，作为独立的服务，逐渐形成稳定的服务中心，使前端应用能更快速的响应多变的市场需求。此时，用于提高业务复用及整合的\*\*分布式服务框架(RPC)\*\*是关键。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424212314908.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

流动计算架构

当服务越来越多，容量的评估，小服务资源的浪费等问题逐渐显现，此时需增加一个调度中心基于访问压力实时管理集群容量，提高集群利用率。此时，用于**提高机器利用率的资源调度和治理中心**(SOA)\[ Service Oriented Architecture\]是关键。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424212333221.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

15.2什么是RPC

RPC【Remote Procedure Call】是指远程过程调用，是一种进程间通信方式，他是一种技术的思想，而不是规范。它允许程序调用另一个地址空间（通常是共享网络的另一台机器上）的过程或函数，而不用程序员显式编码这个远程调用的细节。即程序员无论是调用本地的还是远程的函数，本质上编写的调用代码基本相同。

也就是说两台服务器A，B，一个应用部署在A服务器上，想要调用B服务器上应用提供的函数/方法，由于不在一个内存空间，不能直接调用，需要通过网络来表达调用的语义和传达调用的数据。为什么要用RPC呢？就是无法在一个进程内，甚至一个计算机内通过本地调用的方式完成的需求，比如不同的系统间的通讯，甚至不同的组织间的通讯，由于计算能力需要横向扩展，需要在多台机器组成的集群上部署应用。RPC就是要像调用本地的函数一样去调远程函数；

推荐阅读文章：https://www.jianshu.com/p/2accc2840a1b

说白了就是不同于调用本地的而是调用远程资源和方法

RPC原理：  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424212344708.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

步骤分析：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210425114820761.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

RPC两个核心模块：通讯，序列化。

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)15.2Dubbo的概念和介绍
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)15.2.1Dubbo是什么

Dubbo是一个分布式服务框架，致力于提供高性能和透明化的RPC远程服务调用方案，以及SOA服务治理方案。简单的说，dubbo就是个服务框架，如果没有分布式的需求，其实是不需要用的，只有在分布式的时候，才有dubbo这样的分布式服务框架的需求，并且本质上是个服务调用的东东，说白了就是个远程服务调用的分布式框架

其核心部分包含:  
1》远程通讯: 提供对多种基于长连接的NIO框架抽象封装，包括多种线程模型，序列化，以及“请求-响应”模式的信息交换方式。  
2》集群容错: 提供基于接口方法的透明远程过程调用，包括多协议支持，以及软负载均衡，失败容错，地址路由，动态配置等集群支持。  
3》自动发现: 基于注册中心目录服务，使服务消费方能动态的查找服务提供方，使地址透明，使服务提供方可以平滑增加或减少机器。

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)15.2.2 Dubbo能做什么

1.透明化的远程方法调用，就像调用本地方法一样调用远程方法，只需简单配置，没有任何API侵入。  
2.软负载均衡及容错机制，可在内网替代F5等硬件负载均衡器，降低成本，减少单点。  
3.服务自动注册与发现，不再需要写死服务提供方地址，注册中心基于接口名查询服务提供者的IP地址，并且能够平滑添加或删除服务提供者。

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)15.3搭建测试环境
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Apache Dubbo |ˈdʌbəʊ| 是一款高性能、轻量级的开源Java RPC框架，它提供了三大核心能力：面向接口的远程方法调用，智能容错和负载均衡，以及服务自动注册和发现。

dubbo官网 http://dubbo.apache.org/zh-cn/index.html

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210425115309769.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

**服务提供者**（Provider）：暴露服务的服务提供方，服务提供者在启动时，向注册中心注册自己提供的服务。

**服务消费者**（Consumer）：调用远程服务的服务消费方，服务消费者在启动时，向注册中心订阅自己所需的服务，服务消费者，从提供者地址列表中，基于软负载均衡算法，选一台提供者进行调用，如果调用失败，再选另一台调用。

**注册中心**（Registry）：注册中心返回服务提供者地址列表给消费者，如果有变更，注册中心将基于长连接推送变更数据给消费者

**监控中心**（Monitor）：服务消费者和提供者，在内存中累计调用次数和调用时间，定时每分钟发送一次统计数据到监控中心

**调用关系说明**

l 服务容器负责启动，加载，运行服务提供者。

l 服务提供者在启动时，向注册中心注册自己提供的服务。

l 服务消费者在启动时，向注册中心订阅自己所需的服务。

l 注册中心返回服务提供者地址列表给消费者，如果有变更，注册中心将基于长连接推送变更数据给消费者。

l 服务消费者，从提供者地址列表中，基于软负载均衡算法，选一台提供者进行调用，如果调用失败，再选另一台调用。

l 服务消费者和提供者，在内存中累计调用次数和调用时间，定时每分钟发送一次统计数据到监控中心

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)15.3.1Zookeeper介绍

**Zoookeeper是什么？**

官方文档上这么解释zookeeper，它是一个分布式服务框架，是Apache Hadoop 的一个子项目，它主要是用来解决分布式应用中经常遇到的一些数据管理问题，如：统一命名服务、状态同步服务、集群管理、分布式应用配置项的管理等。

上面的解释有点抽象，简单来说zookeeper=**文件系统**+**监听通知机制**。  
①.文件系统  
Zookeeper维护一个类似文件系统的数据结构  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210425113344540.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)  
每个子目录项如 NameService 都被称作为 znode(目录节点)，和文件系统一样，我们能够自由的增加、删除znode，在一个znode下增加、删除子znode，唯一的不同在于znode是可以存储数据的。  
有四种类型的znode：

*   PERSISTENT-持久化目录节点  
    客户端与zookeeper断开连接后，该节点依旧存在
    
*   PERSISTENT\_SEQUENTIAL-持久化顺序编号目录节点  
    客户端与zookeeper断开连接后，该节点依旧存在，只是Zookeeper给该节点名称进行顺序编号
    
*   EPHEMERAL-临时目录节点  
    \-客户端与zookeeper断开连接后，该节点被删除
    
*   EPHEMERAL\_SEQUENTIAL-临时顺序编号目录节点  
    客户端与zookeeper断开连接后，该节点被删除，只是Zookeeper给该节点名称进行顺序编号
    

2、 监听通知机制  
客户端注册监听它关心的目录节点，当目录节点发生变化（数据改变、被删除、子目录节点增加删除）时，zookeeper会通知客户端。

就这么简单，下面我们看看Zookeeper能做点什么呢？

Zookeeper能做什么  
zookeeper功能非常强大，可以实现诸如分布式应用配置管理、统一命名服务、状态同步服务、集群管理等功能，我们这里拿比较简单的分布式应用配置管理为例来说明。

假设我们的程序是分布式部署在多台机器上，如果我们要改变程序的配置文件，需要逐台机器去修改，非常麻烦，现在把这些配置全部放到zookeeper上去，保存在 zookeeper 的某个目录节点中，然后所有相关应用程序对这个目录节点进行监听，一旦配置信息发生变化，每个应用程序就会收到 zookeeper 的通知，然后从 zookeeper 获取新的配置信息应用到系统中。  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210425114104517.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)  
如上，你大致应该了解zookeeper是个什么东西，大概能做些什么了，我们马上来学习下zookeeper的安装及使用

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)15.3.2windows下安装zookeeper

1、下载zookeeper ：地址， 我们下载3.4.14 ， 最新版！解压zookeeper

2、运行/bin/zkServer.cmd ，初次运行会报错，没有zoo.cfg配置文件；

安装包地址：链接：https://pan.baidu.com/s/1\_iRikIPD7J115f8r8uTLKg 提取码：xd91

可能遇到问题：闪退 !

解决方案：编辑zkServer.cmd文件末尾添加pause 。这样运行出错就不会退出，会提示错误信息，方便找到原因。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424212426186.png)

3、修改zoo.cfg配置文件

将conf文件夹下面的zoo\_sample.cfg复制一份改名为zoo.cfg即可。

注意几个重要位置：

dataDir=./ 临时数据存储的目录（可写相对路径）

clientPort=2181 zookeeper的端口号

修改完成后再次启动zookeeper

4、使用zkCli.cmd测试

ls /：列出zookeeper根下保存的所有节点

```
[zk: 127.0.0.1:2181(CONNECTED) 4] ls /
[zookeeper]

```

create –e /guo123：创建一个guo节点，值为123

我们再来查看一下节点

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)15.3.2window下安装dubbo-admin

dubbo本身并不是一个服务软件。它其实就是一个jar包，能够帮你的java程序连接到zookeeper，并利用zookeeper消费、提供服务。

但是为了让用户更好的管理监控众多的dubbo服务，官方提供了一个可视化的监控程序dubbo-admin，不过这个监控即使不装也不影响使用。

我们这里来安装一下：

**1、下载dubbo-admin**

地址 ：https://github.com/apache/dubbo-admin/tree/master

**2、解压进入目录**

修改 dubbo-admin\\src\\main\\resources \\application.properties 指定zookeeper地址

```
server.port=7001
spring.velocity.cache=false
spring.velocity.charset=UTF-8
spring.velocity.layout-url=/templates/default.vm
spring.messages.fallback-to-system-locale=false
spring.messages.basename=i18n/message
spring.root.password=root
spring.guest.password=guest

dubbo.registry.address=zookeeper://127.0.0.1:2181

```

**3、在项目目录下**打包dubbo-admin

```
mvn clean package -Dmaven.test.skip=true

```

**第一次打包的过程有点慢，需要耐心等待！直到成功！**

4、执行 dubbo-admin\\target 下的dubbo-admin-0.0.1-SNAPSHOT.jar

```
java -jar dubbo-admin-0.0.1-SNAPSHOT.jar

```

【注意：zookeeper的服务一定要打开！】

执行完毕，我们去访问一下 http://localhost:7001/ ， 这时候我们需要输入登录账户和密码，我们都是默认的root-root；

登录成功后，查看界面

[](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)15.4SpringBoot + Dubbo + zookeeper
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)15.4.1框架搭建

**1\. 启动zookeeper ！**

**2\. IDEA创建一个空项目；**

**3.创建一个模块，实现服务提供者：provider-server ， 选择web依赖即可**

**4.项目创建完毕，我们写一个服务，比如卖票的服务；**

编写接口

```
package com.guo.provider.service;

public interface TicketService {
   public String getTicket();
}

```

编写实现类

```
package com.guo.provider.service;

public class TicketServiceImpl implements TicketService {
   @Override
   public String getTicket() {
       return "《狂神说Java》";
  }
}

```

**5.创建一个模块，实现服务消费者：consumer-server ， 选择web依赖即可**

**6.项目创建完毕，我们写一个服务，比如用户的服务；**

编写service

```
package com.guo.consumer.service;

public class UserService {
   //我们需要去拿去注册中心的服务
}

```

**需求：现在我们的用户想使用买票的服务，这要怎么弄呢 ？**

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)15.4.2服务提供者

1、将服务提供者注册到注册中心，我们需要整合Dubbo和zookeeper，所以需要导包

我们从dubbo官网进入github，看下方的帮助文档，找到dubbo-springboot，找到依赖包

```
<!-- Dubbo Spring Boot Starter -->
<dependency>
   <groupId>org.apache.dubbo</groupId>
   <artifactId>dubbo-spring-boot-starter</artifactId>
   <version>2.7.3</version>
</dependency>

```

zookeeper的包我们去maven仓库下载，zkclient；

```
<!-- https://mvnrepository.com/artifact/com.github.sgroschupf/zkclient -->
<dependency>
   <groupId>com.github.sgroschupf</groupId>
   <artifactId>zkclient</artifactId>
   <version>0.1</version>
</dependency>

```

【新版的坑】zookeeper及其依赖包，解决日志冲突，还需要剔除日志依赖；

```
<!-- 引入zookeeper -->
<dependency>
   <groupId>org.apache.curator</groupId>
   <artifactId>curator-framework</artifactId>
   <version>2.12.0</version>
</dependency>
<dependency>
   <groupId>org.apache.curator</groupId>
   <artifactId>curator-recipes</artifactId>
   <version>2.12.0</version>
</dependency>
<dependency>
   <groupId>org.apache.zookeeper</groupId>
   <artifactId>zookeeper</artifactId>
   <version>3.4.14</version>
   <!--排除这个slf4j-log4j12-->
   <exclusions>
       <exclusion>
           <groupId>org.slf4j</groupId>
           <artifactId>slf4j-log4j12</artifactId>
       </exclusion>
   </exclusions>
</dependency>

```

2、在springboot配置文件中配置dubbo相关属性！

```
#当前应用名字
dubbo.application.name=provider-server
#注册中心地址
dubbo.registry.address=zookeeper://127.0.0.1:2181
#扫描指定包下服务
dubbo.scan.base-packages=com.guo.provider.service

```

3、在service的实现类中配置服务注解，发布服务！注意导包问题,因为这里的Service注解需要导入的是dubbo中的注解，而不是spring的注解,所以要把其注入就要用Componet，不过最新版本的好像已经解决这个问题：一个新的注解@DubboService

```
import org.apache.dubbo.config.annotation.Service;
import org.springframework.stereotype.Component;

@Service //将服务发布出去
@Component //放在容器中
public class TicketServiceImpl implements TicketService {
   @Override
   public String getTicket() {
       return "《狂神说Java》";
  }
}

```

逻辑理解 ：应用启动起来，dubbo就会扫描指定的包下带有@component注解的服务，将它发布在指定的注册中心中！

### [](https://blog.csdn.net/qq_41978509/article/details/116104434?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165137280416782391848681%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165137280416782391848681&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-116104434.142^v9^control,157^v4^control&utm_term=spring+boot%E7%AC%94%E8%AE%B0&spm=1018.2226.3001.4187)15.4.3服务消费者

1.导入依赖，和之前的依赖一样；

```
<!--dubbo-->
<!-- Dubbo Spring Boot Starter -->
<dependency>
   <groupId>org.apache.dubbo</groupId>
   <artifactId>dubbo-spring-boot-starter</artifactId>
   <version>2.7.3</version>
</dependency>
<!--zookeeper-->
<!-- https://mvnrepository.com/artifact/com.github.sgroschupf/zkclient -->
<dependency>
   <groupId>com.github.sgroschupf</groupId>
   <artifactId>zkclient</artifactId>
   <version>0.1</version>
</dependency>
<!-- 引入zookeeper -->
<dependency>
   <groupId>org.apache.curator</groupId>
   <artifactId>curator-framework</artifactId>
   <version>2.12.0</version>
</dependency>
<dependency>
   <groupId>org.apache.curator</groupId>
   <artifactId>curator-recipes</artifactId>
   <version>2.12.0</version>
</dependency>
<dependency>
   <groupId>org.apache.zookeeper</groupId>
   <artifactId>zookeeper</artifactId>
   <version>3.4.14</version>
   <!--排除这个slf4j-log4j12-->
   <exclusions>
       <exclusion>
           <groupId>org.slf4j</groupId>
           <artifactId>slf4j-log4j12</artifactId>
       </exclusion>
   </exclusions>
</dependency>

```

2.配置参数

```
#当前应用名字
dubbo.application.name=consumer-server
#注册中心地址
dubbo.registry.address=zookeeper://127.0.0.1:2181

```

3.本来正常步骤是需要将服务提供者的接口打包，然后用pom文件导入，我们这里使用简单的方式，直接将服务的接口拿过来，路径必须保证正确，即和服务提供者相同；

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210424212446340.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxOTc4NTA5,size_16,color_FFFFFF,t_70)

4.  完善消费者的服务类
    
    ```
    package com.guo.consumer.service;
    
    import com.guo.provider.service.TicketService;
    import org.apache.dubbo.config.annotation.Reference;
    import org.springframework.stereotype.Service;
    
    @Service //注入到容器中
    public class UserService {
    
       @Reference //远程引用指定的服务，他会按照全类名进行匹配，看谁给注册中心注册了这个全类名
       TicketService ticketService;
    
       public void buyTicket(){
           String ticket = ticketService.getTicket();
           System.out.println("在注册中心买到"+ticket);
      }
    
    }
    
    ```
    

5.测试类编写

```
@RunWith(SpringRunner.class)
@SpringBootTest
public class ConsumerServerApplicationTests {

   @Autowired
   UserService userService;

   @Test
   public void contextLoads() {

       userService.bugTicket();

  }

}

```

微服务架构问题：

分布式架构会遇到的四个核心问题：

1.这么多的服务，客户端该如何去访问？  
2.这么多的服务，服务器之间如何进行通信？  
3.这么多的服务，该如何管理和治理？  
4.服务挂了，怎么办？

解决方案：

SpringCloud，是一套生态，就是来解决以上分布式架构的四个问题

想使用SpringCloud，必须要掌握Springboot，因为它是基于SpirngBoot的

1.SpringCloud NetFlix，出了一套解决方案

2.Apcahe Dubbo zookeeper 第二套解决方案

API：没有，要么找第三方，要么自己实现

Dubbo是一个高性能的基于java实现的RPC通信框架

服务注册与发现，zookeeper，没有熔断机制，接住了Hystrix

3.SpringCloud Alibaba 一站式解决方案！

 

[

![](https://img-blog.csdnimg.cn/fce44ffe4f1f493b84f6e057060c9c93.png)

创作打卡挑战赛 ![](https://csdnimg.cn/release/blogv2/dist/components/img/iconArrowLeftWhite.png)

赢取流量/现金/CSDN周边激励大奖



](https://mp.csdn.net/clock?utm_campaign=marketingcard&utm_source=qq_41978509&utm_content=116104434)

