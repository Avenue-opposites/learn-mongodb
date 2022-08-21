# 基本概念
    * 数据库(database)
    * 集合(collection)
    * 文档(document)
    -在MongoDB中数据库和集合不需要手动创建,当我们创建文档时,如果当前数据库或集合不存在,则会自动创建。
    -如果在插入文档时,没有指定_id属性,则数据库自动分配添加。该属性为唯一标识。
    -_id属性可以自定义,但是要确保唯一性。
# 基本指令
    * show dbs(database) 查看当前所有的数据库
    * use <db> 进入到指定数据库中
    * db 表示当前所在数据库
    * show collections 查看当前数据库所有的集合
# 数据库的增删改查
    - 增加
        * db.<collection>.insert(Object||Array) 向集合中插入一个或多个文档
        * db.<collection>.insertOne(Object) 
        * db.<collection>.push() 向数组中添加一个数据
        * db.<collection>.addToset() 向数组中添加一个数据,如果数组中有则添加失败
    - 删除
        * db.<collection>.remove() 删除符合条件的文档,条件和find()一样
        * db.<collection>.drop() 删除集合 如果删除的时候就就只有一个集合,那就会把数据库删除
        * db.dropoDatabase() 删除数据库
    - 修改
        * db.<collection>.update(Object,Object) 修改符合查询条件的文档,但是会替换原来的对象
        * db.<collection>.update(Object,{$set:{object}}) 修改符合查询条件的文档,添加对象属性 
        * db.<collection>.update(Object,{$unset:{object}}) 修改符合查询条件的文档,删除对象属性 
    - 查询
        * db.<collection>.find(Object,{设置投影规则}) 在集合中查询所有文档和符合规则的文档
        * db.<collection>.findOne(Object) 查询符合条件的第一个文档
        * db.<collection>.find().count() 查询的文档数量
            如果查询内嵌文档可以使用.的形式,不过属性名要加引号s
# 数据库的运算符
    * gt 大于某个数
    * gte 大于等于某个数
    * lt 小于
    * lte 小于等于
    * litme 限制数据显示数量
    * skip 跳过显示数据数量
    * inc 增加指定的值
    * set 添加值,没有则创建
    * sort 排序
# 文档之间的关系
    * 一对一(one to one)
    * 一对多
    * 多对多
# Mongoose(ODM)对象文档模型
    * Schema 模式对象 定义数据库中的文档约束
    * Model model对象作为collecction中的文档表示,相当于代表集合
    * Document 代表数据库文档
