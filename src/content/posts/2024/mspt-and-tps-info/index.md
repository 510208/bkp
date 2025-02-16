---
title: "伺服器順暢的基本常識：解讀TPS與MSPT"
published: 2024-05-23
categories: 
  - "mc-server-guide"
tags: 
  - "minecraft"
  - "伺服器"
  - "密技"
  - "技巧"
  - "比較"
  - "零程式"
image: "/images/mspt-and-tps-info/伺服器順暢的基本常識-解讀TPS與MSPT.png"
---

哈囉大家好我是SamHacker，今天並沒有要寫程式，也不是裝插件，而是我想介紹一下Minecraft伺服器效能的指標：TPS與MSPT

這篇文章可能會比較短，但我會將所有可以用來評估Minecraft伺服器順暢度的指標：TPS、MSPT及Ping

## Tick

Tick，中文譯為**遊戲刻**，是Minecraft的一種特殊遊戲架構。它控制了Minecraft大部分的遊戲機制，例如火焰延燒、傷害、建築速率、生怪等，你可以把它想像成一個時鐘，每隔一段時間通知怪物出生、通知火焰要蔓延了、通知你的手可以放方塊了...

想要知道Tick的原理，你要先知道Minecraft的絕大多數運算在一個大循環內執行，執行了一次這個循環就執行了一刻。在這一刻內，遊戲會執行定時作業來保持運行。

在單人世界裡，Tick往往由電腦本身發送，但如果開啟了多人世界、或加入伺服器，則Tick會交由伺服器統一發送，這樣才能確保所有玩家的畫面與遊戲內容都是正常的。以下是一張示意圖，表示Tick的原理

<figure>

