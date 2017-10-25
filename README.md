# Front-End Checklist

[![Join the chat at https://gitter.im/Front-End-Checklist/Lobby](https://badges.gitter.im/Front-End-Checklist/Lobby.svg)](https://gitter.im/Front-End-Checklist/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)
[![Contributors](https://img.shields.io/github/contributors/thedaviddias/Front-End-Checklist.svg)](https://github.com/thedaviddias/Front-End-Checklist/graphs/contributors)
[![StackShare](https://img.shields.io/badge/tech-stack-0690fa.svg?style=flat)](https://stackshare.io/thedaviddias/front-end-checklist)
[![CC0](https://img.shields.io/badge/license-CC0-green.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

**Front-End Checklist** là một danh sách tương đối đầy đủ về tất cả các yếu tố bạn cần kiểm tra trang web/HTML của mình trước khi đưa chúng tới tay người dùng trên production.

Checklist này được xây dựng bởi các Front-End developer nhiều năm kinh nghiệm, cùng với sự bổ sung và tham khảo từ nhiều open-source checklists khác.

## Mục lục

1. **[Head](#head)**
2. **[HTML](#html)**
3. **[Webfonts](#webfonts)**
4. **[CSS](#css)**
5. **[Images](#images)**
6. **[JavaScript](#javascript)**
7. **[Security](#security)**
8. **[Performance](#performance-1)**
9. **[Accessibility](#accessibility)**
10. **[SEO](#seo)**

## Cách sử dụng?

Tất cả các mục trong **Front-End Checklist** đều được yêu cầu thực hiện cho phần lớn các dự án, nhưng một số phần có thể được bỏ qua hoặc không cần thiết (Ví dụ trong trường hợp của một ứng dụng web liên quan tới quản trị, bạn có thể không cần phải có RSS feed chẳng hạn). Chúng tôi lựa chọn sử dụng 3 cấp độ linh hoạt :

* ![Low][low_img] có nghĩa là mục này được **recommended** sử dụng nhưng có thể được bỏ qua trong một số tình huống cụ thể.
* ![Medium][medium_img] có nghĩa là mục này được **highly recommended** và có thể được bỏ qua trong một số trường hợp thực sự đặc biệt. Một số yếu tố, nếu như bỏ qua có thể có ảnh hưởng xấu về hiệu suất hoặc SEO của trang web.
* ![High][high_img] có nghĩa là mục này **không thể bỏ qua** vì bất kỳ lý do nào. Bạn có thể gây ra sự rối loạn trong trang web của bạn hoặc các vấn đề truy cập hoặc SEO. Các yếu tố/mục trong phần này cần được ưu tiên kiểm tra trước tiên.

Một số tài nguyên có biểu tượng cảm xúc để giúp bạn hiểu loại nội dung/trợ giúp bạn có thể tìm thấy trong checklist:

* 📖: Tài liệu hoặc các bài viết
* 🛠: Online tool / testing tool
* 📹: Nội dung media hoặc video

---

## Head

> **Notes:** Bạn có thể tìm thấy [một danh sách tất cả mọi thứ](https://github.com/joshbuchea/HEAD) liên quan tới thẻ `<head>` của tài liệu HTML.

### Meta tag

* [ ] **Doctype:** ![High][high_img] Doctype phải là HTML5 và nằm ở đầu tất cả các trang HTML của bạn.

```html
<!-- Doctype HTML5 -->
<!doctype html>
```

> * 📖 [Determining the character encoding - HTML5 W3C](https://www.w3.org/TR/html5/syntax.html#determining-the-character-encoding)

*3 thẻ meta (Charset, X-UA Compatible and Viewport) cần được khai báo đầu tiên ở head.*

* [ ] **Charset:** ![High][high_img] Charset (UTF-8) phải được khai báo một cách chính xác.

```html
<!-- Set character encoding for the document -->
<meta charset="utf-8">
```

* [ ] **X-UA-Compatible:** ![Medium][medium_img] Thẻ X-UA-Compatible meta được khai .

```html
<!-- Instruct Internet Explorer to use its latest rendering engine -->
<meta http-equiv="x-ua-compatible" content="ie=edge">
```

> * 📖 [Specifying legacy document modes (Internet Explorer)](https://msdn.microsoft.com/en-us/library/jj676915(v=vs.85).aspx)

* [ ] **Viewport:** ![High][high_img] Viewport phải được khai báo chính xác.

```html
<!-- Viewport for responsive web design -->
<meta name="viewport" content="width=device-width, initial-scale=1">
```

* [ ] **Title:** ![High][high_img] Tiêu đề phải được sử dụng trên tất cả các trang (SEO: Google tính toán chiều rộng pixel của các ký tự được sử dụng trong tiêu đề, cắt bỏ giữa 472 và 482 pixel. Số lượng ký tự trung bình giới hạn khoảng 55 ký tự).


```html
<!-- Document Title -->
<title>Page Title less than 65 characters</title>
```

> * 📖 [Title - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title)

* [ ] **Description:** ![High][high_img] Thẻ meta mô tả (description) được khai báo, hãy đảm bảo nó là duy nhất và không hơn 150 ký tự.

```html
<!-- Meta Description -->
<meta name="description" content="Description of the page less than 150 characters">
```

* [ ] **Favicons:** ![Medium][medium_img] Hãy đảm bảo mỗi favicon đã được tạo ra và hiển thị chính xác. Nếu bạn chỉ có một tệp tin `favicon.ico`, hãy đặt nó vào thư mục gốc của trang web. Thông thường, bạn sẽ không cần phải sử dụng bất kỳ đánh dấu nào. Tuy nhiên, sẽ là tốt hơn nếu liên kết với nó như ví dụ dưới đây. Ngày nay, **định dạng PNG** được khuyến khích sử dụng thay cho `.ico` (kích thước: 32x32px).


```html
<!-- Standard favicon -->
<link rel="icon" type="image/x-icon" href="https://example.com/favicon.ico">
<!-- Recommended favicon format -->
<link rel="icon" type="image/png" href="https://example.com/favicon.png">
```

> * 🛠 [Favicon Generator](https://www.favicon-generator.org/)
> * 🛠 [RealFaviconGenerator](https://realfavicongenerator.net/)
> * 📖 [Favicon Cheat Sheet](https://github.com/audreyr/favicon-cheat-sheet)
> * 📖 [Favicons, Touch Icons, Tile Icons, etc. Which Do You Need? - CSS Tricks](https://css-tricks.com/favicon-quiz/)
> * 📖 [PNG favicons - caniuse](https://caniuse.com/#feat=link-icon-png)

* [ ] **Apple Touch Icon:** ![Low][low_img] Tồn tại Apple touch favicon apple-mobile-web-app-capable. *(Hãy tạo ra các tệp tin Apple Icon với kích thước tối thiểu 200x200px để hỗ trợ tất cả các kích thước mà bạn cần)*

```html
<!-- Apple Touch Icon -->
<link rel="apple-touch-icon" href="/custom-icon.png">
```

> * 📖 [Configuring Web Applications](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html)

- [ ] **Windows Tiles:**![Low][low_img] Tồn tại Windows tiles và được liên kết.

```html
<!-- Microsoft Tiles -->
<meta name="msapplication-config" content="browserconfig.xml" />
```

Cấu hình xml tối thiểu cho tệp tin browserconfig.xml như sau:

```xml
<?xml version="1.0" encoding="utf-8"?>
<browserconfig>
   <msapplication>
     <tile>
        <square70x70logo src="small.png"/>
        <square150x150logo src="medium.png"/>
        <wide310x150logo src="wide.png"/>
        <square310x310logo src="large.png"/>
     </tile>
   </msapplication>
</browserconfig>
```

> * 📖 [Browser configuration schema reference](https://msdn.microsoft.com/en-us/library/dn320426(v=vs.85).aspx)

* [ ] **Canonical:** ![Medium][medium_img] Sử dụng `rel="canonical"` để tránh nội dung trùng lặp.

```html
<!-- Helps prevent duplicate content issues -->
<link rel="canonical" href="http://example.com/2017/09/a-new-article-to-red.html">
```

> * 📖 [Use canonical URLs - Search Console Help - Google Support](https://support.google.com/webmasters/answer/139066?hl=en)
> * 📖 [5 common mistakes with rel=canonical - Google Webmaster Blog](https://webmasters.googleblog.com/2013/04/5-common-mistakes-with-relcanonical.html)

### HTML tags

* [ ] **Language tag:** ![High][high_img] Thẻ ngôn ngữ trên trang web của bạn được chỉ định và liên quan đến ngôn ngữ của trang hiện tại.

```html
<html lang="en">
```

* [ ] **Direction attribute:** ![Medium][medium_img] Hướng văn bản được chỉ định trên thẻ body (Nó có thể được sử dụng trên thẻ HTML khác).

```html
<html dir="rtl">
```

> * 📖 [dir - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir)

* [ ] **Alternate language:** ![Low][low_img] Thẻ ngôn ngữ thay thế của trang web của bạn được chỉ định và liên quan đến ngôn ngữ của trang hiện tại.

```html
<link rel="alternate" href="https://es.example.com/" hreflang="es">
```

* [ ] **Conditional comments:** ![Low][low_img] Conditional comments are present for IE if needed.

> * 📖 [About conditional comments (Internet Explorer) - MSDN - Microsoft](https://msdn.microsoft.com/en-us/library/ms537512(v=vs.85).aspx)

* [ ] **RSS feed:** ![Low][low_img] Nếu dự án của bạn là một blog hoặc có các bài viết, cần cung cấp một liên kết RSS tới chúng.

* [ ] **CSS Critical:** ![Medium][medium_img] The CSS critical (hoặc "above the fold") tập hợp tất cả các thành phần CSS được sử dụng để hiển thị một phần trên trang web. Nó được nhúng trước khi CSS chính của bạn được gọi ra và giữa thẻ `<style></style>` trong một dòng (minified).

> * 🛠 [Critical by Addy Osmani on Github](https://github.com/addyosmani/critical)

* [ ] **CSS order:** ![High][high_img] Tất cả các tệp tin CSS đểu phải được tải trước bất kỳ tệp tin JavaScript nào trong thẻ `<head>`. (Trừ trường hợp đôi khi tệp JS được tải bất đồng bộ trên đầu trang của bạn).

### Social meta

***Facebook OG*** và ***Twitter Cards*** thì được khuyến khích sử dụng cho bất kỳ website nào. Các thẻ social media khác có thể được xem xét nếu bạn nhắm mục tiêu một hiện diện cụ thể những trang web đó và muốn đảm bảo hiển thị.


* [ ] **Facebook Open Graph:** ![Low][low_img] Đảm bảo tất cả các Facebook Open Graph (OG) được kiểm thử (tested) và không một thẻ nào bị sai thông tin. Các tệp tin ảnh cần có kích thước tối thiểu là 600 x 315 pixels, khuyến khích sử dụng kích thước sau: 1200 x 630 pixels.

```html
<meta property="og:type" content="website">
<meta property="og:url" content="https://example.com/page.html">
<meta property="og:title" content="Content Title">
<meta property="og:image" content="https://example.com/image.jpg">
<meta property="og:description" content="Description Here">
<meta property="og:site_name" content="Site Name">
<meta property="og:locale" content="en_US">
```

> * 📖 [A Guide to Sharing for Webmasters](https://developers.facebook.com/docs/sharing/webmasters/)
> * 🛠 Test your page with the [Facebook OG testing](https://developers.facebook.com/tools/debug/)

* [ ] **Twitter Card:** ![Low][low_img]

```html
<meta name="twitter:card" content="summary">
<meta name="twitter:site" content="@site_account">
<meta name="twitter:creator" content="@individual_account">
<meta name="twitter:url" content="https://example.com/page.html">
<meta name="twitter:title" content="Content Title">
<meta name="twitter:description" content="Content description less than 200 characters">
<meta name="twitter:image" content="https://example.com/image.jpg">
```

> * 📖 [Getting started with cards — Twitter Developers](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/guides/getting-started)
> * 🛠 Test your page with the [Twitter card validator](https://cards-dev.twitter.com/validator)

**[⬆ Về đầu trang](#mục-lục)**

---

## HTML

### Best practices

* [ ] **HTML5 Semantic Elements:** ![High][high_img] Thành phần ngữ nghĩa HTML5 được sử dụng hợp lý (header, section, footer, main...).

> * 📖 [HTML Reference](http://htmlreference.io/)

* [ ] **Error pages:** ![High][high_img] Tồn tại các trang lỗi 404 và 5xx. Hãy nhớ rằng các trang lỗi 5xx cần phải có tích hợp CSS (không gọi tới css bên ngoài máy chủ hiện tại).


* [ ] **Noopener:** ![Medium][medium_img] Trong trường hợp bạn đang sử dụng external links với `target = '_ blank'`, liên kết của bạn phải có thuộc tính `rel ="noopener"` để ngăn chặn tab nabbing. Nếu bạn cần hỗ trợ các phiên bản cũ của Firefox, hãy sử dụng `rel ="noopener noreferrer"`.

> * 📖 [About rel=noopener](https://mathiasbynens.github.io/rel-noopener/)

* [ ] **Clean up comments:** ![Low][low_img] Các đoạn mã không cần thiết mã cần phải được gỡ bỏ trước khi đưa ra production.

### HTML testing

* [ ] **W3C compliant:** ![High][high_img] Toàn bộ các page cần phải được kiểm thử với W3C validator để xác định các vấn đề có thể xảy ra trong HTML code.

> * 🛠 [W3C validator](https://validator.w3.org/)

* [ ] **HTML Lint:** ![High][high_img] Tôi sử dụng các công cụ để giúp phân tích bất kỳ vấn đề nào có thể có trong mã HTML.

> * 🛠 [Dirty markup](https://dirtymarkup.com/)

* [ ] **Desktop Browsers:** ![High][high_img] Tất cả các page đều được kiểm thử trên toàn bộ trình duyệt web của desktop (Safari, Firefox, Chrome, Internet Explorer, EDGE...).
* [ ] **Mobile Browsers:**  ![High][high_img] Tất cả các page đều được kiểm thử trên toàn bộ trình duyệt web của mobile (Native browser, Chrome, Safari...).

* [ ] **Link checker:** ![High][high_img] Hãy đảm bảo không có liên kết bị hỏng trong trang web của bạn, hãy xác minh rằng bạn không có bất kỳ lỗi 404 nào.

> * 🛠 [W3C Link Checker](https://validator.w3.org/checklink)

* [ ] **Adblockers test:** ![Medium][medium_img] Trang web của bạn hiển thị chính xác nội dung ngay cả khi tính năng chặn quảng cáo trên trình duyệt được kích hoạt (Bạn có thể đưa ra một thông báo khuyến khích mọi người vô hiệu hóa adblocker của họ).

- [ ] **Pixel perfect:** ![High][high_img] Các page cần đạt tới trạng thái hoàn hảo đến từng pixel. Tùy thuộc vào chất lượng của quảng cáo, có thể không chính xác 100%, nhưng các web page cần phải gần với template của bạn.


> [Pixel Perfect - Chrome Extension](https://chrome.google.com/webstore/detail/perfectpixel-by-welldonec/dkaagdgjmgdmbnecmcefdhjekcoceebi?hl=en)

**[⬆ Về đầu trang](#mục-lục)**

---

## Webfonts

* [ ] **Webfont format:** ![High][high_img] WOFF, WOFF2 và TTF được hỗ trợ trên tất cả các trình duyệt hiện đại.

> * 📖 [WOFF - Web Open Font Format - Caniuse](https://caniuse.com/#feat=woff).
> * 📖 [WOFF 2.0 - Web Open Font Format - Caniuse](https://caniuse.com/#feat=woff2).
> * 📖 [TTF/OTF - TrueType and OpenType font support](https://caniuse.com/#feat=ttf)
> * 📖 [Using @font-face - CSS-Tricks](https://css-tricks.com/snippets/css/using-font-face/)

* [ ] **Webfont size:** ![High][high_img] Dung lượng (size) của Webfont không vượt quá 2 MB (Bao gồm tất cả các thứ liên quan).

**[⬆ Về đầu trang](#mục-lục)**

---

## CSS

> **Notes:** [CSS guidelines](https://cssguidelin.es/) và [Sass Guidelines](https://sass-guidelin.es/) được follow bởi hầu hết Front-End developers. Nếu bạn gặp vấn đề hay có bất kỳ thắc mắc nào về CSS properties, bạn có thể truy cập [CSS Reference](http://cssreference.io/).

* [ ] **Responsive Web Design:** ![High][high_img] Trang web sử dụng thiết kế phản hồi (responsive).
* [ ] **CSS Print:** ![Medium][medium_img] Một bản in stylesheet đươc cung cấp và chính xác trên mỗi each page.
* [ ] **Preprocessors:** ![Medium][medium_img] Page của bạn đang sử dụng CSS preprocessor (Ưu tiên [Sass](http://sass-lang.com/)).
* [ ] **Unique ID:** ![High][high_img] Nếu IDs được sử dụng, chúng phải là duy nhất trên một page.
* [ ] **Reset CSS:** ![High][high_img] CSS reset (reset, normalize hoặc reboot) được sử dụng và luôn được cập nhật. *(Nếu bạn đang sử dụng CSS Framework như Bootstrap hoặc Foundation, Normalize đã được bao gồm trong đó.)*

> * 📖 [Reset.css](https://meyerweb.com/eric/tools/css/reset/)
> * 📖 [Normalize.css](https://necolas.github.io/normalize.css/)
> * 📖 [Reboot](https://getbootstrap.com/docs/4.0/content/reboot/)

* [ ] **JS prefix:** ![Low][low_img] Tất cả các class (hoặc id- được sử dụng trong tệp tin JavaScript) bắt đầu với **js-** và không được sử dụng làm định dạng trong các tệp tin CSS.

```html
<div id="js-slider" class="my-slider">
<!-- Or -->
<div id="id-used-by-cms" class="js-slider my-slider">
```

* [ ] **CSS embed hoặc line:** ![High][high_img] Tránh sử dụng CSS embed hoặc inline: Chỉ sử dụng nếu có lý do chính đáng (Ví dụ: background-image cho slider, CSS quan trọng, ...).
* [ ] **Vendor prefixes:** ![High][high_img] CSS vendor prefixes được sử dụng và để phù hợp với tính tương thích của trình duyệt.

> * 🛠 [Autoprefixer CSS online](https://autoprefixer.github.io/)

### Performance

- [ ] **Concatenation:** ![High][high_img] Toàn bộ các CSS files cần được concat thành một file duy nhất. *(Not for HTTP/2)*
- [ ] **Minification:** ![High][high_img] Toàn bộ các CSS files cần được minify.
- [ ] **Non-blocking:** ![Medium][medium_img] Toàn bộ các CSS files cần được non-blocking việc ngăn chặn DOM mất thời gian để load.

> * 📖 [loadCSS với filament group](https://github.com/filamentgroup/loadCSS)
> * 📖 [Ví dụ của preload CSS sử dụng loadCSS](https://gist.github.com/thedaviddias/c24763b82b9991e53928e66a0bafc9bf)

- [ ] **Unused CSS:** ![Low][low_img] Loại bỏ các đoạn mã CSS không sử dụng.

> * 🛠 [UnCSS Online](https://uncss-online.com/) 🛠
> * 🛠 [PurifyCSS](https://github.com/purifycss/purifycss)
> * 🛠 [Chrome DevTools Coverage](https://developers.google.com/web/updates/2017/04/devtools-release-notes#coverage)


### CSS testing

* [ ] **Stylelint:** ![High][high_img] Toàn bộ CSS hoặc SCSS files phải không còn lỗi nào.

> * 🛠 [stylelint, a CSS linter](https://stylelint.io/)
> * 📖 [Sass guidelines](https://sass-guidelin.es/)

* [ ] **Responsive web design:** ![High][high_img] Tất cả các trang đã được kiểm thử (test) tại breakpoints sau: 320px, 768px, 1024px (có thể thêm / khác theo phân tích của bạn).

* [ ] **CSS Validator:** ![Medium][medium_img] Các CSS đã được kiểm thử (test) và lỗi cần thiết đã được chỉnh sửa
.

> * 🛠 [CSS Validator](https://jigsaw.w3.org/css-validator/)

* [ ] **Reading direction:** ![High][high_img] Tất cả các trang cần phải được kiểm tra với ngôn ngữ LTR và RTL nếu chúng cần phải hỗ trợ.

> * 📖 [Building RTL-Aware Web Apps & Websites: Part 1 - Mozilla Hacks](https://hacks.mozilla.org/2015/09/building-rtl-aware-web-apps-and-websites-part-1/)
> * 📖 [Building RTL-Aware Web Apps & Websites: Part 2 - Mozilla Hacks](https://hacks.mozilla.org/2015/10/building-rtl-aware-web-apps-websites-part-2/)

**[⬆ Về đầu trang](#mục-lục)**

---

## Images

> **Notes:** Để am hiểu hơn về việc tối ưu hoá hình ảnh, bạn có thể tham khảo ebook miễn phí **[Essential Image Optimization](https://images.guide/)** được viết bởi tác giả Addy Osmani.

### Best practices

* [ ] **Optimization:** ![High][high_img] Tất cả hình ảnh được tối ưu hóa để hiển thị trên trình duyệt. Định dạng WebP có thể được sử dụng cho các trang web quan trọng (chẳng hạn như trang chủ).

> * 🛠 [Imagemin](https://github.com/imagemin/imagemin)
> * 🛠 Sử dụng [ImageOptim](https://imageoptim.com/) tối ưu hóa hình ảnh của bạn miễn phí.

* [ ] **Retina:** ![Low][low_img] Hãy cung cấp sẵn các layout images x2 hoặc 3x, nhằm hỗ trợ retina display.
* [ ] **Sprite:** ![Medium][medium_img] Với các hình ảnh nhỏ nên đặt trong một sprite file (Ví dụ như trường hợp các icons, chúng có thể được lưu trong một SVG sprite image).
* [ ] **Width và Height:** ![High][high_img] Tất cả thẻ `<img>` được thiết lập height (chiều cao) và width (chiều rộng) (Không chỉ định px hoặc %).

> ***Note:*** Rất nhiều nhà phát triển giả định rằng chiều rộng và chiều cao là không tương thích với các thiết kế responsive web. Điều đó không hoàn toàn đúng trong các trường hợp khác nhau.

* [ ] **Alternative text:** ![High][high_img] Mỗi thẻ `<img>` có chứa một alternative text mô tả ảnh một cách trực quan.

> * 📖 [Alt-texts: The Ultimate Guide](https://axesslab.com/alt-texts/)

* [ ] **Lazy loading:** ![Medium][medium_img] Các hình ảnh phải được lazyloaded (Noscript dự phòng luôn luôn cung cấp nếu trình duyệt không hỗ trợ javascript).

**[⬆ Về đầu trang](#mục-lục)**

---

## JavaScript

### Best practices

* [ ] **JavaScript Inline:** ![High][high_img] Hãy đảm bảo bạn không sử dụng bất cứ JavaScript code inline nào (mixed bên trong HTML code).
* [ ] **Concatenation:** ![High][high_img] Toàn bộ các JavaScript files được ghép lại (concatenated) thành một file duy nhất.
* [ ] **Minification:** ![High][high_img] Toàn bộ các JavaScript files được rút gọn (minified) (Bạn có thể thêm hậu tố `.min` vào tên file).

> * 📖 [Minify Resources (HTML, CSS, and JavaScript)](https://developers.google.com/speed/docs/insights/MinifyResources)

* [ ] **JavaScript security:**

> * 📖 [Guidelines for Developing Secure Applications Utilizing JavaScript](https://www.owasp.org/index.php/DOM_based_XSS_Prevention_Cheat_Sheet#Guidelines_for_Developing_Secure_Applications_Utilizing_JavaScript)

* [ ] **Non-blocking:** ![Medium][medium_img] Các JavaScript files được nạp bất đồng bộ (loaded asynchronously) sử dụng `async` hoặc deferred sử dụng thuộc tính `defer`.

> * 📖 [Remove Render-Blocking JavaScript](https://developers.google.com/speed/docs/insights/BlockingJS)

* [ ] **Modernizr:** ![Low][low_img] Nếu bạn cần nhắm mục tiêu tới một số tính năng cụ thể, bạn có thể sử dụng một Modernizr tùy chỉnh thêm các class trong thẻ `<html>` của bạn.

> * 🛠 [Customize your Modernizr](https://modernizr.com/download?setclasses)

### JavaScript testing

* [ ] **ESLint:** ![High][high_img] Hãy đảm bảo không còn bất kỳ lỗi nào được phát hiện bởi ESLint (Dựa trên các rules do bạn cấu hình hoặc bộ rule tiêu chuẩn).

> * 📖 [ESLint - The pluggable linting utility for JavaScript and JSX](https://eslint.org/)

**[⬆ Về đầu trang](#mục-lục)**

---

## Security

### Quét (scan) và kiểm tra web site của bạn

> * [securityheaders.io](https://securityheaders.io/)
> * [Observatory by Mozilla](https://observatory.mozilla.org/)
> * [ASafaWeb - Automated Security Analyser for ASP.NET Websites](https://asafaweb.com/)

### Best practices

* [ ] **HTTPS:** ![Medium][medium_img] Đảm bảo HTTPS được sử dụng trên mọi page và cho toàn bộ external content (plugins, images...).

> * 🛠 [Let's Encrypt - Free SSL/TLS Certificates](https://letsencrypt.org/)
> * 🛠 [Free SSL Server Test](https://www.ssllabs.com/ssltest/index.html)
> * 📖 [Strict Transport Security](http://caniuse.com/#feat=stricttransportsecurity)

* [ ] **HTTP Strict Transport Security (HSTS):** ![Medium][medium_img] HTTP header được thiết lập là 'Strict-Transport-Security'.

> * 🛠 [Kiểm tra trạng thái HSTS preload và tiêu chuẩn](https://hstspreload.org/)
> * 📖 [HTTP Strict Transport Security Cheat Sheet - OWASP](https://www.owasp.org/index.php/HTTP_Strict_Transport_Security_Cheat_Sheet)
> * 📖 [Transport Layer Protection Cheat Sheet - OWASP](https://www.owasp.org/index.php/Transport_Layer_Protection_Cheat_Sheet)

* [ ] **Cross Site Request Forgery (CSRF):** ![High][high_img] Bạn cần chắc chắn rằng mọi request từ phía server phải hợp lệ và có nguồn gốc từ website/app của bạn để ngăn chặn tấn công CSRF.

> * 📖 [Cross-Site Request Forgery (CSRF) Prevention Cheat Sheet  - OWASP](https://www.owasp.org/index.php/Cross-Site_Request_Forgery_(CSRF)_Prevention_Cheat_Sheet)

* [ ] **Cross Site Scripting (XSS):** ![High][high_img] Trang web của bạn không gặp phải các vấn đề liên quan tới XSS.

> * 📖 [XSS (Cross Site Scripting) Prevention Cheat Sheet  - OWASP](https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet)
> * 📖 [DOM based XSS Prevention Cheat Sheet  - OWASP](https://www.owasp.org/index.php/DOM_based_XSS_Prevention_Cheat_Sheet)

* [ ] **Content Type Options** ![Medium][medium_img] Ngăn chặn Google Chrome và Internet Explorer cố gắng mime-sniff content-type của response từ một máy chủ

> * 📖 [X-Content-Type-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-content-type-options)

* [ ] **X-Frame-Options (XFO)** ![Medium][medium_img] Bảo vệ người truy cập website của bạn trước các cuộc tấn công clickjacking.

> * 📖 [X-Frame-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-frame-options)
> * 📖 [RFC7034 - HTTP Header Field X-Frame-Options](https://tools.ietf.org/html/rfc7034)

**[⬆ Về đầu trang](#mục-lục)**

---

## Performance

### Best practices

- [ ] **Weight page:** ![High][high_img] Dung lượng tải của mỗi page nên nằm trong khoảng từ 0 đến 500 KB.

> * 🛠 [Website Page Analysis](https://tools.pingdom.com)
> * 📖 [Size Limit: Make the Web lighter](https://evilmartians.com/chronicles/size-limit-make-the-web-lighter)

- [ ] **Minified:** ![Medium][medium_img] Mã HTML cần được rút gọn (minified).
> * 🛠 [W3C Validator](https://validator.w3.org/)

* [ ] **Lazy loading:** ![Medium][medium_img] Images, scripts và CSS cần được lazy loaded để cải thiện response time của mỗi page (Xem chi tiết trong các sections tương ứng với images, scripts, css).

* [ ] **Cookie size:** Nếu bạn đang sử dụng cookie chắc chắn mỗi cookie không vượt quá 4096 byte và tên miền của bạn không có nhiều hơn 20 cookies.

> * 📖 [Cookie specification: RFC 6265](https://tools.ietf.org/html/rfc6265)
> * 📖 [Cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)
> * 🛠 [Browser Cookie Limits](http://browsercookielimits.squawky.net/)

### Preparing upcoming requests

> * 📖 [Giải thích cho các kỹ thuật bên dưới](https://css-tricks.com/prefetching-preloading-prebrowsing/)

* [ ] **DNS resolution:** ![Low][low_img] DNS của dịch vụ bên thứ ba có thể được phân giải trước trong suốt idle-time bằng cách sử dụng `dns-prefetch`.

```html
<link rel="dns-prefetch" href="https://example.com">
```

* [ ] **Preconnection:** ![Low][low_img] DNS lookup, TCP handshake và TLS negociation với các dịch vụ cần được thực hiện trước trong idle-time bằng cách sử dụng `preconnect`.

```html
<link rel="preconnect" href="https://example.com">
```

* [ ] **Prefetching:** ![Low][low_img] Các tài nguyên cần tải (e.g. lazy loaded images) có thể được request trước trong idle-time bằng cách sử dụng `prefetch`.

```html
<link rel="prefetch" href="image.png">
```

* [ ] **Preloading:** ![Low][low_img] Các tài nguyên cần thiết cho page hiện tại (e.g. scripts được đặt ở cuối thẻ `<body>`) bằng cách sử dụng `preload`.

```html
<link rel="preload" href="app.js">
```

> * 📖 [Khác biệt giữa prefetch và preload](https://medium.com/reloading/preload-prefetch-and-priorities-in-chrome-776165961bbf)

### Performance testing

* [ ] **Google PageSpeed:** ![High][high_img] Toàn bộ các page của bạn cần được kiểm thử (không chỉ riêng homepage) và phải đạt số điểm tối thiểu 90/100.

> * 🛠 [Google PageSpeed](https://developers.google.com/speed/pagespeed/insights/)
> * 🛠 [Test your mobile speed with Google](https://testmysite.withgoogle.com)
> * 🛠 [WebPagetest - Website Performance and Optimization Test](https://www.webpagetest.org/)

**[⬆ Về đầu trang](#mục-lục)**

---

## Accessibility

> **Notes:** Bạn có thể xem playlist sau [A11ycasts with Rob Dodson](https://www.youtube.com/playlist?list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g) 📹

### Best practices

- [ ] **Progressive enhancement:** ![Medium][medium_img] Các chức năng chính như navigation và tìm kiếm nên hoạt động mà không cần kích hoạt JavaScript.

> * 📖 [Enable / Disable JavaScript in Chrome Developer Tools](https://www.youtube.com/watch?v=kBmvq2cE0D8)

- [ ] **Color contrast:** ![Medium][medium_img] Độ tương phản màu tối thiểu cần pass WCAG AA (AAA for mobile).

> * 🛠 [Contrast ratio](https://leaverou.github.io/contrast-ratio/)

#### Headings

* [ ] **H1:** ![High][high_img] Tất cả các page phải có thẻ H1 không là tiêu đề của website.
* [ ] **Headings:** ![High][high_img] Tiêu đề nên được sử dụng đúng cách theo đúng thứ tự (H1 đến H6).

> * 📹 [Tại sao headings và landmarks quan trọng -- A11ycasts #18](https://www.youtube.com/watch?v=vAAzdi1xuUY&index=9&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

#### Landmarks

- [ ] **Role banner:** ![High][high_img] `<header>` có `role="banner"`.
- [ ] **Role navigation:** ![High][high_img] `<nav>` có `role="navigation"`.
- [ ] **Role main:** ![High][high_img] `<main>` có `role="main"`.

> * 📖 [Sử dụng ARIA landmarks để xác định các phân vùng trên page](https://www.w3.org/WAI/GL/wiki/Using_ARIA_landmarks_to_identify_regions_of_a_page)

### Semantics (Ngữ nghĩa)

- [ ] **Specific HTML5 input types are used:** ![Medium][medium_img] Điều này đặc biệt quan trọng trên các thiết bị di động hiển thị bàn phím tùy chỉnh và các widgets cho các kiểu khác nhau.

> * 📖 [Mobile Input Types](http://mobileinputtypes.com/)

### Form

* [ ] **Label:** ![High][high_img] Mỗi một label (nhãn) được gắn kết với một input form element. Trong trường hợp label không thể hiển thị, hãy sử dụng `aria-label` thay thế.

> * 📖 [Using the aria-label attribute - MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-label_attribute)

### Accessibility testing

* [ ] **Accessibility standards testing:** ![High][high_img] Sử dụng công cụ WAVE để kiểm thử nếu page của bạn tuân theo các tiêu chuẩn về khả năng tiếp cận.

> * 🛠 [Wave testing](http://wave.webaim.org/)

* [ ] **Keyboard navigation:** ![High][high_img] Kiểm tra trang web của bạn bằng cách chỉ sử dụng bàn phím theo thứ tự được đặt trước. Tất cả các yếu tố tương tác đều có thể truy cập và sử dụng được.
* [ ] **Screen-reader:** ![Medium][medium_img] Tất cả các page đều được kiểm thử trong trình đọc màn hình (VoiceOver, ChromeVox, NVDA hoặc Lynx).
* [ ] **Focus style:** ![High][high_img] Nếu `focus` bị vô hiệu hóa, nó được thay thế bằng trạng thái `visible` trong CSS.

> * 📹 [Managing Focus - A11ycasts #22](https://www.youtube.com/watch?v=srLRSQg6Jgg&index=5&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

**[⬆ Về đầu trang](#mục-lục)**

---

## SEO

* [ ] **Google Analytics:** ![High][high_img] Google Analytics được cài đặt và định cấu hình chính xác.
* [ ] **Headings logic:** ![Medium][medium_img] Tiêu đề văn bản giúp nội dung trong trang hiện tại dễ hiểu.
* [ ] **sitemap.xml:** ![High][high_img] Tồn tại sitemap.xml và được submit cho Google Search Console (Google Webmaster Tools).
* [ ] **robots.txt:** ![High][high_img] File robots.txt không block webpages.

> * 🛠 Kiểm tra robots.txt của website với [Google Robots Testing Tool](https://www.google.com/webmasters/tools/robots-testing-tool)

* [ ] **Structured Data:** ![High][high_img] Các pages sử dụng dữ liệu có cấu trúc đều được kiểm thử và không có lỗi. Dữ liệu có cấu trúc giúp crawlers hiểu nội dung của page hiện tại.

> * 📖 [Introduction to Structured Data - Search - Google Developers](https://developers.google.com/search/docs/guides/intro-structured-data)
> * 🛠 Test your page with the [Structured Data Testing Tool](https://developers.google.com/structured-data/testing-tool/)
> * 🛠 Complete list of vocabularies that can be used as structured data. [Schema.org Full Heirarchy](http://schema.org/docs/full.html)

* [ ] **Sitemap HTML:** ![Medium][medium_img] Một sơ đồ trang web HTML (sitemap) được cung cấp và có thể truy cập thông qua một liên kết ở footer của trang web.

> * 📖 [Sitemap guidelines - Google Support](https://support.google.com/webmasters/answer/183668?hl=en)
> * 🛠 [Sitemap generator](https://websiteseochecker.com/html-sitemap-generator/)


**[⬆ Về đầu trang](#mục-lục)**

---

## Translation

Front-End Checklist được dịch sang các ngôn ngữ khác:

* 🇬🇧 Tiếng Anh: [thedaviddias/Front-End-Checklist](https://github.com/thedaviddias/Front-End-Checklist)
* 🇯🇵 Tiếng Nhật: [miya0001/Front-End-Checklist](https://github.com/miya0001/Front-End-Checklist)
* 🇪🇸 Tiếng Tây Ban Nha: [eoasakura/Front-End-Checklist-ES](https://github.com/eoasakura/Front-End-Checklist-ES)
* 🇨🇳 Tiếng Trung: [JohnsenZhou/Front-End-Checklist](https://github.com/JohnsenZhou/Front-End-Checklist)
* 🇰🇷 Tiếng Hàn: [kesuskim/Front-End-Checklist](https://github.com/kesuskim/Front-End-Checklist)
* 🇧🇷 Tiếng Bồ Đào Nha: [jcezarms/Front-End-Checklist](https://github.com/jcezarms/Front-End-Checklist)

---

## Front-End Checklist Badge

Nếu bạn muốn hiển thị rằng bạn đang follow các quy tắc của Front-End Checklist, hãy gắn huy hiệu này lên tập tin README của bạn!

➔ [![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)

```md
[![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)
```

**[⬆ Về đầu trang](#mục-lục)**

---

## Contributing

**Mở ra một issue hoặc một pull request khi bạn muốn đề nghị thay đổi hoặc bổ sung.**

### Guide

**Front-End Checklist** repository chứa 2 nhánh chính:

#### 1. `master`

Nhánh này bao gồm `README.md` file tác động trực tiếp đến nội dung trên [Front-End Checklist](http://frontendchecklist.com/) website.

#### 2. `develop`

Nhánh này sẽ được sử dụng để tạo ra các thay đổi thay đổi đáng kể trong cơ cấu, nội dung nếu cần thiết. Nó là thích hợp hơn để sử dụng các nhánh chủ để sửa chữa các lỗi nhỏ hoặc thêm một mục mới.

### Contributors

Danh sách những [cá nhân đóng góp](https://github.com/thedaviddias/frontendchecklist/graphs/contributors) cho dự án.

## Support

Nếu bạn có bất kỳ câu hỏi hoặc lời khuyên nào, đừng ngần ngại liên hệ qua Gitter hoặc Twitter:

* [Chat on Gitter](https://gitter.im/Front-End-Checklist/Lobby?utm_source=share-link&utm_medium=link&utm_campaign=share-link)
* [Twitter](https://twitter.com/thedaviddias)

## Authors

**[David Dias](https://github.com/thedaviddias/Front-End-Checklist)**

## License

[![CC0](https://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

**[⬆ Về đầu trang](#mục-lục)**

[low_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png
[medium_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png
[high_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png
