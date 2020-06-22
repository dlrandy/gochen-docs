webpack会找到app使用的所有的module，并把它们打包成几个文件

### module VS chunk VS bundle
1. module 
    一块封装数据和提供功能的js代码。module相互依赖，可以形成依赖图
2. chunk
    在webpack打包的过程中，几个模块可以形成一个chunk
3. bundle
    打包最终生产的文件，大多数情况下，一个chunk只产生一个bundle

### HMR
在app运行的时候，交换，添加，移除module，不会完全重载app。
HMR的目标就是避免完全的或者说是整个页面的刷新。
> code改变的时候，hmr不会reload app。而是app本身要知道如何响应到来的changes

### HMR是怎么一个过程

webpack                 webpack dev server                   webpack runtime              module
compiler                                                                        

generate                 transfer the                        orchestrate the             handle 
hot update               hot update                           update                     the change

### handle the change
hot update 的处理要么是webpack loader编译时注入或者手动添加的；
手动添加是通过webpack暴露出来的module.hot公共接口处理的。
``` javascript
/*
webpack将会执行改变模块的新版本
*/
module.hot.acccept()

```
### 注销掉旧的模块
module.hot.dispose


### Parent-Accepted Modules
处理其他模块引入该模块的热更新

### 对于一个模块的更新处理逻辑
1. 在引入模块里进行parent accept
2. 在自己的模块内部进行self accept

### 所有的更新处理策略
1. self accept
不好的地方在于引入该模块的的parents不能知道模块的变化
处理过程：
> 执行新的js模块； 执行updateHandler

2. parent accept
一般webpack对于没有做self accept的模块，会去引入该模块的模块里寻找
更新处理。
处理过程：
>  执行新的js模块；更新引入该模块的parent指向新的js模块； 执行updateHandler

3. entry file里进行parent accept
如何当前模块和引用它的模块都没有进行更新处理，webpack会继续沿着依赖图进行寻找Handler
处理过程：
> 执行新的js模块；执行引入该模块的parent模块；在entryfile里更新parent的模块的引用到
新的js模块；最后执行updateHandler.

4. 没有设置updateHandler
 webpack找到rootmodule的时候，webpack-dev-server会回退到整个页面刷新


 



