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

### HTML

### CSS
