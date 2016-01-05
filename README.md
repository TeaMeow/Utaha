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

1. 範例

2. 架構

&nbsp;

# 範例

![範例](http://imgur.com/x2KuEyg.png)

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

# 標記 CSS 樣式重點

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
