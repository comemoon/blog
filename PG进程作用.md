
# [PG进程作用](http://note.youdao.com/noteshare?id=21ae3240351fe17e8de66a764d0d61eb&sub=27AC4B408D364263AAD6EC6D0DE22E6A)

## postmaster
所有数据库进程的主进程(负责监听和fork子进程)
## startup 
主要用于数据库恢复的进程
## syslogger 
记录系统日志
## pgstat 
收集统计信息
## pgarch
如果开启了归档, 那么postmaster会fork一个归档进程.
## checkpointer 
负责检查点的进程
## bgwriter
负责把shared buffer中的脏数据写入磁盘的进程
## autovacuum lanucher 
负责回收垃圾数据的进程, 如果开启了autovacuum的话,那么postmaster会fork这个进程.
## autovacuum worker
负责回收垃圾数据的worker进程, 是lanucher进程fork出来的.
