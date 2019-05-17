#SpringBoot基础讲义
##学习目标
```
1. 能够理解Spring的优缺点
2. 能够理解SpringBoot的特点 
3. 能够理解SpringBoot的核心功能
4. 能够搭建SpringBoot的环境
5. 能够完成application.properties配置文件的配置
6. 能够完成application.yml配置文件的配置
7. 能够使用SpringBoot集成Mybatis
8. 能够使用SpringBoot集成Junit
9. 能够使用SpringBoot集成SpringData JPA
```
##今日重点
```
1. 能够搭建SpringBoot的环境
2. 能够完成application.properties配置文件的配置
3. 能够完成application.yml配置文件的配置
```
#第1节课
##1.1 本节知识点
```
1. Spring的优缺点分析
2. SpringBoot的特点
3. SpringBoot的核心功能概述
4. SpringBoot快速入门-环境搭建
```
##1.2 本节目标
```
1. 能够理解Spring的优缺点
2. 能够理解SpringBoot的特点 
3. 能够理解SpringBoot的核心功能
4. 能够根据文档搭建SpringBoot环境 (掌握)
```
##1.3课程内容
###1.3.1 SpringBoot课程内容介绍
**视频信息**
```
视频名称: 01-SpringBoot课程内容介绍
视频时长: 02:39
```
**小节内容**
```
概述课程要点:	
	1,SpringBoot简介
	2,SpringBoot快速入门
	3,SpringBoot原理分析
	4,SpringBoot的配置文件
	5,SpringBoot与整合其他技术
```
**补充**
```
课程最后又加入了一个Redis的整合
我们今天学习的重点是学习配置,而不是完成功能
```
###1.3.2 SpringBoot课程学习目标
**视频信息**

```
视频名称: 02-SpringBoot课程学习目标
视频时长: 02:58
```
**小节内容**
```
学习目标介绍
今日重点:
	1. 能够搭建SpringBoot的环境
	2. 能够完成application.properties配置文件的配置
	3. 能够完成application.yml配置文件的配置
	4. 能够根据文档整合其他框架
	5. 理解原理
```
**补充**
```
整合部分是要求大家能够根据文档完整整合即可,无需记忆,但是要理解配置文件
```
###1.3.3 Spring的优缺点分析
**视频信息**
```
视频名称: 03-Spring的优缺点分析
视频时长: 07:37
```
**小节内容**
```
Spring 优点:
	1) 通过AOP,IOC,DI 完成了既往复杂的EJB 的开发
Spring缺点
	1) 配置复杂从而占用了开发人人员的大量时间和精力.
项目开发过程中的其他缺点:
	项目jar 包依赖不好管理,一旦出现版本冲突需要消耗大量的时间去调试
```
**补充**
```
Spring 优点:
	IOC容器,解耦
	DI机制降低了业务对象替换的复杂性	
	AOP 面向切面编程为事务,日志等服务提供了支持
```
###1.3.4 SpringBoot的特点
**视频信息**
```
视频名称: 04-SpringBoot的特点
视频时长: 05:58
```
**小节内容**
```
SpringBoot特点及优势说明:
1) SpringBoot 是为解决上述问题而生的
2) SpringBoot不是对Spring功能上的增强，而是提供了一种快速使用Spring的方式,   SpringBoot 能让我们快速的搭建Spring 项目
3) SpringBoot 是约定优于配置的
4) SpringBoot 没有代码生成，也无需XML配置就能完成项目的搭建
5) 提供了一些大型项目中常见的非功能性特性，如嵌入式服务器、安全、指标，健康检测、外部配置等
```
**补充**
```

```
###1.3.5 SpringBoot的核心功能概述
**视频信息**
```
视频名称: 05-SpringBoot的核心功能概述
视频时长: 03:48
```
**小节内容**

```
- 起步依赖
  简单的说，起步依赖就是将具备某种功能的坐标打包到一起，并提供一些默认的功能
- 自动配置
    Spring Boot的自动配置是一个运行时（更准确地说，是应用程序启动时）的过程，考虑了众多因素，才决定	     Spring配置应该用哪个，不该用哪个。该过程是Spring自动完成的。
```
**补充**
```

```
###1.3.6 SpringBoot快速入门-环境搭建
**视频信息**
```
视频名称: 06-SpringBoot快速入门-环境搭建
视频时长: 08:05
```
**小节内容**

