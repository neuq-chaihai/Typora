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

