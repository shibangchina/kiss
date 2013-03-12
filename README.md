kiss
====

Kiss is a stupid system (Kiss 采集站专用后台)

按照计划，Kiss分三版，现在使用的是Kiss2

-Kiss1 面向过程的解析Sqlite3数据库，一般只用来解析一个数据库，复用很不方便

-Kiss2 面向对象的方法从新设计，方便多目录，多数据库

-Kiss3 PHP的模块实现，用C++语言编写，更快速。

Kiss2使用方法见：http://bbs.shibang.cn/forum.php?mod=viewthread&tid=1033

CHANGES
======
2013年03月12日

感谢忠营反馈，发现了上一篇/下一篇中，得到上一篇总id总是1的bug，Kiss1中，我们直接用$id-1得到上一篇，这样如果rowid和posttime不成正比会遇到问题，所以Kiss2按发布时间获取上一篇/下一篇。但是获取上一篇的时候没有按照rowid排序，得到的总是最小的一个.本次改动，修改getPostsByNeighbor为Kiss1的方法，更快速，增加getPostsByNeighbor2为kiss2的调用方法，更准确。
修改该bug只需覆盖Kiss.php即可。改动：https://github.com/shibangchina/kiss/commit/148d1a5a43232e286942eeaaaa2718c4011b0a92

2013年01月08日

Kiss2发布
