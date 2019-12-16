# Optimization_Thread
線程的優化

# Intro

現今電腦的微型處理器均具備多核心，多核心三字拆解給執行單元和記憶體的意思是，多核心架構藉由高度運行的管線 Pipeline Switch | Chain Switch 切換處理或稱情境切換 Context switch，因而能控制 thread 線程，配置合理的執行單元 unit 和層層關卡的 cache 快取。

而現在風靡的 Google 語言 Golang 是併行語言，利用 go 關鍵字可做迸發執行，關於此語言的語法可詳見我的另一篇技術著作儲存庫：github/poupougo，然而這樣的併行架構，倘若強行施行於桌機等級的處理器，可能程式碼仍然無法有效地運行其特色： Concurrency (a.k.a Parallel)。

程式碼能否線程化 threadable 亦取決於資料結構，因為調整 thread 比起配置記憶體可能還更加困難，即使經驗老道的 coder 都可能不甚熟悉。

# Concept

* Event-Oriented, 事件導向

            引用函數庫的事件處理函數 Event-Handler，這些函數提供框架調用呼叫。（手機元件經常使用，實作方面可參考安卓的 Broadcast 系統廣播功能。）

            運作方式：
            底層框架會將每一事件從事件佇列 Event-Queue 中傳給註冊要處理該事件的處理器函數 Handler (即 Func) ，其實事件導向運作方式等同於任務導向 Task-Oreineted，可詳見 Task Scheduler 或是 Scheduler 的源代碼，兩者差別在於事件處理器並非迸行處理的！
            
            （拉軸免覆蓋）
            

* Co-Routine, 協同程序

             coroutine 非多線程 multi-thread的同義詞，故並不需要同步執行，協同程序會明確地將執行權利從一 obj 轉交 另一 obj 中可供 call 的 obj。

             運作方式：
             利用自身的 stack，在 runtime 時任何一時間點上能放棄對另一 coroutine 的控制權。
             執行權移轉的當下，執行指標 execution Ptr 將會被記錄下來，倘若 recall，將可 resume。
             （拉軸免覆蓋）

* Pass-Msg, 傳遞訊息（分散式處理系統的元件之一，Unix 利用管線傳遞訊息）

             意象概念：
                        ＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿ 
                          
                              輸出進入  輸出退出   （管線）
                          
                        ＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿

             運作方式：
             傳遞訊息時，控制線程會從一或多來源取得輸入，轉換後，放進一或多目的地輸出槽 output sink。

              實作方式：
              這些實作訊息傳遞每一階段的 thread 所 r/w 的 items，可被實作成網路資料包 datagrams | 串流 stream| 佇列 queue。
              
              （拉軸免覆蓋）
              
# Optimize Pipeline, 優化管線處理

  管線本身比共用資源，在處理器使用上具有優勢，因為它不會遇到互斥鎖而讓時間慢下來的因素。
            

# Code

筆者將於此議題實作命名空間為 std 而方法調用 async() 以及 thread() 作為優化線程的範例。

... TBD 尚未完成
