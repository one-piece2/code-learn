# 1.开发环境搭建

现在还是使用CRA，create-react-app

![image-20250711131103486](React(!!!).assets/image-20250711131103486.png)

![image-20250711131138831](React(!!!).assets/image-20250711131138831.png)

# 2.基础

## JSX

react是在js里面写html模板，

![image-20250711235846162](React(!!!).assets/image-20250711235846162.png)

![image-20250711235900329](React(!!!).assets/image-20250711235900329.png)

## Map方法（用于列表渲染）

一般用来渲染列表，因为map方法是数组的一个高级方法，创建一个新数组，不影响原数组，新数组的结果是每个数组的元素都调用一个方法返回的结果。

![image-20250712004032274](React(!!!).assets/image-20250712004032274.png)

map循环谁，return结构。





## 条件渲染

![image-20250712004323333](React(!!!).assets/image-20250712004323333.png)

## 基础事件

![image-20250712230330461](React(!!!).assets/image-20250712230330461.png)

也可以直接传递事件对象，如下图：

![image-20250712230539559](React(!!!).assets/image-20250712230539559.png)

==如果想传递自定义参数==：

![image-20250712230642755](React(!!!).assets/image-20250712230642755.png)

![image-20250712230812921](React(!!!).assets/image-20250712230812921.png)





## useState

![image-20250712231736258](React(!!!).assets/image-20250712231736258.png)

![image-20250712231757353](React(!!!).assets/image-20250712231757353.png)

==用法：==

![image-20250712232152495](React(!!!).assets/image-20250712232152495.png)

### usestate使用规则

注意：在 React 中使用 Hooks 时，必须遵守两条核心规则，其中首要规则就是要将 Hooks 写在 React 函数组件的顶层，或者是自定义 Hook 的顶层位置。

**1.**![image-20250712232713049](React(!!!).assets/image-20250712232713049.png)

**2.**

![image-20250712232829842](React(!!!).assets/image-20250712232829842.png)

## 样式控制

**![image-20250712233220364](React(!!!).assets/image-20250712233220364.png)**

### classnames库优化类名控制

![image-20250713002304570](React(!!!).assets/image-20250713002304570.png)

**老的拼接字符串条件控制：**

![image-20250713002333848](React(!!!).assets/image-20250713002333848.png)

**新的：**

![image-20250713002357615](React(!!!).assets/image-20250713002357615.png)





## 表单绑定

![image-20250713085907558](React(!!!).assets/image-20250713085907558.png)



## 获取Dom

==注意（渲染完成之后，dom生成 完之后才可用）==

![image-20250713091055779](React(!!!).assets/image-20250713091055779.png)

# 3.组件通信

## 1.父传子

![image-20250713094741871](React(!!!).assets/image-20250713094741871.png)

==注意：==props是只读数据，只能使用，不能直接修改父组件传来的数据，父组件可以传递任何类型数据。

一个==特殊==的父传子： 特殊的props-->children

![image-20250714000704021](React(!!!).assets/image-20250714000704021.png)

## 2.子传父

核心：在子组件中调用父组件中的函数并传递参数。

例子：

<img src="React(!!!).assets/image-20250714001914918.png" alt="image-20250714001914918" style="zoom:50%;" /> <img src="React(!!!).assets/image-20250714001925221.png" alt="image-20250714001925221" style="zoom:50%;" />

 ## 3.兄弟组件通信

![image-20250714003352486](React(!!!).assets/image-20250714003352486.png)

## 4.跨层组件通信（例如：爷孙）

![image-20250714003901312](React(!!!).assets/image-20250714003901312.png)

==核心==：用**provider**提供数据，用**useContex**t获取使用数据。

案例：

<img src="React(!!!).assets/image-20250714004108613.png" alt="image-20250714004108613" style="zoom:33%;" /> -》<img src="React(!!!).assets/image-20250714004129852.png" alt="image-20250714004129852" style="zoom:33%;" />-》<img src="React(!!!).assets/image-20250714004147807.png" alt="image-20250714004147807" style="zoom:33%;" />

**第一步：**

![image-20250714004257632](React(!!!).assets/image-20250714004257632.png)

**第二步：**

<img src="React(!!!).assets/image-20250714004319460.png" alt="image-20250714004319460" style="zoom:67%;" />

**第三步：**

<img src="React(!!!).assets/image-20250714004452588.png" alt="image-20250714004452588" style="zoom:67%;" />

