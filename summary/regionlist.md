# 获取地域和可用区列表

UCloud 目前拥有 25 大地域（Region），分别是北京一、北京二、金融云、上海二、广州、福建、杭州、香港、洛杉矶、华盛顿、莫斯科、法兰克福、东京、曼谷、首尔、新加坡、高雄、台北、迪拜、雅加达、孟买、圣保罗、伦敦、拉各斯和胡志明。每个地域下开设有多个可用区（Zone），用户在使用公有云相关的 API 发送操作指令时，需要指定指令所指向的地域。

<!-- tabs:start -->

#### ** CURL **

?> 通过 CURL 发起请求需要手动计算签名，签名计算方法请参考 [签名算法](https://docs.ucloud.cn/api/summary/signature)。

```bash
curl -X POST \
  https://api.ucloud.cn \
  -H 'Content-Type: application/json' \
  -d '{
    "Action":"GetRegion",
    "PublicKey":"...",
    "Signature":"..."
  }'
```

!> 建议使用 CLI/SDK/UAPI 等工具发起查询，无需关心签名参数等问题。

#### ** CLI **

**安装**

```bash
brew install ucloud
ucloud init
```

?> 按照提示输入密钥信息，密钥信息可以从 [此页面](https://console.ucloud.cn/uapi/apikey) 获取。

**查询**

```bash
ucloud region list
```

#### ** SDK **

**安装**

```bash
pip install ucloud-sdk-python3
```

**查询**

```python
from ucloud.client import Client

client = Client({"public_key": "...", "private_key": "..."})
client.uaccount().get_region()
```

?> 请将代码片段中的 key 替换为自己的公私钥，密钥信息可以从 [此页面](https://console.ucloud.cn/uapi/apikey) 获取。

<!-- tabs:end -->

## 附录

### 速查表

#### 各地域 (Region) 名称列表

| 地域名称   | 地域短ID         | 可用区                            |
|---|---|---|
|	北京一	|	cn-bj1	|	北京一可用区A	|
|	北京二	|	cn-bj2	|	北京二可用区B	|
|	北京二	|	cn-bj2	|	北京二可用区C	|
|	北京二	|	cn-bj2	|	北京二可用区D	|
|	北京二	|	cn-bj2	|	北京二可用区E	|
|	上海金融云	|	cn-sh	|	上海金融云可用区A	|
|	上海金融云	|	cn-sh	|	上海金融云可用区B	|
|	上海金融云	|	cn-sh	|	上海金融云可用区C	|
|	上海二	|	cn-sh2	|	上海二可用区A	|
|	上海二	|	cn-sh2	|	上海二可用区B	|
|	上海二	|	cn-sh2	|	上海二可用区C	|
|	广州	|	cn-gd	|	广州可用区B	|
|	广州二	|	cn-gd2	|	广州二可用区A	|
|	福建	|	cn-qz	|	福建GPU可用区A	|
|	香港	|	hk	|	香港可用区A	|
|	香港	|	hk	|	香港可用区B	|
|	台北	|	tw-tp	|	台北可用区A	|
|	台北二	|	tw-tp2	|	台北二可用区A	|
|	高雄	|	tw-kh	|	高雄可用区A	|
|	东京	|	jpn-tky	|	东京可用区A	|
|	首尔	|	kr-seoul	|	首尔可用区A	|
|	曼谷	|	th-bkk	|	曼谷可用区A	|
|	新加坡	|	sg	|	新加坡可用区A	|
|	雅加达	|	idn-jakarta	|	雅加达可用区A	|
|	胡志明市	|	vn-sng	|	胡志明市可用区A	|
|	洛杉矶	|	us-ca	|	洛杉矶可用区A	|
|	华盛顿	|	us-ws	|	华盛顿可用区A	|
|	莫斯科	|	rus-mosc	|	莫斯科	|
|	法兰克福	|	ge-fra	|	法兰克福可用区A	|
|	伦敦	|	uk-london	|	伦敦可用区A	|
|	孟买	|	ind-mumbai	|	孟买可用区A	|
|	迪拜	|	uae-dubai	|	迪拜可用区A	|
|	圣保罗	|	bra-saopaulo	|	圣保罗可用区A	|
|	拉各斯	|	afr-nigeria	|	拉各斯可用区A	|


#### 各可用区 (Zone) 名称列表

|可用区名称     |API名称            |
|---|---|
|	北京一可用区A	|	cn-bj1-01	|
|	北京二可用区B	|	cn-bj2-02	|
|	北京二可用区C	|	cn-bj2-03	|
|	北京二可用区D	|	cn-bj2-04	|
|	北京二可用区E	|	cn-bj2-05	|
|	上海金融云可用区A	|	cn-sh-01	|
|	上海金融云可用区B	|	cn-sh-02	|
|	上海金融云可用区C	|	cn-sh-03	|
|	上海二可用区A	|	cn-sh2-01	|
|	上海二可用区B	|	cn-sh2-02	|
|	上海二可用区C	|	cn-sh2-03	|
|	广州可用区B	|	cn-gd-02	|
|	广州二可用区A	|	cn-gd2-01	|
|	福建GPU可用区A	|	cn-qz-01	|
|	香港可用区A	|	hk-01	|
|	香港可用区B	|	hk-02	|
|	台北可用区A	|	tw-tp-01	|
|	台北二可用区A	|	tw-tp2-01	|
|	高雄可用区A	|	tw-kh-01	|
|	东京可用区A	|	jpn-tky-01	|
|	首尔可用区A	|	kr-seoul-01	|
|	曼谷可用区A	|	th-bkk-01	|
|	新加坡可用区A	|	sg-01	|
|	雅加达可用区A	|	idn-jakarta-01	|
|	胡志明市可用区A	|	vn-sng-01	|
|	洛杉矶可用区A	|	us-ca-01	|
|	华盛顿可用区A	|	us-ws-01	|
|	莫斯科	|	rus-mosc-01	|
|	法兰克福可用区A	|	ge-fra-01	|
|	伦敦可用区A	|	uk-london-01	|
|	孟买可用区A	|	ind-mumbai-01	|
|	迪拜可用区A	|	uae-dubai-01	|
|	圣保罗可用区A	|	bra-saopaulo-01	|
|	拉各斯可用区A	|	afr-nigeria-01	|

### GetRegion

获取用户在各地域的权限等信息

#### Response Elements

|Name        |Type   |Description                       |
|---|---|---|
|Action      |String |响应动作: GetRegionResponse      |
|RetCode     |Integer|执行成功与否，0表示成功，其他值则为错误代码            |
|Regions    |Array  |JSON格式的各地域信息，每项参数参见下面的 Regions|

#### Regions 

| Name        | Type     | Description                                                         |
|---|---|---|
| RegionId    | Integer  | 地域ID                                                                |
| RegionName  | String   | 地域名称，若API调用，请参考Region字段                                             |
| IsDefault   | Bool     | 是否用户当前默认地域                                                          |
| BitMaps     | String   | 每一位表示一个权限位，为1则为启用，为0表示未启用相应功能。例：0000001，权限位1、2、3、4、5、6均为关闭，权限位7为开启  |
| Region      | String   | 地域                                                                  |
| Zone        | String   | 可用区名字，如cn-bj-01                                                     |

#### Request Example

```
https://api.ucloud.cn/?Action=GetRegion
```

#### Response Example

```
{
    "Action" : "GetRegionResposne",
    "RetCode" : 0,
    "Regions" : [{
        "RegionId" : 1,
        "RegionName" : "cn-bj1",
        "IsDefault" : true,
        "BitMaps" : "0111110000101010101101010101",
        "Region" : "cn-bj1",
        "Zone" : "cn-bj1-01"
    }]
}
```
