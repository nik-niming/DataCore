# 基础数据

## 调用说明
- 通过api.query函数调用，第一个参数view需填入对应的接口名，如：`view="jz.instrumentInfo"` 
- 输入参数指的是filter参数里面的内容，通过'&'符号拼接，如：`filter="inst_type=&status=1&symbol="` 
- 输出参数指的是fields里面的内容，通过','隔开

样例代码：获取上市股票列表
```python
df, msg = api.query(
                view="jz.instrumentInfo", 
                fields="status,list_date, fullname_en, market", 
                filter="inst_type=1&status=1&symbol=", 
                data_format='pandas')
```

## 目前支持的接口及其含义

| 接口               | view                  | 分类       |
| ------------------ | --------------------- | ---------- |
| 证券基础信息表     | jz.instrumentInfo     | 基础信息   |
| 交易日历表         | jz.secTradeCal        | 基础信息   |
| 分配除权信息表     | lb.secDividend        | 股票       |
| 复权因子表         | lb.secAdjFactor       | 股票       |
| 停复牌信息表       | lb.secSusp            | 股票       |
| 行业分类表         | lb.secIndustry        | 股票       |
| 日行情估值表       | lb.secDailyIndicator  | 股票       |
| 资产负债表         | lb.balanceSheet       | 股票       |
| 利润表             | lb.income             | 股票       |
| 现金流量表         | lb.cashFlow           | 股票       |
| 业绩快报           | lb.profitExpress      | 股票       |
| 限售股解禁表       | lb.secRestricted      | 股票       |
| 指数基本信息表     | lb.indexInfo          | 指数       |
| 指数成份股表       | lb.indexCons          | 指数       |
| 公募基金净值表     | lb.mfNav              | 基金       |
| 公募基金分红表     | lb.mfDividend         | 基金       |
| 公募基金股票组合表 | lb.mfPortfolio        | 基金       |
| 公募基金债券组合表 | lb.mfBondPortfolio    | 基金       |

接口还在进一步的丰富过程中。
