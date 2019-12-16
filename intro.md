# Optimization_RoadMap

優化效能的總覽，此議題主攻 CPU & Memory。

      [1] Opt for Thread by Using Chainning (Pipeline) , 線程的優化 (管線切換與協同程序)

https://github.com/QueensC/Optimization_Thread

__________________________________________________________________

     [2] Opt for Concurrency, 同步的優化 (除非多線程環境，否則不推薦同步）


請詳上述議題內含的管線切換與協同程序

__________________________________________________________________

      [3] Opt for Dynamic Memory by calling New & Delete, 動態記憶體配置的優化

https://github.com/QueensC/Optimization_Memory

__________________________________________________________________

      [4] Opt for Block using [1][3], 這邊的區塊類似區塊鏈，是共用資源。（不推薦共用資源，推薦上述[1]內含的訊息傳遞）

https://github.com/QueensC/Optimization_ShareMemory

__________________________________________________________________

      [5] Opt for Other Conditions, 其他的優化

   including statement of logic, Lib, data structure, I/O (call chains)etc.
   包含邏輯的敘述、好用的函數庫、資料結構（資料型別的使用與轉換，例如 list, queue, map, set）、輸出入（包含叫用鏈)
   
__________________________________________________________________
   
      [6] Specialization, 特化(泛化的相反)
      
   URL Link provided later.
__________________________________________________________________

# Basement, 效能基礎

(1) MultiPath, 代碼的多重執行路徑

(2) CostPay, 代碼的敘述執行代價

(3) NotSeq, 敘述並非依照順序執行 (與交錯執行有關)

