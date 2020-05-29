### webpack 打包的时候发生了什么？
基本上就是module被包装成了函数隔离了scope，同时export被编译成了持有webpackrequire函数
结果的的变量。所有的包装的modules被放到了bundle的数组里。然后webpack的运行时
来处理数组并运行我们的code。**运行到的函数模块被暂存了起来。**

**什么是闭包？**
是函数和它周围的词法作用域里的state的组合。作用是使得函数运行时能够访问到词法环境的
state。

### Scope hoisting
module被放到了引用该module的里面。

### 如何启用Scope hoisting
 new webpack.optimize.ModuleConcatenationPlugin()

### Scope Hoisting的好处
module编译成函数会使得js执行变慢。作用域提升可以减缓编译造成的执行性能影响。

**不是所有的引入方式都会scope hositing的**





