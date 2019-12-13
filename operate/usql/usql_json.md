# 展开json字段

展开json字段嵌套信息，并按上报自定义字段信息查询完整traceroute信息： 

```sql
select
  definedata.key as definekey,
  definedata.val as definevalue,
  traceroutedata.delay,
  traceroutedata.loss,
  traceroutedata.route_ip
from(
  select traceroutedata,definedata
  from traceroute,unnest(traceroute.data.route_info) as t1(traceroutedata),
  unnest(traceroute.user_defined) as t2(definedata) where definedata.key = 'key1'
);
```



查询结果如下： 

![](https://raw.githubusercontent.com/UCloudDocs/umqa/dev/imgs/operation_13.png)