# Markdown 语法学习

*「柳外轻雷池上雨，雨声滴碎荷声。小楼西角断虹明」  - 欧阳修*

### 1. 使用 = 和 - 标记一级和二级标题

```markdown
我展示的是一级标题
=================

我展示的是二级标题
-----------------
```

### 2. 使用 # 号标记

使用 **#** 号可表示 1-6 级标题，一级标题对应一个 **#** 号，二级标题对应两个 **#** 号，以此类推。

```
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题
```

### 3. Markdown 段落

Markdown 段落没有特殊的格式，直接编写文字就好，**段落的换行是使用两个以上空格加上回车**。

### 4. 字体

Markdown 可以使用以下几种字体：

*：斜体 

**：粗体

***：粗斜体

```
*斜体文本*
_斜体文本_
**粗体文本**
__粗体文本__
***粗斜体文本***
___粗斜体文本___
```

### 5. 分割线

 你可以在一行中用三个以上的星号、减号、底线来建立一个分隔线 ---

```
***

* * *

*****

- - -

----------
```

### 6. 删除线

 如果段落上的文字要添加删除线，只需要在文字的两端加上两个波浪线 **~~** 即可 

~~Delete~~

```
RUNOOB.COM
GOOGLE.COM
~~BAIDU.COM~~
```

### 7. 下划线

 下划线可以通过 HTML 的 《u》 标签来实现： 

<u>下划线</u>

注意，Markdown中的html片段会被识别，但是不会实时解析或呈现，另外，原始的Markdown源文件被保存后可能会重新格式化。 

```
<u>带下划线文本</u>
```

### 8. 脚注

脚注是对文本的补充说明。

Markdown 脚注的格式如下:

创建脚注格式类似这样 [^RUNOOB]。

[^RUNOOB]: 菜鸟教程 -- 学的不仅是技术，更是梦想！！！

```
[^要注明的文本]
```

```
创建脚注格式类似这样 [^RUNOOB]。

[^RUNOOB]: 菜鸟教程 -- 学的不仅是技术，更是梦想！！！
```

### 9. 列表

Markdown 支持有序列表和无序列表。

无序列表使用星号(*****)、加号(**+**)或是减号(**-**)作为列表标记，这些标记后面要添加一个空格，然后再填写内容：

```
* 第一项
* 第二项
* 第三项

+ 第一项
+ 第二项
+ 第三项


- 第一项
- 第二项
- 第三项
```

 有序列表使用数字并加上 **.** 号来表示，如： 

```
1. 第一项
2. 第二项
3. 第三项
```

 列表嵌套只需在子列表中的选项前面添加四个空格即可： 

```
1. 第一项：
    - 第一项嵌套的第一个元素
    - 第一项嵌套的第二个元素
2. 第二项：
    - 第二项嵌套的第一个元素
    - 第二项嵌套的第二个元素
```

### 10. 区块

 Markdown 区块引用是在段落开头使用 **>** 符号 ，然后后面紧跟一个**空格**符号： 

> 区块

```
> 区块引用
> 菜鸟教程
> 学的不仅是技术更是梦想
```

### 11. 代码

 如果是段落上的一个函数或片段的代码可以用反引号把它包起来（**`**），例如： 

`printf()`

```
`printf()` 函数
```

  你也可以用 **```** 包裹一段代码，并指定一种语言（也可以不指定）： 

`代码`

```
​```javascript
$(document).ready(function () {
    alert('RUNOOB');
});
​```
```

### 11. 链接

 链接使用方法如下： 

[菜鸟教程](https://www.runoob.com)

```
[链接名称](链接地址)

或者

<链接地址>
```

```
这是一个链接 [菜鸟教程](https://www.runoob.com)
```

### 12. 图片

 Markdown 图片语法格式如下： 

- 开头一个感叹号 !
- 接着一个方括号，里面放上图片的替代文字
- 接着一个普通括号，里面放上图片的网址，最后还可以用引号包住并加上选择性的 'title' 属性的文字。

```
![alt 属性文本](图片地址)

![alt 属性文本](图片地址 "可选标题")
```

```
![RUNOOB 图标](http://static.runoob.com/images/runoob-logo.png)
```

![RUNOOB 图标](http://static.runoob.com/images/runoob-logo.png)

### 13. 表格

 Markdown 制作表格使用 **|** 来分隔不同的单元格，使用 **-** 来分隔表头和其他行。 

```
|  表头   | 表头  |
|  ----  | ----  |
| 单元格  | 单元格 |
| 单元格  | 单元格 |
```

| 表头   | 表头   |
| ------ | ------ |
| 单元格 | 单元格 |
| 单元格 | 单元格 |

对齐方式

**我们可以设置表格的对齐方式：**

- **-:** 设置内容和标题栏居右对齐。
- **:-** 设置内容和标题栏居左对齐。
- **:-:** 设置内容和标题栏居中对齐。  

```
| 左对齐 | 右对齐 | 居中对齐 |
| :-----| ----: | :----: |
| 单元格 | 单元格 | 单元格 |
| 单元格 | 单元格 | 单元格 |
```

| 左对齐 | 右对齐 | 居中对齐 |
| :----- | -----: | :------: |
| 单元格 | 单元格 |  单元格  |
| 单元格 | 单元格 |  单元格  |

### 13. HTML元素

不在 Markdown 涵盖范围之内的标签，都可以直接在文档里面用 HTML 撰写。

目前支持的 HTML 元素有：`       `等 ，如：

```
使用 <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>Del</kbd> 重启电脑
```

<kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>Del</kbd>

### 14.  转义字符

 Markdown 支持以下这些符号前面加上反斜杠来帮助插入普通的符号： 

```
\   反斜线
`   反引号
*   星号
_   下划线
{}  花括号
[]  方括号
()  小括号
#   井字号
+   加号
-   减号
.   英文句点
!   感叹号
```

### 15. 公式

当你需要在编辑器中插入数学公式时，可以使用两个美元符 $$ 包裹 TeX 或 LaTeX 格式的数学公式来实现。提交后，问答和文章页会根据需要加载 Mathjax 对数学公式进行渲染。如： 

上下标（supscript & subscript)![1610408190882](C:\Users\lizhiyao\AppData\Roaming\Typora\typora-user-images\1610408190882.png)

```
$$
\mathbf{V}_1 \times \mathbf{V}_2 =  \begin{vmatrix} 
\mathbf{i} & \mathbf{j} & \mathbf{k} \\
\frac{\partial X}{\partial u} &  \frac{\partial Y}{\partial u} & 0 \\
\frac{\partial X}{\partial v} &  \frac{\partial Y}{\partial v} & 0 \\
\end{vmatrix}
${$tep1}{\style{visibility:hidden}{(x+1)(x+1)}}
$$
```

$$
\mathbf{V}_1 \times \mathbf{V}_2 =  \begin{vmatrix} 
\mathbf{i} & \mathbf{j} & \mathbf{k} \\
\frac{\partial X}{\partial u} &  \frac{\partial Y}{\partial u} & 0 \\
\frac{\partial X}{\partial v} &  \frac{\partial Y}{\partial v} & 0 \\
\end{vmatrix}
${$tep1}{\style{visibility:hidden}{(x+1)(x+1)}}
$$

### 16. 其他高级技巧

流程图等：[高级技巧]( https://www.runoob.com/markdown/md-advance.html )

