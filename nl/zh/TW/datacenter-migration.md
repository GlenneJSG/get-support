---

copyright:

  years: 1994, 2018

lastupdated: "2018-10-22"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# 撤銷部分美國資料中心的支援
{: #dc-migrate}

IBM 將撤銷下列位於美國的資料中心的支援： 

* dal01 pods 2 and 3
* wdc01 pods 1 and 2
{:shortdesc}

##  為何我必須移至另一個資料中心？

為了提供您最佳的服務、硬體和連線功能，我們持續評估我們所有的網站，以確定符合網路、電氣、以及其他基礎架構標準。即使這些網站都可用，它們已不符合我們現行標準。

## 我是否需要在列出的日期之前完成移轉？

是。為了確保您的服務不會被岔斷，我們將儘可能騰出更多前置時間，來讓轉移更順暢。我們已經在 2018 年五月傳達網站移動事宜。

## 我是否需要再度移至另一個資料中心？

我們會持續評估網站品質，來提供您最佳及最可靠的服務。當我們繼續評估部分較舊的網站時，有可能會需要其他移動。

## 我可以選擇任何 {{site.data.keyword.Bluemix_notm}} 美國資料中心嗎？

是，您可以選擇符合您的位置需求的任何美國 IBM 網站。

## 我要如何選取可對其進行部署的資料中心？

IBM 在全球各地擁有超過 60 個資料中心，請檢視全球資料中心頁面上的資料中心地圖，來查看您可以在哪些資料中心進行部署。 

下列因素可能會影響您選擇資料中心：
* 和使用者的系統的鄰近性
* 和需要和此伺服器通訊的其他系統的鄰近性
* 要求資料必須儲存在特定位置的任何資料原則或法規

## 我是否還必須在轉移期間使用美國網站？

您可以在轉移期間使用全球任何 {{site.data.keyword.cloud_notm}} 網站，最長 60 天。

## 除了現有伺服器時間之外，是否還有額外的兩個月免費轉移期間資源可用？

是。您可以聯絡我們，將會有適當的支援代表協助您完成取得轉移期間伺服器的程序。

## 如何判斷我的現行硬體配置？

請登入客戶入口網站。請從**裝置清單**選取您要的伺服器，然後尋找系統配置詳細資料。您可以在其中檢視處理器類型，例如，單一 Intel Xeon E3-1270（4 核心，3.50 GHz）。您可以檢視記憶體數量 (RAM)、儲存空間以及其他資料。

## 如何判斷現行硬體的使用率？

大部分的作業系統都提供工具供您瞭解系統使用率，例如 Linux 上的 vmstat 和 iostat，或者 Windows 系統效能監視器。亦還有其他許多效能監視工具可用來監視系統效能。效能監視和調整需要投入大量的時間和勞力。通常，您需要瞭解系統內是否有特定的資源（處理器、記憶體、磁碟、網路）被過度使用或未充分利用。擁有此資訊可協助您掌握新系統的大小。例如，頻繁過量使用記憶體容量的系統會從移轉至的目標系統擁有較大的記憶體系統獲得好處。

## 如何比較舊和新的處理器？

若要比較舊和新 Intel 處理器的規格，請移至 [https://ark.intel.com/#@Processors](https://ark.intel.com/#@Processors)。如果您知道處理器類型，您可以導覽功能表。或者，您可以使用搜尋選項尋找兩個處理器的規格。新處理器傾向擁有更多處理器核心而且通常會以比其他舊處理更慢的時脈執行。如果的工作負載為受記憶體約束（其效能受到處理器速度限制），建議您選擇具有較少核心以及更高時脈速度的處理器。如果您執行許多不會特別受到處理器速度約束的工作負載，擇具有更多核心以及類似（或者更慢）時脈速度的處理器可能是更佳的行動方針。

## 如何選擇新作業系統？

如果伺服器已經使用多年而且未保持為最新，則您執行的可能是舊版作業系統。這表示移轉是一個挑戰。您可能已經沒有用來安裝舊作業系統的安裝媒體。您可能還會發現舊作業系統版本不支援作為移轉目標的新伺服器硬體。因此，您可能需要選擇不同的作業系統作為移轉目標。

作業系統選擇可能會受到您執行的應用程式限制。作為移轉的一部分，您可能需要在較新的作業系統版本上執行應用程式。請確定該應用程式可以在新版本上運作。

特定作業系統中可用的技術也可能會受到您的選擇影響。如果有應用程式的原始碼，請確定新平台具有必要的開發工具和支援的作業系統或中介軟體功能。通常，相較於 Windows，Linux 類型的系統在新版作業系統上可對舊版應用程式提供更好的支援。

## 我在新配置上可以獲得何種頻寬，該頻寬是否和我目前擁有的速率相同？

您收到和您目前擁有的套件密切相關的現行頻寬套件。套件的速率就是您的現行速率或套件內含的速率。

## 如何從舊伺服器複製資料至新伺服器？

在新與舊伺服器之間建立連線功能後，您要考量如何在兩者之間移動資料。假設您在新伺服器有足夠的儲存空間，可容納大量的資料，直接伺服器對伺服器複製是達成此目標最簡單的方法。有多種工具可供您使用。  

* scp 是從來源安全地複製檔案至目的地的良好選擇。它是以一般線性方式執行複製。 
* 如果您需要複製大量的檔案，則在 ssh 上執行 rsync 的速度比 scp 更快。rsync 還可複製目錄結構以及保留檔案許可權。

通常，您只需要在兩個系統之間複製應用程式和應用程式資料。將舊版的作業系統檔案複製到新版會造成問題。

在系統之間複製資料之前請先關閉資料庫以確保資料一致。移轉資料庫資料時，請確定資料的移轉方式不會對用來匯入至新系統的選項造成限制。除了從某個系統複製資料庫資料至另一個系統的方法外，請考量採用可以匯入至新資料庫的格式匯出資料庫資料。在兩個系統之間移動資料時，純文字檔案、CSV 檔可以提供比專屬或封閉的檔案格式更多的選項。在執行正式複製之前，請一律先以一個小測試資料集測試您的資料移轉方法。

## 我需要在新網站再設定一次網路嗎？

您的網路極有可能需要變更才能夠和新伺服器與網站搭配使用。如果對此程序您需要相關協助，請透過電話或聊天軟體和支援團隊聯絡。

## 如果沒有相移轉技術，我該怎麼辦？

應用程式移轉可能是非常複雜的任務。這些都不是完成此項作業必備的技術。如果應用程式需要變更程式碼，請確定您具備必要的程式設計技術。這在舊系統所需的技術不易取得或或者缺乏系統本身的相關文件或知識的情況特別是如此。如果需要投入大量的工作而且系統對於業務至關重要，請考量投資付費服務或其他移轉服務來協助您。

## 如何取得移轉的一般協助？

視您需要的協助層次而定，您可以透過電話或聊天軟體來連絡支援。或者，您也可以加入我們的管理式服務團隊來取得協助。

## 如果沒有客戶經理，我可以和誰聯絡？

您可以透過電話或聊天軟體針對您遇到的任何移轉問題與支援中心聯絡。
