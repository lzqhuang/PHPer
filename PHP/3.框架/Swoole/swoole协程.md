## 协程Go
1. 用户态线程，遇到IO主动让出
2. PHP代码依然是串行执行的，无需加锁
3. 开销极低，仅占用内存，不存在进程/线程切换开销
4. 并发量大，单个进程可开启50W个协程
5. 随时随地，只要你想并发，就调用go创建新协程
## 示例代码 
```
go(function () {
    echo "hello go1 \n";
});

echo "hello main \n";

go(function () {
    echo "hello go2 \n";
});
```

go() 是 \Co::create() 的缩写, 用来创建一个协程, 接受 callback 作为参数, callback 中的代码, 会在这个新建的协程中执行.

## 协程适合的是 **IO 密集型** 应用
协程适合的是 **IO 密集型** 应用, 因为协程在 **IO阻塞** 时会自动调度, 减少IO阻塞导致的时间损失.
# Swoole4 协程与 Go 协程有哪些区别
###  1. 多线程
* Swoole4的协程调度器是单线程的，因此不存在数据同步问题，同一时间只会有一个协程在运行
* Go协程调度器是多线程的，同一时间可能会有多个协程同时执行
1. 

