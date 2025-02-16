---
title: "五分鐘打造屬於你的隨身Minecraft，隨時隨地即插即用！"
published: 2024-09-17
categories: 
  - "minecraft-tips"
tags: 
  - "minecraft"
  - "免安裝"
  - "密技"
  - "技巧"
image: "/images/5min-java-portable/samhackerblog_5min-java-editon_2_thumbnail.png"
---

當你外出旅行、換了電腦、又或者學校電腦課想要偷玩麥塊時，你是不是曾經想過，如果可以把你的 Minecraft 隨身 帶著走，只要插上電腦就可以立刻開完該有多好？但光是下載遊戲就要好幾分鐘，還要把自己麥塊的世界搬來搬去的、如果你需要特殊的模組還要全部重載一遍，是不是很痛苦？再加上如果是借別人電腦玩，玩完了還要怕帳號會被盜用、或朋友不讓你裝軟體在他電腦？本篇文章將要教你怎麼隨身把你的Minecraft 隨身 帶著走，只需要把USB插上電腦，一鍵就可以開始玩了！

## Minecraft 依賴哪些元件

本文主要會以Java Editon舉例，這個版本的遊戲是基於Java程式的，因此移動會比基岩版便利，相依性元件也比較少。你會需要 隨身 帶著走的有：

### 隨身碟（USB）

隨身碟是用來承擔你的麥塊的工具，所以一定要有。這種USB最低一定要有4GB以上可用空間，一般一個Minecraft實例如果用Prism的隔離模式啟動，平均會吃上1GB左右。因此建議至少要有8GB比較可以玩的久。當然如果你有行動硬碟之類的最好，但請一定要記得USB至少要是3.0以上，你用2.0保證會慢到你懷疑人生ww

<figure>

