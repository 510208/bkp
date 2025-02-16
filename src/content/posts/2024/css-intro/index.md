---
title: "一小時快速入門！用人話解釋的CSS基礎知識"
published: 2024-12-08
category: 程式語言手札
tags: 
  - "css"
  - "wp"
  - "入門"
image: "/images/css-intro/samhacker_css-intro_cover.png"
---

一個標準的網頁是由HTML、CSS與Javascript寫出來的（我會簡稱它為HCJ），HTML定義一個網頁的內容，CSS讓它變得更美觀。此時的網頁仍然沒有辦法與使用者互動（當然，CSS有一些基本的），如果想要讓網站跟訪客更為親近、更有互動性，那就必須要動用到JavaScript了。今天這篇文章默認你已經使用了WordPress架設網站，只會講一些基礎的CSS知識、然後帶你開始修改自己的主題。看完這篇 CSS入門 文章多加練習，相信你也可以讓網站更加獨一無二！

## CSS？那是什麼，可以吃嗎？

首先我們要先來了解一個網站的結構。按下你的F12，如果你沒動過會看到一個名為元素（Elements）的面板，在這裡面會有一大堆由尖括號（a.k.a. 大於小於符號）包夾起來的一堆文字。這就是HTML，古羅馬掌管網頁內容的神

<figure>

