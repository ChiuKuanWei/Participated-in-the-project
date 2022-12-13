# 參與專案

*以下專案都是用Visual C# + SQL Server去進行實作

1.條碼過站系統

系統需求:

設定當下作業的流程卡號、員工編號、原物料編號，按下開始鍵後，會從客戶端Webservice取得當批流程卡號各個所需作業的條碼。

當條碼過入出站時，藉由入出站掃描器所掃描到的條碼內容，由TCPIP傳輸的方式傳送給我的系統，將接收到的條碼內容顯示在畫面上，並記錄當下條碼的入出站時間為何時，將記錄儲存到資料庫裡。

當流程卡號整批做完，按下結束鍵後，會將當批所做的作業紀錄上傳至客戶端WebService，供客戶後續可以做作業紀錄查詢的動作。

選擇時間範圍匯出作業紀錄成csv檔。

開發技術:

利用Socket套件進行設備連線及傳接收資料。

利用web service參考服務呼叫Function，進行作業條碼取得及作業紀錄上傳。

利用CsvFileWriter套件，讓使用者可將作業紀錄匯出成CSV檔。

2.包裝攝影系統

系統需求:

利用WebCam攝影進行外箱包裝拍攝，將拍攝圖片儲存到資料夾內。

利用資料庫處理，將資料內容及存放圖片路徑進行儲存，供使用者後續可進行查閱的動作。

開發技術:

利用Aforge套件，進行WebCam攝影及拍照功能。

利用RS232 SerialPort進行串口連線。

利用InvokeRequired委派處理，解決跨執行緒的問題。

利用System.Drawing套件，使用Graphics.DrawString(寫浮水印文字)和Graphics.FillRectangle(畫矩形包覆浮水字串)在圖片上插入浮水印內容。

3.溫度異常推播系統

系統需求:

當溫度監控系統監測到溫度異常時，會傳送溫度異常的訊息給溫控異常推播系統，溫控異常推播系統再將所接收到的異常內容推播到對應的群組，通知管理員進行異常排除的動作。

開發技術:

利用Socket套件進行Server端監聽。

利用WebAPI與Token驗證方法進行LINE訊息推播。

4.寄倉管理系統

系統需求:

以當天為標準去檢查7天內快到期的合約，將快到期的合約顯示在主頁上，幫助業者掌握各個合約狀態。

製作csv檔資料匯出功能。

系統登入帳密管理。

開發技術:

在合約紀錄查詢介面製作分頁功能，防止大量資料搜尋卡頓問題。

利用CsvFileWriter套件，讓使用者可將合約資料匯出成CSV檔。

5.列印管理系統

功能需求:

PDF讀取介面:

載入PDF檔，並讀取PDF檔內容及Barcode，顯示DPF內容再DataGridView上。

列印管理介面:

利用TXT文字檔匯入要作業的內容。

每列印一筆就把當前筆刪除，並搬移到作業紀錄裡，供使用者後續可進行查閱動作。

作業紀錄刪除介面:

讓使用者勾選(CheckBox)要刪除的項目。

開發技術:

利用using BC.NetPdfBarcodeReaderTrial.All; using BC.NetPdfBarcodeReaderTrial.Pdf;，將PDF檔內Barcode進行讀取。

using iTextSharp.text.pdf; using iTextSharp.text.pdf.parser;，進行PDF內容讀取。

利用usercontrol(使用者控制項)在作業頁面動態新增各個機台的操作介面。

利用SqlBulkCopy將大批資料一次匯入到資料庫裡，因當中有宣告TransactionScope，所以必須開啟DTC(分散式交易協調器)此功能，才能進行使用。

DTC(分散式交易協調器)設定方法及用途參考路徑:https://blog.xuite.net/towns/hc/203881813

利用CsvFileWriter套件，讓使用者可將作業紀錄匯出成CSV檔。

6.外箱條碼比對

功能需求:

將操作員所選的比對條碼內容與當下所掃的外箱條碼內容進行比對，比對內容是否相符，並進行比對結果紀錄。

利用RS232通訊方式連線掃描器。

利用網路連線方式連線IO盒。

利用EXCEL檔匯入要比對的條碼內容至資料管理區。

開發技術:

利用Socket進行IO盒連線。

利用SerialPort進行RS232連線。

利用Microsoft.Office.Interop.Excel套件製作EXCEL匯入功能。

利用Array.copy處理RS232收值不完全的問題。

7.CodeSoft標籤列印與Markingmate Keyence雷雕列印


