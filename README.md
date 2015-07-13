# linux-RPCs
Linux进程间通信方式汇总

# 目前已包含的方式
1. 管道(PIPE)
2. FIFO(有名管道)
3. XSI消息队列
4. XSI信号量
5. XSI共享内存
6. POSIX信号量
7. 域套接字(Domain Socket)
8. 信号(Signal)
9. 互斥量(Mutex)

其中信号(signal)和信号量(semaphore)本质上并不算是进程间通信方式，应该是进程间同步的方式，但是也可以起到一定的通信作用，故也列在上面。

另外普通的mutex是作用线程间同步用的，但是可以将进程A和进程B共享的内存中初始化一个mutex，这样就可以用将此mutex用作进程间通信用了。

# 扩展
##进程与内核通信
其实本来的计划是分两个大块，一块写进程间通信，一块写内核与用户空间通信。后来时间有限，内核与进程间只写了一个netlink，所以没有放到这里，等以后有时间了再补充吧。
##线程间同步
同一个进程的多个线程在同一个地址空间，通信是很容易的事情，因此多线程间要同步就好了。写了一个linux多线程的同步方式的汇总，在以下仓库中[clpsz/linux-itss](https://github.com/clpsz/linux-itss)，供参考，欢迎讨论。
