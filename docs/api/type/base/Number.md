基础数字(Number)类型包含双精度浮点数和任意长度的整数

## 格式

数字型可以直接写在代码中，例如

```javascript
114514; //整数
3.14; //浮点数
Infinity; //正无穷
-Infinity; //负无穷
100_000_000; //语法糖，更可读的长数字
114514e3; //114514后3个0，即114514000
1e-6; //1左边有6个零，同等于0.000001
```

需要注意的是，JS 中的科学计数法并不完全遵守 $0\le a\le10$，其转换公式为 $X e a = X\times 10^a$

在数字上直接调用方法时，需要在数字后面多加一个 `.` ，例如 `10086..toString()`
这是因为在数字后面加点时，计算机默认为小数，如果需要使用点来访问方法，则需要同时写上两个点

同样，我们可以写成`(10086).toString()`

## 特殊情况

关于误差，请注意，当一个数字超出常规数字储存方案(64 位包含符号)时，它会变成一个无穷(`Infinity`)
并且，由于浮点数在计算机中以二进制储存，所以在浮点数运算时极有可能出现误差，例如
`0.1+0.2 = 0.30000000000000004`以及`console.log(9999999999999999) // 10000000000000000`

同时，我们需要注意 `NaN` 这个类型，其全称是 `Not a Number`
当数字遇到无法进行的操作时，例如非同类型数字四位运算，则会转变为 `NaN`。

需要注意的是，`NaN`无法直接比较，NaN 与任何数据都不相等（即使`NaN == NaN`的结果也是<bool>false</bool>）。
若要判断一个数据是否是 `NaN`，可以使用<function>isNaN</function>函数。

## 类型转换

<function>Number</function>也可以作为一个函数使用，可以将一个其他类型的数据转换为数字类型，若无法转换，则返回`NaN`

```javascript
console.log(Number("114514" + "1919810"));
console.log(Number("AlanBestHacker"));
```

<div class="result">
输出结果为

```
1145141919810
NaN
```

</div>
