# 在UFile中查看转存的源数据

在创建APP并开启源数据转存后，在UFile中可以看到刚刚创建的存储空间`umqa-org-0czmci-uciosdemo`

![](https://raw.githubusercontent.com/UCloudDocs/umqa/dev/imgs/operation_06.png)



在集成SDK到APP并有网络数据上报后，可以在该存储空间下看到上报的源数据文件(数据转存延迟1个小时，所以需要你触发网络诊断后1小时才能查看到)。该存储空间内的文件会按照时间自动生成目录并保存对应时间内的原始网络数据。

![](https://raw.githubusercontent.com/UCloudDocs/umqa/dev/imgs/operation_07.png)



然后就可以使用USQL去灵活查询自己想要的网络数据了。 



