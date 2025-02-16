---
title: "F12 中的秘密：網頁開發者必學的除錯工具技巧"
published: 2024-06-20
category: WordPress建站筆記
tags: 
  - "f12"
  - "wp"
  - "分析"
  - "技巧"
image: "/images/f12-guide/F12-中的秘密-網頁開發者必學的除錯工具技巧.png"
---

網站跑版不知道誰害的？想要不透過取色器就選到網站的顏色？想分析自己網站的效能？你是不是除錯除的想哭、安裝了一堆Chrome外掛來分析網站，結果不知道其實有一個內建的功能？沒錯，這就是今天主角 開發者面板 ，又稱作F12除錯面板。

對於F12，你們的想法是什麼呢？是每次按到感覺好複雜的面板、還是非常好用的操作面板，或是跟朋友炫技的時候亂改Google搜尋首頁的那個工具呢？無論你對它的想法是啥，它就是一個非常方便的除錯工具（複雜了億點點而已...）

## 什麼是開發者面板

開發者面板 ，顧名思義是一個提供開發者進行網站除錯、開發、設計、評估等用途的面板。這個面板基本上所有瀏覽器都會有，以下列出各瀏覽器的F12面板：

<figure>

[![](/images/f12-guide/image-14-946x1024.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-14.png)

<figcaption>

Internet Explorer 11的F12

</figcaption>

</figure>

<figure>

[![](/images/f12-guide/image-16.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-16.png)

<figcaption>

Google Chrome的F12

</figcaption>

</figure>

<figure>

[![](/images/f12-guide/image-15.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-15.png)

<figcaption>

Microsoft Edge的F12

</figcaption>

</figure>

<figure>

[![](/images/f12-guide/image-17.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-17.png)

<figcaption>

Mozilla Firefox的F12

</figcaption>

</figure>

以上是各大瀏覽器的F12（如果不查資料我還真不知道IE也有...）。雖然每一個看起來都不一樣，但主要的功能基本一致，因此本文就使用我常用的Edge瀏覽器作示範（部分功能會是Edge才有，若是該種功能我會註明的）

一直說F12F12，但這個面板的本名其實叫做 開發者面板 、 開發人員工具 、DevTool等（算了能用就好我不想管他們怎麼命名了），比較有趣的是IE的真的就直接叫做F12面板...無論如何因為打F12比較省事而且比較廣為人知，因此我都直接以F12稱這個面板囉！

既然稱為F12，就代表這個面板可以使用F12鍵開啟，其他還可以透過Ctrl+Shift+I、Ellipsis Vertical選單（漢堡選單）中更多工具>開發人員工具開啟它（當然最簡單還是F12開），打開你想分析的網頁再打開它，準備開始囉！

<figure>

[![](/images/f12-guide/image-18.jpg)](http://samhacker-local.local/wp-content/uploads/2024/06/image-18.jpg)

<figcaption>

從Edge選單開啟（我主題是麥塊的）

</figcaption>

</figure>

## 開發者面板 概覽

為了說明方便，我把我的F12面板置於左邊，稍加放大，各位可以視情況決定它的大小與位置，以下是除錯面板預設開啟的面板：元素面板

### 元素面板（Elements）

<figure>

[![](/images/f12-guide/image-18.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-18.png)

<figcaption>

我畫的有點亂抱歉，這是元素面板的示意圖

</figcaption>

</figure>

#### HTML原始碼區塊（HTML Source Code）

在此區塊（紅色）中會顯示建構這個網站所需的所有HTML原始碼，並進行格式化以方便使用者檢視。單按某個元素可以選定該元素，選定的元素會在其他面板中顯示詳細說明，方便使用者對該元素進行評估與編輯。

在本區塊中對HTML元素的任何改動會立刻套用到右邊顯示的網頁中，將游標Hover到任一元素上會在右邊網頁中顯示該元素的範圍與位置如下圖：

修改網頁元件內容

你在 F12 中進行的所有修改只對當前頁面有效，如果按下F5重新載入，則元件設定會還原成原本網站設定的。

其實就類似沙箱的概念，是用來測試的...

<figure>

[![](/images/f12-guide/image-19-1024x561.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-19.png)

<figcaption>

游標移到元素上會顯示這樣的框框顯示該元素的範圍、說明、CSS Selector與以px為單位的大小

</figcaption>

</figure>

#### 版型（Style）區塊

在版型面板中可以管理你選取的元素的CSS設定，如色彩、底線、排列方式、Padding、Margin等設定。並且在已計算頁籤中看到該元素的內外距、框線、色彩與版型設定等。如下圖為已計算區塊提供的資訊：

<figure>

[![](/images/f12-guide/image-20.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-20.png)

<figcaption>

版型已計算區塊

</figcaption>

</figure>

在此區塊中紅色部分為區塊計算器，這裡面顯示的是瀏覽器實際用來渲染這個元素所使用的版型設定（也就是瀏覽器自己真正用的設定）。為了詳細說明，我使用[border - CSS：层叠样式表 | MDN (mozilla.org)](https://developer.mozilla.org/zh-CN/docs/Web/CSS/border)頁面擷取頁首的容器來說明：

<figure>

[![](/images/f12-guide/image-22.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-22.png)

<figcaption>

這是量測區塊提供的資訊

</figcaption>

</figure>

如上，最外圈標記margin的橘色區塊代表元素的外距，也就是元素與其他元素之間隔的距離，圖中標記為減號代表沒有進行設定，也就是0；內圈border代表邊框粗細，只有下方有標記1（px）代表只有下方有設定底框線，而上、左與右都沒有。

padding則代表內距，也就是綠色部分，它代表元素邊框與內部元素的間隔，也是以px作單位；最後的藍色代表內部所有元素，總共有1071px寬31px高，以下是這幾個框代表的示意圖：

<figure>

[![](/images/f12-guide/image-23.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-23.png)

<figcaption>

示意圖

</figcaption>

</figure>

#### 元素路徑說明

先說清楚，我自己不知道這地方到己真名字叫什麼，這是我自己習慣的稱呼。這個區塊會提供該元素所在的位置，就像電腦檔案的路徑一樣。例如有一個元素路徑如下：`html > body > div.container1 > h1#sh-title`，我們就可以知道這個元素位在網頁中html標籤底下body > div（Class為`container1`，在Class前加上小數點可標記這串字串為Class）裡的大標題（h1，ID為sh-title，加井號標記該字串為ID）。  
如果你不太懂這個意思的話，也可以不用在意這個區塊啦ww

#### 主控台、動畫與問題

Chrome

在Chrome瀏覽器中，主控台在另外一個頁籤中，預設這裡會顯示問題或不顯示，並且Chrome瀏覽器預設狀態沒有動畫頁籤

<figure>

[![](/images/f12-guide/image-24.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-24.png)

<figcaption>

Chrome瀏覽器的主控台（Console）頁籤

</figcaption>

</figure>

在這個部分會顯示三項元素，因為預設都會放在一起，我就把它們寫在同一個章節中。這部分各個瀏覽器有不同的設定法，不像前面幾個區塊基本上都一樣，如果沒看到請自行找到對應的區塊或換成Edge瀏覽器。

在主控台中可以執行JavaScript程式碼，並檢視網頁JS程式碼輸出的內容。例如Discord網頁版會在這個部分輸出訊息提醒你不要執行任何你不熟悉的程式碼。因為惡意使用者可以執行這些指令碼來破壞你的系統，或盜用帳號等行為。

<figure>

[![](/images/f12-guide/image-25.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-25.png)

<figcaption>

Discord提供的警告

</figcaption>

</figure>

動畫頁籤會分析這個頁面執行的所有動畫，並提供該動畫的程式、選擇器與它的相關設定。如果你看到別的網頁有喜歡的動畫，可以試試看在這個頁籤中找它的原始碼來研究。我之後會說明，不過記憶中這個功能似乎只有Edge有，Chrome預設沒有的。

問題頁籤會顯示瀏覽器抓到的所有HTML、CSS與JavaScript問題、警告與錯誤，是除錯時非常重要的幫手之一：

<figure>

[![](/images/f12-guide/image-26.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-26.png)

<figcaption>

網頁的問題，大家養成習慣不要留這麼多錯誤，這是壞榜樣喔！

</figcaption>

</figure>

### 控制台面板（Console）

這個面板在Edge中稱為"主控台"，是用來執行JavaScript指令的面板。如果網頁代碼中用到了`console.log()`指令就會將訊息顯示在此面板中，並且像Windows的命令行介面一樣可以在其中執行JS程式碼。也就是實驗用的地方...如圖：

[![](/images/f12-guide/image-27.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-27.png)

最上面紅色背景那一行是程式傳出的錯誤，旁邊的藍色超連結載明錯誤發生在哪裡（此例為post-1005.css中的第一行（冒號後是錯誤行號），第二行前面有大於符號的項目是在Console中執行的程式碼，下方的`Hit your hand for SamHacker!!plz`是顯示出的內容。

<figure>

[![](/images/f12-guide/image-28.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-28.png)

<figcaption>

完整畫面

</figcaption>

</figure>

你可以在左列選擇你要的錯誤層級，預設會有除錯訊息、資訊、警告、錯誤（由小到大）四個層級可供挑選，並且可以在左列中選擇你要看哪個層級的訊息。上方由左而右可以清空主控台（禁止符號）、設定JS顯示範圍（top那個下拉選單，top代表網頁，底下可以選擴充功能）、建立即時運算式（眼睛）、設定顯示訊息範圍（輸入框）、選擇顯示哪些層級（預設層級按鈕）等功能。

AI解釋錯誤

在Google Chrome與Microsoft Edge兩款瀏覽器中， F12 工具內建有AI解釋錯誤的功能。Edge會預設開啟此功能，Chrome則是需要先到設定將語言改為英文（美國），並開啟設定>偏好設定下的"使用AI解釋錯誤"（應該在最下面）功能。

開啟此功能後，會像下圖一般在瀏覽器錯誤訊息中顯示按鈕來請AI做解釋，都不會使用自己的電腦效能而是官方伺服器跑完，所以可以不用擔心自己跑不動喔！解釋似乎只支持英文的樣子。

<figure>

[![](/images/f12-guide/image-31.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-31.png)

<figcaption>

了解此錯誤按鈕

</figcaption>

</figure>

<figure>

[![](/images/f12-guide/image-30.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-30.png)

<figcaption>

Chrome提供的解釋

</figcaption>

</figure>

<figure>

[![](/images/f12-guide/image-33.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-33.png)

<figcaption>

右邊藍色小小的按鈕就是叫AI解釋的功能

</figcaption>

</figure>

<figure>

[![](/images/f12-guide/image-32-1024x657.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-32.png)

<figcaption>

Edge對錯誤的解釋支持繁體中文喔！

</figcaption>

</figure>

### 來源（原始碼，Source）面板

在此面板中將會顯示瀏覽器從伺服器收到的所有檔案，包括圖片、影片、音訊、JavaScript指令稿、HTML檔案、CSS版型設定等資料，並採樹狀列出這些資源。在Chrome中被稱為原始碼，Edge則稱之為來源，如下圖：

<figure>

[![](/images/f12-guide/image-29.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-29.png)

<figcaption>

來源面板

</figcaption>

</figure>

自動格式化

你或許發現了，不管在來源面板中檢視的檔案是壓縮過的還是未壓縮的，在此面板中都會先進行格式化後才顯示喔！

紅框處的最上層寫著"top"，代表你訪問的網站主機。這底下會顯示該主機回傳的資料，並依照資料夾架構來顯示。橘框處是網站需要的外部資源，這是我的網站首頁，需要訪問有前面兩個（Google Fonts）、第三個Gravatar是頭像服務、DMCA是網站最底下那張DMCA保護的圖片（如下圖），以及還是Gravatar的其他資源...

<figure>

![](/images/f12-guide/dmca-badge-w250-5x1-06.png)

<figcaption>

受DMCA保護的徽章，在頁尾

</figcaption>

</figure>

### 網路（Network）面板

網路面板中會提供關於此網站向網路伺服器請求的所有檔案，並且為這些檔案繪製一張類似甘特圖的圖表以方便進行分析。在圖表中越大的檔案占的長度就越長，反之亦然。如下圖：

<figure>

[![](/images/f12-guide/image-35.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-35.png)

<figcaption>

網路面板

</figcaption>

</figure>

在最上方最常用的就是選擇要看的類別，分全部、Fetch/XHR、文件、CSS、JS、字型、影像、媒體等。CSS會列出所有網頁版型檔案，JS則是列出所有腳本（JavaScript）檔案，字型列出的檔案有`*.woff`、`*.woff2`、`*.ttf`等，可在預覽窗格中預覽字體。

在上方的選單中可以透過filter過濾你要看的東西，以下是filter可以指定的部分過濾器：

<figure>

| **過濾器** | **說明** | **範例** |
| --- | --- | --- |
| domain | 資源所在的域，即url中的域名部分 | domain:api.github.com |
| has-response-header | 資源是否存在響應頭，無論其值是什麼 | has-response-header:Access-Control-Allow-Origin |
| is | 當前時間點在執行的請求。當前可用值：`running` | is:running |
| larger-than | 顯示大於指定值大小規格的資源。  
單位是位元(B)，但是K(kB)和M(MB)也是可以的 | larger-than:150K |
| method | 使用何種HTTP請求方式 | method:GET |
| mime-type | 也寫作content-type，是資源類型的標識符 | mime-type:text/html |
| scheme | 協議規定 | scheme:HTTPS |
| set-cookie-name | 服務器設置的cookies名稱 |  |
| set-cookie-value | 服務器設置的cookies的值 |  |
| set-cookie-domain | 服務器設置的cookies的域 |  |
| status-code | HTTP響應頭的狀態碼 | status-code:200 |

<figcaption>

Filter輸入框可用的過濾器

</figcaption>



</figure>

文件則會列出瀏覽器向網站發送的請求，如圖：

<figure>

[![](/images/f12-guide/image-36.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-36.png)

<figcaption>

我比較少看回應標頭，所以把它收合起來

</figcaption>

</figure>

其中回應標頭代表網站回傳的Header；要求標頭則是瀏覽器送至網站的Header，一般會列出此請求的基本資訊，例如成功與否（狀態代碼）、動作是啥（要求方法）與主機位置（要求URL）等資訊，很完整了'v'

### 本地Lighthouse

[Lighthouse](https://developer.chrome.com/docs/lighthouse/overview?hl=zh-tw)是一款由Google開發的自動化網站測試工具，它會對網站的前端進行完整的測試，例如網站速度、SEO、無障礙友好度與PWA效能等，方便開發者可以輕鬆地知道自己的網站效能與體驗如何。而此程式Google有提供網頁版與瀏覽器內嵌版。這一章節介紹的就是瀏覽器內嵌的版本：

<figure>

[![](/images/f12-guide/image-37.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-37.png)

<figcaption>

Lighthouse

</figcaption>

</figure>

補充一下，以下是網頁版的Lighthouse（PageSpeed Insights）網頁：

[PageSpeed Insights網頁](https://pagespeed.web.dev/)

這是Lighthouse的主頁面，可以選擇要用手機還電腦的體驗、以及要測試多少項目。這邊解釋一下五個類別的意義：

- **效能（Perfomance）**：它會分析網站的效能指數，如TBT、FCP等數值（順便說一下我的網站這項超差的...），並評估訪客的訪問體驗。如果你希望訪客可以很順的造訪你的部落格，這項的分數至少要及格60分（但我沒有QAQ）

- **無障礙作法（Accessibility）**：這項會分析網站無障礙的效能，也就是對於身心障礙者的友好程度，例如圖片是否加上Alt替代標籤、顏色對比度等。換言之其實就是類似UX（User Experince）的概念

- **最佳做法（Best Practices）**：此項會檢查網站是否有錯誤、是否採用https來保證安全等對於網站安全、體驗等的幫助

- **搜尋引擎最佳化（SEO，Search Engine Optimization）**：此項會檢查網站對搜尋引擎爬蟲的友善度，它會影響你的網站在搜尋引擎的排名，滿重要的

## 除錯面板輔助工具

這段會介紹 F12 面板中大部分的除錯輔助工具，本段介紹的工具你都可以在最上面的選單中找到對應的切換按鈕，如下圖：

<figure>

[![](/images/f12-guide/image-38.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-38.png)

<figcaption>

三個工具，其中最右邊那個是切換選單要停駐在左邊還是上方所以我就不特別說明了

</figcaption>

</figure>

### 頁面元素選擇器

頁面元素選擇器位在頁籤最左邊（它不是一個面板喔），快速鍵是Ctrl+Shift+C。進入此模式後游標指向網頁上的任一元素都會顯示該元素的資訊，就像你在HTML原始碼區塊中的那樣，如圖：

[![](/images/f12-guide/image-19-1024x561.png)](http://samhacker.is-from.tw/wp-content/uploads/2024/06/image-19.png)

他會透過顏色標記內外距、邊框粗細等，就像前面提到的一樣。在某個元素上點一下左鍵即可選定該元素，開發工具會自動切換至元素面板並選定你點擊的元素。請記得一個元素可以被許多容器包起來，所以如果想要選取一個元素，最好要直接點在它上方，不要離它太遠否則可能會選錯元素；選取後就可以對選取的元素修改，像是更改內容、更改色彩、字體等，可以方便你不用一直去翻元素裡滿滿看不懂的東西~~

### 裝置模擬（Device Simulation）

這項功能位在頁面元素選擇器旁邊，它可以在電腦中模擬手機、平板版的網站，開啟後左邊的網頁上方會多出一列裝置模擬工具列：

<figure>

[![](/images/f12-guide/image-39-1024x50.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-39.png)

<figcaption>

裝置模擬工具列

</figcaption>

</figure>

#### 尺寸選單

尺寸選單就是圖片中黃色的區塊，裡面有對某些裝置預設設定好的設定檔，如iPhone、Samsung、Google Pixel等手機都有對應的配置。這些預設配置檔包含那隻手機的螢幕大小等資訊，選擇後載入網站時傳到伺服器的User Agent也會用對應的作業系統，也就是說對伺服器而言這就是完完全全的手機。

<figure>

[![](/images/f12-guide/image-40.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-40.png)

<figcaption>

你可以選這幾種

</figcaption>

</figure>

如果裡面沒有你自己的機型可以按下編輯進去設定中添加自己所需要的機型，方便你設定常用手機的預覽。預設的"回應式"代表你可以自由拖動左右邊框來改變手機螢幕的大小，用來測試網站對每種機型的相容性。

#### 尺寸輸入框

尺寸輸入框位於圖片中紅色區塊，它提供你可以直接輸入要模擬的裝置螢幕大小，以像素（px）作單位計算。

#### 顯示大小

顯示大小位於橘色框中，可以設定底下模擬畫面的大小。如果選定的機型長寬比太大容易造成螢幕看不清楚內容，這時就可以用這邊的選單來放大方便檢視

#### 節流設定

位於綠色框中，你可以在之中設定瀏覽網頁時網速上下限，模擬使用行動網路瀏覽網站的體驗。

#### 視力缺乏模擬

這裡可以模擬視障者（全色盲、紅綠、藍黃色盲與近視）看到的畫面：

<figure>

[![](/images/f12-guide/image-41.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-41.png)

<figcaption>

視力模糊

</figcaption>

</figure>

<figure>

[![](/images/f12-guide/image-42.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-42.png)

<figcaption>

紅色盲

</figcaption>

</figure>

<figure>

[![](/images/f12-guide/image-43.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-43.png)

<figcaption>

黃色盲

</figcaption>

</figure>

<figure>

[![](/images/f12-guide/image-45.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-45.png)

<figcaption>

全色盲

</figcaption>

</figure>

<figure>

[![](/images/f12-guide/image-44.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-44.png)

<figcaption>

藍色盲

</figcaption>

</figure>

#### 旋轉

粉紅色按鈕，可以切換模擬範圍是模擬直向還是橫向（畢竟目前無論哪家系統，都有自動旋轉功能...）

## 基礎使用技巧

### 網頁長截圖

首先按下Ctrl+Shift+P叫出操作輸入框，輸入擷取（英文版輸入`Screenshot`），然後你就可以選擇擷取範圍：區域（要再用游標選取矩形範圍）、完整大小（長截圖）、節點螢幕（好像也一樣，用完整大小吧ww）和螢幕擷取畫面（當前範圍）

<figure>

[![](/images/f12-guide/image-46.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-46.png)

<figcaption>

四個選項

</figcaption>

</figure>

選擇自己要的截圖方式後會自動處理，並下載到本機電腦（出現在下載）

### 分析網頁字體

先使用頁面元素選擇器選定需要分析的元件（選到該物件，小心**不要選到上級的Container**喔！），本例分析這篇文章標題的字體。接著進入已計算樣式（元素面板）中。找到"轉譯字型"區塊就會看到類似以下資料：

```
轉譯字型
Family name: Noto Sans TC Thin
PostScript name: Noto-Sans-TC-Thin-Thin
Font origin: 網路資源(23 個字符)
```

- **Family Name（字體名稱）**：字體本身名稱，基本上注意這項就好

- **PostScript Name（PostScript名稱）**：PostScript是用來與印表機溝通的語言名稱，這項即是PostScript中用來標記字體名稱的寫法。設計網頁大多不需要注意這項

- **Font Origin（字體來源）**：說明這個字體檔案從哪裡存取，分為以下幾種：
    - **本機檔案（Local Font）**：由使用者電腦提供的字體，也就是字體檔案在電腦中，不需要另外等網站提供資料
    
    - **網路資源（Network Resource）**：由網站方提供字體檔案，因為是伺服器提供的，可以不用擔心需要的字體不在使用者電腦中，相對的需要花時間下載字體檔案，會拖到載入速度。大多用在英文網站或個人部落格（例如本站）

但這個方法有點麻煩，如果大家想直接一鍵抓到字體名稱可以使用[FontNinja](https://www.fonts.ninja/)這款Chromium瀏覽器擴充功能。

### 抓取元件色碼

先使用頁面元素選擇器選定要分析的元件（選到該物件，小心**不要選到上級的Container**喔！），本例分析這篇文章標題的字體。接著進入已計算樣式（元素面板）中。找到`color`如圖，這代表元件本身顏色（淡紅色框）；`border-color`則代表邊框顏色（綠色框）；`background-color`則代表背景顏色。其他建議大家可以自己學習一下CSS，這樣比較容易了解這個面板的功能。

[![](/images/f12-guide/image-47.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-47.png)

### 移除"你已開啟廣告攔截器"訊息

在許多網站上會跳出如圖的"你已開啟廣告攔截器"訊息，相信會非常妨礙訪客的造訪。其實可以用F12去移除喔！請跟著以下操作：

<figure>

[![](/images/f12-guide/image-48.jpg)](http://samhacker-local.local/wp-content/uploads/2024/06/image-48.jpg)

<figcaption>

為保護當事網站，背景已打碼

</figcaption>

</figure>

封鎖F12

大多數時候這類網站會封鎖F12的執行，所以需要用選單或其他方式叫出喔！

選到背景Cover的那個物件，按下Delete刪除。並如法炮製移除其他元件即可訪問。但請記得這招不一定有用喔！

尊重網站作者

大部分個人部落格都是自己扛主機、網域的費用，他們的收入幾乎來自於廣告。因此希望各位無論訪問哪個網站最好**可以不要開攔截器就不要開，這是支持網站站長的行為**，也可以幫助該網站繼續運營下去。**此部分只是作技術介紹，希望各位不要拿去做侵害智慧財產權的事喔！**

## 結語

我最近在FB社團中看到有不少新手網站跑版，但其實我親自去看之後發現靠自己就可以除錯了。因此我寫了這篇文章來教會大家用這款幾乎所有瀏覽器都有內建，超級好用的網站除錯工具。但這是面向開發者的工具，因此希望各位想要架部落格可以的話還是最好先學網頁語言。

架站工具好用歸好用，但希望各位要至少有一些基本的網頁設計知識。對我而言，我認為工具是用來節省時間而不是直接靠他做網頁，因此希望各位有時間學一下HTML之類的語言，可以方便自己更能做出理想中的網站。

最後希望這篇文章有幫助到你們，我寫了快要一個禮拜很辛苦，因此如果可以最好可以幫我分享文章給你其他可能需要的朋友，讓我的文章可以給更多人看見，也讓更多人可以更輕易的做出自己理想中的網站！

最後一句話了，祝各位站長們輕鬆架出自己理想中的網站喔！
