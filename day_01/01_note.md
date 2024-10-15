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

首先我們先創造一個名為 `index.html` 的檔案，並且在頁面內輸入以下 HTML 原始碼：

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