# 4.hooks和常用API

## hooks使用规则

注意：在 React 中使用 Hooks 时，必须遵守两条核心规则，其中首要规则就是要将 Hooks 写在 React 函数组件的顶层，或者是自定义 Hook 的顶层位置。

![image-20250714132921477](React(!!!).assets/image-20250714132921477.png)





## 4.1.useState

![image-20250712231736258](React(!!!).assets/image-20250712231736258.png)

![image-20250712231757353](React(!!!).assets/image-20250712231757353.png)

==用法：==

![image-20250712232152495](React(!!!).assets/image-20250712232152495.png)



**1.**![image-20250712232713049](React(!!!).assets/image-20250712232713049.png)

**2.**

![image-20250712232829842](React(!!!).assets/image-20250712232829842.png)

==3.可以传函数进来==

- 使用函数式初始化（`useState(() => new Date())`）可以确保 `new Date()` 只在组件初始化时执行一次，避免性能问题和状态不一致。
- 如果直接写 `useState(new Date())`，每次组件重新渲染时都会生成一个新的日期对象，可能导致不必要的性能开销和状态问题。



## 4.2.useEffect

![image-20250714010223412](React(!!!).assets/image-20250714010223412.png)

使用：

```
useEffect(  ()=>{需要执行的操作}, []  )
```

<img src="React(!!!).assets/image-20250714011333388.png" alt="image-20250714011333388" style="zoom: 50%;" /> 

<img src="React(!!!).assets/image-20250714011351055.png" alt="image-20250714011351055" style="zoom:50%;" />



**后面的依赖项与副作用的关系：**

![image-20250714114233501](React(!!!).assets/image-20250714114233501.png)

### 清除副作用

![image-20250714125822682](React(!!!).assets/image-20250714125822682.png)

语法：在第一个函数末尾写上return就行。

<img src="React(!!!).assets/image-20250714130719988.png" alt="image-20250714130719988" style="zoom:50%;" /> <img src="React(!!!).assets/image-20250714130741836.png" alt="image-20250714130741836" style="zoom: 33%;" />

例子：

<img src="React(!!!).assets/image-20250714130821923.png" alt="image-20250714130821923" style="zoom:67%;" /> 





## 4.3.自定义Hook

**例子：**（返回需要使用的状态和函数）

<img src="React(!!!).assets/image-20250714131345069.png" alt="image-20250714131345069" style="zoom:67%;" /> 

<img src="React(!!!).assets/image-20250714131422098.png" alt="image-20250714131422098" style="zoom:67%;" /> 



## 4.4useMemo

**`useMemo`** 是 React 提供的一个 Hook，用于优化性能，避免在每次渲染时都进行高开销的计算。它的核心作用是**缓存计算结果**，只有当依赖项发生变化时才重新计算。



**为什么需要 useMemo？**

在 React 中，**组件渲染时会执行其中的所有代码**。如果某些计算成本很高（例如复杂的数组排序、大量数据处理），每次渲染都重新计算会导致性能问题。`useMemo` 可以缓存这些计算结果，只有在必要时才重新计算。



**语法：**

<img src="React(!!!).assets/image-20250727214048264.png" alt="image-20250727214048264" style="zoom:50%;" /> 



## 4.5 useReducer

和useState的作用类似，用来管理相对复杂的数据。

首先：

```javascript
const [state,dispatch]=useReducer(reducer,0)
```

然后在定义reducer函数：

![image-20250729160700929](React(!!!).assets/image-20250729160700929.png)

使用时，直接dispatch即可，

```javascript
dispatch({type:'INC})
```

同时，**action可以传参**，传参方法如下：

<img src="React(!!!).assets/image-20250729161806948.png" alt="image-20250729161806948" style="zoom: 50%;" />



## 4.6 React.memo

允许组件在**Props没有改变**的情况下跳过渲染。

由来：

<img src="React(!!!).assets/image-20250729163043757.png" alt="image-20250729163043757" style="zoom: 50%;" /> 



**基础语法:**（也可以用React.meoo包裹）

![image-20250729163316245](React(!!!).assets/image-20250729163316245.png)

用memo函数包裹生成的缓存组件只有在props变化时才会重新渲染。



## 4.7useCallback

​     用于在组件多次重新渲染的时候，缓存函数。和usememo类似，usememo是缓存值。

