
# 简介

[![Build Status](https://travis-ci.org/dyc87112/spring-cloud-config-admin.svg?branch=1.2.x)](https://travis-ci.org/dyc87112/spring-cloud-config-admin)
[![Release Version](https://img.shields.io/github/release/dyc87112/spring-cloud-config-admin.svg)](https://github.com/dyc87112/spring-cloud-config-admin/releases)
[![Maven Central](https://img.shields.io/maven-central/v/com.didispace/spring-cloud-config-admin.svg)](https://mvnrepository.com/artifact/com.didispace/spring-cloud-config-admin)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

在Spring Cloud的微服务架构方案中虽然提供了Spring Cloud Config来担任配置中心的角色，但是该项目的功能在配置的管理层面还是非常欠缺的。初期我们可以依赖选取的配置存储系统（比如：Gitlab、Github）给我们提供的配置管理界面来操作所有的配置信息，但是这样的管理还是非常粗粒度的，因此这个项目的目的就是解决这个问题，通过此项目，我们将提供一套基于Spring Cloud Config配置中心的可视化管理系统。

在该项目中，我们对于服务治理、配置存储、可视化操作都做了抽象，只要目的就是为了尽可能的兼容所有Spring Cloud Config的用户。任何Spring Cloud Config仅需要通过一些简单的配置，或者迁移工具就能将原来正在使用的配置中心统一的管理起来。

# 架构概览

本项目采用了前后端分离的架构，通过core模块抽象了前端需要的操作，再通过persistence和discovery模块隔离不同的配置仓库和不同的服务注册中心，从而达到前端程序不需要关心到底使用了什么存储配置以及使用了什么注册中心，这样用户可以根据自己的需要自由的组合不同的配置存储和服务治理机制，尽可能的匹配大部分Spring Cloud用户的需求。

![](https://github.com/dyc87112/spring-cloud-config-admin-doc/raw/master/statics/images/scca-arch-v1.1.x.png)

# 版本说明

各版本[Release Notes](https://dyc87112.github.io/spring-cloud-config-admin/release_notes.html)

## 1.2.0-SNAPSHOT

**欢迎提交ISSUE提出您的想法，我们会综合考虑纳入该版本的开发清单中！**

[使用文档v1.2.0](https://dyc87112.github.io/spring-cloud-config-admin-doc/1.2.0)

## 1.1.0-RELEASE

- 架构调整
  - 增加配置中心的plugin模块，对外提供存储的更多控制能力
  - DB存储的配置中心不需要与管理端的DB用同一个数据库了，可以独立部署
- 增加用户管理、用户登录功能
- Git存储优化：yaml和properties同时支持
- 支持配置中心增加用户名/密码访问控制的优化

[使用文档v1.1.0](https://dyc87112.github.io/spring-cloud-config-admin-doc/1.1.0)

## 1.0.0-RELEASE

- 灵活易用的配置管理界面
- 具备对Spring Cloud Config基本元素以及为方便管理增加的管理元素的维护功能，包括：多环境管理、环境特有参数的维护、加密参数维护、项目维护、配置的多版本等
- 便捷常用操作，包括：加密解密功能、批量替换环境参数、批量加密等
- 支持多种配置编辑模式：列表格式、YAML格式、PROPERTIES格式
- 适配目前已经在使用Spring Cloud Config的用户（支持DB和Git存储）
- 模块可分离部署，支持多种不同场景的用户使用
- 兼容所有Spring Cloud支持的服务发现机制

[使用文档v1.0.0](https://dyc87112.github.io/spring-cloud-config-admin-doc/1.0.0)