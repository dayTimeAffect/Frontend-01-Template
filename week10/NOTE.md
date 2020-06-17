# 每周总结可以写在这里
把一个元素的所有子元素逆序
```
function reverseChildren(element) {
        Array.from(ul.children).reverse().forEach(node => {ul.append(node)})
    }
```
### Range API
```javascript
//创建 Range
var range = new Range()
range.setStart(element,number)  //用于将某个节点中的某处位置指定为Range对象所代表区域的起点位置
range.setEnd(element,number) //用于将某个节点中的某处位置指定Range对象所代表区域的结束位置
var range = document.getSelection().getRangeAt(0)
```
+ selectNodeContents  选择节点的子节点
+ selectNode 选择整个节点，包括子节点
+ extractContents 用于将Range对象所代表区域中的html代码克隆到一个DocumentFragment对象中，然后从页面中删除这段HTML代码
+ deleteContents 用于将Range对象中所包含的内容从页面中删除

### CSSOM
+ document.styleSheets //Array

#### Rules
+ document.styleSheets[].cssRules //Array

#### Rule
+ CSSStyleRule
    + selectorText String
    + rule

##### getComputedStyle
+ window.getComputedStyle(elt,pseudoElt) //elt 元素 pseudoElt可选，伪元素


####
+ window.open(url,打开方式,)
