# Table Codec

## 概述

代码实现了 [DecodeRecordKey](https://github.com/Andrewmatilde/tinysql/blob/course/tablecodec/tablecodec.go#L73)和 [DecodeIndexKeyPrefix](https://github.com/Andrewmatilde/tinysql/blob/course/tablecodec/tablecodec.go#L108).

基本上是按照对应的编码过程进行解码，

Key 组成部分会存在不合法情况，已经进行长度判断，如果不符合，会触发错误。



Tip1：测试过程写在一个新增的workflow [go_course_test](https://github.com/Andrewmatilde/tinysql/blob/course/.github/workflows/go_course_test.yml) 里了，之后的测试都会增加在里面。

Tip2：建议把原有的[/* Your code here */](https://github.com/pingcap-incubator/tinysql/blob/course/tablecodec/tablecodec.go#L74)这种提示改成和后面统一的TODO模式