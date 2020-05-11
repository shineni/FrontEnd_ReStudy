# Promise专题
## 1.知识准备
### 1.1 区别实例对象和函数对象
- 实例对象：new函数产生的对象，简称为对象
- 函数对象：将函数作为对象使用时，简称函数对象
```
    <script>
        /*
        1.函数对象与实例对象
            函数对象： 将函数作为对象使用时，简称为函数对象
            实例对象： new 函数 产生的对象，简称为对象

            a()[0]()()  可以知道什么？
                1). a是一个函数
                2). 返回值是一个数组
                3). 数组的第一个元素是函数
                4). 数组第一个元素的返回值还是一个函数
        */
        function Fn(){           //Fn是函数

        }
        const fn = new Fn();        //Fn是构造函数 fn是实例对象（对象）
        console.log(Fn.prototype);  //Fn函数对象
        Fn.bind({});                //只有函数对象才有bind, call ,apply方法，在Function的原型上面定义，Fn是函数对象
        $('#test');
        $.get('/test');
    </script>
```

### 1.2 两种类型的回调函数
回调函数的三个要点：
1. 自己定义的函数，如setTimeout就不是回调函数
2. 不会自己亲自调用
3. 最终是会执行的

#### 1.2.1 同步回调
- 理解：立即执行，完全执行完了才能结束，不会放入回调队列中
- 例子：数组遍历相关的回调函数/Promise 的excutor函数

#### 1.2.2 异步回调
- 理解：不会立即执行，会放入回调队列中将来执行
- 例子:定时器回调/Ajax回调/Promise的成功|失败的回调

```
//1.2.1同步回调函数
const arr=[1,2,3]
arr.forEach(item=>{    //遍历回调，同步回调函数，不会放入队列中，一上来就要执行完
    console.log(item)
})
console.log("foreach()之后")

//1.2.2异步回调函数
setTimeout(()=>{        //异步回调函数，会放入队列中将来执行
    console.log("timeout callback()")
},0)
console.log('setTimeout()之后')
```

### 1.3 JS的error处理
#### 1.3.1 错误的类型
- Error:所有错误的父类型
- ReferenceError: 引用的变量不存在
- TypeError: 数据类型不正确的错误
- RangeError: 数据值不再其所允许的范围内
- SyntaxError: 语法错误

#### 1.3.2 错误处理
- 捕获错误： try ... catch
- 跑出错误： throw error

#### 1.3.3 异步回调
- message属性：错误相关信息
- stack属性：函数调用栈记录信息

## 2.promise的理解和和使用
### 2.1 Promise是什么
- 理解
	- 抽象表达
		- Promise是JS中进行一步编程的新的解决方案（旧的是谁？纯回调函数）
	- 具体表达
		- 从语法上说： Promise是一个构造函数(一旦是构造函数，一般都是实例做事情)
		- 从功能上说： promise 对象是用来封装一个一步操作并可以获取其结果
- 状态
	- pending 初始状态/未确定的状态
	- resolved 成功状态
	- rejected 失败状态
- 状态改变
	- pending变为resolved
	- pending变为regjectd
说明：
	只有两种状态改变，且一个promise对象只能改变一次
    无论变为成功还是失败，都会有一个结果数据
    成功的数据一般称为value,失败的结构钢数据一般称为resaon

![执行原理图.PNG](.\PromiseImgs\执行原理图.PNG)

```
    <script>
        //    1.创建一个Promise对象
        const p  = new Promise((resolve,reject)=>{  //执行器函数
        //  2.执行异步操作任务
        setTimeout(() => {
            const time = Date.now();//如果当前时间是偶数就代表成功，否则代表失败
            if(time%2==0){
            //  3.1如果成功了，调用resolve(value)
                resolve("成功数据，time = "+time)

            }else{
            //  3.2如果失败了，调用reject(reason)
                reject("失败数据，time=" +time)
            }
        }, 1000);
        })

        p.then(value=>{ //接受得到成功的value数据
            console.log("成功的回调",value)
        },reason=>{     //接受得到失败的reason数据
            console.log("失败的回调",reason)
        })
    </script>
```

### 2.2 为什么用Promise
- a. 指定回调函数的方式更加灵活
	- 旧的：必须在启动异步任务前指定
	- promise: 启动异步任务=>返回promise对象=>给Promise对象绑定回调函数(甚至可以在异步任务结束后指定)
