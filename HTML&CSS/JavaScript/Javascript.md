# JavaScript

![JS知识架构图.PNG](.\JSImgs\JS知识架构图.PNG)

## 1.JS类型
运行时类型：
运行时类型是代码实际执行过程中我们用到的类型。所有的类型数据都会属于 7 个类型之一。从变量、参数、返回值到表达式中间结果，任何 JavaScript 代码运行过程中产生的数据，都具有运行时类型。
7种语言类型：
- Undefined（一个值）
	- 定义
    	- 表示未定义
    	- 任何变量在赋值之前都是Undefined类型，值为undefined
    - 表达
    	- 可以用全局变量undefined(名为undefined的这个变量)来表达这个值
    	- 也可以用void运算来把任意一个表达式变成undefined值
    - 注意
    	- undefined不是关键字
    	- undefined 是一个变量，并非一个关键字
    	- 为避免无意被篡改，建议使用void 0获取undefined值
    	- 实际编程时，我们不会吧变量赋值为undefined,这样可以保证所有值为undefined的变量，都是从未没有赋值的自然状态
- Null（一个值）
	- 定义
		- 已经定义了，但是值为空
	- 注意
		-  JS的关键字
- Boolean（两个值）
- String
	- 定义
		- String 并非“字符串”，而是字符串的UTF16编码
		- 字符串操作都是针对UTF-16编码，所以字符串最大长度，实际上是多厚字符串的编码长度影响的
	- 字符串操作
		- charAt
		- charCodeAt
		- length
	- 注意
		- 字符串是永远无法变更的，一旦字符串构造出来，无法用任何方式改变字符串的内容，所以字符串具有值类型的特征
- Number（对应有理数）
	- 值
		- 正常数
		- NAN
		- Infinity
		- -Infinity
	- 注意
		- 检测正0 和负 0可以用除法来表示
		- 使用JS提供的最小精度值来比较0.1+0.2！=0.3的问题，检查等式左右两边差的绝对值是否小于最小精度，才是正确比较浮点数的方法
		`console.log( Math.abs(0.1 + 0.2 - 0.3) <= Number.EPSILON);`
- Symbol
	- 定义
		- 一切非字符串的对象 key 的集合
- Object
	- 定义
		- 一切物体的总称，是属性的集合
			- 属性
				- 数据属性
                - 访问器属性
        - JavaScript 中的“类”仅仅是运行时对象的一个私有属性，而 JavaScript 中是无法自定义类型的。

为什么有的编程规范要求用 void 0 代替 undefined？

字符串有最大长度吗？
0.1 + 0.2 不是等于 0.3 么？
为什么 JavaScript 里不是这样的？
ES6 新加入的 Symbol 是个什么东西？
为什么给对象添加的方法能用在基本类型上？





































































