单词：

ResultSet 结果集

Ctrl+o 选择要重写的父类方法。

```
Attribute  //属性
```

​    

注意

~~~java
浏览器视角，和服务器视角的区别
~~~

http 超文本协议

Servlet的生命周期

~~~java
servlet不运行在java虚拟机中m由Servlet容器负责管理其整个生命周期
~~~

![image-20250904104520206](%E5%9B%BE%E7%89%87/image-20250904104520206.png)

~~~java
容器像jvm虚拟机一样管理java对象
    init（）初试化
    server对象（一个程序）
~~~

![image-20250904104741865](%E5%9B%BE%E7%89%87/image-20250904104741865.png)

~~~java
自动装入
~~~

将一个普通类转变为server类

~~~java
继承HttpServlent
~~~

dependenty

![image-20250907145713618](C:/Users/86159/AppData/Roaming/Typora/typora-user-images/image-20250907145713618.png)

~~~java
//先本机的tomcat发送一次请求。
//javaWebDemo 打包的项目（从tomcat中中找到）
~~~

~~~java
//直接去搜索一个网址它对应的请求是get （给参数，获取数据）//调用doGet方法
~~~

通过webservlet来声明servlet

![03024b81-1633-4b60-9e1f-9a1a64903f55](../%E6%96%B0%E5%BB%BA%E6%96%87%E4%BB%B6%E5%A4%B9%20(2)/xwechat_files/wxid_pnxxjq8mi47s22_c95e/temp/InputTemp/03024b81-1633-4b60-9e1f-9a1a64903f55.png)

asyncSupported 异步操作

~~~java
先执行一些东西，跳过一些东西，网页的加载
~~~

~~~java
//通过web.xml配置
<servlet>
    <servlet-name>DemoServlet</servlet-name>
    <servlet-class>包名+类名 com.qst.DemoServlet</servlet-class> //给那个类的
    </servlet>
 //访问路径单独配置
 <servlet-mapping>
         <servlet-name>DemoServlet</servlet-name>//和上面的名称保持一致
        <url-pattern>/demo</url-pattern>
        <servlet-mapping>
        //不好用
~~~

### 超链接

![1de3e9e0-0ea9-487d-aac9-5348de7c01d9](../%E6%96%B0%E5%BB%BA%E6%96%87%E4%BB%B6%E5%A4%B9%20(2)/xwechat_files/wxid_pnxxjq8mi47s22_c95e/temp/InputTemp/1de3e9e0-0ea9-487d-aac9-5348de7c01d9.png)

![eb835d31-8364-4d3c-b7be-16c863c80947](../%E6%96%B0%E5%BB%BA%E6%96%87%E4%BB%B6%E5%A4%B9%20(2)/xwechat_files/wxid_pnxxjq8mi47s22_c95e/temp/InputTemp/eb835d31-8364-4d3c-b7be-16c863c80947.png)

~~~java
//超链接都调用doGet（）方法
~~~

~~~java
注意
    //前端资源的根在容器，超链接在后端应该具体的对应的程序 
    /之前的表示gen
~~~

```
PreparedStatement  准备声明。
```

### 1. **`Connection` 是什么？**

- `Connection` 是 JDBC 提供的 **数据库连接对象**，来自 `java.sql.Connection` 接口。

- 你可以把它理解为：
   👉 **Java 程序和数据库之间的“通道”**。

- 通过 `Connection`，你可以：

  - 创建 `Statement` / `PreparedStatement` 执行 SQL
  - 控制事务（提交 `commit` / 回滚 `rollback`）
  - 关闭连接 `connection.close()`

  

  

  

  ### 1. **`PreparedStatement` 是什么？**

  - `PreparedStatement` 是 JDBC 提供的 **预编译 SQL 语句对象**，继承自 `Statement`。
  - 它的主要作用是：
    1. 先把 SQL 语句发送给数据库进行 **预编译**（只做一次）。
    2. 后续只需要填充 `?` 参数并执行，效率更高。
    3. 避免字符串拼接，防止 **SQL 注入攻击**。
    4. 代码更简洁、安全。

  ------

  ### 2. **`connection.prepareStatement(sql)` 做了什么？**

  - `connection` 是你和数据库之间的 **通道对象**。
  - 调用 `prepareStatement(sql)` 相当于告诉数据库：
     👉 “我要执行这条 SQL，请先编译好”。
  - 结果返回一个 `PreparedStatement` 对象，你可以对其中的 `?` 占位符赋值，然后执行。





​	超链接

~~~java
<>
~~~

parameter 参数

~~~java
<from action = "demo" method = "post">
~~~

~~~java
//get请求参数明文
//post请求隐藏
~~~

![image-20250915150358354](C:/Users/86159/AppData/Roaming/Typora/typora-user-images/image-20250915150358354.png)

重定向

![image-20250915150813642](C:/Users/86159/AppData/Roaming/Typora/typora-user-images/image-20250915150813642.png)

~~~java
//先返回客户端，之后重新发送请求
//可以重定向到任何网址
~~~

`/` 是 **相对于当前 Web 应用的根路径**：我们的项目如：prject

~~~java
servlitA(){
    resp.sendRedirect("servletB") //重定向到B 
}
  serlitb
      //Redirect 重定向
      
      //重定向对应两次请求，两次相应
      //重定向是切换不同的后端服务
~~~

请求转发

![image-20250915152105102](C:/Users/86159/AppData/Roaming/Typora/typora-user-images/image-20250915152105102.png)

~~~java
//把请求直接给另外一个servlet
//请求的地址不变 是url是请求的地址 浏览器显示的是响应的结果 
//局限：
//只能在服务器内部进行，不能调用外部的服务器

~~~

![image-20250915152628049](C:/Users/86159/AppData/Roaming/Typora/typora-user-images/image-20250915152628049.png)

~~~java
//好长的函数
~~~

有一技之长，总是好的

异步操作

~~~java
//需要等待的数据不在等待，如：先加载的网页框架。
//网页的逐步加载
~~~

~~~java
//servlet的定义
//首先继承HttpServlet 实现doGet（） doPost（） 方法
//之后@webServlet("/demo") 声明，一般是配置路径
`/` 是 **相对于当前 Web 应用的根路径**：我们的项目如：prject
 //之后在通过jsp发送请求
    //httpservletRequt httpservletResponse  请求和响应对象
 //重定向和请求转发
  
~~~

~~~java
req.getParameter
~~~

### Servlet核心接口

![image-20250915163420267](C:/Users/86159/Pictures/image-20250915163420267.png)



![image-20250915163711912](%E5%9B%BE%E7%89%87/image-20250915163711912.png)

~~~JAVAZ
servlet对象通过ServletContext对象来访问容器中的的各种资源
~~~

容器中的数据是共享的 

servletContext对象可以理解为容器内的一个共享空间，重点它通过k-v键值对储存

![image-20250915164307260](%E5%9B%BE%E7%89%87/image-20250915164307260.png)

应用域 里面的数据的增删

一个容器中含有多个web应用 每一个对应一个servletContext 可以相互访问 



### HTTP协议

![image-20250915170313243](C:/Users/86159/AppData/Roaming/Typora/typora-user-images/image-20250915170313243.png)





![image-20250915170647364](%E5%9B%BE%E7%89%87/image-20250915170647364.png)

~~~JAVA
//结构说明
~~~

