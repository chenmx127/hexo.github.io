vuex是状态管理，是为了解决跨组件之间数据共享问题的，一个组件的数据变化会映射到使用这个数据的其他组件当中。如果刷新页面，之前存储的vuex数据全部都会被初始化掉。

localStorage是H5提供的一个更简单的数据存储方式，之前是用cookie存放数据，但是cookie的数据量太小，所以就用localStorage，它可以有5M的限制，不受刷新页面的控制，长久保存。

vuex和全局变量的区别：

1，【响应式】vuex的状态存储是响应式的，当Vue组件从store中读取状态的时候，若store中的状态发生变化，那么相应的组件也会得到高效更新。

2，【不能直接改变store】不能直接改变store的变化，改变store中状态的唯一途径是commit mutation。方便于跟踪每一个状态的变化。

get与post区别

最直观的区别就是GET把参数包含在URL中，POST通过request body传递参数。

- GET在浏览器回退时是无害的，而POST会再次提交请求。
- GET产生的URL地址可以被Bookmark，而POST不可以。
- GET请求会被浏览器主动cache，而POST不会，除非手动设置。
- GET请求只能进行url编码，而POST支持多种编码方式。
- GET请求参数会被完整保留在浏览器历史记录里，而POST中的参数不会被保留。
- GET请求在URL中传送的参数是有长度限制的，而POST么有。
- 对参数的数据类型，GET只接受ASCII字符，而POST没有限制。
- GET比POST更不安全，因为参数直接暴露在URL上，所以不能用来传递敏感信息。
- GET参数通过URL传递，POST放在Request body中。

 