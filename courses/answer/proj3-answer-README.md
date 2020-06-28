# DDL

## 概述

完成了`Drop Column` 涉及的[一些代码](https://github.com/pingcap-incubator/tinysql/blob/course/ddl/column.go#L216)。

参考[这里](https://github.com/ngaut/builddatabase/blob/master/f1/schema-change.md)，编写在三个Drop Colum 的 并行状态中切换状态的[代码](https://github.com/Andrewmatilde/tinysql/blob/course/ddl/column.go#L220)。





Tip1：TODO 中说要加 [adjustColumnInfoInDropColumn](https://github.com/Andrewmatilde/tinysql/blob/course/ddl/column.go#L224)

我并没有没理解怎么加，猜了一个做法，不过测试也过了，似乎针对测试，不写也能过。

Tip2：这部分感觉有点迷惑，资料也比较少，希望有一些这方面的源码剖析吧