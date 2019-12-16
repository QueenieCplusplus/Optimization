# Optimization_Memory
記憶體相關的優化處理

因為共用記憶體不是每個 CPU 和 GPU 架構都有提供的，故傳遞訊息顯得相當重要了！ 而且真正的擴展 Scale Up 基礎不在共用資源，而是透過管線 Pipeline (a.k.a Chain) 方法來達成。

# Lock Free using Atomic

免鎖🔒編程，利用硬體進行同步的原子操作 atomic operations，允許多線程不需要互斥，即能更新資料。

# Lifecycle of Var

* assign, 使用記憶體資源的型別配置

* init, 初始化的置放

* consum, 消耗或使用

* delete, 銷毀

* free, 釋放資源或稱釋出

# Optimize Dynamic Memory

1. 盡可能配置相同大小的記憶體給物件。

2. 要先行考量物件中元素的大小可能不盡相同。

3. 如上，大可能有輸出入緩衝區那麼大，也可能小到僅是一個指標。(有點像是廢話)

4. 設計上，需要明確：
    
        ＊ Ptr Boundaries, 指標邊界

        ＊ Cache Lines, 快取線

        ＊ Pages, 虛擬記憶體頁

5. 已經配置好的變數容器，請有效 reuse 和記得歸還 delete or free。

# Code

筆者將利用 new 建構變數和用 delete 解構其記憶體資源，讓系統有效利用之。

    尚未完成．．．To Be Done.