1.创建maven 工程

2.导入坐标

SpringBoot要求，项目要继承SpringBoot的起步依赖spring-boot-starter-parent

```xml
<parent>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-parent</artifactId>
    <version>2.0.1.RELEASE</version>
</parent>
```
SpringBoot要集成SpringMVC进行Controller的开发，所以项目要导入web的启动依赖

```xml
<dependencies>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-web</artifactId>
    </dependency>
</dependencies>
```

编写SpringBoot引导类

```java
@SpringBootApplication
public class MySpringBootApplication {
    public static void main(String[] args) {
        SpringApplication.run(MySpringBootApplication.class);
    }
}
```



**补充**

```
SpringBoot 本身就是基于maven 的
```
#第2节课
##2.1 本节知识点
```
1. SpringBoot快速入门-Controller编写和测试
2. SpringBoot快速入门-入门解析
3. SpringBoot工程的热部署
4. IDEA快速创建SpringBoot工程
5. SpringBoot的原理分析-起步依赖-parent
6. SpringBoot的原理分析-起步依赖-web
```
##2.2 本节目标
```

```

##2.3课程内容
###2.3.1 SpringBoot快速入门-Controller编写和测试
**视频信息**
```
视频名称: 07-SpringBoot快速入门-Controller编写和测试
视频时长: 03:26
```
**小节内容**

编写Controller 启动,并访问

```java
@ResponseBody:
	表示返回的是一个字符串;
```
**补充**
```

```
###2.3.2 SpringBoot快速入门-入门解析
**视频信息**
```
视频名称: 08-SpringBoot快速入门-入门解析
视频时长: 05:57
```
**小节内容**
```
1) 所有的项目都需要继承Parent 坐标
2) 只需要导入启动坐标即可
3) SpringApplication.run(参数是标注了@SpringBootApplication注解的类);
```
**补充**
```

```
###2.3.3 SpringBoot工程的热部署
**视频信息**
```
视频名称: 09-SpringBoot工程的热部署
视频时长: 05:45
```
**小节内容**

1) 导入坐标

```xml
<!--热部署配置-->
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-devtools</artifactId>
</dependency>
```
Idea 需要特殊配置

![](img\19.png)

然后 Shift+Ctrl+Alt+/，选择Registry

![](img\20.png)



**补充**

```

```
###2.3.4 IDEA快速创建SpringBoot工程
**视频信息**
```
视频名称: 10-IDEA快速创建SpringBoot工程
视频时长: 08:29
```
**小节内容**

```
Idea 快速搭建SpringBoot 项目
```
**补充**
```
0)需要联网
1)报错解决方案 : Artficate 改为小写即可
```
###2.3.5 SpringBoot的原理分析-起步依赖-parent
**视频信息**
```
视频名称: 11-SpringBoot的原理分析-起步依赖-parent
视频时长: 05:56
```
**小节内容**
```
1) parent 规定了自定义项目的配置文件路径
2) 规定了自动一项目配置文件的格式及文件命名规则
3) parent  规定了依赖jar 的版本号
```
**补充**
```
注意:
	parent 只是一堆规则,不导入具体的依赖
```
###2.3.6 SpringBoot的原理分析-起步依赖-web
**视频信息**
```
视频名称: 12-SpringBoot的原理分析-起步依赖-web
视频时长: 03:50
```
**小节内容**
```
web 
	例如导入了jackson的依赖
	例如导入了tomcat的依赖
web 负责具体的jar 导入

```
**补充**
```
web-starter 规定了web 项目具体依赖的jar ,并导入项目
parent 规定了具体jar 版本
```
#第3节课
##3.1 本节知识点
```
1. SpringBoot的原理分析-自动配置1
2. SpringBoot的原理分析-自动配置2
3. SpringBoot的原理分析-自动配置3
4. SpringBoot的配置文件的类型和作用
5. SpringBoot的配置文件-yml文件的简介
```
##3.2 本节目标
```

```
##3.3课程内容
###3.3.1 SpringBoot的原理分析-自动配置1
**视频信息**
```
视频名称: 13-SpringBoot的原理分析-自动配置1
视频时长: 05:52
```
**小节内容**

