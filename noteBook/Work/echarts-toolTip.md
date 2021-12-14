### charts tooltip 显示不全问题

```js
position: function (point, params, dom, rect, size) {
  // 鼠标坐标和提示框位置的参考坐标系是：以外层div的左上角那一点为原点，x轴向右，y轴向下
  // 提示框位置
  let x = 0; // x坐标位置
  let y = 0; // y坐标位置
 
  // 当前鼠标位置
  let pointX = point[0];
  let pointY = point[1];
 
  // 外层div大小
  // var viewWidth = size.viewSize[0];
  // var viewHeight = size.viewSize[1];
 
  // 提示框大小
  let boxWidth = size.contentSize[0];
  let boxHeight = size.contentSize[1];
 
  // boxWidth > pointX 说明鼠标左边放不下提示框
  if (boxWidth > pointX) {
    x = 5;
  } else { // 左边放的下
    x = pointX - boxWidth;
  }
 
  // boxHeight > pointY 说明鼠标上边放不下提示框
  if (boxHeight > pointY) {
    y = 5;
  } else { // 上边放得下
    y = pointY - boxHeight;
  }
 
  return [x, y];
}
```

