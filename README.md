# \<head> 對照表

[![CC0](https://img.shields.io/badge/license-CC0-green.svg)](https://creativecommons.org/publicdomain/zero/1.0/)
[![Contributors](https://img.shields.io/github/contributors/joshbuchea/head.svg)](https://github.com/joshbuchea/HEAD/graphs/contributors)

一份關於任何你可以加入你網頁 `<head>` 部分的列表。 

## 目錄

- [基本推薦](#recommended-minimum)
- [網頁元件](#elements)
- [Meta 標籤](#meta)
- [鏈結](#link)
  - [網站圖示](#favicons)
- [社群網站](#social)
  - [Facebook Open Graph](#facebook-open-graph)
  - [Facebook Instant Articles](#facebook-instant-articles)
  - [Twitter Cards](#twitter-cards)
  - [Google+ / Schema.org](#google--schemaorg)
  - [OEmbed](#oembed)
- [瀏覽器 / 平台](#browsers--platforms)
  - [Apple iOS](#apple-ios)
  - [Apple Safari](#apple-safari)
  - [Google Android](#google-android)
  - [Google Chrome](#google-chrome)
  - [Microsoft Internet Explorer](#microsoft-internet-explorer)
- [中國瀏覽器](#browsers-chinese)
  - [360 瀏覽器](#360-browser)
  - [QQ 行動瀏覽器](#qq-mobile-browser)
  - [UC 行動瀏覽器](#uc-mobile-browser)
- [應用程式鏈結](#app-links)
- [注意](#notes)
  - [效能](#performance)
- [其他資源](#other-resources)
- [相關專案](#related-projects)
- [其他格式](#other-formats)
- [翻譯](#translations)
- [貢獻](#contributing)
- [貢獻者](#contributors)
- [作者](#author)
- [授權](#license)

## 基本推薦

以下是最小化、最低限度的網站基本標籤：

```html
<meta charset="utf-8">
<meta http-equiv="x-ua-compatible" content="ie=edge">
<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
<!-- 以上三個 meta 標籤 *必須* 放在 head 最前面；其他任何 head 內容必須放在這些標籤 *後面* -->
<title>頁面標題</title>
```

**[⬆ 返回頂端](#table-of-contents)**

## 網頁元件

``` html
<!-- 文件標題 -->
<title>頁面標題</title>

<!-- 基本 URL 用於文件中包含的所有相關 URLs -->
<base href="https://example.com/page.html">

<!-- 外部 CSS -->
<link rel="stylesheet" href="styles.css">

<!-- 文件內的 CSS -->
<style>
  /* ... */
</style>

<!-- JavaScript -->
<script src="script.js"></script>
<noscript><!--無 JS 時的替代方案--></noscript>
```

**[⬆ 返回頂端](#table-of-contents)**

## Meta 標籤

``` html
<meta charset="utf-8"> <!-- 設定文件的字元編碼 -->
<meta http-equiv="x-ua-compatible" content="ie=edge">
<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
<!-- 以上三個 meta 標籤 *必須* 放在 head 最前面；其他任何 head 內容必須放在這些標籤 *後面* -->

<!-- 設定允許從那裡載入資源 -->
<meta http-equiv="Content-Security-Policy" content="default-src 'self'">
<!-- 盡早放置於文件中 -->
<!-- 僅對於該標籤後的內容有效 -->

<!-- 網頁應用程式名稱（只在網站被做為一個應用程式時才會使用） -->
<meta name="application-name" content="應用程式名稱">

<!-- 此頁面的簡短描述（限制 150 個字元） -->
<!-- 在 *某些* 情況下，描述會成為搜尋結果片段的一部分。 -->
<meta name="description" content="一段頁面描述">

<!-- 控制搜尋引擎的抓取和索引行為 -->
<meta name="robots" content="index,follow"><!-- 所有搜尋引擎 -->
<meta name="googlebot" content="index,follow"><!-- 僅限 Google -->

<!-- 告訴 Google 不顯示網站鏈結的搜尋框 -->
<meta name="google" content="nositelinkssearchbox">

<!-- 告訴 Google 不提供此頁面翻譯 -->
<meta name="google" content="notranslate">

<!-- 驗證 Google 網站管理員工具所有權 -->
<meta name="google-site-verification" content="verification_token">

<!-- 驗證 Yandex 網站管理員所有權 -->
<meta name="yandex-verification" content="verification_token">

<!-- 驗證 Bing 網站管理員中心所有權 -->
<meta name="msvalidate.01" content="verification_token">

<!-- 驗證 Alexa 控制台所有權 -->
<meta name="alexaVerifyID" content="verification_token">

<!-- 驗證 Pinterest 控制台所有權-->
<meta name="p:domain_verify" content="code from pinterest">

<!-- 驗證 Norton 安全網頁所有權 -->
<meta name="norton-safeweb-site-verification" content="norton code">

<!-- 用來命名建立網站的軟體（例如：WordPress、Dreamweaver） -->
<meta name="generator" content="program">

<!-- 簡短描述你的網站主題 -->
<meta name="subject" content="你的網站主題">

<!-- 為你的網站內容加入年齡分級 -->
<meta name="rating" content="General">

<!-- 允許控制 referrer 資訊如何傳遞 -->
<meta name="referrer" content="no-referrer">

<!-- 停用對於電話號碼自動檢測和格式化 -->
<meta name="format-detection" content="telephone=no">

<!-- 設定為 'off' 完全退出 DNS 預先載入 -->
<meta http-equiv="x-dns-prefetch-control" content="off">

<!-- 為使用者識別在用戶網頁瀏覽器儲存 cookie -->
<meta http-equiv="set-cookie" content="name=value; expires=date; path=url">

<!-- 指定要顯示於一個特定框架中的頁面 -->
<meta http-equiv="Window-Target" content="_value">

<!-- 地理標籤 -->
<meta name="ICBM" content="latitude, longitude">
<meta name="geo.position" content="latitude;longitude">
<meta name="geo.region" content="country[-state]"><!-- 國家代碼 (ISO 3166-1): 強制性，州代碼 (ISO 3166-2): 選用; 例如 content="US" / content="US-NY" -->
<meta name="geo.placename" content="city/town"><!-- 例如 content="New York City" -->
```

- [Google 可以識別的 Meta 標籤](https://support.google.com/webmasters/answer/79812?hl=en)
- [WHATWG Wiki: Meta 拓展](https://wiki.whatwg.org/wiki/MetaExtensions)
- [ICBM - 維基百科](https://en.wikipedia.org/wiki/ICBM_address#Modern_use)
- [地理標記 - 維基百科](https://en.wikipedia.org/wiki/Geotagging#HTML_pages)

**[⬆ 返回頂端](#table-of-contents)**

## 鏈結

``` html
<!-- 指定一個 CSS 樣式表 -->
<link rel="stylesheet" href="https://example.com/styles.css">

<!-- 有助於避免多重內容問題 -->
<link rel="canonical" href="https://example.com/2010/06/9-things-to-do-before-entering-social-media.html">

<!-- 之前用於包含圖示鏈結，但現已被廢棄且不再使用 -->
<link rel="shortlink" href="https://example.com/?p=42">

<!-- 連結到當前文件的 AMP HTML 版本 -->
<link rel="amphtml" href="https://example.com/path/to/amp-version.html">

<!-- 連結到一個指定網頁應用程式「安裝」證書的 JSON 檔案 -->
<link rel="manifest" href="manifest.json">

<!-- 連結到文件的作者 -->
<link rel="author" href="humans.txt">

<!-- 指向一個適用於鏈結內容的版權申明 -->
<link rel="license" href="copyright.html">

<!-- 提供文件中可能使用的其他語言位置 -->
<link rel="alternate" href="https://es.example.com/" hreflang="es">

<!-- 提供有關作者和其他人的資訊 -->
<link rel="me" href="https://google.com/profiles/thenextweb" type="text/html">
<link rel="me" href="mailto:name@example.com">
<link rel="me" href="sms:+15035550125">

<!-- 連結到一個描述歷史紀錄、文件或其他具有歷史意義資料的彙整。 -->
<link rel="archives" href="https://example.com/archives/">

<!-- 連結到層次結構中的最頂層資源 -->
<link rel="index" href="https://example.com/">

<!-- Gives a self reference - useful when the document has multiple possible references -->
<link rel="self" type="application/atom+xml" href="https://example.com/atomFeed.php?page=3">

<!-- 分別是一系列文件中的第一個、下一個、前一個和最後一個 -->
<link rel="first" href="https://example.com/atomFeed.php">
<link rel="next" href="https://example.com/atomFeed.php?page=4">
<link rel="prev" href="https://example.com/atomFeed.php?page=2">
<link rel="last" href="https://example.com/atomFeed.php?page=147">

<!-- 當使用第三方服務來維護網誌時會用到 -->
<link rel="EditURI" href="https://example.com/xmlrpc.php?rsd" type="application/rsd+xml" title="RSD">

<!-- 當其他 WordPress 網誌連結到你的 WordPress 網誌或文章時建立一個自動化的留言 -->
<link rel="pingback" href="https://example.com/xmlrpc.php">

<!-- 當你在自己的頁面上連結到一個 URL 時通知它 -->
<link rel="webmention" href="https://example.com/webmention">

<!-- 載入一個外部 HTML 檔案至當前 HTML 檔案中 -->
<link rel="import" href="/path/to/component.html">

<!-- 開放搜尋 -->
<link rel="search" href="/open-search.xml" type="application/opensearchdescription+xml" title="搜尋標題">

<!-- Feeds -->
<link rel="alternate" href="https://feeds.feedburner.com/example" type="application/rss+xml" title="RSS">
<link rel="alternate" href="https://example.com/feed.atom" type="application/atom+xml" title="Atom 0.3">

<!-- 預先載入、讀取、瀏覽 -->
<link rel="dns-prefetch" href="//example.com/">
<link rel="preconnect" href="https://www.example.com/">
<link rel="prefetch" href="https://www.example.com/">
<link rel="prerender" href="https://example.com/">
<link rel="preload" href="image.png" as="image">
<!-- 更多資訊：https://css-tricks.com/prefetching-preloading-prebrowsing/ -->
```

**[⬆ 返回頂端](#table-of-contents)**

### 網站圖示

``` html
<!-- 針對 IE 10 及以下版本 -->
<!-- 將 favicon.ico 放在你的根目錄下，無須標籤 -->

<!-- 對於 IE 11、Chrome、Firefox、Safari、Opera -->
<link rel="icon" type="image/png" sizes="16x16" href="/path/to/favicon-16x16.png">
<link rel="icon" type="image/png" sizes="32x32" href="/path/to/favicon-32x32.png">
<link rel="icon" type="image/png" sizes="96x96" href="/path/to/favicon-96x96.png">
```

- [所有關於網站圖示（及觸控圖示）資訊](https://bitsofco.de/all-about-favicons-and-touch-icons/)
- [Favicon 對照表](https://github.com/audreyr/favicon-cheat-sheet)

**[⬆ 返回頂端](#table-of-contents)**

## 社群網站

### Facebook Open Graph

``` html
<meta property="fb:app_id" content="123456789">
<meta property="og:url" content="https://example.com/page.html">
<meta property="og:type" content="website">
<meta property="og:title" content="內容標題">
<meta property="og:image" content="https://example.com/image.jpg">
<meta property="og:description" content="在這裡寫上描述">
<meta property="og:site_name" content="網站名稱">
<meta property="og:locale" content="en_US">
<meta property="article:author" content="">
```

- [Facebook 的 Open Graph 標記](https://developers.facebook.com/docs/sharing/webmasters#markup)
- [Open Graph 協定](http://ogp.me/)

**[⬆ 返回頂端](#table-of-contents)**

### Facebook Instant Articles

``` html
<meta charset="utf-8">
<meta property="op:markup_version" content="v1.0">

<!-- 你的文章 Web 版網址 -->
<link rel="canonical" href="http://example.com/article.html">

<!-- 用於文章的樣式 -->
<meta property="fb:article_style" content="myarticlestyle">
```

- [Facebook Instant Articles：建立文章](https://developers.facebook.com/docs/instant-articles/guides/articlecreate)
- [Instant Articles：格式參考](https://developers.facebook.com/docs/instant-articles/reference)

**[⬆ 返回頂端](#table-of-contents)**

### Twitter Cards

``` html
<meta name="twitter:card" content="summary">
<meta name="twitter:site" content="@site_account">
<meta name="twitter:creator" content="@individual_account">
<meta name="twitter:url" content="https://example.com/page.html">
<meta name="twitter:title" content="內容標題">
<meta name="twitter:description" content="內容描述少於 200 個字元">
<meta name="twitter:image" content="https://example.com/image.jpg">
```

- [Twitter Cards：入門指南](https://dev.twitter.com/cards/getting-started)
- [Twitter Card 驗證工具](https://cards-dev.twitter.com/validator)

**[⬆ 返回頂端](#table-of-contents)**

### Google+ / Schema.org

``` html
<link href="https://plus.google.com/+YourPage" rel="publisher">
<meta itemprop="name" content="內容標題">
<meta itemprop="description" content="內容描述少於 200 個字元">
<meta itemprop="image" content="https://example.com/image.jpg">
```

**[⬆ 返回頂端](#table-of-contents)**

### Pinterest

根據[他們的幫助中心](https://help.pinterest.com/en/articles/prevent-people-saving-things-pinterest-your-site)說明，Pinterest 允許你禁止其他人儲存你網站裡的內容。`description` 為選填。

``` html
<meta name="pinterest" content="nopin" description="抱歉，你不能從我的網站儲存內容！">
```

**[⬆ 返回頂端](#table-of-contents)**

### OEmbed

``` html
<link rel="alternate" type="application/json+oembed"
  href="http://example.com/services/oembed?url=http%3A%2F%2Fexample.com%2Ffoo%2F&amp;format=json"
  title="oEmbed Profile: JSON">
<link rel="alternate" type="text/xml+oembed"
  href="http://example.com/services/oembed?url=http%3A%2F%2Fexample.com%2Ffoo%2F&amp;format=xml"
  title="oEmbed Profile: XML">
```

- [oEmbed 格式](http://oembed.com/)

**[⬆ 返回頂端](#table-of-contents)**

## 瀏覽器 / 平台

### Apple iOS

``` html
<!-- 智慧型應用程式橫幅 -->
<meta name="apple-itunes-app" content="app-id=APP_ID,affiliate-data=AFFILIATE_ID,app-argument=SOME_TEXT">

<!-- 停用對於電話號碼自動檢測和格式化 -->
<meta name="format-detection" content="telephone=no">

<!-- 新增至主畫面 -->
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black">
<meta name="apple-mobile-web-app-title" content="應用程式標題">

<!-- 觸控圖示 -->
<!-- 大多數情況下，在 `<head>` 中一個 180×180px 觸控圖示就已經足夠 -->
<link rel="apple-touch-icon" href="/path/to/apple-touch-icon.png">
<!-- 注意：iOS 7 的 Safari 不會對圖示產生效果。 -->
<!-- 更早版本的 Safari 不會對以 -precomposed.png 後綴命名的圖示檔案產生效果。 -->

<!-- 啟動畫面（已失效） -->
<link rel="apple-touch-startup-image" href="/path/to/startup.png">

<!-- iOS 應用程式深度鏈結 -->
<meta name="apple-itunes-app" content="app-id=APP-ID, app-argument=http/url-sample.com">
<link rel="alternate" href="ios-app://APP-ID/http/url-sample.com">
```

- [Apple Meta 標籤](https://developer.apple.com/library/safari/documentation/AppleApplications/Reference/SafariHTMLRef/Articles/MetaTags.html)

**[⬆ 返回頂端](#table-of-contents)**

### Apple Safari

```html
<!-- 固定網站 -->
<link rel="mask-icon" href="/path/to/icon.svg" color="red">
```

**[⬆ 返回頂端](#table-of-contents)**

### Google Android

``` html
<meta name="theme-color" content="#E64545">

<!-- 新增至主畫面 -->
<meta name="mobile-web-app-capable" content="yes">
<!-- 更多資訊：https://developer.chrome.com/multidevice/android/installtohomescreen -->

<!-- Android 應用程式深度鏈結 -->
<meta name="google-play-app" content="app-id=package-name">
<link rel="alternate" href="android-app://package-name/http/url-sample.com">
```

**[⬆ 返回頂端](#table-of-contents)**

### Google Chrome

``` html
<link rel="chrome-webstore-item" href="https://chrome.google.com/webstore/detail/APP_ID">

<!-- 停用翻譯提示 -->
<meta name="google" content="notranslate">
```

**[⬆ 返回頂端](#table-of-contents)**

### Google Chrome 行動版（只針對 Android）

從 Chrome 31 開始，你可以設定你的網頁應用程式為「app mode」，例如 Safari。

``` html
<!-- 連結到一個 manifest 並定義 manifest 的 Metadata。 -->
<!-- 範例中的 manifest.json 也可以透過以下鏈結找到。 -->
<link rel="manifest" href="manifest.json">

<!-- 定義你的網頁為網頁應用程式 -->
<meta name="mobile-web-app-capable" content="yes">

<!-- 主畫面圖示 -->
<link rel="icon" sizes="192x192" href="highres-icon.png">
```

- [Google 開發者](https://developer.chrome.com/multidevice/android/installtohomescreen)

**[⬆ 返回頂端](#table-of-contents)**

### Microsoft Internet Explorer

``` html
<meta http-equiv="x-ua-compatible" content="ie=edge">
<meta name="skype_toolbar" content="skype_toolbar_parser_compatible">

<!-- IE10：停用鏈結點擊後高亮效果 (https://blogs.windows.com/buildingapps/2012/11/15/adapting-your-webkit-optimized-site-for-internet-explorer-10/) -->
<meta name="msapplication-tap-highlight" content="no">

<!-- 固定網站 (https://msdn.microsoft.com/en-us/library/dn255024(v=vs.85).aspx) -->
<meta name="application-name" content="Sample Title">
<meta name="msapplication-tooltip" content="A description of what this site does.">
<meta name="msapplication-starturl" content="http://example.com/index.html?pinned=true">
<meta name="msapplication-navbutton-color" content="#FF3300">
<meta name="msapplication-window" content="width=800;height=600">
<meta name="msapplication-task" content="name=Task 1;action-uri=http://host/Page1.html;icon-uri=http://host/icon1.ico">
<meta name="msapplication-task" content="name=Task 2;action-uri=http://microsoft.com/Page2.html;icon-uri=http://host/icon2.ico">
<meta name="msapplication-badge" value="frequency=NUMBER_IN_MINUTES;polling-uri=http://example.com/path/to/file.xml">
<meta name="msapplication-TileColor" content="#FF3300">
<meta name="msapplication-TileImage" content="/path/to/tileimage.jpg">

<meta name="msapplication-config" content="http://example.com/browserconfig.xml">
<meta name="msapplication-notification" content="frequency=60;polling-uri=http://example.com/livetile;polling-uri2=http://example.com/livetile2">
<meta name="msapplication-task-separator" content="1">
```

**[⬆ 返回頂端](#table-of-contents)**

## 應用程式鏈結

``` html
<!-- iOS -->
<meta property="al:ios:url" content="applinks://docs">
<meta property="al:ios:app_store_id" content="12345">
<meta property="al:ios:app_name" content="App Links">
<!-- Android -->
<meta property="al:android:url" content="applinks://docs">
<meta property="al:android:app_name" content="App Links">
<meta property="al:android:package" content="org.applinks">
<!-- Web Fallback -->
<meta property="al:web:url" content="http://applinks.org/documentation">
<!-- 更多資訊：http://applinks.org/documentation/ -->
```

- [應用程式鏈結說明文件](http://applinks.org/documentation/)

**[⬆ 返回頂端](#table-of-contents)**

## 中國瀏覽器

### 360 瀏覽器

``` html
<!-- 選擇渲染引擎 -->
<meta name="renderer" content="webkit|ie-comp|ie-stand">
```

**[⬆ 返回頂端](#table-of-contents)**

### QQ 行動瀏覽器

``` html
<!-- 在指定方向上鎖定螢幕（鎖定橫向或直向螢幕） -->
<meta name="x5-orientation" content="landscape/portrait">
<!-- 在全螢幕狀態下顯示此頁面 -->
<meta name="x5-fullscreen" content="true">
<!-- 頁面將以「應用程式模式」顯示（全螢幕等等） -->
<meta name="x5-page-mode" content="app">
```

**[⬆ 返回頂端](#table-of-contents)**

### UC 行動瀏覽器

``` html
<!-- 在指定方向上鎖定螢幕（鎖定橫向或直向螢幕） -->
<meta name="screen-orientation" content="landscape/portrait">
<!-- 在全螢幕狀態下顯示此頁面 -->
<meta name="full-screen" content="yes">
<!-- 即使在「文字模式」下，UC 瀏覽器也會顯示圖片 -->
<meta name="imagemode" content="force">
<!-- 頁面將以「應用程式模式」顯示（全螢幕、禁止手勢等等） -->
<meta name="browsermode" content="application">
<!-- 在此頁面停用 UC 瀏覽器的「夜間模式」 -->
<meta name="nightmode" content="disable">
<!-- 簡化頁面，減少資料傳輸量 -->
<meta name="layoutmode" content="fitscreen">
<!-- 在此頁面停用 UC 瀏覽器的「當此頁面中有較多文字時縮放字體」功能 -->
<meta name="wap-font-scale" content="no">
```

- [UC 瀏覽器說明文件](http://www.uc.cn/download/UCBrowser_U3_API.doc)

**[⬆ 返回頂端](#table-of-contents)**

## 注意

### 效能
當 GZIP 啟用時，將 `href` 屬性移到該元件的開頭以提高壓縮，因為 `href` 屬性也被用於 `a`、 `base` 和 `link` 標籤。

範例：

``` html
<link href="https://fonts.googleapis.com/css?family=Open+Sans:400,700" rel="stylesheet">
```

**[⬆ 返回頂端](#table-of-contents)**

## 其他資源

- [HTML5 模版文件：HTML 標籤](https://github.com/h5bp/html5-boilerplate/blob/master/dist/doc/html.md)
- [HTML5 模版文件：擴展和自定](https://github.com/h5bp/html5-boilerplate/blob/master/dist/doc/extend.md)

**[⬆ 返回頂端](#table-of-contents)**

## 相關專案

- [Atom HTML Head 程式碼](https://github.com/joshbuchea/atom-html-head-snippets) - Atom `HEAD` 程式碼
- [Sublime Text HTML Head 程式碼](https://github.com/marcobiedermann/sublime-head-snippets) - Sublime Text `HEAD` 程式碼
- [head-it](https://github.com/hemanth/head-it) - CLI 介面的 `HEAD` 程式碼
- [vue-head](https://github.com/ktquez/vue-head) - 在 Vue.js 中操作 `HEAD` 標籤的 Meta 資訊

**[⬆ 返回頂端](#table-of-contents)**

## 其他格式

- [PDF](https://gitprint.com/joshbuchea/HEAD/blob/master/README.md)

**[⬆ 返回頂端](#table-of-contents)**

## 翻譯

- [巴西葡萄牙語](https://github.com/Webschool-io/HEAD)
- [中文（簡體）](https://github.com/Amery2010/HEAD)
- [義大利語](https://github.com/Fakkio/HEAD)
- [日語](http://coliss.com/articles/build-websites/operation/work/collection-of-html-head-elements.html)
- [俄羅斯語](https://github.com/Konfuze/HEAD)
- [土耳其語](https://github.com/mkg0/HEAD)
- [韓語](https://github.com/Lutece/HEAD)

**[⬆ 返回頂端](#table-of-contents)**

## 貢獻

**開啟一個 issue 或一個 pull 請求來提出修改或補充。**

### 指南

**HEAD** repository 由兩個分支組成：

#### 1. `master`

對於此分支內包含的 `README.md` 檔案修改會自動反映在 [\<head> Cheat Sheet](http://gethead.info/) 網站上。所有對照表內容變更都應該針對此檔案。

請依照下列步驟提交 pull 請求：

- 只修改一個標籤，或一次一組相關的標籤
- 對屬性使用雙引號
- 請不要在自我關閉元件中使用斜線 — 即使 HTML5 規範裡說它們是選用的
- 考慮在文件中加入鏈結以支持你的變更

#### 2. `gh-pages`

該分支負責 [\<head> Cheat Sheet](http://gethead.info/) 網站。我們使用 [Jekyll](https://jekyllrb.com/) 透過 [GitHub Pages](https://pages.github.com/) 服務來部屬 `README.md` 文件。所有網站相關的修改必須集中在這裡。

你可以透過 [Jekyll 說明文件](https://jekyllrb.com/docs/home/) 來了解 Jekyll 如何在該分支上運作。

**[⬆ 返回頂端](#table-of-contents)**

### 貢獻者

看看這些超級棒的[貢獻者們](https://github.com/joshbuchea/HEAD/graphs/contributors)。

**[⬆ 返回頂端](#table-of-contents)**

## 作者

**[Josh Buchea](http://joshbuchea.com/)**

**[⬆ 返回頂端](#table-of-contents)**

## 授權

[![CC0](http://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

在法律範圍內，[Josh Buchea](http://joshbuchea.com) 已經放棄這項工作的所有版權以及相關或鄰近的權利。

**[⬆ 返回頂端](#table-of-contents)**
