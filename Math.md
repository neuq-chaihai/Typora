# es6中的Math.trunc()和parseInt()的对比

```
Math.trunc()作用就是去除一个数的小数部分, 如果参数的字符串内部会先使用Number将其先转为数值

parseInt(): 如果出现连续的超过6个及其以上连续的6个0会自动改成科学计数法：
			parseInt() 函数解析一个字符串参数，并返回一个指定基数的整数 (数学系统的基础)。 
			parseInt() 函数将其第一个参数转换为字符串，解析它，并返回一个整数或NaN。如果不是NaN，返回的值将是作为指定基数（基数）中的数字的第一个参数的整数。

console.log(parseInt('13.14g'));//13
console.log(Math.trunc('13.14g'));//NaN

console.log(parseInt(6.022e23)); // 6
console.log(Math.trunc(6.022e2)); // 6.02

console.log(parseInt(0.00000060));//6
console.log(Math.trunc(0.00000060));//0


```

