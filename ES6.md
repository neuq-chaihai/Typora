# ${}

```
    /*
        使用 ${} 来包裹一个变量或者一个表达式
    */
    const a = 1;
    const b = 2;
    const string=`${a}+${b}=${a+b}`;
    //1+2=3
    console.log(string)
    
const Hello = (props) => {
    return (
        `你好吗，这是一个很厉害的一句话：${props}`
    )
}

console.log(Hello("HelloWorld"));
console.log(Hello("nihao"));

const obj = {
    a: "小明",
    b: "小红",
    c: "吃饭",
    d: 1,
    e: 2
}

const Party = (props) => {
    return (
        `${props.a}想要请${props.b}${props.c},但是他们发现人太多了，有${props.d+props.e}`
    )
}

console.log(`告诉你一个好消息, ${Party(obj)}`);

const tmpl = addrs => `
  <table>
  ${addrs.map(addr => `
    <tr><td>${addr.first}</td></tr>
    <tr><td>${addr.last}</td></tr>
  `).join('')}
  </table>
`;

const data = [
    { first: '<Jane>', last: 'Bond' },
    { first: 'Lars', last: '<Croft>' },
];
```





# 字符串新增函数

```
String.fromCodePoint()
ES5 提供String.fromCharCode()方法，用于从 Unicode 码点返回对应字符，但是这个方法不能识别码点大于0xFFFF的字符。
ES6 提供了String.fromCodePoint()方法，可以识别大于0xFFFF的字符，弥补了String.fromCharCode()方法的不足。
```



## 字符串查找

```
ES5的写法: 其实这种方法并不实用，给我们的索引位置，我们自己还要确定位置。(若字符串不存在,返回-1)
	let jspang='技术胖';
	let blog = '非常高兴你能看到这篇文章，我是你的老朋友技术胖。这节课我们学习字符串模版。';
	document.write(blog.indexOf(jspang));
	
ES6直接用includes就可以判断，不再返回索引值，这样的结果我们更喜欢，更直接。(返回值为true和false)
	let jspang='技术胖';
	let blog = '非常高兴你能看到这篇文章，我是你的老朋友技术胖。这节课我们学习字符串模版。';
	document.write(blog.includes(jspang));
	
判断开头是否存在: (返回值为true和false)
	let jspang='技术胖';
	let blog = '非常高兴你能看到这篇文章，我是你的老朋友技术胖。这节课我们学习字符串模版。';
	blog.startsWith(jspang);
	
判断结尾是否存在：(返回值为true和false)
	let jspang='技术胖';
	let blog = '非常高兴你能看到这篇文章，我是你的老朋友技术胖。这节课我们学习字符串模版。';
	blog.endsWith(jspang);
```



## 复制字符串



# 数字操作

## **二进制声明：**

二进制的英文单词是Binary,二进制的开始是0（零），然后第二个位置是b（注意这里大小写都可以实现），然后跟上二进制的值就可以了。

```
let binary = 0B010101;
console.log(binary);  //21
```

##  八进制声明：

八进制的英文单词是Octal，也是以0（零）开始的，然后第二个位置是O（欧），然后跟上八进制的值就可以了。

```
let b=0o666;
console.log(b);		//438
```

## 数字判断和转换:

```
数字验证Number.isFinite( xx )
可以使用Number.isFinite( )来进行数字验证，只要是数字，不论是浮点型还是整形都会返回true，其他时候会返回false。

let a= 11/4;
console.log(Number.isFinite(a));			//true
console.log(Number.isFinite('jspang'));		//false
console.log(Number.isFinite(NaN));			//false
console.log(Number.isFinite(undefined));	//false
```

## NaN验证

NaN是特殊的非数字，可以使用Number.isNaN()来进行验证。下边的代码控制台返回了true。

```
console.log(Number.isNaN(NaN));				//true
```

## 判断是否为整数Number.isInteger(xx)

```
let a=123.1;
console.log(Number.isInteger(a)); 			//false
```

## 整数转换Number.parseInt(xxx)和浮点型转换Number.parseFloat(xxx)

```
let a='9.18';
console.log(Number.parseInt(a)); 
console.log(Number.parseFloat(a));
```

## 整数取值范围

### 最大安全整数

```
console.log(Number.MAX_SAFE_INTEGER);		//9007199254740991
```



# 字符串新增数组知识

