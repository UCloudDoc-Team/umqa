# 概念介绍

## 什么是UMQA源数据

用户集成开源 SDK 代码时，提供用户接口用于自定义探测目标服务 IP;源数据即指 SDK 对该 IP 进行探测的网络延迟、丢包、运营商等信息的原始上报数据。若未设定 IP，则如图所示。



后续 `UMQA`将向客户开放该 APP 针对 `UCLOUD` 数据中心的源数据质量探测，用户可以直接转 存查看。 

![](https://raw.githubusercontent.com/UCloudDocs/umqa/dev/imgs/intro_02.png)

## 源数据适用于什么样的场景

* `ping`源数据：统计分析移动端运营商(ISP)、网络类型、地理位置、网络延迟、丢包等。 若仅查看整体网络质量结果，建议在移动网络数据页面定义条件查询，UCLOUD 根据网络运 营经验提供质量评测打分以供参考。
* `trace route`源数据:配合自定义上报字段(`user_defined`)定位具体移动用户的网络故障。 

## 源数据转存、运营分析设计哪些公有云产品支持？

* `UMQA`: 注册APP、集成SDK、源数据转存的管理窗口。
* `UFile`: 一个对象存储产品，主要用于存储SDK上报源数据和`USQL`的查询结果，产品文档：https://docs.ucloud.cn/storage_cdn/ufile/index
* `USQL`: serverless数据分析工具，按扫描分析数据量的规模计费，无需搭建任何数据库、分析平台， 控制台服务闭环、便宜，产品文档： https://docs.ucloud.cn/analysis/usql
* 以上三个产品必须切至源数据所在的 UFILE 地域(即所选的数据中心必须一致)。目前暂时不支持跨域扫描源数据。 

![](https://raw.githubusercontent.com/UCloudDocs/umqa/dev/imgs/intro_03.png)

## UMQA与UFile、USQL的关系

UMQA单独也可以工作，只不过能查询到的网络数据只有控制台提供的几个维度的结果。如果控制台提供功能不能满足你们的需求，你们可以把源数据通过转存UFile，用USQL按照自己的逻辑做数据分析。它们之间的关系如下：

![](https://raw.githubusercontent.com/UCloudDocs/umqa/dev/imgs/intro_04.png)