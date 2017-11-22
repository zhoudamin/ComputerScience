# JPA
JPA本身就是一种ORM（对象关系映射）的实现规范

就是在框架中将对象与数据库关联起来，通过操作对象，操作数据库数据

JPA维护一个Persistence Context（持久化上下文），在持久化上下文中维护实体的生命周期。主要包含三个方面的内容：

    ORM元数据。JPA支持annotion或xml两种形式描述对象-关系映射。
    实体操作API。实现对实体对象的CRUD操作。
    查询语言。约定了面向对象的查询语言JPQL（Java Persistence Query Language）。
    
    
