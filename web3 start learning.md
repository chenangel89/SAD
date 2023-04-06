# [學習筆記](https://hackmd.io/aUM4r9ZfTrmxu8W2UY606w?both)
# 學習筆記
## 1. Command Line
常用的 Windows 終端機命令程式

| 命令程式   |    說明  | 
| -------- | -------- |
|notepad|編輯文件|
|clear|清空當前頁面|
| dir    | 	列出當前目錄下的所有文件和子目錄。    | 
| cd    | 	改變當前工作目錄。例如：cd Documents 將當前目錄更改為 Documents。    | 
| mkdir    | 	創建一個新的目錄。例如：mkdir NewFolder 將創建一個名為 NewFolder 的新目錄。。    | 
| type    | 	顯示指定文件的內容。例如：type example.txt 會顯示 example.txt 文件的內容。    | 
| copy   | 	複製文件。例如：copy example.txt new.txt 將複製 example.txt 文件並將其命名為 new.txt。    | 
| move    | 	移動文件或重命名文件。例如：move example.txt Documents\example.txt 將 example.txt 文件移動到 Documents 文件夾中。    | 
| del   | 	刪除文件。例如：del example.txt 將刪除 example.txt 文件。    | 
| tasklist   | 	列出當前正在運行的所有進程。   | 
|ping|測試與另一個設備的連接。例如：ping www.google.com 將測試您的計算機是否可以連接到 Google 網站。|
|ipconfig|顯示計算機的 IP 配置信息。|

<hr>

## 2. 前端基礎知識

