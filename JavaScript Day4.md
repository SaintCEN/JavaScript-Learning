# JavaScript  Day 4

> 知道对象数据类型的特征，能够利用数组对象渲染页面

## 对象

> 对象是 JavaScript 数据类型的一种，可以被理解成是一种数据集合，由属性和方法两部分构成。

### 语法

声明一个对象类型的变量与之前声明一个数值或字符串类型的变量没有本质上的区别。

```javascript
var user = {};
```

### 属性和访问

数据描述性的信息称为属性，如人的姓名、身高、年龄、性别等，一般是名词性的。

1. 属性都是成对出现的，包括属性名和值，它们之间使用英文 `:` 分隔
2. 多个属性之间使用`,` 分隔

声明对象，并添加了若干属性后，可以使用 `.` 或 `[]` 获得对象中属性对应的值。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>JavaScript 基础 - 对象语法</title>
</head>
<body>
  <script>
    // 通过对象描述一个人的数据信息
    // person 是一个对象，它包含了一个属性 name
    // 属性都是成对出现的，属性名 和 值，它们之间使用英文 : 分隔
    let person = {
      name: '小明', // 描述人的姓名
      age: 18, // 描述人的年龄
      stature: 185, // 描述人的身高
      gender: '男', // 描述人的性别
    };
    // 访问人的名字
    console.log(person.name) // 结果为 小明
    // 访问人性别
    console.log(person.gender) // 结果为 男
    // 访问人的身高
    console.log(person['stature']) // 结果为 185
   // 或者
    console.log(person.stature) // 结果同为 185
  </script>
</body>
</html>
```

**扩展：也可以动态为对象添加属性，动态添加与直接定义是一样的，只是语法上更灵活。**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>JavaScript 基础 - 对象语法</title>
</head>
<body>
  <script>
    // 声明一个空的对象（没有任何属性）
	let user = {}
    // 动态追加属性
    user.name = '小明'
    user['age'] = 18
    // 动态添加与直接定义是一样的，只是语法上更灵活
  </script>
</body>
</html>
```

### 方法和调用

数据行为性的信息称为方法，如跑步、唱歌等，一般是动词性的，其本质是函数。

1. 方法是由方法名和函数两部分构成，它们之间使用 : 分隔
2. 多个属性之间使用英文 `,` 分隔
3. 方法是依附在对象中的函数
4. 方法名可以使用 `""` 或 `''`，一般情况下省略，除非名称遇到特殊符号如空格、中横线等

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>JavaScript 基础 - 对象方法</title>
</head>
<body>
  <script>
    // 方法是依附在对象上的函数
    let person = {
      name: '小红',
      age: 18,
      // 方法是由方法名和函数两部分构成，它们之间使用 : 分隔
      singing: function () {
        console.log('两只老虎，两只老虎，跑的快，跑的快...')
      },
      run: function () {
        console.log('我跑的非常快...')
      }
    }
  </script>
</body>
</html>
```

声明对象，并添加了若干方法后，可以使用 `.` 或 `[]` 调用对象中函数。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>JavaScript 基础 - 对象方法</title>
</head>
<body>
  <script>
    // 方法是依附在对象上的函数
    let person = {
      name: '小红',
      age: 18,
      // 方法是由方法名和函数两部分构成，它们之间使用 : 分隔
      singing: function () {
        console.log('两只老虎，两只老虎，跑的快，跑的快...')
      },
      run: function () {
        console.log('我跑的非常快...')
      }
    }
    // 调用对象中 singing 方法
    person.singing()
    // 调用对象中的 run 方法
    person.run()
  </script>
</body>
</html>
```

**扩展：也可以动态为对象添加方法，动态添加与直接定义是一样的，只是语法上更灵活。**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>JavaScript 基础 - 对象方法</title>
</head>
<body>

  <script>
    // 声明一个空的对象（没有任何属性，也没有任何方法）
	let user = {}
    // 动态追加属性
    user.name = '小明'
    user.['age'] = 18
    
    // 动态添加方法
    user.move = function () {
      console.log('移动一点距离...')
    }
    
  </script>
