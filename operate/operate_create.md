# 创建APP

首先必须登录控制台，然后进入`全球移动网络 UMQA`

![](/images/operation_01.png)



点击`注册APP`按钮

![](/images/operation_02.png)



编辑APP信息，下面对关键信息做简单介绍。 



1. 表示是否开启源数据转存，默认不开启。如果开启则源数据会转存到`UFile`，你可以利用`USQL`以转存到`UFile`的源数据然后 进行灵活的数据SQL查询。
2. 表示存储地域，你选择的`UFile`存储地域和`USQL`存储地域必须一致。
3. `UFile`的存储空间名，请按照规则填写，后续使用`USQL`的时候会用到。
4. 选择要转存的源数据类型，可以选择只转存`ping`、只转存`traceroute`、两者都转存。
5. 转存源数据的文件名称，请按照规则填写。

![](/images/operation_03.png)



注册好APP后，目前还没有数据上报，如下图所示：

![](/images/operation_04.png)



然后点击`查看APPKey`按钮即可查看APP Key和App Secret,进而这些参数应用你你的APP内集成SDK。 

![](/images/operation_05.png)

