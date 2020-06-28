# DDL

## 概述

`Drop Column` 涉及的[一些代码](https://github.com/pingcap-incubator/tinysql/blob/course/ddl/column.go#L216)。

参考[这里](https://github.com/ngaut/builddatabase/blob/master/f1/schema-change.md)了解主要是要写什么，在三个StateTag中写切换状态的代码。

TODO 中说要加 adjustColumnInfoInDropColumn

我是真的没理解怎么加，不过测试也就过了。



Tip：这部分感觉有点迷惑，资料也比较少，希望有一些这方面的源码剖析吧