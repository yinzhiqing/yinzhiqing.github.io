---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_markdown_edit
title: Edit Markdown file

# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: yinzhiqing
# multiple category is not supported
category: language
# multiple tag entries are possible
tags: [yzq, new feature]
# thumbnail image for post
img: ":mock1.jpg"
# disable comments on this page
#comments_disable: true

# publish date
date: 2022-08-12 12:32:10 +0800

# seo
# if not specified, date will be used.
#meta_modify_date: 2022-03-03 12:32:10 +0900
# check the meta_common_description in _data/owner/[language].yml
#meta_description: ""

# optional
# if you enabled image_viewer_posts you don't need to enable this. This is only if image_viewer_posts = false
#image_viewer_on: true
# if you enabled image_lazy_loader_posts you don't need to enable this. This is only if image_lazy_loader_posts = false
#image_lazy_loader_on: true
# exclude from on site search
#on_site_search_exclude: true
# exclude from search engines
#search_engine_exclude: true
# to disable this page, simply set published: false or delete this file
#published: false
---

<!-- outline-start -->

GitHub markdown file format. <!-- outline-end -->

## 注意
　字符用半角
 
## 标题
  第一种是使用 # 表示标题，其中 # 号必须在行首，(1～6个＃)
  第二种是使用 === 或者 --- 表示。

**格式：**
```
# 标题１
## 标题2
### 标题3
#### 标题4
##### 标题5
###### 标题６
```
**显示效果：**

## 标题2（＃＃）
### 标题3（＃＃＃）
#### 标题4（＃＃＃＃）
##### 标题5（＃＃＃＃＃）
###### 标题６（＃＃＃＃＃＃）

**格式：**
```
标题
===

标题
---
```
**显示效果：**

标题
===

标题
---

## 分割线

使用三个或以上的 - 或者 * 表示，且这一行只有符号，注意不要被识别为二级标题即可，例如中间或者前面可以加空格。

**格式：**
```
分割线上

---

分割线下
```

**显示效果：**

分割线上

---

分割线下

## 斜体和粗体

使用 * 和 ** 分别表示斜体和粗体，删除线使用两个 ~~ 表示

格式：
```
  *斜体*　　　**粗体**　　***斜且粗***　　~~删除~~
```

**显示效果：**

*斜体(*x*)*　　　**粗体（**x**）**　　***斜且粗(***x***)***　　~~删除(~~x~~)~~

## 超链接和图片

**格式（链接）：**
```
［文字表述］（https://www.baidu.com　"baidu"）
```
**显示效果：**

 [百度首页](https://www.baidu.com　"baidu")
 
**格式（图片):**

```
 ![文字描述](demo.jpeg)
```
***显示效果：***

 ![本地图片](./demo.jpeg)
 
 **格式（链接ＩＤ)**
 
 ```
 [名称][id]
 
 [id]:http://example.com  "鼠标悬浮标题（可选）"
 ```
 - [百度][1] 
 - [新浪][2]
 
 [1]:https://www.baidu.com/ "baidu"
 [2]:https://www.sina.com.cn/ "sina"
 
  
## 无序列表
  使用 -、+ 和 * 表示无序列表，前后留一行空白，可嵌套:
  
**
```
+ 第一层
    - 第二层
    - 有第三层
      * 第三次
  + 第一层
```
  + 第一层
    - 第二层
    - 有第三层
      * 第三次
  + 第一层

## 有序列表
 使用 数字　+　. （点号后面有个空格）表示有序列表，可嵌套。
 
**格式**
```
1. 第一层
   1. 二层
      1. 第三层
2. 第一层
3. 第一层
```
**显示效果：**
1. 第一层
   1. 二层
      1. 第三层
2. 第一层
3. 第一层

## 层级
使用 > 表示(不用空格)，可以有多个 >，>越多表示层级更深．

**格式:**
```
>第一层
>>第二层
>>>第三层

>>第二层(上一行是空行，跳出第三层)

>第一层(上一行是空行，跳出第二层)

```

**显示效果:**

>第一层
>>第二层
>>>第三层

>>第二层(上一行是空行，跳出第三层)

>第一层(上一行是空行，跳出第二层)

## 代码块
使用\｀即^~实现代码块

这是行内代码块:\`代码块\`
　`行内代码`

这是多行代码块

\`\`\`
   代码块
\`\`\`

```
  int main() {
    return 0;
  }
```
<a name="角标" id="锚点２"></a>
## 角标

格式
```
标注１．[^1]
[^1]: 标注１内容

标注２. [^2]
[^2]: 标注２内容
```

**显示效果**
标注１．[^1]
[^1]: 标注１内容

标注２. [^2]
[^2]: 标注２内容

## 链接

**格式***
```
<https://www.baidu.com>
```

**显示效果**
<https://www.baidu.com>

<a name="代码高亮" id="锚点１"></a>
## 代码高亮

标记代码的语种，实现代码的高亮

**ruby语言代码**
```
    ```ruby
    require 'redcarpet'
    markdown = Redcarpet.new("Hello World!")
    puts markdown.to_html
    ```
```

**显示效果**
```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```

**c语言代码**
```
    ```c
    int main() {
       printf("%s", "hello world.");
       return 0;
    }
    ```
```


**显示效果**
```c
    int main() {
       printf("%s", "hello world.");
       return 0;
    }
```
## 内部跳转

**格式**
```
  点此[代码高亮](#锚点１)跳转。
  点此[角标](#锚点２)跳转。
  
  ＃跳转处格式
  <a name="代码高亮" id="锚点１"></a>
  ## 代码高亮
```
点此[代码高亮](#锚点１)跳转。
点此[角标](#锚点２)跳转。

## html格式表格

**格式**
```
<table>
 <tr>
  <td><strong>Name</strong></td>
  <td><strong>Type</strong></td>
  <td><strong>Description</strong></td>
 </tr>
 <tr>
  <td><strong>md</strong></td>
  <td>string</td>
  <td>markdown table</td>
 </tr>
 <tr>
  <td><strong>kd</strong></td>
  <td>string</td>
  <td>kramdown</td>
 </tr>
</table>
```

**显示效果**
<table>
 <tr>
  <td><strong>Name</strong></td>
  <td><strong>Type</strong></td>
  <td><strong>Description</strong></td>
 </tr>
 <tr>
  <td><strong>md</strong></td>
  <td>string</td>
  <td>markdown table</td>
 </tr>
 <tr>
  <td><strong>kd</strong></td>
  <td>string</td>
  <td>kramdown</td>
 </tr>
</table>

### 表格中链接到本地

**格式**
```
<table>
 <tr>
  <td><strong>Name</strong></td>
  <td><strong>Type</strong></td>
  <td><strong>Description</strong></td>
 </tr>
 <tr>
  <td><strong><a href="#有序列表">有序列表</a></strong></td>
  <td>string</td>
  <td>查看有序列表</td>
 </tr>
</table>
```
**显示效果**
<table>
 <tr>
  <td><strong>Name</strong></td>
  <td><strong>Type</strong></td>
  <td><strong>Description</strong></td>
 </tr>
 <tr>
  <td><strong><a href="#有序列表">有序列表</a></strong></td>
  <td>string</td>
  <td>查看有序列表</td>
 </tr>
</table>