## Array.from(json)方法:

```
将标准的json代码转换为数组的形式
/*===============标准形式 ============*/
let str1 = {
    '0': "Hello",
    '1': "World",
    '2': "你好",
    length: 3
}
/*===================================*/

let s1 = Array.from(str1);
console.log(s);      	// [ 'Hello', 'World', '你好' ]

let str2 = {
    '0': "Hello",
    '1': "World",
    '2': "你好",
}

let s2 = Array.from(str2);
console.log(s2); 		// []
```

## **Array.of()方法：**

```
负责把一堆文本或者变量转换成数组。

let arr =Array.of(3,4,5,6);
console.log(arr);           //[ 3, 4, 5, 6 ]

let arr =Array.of("Hello", "World", "你好", "世界");
console.log(arr);           //[ 'Hello', 'World', '你好', '世界' ]
```

# **fill( )实例方法：**

```
fill()也是一个实例方法，它的作用是把数组进行填充，它接收三个参数，第一个参数是填充的变量，第二个是开始填充的位置，第三个是填充到的位置。

let str = ["Hello", "World", "react", "Vue", "Flutter"];
let str1 = ["Hello", "World", "react", "Vue", "Flutter"];
let str2 = ["Hello", "World", "react", "Vue", "Flutter"];
str.fill("EngLish", 2, 3);
str1.fill("EngLish", 2, 5);
str2.fill("EngLish", 5, 7);
console.log(str);                   //  [ 'Hello', 'World', 'EngLish', 'Vue', 'Flutter' ]
console.log(str1);                  //  [ 'Hello', 'World', 'EngLish', 'EngLish', 'EngLish' ]
console.log(str2);                  //  [ 'Hello', 'World', 'react', 'Vue', 'Flutter' ]
```

# **数组的遍历**

## **for…of循环：**

### for...of数组内容:

```
let str = ["Hello", "World", "react", "Vue", "Flutter"];

for(let s of str){

  console.log(s);

}

// Hello

// World

// react

// Vue

// Flutter
```

### for...of数组索引

```
for(let k of str.keys()){
    console.log(k)
}
// 0
// 1
// 2
// 3
// 4
```

### for..of数组索引和内容

```
for(let [index, b] of str.entries()){
    console.log(index+";"+b)
}
// 0;Hello
// 1;World
// 2;react
// 3;Vue
// 4;Flutter


for(let c of str.entries()){
    console.log(c)
}
// [ 0, 'Hello' ]
// [ 1, 'World' ]
// [ 2, 'react' ]
// [ 3, 'Vue' ]
// [ 4, 'Flutter' ]
```

### **in的用法**

```
in是用来判断对象或者数组中是否存在某个值的。

let Hello = {
    a: "Hello",
    b: "World",
    c: "HelloWorld"
}

console.log('a' in Hello);                          //true
console.log('Hello' in Hello);                      //false
```



## entries( )实例方法：**

```
entries()实例方式生成的是Iterator形式的数组，那这种形式的好处就是可以让我们在需要时用next()手动跳转到下一个值。


对象判断
let str = ["Hello", "World", "react", "Vue", "Flutter"];
let s = str.entries();  
console.log(s);                         //  Object [Array Iterator] {}
console.log(s.next().value);            //  [ 0, 'Hello' ]
console.log(s.next().value);            //  [ 1, 'World' ]
console.log(s.next().value);            //  [ 2, 'react' ]
console.log(s.next().value);            //  [ 3, 'Vue' ]
console.log(s.next().value);            //  [ 4, 'Flutter' ]
console.log(s.next().value);            //  undefined

数组判断
let Hello = [,,,,,,];
let World = ["Hello", "World", "HelloWorld"];
console.log(Hello.length);              //6
console.log(World.length);              //3
console.log(0 in Hello);                //false
console.log(0 in World);                //true
```

## 数组遍历

### ForEach

```
forEach循环的特点是会自动省略为空的数组元素，相当于直接给我们筛空了。

let Hello = [
    "老狼老狼几点啦",
    "七点啦",
    "老狼老狼几点啦",
    "",
    "开饭啦"
]

Hello.forEach((item ,index)=>(
    console.log(item),
    console.log(index)
))

// 老狼老狼几点啦
// 0
// 七点啦
// 1
// 老狼老狼几点啦
// 2

// 3
// 开饭啦
// 4
```

