# Taipei_Metro_System
> 一個由 git branch 組成的台北捷運路網圖

## 目的
* 練習 git，捷運都建的出來了應該是摸透git了吧

## 進度
* 截至2023.06.012的 台北/新北/桃園 捷運、輕軌、纜車 站名皆已完成

## 分支圖製作與解釋
* 轉運站部分都是merge而成的，因此單看個別分支的commit一定會存到其他路線的站名
* 使用任何可以顯示 git graph 的軟體或指令，最簡單的如 `git log --graph --oneline`；知名的如 [SourceTree](https://www.sourcetreeapp.com/)

### master
* 存放README.md的更新，目前所有的路線都從這邊長出，之後有空會把它跟其他路線分離
![](https://drive.google.com/uc?id=1AJXNpv9sc0SSDiPVetaNbnCoHs37_wPG&export=download)

### 基本路線
* 無分支的路線以 `commit -m <msg> --allow-empty` 生成，下圖為BR02~BR08的路線圖
![](https://drive.google.com/uc?id=1yA_QdPvFFTNlxq4R9Acqz46u7jbdARnr&export=download)

* 一般轉運站使用 merge 方式實現
* 以忠孝新生周邊為例，捷運圖如下
    * ![](https://drive.google.com/uc?id=1FxVI6xxJNPEu8UTrgR_zZAAmIPLZr-Ou&export=download)
    * 在`BL branch` 上， merge `O branch`，並寫入message為忠孝新生

* 生成 branch 如下，查看板南線的Current branch可得到：
* ![](https://drive.google.com/uc?id=11YVG8a6Fpv0DWIkqkg0UXOTdyoWq-tKt&export=download)

* 實際上包含四條線分別，如下圖：
* ![](https://drive.google.com/uc?id=1dmPuCLafTn5H0A-cSfEstFW4RtVIpEgt&export=download)

### 站外轉乘結構
* 環狀線、機場捷運與輕軌等會有這種情況產生，這種情況兩邊的站會分開寫，其實就是多一筆commit再merge
* 以板橋附近為例：
    * ![](https://drive.google.com/uc?id=1w9sjhYbfKkjXDPIIV9wEerkARP1iNYl9&export=download)
    * 板橋與新埔都設有站外轉乘，因此可以看到板南線(粉色)與環狀線(藍色)有連接

### 支線
* 目前有的是小碧潭與新北投支線、以及淡海輕軌與中和新蘆線的分支
* 直接從分支點創建新的branch
* 以小碧潭支線為例：
    * ![](https://drive.google.com/uc?id=1MDZz5XSLQItb-XdNA2DDAnHZvidD-Wnk&export=download)
    * 小碧潭支線從 七張 分離出去，原本的松山新店線經過紫色的轉運站後，繼續沿著深黃色路線前進


## 缺失
* 是否有更好的方法可以改善視覺化
* [Y09]秀朗橋 誤植為 [Y0]秀朗橋
* 所有 branch 目前都從 master 長出，應該要與 master 分離，也就是砍掉每個分支的第一個 commit
