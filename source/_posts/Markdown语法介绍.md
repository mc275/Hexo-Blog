---
title: Markdown语法介绍
top: false
comments: true
date: 2018-04-02 10:09:00
tags: Markdown
categories: Coding
---

# 前言
最近准备开始写博客，整理自己学习的技术知识。但手动调整博客的文本格式实在太不美观和geek，因而选择Markdown排版博客内容。Markdown是一种轻量级标记语言，且兼容HTML。可通过标记符号设置文本格式，让作者专注于写作内容，当前的主流博客网站和GitHub版块多采用Markdown。

Markdown将格式对象主要分为**区块元素**和**区段元素**两部分。区块元素主要包括*段落*，*换行*，*标题*，*区块引用*，*列表*和*分割线*；区段元素包括*强调*，*链接*，*图片*和*代码块*。

<!-- more -->

# 区块元素

## 段落和换行
Markdown中段落是由*一个或多个连续的本文组成*，段落前后应该有1个以上的空行，单独的换行符不会实现段落换行。如果不想插入空行进行换行，可以在换行符前插入2个以上的空格来实现段落换行。例如：
>
>第一段
>
>第二段

或
>第一段(两空格)  
第二段

## 标题
在标题文本前使用“#”，并用空格分割可以创建一级标题。如果需要创建多级标题，可使用不同数量的“#”，最多可创建6级标题。如下所示：
>\# 一级标题  
>\#\# 二级标题  
\#\#\# 三级标题  
\#\#\#\# 四级标题  
\#\#\#\#\# 五级标题  
\#\#\#\#\#\# 六级标题  

## 区块引用
Markdown标记区块引用时，在每行的开头添加符号">"或在每段的第一行开头添加">"，如下所示：
> \> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

或
> \> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
\>Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

效果如下：
> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
>Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

另外区块引用允许多级嵌套，只需根据层次添加不同数量的">"。例如：
> \> 这是第一级引用。    
\>  
\> \> 这是第二级引用。  
\>  
\> 现在回到第一级引用。

效果如下
> 这是第一级引用。
>
> > 这是第二级引用。
>
> 现在回到第一级引用。

## 列表
Markdown支持有序列表和无序列表。

*无序列表*使用“*”，"+"和"-"作为记号，通常放在最左侧，记号与文本间用空格分割。
> \* 列表1  
  \* 列表2  
  \* 列表3  
  
效果如下
* 列表1
* 列表2
* 列表3
  
*有序列表*使用数字加英文句号作为记号，记号与文本间用空格分割，且有序列表的序号与记号中的数字无关。例如以下两组列表，生成的列表序号相同。
> 1\. 列表1  
  2\. 列表2  
  3\. 列表3  

与

> 1\. 列表1  
  1\. 列表2  
  1\. 列表3  

效果如下
1. 列表1
1. 列表2
1. 列表3

如果需要在列表中加入区块引用或代码块，则整个区块或代码块需整体缩进4个空格或一个制表符，例如：
> \* 列表1  
>&nbsp; &nbsp; &nbsp; &nbsp; \> 引用内容

效果如下所示
* 列表1
    > 引用内容

## 分割线
在单独的一行中使用三个以上的星号"*"，减号“-”或底线"_"来创建分割线，且行内不能再有其他内容。
> \_\_\_  
  \*\*\*  
  \-\-\-
  
效果如下
***
  


# 区段元素

## 强调
强调包括**斜体**和**加粗**两种方式。

斜体使用一对“*”包裹需要强调的文字，例如:
> \*斜体*

其效果为：*斜体*

加粗使用一对“**”包裹需要强调的文字，例如：
> \**加粗**

其效果为：**加粗**


## 代码块
标记代码块的方式有两种。一种是通过**缩进**4个空格或1个制表符进行标记；更**常用**的方法是使用反引号将代码块包裹起来，避免无休止的缩进。该方法可指定语言标识，对标记的代码块启用语法着色。例如：
> \`\`\`python    
> import sys  
>img_list_in = open(sys.argv[1])  
\`\`\`

效果如下：
```python
import sys
img_list_in = open(sys.argv[1])
```

## 链接
Markdown支持两种链接的表示方式：**内联式**和**引用式**。

**内联式**的表示形式为 *\[text] (URL)*。其中，\[]中的内容是链接文字，()中的内容是链接地址。例如：
> This is \[GitHub\] (https://www.github.com) link.

效果如下
This is [GitHub](https://www.github.com) link.

**引用式**的表示方式为
> \[text] \[id\]
>
> \[id\]: URL 

例如：
> This is \[GitHub] \[github] link.
>
> \[github\]: https://www.github.com

效果如下：
This is [GitHub] [github] link.

[github]: https://www.github.com


## 插入图片
Markdown使用与链接相似的语法来插入图片，也可分为内联式和引用式。

内联式插入图片的语法为：
> \!\[text] (URL)

引用式插入图片的语法为：
> \!\[text] [id]
>
> \[id]: URL

例如：
>\!\[CR7](http://bestsportsshots.com/wp-content/uploads/2018/01/cr7-power.jpg)

或
> \!\[CR7] [player]
>
> \[player]: http://bestsportsshots.com/wp-content/uploads/2018/01/cr7-power.jpg

效果如下
![CR7](http://bestsportsshots.com/wp-content/uploads/2018/01/cr7-power.jpg)


需要注意的是，Markdown无法指定插入图片的宽高。如果需要，可以使用 <img\>标签。
