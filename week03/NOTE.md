# 每周总结可以写在这里

## JS 标准里面有哪些对象是我们无法实现的，都有哪些特性

#### Function Object

- `[[call]] `视为函数Function
- `[[Construct]] `可以被new 操作符调用，根据new的规则返回对象 Array Object
- Property == length 设置对象的length属性，根据length的变化对对象进行操作
- newLength > length 用空扩充数组
- ewLength < length 截取数组

#### String Object

- 内部使用` [[StringData]]` 存储原始字符串值
- 字符串提供了一个` length` 属性来访问其长度

#### Array Object

+ 数组对象都有一个  `length` 属性
+ 当` length `属性改变的时候，任何 index 值大于等于 length 的项都会被删除

#### Arguments Object

- `[[callee]] `视为函数参数对对象，伪数组 caller

#### Module Namespece

- `[[Module]] `视为一个引入的模块` [[Exports]]` 视为一个导出的模块

#### Date Object

#### RegExp Object