### filter

```
let Hello = [
    "老狼老狼几点啦",
    "七点啦",
    "老狼老狼几点啦",
    "",
    "开饭啦"
]

Hello.filter((item ,index)=>(
    console.log(item),
    console.log(index)
))
let Hello = [
    "老狼老狼几点啦",
    "七点啦",
    "老狼老狼几点啦",
    "",
    "开饭啦"
]

Hello.filter((item ,index)=>(
    console.log(item),
    console.log(index)
))
// 老狼老狼几点啦
// 0
// 七点啦
// 1
// 老狼老狼几点啦
// 2

// 3
// 开饭啦
// 4
```

### some

```
let Hello = [
    "老狼老狼几点啦",
    "七点啦",
    "老狼老狼几点啦",
    "",
    "开饭啦"
]

Hello.some((item ,index)=>(
    console.log(item),
    console.log(index)
))
// 老狼老狼几点啦
// 0
// 七点啦
// 1
// 老狼老狼几点啦
// 2

// 3
// 开饭啦
// 4

```

### map

```
map在这里起到一个替换的作用

let Hello = [
    "老狼老狼几点啦",
    "七点啦",
    "老狼老狼几点啦",
    "",
    "开饭啦"
]

Hello.map((item ,index)=>(
    console.log(item),
    console.log(index)
))
// 老狼老狼几点啦
// 0
// 七点啦
// 1
// 老狼老狼几点啦
// 2

// 3
// 开饭啦
// 4
```

## 数组转换字符串

### **join()方法**

```
let Hello = [
    "老狼老狼几点啦",
    "七点啦",
    "老狼老狼几点啦",
    "",
    "开饭啦"
]

console.log(Hello.join("???"));
// 老狼老狼几点啦???七点啦???老狼老狼几点啦??????开饭啦
```

### toString()方法

```
let Hello = [
    "老狼老狼几点啦",
    "七点啦",
    "老狼老狼几点啦",
    "",
    "开饭啦"
]

console.log(toString.length);
console.log(Hello.toString());
// 老狼老狼几点啦,七点啦,老狼老狼几点啦,,开饭啦
```

# 函数

## 获得函数个数的方法

```
使用.length

function Hello(a, b,  c){
    return "Hello World!!!"
}

console.log(Hello.length);			//3
```

# 对象

## 对象赋值

```
let firstname = "Hello";
let lastname= "World";

let Name = {firstname, lastname};
console.log(Name);
// { firstname: 'Hello', lastname: 'World' }
```

## 对象Key值创建

```
有时候我们会在后台取出key值，而不是我们前台定义好的，这时候我们如何构建我们的key值那。比如我们在后台取了一个key值，然后可以用[ ] 的形式，进行对象的构建。


let key = "Hello";

let Hello = {
    [key]: "HelloWorld"             // 从后台拿到的数据
}

console.log(Hello.Hello);           // HelloWorld
```

## 自定义方法

```
var obj={
    add:function(a,b){
        return a+b;
    }
}
console.log(obj.add(1,2));  //3
```

## Object.is( ) 对象比较

```
=== 和 is方法的区别

console.log(+0 === -0);  //true
console.log(NaN === NaN ); //false
console.log(Object.is(+0,-0)); //false
console.log(Object.is(NaN,NaN)); //true
```

## Object.assign( )合并对象

```
// 数组合并

let a = {
    key: "Hello",
    web: "World"
}
let b = {
    Day: "Hello",
    web: "Today"
}

let c = Object.assign(a,b);
console.log(c);						// { key: 'Hello', web: 'Today', Day: 'Hello' }
```



## Symbol在对象中的作用

```
let Hello = Symbol();
let World = {
    [Hello] : "Hello World!!!"
}

console.log(World[Hello]);          // Hello World!!!
Hello[Hello] = '你好';
console.log(World[Hello]);          // Hello World!!!


Symbol对象元素的保护作用
在对象中有很多值，但是循环输出时，并不希望全部输出，那我们就可以使用Symbol进行保护。

let item = Symbol();

let Hello = {
    [item]: "Hello",
    list: "List",
    web: "Web"
}

for(let i in Hello){
    console.log(Hello[i]);                          // List    Web
}
console.log(Hello);                                 // { list: 'List', web: 'Web', [Symbol()]: 'Hello' }


```