​     由于父组件重新渲染的时候，函数属于引用类型的props，它的引用地址会改变，即使写了memo，子组件也会跟着重新渲染，所以需要使用它来缓存韩式哦，使得引用一致。使得props稳定，不会让子组件重新渲染。

用法： 空数组表示只缓存一次，也可以增加依赖项。

<img src="React(!!!).assets/image-20250729170158140.png" alt="image-20250729170158140" style="zoom:80%;" />



![image-20250729170326805](React(!!!).assets/image-20250729170326805.png)



## 4.8 React.forwardRef（父组件拿子组件的DOM元素）

使用ref暴露DOM节点给父组件。

可以让父组件拿到子组件中的DOM节点。

<img src="React(!!!).assets/image-20250729170806446.png" alt="image-20250729170806446" style="zoom:25%;" /> 



**用法：**

**在父组件中：**通过useRef得到值，ref传递给子组件。

<img src="React(!!!).assets/image-20250729170946558.png" alt="image-20250729170946558" style="zoom: 50%;" /> 

**在子组件中：**用该API包裹子组件，然后用ref给想拿到的DOM元素。

<img src="React(!!!).assets/image-20250729171139814.png" alt="image-20250729171139814" style="zoom:50%;" /> 

​	

## 4.9 useImperativeHandle（父组件拿子组件的方法）

暴露子组件中的方法和属性。（使用它可以同时暴露子组件中的dom节点和方法）

要配合forwardRef来使用

语法：

**父组件：**通过useRef得到值，ref传递给子组件。

<img src="React(!!!).assets/image-20250729173126505.png" alt="image-20250729173126505" style="zoom:50%;" /> 

**子组件：**（用该hooks暴露方法，此方法是子组件内部自己定义的方法。）

<img src="React(!!!).assets/image-20250729173654566.png" alt="image-20250729173654566" style="zoom:50%;" /> 

























# 5.Redux

==定义：==

![image-20250714231303358](React(!!!).assets/image-20250714231303358.png)

## 1.React中使用Redux环境搭建

![image-20250714235704503](React(!!!).assets/image-20250714235704503.png)

<img src="React(!!!).assets/image-20250714235713770.png" alt="image-20250714235713770" style="zoom:67%;" /> 

​        

## 2.Redux使用

### 1.纯Redux

![image-20250715184614760](React(!!!).assets/image-20250715184614760.png)

<img src="React(!!!).assets/image-20250715184703532.png" alt="image-20250715184703532" style="zoom:67%;" /> 

<img src="React(!!!).assets/image-20250715184740057.png" alt="image-20250715184740057" style="zoom:67%;" /> 

![image-20250715184808064](React(!!!).assets/image-20250715184808064.png)  

<img src="React(!!!).assets/image-20250715184837731.png" alt="image-20250715184837731" style="zoom:67%;" /> 

<img src="React(!!!).assets/image-20250715185417816.png" alt="image-20250715185417816" style="zoom:67%;" /> 

![image-20250715185430875](React(!!!).assets/image-20250715185430875.png)

### 2.React中

#### 项目目录

**Redux项目的目录**

![image-20250715000502680](React(!!!).assets/image-20250715000502680.png) 

<img src="React(!!!).assets/image-20250715000619082.png" alt="image-20250715000619082" style="zoom: 33%;" /> 

**步骤：**

#### ==1.在counterStore中创建自己模块的Store==

<img src="React(!!!).assets/image-20250715190624530.png" alt="image-20250715190624530" style="zoom:67%;" /> 

#### ==2.在store的入口文件中组合一下counterstore==

<img src="React(!!!).assets/image-20250715191106913.png" alt="image-20250715191106913" style="zoom:67%;" />  

#### ==3.为react注入store==

![image-20250715191609130](React(!!!).assets/image-20250715191609130.png) 

==在项目的入口文件index.js中导入**provider**函数和**store**，==如下图，完成注入。

![image-20250715191759950](React(!!!).assets/image-20250715191759950.png) 



#### ==4.在组件中使用store中的数据==

使用==useSelector==钩子函数，把store中的数据映射到组件当中。直接在组件函数里面调用即可。

其中例子里面的这个counter来源于configureStore中创建的reducer名字。

<img src="React(!!!).assets/image-20250715192506052.png" alt="image-20250715192506052" style="zoom: 50%;" />



==5.在react中修改store的数据。==

