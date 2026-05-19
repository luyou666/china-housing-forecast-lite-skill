# Data Sources and Freshness Rules

## Reliability Levels

A Level:
- 国家统计局
- 中国人民银行
- 地方统计局
- 地方住建局
- 地方房地产交易中心
- 地方自然资源和规划局
- 地方公共资源交易中心
- 地方公积金中心
- 地方政府官网

B Level:
- 贝壳研究院
- 链家
- 中指研究院
- 克而瑞
- Wind
- Choice
- CEIC
- 主流财经媒体引用的官方或行业数据

C Level:
- 平台挂牌数据
- 百度指数
- 微信指数
- 安居客热度
- 社交媒体讨论热度
- 中介门店反馈

D Level:
- 自媒体观点
- 房产论坛观点
- 未验证的中介单点口径
- 未注明来源的数据截图

## Search Priority by Data Type

### Price Data

1. 国家统计局 70 城新房/二手房价格指数
2. 地方房地产交易中心
3. 地方住建局
4. 贝壳 / 链家成交或挂牌数据
5. 中指 / 克而瑞
6. 其他平台数据

### Transaction Data

1. 地方房地产交易中心
2. 地方住建局
3. 贝壳 / 链家
4. 中指 / 克而瑞
5. 主流媒体引用的官方或行业数据

### Inventory and Listing Data

1. 地方住建局
2. 地方房地产交易中心
3. 中指 / 克而瑞
4. 贝壳 / 链家挂牌数据
5. 平台挂牌数据

### Credit and Policy Data

1. 中国人民银行
2. 全国银行间同业拆借中心 LPR
3. 地方政府官网
4. 地方住建局
5. 地方公积金中心
6. 主流财经媒体引用的官方政策

### Population and Economy Data

1. 地方统计局
2. 统计年鉴
3. 统计公报
4. 国家统计局
5. 地方政府工作报告
6. 主流财经媒体引用的官方数据

### Land Auction Data

1. 地方自然资源和规划局
2. 地方公共资源交易中心
3. 地方土地市场网或土地交易平台
4. 中指研究院
5. 克而瑞
6. 主流财经媒体引用的土地成交数据

Land auction data is a leading indicator of developer expectations and local land-market sentiment. Land premium rate, failed auction rate, base-price transaction share, and land transaction value are more useful than headline land news.

Land auction data should not override housing transaction and inventory data. If land data conflicts with housing-market data, explain the horizon difference: land market may reflect developer expectations, while second-hand transactions reflect household demand.

## Search Query Templates

Use these templates as retrieval aids when Fresh Data Retrieval Rule is triggered. They are optional references, not mandatory search strings. Use public sources only; do not bypass paywalls, login restrictions, captchas, or anti-bot systems.

### Price Data Queries

```text
{city} 70城 房价指数 二手住宅 最新
{city} 新房 价格指数 环比 同比 最新
{city} 二手房 成交价 最新
{city} 二手房 挂牌价 成交价 对比
国家统计局 70个大中城市 商品住宅 销售价格 {city}
```

### Transaction Data Queries

```text
{city} 二手房 成交量 最新
{city} 二手房 网签 成交 套数 最新
{city} 新房 成交面积 最新
{city} 住建委 房地产交易 成交数据
{city} 房地产交易中心 二手房 网签
```

### Inventory and Listing Queries

```text
{city} 新房 库存 去化周期 最新
{city} 二手房 挂牌量 最新
{city} 二手房 新增挂牌 降价房源
{city} 商品住宅 库存 去化周期
{city} 贝壳 二手房 挂牌量
```

### Credit and Policy Queries

```text
5年期 LPR 最新
{city} 房贷利率 最新 首套 二套
{city} 首付比例 最新
{city} 公积金 政策 最新
{city} 限购 限贷 政策 最新
{city} 收储 商品房 政策
```

### Population and Economy Queries

```text
{city} 常住人口 统计公报 最新
{city} 人口流入 流出 最新
{city} 居民可支配收入 最新
{city} 城镇调查失业率 最新
{city} GDP 增速 统计公报 最新
{city} 统计年鉴 常住人口 收入
```

### District-Level Queries

```text
{city} {district} 二手房 成交价 最新
{city} {district} 二手房 挂牌量
{city} {district} 新房 库存
{city} {district} 房价 成交量
{city} {district} 地铁 学区 产业 人口
```

Search query templates are only retrieval aids. The final forecast must still rely on source quality, freshness, and data consistency checks.

## Data Freshness Standards

| Data Type | Preferred Freshness | If Older Than |
|---|---|---|
| Price MoM / YoY | latest 1-2 months | mark stale if > 3 months |
| Transaction volume | latest week or latest month | mark stale if > 2 months |
| Listing volume | latest week or latest month | mark stale if > 2 months |
| Inventory / months of supply | latest quarter or month | mark stale if > 6 months |
| LPR / mortgage rate | latest available period | mark stale if not latest period |
| Local housing policy | latest 3-6 months | mark stale if policy may have changed |
| Population data | latest annual data | mark stale if older than 2 years |
| GDP / income / employment | latest quarter or annual data | mark stale if older than 1 year |
| Land auction data | latest quarter or month | mark stale if > 6 months |

## Conflict Handling Rules

- Official data has priority for macro and city-level indicators.
- Platform data may be more timely for listings and second-hand sentiment, but must be labeled as platform sample data.
- Asking prices cannot replace transaction prices.
- New-home filing prices cannot replace real transaction prices.
- If data sources conflict, explain methodology differences.
- If conflict cannot be resolved, lower confidence.
- Do not average incompatible indicators mechanically.

## Data Gaps

If the following data cannot be found:

- Transaction volume: short-term forecast confidence max Medium.
- Inventory / listings: supply-demand judgment confidence max Medium.
- Rental yield / price-to-income ratio: investment recommendation must be conservative.
- Population data: medium-long-term forecast confidence max Medium.
- Latest policy: policy impact judgment max Medium.
- Only C/D level data: overall confidence max Low-Medium or Low.

## Use Disclaimer

仅供交流学习娱乐，不提供投资建议，所有解释权归作者所有。
