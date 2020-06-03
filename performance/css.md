1. 使用css的快捷方式(使用简洁的属性和值，先指明快捷的，在使用特定的去覆盖)，shallow css的选择器以及
实践DRY原则，减小css的size，自定义css框架达到最小值
2. 使用不同的page模板进行css的分段
3. 使用高效率的css选择器，flexbox引擎和
css的transition
4. 使用一些css加速属性will-change，tanslate3d等

### shallow css selectors
指的是css 的特指性，不要太大。尽量简洁，节省空间还能够
使得css简洁加载的性能更好.
一般css的优化可以使用critical css和unused css来进行
优化。
### 不要DRY
尽量不要书写重复的css。因为有些属性总是出现不同的选择器里
所以考虑将这些重复的放在一起。注意寻找冗余的css。
可以使用csscss来看重复的css。对于响应式的网站
要考虑跨断点的值进行合并。

### segment css
就是将css按照不同的模板或者模块进行分割

### 自定义UI框架下载

### 调优css
> 主要是改善加载和渲染的时间
1. css里应该避免@import的声明的使用
  性能的改善是尽可能的并行。@import是串行的序列化操作
2. link标记是并发请求
   html文档被扫描之后，所有的link标记是要并行加载的
3. css文件应该放在head里
  这样可以避免两个问题：
  - 未样式化的内容闪烁
  - 页面的渲染性能，避免了重新渲染和重绘整个dom
4. 使用更快的css选择器
tag>desendant>class>direct child>sibling>pseudo>attribute
5. flexbox优于box
6. transition适合简单线性的动画，可以will-change进行优化
translatZ和will-change的区别在于translateZ在于只能告诉
浏览器这里有事情要发生，但是will-change会指明元素的哪个方面要发生变化。
对于will-change注意要给浏览器足够的准备时间。
> 比如设置一个元素在hover的时候背景色变化，可以在静态的时候指明will-change也可以在父亲元素hover的时候指定该元素的willchange。





















