---
title: Geolocation.clearWatch()
slug: Web/API/Geolocation/clearWatch
---
{{ APIref("Geolocation API") }}

**`Geolocation.clearWatch()`**这个方法主要用于使用 {{domxref("Geolocation.watchPosition()")}} 注册的 位置/错误 监听器。

## 语法

```plain
navigator.geolocation.clearWatch(id);
```

### 参数

- _id_
  - : 希望移除的监听器所对应的 {{domxref("Geolocation.watchPosition()")}} 返回的 ID 数字。

## 示例

```js
var id, target, option;

function success(pos) {
  var crd = pos.coords;

  if (target.latitude === crd.latitude && target.longitude === crd.longitude) {
    console.log('Congratulation, you reach the target');
    navigator.geolocation.clearWatch(id);
  }
};

function error(err) {
  console.warn('ERROR(' + err.code + '): ' + err.message);
};

target = {
  latitude : 0,
  longitude: 0,
}

options = {
  enableHighAccuracy: false,
  timeout: 5000,
  maximumAge: 0
};

id = navigator.geolocation.watchPosition(success, error, options);
```

## 规范

{{Specifications}}

## 浏览器兼容性

{{Compat("api.Geolocation.clearWatch")}}

## 相关链接

- [使用地理位置定位](/en-US/docs/WebAPI/Using_geolocation)
- {{domxref("Geolocation")}}
- {{domxref("Geolocation.watchPosition()")}}
- {{domxref("Geolocation.getCurrentPosition()")}}
