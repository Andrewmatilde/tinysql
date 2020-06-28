# 执行模型: 火山模型和向量化

实现了[vecEvallnt](https://github.com/Andrewmatilde/tinysql/blob/course/expression/builtin_string_vec.go#L89)和selection的[Next](https://github.com/Andrewmatilde/tinysql/blob/course/executor/executor.go#L380)函数，完成了原有算法的向量化

编写[vecEvallnt](https://github.com/Andrewmatilde/tinysql/blob/course/expression/builtin_string_vec.go#L89)过程中有一个难点的地方在于处理[null map](https://github.com/Andrewmatilde/tinysql/blob/course/util/chunk/column.go#L30)，要根据测试了解Chunk的结构，再进行Debug。

selection部分的核心在于理解执行器，通过调用Next子树实现各节点之间的chunk交换，
自顶向下遍历计划树，然后再自底向上的返回，最终输出执行结果，主要编写的就是在此基础上进行 行过滤。

Tip：这部分代码的难点在于，很多代码要做好那些事情非常不明确，
从中间开始写代码，很多需求说明都要自己考虑，没有那种从头写起的明确性，希望提供更多的源码剖析材料。

# Hash Join&Hash Aggregate

这两部分代码，基本都在完成在course文档中说明的内容，
内容比较多，代码量也比较大。在编写过程中，花费了大量时间Debug，还有一个Test不会处理Bug，
感觉这个并发执行模型的写起来真的感觉非常的不直观，希望未来能有个更易读的框架。



Tip1：第五课基本上代码的链接都是坏的

Tip2：[向量化的进行计算](https://docs.google.com/document/d/1JKP9YS3wYsuXsYhDgVepJt5y72K6_WxhUVfOLyjpAjc/edit#heading=h.66r4twnr3b1c) 这个链接点进去居然和我说需要访问权限
