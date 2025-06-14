# picture tag

今天用 [PageSpeed](https://developers.google.com/speed/pagespeed/insights/) 掃描網站的時候，有一個建議是說可以將圖片改用 `WebP`、`JPEG 2000` 或 `JPEG XR`，但除了 `WebP` 之外，另外兩種格式目前主流瀏覽器都還不支援。

如果瀏覽器不支援 `WebP` 的話，要如何使用回原本的 `jpg` 或 `png`。

html 有個 `picture` tag，範例如下

```html
<picture>
  <source type="image/webp" srcset="images/flower1.webp">
  <source type="image/jpeg" srcset="images/flower1.jpg">
  <img src="images/flower1.jpg">
</picture>
```

`source` tag 內設定 `media`、`srcset`、`type` 等屬性當條件，若是都不符合或是瀏覽器都不支援，就會用回原本的 `img` tag，詳細請參考 [MDN](https://developer.mozilla.org/zh-TW/docs/Web/HTML/Element/picture)。

## 參考

* https://developer.mozilla.org/zh-TW/docs/Web/HTML/Element/picture
* https://web.dev/uses-webp-images/
* https://web.dev/codelab-serve-images-webp/
* https://caniuse.com/#feat=webp
* https://caniuse.com/#feat=jpeg2000
* https://caniuse.com/#feat=jpegxr

---

`html` `picture-tag` `webp`
