# 题目一：判断年月的天数

```text
# 提示：（考虑闰年 和月份的有效性 )
# 闰年条件：能被4整除，但不能被100整除。或者能够被400整除。
# 输入的示例： let year=prompt("请输入年：")
# 其中year代表输入年的字符串，可以通过year=parseInt(year)将字符串的year转成数值类型的year
```

请填写代码：

```
<!-- 思考
 题目
  # 提示：（考虑闰年 和月份的有效性 )
# 闰年条件：能被4整除，但不能被100整除。或者能够被400整除。
# 输入的示例： let year=prompt("请输入年：")
# 其中year代表输入年的字符串，可以通过year=parseInt(year)将字符串的year转成数值类型的year
 
功能为输入某一年的某一个月的天数

先判断年份且输出是否为闰年
sum+=30 等效于 sum=sum+30  （不要弄成sum+=sum+30）
-->

<script>
  let year = prompt("请输入年：")
  let month = prompt("输入月份（数字1~12）：")
  let num = prompt("当月的日期（1~31）：")

  year = parseInt(year);
  month = parseInt(month);
  num = parseInt(num);
  document.write("输入年份为：" + year + "<br/>")
  document.write("月份为：" + month + "<br/>")
  document.write("当月日期为：" + num + "<br/>")
  document.write("--------------运行效果如下--------------<br/>")


  // 年份定值范围
  if (year < 0) {
    document.write("年份错误请重新输入（年份为正整数）！<br/>")
  }
  else if (year % 4 == 0 && year % 100 > 0 || year % 400 == 0) {
    document.write(year + "年为闰年<br/>");
  }else{
    document.write(year + "年不是闰年<br/>");
  }
  // 月份定值范围
  if (month < 1 || month > 12) {
    document.write("月份错误请重新输入（1~12）！<br/>")
  }
  // 当月日期的定值范围
  if (num < 0 || num > 31) {// 日期必定为整整数,且都小于31
    document.write("当月日期错误请重新输入（参考1-31）！<br/>");
  }
  // 用30天月份排除31天的月份
  else if ((month == 2 || month == 4 || month == 6 || month == 9 || month == 11) && num == 31) {
    document.write("月份输入错误，此月份日期应小于31<br/>");
  }
  // 闰年排除月份28天,当不是闰年是月份2=29时，当月日期报错
  else if ((year % 4 > 0 && year % 100 == 0 || year % 400 > 0 )&& month == 2 && num == 29) {
    document.write("当月日期输入错误,非闰年，2月最高28天<br/>");
  }
  else {
    let sum = 0;// 用以累加天数
    switch (month - 1) {
      case 11: sum += 30;
      case 10: sum += 31;
      case 9: sum += 30;
      case 8: sum += 31;
      case 7: sum += 31;
      case 6: sum += 30;
      case 5: sum += 31;
      case 4: sum += 30;
      case 3: sum += 31;
      case 2:
        if (year % 4 == 0 && year % 100 > 0 || year % 400 == 0) {
          sum += 29;
        }
        else {
          sum += 28;
        }
      case 1: sum += 31;
      case 0: sum += 0;

        sum = sum + num;// 加上当月的天数，合为总天数
        document.write("天数为一年中的第：" + sum + "天<br/>")
    }
  }




</script>
```



# 题目二：猜拳游戏

```
# 说明：
# 0：石头	1：剪刀  2：布
# 玩家通过键盘输入一个0~2的数表示玩家出的是：石头/剪刀/布
# 电脑通过系统随机生成一个0--2的数表示电脑出拳
# 请计算出玩家赢还是计算机赢，若不是0~2的数字返回玩家输入错误
# 随机数生成示例：var num1 = Math.floor(Math.random() * 3);
（其中num1就是随机数)
```

请填写代码：

```
<!-- 思想
 题目
 # 说明：
# 0：石头	1：剪刀  2：布
# 玩家通过键盘输入一个0~2的数表示玩家出的是：石头/剪刀/布
# 电脑通过系统随机生成一个0--2的数表示电脑出拳
# 请计算出玩家赢还是计算机赢，若不是0~2的数字返回玩家输入错误
# 随机数生成示例：var num1 = Math.floor(Math.random() * 3);
（其中num1就是随机数)

floor 为取整
math.random() 为0~1的随机数，然后×3取整，可随机取得整数0,1,2
用于电脑的猜拳

玩家输入用prompt方法
随机输入0,1,2便可

玩家    电脑    
0       0       平局
0       1       玩家赢
0       2       电脑赢

1       0       电脑赢
1       1       平局
1       2       玩家赢

0>1
1>2
2>0

除开平局外，定一个单位，当满足条件这个单位失败、获胜即可
如去除平局后，再去除玩家获胜的可能，那剩下的可能为电脑获胜。

-->

<script>
    // 玩家输入的参数
    let man_1 = prompt("输入✄，石头，布。输入数字，✄=0，石头=1，布=2 ");
    // 电脑随机生成的参数
    let man_2 = Math.floor(Math.random() * 3);// 用整数方法随机生成0,1,2


    man_1 = parseInt(man_1);

    if (man_1 < 0 || man_1 > 2) {
        document.write("输入参数错误，请选择0,1,2 <br/>");
    }
    switch (man_1) {
        case 0: document.write("你输入的为：石头 <br/>");
            break;

        case 1: document.write("你输入的为：✄ <br/>");
            break;

        case 2: document.write("你输入的为：布 <br/>");
            break;
    }
    switch (man_2) {
        case 0: document.write("电脑输入的为：石头 <br/>");
            break;

        case 1: document.write("电脑输入的为：✄ <br/>");
            break;

        case 2: document.write("电脑输入的为：布 <br/>");
            break;
    }

    document.write("比赛结果为：")
    // 当两数相等，则平局
    if (man_1 == man_2) {
        document.write("平局")
    }
    // 玩家获胜的条件
    else if ((man_1 == 0 && man_2 == 1) || (man_1 == 1 && man_2 == 2)|| (man_1 == 2 && man_2 == 0)) {
        document.write("玩家获胜");
    }
    else{
        document.write("电脑获胜");
    }


</script>

```



