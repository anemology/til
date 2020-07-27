# Template Literals

JavaScript 中格式化字串的方式，從 `ES6` 開始，不支援 IE (放生 IE 吧!)

類似 Java 的 `String.format`，或是 Python3 的 `f-strings` ([Literal String Interpolation](https://www.python.org/dev/peps/pep-0498/))

## 使用方式

將原本字串使用的單引號 `'` 或雙引號 `"`，替換成 backtick `` ` ``

* 原本字串內要加入換行符號
    ```javascript
    console.log("我是第一行\n"+
    "我是第二行");
    ```
    可以改寫成
    ```javascript
    console.log(`我是第一行
    我是第二行`);
    // 我是第一行
    // 我是第二行
    ```
* 字串內直接帶入變數
    ```javascript
    let a = 5;
    let b = 10;
    console.log(`a 的值是: ${a}, b 的值是: ${b}`);
    // a 的值是: 5, b 的值是: 10
    ```

---

## 參考

* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals
* https://caniuse.com/#feat=template-literals
