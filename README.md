# str-parm
Android str_parms for audio
str_parms深入分析
在了解android audio，梳理audio hal的流程时，遇到这样一个数据结构，struct str_parms, 查看代码的上下文，它在这里的主要功能是用来对各种参数进行set与get操作的。其底层采用hash map实现，并通过链接法解决哈希碰撞。

