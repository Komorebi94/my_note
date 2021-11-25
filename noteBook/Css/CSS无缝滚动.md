### CSS无缝滚动

```html

<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }
        
        div {
            height: 40px;
            line-height: 40px;
            overflow: hidden;
        }
        
        ul.scroll {
            animation: scrollY 8s linear infinite;
        }
        
        @keyframes scrollY {
            from {
                transform: translateY(0%);
            }
            to {
                transform: translateY(-200%);
            }
        }
    </style>
</head>

<body>
    <div>
        <ul class="scroll">就尽量少的圣诞节福利三速度快萨克</ul>
        <ul class="scroll">两三点开飞机上看熟练度附近阿克苏</ul>
        <ul class="scroll">就尽量少的圣诞节福利三速度快萨克</ul>
        <ul class="scroll">两三点开飞机上看熟练度附近阿克苏</ul>
    </div>
</body>

</html>
```

