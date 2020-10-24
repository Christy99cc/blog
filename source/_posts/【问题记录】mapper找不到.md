---
title: 【问题】A component required a bean of type 'com.cs.actionmall.mapper.UserMapper' that could not be found.
date: 2020-10-24T15:20:00Z
tags:
- SpringBoot
- 问题记录
categories: ''
---

> 记录专业实践使用SpringBoot后端开发遇到的问题

报错显示

```
Description:

A component required a bean of type 'com.cs.actionmall.mapper.UserMapper' that could not be found.


Action:

Consider defining a bean of type 'com.cs.actionmall.mapper.UserMapper' in your configuration.


Process finished with exit code 1
```



首先检查，@Mapper注解

```java
@Mapper
public interface UserMapper {
  ...
}
```



考虑缺少依赖，发现pom.xml文件中没有写如下部分

```xml
<dependency>
            <groupId>org.mybatis.spring.boot</groupId>
            <artifactId>mybatis-spring-boot-starter</artifactId>
            <version>2.1.1</version>
</dependency>
```

用的是mybatis不是mybatisplus，要用mybatis的依赖而不是mybatisplus的依赖