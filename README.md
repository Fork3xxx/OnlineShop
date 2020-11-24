# OnlineShop

## 在线商城网站设计实现（Springboot案例）

[![](https://img.shields.io/badge/IDE-IntelliJ%20IDEA-000000?style=flat-square&logo=IntelliJ-IDEA&logoColor=ffffff)](https://www.jetbrains.com/idea/) ![](https://img.shields.io/badge/-Java-007396?style=flat-square&logo=java&logoColor=white)

## memo

![Hi😀](https://gitee.com/Rawteaz/Ash/raw/master/img/20201115110438.gif)  

---
#### 一、 项目概况

多模块项目

使用技术： SSM spring + springmvc + mybatis + maven

jquery bootstrap js 文件服务器

zshop_parent pom模块

zshop_common java模块

zshop_pojo       java模块

zshop_dao        java模块

zshop_service    java模块

zshop_front_web 前端web模块

zshop_backend_web 后端web模块

---

#### 二、项目搭建

##### 1. 项目初始化

* Encoding -UTF-8

* maven 

  > * 解压 maven 3.2.5
  > * 配置环境变量
  >   * M2_HOME
  >   * PATH
  > * setting.xml
  >   * 修改repository地址
  >   * 添加镜像mirror
  >   * jdk版本 1.8

  * importing : auto
  * maven home directory : maven3.2.5
  * user setting file : .xml

* jdk

---

##### 2. zshop_parent pom模块

* 新建maven 模块

  命名：所在组织单位名称__项目名称

  ​         模块名称 zshop_parent

* 修改pom.xml文件
  * dependecy添加所需依赖
  * build plugin : tomcat
* 在maven project界面可以看到

---

##### 3. zshop_common java模块

