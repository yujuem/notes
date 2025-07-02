# python异步编程
https://liaoxuefeng.com/books/python/async-io/index.html  

## 协程
在一个线程中实现子程序之间的切换，由程序自身控制，没有多线程切换的开销和加锁机制，多进程+协程可以获得极高的性能。  
Python通过生成器（generator）实现对协程的支持，包含yield关键字的函数被称为生成器，会返回一个可迭代的generator对象，可以使用for循环或者调用next()方法遍历generator对象提取结果，可以减少内存资源占用。  

## 使用asyncio
asyncio的编程模型就是一个消息循环。asyncio模块内部实现了EventLoop，把需要执行的协程扔到EventLoop中执行，就实现了异步IO。  
asyncio.run()执行async函数的入口。  
asyncio.gather()同时调度多个async函数。  
await语法用于async函数中调用另一个async函数，线程在await时并未等待，而去执行消息队列里的其他任务，等到返回结果时再执行下一行语句。  

## 使用aiohttp
asyncio实现了TCP、UDP、SSL等协议，aiohttp则是基于asyncio实现的HTTP框架。  
asyncio可以实现单线程并发IO操作，如果把asyncio用在服务器端，例如Web服务器，由于HTTP连接就是IO操作，因此可以用单线程+async函数实现多用户的高并发支持。  

## 1、Ray Core

Tasks: 
无状态函数
资源分配
句柄传递
多返回值与异步等待
Generators
任务取消
任务调度
故障恢复
任务事件
*函数嵌套调用

Actors:
有状态类/对象
资源分配
方法调用
句柄传递
Generators
任务取消
任务调度
故障恢复
任务事件
*具名实例：Create、Get-Or-Greate、Lifetimes（detached实例生命周期独立于driver进程，需要手动kill）
*终止实例：automatic、manual via actor handle、manual within actor method
