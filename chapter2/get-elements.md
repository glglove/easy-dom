Document 对象提供了属性和方法实现定位页面元素功能，这也是 DOM 的标准规范中 Document 对象的主要应用之一。

## 定位页面元素方法

目前 Document 对象提供实现定位页面元素的方法具有如下几种:

- getElementById()方法：通过页面元素的 id 属性值定位元素。
- querySelectorAll()方法：通过 CSS 选择器定位所有匹配的元素。

## 通过元素的 ID 属性值定位元素

其语法格式如下:

```javascript
element = document.getElementById(id);
```

在上述语法中，id 是参数，表示所要定位元素的 id 属性值，是一个大小写敏感的字符串。element 是返回值，表示定位的元素，是一个 Element 对象。

> **值得注意的是:** 如果 HTML 页面中不存在具有该 id 属性值的元素，则返回 null。
下面是使用 getElementById() 方法的示例代码:

```javascript
var btn = document.getElementById('btn');
```

## 通过元素的 name 属性值定位元素

```javascript
elements = document.getElementsByName(name);
```

在上述语法中，name 是参数，表示所要定位元素的 name 属性值，是一个大小写敏感的字符串。elements 是返回值，表示定位元素的集合，是一个 NodeList 集合。

```javascript
var elems = document.getElementsByName('btn');
```

上述代码通过 getElementsByName() 方法定位 HTML 页面中 name 属性值为 btn 的元素，并遍历所有得到的元素，为其元素的 class 属性添加 animate 样式。

## 通过元素的元素名定位元素

```javascript
elements = document.getElementsByTagName(name);
```

在上述语法中，name 是参数，表示所要定位元素的元素名，符号”*”表示所有元素。elements 是返回值，表示定位元素的集合，是一个 NodeList 集合。

```javascript
var elems = document.getElementsByTagName('button');
```

上述代码通过 getElementsByTagName() 方法定位 HTML 页面中元素名为 button 的元素，并遍历所有得到的元素，为其元素的 class 属性添加 animate 样式。

## 通过元素的 class 属性值定位元素

```javascript
elements = document.getElementsByClassName(names);
```

在上述语法中，names 是参数，表示所要定位元素的 class 属性值列表，class 名称通过空格分隔。

> **值得注意的是:** names 参数可以是一个样式属性名称，也可以是多个样式属性名称。

elements 是返回值，表示定位元素的集合，是一个 NodeList 集合。

下面是使用 getElementsByClassName() 方法的示例代码:
var elems = document.getElementsByClassName('btn');
```

上述代码通过 getElementsByClassName() 方法定位 HTML 页面中 class 属性值为 btn 的元素，并遍历所有得到的元素，为其元素的 class 属性添加 animate 样式。

#### 兼容 IE 8 及之前版本的浏览器

getElementsByClassName() 方法只支持 IE 9 版本及之后版本的浏览器。也就是说，该方法并不支持 IE 8 及之前版本的浏览器。

下图是不同浏览器的不同版本对 getElementsByClassName() 方法的支持情况:

![](images/chapter2/02.png)

由于国内的生产环境中，依旧存在使用 IE 8 及之前版本浏览器的情况。所以，我们需要自定义 getElementsByClassName() 方法解决浏览器的兼容问题。

```javascript
function getElementsByClassName(element, names) {
```

上述自定义兼容方法接受两个参数，element 参数表示调用 getElementsByClassName() 方法的对象（目前为 Document 对象），names 参数表示所要定位元素的 class 属性值列表。

```javascript
function getElementsByClassName(element, names) {
```

这里我们要优先使用 W3C 规范的方法。所以，需要先判断当前浏览器环境是否存在 getElementsByClassName() 方法。

如果存在，就使用原本的 getElementsByClassName() 方法。如果不存在，就使用自定义代码来实现。

```javascript
function getElementsByClassName(element, names) {
        
        // 获取所有后代元素节点
        // 定义空数组
        // 将样式名称改为数组类型
        // 循环遍历所有元素节点
        	  // 获取每个元素节点的样式名称
            // 开启开关
            // 循环遍历所有的样式名称
                // 判断当前元素节点的样式名称中是否包含指定的样式名称
                    // 如果不包含，则关闭开关，并且结束循环
            // 判断当前元素节点是否包含指定样式名称
                // 如果包含，则将当前元素节点添加到数组中
        // 返回数组(所有包含指定样式名称的元素节点)
```

## 通过 CSS 选择器定位元素

- querySelector(): 定位匹配选择器的第一个元素。
- querySelectorAll(): 定位匹配选择器的所有元素。

#### querySelector() 方法

其语法格式如下:

```javascript
element = document.querySelector(selectors);
```

在上述语法中，selectors 是参数，表示选择器，可以包含一个或多个 CSS 选择器，多个则以逗号分隔。element 是返回值，表示定位元素的集合，匹配的第一个元素。

下面是使用 querySelector() 方法的示例代码:
var btn = document.querySelector(’#btn');
```

上述代码通过 querySelector() 方法定位 HTML 页面中 id 属性值为 btn 的元素，并为其元素的 class 属性添加 animate 样式。

#### querySelectorAll() 方法

其语法格式如下:

```javascript
elements = document.querySelectorAll(selectors);
```

在上述语法中，selectors 是参数，表示选择器，可以包含一个或多个 CSS 选择器，多个则以逗号分隔。elements 是返回值，表示定位元素的集合，是一个 NodeList 集合。

下面是使用 querySelectorAll() 方法的示例代码:
var elems = document.querySelectorAll('button');
```

上述代码通过 querySelectorAll() 方法定位 HTML 页面中元素名为 button 的元素，并遍历所有得到的元素，为其元素的 class 属性添加 animate 样式。

## 节点集合 NodeList



NodeList 集合分为两种: 动态 NodeList 和静态 NodeList。

### 动态的 NodeList 集合

以下几种定位 HTML 页面元素的方法返回的都是动态的 NodeList 集合。
- getElementsByTagName()方法：通过页面元素的元素名定位元素。
- getElementsByClassName()方法：通过页面元素的 class 属性值定位元素。

```javascript
var elems = document.getElementsByTagName('button');
```

上述代码通过 getElementsByTagName() 方法定位 HTML 页面中所有的 button 元素，测试打印 button 元素的个数是 3 个。

然后，我们创建一个新的 button 元素，并且将其添加到 HTML 页面中，再测试打印 button 元素的个数是 4 个。

> **值得注意的是:** 我们在第二次测试打印 button 元素的个数时，并没有重新定位 HTML 页面中的 button 元素。

### 静态 NodeList 集合

所谓静态 NodeList 集合，就是对文档对象模型的任何改动都不会影响集合的内容。

我们可以通过以下示例代码，体验静态 NodeList 集合的特点:

```javascript
var elems = document.querySelectorAll('button');
```

上述代码通过 querySelectorAll() 方法定位 HTML 页面中所有的 button 元素，测试打印 button 元素的个数是 3 个。

然后，我们创建一个新的 button 元素，并且将其添加到 HTML 页面中，再测试打印 button 元素的个数依旧是 3 个。

## 定位页面元素属性

Document 对象也提供了一些属性，来定位 HTML 页面中一些比较特殊的元素。

- documentElement：获取 HTML 页面中的 `<html>` 元素。

```javascript
console.log(document.documentElement);
console.log(document.head);
console.log(document.body);
console.log(document.title);
console.log(document.links);
console.log(document.images);
```