---
title: VQR Data Catalogue

language_tabs: # must be one of https://git.io/vQNgJ
  - sql


toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

search: true
---

# Introduction

Welcome to the **Data Catalogue**! The document gives you descriptions on database we are using, all available data feeds we are collecting, and all available api that we are tracking.

Database is [InfluxDB](https://docs.influxdata.com/influxdb/v1.8/),whihc is a time-series database. Few terminologies to explain, tags in the influxdb is the unqie index and it is very useful to sort tickers via taging. Measurement is another word for table in the influxdb. Time is the defalut column in the table, which means the time that data wrote into database. Currently, we have two influxbd servers, one is primary server and another one is backup server.

Host Server: 
`Host-1 (Primary): 99-79-47-186 &&&& Host-2 (Backup): 15-223-68-239`

<aside class="notice">
Need credentials to log in.
</aside>

# Data Catalogue

The summary for all available data feeds. 

<aside class="warning"> <code> Case Sensitive </code> applys in table names </aside>

## Table Summary 

TableName | Frequency | DataType | CurrentStatus
--------- | --------- | ---------| -----------|
[bigone_orderbook](#bigone-orderbook) | 30 seconds | Orderbook Data | Running
[bigone_trades](#bigone-trade)  | RealTime | Trades Data | Running
[binance_borrow_rates_clean](#binance-borrow-rate) | 30 minutes | Borrow Rates | Running
[binance_funding_rates](#binance-funding-rate) | 8 hours | Trades Data | Running
[binance_future_stats_long_short_ratio](#binance-long-short-ratio) | Varies | Futures Data | Running
[binance_future_stats_long_short_ratio_account](#binance-long-short-ratio-account) | Varies | Futures Data | Running
[binance_future_stats_long_short_ratio_position](#binance-long-short-ratio-position) | Varies | Futures Data | Running
[binance_future_stats_open_interest](#binance-future-stats-open-interest) | Varies | Futures Data | Running
[binance_future_stats_taker_buy_sell_volume](#binance-taker-buy-sell-volume) | Varies | Futures Data | Running
[binance_liquidation_trades](#binance-liquidation-trade) | 1 hour | Liquidation Trades Data | Running
[binance_open_interest_clean](#binance-open-interest) | 1 minute | Open Interest | Running
[binance_orderbook_futures_clean](#binance-orderbook) | 30 seconds | Orderbook Data | Running
[binance_orderbook_spot_clean](#binance-orderbook) | 30 seconds | Orderbook Data | Running
[binance_trade_futures](#binance-trade) | 2 minutes | Trades Data | Running
[binance_trade_spot](#binance-trade) | 2 minutes | Trades Data | Running
[bitfinex_funding_orderbook](#bitfinex-funding-orderbook) | 30 seconds | Funding Orderbook | Running
[bitfinex_funding_trade](#bitfinex-funding-trade) | 1 hour | Funding Trades | Running
[bitfinex_leaderboard](#bitfinex-leaderboard) | Varies | Leaderboard | Running
[bitmex_full_orderbook](#bitmex-full-orderbook) | RealTime | Orderbook | Running
[bitmex_funding](#bitmex-funding) | 8 hours | Funding | Running
[bitmex_funding_rates](#bitmex-funding-rate) | 8 hours | Funding | Running
[bitmex_instrument](#bitmex-instrument) | 1 minute | Market Summary | Running 
[bitmex_insurance](#bitmex-insurance) | None | None | Running
[bitmex_leaderboard_notional](#bitmex-leaderboard) | 1 hour | Leaderboard | Running
[bitmex_leaderboard_ROE](#bitmex-leaderboard) | 1 hour | Leaderboard | Running
[bitmex_liquidation](#bitmex-liquidation) | RealTime | Liquidation | Running
[bitmex_settlement](#bitmex-settlement) | 1 week | Settlement | NoLongerUpated
[bitmex_trade](#bitmex-trade) | RealTime | Trade Data | Running
[bybit_funding_rate](#bybit-funding-rate) | 8 hours | Funding Rates | Running 
[bybit_tickers](#bybit-tickers) | 1 minute | Ticker | Running
[bybit_trades](#bybit-trades) | 1 minute | Trade Data | Running
cftc_futures_report | 1 week | Commodity Futures Report | Running
cme_futures_index | 1 hour | CME BTC Futures | Running
coinbase_custody | 1 hour | Custody Data | Running
coinbase_orderbook | 30 seconds | Orderbook | Running
coinbase_trades | 1 minutes | Trades Data | Running
coinex_orderbook | 30 seconds | Orderbook | Running
coinex_trades | 1 minute | Trade Data | Running
coinflex_burn_fees | 1 hour | Burn Fees | Running
compound_borrow_rates | 1 minute | Borrow Rates | Running
cosmos_validator_ranking | 1 hour | Validator Ranking | Running
cosmos_validator_status | 1 hour | Validator Status | Running
deribit_fundingRate | 8 hours | Funding Rate | Running
deribit_optoinTicker | RealTime | Option Ticker | Running
deribit_orderbook | RealTime | Orderbok | Running
deribit_ticker | RealTime | Ticker | Running
deribit_trades | RealTime | Trade Data | Running
dydx_borrow_rates | 1 minute | Borrow Rates | Running
exchange_open_interest | 1 minute | Open Interest | Running
FTX_funding_rates | 8 hours | Funding Rates | Running
FTX_future_stats | 1 minute | Market Summary | Running
FTX_leaderboard | 1 hour | Leaderboard | Running
FTX_option_request | RealTime | Request Data | Running
FTX_orderbook | 30 seconds | Orderbook | Running
FTX_trades | RealTime | Trades | Running
FTX_trades_option | RealTime | Trades | Running
gateio_orderbook | 30 seconds | Orderbook | Running
gateio_trades_data | RealTime | Trades | Running
hashpool_coins | 1 hour | Summary | Running
hnscan_block_info | RealTime | BlockChain | Running
hnscan_chart_data | 1 day | Chart | Running
hnscan_chart_data_snapshot | 1 day | Chart | Running
hnscan_status | 1 hour | Summary | Running
hnscan_summary | 1 hour | Summary | Running
hnscan_transaction | RealTime | BlockChian | Running
huobidm_contract_delivery_price | 1 minute | Delivery Price | Running
huobidm_contract_market_overvoew | 1 minute | Market Overview | Running
huobidm_contract_price_limit | 1 minute | Price Limit | Running  
huobidm_contract_risk_info | 1 minute | Risk Info | Running
huobidm_index_price | 1 minute | Index Price | Running
huobidm_insurance_fund | 1 minute | Insurance Fund | Running
huobidm_open_interest | 1 minute | Open Interest | Running
huobidm_orderbook | 30 seconds | Orderbook | Running
huobidm_trades | RealTime | Trade | Running
mxc_trades | RealTime | Trade | Running
mxc_orderbook | 30 seconds | Orderbook | Running
namebase_domain | 8 hours | Domain Data | Running
namebase_orderbook |30 seconds | Orderbook | Running 
namebase_trade | RealTime | Trade | Running
nervos_block | 1 minute | BLockChain | Running
nervos_hashrate | 1 minute | Hash Rate | Running
okex_fundingRate | 8 hours | Funding Rate | Running
okex_future_stats_contractBasis | Varies | Futures Data | Running
okex_future_stats_FutureTakerBuySell | Varies | Futures Data | Running
okex_future_stats_longShortPositionRatio | Varies | Futures Data | Running
okex_future_stats_OpenInterestVolume | Varies | Futures Data | Running
okex_future_stats_SwapFundingRate | Varies | Futures Data | Running
okex_future_stats_topTraderAverageMarginUsed | Varies | Futures Data | Running
okex_future_stats_topTraderSentimentIndex | Varies | Futures Data | Running
okex_liquidation | RealTime | Liquidation | Running
okex_markPrice | RealTime | Mark Price | Running
okex_Orderbook | RealTime | Orderbook | Running
okex_priceRange | RealTime | Price Range | Running
okex_recentTrades | RealTime | Trade | Running
okex_spotTrades | RealTime | Trade | Running
okex_SwapOpenInterest | RealTime | Open Interest | Running
okex_ticker | RealTime | Ticker | Running
okex_ticker_swap | RealTime | Ticker | Running
okex_ticker_v1 | RealTime | Ticker | Running
poloniex_funding_orderbook | 1 minute | Orderbook | Running
poloniex_leaderboard | 1 hour | Leaderboard | Running
poloniex_orderbook | 1 minute | Orderbook | Running
poloniex_trades | 1 minute | Trade | Running
sp500_futures | 1 second | Trade | Running
tether_richlist | 1 hour | Leaderboard | Running
tezos_leaderboard | 1 hour | Leaderboard | Running
wazirx_tickers | 1 hour | Ticker | Running



# Binance 
[Binance](https://www.binance.com/en) is a cryptocurrency exchange that provides a platform for trading various cryptocurrencies. Biance provide a powerful [api](https://binance-docs.github.io/apidocs/spot/en/#change-log).



## Binance Borrow Rate 

```sql
-- fetch one ticker
select * from binance_borrow_rates_clean where symbol = 'ADA'
```

> response

```json
[
    {
        "time": "2020-04-16 20:39:55.416015",
        "borrowLimit": 5000000",
        "dailyInterestRate": 0.0016,
        "symbol": "ADA",
        "timestamp": "2020-04-16 20:39:55.416015",
        "vipLevel": 9
    }
]
```

### Description
[Binance borrow rate](https://www.binance.com/en/margin-fee) is part of margin data listed in the website. Binance borrow rate has a frequency of 30 minutes and data time range is from 2019-12-02 21:34:09 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
borrowLimit | float | 
dailyInterestRate | float |
timestamp | string | data timstamp
vipLevel | string |
symbol | string | symbol is tag

### Tag Vlaues 
symbol tags are ADA, ATOM, BAT, BCH, BNB, BTC, BUSD, DASH, EOS, ETC, ETH, IOST, IOTA, LINK, LTC, MATIC, NEO, ONT, QTUM, RVN, TRX, USDC, USDT, VET, XLM, XMR, XRP, XTZ, ZEC. 

### Data Sanity
No downtime.

### API Reference

`GET https://www.binance.com/gateway-api/v1/public/margin/vip/spec/list-all`

### API Query Parameters
No parameters.

### API Return Schema
No Information.



## Binance Funding Rate

> database request

```sql
select * from binance_funding_rates_clean 
```

> response:

```json
[
    {
        "symbol": "BTCUSDT",
        "fundingRate": "-0.03750000",
        "fundingTime": 1570608000000,
        "time": 1576566020000
    },
    {
        "symbol": "BTCUSDT",
        "fundingRate": "0.00010000",
        "fundingTime": 1570636800000,
        "time": 1576566020000
    }
]
```


### Description
[Binance funding rate](https://binance-docs.github.io/apidocs/futures/en/#get-funding-rate-history-market_data) has a frequency of 8 hours and data time range is from 2020-01-27 18:07:37 till now. Collectors are continously runing in two hosts. 

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
fundingRate | float | 
fundingTime | integer |
time | string | data timestamp
symbol | string | 

### Funding Rate Symbols 
No tags in the table. All available symbols are BTCUSDT ETHUSDT, BCHUSDT, XRPUSDT, EOSUSDT, LTCUSDT, TRXUSDT, ETCUSDT, LINKUSDT, XLMUSDT, ADAUSDT, XMRUSDT, DASHUSDT, ZECUSDT, XTZUSDT, BNBUSDT, ATOMUSDT, ONTUSDT, IOTAUSDT, BATUSDT, VETUSDT, NEOUSDT.

### Data Sanity
No downtime.

### API Endpoint
`GET https://fapi.binance.com/fapi/v1/fapi/v1/fundingRate`

### API Query Parameters
Name | Type | Mandatory | Description
---- | ---- | ---------- | -------- |
symbol | string | yes | 
startTime | long | no | Timestamp in ms to get funding rate from INCLUSIVE
endTime | long | no | Timestamp in ms to get funding rate from INCLUSIVE
limit | integer | no | Default 100  max 1000

1. If `startTime` and `endTime` are not sent, the most recent `limit` datas are returned.
2. If the number of data between `startTime` and `endTime` is larger than `limit`, return as `startTime` + `limit`.
3. In ascending order.

### API Return Schema
No information



## Binance Long Short Ratio

> database request

```sql
select * from binance_future_stats_long_short_ratio where symbol = 'BTCUSDT'
```

> response:

```json
[
    { 
         "time":"1583139600000",
         "symbol":"BTCUSDT",  // long/short account num ratio of all traders
          "long_short_ratio":0.1960,  //long account num ratio of all traders
          "long_account": "0.6622",   // short account num ratio of all traders
          "short_account":"0.3378", 
          "timestamp":"1583139600000"

     },

     {
         "time":"1583139900000"
         "symbol":"BTCUSDT",
          "long_short_ratio":"1.9559",
          "long_account": "0.6617", 
          "short_account":"0.3382",                  
          "timestamp":"1583139900000"

        },   

]
```


### Description
[Binance long short ratio](https://www.binance.com/en/futures/funding-history/4) is trading data in the Binance futures. Binance long short ratio data has a variety of frequency, which includes 5 minutes, 15 minutes, 30 minutes, 1 hour, 2 hour, 4 hour, 6 hour, 12 hour, and 1 day. Data time range is from 2019-12-10 00:00:00 till now. Collectors are continously runing in two hosts. 

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
frequency | string | tag values 
long_account | string | 
short_account | string | 
long_short_ratio | float | 
symbol | string | tag values 
timestamp | integer | data timestamp 

### Tag Vlaues 
**Frequency**:
5 minutes, 15 minutes, 30 minutes, 1 hour, 2 hour, 4 hour, 6 hour, 12 hour, and 1 day

**Symbol**:
ADAUSDT, ATOMUSDT, BATUSDT, BCHUSDT, BNBUSDT, BTCUSDT, DASHUSDT, EOSUSDT, ETCUSDT, ETHUSDT, IOSUSDT, IOATUSDT, LINKUSDT, LTCUSDT, NEOUSDT,ONTUSDT,QTUMUSDT, TRXUSDT, VETUSDT, XLMUSDT, XMRUSDT, XRPUSDT, XTZUSDT, ZECUSDT

### Data Sanity
No downtime.

### API Endpoint
`GET https://fapi.binance.com/futures/data/globalLongShortAccountRatio`

### API Query Parameters
Name | Type | Mandatory | Description
---- | ---- | ---------- | -------- |
symbol | string | yes | 
period | number | yes | "5m","15m","30m","1h","2h","4h","6h","12h","1d"
limit | long | no | Default 100  max 1000
startTime | integer | no | 
endTime | integer | no | 

1. If there is no limit of startime and endtime, it will return the value brfore the current time by default.
2. Only the data of the latest 30 days is available.

### API Return Schema
No information



## Binance Long Short Ratio Account

> database request

```sql
select * from binance_future_stats_long_short_ratio_account where symbol = 'BTCUSDT'
```

> response:

```json
[
    { 
         "time":"1583139600000",
         "symbol":"BTCUSDT",  // long/short account num ratio of all traders
         "long_short_ratio":0.1960,  //long account num ratio of all traders
         "long_account": "0.6622",   // short account num ratio of all traders
         "short_account":"0.3378", 
         "timestamp":"1583139600000"

     },

     {
         "time":"1583139900000"
         "symbol":"BTCUSDT",
         "long_short_ratio":"1.9559",
         "long_account": "0.6617", 
         "short_account":"0.3382",                  
         "timestamp":"1583139900000"

        },   

]
```


### Description
[Binance long short ratio account](https://www.binance.com/en/futures/funding-history/4) is trading data in the Binance futures. Binance long short ratio account data has a variety of frequency, which includes 5 minutes, 15 minutes, 30 minutes, 1 hour, 2 hour, 4 hour, 6 hour, 12 hour, and 1 day. Data time range is from 2019-12-10 00:00:00 till now. Collectors are continously runing in two hosts. 

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
frequency | string | tag values 
long_account | string | 
short_account | string | 
long_short_ratio | float | 
symbol | string | tag values 
timestamp | integer | data timestamp 

### Tag Vlaues 
**Frequency**:
5 minutes, 15 minutes, 30 minutes, 1 hour, 2 hour, 4 hour, 6 hour, 12 hour, and 1 day

**Symbol**:
ADAUSDT, ATOMUSDT, BATUSDT, BCHUSDT, BNBUSDT, BTCUSDT, DASHUSDT, EOSUSDT, ETCUSDT, ETHUSDT, IOSUSDT, IOATUSDT, LINKUSDT, LTCUSDT, NEOUSDT,ONTUSDT,QTUMUSDT, TRXUSDT, VETUSDT, XLMUSDT, XMRUSDT, XRPUSDT, XTZUSDT, ZECUSDT

### Data Sanity
No downtime.

### API Endpoint
`GET https://fapi.binance.com/futures/data/topLongShortAccountRatio`

### API Query Parameters
Name | Type | Mandatory | Description
---- | ---- | ---------- | -------- |
symbol | string | yes | 
period | number | yes | "5m","15m","30m","1h","2h","4h","6h","12h","1d"
limit | long | no | Default 100  max 1000
startTime | integer | no | 
endTime | integer | no | 

1. If there is no limit of startime and endtime, it will return the value brfore the current time by default.
2. Only the data of the latest 30 days is available.



## Binance Long Short Ratio Position

> database request

```sql
select * from binance_future_stats_long_short_ratio_position where symbol = 'BTCUSDT'
```

> response:

```json
[
    { 
         "time":"1583139600000",
         "symbol":"BTCUSDT",  // long/short account num ratio of all traders
         "long_short_ratio":0.1960,  //long account num ratio of all traders
         "long_account": "0.6622",   // short account num ratio of all traders
         "short_account":"0.3378", 
         "timestamp":"1583139600000"

     },

     {
         "time":"1583139900000"
         "symbol":"BTCUSDT",
         "long_short_ratio":"1.9559",
         "long_account": "0.6617", 
         "short_account":"0.3382",                  
         "timestamp":"1583139900000"

        },   

]
```


### Description
[Binance long short ratio position](https://www.binance.com/en/futures/funding-history/4) is trading data in the Binance futures. Binance long short ratio position data has a variety of frequency, which includes 5 minutes, 15 minutes, 30 minutes, 1 hour, 2 hour, 4 hour, 6 hour, 12 hour, and 1 day. Data time range is from 2019-12-10 00:00:00 till now. Collectors are continously runing in two hosts. 

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
frequency | string | tag values 
long_account | string | 
short_account | string | 
long_short_account | float | 
symbol | string | tag values 
timestamp | integer | data timestamp 

### Tag Vlaues 
**Frequency**:
5 minutes, 15 minutes, 30 minutes, 1 hour, 2 hour, 4 hour, 6 hour, 12 hour, and 1 day

**Symbol**:
ADAUSDT, ATOMUSDT, BATUSDT, BCHUSDT, BNBUSDT, BTCUSDT, DASHUSDT, EOSUSDT, ETCUSDT, ETHUSDT, IOSUSDT, IOATUSDT, LINKUSDT, LTCUSDT, NEOUSDT,ONTUSDT,QTUMUSDT, TRXUSDT, VETUSDT, XLMUSDT, XMRUSDT, XRPUSDT, XTZUSDT, ZECUSDT

### Data Sanity
No downtime.

### API Endpoint
`GET https://fapi.binance.com/futures/data/topLongShortPositionRatio`

### API Query Parameters
Name | Type | Mandatory | Description
---- | ---- | ---------- | -------- |
symbol | string | yes | 
period | number | yes | "5m","15m","30m","1h","2h","4h","6h","12h","1d"
limit | long | no | Default 100  max 1000
startTime | integer | no | 
endTime | integer | no | 

1. If there is no limit of startime and endtime, it will return the value brfore the current time by default.
2. Only the data of the latest 30 days is available.



## Binance Future Stats Open Interest
> database request

```sql
select * from binance_future_stats_open_interest where symbol = 'BTCUSDT'
```

> response:

```json
[
    { 
         "time":"1583127900000",
         "symbol":"BTCUSDT",
         "open_interets":"20403.63700000",  // total open inerest 
         "notional_value_open_interest": "150570784.07809979",   // total open interet value
         "timestamp":"1583127900000"

     },

     {
         "time":"1583128200000",
         "symbol":"BTCUSDT",
         "open_interest":"20401.36700000",
         "notional_value_open_interest":"149940752.14464448",
         "timestamp":"1583128200000"

        },   

]

```


### Description
[Binance futures stats open interest](https://www.binance.com/en/futures/funding-history/4) is trading data in the Binance futures. Binance futures stats open interets data has a variety of frequency, which includes 5 minutes, 15 minutes, 30 minutes, 1 hour, 2 hour, 4 hour, 6 hour, 12 hour, and 1 day. Data time range is from 2019-12-10 00:00:00 till now. Collectors are continously runing in two hosts. 

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
frequency | string | tag values 
notional_value_open_interest | float | 
open_interest | float | 
symbol | string | tag values 
timestamp | integer | data timestamp 

### Tag Vlaues 
**Frequency**:
5 minutes, 15 minutes, 30 minutes, 1 hour, 2 hour, 4 hour, 6 hour, 12 hour, and 1 day

**Symbol**:
ADAUSDT, ATOMUSDT, BATUSDT, BCHUSDT, BNBUSDT, BTCUSDT, DASHUSDT, EOSUSDT, ETCUSDT, ETHUSDT, IOSUSDT, IOATUSDT, LINKUSDT, LTCUSDT, NEOUSDT,ONTUSDT,QTUMUSDT, TRXUSDT, VETUSDT, XLMUSDT, XMRUSDT, XRPUSDT, XTZUSDT, ZECUSDT

### Data Sanity
No downtime.

### API Endpoint
`GET https://fapi.binance.com/futures/data/openInterestHist`

### API Query Parameters
Name | Type | Mandatory | Description
---- | ---- | ---------- | -------- |
symbol | string | yes | 
period | number | yes | "5m","15m","30m","1h","2h","4h","6h","12h","1d"
limit | long | no | Default 100  max 1000
startTime | integer | no | 
endTime | integer | no | 

1. If there is no limit of startime and endtime, it will return the value brfore the current time by default.
2. Only the data of the latest 30 days is available.



## Binance Taker Buy Sell Volume

> database request

```sql
select * from binance_future_stats_taker_buy_sell_volume where symbol = 'BTCUSDT'
```

> response:

```json
[
    { 
          "time":"1585614900000",
          "long_short_ratio":"1.5586",
          "long_volume": "387.3300", 
          "short_volume":"248.5030", 
          "timestamp":"1585614900000",
          "symbol": "BTCUSDT"

     },

     {
          "time":"1583139900000",
          "long_short_ratio":"1.3104",
          "long_volume": "343.9290", 
          "short_volume":"248.5030",                     
          "timestamp":"1583139900000",
          "symbol":"BTCUSDT"

        },   

]
```

### Description
[Binance taker buy sell volume](https://binance-docs.github.io/apidocs/futures/en/#taker-buy-sell-volume-market_data) is trading data in the Binance futures. Binance taker buy sell  ratio data has a variety of frequency, which includes 5 minutes, 15 minutes, 30 minutes, 1 hour, 2 hour, 4 hour, 6 hour, 12 hour, and 1 day. Data time range is from 2019-12-10 00:00:00 till now. Collectors are continously runing in two hosts. 

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
frequency | string | tag values 
long_volume | float | 
short_volume | float | 
long_short_ratio | float | 
symbol | string | tag values 
timestamp | integer | data timestamp 

### Tag Vlaues 
**Frequency**:
5 minutes, 15 minutes, 30 minutes, 1 hour, 2 hour, 4 hour, 6 hour, 12 hour, and 1 day

**Symbol**:
ADAUSDT, ATOMUSDT, BATUSDT, BCHUSDT, BNBUSDT, BTCUSDT, DASHUSDT, EOSUSDT, ETCUSDT, ETHUSDT, IOSUSDT, IOATUSDT, LINKUSDT, LTCUSDT, NEOUSDT,ONTUSDT,QTUMUSDT, TRXUSDT, VETUSDT, XLMUSDT, XMRUSDT, XRPUSDT, XTZUSDT, ZECUSDT

### Data Sanity
No downtime.

### API Endpoint
`GET https://fapi.binance.com/futures/data/topLongShortPositionRatio`

### API Query Parameters
Name | Type | Mandatory | Description
---- | ---- | ---------- | -------- |
symbol | string | yes | 
period | number | yes | "5m","15m","30m","1h","2h","4h","6h","12h","1d"
limit | long | no | Default 100  max 1000
startTime | integer | no | 
endTime | integer | no | 

1. If there is no limit of startime and endtime, it will return the value brfore the current time by default.
2. Only the data of the latest 30 days is available.



## Binance Liquidation Trade

```sql
-- fetch one ticker
select * from binance_liquidation_trades where symbol = 'BTCUSDT'
```

> response

```json
[

    {
          "symbol": "BTCUSDT",                // SYMBOL
          "price": "7918.33",                 // ORDER_PRICE
          "origQty": "0.014",                 // ORDER_AMOUNT
          "executedQty": "0.014",             // FILLED_AMOUNT
          "avragePrice": "7918.33",           // AVG_PRICE
          "status": "FILLED",                 // STATUS
          "timeInForce": "IOC",               // TIME_IN_FORCE
          "type": "LIMIT",
          "side": "SELL",                     // DIRECTION
          "time": 1568014460893 
    },
]
```

### Description
[Binance liquidation trade](https://binance-docs.github.io/apidocs/futures/en/#get-all-liquidation-orders) has a frequency of 1 hour and data time range is from 2020-02-16 16:48:09 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | data timestamp
averagePrice | float | 
executedQty | float |
origQty | float | 
price | float |
side | string | 
status | string |
timeInForce | string | 
symbol | string | tag values

### Tag Vlaues 
Symbol tags are ADAUSDT, ATOMUSDT, BATUSDT, BCHUSDT, BNBUSDT, BTCUSDT, DASHUSDT, EOSUSDT, ETCUSDT, ETHUSDT, IOSTUSDT, IOTAUSDT, LINKUSDT, LTCUSDT,  NEOUSDT, ONTUSDT, QTUMUSDT, TRXUSDT, VETUSDT, XLMUSDT, XMRUSDT, XRPUSDT, XTZUSDT, ZECUSDT. 

### Data Sanity
No downtime.

### API Reference

`GET https://fapi.binance.com/fapi/v1/allForceOrders`

### API Query Parameters
Name | Type | Mandatory | Description
---- | ---- | ---------- | -------- |
symbol | string | yes | 
limit | long | no | Default 100  max 1000
startTime | integer | no | 
endTime | integer | no | 

1. If the symbol is not sent, liquidation orders for all symbols will be returned.

### API Return Schema
See code comments.



## Binance Open Interest

```sql
-- fetch one ticker
select * from binance_open_interest_clean
```

> response

```json
[

   {
    "time": "1576866488447948032", 
    "openInterest": "10659.509", // Coin denominated OI
    "symbol": "BTCUSDT"
   }


]
```

### Description
[Binance open interest](https://binance-docs.github.io/apidocs/futures/en/#open-interest) has a frequency of 1 minute and data time range is from 2019-12-20 18:28:09 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | data timestamp
open_interest | float | 
symbol | string |

### Open Interest symbols 
Symbols are ADAUSDT, ATOMUSDT, BATUSDT, BCHUSDT, BNBUSDT, BTCUSDT, DASHUSDT, EOSUSDT, ETCUSDT, ETHUSDT, IOSTUSDT, IOTAUSDT, LINKUSDT, LTCUSDT,  NEOUSDT, ONTUSDT, QTUMUSDT, TRXUSDT, VETUSDT, XLMUSDT, XMRUSDT, XRPUSDT, XTZUSDT, ZECUSDT. 

### Data Sanity
No downtime.

### API Reference

`GET https://fapi.binance.com/fapi/v1/openInterest`

### API Query Parameters
Name | Type | Mandatory | Description
---- | ---- | ---------- | -------- |
symbol | string | yes | 


### API Return Schema
See code comments.



## Binance Orderbook

```sql
-- fetch futures 
select * from binance_orderbook_futures_clean where symbol = 'BTCUSDT'

-- fetch spot
select * from binance_orderbook_spot_clean where symbol = 'BTCUSDT'


```

> response

```json
[

 {
   "time": "2019-12-30T2019 8:29:05.271",
   "current_snapshot":1577737657121,
   "lastUpdateID": 2206697117,
   "price":7261.1,
   "qty": 4.784,
   "symbol": "BTCUSDT",
   "type": "ask"
   
 }

]
```

### Description
[Binance orderbook](https://binance-docs.github.io/apidocs/futures/en/#order-book) has a frequency of 30 seconds and data time range is from 2019-12-20 18:28:09 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
current_snapshot | integer | data timestamp
lastUpdateID | integer | 
price | float | 
qty | float |
type | string |
symbol | string | tag values

### Tag Vlaues 
**Futures Symbols**: ADAUSDT, ATOMUSDT, BATUSDT, BCHUSDT, BNBUSDT, BTCUSDT, DASHUSDT, EOSUSDT, ETCUSDT, ETHUSDT, IOSTUSDT, IOTAUSDT, LINKUSDT, LTCUSDT,  NEOUSDT, ONTUSDT, QTUMUSDT, TRXUSDT, VETUSDT, XLMUSDT, XMRUSDT, XRPUSDT, XTZUSDT, ZECUSDT. 

**Spot Symbols**: BCHBTC, BCHUSDT, BNBBTC, BNBETH, BNBUSDT, BTCUSDT, DGDBTC, DGDETH, ETHUSDT, KNCBTC, KNCETH, RENBNB, RENBTC, RENUSDT, SOLBNB, SOLBTC, SOLBUSD 

### Data Sanity
No downtime.

### API Reference

`GET https://fapi.binance.com/fapi/v1/depth`

### API Query Parameters
Name | Type | Mandatory | Description
---- | ---- | ---------- | -------- |
symbol | string | yes | 
limit | int | no | Default 100; max 1000. Valid limits:[5, 10, 20, 50, 100, 500, 1000]

### API Return Schema
See code comments.



## Binance Trade

```sql
-- fetch futures 
select * from binance_trade_futures where symbol = 'BTCUSDT'

-- fetch spot
select * from binance_trade_spot where symbol = 'BTCUSDT'
```

> response

```json
[

 {
   "time": "2019-12-30T2019 8:29:05.271",
   "id":0,
   "isBuyerMaker": true,
   "price":4261.48,
   "qty": 0.1,
   "quoteQty":426.148,
   "symbol": "BTCUSDT",
   "trade_timestamp": "1502942428322"
   
 }

]
```

### Description
[Binance trade](https://binance-docs.github.io/apidocs/futures/en/#recent-trades-list) has a frequency of 2 minutes and data time range is from 2019-12-20 18:28:09 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
trade_timestamp | integer | data timestamp
id | integer | 
price | float | 
qty | float |
quoteQty | float |
isBuyerMaker | string |
symbol | string | tag values

### Tag Vlaues 
**Futures Symbols**: ADAUSDT, ATOMUSDT, BATUSDT, BCHUSDT, BNBUSDT, BTCUSDT, DASHUSDT, EOSUSDT, ETCUSDT, ETHUSDT, IOSTUSDT, IOTAUSDT, LINKUSDT, LTCUSDT,  NEOUSDT, ONTUSDT, QTUMUSDT, TRXUSDT, VETUSDT, XLMUSDT, XMRUSDT, XRPUSDT, XTZUSDT, ZECUSDT. 

**Spot Symbols**: BCHBTC, BCHUSDT, BNBBTC, BNBETH, BNBUSDT, BTCUSDT, DGDBTC, DGDETH, ETHUSDT, KNCBTC, KNCETH, RENBNB, RENBTC, RENUSDT, SOLBNB, SOLBTC, SOLBUSD 

### Data Sanity
**Duplicates**:
There will be duplicates in the trades data since the api returns maximum of 1000 for each query in case of loss data. So deduplicating id field to make sure data is clean. 

**Others**
Trade data may have some gaps in the past but api can fetch all historical, so we will fill gap soon.

### API Reference

`GET https://fapi.binance.com/fapi/v1/trade`

### API Query Parameters
Name | Type | Mandatory | Description
---- | ---- | ---------- | -------- |
symbol | string | yes | 
limit | int | no | Default 100; max 1000. Valid limits:[5, 10, 20, 50, 100, 500, 1000]

### API Return Schema
See code comments.



# Bitfinex
[Bitfinex](https://www.bitfinex.com/) is a cryptocurrency exchange and check their [api](https://docs.bitfinex.com/docs). Ratelimit for Bitfinex is 30 req/min.

## Bitfinex Funding Orderbook
```sql
-- fetch funding orderbook  
select * from bitfinex_funding_orderbook where SYMBOL = 'fUSDT'
```

> response

```json
[

 {
   "time": "2019-12-30T2019 8:29:05.271",
   "AMOUNT":9568.95412246x,
   "COUNT": 1,
   "MTS": 1502942428322,
   "PERIOD":30,
   "RATE": 0.0002070,
   "symbol": "fUSDT",
   "TYPE":"bid"
   
 }

]
```

### Description
[Bitfinex funding orderbook](https://docs.bitfinex.com/reference#rest-public-book) has a frequency of 1 minute and data time range is from 2019-12-20 18:28:09 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
MTS | float | data timestamp
AMOUNT | float | 
COUNT | integer | 
RATE | float |
TYPE | string |
symbol | string | tag values

### Tag Vlaues 
**Symbols**: fUSD, fGBP, fEUR, fBTC, fLTC, fETH, fETC, fZEC, fXMR, fDSH, fJPY, fXRP, fIOT, fEOS, fSAN, fOMG, fNEO, fETP, fEDO, fBTG, fZRX, fXLM, fXTZ, fBSV, fBAB, fUST, fATO, fLEO, fALG, fFTT, fXAUT.
### Data Sanity
No downtime.

### API Reference

`GET https://api-pub.bitfinex.com/v2/book/{Symbol}/{Precision}`

### API Query Parameters
Name | Type | Mandatory | Description | Example
---- | ---- | ---------- | -------- | ----------
Symbol | string | yes | The symbol you want information about | tBTCUSD, tETHUSD, fUSD, fBTC
Precision | string | yes | Level of price aggregation | P0, P1, P2, P3, P4, R0

### API Return Schema
Fields	|Type	|Description
--------| ----| ----------|
PRICE	|float	|Price level (Trading only)
RATE	|float	|Rate level (Funding only)
PERIOD|	float	|Period level (Funding only)
COUNT	|int	|Number of orders at that price level
±AMOUNT|	float	|Total amount available at that price level.
ORDER_ID|	int	|Order ID


## Bitfinex Funding Trade

```sql
-- fetch funding orderbook  
select * from bitfinex_funding_trade where SYMBOL = 'fUSD'
```

> response

```json
[

 {
   "time": "2019-10-17T 22:31:23.271",
   "MTS":1469734163000,
   "AMOUNT": 50.845,
   "ID":8,
   "PERIOD": 2,
   "RATE":0.000218,
   "SYMBOL": "fUSD",
   
 }

]
```

### Description
[Bitfinex funding trade](https://docs.bitfinex.com/reference#rest-public-trades) has a frequency of 1 hour and data time range is from 2019-12-20 18:28:09 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
MTS | float | data timestamp
AMOUNT | float | 
PERIOD | integer | 
RATE | float |
symbol | string | tag values

### Tag Vlaues 
**Symbols**: fUSD, fGBP, fEUR, fBTC, fLTC, fETH, fETC, fZEC, fXMR, fDSH, fJPY, fXRP, fIOT, fEOS, fSAN, fOMG, fNEO, fETP, fEDO, fBTG, fZRX, fXLM, fXTZ, fBSV, fBAB, fUST, fATO, fLEO, fALG, fFTT, fXAUT.

### Data Sanity
No downtime.

### API Reference

`GET https://api-pub.bitfinex.com/v2/trades/{Symbol}/hist`

### API Query Parameters
Name | Type | Mandatory | Description
---- | ---- | ---------- | -------- |
symbol | string | yes | The symbol you want information about. (e.g. tBTCUSD, tETHUSD, fUSD, fBTC)
limit | int | yes | Number of records (Max: 10000)
start | string | yes | Millisecond start time
end | string | yes | Millisecond end time
sort | string | yes | If = 1 it sorts results returned with old > new

### API Return Schema
Fields	|Type	|Description
--------| ----| ----------|
ID	|int	|ID of the trade
MTS	|int	|millisecond time stamp
±AMOUNT	|float	|How much was bought (positive) or sold (negative).
PRICE	|float	|Price at which the trade was executed (trading tickers only)
RATE	|float	|Rate at which funding transaction occurred (funding tickers only)
PERIOD	|int	|Amount of time the funding transaction was for (funding tickers only)

## Bitfinex Leaderboard
```sql
-- fetch leaderboard by symbol and type
select * from bitfinex_leaderboard where symbol = `1w:tGlobal:USD` and type = "unrealized_profit_period_delta"
```

> response

```json
[

 {
   "time": "2020-04-17T 17:12:21.271",
   "amount":802210.01,
   "name": "ubris",
   "rank":1,
   "symbol": "1M:tGLOBAL:USD",
   "timestamp": "1585699200000"
   "stype": "unrealized_profit_period_delta",
   
   
 }

]
```

### Description
[Bitfinex leaderboard](https://leaderboard.bitfinex.com/) has a variety of frequencies, including 3 hours, 1 week, 1 month. And data time range is from 2020-04-01 00:00:00 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
timestamp | float | data timestamp
amount | float | 
rank | integer |
symbol | string | tag values 
type | string | tag values

### Tag Vlaues 
**Symbols (time:ticker)**: 3h:tGLOBAL:USD, 3h:tBTCUSD, 3h:tBTCF0:USTF0, 3h:tBTCUST, 3h:tBTCEUR, 3h:tLEOUSD, 3h:tETHUSD, 3h:tETHF0:USTF0, 3h:tETHUST, 3h:tEOSUSD, 3h:tLTCUSD, 3h:tETCUSD, 1w:tGLOBAL:USD, 1w:tGLOBAL:CHZ, 1M:tGLOBAL:USD

**type**: unrealized_profit_period_delta, unrealized_profit_inception, realized_profit, volume

### Data Sanity
No downtime.

### API Reference

`GET https://api-pub.bitfinex.com/v2/rankings/{key}:{time_frame:symbol}/hist?limit={num_return}`

### API Query Parameters
Key | Available Time Frames | Available Symbols 
---- | ------------------ | ------------------
"plu_diff" - (Unrealised Profit (Period Delta)) | "1w", "1M" | tGLOBAL:USD
"plu" - (Unrealised Profit (Inception)) |  "3h" - for specific pairs "1w", "1M" - for tGLOBAL:USD | Trading Pairs (e.g. tBTCUSD, tETHUSD tGLOBAL:USD
"plr" - (Realized Profit) | "1w", "1M" | tGLOBAL:USD
"vol" - (Volume) | "3h", "1w", "1M" | Trading Pairs (e.g. tBTCUSD, tETHUSD) tGLOBAL:USD

### API Return Schema
Fields	|Type	|Description
--------| ----| ----------|
MTS	|int	|millisecond timestamp
USERNAME	|string	|Username
RANKING	|int	|Place on leaderboard
VALUE	|float	|Value of volume, unrealized profit, or realized profit
TWITTER_HANDLE	|string	|Shows the user's Twitter handle (if available)



# Bitmex
[Bitmex](https://www.bitmex.com/) is a cryptocurrency exchange. [Bitmex api](https://www.bitmex.com/app/apiOverview) has a very low rate limit so use it properly. 

## Bitmex Full Orderbook 

```sql
-- fetch data
select * from bitmex_full_orderbook where symbol = 'XRPZ19'
```

> response

```json
[

 {
   "time": "2019-11-21 17:40:53.056972",
   "snapshot_time":"2019-11-21 17:40:53.188963"
   "id":34699996624,
   "price": 0.00003376,
   "size":100,
   "symbol": "XRPZ19",
   "side": "Sell",
   
   
 }

]
```

### Description
[Bitmex full orderbook](https://leaderboard.bitfinex.com/) has a variety of frequencies, including 3 hours, 1 week, 1 month. And data time range is from 2020-04-01 00:00:00 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
snapshot_time | float | data timestamp
id | integer | 
size | integer |
symbol | string | tag values 
price | float | tag values
side | string | "Buy/Sell"


### Tag Vlaues 
**Symbols (time:ticker)**: 3h:tGLOBAL:USD, 3h:tBTCUSD, 3h:tBTCF0:USTF0, 3h:tBTCUST, 3h:tBTCEUR, 3h:tLEOUSD, 3h:tETHUSD, 3h:tETHF0:USTF0, 3h:tETHUST, 3h:tEOSUSD, 3h:tLTCUSD, 3h:tETCUSD, 1w:tGLOBAL:USD, 1w:tGLOBAL:CHZ, 1M:tGLOBAL:USD

**type**: unrealized_profit_period_delta, unrealized_profit_inception, realized_profit, volume

### Data Sanity
No downtime.

### API Reference

`GET https://www.bitmex.com/api/v1/orderBook/L2?symbol={Symbol}&depth={Depth}`

### API Query Parameters
Key | Available Time Frames | Available Symbols 
---- | ------------------ | ------------------
"plu_diff" - (Unrealised Profit (Period Delta)) | "1w", "1M" | tGLOBAL:USD
"plu" - (Unrealised Profit (Inception)) |  "3h" - for specific pairs "1w", "1M" - for tGLOBAL:USD | Trading Pairs (e.g. tBTCUSD, tETHUSD tGLOBAL:USD
"plr" - (Realized Profit) | "1w", "1M" | tGLOBAL:USD
"vol" - (Volume) | "3h", "1w", "1M" | Trading Pairs (e.g. tBTCUSD, tETHUSD) tGLOBAL:USD

### API Return Schema
Fields	|Type	|Description
--------| ----| ----------|
MTS	|int	|millisecond timestamp
USERNAME	|string	|Username
RANKING	|int	|Place on leaderboard
VALUE	|float	|Value of volume, unrealized profit, or realized profit
TWITTER_HANDLE	|string	|Shows the user's Twitter handle (if available)


## Bitmex Funding 
```sql
-- fetch data
select * from bitmex_funding
```

> response

```json
[

 {
   "time": "2019-11-21 17:40:53.056972",
   "snapshot_time":"2019-11-21 17:40:53.188963"
   "id":34699996624,
   "price": 0.00003376,
   "size":100,
   "symbol": "XRPZ19",
   "side": "Sell",
   
   
 }

]
```

### Description
[Bitmex funding](https://leaderboard.bitfinex.com/) has a variety of frequencies, including 3 hours, 1 week, 1 month. And data time range is from 2020-04-01 00:00:00 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
snapshot_time | float | data timestamp
fundingInterval  |string |
fundingRate      |float |
fundingRateDaily |float |

### Tag Vlaues 
**Symbols (time:ticker)**: 3h:tGLOBAL:USD, 3h:tBTCUSD, 3h:tBTCF0:USTF0, 3h:tBTCUST, 3h:tBTCEUR, 3h:tLEOUSD, 3h:tETHUSD, 3h:tETHF0:USTF0, 3h:tETHUST, 3h:tEOSUSD, 3h:tLTCUSD, 3h:tETCUSD, 1w:tGLOBAL:USD, 1w:tGLOBAL:CHZ, 1M:tGLOBAL:USD

**type**: unrealized_profit_period_delta, unrealized_profit_inception, realized_profit, volume

### Data Sanity
No downtime.

### API Reference

`GET https://www.bitmex.com/api/v1/orderBook/L2?symbol={Symbol}&depth={Depth}`

### API Query Parameters
Key | Available Time Frames | Available Symbols 
---- | ------------------ | ------------------
"plu_diff" - (Unrealised Profit (Period Delta)) | "1w", "1M" | tGLOBAL:USD
"plu" - (Unrealised Profit (Inception)) |  "3h" - for specific pairs "1w", "1M" - for tGLOBAL:USD | Trading Pairs (e.g. tBTCUSD, tETHUSD tGLOBAL:USD
"plr" - (Realized Profit) | "1w", "1M" | tGLOBAL:USD
"vol" - (Volume) | "3h", "1w", "1M" | Trading Pairs (e.g. tBTCUSD, tETHUSD) tGLOBAL:USD

### API Return Schema
Fields	|Type	|Description
--------| ----| ----------|
MTS	|int	|millisecond timestamp
USERNAME	|string	|Username
RANKING	|int	|Place on leaderboard
VALUE	|float	|Value of volume, unrealized profit, or realized profit
TWITTER_HANDLE	|string	|Shows the user's Twitter handle (if available)

## Bitmex Funding Rate
```sql
-- fetch data
select * from bitmex_funding_rate
```

> response

```json
[

 {
   "time": "2019-11-21 17:40:53.056972",
   "snapshot_time":"2019-11-21 17:40:53.188963"
   "id":34699996624,
   "price": 0.00003376,
   "size":100,
   "symbol": "XRPZ19",
   "side": "Sell",
   
   
 }

]
```

### Description
[Bitmex funding rate](https://leaderboard.bitfinex.com/) has a variety of frequencies, including 3 hours, 1 week, 1 month. And data time range is from 2020-04-01 00:00:00 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
snapshot_time | float | data timestamp
fundingInterval       |string|
fundingRate           |float|
fundingRateDaily      |float|
indicativeFundingRate |float|
timestamp             |string|


### Tag Vlaues 
**Symbols (time:ticker)**: 3h:tGLOBAL:USD, 3h:tBTCUSD, 3h:tBTCF0:USTF0, 3h:tBTCUST, 3h:tBTCEUR, 3h:tLEOUSD, 3h:tETHUSD, 3h:tETHF0:USTF0, 3h:tETHUST, 3h:tEOSUSD, 3h:tLTCUSD, 3h:tETCUSD, 1w:tGLOBAL:USD, 1w:tGLOBAL:CHZ, 1M:tGLOBAL:USD

**type**: unrealized_profit_period_delta, unrealized_profit_inception, realized_profit, volume

### Data Sanity
No downtime.

### API Reference

`GET https://www.bitmex.com/api/v1/orderBook/L2?symbol={Symbol}&depth={Depth}`

### API Query Parameters
Key | Available Time Frames | Available Symbols 
---- | ------------------ | ------------------
"plu_diff" - (Unrealised Profit (Period Delta)) | "1w", "1M" | tGLOBAL:USD
"plu" - (Unrealised Profit (Inception)) |  "3h" - for specific pairs "1w", "1M" - for tGLOBAL:USD | Trading Pairs (e.g. tBTCUSD, tETHUSD tGLOBAL:USD
"plr" - (Realized Profit) | "1w", "1M" | tGLOBAL:USD
"vol" - (Volume) | "3h", "1w", "1M" | Trading Pairs (e.g. tBTCUSD, tETHUSD) tGLOBAL:USD

### API Return Schema
Fields	|Type	|Description
--------| ----| ----------|
MTS	|int	|millisecond timestamp
USERNAME	|string	|Username
RANKING	|int	|Place on leaderboard
VALUE	|float	|Value of volume, unrealized profit, or realized profit
TWITTER_HANDLE	|string	|Shows the user's Twitter handle (if available)


## Bitmex Instrument
```sql
-- fetch data
select * from bitmex_instrument
```

> response

```json
[

 {
   "time": "2019-11-21 17:40:53.056972",
   "snapshot_time":"2019-11-21 17:40:53.188963"
   "id":34699996624,
   "price": 0.00003376,
   "size":100,
   "symbol": "XRPZ19",
   "side": "Sell",
   
   
 }

]
```

### Description
[Bitmex full orderbook](https://leaderboard.bitfinex.com/) has a variety of frequencies, including 3 hours, 1 week, 1 month. And data time range is from 2020-04-01 00:00:00 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
snapshot_time | float | data timestamp
askPrice                       |float|
bidPrice                       |float|
calcInterval                   |string|
capped                         |boolean|
closingTimestamp               |string|
deleverage                     |boolean|
expiry                         |string|
fairBasis                      |float|
fairBasisRate                  |float|
fairMethod                     |string|
fairPrice                      |float|
foreignNotional24h             |float|
front                          |string|
fundingBaseSymbol              |string|
fundingInterval                |string|
fundingPremiumSymbol           |string|
fundingQuoteSymbol             |string|
fundingRate                    |float|
fundingTimestamp               |string|
hasLiquidity                   |boolean|
highPrice                      |float|
homeNotional24h                |float|
impactAskPrice                 |float|
impactBidPrice                 |float|
impactMidPrice                 |float|
indicativeFundingRate          |float|
indicativeSettlePrice          |float|
indicativeTaxRate              |float|
initMargin                     |float|
insuranceFee                   |float|
isInverse                      |boolean|
isQuanto                       |boolean|
lastChangePcnt                 |float|
lastPrice                      |float|
lastPriceProtected             |float|
lastTickDirection              |string|
limitDownPrice                 |float|
limitUpPrice                   |float|
listing                        |string|
lotSize                        |float|
lowPrice                       |float|
maintMargin                    |float|
makerFee                       |float|
markMethod                     |string|
markPrice                      |float|
maxOrderQty                    |float|
maxPrice                       |float|
midPrice                       |float|
multiplier                     |float|
openInterest                   |float|
openValue                      |float|
openingTimestamp               |string|
optionMultiplier               |float|
optionStrikePcnt               |float|
optionStrikePrice              |float|
optionStrikeRound              |float|
optionUnderlyingPrice          |float|
positionCurrency               |string|
prevClosePrice                 |float|
prevPrice24h                   |float|
prevTotalTurnover              |float|
prevTotalVolume                |float|
publishInterval                |string|
publishTime                    |string|
quoteCurrency                  |string|
quoteToSettleMultiplier        |float|
reference                      |string|
referenceSymbol                |string|
relistInterval                 |string|
riskLimit                      |float|
riskStep                       |float|
rootSymbol                     |string|
sessionInterval                |string|
settlCurrency                  |string|
settle                         |string|
settledPrice                   |float|
settlementFee                  |float|
state                          |string|
takerFee                       |float|
taxed                          |boolean|
tickSize                       |float|
timestamp                      |string|
totalTurnover                  |float|
totalVolume                    |float|
turnover                       |float|
turnover24h                    |float|
typ                            |string|
underlying                     |string|
underlyingSymbol               |string|
underlyingToPositionMultiplier |float|
underlyingToSettleMultiplier   |float|
volume                         |float|
volume24h                      |float|
vwap                           |float|



### Tag Vlaues 
**Symbols (time:ticker)**: 3h:tGLOBAL:USD, 3h:tBTCUSD, 3h:tBTCF0:USTF0, 3h:tBTCUST, 3h:tBTCEUR, 3h:tLEOUSD, 3h:tETHUSD, 3h:tETHF0:USTF0, 3h:tETHUST, 3h:tEOSUSD, 3h:tLTCUSD, 3h:tETCUSD, 1w:tGLOBAL:USD, 1w:tGLOBAL:CHZ, 1M:tGLOBAL:USD

**type**: unrealized_profit_period_delta, unrealized_profit_inception, realized_profit, volume

### Data Sanity
No downtime.

### API Reference

`GET https://www.bitmex.com/api/v1/orderBook/L2?symbol={Symbol}&depth={Depth}`

### API Query Parameters
Key | Available Time Frames | Available Symbols 
---- | ------------------ | ------------------
"plu_diff" - (Unrealised Profit (Period Delta)) | "1w", "1M" | tGLOBAL:USD
"plu" - (Unrealised Profit (Inception)) |  "3h" - for specific pairs "1w", "1M" - for tGLOBAL:USD | Trading Pairs (e.g. tBTCUSD, tETHUSD tGLOBAL:USD
"plr" - (Realized Profit) | "1w", "1M" | tGLOBAL:USD
"vol" - (Volume) | "3h", "1w", "1M" | Trading Pairs (e.g. tBTCUSD, tETHUSD) tGLOBAL:USD

### API Return Schema
Fields	|Type	|Description
--------| ----| ----------|
MTS	|int	|millisecond timestamp
USERNAME	|string	|Username
RANKING	|int	|Place on leaderboard
VALUE	|float	|Value of volume, unrealized profit, or realized profit
TWITTER_HANDLE	|string	|Shows the user's Twitter handle (if available)



## Bitmex Insurance
```sql
-- fetch leaderboard by symbol and type
select * from bitmex_full_orderbook where symbol = 'XRPZ19'
```

> response

```json
[

 {
   "time": "2019-11-21 17:40:53.056972",
   "snapshot_time":"2019-11-21 17:40:53.188963"
   "id":34699996624,
   "price": 0.00003376,
   "size":100,
   "symbol": "XRPZ19",
   "side": "Sell",
   
   
 }

]
```

### Description
[Bitmex full orderbook](https://leaderboard.bitfinex.com/) has a variety of frequencies, including 3 hours, 1 week, 1 month. And data time range is from 2020-04-01 00:00:00 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
snapshot_time | float | data timestamp
currency      |string|
walletBalance |integer|



### Tag Vlaues 
**Symbols (time:ticker)**: 3h:tGLOBAL:USD, 3h:tBTCUSD, 3h:tBTCF0:USTF0, 3h:tBTCUST, 3h:tBTCEUR, 3h:tLEOUSD, 3h:tETHUSD, 3h:tETHF0:USTF0, 3h:tETHUST, 3h:tEOSUSD, 3h:tLTCUSD, 3h:tETCUSD, 1w:tGLOBAL:USD, 1w:tGLOBAL:CHZ, 1M:tGLOBAL:USD

**type**: unrealized_profit_period_delta, unrealized_profit_inception, realized_profit, volume

### Data Sanity
No downtime.

### API Reference

`GET https://www.bitmex.com/api/v1/orderBook/L2?symbol={Symbol}&depth={Depth}`

### API Query Parameters
Key | Available Time Frames | Available Symbols 
---- | ------------------ | ------------------
"plu_diff" - (Unrealised Profit (Period Delta)) | "1w", "1M" | tGLOBAL:USD
"plu" - (Unrealised Profit (Inception)) |  "3h" - for specific pairs "1w", "1M" - for tGLOBAL:USD | Trading Pairs (e.g. tBTCUSD, tETHUSD tGLOBAL:USD
"plr" - (Realized Profit) | "1w", "1M" | tGLOBAL:USD
"vol" - (Volume) | "3h", "1w", "1M" | Trading Pairs (e.g. tBTCUSD, tETHUSD) tGLOBAL:USD

### API Return Schema
Fields	|Type	|Description
--------| ----| ----------|
MTS	|int	|millisecond timestamp
USERNAME	|string	|Username
RANKING	|int	|Place on leaderboard
VALUE	|float	|Value of volume, unrealized profit, or realized profit
TWITTER_HANDLE	|string	|Shows the user's Twitter handle (if available)

## Bitmex Leaderboard

```sql
-- fetch leaderboard by symbol and type
select * from bitmex_full_orderbook where symbol = 'XRPZ19'
```

> response

```json
[

 {
   "time": "2019-11-21 17:40:53.056972",
   "snapshot_time":"2019-11-21 17:40:53.188963"
   "id":34699996624,
   "price": 0.00003376,
   "size":100,
   "symbol": "XRPZ19",
   "side": "Sell",
   
   
 }

]
```

### Description
[Bitmex full orderbook](https://leaderboard.bitfinex.com/) has a variety of frequencies, including 3 hours, 1 week, 1 month. And data time range is from 2020-04-01 00:00:00 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
CREATION_TIME| string | data timestamp
Rank          |integer |
isRealName    |boolean |
name          |string |
profit        |float |


### Tag Vlaues 
**Symbols (time:ticker)**: 3h:tGLOBAL:USD, 3h:tBTCUSD, 3h:tBTCF0:USTF0, 3h:tBTCUST, 3h:tBTCEUR, 3h:tLEOUSD, 3h:tETHUSD, 3h:tETHF0:USTF0, 3h:tETHUST, 3h:tEOSUSD, 3h:tLTCUSD, 3h:tETCUSD, 1w:tGLOBAL:USD, 1w:tGLOBAL:CHZ, 1M:tGLOBAL:USD

**type**: unrealized_profit_period_delta, unrealized_profit_inception, realized_profit, volume

### Data Sanity
No downtime.

### API Reference

`GET https://www.bitmex.com/api/v1/orderBook/L2?symbol={Symbol}&depth={Depth}`

### API Query Parameters
Key | Available Time Frames | Available Symbols 
---- | ------------------ | ------------------
"plu_diff" - (Unrealised Profit (Period Delta)) | "1w", "1M" | tGLOBAL:USD
"plu" - (Unrealised Profit (Inception)) |  "3h" - for specific pairs "1w", "1M" - for tGLOBAL:USD | Trading Pairs (e.g. tBTCUSD, tETHUSD tGLOBAL:USD
"plr" - (Realized Profit) | "1w", "1M" | tGLOBAL:USD
"vol" - (Volume) | "3h", "1w", "1M" | Trading Pairs (e.g. tBTCUSD, tETHUSD) tGLOBAL:USD

### API Return Schema
Fields	|Type	|Description
--------| ----| ----------|
MTS	|int	|millisecond timestamp
USERNAME	|string	|Username
RANKING	|int	|Place on leaderboard
VALUE	|float	|Value of volume, unrealized profit, or realized profit
TWITTER_HANDLE	|string	|Shows the user's Twitter handle (if available)


## Bitmex Liquidation
```sql
-- fetch leaderboard by symbol and type
select * from bitmex_full_orderbook where symbol = 'XRPZ19'
```

> response

```json
[

 {
   "time": "2019-11-21 17:40:53.056972",
   "snapshot_time":"2019-11-21 17:40:53.188963"
   "id":34699996624,
   "price": 0.00003376,
   "size":100,
   "symbol": "XRPZ19",
   "side": "Sell",
   
   
 }

]
```

### Description
[Bitmex full orderbook](https://leaderboard.bitfinex.com/) has a variety of frequencies, including 3 hours, 1 week, 1 month. And data time range is from 2020-04-01 00:00:00 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
snapshot_time | float | data timestamp
leavesQty |float|
orderID   |string|
price     |float|


### Tag Vlaues 
**Symbols (time:ticker)**: 3h:tGLOBAL:USD, 3h:tBTCUSD, 3h:tBTCF0:USTF0, 3h:tBTCUST, 3h:tBTCEUR, 3h:tLEOUSD, 3h:tETHUSD, 3h:tETHF0:USTF0, 3h:tETHUST, 3h:tEOSUSD, 3h:tLTCUSD, 3h:tETCUSD, 1w:tGLOBAL:USD, 1w:tGLOBAL:CHZ, 1M:tGLOBAL:USD

**type**: unrealized_profit_period_delta, unrealized_profit_inception, realized_profit, volume

### Data Sanity
No downtime.

### API Reference

`GET https://www.bitmex.com/api/v1/orderBook/L2?symbol={Symbol}&depth={Depth}`

### API Query Parameters
Key | Available Time Frames | Available Symbols 
---- | ------------------ | ------------------
"plu_diff" - (Unrealised Profit (Period Delta)) | "1w", "1M" | tGLOBAL:USD
"plu" - (Unrealised Profit (Inception)) |  "3h" - for specific pairs "1w", "1M" - for tGLOBAL:USD | Trading Pairs (e.g. tBTCUSD, tETHUSD tGLOBAL:USD
"plr" - (Realized Profit) | "1w", "1M" | tGLOBAL:USD
"vol" - (Volume) | "3h", "1w", "1M" | Trading Pairs (e.g. tBTCUSD, tETHUSD) tGLOBAL:USD

### API Return Schema
Fields	|Type	|Description
--------| ----| ----------|
MTS	|int	|millisecond timestamp
USERNAME	|string	|Username
RANKING	|int	|Place on leaderboard
VALUE	|float	|Value of volume, unrealized profit, or realized profit
TWITTER_HANDLE	|string	|Shows the user's Twitter handle (if available)


## Bitmex Settlement
```sql
-- fetch data
select * from bitmex_settlement
```

> response

```json
[

 {
   "time": "2019-11-21 17:40:53.056972",
   "snapshot_time":"2019-11-21 17:40:53.188963"
   "id":34699996624,
   "price": 0.00003376,
   "size":100,
   "symbol": "XRPZ19",
   "side": "Sell",
   
   
 }

]
```

### Description
[Bitmex settlement](https://leaderboard.bitfinex.com/) has a variety of frequencies, including 3 hours, 1 week, 1 month. And data time range is from 2020-04-01 00:00:00 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
snapshot_time | float | data timestamp
bankrupt              |float|
optionStrikePrice     |float|
optionUnderlyingPrice |float|
settledPrice          |float|
settlementType        |string|
taxBase               |float|
taxRate               |float|



### Tag Vlaues 
**Symbols (time:ticker)**: 3h:tGLOBAL:USD, 3h:tBTCUSD, 3h:tBTCF0:USTF0, 3h:tBTCUST, 3h:tBTCEUR, 3h:tLEOUSD, 3h:tETHUSD, 3h:tETHF0:USTF0, 3h:tETHUST, 3h:tEOSUSD, 3h:tLTCUSD, 3h:tETCUSD, 1w:tGLOBAL:USD, 1w:tGLOBAL:CHZ, 1M:tGLOBAL:USD

**type**: unrealized_profit_period_delta, unrealized_profit_inception, realized_profit, volume

### Data Sanity
No downtime.

### API Reference

`GET https://www.bitmex.com/api/v1/orderBook/L2?symbol={Symbol}&depth={Depth}`

### API Query Parameters
Key | Available Time Frames | Available Symbols 
---- | ------------------ | ------------------
"plu_diff" - (Unrealised Profit (Period Delta)) | "1w", "1M" | tGLOBAL:USD
"plu" - (Unrealised Profit (Inception)) |  "3h" - for specific pairs "1w", "1M" - for tGLOBAL:USD | Trading Pairs (e.g. tBTCUSD, tETHUSD tGLOBAL:USD
"plr" - (Realized Profit) | "1w", "1M" | tGLOBAL:USD
"vol" - (Volume) | "3h", "1w", "1M" | Trading Pairs (e.g. tBTCUSD, tETHUSD) tGLOBAL:USD

### API Return Schema
Fields	|Type	|Description
--------| ----| ----------|
MTS	|int	|millisecond timestamp
USERNAME	|string	|Username
RANKING	|int	|Place on leaderboard
VALUE	|float	|Value of volume, unrealized profit, or realized profit
TWITTER_HANDLE	|string	|Shows the user's Twitter handle (if available)

## Bitmex Trade
 
```sql
-- fetch data
select * from bitmex_trade
```

> response

```json
[

 {
   "time": "2019-11-21 17:40:53.056972",
   "snapshot_time":"2019-11-21 17:40:53.188963"
   "id":34699996624,
   "price": 0.00003376,
   "size":100,
   "symbol": "XRPZ19",
   "side": "Sell",
   
   
 }

]
```

### Description
[Bitmex trade](https://leaderboard.bitfinex.com/) has a variety of frequencies, including 3 hours, 1 week, 1 month. And data time range is from 2020-04-01 00:00:00 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
snapshot_time | float | data timestamp
foreignNotional    |float|
grossValue         |float|
homeNotional       |float|
official_timestamp |float|
price              |float|
size               |float|
tickDirection      |string|
trdMatchID         |string|



### Tag Vlaues 
**Symbols (time:ticker)**: 3h:tGLOBAL:USD, 3h:tBTCUSD, 3h:tBTCF0:USTF0, 3h:tBTCUST, 3h:tBTCEUR, 3h:tLEOUSD, 3h:tETHUSD, 3h:tETHF0:USTF0, 3h:tETHUST, 3h:tEOSUSD, 3h:tLTCUSD, 3h:tETCUSD, 1w:tGLOBAL:USD, 1w:tGLOBAL:CHZ, 1M:tGLOBAL:USD

**type**: unrealized_profit_period_delta, unrealized_profit_inception, realized_profit, volume

### Data Sanity
No downtime.

### API Reference

`GET https://www.bitmex.com/api/v1/orderBook/L2?symbol={Symbol}&depth={Depth}`

### API Query Parameters
Key | Available Time Frames | Available Symbols 
---- | ------------------ | ------------------
"plu_diff" - (Unrealised Profit (Period Delta)) | "1w", "1M" | tGLOBAL:USD
"plu" - (Unrealised Profit (Inception)) |  "3h" - for specific pairs "1w", "1M" - for tGLOBAL:USD | Trading Pairs (e.g. tBTCUSD, tETHUSD tGLOBAL:USD
"plr" - (Realized Profit) | "1w", "1M" | tGLOBAL:USD
"vol" - (Volume) | "3h", "1w", "1M" | Trading Pairs (e.g. tBTCUSD, tETHUSD) tGLOBAL:USD

### API Return Schema
Fields	|Type	|Description
--------| ----| ----------|
MTS	|int	|millisecond timestamp
USERNAME	|string	|Username
RANKING	|int	|Place on leaderboard
VALUE	|float	|Value of volume, unrealized profit, or realized profit
TWITTER_HANDLE	|string	|Shows the user's Twitter handle (if available)
 
 
 
# BigOne
[BigOne exchange](https://big.one/) is a cryptocurrency exchange with [api documents](https://open.big.one/docs/api.html) 

## BigOne Trade

```sql
-- fetch trades
select * from bigone_trades where symbol = "HNS-USDT"

```

> response

```json
[

 {
   "time": "2020-03-11T16:47:38Z",
   "amount":1.0,
   "price":4.5,
   "type": "BID",
   "symbol": "HNS-USDT",
   "timestamp": "2020-03-11T16:47:38Z",
   "tradeID": 123456,
 }

]
```

### Description
Bigone trade has a frequency of 30 seconds and data time range is from 2020-03-11 16:47:38 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
timestamp | string | data timestamp
tradeID | integer | 
price | float | 
amount | float |
type | string |
symbol | string | tag values

### Tag Vlaues 
**Symbol**: HNS-BTC, HNS-USDT

### Data Sanity
No downtime.

### API Reference

`GET https://big.one/api/v3/asset_pairs/{symbol}/trades`

### API Query Parameters
Attribute Name | Type | Require | Description | Excample|
-------------- | ---- | ---------- | -------- |---------|
asset_pair_name | string | True | name of asset pair | BTC-USDT

### API Return Schema
Attribute Name | Type | Description | Excample
-------------- | ---- | ---------- | -------- |
id | number | id of trade| 
asset_pair_name | string | name of asset pair | BTC-USDT
price | string | deal price |
amount | string | amount 
taker_side | string | order side | one of "ASK/BID"
created_at | string | order created datetime|


## BigOne Orderbook

```sql
-- fetch trades
select * from bigone_orderbook where symbol = 'HNS-USDT'

```

> response

```json
[

 {
   "time": "2020-03-13T16:47:38Z",
   "order_count":1.0,
   "price":0.00039,
   "size": 798.3,
   "symbol": "HNS-USDT",
   "snapshot": "2020-03-11T16:47:38Z",
   "type": "ask",
 }

]
```

### Description
Bigone orderbook has a frequency of 30 seconds and data time range is from 2020-03-13 16:47:38 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
snapshot | string | data timestamp
price | float | 
size | float |
type | string | ask/bid
symbol | string | tag values

### Tag Vlaues 
**Symbol**: HNS-BTC, HNS-USDT

### Data Sanity
No downtime.

### API Reference

`GET https://big.one/api/v3/asset_pairs/{asset_pair_name}/depth`

### API Query Parameters
Attribute Name | Type | Require | Description | Excample
-------------- | ---- | ---------- | -------- | ------- |
asset_pair_name | string | True |name of asset pair | BTC-USDT

### API Return Schema
### PriceLevel
Attribute Name | Type | Description | Excample
-------------- | ---- | ---------- | -------- |
price | string |  price | 5098.37
quantity | string | quantity | 0.0679 
order_count | string | order count in this level | 10

### OrderCount
Attribute Name | Type | Description | Excample
-------------- | ---- | ---------- | -------- |
id | number | id of trade| 
asset_pair_name | string | name of asset pair | BTC-USDT
bids | PriceLevel array | bids |
asks | PriceaLevel array | asks 



# Bybit
[Bybit](https://www.bybit.com/) is a cryptocurrency exchange that only has BTCUSD, ETHUSD, EOSUSD, XRPUSD, and BTCUSDT with inverse perpetual and USDT perpetual [api](https://bybit-exchange.github.io/docs/inverse/#t-introduction).

## Bybit Trades 

```sql
-- fetch trades
select * from bybit_trades where symbol = 'BTCUSDT'

```

> response

```json
[

 {
   "time": "2020-01-23T16:47:38Z",
   "current_snapshot":"2020-01-23T16:47:38Z",
   "id":32665362,
   "price": "8324",
   "qty": 3000,
   "symbol": "BTCUSD",
   "side": "Sell",
 }

]
```

### Description
Bybit trades has a frequency of 60 seconds and data time range is from 2020-01-23 17:28:19 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
current_snapshot | string | data timestamp
id | integer | 
price | string | 
qty | integer |
side | string | Sell/Buy
symbol | string | tag values

### Tag Vlaues 
**Symbol**: BTCUSD, BTCUSDT, EOSUSD, ETHUSD, XRPUSD

### Data Sanity
Inverse perpetual collection starts from 2020-01-23 and USDT perpetual starts from 2020-04-17. 

### API Reference
**Inverse Perpetual**
`GET https://api.bybit.com/v2/public/trading-records`

**USDT Perpetual** 
`GET https://api.bybit.com/v2/public/public/linear/recent-trading-records`

### API Query Parameters
parameter | Type | Required | Description | 
-------------- | ---- | ---------- | -------- | 
symbol | string | True | Contract Type |
from | int | False | From ID. Default: return latest data
limit | int | False |  default 500; max 1000

### API Return Schema
No information.


## Bybit Funding Rate

```sql
-- fetch funding rate
select * from bybit_funding_rate

```

> response

```json
[

 {
   "time": "2020-01-23T16:47:38Z",
   "id":32665362,
   "value": "0.0001",
   "symbol": "BTCUSD"
 }

]
```

### Description
Bybit funding rate has a frequency of 8 hours and data time range is from 2018-11-24 16:00:00 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
id | integer | 
value | string | 
symbol | string |

### Tickers Symbol
Symbols are BTCUSD, ETHUSD, EOSUSD, XRPUSD

### Data Sanity
No downtime.

### API Reference

`GET https://api2.bybit.com/funding-rate/list`

### API Query Parameters
No information.

### API Return Schema
No information.


## Bybit Tickers

```sql
-- fetch tickers
select * from bybit_tickers

```

> response

```json
[

        {
            "time": "2020-01-23T16:47:38Z",
            "symbol": "BTCUSD",
            "bid_price": "7230",
            "ask_price": "7230.5",
            "last_price": "7230.00",
            "last_tick_direction": "ZeroMinusTick",
            "prev_price_24h": "7163.00",
            "price_24h_pcnt": "0.009353",
            "high_price_24h": "7267.50",
            "low_price_24h": "7067.00",
            "prev_price_1h": "7209.50",
            "price_1h_pcnt": "0.002843",
            "mark_price": "7230.31",
            "index_price": "7230.14",
            "open_interest": 117860186,
            "open_value": "16157.26",
            "total_turnover": "3412874.21",
            "turnover_24h": "10864.63",
            "total_volume": 28291403954,
            "volume_24h": 78053288,
            "funding_rate": "0.0001",
            "predicted_funding_rate": "0.0001",
            "next_funding_time": "2019-12-28T00:00:00Z",
            "countdown_hour": 2
          }
]
```

### Description
Bybit funding rate has a frequency of 1 minute and data time range is from 2019-12-11 20:03:05 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
ask_price              |string|
bid_price              |string|
countdown_hour         |integer|
current_snapshot       |string|
funding_rate           |string|
high_price_24h         |string|
index_price            |string|
last_price             |string|
last_tick_direction    |string|
low_price_24h          |string|
mark_price             |string|
next_funding_time      |string|
open_interest          |integer|
open_value             |string|
predicted_funding_rate |string|
prev_price_1h          |string|
prev_price_24h         |string|
price_1h_pcnt          |string|
price_24h_pcnt         |string|
symbol                 |string|
total_turnover         |string|
total_volume           |integer|
turnover_24h           |string|
volume_24h             |integer|
symbol | string |

###  Tickers Symbol
Symbols are BTCUSD, ETHUSD, EOSUSD, XRPUSD

### Data Sanity
No downtime.

### API Reference

`GET https://api2.bybit.com/v2/public/tickers`

### API Query Parameters
parameter | Type | Required | Description | 
-------------- | ---- | ---------- | -------- | 
symbol | string | True | Contract Type |


### API Return Schema
No information.



# Coinbase

# Coinex

# Compound

# Deribit

# Dydx

# FTX

# Gateio

# HuobiDM

# MXC

# OKEX

# Poloniex

# Wazirx

# Coinflex

# Cosmos

# HNScan

# Namebase

# Nervos

# Tether

# Tezos


# Aggregate Exchange Open Interest


# Futures Market Data
## CME Group 

## Commodity Futures Trading Commission

## Investing.com


