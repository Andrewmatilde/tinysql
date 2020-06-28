# Parser

## 概述

完成 `JoinTable`即可，实际上会一点Parser相关知识就容易很多。

第一，编译附送的goyacc工具，相信很多人会既没看Makefile也没看到有个goyacc文件夹

第二，编写JoinTable相关的代码，基本上照着MySQL的文档写就行了，制导翻译部分去看看ast的定义填就行

## 推荐材料

推荐直接给MySQL的[Join Clause](https://dev.mysql.com/doc/refman/5.7/en/join.html)文档

同时感觉先了解一下基础的的Parser如何写比较好，推荐两篇同学写的Blog

[最简单的Parser写法--含回溯的递归自顶而下分析]([https://longfangsong.github.io/2020/05/17/%E6%9C%80%E7%AE%80%E5%8D%95%E7%9A%84Parser%E5%86%99%E6%B3%95%E2%80%94%E2%80%94%E5%90%AB%E5%9B%9E%E6%9C%94%E7%9A%84%E9%80%92%E5%BD%92%E8%87%AA%E9%A1%B6%E8%80%8C%E4%B8%8B%E5%88%86%E6%9E%90/](https://longfangsong.github.io/2020/05/17/最简单的Parser写法——含回朔的递归自顶而下分析/))

[一个最简单的编译器实现]([https://longfangsong.github.io/2019/05/21/%E4%B8%80%E4%B8%AA%E6%9C%80%E7%AE%80%E5%8D%95%E7%9A%84%E7%BC%96%E8%AF%91%E5%99%A8%E7%9A%84%E5%AE%9E%E7%8E%B0/](https://longfangsong.github.io/2019/05/21/一个最简单的编译器的实现/))



Tip: 建议增加一些测试，Parser写的不对，会出现之后别的地方出问题，还比较难发现问题所在

Tip: 同样建议把原有的/* Your code here */这种提示改成和后面统一的TODO的模式

