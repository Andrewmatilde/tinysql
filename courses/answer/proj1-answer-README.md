# Table Codec

## 详情

代码实现了 [DecodeRecordKey](https://github.com/pingcap-incubator/tinysql/blob/course/tablecodec/tablecodec.go#L72)和 [DecodeIndexKeyPrefix](https://github.com/pingcap-incubator/tinysql/blob/course/tablecodec/tablecodec.go#L95).

基本上是按照对应的编码过程进行解码，

Key 组成部分会存在不合法情况，已经进行长度判断，如果不符合，会触发错误。