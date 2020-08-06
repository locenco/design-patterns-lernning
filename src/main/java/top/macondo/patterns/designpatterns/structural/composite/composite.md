## 组合模式基本内容
- 意图：将对象组合成树形结构以表示"部分-整体"的层次结构。组合模式使得用户对单个对象和组合对象的使用具有一致性。
- 主要解决：它在我们树型结构的问题中，模糊了简单元素和复杂元素的概念，客户程序可以像处理简单元素一样来处理复杂元素，从而使得客户程序与复杂元素的内部结构解耦。
- 何时使用： 1、您想表示对象的部分-整体层次结构（树形结构）。 2、您希望用户忽略组合对象与单个对象的不同，用户将统一地使用组合结构中的所有对象。
- 如何解决：树枝和叶子实现统一接口，树枝内部组合该接口。
- 关键代码：树枝内部组合该接口，并且含有内部属性 List，里面放 Component。
- 应用实例： 1、算术表达式包括操作数、操作符和另一个操作数，其中，另一个操作符也可以是操作数、操作符和另一个操作数。 2、在 JAVA AWT 和 SWING 中，对于 Button 和 Checkbox 是树叶，Container 是树枝。
- 优点： 1、高层模块调用简单。 2、节点自由增加。
- 缺点：在使用组合模式时，其叶子和树枝的声明都是实现类，而不是接口，违反了依赖倒置原则。
- 使用场景：部分、整体场景，如树形菜单，文件、文件夹的管理。
- 注意事项：定义时为具体类。


## 组合模式 主要包含三种角色：

- 抽象根节点（Component）：
定义系统各层次对象的共有方法和属性，可以预先定义一些默认行为和属性；
- 树枝节点（Composite）：
定义树枝节点的行为，存储子节点，组合树枝节点和叶子节点形成一个树形结构；
- 叶子节点（Leaf）：
叶子节点对象，其下再无分支，是系统层次遍历的最小单位；
## 组合模式在代码具体实现上，有两种不同的方式：

- 透明模式：
> 把组合（树节点）使用的方法放到统一行为（Component）中，让不同层次（树节点，叶子节点）的结构都具备一致行为；

- 安全组合模式 
> 把系统各层次公有的行为定义在 Component 中，把组合（树节点）特有的行为（管理子类增加，删除等）放到自身（Composite）中。
这样做的好处是接口定义职责清晰，符合设计模式 单一职责原则 和 接口隔离原则；
缺点是客户需要区分树枝节点（Composite）和叶子节点（Leaf），这样才能正确处理各个层次的操作，客户端无法依赖抽象（Component），
违背了设计模式 依赖倒置原则。
注意的问题：

有时候系统需要遍历一个树枝结构的子构件很多次，这时候可以考虑把遍历子构件的结构存储在父构件里面作为缓存。
客户端尽量不要直接调用树叶类中的方法（在我上面实现就是这样的，创建的是一个树枝的具体对象;），而是借用其父类（Graphics）的多态性完成调用，这样可以增加代码的复用性。
### 组合模式的使用场景
在以下情况下应该考虑使用组合模式：

当想表达对象的部分-整体的层次结构时。
希望用户忽略组合对象与单个对象的不同，用户将统一地使用组合结构中的所有对象时。

### 参考地址
[https://www.jianshu.com/p/c7f19e5310f9](https://www.jianshu.com/p/c7f19e5310f9)