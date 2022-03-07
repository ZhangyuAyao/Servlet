# Servlet
JavaWeb Servlet 
# JavaWeb
## 1、基本概念
### 1.1 web开发
- web，网页
- 静态web
    - html, css
    - 提供给所有人看的数据始终不会发生变化
- 动态web
    - 淘宝，几乎所有的网站；
    - 提供给所有人看的数据始终会发生变化，每个人能在不同的时间，不同的地点看到的信息各不相同；
    - 技术栈：Servlet/JSP, ASP, PHP

在 java 中，动态 web 资源开发的技术统称为 JavaWeb
### 1.2 web应用程序
web应用：可以提供访问的程序；
- a.html、b.html...多个web资源可以被外界访问，对外界提供服务；
- 你们能访问到的任何一个页面或者资源，都存在于这个世界的某一个角落的计算机上
- URL
- 这个统一的 web 资源会被放在同一个文件夹下，web应用程序->Tomcat：服务器
- 一个web引用由多部分组成（静态web，动态web）
    - html, css, js
    - jsp, servlet
    - java程序
    - jar包
    - 配置文件（Properties）
    
web应用程序编写完毕后，若想提供给外界访问：需要一个服务器来统一管理；

### 1.3 静态web
- *.htm, *.html 这些都是网页的后缀，如果服务器上一直存在这些东西
![image.png](https://note.youdao.com/yws/res/10185/WEBRESOURCEb4e33d780463b4ccd552c0910cdbad62)

- 静态web存在的缺点
    - web页面无法动态更新，所有用户看到都是同一个页面
        -  轮播图，点击特效：伪动态
        -  JavaScript [实际开发中，它用的最多]
        -  VBScript
    - 它无法和数据库交互（数据无法持久化，用户无法交互）

### 1.4 动态web
页面会动态展示：“Web的页面展示效果会因人而异”。

![image.png](https://note.youdao.com/yws/res/10200/WEBRESOURCE5373216f02145ab1ae056b1a29f8e4b2)

缺点：
- 加入服务器的动态web资源出现了错误，我们需要重新编写我们的后台程序，重写发布
    - 停机维护

优点：
- Web页面可以动态更新，所有的用户看到的都不是同一个页面
- 他可以和数据库交互（数据持久化，注册，商品信息，用户信息.....）

![image.png](https://note.youdao.com/yws/res/10214/WEBRESOURCEd589c45d66a2438775ce89cb00c280b2)


## 2. web服务器
**ASP：**
- 微软：国内最早流行的就是ASP；
- 在HTML中嵌入了VB的脚本，ASP + COM；
- 在ASP开发中，基本一个页面都有几千行的业务代码，页面极其混乱
- 维护成本极高
- C#
- IIS

![image.png](https://note.youdao.com/yws/res/10222/WEBRESOURCE82a489ff0abb75b469575dbc5179cc46)

**php：**
- PHP开发速度很快，功能很强大，跨平台，代码很简单（70%）
- 无法承载大访问量的情况（局限性）

**JSP/Servlet:**
B/S：浏览器和服务器
C/S：客户端和服务器
- Sun公司主推的B/S架构
- 基于Java语言的（所有的大公司，或者一些开源的组件，都是用Java写的）
- 可以承载三高问题带来的影响；
- 语法像ASP，ASP-->JSP，加强市场强度；

### 2.2 web服务器
服务器是一种被动的操作，用来处理用户的一些请求和给用户一些响应信息；

**IIS**
微软的；ASP...， Windows中自带的

**Tomcat**
面向百度编程
Tomcat是Apache 软件基金会（Apache Software Foundation）的Jakarta 项目中的一个核心项目，最新的Servlet 和JSP 规范总是能在Tomcat 中得到体现，因为Tomcat 技术先进、性能稳定，而且免费，因而深受Java 爱好者的喜爱并得到了部分软件开发商的认可，成为比较流行的Web 应用服务器。

Tomcat 服务器是一个免费的开放源代码的Web 应用服务器，属于轻量级应用服务器，在中小型系统和并发访问用户不是很多的场合下被普遍使用，是开发和调试JSP 程序的首选。对于一个初学者来说，它是最佳的选择

而Tomcat 实际上运行JSP 页面和Servlet。Tomcat最新版本为10.0.14。

**工作3-5年之后，可以尝试手写Tomcat服务器：**
下载tomcat：
1. 安装 or 解压
2. 了解配置文件及目录结构
3. 这个东西的作用

## 3、Tomcat
### 3.1 安装Tomcat
Tomcat官网：下载
### 3.2 文件夹的作用
![image.png](https://note.youdao.com/yws/res/10254/WEBRESOURCEc27d2c901e647dd2d99f594d46a48df6)

### 3.3 服务的启动、关闭
startup.bat
shutdown.bat
启动闪退的解决：
方法一：在环境变量中添加JAVA_HOME以及jdk的目录
方法二：在bat文件中添加如下的信息：
> SET JAVA_HOME=C:\Program Files\Java\jdk1.8.0_202
> SET TOMCAT_HOME=C:\Users\bytedance\Documents\environment\apache-tomcat-10.0.16

> 1：在已解压的tomcat的bin文件夹下找到startup.bat（我这里是C:\Tool\apache-tomcat-8.5.32\bin），右击->编辑（也可以代码编辑器用打开eg:Notepad）。在文件头下加入下面两行：
> 
> SET JAVA_HOME=C:\Tool\Java （java jdk目录）
> SET TOMCAT_HOME=C:\Tool\apache-tomcat-8.5.32（解压后的tomcat文件目录）
>
> 
> 2.在已解压的tomcat的bin文件夹下找到shutdown.bat，右击->编辑。在文件头下面同样加入两行：
> 
> SET JAVA_HOME=C:\Tool\Java
> SET TOMCAT_HOME=C:\Tool\apache-tomcat-8.5.32 
> 
> 点击startup.bat就可以启动tomcat服务了了

![image.png](https://note.youdao.com/yws/res/10263/WEBRESOURCEe2ac1c1fb00bdce75934d44700de66ca)
该文件可以配置启动的端口号
- tomcat的默认端口号：8080
- mysql：3306
- http：80
- https：443
```xml
<Connector port="8080" protocol="HTTP/1.1"
           connectionTimeout="20000"
           redirectPort="8443" />
```
可以配置主机的名称
- 默认的主机名为：localhost->127.0.0.1
- 默认网站应用存放的位置:webapps

```xml
  <Host name="localhost"  appBase="webapps"
        unpackWARs="true" autoDeploy="true">
```

**高难度面试题：**
请你谈谈网站是怎么访问的？
1. 输入一个域名，回车
2. 检查本机 C:\Windows\System32\drivers\etc\hosts 配置文件下有没有这个域名映射
    1. 有：直接返回对应的ip地址，这个地址中，有我们需要访问的web程序，可以直接访问
    2. 如果没有，再去找DNS服务器里面找

![image.png](https://note.youdao.com/yws/res/10295/WEBRESOURCEc800a8e6eaec6817d2212b940cc858d7)
3. 可以配置一下环境变量（可选）

### 3.4 发布一个网站
不会就先模仿：
- 将自己写的网站，放到服务器（Tomcat）中指定的web应用的文件夹（webapps）下，就可以访问了
网站应该有的结构

```
--webapps: Tomcat服务器的web目录
    --ROOT
    -kuangshen : 网站的目录名
        -classes: java程序
        -lib: web应用所依赖的jar包
        -web.xml: 网站配置文件
    - index.html 默认的首页
    - static 
        -css
            -style.css
        -js
        -img
    -...
```

## 4、HTTP
### 4.1 什么是HTTP
HTTP（超文本传输协议）是一个简单的请求-响应协议，它通常运行在TCP之上。
- 文本：html，字符串，~...
- 超文本：图片，音乐，视频，定位，地图......
- 端口：80

HTTPS：安全的

- 端口：443

### 4.2 两个时代
- http1.0
    - HTTP/1.0：客户端可以与web服务器连接后，只能获得一个web资源，断开连接
- http2.0
    - HTTP/1.1：客户端可以与web服务器连接后，可以获得多个web资源。

### 4.3 Http请求
- 客户端---发请求（Request）---服务器
百度：
```java
Request URL: https://www.baidu.com/ 请求地址
Request Method: GET  get方法/post方法
Status Code: 200 OK 状态吗：200
Remote Address: 103.235.46.39:443 
```
```java
Accept: text/html
Accept-Encoding: gzip, deflate, br
Accept-Language: zh-CN,zh;q=0.9,en;q=0.8,zh-TW;q=0.7 语言
Cache-Control: max-age=0
Connection: keep-alive
```
#### 1. 请求行
- 请求行中的请求方式：GET
- 请求方式：**Get，Post**，HEAD、DELDETE、PUT、TRAC

    - get：请求能够携带的参数比较少，大小有限制，会在浏览器的URL地址栏显示数据内容，不安全，但高效
    
    - post：请求能够携带的参数没有限制，大小没有限制，不会再浏览器的URL地址栏显示内容，安全，但不高效

#### 2. 消息头
```java
Accept: 告诉浏览器，他所支持的数据类型
Accept-Encoding: 支持那种编码格式 GBK UTF-8 GB2312 IOS8859-1
Accept-Language: 告诉浏览器，他的语言环境
Cache-Control: 缓存控制
Connection: 告诉浏览器，请求完成时断开还是保持连接
HOST：主机...../
```


### 4.4 Http响应
- 服务器---响应（Response）---客户端
百度：
```java
Cache-Control: private
Connection: keep-alive
Content-Encoding: gzip
Content-Type: text/html;charset=utf-8
```

#### 1. 响应体
```java
Accept: 告诉浏览器，他所支持的数据类型
Accept-Encoding: 支持那种编码格式 GBK UTF-8 GB2312 IOS8859-1
Accept-Language: 高数浏览器，他的语言环境
Cache-Control: 缓存控制
Connection: 告诉浏览器，请求完成时断开还是保持连接
HOST：主机...../
Refresh：告诉客户端，多久刷新一次
Location：让网页重新定位
```
####  2. 响应状态码（==重点==）
200：请求响应成功

3xx：请求重定向
- 重定向：你重新到给我给你的新位置；

4xx：找不到资源
- 资源不存在；

5xx：服务器代码错误 500  502：网关错误

#### **常见面试题：**

当你的浏览器中地址栏输入地址并回车的一瞬间到页面能够展示回来，经历了什么？
1. 客户端发送HTTP请求到服务端，其中HTTP请求的头文件包含请求的URL，请求的方法，以及支持的接受类型、编码格式、语言环境、连接是否断开等

2. 服务端接受到客户端的Request之后，服务端的服务会填充响应头告诉客户端编码格式、资源类型、语言环境、状态码等，并附上请求的内容，回传给客户端

3. 上诉连接的建立会经历HTTP的三次握手

4. 客户端接受到服务端的响应后，会根据协议将响应的内容显示在浏览器上面

## 5. Maven
**我为什么要学这个技术？**
1. 在javaweb开发中，需要使用大量的jar包，我们手动去导入；

2. 如何能够让一个东西自动帮我导入和配置这个jar包。
    由此，Maven诞生了

### 5.1 Maven项目结构管理工具
我们目前用来就是方便导入jar包的！

Maven的核心思想：**约定大于配置**
- 有约束，不要去违反。

Maven会规定好你该如何去编写我们的java代码，必须按照这个规定来

### 5.2 Maven的下载
![image.png](https://note.youdao.com/yws/res/10480/WEBRESOURCE454ecb628d92f1abeb788457eed8e72e)
下载完成后，解压即可
小狂神友情建议，下载的软件包都放在同一个地方方便管理

### 5.3 配置环境变量
在我们的系统环境变量中

配置如下配置：

- M2_HOME：maven目录下的bin目录
- MAVEN_HOME：maven的目录
- 在系统的path中配置 %MAVEN_HOME%\bin

![image.png](https://note.youdao.com/yws/res/10489/WEBRESOURCE498575cba7a560ecc21f66e30cd208c3)

测试是否配置正常

### 5.4 配置阿里云镜像
- 镜像：mirrors

    - 作用：加速我们的下载
    
- 国内建议使用阿里云的镜像

```xml
<id>nexus-aliyun</id>
<mirrorOf>central</mirrorOf>
<name>Nexus aliyun</name>
<url>http://maven.aliyun.com/nexus/content/groups/public</url>
```

### 5.5 本地仓库
在本地的仓库，远程仓库；

建立一个本地仓库：
```xml
<localRepository>C:\Users\bytedance\Documents\environment\apache-maven-3.8.4\maven-repo</localRepository>
```

### 5.6 在IDEA中使用Maven
1. 启动IDEA
2. 创建一个Maven项目
3. 创建步骤
![image.png](https://note.youdao.com/yws/res/10500/WEBRESOURCEf02e87372c3224f0080b82f8d802f31b)

![image.png](https://note.youdao.com/yws/res/10502/WEBRESOURCE1f3884aeb952b3a39b086bbb0d37e394)

![image.png](https://note.youdao.com/yws/res/10504/WEBRESOURCEa3ffce6c18343f6d699e224b8d553f7c)

![image.png](https://note.youdao.com/yws/res/10509/WEBRESOURCE851a490549b71b914e3bfcdfca3e046c)
4. 观察maven仓库中多了什么
5. IDEA中的Maven设置
    IDEA项目创建成功后，看一眼Maven的配置
![image.png](https://note.youdao.com/yws/res/10516/WEBRESOURCE4db58f9a3ee4914cd65789ccc8edfa44)

![image.png](https://note.youdao.com/yws/res/10518/WEBRESOURCEb3b28bf45943b9b2b9a6c0a40c217517)

6. 到这里，Maven在IDEA中的配置和使用就ok了

### 5.7 创建一个普通的Maven项目

不使用模板，创建一个干净的maven项目
![image.png](https://note.youdao.com/yws/res/10524/WEBRESOURCE9704fbf244e0ff6806ca9187d833abf6)

这个只有在webapp下才有
![image.png](https://note.youdao.com/yws/res/10527/WEBRESOURCE1c3fb6589c8b7f0222a6bd986cd7334c)

### 5.8 标记文件夹功能
![image.png](https://note.youdao.com/yws/res/10537/WEBRESOURCEa8eba4ea31b1dc80de282d438edff777)

![image.png](https://note.youdao.com/yws/res/10539/WEBRESOURCEa065126535ebc9125a42f97acb4bfd4f)

![image.png](https://note.youdao.com/yws/res/10541/WEBRESOURCE9bd596b42a6740b5a02adf3f979a0922)

![image.png](https://note.youdao.com/yws/res/10545/WEBRESOURCE1c2f5e81b939640f82137b6a58929014)

### 5.9 在IDEA中配置Tomcat
![image.png](https://note.youdao.com/yws/res/10547/WEBRESOURCE7df332545a62d3ac5b338531140789db)

![image.png](https://note.youdao.com/yws/res/10549/WEBRESOURCEe59ec0b2d68920d73f91d957f57a2b7d)

解决警告问题

必须要的配置：**为什么会有这个问题：我们访问一个网站，需要指定一个文件夹名字；**

![image.png](https://note.youdao.com/yws/res/10553/WEBRESOURCE8051cf659c4423d8e1667272011b28d6)

![image.png](https://note.youdao.com/yws/res/10558/WEBRESOURCEfdf5b91114760397d5b32fdf0012f6cd)

![image.png](https://note.youdao.com/yws/res/10556/WEBRESOURCEd8454288763b602938a197f8652e4b80)

### 5.10 pom文件
pom.xml 是maven的核心配置文件 

```xml
<?xml version="1.0" encoding="UTF-8"?>

<!--maven版本和头文件-->
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>

  <!--这里就是我们刚才配置的GAV-->
  <groupId>com.kuang</groupId>
  <artifactId>javaweb-01-maven</artifactId>
  <version>1.0-SNAPSHOT</version>
  <!--Package:项目的打包方式
  jar:java应用
  war：JavaWeb应用-->
  <packaging>war</packaging>

  <name>javaweb-01-maven Maven Webapp</name>
  <!-- FIXME change it to the project's website -->
  <url>http://www.example.com</url>

  <!--配置-->
  <properties>
    <!--项目的默认构建编码-->
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    <!--编码版本-->
    <maven.compiler.source>1.8</maven.compiler.source>
    <maven.compiler.target>1.8</maven.compiler.target>
  </properties>

  <!--项目依赖-->
  <dependencies>
    <!--具体依赖的jar包配置文件-->
    <dependency>
      <groupId>junit</groupId>
      <artifactId>junit</artifactId>
      <version>4.11</version>
      <scope>test</scope>
    </dependency>
  </dependencies>

  <!--项目构建用的东西-->
  <build>
    <finalName>javaweb-01-maven</finalName>
    <pluginManagement><!-- lock down plugins versions to avoid using Maven defaults (may be moved to parent pom) -->
      <plugins>
        <plugin>
          <artifactId>maven-clean-plugin</artifactId>
          <version>3.1.0</version>
        </plugin>
        <!-- see http://maven.apache.org/ref/current/maven-core/default-bindings.html#Plugin_bindings_for_war_packaging -->
        <plugin>
          <artifactId>maven-resources-plugin</artifactId>
          <version>3.0.2</version>
        </plugin>
        <plugin>
          <artifactId>maven-compiler-plugin</artifactId>
          <version>3.8.0</version>
        </plugin>
        <plugin>
          <artifactId>maven-surefire-plugin</artifactId>
          <version>2.22.1</version>
        </plugin>
        <plugin>
          <artifactId>maven-war-plugin</artifactId>
          <version>3.2.2</version>
        </plugin>
        <plugin>
          <artifactId>maven-install-plugin</artifactId>
          <version>2.5.2</version>
        </plugin>
        <plugin>
          <artifactId>maven-deploy-plugin</artifactId>
          <version>2.8.2</version>
        </plugin>
      </plugins>
    </pluginManagement>
  </build>
</project>
```

![image.png](https://note.youdao.com/yws/res/10564/WEBRESOURCE8342eee1b00aeee440ee264c7787078b)

maven由于他的约定大于配置，我们之后可能会遇到我们写的配置文件，无法被导出或者生效的可能，解决方案在maven的pom.xml中配置：
```xml
<!--在build中配置resources,来防止我们资源导出失败的问题-->
    <build>
        <resources>
            <resource>
                <directory>src/main/resources</directory>
                <excludes>
                    <exclude>**/*.properties</exclude>
                    <exclude>**/*.xml</exclude>
                </excludes>
                <filtering>false</filtering>
            </resource>
            <resource>
                <directory>src/main/java</directory>
                <includes>
                    <include>**/*.properties</include>
                    <include>**/*.xml</include>
                </includes>
                <filtering>false</filtering>
            </resource>
        </resources>
    </build>
```

### 5.11 IDEA目录树

![image.png](https://note.youdao.com/yws/res/10572/WEBRESOURCE40508b00d6b05f143ae7a2467b4a8f5e)

![image.png](https://note.youdao.com/yws/res/10574/WEBRESOURCEda22378295f78f85bca7de5f41726fa4)

## 6. Servlet
### 6.1 Servlet简介

- Servlet 就是 sum 公司开发动态 web 的一门技术

- Sun在这些API中行提供了一个接口叫做：Servlet，如果你想开发一个Servlet程序，只需要完成两个小步骤：
    - 编写一个类，实现Servlet接口
    - 把开发好的Java类部署到web服务器中
把实现了Servlet接口的Java程序叫做，Servlet

### 6.2 HelloServlet
Servlet接口在Sun公司有两个默认的实现类：HttpServlet，GenericServlet
1. 构建一个普通的Maven项目，删掉里面的serc目录，以后我们的学习就在这个项目里面建立Moudel
2. 关于Maven父子工程的理解：（这里子项目不一定会有parent标签）
![image.png](https://note.youdao.com/yws/res/10593/WEBRESOURCE43c9f5ec215cf366c81fd858a9c7471c)
3. Maven环境优化
    1. 修改web.xml为最新的
    2. 将maven的结构搭建完整
    
4. 编写一个servlet程序
    1. 编写一个普通类
    2. 实现Servlet接口，这里我们直接继承HttpServlet

```java
public class HelloServlet extends HttpServlet {

    //由于get或者post只是请求实现的不同的方式，可以相互调用，业务逻辑都一样；

    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
//        ServletOutputStream outputStream = resp.getOutputStream();
        PrintWriter writer = resp.getWriter();//响应流
        writer.print("Hello,Servlet");

    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        super.doPost(req, resp);
    }
}
```
5. 编写Servlet的映射
    为什么需要映射：我们写的是JAVA程序，但是要通过浏览器访问，而浏览器需要连接web服务器，所以我们需要在web服务中注册我们写的Servlet，还需要给他一个浏览器能够访问的路径
```xml
    <servlet>
        <servlet-name>hello</servlet-name>
        <servlet-class>com.kuang.service.HelloServlet</servlet-class>
    </servlet>
    <servlet-mapping>
        <servlet-name>hello</servlet-name>
        <url-pattern>/hello</url-pattern> //注意！！这里hello前面有一个/
    </servlet-mapping>
```

6. 配置Tomacat
    注意：配置项目发布的路径就可以了，将项目访问路径改写为/s1
![image.png](https://note.youdao.com/yws/res/10625/WEBRESOURCE0e62e2738fa21f2f3daa1cb790af4f09)
7. 启动测试
    访问：localhost:8080/s1/hello

### 6.3 Servlet原理
![image.png](https://note.youdao.com/yws/res/10687/WEBRESOURCE5b75343c45fa324e0e30bc96853c3f51)
> 个人备注：
> 1. web容器是Tomcat
> 2. Srrvlet是java类
> 3. 浏览器发送的Http请求到web容器中，web容器接收后创建Request对象
> 4. 我们重写的 doGet 实现类是可以拿到Request对象和Response对象，可以取得浏览器Http请求的各种信息，也可以设置响应的各种信息
> 5. 走完我们这个类的流程后web容器会返回Response给浏览器

### 6.4 Mapping问题
1. 一个Servlet可以指定一个映射路径
```xml
  <servlet-mapping>
    <servlet-name>hello</servlet-name>
    <url-pattern>/hello</url-pattern>
  </servlet-mapping>
```
2. 一个Servlet可以指定多个映射路径
```xml
  <servlet-mapping>
    <servlet-name>hello</servlet-name>
    <url-pattern>/hello</url-pattern>
  </servlet-mapping>
  <servlet-mapping>
    <servlet-name>hello</servlet-name>
    <url-pattern>/hello1</url-pattern>
  </servlet-mapping>
  <servlet-mapping>
    <servlet-name>hello</servlet-name>
    <url-pattern>/hello2</url-pattern>
  </servlet-mapping>
```
3. 一个Servlet可以指定通用映射路径
```xml
  <servlet-mapping>
    <servlet-name>hello</servlet-name>
    <url-pattern>/hello/*</url-pattern>
  </servlet-mapping>
```
4. 默认请求路径
```xml
  <servlet-mapping>
    <servlet-name>hello</servlet-name>
    <url-pattern>/*</url-pattern>
  </servlet-mapping>
```
5. 指定一些后缀或者前缀等等...
```xml
<!--可以自定义后缀实现请求映射
    注意点，*前面不能加项目映射的路径"/"
    http://localhost:8080/s1/dfd.qinjiang 能被找到，需要带默认的部署s1
    http://localhost:8080/hello/dfd.qinjiang 不能被找到
    -->
  <servlet-mapping>
    <servlet-name>hello</servlet-name>
    <url-pattern>*.qinjiang</url-pattern>
  </servlet-mapping>
```
6. 优先级问题
    指定了固有的映射路径优先级最高，如果找不到就会走默认的处理请求
```xml
  <!--自定义404页面-->
  <servlet>
    <servlet-name>error</servlet-name>
    <servlet-class>com.kuang.servlet.ErrorServlet</servlet-class>
  </servlet>
  <servlet-mapping>
    <servlet-name>error</servlet-name>
    <url-pattern>/*</url-pattern>
  </servlet-mapping>
```
### 6.5 ServletContext
web容器在启动的时候，它会为每个web程序都创建一个对应的ServletContext对象，它代表了当前的web应用
> web容器：Tomcat
> web程序：Servlet1、Servlet2、Servlet3
> ServletContext: 一个web程序共享的对象
![image.png](https://note.youdao.com/yws/res/10749/WEBRESOURCEe87d095e28d7ae549af4019683db7e1a)

#### 1. 共享数据
我在这个Servlet中保存的数据，可以在另一个Servlet中拿到
```java
public class HelloServlet extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        System.out.println("Servlet02:Hello");

        //this.getInitParameter() 初始化参数
        //this.getServletConfig() Servlet配置
        //this.getServletContext()  Servlet上下文
        ServletContext context = this.getServletContext();

        String username = "青江";//数据
        context.setAttribute("username", username);//讲一个数据保存在了ServletContext中，名字为username，值为username
    }
}
```
```java
public class GetServlet extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        ServletContext context = this.getServletContext();
        String username = (String)context.getAttribute("username");
        resp.setHeader("Content-Type", "text/html;charset=utf-8");
        PrintWriter writer = resp.getWriter();
        writer.print("名字"+username);
    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        super.doPost(req, resp);
    }
}
```
```xml
<!DOCTYPE web-app PUBLIC
 "-//Sun Microsystems, Inc.//DTD Web Application 2.3//EN"
 "http://java.sun.com/dtd/web-app_2_3.dtd" >

<web-app>
  <display-name>Archetype Created Web Application</display-name>
  
  <servlet>
    <servlet-name>hello</servlet-name>
    <servlet-class>com.kuang.servlet.HelloServlet</servlet-class>
  </servlet>
  <servlet-mapping>
    <servlet-name>hello</servlet-name>
    <url-pattern>/hello</url-pattern>
  </servlet-mapping>

  <servlet>
    <servlet-name>getc</servlet-name>
    <servlet-class>com.kuang.servlet.GetServlet</servlet-class>
  </servlet>
  <servlet-mapping>
    <servlet-name>getc</servlet-name>
    <url-pattern>/getc</url-pattern>
  </servlet-mapping>
</web-app>
```
测试访问结果：

#### 2. 获取初始化参数
```xml
  <context-param>
    <param-name>url</param-name>
    <param-value>jdbc:mysql://localhost:3306/mybatis</param-value>
  </context-param>
```
```java
public class ServletDemon03 extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        ServletContext context = this.getServletContext();
        String url = context.getInitParameter("url");
        resp.getWriter().print(url);
    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        super.doPost(req, resp);
    }
}
```
#### 3. 请求转发
```java
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        ServletContext context = this.getServletContext();
        System.out.println("进入了ServletDemo04...");
        //RequestDispatcher requestDispatcher = context.getRequestDispatcher("/gp");
        //requestDispatcher.forward(req, resp);//调用forward实现请求转发：转发不像是重定向，其url不会发生改变
        context.getRequestDispatcher("/gp").forward(req, resp);
    }
```
![image.png](https://note.youdao.com/yws/res/10768/WEBRESOURCE94379aeb233bc2e88fc5a1fcf6bdb3e0)
> 上图：是请求转发的过程
> 下图：是重定向的过程

#### 4. 读取资源文件
Properties
- 在java目录下新加properties
- 在resources目录下新加properties

发现：都被打包到了同一个路径下：classes，我们俗称这个路径为classpath

思路：需要一个文件流；
```properties
username=root
password=123456
```

```java
public class ServletDemo05 extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        ServletContext context = this.getServletContext();
        InputStream is = context.getResourceAsStream("/WEB-INF/classes/db.properties");

        Properties properties = new Properties();
        properties.load(is);
        String username = properties.getProperty("username");
        String password = properties.getProperty("password");

        resp.getWriter().print(username + ":" + password);
    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        super.doPost(req, resp);
    }
}
```
访问测试即可ok；

### 6.6 HttpServletResponse
web服务器接受到客户端的http请求，针对这个请求，分别创建一个代表哦请求的HttpServletResponse对象，代表响应的一个HttpServletResponse；
- 如果要获取客户端请求过来的参数：找HttpServletRequest
- 如果要给客户端响应一些信息：找HttpServletResponse

#### 1. 简单分类
负责向浏览器发送数据的方法
```java
    ServletOutputStream getOutputStream() throws IOException;
    
    PrintWriter getWriter() throws IOException;
```
负责向浏览器发送响应的方法
```java
    void setCharacterEncoding(String var1);

    void setContentLength(int var1);

    void setContentLengthLong(long var1);

    void setContentType(String var1);
    
    void setDateHeader(String var1, long var2);

    void addDateHeader(String var1, long var2);

    void setHeader(String var1, String var2);

    void addHeader(String var1, String var2);

    void setIntHeader(String var1, int var2);

    void addIntHeader(String var1, int var2);
```
响应状态码
```java
    int SC_CONTINUE = 100;
    int SC_SWITCHING_PROTOCOLS = 101;
    int SC_OK = 200;
    int SC_CREATED = 201;
    int SC_ACCEPTED = 202;
    int SC_NON_AUTHORITATIVE_INFORMATION = 203;
    int SC_NO_CONTENT = 204;
    int SC_RESET_CONTENT = 205;
    int SC_PARTIAL_CONTENT = 206;
    int SC_MULTIPLE_CHOICES = 300;
    int SC_MOVED_PERMANENTLY = 301;
    int SC_MOVED_TEMPORARILY = 302;
    int SC_FOUND = 302;
    int SC_SEE_OTHER = 303;
    int SC_NOT_MODIFIED = 304;
    int SC_USE_PROXY = 305;
    int SC_TEMPORARY_REDIRECT = 307;
    int SC_BAD_REQUEST = 400;
    int SC_UNAUTHORIZED = 401;
    int SC_PAYMENT_REQUIRED = 402;
    int SC_FORBIDDEN = 403;
    int SC_NOT_FOUND = 404;
    int SC_METHOD_NOT_ALLOWED = 405;
    int SC_NOT_ACCEPTABLE = 406;
    int SC_PROXY_AUTHENTICATION_REQUIRED = 407;
    int SC_REQUEST_TIMEOUT = 408;
    int SC_CONFLICT = 409;
    int SC_GONE = 410;
    int SC_LENGTH_REQUIRED = 411;
    int SC_PRECONDITION_FAILED = 412;
    int SC_REQUEST_ENTITY_TOO_LARGE = 413;
    int SC_REQUEST_URI_TOO_LONG = 414;
    int SC_UNSUPPORTED_MEDIA_TYPE = 415;
    int SC_REQUESTED_RANGE_NOT_SATISFIABLE = 416;
    int SC_EXPECTATION_FAILED = 417;
    int SC_INTERNAL_SERVER_ERROR = 500;
    int SC_NOT_IMPLEMENTED = 501;
    int SC_BAD_GATEWAY = 502;
    int SC_SERVICE_UNAVAILABLE = 503;
    int SC_GATEWAY_TIMEOUT = 504;
    int SC_HTTP_VERSION_NOT_SUPPORTED = 505;
```
#### 2. 常见应用
1. 向浏览器输出消息（一直在讲，就不说了）
2. 下载文件
    1. 要获取下载文件的路径
    2. 下载的文件名
    3. 设置想办法让浏览器能够支持下载我们需要的东西
    4. 获取下载文件的输入流
    5. 创建缓冲区
    6. 获取OutputStream对象
    7. 将FileOutputStream流写入到buffer缓冲区
    8. 使用OutputStream将缓冲区中的数据输出到客户端
    
```java
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        //1. 要获取下载文件的路径
        //String realPath = this.getServletContext().getRealPath("/1.png");//会报错
        String realPath = "C:\\Users\\bytedance\\IdeaProjects\\javaweb-01-maven\\javaweb-02-maven\\response\\src\\main\\resources\\青江.jpg";
        System.out.println("下载文件的路径：" + realPath);
        //2. 下载的文件名
        String fileName = realPath.substring(realPath.lastIndexOf("\\") + 1);
        //3. 设置想办法让浏览器能够支持下载我们需要的东西Content-Disposition，中文文件名使用URLEncoder.encode编码放置乱码
        resp.setHeader("Content-Disposition", "attachment; filename="+ URLEncoder.encode(fileName, "utf-8"));
        //4. 获取下载文件的输入流
        FileInputStream in = new FileInputStream(realPath);
        //5. 创建缓冲区
        int len = 0;
        byte[] buffer = new byte[1024];
        //6. 获取OutputStream对象
        ServletOutputStream out = resp.getOutputStream();
        //7. 将FileOutputStream流写入到buffer缓冲区
        while((len = in.read(buffer)) > 0) {
            out.write(buffer, 0, len);
        }
        in.close();
        out.close();
    }
```
#### 3. 验证码功能
验证怎么来的？
- 前端实现
- 后端实现，需要用到java的图片类，生产一个图片
```java
public class ImageServlet extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        System.out.println("进入/image的doGet方法");
        //如何让浏览器5秒自动刷新一次；
        resp.setHeader("refresh", "5");

        //在内存中创建一个图片
        BufferedImage image = new BufferedImage(80, 20, BufferedImage.TYPE_INT_BGR);
        //得到图片
        Graphics2D g = (Graphics2D)image.getGraphics();
        //设置图片的背景颜色
        g.setColor(Color.white);
        g.fillRect(0,0,80,20);
        //给图片写数据
        g.setColor(Color.blue);
        g.setFont(new Font(null, Font.BOLD,20));
        g.drawString(makeNum(), 0, 20);

        //告诉浏览器，这个请求用图片的方式打开
        resp.setContentType("image/jpeg");
        //网站存在缓存，不让浏览器缓存
        resp.setDateHeader("expires", -1);
        resp.setHeader("Cache-Control", "no-cache");
        resp.setHeader("pragma", "no-cache");

        //把图片写给浏览器
        ImageIO.write(image, "jpg", resp.getOutputStream());

    }
    //生成随机数
    private String makeNum() {
        Random random = new Random();
        String num = random.nextInt(9999999) + "";
        StringBuffer sb = new StringBuffer();
        for(int i = 0; i < 7 - num.length(); i++) {
            sb.append("0");
        }
        return sb.append(num).toString();
    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        super.doPost(req, resp);
    }
}
```
#### 4. 实现重定向
![image.png](https://note.youdao.com/yws/res/10819/WEBRESOURCE8c2d1e8c2c4912b79eaa698f5be810b9)
一个web资源收到客户端A请求后，B他会通知客户端A去访问另外一个web资源C，这个过程叫重定向

常见场景：
- 用户登录
```JAVA
void sendRedirect(String var1) throws IOException;
```
**面试题：请你聊聊重定向和转发的区别？**
相同点
- 页面都会实现跳转
不同点
- 请求转发的时候，url不会产生变化
- 重定向的时候，url地址栏会发生变化

### 6.7 HttpServletRequest
HttpServletRequest代表客户端的请求，用户通过Http协议访问服务器，HTTP请求中的所有信息会被封装到HttpServletRequest，通过这个HttpServletRequest可以获取客户端的所有信息

![image.png](https://note.youdao.com/yws/res/10832/WEBRESOURCE325c65f640e46fa21076e4fc1b9fc7ae)

![image.png](https://note.youdao.com/yws/res/10834/WEBRESOURCE8c2553dacc66f4de3a8a4555b95eebea)


![image.png](https://note.youdao.com/yws/res/10838/WEBRESOURCEef355c8584ea8a314c17e9b7f5f837c8)
**1. 获取前端传递的参数**
**2. 请求转发**

```java
public class LoginServlet extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        req.setCharacterEncoding("utf-8");
        resp.setCharacterEncoding("utf-8");
        String username = req.getParameter("username");
        String password = req.getParameter("password");
        String[] hobbies = req.getParameterValues("hobby");
        System.out.println("===================");;
        System.out.println(username);
        System.out.println(password);
        System.out.println(Arrays.toString(hobbies));
        System.out.println("===================");;

        //通过请求转发
        //这里的 / 代表当前的web应用
        req.getRequestDispatcher("/success.jsp").forward(req, resp);
        resp.setCharacterEncoding("utf-8");
    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        //这里直接将post请求交给doGet处理
        doGet(req,resp);
    }
}
```
**面试题：请你聊聊重定向和转发的区别**

相同点

- 页面都会实现跳转

不同点

- 重定向的时候，URL会改变 状态码是302
- 转发的时候，URL不会产生变化 状态码是307

最新web.xml
```xml
<?xml version="1.0" encoding="UTF-8"?>
<web-app xmlns="http://xmlns.jcp.org/xml/ns/javaee"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee
                  http://xmlns.jcp.org/xml/ns/javaee/web-app_4_0.xsd"
         version="4.0"
         metadata-complete="true">

</web-app >
```

## 7. Cookie、Session
### 7.1 会话 
**会话**：用户打开了一个浏览器，惦记了很多超链接，访问了多个web资源，关闭浏览器，这个过程可以称之为会话。

**有状态会话：** 一个同学来过教室，下次再来教室，我们会知道这个同学，曾经来过，称之为有状态会话；

**你能怎么证明你是西开的学生？**
你 ------- 西开
1. 发票         西开给你发票
2. 学校登记     西开标记你来过了

**一个网站，怎么证明你来过？**
客户端 ------- 服务端
1. 服务端给客户端一个信件，客户端下次访问服务端带上信件就可以了；cookie
2. 服务器登记你来过了，下次你来的时候我来匹配你；session

### 7.2 保存会话的两种技术

**cookie**
- 客户端技术（响应，请求）

**session**
- 服务端技术，利用这个技术，可以保存用户的会话信息？我们可以把信息或者信息放在Session中！

常见场景：网站登录之后，你下次不用再登录了，第二次访问就直接上去了

### 7.3 Cookie
![image.png](https://note.youdao.com/yws/res/11034/WEBRESOURCE0dce098e9206025513b8706f8d28f85a)

1. 从请求中拿到cookie信息
2. 服务器响应给客户端cookie

```java
Cookie[] cookies = req.getCookies();
cookie.getName();
cookie.getValue();
Cookie cookie = new Cookie("lastLoginTime", System.currentTimeMillis()+"");
resp.addCookie(cookie);
```
**cookie：一般会保存在本地的用户目录下appdata；**

一个万战cookie是否存在上限？**聊聊细节问**题
- 一个Cookie只能保存一个信息；
- 一个web站点可以给浏览器发送多个cookie，最多存放20个cookie；
- Cookie大小有限制4kb
- 300个cookie浏览器上限

**删除Cookie：**
- 不设置有效期，关闭浏览器，自动失效；
- 设置有效期时间为0

编码解码：
```java
URLDecoder.decode(cookie.getValue(), "utf-8")
URLEncoder.encode("青江", "utf-8")
```

### 7.4 Session (==重点==)
![image.png](https://note.youdao.com/yws/res/11036/WEBRESOURCE968ed01b9b5e5c1cd76dc560657583a3)
什么是Session：
- 服务器会给每一个用户（浏览器）创建一个Session对象
- 一个Session独占一个浏览器，重要浏览器没有关闭，这个Session就存在
- 用户登录之后，整个网站他都可以访问！-->保存用户的信息；保存购物车的信息...

Session和cookie的区别：
- Cookie是把用户的数据写给用户的浏览器，浏览器保存（可以保存多个）
- Session把用户的数据写到用户独占Session中，服务器端保存（保存重要的信息，减少服务器资源的浪费）
- Session对象由服务器端创建；

使用场景：
- 保存一个登录用户的信息；
- 购物车信息；
- 在整个网站中经常会使用的数据，我们将它保存在Session中

```java
public class SessionDemo01 extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {

        //解决乱码问题
//        resp.setHeader("Content-Type", "text/html;charset=utf-8");
        resp.setContentType("text/html;charset=utf-8");

        //得到session
        HttpSession session = req.getSession();

        //给session中存东西
        session.setAttribute("name", new Person("青江", 28));

        //获取session的ID
        String sessionId = session.getId();

        //判断Session是不是新创建
        if(session.isNew()) {
            resp.getWriter().write("session创建成功,ID="+sessionId);
        } else {
            resp.getWriter().write("session已经在服务器中存在了ID="+sessionId);
        }

        //Session创建的时候做了什么事情
//        Cookie jsessionid = new Cookie("JSESSIONID", sessionId);
//        resp.addCookie(jsessionid);

    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        doGet(req, resp);
    }
}

        //得到session
        HttpSession session = req.getSession();

        Person person = (Person) session.getAttribute("name");
        System.out.println(person);

        HttpSession session = req.getSession();
        session.removeAttribute("name");
        //手动注销session
        session.invalidate();
```
![image.png](https://note.youdao.com/yws/res/11038/WEBRESOURCE387eedbfe48db7ecd1620a3dc6c381b8)
> 如果想要多个人共享数据，则可以将数据存到ServletContext中

## 8. JSP
### 8.1 什么是JSP
java Server Pages: java服务器端页面，也和Servlet一样，用于动态Web技术！

最大的特点：
- 写JSP就想在写HTML
- 区别
    - HTML只给用户提供静态的数据
    - JSP页面中可以嵌入JAVA代码，为用户提供动态数据；
    

### 8.2 JSP原理

思路：JSP到底怎么执行的
- 代码层面没有任何问题
- 服务器内部工作
    tomcat中有一个work目录；
    
**浏览器向服务器发送请求，不管访问什么资源，其实都是在访问Servlet！**

JSP最终也会被转换成一个JAVA类

**JSP本质上就是一个Servlet**

![image.png](https://note.youdao.com/yws/res/11057/WEBRESOURCEa49ecf5f5f363ca96760d911f2c6c03f)

1. 判断请求
2. 内置一些对象
![image.png](https://note.youdao.com/yws/res/11063/WEBRESOURCE985e7a77e824107408e4c2cd5d710eac)
3. 输出页面前增加的代码
![image.png](https://note.youdao.com/yws/res/11067/WEBRESOURCEdd665af7b7861caf820ac5698383f2ac)
4. 以上的这些个对象我们可以在JSP页面中直接使用

![image.png](https://note.youdao.com/yws/res/11069/WEBRESOURCE1a44b804e22aa7c8d5d5e5c8bb6046e4)

在JSP页面中：
只要是JAVA代码，就会原封不动的输出：
如果是HTML代码，就会被转换为
```java
out.write("<heml>\r\n")
```

### 8.3 JSP基础语法
任何语言都有自己的语法，JAVA中有，JSP作为java技术的一种应用，它拥有一些自己扩充的语法（了解即可！）java所有语法都支持

#### JSP表达式
![image.png](https://note.youdao.com/yws/res/11084/WEBRESOURCEd7e95abbeb17a9af3a4b012a9561811c)

####  **JSP脚本片段**
![image.png](https://note.youdao.com/yws/res/11089/WEBRESOURCE2a0c946f2da8e3c6627f30ac10100870)

####  **脚本片段的再实现**
![image.png](https://note.youdao.com/yws/res/11099/WEBRESOURCE2c33cb5af105560adb3225b455e4d162)

#### JSP声明

![image.png](https://note.youdao.com/yws/res/11095/WEBRESOURCE16d905028b2434b5c3f49fc56d256b7d)
JSP声明会被编译到生成JSP的java类中！其他的，就会被嵌入到_jspService方法中

在JSP，嵌入Java代码即可
![image.png](https://note.youdao.com/yws/res/11103/WEBRESOURCEdb5ad8ff6d6f889289a42df15b50e4c1)

JSP的注释，不会再客户端显示，HTML就会！

### 8.4 JSP指令
![image.png](https://note.youdao.com/yws/res/11108/WEBRESOURCE50227b6b713dd071162b6969f148db02)

### 8.5 九大内置对象
- PageContext  存东西
- Request  存东西
- Response
- Session   存东西
- Application【ServletContext】  存东西
- config 【ServletConfig】
- out
- page，不用了解
- exception

作用域：

![image.png](https://note.youdao.com/yws/res/11117/WEBRESOURCE08b94d0b4b47a9c50ff5c40f4a9515be)

Request：客户端向服务器发送请求，产生的数据，用户看完就没用了，比如：新闻，用户看完就没用了

Session：客户端向服务端发送请求，产生的数据，用户用完一会还有用，比如：购物车

application：客户端向服务器发送请求，产生的数据，一个用户用完了，其他用户还可能使用，比如：聊天数据

### 8.6 JSP标签、JSTL标签、EL表达式

EL表达式：
- 获取数据
- 执行运算
- 获取web开发的常用对象
- ~~调用java方法~~
![image.png](https://note.youdao.com/yws/res/11134/WEBRESOURCE82376ca841264c5bedb086d70fe0ceec)

**JSP标签**
![image.png](https://note.youdao.com/yws/res/11137/WEBRESOURCE519120c219ff35373b0f67c6a4d44c96)

JSTL表达式
JSTL便签哭的使用就是为了弥补HTML标签的不足；他自定义许多标签，可以供我们使用，标签的功能和java代码一样！

## 9. JavaBean
实体类

JavaBean有特定的写法：
- 必须要有一个无参构造器
- 属性必须私有化
- 必须有对应的get/set方法

一般用来和数据库做映射 ORM

ORM：对象关系映射
- 表 ---> 类
- 字段 ---> 属性
- 行记录 ---> 对象


| Col1 | Col2 | Col3 | Col4 |
| --- | --- | --- | --- |
| 1 | 青江1号 | 3 | 西安 |
| 2 | 青江2号 | 18 | 西安 |
| 3 | 青江2号 | 100 | 西安 |

```java
class People {
    private int id;
    private String name;
    private int age;
    private 
}
```

## 10. MVC三层架构
什么是MVC：Model、View、Controller 模型、视图、控制器

### 10.1 早些年的架构
![image.png](https://note.youdao.com/yws/res/11236/WEBRESOURCE4040495ba7712db3d2456b853484f05c)

用户直接访问控制层，控制层就可以直接操作数据库
```java
servlet-CRUD-->数据库
弊端：程序十分臃肿，不利于维护
servlet的代码中：处理请求、响应、视图跳转、处理JDBC、处理业务代码、处理逻辑代码

架构：没有什么事加一层解决不了的！
程序员调用
|
JDBC
|
Mysql Oracle SqlServer ....

```
### 10.2 MVC三层架构

![image.png](https://note.youdao.com/yws/res/11242/WEBRESOURCEf5658262e08d9bf96751950e41c7b7e5)

Model
- 业务处理：业务逻辑（Service）
- 数据持久层：CRUD（Dao）

View
- 展示数据
- 提供链接发起Servlet请求（a， form， img...)

Contoller （Servlet）
- 接受用户的请求：（req：请求参数、Session信息...）
- 交给业务层处理对应的代码
- 控制视图的跳转

```xml
登录-----> 接受用户的登录请求----> 处理用户的请求（获取用户登录的参数，username，password）----> 交给业务层处理（判断用户名密码是否正确）--->Dao层查询用户名和密码是否正确 ----> 数据库
```
## 11. Filter (==重点==)
Filter: 过滤器，用来过滤网站的数据；
- 处理中文乱码
- 登录验证...

![image.png](https://note.youdao.com/yws/res/11259/WEBRESOURCEee454a8914ad24c55a5a725d31966d0d)

Filter开发步骤：
1. 导包
2. 编写过滤器
    1. 导包不要错
    ![image.png](https://note.youdao.com/yws/res/11265/WEBRESOURCE715b5a6edd80078e32ce04497c70d873)
    2. 实现filter接口，重写对应方法即可
```java
public class CharacterEncodingFilter implements Filter {
    //初始化:web服务器启动，就已经初始化了，等待随时进行过滤
    @Override
    public void init(FilterConfig filterConfig) throws ServletException {
        System.out.println("CharacterEncodingFilter初始化");
    }

    //chain：链
    /*
        1. 过滤中的所有代码，在过滤特定请求的时候都会执行
        2. 必须要让过滤器继续同行
            chain.doFilter(request, response);
    */
    @Override
    public void doFilter(ServletRequest request, ServletResponse response, FilterChain chain) throws IOException, ServletException {
        request.setCharacterEncoding("utf-8");
        response.setCharacterEncoding("utf-8");
        response.setContentType("text/html;charset=UTF-8");
        System.out.println("CharacterEncodingFIlter执行前...");
        chain.doFilter(request, response); //让我们得请求继续走，如果不写，程序到这里就停止了
        System.out.println("CharacterEncodingFIlter执行后...");
    }

    //web服务器关闭的时候，过滤器会销毁
    @Override
    public void destroy() {
        System.out.println("CharacterEncodingFilter销毁");
    }
}
```

3. 在web.xml中配置 Filter过滤器
    
```xml
    <filter>
        <filter-name>CharacterEncodingFilter</filter-name>
        <filter-class>com.kuang.filter.CharacterEncodingFilter</filter-class>
    </filter>
    <filter-mapping>

        <filter-name>CharacterEncodingFilter</filter-name>
        <!--只要是/servlet的任何请求，会经过这个过滤器-->
        <url-pattern>/servlet/*</url-pattern>
    </filter-mapping>
```

## 12. 监听器
实现一个监听器的接口；（有N种）
1. 实现监听器的接口
```java
public class OnlineCountListener implements HttpSessionListener{
    //创建session监听：看你的一举一动
    //一旦创建session就会出发一次这个事件！
    @Override
    public void sessionCreated(HttpSessionEvent se) {
        ServletContext servletContext = se.getSession().getServletContext();

        System.out.println(se.getSession().getId());
        Integer onlineCount = (Integer)servletContext.getAttribute("OnlineCount");
        if (onlineCount == null) {
            onlineCount = new Integer(1);
        } else {
            int count = onlineCount.intValue();
            onlineCount = new Integer(count + 1);
        }

        servletContext.setAttribute("OnlineCount", onlineCount);
    }

    //销毁session监听
    @Override
    public void sessionDestroyed(HttpSessionEvent se) {
        ServletContext servletContext = se.getSession().getServletContext();
        Integer onlineCount = (Integer)servletContext.getAttribute("OnlineCount");
        if (onlineCount == null) {
            onlineCount = new Integer(0);
        } else {
            int count = onlineCount.intValue();
            onlineCount = new Integer(count - 1);
        }

        servletContext.setAttribute("OnlineCount", onlineCount);
    }

    /*
        1. 手动销毁
        2. 设置自动销毁
    */
}
```

2. web.xml中注册监听器
```xml
<listener>
    <listener-class>com.kuang.listener.OnlineCountListener</listener-class>
</listener>
```

3. 看情况是否使用，这个技术在web中基本不怎么用了

## 13. 过滤器、监听器常见应用
监听器：
```java
public class TestPanel {
    public static void main(String[] args) {
        Frame frame = new Frame("中秋节快乐"); //新建一个窗体
        Panel panel = new Panel(null);//面板
        frame.setLayout(null);//设置窗体的布局

        frame.setBackground(new Color(0,0,255));
        frame.setBounds(300,300,500,500);

        frame.setBackground(new Color(0,255,0));
        panel.setBounds(50,50,300,300);

        frame.add(panel);

        frame.setVisible(true);

        frame.addWindowListener(new WindowListener() {
            @Override
            public void windowOpened(WindowEvent e) {
                System.out.println("打开");
            }

            @Override
            public void windowClosing(WindowEvent e) {
                System.out.println("关闭...");
                System.exit(0);
            }

            @Override
            public void windowClosed(WindowEvent e) {

            }

            @Override
            public void windowIconified(WindowEvent e) {

            }

            @Override
            public void windowDeiconified(WindowEvent e) {

            }

            @Override
            public void windowActivated(WindowEvent e) {

            }

            @Override
            public void windowDeactivated(WindowEvent e) {
                
            }
        });
    }
}
```

过滤器：用户登录之后才能进入主页！用户注销后就不能进入主页了
1. 用户登录之后，向Session中放入用户的数据
2. 进入主页的时候要判断用户是否已经登录：
```java
public class SysFilter implements Filter {
    @Override
    public void init(FilterConfig filterConfig) throws ServletException {

    }

    @Override
    public void doFilter(ServletRequest servletRequest, ServletResponse servletResponse, FilterChain filterChain) throws IOException, ServletException {

        HttpServletRequest request = (HttpServletRequest) servletRequest;
        HttpServletResponse response = (HttpServletResponse) servletResponse;

        if (request.getSession().getAttribute("USER_SESSION") == null) {
            response.sendRedirect("/error.jsp");
        }


        filterChain.doFilter(request,response);
    }

    @Override
    public void destroy() {

    }
}
```

## 14. JDBC
什么是JDBC：java连接数据库！
![image.png](https://note.youdao.com/yws/res/11294/WEBRESOURCE6fea57e728e3c13e8be02a6750d25cef)

需要jar包的支持
- java.sql
- javax.sql
- mysql-connector-java... 连接驱动（必须要导入）

**实验环境搭建**
```sql
CREATE TABLE users(
	id INT PRIMARY KEY,
	`name` VARCHAR(40),
	`password` VARCHAR(40),
	email VARCHAR(60),
	birthday DATE
);

INSERT INTO users(id, `name`, `password`, email, birthday) 
	VALUES(1, '张三', '123456', 'zs@qq.com','2000-01-01');
INSERT INTO users(id, `name`, `password`, email, birthday) 
	VALUES(2, '李四', '123456', 'zs@qq.com','2000-01-01');
INSERT INTO users(id, `name`, `password`, email, birthday) 
	VALUES(3, '王五', '123456', 'zs@qq.com','2000-01-01');
INSERT INTO users(id, `name`, `password`, email, birthday) 
	VALUES(4, '老六', '123456', 'zs@qq.com','2000-01-01');
	
SELECT * FROM users
```

导入数据库依赖

```xml
<dependencies>
    <!--mysql的驱动-->
    <dependency>
        <groupId>mysql</groupId>
        <artifactId>mysql-connector-java</artifactId>
        <version>5.1.47</version>
    </dependency>
</dependencies>
```

IDEA中连接数据库

![image.png](https://note.youdao.com/yws/res/11308/WEBRESOURCE4b97c13060eafba7dead1a7bfa50087f)

JDBC固定步骤：
1. 加载驱动
2. 连接数据库，代表数据库
3. 向数据库发送SQL的对象Statement：CRUD
4. 编写SQL（根据业务，不同的SQL）
5. 执行SQL
6. 关闭连接

```java
public class TestJdbc {
    public static void main(String[] args) throws ClassNotFoundException, SQLException {
        //配置信息
        String url = "jdbc:mysql://localhost:3306/jdbc?useUnicode=true&characterEncoding=UTF-8";
        String username = "root";
        String password = "123456";

        //1. 加载驱动
        Class.forName("com.mysql.jdbc.Driver");
        //2. 连接数据库, 代表数据库
        Connection connection = DriverManager.getConnection(url, username, password);

        //3. 向数据库发送SQL的对象Statement PrepareStatement：CRUD
        Statement statement = connection.createStatement();

        //4. 别写SQL
        String sql ="select * from users";

        //5. 执行SQL，返回一个resultset结果集
        ResultSet resultSet = statement.executeQuery(sql);

        while(resultSet.next()) {
            System.out.println("id"+ resultSet.getObject("id"));
            System.out.println("name"+ resultSet.getObject("name"));
            System.out.println("password"+ resultSet.getObject("password"));
            System.out.println("email"+ resultSet.getObject("email"));
            System.out.println("birthday"+ resultSet.getObject("birthday"));
        }

        //6. 关闭连接，释放资源（一定要做）先开后关
        resultSet.close();
        statement.close();
        connection.close();

    }
}
```
**事务**
要么都成功，要么都失败！
ACID原则：保证数据的安全

```jajva
开启事务
事务提交 commit()
事务回滚 rollback()
关闭事务

转账：
A：1000
B：1000

A (900) --100--> B(1100)

```

**Junit单元测试**

依赖
```xml
<dependency>
    <groupId>org.junit.jupiter</groupId>
    <artifactId>junit-jupiter-api</artifactId>
    <version>5.7.0</version>
</dependency>
```
