# testlib-for-lexue

适用于乐学平台的`testlib.h`

## 食用指南

考虑到程序设计相关老师/助教的出题需求，需要使用SPJ功能，而基于`testlib.h`的SPJ为当今出题主流，因此修改相关接口以适配乐学平台。

将写好的SPJ的`#include "testlib.h"`修改为此仓库里`testlib.h`即可。

## 后遗症与解决方案

因为乐学比较~~垃圾~~。每一个测试用例都会编译一遍SPJ。会导致判题速度特别慢。

解决方案：

利用乐学现有bug解决。第一次慢了以后，如果把代码改成一个CE的代码，之前的SPJ编译出来的exe文件会继续做为判题代码。因为建议出题老师/助教测试完毕以后，将SPJ代码改回原样（`#include "testlib.h"`）。这样也方便后续再修改，留作记录。

但是这样判题信息里就会多一些无用CE提示，可能需要发公告告诉学生相关含义。大致显示如下：

```
/usr/lib/bitoj/data/cms/validator/0000024075/main.cpp:1:21: fatal error: testlib.h: No such file or directory
 #include "testlib.h"
                     ^
compilation terminated.
ok a circle
```

除最后一行外其他是编译错误信息。但是我们发现，这里依旧正常判题`ok a circle`。

## Warning

乐学大更新、课程复制可能会导致缓存的SPJ编译文件丢失，此时需重新替换一下提交一次即可。
