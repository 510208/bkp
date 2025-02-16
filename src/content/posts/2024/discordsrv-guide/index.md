---
title: "雲玩家的最佳首選－DiscordSRV聊天同步插件"
published: 2024-06-01
categories: 
  - "mc-server-guide"
tags: 
  - "dc"
  - "dc群"
  - "discord"
  - "ic"
  - "icd"
  - "minecraft"
  - "插件"
  - "綁定"
  - "連接"
image: "/images/discordsrv-guide/DiscordSRV聊天同步插件-雲玩家的最佳首選.png"
---

正所謂秀才不進服，能知天下事；想要不在伺服器裡就知道到底花生什麼事、讓玩家吵架有一個聊天紀錄的備份、又或者你希望給個權限不用再/lp editor、甚至一看就知道這個玩家是誰...你都會需要一個在伺服器的內鬼...喔不對，內應（別說這麼難聽w），但是又不想自己寫一個DC Bot（像我正被Node.JS搞得團團轉），那選擇一個插件用來代替機器人不正是個好選擇嗎？  
然後你開始上網查哪個插件好，轉來轉去其實基本上要做聊天同步、群組與權限同步什麼的，最多人推薦最老牌的還是DiscordSRV（ DCSRV ），再來就是那個好像自1.18就不更新的DiscordConnection...因此我還是乖乖介紹DCSRV啦（絕對不是蹭熱度）

而至於為什麼 DCSRV 可以讓一堆插件作者乾脆直接讓他霸榜就好，似乎只剩下EssentialsX Discord想跟他爭...原因很簡單：DCSRV實在強大到打不過。沒錯，DCSRV擁有例如最基本的Discord聊天同步、連結Discord帳號、權限節點同步、直接檢視線上玩家、直接檢視線上回應數據、甚至於內建有對PlaceHolderAPI的超完整相容性、還支持VentureChat讓你可以在伺服器開三四種聊天頻道。光是看我打了三段的開頭就知道DCSRV真的不是吃素的...所以光講DCSRV應該會講很久，就等之後靠時間慢慢累積啦！

## 安裝插件與取得Token

安裝DiscordSRV的方法就有些複雜了，首先當然一樣要先前往官網下載，傳送們底加：