```
自动配置:
	@SpringBootApplication
		-@SpringBootConfiguration 和 @Configuration 同样的功能 告诉程序当前类是一个配置类
		-@ComponentScan 自动包扫描 默认扫描 当前包及其子包下面的类
		-@EnableAutoConfiguration 
			
```
**补充**
```

```
###3.3.2 SpringBoot的原理分析-自动配置2
**视频信息**
```
视频名称: 14-SpringBoot的原理分析-自动配置2
视频时长: 11:46
```
**小节内容**
```
@EnableAutoConfiguration
	是否自动配置的开关,配置后自动加载(Import)配置文件
	spring-boot-autoconfigure-2.0.1.RELEASE.jar
		\META-INF\spring.factories
	进而完成对应的配置
每个Auto 都有自动配置,我们如果需要覆盖SpringBoot 的配置,需要自己编写配置文件
命名
```
**补充**
```

```
###3.3.3 SpringBoot的原理分析-自动配置3
**视频信息**
```
视频名称: 15-SpringBoot的原理分析-自动配置3
视频时长: 05:13
```
**小节内容**
```properties
我们可以修改配置
#服务器端口号
server.port=8081
#当前web应用名称
server.servlet.context-path=/demo
	
```
**补充**
```

```
###3.3.4 SpringBoot的配置文件的类型和作用
**视频信息**

```
视频名称: 16-SpringBoot的配置文件的类型和作用
视频时长: 03:16
```
**小节内容**
```
作用:
	1) 覆盖SpringBoot 的默认配置
	2) 编写自己的配置信息
类型:
	properties,yml.yaml
```
**补充**
```
1) 配置文件有路径要求 放在  /src/main/resources 下
2) 配置文件名称必须以  application 开头
3) 格式必须是properties 或ymal或yml 格式
-----------------------------
配置文件的名称约定: 
    ConfigFileApplicationListener.java
    文件中定义了配置文件存放的目录
    必须是 根目录下或者 config 目录下
    默认名称必须是 application.properties 或者 application.yml,yaml
-----------------------------

SpringBoot 是基于约定的

SpringBoot 的约定优于配置:
	1) 配置文件的路径和名称是由格式要求的
	2) 配置文件中的属性名称是约定好的
-------------
SpringBoot的配置文件，主要的目的就是对配置信息进行修改的，但在配置时的key从哪里去查询呢？我们可以查阅SpringBoot的官方文档

文档URL：https://docs.spring.io/spring-boot/docs/2.0.1.RELEASE/reference/htmlsingle/#common-application-properties
```
```

```



###3.3.5 SpringBoot的配置文件-yml文件的简介

**视频信息**
```
视频名称: 17-SpringBoot的配置文件-yml文件的简介
视频时长: 03:39
```
**小节内容**
```
YML文件格式是YAML (YAML Aint Markup Language)编写的文件格式，YAML是一种直观的能够被电脑识别的的数据数据序列化格式，并且容易被人类阅读，容易和脚本语言交互的，可以被支持YAML库的不同的编程语言程序导入，比如： C/C++, Ruby, Python, Java, Perl, C#, PHP等。YML文件是以数据为核心的，比传统的xml方式更加简洁。

和 json,xml,properties 类似 另一种另一种通用的文件格式
```
**补充**
```

```
#第4节课
##4.1 本节知识点
```
1. SpringBoot的配置文件-yml文件的的普通属性和对象属性
2. SpringBoot的配置文件-yml文件的集合配置
3. SpringBoot的配置文件-通过@Value映射数据
4. SpringBoot的配置文件-通过@ConfigurationProperties映射数据
5. SpringBoot的配置文件-configuration-processor作用
```
##4.2 本节目标
```
掌握yml 格式的编写
会解析自定义配置文件并注入我们的Java代码
```
##4.3课程内容
###4.3.1 SpringBoot的配置文件-yml文件的的普通属性和对象属性
**视频信息**
```
视频名称: 18-SpringBoot的配置文件-yml文件的的普通属性和对象属性
视频时长: 08:13
```
**小节内容**

#####  配置普通数据

- 语法： key:  value

- 示例代码：

- ```yaml
  name: haohao
  ```

- 注意：value之前有一个空格

#####  配置对象数据

- 语法： 

  ​	key: 

  ​		key1:  value1

  ​		key2:  value2

  ​	或者：

  ​	key: {key1:  value1,key2:  value2}

