---
title: "Minecraft 開服之路：概念與安裝步驟"
published: 2024-05-01
category: Minecraft開服之路
tags: 
  - "minecraft"
  - "伺服器"
  - "基本"
  - "插件"
image: "/images/mcserver-1-basic/標題-1.png"
---

大家好，我是 **[SamHacker](http://samhacker.is-from.tw)**，最近突發奇想想寫文章教 開麥塊伺服器 的一個無聊人

今天是一系列的文章（坑）的開始，我想寫一系列文章來教大家開伺服器。前面廢話不用太多，直接進入正題吧！我是第一次發文，有些地方可能寫的怪怪的請大家多多包容啦！

## 一、什麼是伺服器

什麼是伺服器？這個問題其實很簡單，不用想的太難，你現在在看我的文章，我的文章就存在巴哈的伺服器上。伺服器依照維基百科的定義，就是：

> 一個管理資源並為使用者提供服務的電腦軟體，通常分為檔案伺服器（能使使用者在其他電腦存取檔案），資料庫伺服器和應用程式伺服器。  
> 簡單來說，伺服器就是一台電腦，但不是我們熟悉的個人電腦。伺服器是擁有特殊功能的企業級電腦產品，用戶可透過行動裝置或個人電腦與其連線，索取額外的資訊與服務。
> 
> 維基百科 - [https://zh.wikipedia.org/zh-tw/%E6%9C%8D%E5%8A%A1%E5%99%A8](https://zh.wikipedia.org/zh-tw/%E6%9C%8D%E5%8A%A1%E5%99%A8)

對，如上面所說的，伺服器簡單來講就是一台電腦，無論是什麼電腦都可以，桌機、筆電、手機、甚至是你的智慧手表，只要這台裝置可以連上網路，就可以是一台伺服器，就這麼簡單。伺服器的用途簡單說，就是**提供服務的機器**

至於麥塊伺服器是幹嘛的？請想一個情境：你想要跟朋友一起相約比速通，看誰先打終界龍打完，於是你建立了一個世界，然後在區網發布，你的電腦現在就是一台可以在區網中跟朋友開黑打遊戲的伺服器，也就是說，麥塊伺服器就只是用來讓一堆人可以在一個世界玩麥塊的一台機器，他會記錄所有人的資訊、地圖等。

## 二、怎麼開伺服器

開麥塊伺服器 的方法，目前可以分成兩種方法：本機開服與租用託管，底下來比較一下兩個方法的差異：

### 本機開服

就跟名字一樣，你用自己的電腦開伺服器給別人連線。

但因為一些原因（好奇的話留個言敲碗，夠多人敲我就寫），你的電腦要讓玩家們玩是需要一些...方法的，稍微複雜一些，適合有開服基礎和想不開

的人使用

### 租用託管

看到"租"就知道，這個方法是要一（億）

些錢，但俗話說的好：付錢的最大，選擇這個方法你不用自己設定內網穿透、伺服器軟體、設定連線位置、申請固定IP...的事情，你只需要出一些錢就可以了。

至於這兩個方法差在哪裡，用買電腦來說，本機開服就像你自己買各個零件自己拼在一起，而租託管就是買現成的套裝機。一個是CP值高，你可以確保你花的每一毛錢都有變成硬體或光害；另一個則是簡單，買來回家接電接滑鼠鍵盤螢幕開機就可以快樂地用了，出事再把電腦丟去給廠商修。一個是性價比高、一個是不用自己DebugDe得要死要活，底下我開個表格可能比較省事：

| 項目 | 租用託管 | 本機開服 |
| --- | --- | --- |
| 除錯 | 不用，廠商會幫你解決一切 | 要，看要爬聞問GPT還是來巴哈找大佬（不是我） |
| 花錢 | 要，你就是多花錢買個方便，大概幾百一個月 | 如果你有電腦就不用 |
| 優點 | 你不用另外肝，託管商會幫你解決開服前的設定，你只要專注把伺服器做好就好你的電腦不用24小時開機，反正你是用託管商的主機不用另外設定動態IP，也不用學太多東西 | 基本上不用花錢CP值比較高，每毛錢都可以花在刀口上自訂性可以比託管高，伺服器就在你手上啊 |
| 缺點 | 要錢CP相對低：同樣價位的託管，有的DIY大神可以直接一台伺服器只要幾千，吊打託管的同價位伺服器遇到不好的託管商，恭喜你 | 你要自己設定一堆東西，而且基本不會太簡單的電腦24小時開機可能會讓它短命點（雖然好像也沒太嚴重）自訂性高代表你肝也會比較快硬化 |
| 適合的情境 | 只想跟朋友玩中小型伺服器 | 想開大型伺服器，且自己有一定基礎追求CP值，對花錢有沒有花在適合的地方有強迫症喜歡肝，時間很多 |

## 三、開服的軟體

常見用來開麥塊伺服器的軟體有以下幾套：

- **原版伺服器：**Vanilla

- **插件伺服器：**Bulkkit、Paper、Spigot、Purpur

- **模組伺服器：**Forge、Fabric

- **協議轉換程式：**GeyserMC、BigBrother

（以上資料部分[來自Wiki頁面](https://ref.gamer.com.tw/redir.php?url=https%3A%2F%2Fminecraft.fandom.com%2Fzh%2Fwiki%2F%E5%AE%9A%E5%88%B6%E6%9C%8D%E5%8A%A1%E5%99%A8)）

底下來比較一下（沒有全部，只拿我比較熟悉的）：

| 項目 | Vanilla | Bulkkit | Paper | Spigot | Forge & Fabric | GeyserMC |
| --- | --- | --- | --- | --- | --- | --- |
| 開發者 | Mojang Studios  
（官方） | SpigotMC | PaperMC | SpigotMC | MinecraftForge & FabricMC | GeyserMC |
| Fork來源 | 無 | 無 | Bulkkit | Bulkkit  
的續作 | 無 | 無 |
| 類型 | 原版 | 插件 | 插件 | 插件 | 模組 | 封包轉譯器  
（協議轉換  
程式） |
| 開放性與可自訂性 | 低 | 中 | 中 | 中 | 中高 | 不可比較 |
| 特點 | 官方原版，對新版本支持較佳不容易出錯，穩定度佳 | 可安裝插件社群廣大 | 可安裝插件社群廣大且大多相容Bulkkit | 可安裝插件社群廣大且大多相容Bulkkit | 可安裝模組社群較插件更加大可修改的部分更多 | 可讓基岩版伺服器加入Java伺服器 |
| 更新速度 | 最快，幾乎即時 | 快，但插件不一定相容 | 快，但插件不一定相容 | 快，但插件不一定相容 | 快，但模組不一定相容 | 通常支持全版本 |
| 擴充內容 | 最少 | 多 | 多 | 多 | 最多 | 不可比較 |
| 玩家須安裝 | 無，直接加入即可 | 無，直接加入即可 | 無，直接加入即可 | 無，直接加入即可 | 需安裝對應模組 | 無，直接加入即可 |
| 價格 | 免費 |

我的文章應該之後會教學主要是Paper伺服器，因為我最熟悉...

## 四、下載自己的第一個伺服器軟體

### 4-1 下載Java環境

如果你可以玩MC，一般你應該已經下載好Java環境了，可以試著按下Windows + R，輸入 cmd 並執行，然後你會看到類似以下的視窗：

```
Microsoft Windows [版本 10.0.19045.4046]
(c) Microsoft Corporation. 著作權所有，並保留一切權利。

C:\Users\510208>
```

輸入 java --version ，如果你回應以下訊息就OK了：

```
Microsoft Windows [版本 10.0.19045.4046]
(c) Microsoft Corporation. 著作權所有，並保留一切權利。

C:\Users\510208>java --version
java 21.0.2 2024-01-16 LTS
Java(TM) SE Runtime Environment (build 21.0.2+13-LTS-58)
Java HotSpot(TM) 64-Bit Server VM (build 21.0.2+13-LTS-58, mixed mode, sharing)

C:\Users\510208>
```

沒的話...[這邊](https://ref.gamer.com.tw/redir.php?url=https%3A%2F%2Fwww.oracle.com%2Fjava%2Ftechnologies%2Fjavase%2Fjdk17-archive-downloads.html)自己翻檔案，直接下載無腦下一步即可，通常找 **Windows x64 Installer** 即可

### 4-2 下載伺服器軟體（Paper篇）

底下連結有所有Paper發行版連結：

[前往網站](https://gist.github.com/osipxd/6119732e30059241c2192c4a8d2218d9)

在這邊找自己要安裝的版本，複製連結下載，我建議不要裝最新版本，很容易出事情，我這邊用1.20示範，以下是我取得的連結：

[前往網站](https://api.papermc.io/v2/projects/paper/versions/1.20/builds/17/downloads/paper-1.20-17.jar)

下載到檔案以後，不要直接打開，先把它移到一個資料夾，我自己習慣扔到C槽根目錄創一個 server 資料夾，以下是正常的樣子：

```
C:.
    paper-1.20-17.jarpaper-1.20-17.jar
```

是我剛剛下載的伺服器檔案，前往這個網站，要做啟動設定檔案：

[前往網站](https://flags.sh)

FileName輸入你的伺服器檔案名稱，像我是 paper-1.20-17.jarMemory輸入你本機硬體記憶體的一半左右就夠了，工作管理員裡面效能裡有，可以自己去看看：

<figure>

[![](/images/mcserver-1-basic/9984a14c5d6864d9c55d821911d3d9a2.png)](http://samhacker-local.local/wp-content/uploads/2024/05/9984a14c5d6864d9c55d821911d3d9a2.png)

<figcaption>

先確定你的記憶體容量，這是工作管理員

</figcaption>

</figure>

然後按網站上的下載按鈕（上面先切到你的作業系統，通常是Windows）：

<figure>

[![](/images/mcserver-1-basic/a047f167eed2e0580a98a9f5f5393e82-1024x555.jpg)](http://samhacker-local.local/wp-content/uploads/2024/05/a047f167eed2e0580a98a9f5f5393e82.jpg)

<figcaption>

這是一個可以線上產生伺服器啟動腳本的工具

</figcaption>

</figure>

你會得到一個start.bat，把他跟你的伺服器軟體一起放資料夾下，然後變這樣：

```
C:.
    paper-1.20-17.jar
```

    start.bat啟動伺服器很簡單，執行剛載的檔案即可，你也可以改檔名讓自己不會忘記，跳警告請放心讓他跑。然後...你會發現它...閃退了？？？其實很簡單，就像註冊帳號會叫你同意那一大串可能打死我也不會看的條款一樣，這個東西也是要同意那一大串可能打死我也不會看的條款，然後你會發現一件事：X北為啥出現這麼多資料夾跟檔案？？？？

```
C:.
│  eula.txt
│  paper-1.20-17.jar
│  server.properties
│  start.bat
│
├─cache
│      mojang_1.20.jar
│
├─libraries
│  // 這就是一堆相依性文件，不用管...
├─logs
│      latest.log
│
├─plugins
└─versions
    └─1.20
            paper-1.20.jar
```

這一堆就是伺服器的檔案，我簡單整理幾個重要的給你：

- **cache**：快取，不要動它，之後要搬伺服器把這個刪掉也可以

- **logs**：記錄檔，快樂的除錯時間時會需要...最好永遠不要用到，因為要用到代表你會很痛苦

- **plugins**：插件，之後我會教

- **eula.txt**：害你閃退的元兇，待會教你怎麼弄

- **paper-1.20-17.jar**：伺服器主程式

- **server.properties**：伺服器配置文件，未來會教，也可以自己預習

- **start.bat**：你忘記這啥了嗎？以後啟動伺服器要找它欸

這個顏色的是資料夾，這個顏色的叫做檔案

打開 eula.txt 看到裡面有以下文字：

```
#Tue Feb 20 17:38:18 CST 2024
eula=false
```

把第三行的 `eula=false` 改成 `eula=true`

存檔重開伺服器

然後...檔案變得更多了...

記錄檔變這樣：

```
[17:48:24 INFO]: Environment: authHost='<a href="https://ref.gamer.com.tw/redir.php?url=https%3A%2F%2Fauthserver.mojang.comxxx%2C" target="_blank" rel="noreferrer noopener">https://authserver.mojang.com',</a> accountsHost='<a href="https://ref.gamer.com.tw/redir.php?url=https%3A%2F%2Fapi.mojang.comxxx%2C" target="_blank" rel="noreferrer noopener">https://api.mojang.com',</a> sessionHost='<a href="https://ref.gamer.com.tw/redir.php?url=https%3A%2F%2Fsessionserver.mojang.comxxx%2C" target="_blank" rel="noreferrer noopener">https://sessionserver.mojang.com',</a> servicesHost='<a href="https://ref.gamer.com.tw/redir.php?url=https%3A%2F%2Fapi.minecraftservices.comxxx%2C" target="_blank" rel="noreferrer noopener">https://api.minecraftservices.com',</a> name='PROD'
[17:48:24 INFO]: Found new data pack file/bukkit, loading it automatically
[17:48:26 INFO]: Loaded 7 recipes
[17:48:26 INFO]: Starting minecraft server version 1.20
[17:48:26 INFO]: Loading properties
[17:48:26 INFO]: This server is running Paper version git-Paper-17 (MC: 1.20) (Implementing API version 1.20-R0.1-SNAPSHOT) (Git: c287e92)
[17:48:26 INFO]: Server Ping Player Sample Count: 12
[17:48:26 INFO]: Using 4 threads for Netty based IO
[17:48:26 INFO]: [ChunkTaskScheduler] Chunk system is using 1 I/O threads, 2 worker threads, and gen parallelism of 2 threads
[17:48:26 WARN]: [!] The timings profiler has been enabled but has been scheduled for removal from Paper in the future.
    We recommend installing the spark profiler as a replacement: <a href="https://ref.gamer.com.tw/redir.php?url=https%3A%2F%2Fspark.lucko.me%2F" target="_blank" rel="noreferrer noopener">https://spark.lucko.me/</a>
    For more information please visit: <a href="https://ref.gamer.com.tw/redir.php?url=https%3A%2F%2Fgithub.com%2FPaperMC%2FPaper%2Fissues%2F8948" target="_blank" rel="noreferrer noopener">https://github.com/PaperMC/Paper/issues/8948</a>
[17:48:27 INFO]: Default game type: SURVIVAL
[17:48:27 INFO]: Generating keypair
[17:48:27 INFO]: Starting Minecraft server on *:25565
[17:48:27 INFO]: Using default channel type
[17:48:27 INFO]: Paper: Using Java compression from Velocity.
[17:48:27 INFO]: Paper: Using Java cipher from Velocity.
[17:48:27 INFO]: Preparing level "world"
[17:48:35 INFO]: Preparing start region for dimension minecraft:overworld
[17:48:35 INFO]: Time elapsed: 157 ms
[17:48:35 INFO]: Preparing start region for dimension minecraft:the_nether
[17:48:35 INFO]: Time elapsed: 136 ms
[17:48:35 INFO]: Preparing start region for dimension minecraft:the_end
[17:48:35 INFO]: Time elapsed: 71 ms
[17:48:35 INFO]: Running delayed init tasks
[17:48:35 INFO]: Done (9.177s)! For help, type "help"
[17:48:35 INFO]: Timings Reset
```

看到這個，伺服器就搞定了...

<figure>

[![](/images/mcserver-1-basic/70bfe526360243bf8400ec8f9ffe3ea0-1024x577.png)](http://samhacker-local.local/wp-content/uploads/2024/05/70bfe526360243bf8400ec8f9ffe3ea0.png)

<figcaption>

終端機的訊息

</figcaption>

</figure>

很完美，現在打開MC，因為我們還沒裝全版本插件，所以你只能用你當初下載的版本，在終端上會寫，像我在截圖上數下來第三行出現這段字：

```
[17:48:26 INFO]: Starting minecraft server version 1.20
```

這代表我下載的是1.20版本的伺服器，也就是我要去載1.20版的遊戲才能連線，但這樣好麻煩...於是我們要來裝第一個插件啦！

## 五、裝全版本支持插件

首先，連到以下網站下載檔案：

[下載插件~~](https://www.spigotmc.org/resources/viaversion.19254)

這個是向上支援的插件，找這顆按鈕按下去，然後把下載下來檔案扔進 plugins 資料夾，這就是安裝插件的方式，很簡單齁？

[![](/images/mcserver-1-basic/9a4309b618709b1171df31e9a7f39dca.PNG)](https://truth.bahamut.com.tw/s01/202402/9a4309b618709b1171df31e9a7f39dca.PNG)

再來我們安裝這套：

[下載插件~~](https://www.spigotmc.org/resources/viabackwards.27448)

安裝方法一樣，兩個裝好之後在終端視窗輸入stop按Enter，等視窗消失

然後重開...

你會看到終端多這些：

```
[17:55:21 INFO]: [ViaVersion] Loading server plugin ViaVersion v4.9.2
[17:55:21 INFO]: [ViaVersion] ViaVersion 4.9.2 is now loaded. Registering protocol transformers and injecting...
[17:55:22 INFO]: [ViaVersion] Loading block connection mappings ...
[17:55:22 INFO]: [ViaVersion] Using FastUtil Long2ObjectOpenHashMap for block connections
[17:55:22 INFO]: [ViaBackwards] Loading translations...
[17:55:22 INFO]: [ViaBackwards] Registering protocols...
[17:55:22 INFO]: [ViaBackwards] Loading server plugin ViaBackwards v4.9.1
```

這代表插件正常載入了，之後你用任何版本都可以輸入 127.0.0.1 當IP連上去！

今天先講到這裡，剩下的我下一篇在講
