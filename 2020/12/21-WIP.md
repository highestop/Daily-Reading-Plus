# [Modern storage is plenty fast. It is the APIs that are bad.](https://itnext.io/modern-storage-is-plenty-fast-it-is-the-apis-that-are-bad-6a68319fbc1a)

> 阅读来源：https://github.com/daily-reading/daily-reading/tree/main/2020/12/11

作者认为在硬件储存性能大幅提升的大背景下，I/O 暴露出了因为本身的历史遗留「 成见 」或「 假设 」引起的问题。例如：

- I/O 的成本很高。其实之前可能高于虚拟内存和缓存等，但现在差异已经很小了
- OS 默认会有读放大策略，但其实这种 read-ahead 的 amplification 会浪费性能（ 这里提到了随机读和顺序读，以及单文件多文件几种不同场景的比较 ）
- 传统观念中没有重视并行效率，这与现代 OS 的理念是相悖的

作者提到了一些优化 API 的措施，例如缓冲、动态配置、定制化一些策略等，并且用测试去验证了其效果

对文中提到的不少细节不是很懂，大致了解了下系统 I/O 的现状和在现代存储系统中面临的问题。底层设施是硬件，在性能越来越好的时代，可能要打破一些之前的假设，改变角度去做一些上层 API 的优化，来提升整体储存系统的性能。这一点其实也可以类比到无线端开发上。之前总是面临各种弱网环境的问题假设，做很多网络层面的优化，但在网络整体环境越来越好的今天，可能很多端上应用的性能瓶颈并不在网络环境上，而是在应用本身的结构组织不合理上。比如请求过多可能比因为接收了大量数据而多次渲染造成的影响要小得多，应该先考虑优化后者

# [How Netflix Scales its API with GraphQL Federation (Part 1)](https://netflixtechblog.com/how-netflix-scales-its-api-with-graphql-federation-part-1-ae3557c187e2)

# [How Netflix Scales its API with GraphQL Federation (Part 2)](https://netflixtechblog.com/how-netflix-scales-its-api-with-graphql-federation-part-2-bbe71aaec44a)