这里需要使用==useDispatch==钩子函数。

1.先导入action的方法，和钩子，

2.在组件内部使用useDispatch函数生成dispatch对象，

3.然后在事件中使用。

![image-20250715192758390](React(!!!).assets/image-20250715192758390.png)

#### 5.在action中传递参数

写法：在方法中多传递一个action，他的payload属性就是传递过来的参数。然后调用时直接传参。

<img src="React(!!!).assets/image-20250715230622864.png" alt="image-20250715230622864" style="zoom:67%;" /> 

![image-20250715230807264](React(!!!).assets/image-20250715230807264.png)



#### 6.异步状态操作

创建store的写法保持不变，如图：

<img src="React(!!!).assets/image-20250716000729287.png" alt="image-20250716000729287" style="zoom:67%;" /> 

区别：如下图：

需要==单独封装==一个函数，同时函数内部需要==return==一个新函数，

新函数：封装异步请求获取数据，调用同步action，然后传入异步数据，然后使用dispatch提交。

<img src="React(!!!).assets/image-20250716001441548.png" alt="image-20250716001441548" style="zoom:67%;" /> 

随后在组件中要使用useEffect hooks来发送请求。如下图：

<img src="React(!!!).assets/image-20250716001651641.png" alt="image-20250716001651641" style="zoom:67%;" /> 





# 6.ReactRouter

## 1.安装react-router-dom包



## 2.使用（createBrowserRouter）

1.创建路由组件文件夹，写路由组件。

**2.新增router文件，专门配置和管理路由**，并导出。

引入createBrowserRouter来创建路由，如下图：

<img src="React(!!!).assets/image-20250717001928101.png" alt="image-20250717001928101" style="zoom:67%;" /> 

**3.使用。在路口文件中注入路由。**

<img src="React(!!!).assets/image-20250717002112112.png" alt="image-20250717002112112" style="zoom:67%;" />  



### 2.1导航跳转

**1.声明式导航**

<img src="React(!!!).assets/image-20250719231709320.png" alt="image-20250719231709320" style="zoom:50%;" /> 

**2.编程式导航**

<img src="React(!!!).assets/image-20250719232157909.png" alt="image-20250719232157909" style="zoom:50%;" /> 

 ### 2.2导航传参

**1.searchParams传参**

<img src="React(!!!).assets/image-20250719232512291.png" alt="image-20250719232512291" style="zoom:50%;" /> 

**2.Params传参**

先占位：

<img src="React(!!!).assets/image-20250719232646379.png" alt="image-20250719232646379" style="zoom:50%;" />  

<img src="React(!!!).assets/image-20250719232618101.png" alt="image-20250719232618101" style="zoom:50%;" /> 

### 2.3嵌套路由

注意：（默认二级路由设置）

![image-20250719233725962](React(!!!).assets/image-20250719233725962.png)

<img src="React(!!!).assets/image-20250719233131134.png" alt="image-20250719233131134" style="zoom: 50%;" />  

### 2.4  404路由配置

<img src="React(!!!).assets/image-20250719233842658.png" alt="image-20250719233842658" style="zoom: 33%;" />  



## 3.使用（**`<Routes>`** 和 **`<Route>`**）

1.先用路由容器（BrowserRouter）包裹根组件。注意：**只需在应用根组件包裹一次**

2.路由匹配：

- `<Routes>`：渲染第一个匹配的子 `<Route>`。
- `<Route>`：定义路径（`path`）和对应组件（`element`）。

3.嵌套路由

- 使用 `<Outlet>` 标记子路由的渲染位置。





#### 3.1实际用法

![image-20250719234513714](React(!!!).assets/image-20250719234513714.png)

<img src="React(!!!).assets/image-20250719234531400.png" alt="image-20250719234531400" style="zoom:67%;" /> 





<img src="React(!!!).assets/image-20250719234619435.png" alt="image-20250719234619435" style="zoom:67%;" />   

<img src="React(!!!).assets/image-20250719234704150.png" alt="image-20250719234704150" style="zoom:50%;" /> 

<img src="React(!!!).assets/image-20250719234725414.png" alt="image-20250719234725414" style="zoom:50%;" /> 



## 4.**路由跳转并传递状态**

![image-20250719235014190](React(!!!).assets/image-20250719235014190.png)

**useLocation还可以用来获取路由路径。**

```
使用：location.pathname
```



# 7.别名配置

