# JavaScript Day1

## 组成

* ECMAScript JS基础语法
* DOM 文档对象类型 
* BOM 浏览器对象类型

## 位置

``行内式``

```html
<input type="button" value="JS" onclick="alert('JavaScript')"> //一般用单引号
```

``内嵌式``

```html
<script>
    alert('JavaScript');
</script>
```

``外部式``

```html
<script src="my.js"></script> //中间不允许写代码
```

## 输入输出语句

```javascript
alert('JavaScript');//弹出警示框
prompt('请输入您的年龄');//弹出输入框
console.log('123');//控制台输出 给程序员看
document.write('123');//界面输出
```

## 变量

> 声明+赋值

```javascript
var age;\\variable 自动分配数据类型
age = 18;
console.log(age);
```

```javascript
var myname = prompt('请输入你的名字');
alert('myname');
console.log(myname);
```

```javascript
var age = 18,
    address = 'hy',
    email = '1234';
```

## 数据类型

```javascript
var x = 10;
x = 'pink';//不会报错 数据类型可以转换
x = 010;//八进制
x = 0x10;//十六进制
```

``Number``

```javascript
var num = 10;
var PI = 3.14;//小数 整数均可
```

```javascript
console.log(Number.MAX_VALUE);//MIN_VALUE
console.log(Infinity);//Number.MAX_VALUE * 2
console.log(NaN);//非数字 如'pink'-100
console.log(isNaN(12));//是数字返回false
```

``Boolean``

```javascript
var flag1 = true;
var flag2 = false;
console.log(flag + 1);//加法时true当1 false当0
```

``String``

```javascript
var str = 'Java\nscript';//\n换行 转义字符加斜杠
```

```javascript
var str = 'my name is chen';
console.log(str.length);//检测长度
console.log('java' + 'script');//字符串拼接
var age = 18;
console.log('pink' + age + 's');//不同类型也可以
```

```javascript
var age = prompt('your age');
var str = 'your age is' + age;
alert(str);
```

```javascript
//模板字符串 `${变量名}`
var age = 18;
document.write(`我今年${age}岁了`)
```

``Undefined``

```javascript
var str;
console.log(str);//报undefined
var variable = undefined;
console.log(variable + 1)；//NaN
console.log(variable + 'ABC')//undefinedABC
```

``Null``

```javascript
var space = null;
console.log(space + 1)；//1
console.log(space + 'ABC')//nullABC
```

#### 获取变量数据类型

```javascript
var num = 10;
console.log(typeof num);
```

#### 数据类型转换

``字符串型``

```javascript
var num = 1;
alert(num.toSrting());
alert(String(num));
alert(num+'');
```

``数字型``

```javascript
console.log(parseInt('3.14'));//取整3
console.log(parseInt('120px'));//取120
console.log(parseInt('rem120px'));//NaN
```

```javascript
console.log(parseFloat('3.14'));//3.14
```

```javascript
var str = '123';
console.log(Number(str));
```

```javascript
console.log('12' - 0);//隐式转换-，*，/
console.log('123' - '120');//输出数值3
```

```javascript
//加法计算器示例
var num1 = prompt();
var num2 = prompt();
var result = parseFloat(num1)+parseFloat(num2);
alert(result);
```

``布尔型``

```javascript
console.log(Boolean('123'));
//'',0,NaN,null,undefined返回false，其余均为true
```

## 解释型语言和编译型语言的区别

编程语言需要通过翻译器转化为机器语言，翻译有两种方式，一种是编译，一种是解释。

编译是翻译完成后才能运行代码，解释是边运行代码边翻译，二者区别在于**翻译时间点不同**

JavaScript属于解释型语言

## 数组

```javascript
let arr = [10,20,30];
console.log(arr[0]);
console.log(arr.length);
```

## 常量

``const``

## 实战：获取输入数据 制作表格

```html
<!DOCTYPE html>
<html lang = 'en'>
    <head>
        <meta charset = 'UTF-8'>
        <title>Document</title>
        <style>
            h2{
                text-align : center;
            }
            table{
                border-collapse: collapse;
                height:80px;
                margin:0 auto;
                text-align:center;
            }
            table,th,td{
                border:1px,solid,#000
            }
            th{
                padding:5px,30px;
            }
        </style>
    </head>
    <body>
        <h2>订单确认</h2>
                <script>
                    var price = parseInt(prompt('请输入商品价格'));
                    var num = parseInt(prompt('请输入商品数量'));
                    var address = prompt('请输入收货地址')

                    var total = price * num;

                    document.write(`
                    <table>
            <tr>
                <th>名称</th>
                <th>商品价格</th>
                <th>商品数量</th>
                <th>总价</th>
                <th>收货地址</th>
            </tr>
            <tr>
                <td>SaintCHEN</td>
                <td>${price}</td>
                <td>${num}</td>
                <td>${total}</td>
                <td>${address}</td>
                    `)
                </script>
            </tr>
        </table>
    </body>
</html>
```