# 题目三：判断三角形

```
# 任意输入三个数值，判断能否生成一个三角形
# 提示：三角形（任意两边之和大于第三边）
```

请填写代码：

```
<!-- 
 # 任意输入三个数值，判断能否生成一个三角形
# 提示：三角形（任意两边之和大于第三边）

边长    a
边长    b
边长    C
-->

<script>
    let a = prompt("请输入三角形的边长a");
    let b = prompt("请输入三角形的边长b");
    let c = prompt("请输入三角形的边长c");

    a = parseInt(a);
    b = parseInt(b);
    c = parseInt(c);

    document.write("边长a为：" + a + "<br/>");
    document.write("边长b为：" + b + "<br/>");
    document.write("边长c为：" + c + "<br/>");

    if (a + b > c && a + c > b && b + c > a) {
        document.write("可组成一个三角形");
    }
    else {
        document.write("无法组成一个三角形");
    }

</script>
```



# 题目四：排序

```
# 任意输入三个数，利用三元运算符，将这三个数按照从小到大的顺序排列
```

请填写代码：

```
<!-- 
 # 任意输入三个数，利用三元运算符，将这三个数按照从小到大的顺序排列

 可用类似于冒泡的方法，改变位置，小换大解决。
-->

<script>
    let a = prompt("请输入数值a");
    let b = prompt("请输入数值b");
    let c = prompt("请输入数值c");

    a = parseInt(a);
    b = parseInt(b);
    c = parseInt(c);

    document.write("数值a为：" + a + "<br/>");
    document.write("数值b为：" + b + "<br/>");
    document.write("数值c为：" + c + "<br/>");

    

    let d=0;
    if(a>b){
        d=a;
        a=b;
        b=d;
    }
    if(a>c){
        d=a;
        a=c;
        c=d;
    }
    if(b>c){
        d=b;
        b=c;
        c=d;
    }
    
    document.write("小到大排序为："+a+"&nbsp"+b+"&nbsp"+c);

    

</script>
```



# 题目五：求周长和面积

```
# 编写程序，输入长方形的宽与高，输出这个长方形的周长与面积。   
```

请填写代码：

```
<!-- 
 # 编写程序，输入长方形的宽与高，输出这个长方形的周长与面积。   

 简单的加减乘除

 宽     a
 高     b

 周长   （a+b）*2
 面积     a*b
-->

<script>
    let a = prompt("请输入长方形宽");
    let b = prompt("请输入长方形高");

    a = parseInt(a);
    b = parseInt(b);

    // 图形的边长必须大于等于0，为0是则表示没有
    if (a >= 0 && b >= 0) {
        document.write("长方形宽：" + a + "<br/>");
        document.write("长方形高：" + b + "<br/>");

        document.write("长方形周长为：" + (a + b) * 2 + "<br/>");
        document.write("长方形面积为：" + a * b + "<br/>");
    }
    else{
        document.write("图像数值输入错误，图像边长应为正数")
    }





</script>
```



#  题目六：计算成绩

```
# 输入某位学生的三科考试成绩，输出这个学生的三门成绩的 总分、平均分；   
```

请填写代码：

```
<!-- 
 # 输入某位学生的三科考试成绩，输出这个学生的三门成绩的 总分、平均分；   

 简单乘除
 分数应不为负数
-->

<script>
    let a = prompt("输入科目一的分数：");
    let b = prompt("输入科目二的分数：");
    let c = prompt("输入科目三的分数：");

    a = parseInt(a);
    b = parseInt(b);
    c = parseInt(c);

    document.write("科目一分数为：" + a + "<br/>");
    document.write("科目二分数为：" + b + "<br/>");
    document.write("科目三分数为：" + c + "<br/>");

    if (a < 0 || b < 0 || c < 0){
        document.write("输入的分数异常，请重新输入！")
    }
    else{
        document.write("三门科目的总分为："+(a+b+c)+ "<br/>");
        document.write("三门科目的均分分为："+(a+b+c)/3+ "<br/>");
    }
</script>
```