</body>
</html>
```

**注：无论是属性或是方法，同一个对象中出现名称一样的，后面的会覆盖前面的。**

### null

null 也是 JavaScript 中数据类型的一种，通常只用它来表示不存在的对象。使用 ``typeof ``检测类型它的类型时，结果为 `object`。

#### 遍历对象

~~~javascript
let obj = {
    uname: 'pink'
}
for(let k in obj) {
    // k 属性名  字符串  带引号    obj.'uname'     k ===  'uname'
    // obj[k]  属性值    obj['uname']   obj[k]
}
~~~

for in 不提倡遍历数组 因为 k 是 字符串  

## 内置对象

回想一下我们曾经使用过的 `console.log`，`console`其实就是 JavaScript 中内置的对象，该对象中存在一个方法叫 `log`，然后调用 `log` 这个方法，即 `console.log()`。

除了 `console` 对象外，JavaScript 还有其它的内置的对象

### Math

`Math` 是 JavaScript 中内置的对象，称为数学对象，这个对象下即包含了属性，也包含了许多的方法。

#### 属性

- ``Math.PI``，获取圆周率

```javascript
// 圆周率
console.log(Math.PI);
```

#### 方法

- ``Math.random``，生成 0 到 1 间的随机数

```javascript
// 0 ~ 1 之间的随机数, 包含 0 不包含 1
Math.random()
```

- ``Math.ceil``，数字向上取整

```javascript
// 舍弃小数部分，整数部分加1
Math.ceil(3.4)
```

- ``Math.floor``，数字向下取整

```javascript
// 舍弃小数部分，整数部分不变
Math.floor(4.68)
```

- ``Math.round``，四舍五入取整

```javascript
// 取整，四舍五入原则
Math.round(5.46539)
Math.round(4.849)
```

- ``Math.max``，在一组数中找出最大的

```javascript
// 找出最大值
Math.max(10, 21, 7, 24, 13)
```

- ``Math.min``，在一组数中找出最小的

```javascript
// 找出最小值
Math.min(24, 18, 6, 19, 21)
```

- ``Math.pow``，幂方法

```javascript
// 求某个数的多少次方
Math.pow(4, 2) // 求 4 的 2 次方
Math.pow(2, 3) // 求 2 的 3 次方
```

- ``Math.sqrt``，平方根

```javascript
// 求某数的平方根
Math.sqrt(16)
```

## 示例

* 利用对象数组里面的数据来渲染页面，鼠标经过停留会显示`英雄名字`

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<meta http-equiv="X-UA-Compatible" content="ie=edge">
	<title>渲染英雄列表案例</title>
	<link rel="stylesheet" href="css/hero.css">
</head>

<body>
	<!-- 利用对象数组渲染英雄列表案例 -->
	<!-- <ul class="list">
	</ul> -->
	<script>
		const datas = [
			{ name: '司马懿', imgSrc: '01.jpg' },
			{ name: '女娲', imgSrc: '02.jpg' },
			{ name: '百里守约', imgSrc: '03.jpg' },
			{ name: '亚瑟', imgSrc: '04.jpg' },
			{ name: '虞姬', imgSrc: '05.jpg' },
			{ name: '张良', imgSrc: '06.jpg' },
			{ name: '安其拉', imgSrc: '07.jpg' },
			{ name: '李白', imgSrc: '08.jpg' },
			{ name: '阿珂', imgSrc: '09.jpg' },
			{ name: '墨子', imgSrc: '10.jpg' },
			{ name: '鲁班', imgSrc: '11.jpg' },
			{ name: '嬴政', imgSrc: '12.jpg' },
			{ name: '孙膑', imgSrc: '13.jpg' },
			{ name: '周瑜', imgSrc: '14.jpg' },
			{ name: 'XXX', imgSrc: '15.jpg' },
			{ name: 'XXX', imgSrc: '16.jpg' },
			{ name: 'XXX', imgSrc: '17.jpg' },
			{ name: 'XXX', imgSrc: '18.jpg' },
			{ name: 'XXX', imgSrc: '19.jpg' },
			{ name: 'XXX', imgSrc: '20.jpg' }
		]
		let str = ''
		for (let i = 0; i < datas.length; i++) {
			str += `
				<li><img src="./uploads/heros/${datas[i].imgSrc}" title="${datas[i].name}"></li>
			`
		}
		document.write(`
		<ul class="list">
			${str}
		</ul>
		`)
	</script>
</body>
</html>
```

* 表格行要求 编号、科目、成绩和删除链接,最后计算出总分和平均分

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta http-equiv="X-UA-Compatible" content="IE=edge" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <link rel="stylesheet" href="./styles/index.css" />
  <title>Document</title>
</head>
<body>
  <script>
    // 核心数据
    const data = [
      { subject: '语文', score: 46 },
      { subject: '数学', score: 80 },
      { subject: '英语', score: 100 },
    ]
    let tr = ''
    let total = 0 // 计算总分
    for (let i = 0; i < data.length; i++) {
      tr += `
        <tr>
            <td>${i + 1}</td>
            <td>${data[i].subject}</td>
            <td>${data[i].score}</td>
            <td><a href="#">删除</a></td>
        </tr>
      `
      total += data[i].score
    }
    document.write(`
    <div id="app" class="score-case">
      <div class="table">
        <table>
          <thead>
            <tr>
              <th>编号</th>
              <th>科目</th>
              <th>成绩</th>
              <th>操作</th>
            </tr>
          </thead>
          <tbody>
            ${tr}
          </tbody>
          <tbody>
            <tr>
              <td colspan="5">
                <span class="none">暂无数据</span>
              </td>
            </tr>
          </tbody>

          <tfoot>
            <tr>
              <td colspan="5">
                <span>总分：${total}</span>
                <span style="margin-left: 50px">平均分：${total / data.length}</span>
              </td>
            </tr>
          </tfoot>
        </table>
      </div>

    </div>
    `)
  </script>
</body>
</html>
```

