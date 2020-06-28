#  System R 和 Cascades

## 概述

参考TiDB源码二十四章经3-8章的内容，编写谓词下推优化规则[LogicalAggregation](https://github.com/Andrewmatilde/tinysql/blob/course/planner/core/rule_predicate_push_down.go#L355)部分代码，总体上使用System R框架

再根据Cascades 框架写[类似部分](https://github.com/Andrewmatilde/tinysql/blob/course/planner/cascades/transformation_rules.go#L508)，不同框架下的谓词下推优化规则的代码。

主要的流程是，筛选plan tree中上部传来的表达式中各列都包含在GroupByCols中的部分，讲这些表达式下推到子树中去。



Tip:这部分代码可以非常直观的理解传统框架 和 Cascades框架的不同，
显然在写System R 中的优化规则时，上下文的传入和传出都是我非常关注的地方，
而在写Cascades框架的代码时，直接的针对优化情况进行建模使得写代码的抽象层次非常清晰，
不需要去了解上下文的情况，而是主动框定上下文的格式，进行在此基础上的优化。

# Join and Access Path Selection

实现了Count-Min Sketch 算法，可以进行粗略的数据频率统计，由于精度问题，在此基础上，查阅资料，采用Count-Mean-Min Sketch 算法优化了误差。

完成了CMSketch这[部分代码](https://github.com/Andrewmatilde/tinysql/blob/course/statistics/cmsketch.go#L74)



Tip1：可以添加的资料：[频率估计](https://soulmachine.gitbooks.io/system-design/content/cn/bigdata/frequency-estimation.html)



Tip2：后面的两个算法我没写过，资料有些少，似乎也不算在评分项内。
