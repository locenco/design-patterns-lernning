- 目的：使用不同的标准来过滤一组对象，通过逻辑运算以解耦的方式把它们连接起来；
- 实现：制定不同的规则来对一组对象进行过滤，然后对过滤结果进行分组。
涉及角色
过滤器模式包含如下两个角色：

- (1) AbstractFilter（抽象过滤器角色）：在客户端可以调用它的方法，在抽象过滤器角色中可以知道相关的（一个或者多个）子系统的功能和责任；在正常情况下，它将所有从客户端发来的请求委派到相应的实现类去，传递给相应的实现类对象处理。
- (2) ConcreteFilter（具体滤器角色）：在客户端可以调用它的方法，在具体滤器角色会对目标对象集合进行逻辑过滤，最后再返回一个过滤后的集合。
- (3) Subject（被过滤角色）：在软件系统中可以有一个或者多个目标角色，在具体过滤器中会对目标角色进行逻辑处理以查看是否是我想要的。
————————————————
版权声明：本文为CSDN博主「尘埃安然」的原创文章，遵循 CC 4.0 BY-SA 版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/weixx3/article/details/80233991

