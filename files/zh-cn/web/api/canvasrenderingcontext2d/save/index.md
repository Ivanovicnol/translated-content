---
title: CanvasRenderingContext2D.save()
slug: Web/API/CanvasRenderingContext2D/save
---
{{APIRef}}

**`CanvasRenderingContext2D.save()`** 是 Canvas 2D API 通过将当前状态放入栈中，保存 canvas 全部状态的方法。

## 语法

```
void ctx.save();
```

## 绘制状态

保存到栈中的绘制状态有下面部分组成：

- 当前的变换矩阵。
- 当前的剪切区域。
- 当前的虚线列表。
- 以下属性当前的值： {{domxref("CanvasRenderingContext2D.strokeStyle", "strokeStyle")}}, {{domxref("CanvasRenderingContext2D.fillStyle", "fillStyle")}}, {{domxref("CanvasRenderingContext2D.globalAlpha", "globalAlpha")}}, {{domxref("CanvasRenderingContext2D.lineWidth", "lineWidth")}}, {{domxref("CanvasRenderingContext2D.lineCap", "lineCap")}}, {{domxref("CanvasRenderingContext2D.lineJoin", "lineJoin")}}, {{domxref("CanvasRenderingContext2D.miterLimit", "miterLimit")}}, {{domxref("CanvasRenderingContext2D.lineDashOffset", "lineDashOffset")}}, {{domxref("CanvasRenderingContext2D.shadowOffsetX", "shadowOffsetX")}}, {{domxref("CanvasRenderingContext2D.shadowOffsetY", "shadowOffsetY")}}, {{domxref("CanvasRenderingContext2D.shadowBlur", "shadowBlur")}}, {{domxref("CanvasRenderingContext2D.shadowColor", "shadowColor")}}, {{domxref("CanvasRenderingContext2D.globalCompositeOperation", "globalCompositeOperation")}}, {{domxref("CanvasRenderingContext2D.font", "font")}}, {{domxref("CanvasRenderingContext2D.textAlign", "textAlign")}}, {{domxref("CanvasRenderingContext2D.textBaseline", "textBaseline")}}, {{domxref("CanvasRenderingContext2D.direction", "direction")}}, {{domxref("CanvasRenderingContext2D.imageSmoothingEnabled", "imageSmoothingEnabled")}}.

## 示例

### 使用 `save` 方法

这是一段简单的代码片段，使用 `save` 方法保存默认的状态，这样，稍后你就可以使用默认的设置绘制一个矩形。

#### HTML

```html
<canvas id="canvas"></canvas>
```

#### JavaScript

```js
var canvas = document.getElementById("canvas");
var ctx = canvas.getContext("2d");

ctx.save(); // 保存默认的状态

ctx.fillStyle = "green";
ctx.fillRect(10, 10, 100, 100);

ctx.restore(); // 还原到上次保存的默认状态
ctx.fillRect(150, 75, 100, 100);
```

修改下面的代码并在线查看 canvas 的变化：

```html hidden
<canvas id="canvas" width="400" height="200" class="playable-canvas"></canvas>
<div class="playable-buttons">
  <input id="edit" type="button" value="Edit" />
  <input id="reset" type="button" value="Reset" />
</div>
<textarea id="code" class="playable-code">
ctx.save();
ctx.fillStyle = "green";
ctx.fillRect(10, 10, 100, 100);
ctx.restore();
ctx.fillRect(150, 75, 100, 100);</textarea>
```

```js hidden
var canvas = document.getElementById("canvas");
var ctx = canvas.getContext("2d");
var textarea = document.getElementById("code");
var reset = document.getElementById("reset");
var edit = document.getElementById("edit");
var code = textarea.value;

function drawCanvas() {
  ctx.clearRect(0, 0, canvas.width, canvas.height);
  eval(textarea.value);
}

reset.addEventListener("click", function() {
  textarea.value = code;
  drawCanvas();
});

edit.addEventListener("click", function() {
  textarea.focus();
})

textarea.addEventListener("input", drawCanvas);
window.addEventListener("load", drawCanvas);
```

{{ EmbedLiveSample('Playable_code', 700, 360) }}

## 规范描述

{{Specifications}}

## 浏览器兼容性

{{Compat("api.CanvasRenderingContext2D.save")}}

## 参见

- 接口定义， {{domxref("CanvasRenderingContext2D")}}.
- {{domxref("CanvasRenderingContext2D.restore()")}}
