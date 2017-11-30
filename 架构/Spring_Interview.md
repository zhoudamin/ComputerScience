# Spring--Interview
## 使用Spring框架能带来哪些好处？
Dependency Injection(DI) 方法使得构造器和JavaBean properties文件中的依赖关系一目了然。

与EJB容器相比较，IoC容器更加趋向于轻量级。这样一来IoC容器在有限的内存和CPU资源的情况下进行应用程序的开发和发布
就变得十分有利。

Spring并没有闭门造车，Spring利用了已有的技术比如ORM框架、logging框架、J2EE、Quartz和JDK Timer，以及其他视图技术。

Spring框架是按照模块的形式来组织的。由包和类的编号就可以看出其所属的模块，开发者仅仅需要选用他们需要的模块即可。

要测试一项用Spring开发的应用程序十分简单，因为测试相关的环境代码都已经囊括在框架中了。更加简单的是，利用JavaBean
形式的POJO类，可以很方便的利用依赖注入来写入测试数据。

Spring的Web框架亦是一个精心设计的Web MVC框架，为开发者们在web框架的选择上提供了一个除了主流框架比如Struts、
过度设计的、不流行web框架的以外的有力选项。

Spring提供了一个便捷的事务管理接口，适用于小型的本地事物处理（比如在单DB的环境下）和复杂的共同事物处理
（比如利用JTA的复杂DB环境）。