[![](/images/5min-java-portable/samhackerblog_5min-java-editon_1.jpg)](http://samhacker-local.local/wp-content/uploads/2024/09/samhackerblog_5min-java-editon_1.jpg)

<figcaption>

USB 3.0街口（來源：[File:USB 3.0 A Buchse 13.jpg - Wikimedia Commons](https://commons.wikimedia.org/wiki/File:USB_3.0_A_Buchse_13.jpg)）

</figcaption>

</figure>

### 啟動器

Minecraft啟動器可以協助你啟動自己的麥塊，並幫助你產生啟動遊戲的指令。但大部分都是安裝版本，因此你會需要一個第三方（官方又不提供免安裝的）啟動器，用來幫助你在任何電腦啟動遊戲。本文會推薦一款頗具盛名的啟動器：稜鏡啟動器[Prism Launcher](https://prismlauncher.org/)。如果你有其他喜歡的啟動器，也可以去官網看看它是否有免安裝版本喔！

<figure>

[![](/images/5min-java-portable/samhackerblog_5min-java-editon_2-1024x555.jpg)](http://samhacker-local.local/wp-content/uploads/2024/09/samhackerblog_5min-java-editon_2.jpg)

<figcaption>

Prism主介面

</figcaption>

</figure>

### Java執行環境

顧名思義，Minecraft Java Editon當然是Java寫的遊戲，所以你一定會需要在電腦裝Java才能玩（廢話），官網沒有

<figure>

[![](/images/5min-java-portable/images/samhackerblog_5min-java-editon_3.jpg)](http://samhacker-local.local/wp-content/uploads/2024/09/samhackerblog_5min-java-editon_3.jpg)

<figcaption>

免安裝Java的檔案清單

</figcaption>

</figure>

## 下載免安裝版Java

首先當然是先把準備好的USB插入電腦裡面，我用的是一支威剛的32GB USB，事前已經格式化成NTFS格式了

再來要前往Java官網下載Java，如果你玩的是1.12~1.17，至少需要Java 8；1.17開始就需要最少Java 16；從1.18（1.18-pre2）開始，執行Minecraft的最低要求是Java 17；而如果是1.20.5（24w14a）開始，執行Minecraft的最低要求是Java 21，且**作業系統要求為64位元**（以上資料來自[Minecraft Wiki](https://minecraft.fandom.com/zh/wiki/Java%E7%89%88?variant=zh-tw)），因此建議可以直接下載21版的Java。

STEP

下載Java 21 for Windows（免安裝版）

如果要做到極致的免安裝，當然是不能用安裝版的Java囉。以下是安不安裝Java的差別

| Java免安裝版 | Java安裝版 |
| --- | --- |
| 因為安裝在USB裡面，執行速度會受到USB街口限制 | 安裝在本機，硬碟速度夠快的話其實可以很順 |
| 不用安裝，比較省事 | 要安裝，會更麻煩 |

[Java官網下載點](https://www.oracle.com/tw/java/technologies/downloads/#jdk21-windows)

下載適合你的檔案

[![](/images/5min-java-portable/images/samhackerblog_5min-java-editon_4-1024x458.png)](http://samhacker-local.local/wp-content/uploads/2024/09/samhackerblog_5min-java-editon_4.png)

STEP

解壓免安裝檔案

我會使用免安裝版本，因此下載下來會是一個Zip檔案，將它用WinRAR或其他解壓軟體解壓到USB底下你想放麥塊的目錄。裡面的檔案都是需要的，所以請乖乖等它解壓完吧！解壓出來的檔案大小約為300多MB

STEP

去蕪存菁

根目錄下的README、LICENSE兩個檔案都不需要，只是它們也不大，所以不一定要刪掉。其他東西就不能亂動了...就這樣吧

## 下載並初始化Prism Launcher

前往以下網站下載Prism啟動器，直接選Windows 10/11 64bit底下的Portable，下載下來一樣解到USB下，跟Java同目錄就好。此時你的USB會有java的資料夾跟prism資料夾

[Prism Launcher](https://prismlauncher.org/download/windows/)

### 將Java移動至Prism資料夾

在Prism安裝資料夾底下建立一個名叫`javaportable`的資料夾（你可以隨便命名，但最好是英文的才不會出一堆問題），現在你的資料夾架構長這樣：

```
PrismLauncher
├─catpacks
├─iconengines
├─icons
├─iconthemes
├─imageformats
├─instances
├─jars
├─javaportable
│  ├─bin
│  ├─conf
│  ├─include
│  ├─jmods
│  ├─legal
│  └─lib
├─logs
├─platforms
├─styles
├─themes
├─tls
└─translations
(我只有放資料夾而已)
```

### 對啟動器執行初始設定

STEP

選擇語言

我就用繁體中文做示範囉~~

[![](/images/5min-java-portable/images/samhackerblog_5min-java-editon_6-1.jpg)](http://samhacker-local.local/wp-content/uploads/2024/09/samhackerblog_5min-java-editon_6-1.jpg)

STEP

Java設定

這裡請指向剛剛的免安裝Java，前面不要有硬碟名稱。如果你都照我剛剛給的指示做的話，你應該在路徑欄填入以下文字：

```
javaportable/bin/javaw.exe
```

[![](/images/5min-java-portable/images/samhackerblog_5min-java-editon_7.jpg)](http://samhacker-local.local/wp-content/uploads/2024/09/samhackerblog_5min-java-editon_7.jpg)

記憶體的限制部分就請各位自己看看，或是直接用預設，我個人會建議至少要有2GB，最多分實體記憶體一半過去就好

第三個設定其實可以不用動，就這樣進到Prism主介面即可

## 登入Prism啟動器

左上角帳號>管理帳號，因為我有正版就用"新增Microsoft帳號"，然後會跳出一個網頁，在網頁上登入即可

<figure>

[![](/images/5min-java-portable/images/samhackerblog_5min-java-editon_８.jpg)](http://samhacker-local.local/wp-content/uploads/2024/09/samhackerblog_5min-java-editon_８.jpg)

<figcaption>

他需要的權限我寫在上面了，基本上沒有甚麼奇怪的，而且Prism也是開源的專案，所以可以直接接受

</figcaption>

</figure>

<figure>

[![](/images/5min-java-portable/images/samhackerblog_5min-java-editon_9.jpg)](http://samhacker-local.local/wp-content/uploads/2024/09/samhackerblog_5min-java-editon_9.jpg)

<figcaption>

這樣就可以了

</figcaption>

</figure>

## 匯入現有的實例

本方式已過時，不保證有用

如果你想要匯入現有的實例，可以在底下匯入實例失敗的部分看看詳細的說明

[快速跳轉吧！](#h-import-instant-wrong)

在Minecraft中，實例代表一個麥塊版本。原版啟動器的實例預設會全裝在C槽的目錄中，如果你想前往，可以使用Win+R叫出執行對話框，輸入以下文字開啟麥塊預設安裝的資料夾：

```
%appdata%/.minecraft
```

以下附上一些著名啟動器的實例路徑：

### HMCL（Hello Minecraft Launcher）

HMCL的實例預設會跟HMCL主程式是一樣的路徑下的.minecraft資料夾

### Prism Launcher

如果你先前就已經在使用Prism，可以在以下部分開啟實例資料夾。或是在Prism的安裝目錄底下的`instances`資料夾看到所有實例

[![](/images/5min-java-portable/images/samhackerblog_5min-java-editon_10.jpg)](http://samhacker-local.local/wp-content/uploads/2024/09/samhackerblog_5min-java-editon_10.jpg)

### CurseForge App

CurseForge App本身並不帶有啟動器功能，他調用的是原版的啟動器，因此路徑也跟原版一樣是`%appdata%/.minecraft`

### PCL（Plain Craft Launcher）

PCL跟HMCL類似，但PCL預設路徑使用的是官方的路徑，所以也是那一串，我就不多贅述了...

### MultiMC

這款是Prism Launcher的前身，因此方法也跟隔壁棚Prism一樣

### TLauncher

預設資料夾也跟原版一樣，不想說明好麻煩...

### XMCL

XMCL也是一款由對岸中國人開發的啟動器，預設儲存路徑會在

```
C:\Users\%username%\.xmcl
```

這個資料夾中，其中`%username%`代表的是電腦的使用者名稱

這裡面會存著以實例名稱為名的一堆資料夾，假設你要複製的實例名為a

如果要匯入你原有的實例，請照以下步驟：

STEP

進入instances資料夾中建立instgroups.json

如標題所示，這個檔案用記事本建立即可，建立完後在裡面輸入以下文字：

```
{
    "formatVersion": "1",
    "groups": {
    }
}
```

STEP

建立一個資料夾，資料夾名稱就是要複製的實例名稱

就如標題所言

STEP

在第二步建立的那個資料夾底下建立一個新資料夾，資料夾名為`.minecraft`

這樣一來，你的資料夾會像這樣：

```
instances
├─a
│  └─.minecraft
└─instgroups.json
```

STEP

在資料夾中建立`instance.cfg`檔案

檔案內容放這個，記得name=a的a要換成你來源實例名稱

```
[General]
ConfigVersion=1.2
iconKey=default
name=a
InstanceType=OneSix
ExportAuthor=
ExportName=
ExportOptionalFiles=true
ExportSummary=
ExportVersion=1.0.0
JoinServerOnLaunch=false
LogPrePostOutput=true
ManagedPack=false
ManagedPackID=
ManagedPackName=
ManagedPackType=
ManagedPackVersionID=
ManagedPackVersionName=
OverrideCommands=false
OverrideConsole=false
OverrideEnv=false
OverrideGameTime=false
OverrideJavaArgs=false
OverrideJavaLocation=false
OverrideLegacySettings=false
OverrideMemory=false
OverrideMiscellaneous=false
OverrideNativeWorkarounds=false
OverridePerformance=false
OverrideWindow=false
Profiler=
UseAccountForInstance=false
lastLaunchTime=0
lastTimePlayed=113
linkedInstances=[]
notes=
totalTimePlayed=113
```

STEP

複製原本的遊戲內容

把原有實例資料夾裡所有檔案通通複製進.minecraft中，然後將根目錄下會有一個jar和一個json檔案，兩個檔案的名稱都會跟原有實例資料夾名稱相同。因此只要照著用就好，如下：

```
instances
│  instgroups.json
└─1.21
    │  instance.cfg
    └─.minecraft
        │  1.21.jar
        └─ 1.21.json
```

STEP

打開啟動器

對，打開啟動器就好囉~~

如以上步驟，就可以完成了！

<figure>

[![](/images/5min-java-portable/images/samhackerblog_5min-java-editon_11.jpg)](http://samhacker-local.local/wp-content/uploads/2024/09/samhackerblog_5min-java-editon_11.jpg)

<figcaption>

（然後我說你USB可以再給我慢一點沒關係喔...）

</figcaption>

</figure>

喔教大家一個麥塊冷知識，以下是你麥塊一個實例裡面資料夾的架構：

```
Easy Optimization 1.21_v3
│  command_history.txt                   // 上次世界使用的所有指令列表
│  Easy Optimization 1.21_v3.jar         // 主程式(檔案名稱會跟資料夾名稱一樣)
│  Easy Optimization 1.21_v3.json        // 麥塊的配置(檔案名稱會跟資料夾名稱一樣)
│  hmclversion.cfg                       // 我這個實例是用HMCL建立的
│  icon.png                              // 實例的圖示
│  options.txt                           // 實例的所有設定，如鍵盤設定、畫質、音效等
│  realms_persistence.json               // Realms伺服器配置
│  servers.dat                           // 記錄你玩的所有伺服器
├─config                                 // 模組設定檔*
├─crash-reports                          // 崩潰回報，麥塊掛掉的話會存原因在這裡
├─debug                                  // 這裡會存麥塊錯誤的紀錄
├─downloads                              // 下載資料夾，主要是存麥塊伺服器要求的材質包之類的
├─logs                                   // 除錯用的，這是麥塊的紀錄檔案
├─mods                                   // 模組資料夾
├─replay_recordings                      // Replay Mod的資料夾，沒有裝這個模組的話不會有
├─resourcepacks                          // 資源包，a.k.a. 材質包
├─saves                                  // 單人世界存檔
├─schematics                             // 藍圖存檔，安裝Litematica才會有
├─screenshots                            // 截圖，遊戲中按下F2截下來的圖會放這裡
└─shaderpacks                            // 光影包，
                                         // 有裝像Iris(Fabric)、OptiFine(Forge)等光影模組
                                         // 就會創建這個資料夾
```

因此如果你世界太大的話，基本上你只需要複製以下資料夾與檔案：

- **主程式的Jar與Json配置檔案**：這不扛走你玩啥麥塊

- **icon.png**：看你

- **options.txt**：如果你要同步原本的鍵位設定的話

- **servers.dat**：所有你建立的多人伺服器都存這裡，如果你像我一樣常玩伺服器這個建議也一起帶走

- **config**：裡面是所有模組的設定，我一般會留著

- **downloads**：之後遊玩過程中也會自己生回來，除非你不想下次進伺服器再重載，否則不一定要複製這個

- **mods**：模組，一定要複製走，有玩模組的話

- **resourcepacks**：材質包，也一起帶走吧，除非你沒裝

- **saves**：想帶走世界的話也一起摳

- **schematics**：有玩藍圖的話也建議一起拿走

- **shaderpacks**：如果你不覺得新電腦跑得動光影可以不用拿走，我個人還是會建議一起拿

減少複製時間

如果你只把該複製的複製過去了，但還是覺得慢，以下幾招可能可以幫你快一點：

- 檢查resourcepacks、shaderpacks中是否有資料夾格式的材質包（解壓出來），如果有，那把它們分別壓成zip格式

- 將一些雜亂的檔案壓縮成壓縮檔，複製完後再解出來

- 檢查USB是否插在USB3以上的接口（USB3.0的接口與接頭內的塑膠防呆片會是藍色、USB3.1則會是紅色。如果是USB Type C的話就會是扁平的插頭，看起來很像Oracle公司的Logo）。如果否，換接USB3以上的

- 盡量減少雜亂的小檔案，USB複製一個大檔案會比一堆小檔案來的快

## 打開遊戲測試

很棒，現在你的USB製作已經好了！只要把USB插到別台電腦打開啟動器就可以直接啟動遊戲囉~~如果嫌這樣太慢也可以把整個Prism資料夾複製到電腦裡面，玩完直接把那資料夾刪掉就好囉！

### 打不開Prism Launcher？

如果打不開啟動器，有可能是你沒有安裝啟動器需要的環境。這個環境可以在下載時找到，以下附上環境安裝包連結：

[Visual C++ Redisturible Package 64位元](https://aka.ms/vs/17/release/vc_redist.x64.exe)

### 匯入實例失敗？

如果匯入實例失敗，你還可以用另一種方式把你習慣的麥塊給丟回去：

STEP

建立一個實例

在Prism中建立一個與原本實例完全相同（包括版本、Mod Loader種類等設定）的新實例

STEP

啟動一次那個實例

啟動一次該實例，來讓啟動器建立並下載所需的文件

STEP

將原本實例的資料複製到新實例

把舊實例的檔案複製進新實例，把jar檔案的檔名與json檔案的檔名都設為資料夾名稱。例如剛才建立了一個1.21實例，那就把舊實例的jar與json（如果以前面提到的那個實例的話，就是`Easy Optimization 1.21_v3.jar`與`Easy Optimization 1.21_v3.json`改成`1.21.jar`&`1.21.json`

STEP

重啟實例

重啟實例後應該就可以了

如果你原本用的是HMCL或其他支持匯出模組包的啟動器，也可以用匯出模組包的方式完成移動遊戲的作業，或是直接砍掉重練也不是不行

## 結語

恭喜你！你現在應該已經成功安裝完隨身版麥塊了，現在你可以輕鬆遊玩你的麥塊，在任何你想玩的地方。不過切記，USB真的要買支速度快一點的，不然保證你玩到懷疑人生！喔對了，如果你對其他 Minecraft 技巧有興趣，歡迎參考我寫的其他教學文章，讓你的遊戲體驗更上一層樓！
