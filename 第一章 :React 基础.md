# 01 | React出现的历史背景及特性介绍
React 是由Fackbook工程师开发（消息状态错误，上线后检查还是出错，一直调试不好）
#### 为什么会出现 React 这种新框架
```
1,传统UI操作关注太多细节
2.应用程序状态分散在各处,难以追踪和维护
1.传统DOM API关注太多细节
2.React :始终整体"刷新"页面)无需关心细节

```
#### React很简单
```
1.1个新概念
2.4个必须API
3.单向数据流
4.完善的错误提示
```
#### React解决了UI细节问题,数据模型如何解决?
```
1.传统MVC难以扩展和维护(很难追踪是model出现错误还是view上出错)
2.Flux架构:单向数据流:
WebAPI==>Web API Utils==>Action Creators==>Action==>Dispatcher==>Callbacks==>Store==>Changg Events +Store Queries
==>React Views==>User Interactions==>Action Creators==>Web API Utils==>Web API
相比于传统的MV* 而言，Flux强调单向，从而让整个数据流形成了闭环。
而在MV* 中，数据流往往不会是单向的。
```

#### Flux架构的衍生项目

> Redux 和 Mobx


#### 提到的4个必须的APi具体是指哪四个？
```
1. ReactDOM.render 方法让 React 组件渲染到某个具体的 DOM 节点。
2. 组件的 render 方法 
3. 组件的 setState 方法，用于改变组件状态，触发 render 
4. 如何通过 props 给 React 组件传递参数
```
#### 目前前端react开发主流用什么IDE

一般都是 VSCode，不过你也可以尝试 Rekit

#### 老师这里的整体刷新是整个页面刷新嘛，如果这个页面有多个http后端请求，难道所有的http全都要刷新一次嘛？
#### 这里的store存储的是什么，具体如何通过状态的改变去感知页面的改变，求详解

这里说的整体刷新是指逻辑上纯 UI 的重绘，HTTP 请求一般都在组件的 componentDidMount 或者 componentDidUpdate 中
根据条件来发送，只要逻辑正确，不会每次都重新发起。store 存储的是应用程序状态，包括 UI 状态，例如某个树节点是否展
开，和业务数据状态，比如一个商品列表。页面是根据状态来渲染的，state -> view。 只要通过组件的 this.setState 方法
去改变组件状态，那么页面就会自动更新。


#### 怎么理解 Redux ？ 

是 React 的进行状态管理的标准










# 以组件方式考虑UI的构建

props（外部属性） + state（内部状态） => View（视图）

1.React组件一般不提供方法,而是某种状态机 , 
2.React组件可以理解为一个纯函数 
3.单向数据绑定

# 创建一个简单的组件: TabSelect

1.创建静态UI,
2.考虑组件的状态组成 
3.考虑组件的交互方式

# 受控组件vs非受控组件
受控组件 表单元素状态由使用者维护
非受控组件 表单元素状态DOM自身维护

# 何时创建组件:单一职责原则
1.每个组件只做一件事
2.如果组件变得复杂,那么应该拆分成小组件

# 数据状态管理: DRY原则 
1.能计算得到的状态就不要单独存储 
2.组件尽量无状态,所需数据通过 props 获取


# 第三节 理解JSX :不是模板语言,只是一种语法糖
JSX:在JavaScript代码中直接写HTML标记
JSX的本质:动态创建组件的语法糖

# 在JSX中使用表达式

1, JSX本身也是表达式
2,在属性中使用表达式
3,延展属性
4,表达式作为子元素

# JSX优点
1.声明式创建界面的直观 
2.代码动态创建界面的灵活 
3.无需学习新的模板语言


# 约定:自定义组件以大写字母开头 

1. React认为小写的taq是原生DOM节点,如div 
2.大写字母开头为自定义组件
3.JSX标记可以直接使用属性语法,例如<menu.lItem /


# 第四节 React组件的生命周期及其使用场景





## constructor

1·用于初始化内部状态,很少使用
2·唯一可以直接修改state的地方

## getDerivedStateFromProps
1.当state需要从props初始化时使用
2.尽量不要使用:维护两者状态一致性会增加复杂度 
3.每次render都会调用 
4.典型场景:表单控件获取默认值

## componentDidMount

1.UI渲染完成后调用 
2.只执行一次 
3.典型场景:获取外部资源

## componentWillUnmount
1.组件移除时被调用 
2.典型场景:资源释放

## getSnapshotBeforeUpdate
1,在页面render之前调用, state已更新 
2典型场景:获取render之前的DOM状态

## componentDidUpdate
1.每次UI更新时被调用 
2.典型场景:页面需要根据 props变化重新获取数据


## shouldComponentUpdate
1.决定Virtual DOM是否要重绘
2.一般可以由PureComponent自动实现 
3.典型场景:性能优化

## JSX的运行基础: Virtual DOM
## 虚拟DOM是如何工作的


## 虚拟DOM的两个假设
1.组件的DOM结构是相对稳定的 
2.类型相同的兄弟节点可以被唯一标识

## 1.算法复杂度为O(n)


## 2.虚拟DOM如何计算diff


## 3.key属性的作用

## 组件复用的另外两种形式:高阶组件和函数作为子组件
高阶组件：对已有组件的分装，形成一个新的组件，包含自己的应用逻辑，新的逻辑产生新的状态，会传给已有的组件
高阶组件一般不会有自己高阶展现，只是负责为分装的组件提供一些额外的功能或者数据

## 可以实现更多场景的组件复用



# 第7节：理解Context API的使用场景
组件通信问题。