![image-20250726212855829](React(!!!).assets/image-20250726212855829.png)

==1.路径解析配置==

![image-20250726213055879](React(!!!).assets/image-20250726213055879.png)

第三步和第四步：

<img src="React(!!!).assets/image-20250726213255014.png" alt="image-20250726213255014" style="zoom:50%;" /> 

==2.vscode中的路径联想配置==

<img src="React(!!!).assets/image-20250726213738302.png" alt="image-20250726213738302" style="zoom: 50%;" /> 

# 8.数据mock

工具：json-server

<img src="React(!!!).assets/image-20250726214716209.png" alt="image-20250726214716209" style="zoom:50%;" /> 





# 9.Token持久化

存储在状态管理工具中的token，在浏览器刷新时就会丢失，

原因：他们是基于浏览器内存的存储方式，刷新时，状态恢复初始值。

可存储在LocalStorage中来避免。

<img src="React(!!!).assets/image-20250728142824166.png" alt="image-20250728142824166" style="zoom:50%;" /> 

初始化时，先在LocalStorage中取值，没有的话就置空。

<img src="React(!!!).assets/image-20250728142945830.png" alt="image-20250728142945830" style="zoom:50%;" /> 



## 9.1处理Token失效

<img src="React(!!!).assets/image-20250728161858570.png" alt="image-20250728161858570" style="zoom:67%;" />

**思路：在响应拦截器中监控状态码401，操作如下：**

<img src="React(!!!).assets/image-20250728162422330.png" alt="image-20250728162422330" style="zoom:50%;" /> 





# 10.Ant design组件

## 10.1 form组件实例

可以通过

```
const [form] = Form.useForm()
```

来获取表单实例对象，然后就可以调用表单上的方法，

比如：form.setFieldsValue（）来回填数据等.........



# 11.路由懒加载优化

![image-20250729151446806](React(!!!).assets/image-20250729151446806.png)

**路由懒加载的配置：**

![image-20250729151513584](React(!!!).assets/image-20250729151513584.png)

**步骤：1.使用lazy函数对组件进行导入。**

![image-20250729153809654](React(!!!).assets/image-20250729153809654.png)

**2.通过内置组件进行包裹。**

![image-20250729153911862](React(!!!).assets/image-20250729153911862.png)

**由于现在的路由是异步渲染，其中fallback是占位，也就是说渲染完成之前，画面显示什么东西。**





# 12.zustand

补充：如果**箭头函数**的函数体只有一个 表达式的时候，可以省略大括号 `{}` 和 `return` 关键字，

表达式的结果会自动作为返回值。如果要隐式返回对象字面量，必须用括号 `()` 包裹对象，否则大

括号会被解析为函数体。



一个极简的状态管理工具

## 使用步骤：

1.创建store

```
import  {create}  from 'zustand'
```

![image-20250730103120810](React(!!!).assets/image-20250730103120810.png)

或者

<img src="React(!!!).assets/image-20250730105538196.png" alt="image-20250730105538196" style="zoom:50%;" /> 

其中set是专门用来修改数据的方法，必须使用他来修改数据。

1.1 当修改的时候 需要用到老数据的时候，参数是函数。

<img src="React(!!!).assets/image-20250730110304743.png" alt="image-20250730110304743" style="zoom:50%;" /> 

1.2 当修改不需要使用老数据的时候，参数是对象。

<img src="React(!!!).assets/image-20250730110340144.png" alt="image-20250730110340144" style="zoom: 67%;" /> 

2.使用store 

<img src="React(!!!).assets/image-20250730105650462.png" alt="image-20250730105650462" style="zoom:50%;" /> 



## 异步支持

![image-20250730110510994](React(!!!).assets/image-20250730110510994.png)

<img src="React(!!!).assets/image-20250730110531641.png" alt="image-20250730110531641" style="zoom: 67%;" />  



## 切片模式

![image-20250730112254281](React(!!!).assets/image-20250730112254281.png)

1.拆分

<img src="React(!!!).assets/image-20250730112319433.png" alt="image-20250730112319433" style="zoom:33%;" />  <img src="React(!!!).assets/image-20250730112336893.png" alt="image-20250730112336893" style="zoom:33%;" />



2.组合（函数调用结果需要...展开，同时creat函数的参数也需要...展开然后传下去）

![image-20250730112441407](React(!!!).assets/image-20250730112441407.png)
