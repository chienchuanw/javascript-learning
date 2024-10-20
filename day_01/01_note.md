# 10 天搞定 JavaScript——第一天：開始真的不難

## 前言

這個計畫源自於 Kuro 老師的《0 陷阱！0 誤解！8 天重新認識 JavaScript！》以及軟體工程師 Asabeneh Yetayeh 於個人 GitHub 所發起的 [30-Days-Of-JavaScript](https://github.com/Asabeneh/30-Days-Of-JavaScript/tree/master) 計畫，同一時間，由五倍學院所舉辦的第十八屆 ASTRO Camp 也才開班，想趁這個時間重新複習 JavaScript，並且認真解決過往未能徹底了解的部分。

至於為什麼叫「10 天搞定 JavaScript」呢？真的能在 10 天搞定 JavaScript 嗎？老實說我也不知道，只是想說 Kuro 老師的書名取作「8 天重新認識 JavaScript」，那凡人如我多花個兩天應該也算挺合理的吧，若是真的 10 天沒辦法講完複習的內容，大不了再多加個幾天就是，可以的！

和復健系列相同，這個《10 天搞定 JavaScript》主要針對「已經有 JavaScript 初步觀念」的學習者們，透過這系列文章來再次複習 JavaScript 的內容，如果發現本文有任何錯誤的地方，也歡迎各方大神隨時指出，因為這個系列還有一個重點是希望將 Asabeneh Yetayeh 的 [30-Days-Of-JavaScript](https://github.com/Asabeneh/30-Days-Of-JavaScript/tree/master) 進行中文翻譯與勘誤，希望能使學習程式語言成為一件更輕鬆的事。

## 需要準備什麼？

如果說學 JavaScript 什麼都不需要準備，是也有點太過煽情，不過需要準備的東西，倒也真的不多，大概就這些：

- 下定學好的決心（熱血了！）
- 一台可以用的電腦（建議是不要太舊的 Mac，因為我的沒有很舊。）
- 可以上網（不能上網，要電腦幹嘛？）
- 瀏覽器（建議使用 Chrome，因為很方便）
- 程式代碼編輯器（新手推薦使用 Visual Studio Code aka [VSCode](https://code.visualstudio.com/download)）

## 環境安裝與設定

由於現今大部分的瀏覽器 browser 都支援 JavaScript，所以如果有安裝 Chrome 作為預設瀏覽器的話，可以直接使用 Chrome 作為 JavaScript 的執行環境（Runtime），並且按下 `F12` 打開開發者工具，並點選 `Console（控制台）` 的頁籤，便能夠直接輸入與執行 JavaScript 原始碼。

JavaScript 執行環境也不僅於瀏覽器，我們也可以在電腦上安裝 Node.js，來執行 JavaScript 原始碼，這邊先有個觀念是 Node.js 是**最常見**的 **JavaScript 執行環境 run-time environment**，但**並非唯一**可以執行 JavaScript 的執行環境，市面上還有很多其他各有優點的執行環境，但這並非目前的重點，所以暫時就不介紹了。

### 開啟瀏覽器裡的 Console 控制台——以 Chrome 為例

- 在瀏覽頁面的空白處點擊右鍵，並選擇最下方的 Inspect （檢查），或者按下鍵盤上的 `F12`。
  ![Screenshot_inspect](./images/Screenshot%202024-10-14%20at%204.35.24%20PM.png)
- 點選頁籤上的 Console（控制台）。
  ![Screenshot_console](./images/Screenshot%202024-10-14%20at%204.39.21%20PM.png)
- 開始輸入 JavaScript 原始碼。
  ![Screenshot_code](./images/Screenshot%202024-10-14%20at%205.06.02%20PM.png)

### 安裝 Node.js

最簡單的作法莫過於直接前往 [Node.js 的官網](https://nodejs.org/zh-tw/download/package-manager)，找到想要使用的版本，進行下載安裝，無腦地點擊下一步即可。

不過身為 Mac 的使用者，如果有在使用 Homebrew 作為軟體套件的管理系統，更推薦使用 Homebrew 指令來安裝與管理 Node.js 的版本，這邊也簡單說一下流程。

```zsh
# 安裝最新版本 Node.js
brew install node

# 安裝 Node.js 14.x 版本
brew install node@14

# 將 Node.js 加入 PATH 環境變數中，讓終端機可以找到正確的版本
export PATH="/usr/local/opt/node@14/bin:$PATH"

# 使用命令讓更改生效（假設使用的是 zsh shell）
source ~/.zshrc

# 更新 Node.js
brew upgrade node

# 移除已安裝的 Node.js
brew uninstall node
```

## 我的第一個 Hello world

有發現嗎？我們在剛剛說明執行環境的地方，同一時間寫下了第一個 JavaScript 程式碼——`console.log('Hello World!')`，`console.log()` 是 JavaScript 中，用來印出各種東西的函式，未來如果不知道程式碼錯在哪？`console.log()`！，不知道結果是什麼？`console.log()`！`console.log()` 絕對是 JavaScript 中最常見的好朋友。

這邊也簡單講一下 `console.log()` 的使用方式：

```js
// Syntax
// console.log 可以接受多個引數 argument
console.log(param1, param2, param3);

// Example
// 可以自己試著把這些輸入在瀏覽器的 console，印出來看看結果是什麼
console.log("Hello", "World", "!");
console.log("HAPPY", "NEW", "YEAR", 2020);
console.log("Welcome", "to", 30, "Days", "Of", "JavaScript");
```

## 如果想要在 JavaScript 原始碼做筆記怎麼辦？

其實這個答案在上面已經不言自明了，我們可以用 `//` **兩條斜線**「註解 comment」掉單行的程式碼，而被註解掉的程式碼，執行環境將不會執行該段程式碼，直接跳到下一段未註解的程式碼。

註解除了跳過某段程式碼，主要也會用來註記某段程式碼的功用，以便我們在閱覽程式碼時，可以更快地瞭解該段程式碼的功能，省去逐行閱覽程式碼、猜測其功能的時間。

- 單行註解 Single Line Comment

  ```js
  // This is the first comment
  // This is the second comment
  // I am a single line comment
  ```

- 多行註解 Multi-line Comment

  ```js
  /*
  This is a multiline comment  
  Multi-line comments can take multiple lines  
  JavaScript is the language of the web  
  */
  ```

## 各種可能的錯誤

剛開始學習任何新事物時，會害怕犯錯、看到錯誤訊息，然後學習程式語言注定會是一場與錯誤相伴的旅程，遇到錯誤時，更重要的是需要知道哪裡出錯，以及如何解決錯誤，越是深入學習，越能感受到錯誤其實不可怕，最可怕的是「明明出錯了，但程式卻不知道哪裡錯了」，這種錯誤才叫人難以解決。

而且工程師其實是個非常貼心的生物，如果有哪邊出了錯，也會盡可能透過**錯誤訊息**告訴我們哪裡出錯了，甚至還會提供我們如何解決錯誤的方式。

讓我們逐行執行下列的程式碼，看看會得到哪些訊息：

```js
console.log("Hello, World!')
// Uncaught SyntaxError: Invalid or unexpected token
// 解決方式：應該要使用成對的單引號或是成對的雙引號夾住字串，不應該混用。

console.log('Hello, World!)
// Uncaught SyntaxError: Invalid or unexpected token
// 解決方式：開頭使用了單引號，結尾也應該使用單引號包覆住字串

console.log('Hello, World!'
// Uncaught SyntaxError: missing ) after argument list
// 解決方式：應該要用 ) 關閉 console.log 的函式
```

## 數學運算

我們也可以使用 JavaScript 進行數學運算，然後透過 `console.log()` 印出計算的結果：

```js
console.log(2 + 3); // 加法
console.log(3 - 2); // 減法
console.log(2 * 3); // 乘法
console.log(3 / 2); // 除法
console.log(3 % 2); // 取得餘數
console.log(3 ** 2); // 指數，也就是次方
```

## 開始使用程式碼編輯器（code editor）

雖然我們可以在瀏覽器的 Console 中編寫 JavaScript 程式碼，但這並不適合大型專案。在實際的專案中，工程師們通常使用不同的程式碼編輯器來編寫程式碼，而在這次的系列文章中，我們將使用微軟的 Visual Studio Code，如果自己有習慣的編輯器，也是可以使用的！

### 安裝 Visual Studio Code

Visual Studio Code 是一款非常受歡迎的開源文字編輯器，如果還沒有安裝的話，可以從 [Visual Studio Code](https://code.visualstudio.com/) 官方網站下載並安裝。

在完成安裝 Visual Studio Code 後，也請至 Extension 的頁籤內搜尋 **Live Server** 並安裝，之後會需要使用 Live Server 來預覽我們所創造出來的網頁畫面。

## 如何在網頁程式碼裡面使用 JavaScript

基本上 JavaScript 可以透過幾種方式放入網頁之中，由於中文翻譯起來容易詞不達意，這邊我們用英文進行分類：

- Inline script
- Internal script
- External script
- Multiple External scripts

### Inline Script

首先我們先創造一個名為 `inline-script.html` 的檔案，並且在頁面內輸入以下 HTML 原始碼：

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>30DaysOfScript:Inline Script</title>
  </head>

  <body>
    <button onclick="alert('Welcome to 30DaysOfJavaScript!')">Click Me</button>
  </body>
</html>
```

可以先透過 VS Code 的 Live Server 來預覽一下這個網頁，會在網頁上看到一個 `Click Me` 的按鈕，按下去之後會跳出一個警示文字 `Welcome to 30DaysOfJavaScript`。

![screenshot_button](./images/Screenshot%202024-10-15%20at%209.14.03 PM.png)

在這個程式碼中，我們使用了 `<button>` 標籤創造了一個按鈕，並且使用 `onclick` 屬性監聽按鈕的點擊事件，在點擊那個按鈕後，會觸發 `alert('Welcome to 30DaysOfJavaScript!')` 這個 JavaScript 函式。

這邊的 `alert()` 是一個 JavaScript 的內建函式，在執行這個函式後，會跳出一個彈出式（pop-up）的訊息，而訊息的內容則會是我們剛剛寫的 `'Welcome to 30DaysOfJavaScript!'`。

### Internal Script

如果我們把 JavaScript 直接寫在 HTML 檔案內的 `<script>` 標籤內，一般來說會將 `<script>` 放在 HTML 裡的 `<head>` 或是 `<body>` 標籤內，而這種作法稱為 **Internal Script**。

讓我們再新建一個 `internal-script.html` 檔案，並且在檔案內加入下方原始碼：

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>30DaysOfScript:Internal Script</title>
    <script>
      console.log("Welcome to 30DaysOfJavaScript");
    </script>
  </head>
  <body></body>
</html>
```

當我們用 Live Server 預覽頁面時，會發現頁面裡雖然一片空白，但使用 `F12` 並打開 Console 後，會發現上面出現了一行，因為 `console.log()` 而印出的 `Welcome to 30DaysOfJavaScript` 字串。

剛剛範例示範了如何在 `<head>` 標籤裡使用 JavaScript，接下來我們也可以試試看如何在 `<body>` 標籤裡使用 JavaScript，讓我們修改一下剛才的 HTML 原始碼：

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>30DaysOfScript:Internal Script</title>
  </head>
  <body>
    <script>
      console.log("Hello world!");
    </script>
  </body>
</html>
```

同樣地，雖然頁面仍然一片空白，我們卻可以在 Console 看到被印出的 `Hello world!` 字串。

### External Script

和 Internal Script 相似，External Script 同樣會在 `<head>` 或 `<body>` 裡嵌入 `<script>` 標籤，但和 Internal Script 不同的是，External Script 會把 JavaScript 的程式碼拆分到副檔名為 `.js` 的檔案裡，再透過「引入」的方式導進 HTML 使用，藉此拆分 HTML 與 JavaScript 原始碼，讓檔案依照其功能好好分類，而不是全部都塞在 HTML 裡面。

所以依照前面的例子，我們會把 `console.log('Hello world!')` 放在一個新的 `introduction.js` 檔案裡（這個檔案可以任意命名）：

```js
// introduction.js
console.log("Hello world!");
```

然後在新的 `external-script.html` 中，引入 `introduction.js`：

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>30DaysOfJavaScript:External script</title>
    <script src="introduction.js"></script>
  </head>
  <body></body>
</html>
```

同樣地，`<script>` 也可以放在 HTML 的 `<body>` 標籤內：

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>30DaysOfJavaScript:External script</title>
  </head>
  <body>
    <script src="introduction.js"></script>
  </body>
</html>
```

這兩個方式都可以在 Console 裡看到 `Hello world!` 被印出來。

### Multiple External Scripts

一份 HTML 不只可以引入一份 `.js` 檔案，我們可以針對不同的功能需求，引入多份 External Script，所要做的僅僅是於 HTML 中再新增 `<script>` 標籤。

承接剛剛的範例，如果我們想在 `external-script.js` 中，再引入一個 `myName.js` 的 JavaScript 檔案：

```js
// myName.js
console.log("I am Frank.");
```

```html
<!-- external-script.html -->
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>30DaysOfJavaScript:External script</title>
  </head>
  <body>
    <script src="./introduction.js"></script>
    <script src="./myName.js"></script>
  </body>
</html>
```

這時候可以在 Console 看到字串 `Hello world!` 與 `I am Frank.` 相繼被印出。

## JavaScript 中的資料型別（Data Types）

如同其他程式語言，JavaScript 種也有多種資料型別（Data Types），其中資料型別又可分為兩種：

- **基本型別 Primitive Types**
- **物件型別 Object Types**

（在程式語言中會有大量的英文專有名詞，由於不同的工程師有不同的翻譯方式，為了避免同一英文字詞卻有多種中文翻譯，後續文章將主要使用英文專有名詞。）

### Primitives Type 基本型別

JavaScript 中的 Primitive Types 包含：

- String 字串
- Number 數字
- Boolean 布林值（真假值）
- undefined 未定義
- Null 空值
- Symbol 符號

#### Numbers

作為最常見的資料型別之一，Number 又可以再細分成：

- Integer 整數：其中包含了**正整數 Positive Integer**、**負整數 Negative Integer**、**零 Zero**。
- Float 浮點數：也就是我們熟知的小數，只要任何帶有小數點的數字都是 Float，像是 0.0 也是浮點數。

```js
// integers
-3,
  -2,
  -1,
  0,
  1,
  2,
  3 -
    // float
    3.5,
  -2.25,
  -1.0,
  0.0,
  1.1,
  2.2,
  3.5;
```

#### Strings

String 應該更熟悉不過了，任何字元（Character）被夾在雙引號（single quotes）、單引號（double quotes）、反引號（backticks），都可以被視為 String。

```js
// 使用 single quotes
"I am a string.";

// 使用 double quotes
"This is also a string." // 使用 backticks
`String string string!`;
```

#### Booleans

Boolean 布林值又可以被稱作「真假值」，因為 boolean 只有 `true` 真值與 `false` 假值，非真即假非假即真。

```js
true;
false;
```

#### Undefined

在 JavaScript 中，如果沒有給變數（variable）進行賦值（assign a value），此時該變數的值會是 `undefined`。此外，如果一個函數沒有返回（return）任何值，它也會返回 `undefined`。

```js
let firstName;
console.log(firstName); // undefined，因為還沒有賦值
```

#### Null

`null` 代表的是「空值」，而在 JavaScript 或是其他的程式語言中，`null` 跟 `undefined` 是有所區別的，`null` 像是說「**沒有東西**」，而 `undefined` 則像是說「**不知道這個東西是什麼**」，在語意上有明顯的區別。

```js
// 我們可以將一個變數賦值為 null 空值
let emptyValue = null;
```

### 如何判別資料型別？

在 JavaScript 中，我們可以透過內建關鍵字（keyword） `typeof` 來確認變數或值的資料型態為何。

```js
console.log(typeof "Frank"); // string
console.log(typeof 5); // number
console.log(typeof true); // boolean
console.log(typeof null); // object type
console.log(typeof undefined); // undefined
```

> 這邊補充一個小知識：有時候可能會看到其他人寫成 `typeof(123)` 確認其資料型態，但我們前面有說過，`typeof` 其實是一個關鍵字，而不是內建函式（built-in function），所以這邊 `typeof()` 裡面的 `123` 也並非引數（argument），實際上這邊的小括號 `()` 有跟沒有是沒有差別的，也就是說 `typeof(123)` 跟 `typeof 123` 是完全等價的內容。

## 變數是什麼？

在程式語言中，我們使用變數 variable 來儲放想要放入的值 value，換成生活化的例子，變數可以視作一個塑膠盒，我們可以在塑膠盒裡面放入各種想放進去的物品，可以放入雞腿、青菜，也可以放入充電線、電池等各種東西，而這些變數會被記錄在記憶體內，等到我們需要使用時，程式會從記憶體中找出這些變數，接續進行後續的運算。

在 JavaScript 中，當我們要想要儲放值在一個變數時，我們首先需要進行**宣告 declare**，透過關鍵字如：`var`、`let`、`const` 完成變數宣告後，才能接續變數的賦值，我們可以把宣告想像成「為塑膠盒貼上姓名標籤，好讓我們（記憶體）知道這是一個變數與它的名稱」。

早期 JavaScript 其實只能使用 `var` 進行變數宣告，然而透過 `var` 宣告的變數會造成一些問題，像是變數提升 hoisting（這個之後會再提到），為了解決最初語言設計上的缺陷，所以新增了 `let` 與 `const` 兩個用於變數宣告的關鍵字。

- `let` 所宣告的變數，後續可以重新賦值，覆蓋最初的值。
- `const` 所宣告的變數，裡面的值是「不可以」再修改，所以通常會常數 constant 的宣告。（例如：圓周率固定是 3.14，所以我們可以 `const PI = 3.14`）

> 對於初學者來說，可以無腦理解成優先使用 `const` 進行變數宣告，如果遇到跳錯（像是要改變變數的值，也就是重新賦值），再把 `const` 改成 `let` 即可。但就是不要使用 `var` 做宣告，更重要的是，**千萬不要沒宣告就使用變數**。