[DiscordSRV 官方下載點](https://www.spigotmc.org/resources/discordsrv.18494/)

然後一樣的重開伺服器和一樣的打開配置檔案，安裝插件請回去複習[Minecraft開服之路：最初的開始 – 權限設定插件](http://samhacker-local.local/2024/05/02/mcserver-2-luckperms/)一文，配置檔案怎麼玩請回去複習[今天我就是巴菲特－ XConomy 經濟插件](http://samhacker-local.local/2024/05/16/xconomy-guide/)這篇...

再來就是所有新手最痛苦的一環：怎麼取得BotToken？

<figure>

[![](/images/discordsrv-guide/image-34-1024x376.png)](http://samhacker-local.local/wp-content/uploads/2024/05/image-34.png)

<figcaption>

對，就是那個"YOUR\_TOKEN\_HERE"...

</figcaption>

</figure>

## 中文化DiscordSRV

這款插件目前沒有提供可以直接切換中文化版本的能力，也就是說他不像之前的[XConomy](http://XC)一樣可以直接改languange。官方有提供簡體中文的語系文件，但我已經將繁體中文的檔案提交給官方作審核了（但因為我耍笨忘記開分支，不知道官方會不會收...對不起我的錯）。如果各位想要繁體中文的語系，請依照教學來操作

首先因為DiscordSRV有6個配置檔案：`alerts`、`config`、`linking`、`messages`、`synchronization`、`voice`，所以要先分別將這些配置檔案給下載下來。你可以用Git來下載，但技術含量太高。因此我會建議用網頁上直接手動下載（反正又不是六百個檔案，怕甚麼？）。先前往我中文化的儲存庫（我不知道官方會不會收我的語系，所以先去我那裏載吧），傳送門在下面：

[這是中文化存儲庫傳送門](https://github.com/510208/DiscordSRV/tree/master/src/main/resources)

<figure>

[![](/images/discordsrv-guide/image.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image.png)

<figcaption>

你會看到這樣的畫面

</figcaption>

</figure>

再來是一件麻煩的事情：裡面有六個資料夾，代表的是六個DCSRV的配置文件的多國語系版本。因此請分別進到各個資料夾裡面找`zht.yml`並點擊右邊的下載：

[![](/images/discordsrv-guide/image-1-1024x544.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-1.png)

確定紅色的框框框的是zht.yml（繁體中文語系），並點擊黃色框的按鈕以下載。請在六個資料夾中都如法炮製。如果你還是看不懂，我在底下另外附上準備好的檔案，但可能會版本比較低，因為我不會每個版本都做打包：

[打包好的語系文件](https://github.com/510208/DiscordSRV/releases/tag/chinese-1.0)

語系文件日期時間

此語系文件已確認支援2024/6/1之前的所有DiscordSRV更新版本，如果官方將我的作品Pull進他們的儲存庫，這個語系的更新檔案應該會出現[在官方的儲存庫](https://github.com/DiscordSRV/DiscordSRV/tree/master/src/main/resources)中。

如果你發現更換此版本後會出錯，請在這裡提出Issue，我會進行修復（只有跟語系版本有關的錯誤我會受理，其他請[自行向官方回報](https://github.com/DiscordSRV/DiscordSRV/issues)！）

之後請將語系文件複製進伺服器的`/plugins/DiscordSRV`中，然後重新載入 DCSRV （`/discordsrv reload`）即可！

Token

覆蓋後Token會被重設，因此請記得先將Token保存好再進行覆蓋（如果你先前在英文語系中配置過），覆蓋完要記得將Token重新貼進新語系文件！

更換語系後你會發現，原作者很細心地將所有配置點都有寫註解說明，我也都翻譯好了。如果你們自己有實力也可以自行參考註解(^\_^)

## 取得Bot Token與建立DC機器人

保護好Token

再來教你做的事，是建立一隻Discord機器人，並將她加入到你的Discord群組裡面；想像一下你是這個機器人的駕駛員，這組Token就是你啟動機器人的鑰匙。

所以千萬記得，**把這串Token作為你的密碼保管，絕對不要讓任何人（包括任何願意幫妳寫插件的人、甚至是我！）**，如果讓任何人知道了，代表他可以在你的DC群中為所欲為！！

因為DC的開發者面板變了，不然我應該會直接摳走別人的文章來用...首先前往DC開發者面板，底下是傳送門歡迎自取：

[Discord Developer Portal（DC開發者面板）](https://discord.com/developers/applications)

看到右上角有一個大大紫色的New Applaction，它代表建立新機器人，用力地點下去！

<figure>

[![](/images/discordsrv-guide/image-35-1024x83.png)](http://samhacker-local.local/wp-content/uploads/2024/05/image-35.png)

<figcaption>

對他很紫

</figcaption>

</figure>

他會請你輸入一個名稱，也就是DC機器人的名字。輸入之後點一下下方我同意Discord ToS的勾勾，Create給他按下去就對啦！

再來會看到一個滿滿英文的畫面，不要慌，這不就給你帶來介紹了嗎？

[![](/images/discordsrv-guide/image-2.png)](http://samhacker-local.local/wp-content/uploads/2024/05/image-2.png)

1. 這隻**機器人的名字**

3. **機器人的介紹**

5. 暫時不用管它，不重要

7. **機器人的ID**，方便官方識別機器人，每隻機器人的ID都是獨一無二的，所以不要外流

9. **公開密鑰**，不要給別人看。雖然沒Token重要，但人家也是重要的

11. **伺服器數量**，代表這隻機器人出現在幾個伺服器中，你剛建立通常是0

寫好之後要取得這個堪稱可以毀壞你DC群，令一眾開發者哭爹喊娘（？）的Token了。切換到左邊的Bot頁籤，如下

[![](/images/discordsrv-guide/image-22-1.jpg)](http://samhacker-local.local/wp-content/uploads/2024/05/image-22-1.jpg)

1. **機器人頭像**，基本上不太重要，你剛剛應該都設定好了

3. **機器人的Banner**，實測發文時這個Banner不用Nitro，你可以做一下，滿良心的

5. **機器人名稱**，反正跟剛剛一樣就好

7. **重設Token**。為了保障安全，Discord規定一組Token只能在面板顯示一次，因此請好好保存Token，因為重設它你要更新其他所有地方，否則會出事

9. 這是授權流程，如果你想寫機器人這很重要，但 DCSRV 跟它不會有關係

[![](/images/discordsrv-guide/image-22-3.jpg)](http://samhacker-local.local/wp-content/uploads/2024/05/image-22-3.jpg)

在這個分類裡有著機器人的特權選項，包含了**Presence Intent、Server Members Intent和Message Content Intent**，這三個選項分別具有以下功能：

6. **Presence Intent**：它允許你的機器人接收有關用戶在線狀態和活動的信息，例如他們正在玩什麼遊戲或在線時間

8. **Server Members Intent**：允許您的機器人接收有關服務器成員的信息，例如成員加入或離開服務器。例如YeeCord的進入退出歡迎訊息就會需要這個

10. **Message Content Intent**：這項目會允許機器人接收訊息內容、附件、嵌入和其他組件、物件。如果沒有勾這個項目，則當收到事件呼叫時，這些地方不會被回傳，而是回傳空值

其實你不需要知道這些東西

這三個項目是補充的，因為DCSRV會需要這些東西，所以我習慣上三個都會開。因為想到有些人相對比較謹慎，所以我列出來給大家參考，需要的話可以用。

這是Bot的頁面，再來的事情就更重要了，請小心翼翼操作喔！首先先把三個特權網關意圖（上面那三個勾勾）勾上，以防之後DCSRV需要權限卻沒給夠，因為要重啟才能解決，真的是有夠難伺候...

下一步，請點擊上面的Reset Token以重設你的Token。再提醒一次絕對死也不要給任何人這個Token，除非你想被炸服...Token格式大概會像這樣：`MjE5NTE5Oxxxxxxxxxxxxxxx.xxxxxx.xxxxxxxxxxxxxxxxx-xxxxxxxxx`

這個是DCSRV官網上的Token範例

這是DCSRV上的Token範例。我相信他們一定已經重設Token了（只是如果你們也要寫文章介紹，絕對不要像這樣，這是不好的示範！）

保護好Token

我還是要提醒一次，這是TOKEN，不要給別人除非你欠炸服...

千萬記得，**把這串Token作為你的密碼保管，絕對不要讓任何人（包括任何願意幫妳寫插件的人、甚至是我！）**，如果讓任何人知道了，代表他可以在你的DC群中為所欲為！！

完美，現在把你記下來的Token貼到 DCSRV 的配置文件中token的部分，請記得**貼上後要重啟伺服器才會套用，我有在中文化版本中提示這一點！**

然後請千萬不要忘記把機器人邀進你的群組中，否則沒用喔！邀請方法如下：

```
https://discord.com/oauth2/authorize?scope=bot+applications.commands&permissions=8&client_id={APPLICATION ID}
```

如上是DC機器人的標準邀請格式，這個格式會提供機器人完全管理的權限。你可以**直接給最高權限**，DiscordSRV是開源的，因此你大可以不必擔心機器人會炸你的群；但記得，**絕對不要給任何人Token**，因為人腦並不開源，所以你給別人Token你不知道他會不會炸你群！

## 打開Discord開發者模式

為甚麼要開這個模式呢？因為我們待會會需要取得你DC伺服器中某些頻道的專屬ID，因此請照這段說明開啟開發者模式

專屬ID

Discord允許建立兩個相同名稱的頻道、且頻道允許其他非英文的字符串，因此 DCSRV 不能透過頻道名稱來指定設定的頻道。因此他會透過每個頻道專屬的單一識別碼（頻道ID，Channel ID）來分辨該發送訊息到哪裡

先點左下角的設定，前往進階>開發者模式，並開啟該項目：

[![](/images/discordsrv-guide/image-2-1024x936.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-2.png)

然後回到你要同步的DC伺服器，建立一個頻道或選擇現有的頻道做為Discord同步頻道（請記得你有把機器人加入這個伺服器喔），右鍵選擇複製頻道ID：

<figure>

[![](/images/discordsrv-guide/image-3.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-3.png)

<figcaption>

複製ID~~

</figcaption>

</figure>

你會得到一組類似這樣的十九位亂碼數字（直接Ctrl+V可以貼上喔）：`1186330639121780736`（[白狼生存服](https://discord.gg/RfFzb5ngGR) > 白狼同步頻道），這串代碼就指向你的同步頻道。現在我們要設定Discord同步的頻道，因此你未來的聊天同步都會出現在這裡。

## 配置插件

### 基礎聊天頻道與終端頻道

找到以下代碼所在的位置，我會說明它們的配置方法與功能：

```
# 從遊戲到Discord的頻道鏈接
# 語法為 Channels: {"來自Minecraft的遊戲中頻道名稱": "來自Discord的數字頻道ID", "來自Minecraft的另一個遊戲中頻道名稱": "來自Discord的另一個數字頻道ID”}
#
# DiscordSRV的所有消息將轉到第一個通道，除非為該消息定義了一個通道:
# 使用兼容的聊天插件之一時，頻道名稱將來自該插件（用於聊天消息）
#  - 如果您使用的是TownyChat，則默認頻道通常稱為"general"而不是"global"
# 用於播放器聊天消息（不使用聊天插件時）: global
# 用於服務器啟動/停止消息: status
# 成就/進階訊息編號: awards
# 死亡消息: deaths
# 加入消息: join
# 留言留言: leave
# 用於dynmap消息: dynmap
# 用於看門狗消息: watchdog
# 用於/discord broadcast: broadcasts（除非在命令中指定）
# 帳戶鏈接: link
#
# "頻道對的第一部分不是Discord頻道名稱！
# 更改此選項並運行“/discord reload”以應用
Channels: {"global": "000000000000000000"}

# 控制台頻道ID,留白表示不使用
DiscordConsoleChannelId: "000000000000000000"

# 使用 /discord 時顯示給玩家的邀請鏈接，以及執行鏈接時顯示給未鏈接的玩家的消息
DiscordInviteLink: "https://discord.gg/changethisintheconfig.yml"
```

- **Channels**：這是一個字典型別，我會給大家一些常用的類別在底下，如果你希望一個**聊天頻道同時出現加入退出死亡與聊天同步等的訊息**，不用特別改，把**"global"後面的那些0換成你剛剛複製的頻道ID**即可

- **DiscordConsoleChannelId**：一串字串，這個功能可以讓你將Discord群組中一個頻道作為指令輸入區，直接用聊天的方式傳送指令，並會把終端輸出的內容同步到這個頻道。啟用功能只要建立一個相對應的頻道（請記得一定**只有管理員可以用，不能給一般玩家看**喔！）並將它的ID貼上到這裡即可

- **DiscordInviteLink**：DC群的邀請連結，請記得指定，玩家使用`/discord`會出現這個連結

以下附上常見的Channels分類：

#### 分開系統訊息與聊天

```
# 請把000000000000000000設為希望的聊天同步頻道，xxxxxxxxxxxxxxxxxxx則一致設為系統訊息頻道
Channels: {"global": "000000000000000000", "status": "xxxxxxxxxxxxxxxxxxx", "awards": "xxxxxxxxxxxxxxxxxxx", "deaths": "xxxxxxxxxxxxxxxxxxx", "join": "xxxxxxxxxxxxxxxxxxx", "leave": "xxxxxxxxxxxxxxxxxxx"}
```

#### 分開DC帳號綁定頻道

```
# 請把000000000000000000設為希望的聊天同步頻道，xxxxxxxxxxxxxxxxxxx則設為綁定頻道
Channels: {"global": "000000000000000000", "link": "xxxxxxxxxxxxxxxxxxx"}
```

這是我常用的兩種格式，私心分享給大家！不過提醒各位，DC綁定預設不會開，我待會才介紹怎麼開喔~

### WebHook

如果你想做到像這樣的效果，你需要使用WebHook功能。以下是WebHook的相關功能，它應該在配置檔案的第81行開始（如果你用我的中文版）

<figure>

[![](/images/discordsrv-guide/image-4.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-4.png)

<figcaption>

這個功能可以用WebHook得到

</figcaption>

</figure>

```
# Webhook
Experiment_WebhookChatMessageDelivery: false
Experiment_WebhookChatMessageUsernameFormat: "%displayname%"
Experiment_WebhookChatMessageFormat: "%message%"
Experiment_WebhookChatMessageUsernameFromDiscord: false
Experiment_WebhookChatMessageAvatarFromDiscord: false
Experiment_WebhookChatMessageUsernameFilters: {}

# 嵌入和 webhook 圖片/頭像 url 格式
# 離線伺服器的替代嵌入頭像網址:
# https://cravatar.eu/helmavatar/{username}/{size}.png#{texture}
AvatarUrl: https://api.creepernation.net/avatar/{uuid}

# Reserializer
# 轉換格式，例如 Minecraft和Discord之間的粗體，斜體，下劃線
Experiment_MCDiscordReserializer_ToDiscord: false
Experiment_MCDiscordReserializer_ToMinecraft: false
Experiment_MCDiscordReserializer_InBroadcast: false
```

- **Experiment\_WebhookChatMessageDelivery**：布林值，代表是否啟用這項功能，這個不設成`true`其他不用玩

- **Experiment\_WebhookChatMessageUsernameFormat**：玩家帳號的格式，你可以用PlaceholderAPI的格式設定，想了解的可以留言問我

- **Experiment\_WebhookChatMessageFormat**：玩家聊天的訊息，如果你希望像我給的圖片一樣訊息前面會有一條線（引用），請在`%message%`前面加上`>` （後面有空白）

- **Experiment\_WebhookChatMessageUsernameFromDiscord**：如果玩家有綁定自己的Discord帳號，要不要改成顯示玩家的DC帳號而非MC帳號？

- **Experiment\_WebhookChatMessageAvatarFromDiscord**：跟上面類似，但上面決定是否顯示DC帳號，這個則是決定是否將頭像也換DC頭像

- **Experiment\_WebhookChatMessageUsernameFilters**：這算是一種過濾器，不太重要大可不用管

- **Avatar**：玩家的頭像，通常會搭配聊天API。以下是各種配置方式的效果

- **Experiment\_MCDiscordReserializer\_ToDiscord**：將MC聊天格式轉換成DC聊天格式，建議可以直接開啟

- **Experiment\_MCDiscordReserializer\_ToMinecraft**：將DC聊天格式轉換成MC聊天格式，建議可以直接開啟

- **Experiment\_MCDiscordReserializer\_InBroadcast**：轉換廣播的格式，建議可以直接開啟

你希望玩家頭像是怎麼樣呢？以下是各種設定方式，可以直接將連結複製進**AvatarUrl**項目中：

![](/images/discordsrv-guide/150.png)

#### 純玩家頭像

```
https://api.creepernation.net/avatar/{uuid}
```

![](/images/discordsrv-guide/100.png)

#### 玩家頭顱

```
https://mineskin.eu/headhelm/{username}/100.png
```

![](/images/discordsrv-guide/100.png)

#### 玩家全身

```
https://mineskin.eu/armor/body/username}/100.png
```

![](/images/discordsrv-guide/100.png)

#### 胸像

```
https://mineskin.eu/armor/bust/{username}/100.png
```

![](https://mineskin.eu/skin/Sam510208)

#### Skin原始檔

```
https://mineskin.eu/skin/{username}
```

（痾...最後一個是湊數的吧？）

### Discord機器人狀態

你想讓機器人顯示"正在玩你的伺服器"之類的訊息嗎？請在這邊設定吧！

```
# 遊戲訊息
# 為機器人設定「正在播放：______」指示器。
# 可以是單一靜態值，也可以循環使用多個不同的選項
# 您可以在狀態前加上「正在播放」、「正在觀看」或「正在聆聽」來設定活動類型
# 支援PlaceholderAPI佔位符
#
# DiscordGameStatus：要顯示的文字。可以是單一值，例如“Minecraft”，或多個值，例如[“我的世界”，“yourip.changeme.com”]
# DiscordOnlineStatus：要顯示的活動狀態。必須是以下其中之一：ONLINE, DND, IDLE or INVISIBLE分別代表在線、免受打擾、空閒或不可見
# StatusUpdateRateInMinutes：循環狀態的頻率
DiscordGameStatus: ["Minecraft"]
DiscordOnlineStatus: ONLINE
StatusUpdateRateInMinutes: 2
```

- **DiscordGameStatus**：機器人在玩甚麼遊戲，你可以設定`Minecraft`，或是`你的伺服器名稱`喔~~

<figure>

[![](/images/discordsrv-guide/image-5.jpg)](http://samhacker-local.local/wp-content/uploads/2024/06/image-5.jpg)

<figcaption>

黃框處

</figcaption>

</figure>

- **DiscordOnlineStatus**：機器人的上線狀況，上圖中頭像旁邊的綠點就是這個設的，可以設定成以下內容：
    - **ONLINE**：在線上，綠點
    
    - **DND**：禁止打擾，紅點
    
    - **IDLE**：閒置，黃色月亮
    
    - **INVISIBLE**：隱藏，灰色中空圓點

- **StatusUpdateRateInMinutes**：循環狀態的頻率，基本不用改它

### PlayerList

它會顯示在線上的玩家列表，以下是配置

```
DiscordChatChannelListCommandEnabled: true
DiscordChatChannelListCommandMessage: "playerlist"
DiscordChatChannelListCommandExpiration: 10
DiscordChatChannelListCommandExpirationDeleteRequest: true
```

- **DiscordChatChannelListCommandEnabled**：是否啟用，建議直接`true`

- **DiscordChatChannelListCommandMessage**：怎麼調出玩家列表，預設就好除非你想改

- **DiscordChatChannelListCommandExpiration**：多久會刪除訊息？預設十秒鐘

- **DiscordChatChannelListCommandExpirationDeleteRequest**：是否把先前發指令的人的訊息也刪掉，建議true

如果你希望像這樣美美的，而不是一大串文字，且聽下回分解...

[![](/images/discordsrv-guide/image-5.png)](http://samhacker-local.local/wp-content/uploads/2024/06/image-5.png)

### 帳戶連接

如果你希望玩家加入要先綁定DC帳號，請開啟插件目錄下的`linking.yml`，這不是在`config.yml`設定喔！

```
# DiscordSRV | 翻譯者: 510208
#
Require linked account to play:
  Enabled: false

  # 如果您不知道這些是什麽意思，請不要觸摸它們
  #
  # 加入監聽器的優先級
  # 按照從頭到尾的順序，可用值為LOWEST，LOW，NORMAL，HIGH，HIGHEST
  # 您可能需要將此優先級更改為更高的優先級，以在DiscordSRV拒絕播放器之前將其插入播放器
  Listener priority: LOWEST
  # 帳號連接模組應監聽並禁止登錄的事件
  # 一些白名單插件使用AsyncPlayerPreLoginEvent（很好），一些使用PlayerLoginEvent（不好）
  Listener event: AsyncPlayerPreLoginEvent
  #
  # 如果您不知道這些是什麽意思，請不要觸摸它們

  # Minecraft IGN始終允許，忽略播放器是否連結或訂戶
  Bypass names: [Scarsz, Vankka]
  # 如果 Vanilla 白名單上的玩家不需要連接其帳戶或具有子角色
  Whitelisted players bypass check: true
  # 是否讓 Vanilla 禁止名單中的玩家能夠連接其帳戶
  Check banned players: false
  # 不在 Vanilla 黑名單中的玩家是否會繞過連結其帳戶/具有子角色的需要
  Only check banned players: false

  # 提示玩家連結其帳戶的消息
  # 使用{BOT}作為機器人名稱的占位符
  # 使用{CODE}作為占位符，以占人DM機器人所需的代碼
  # 使用{INVITE}作為人們加入Discord服務器所需的邀請連結的占位符，使用config.yml中配置的DiscordInviteLink
  Not linked message: "&7您必須連接您的&9Discord&7帳戶才能玩。\n\n&7將僅包含&b{CODE}&7的DM發送到Discord服務器中的&b{BOT}&7，以連結您的帳戶。\n\n&7Discord邀請 » &b{INVITE}"

  # 如果啟用，玩家不僅需要關聯其帳戶，還需要
  # 成為該機器人所在的Discord服務器的成員。
  #
  # 可接受的格式:
  #   true/false: 關聯帳戶必須至少位於該漫遊器所在的一台Discord服務器中
  #     前: true
  #   <服務器ID>: 關聯帳戶必須位於給定的Discord服務器中
  #     前: 135634590575493120
  #   [<服務器ID>，<服務器ID>，...]：連結帳戶必須位於所有給定的Discord服務器中
  #     前: [135634590575493120, 690411863766466590]
  #
  # 當您在下面強制執行了訂戶角色時，此選項的值將被取代。
  Must be in Discord server: true

  #（可選）要求人們不僅要連結，而且要擁有一個或所有指定角色（例如Twitch子角色）中的一個
  Subscriber role:
    Require subscriber role to join: false
    Subscriber roles: ["00000000000000000", "00000000000000000", "00000000000000000"]
    Require all of the listed roles: false # 如果為false，則僅需要上述角色之一
    Kick message: "&c您必須訂閱Twitch才能玩。"

  Messages:
    DiscordSRV still starting: "&c當前無法檢查帳戶連結狀態，因為服務器仍在連接到Discord。\n\n請稍後重試。"
    Not in server: "&c您目前不屬於我們的Discord服務器。\n\n加入{INVITE}！"
    Failed to find subscriber role: "&c在Discord上找不到任何訂戶角色。\n\n有關此問題，請與您的服務器管理員聯系。"
    Failed for unknown reason: "&c嘗試驗證您的帳戶時發生錯誤。\n\n有關此問題，請與您的服務器管理員聯系。"
    Kicked for unlinking: "&c您因取消帳戶關聯而被踢出服務器。\n\n請重新加入服務器以再次連結您的帳戶。"
```

這我就直接把所有配置貼上了，反正幾十行而已

- **Enabled**（第四行）：是否強制玩家要綁定DC帳號，如果設定False玩家也可以用/discord link連帳號喔（記得給權限）

- **Check banned players**：被BAN的玩家是否可以連接DC帳戶，不要比較好吧...

以上兩個是基本需要設定的東西，其他保持預設就好不用特別改。其實真的要改的也就Enabled改True，另一個你可以當成我想不到放甚麼又不想太寒酸才放的...

## DiscordSRV的外掛：ICD與IC

### Interactive Chat（IC）

你希望聊天欄中出現更多有趣的東西嗎？想想看，你可以在聊天欄中輸入`[<指令>]`來讓別人直接點擊執行該指令，交易的時候是不是很方便？在聊天中輸入色碼、粗體、斜體...把你的MC變成Discord？甚至你可以直接用`[money]`炫炫富、用`[ping]`顯示你的延遲，還可以用`[world]`顯示你身在何處？最棒的是，他們可以同步到DC群組！

不用想像，這些正是IC做到的事情，安裝好IC之後還沒完，還有ICD喔！

[Interactive Chat](https://www.spigotmc.org/resources/interactivechat-show-items-inventory-in-chat-custom-chat-keywords-bungee-velocity-support.75870/)

### IC Discord Addon（ICD、ICDA）

IC沒辦法跟DCSRV同步，那是你不會用！使用ICD就可以串接IC與DCSRV，讓DC群一起出現包包內容、憶起出現你的位置，甚至是你剛做好的新武器！

<figure>

[![](/images/discordsrv-guide/image-6.jpg)](http://samhacker-local.local/wp-content/uploads/2024/06/image-6.jpg)

<figcaption>

秀出你的背包吧！

</figcaption>

</figure>

<figure>

[![](/images/discordsrv-guide/image-6-1.jpg)](http://samhacker-local.local/wp-content/uploads/2024/06/image-6-1.jpg)

<figcaption>

還有作好的超讚裝備

</figcaption>

</figure>

[ICD下載點](https://www.spigotmc.org/resources/interactivechat-discordsrv-addon-show-items-and-invs-on-discord-preview-discord-/images/discordsrv-guide-in-game.83917/)

其實把兩個裝好之後就可以了，配置的部分我正在為它們中文化，大家可以期待一下~~如果你想自己中文化，反正看到英文就翻譯就好~~

## 權限設定

你以為逃得掉嗎？該來的遲早會來...配置玩了以後就是快樂的LP時間啦~如果你還不知道LP的話，記得去複習一下：[Minecraft開服之路：最初的開始 – 權限設定插件](http://samhacker-local.local/2024/05/02/mcserver-2-luckperms/)

<figure>

| 節點 | 說明 | 建議擁有者 |
| --- | --- | --- |
| `discordsrv.player` | 所有一般玩家該有的權限，你直接設定LP上`discordsrv.player.*`、`discordsrv.player`為True就可以解決了...把這個訂為true跟以下項目通通訂為true是一樣意思：  
`discordsrv.chat`、`discordsrv.help`、`discordsrv.link`  
、`discordsrv.linked`、`discordsrv.discord`、  
`discordsrv.nicknamesync` | 一般玩家 |
| `discordsrv.admin` | 所有管理員該有的權限，你直接設定LP上`discordsrv.admin.*`、`discordsrv.admin`為True就可以解決了 | OP |

<figcaption>

[https://docs.discordsrv.com/permissions](https://docs.discordsrv.com/permissions)有更多說明

</figcaption>



</figure>

抱歉啦，因為之前翻譯插件翻太久了，所以我這邊就水一下，希望各位原諒我啦...隔了好久我想快點發新文章啦><對不起大家...

## 指令表

<figure>

| 指令 | 說明 | 對應權限節點 |
| --- | --- | --- |
| **/discord** | 顯示Discord伺服器的邀請網址 | discordsrv.discord |
| **/discord help、/discord ?** | 顯示指令列表 | discordsrv.help |
| **/discord link** | 使用Discord帳戶連結至Minecraft帳戶 | discordsrv.link |
| **/discord unlink** | 刪除Minecraft和Discord帳戶之間的連結 | discordsrv.unlink |
| **/discord linked** | 顯示有關連結狀態的資訊 | discordsrv.linked |
| **/discord broadcast** | 向Discord廣播文字 | discordsrv.bcast |
| **/discord setpicture** | 設置機器人的頭像 | 忘了...discordsrv.admin裡面 |
| **/discord debug** | 將除錯資訊發送給Gist | discordsrv.debug |
| **/discord reload** | 重新載入插件 | discordsrv.reload |
| **/discord resync** | 重新同步Slash指令等 | discordsrv.resync |

<figcaption>

一般玩家指令表

</figcaption>



</figure>

<figure>

<table><tbody><tr><td><strong>/discord resync</strong></td><td>重新同步Slash指令等</td><td>discordsrv.resync</td></tr><tr><td><strong>/discord broadcast</strong></td><td>向Discord廣播文字</td><td>discordsrv.bcast</td></tr><tr><td><strong>/discord setpicture</strong></td><td>設置機器人的頭像</td><td>忘了...discordsrv.admin裡面</td></tr><tr><td><strong>/discord debug</strong></td><td>將除錯資訊發送給Gist</td><td>discordsrv.debug</td></tr><tr><td><strong>/discord reload</strong></td><td>重新載入插件</td><td>discordsrv.reload</td></tr></tbody></table>

<figcaption>

管理員指令表

</figcaption>



</figure>

## 結語

很高興我總算更新文章了，大家期不期待w。結果好像還是沒啥人要看我的部落格，但其實這邊才是最快出現文章的地方，巴哈的文章算Blog的簡略版喔~~歡迎大家來這邊逛啦w

如果喜歡我的文，拜託底下有一個拍手，Google帳戶登入拍手不用幾秒鐘，按五下就好了，很舒壓唷~~聽說有按的人不用宣傳伺服器也一堆玩家喔...
