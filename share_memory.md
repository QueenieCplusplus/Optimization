# Optimization_ShareMemory
共用資源(不被社區支持)

筆者與設計社區認為共用變數是程式設計的下策，因為其複雜且具有資源競奪得競爭性，倘若規模擴展，將會有無法預期且不可測的各種結果。

共用資源適用於多執行緒採用的併行處理，資源利用其實可以利用『管線切換的資源調度』解決方案，如下
https://github.com/QueensC/Optimization_Thread/blob/master/README.md#optimize-pipeline-優化管線處理

共用資源互斥鎖的運行代價高，以免鎖編程作為解決方案
https://github.com/QueensC/Optimization_Memory#lock-free

