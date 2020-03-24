# UMQA源数据转存分析有哪些公有云产品支持？

* `UMQA`: 注册APP、集成SDK、源数据转存的管理窗口。
* `UFile`: 一个对象存储产品，主要用于存储SDK上报源数据和`USQL`的查询结果，产品文档：https://docs.ucloud.cn/ufile/index
* `USQL`: serverless数据分析工具，按扫描分析数据量的规模计费，无需搭建任何数据库、分析平台， 控制台服务闭环、便宜，产品文档： https://docs.ucloud.cn/usql/README
* 以上三个产品必须切至源数据所在的 UFILE 地域(即所选的数据中心必须一致)。目前暂时不支持跨域扫描源数据。 

![](https://raw.githubusercontent.com/UCloudDocs/umqa/dev/imgs/intro_03.png)