[![](/images/css-intro/samhacker_css-intro_1.jpg)](http://samhacker-local.local/wp-content/uploads/2024/12/samhacker_css-intro_1.jpg)

<figcaption>

網際網路三劍客

</figcaption>

</figure>

你可以把HTML想像成一間未裝潢的毛胚屋，基本上不能住人，當然你要住進去也沒人管的著你。為了讓你家比較好一點，就必須要刷上油漆、接水電、裝潢內部來讓你的家更好住。而如果你還希望住得便利，JS智慧家具就是不可或缺的必需品

今天文章要用的程式語言就是所謂的CSS，古羅馬掌管網站內容的神。CSS，全稱Cascading Style Sheets，中文可以翻譯成「層疊樣式表」或是「階層樣式表」。會叫做"層疊"是因為他的語法結構就是一層一層的，由上疊到下。叫樣式表的原因則是因為CSS指定元素的樣子

你可以想像一下HTML、CSS和JavaScript在看網頁時跟瀏覽器的對話：HTML會先告訴瀏覽器「欸欸幫我畫一個標題在上面，內容...」，而CSS會在HTML說完後補充一句「啊，所有的標題都要用等寬字體喔！」，JavaScript則是在最後告訴瀏覽器：「如果有人點了這個標題，就幫我跳個訊息（使用`alert`）」，如下圖：

[![](/images/css-intro/samhacker_css-intro_3.jpg)](http://samhacker-local.local/wp-content/uploads/2024/12/samhacker_css-intro_3.jpg)

> 如果HTML為你裝上了一扇門，那麼CSS就讓它像個藝術品。如果CSS讓一扇門像個藝術品，那麼JavaScript就讓它變成一扇能開的門。
> 
> 如果沒有HTML，你見不到那一扇門；如果沒了CSS，它就只是一塊木板；如果連JavaScript都不復存在，那這扇門連開都不能開
> 
> SamHacker

前面說了假設你用WP，那你就已經有一棟毛胚屋了。JS的部分有外掛可以幫助你，所以其實也不會需要自己寫。但網站版型的部分別人做好得你不一定會喜歡，這種時候就只好自己刷油漆囉~~

## CSS的基本架構

一段CSS由三個部分組成：

[![](/images/css-intro/samhacker_css-intro_2.jpg)](http://samhacker-local.local/wp-content/uploads/2024/12/samhacker_css-intro_2.jpg)

你可以想像CSS是在形容一個人。形容一個人，首先最重要的當然就是要知道你要形容誰，也就是Selector，翻譯成CSS的概念就是被修改的元素（元素嘛...像標題、段落、圖片、容器等都可以是一個元素）

再來你要形容他的甚麼，例如形容他的身高（height）、寬度（就是腰圍啦...width，禮貌一點），這叫屬性名稱。一樣翻譯一下， 字型（Font Family）、內外距（Padding、Margin）都是屬性名稱（Property Syntax）

最後就是到底身高多少，腰圍幾公分，也就是屬性值（Property Inherits、或者說Property Value）。翻譯蒟蒻吃完後就知道了，像上面的sans-serif（無襯線體）、10px（大小10像素）

換成CSS的術語：選擇器用來指定被修改的元素（不一定只能改一個，在下面群組選擇器會教）、一個屬性名稱與屬性值合稱一個「宣告（Declaration）」，在上圖中有兩個宣告分別為字體（`font-family: sans-serif;`）與字型大小（`font-size: 10px;`）

## 選擇器（Selector）：指定被開刀的元素

想要說明一個人的樣子，首先當然是要知道你在說誰。在CSS中你不只可以指定單一一個人、還可以指定一群人、或是所有人等等

常用的CSS選擇器分三種：類選擇器（Type Selector）、類型選擇器（Class Selector）與ID選擇器（ID Selector）

如果你想多學一點更好用的選擇器，建議你可以參考這篇文章：[30個你必須記住的CSS選擇器 | Envato Tuts +](https://webdesign.tutsplus.com/zh-hant/the-30-css-selectors-you-must-memorize--net-16048t)

### 通用選擇器：小孩才做選擇，我全都要

小孩才做選擇，我全都要！如果你要選擇整個網頁的所有元素，使用通用選擇器就好。通用選擇器的用途就是選擇整個網站所有的元素，在寫HTML的時候常常會用來清空瀏覽器的預設設定，這個我就不特別做Demo了，大家可以自己回家網路找個Hello World慢慢玩，或是拿下面的Demo下去改~~

通用選擇器的語法很簡單，使用星號就好（`*`），像以下的CSS是清除所有元素的內外距（`padding`、`margin`都歸零）：

```
* {
  padding: 0;
  margin: 0;
}
```

### 類選擇器：一群人，但至少還有說是一群誰

標題、內文、容器、圖片...每一個標題長的都是那副模樣、每個內文也是那個味道、每個容器也都是用`div`定義，如果你想把整個網站所有同類型的物件通通選起來，那用類選擇器就對了。

打個比方，類選擇器就像「我要形容所有女生」、「我要形容全部"國中生"」這樣的形容方式。這種形容方式**比較廣泛、籠統，但好處就是可以一次全選同樣類型的東西**，當然也可以跟後面提到的類型和ID選擇器連用，只選擇有某種Class的內文元件之類的，就像是「我要形容所有國二生」跟「我要形容明欣國中的所有二年級生」的差別一樣。一言以蔽之，類選擇器的用途是選擇所有同樣Tag的

以下是一個使用類選擇器選擇「所有的"圖片"（`<img>`標籤）」，然後設定邊框圓角半徑10px（border-radius: 10px）的方式：

```
img {
    border-radius: 10px;
}
```

很明顯的，類選擇器的用法很簡單：直接把你要選擇的標籤名稱給打上去當選擇器就好。如果要一次改許多不同的類，可以用半形逗號（`,`）隔開，像以下CSS會選擇「所有的"圖片"（`<img>`標籤）、"容器"（`<div>`標籤）」，設定內容跟上面一樣，圓角10px：

```
img, div {                   /* 選擇 img 與 div 標籤 */
    border-radius: 10px;
}
```

### 類型選擇器：一群類似的人

如果你只想某幾個標題、某幾個內文，很明顯的類選擇器太廣泛了，根本不好用。這種時候我們可以使用"類型選擇器"來取代類選擇器

類選擇器跟類型選擇器中文看起來很像，因此來看看英文版。類選擇器（Type Selector）與類型選擇器（Class Selector）很明顯的可以看出是兩個東西，看來遠古人類三千年智慧反而讓他更難懂

類選擇器會選擇所有同樣標籤的元素，而類型選擇器選擇的是具有同樣"類別（Class）"的元素。這樣好了，我做一個DEMO給大家看：

<iframe id="cp_embed_NPKNjpM" src="//codepen.io/anon/embed/preview/NPKNjpM?height=450&amp;theme-id=1&amp;slug-hash=NPKNjpM&amp;default-tab=css,result&amp;editable=true" height="450" scrolling="no" frameborder="0" allowfullscreen allowpaymentrequest name="CodePen Embed NPKNjpM" title="CodePen Embed NPKNjpM" class="cp_embed_iframe" style="width:100%;overflow:hidden">CodePen Embed Fallback</iframe>

以上是一個簡單的範例，你可以知道幾件事：

- 沒有加Class時，會套用類選擇器`div`的內容

- 只有Class A，當然就會套用Class A（`.A`）選擇器的設定。Class A選擇器沒有說到的，就往上找類選擇器`div`

- 只有Class B，跟上面一樣，套用Class B（`.B`）的設定。沒提及的就上去找`div`選擇器

- 同時有Class A和Class B的話就從下往上找。我的範例中`.B`在`.A`的下面，所以先找`.B`，`.B`沒提及再找`.A`，兩者都沒提到就上去最上面找`div`。你可以自己在上面改改看我寫好的CSS，看看把`.A`搬到下面會發生啥事？

- 所有擁有Class的項目都會被設定，不會只選第一個或只選第幾個

Class 重點整理

- 類別選擇器（Class Selector）會**選擇所有擁有同樣Class的元素，不會偏心**，所有擁有這個Class的元素都會被套用設定
    - 例如：`.A`會套用到所有`class="A"`的元素

- 如果只有一個Class，**會直接套用該Class的設定**。沒提到的樣式，**會往上找標籤選擇器（例如div）的設定來補**

- 同時擁有多個Class時，會**按照CSS檔案裡的順序從下往上**找設定
    - 例如：`.B`在`.A`的下面，則先看.B的設定，沒提到的才找.A

- **Class的設定不會互相影響**，每個Class的設定只會影響有使用它的元素

- 標籤的**基礎設定（例如div）永遠是最基本的**，如果Class沒有設定某些樣式，就會套用這些標籤的基礎設定

### ID選擇器：你的名字，非你莫屬

Class選擇器還是會選擇好幾個，如果你只想選一個，有兩條路可以走：要嘛就定義一個Class只用一次，但這樣會讓你的Code很髒。所以我們會選另一種方式－**使用ID選擇器**

先說什麼是ID，你可以把它想像成"元素的名字"，例如我想介紹一個朋友的樣子，比起「九年二班那個有長黑髮個性很陰森的同學」，直接說「九年二班的林晴恩」肯定比較快（至於為什麼是這個名字，我就拿我之前寫的小說來客串，雖然那篇好像爛尾了...）

前面「九年二班那個有長黑髮個性很陰森的同學」就像定義一堆Class，直接定義ID的「九年二班的林晴恩」比起定義一堆Class，當然更加方便！

ID不可重複

雖然HCJ的容錯性很高，HTML不小心定義兩個一樣的ID也不會扔Error不讓你看，但這樣會顯得你的技術很爛。俗話說的好，笨蛋不說話沒人知道他是笨蛋（好兇），所以**小心別把ID重複了，即使這樣瀏覽器還是會跑給你看**！

你可以[看看這篇文章](https://popeye-ux.medium.com/html%E4%B8%AD%E7%9A%84id%E9%87%8D%E8%A4%87%E6%9C%83%E6%80%8E%E6%A8%A3-85778e4da8c3)，有詳細解釋ID重複發生啥事。一言以蔽之就是沒事，地球不會毀滅

以下一樣寫一個Demo給你們看：

<iframe id="cp_embed_emOZWQY" src="//codepen.io/anon/embed/preview/emOZWQY?height=450&amp;theme-id=1&amp;slug-hash=emOZWQY&amp;default-tab=css,result&amp;editable=true" height="450" scrolling="no" frameborder="0" allowfullscreen allowpaymentrequest name="CodePen Embed emOZWQY" title="CodePen Embed emOZWQY" class="cp_embed_iframe" style="width:100%;overflow:hidden">CodePen Embed Fallback</iframe>

從以上範例中，你可以知道這些事：

- 如果不小心重複ID，它看起來就像套了Class一樣，不會只套用第一個，還是會通通套用。但記得，真的不好，不要模仿

- 只有一個ID（如`#A`）時，會直接套用該ID選擇器的設定（`#A`）。ID選擇器的等級（在CSS中我們稱之為權重）比類選擇器高，所以不會繼承到類選擇器的設定，除非該屬性未在ID選擇器中設定

- 如果有多個選擇器（如類選擇器與ID選擇器）同時作用：
    - ID選擇器的權重（你可以想像成等級）最高，所以會優先套用ID的設定
    
    - 如果該屬性未在ID選擇器中明確設定，則會往上去翻類選擇器（如`.A`或`div`）的相關設定

- ID選擇器具有唯一性，一個HTML文檔中應該只有一個元素能使用某個特定ID，所以ID選擇器不會像類選擇器那樣套用到多個元素

- 一個元素只能用一個ID，因為ID的意思是「身份證號」，**一個HTML文件裡不可以有重複的ID，否則瀏覽器會不知道聽哪一個**

ID 重點整理

- **ID選擇器（ID Selector）專門針對特定元素**，每個ID只能用在一個元素上，就像身份證號一樣，**唯一且專屬**

- ID的設定會優先，如果同時有ID和其他設定（例如Class），會**優先套用ID的設定**

- **沒有ID設定時，才會往下翻，依照Class或標籤的設定來補充**

- 每個元素**只能有一個ID，不能有兩個或以上的ID**，因為HTML會不知道該用哪個ID的樣式

- ID的等級比較高，就算CSS裡有很多Class或標籤設定，**只要有ID，它的設定一定優先**

* * *

### 群組選擇器（Group Selector）：手心手背都是肉~

群組選擇器，用前面形容人的方式形容就是：「林晴恩、林韻恩跟夏庭祐都...」，一次把所有符合條件的全部選起來。HTML有六個標題等級（`h1`、`h2`、`h3`、`h4`、`h5`、`h6`），在初始化他們的字體時就常常用到群組選擇器

> 一言以蔽之：選取所有符合條件的元素

群組選擇器的用法是用半形逗號隔開所有的項目。因為它不難，就不特別做Demo了（而且我的CodePen也沒太多地方）

以下是一個範例CSS，大家可以自己放進瀏覽器玩玩看：

```
h1, h2, h3, h4, h5, h6 {
    color: red;             /* 把h1到h6的標題都變繩紅色 */
}
```

### 子選擇器與後代選擇器：株連九族滿門抄斬

子選擇器（Child Combinator）與後代選擇器（Descendant Combinator）都是用來選取"子代元素"的

國中生物課本有教過，親代生下的叫做子代，子代生下的叫第二子代（當然，俗稱孫子）。在CSS中也有這種玩法，假設有一個長這樣的HTML（建議你要稍微會讀HTML，希望啦）：

```
<html>

<body>
    <div>      <!-- 這是父元素 -->
        <p>第一層的直接子元素</p>
        <div>
            <p>第二層的後代元素</p>
        </div>
    </div>
</body>

</html>
```

如上，以上這個HTML中，直接子元素在家庭中就是緊挨著父元素的孩子，也就是父元素的第一層子元素。在這個範例中我已經寫出來了，就是第五行的`<p>第一層的直接子元素</p>`

而後代元素就是像孫子、孫女（你愛誰是女的就誰是女的，我是隨便啦），也就是屬於父元素內部的所有元素，**無論它們在第幾層**。在這個範例中，第五行`<p>第一層的直接子元素</p>`和第七行的`<p>第二層的後代元素</p>`

它的解釋比較複雜，建議可以去看看這篇文章：[CSS 選擇器 (2) 複合選擇器 — 後代選擇器及兄弟選擇器](https://ithelp.ithome.com.tw/articles/10312302)

### 屬性相關選擇器

如果不想每個項目都手動加上Class，或是有特殊需要，可以選擇使用"屬性相關選擇器"，功能是「選取所有有指定屬性的元素」。每個HTML元素都有自己的屬性，例如前面提到的ID、Class，甚至可以做到「導航到SamHacker Blog的所有URL連結」，用法因為比較複雜，就請GPT大大列成一份清單給大家看看：

#### \[屬性存在選擇器\]

選擇具有特定屬性的元素。

```
[type] {
  border: 1px solid black;
}
```

#### \[屬性值選擇器\]

選擇屬性等於特定值的元素。

```
[type="text"] {
  background-color: lightgray;
}
```

例如想做出前面提到的「導航到SamHacker Blog的所有URL連結」，可以寫成這樣：

```
[href="http://samhacker-local.local"] {
  /* ... */
}
```

其他的就等你有興趣再探索吧😁

### 偽類選擇器：全都是假的啦

CSS 的偽類就像是給元素加上一些「特殊的狀態標籤」，這些標籤能根據元素的不同狀態或條件來改變樣式，讓你的網站更靈活和互動。

偽類（Pseudo）

偽類（Pseudo）是加在選擇器後面的一個**冒號加條件**（例如 :hover），用來定義某些特殊情況下的樣式。而偽類選擇器則是用來修改這些偽類的工具

來看看一個Demo，你會更容易理解：

<iframe id="cp_embed_ZYzWyeW" src="//codepen.io/anon/embed/preview/ZYzWyeW?height=450&amp;theme-id=1&amp;slug-hash=ZYzWyeW&amp;default-tab=css,result&amp;editable=true" height="450" scrolling="no" frameborder="0" allowfullscreen allowpaymentrequest name="CodePen Embed ZYzWyeW" title="CodePen Embed ZYzWyeW" class="cp_embed_iframe" style="width:100%;overflow:hidden">CodePen Embed Fallback</iframe>

其實偽類的部分也很複雜，我們就邊做邊學吧~

上面這段HTML用到了以下幾個偽類：

- `:active`：滑鼠按下的樣式

- `:focus`：鍵盤聚焦的樣式

- `:hover`：滑鼠滑過的樣式

- `:link`：（連結）還沒被訪問的樣式

- `:visited`：（連結）被訪問過的樣式

簡單來說，這個Demo的意思是：

> 游標移上元素，顏色就變成黃色；  
> 左鍵按下去、輸入框被點擊，顏色變紅色；  
> 連結被看過，顏色就變藍色了！

## 宣告（Declaration）：元素的形容詞

剛才寫太多選擇器的東西了，一直在想辦法叫到一個人。現在總算可以開始形容他了。首先還是剛剛那張圖：

[![](/images/css-intro/samhacker_css-intro_2.jpg)](http://samhacker-local.local/wp-content/uploads/2024/12/samhacker_css-intro_2.jpg)

前面一直在選擇器的地方晃來晃去，現在要解釋的是裡面的屬性名稱與屬性值，那你又要問了：「啊不是說宣告？」，簡單來講，**屬性名稱+屬性值=宣告**

CSS的宣告是由屬性值與屬性名稱組合成的，以上圖的CSS程式碼為例，他有兩個宣告：`font-family: sans-serif;`與`font-size: 10px;`。你會看到每個宣告的格式都是一段英文字串加半形冒號後面再加一段東西最後加個分號。這就是CSS的宣告規則：**前面的英文字串叫屬性名稱，用途是告訴瀏覽器你要改什麼；後面是屬性值，告訴瀏覽器你要改成怎樣**

以上面的CSS第一行的`font-family`宣告為例，這段話翻譯成人話的話，可以說成「把字體（`font-family`）改成無襯線字體（`sans-serif`）。」

前面的屬性名稱你要背，通常是由一個或兩個單字（三個以上幾乎沒有，可以忽略）組成，而通常兩個單字組成的屬性名稱如上面的`font-family`和`font-size`，中間不能用空白隔開，而是使用減號連接兩個單字。而這種兩個字組成的複合屬性名稱通常慧根前面的單字有關係，例如font-family跟font-size兩個可以喇作伙用簡寫屬性font取代

簡寫屬性

**簡寫屬性**（Shorthand properties，又譯為特性簡寫）是**可以讓你同時設置好幾個 CSS 屬性值的 CSS 屬性**。使用簡寫屬性，開發人員可以編寫更簡潔、更具可讀性的樣式表，節省時間和精力。例如上面的字體設定可以使用簡寫屬性縮短成`font: 10px sans-serif;`，這種方便的寫法又被稱為**語法糖（Syntactic sugar）**

因此我們可以把CSS架構寫成一個公式：

> 屬性名稱+冒號（`:`）+屬性值+分號（;）

為什麼要加分號？

CSS的分號就像我們講完一句話要加個句點。（對，要加句點）

這個分號用來隔開兩個宣告。在多行的CSS中他可能沒有太大的用途，甚至會讓人覺得麻煩（跟某C語言一樣），但因為HCJ（HTML、CSS和JS，怕你忘記）都有「壓縮成一行並省略註解來減少檔案體積換取加快訪問」這一招，在壓縮起來後全部變一行就必須要有辦法知道一個宣告哪裡開始哪裡結尾，所以就會有分號的出現。

所以下次看到分號不要在厭煩了，沒有這個分號，你上網的下載速度可能要再多好幾秒...

既然已經知道怎麼寫宣告了，那我們就開始學習常用的屬性吧！

### 字體（font）

這個屬性可以用來指定字體的相關設定，以下是他的語法：

```
font: [font-style] [font-variant] [font-weight] <font-size> [line-height] <font-family>;
```

在上面我們可以看到，font屬性是好幾個屬性的合體。以下來解釋一下他們的意思：

#### font-style

font-style是用來設定斜體的。你可以使用`italic`（草書，書寫體）或`oblique`（只是斜體），一般我會習慣用草書的`italic`，反正大部分中文字體（甚至很多英文字體）並沒有為兩種字體分別做不同樣式，所以都用italic就好。補充一句，要清除font-style用`unset`，不想斜也不想草用`normal`

unset與normal

unset與normal看起來很像，但其實差的可不小！unset代表的是預設，也就是「我不想管，你去上面翻」，而normal代表的是「我要管喔！不管之前有沒有設定斜體，通通給我變為正常的字體」

我們可以看看一個例子：這個例子中我用通用選擇器把預設的font-style變成斜體，來看看使用normal和使用unset的差別（不得不說，CodePen好方便）

<iframe id="cp_embed_KwPzQwR" src="//codepen.io/anon/embed/preview/KwPzQwR?height=450&amp;theme-id=1&amp;slug-hash=KwPzQwR&amp;default-tab=css,result&amp;editable=true" height="450" scrolling="no" frameborder="0" allowfullscreen allowpaymentrequest name="CodePen Embed KwPzQwR" title="CodePen Embed KwPzQwR" class="cp_embed_iframe" style="width:100%;overflow:hidden">CodePen Embed Fallback</iframe>

簡而言之，normal就像穿回一件「正常的衣服」，專門設計好這件屬性該怎麼「正常表現」。unset則會變成直接脫掉這件衣服，看上下文決定是穿父母的衣服（繼承），還是穿系統預備的預設衣服（初始值）

最後整理個比較表，來看看他們的意義所在：

| 特性 | normal | unset |
| --- | --- | --- |
| 定義 | 設為該屬性的標準值 | 移除屬性定義，繼承或回到瀏覽器預設值 |
| 作用範圍 | 和屬性密切相關，具體值依賴屬性規範 | 通用，可用於所有 CSS 屬性 |
| 使用場景 | 明確將屬性設置為正常狀態 | 不確定繼承與非繼承的情況下清除定義 |

#### font-variant

這個屬性控制字體的變形，解釋起來超級爆炸複雜，而且通常不太會用到，所以如果想了解的，歡迎[前往MDN翻文件](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant)

#### font-weight

font-weight指定字體的粗細。網路字體常用的有兩種：可變字體（Variable Fonts）與固定字體（Static Fonts）。

**可變字體通常會有100~900九種不同的字體粗細**，你在[Google Fonts](https://fonts.google.com/)和[Adobe Fonts](https://fonts.adobe.com/)（個人常用Google Fonts，Adobe Fonts字體有些要錢，而且載入速度有點慢）等網站上找到的基本上都是這種字體。**優點**是字體有很多種不同的樣式，設計彈性大；但樣式多造成的**缺點**就是檔案會大，尤其中文字博大精深一個就不知道幾MB了...

<figure>

[![](/images/css-intro/samhacker_css-intro_4.png)](http://samhacker-local.local/wp-content/uploads/2024/12/samhacker_css-intro_4.png)

<figcaption>

在Google Fonts看到**Technology-Varible**就是可變字體囉

</figcaption>

</figure>

<figure>

[![](/images/css-intro/samhacker_css-intro_5.jpg)](http://samhacker-local.local/wp-content/uploads/2024/12/samhacker_css-intro_5.jpg)

<figcaption>

Adobe Fonts上沒有特別標註，但可以看字體數量來大略判斷

</figcaption>

</figure>

**固定字體就相反，一般只有normal和bold兩種樣子**，分別對應一般狀態與粗體。好處是檔案小了，但彈性自然也少

總之，如果你用的是可變字體，你就可以使用`100`~`900`的數字來當屬性值，數字越大就越粗。用的如果是固定字體，那就只有`normal`，`bold`也不一定會有...

#### line-height

這個是行高的設定。行高指定每行的高度，以下是兩個比較：左邊的行高設為2.0，右邊則是1.0

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

#### font-family

這設定了字體。你可以一次指定多個字體，例如`"Noto Sans TC", "Microsoft YaHei", sans-serif`。指定多個字體時，CSS會從最前面的字體開始查找，如果使用者電腦沒有、伺服器也沒有Load下來的話就往下找，直到找到字體為止。前面給的CSS就會先尋找思源黑體（Noto Sans TC），然後是微軟雅黑體（Microsoft YaHei），都找不到就使用sans-serif（無襯線字體）

Font Family有三個保留字：sans-serif、serif與monospace。第一個是無襯線體、第二個是襯線字體，而第三個則是等寬字體，俗稱程式碼字體。下圖是無襯線體、襯線體與等寬字體的比較：

[![](/images/css-intro/samhacker_css-intro_6.png)](http://samhacker-local.local/wp-content/uploads/2024/12/samhacker_css-intro_6.png)

### 邊框（border）、內距（padding）與外距（margin）

在 CSS 中，**內距（padding）**和**外距（margin）**就像盒子裡的緩衝空間。內距是盒子內容和邊框之間的距離，好比一個包裝盒裡的泡棉，用來保護裡面的物品。而外距是盒子和其他物品之間的距離，就像這個包裝盒和旁邊其他盒子之間的空隙。簡單來說，內距決定內容和盒子邊界的「內部距離」，而外距決定盒子和其他物件的「外部距離」。兩者搭配使用，可以輕鬆調整元素的佈局和位置。

至於邊框，你就可以想像成"包裝盒"本身的厚度，它用來隔開內距和外距。怎麼看這三個數值呢？你可以參考我之前寫的[F12 中的秘密：網頁開發者必學的除錯工具技巧](http://samhacker-local.local/2024/06/20/f12-guide/)

<figure>

[![](/images/css-intro/samhacker_css-intro_7.png)](http://samhacker-local.local/wp-content/uploads/2024/12/samhacker_css-intro_7.png)

<figcaption>

這張圖應該很好懂吧？

</figcaption>

</figure>

### 背景色彩（background-color）與背景模糊（blur）

這在網頁設計裡很重要，畢竟顏色可以給人各種不同的感覺。看到紅色會覺得很溫暖、看到綠色讓人覺得安心、藍色聯想到天空的廣袤、黃色是信心與聰明的代表色。有了顏色才讓網頁更加的美觀

在CSS中，設定背景色彩的方式很簡單：直接使用background-color就好了。但有個奇特的地方，如果你要使用的是漸層，那要設定的是背景圖（background-image）不是背景色喔！

#### 背景色彩（background-color）

背景色彩的設定要用background-color，後面可以接上一些保留字如red、lightgreen等；或接HEX色碼如#FFFFFF代表白色、#000000代表黑色；也可以使用`rgba(red, green, blue, alpha)`函式（Red：紅色、Green：綠色、Blue：藍色，前面三項都是0~255、以及Alpha：透明度，用0~1之間的小數代表）

#### 背景漸層（Gradients）

CSS的漸層是作為背景圖片來輸出的，提供以下幾種漸層樣式：

[![](/images/css-intro/samhacker_css-intro_8-2.jpg)](http://samhacker-local.local/wp-content/uploads/2024/12/samhacker_css-intro_8-2.jpg)

寫法是透過CSS的background-color後接上上圖中給的函式，例如以下這樣：

<iframe id="cp_embed_bNbpLLK" src="//codepen.io/anon/embed/preview/bNbpLLK?height=450&amp;theme-id=1&amp;slug-hash=bNbpLLK&amp;default-tab=css,result&amp;editable=true" height="450" scrolling="no" frameborder="0" allowfullscreen allowpaymentrequest name="CodePen Embed bNbpLLK" title="CodePen Embed bNbpLLK" class="cp_embed_iframe" style="width:100%;overflow:hidden">CodePen Embed Fallback</iframe>

#### 背景模糊（Blur）

如果想不到背景要放什麼，有時候背景模糊可以讓介面變得比較有質感。你可以看看我網站的頁首，就有做背景模糊效果。背景模糊不是使用background-color或background-image，而是一個新的屬性名稱：`backdrop-filter`

以下是一個範例，設定背景模糊。背景圖片我拿網站上的一張Minecraft圖片來當背景用：

<iframe id="cp_embed_QwLNQrZ" src="//codepen.io/anon/embed/preview/QwLNQrZ?height=450&amp;theme-id=1&amp;slug-hash=QwLNQrZ&amp;default-tab=css,result&amp;editable=true" height="450" scrolling="no" frameborder="0" allowfullscreen allowpaymentrequest name="CodePen Embed QwLNQrZ" title="CodePen Embed QwLNQrZ" class="cp_embed_iframe" style="width:100%;overflow:hidden">CodePen Embed Fallback</iframe>

## 變數（Variable）：你到底會怎麼變

如果你有學過程式語言，相信變數兩個字看到就會勾起內心可怕的回憶對吧？（謎之音：那一天，人們想起了被變數型別支配的恐懼）

放心，CSS的變數主要是用來存放網站主題的設定。你可以把它想像成Minecraft伺服器的配置文件、或是WP主題那些可以改的選項。也就是說基本上你不會、也沒必要考慮變數的型別

CSS的變數宣告很簡單，通常我們會讓它在根宣告，也就是選擇器`:root`下，這樣宣告的變數去哪都能用。至於`:root`和前面提到的`*`差在哪裡？簡而言之，`:root`指向的是整個`<html>`元素，所以不管誰都幹不過它，它是最大的預設；而`*`代表「`<html>`底下所有的元素」，詳情可以看[這則StackOverflow的問題](https://stackoverflow.com/questions/60680887/root-html-selector-any-differences)

不支援變數的瀏覽器

CSS的變數是比較新的功能，所以當然傳說中那位老不死的IE沒一個版本支持，不意外。詳細情形可以[看看這個頁面](https://caniuse.com/?search=css%20variables)

以下是一個宣告CSS變數與使用該變數的方式。這個變數比較像C語言標頭文件的define指令定義出的變數。它基本沒有型別的概念，就只是把變數的文字拿去替換而已。至於怎麼引用...**使用var()函數**就對了，對這個反人類的東西，用變數要用函式引用，我愛你喔...

以下是幾個CSS變數的命名規則與習慣：

- **CSS變數都須以雙連字號開頭**，另外會習慣使用[Kebab Case命名法](https://ithelp.ithome.com.tw/articles/10294637)（就是單字中間用連字號（減號）隔開）

- **CSS變數區分大小寫**，不信你把下面範例的變數改一下大小寫，會發現直接爆炸

- **變數命名有意義**，不要用什麼ABCDEFG，別人不會通靈，你也不會（變數是給人看的）

- 建議**使用分層式命名**，例如設定按鈕的顏色用`--button-color`、按鈕字體可以寫`--button-font`

<iframe id="cp_embed_EaYKLeO" src="//codepen.io/anon/embed/preview/EaYKLeO?height=450&amp;theme-id=1&amp;slug-hash=EaYKLeO&amp;default-tab=css,result&amp;editable=true" height="450" scrolling="no" frameborder="0" allowfullscreen allowpaymentrequest name="CodePen Embed EaYKLeO" title="CodePen Embed EaYKLeO" class="cp_embed_iframe" style="width:100%;overflow:hidden">CodePen Embed Fallback</iframe>

### Calc函式：一個很不科學的數學

CSS的Calc函式，常常被人調侃成沒有數學定律的數學。在數學上不可能出現三十公尺減五百公分（要把它換成同單位才能計算），但CSS的計算函式卻可以做到這種畫風清奇的事，不知道CSS作者的數學老師現在表情是如何？

打個比方，上面的範例中你會看到`calc(100vw - var(--div-width))`，這段Code會告訴瀏覽器拿100vw（vw是一個可變單位，代表使用者螢幕可以顯示網頁內容的所有部分的寬度）去減掉變數--div-width的值（這邊是100px）

CSS常用單位

以下列出一些常用的CSS長度單位，考試會考要背起來或把這網站存起來喔~~

如果需要角度（通常就用deg，很少有別的）、時間（做動畫會用）等單位的話，可以看看[這個網頁](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Building_blocks/Values_and_units)或自己去查

| 類型 | 單位 | 說明 |
| --- | --- | --- |
| **絕對單位** | `px`（Pixel，像素） | 網頁設計中最常用的單位，適合指定固定大小，**一像素代表螢幕上一個點** |
|  | `cm`（Centimeter，公分）、`mm`（Milimeter，毫米）與`in`（Inch，英吋） | 實體尺寸單位，用得比較少，但可以模擬列印效果  
1ic=96px |
|  | `pc`（派卡，Pica） | 1pc=12pt=12/72in |
|  | `pt`（Point，點） | 1pt=1/72in |
| **相對單位** | `%`（百分比） | 相對於父元素的大小，例如 `width: 50%;` 表示佔父元素寬度的一半 |
|  | `em` | 相對於父元素字體大小，常用來設計字體相關屬性或間距 |
|  | `rem` | 相對於根元素（通常是 `<html>`）的字體大小，更統一、更好管理 |
|  | `vw`（可視範圍寬，Visible Width）與`vh`（可視範圍高，Visible Height） | 視窗寬度和高度的百分比，`1vw` 等於螢幕寬度的1%，`1vh` 等於螢幕高度的1% |
|  | `ch`與`ex` | 前者是相對於字體`0`的寬度，後者是相對於`x`的 |

## 修改WordPress的主題

該怎麼修改你網站的版型呢？首先你要**先用F12工具找到目標**（可以看看這篇：[F12 中的秘密：網頁開發者必學的除錯工具技巧](http://samhacker-local.local/2024/06/20/f12-guide/)），然後**在底下的樣式面板中找到最上層的CSS**，通常它的選擇器就可以選取到這個物件

如果你用Gutenberg編輯器想修改特定元素的效果，可以**在選取該元素後在左列進階設定中"附加的CSS類別"中新增**。記得CSS類別（Class）有規定不能用空白，數字最好不要用來當開頭。為了防止跟網站原有的CSS Class衝突，建議在前面加上一個自己的代號，像我的網站就會在自訂Class開頭加上`sh-`（SamHacker的縮寫）

Elementor可以在進階裡面找到HTML ID和HTML類別，類別當然是指Class囉！一樣的概念，但Elementor的自訂類別不能用空白分開好幾個類別，所以只能加入一個類別，算是美中不足的地方（至少我網站目前的版本是這樣的）

<figure>

[![](/images/css-intro/samhacker_css-intro_9.jpg)](http://samhacker-local.local/wp-content/uploads/2024/12/samhacker_css-intro_9.jpg)

<figcaption>

外觀>自訂，從這邊走

</figcaption>

</figure>

<figure>

[![](/images/css-intro/samhacker_css-intro_10-1024x331.png)](http://samhacker-local.local/wp-content/uploads/2024/12/samhacker_css-intro_10.png)

<figcaption>

這是直接改主題CSS的方式

</figcaption>

</figure>

找到後**前往網站的"外觀">"自訂"，在底下的"附加的CSS程式碼"就可以鍵入自己的CSS了**。如果不想的話也可以在"外觀">"佈景主題檔案編輯器"選擇`style.css`（大部分主題是用這名字，有些不是那要自己判斷），就可以輸入自訂CSS了。不過個人會推薦前面的方式，比較不會搞死網站

更新主題

在更新主題後，在style.css中的修改都會被蓋掉，因此除非有特殊需要，不然就在外觀那邊改就好。如果一定要在style.css改，也要記得先建立子主題以免不小心自己肝出來的CSS消失！

## 結語

恭喜你看完了這篇文章，到結語之前就有一萬兩千多字了，我肝了兩天出來的。早知道當初不要在FB社團那邊立下「寫 CSS入門 教學」這個Flag，現在就不用在這邊回收的要死了。為了這篇文章我還特地去弄了CodePen、想了一堆比喻、還難得用粗體與螢光筆來註明重點，希望大家可以學起CSS的基礎操作

最後想給各位一句話：「_**CSS不是三天兩頭可以上手的東西，熟能生巧，建議大家可以多去練練**_」。之後可能會寫HTML入門，等我想不開吧？

感謝各位賞臉閱讀，我是寫了兩天文章快死掉的SamHacker，掰掰~~...喔對了，如果你看這篇文章沒有看到一個小時，那代表WP的閱讀時間預估是錯的...他說會讀六十七分鐘喔，沒有的話可能你不夠用功吧？如果有的話那謝謝妳這麼用功，話說再問一句：你真的成功 CSS入門 了嗎？
