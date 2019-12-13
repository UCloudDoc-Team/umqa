# 源数据字段解释

在使用数据湖(USQL)分析网络源数据之前，我们先介绍一下源数据中部分字段的含义。

|    字段名    |     类型     | 含义                                                         |
| :----------: | :----------: | :----------------------------------------------------------- |
|    app_id    | varchar(200) | andorid是APP包名，iOS是build id，集成SDK后自动上报，控制台 'APP管理' 页面可查看 |
|   platform   | smallint(6)  | 移动端系统类型，0表示安卓，1表示苹果                         |
|     ver      | varchar(100) | SDK版本号                                                    |
|   net_type   | varchar(40)  | 网络类型，如：WIFI、4G、3G等                                 |
|    src_ip    |   char(15)   | 移动外网出口ip                                               |
|      t       |  bigint(20)  | SDK探测网络质量的时间戳                                      |
|    delay     |  bigint(20)  | 延迟(ms),缩放倍数 1,000,000                                  |
|     loss     |  bigint(20)  | 丢包率(%),缩放倍数 1,000,000                                 |
|    dst_ip    |   char(15)   | 目标探测服务节点ip                                           |
| ping_status  | smallint(6)  | 移动端100%丢包，二次探测8.8.8.8结果。0表示丢包数据真实，1表示丢包数据无效 |
| user_defined |     JSON     | 用户自定义字段{json 字符串},SDK校验最大长度1024字节          |
|     data     |     JSON     | 移动用户探测的完整路由信息，ping源数据无该字段               |
|   country    | varchar(50)  | 移动端网络所在国家                                           |
|    region    | varchar(50)  | 移动端网络所在省级行政区域                                   |
|     city     | varchar(50)  | 移动端城市名，空值表明网络基站可能在省级行政区域或数据缺失   |
|      tz      | varchar(20)  | 移动端所在时区                                               |
|     isp      | varchar(20)  | 移动端网络运营商                                             |

