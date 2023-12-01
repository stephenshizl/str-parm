# str-parm
Android str_parms for audio
str_parms深入分析
在了解android audio，梳理audio hal的流程时，遇到这样一个数据结构，struct str_parms, 查看代码的上下文，它在这里的主要功能是用来对各种参数进行set与get操作的。其底层采用hash map实现，并通过链接法解决哈希碰撞。
1: Extract the card and device numbers from the supplied key/value pairs.
struct str_parms * parms = str_parms_create_str(kvpairs);
*card = -1;
*device = -1;
param_val = str_parms_get_str(parms, "card", value, sizeof(value));
    if (param_val >= 0) {
        *card = atoi(value);
    }

    param_val = str_parms_get_str(parms, "device", value, sizeof(value));
    if (param_val >= 0) {
        *device = atoi(value);
    }

