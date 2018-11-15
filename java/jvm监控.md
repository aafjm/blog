### jstack
> oom情况下，查看最耗cpu的线程

- ps -ef | grep java 查看进程id
- top -Hp pid 查出最耗cpu的线程id PID
- printf "%x\n" pid   输出线程id的十六进制数
- jstack 进程id | grep 线程id   打印出日志



### jstat
> jstat [-命令选项] [vmid] [间隔时间/毫秒] [查询次数]

####  jstat -class pid （类加载统计）
- Loaded:加载class的数量
- Bytes：所占用空间大小
- Unloaded：未加载数量
- Bytes:未加载占用空间
- Time：时间

#### jstat -compiler pid（编译统计）
- Compiled：编译数量。
- Failed：失败数量
- Invalid：不可用数量
- Time：时间
- FailedType：失败类型
- FailedMethod：失败的方法

#### jstat -gc pid（垃圾回收统计）
- S0C：第一个幸存区的大小
- S1C：第二个幸存区的大小
- S0U：第一个幸存区的使用大小
- S1U：第二个幸存区的使用大小
- EC：伊甸园区的大小
- EU：伊甸园区的使用大小
- OC：老年代大小
- OU：老年代使用大小
- MC：方法区大小
- MU：方法区使用大小
- CCSC:压缩类空间大小
- CCSU:压缩类空间使用大小
- YGC：年轻代垃圾回收次数
- YGCT：年轻代垃圾回收消耗时间
- FGC：老年代垃圾回收次数
- FGCT：老年代垃圾回收消耗时间
- GCT：垃圾回收消耗总时间