# Javascript

## DateType(數據類型)

### 基本類型(pass by value)
    1.Undefined  
    2.Null  
    3.Boolean  
    4.Number  
    5.String  
    
### 複雜類型(pass by reference)
    1.Object 

---

## this 綁定

1.call 
```js
//返回函數執行的結果
fun.call(thisArg[, arg1[, arg2[, ...]]])
```
2.apply 
```js
//返回函數執行的結果
fun.call(thisArg, [argsArray])
```
3.bind 
```js
//返回原函數
fun.call(thisArg, [argsArray])
```

---

## Data check(數據檢查)
|      | typeof       | instanceof           |
| ---- | ------------ | -------------------- |
| 作用 | 檢測數據類型 | 檢測對象之間的關聯性 |
| 返回 | 字符串       | 布林值               |

```js
typeof '123' //'string'
typeof 123   // 'number'
typeof true  // boolean
typeof null  // object'

[1, 2] instanceof Array // true
[1, 2] instanceof Object // true
[1, 2] instanceof Number // false
[1, 2] instanceof String // false
1 instanceof Number // fasle 因為1並不是創建的實例
```

---

## Math

* Math.floor(): Math.floor() 函式會回傳小於等於所給數字的最大整數。
  
* Math.ceil(): Math.ceil() 函式會回傳大於等於所給數字的最小整數。
