为什么 css in  js？

css  in js的优缺点？

css module， BEM？

### styled-components 
它的目的是强化React component system的css样式。主要是通过关注于单一使用情况优化开发者体验和终端输出。

### 好处
1. 开发者体验较好
2. 自动 critical css
3. 没有类名冲突
4. 更容易的css删除，因为类名绑定到了特定的组件
5. 无痛的维护，不需要搜索不同的文件来寻找样式的相互影响
6. 自动厂商前缀

### 原理
taged templateral



### emotion



### styled-components VS emotion
| css in js 特性     | styled-components | emotion |
| -------------------|------------------------|------------|
| styled             | ✅ :white_check_mark:  |❌ :x:|
| css-prop           |  ❌ :x:                |✅ :white_check_mark:|
| JSX                |  ❌ :x:                |✅ :white_check_mark:|
| React Concurrent   |  ❌ :x:                |✅ :white_check_mark:|
| Bundle Size smaller| ✅ :white_check_mark:  |❌ :x:|
| Speed              | 待测试                   |待测试，但是一般相对较快|

### css module
他通常是要生成一个css code和jscode，css的code放到style或者文件里，js则是一个map用于
对应css类名

> css module VS css in js
css momdule 主要解决的是选择器名字作用域的问题， 一般是使用sass或者stylus的时候使用;
css in js也是解决了命名冲突的问题，但是对于theme提供了更好的支持；也可以包装第三方组件；

