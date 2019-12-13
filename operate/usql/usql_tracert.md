# 创建表用于展示traceroute源数据

和创建ping表一下，下面是创建tracerroute表的脚本，你可以稍作修改并执行。

```sql
CREATE EXTERNAL TABLE traceroute(
    app_id               string,
    country              string,
    region               string,
    city                 string,
    dst_ip               string,
    isp                  string,
    net_type             string,
    ping_status          string,
    src_ip               string,
    platform             INT,
    t                    INT,
    ver                  string,
    user_defined         array<
                             struct<
                                  key:string,
                                  val:string
                             >
                         >,
    data struct<
            route_info:array<
                            struct<
                                delay:INT,
                                loss:INT,
                                route_ip:STRING
                            >
                        >
            >
)
ROW FORMAT SERDE 'org.openx.data.jsonserde.JsonSerDe'
WITH SERDEPROPERTIES (
'serialization.format' = '1' )
LOCATION 'ufile://umqa-org-0czmci-uciosdemo/umqa/traceroute/uciosdemo' TBLPROPERTIES(
'has_encrypted_data'='false');
```



执行完成后，预览数据如下： 

![](https://raw.githubusercontent.com/UCloudDocs/umqa/dev/imgs/operation_12.png)