# css3-switch
利用css3实现背景图片动画切换效果

##### demo地址：(https://htmlpreview.github.io/?https://github.com/xiaokk06/css3-switch/blob/master/switch.html)


主要用到了一些新的CSS3属性来完成这个动态效果

transition和keyframes不用多说，一个用来应用动画，一个用来定义动画
这里为了简便起见 ，只设置了简单的0%到100%之间的过渡效果，过渡效果基本涵盖了比较常见的一些CSS3属性，这里不细细展开

主要注意的是一个<i>:target结构性伪类选择器</i>和<i>nth-of-type(n)选择器</i><br>
:target选择器称为目标选择器，用来匹配文档(页面)的url的某个标志符的目标元素。<br>

>       <img src="images/bg1.jpg" alt="" class="bg slideLeft" id="bg1" />
>       .slideLeft:target {
        <!-- do something -->
        }
        *这里的:target就是指id="bg1"的div对象，如下*/
        <li><a href="#bg1">Hipster Fashion Haircut </a></li>

nth-of-type(n)选择器
“:nth-of-type(n)”选择器和“:nth-child(n)”选择器非常类似，不同的是它只计算父元素中指定的某种类型的子元素。当某个元素中的子元素不单单是同一种类型的子元素时，使用“:nth-of-type(n)”选择器来定位于父元素中某种类型的子元素是非常方便和有用的。在“:nth-of-type(n)”选择器中的“n”和“:nth-child(n)”选择器中的“n”参数也一样，可以是具体的整数，也可以是表达式，还可以是关键词。

######这里注意一下：<br>
下面是我在实际写的过程中遇到的一个坑，主要是因为没有正确理解上面的解释，具体说明如下
>        /*只计算父元素中指定的某种类型的子元素*/
        /*换成a:nth-of-type(1)之后a的父元素始终为li
        li中只有一个a所有之后的样式无效 
        5gea共用这一个样式 即背景颜色相同*/
        li:nth-of-type(1) a {
            background-color: #02646e;
        }

有关其他问题可以查看源码 注释比较清楚

参考资料：
* ![慕课网](http://www.imooc.com/code/1882)
* ![mozilla mdn](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:nth-of-type)

