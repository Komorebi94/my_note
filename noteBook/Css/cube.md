### 立方体

```html
<!DOCTYPE html>
<html>

<head>
    <title>Cube</title>
    <meta charset="utf-8">
    <style type="text/css">
        div {
            width: 300px;
            height: 300px;
            border-radius: 50%;
        }

        .box {
            margin: 200px auto 0;
            position: relative;
            /*3D转换*/
            transform-style: preserve-3d;
            transform: rotateY(45deg) rotateX(45deg);
        }

        .box:hover {
            animation: rotate 2s infinite linear;
        }

        /*通过子选择器获取 类box 中的 div 儿子级别的*/
        .box>div {
            position: absolute;
            font-size: 100px;
            border: 1px solid black;
            text-align: center;
            line-height: 300px;
        }

        .box>div:nth-child(1) {
            background-color: red;
            /*沿着Z轴平移150px；*/
            transform: translateZ(150px);
        }

        .box>div:nth-child(2) {
            background-color: orange;
            transform: rotateY(180deg) translateZ(150px);

        }

        .box>div:nth-child(3) {
            background-color: yellow;
            transform: rotateX(90deg) translateZ(150px);

        }

        .box>div:nth-child(4) {
            background-color: green;
            transform: rotateX(-90deg) translateZ(150px);

        }

        .box>div:nth-child(5) {
            background-color: pink;
            transform: rotateY(90deg) translateZ(150px);

        }

        .box>div:nth-child(6) {
            background-color: purple;
            transform: rotateY(-90deg) translateZ(150px);

        }

        @keyframes rotate {
            from {
                transform: rotateX(0deg) rotateY(0deg);

            }

            to {
                transform: rotateX(360deg) rotateY(360deg);
            }
        }
    </style>
</head>

<body>
    <div class="box">
        <div>宫</div>
        <div>商</div>
        <div>羽</div>
        <div>徽</div>
        <div>角</div>
        <div>哈</div>
    </div>
</body>

</html>
```

