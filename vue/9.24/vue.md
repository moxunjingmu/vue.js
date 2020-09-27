## render函数是什么

　　简单的说，在vue中我们使用模板HTML语法组建页面的，使用render函数我们可以用js语    言来构建DOM

　　因为vue是虚拟DOM，所以在拿到template模板时也要转译成VNode的函数，而用render函数构建DOM，vue就免去了转译的过程。

　　当使用render函数描述虚拟DOM时，vue提供一个函数，这个函数是就构建虚拟DOM所需要的工具。官网上给他起了个名字叫createElement。还有约定的简写叫h,

　　vm中有一个方法_c,也是这个函数的别名

## 虚拟dom
　　DOM是文档对象模型(Document Object Model)的简写，在浏览器中通过js来操作DOM的操作性能很差，于是虚拟Dom应运而生。虚拟Dom就是在js中模拟DOM对象树来优化DOM操作的一种技术或思路。React和Vue2都使用了虚拟DOM技术，虚拟DOM并不是真正意义上的DOM，它作为一个轻量级的JavaScript对象，在状态发生变化时，会进行Diff运算，来更新发生变化的DOM，对于未发生变化的DOM节点，不予操作，由于不是全部重绘，大大提高更新渲染性能。当使用render函数描述虚拟DOM时，vue提供一个函数，这个函数是就构建虚拟DOM所需要的工具。官网上给他起了个名字叫 createElement。还有约定的简写叫 h, vm中有一个方法 _c, 也是这个函数的别名。

在Vue2中，虚拟DOM就是通过一种VNode类表达，每个DOM元素或组件都对应一个VNode对象。

 ## VNode节点解析：

children 子节点，数组，也是VNode类型。
text 当前节点的文本，一般文本节点或注释节点会有该属性。
elm 当前虚拟节点对应的真实的DOM节点。
ns 节点的namespace
content 编译作用域
functionalContext 函数化组件的作用域
key 节点的key属性，用于作为节点的标识，有利于patch的优化
componentOptions 创建组件实例时会用到的选项信息。
child 当前节点对应的组件实例。
parent 组件的占位节点。
raw 原始html
isStatic 静态节点的标识
isRootInset 是否作为根节点插入，被<transition>包裹的节点，该属性的值为false。
isConment 当前节点是否是注释节点。
isCloned 当前节点是否为克隆节点。
isOnce 当前节点是否有v-once指令。

TextVNode 文本节点。
ElementVNode 普通元素节点。
ComponentVNode 组件节点。
EmptyVNode 没有内容的注释节点。
CloneVNode 克隆节点，可以是以上任意类型的节点，唯一的区别在于isCloned属性为true。