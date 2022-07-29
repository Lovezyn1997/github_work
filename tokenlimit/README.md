Go分布式令牌桶限流 + 兜底策略 

工作原理

1、单位时间按照一定速率匀速的生产 token 放入桶内，直到达到桶容量上限。

2、处理请求，每次尝试获取一个或多个令牌，如果拿到则处理请求，失败则拒绝请求。

<img src="https://oscimg.oschina.net/oscnet/up-48f93b8becb58f39c07f3963253d0aa1462.png" alt="Architecture" width="600" />

优点：可以有效处理瞬间的突发流量，桶内存量 token 即可作为流量缓冲区平滑处理突发流量。

缺点：实现较为复杂。

获取令牌：

<img src="https://oscimg.oschina.net/oscnet/up-56a1eefa50a21971e415b091afb49185be7.png" alt="Architecture" width="600" />