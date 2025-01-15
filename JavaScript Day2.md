# JavaScript Day2

**今天的内容和C语言大同小异**

## 运算符

* 赋值:``=，+=，-=，*=，/=，%=``

* 自增:``++，--``
* 比较:``>,<,<=,<=,==（隐式转换）,===（类型和值都相等）,!==（不全等）``
* 逻辑:``&&,||``

## if语句

```javascript
//单分支
if (true){
    console.log('执行语句');
}
//双分支
var name = prompt();
var password = prompt();
if( name==='pink' && password===123456 ){
    alert('success');
}
else{
    alert('failed');
}
//多分支
else if(){
}
```

## switch语句

```javascript
switch (num){
    case 1 :
        code1;
        break;
    case 2 :
        code2;
        break;
}
```

## while循环

```javascript
var i = 1;
while(i<=3){
    document.write('Three Times');
    i++;
}
```

``continue``:跳过剩下语句

``break``:直接跳出循环

```javascript
while(true){
    var str = prompt('Do you love me?')
    if(str==='love'){
        break;
    }
}
```

## for循环

```javascript
for (var i = 1;i <= 3;i++){
    document.write('javascript');
    console.log(arr[i]);
}
```

## array

```javascript
var arr = [1,2,'pink',true];
console.log(arr);
arr[0] = 3;
arr.push(3);//在末尾添加
arr.unshift(4);//在开头添加
arr.pop();//删最后一个
arr.shift();//删第一个
arr.splice(1，1);//起始位置1，删1个
```

## 示例：渲染柱形图案

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }

        .box {
            display: flex;
            width: 700px;
            height: 300px;
            border-left: 1px solid pink;
            border-bottom: 1px solid pink;
            margin: 50px auto;
            justify-content: space-around;
            align-items: flex-end;
            text-align: center;
        }

        .box>div {
            display: flex;
            width: 50px;
            background-color: pink;
            flex-direction: column;
            justify-content: space-between;
        }

        .box div span {

            margin-top: -20px;
        }

        .box div h4 {
            margin-bottom: -35px;
            width: 70px;
            margin-left: -10px;
        }
    </style>
</head>

<body>
    <script>
        // 1. 四次弹框效果
        // 声明一个新的数组
        let arr = []
        for (let i = 1; i <= 4; i++) {
            // let num = prompt(`请输入第${i}季度的数据:`)
            // arr.push(num)
            arr.push(prompt(`请输入第${i}季度的数据:`))
            // push记得加小括号，不是等号赋值的形式
        }
        // console.log(arr)  ['123','135','345','234']
        // 盒子开头
        document.write(` <div class="box">`)

        // 盒子中间 利用循环的形式  跟数组有关系
        for (let i = 0; i < arr.length; i++) {
            document.write(`
              <div style="height: ${arr[i]}px;">
                <span>${arr[i]}</span>
                <h4>第${i + 1}季度</h4>
              </div>          
            `)
        }
        // 盒子结尾
        document.write(` </div>`)
    </script>
</body>

</html>
```

