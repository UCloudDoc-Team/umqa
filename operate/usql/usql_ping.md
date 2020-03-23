# 创建表用于展示ping源数据 

a. 进入到刚刚你创建的数据库并选择创建数据表。如下图所示：

![](/images/operation_09.png)



![](/images/operation_10.png)



b. 把网页上显示的原始脚本清除掉，并把下列建表语句稍作修改执行。

```sql
# 创建接收ping结果的表
CREATE EXTERNAL TABLE ping(
    app_id string,
    country string,
    region string,
    city string,
    dst_ip string,
    delay string,
    loss int,
    isp string,
    net_type string,
    ping_status string,
    src_ip string,
    platform int,
    t int,
    ver string,
    user_defined array<
        struct<
            key:string,
            val:string
        >
    >
)
ROW FORMAT SERDE 'org.openx.data.jsonserde.JsonSerDe'
WITH SERDEPROPERTIES (
'serialization.format' = '1'
)
LOCATION 'ufile://umqa-org-0czmci-uciosdemo/umqa/ping/uciosdemo'
TBLPROPERTIES(
'has_encrypted_data'='false'); 
```



预览ping表，如下图：

 ![](https://raw.githubusercontent.com/UCloudDocs/umqa/dev/imgs/operation_11.png)



注意：

1. 上面建表脚本的第28行表示的就是你的上报源数据所在的目录，USQL会自动扫描该目录，并把数据自动录入表中。此处你需要修改成自己源数据所在的UFile目录。 

2. 如果你的数据量很大，你还可以为你创建的表添加分区，用于防止因数据量过大而导致的查询速度变慢。

3. `UFile`和`USQL`所选必须是同一区域(示例中同时上海二区域)。

4. 上面的建表语句只是个示例，你可以按照自己的需求定义所要展示的字段。

5. 创建完ping表之后，你可以按照自己的需求写出各种灵活的SQL查询自己想要查询的不同纬度的网络数据。

   