---
title: how-to-fix-This-application-has-no-explicit-mapping-error
tags: [springboot, debug]
date: 2023-03-17 10:34:50
updated: 2023-03-17 10:34:50
categories: 
- debug
- springboot
---

报错完整信息:This application has no explicit mapping for /error, so you are seeing this as a fallback

<!--more-->

翻阅了网上众多资料，主要有一下几种解决的方向：

## 方向1:包的位置可能错误

Application启动类的位置不对.要将Application类放在最外侧,即包含所有子包

原因:spring-boot会自动加载启动类所在包下及其子包下的所有组件.

## 方向2: springboot配置文件有误

在springboot的配置文件:application.yml或application.properties中关于视图解析器的配置问题:

当pom文件下的spring-boot-starter-paren版本高时使用:

spring.mvc.view.prefix/spring.mvc.view.suffix

当pom文件下的spring-boot-starter-paren版本低时使用:

spring.view.prefix/spring.view.suffix

## 方向3: 映射路径有误

控制器的URL路径书写问题

@RequestMapping(“xxxxxxxxxxxxxx”)

实际访问的路径与”xxx”不符合.

然而作为刚接触SpringBoot的我一开始犯错的时候是在第四层

## 方向4: 扫包出现错误

你把你Controller类的@Controller给补上

## 方向5: nginx是否打开并检查端口

当使用nginx代理静态资源时，需要检查是否运行nginx，并注意端口不能冲突

