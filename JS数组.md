# split()函数

```
定义:
	split() 方法用于把一个字符串分割成字符串数组。
语法:
	stringObject.split(separator,howmany)
参数:
	separator: 必需。字符串或正则表达式，从该参数指定的地方分割 stringObject。
	howmany: 可选。该参数可指定返回的数组的最大长度。如果设置了该参数，返回的子串不会多于这个参数指定			  的数组。如果没有设置该参数，整个字符串都会被分割，不考虑它的长度。
	
	
let myData = "HelloWorld, toDay, yesterday";
let myArray = myData.split(",");
let yourArray = myData.split(",", 2);

console.log(myArray.length);        // 3
console.log(myArray);               // [ 'HelloWorld', ' toDay', ' yesterday' ]
console.log(yourArray.length);      // 2
console.log(yourArray);             // [ 'HelloWorld', ' toDay' ]
```



# join()函数

```
定义:
	join() 方法用于把数组中的所有元素放入一个字符串。元素是通过指定的分隔符进行分隔的。(将数组转换成字	 符串)
语法:
	arrayObject.join(separator)
参数:
	separator: 可选。指定要使用的分隔符。如果省略该参数，则使用逗号作为分隔符。
	
	
let myData = ['HelloWorld', 'toDay', 'yesterday'];
let myString = myData.join();
let yourString = myData.join(',');
let herString = myData.join('');
let hisString = myData.join('-');

console.log(myString);          // HelloWorld,toDay,yesterday
console.log(yourString);        // HelloWorld,toDay,yesterday
console.log(hisString);         // HelloWorld-toDay-yesterday
console.log(herString);         // HelloWorldtoDayyesterday
```



# toString()函数

```
定义: 
	toString() 方法可把数组转换为字符串，并返回结果。
语法: 
	arrayObject.toString()
参数:
	无


let array = ["abcs", "12356", ["Hello", "World"]];

let myArray = array.toString();
console.log(myArray);           // abcs,12356,Hello,World
```



# 添加 删除

```
pop(): 删除并返回数组的最后一个元素
push(): 向数组的末尾添加一个或更多元素，并返回新的长度。
shift(): 删除并返回数组的第一个元素
unshift(): 	向数组的开头添加一个或更多元素，并返回新的长度。


let array = ["abcs", "12356", ["Hello", "World"]];

let myArray = array.pop();
console.log(myArray);                   // [ 'Hello', 'World' ]
console.log(array);                     // [ 'abcs', '12356' ]

let yourArray = array.push("你好,世界");
console.log(array);                     // [ 'abcs', '12356', '你好,世界' ]

let hisArray = array.shift();
console.log(hisArray);                  // abcs
console.log(array);                     // [ '12356', '你好,世界' ]

let herArray = array.unshift("今天");
console.log(array);                     // [ '今天', '12356', '你好,世界' ]
```



[w3cschool数组]: w3cschool数组	"https://www.w3school.com.cn/jsref/jsref_obj_array.asp"



