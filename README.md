# distributed-theory
Distributed theory

# cap
计算机领域，cap定理，又叫布鲁尔定理。cap具体内容为，在分布式数据存储方面，不能确保如下三个方面超过两个：

Consistency：每次读都能读到最新的写入内容或者错误；（Every read receives the most recent write or an error）

Availability：每次请求都会收到非错误的响应，但不保证读到最新的内容；（Every request receives a (non-error) response – without guarantee that it contains the most recent write）

Partition tolerance ：节点之间允许出现部分消息丢失系统还能正常运行（The system continues to operate despite an arbitrary number of messages being dropped (or delayed) by the network between nodes）

没有系统能够避免网络连接失败，所以网络分区是必然的，所以我们就只能在Consistency和Availability之间选择其一了，在发生网络分区时，当我们选择Consistency的时候，在系统不能更新到最新的内容时，会返回error或者超时。当我们选择Availability时，查询依然会返回最新可用的值，即使它不能保证是最新的值。

 cap理论常常被人误解，被认为是三者不能具备的。事实上，在没有网络分区的情况下，是可以兼备三者的。