[![](/images/mspt-and-tps-info/image-28-947x1024.png)](http://samhacker-local.local/wp-content/uploads/2024/05/image-28.png)

<figcaption>

單人與多人遊戲的Tick示意圖

</figcaption>

</figure>

## TPS（Tick Per Second）

TPS，**Tick Per Second**，中文譯名為**每秒遊戲刻數**，代表一秒鐘伺服器可以發送多少個Tick。**理想狀況下每秒發送20Tick**，也就是20TPS或TPS20。

<figure>

[![](/images/mspt-and-tps-info/image-29-1024x205.png)](http://samhacker-local.local/wp-content/uploads/2024/05/image-29.png)

<figcaption>

TPS狀態與嚴重性分段

</figcaption>

</figure>

如果伺服器開始卡頓，Tick會降到20以下。一般**在15~20TPS浮動都是正常的**，這個狀況仍然可稱為穩定，但要是**降到15以下就會有明顯動畫卡卡的，7TPS以下就會開始可感的卡頓**：挖礦會開始有延遲、也開始容易放出幽靈方塊。倘若這時候再不進行優化，讓**TPS掉到4以下，伺服器的穩定度就會開始彈動，系統可能會突然當住**。如果真的到了最糟的狀況，系統卡死了，這將會造成當前地圖檔沒有存到。最糟的狀況甚至地圖檔故障！

## MSPT（MilliSeconds Per Tick）

MSPT，**MilliSeconds Per Tick**，代表**伺服器實際用於計算一個Tick的時間，以毫秒計算**。此數據與TPS對立，也就是**如果TPS高，則MSPT就低**，反之亦然。

**理想狀況下此數據最好在50以內**，也就是50MSPT或MSPT50。如果MSPT低於50，TPS才能穩定在20運作，如果MSPT超過50，則TPS將開始下降，一般而言TPS是整數，而MSPT則有小數點。在Java版的F3除錯選單中，可以使用Alt+F3打開幀生成圖表來檢視。如果MSPT超過50則伺服器就會有延遲，超過500會感到實際延遲，倘若大於1000，那看起來伺服器準備蒙主寵召了...你會看到一道聖光，然後伺服器就打掉故障了...

<figure>

[![](/images/mspt-and-tps-info/image-31-1024x200.png)](http://samhacker-local.local/wp-content/uploads/2024/05/image-31.png)

<figcaption>

MSPT狀態與嚴重性分段

</figcaption>

</figure>

## Ping值

Ping代表客戶端發送一個訊息至伺服器，再由伺服器傳回該訊息的時間，大都以毫秒為單位：

[![](/images/mspt-and-tps-info/image-33-1024x158.png)](http://samhacker-local.local/wp-content/uploads/2024/05/image-33.png)

這個數值代表電腦連上伺服器的延遲，以毫秒計算。Ping值越高則感到越延遲，但這個項目影響的是玩家的體驗，而非伺服器效能占用量。也就是說，就算伺服器Ping值高達上萬，也不直接代表伺服器硬體被吃滿了。

主要會影響到Ping值的原因是託管商網路品質、線路不佳，或玩家的網路不好（Ping值高不一定是伺服器的問題，如果只有特定玩家Ping高可能該玩家自己網路不好，網路有木桶效應的）

網路的木桶效應

[![](/images/mspt-and-tps-info/image-32.png)](http://samhacker-local.local/wp-content/uploads/2024/05/image-32.png)

如上圖，木桶效應代表在一個木桶中，水只能裝到最矮的那塊木板中，超過了就會漏出去。

在網路中這代表網路架構會被最慢的那個硬體限制住。也就是說甭管你伺服器網路搭了幾千M的光纖，玩家網路只要太低，你的網路效能是吃不滿的...因此伺服器Ping值也有可能是因為玩家網路太差導致。

* * *

<figure>

| 項目 | TPS | MSPT | Ping |
| --- | --- | --- | --- |
| 定義 | 一秒內伺服器可發出幾個Tick（遊戲刻） | 伺服器處理一個Tick需要多久毫秒的時間 | 一個訊息從玩家到伺服器後再傳回來的時間 |
| 單位 | Tick/秒 | 毫秒/Tick | 毫秒 |
| 測量方式 | 監控伺服器端執行速度 | 監控伺服器端執行速度 | 監控網路延遲時間 |
| 可能影響因素 | **玩家：**玩家數量、玩家行為、客戶端性能、網路狀況  
**伺服器：**伺服器硬體理論性能、伺服器負載、插件、世界大小、世界複雜度 | **玩家：**玩家數量、玩家行為、客戶端性能、網路狀況  
**伺服器：**伺服器硬件性能、伺服器負載、插件、世界大小、世界複雜度 | **玩家：**網路狀況、路由、距離  
**伺服器：**伺服器端位置 |
| 反映 | 伺服器端處理遊戲世界的速度 | 伺服器端執行一個更新所需的平均時間 | 使用者端與伺服器端之間的網路延遲時間 |
| 影響因素 | 伺服器硬件性能、負載、插件等 | 伺服器硬件性能、負載、插件等 | 網路狀況、路由、距離等 |
| 理想值 | 20 TPS | 50 MSPT 以下 | 50 ms 以下 |
| 應用 | 評估伺服器性能、優化伺服器 | 評估伺服器性能、優化伺服器 | 評估網路狀況、選擇伺服器 |
| 改善方式 | 升級伺服器硬件、減少伺服器負載、[優化插件](https://www.spigotmc.org/resources/lagfixer-1-17-1-20-6-%E2%9A%A1%EF%B8%8F-best-performance-solution-%E2%AD%95-500-servers-%E2%9C%85-folia-supported.111684/) | 升級伺服器硬件、減少伺服器負載、[優化插件](https://www.spigotmc.org/resources/lagfixer-1-17-1-20-6-%E2%9A%A1%EF%B8%8F-best-performance-solution-%E2%AD%95-500-servers-%E2%9C%85-folia-supported.111684/) | 調整路由、升級網路頻寬、更換網路服務商 |

<figcaption>

比較三項因素

</figcaption>



</figure>

## 總結

今天的文章沒有涉及任何插件，但今天的內容比任何插件都更為重要。如果你在開設伺服器時不懂這些關鍵資訊，那麼和新手沒什麼區別。這些基礎知識是伺服器運行的根本，了解它們能讓你更好地管理和優化伺服器，確保玩家們獲得最佳的遊戲體驗。記住，掌握這些資訊是成為伺服器管理大師的第一步。即使沒有華麗的插件，這些基本原則依然是伺服器運行順暢的核心。