### JavaScript
學習自[JavaScript 速成](https://www.youtube.com/watch?v=hWmri8PbZUc)
* #### 一些方法
```javascript
console.log("hello".length);//字串長度
console.log("hello".charAt(0));//第幾個字符
console.log("hello, world!".replace("world", "puppy"));//字串替換
console.log("hello, world!".toUpperCase());//切換成大寫
```
* #### 變量、型別
```javascript
const pi = 3.14 //不可改變
console.log(pi);
//程式將3看成字串，輸出為345
var x = 3 + '4' + '5'; //345
console.log(x);
//3先和4相加為7，之後轉為字串和'5'相加
var y = 3 + 4 + '5' //75
console.log(y)

///三個等號時，沒有類型字符轉換
console.log(123 == '123'); //true
console.log(123 === '123'); //false，沒有類型字符轉換
console.log(1 == true); //true
console.log(1 === true); //false，沒有類型字符轉換

var沒有作用域，let有作用域
```
* #### switch示例
```javascript
let name = "Ann"
switch (name){
    case "Ann":
        console.log("Ann");
        break;
    case "David":
        console.log("David");
        break;
    default:
        console.log("Stranger");
}//設置break防止重複判斷
```
* #### 物件對象
```javascript
var obj = new Object();
obj = {
    name: "Ann",
    age: "23",
    email: "Ann.891010@gmail.com",
    contact:{
        phone: "0927035899",
        LineId: "Ann891010"
    }
};
//兩種方式調用
console.log(obj.contact.phone);
console.log(obj["contact"]["LineId"]);
//直接新增新的項目
obj.contact.ig = "chen.ann.10";
console.log(obj.contact);
```

* #### 數組
```javascript
//兩種開陣列方式
let a = new Array();
let b = [];

a[0] = "puppy";
a[6] = "love"
// console.log(a);
// console.log(a[1]);

b = ["Park en-bin", "Kim hyun-jung", "Chen An-chieh"]
//兩種遍歷陣列的方式
for(let i=0; i<a.length; i++) console.log(a[i]);
for(let i in a) console.log(a[i]);
//下面的這種方式不會印出中間的空值(未定義值)

a.reverse();//反轉
a.push("monkey");//尾端加入
a.pop();//尾端刪除
a.unshift("cat");//開頭加入
a.shift();//開頭刪除
```

* #### 函式
```javascript
let c = 1;
function add(x){
    c += x;
}
add(5);
console.log(c);//6

function add_2(){
    let sum = 0;//arguments可以得到傳入的東西
    for(let i=0; i<arguments.length; i++){
        sum += arguments[i];
    }
    return sum;
}
let sum = add_2(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);
console.log(sum);

//一種沒聽過的function用法
function add_3(a){//閉包
    return function(b){
        return a + b;
    }
}
let x = add_3(5);//x變成一種方法
let sum_2 = x(10);//10作為a和b的5相加
console.log("sum_2:"+sum_2);//11
```
<hr>

### HTML
* [ mozilla 的 HTML 入門文件](https://developer.mozilla.org/zh-TW/docs/Learn/HTML/Introduction_to_HTML/Getting_started)
* [HTML 速成](https://www.youtube.com/watch?v=nNFF_sib0Jc)
* [HTML教學](https://steam.oxxostudio.tw/category/html/index.html)
* ##### 基本架構
![](https://i.imgur.com/qHPg1mw.jpg)
* ##### 塊級元素 vs. 內聯元素
```typescript!
在HTML中，元素可以分為塊級元素和內聯元素。

塊級元素在網頁中佔據一個獨立的區塊，預設情況下總是從新行開始，且佔據整個可用的寬度。塊級元素的例子包括<div>, <p>, <h1>, <ul>, <li>等等。

內聯元素則不會在網頁中佔據一個獨立的區塊，而是在一行上與其他元素共享空間，僅佔據其內容的寬度。內聯元素的例子包括<span>, <a>, <img>, <em>, <strong>等等。

塊級元素可以包含其他元素，包括其他塊級元素和內聯元素。內聯元素只能包含文本或其他內聯元素。
```

* ##### 一些用法
```htmlembedded!
<!-- 水平線 -->
<hr>

<!-- 換行 -->
<br>

<!-- 斜體 -->
<em></em>

<!-- 粗體 -->
<strong></strong>

<!-- 文字大到小 -->
<h1></h1>
<h2></h2>
<h3></h3>
<h4></h4>
<h5></h5>
<h6></h6>

<!-- 設連結 -->
<a href="https://moodle3.ntnu.edu.tw/" target="_blank">ntnu moodle</a>
```
<a href="https://moodle3.ntnu.edu.tw/" target="_blank">ntnu moodle</a>

```htmlembedded!
<!-- 無序列表 -->
<ul>
<li>item 1</li>
<li>item 2</li>
</ul>
```

<ul>
<li>item 1</li>
<li>item 2</li>
</ul>

```htmlembedded!
<!-- 有序列表 -->
<ol>
<li>item 1</li>
<li>item 2</li>
</ol>
```

<ol>
<li>item 1</li>
<li>item 2</li>
</ol>

#### 表格

```htmlembedded!
<table>
  <tr>
    <th>早餐</th>
    <th>午餐</th>
    <th>晚餐</th>
  </tr>
  <tr>
    <td>三明治</td>
    <td>牛肉麵</td>
    <td>餃子</td>
  </tr>
  <tr>
    <td>鮪魚蛋餅</td>
    <td>拉麵</td>
    <td>咖哩飯</td>
  </tr>
</table>
```

<table>
  <tr>
    <th>早餐</th>
    <th>午餐</th>
    <th>晚餐</th>
  </tr>
  <tr>
    <td>三明治</td>
    <td>牛肉麵</td>
    <td>餃子</td>
  </tr>
  <tr>
    <td>鮪魚蛋餅</td>
    <td>拉麵</td>
    <td>咖哩飯</td>
  </tr>
</table>

#### 表單

```htmlembedded!
<form action="xxx.js" method="POST">
    
    <div>
        <label>First Name：</label>
        <input type="text" name="firstname" placeholder="Enter First Name">
    </div>
    
    <div>
        <label>Last Name：</label>
        <input type="text" name="lastname" placeholder="Enter Last Name">
    </div>
    
    <div>
        <label>Email：</label>
        <input type="email" name="email" placeholder="Enter Email">
    </div>
    
    <div>
      <input type="submit" name="submit" value="提交" style="margin-left:30%"> 
    </div>

</form>
```
![](https://i.imgur.com/6aRdrIk.png)

##### - action="xxx.js"表示提交後交給xxx.js
##### -在HTML表單中，method屬性用於定義提交表單的HTTP請求的方法。常見的方法有兩種：POST和GET。
```typescript!
POST方法會將表單數據作為HTTP請求主體的一部分發送到伺服器端。這通常用於提交敏感信息，例如登入資訊、銀行賬戶等等。由於數據在請求主體中發送，因此無法通過URL查看提交的內容，因此比較安全。

GET方法會將表單數據作為URL的一部分發送到伺服器端。這通常用於查詢資料，例如搜索關鍵字。由於數據在URL中發送，因此可以輕鬆地通過查看URL來查看提交的內容，因此較不安全。
```
##### - placeholder是輸入框內的提示文字
##### - 當表單被提交時，所有擁有 name 屬性的表單元素都會被發送到伺服器，並且 name 屬性值會用作伺服器端處理表單資料的索引鍵或名稱。

#### 圖片
```typescript!
<img style="width: 顯示的比例vw" src="圖片位址" alt="找不到圖片的時候要顯示的文字">
```
<img  alt="找不到圖片的時候要顯示的文字">
<p>
    
</p>
<img style="width: 40vw" src="https://images.unsplash.com/photo-1589652717521-10c0d092dea9?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=870&q=80" alt="img error">

<br>

#### 引用 & 註解
```htmlembedded!
<!-- 引用 -->
<blockquote>要引用的話</blockquote>

<!-- 註解 -->
<abbr title="高達900度近視">重度近視</abbr>

<!-- 斜體 -->
<cite> 斜體標記的話 </cite>

<!-- 刪除線 -->
<del>要被刪的話</del>
```

<blockquote>
    正值青年的狗狗村長，因為平時工作繁忙，長期坐在桌前使用平板處理事務，導致眼睛<abbr title="高達900度近視">重度近視</abbr>，平時都得戴著眼鏡才能好好處理工作，今天也正一如往常的認真做事...
</blockquote>
<p>
    <cite>整天都看著平板，<del>也不看看我。</del></cite> By村長老婆
</p>

#### 嵌入youtube影片
<img src="https://i.imgur.com/UZPHQBY.png" style="width: 35vw">

##### - 複製嵌入程式碼

<hr>

### CSS
* [mozilla 的 CSS 入門文件](https://developer.mozilla.org/zh-TW/docs/Learn/CSS/First_steps/Getting_started)
* [CSS 速成](https://youtu.be/laEqXy9cjs0)
<!-- {%youtube laEqXy9cjs0 %} -->


#### CSS 有三種寫法：外部樣式表、內部樣式表和內聯樣式。

1. 外部樣式表 (External Style Sheet)：透過使用 <link> 標籤將 CSS 樣式表連結到 HTML 文件中，讓不同的 HTML 文件可以共享同一個樣式表。外部樣式表的優點是維護方便，只需修改樣式表一次即可，所有引用該樣式表的 HTML 文件都會套用最新的樣式。

```htmlembedded!
<head>
  <link rel="stylesheet" type="text/css" href="styles.css">
</head>
```

2. 內部樣式表 (Internal Style Sheet)：在HTML文件的head標籤中使用```<style>```標籤來定義css樣式，只對當前html生效。

```htmlembedded!
<head>
  <style type="text/css">
    h1 {
      color: red;
    }
    p {
      font-size: 16px;
    }
  </style>
</head>
```
3. 內聯樣式 (Inline Style)：在 HTML 標籤中使用 style 屬性定義 CSS 樣式，只對當前標籤生效。內聯樣式的優點是方便快捷，但不推薦大量使用，會降低代碼的可讀性和維護性。

```htmlembedded!
<h4 style="color: royalblue;">Hello World</h4>
```
<h4 style="color: royalblue;">Hello World</h4>

#### CSS 選擇器介紹

在 CSS 中，有幾種選擇器可以用來選取網頁上的元素
1. class 選擇器：

    class 選擇器可以選取網頁上所有使用該 class 的元素。在 CSS 中，class 選擇器以句點（.）開頭，然後加上 class 名稱。例如，以下是一個 class 選擇器：
    ```css
    .my-class {
      color: red;
    }
    ```
    在 HTML 中，可以使用 class 屬性將該 class 應用到一個或多個元素：
    ```html
    <p class="my-class">This text will be red.</p>
    ```
2. id 選擇器：

    id 選擇器可以選取網頁上擁有特定 id 屬性的元素。在 CSS 中，id 選擇器以井字號（#）開頭，然後加上 id 名稱。例如，以下是一個 id 選擇器：
    ```css
    #my-id {
      background-color: yellow;
    }
    ```
    在 HTML 中，可以使用 id 屬性將該 id 應用到一個元素：
    ```html!
    <div id="my-id">This div will have a yellow background.</div>
    ```
3. 屬性選擇器：

    屬性選擇器可以選取擁有特定屬性的元素。在 CSS 中，屬性選擇器以方括號（[]）包括屬性名稱，例如：
    ```css
    input[type="text"] {
      border: 1px solid black;
    }
    ```
    上述選擇器會選取所有 type 屬性為 "text" 的 input 元素，並將它們的邊框設定為 1 像素寬的黑色線條。






#### VS Code小插播
<div style="background-color: antiquewhite;">
<h4>● 要開一個類別為article的div，可打.article後生成</h6>
<img src="https://i.imgur.com/oRYzhCh.png">
<br><br>
<img src="https://i.imgur.com/7nZwZ57.png">
<br><br>
<h4>● 在VS Code裡要指定css的來源，可打link後選link.css</h4>
<img src="https://i.imgur.com/FDkyEjC.png">
<h4>● 要新增指定數量個列表</h4>
    
![](https://i.imgur.com/ET5ewFN.png)

![](https://i.imgur.com/QrOiI8I.png)

    
</div>

#### margin & padding
<img src="https://miro.medium.com/freeze/fit/c/80/56/1*L5bN2lty8lg5F50PTo4jtw.gif"> 

<br>

margin指的是元素與其他元素之間的空間，是外邊距。我們可以使用以下的屬性值對margin進行控制：
* margin-top：設置元素上方的外邊距
* margin-right：設置元素右邊的外邊距
* margin-bottom：設置元素下方的外邊距
* margin-left：設置元素左邊的外邊距
* margin：一次性設置所有邊的外邊距，按照順序分別為上、右、下、左  

padding指的是元素內部和邊框之間的空間，是內邊距。我們可以使用以下的屬性值對padding進行控制：
* padding-top、padding-right、padding-bottom、padding-left分別設置素上右下左的內邊距
* padding：一次性設置所有邊的內邊距，按照順序分別為上、右、下、左
```css!
<h5 style="padding: 5px 5px 5px 300px">
    padding setting1
</h5>
```
<h5 style="padding: 5px 5px 5px 300px">
    padding setting1
</h5>

```typescript!
/* 上下邊距 左右邊距 */
<h5 style="padding: 5px 10px">
    padding setting2
</h5>

/* 上邊距 左右邊距 下邊距 */
<h5 style="padding: 5px 10px 10px">
    padding setting3
</h5>
```
![](https://i.imgur.com/HFpipxt.png)

```css!
.box{
  border-top: firebrick dotted;
  border-bottom: royalblue double;
  border-left: gold dashed;
  border-right: silver solid;
  padding: 15px;
  border-width: 5px;
  margin: 25px;
  border-radius: 40px;
}

```

#### color
* 字詞：royalblue、gold、silver、darkgreen、springgreen
<span style="color: royalblue">royalblue、</span>
<span style="color: gold">gold、</span>
<span style="color: silver">silver、</span>
<span style="color: darkred">darkred、</span>
<span style="color: springgreen">springgreen</span>

* 十六進位制：#B15BFF
<h5 style="color: #B15BFF">#B15BFF</h5>

* rgb
<h5 style="color: rgb(10,100,255)"> rgb(10,100,255) </h5>

* rgba
<h5 style="color: rgba(10,100,255,0.5)"> rgba(10,100,255,0.5) </h5>

#### font-family
* 標楷體(DFKai-sb)、微軟正黑體(Microsoft JhengHei)、monospace font、Times New Romance

<span style="font-family:DFKai-sb;">標楷體、</span>
<span style="font-family:Microsoft JhengHei;">微軟正黑體、</span>
<span style="font-family:monospace;">monospace font、</span>
<span style="font-family:TimesNewRomance;">Times New Romance</span>

* serif(有襯線)、sans-serif(無襯線)

<img src="https://i.imgur.com/11MRVVV.png" style="width: 20vw"> 

<br>

* font-style、text-decoration、text-transform、letter-spacing、word-spacing

```css!
.box h1{
  font-family: serif;
  font-style: italic; /* 斜體 */
  text-decoration: underline;
  text-transform: uppercase;
  letter-spacing: 0.5em;/* 字間距 */
  word-spacing: 0.5em;/* 詞間距 */
}
```
![](https://i.imgur.com/5rL8Pmv.png)

* 字行高
```css!
body{
  background-color: #f4f4f4;
  color: #555555;
  line-height: 1.5em; /* 字行高 */
}
```
![](https://i.imgur.com/RHokoLB.png)

* 更換list圖示
* list-style: circle(square、none、lower-alpha...);
```css!
.list{
  list-style-image: url(https://i.imgur.com/TIK5BH9.png);
}
```
![](https://i.imgur.com/Xe2C5TA.png)  
(圖片大小0.3*0.3)

* list 選擇器
```css!
.li2 li:nth-child(odd){
  color: gold;
  /*  陰影 往右 往下 寬度(越寬顏色會越淡)  */
  text-shadow: 2px 2px 2px black;
  font-weight: bold;
}

.li2 li:nth-child(2){
  color: red;
  font-weight: bold;
}
```
![](https://i.imgur.com/4cxJoY0.png)


* 按鈕

```css!
button {
    padding: 10px;
    border-width: 0px;
    border-radius: 5px;
    margin: 15px;
    font-size: 16px;
    color: #fff;
    background-color: royalblue;
    cursor: pointer;
}

button:hover{
  background-color: darkblue;
}

button:active{
  background-color: lightblue;
}
```
![](https://i.imgur.com/OspCluN.png)

* 超鏈結
```css!
a{
  /*  底線設為無  */ 
  text-decoration: none;
  color: brown;
  font-weight: bold;
}

a:hover{
  color: gray;
}

a:visited{
  /* 網址被訪問後  */
  color: gold;
}

```
![](https://i.imgur.com/5HWUhfs.png)
![](https://i.imgur.com/FXQ0uvI.png)

* 浮動box(平分)
```css!
.box{
  float: left;
  width: 30%;
  box-sizing: border-box;
}
```
![](https://i.imgur.com/Dh0Vmfu.png)

* 浮動box(主副)

![](https://i.imgur.com/HLywVrO.png)

* 清除浮動
```htmlembedded!
<div class="clfix"></div>
```
```css!
.clfix{
  clear: both;
}
```

* position(absolute、relative) ---- 在父關係的position沒有設定為relative時，子關係若設定 position: absolute，其固定關係會跟著整個頁面改變
```css!
.box2{
  width: 200px;
  height: 200px;
  border: gold 3px solid;
  margin: 10px;
  padding: 10px;
  position: relative;
}

.box2 h1{
  position: absolute;
  top: 80px;
}

.box2 h2{
  position: absolute;
  right: 30px;
}
```
<img src="https://i.imgur.com/5RjKvFs.png" style="width: 20vw">

* position(fixed) ---- 固定在頁面的某個位置
```css!
#fixed{
  position: fixed;
  bottom: 0;
  right: 0;
}
```
![](https://i.imgur.com/L60Swxp.png)

![](https://i.imgur.com/e3mP347.png)

  


<hr>

## 3. 網頁部署

### ★ [Flask 網站應用程式](https://ithelp.ithome.com.tw/articles/10296051)
* Flask 是一個輕量級的 Python 網頁應用程式框架，可以用來建立快速、靈活、可擴展且具有可重用性的網頁應用程式。Flask 支援 Python 2.7 和 3.5 以上的版本，並提供了諸如路由、模板渲染、表單處理、資料庫存取等功能，同時具有良好的擴展性，可以與各種 Python 的擴展庫（如 SQLAlchemy、WTForms 等）無縫整合。

#### 開始Flask網站部署實作

```python
from flask import Flask, render_template
```
##### - 引入 Flask 和 render_template 這兩個模組。Flask 是 Python 的一個網頁框架，render_template 則是用來載入 HTML 模板。
```python
app = Flask(__name__)
app.static_folder = 'static'
```
##### - 建立了一個 Flask 應用程式物件，並設定了靜態資料夾為 static，裡面可存放css和javascript檔案。
```python
@app.route('/')

def web():
    return render_template("directory.html")
```
##### - 使用 app.route() 裝飾器建立了一個路由，也就是當使用者訪問網站首頁時會執行的函式。這個函式使用了 render_template 函式來載入名為 directory.html 的 HTML 模板。

```python
if __name__ == "__main__":
    app.run(debug=True, host='127.0.0.1', port=5002)
```

##### - 最後使用了 if name == "main": 來確保這個應用程式只有在直接執行時才會啟動。也設定了 debug=True，這表示啟用除錯模式，修改檔案時網頁也會同步更新。最後，我們指定了應用程式監聽的主機和埠號。在本例中，應用程式會在本機的 127.0.0.1:5002 執行。

```python
from flask import Flask, render_template

app = Flask(__name__)
app.static_folder = 'static'
@app.route('/')

def web():
    return render_template("directory.html")

if __name__ == "__main__":
    app.run(debug=True, host='127.0.0.1', port=5002)
```
##### - 完整程式碼


![](https://i.imgur.com/hNMt4Zg.png)

##### - 成功部署在內建的伺服器上，且可正常執行

```
.
├── web.py
├── templates
│   └── directory.html
└── static
    ├── directory.css
    └── directory.js

```
##### - 補充:檔案存放架構

###  ★ [netlify 靜態網頁部署](https://www.youtube.com/watch?v=AD__uCioJjY)
* Netlify 是一個現代化的網頁應用程式部署平台，可以幫助使用者輕鬆地將網頁應用程式部署到全球 CDN（Content Delivery Network）上，以提高應用程式的可用性和可靠性。Netlify 除了提供基本的應用程式部署和域名管理外，還提供了許多功能，如 HTTPS 支援、自動構建、Git 集成、CD/CI 流程等，使開發人員可以專注於應用程式開發，而不用擔心部署和基礎架構的問題。
#### 開始Flask網站部署實作
![](https://i.imgur.com/Uy5fLzU.png)
##### - 在VS Code開啟html檔所在的資料夾，在終端機輸入git init
![](https://i.imgur.com/uu0NBJm.jpg)
##### - 在原始檔控制提交git init
![](https://i.imgur.com/DE34wCp.png)
##### - 在github建新的repo
![](https://i.imgur.com/qVxgSk8.jpg)
![](https://i.imgur.com/e0iNbEJ.png)
##### - 把檔案上傳到github
![](https://i.imgur.com/cXwly3q.jpg)
##### - 到netlify新增網站
![](https://i.imgur.com/96S59e5.jpg)
##### - 從github引入
![](https://i.imgur.com/l6lEW4N.png)
##### - 選擇檔案在的repo
![](https://i.imgur.com/CsvfYYe.jpg)
##### - Deploy site
![](https://i.imgur.com/BmYdgEY.png)
##### - [成功部署網站](https://eclectic-banoffee-be8e2c.netlify.app/)



