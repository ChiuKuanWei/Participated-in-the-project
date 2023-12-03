# 開發專案

*以下專案都是用Visual C# + SQL Server去進行實作

1.條碼過站系統

專案內容:

顯示晶片條碼入出站掃描內容。

開發技術:

利用Socket套件進行設備連線及溝通。

利用web service參考服務呼叫Function，進行當批條碼內容取得及作業紀錄上傳。

利用CsvFileWriter套件，讓使用者可將作業紀錄匯出成CSV檔。

2.包裝攝影系統

專案內容:

利用WebCam進行外箱包裝拍攝，將拍攝圖片儲存到資料夾內。

開發技術:

利用Aforge套件，進行WebCam攝影及拍照功能。

利用RS232 SerialPort進行串口連線。

利用InvokeRequired委派處理，解決跨執行緒的問題。

利用System.Drawing套件，使用Graphics.DrawString(寫浮水印文字)和Graphics.FillRectangle(畫矩形包覆浮水字串)在圖片上插入浮水印內容。

3.溫度異常推播系統

專案內容:

接收溫度監控系統異常訊息，將接收到的異常內容推播到對應的群組，通知管理員進行異常排除動作。

開發技術:

利用Socket套件進行Server端監聽。

利用WebAPI與Token驗證方法進行LINE訊息推播。

4.寄倉管理系統

專案內容:

檢查7天內快到期的合約，將快到期的合約提醒使用者。

開發技術:

在合約紀錄查詢介面製作分頁功能，防止大量資料搜尋卡頓問題。

利用CsvFileWriter套件，讓使用者可將合約資料匯出成CSV檔。

5.列印管理系統

專案內容:

(1) 讀取PDF檔內容及Barcode。

(2) 選擇當下作業的品項，將每筆內容進行標籤列印。

開發技術:

利用using BC.NetPdfBarcodeReaderTrial.All; using BC.NetPdfBarcodeReaderTrial.Pdf;，將PDF檔內Barcode進行讀取。

using iTextSharp.text.pdf; using iTextSharp.text.pdf.parser;，進行PDF內容讀取。

利用usercontrol(使用者控制項)在作業頁面動態新增各個機台的操作介面。

利用SqlBulkCopy將大批資料一次匯入到資料庫裡，因當中有宣告TransactionScope，所以必須開啟DTC(分散式交易協調器)此功能，才能進行使用。

DTC(分散式交易協調器)設定方法及用途參考路徑:https://blog.xuite.net/towns/hc/203881813

利用CsvFileWriter套件，讓使用者可將作業紀錄匯出成CSV檔。

6.外箱條碼比對

專案內容:

將操作員所選的條碼與當下所掃的外箱條碼進行條碼比對，比對是否相符，並進行比對結果紀錄。

開發技術:

利用Socket進行IO盒連線。

利用SerialPort進行RS232連線。

利用Microsoft.Office.Interop.Excel套件製作EXCEL匯入功能。


7.CodeSoft標籤列印與Markingmate Keyence雷雕列印

專案內容:

將每批料號所對應的內容更新到標籤編輯檔上，將最後的明細結果列印下來。

開發技術:

利用Microsoft.Office.Interop.Excel套件製作EXCEL匯入功能。

呼叫WebAPI帳密驗證方式取得回傳資料，並將JSON格式資料進行分析處理。


8.外箱包裝秤重系統

專案內容:

選擇先前設定好的產品上下限、標準值和包裝入數，並設定外箱重量，來進行產線外箱包裝秤重作業檢測。

開發技術:

利用Socket、SerialPort進行設備與內部網站連線。

利用Microsoft.Office.Interop.Excel套件製作EXCEL匯出功能。

利用Array.copy處理RS232收值不完全的問題。

9.產品良率檢測系統

專案內容:

與各站PLC設備進行連線，將各站檢測結果進行資料分析處理。

開發技術:

利用非同步處理(Thread.start)，分別對各站進行所需執行的任務。

利用Socket、SerialPort通訊進行設備連線。

利用Microsoft.Office.Interop.Excel套件製作EXCEL匯出功能。




