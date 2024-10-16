### 题目一：使用内联样式

**要求**：创建一个包含以下内容的HTML文档，并使用内联样式来美化它。

1. 标题为“内联样式示例”，字体颜色为红色。
2. 段落文本为“这是一个测试段落”，字体大小为20px，背景颜色为黄色。
3. 添加一个蓝色虚线边框的水平线。

**补全代码**：

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>内联样式示例</title>
</head>
<body>
    <h1 style="color:red">内联样式示例</h1>
    <hr style="border:none; border-bottom:2px dashed blue"> /*dashed虚线*/
    <p style="font-size:20px; background-color: yellow;">这是一个测试段落</p>
</body>
</html>
```



### 题目二：使用内部样式表

**要求**：创建一个包含以下内容的HTML文档，并使用内部样式表来美化它。

1. 标题为“内部样式表示例”，字体颜色为紫色。
2. 段落文本为“这是一个使用内部样式表的段落”，背景颜色为黄色，字体颜色为蓝色，宽度为300px，高度为50px。

**补全代码**：

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>内部样式表</title>
    <style>
        h1{
            color:violet;
        }
        p{
            background-color:yellow;
            color:blue;
            width: 300px;
            height: 50px;
        }
    </style>
</head>
<body>
    <h1>内部样式表示例</h1>
    <p>这是一个使用内部样式表的段落</p>
</body>
</html>
```



### 题目三：使用外部样式表

**要求**：创建两个文件，一个HTML文件和一个CSS文件，并使用外部样式表来美化网页。

1. HTML文件包含一个标题为“外部样式表示例”和一个段落，段落文本为“这是一个使用外部样式表的段落”。
2. 在CSS文件中设置标题的字体颜色为绿色，段落的背景颜色为蓝色，字体颜色为黑色。

**补全代码**：

- HTML文件 (`index.html`):

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>使用外部样式表</title>
    <link rel="stylesheet" href="./homework.css">
</head>
<body>
    <h1>外部样式表示例</h1>
    <p>这是一个使用外部样式表的段落</p>
</body>
</html>

```

- CSS文件 (`homework.css`):

```
h1{
    color:green;
}
p{
    color:rgb(2, 0, 0);
}

```



### 题目四：使用CSS选择器

**要求**：创建一个包含多个不同HTML元素的网页，并使用CSS选择器来美化这些元素。

1. 所有`h4`标签的字体颜色为蓝色。
2. 所有类名为“highlight”的段落字体颜色为红色，背景颜色为灰色。
3. id为“special”的段落字体颜色为橙色，字体大小为30px。

**补全代码**：

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>选择器</title>
    <style>
        .highlight{
            color:red;
            background-color:grey;
        }
        #special{
            color:orange;
            font-size:30px;
        }
    </style>
    
</head>
<body>
    <h1>css选择器</h1><br>
    <h4>默认标题，无类</h4>
    <h4 class="highlight">标题，highlight类</h4>
    <h4>默认标题，无类</h4>
    <h4 class="highlight">标题，highlight类</h4>
    <h4>默认标题，无类</h4>
    <h4 class="highlight">标题，highlight类</h4>
    <h4>默认标题，无类</h4>
    <p>我是一个段落，无id</p>
    <p id="special">我是一个段落，id为special,字体大小30px，橙色</p>
</body>
</html>

```

### 