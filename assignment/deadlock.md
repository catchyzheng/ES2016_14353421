 ## 嵌入式系统导论 lab4 实验报告
  姓名：郑铠奇

  学号：14353421


 ### 一. 运行截图
 死锁发生在第261次。
![image](http://r.photo.store.qq.com/psb?/dce13127-d94c-48ba-bb6c-c4180755b0f2/lMnKk3f*FZvyCVBgF1qvva9x6USlRmXum9NVUN57VNg!/o/dMgAAAAAAAAA&bo=.gLxAfoC8QEDACU!&rf=viewer_4)
 ### 二. 产生死锁四个必要条件
 1.互斥使用：至少有一个资源必须处于非共享模式，即资源每次只能给一个进程使用；

 2.占有并等待： 一个进程必须占有至少一个资源，并等待另一其他进程占有的资源

 3.非抢占：资源不能抢占，即资源只能在进程完成任务后自动释放

 4.循环等待：有一组等待进程{P0,P1,…Pn}, Pn-1等待的资源被Pn占有，Pn被P0占有
 ### 三. 对上述死锁生成的解释
调用一个t线程占用b的资源同时请求a的资源，等待20000次减法运算之后用主函数占用a的资源同时请求b的资源，如果碰巧主函数拥有a的资源请求b的资源，与此同时t线程占有b的资源等待a的资源，那么主函数会一直等待t线程释放资源，t线程也会一直等待主函数释放资源，形成死锁