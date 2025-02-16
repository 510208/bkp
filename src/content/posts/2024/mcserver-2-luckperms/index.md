---
title: "Minecraft開服之路：最初的開始 - 權限設定插件"
published: 2024-05-02
categories: 
  - "mc-server-guide"
tags: 
  - "luckperms"
  - "minecraft"
  - "伺服器"
  - "插件"
image: "/images/mcserver-2-luckperms/mcperms-header.png"
---

抱歉拖了這麼久才更下一篇文章，我是上一集大家應該就認識的 SamHacker ，今天要來跟大家介紹一下幾乎每個服主都會裝的 LuckPerms 插件：

（喔對了這張是[Github頁面](https://ref.gamer.com.tw/redir.php?url=https%3A%2F%2Fgithub.com%2FLuckPerms%2FLuckPerms)上的圖...）

## 一、什麼是LuckPerms

LuckPerms是一款非常強大的伺服器權限插件（而且有繁中版），透過權限節點的方式來管理權限，如果沒有這個的話，一般玩家就沒辦法運用部分插件（像經濟插件、Residence那些的...）

## 二、安裝LuckPerms

### 2-1 安裝LuckPerms

安裝LuckPerms是件很簡單的事...

首先，先去官網下載打包好的檔案：

[LuckPerms 官網](https://luckperms.net)

點最大、綠綠的下載按鈕：

[![](/images/mcserver-2-luckperms/1c7d590d69197b430441f76b06d5ce4e-1024x148.jpg)](http://samhacker-local.local/wp-content/uploads/2024/05/1c7d590d69197b430441f76b06d5ce4e.jpg)

再來我們[第一集](http://samhacker-local.local/2024/05/01/mcserver-1-basic/)教的是安裝Paper伺服器，所以這邊就下載Bukkit版本，上一篇文章我在第三段"開服的軟體"有提到Paper是Fork原本的Bulkkit，所以自然下載Bukkit版本：

[![](/images/mcserver-2-luckperms/37f4080287dd007c7d33e539e989aa43.jpg)](http://samhacker-local.local/wp-content/uploads/2024/05/37f4080287dd007c7d33e539e989aa43.jpg)

（請看，後面也有註名Paper）

[![](/images/mcserver-2-luckperms/5058a4f1b7cfe70a6dba0252bbb4f10c.jpg)](http://samhacker-local.local/wp-content/uploads/2024/05/5058a4f1b7cfe70a6dba0252bbb4f10c.jpg)

你會得到這樣一個\*.jar檔案，它就是你要的插件

於是將這個檔安裝進伺服器（上次我在第五段"裝全版本支持插件"有提到），然後重啟

進伺服器後，你會發現多了/lp開頭的指令可以用：

[![](/images/mcserver-2-luckperms/89846507a3724dd716939164db7445e3.jpg)](http://samhacker-local.local/wp-content/uploads/2024/05/89846507a3724dd716939164db7445e3.jpg)

（至於這裡的lpc等等就會講到）

然後就可以開始用了...還沒謝謝![](/images/mcserver-2-luckperms/14.gif)

### 2-2 安裝LPC與TAB

為甚麼要裝LPC跟TAB？首先要先來說說他們兩個是個啥：

- **LPC**，全名LuckPerms Chat，官網上寫這樣：LPC - Chat Formatter，用來讓聊天區有辦法顯示Prefix跟Suffix，前置插件：LuckPerms

- **TAB**，對於顯示的部分有許多功能，例如按住TAB會得到更好看的玩家列表、也有伺服器右邊的資料甚麼的，之後都會教，都是廢話你可以不用看，今天要用的是更改頭上玩家名條的功能，前置插件：好像沒有

現在懂了吧...它們是讓LuckPerms用得更順的工具，a.k.a. 插件的插件

這邊貼下載連結：

- **LPC**：[https://www.spigotmc.org/resources/lpc-chat-formatter-1-7-10-1-20.68965/](https://ref.gamer.com.tw/redir.php?url=https%3A%2F%2Fwww.spigotmc.org%2Fresources%2Flpc-chat-formatter-1-7-10-1-20.68965%2F)

- **TAB**：[https://www.spigotmc.org/resources/tab-1-5-1-20-4.57806/](https://ref.gamer.com.tw/redir.php?url=https%3A%2F%2Fwww.spigotmc.org%2Fresources%2Ftab-1-5-1-20-4.57806%2F)

下載的按鈕跟第一篇那邊裝全版本一樣，[失憶的自己飛回去研究](https://ref.gamer.com.tw/redir.php?url=https%3A%2F%2Fhome.gamer.com.tw%2Fartwork.php%3Fsn%3D5885857)

下載裝完記得重開，不要忘記~

## 三、簡述權限節點、繼承與父子群組、權重

### 3-1 類別與屬性

打個比方，要形容SamHacker（我）這個人，你可能可以用這些說明：

- Minecraft玩家

- 插件師

- 男生

- ...

這時候，我SamHacker就是個類別，而上面提及的麥塊玩家、插件師、男性...都是我的屬性，為什麼要突然提這個？看下去就知道了

### 3-2 權限節點

權限節點就是用來管理玩家有哪些權限沒有哪些權限的東西的專有名詞。我們可以把每個玩家看作是一個類別，那就會需要幫他們設定可以用哪些指令、或是不能用哪些指令，這些設定項目就是一個個權限節點，或者說...屬性（對，這兩個基本上是可以想在一起的）。

### 3-3 群組

剛剛講到你要幫所有玩家設定他們該有的權限，但如果你伺服器五六十個玩家就好，一個一個設定權限肯定會死...那有沒有辦法一次設定大家一起用？可以，就是**群組**這項功能。

我們可以建立許多群組，像是一般玩家、VIP、管理員、服主...然後設定好該有的，例如一般玩家總該給他們建立領地、給別人錢那些的...但是不能讓他們可以用例如創造、give指令、或是kick那些的指令，VIP多給一些福利，例如粒子特效、短暫飛行...管理員則是要有kick、kill、ban這些指令權限，服主嘛...都給就對了不用講廢話...

所以有沒有發現？群組其實就是所謂痛一次之後都輕鬆的概念，先設定好所有分類，然後之後誰要什麼就給什麼，就這麼簡單。

### 3-4 繼承與父子群組

講完了群組，現在要看看繼承和父子了。

今天一個玩家會需要一般玩家的能力，我們就把一般玩家給他用，也就是"把一般玩家群組的權限全部繼承給這位玩家"，如此一來，這位玩家就獲得了所有一般玩家該有的東西了，你也不用一個一個貼來貼去。如果我們另外把管理員跟服主的東西都設好應該像這樣：

[![](/images/mcserver-2-luckperms/4b9ecca1dd4be43c2867c1f11ad8b428.jpg)](http://samhacker-local.local/wp-content/uploads/2024/05/4b9ecca1dd4be43c2867c1f11ad8b428.jpg)

這時候，你可以很清楚看到，管理員有管理員的權限，也有玩家的權限，也就是說，"玩家繼承一般玩家跟管理員兩群組"，而我則另外再繼承了"服主"群組，但有沒有發現？管理員也是繼承一般玩家的權限，兒服主也繼承管理員，也就是服主繼承一般玩家...（這是套娃吧...我變成教國文了）

那這時候考考你：我有沒有辦法使用玩家的指令，如果這指令我只在一般玩家那邊設定的話？可以，你答對了嗎

如果你答對了，那恭喜你應該看懂了我的教學！那可以繼續看下去了，如果有什麼不懂的，下面留言我有空看到會回你

## 四、LuckPerms必學指令

基本上這個插件我會用到的、常用的就三個指令：

<table><tbody><tr><td>指令</td><td>說明</td></tr><tr><td>/lp editor</td><td>打開網頁編輯器，下面說明</td></tr><tr><td>/lp user &lt;玩家名稱&gt;</td><td>編輯玩家的權限，我最常用在新增管理員或其他身分組給玩家的時候<br>因為只是件小事我懶得開編輯器，像以下是給玩家Sam510208 manager群組的權限：<br>/lp user Sam510208 parent add manager</td></tr><tr><td>/lp group &lt;群組名稱&gt;</td><td>編輯某群組的權限</td></tr></tbody></table>

所以...打開編輯器吧，指令我基本能不用就懶得用

## 五、LuckPerms網頁編輯器

使用/lp editor後點開這個連結：

[![](/images/mcserver-2-luckperms/b3accb99da20326c9f7afe8bf4478c75.jpg)](http://samhacker-local.local/wp-content/uploads/2024/05/b3accb99da20326c9f7afe8bf4478c75.jpg)

你會看到這個：

[![](/images/mcserver-2-luckperms/3f24f6d2f7e85c865eb4ced065435b18-1024x492.png)](http://samhacker-local.local/wp-content/uploads/2024/05/3f24f6d2f7e85c865eb4ced065435b18.png)

認識一下，最左邊那一直行，有權限階級、群組和使用者三項，

- **權限階級**：我不會用w

- **群組**：剛剛提到了

- **使用者**：就是玩家啦

右邊那個則是設定的地方，待會就會說了

右上角有儲存按鈕，可別好不容易弄好結果忘記存

## 六、實戰 - 建立一個管理員群組，給予TP和Gamemode

開工了！

首先，點選群組旁邊加號，來建立一個管理員群組：

[![](/images/mcserver-2-luckperms/71bd5c529dcb3c1c38097de66bcc4505.png)](http://samhacker-local.local/wp-content/uploads/2024/05/71bd5c529dcb3c1c38097de66bcc4505.png)

- **群組名稱：**輸入群組名稱，我會建議用英文，例如manager

- **顯示名稱：**這邊用中文打管理員就好吧

- **父群組：**剛講的，我希望他繼承一般玩家，父群組選default（LuckPerms預設的類別，每個玩家都會有這個類別，也就是一般玩家）

- **權重：**忘記講到了，你就想像成繪圖軟體圖層的概念，如果父群組也有某個項目、子群組也有同一個項目，就會以權重比較高的做主，也就是有錢的最大  
    我希望管理員的權限設定覆蓋掉玩家（父群組的），所以把它設為10

- **前綴與後綴：**前綴就是玩家名字前面加的，後綴就以此類推，前提是要記得裝LPC

然後會建立一個全空的身分組：

[![](/images/mcserver-2-luckperms/8b74a68e68eba0817ccf8df8e137fa0c-1024x529.png)](http://samhacker-local.local/wp-content/uploads/2024/05/8b74a68e68eba0817ccf8df8e137fa0c.png)

現在我們要開始設定TP和Gamemode，我已經知道這兩個都是minecraft這個類別底下的權限，所以以下是這兩個項目的權限節點：

> **minecraft.command.gamemode.teleport**
> 
> TP 指令的權限節點

- **綠色的是最父類別**，通常來講這個會是插件的名稱

- **黃色是底下的項目**，這邊兩個例子都是只有一層，但有些會有很多層

- **紅色是鍵名**，也是你真的要改的：  
    把值設為True，也就是給這個身分組擁有這兩個權限，  
    直接按+新增就好

## 七、實戰 - 給自己這些權限

要怎麼給自己這些權限？

首先，展開左邊的使用者並找到自己，然後在最上面的父群組新增剛剛建立好的manager，結束（這段好像湊字數...）

現在你已經學會基本的設定了（好隨便），其他的東西之後會寫，（拜託不要覺得我寫的爛，我只是想循序漸進教而已），只是不知道下一篇啥時出來而已w
