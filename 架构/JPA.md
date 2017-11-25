# JPA
JPA本身就是一种ORM（对象关系映射）的实现规范

就是在框架中将对象与数据库关联起来，通过操作对象，操作数据库数据

JPA维护一个Persistence Context（持久化上下文），在持久化上下文中维护实体的生命周期。主要包含三个方面的内容：

    ORM元数据。JPA支持annotion或xml两种形式描述对象-关系映射。
    实体操作API。实现对实体对象的CRUD操作。
    查询语言。约定了面向对象的查询语言JPQL（Java Persistence Query Language）。
    
JPA定义了one-to-one、one-to-many、many-to-one、many-to-many 4种关系。

对于数据库来说，通常在一个表中记录对另一个表的外键关联；对应到实体对象，持有关联数据的一方称为owning-side，另一方称为inverse-side。


为了编程的方便，我们经常会希望在inverse-side也能引用到owning-side的对象，此时就构建了双向关联关系。 在双向关联中，需要在inverse-side定义mappedBy属性，以指明在owning-side是哪一个属性持有的关联数据。
