# Redux(1) :前端为何需要状态管理库
Redux 是基于 flux 的设计模式，完整的前端状态管理框架

#### Redux 是什么？回想 React 的组件是什么样的工作模式呢？
```
其实就是把 State 转换为 DOM 的结构，如果说 React 把状态 State 转换为 DOM 是在组件内部发生的话，那么 Redux 就是把
状态 State 移到外部,就是把全局所有的状态 State 放在全局 Store 中，全局只有一个唯一的 Store，负责全局提供所有应用程序
的状态，组件所有的状态都可以放在外部 Store 中,Store 有任何变化，组件也会自动更新，页面不同部分的更新，可能是来自
Store 中不同的节点， Redux Store中的结构也是一个 tree 的结构，跟组件的结构 tree 是一个映射的关系，这是 Redux 的
核心概念，管理所有React的所有状态。Redux让组件通信更加容易。是一个单向数据流的过程。
```
#### Redux 有哪些特性？
```
第一个特性: Single Source of Truth
传统的1个 model 可能被多个view 应用，1个view 使用多个 model,关系错综复杂。有BUG,检查状态哪里发生错误，追踪难
Redux 是所有的状态都放在唯一的 Store 中，是唯一状态的来源，所有的 View 都是依赖于 Store ， View 内部尽量没有自己的状态，
当 Store 变化，View 会更新， View 上有用户操作，会通过事件通知 Store 进行变化，让整个应用程序，变得更加容易理解和追踪。
当有BUG，检查当前的状态就可以很容易定位追踪

第二个特性:可预测性  state + action = new state

第三个特性：纯函数更新Store
什么是纯函数？它的输出结果完全取决于它的输入参数，函数的内部不依赖于任何外部参数和资源。这样的特点就是整个函数非常容易
预测和测试的，给定的参数输出结果一定是某个确定的值
```

# Redux(2) :深入理解 Store, Action, Reducer
#### 如何理解 Store ？ Store 有什么作用呢？
```
1. getState()  得到当前的状态数据；     
2. dispatch(action)   当UI上用户有操作事件，产生 Action， Store 就会派遣出去给 Reducer；   
3. subscribe(listener)   监听 Store 的变化， Store 有任何变化， Store 都会调用监听器listener；

```

#### 如何理解 Action？Action 有什么作用呢？
```
指定一个数据类型
通过  Reducer

```
Redux 是独立于UI 框架之外的状态管理框架
Redux 跟UI没有直接关系，是可以完全脱离UI去进行运行的；在 nodejs 中它也是直接执行的，所以它是通用的状态管理框架
Redux 跟 React 一起的使用场景比较多，所以大家认为Redux 跟 React 是很好的结合。

# Redux(3) :在React中使用Redux
```
通过连接组件react-redux
通过 connect 方法连接到 store 上

基本语法：
首先定义了一个组件，组件需要用到 store 上的节点，mapStateToProps 定义了组件用到哪些节点
mapDispatchToProps 把 actions 绑定到组件上面，这个时候组件上就可以通过 actions 去访问所有的 Redux 中的 actions 
最后通过高阶组件方式去connect 一个已有的组件，connect 首先是接收两个参数，然后形成一个函数，函数再去调 SidePanel,形成一个高阶组件
这是 redux 的实现原理：如何connect 一个已有的组件到 store
```


#### connect的工作原理:高阶组件
 connect 之后，会在数据逻辑里面去访问store 以及访问 action ,
redux 的自身逻辑：触发action ==> 到reducers ==> 然后更新 store，store会传到高阶组件 ==》高阶组件传到需要用到 store 数据的组件上面

#### 性能问题：
如果把整个 store 都绑定到组件上，store中任何节点变化都会触发组件的更新
绑定到 count 的话，只有 count发生变化，组件才更新，在这个方法中，必须把访问的节点限定在最小范围，限定到必须的范围，
才能让组件高性能的状态

#### store 里面如何更新store呢？
原理：那就必须访问 redux 的 action。
具体：提供 mapDispatchToProps 的方法，这个方法接收的参数是Dispatch，然后调用的是

组件上的属性是由自己定义的函数传进来的，函数中的方法绑定到上面的属性，定义好之后，就可以调用 connect 来完成高阶组件的创建
 connect 接收函数，再传入已有的组件，在counter 上就会显示属性。


# Redux(4) :理解异步Action , Redux中间件
#### 理解异步Action 
```
View 点击一个按钮，获取API的数据，会发送一个Ajx的请求，这是一个异步的过程
不是在View 点击一个按钮，触发 Action 直接到 Store 的

异步Action 不是特殊类型的 Action，而是 几个同步的Action的组合使用

Redux 的工作流程是怎样的呢？
在 View 上点击 button ==>触发 Action （这个Action不是标准的 Javascrict 对象，描述如何发送Ajx请求以及如何处理结果的）
==>再到 Middlewares 中间件==> API 访问成功（发送成功的 Action 的结果，否则发失败的 Action  ）==> Dispatcher不同的Action出去 
==> 真正把结果传到 Redecer ==>更新Store



```
#### Redux中间件
中间件 Middlewares 作用：截获某种特殊类型的 Action ，先进行预处理，才会真正把结果传到Reducer来更新Store；比如Ajx请求的 Action，


1.截获action 
2.发出action




# Redux(5) :如何组织Action和Reducer
#### 
#### 

# Redux(6) :理解不可变数据( Immutability )
#### 

#### 

# React Router (1) :路由不只是页面切换,更是代码组织方式
#### 
#### 

# React Router (2) :参数定义,嵌套路由的使用场景观看进度:0%

#### 
#### 




























