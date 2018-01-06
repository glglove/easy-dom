Element 对象提供一系列有关样式的属性:


Element 对象的 clientWidth 和 clientHeight 属性表示元素内部的宽度和高度，单位为像素。这些属性的值包含内边距，但不包含滚动条、边框和外边距。

我们也可以通过以下方式计算 clientWidth 和 clientHeight 属性:


我们可以通过以下示例代码，学习测试 clientWidth 和 clientHeight 属性:

```javascript
var div = document.getElementById('d');
```

## 内容区的宽度和高度

Element 对象的 scrollWidth 属性表示元素内容的宽度，单位为像素。 scrollWidth 属性返回元素内容区的宽度和元素本身宽度中更大的那个值。

Element 对象的 scrollHeight 属性表示元素内容的高度，单位为像素。scrollHeight 属性包含 overflow 样式属性导致不可见的内容区。

我们可以通过以下示例代码，学习测试 scrollWidth 和 scrollHeight 属性:

```javascript
var div1 = document.getElementById('d1');
console.log(div1.scrollWidth);

var div2 = document.getElementById('d2');
console.log(div2.scrollHeight);
```

## 滚动条滚动的宽度和高度

Element 对象的 scrollLeft 属性表示滚动条到元素左边的距离，单位为像素。scrollLeft 属性的默认值为 0。

Element 对象的 scrollTop 属性表示滚动条到元素顶部的距离，单位为像素。scrollHeight 属性的默认值为 0。

## 判断元素内容是否滚动到底

```

![](images/chapter5/16.png)

## 获取指定元素的定位父元素

```javascript
var parentObj = element.offsetParent;
```

上述语法结构中，作为返回值的 parentObj 表示一个指向最近的包含该元素的定位元素。

```html
<style>
```

### offsetParent 属性的浏览器兼容性

- 在 Webkit 中，如果元素为隐藏的（该元素或其祖先元素的 style.display 为 "none"），或者该元素的 style.position被设为 "fixed"，则该属性返回 null。
- 在 IE 9 中，如果该元素的 style.position 被设置为 "fixed"，则该属性返回 null。（display:none 无影响。）

- 指定元素的 offsetWidth 和 offsetHeight 属性分别表示该元素的布局宽度和布局高度，其中包含边框、内边距、滚动条和 CSS 设置的宽度或高度的值。