- 示例代码：

- ```yaml
  person:
    name: haohao
    age: 31
    addr: beijing
  
  #或者
  
  person: {name: haohao,age: 31,addr: beijing}
  ```

- 注意：key1前面的空格个数不限定，在yml语法中，相同缩进代表同一个级别

**补充**

```
缩进请不要使用 \tab  Idea 不报错更换开发工具可能就有问题了,尽量使用两个空格代替\tab
```
###4.3.2 SpringBoot的配置文件-yml文件的集合配置
**视频信息**
```
视频名称: 19-SpringBoot的配置文件-yml文件的集合配置
视频时长: 05:23
```
**小节内容**

##### 配置数组（List、Set）数据

- 语法： 

  ​	key: 

  ​		-  value1

  ​		-  value2

  或者：

  ​	key: [value1,value2]

- 示例代码：

- ```yaml
  city:
    - beijing
    - tianjin
    - shanghai
    - chongqing
    
  #或者
  
  city: [beijing,tianjin,shanghai,chongqing]
  
  #集合中的元素是对象形式
  student:
    - name: zhangsan
      age: 18
      score: 100
    - name: lisi
      age: 28
      score: 88
    - name: wangwu
      age: 38
      score: 90
  ```

- 注意：value1与值间的 - 之间存在一个空格

**补充**

```
对象一样
map:
  key1: value1
  key2: value2
```
###4.3.3 SpringBoot的配置文件-通过@Value映射数据
**视频信息**
```
视频名称: 20-SpringBoot的配置文件-通过@Value映射数据
视频时长: 06:40
```
**小节内容**
```
@Value 获取配置文件的信息
格式
 @Value("${person.name}")
    private String name;
  优点:
  	方便直观
  缺点:
  	繁琐
```
**补充**
```

```
###4.3.4 SpringBoot的配置文件-通过@ConfigurationProperties映射数据
**视频信息**
```
视频名称: 21-SpringBoot的配置文件-通过@ConfigurationProperties映射数据
视频时长: 03:41
```
**小节内容**
```
@ConfigurationProperties(prefix = "person")
1) 需要给定前缀
2) 需要set 方法才能注入数据
3) get 方法是方法是方便其他文件配置
```
**补充**
```
我们一般单独定义一个配置类配注入配置数据,
```
###4.3.5 SpringBoot的配置文件-configuration-processor作用
**视频信息**
```
视频名称: 22-SpringBoot的配置文件-configuration-processor作用
视频时长: 04:42
```
**小节内容**

configuration-processor
配置是我们先定义一个配置文件,然后我们在写yml配置文件会有提示

```xml
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-configuration-processor</artifactId>
	<optional>true</optional>
</dependency>
```
**补充**
```
配置完毕可能依旧配有提示,
 	解决方法:
 	重新运行一下启动类main 方法
```
#第5节课
##5.1 本节知识点
```
1. SpringBoot集成其他技术-集成Mybatis1
2. SpringBoot集成其他技术-集成Mybatis2
3. SpringBoot集成其他技术-集成Junit
```
##5.2 本节目标
```
掌握整合的步骤
能根据文档整合mybiats 
```
##5.3课程内容
###5.3.1 SpringBoot集成其他技术-集成Mybatis1
**视频信息**
```
视频名称: 23-SpringBoot集成其他技术-集成Mybatis1
视频时长: 14:28
```
**小节内容**
```
步骤:
	1) 添加Mybatis的起步依赖
	2) 添加数据库驱动坐标
	3) 添加数据库连接信息
	4) 创建user表
	5) 创建实体Bean
	6) 编写Mapper
	7) 配置Mapper映射文件(在dao 层上增加Mapper 注解 )
	8) 在application.properties中添加mybatis的信息
说明:
	1)Mybatis的起步依赖 只负责导入它依赖的包,但是数据库的jar包需要我们自己导入
	2) 需要我们自己配置数据库信息
	
```
**补充**
```

```
###5.3.2 SpringBoot集成其他技术-集成Mybatis2
**视频信息**
```
视频名称: 24-SpringBoot集成其他技术-集成Mybatis2
视频时长: 03:59

```
**小节内容**
```
编写测试Controller 测试数据库连接及配置

```



