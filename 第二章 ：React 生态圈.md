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
1. getState()  得到当前的状态数据；     
2. dispatch(action)   当UI上用户有操作事件，产生 Action， Store 就会派遣出去给 Reducer；   
3. subscribe(listener)   监听 Store 的变化， Store 有任何变化， Store 都会调用监听器listener；



#### 如何理解 Action？Action 有什么作用呢？
指定一个数据类型
通过  Reducer



# Redux(3) :在React中使用Redux
#### 
#### 

# Redux(4) :理解异步Action , Redux中间件
#### 
#### 

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




