- b. 支持链式调用，可以解决回调地狱的问题
	- 什么是回调地狱？
		- 回调函数嵌套调用，外部回调函数异步执行的结果是嵌套的回调函数执行的条件
	- 回调地狱的缺点？
		- 不便于阅读/不便于异常处理
	- 解决方案
		- promise链式调用（仍然存在回调函数）
		- 【终极解决方案】async/await

**回调地狱： 回调函数嵌套调用,不便于阅读也不便于异常处理**

![回调地狱.PNG](.\PromiseImgs\回调地狱.PNG)

**纯回调：**

![纯回调.PNG](.\PromiseImgs\纯回调.PNG)
**Promise**

![Promise.PNG](.\PromiseImgs\Promise.PNG)
**Promise链式调用**

![Promise链式调用.PNG](.\PromiseImgs\Promise链式调用.PNG)

**Async 和Await**

![async.PNG](.\PromiseImgs\async.PNG)

### 2.3 如何使用Promise
#### 2.3.1 API
(搞清楚语法，语法是啥？如果是函数，知道函数的参数有哪些，函数干嘛用的。如果是对象，搞清楚有哪些属性和方法，并且知道这些属性和方法都是干嘛用的，如果是函数)
1. Promise 构造函数：Promise(excutor){}
	(1)excutor函数：同步执行 (resolve,reject)=>{}
    (2)resolve函数：内部定义成功时我们调用的函数value=>{}
    (3)reject函数：内部定义失败时我们调用的函数 reason=>{}
    说明：excutor会在Promise内部立即同步回调，异步操作在执行器中执行
2. Promise.prototype.then方法：（onResolved,onRejected）={}
	(1)onResolved函数：成功的回调函数 （value）=>{}
    (2)onRejected函数：失败的回调函数  (reason)=>{}
    说明：指定用于得到成功value的成功回调和用于得到失败的reason的失败回调
    	**返回一个新的Promise对象**
3. Promise.prototype.catch方法： （onRejectd）=>{}
	onrejected函数：失败的回调函数（reason）=>{}
    说明： then的语法糖，相当于： then(undefined,onrejected)
4. Promise.resolve方法：(value)=>{}
	value：成功的数据或promise对象
    说明：返回一个成功/失败的promise对象
5. Promise.reject方法： (reason)=>{}
	reason:失败的原因
    说明：返回一个失败的promise对象
6. Promise.all方法： (promises)=>{}
	promises: 包含n个promise的数组
    说明：返回一个新的promise,只有所有的promise都成功才成功，只要有一个失败了就直接失败
7. Promise.race方法：(promises)=>{}
	promises: 包含n个promise的数组
    说明：返回一个新的promise,第一个完成的promise的结果状态就是最终的结果状态

#### 2.3.2几个关键问题
1. 如何改变promise的状态？
	(1) resolve(value):如果当前是Pending就会变为resolved
    (2)rejecte（reason）:如果当前是Pending就会变成rejected
    (3)抛出异常：如果当前是pending就会变成rejected

2. 一个promise指定多个成功/失败回调函数，都会调用嘛？
	当promise改变为对应状态是都会调用

3. 改变promise砖头和指定回调函数谁先谁后？
	(1)都有可能，正常情况下是先指定回调再改变状态，但是也可以先改状态，再指定回调
    (2)如何先改变状态在指定回调？
	a.在执行器中直接调用resolve()/reject()
    b.延迟更长时间才调用then()
    (3)什么时候才能得到数据？
     a.如果先指定的回调，那当状态发生改变时，回调函数就会调用，得到数据
     b.如果先改变的状态，那当指定回调时，回调函数就会调用，得到数据
4. promise.then()返回的新promise的结果状态由什么决定？
	(1)简单表达：由then()指定的回调函数执行的结果决定
    (2)详细表达：
    a.如果抛出异常，新promise变为rejected,reason为抛出的异常
    b.如果返回的是非promise的任意值，新promise变为resolved,value为返回的值
    c.如果返回的是另一个新promise,此promise的结果就会成为新promise的结果

5.

## 3.自定义(手写)Promise
## 4.async与awiat
## 5.JS异步之宏队列与微队列
## 6.Promise相关面试题






