**补充**
```
--- 
SpringBoot 的启动类会加载所有starter 中的启动类
所以当我们引入另一个starter 启动类时会自动集成

```
###5.3.3 SpringBoot集成其他技术-集成Junit
**视频信息**
```
视频名称: 25-SpringBoot集成其他技术-集成Junit
视频时长: 05:30
```
**小节内容**

起步依赖

```xml
<!--测试的起步依赖-->
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-test</artifactId>
    <scope>test</scope>
</dependency>
```
编写测试类

````java
	@RunWith(SpringRunner.class)
    @SpringBootTest(classes = MySpringBootApplication.class)
    public class MapperTest {

        @Autowired
        private UserMapper userMapper;

        @Test
        public void test() {
            List<User> users = userMapper.queryUserList();
            System.out.println(users);
        }
    }

````

SpringRunner继承自SpringJUnit4ClassRunner，使用哪一个Spring提供的测试测试引擎都可以

```java
public final class SpringRunner extends SpringJUnit4ClassRunner 
```

@SpringBootTest的属性指定的是引导类的字节码对象

**补充**

```
1) 导入启动器坐标
2) 添加配置文件
```
#第6节课
##6.1 本节知识点
```
1. SpringBoot集成其他技术-集成SpringDataJPA
2. SpringBoot集成其他技术-集成Redis
```
##6.2 本节目标
```
能根据文档整合SpringDataJPA
能根据文档整合Redis
```
##6.3课程内容
###6.3.1 SpringBoot集成其他技术-集成SpringDataJPA
**视频信息**
```
视频名称: 26-SpringBoot集成其他技术-集成SpringDataJPA
视频时长: 11:11
```
**小节内容**
```
1) 添加Spring Data JPA的起步依赖
2) 添加数据库驱动依赖
3) 在application.properties中配置数据库和jpa的相关属性
4) 创建实体配置实体
5) 编写UserRepository(DAO)
6) 编写测试类
```
**补充**
```properties

# 如果不配置注解 系统会自动帮助我们映射数据库字段
# 注意 如果是驼峰式命名则数据库表及字段需要下划线支持
# 例如 字段名称 为 userName 则 自动生成sql 查询的是user_name

# 如果程序是驼峰式命名并且想和数据库字段名一直的话需要增加如下配置
# 如果想类名成一样的话 改为如下配置
spring.jpa.hibernate.naming.physical-strategy=org.hibernate.boot.model.naming.PhysicalNamingStrategyStandardImpl


```
###6.3.2 SpringBoot集成其他技术-集成Redis
**视频信息**
```
视频名称: 27-SpringBoot集成其他技术-集成Redis
视频时长: 16:44
```
**小节内容**
## 

#### 添加redis的起步依赖

```xml
<!-- 配置使用redis启动器 -->
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-data-redis</artifactId>
</dependency>
```

#### 配置redis的连接信息

```properties
#Redis
spring.redis.host=127.0.0.1
spring.redis.port=6379
```

####  注入RedisTemplate测试redis操作

```java
@RunWith(SpringRunner.class)
@SpringBootTest(classes = SpringbootJpaApplication.class)
public class RedisTest {

    @Autowired
    private UserRepository userRepository;

    @Autowired
    private RedisTemplate<String, String> redisTemplate;

    @Test
    public void test() throws JsonProcessingException {
        //从redis缓存中获得指定的数据
        String userListData = redisTemplate.boundValueOps("user.findAll").get();
        //如果redis中没有数据的话
        if(null==userListData){
            //查询数据库获得数据
            List<User> all = userRepository.findAll();
            //转换成json格式字符串
            ObjectMapper om = new ObjectMapper();
            userListData = om.writeValueAsString(all);
            //将数据存储到redis中，下次在查询直接从redis中获得数据，不用在查询数据库
            redisTemplate.boundValueOps("user.findAll").set(userListData);
            System.out.println("===============从数据库获得数据===============");
        }else{
            System.out.println("===============从redis缓存中获得数据===============");
        }

        System.out.println(userListData);

    }

}
```



**补充**
```
整体来看不论SpringBoot 整合第三方框架
	1) 导入起步依赖
	2) 增加配置文件
 	
```

# 整体补充

```
-- 动态标签
<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-thymeleaf</artifactId>
</dependency>
---------html 
<span th:text="${key}"></span>
----------
https://www.cnblogs.com/zjfjava/p/6892576.html
```

