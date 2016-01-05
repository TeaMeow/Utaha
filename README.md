<p align="center">
  <img src="http://imgur.com/WdzQQZE.png"/>
</p>
<p align="center">
  <i>Realize the things you haven't realized</i>
</p>

&nbsp;

# Utaha

詩羽是一個 JavaScript 小型套件，通常用在 CSS UI 說明文件上，可以將某個指定容器

轉換成 HTML 原始碼，並且標記其 CSS 樣式重點，輸出到另一個容器，類似「預覽」和「原始碼」的功能。

請注意的是：**詩羽目前僅支援標記 CSS 類別名稱。**

&nbsp;

# 索引

1. [範例](#範例)

2. [需求](#需求)

3. [架構](#架構)

4. [開始](#開始)

  * [設置功能](#設置功能)
 
5. [標記重點](#標記重點)

  * [自訂樣式](#自訂樣式)
  
  * [CSS 樣式重點](#css-樣式重點)

&nbsp;

# 範例

假設你今天可能正在製作一個 CSS 的教學網站，

下面就是採用詩羽的範例，會自動產生一個 HTML 原始碼，並自動畫上重點供大家檢閱。

![範例](http://imgur.com/gct2W0e.png)

&nbsp;

# 需求

1. jQuery 是**不必要**的

2. [Highlight.JS](https://highlightjs.org/) 是**必要的**

&nbsp;

# 架構

首先，一個「示範群組 `.example` 」是必要的，其中必須包含「預覽 `.preview` 」和一個「原始碼輸出區 `.code` 」

整體來說，像這樣：

```html
<!-- 示範群組 -->
<div class="example">

  <!-- 預覽 -->
  <div class="preview"></div>
  <!-- / 預覽 -->
    
  <!-- 原始碼輸出區 -->
  <pre class="code"></pre>
  <!--/  原始碼輸出區 -->

</div>
<!-- / 示範群組 -->
```

&nbsp;

# 開始

詩羽是一個函式，你需要透過 `utaha()` 來呼叫她，我們的建議是在網頁讀取完後才呼叫，

基本上是這樣子：

```javascript
document.addEventListener('DOMContentLoaded', function()
{ 
    utaha();
});
```

&nbsp;

## 設置功能

詩羽有幾個可自訂的功能。

```javascript
var options = 
{
    'exampleContainer' : '.example',  // 示範容器的類別名稱 
    'previewContainer' : '.preview',  // 預覽容器的類別名稱
    'codeConrainer'    : '.code',     // 原始碼容器的類別名稱
    'insertBeforeCode' : '',          // 欲在原始碼之前插入的文字
    'insertAfterCode'  : '',          // 欲在原始碼之後插入的文字
}
```

&nbsp;

接下來要套用的時候，在呼叫詩羽的時候傳入這個設置就可以了：

```javascript
utaha(options);

/** 或者 */
utaha({'insertAfterCode': '上述都是原始碼喔喔喔喔喔！'})
```

&nbsp;

# 標記重點

你可以透過我們提供的 `data-important-*` 功能，來特別標記輸出原始碼的某些片段。

&nbsp;

## 自訂樣式

被標記的 CSS 樣式重點會套用 `.hljs-important-class` 樣式，您可以透過自訂 CSS 處理重點外觀。

&nbsp;

## CSS 樣式重點

如果你有需要標記的 CSS 樣式，那就在原始碼輸出區新增一個 `data-important-class` 。

```html
<!-- 原始碼輸出區 -->
<pre class="code" data-important-class="button"></pre>
<!--/  原始碼輸出區 -->
```

&nbsp;

當然，你也可以透過 `, ` 來一次標記多個類別：

```html
<!-- 原始碼輸出區 -->
<pre class="code" data-important-class="button, ts, menu, btn"></pre>
<!--/  原始碼輸出區 -->
```
