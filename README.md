# OnlineShop

## 在线商城网站设计实现（Springboot案例）

[![](https://img.shields.io/badge/IDE-IntelliJ%20IDEA-000000?style=flat-square&logo=IntelliJ-IDEA&logoColor=ffffff)](https://www.jetbrains.com/idea/) ![](https://img.shields.io/badge/-Java-007396?style=flat-square&logo=java&logoColor=white)

## memo

![Hi😀](https://gitee.com/Rawteaz/Ash/raw/master/img/20201115110438.gif)  

---
### 一、 项目概况

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

### 二、项目搭建

#### （一） 构建项目模块

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

> Module: maven-archetype-quickstart

* 新建maven 模块

  命名：所在组织单位名称__项目名称

  ​         模块名称 zshop_parent

* 修改pom.xml文件
  * dependecy添加所需依赖
  * build plugin : tomcat
* 在maven project界面可以看到

---

##### 3. zshop_common java模块

> Module: maven-archetype-quickstart

* 配置pom.xml文件
  * 继承了parent模块
  * 引用父模块的spring核心依赖（引用不需要版本号）

---

##### 4. zshop_pojo java模块

> Module: maven-archetype-quickstart

* 配置pom.xml文件
  * 去掉自动生成的dependecy和build

---

##### 5. zshop_dao java模块

> Module: maven-archetype-quickstart

* 配置pom.xml文件
  * 连接数据库的jar包
    * dbcp
    * mysql
    * mybatis
    * 分页插件
  * 依赖common、pojo

---

##### 6. zshop_service java模块

> Module: maven-archetype-quickstart

* 配置pom.xml文件
  * 依赖dao

---

##### 7. zshop_front_web java模块

> Module: maven-archetype-webapp

* 配置文件目录结构

  * main下面只有webapp
  * 添加directory: java （mark as Sources Root )
  * 添加directory: resources (mark as Resources Root)

* 替换webapp下自动生成的web.xml

  ```xml
  <?xml version="1.0" encoding="UTF-8"?>
  <web-app xmlns="http://xmlns.jcp.org/xml/ns/javaee"
           xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
           xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee http://xmlns.jcp.org/xml/ns/javaee/web-app_3_1.xsd"
           version="3.1">
  </web-app>
  ```

* pom.xml文件去掉自动生成的build和dependency(留下junit)

---

##### 8. zshop_backend_web java模块

> Module: maven-archetype-webapp

* 配置文件目录结构

  * main下面只有webapp
  * 添加directory: java （mark as Sources Root )
  * 添加directory: resources (mark as Resources Root)

* 替换webapp下自动生成的web.xml

  ```xml
  <?xml version="1.0" encoding="UTF-8"?>
  <web-app xmlns="http://xmlns.jcp.org/xml/ns/javaee"
           xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
           xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee http://xmlns.jcp.org/xml/ns/javaee/web-app_3_1.xsd"
           version="3.1">
  </web-app>
  ```

* pom.xml文件配置

  * 去掉自动生成的build和dependency(留下junit)

  * 添加web项目所需jar包

    * servlet
    * jsp
    * jstl
    * springweb
    * springmvc

  * 依赖于zshop_service

  * plugins: tomcat 同时配置path port

    ```xml 
      <plugins>
                <plugin>
                    <groupId>org.apache.tomcat.maven</groupId>
                    <artifactId>tomcat7-maven-plugin</artifactId>
                    <configuration>
                        <path>/zshop</path>
                        <port>8800</port>
                        <!--get请求中文乱码问题-->
                        <uriEncoding>utf-8</uriEncoding>
                    </configuration>
                </plugin>
            </plugins>
    ```


##### 9. 测试 

* 在maven project界面zshop_parent install所有包
* 打开本地maven项目仓库检查路径下文件
* 配置configuration
  * 添加maven tomcatbackend  
    * comand line : clean tomcat7:run
  * 直接运行跳转到浏览器界面
  * hello world

