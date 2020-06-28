#  System R 和 Cascades

## 概述

这部分首先是参考二十四章经3-8章的内容，首先完成 System R 版本的，rule_predicate_push_down.go中的Aggregation部分代码，然后再根据Cascades 框架写同样部分，不同框架的代码。

主要的工作是，筛选plan tree中上部传来的表达式中各列都包含在GroupByCols中的部分，讲这些表达式下推到子树中去。

这部分代码可以非常直观的理解传统框架 和 Cascades框架的不同，显然在写System R 中的优化规则时，上下文的传入和传出都是十分担心的一个点，在写Cascades框架的代码时，直接的针对优化情况进行建模使得写代码的抽象层次非常清晰。

# Join and Access Path Selection

这部分内容主要针对Join部分，似乎相关资料有些不足，CMSketch这部分代码我一开始第一个测试样例怎么都过不去，后来看到一个降低这个算法的误差的优化方式才过了。

后面的两个算法我没写过，资料有些少，似乎也不算在评分项内。