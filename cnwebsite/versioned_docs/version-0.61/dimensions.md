---
id: version-0.61-dimensions
title: Dimensions
original_id: dimensions
---

##### 本文档贡献者：[sunnylqm](https://github.com/search?q=sunnylqm%40qq.com+in%3Aemail&type=Users)(100.00%)

本模块用于获取设备屏幕的宽高。

```jsx
import {Dimensions } from "react-native";
```
You can get device width and height using below :


Get device screen width and height :
```jsx
const screenWidth = Math.round(Dimensions.get('window').width);
const screenHeight = Math.round(Dimensions.get('window').height);
```

---

# 文档

## 方法

### `get()`

```jsx
static get(dim)
```

初始的尺寸信息应该在`runApplication`之后被执行，这样才可以在任何其他的 require 被执行之前使用。不过在稍后可能还会更新。

> 注意：尽管尺寸信息立即就可用，但它可能会在将来被修改（譬如设备的方向改变），所以基于这些常量的渲染逻辑和样式应当每次 render 之后都调用此函数，而不是将对应的值保存下来。（举例来说，你可能需要使用内联的样式而不是在<code>StyleSheet</code>中保存相应的尺寸）。

示例： `const {height, width} = Dimensions.get('window');`

**Parameters:**

| Name      | Type     | Required | Description                                                                                   |
| ------    | ------   | -------- | ----------------------------------------------------------------------------------------------|
| dim       | string   | Yes      | 想要获取的尺寸信息的字段名。 @returns {Object?} 返回的尺寸信息值。  | 

> For Android the `window` dimension will exclude the size used by the `status bar` (if not translucent) and `bottom navigation bar`

---

### `addEventListener()`

```jsx
static addEventListener(type, handler)
```

Add an event handler. Supported events:

- `change`: Fires when a property within the `Dimensions` object changes. The argument to the event handler is an object with `window` and `screen` properties whose values are the same as the return values of `Dimensions.get('window')` and `Dimensions.get('screen')`, respectively.

---

### `removeEventListener()`

```jsx
static removeEventListener(type, handler)
```

Remove an event handler.

---

### `set()`

```jsx
static set(dims)
```

这个函数只应该被原生代码调用。 by sending the didUpdateDimensions event.

**Parameters:**

| Name      | Type     | Required | Description                               |
| ------    | ------   | -------- | ------------------------------------------|
| dims      | object   | Yes      | string-keyed object of dimensions to set  | 

