---
title: "有了經濟要開始賣房啦：Residence建立一個屬於自己的家園"
published: 2024-08-29
categories: 
  - "mc-server-guide"
tags: 
  - "minecraft"
  - "residence"
  - "介紹"
  - "伺服器"
  - "插件"
  - "領地"
image: "/images/resisdence-plugin/我的伺服器該怎麼經營？老服主給的三種麥塊伺服器經營方向.png"
---

> 「啊~~好累，今天我的生存先到這邊，休息一下吧~~」，我邊說邊把自己身上的物品倒到家裡的箱子，然後熟練的Esc之後按了中斷連線。到了隔天我再次上線的時候，昨天剛放好的東西已經變成空了？？

你的伺服器是不是也常常發生像上面的故事一樣的闖空門事件，但又不想自己處理，結果問題一大堆，想著如果能讓玩家自己保護自己的物品就好了？如果你也有這樣的想法，那這篇文章要介紹的 領地 插件就是你的救星！

## Zrips

[Zrips](https://www.zrips.net/)，a.k.a. Residence的開發商，專門開發付費的麥塊插件，例如頗具盛名的CMI（Content Management Interface）就是他們的傑作。但不要以為這個Residence也是他們的付費產品，因為事實上...它是免費的！只是沒開源而已ww

## 安裝Residence

STEP

前往插件網站

以下附上插件的下載網址。點進網頁內後會看到要求登入，就先註冊帳號吧~~（喔對了，基本上在這個網站看到要求登入大都是付費插件）

[Residence Plugin](https://www.spigotmc.org/resources/residence-1-7-10-up-to-1-20.11480/)

STEP

下載免費版

免費版跟付費版基本上是沒有差別的，付費版是用來支持作者開發的。因此如果各位有經濟實力建議可以付費一下支持作者，大概三百多台幣而已。如果你不想付費支持，就把網站稍微往下拉到看到以下字串：

> With previous developers approval, this plugin went from free to "Premium" to help motivate the active developer and push allot more updates and bug fixes in near feature. If you don't appreciate hard work put on this plugins updates, you are welcome to download the same versions for free [here](http://zrips.net/Residence/) but he will be sad and will come to haunt you in your dreams!​

沒錯，你應該已經注意到"here"有個連結了，點進去後就是官網提供的下載連結，一般進去之後選最新版本就夠用了

<figure>

[![Residence下載連結](/images/resisdence-plugin/image.png)](http://samhacker-local.local/wp-content/uploads/2024/08/image.png)

<figcaption>

我下載時的最新版本是5.1.6.1

</figcaption>

</figure>

STEP

下載前置插件

上次遇到前置插件應該是在[XConomy](http://samhacker-local.local/2024/05/16/xconomy-guide/)那篇裡面的Vault插件，而這個Residence則是需要一款名為CMILib的插件，連結如下，這款不需要付費，可以直接下載喔~~

會提到Vault是因為...這款Residence也會需要Vault作為經濟系統的前導，簡單來講就是要先裝Vault和經濟插件（XC），Vault的部分就請回去之前那篇的說明看看吧~

[CMILib](https://www.spigotmc.org/resources/cmilib.87610/)

[Vault與XConomy](http://samhacker-local.local/2024/05/16/xconomy-guide/)

對沒錯，我裝了新的步驟流外掛了，先試用看看吧 (^\_^)

等裝完重啟後，你會看到系統多了以下幾個檔案：

```
Residence
├╴Languange            # 資料夾
├╴config.yml           # 插件主配置檔
├╴flags.yml            # 基礎權限設定相關
└╴groups.yml           # Residence身分組設定
```

## 配置領地插件（config.yml）

```
# These are Global Settings for Residence.
Global:
  # Starts UUID conversion on plugin startup
  # DONT change this if you are not sure what you doing
  UUIDConvertion: false
  # STRONGLY not recomended to be used anymore. Only enable if you are sure you want to use this
  # If you running offline server. Suggestion would be to keep this at false and base residence ownership from UUID and not on players name
  OfflineMode: false
  # Players with residence.versioncheck permission node will be noticed about new residence version on login
  versionCheck: true
  # This loads the <language>.yml file in the Residence Language folder
  # All Residence text comes from this file. (NOT DONE YET)
  Language: ChineseTW
  # Wooden Hoe is the default selection tool for Residence.
  SelectionToolId: WOODEN_HOE
  Selection:
    # By setting this to true, all selections will be made from bedrock to sky ignoring Y coordinates
    IgnoreY: false
    # When this set to true, selections inside existing residence will be from bottom to top of that residence
    # When this set to false, selections inside existing residence will be exactly as they are
    IgnoreYInSubzone: false
```

在Global下的Language，把它改成ChineseTW即可套用繁體中文，如上。下表列出一些需要修改的項目：

<figure>

| YAML鍵名（Global以下） | 類型 | 說明 | 建議值 |
| --- | --- | --- | --- |
| `versionCheck` | Boolean | 是否讓擁有`residence.versioncheck`權限節點的使用者進伺服器時看到版本資訊 | 看你狀況，不介意的話就直接預設用下去吧 |
| `Languange` | String | 設定插件語言，有以下幾種可供選擇：  
Chinese.yml（簡體中文）  
**ChineseTW.yml（繁體中文）**  
Czech.yml（捷克語）  
**English.yml（英文，預設值）**  
French.yml（法語）  
Spanish.yml（西班牙文）  
Ukrainian.yml（烏克蘭語） | ChineseTW，想練英文或伺服器想開給外國人玩是可以考慮English，其他的就...見仁見智啦 |
| `SelectionToolId` | Minecraft Item ID | 這選項可以設定玩家該用哪個物品選擇自己領地的範圍（滑鼠攻擊鍵第一點，使用鍵第二點） | 預設吧，玩家比較習慣反正小心別跟小木斧衝到（小木斧預設值是木斧啊是在講什麼贛話...） |
| Selection/`NoCostForYBlocks` | Boolean | 設定成True時，玩家只需選擇領地範圍，範圍內的領地從基岩層到世界最高點都是屬於他的  
**若設定此項為True，建議要調高領地價格以免後來加入的玩家沒地可選...** | False，不用懷疑ww |
| `InfoToolId` | Minecraft Item ID | 拿著此物品右鍵敲一下即可在聊天欄得知那一格是否有人設定領地，以及該領地的範圍大小 | 保持預設的線吧 |
| DisabledWorlds/`List` | List/World Name | 加入此清單中的世界無法設定領地，例如副本世界等，會需要多世界插件如[Multiverse Core](https://www.spigotmc.org/resources/multiverse-core.390/)等 | 副本世界之類的要加進來 |
| Optimazions/`NegativePotionEffects`  
Optimazions/`NegativeLingeringPotions` | List/Minecraft ID | 設定藥水效果ID，如果藥水被設定在這裏面，則該藥水效果無法於領地PvP項目設為False時發揮效用  
例如若將傷害藥水的ID（`harm`）設定在這個列表中，則玩家無法在領地中使用傷害藥水，除非該領地的Pvp被設為True  
**NegativePotionEffects**是一般的藥水，**NegativeLingeringPotions**則是滯留藥水的設定 | 保持預設，他預設的很夠用 |
| Optimazions/`WalkSpeed` | Key-Value Pair/Integer | 設定wspeed1、wspeed2兩個領地選項所加成的玩家移動速度（wspeed1與wspeed2等等會寫相關說明） | 預設吧 |
| `TimeZone` | String | 設定插件時區，直接設為Asia/Taipei（亞洲，台北）即可 | Asia/Taipei |
| `DefaultGroup` | String | 設定玩家預設的領地身分組，底下groups.yml部分會詳細說明 |  |

<figcaption>

config.yml設定值

</figcaption>



</figure>

## 領地權限預設設定（flags.yml）

Residence插件可以讓玩家自行設定在自己的領地中要允許哪些動作和不允許哪些動作，以下製作了一張圖給大家做比對，**如果要拿去自己伺服器用請不要移除我的Logo，並註明出處**：

[點我下載權限表PDF檔案](https://drive.google.com/file/d/1tMAZtY-vMHwPgC4RHdMOPlkTYSgYOOuG/view?usp=sharing)

為什麼不打在網站裡

因為很長，真的很長，把這些東西打成PDF就花了我不知道幾天...

### 領地預設權限

打開`flags.yml`，找到`FlagPermission`後底下會列出許多內容為boolean的鍵值對：

```
ResidenceDefault:
    build: false
    destroy: false
    use: false
    container: false
    pvp: false
    tnt: false
    creeper: false
    ignite: false
    firespread: false
    vehicledestroy: false
    animalkilling: false
    hook: false
    shear: false
    leash: false
    pistonprotection: true
    # ...
```

看到了嗎？前面的就是領地的權限節點，我來簡單說明一下後面該接甚麼：

- true：啟用，例如pistonprotection設為true代表預設啟用防止活塞進入領地中的功能

- false：禁用，例如build設為false會讓玩家預設無法在領地中建築

此設定套用範圍

各位請放心，這個設定只會套用在非領地所有者的身上，也就是領地的擁有者會無視這些設定（畢竟領地就是他的想怎樣當然就怎樣啊www）

## 領地 身分組（groups.yml）

這裡的身分組跟前面LuckPerms的身分組是不一樣的喔！領地插件本身擁有一個獨立於LuckPerms外的身分組系統（當然這個系統最後還是會需要LP設定，待會教放心吧）

首先，插件預設會產生兩個身分組：Default與NextGroup，Default不要刪掉，那是一般玩家剛加入會有的預設身分組；NextGroup則是管理員用的，你有OP權限就可以獲得。如果你想新增一個新身分組，可以使用以下語法：

（對，請記得前面的縮排要有，不然語法會跑掉喔）

```
    Default:
       Residence:
           CanCreate: true
           MaxResidences: 9999
           MaxAreasPerResidence: 2000
           MaxEastWest: 999
           MinEastWest: 0
           MaxNorthSouth: 9999
           MinNorthSouth: 0
           MaxUpDown: 320
           MinUpDown: 0
           MinHeight: -64
           MaxHeight: 320
           MaxSubzonesInArea: 999
           SubzoneDepth: X
           SubzoneMaxEastWest: X
           SubzoneMinEastWest: Z
           SubzoneMaxNorthSouth: Z
           SubzoneMinNorthSouth: Y
           SubzoneMaxUpDown: Y
           SubzoneMinUpDown: Y
           CanTeleport: true
           Unstuck: true
           Kick: False
           SelectCommandAccess: true
           ItemListAccess: true
       Messaging:
           CanChange: true
           DefaultEnter: "&f歡迎 &6%player &f來到 &a%residence &f此領地為 &6%owner &f擁有"
           DefaultLeave: "&f您已離開 &a%residence &f保護區"
       Lease:
          MaxDays: 16
          RenewIncrement: 14
       Rent:
           MaxRents: 320
           MaxRentables: 320
           MaxRentDays: 320
       Economy:
          CanBuy: true
          CanSell: false
          IgnoreLimits: false
          BuyCost: 0.5
          SellCost: 0.25
          RenewCost: 0.2
       Flags:
          Permission:
          Default:
          CreatorDefault:
          GroupDefault:
          World:
                Global:
                     #build: false
                WorldNameHere:
                     #build: false
```

來解釋一下，然後還有表格真是好用，不只整理得很好看還能湊字數（當我沒說）

自訂預設身分組

如果你不喜歡預設的身分組名稱（雖然我是不推薦大家改啦），可以在`config.yml`檔案中，`DefaultGroup`鍵那邊改掉，不然不要把`Default`身分組刪掉，**刪掉包你出錯！**

### Residence/\* 領地建立設定

```
Residence:
    CanCreate: true
    MaxResidences: 9999
    MaxAreasPerResidence: 2000
    MaxEastWest: 999
    MinEastWest: 0
    MaxNorthSouth: 9999
    MinNorthSouth: 0
    MaxUpDown: 320
    MinUpDown: 0
    MinHeight: -64
    MaxHeight: 320
    MaxSubzonesInArea: 999
    SubzoneDepth: X
    SubzoneMaxEastWest: X
    SubzoneMinEastWest: Z
    SubzoneMaxNorthSouth: Z
    SubzoneMinNorthSouth: Y
    SubzoneMaxUpDown: Y
    SubzoneMinUpDown: Y
    CanTeleport: true
    Unstuck: true
    Kick: False
    SelectCommandAccess: true
    ItemListAccess: true
```

Residence底下的所有鍵都是用來管理領地設定的相關事宜的，例如玩家領地最大可以設定多少（MaxResidences）、領地最高消費和最低消費（？，反正是指`MaxEastWest`、`MinEastWest`那排的設定）等資訊，選項說明如下：

| YAML鍵名 | 類型 | 說明 |
| --- | --- | --- |
| Residence/`CanCreate` | Boolean | 擁有此權限組的玩家可否建立領地，建議設定true不然你裝Res幹嘛... |
| Residence/`MaxResidences` | Integer | 最大領地數，我個人不會設定限制（也就是直接打一個非常大的數字像是我這邊的9999）。  
看個人狀況，如果有VIP或不希望玩家設太多領地結果伺服器沒有空地的話可以設少一點 |
| Residence/`MaxSubzonesInArea` | Integer | 每個領地最大子領地數，這個在我們伺服器沒作用，簡單來講就像檔案資料夾可以再套娃一個新資料夾，同樣的概念 |
| Residence/`MaxEastWest`  
Residence/`MaxNorthSouth`  
Residence/`MaxUpDown` | Integer | 由上而下分別為**東西軸最大格數**、**南北軸最大格數**與**上下最大格數**，  
也就是**Z軸**、**X軸**或**Y軸**最多可以選幾格方塊，我也是不設限啦...反正你有錢你愛設多大隨便你 |
| Residence/`MinEastWest`  
Residence/`MinNorthSouth`  
Residence/`MinUpDown` | Integer | 跟上面大致同理，只是是最小格數不是最大，如果要解除設為0，簡單來講就類似低消，至少要買這樣的量... |
| Residence/（`SubZone開頭的`） | Integer | 跟前面兩項一樣的東西，只不過是子領地的設定 |
| Residence/`CanTeleport` | Boolean | 可否傳送至該領地 |
| Residence/`Unstuck` | Boolean | 如果因為某些原因（例如move權限被關掉之類的）造成自己無法離開領地，可以使用`/res unstuck`指令來強制離開該領地，這個選項就是用來開關unstuck指令可否使用的 |
| Residence/`Kick` | Boolean | 指定領地擁有者與Admin是否可以使用`/res kick`踢出領地內的玩家 |
| Residence/`SelectCommandAccess` | Boolean | 指定玩家可不可以用`/res select`選擇領地範圍，設定為False的話就只能使用config.yml中設定的`SelectionToolId`來選擇領地範圍 |

### Messaging/\* 訊息相關設定

```
Messaging:
    CanChange: true
    DefaultEnter: "&f歡迎 &6%player &f來到 &a%residence &f此領地為 &6%owner &f擁有"
    DefaultLeave: "&f您已離開 &a%residence &f保護區"
```

這個部分會設定玩家進出領地提示訊息的資訊，例如進入時與離開時的訊息，以及是否允許領地所有者變更這些相關設定等...

<figure>

[![](/images/resisdence-plugin/image-1.jpg)](http://samhacker-local.local/wp-content/uploads/2024/08/image-1.jpg)

<figcaption>

設定的訊息會像這樣顯示

</figcaption>

</figure>

| YAML鍵名 | 類型 | 說明 |
| --- | --- | --- |
| Messaging/`CanChange` | Boolean | 進入、離開領地預設是否允許使用者更改物品欄上顯示的訊息 |
| Messaging/`DefaultEnter`  
Messaging/`DefaultLeave` | Boolean | 設定進出領地的訊息預設值，可以使用以下Placeholder（不須Placeholder API）：  
**%player**：進入領地的玩家名稱  
**%playerDisplay**：玩家的顯示名稱  
**%owner**：領地主人的玩家名稱  
**%residence**：領地名稱  
**%zone**：如果只想包含目前領地名稱而不將父領地包含在名稱中 |

### Lease/\* 領地出租相關設定

```
Rent:
    MaxRents: 320
    MaxRentables: 320
    MaxRentDays: 320
```

如果你希望讓你的玩家可以互相租用領地，到期還要付租金（？），或許指令`/res lease [renew/cost] [領地名]`可以滿足你的玩家的需求，至於要怎麼設定...就看下面的表格啦 (^w^)

| YAML鍵名 | 類型 | 說明 |
| --- | --- | --- |
| Lease/`MaxRents` | Integer | 玩家**最多可以租用幾個領地** |
| Lease/`MaxRentables` | Integer | 玩家**最多可以出租幾個領地** |
| Lease/`MaxRentDays` | Integer | 領地最多**可以租幾天** |

領地租用的相關Bugs

我在Residence插件的Issues上看到不少人出租系統的錯誤，例如[租用領地者無法TP到自己租的領地](https://github.com/Zrips/Residence/issues/896)、[經濟系統無法正確轉帳](https://github.com/Zrips/Residence/issues/586)、[租用的土地無法建造](https://github.com/Zrips/Residence/issues/476)等錯誤，我自己也有遇到一些玩家無法正確使用領地相關的問題。

因此如果各位不願意處理這些錯誤的話，建議**可以不要開放領地出租的功能**給玩家會比較好喔（像我[個人的伺服器](http://whiter.lnstw.xyz)就沒有開）！

### Economy/\* 經濟系統相關設定

重點畫起來！這裡是要設定錢的部分了~~在這個部分你會設定玩家要花多少錢買領地（BuyCost）、賣出賺多少等問題，可惜這插件不能依照領地數量自動調整價格（然後伺服器就會有貧富差距、鄉村和都市還能炒地皮？我到底在說什麼XD）

```
Economy:
    CanBuy: true
    CanSell: false
    IgnoreLimits: false
    BuyCost: 0.5
    SellCost: 0.25
    RenewCost: 0.2
```

| YAML鍵名 | 類型 | 說明 |
| --- | --- | --- |
| Economy/`CanBuy` | Boolean | 玩家能否購買待售的領地（待售領地相關資訊待會講） |
| Economy/`CanSell` | Boolean | 玩家可否出售自己的領地 |
| Economy/`IgnoreLimits` | Boolean | 玩家在購買待售領地時如果待售領地的大小超過在`Residence/*`中設定的值，玩家還能購買該領地嗎 |
| Economy/`BuyCost` | Integer | 玩家購買一格土地要花多少錢，簡單說就是領地一格賣多少 |
| Economy/`SellCost` | Integer | 玩家賣領地時一格可以賺多少錢 |
| Economy/`RenewCost` | Integer | 玩家租用領地一格要多少錢 |

### Flags/\* 權限與牠們的更改

首先要注意的是領地插件前面給的一大串註解：

> \# Flags are checked in the order:  
> \# 1: Player  
> \# 2: Group  
> \# 3: Owner  
> \# 4: If all others are undefined, reverts to default value (usually true).  
> \# Flag permissions default to false.  
> \# These flags settings override the globals.

這個區段會設定擁有此身分組的玩家可否更改這邊設定出來的領地權限，而上面註解則是說明檢查是否可更改領地權限是按照`"玩家">"身分組">"管理員"`，如果這三項都未定義，那就照前面`flags.yml`中的設定來決定。

以上這段話是什麼意思呢？

舉個例子，伺服器有一名玩家A擁有一個領地`a_home`，這位玩家不希望怪物進到自己的家裡，但服主我又只把"禁止原版怪物生成（`nmonsters`）"訂為只給VIP的設定。此時領地插件就會**先檢查我有沒有專門設定給A"可以配置nmonsters"的權限**；如果沒有，就去**檢查A的身分組**（default）可不可以修改這個設定，如果都沒設定的話會去**檢查他是不是OP（管理員）**，最後才是去翻`flags.yml`找預設值（然後如果還是又双叒叕找無...那只好全部預設False...）。

其實一般狀況下不用特別注意這段話，畢竟大部分狀況檢查到Group就可以了...我是怕有些人不知道這段話的意思另外翻譯給他們看的。回歸正題，來看配置吧。這個區段預設是沒有設定玩家的任何限制，而我個人也沒有特別建議你做限制，除非你想做VIP權限可能才需要動到這裡：

```
Flags:
    # Specifically allow or deny this group from changing certain flags.
    Permission:
        #build: true
   
    # Specifys the flags that are applied at residence creation for players of this group.
    Default:
        #build: true
   
    # Specifys the flags that are applied at to the creator at residence creation.
    CreatorDefault:
        #build: true
   
    # Specifys the flags that are applied to other groups for this residence, at creation.
    GroupDefault:
        #default: #group name
        #build: false
    #these flags are applied specifically to this group whenever they are outside a residence
    #these flags will override the flags at the top, under the Global section.
    World:
        Global: #these flags will apply to all worlds
            #build: false
        WorldNameHere: #or you can apply them by each individual world
            #build: false
```

這個設定比較複雜，我盡量簡單解釋：

首先我們看到Permission，這裡指定**此身份組是不是有權更改某些flag**（領地的權限叫做flag，要跟LP的Permission分開）。如果你想禁用某些權限（例如我不希望玩家可以更改build權限的開啟與否），那就設定`[被控制的權限英文名稱]: [true/false]`，例如註解寫的`build: true`代表允許玩家更改build權限。

Default則是**指定預設的權限**，其實就跟隔壁`flags.yml`那一棚`FlagPermission`的功能一樣，只是如果在這邊設定的話會覆蓋掉那邊的設定，這是比較大的重點啦

CreatorDefault跟Default差不多，唯一差別是這個指定的是**領地擁有者預設的權限**（比如如果你想搞玩家，可以把這邊的build設為false，然後建領地時你就建造不了了...搞事啊！！！）

GroupDefault則是指定**其他的權限組套用的權限**，跟Default也是一樣的意思，唯一的差別也一樣是這個指定的是其他權限組，不是領地擁有者或預設...

World鍵下代表的是這個權限組在其他領地套用的預設設定，也就是如果這個權限組的使用者去到別人領地預設會套用哪些權限設定（當然領地主設定的權限一定會蓋過這個）。底下有兩個子鍵分別名為Global和WorldNameHere，Global代表所有世界沒有另外指定都是用Global設定，WorldNameHere是叫你把世界名稱填在這裡，然後玩家到了該世界就套用這裡的設定而非Global。

Default與World的差別

Default（包含他的兩個衍生：CreatorDefault＆GroupDefault）指定的是符合條件的人在自己領地內的權限，而World則是指定符合該條件的人在別人領地內的預設權限

我也知道這個非常繞，繞來繞去我頭都暈了，這邊畫一個簡單的流程圖來讓大家比較能了解。喔然後之前有人來私我DC問說怎麼畫這個流程圖，這邊也附一下網址是[draw.io](http://draw.io)：

<figure>

[![](/images/resisdence-plugin/samhackerblog_resisdence-plugin_3.png)](http://samhacker-local.local/wp-content/uploads/2024/08/samhackerblog_resisdence-plugin_3.png)

<figcaption>

你這真的可以再給我長一點沒關係...啊不過好像也沒好懂到哪...

</figcaption>

</figure>

## 領地 插件基本玩法

語法格式

在我的文章中，語法會用以下格式顯示：

**<參數說明>**：可選參數，也就是給不給都可以  
**\[參數說明\]**：必選參數，一定要給  
**指令內容**：這不是格式，它是指令的語法本體

### 建立一個自己的領地

最一開始當然就是要先擁有一個自己的領地，來看看要怎麼選吧！

| 項目 | 說明 |
| --- | --- |
| 指令語法 | /res create \[領地名稱\] |
| 指令權限節點 | residence.create（執行/res create指令所需）  
residence.select（使用權杖選取範圍所需） |

STEP

選取範圍

拿出你在config.yml的SelectionToolId設定的選取權杖（預設是木鋤），對著要選取的領地範圍用左右鍵選擇第一、第二點

STEP

執行領地指令建立領地

創建領地的指令是`/res create [領地名稱]`，該指令後面接的領地名稱是一個唯一值，也就是建立領地的這名玩家的所有領地中，不可以有任何領地名稱與此領地名重複

STEP

付錢，結束

在執行完指令後系統會通知已經從金錢帳戶支出領地費用，然後執行指令的玩家就會擁有這塊領地的所有權

選擇領地範圍的原理

此原理就跟先前介紹過的小木斧一樣，使用左右鍵選擇兩個點，而兩點間形成的長方體區塊就會是領地的範圍，也就是要交錢的範圍...

其他領地選取指令

難道你選地一定要用木鋤點來點去的嗎？如果你沒有飛行權限又點不到自己家就只能用疊方塊大法嗎？

當然不是啦ww，這邊來補充幾個輔助選領地的指令（啊那個記得喔，如果你手賤把groups.yml裡面的Residence/SelectCommandAccess設為false的話你可以無視這段了...），這些指令權限節點你有給residence.select應該就OK了：

| 指令 | 說明 |
| --- | --- |
| /res select chunk | 選取整個區塊 |
| /res select expand \[格數\] | 向眼前面向的方向（好多向）延伸指定的格數 |
| /res select size | 顯示目前選定的範圍噢...價錢 |
| /res select shift \[格數\] | 把選區往面向方向整個移動指定格數，小心不要跟expand搞混 |
| /res select vert | 把選區延伸到從天頂到地底 |

### 取得領地資訊

你可以查看自己領地的資訊，執行該指令會跳出類似以下畫面的訊息：

[![](/images/resisdence-plugin/samhackerblog_resisdence-plugin_5.webp)](http://samhacker-local.local/wp-content/uploads/2024/08/samhackerblog_resisdence-plugin_5.webp)

| 項目 | 說明 |
| --- | --- |
| 指令語法 | /res info <領地名稱> |
| 指令權限節點 | residence.command.info |

### 編輯自己領地的全局權限

使用這個指令可以讓你設定其他玩家到你的領地預設會擁有哪些權限，以下是我個人建議的權限設定：

這個指令有兩種用法：指令指定或GUI指定

#### 指令指定法

透過指令的方式編輯權限，如果在GUI中找不到你要改的項目可以用這招直接打指令尋找，我個人也比較愛用這種方法，因為我常眼殘找不到設定

| 項目 | 說明 |
| --- | --- |
| 指令語法 | /res set \[領地名稱\] \[Flag名稱\] \[true/false/default\] |
| 指令權限節點 | residence.set（基本不用修改，它預設就是true） |

例如想要更改玩家放置方塊的權限（place），就執行/res set place true來允許所有玩家放置方塊。後方可以指定這個權限的狀態：

- **true**：可以、允許、啟用

- **false**：禁止、封鎖、禁用

- **default**：設為預設值

#### GUI指定法

此指定法會開啟一個GUI讓玩家在該介面中管理領地一切權限

| 項目 | 說明 |
| --- | --- |
| 指令語法 | /res set \[領地名稱\] |
| 指令權限節點 | residence.set（基本不用修改，它預設就是true） |

<figure>

[![](/images/resisdence-plugin/image-1-1024x576.png)](http://samhacker-local.local/wp-content/uploads/2024/08/image-1-2.jpg)

<figcaption>

這是GUI，感謝雲羽伺服器的玩家幫忙

</figcaption>

</figure>

> 操作說明很簡單，左鍵右鍵這樣玩；  
> 左鍵設定可以玩，右鍵代表不可以；  
> 按到中鍵怎麼辦，設定重來預設版；  
> 左右中鍵記好好，領地安全沒煩惱。

### 編輯自己領地的個人權限

一樣的設定，但set換pset：

#### 指令設定法

| 項目 | 說明 |
| --- | --- |
| 指令語法 | /res pset \[領地名稱\] \[被設定的玩家名稱\] \[Flag名稱\] \[true/false/default\] |
| 指令權限節點 | residence.set（基本不用修改，它預設就是true） |

#### GUI設定法

| 項目 | 說明 |
| --- | --- |
| 指令語法 | /res pset \[領地名稱\] \[被設定的玩家名稱\] |
| 指令權限節點 | residence.set（基本不用修改，它預設就是true） |

### 領地改名

領地名稱不好嗎？改一下吧ww

| 項目 | 說明 |
| --- | --- |
| 指令語法 | /res rename \[領地名稱\] \[新名稱\] |
| 指令權限節點 | residence.set（基本不用修改，它預設就是true） |

改名遊戲規則還是一樣，英文小寫、底線減號這幾個ww

### 傳送進領地與設定領地預設傳送點

想睡覺，想轉去厝內？沒關係，只要你有設領地，不管你人在哪裡，插件都會帶你回來（黨很喜歡妳的創意，Sam）

| 項目 | 說明 |
| --- | --- |
| 指令語法 | /res tp \[領地名稱\] |
| 指令權限節點 | residence.command.tp（基本不用修改，它預設就是true） |

執行這個指令後會將你傳送回自己的領地。如果預設的傳送點很奇葩可以用以下指令重新設定

| 項目 | 說明 |
| --- | --- |
| 指令語法 | /res tpset |
| 指令權限節點 | residence.command.tpset（基本不用修改，它預設就是true） |

這個指令會設定你所在的領地的傳送點是你個人站的位置，因為你站的位置必須要在領地內才能傳（所以預設傳點不能放在領地外面喔，放在奇葩的地方你要自己負責，就醬），因此就不需特別指定領地名，然後設定的位置就是自己站的位置，好像官方文件也沒特別說可以指定座標的樣子...

### 贈送領地給玩家

| 項目 | 說明 |
| --- | --- |
| 指令語法 | /res give \[領地名\] \[玩家名\] |
| 指令權限節點 | residence.command.give（基本不用修改，它預設就是true） |

此指令會允許你將領地給玩家，但請注意你必須滿足以下兩條件：

- 你是領地的擁有者（不能是Admin喔）

- 領受人（玩家名）目前在線上，無法贈與給不在線玩家

在執行完此指令後，通常會要求你再輸入確認指令以確認你真的要給：

| 項目 | 說明 |
| --- | --- |
| 指令語法 | /res confirm |
| 指令權限節點 | residence.command.confirm |

### 移除自身擁有的領地

如果你不想要領地了，可以執行這個指令，插件會退還一點點領地的錢給你，折舊本來就會比較便宜你說484？

| 項目 | 說明 |
| --- | --- |
| 指令語法 | /res remove \[領地名\] |
| 指令權限節點 | residence.command.remove |

以上指令會移除一個名稱為所指定領地名稱的領地（好繞...），一樣需要確認指令，前面給過表格了這邊就不會給囉~~

| 項目 | 說明 |
| --- | --- |
| 指令語法 | /res removeall |
| 指令權限節點 | residence.command.removeall |

此指令會移除自身擁有的所有領地，小心使用不然你的領地...對你懂的ww

### 列出自己擁有的所有領地

你忘記了自己的領地嗎？執行以下指令看看吧：

| 項目 | 說明 |
| --- | --- |
| 指令語法 | /res list |
| 指令權限節點 | residence.command.list |

<figure>

[![](/images/resisdence-plugin/samhackerblog_resisdence-plugin_6.webp)](http://samhacker-local.local/wp-content/uploads/2024/08/samhackerblog_resisdence-plugin_6.webp)

<figcaption>

輸出結果底家

</figcaption>

</figure>

### 管理員專用指令

管理員如果需要移除某玩家的領地，例如移除錯設領地、繞過自身領地限制（限制當然是  
所謂的group.yml），需要使用管理員專用的指令。至於這個指令嘛...簡單，前面講的/res什麼的，就把res換成resadmin，像是要強制移除某領地，執行`/resadmin remove [領地名稱]`即可。

| 項目 | 說明 |
| --- | --- |
| 指令語法 | /resadmin \[其他指令\] |
| 指令權限節點 | residence.admin.\* |

## 指令表

前面已經寫好基礎的指令了，基本上習得這幾招你就可以玩轉領地插件囉~~

我的能力有限，如果大家有需要完整的指令內容，可以前往以下兩個網站。以下兩個都是我覺得寫的好的文章，大家可以前往看看：

- [【情報】res領地插件指令大全](https://forum.gamer.com.tw/Co.php?bsn=18673&sn=175860)

- [Permissions - Zrips](https://www.zrips.net/residence/permissions/)

## 權限節點

整理這東西真的好麻煩...快累死了

<figure>

| 節點 | 說明 | 建議擁有者 |
| --- | --- | --- |
| `residence.command.message.enter   residence.command.message.leave` | **更改**進入訊息（上面）、離開訊息（下面） | 玩家 |
| `residence.command.message.enter.remove   residence.command.message.leave.remove` | **移除**進入訊息（上面）、離開訊息（下面） | 玩家 |
| `residence.flag.[領地權限名稱]` | 允許或拒絕此人更改"領地權限名稱"所指的權限，也就是前面提到的"個人設定" | 按需使用 |
| `residence.admin.tp` | 即使領地的tp權限設為False，擁有這個節點的人也可以強制TP前往 | 管理員 |
| `residence.topadmin`  
`residence.admin` | 擁有此節點的人為最高管理員（上面）、領地插件管理員（下面） | **上面**：服主（自身）  
**下面**：管理員 |
| `residence.admin.[領地權限名稱]` | 允許管理員繞過"領地權限名稱"所指的權限 | 服主 |
| `residence.newguyresidence` | 在首次放置箱子的地方設定領地 | 按需使用 |
| `residence.group.[群組名稱]` | 用權限設定指定某玩家的群組為指定的群組  
**例如**：groups.yml中建立一個vip群組，就給vip權限組`residence.group.vip`權限節點 | 按需使用 |
| `residence.rename` | 重新命名領地 | 玩家 |
| `residence.select` | 選擇領地範圍 | 玩家 |
| `residence.resize` | 調整領地大小 | 玩家 |
| `residence.create` | 建立領地 | 玩家 |
| `residence.delete` | 移除自己領地 | 玩家 |
| `residence.command.kick.bypass` | 擁有此權限後，別人無法踢出這名玩家 | 管理員 |
| `residence.versioncheck` | 檢查領地插件版本 | 管理員 |
| `residence.command.[指令名稱]` | 給予玩家執行指定指令的權限 | 按需使用 |

<figcaption>

其他權限節點請參照[Permissions - Zrips](https://www.zrips.net/residence/permissions/)中的說明

</figcaption>



</figure>

## 結語

最近很久沒趕這麼長篇文章了（這篇我寫了大概有兩個禮拜，期間要整理資料什麼的，光是那份權限表就一大堆內容...到底喔），希望大家不要把我當成都在水文章，我還是會認真寫的啦哈哈。

總之還是要來官腔一下，如果各位有看我文章學到一些東西，歡迎你底下留個言或拍拍手。我想要把這個系列免費開放給所有想開服的朋友，因此我就不做贊助的功能了，網站也沒放廣告因為估狗不給我過啊。

謝謝各位的支持，有你們我的文章才能發（肝）這麼多篇，總之我要去做封面圖了，再見（^v^）
