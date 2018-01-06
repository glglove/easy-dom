## CSS 样式的优先级别

通过 DOM 操作 HTML 页面中指定元素的样式时，只需要获取其运行时的有效样式即可。

## getComputedStyle() 方法

其语法结构如下:

```javascript
var style = window.getComputedStyle(element, [pseudoElt]);
```

上述语法结构中，向 getComputedStyle() 方法传递的 element 参数表示获取有效样式的指定元素。而 pseudoElt 参数是个可选项，指定一个要匹配的伪元素的字符串。

> **值得注意的是:** pseudoElt 参数必须对普通元素省略（或 null）。

getComputedStyle() 方法的返回值是 CSSStyleDeclaration 对象，表示指定元素的有效样式。

我们可以通过以下示例代码，学习 getComputedStyle() 方法的使用方式:

```javascript
var btn = document.getElementById('btn');
```

## currentStyle 属性
var btn = document.getElementById('btn');
```

通过 element.currentStyle 属性得到 currentStyle 对象，该对象提供了有关 CSS 样式表的所有样式属性。

```javascript
function getStyle(elem, attrName){
```