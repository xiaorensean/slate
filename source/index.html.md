---
title: VQR Data Catalogue

language_tabs: # must be one of https://git.io/vQNgJ
  - sql
  
toc_footers:
  - <a href='https://github.com/virdevop/Market-Data-Host-1'>Check out scripts on Github</a>


search: true
---

# Introduction

Welcome to the **Data Catalogue**! The document gives you descriptions on database we are using, all available data feeds we are collecting, and all available api that we are tracking.

Database is [InfluxDB](https://docs.influxdata.com/influxdb/v1.8/),whihc is a time-series database. Few terminologies to explain, tags in the influxdb is the unqie index and it is very useful to sort tickers via taging. Measurement is another word for table in the influxdb. Time is the defalut column in the table, which means the time that data wrote into database. Currently, we have two influxbd servers, one is primary server and another one is backup server.

**Host Server 1**: 
`Host-1 (Primary): 35-183-117-153`
**Host Server 2**:
`Host-2 (Backup): 15-223-68-239`

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
[bigone_trades](#bigone-trade)  | 30 seconds | Trades Data | Running
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
[cftc_futures_report](#commodity-futures-trading-commission) | 1 week | Commodity Futures Report | Running
[cme_futures_index](#cme-group) | 1 hour | CME BTC Futures | Running
[coinbase_custody](#coinbase-custody) | 1 hour | Custody Data | Running
[coinbase_orderbook](#coinbase-orderbook) | 30 seconds | Orderbook | Running
[coinbase_trades](#coinbase-trades) | 5 minutes | Trades Data | Running
[coinex_orderbook](#coinex-orderbook) | 30 seconds | Orderbook | Running
[coinex_trades](#coinex-trades) | 30 seconds | Trade Data | Running
[coinflex_burn_fees](#coinflex-burn-fees) | 1 day | Burn Fees | NoLongerUpdating
[compound_borrow_rates](#compound-borrow-rates) | 1 minute | Borrow Rates | Running
[cosmos_validator_ranking](#cosmos-validator-ranking) | 1 hour | Validator Ranking | Running
[cosmos_validator_status](#cosmos-validator-status) | 1 hour | Validator Status | Running
[deribit_fundingRate](#deribit-funding-rate) | 8 hours | Funding Rate | Running
[deribit_optoinTicker](#deribit-ticker) | RealTime | Option Ticker | Running
[deribit_orderbook](#deribit-orderbook) | 30 seconds | Orderbok | Running
[deribit_ticker](#deribit-ticker) | RealTime | Ticker | Running
[deribit_trades](#deribit-trades) | RealTime | Trade Data | Running
[dydx_borrow_rates](#dydx-borrow-rates) | 1 minute | Borrow Rates | Running
[exchange_open_interest](#open-interest) | 1 minute | Open Interest | Running
[FTX_funding_rates](#ftx-funding-rate) | 1 minute | Funding Rates | Running
[FTX_future_stats](#ftx-futures-statistics) | 1 minute | Market Summary | Running
[FTX_leaderboard](#ftx-leaderboard) | 1 hour | Leaderboard | Running
[FTX_option_request](#ftx-option-request) | 1 second | Request Data | Running
[FTX_orderbook](#ftx-orderbook) | 30 seconds | Orderbook | Running
[FTX_trades](#ftx-trades) | 10 minutes | Trades | Running
[FTX_trades_option](#ftx-trades-option) | 1 second | Trades | Running
[gateio_orderbook](#gateio-orderbook) | 30 seconds | Orderbook | Running
[gateio_trades_data](#gateio-trades) | RealTime | Trades | Running
[hashpool_coins](#hashpool-coins) | 1 hour | Summary | Running
[hnscan_block_info](#hnscan-blockchain) | 1 hour | BlockChain | Running
[hnscan_chart_data](#hnscan-chart) | 1 day | Chart | Running
[hnscan_chart_data_snapshot](#hnscan-chart) | 1 day | Chart | Running
[hnscan_status](#hnscan-status) | 9 minutes | Summary | Running
[hnscan_summary](#hnscan-summary) | 9 minutes | Summary | Running
[hnscan_transaction](#hnscan-blockchain) | 1 hour | BlockChian | Running
[huobidm_contract_delivery_price](#huobidm-contract-delivery-price) | 1 minute | Delivery Price | Running
[huobidm_contract_market_overview](#huobidm-contract-market-overview) | 1 minute | Market Overview | Running
[huobidm_contract_price_limit](#huobidm-contract-price-limit) | 1 minute | Price Limit | Running  
[huobidm_contract_risk_info](#huobidm-contract-risk-info) | 1 minute | Risk Info | Running
[huobidm_index_price](#huobidm-index-price) | 1 minute | Index Price | Running
[huobidm_insurance_fund](#huobidm-insurance-fund) | 1 minute | Insurance Fund | Running
[huobidm_open_interest](#huobidm-open-interest) | 1 minute | Open Interest | Running
[huobidm_orderbook](#huobidm-orderbook) | 30 seconds | Orderbook | Running
[huobidm_trades](#huobidm-trade) | RealTime | Trade | Running
[mxc_trades](#mxc-trades) | 5 minutes | Trade | Running
[mxc_orderbook](#mxc-orderbook) | 30 seconds | Orderbook | Running
[namebase_domain](#namebase-domain) | 9 hours | Domain Data | Running
[namebase_orderbook](#namebase-orderbook) |30 seconds | Orderbook | Running 
[namebase_trade](#namebase-trade) | RealTime | Trade | Running
[nervos_block](#nervos-block) | 10 minutes | BLockChain | Running
[nervos_hashrate](#nervos-hashrate) | 10 minutes | Hash Rate | Running
[okex_fundingRate](#okex-funding-rate) | 8 hours | Funding Rate | Running
[okex_future_stats_contractBasis](#okex-future-stats-contract-basis) | Varies | Futures Data | Running
[okex_future_stats_FutureTakerBuySell](#okex-future-stats-taker-buy-sell) | Varies | Futures Data | Running
[okex_future_stats_longShortPositionRatio](#okex-future-stats-long-short-ratio-position) | Varies | Futures Data | Running
[okex_future_stats_OpenInterestVolume](#okex-future-stats-open-interest-volume) | Varies | Futures Data | Running
[okex_future_stats_SwapFundingRate](#okex-future-stats-swap-funding-rate) | Varies | Futures Data | Running
[okex_future_stats_topTraderAverageMarginUsed](#okex-future-stats-top-trader-average-margin-used) | Varies | Futures Data | Running
[okex_future_stats_topTraderSentimentIndex](#okex-future-stats-top-trader-sentimental-index) | Varies | Futures Data | Running
[okex_liquidation](#okex-liquidation) | RealTime | Liquidation | Running
[okex_markPrice](#okex-mark-price) | RealTime | Mark Price | Running
[okex_Orderbook](#okex-orderbook) | RealTime | Orderbook | Running
[okex_priceRange](#okex-price-range) | RealTime | Price Range | Running
[okex_recentTrades](#okex-trades) | RealTime | Trade | Running
[okex_spotTrades](#okex-trades) | RealTime | Trade | Running
[okex_SwapOpenInterest](#okex-open-interest-swap) | RealTime | Open Interest | Running
[okex_ticker](#okex-ticker) | RealTime | Ticker | Running
[okex_ticker_swap](#okex-ticker-swap) | RealTime | Ticker | Running
[okex_ticker_v1](#okex-ticker-v1) | RealTime | Ticker | Running
[poloniex_funding_orderbook](#poloniex-funding-orderbook) | 1 minute | Orderbook | Running
[poloniex_leaderboard](#poloniex-leaderboard) | 1 hour | Leaderboard | Running
[poloniex_orderbook](#poloniex-orderbook) | 30 seconds | Orderbook | Running
[poloniex_trades](#poloniex-trades) | 10 minutes | Trade | Running
[sp500_futures](#investing) | 1 second | Trade | Running
[tether_richlist](#tether-richlist) | 1 hour | Leaderboard | Running
[tezos_leaderboard](#tezos-leaderboard) | 1 hour | Leaderboard | Running
[wazirx_tickers](#wazirx-tickers) | 1 hour | Ticker | Running



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

### API Response Schema
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

### API Response Schema
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

### API Response Schema
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

### API Response Schema
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


### API Response Schema
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

### API Response Schema
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

### API Response Schema
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

### API Response Schema
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

### API Response Schema
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

### API Response Schema
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
[Bitmex full orderbook](https://www.bitmex.com/api/explorer/#!/OrderBook/OrderBook_getL2) has a frequency of 30 seconds for XBT symbols and has a frequency of 1 minute for other symbols. And data time range is from 2020-04-01 00:00:00 till now. Collectors are continously runing in two hosts.

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
**Symbols**: ADAH20, ADAM20, ADAZ19, BCHH20, BCHM20, BCHZ19, EOSH20, EOSM20, EOSZ19, ETHH20, ETHM20, ETHUSD, ETHZ19. LTCH20, LTCM20, LTCZ19, TRXH20, TRXM20, TRXZ19, XBT7D_D95, XBT7D_U105, XBTH20, XBTM20, XBTU20, XBTUSD, XBTZ19, XRPH20, XRPM20, XRPUSD, XRPZ19

### Data Sanity
No downtime.

### API Reference
`GET https://www.bitmex.com/api/v1/orderBook/L2?symbol={Symbol}&depth={Depth}`

### API Query Parameters
Name | Type | Description
-----| ----- | --------- |
symbol | string | Instrument symbol. Send a series (e.g. XBT) to get data for the nearest contract in that series.
depth | double | Orderbook depth per side. Send 0 for full depth.

### API Response Schema
No Information.


## Bitmex Funding 
```sql
-- fetch data
select * from bitmex_funding where symbol = 'ETHXBT'
``` 

> response

```json
[

 {
   "time": "2016-11-04 04:00:00",
   "fundingInterval":"2000-01-01T08:00:00.000Z"
   "fundingRate":-0.0016619999999999998,
   "fundingRateDaily": -0.004985999999999999,
   "symbol": "ETHXBT"
 }

]
```

### Description
[Bitmex funding](https://www.bitmex.com/app/wsAPI) is connected through webscoket so it is real-time update. And data time range is from 2016-11-04 04:00:00 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
fundingInterval  |string |
fundingRate      |float |
fundingRateDaily |float |
symbol | string |

### Tag Vlaues 
**Symbols (time:ticker)**: XBTUSD, ETHUSD, ETHXBT, FCTXBT, LSKXBT, LTCXBT, XRPUSD

### Data Sanity
No downtime.

### API Reference

`Websocket wss://www.bitmex.com/realtime?subscribe=funding`

### API Query Parameters
Name | Type | Description
-----| ----- | --------- |
symbol | string | Instrument symbol. Send a series (e.g. XBT) to get data for the nearest contract in that series.


### API Response Schema
No information.


## Bitmex Funding Rate
```sql
-- fetch data
select * from bitmex_funding_rates where symbol = 'XBTUSD'
```

> response

```json
[

 {
   "time": "2016-11-04 04:00:00",
   "fundingInterval":"2000-01-01T08:00:00.000Z"
   "fundingRate":0.00016619999999999998,
   "fundingRateDaily": 0.0004985999999999999,
   "indicativeFundingRate": None,
   "timestamp": None,
   "symbol": "XBTUSD"
 }

]
```

### Description
[Bitmex funding rate](https://www.bitmex.com/app/fundingHistory) has a frequency of 8 hours. And data time range is from 2016-05-04 12:00:00 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
fundingInterval       |string|
fundingRate           |float|
fundingRateDaily      |float|
indicativeFundingRate |float|
timestamp             |string|
symbol | string | tag values


### Tag Vlaues 
**Symbols (time:ticker)**: XBTUSD, ETHUSD, ETHXBT, FCTXBT, LSKXBT, LTCXBT, XRPUSD


### Data Sanity
No downtime.

### API Reference
`GET https://www.bitmex.com/api/v1/funding?reverse=True`

### API Query Parameters
Name | Type | Description
-----| ----- | --------- |
symbol | string | Instrument symbol. Send a series (e.g. XBT) to get data for the nearest contract in that series.

### API Response Schema
No information.


## Bitmex Instrument
```sql
-- fetch data
select * from bitmex_instrument where symbol = 'XRPUSD'
```

> response

```json
[

 {
    "symbol": "XRPUSD",
    "rootSymbol": "string",
    "state": "string",
    "typ": "string",
    "listing": "2020-04-18T20:55:42.795Z",
    "front": "2020-04-18T20:55:42.795Z",
    "expiry": "2020-04-18T20:55:42.795Z",
    "settle": "2020-04-18T20:55:42.795Z",
    "relistInterval": "2020-04-18T20:55:42.795Z",
    "inverseLeg": "string",
    "sellLeg": "string",
    "buyLeg": "string",
    "optionStrikePcnt": 0,
    "optionStrikeRound": 0,
    "optionStrikePrice": 0,
    "optionMultiplier": 0,
    "positionCurrency": "string",
    "underlying": "string",
    "quoteCurrency": "string",
    "underlyingSymbol": "string",
    "reference": "string",
    "referenceSymbol": "string",
    "calcInterval": "2020-04-18T20:55:42.795Z",
    "publishInterval": "2020-04-18T20:55:42.795Z",
    "publishTime": "2020-04-18T20:55:42.795Z",
    "maxOrderQty": 0,
    "maxPrice": 0,
    "lotSize": 0,
    "tickSize": 0,
    "multiplier": 0,
    "settlCurrency": "string",
    "underlyingToPositionMultiplier": 0,
    "underlyingToSettleMultiplier": 0,
    "quoteToSettleMultiplier": 0,
    "isQuanto": true,
    "isInverse": true,
    "initMargin": 0,
    "maintMargin": 0,
    "riskLimit": 0,
    "riskStep": 0,
    "limit": 0,
    "capped": true,
    "taxed": true,
    "deleverage": true,
    "makerFee": 0,
    "takerFee": 0,
    "settlementFee": 0,
    "insuranceFee": 0,
    "fundingBaseSymbol": "string",
    "fundingQuoteSymbol": "string",
    "fundingPremiumSymbol": "string",
    "fundingTimestamp": "2020-04-18T20:55:42.795Z",
    "fundingInterval": "2020-04-18T20:55:42.795Z",
    "fundingRate": 0,
    "indicativeFundingRate": 0,
    "rebalanceTimestamp": "2020-04-18T20:55:42.795Z",
    "rebalanceInterval": "2020-04-18T20:55:42.795Z",
    "openingTimestamp": "2020-04-18T20:55:42.795Z",
    "closingTimestamp": "2020-04-18T20:55:42.795Z",
    "sessionInterval": "2020-04-18T20:55:42.795Z",
    "prevClosePrice": 0,
    "limitDownPrice": 0,
    "limitUpPrice": 0,
    "bankruptLimitDownPrice": 0,
    "bankruptLimitUpPrice": 0,
    "prevTotalVolume": 0,
    "totalVolume": 0,
    "volume": 0,
    "volume24h": 0,
    "prevTotalTurnover": 0,
    "totalTurnover": 0,
    "turnover": 0,
    "turnover24h": 0,
    "homeNotional24h": 0,
    "foreignNotional24h": 0,
    "prevPrice24h": 0,
    "vwap": 0,
    "highPrice": 0,
    "lowPrice": 0,
    "lastPrice": 0,
    "lastPriceProtected": 0,
    "lastTickDirection": "string",
    "lastChangePcnt": 0,
    "bidPrice": 0,
    "midPrice": 0,
    "askPrice": 0,
    "impactBidPrice": 0,
    "impactMidPrice": 0,
    "impactAskPrice": 0,
    "hasLiquidity": true,
    "openInterest": 0,
    "openValue": 0,
    "fairMethod": "string",
    "fairBasisRate": 0,
    "fairBasis": 0,
    "fairPrice": 0,
    "markMethod": "string",
    "markPrice": 0,
    "indicativeTaxRate": 0,
    "indicativeSettlePrice": 0,
    "optionUnderlyingPrice": 0,
    "settledPrice": 0,
    "timestamp": "2020-04-18T20:55:42.796Z"
]
```

### Description
[Bitmex instrument](https://www.bitmex.com/app/wsAPI) is connected through webscoket so it is real-time update. And data time range is from 2019-07-11 04:00:00 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
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
symbol | string | tag values



### Tag Vlaues 
**Symbols {time:ticker} (Symbols are subject to change)**: .BADAXBT, .BADAXBT30M, .BADAXBT_NEXT, .BBCHXBT, .BBCHXBT30M, .BBCHXBT_NEXT, .BEOSXBT, .BEOSXBT30M, .BEOSXBT_NEXT, .BETH, .BETH30M, .BETHXBT, .BETHXBT_NEXT, .BETHXBT30M, .BETHXBT_NEXT, .BLTCXBT, .BLTCXBT30M, .BLTCXBT_NEXT, .BTRXXBT, .BTRXXBT30M, .BTRXXBT_NEXT, .BVOL, .BVOL24H, .BVOL7D,  .BXBT, .BXBT_NEXT,.BXBT30M, .BXBTJPY, .BXBTJPY30M, .BXRP, .BXRPXBT, .BXRP30M, .BXRP_NEXT, .BXRPXBT30M, .BXRPXBT_NEXT, .ETHBON, .ETHBON2H, .ETHBON8H,  .ETHUSDPI,  .ETHUSDPI2H, .ETHUSDPI8H, .EVOL7D, .TRXXBT, .TRXXBT30M, .USDBON, .USDBON2H, .USDBON8H, .XBT, .XBTBON, .XBTBON2H, .XBTBON8H, .XBTJPY, .XBTJPY30M, .XBTUSDPI, .XBTUSDPI2H, .XBTUSDPI8H, .XRPBON, .XRPBON2H, .XRPBON8H, .XRPUSDPI, .XRPUSDPI2H, .XRPUSDPI8H, ADAH20, ADAM20, ADAU19, ADAZ19, BCHH20, BCHM20, BCHZ19, BCHU20, EOSH20, EOSM20, EOSU19, EOSZ19, ETHH20, ETHM20, ETHUSD, ETHU19, ETHZ19. LTCH20, LTCM20, LTCZ19, LTCU19, TRXH20, TRXM20, TRXZ19,TRXU19,  XBT7D_D95, XBT7D_U105, XBTH20, XBTM20, XBTU20, XBTUSD, XBTZ19, XBTU19, XRPH20, XRPM20, XRPU19, XRPUSD, XRPZ19

### Data Sanity
No downtime.

### API Reference
`Websocket wss://www.bitmex.com/realtime?subscribe=instrument`

### API Query Parameters
Name | Type | Description
-----| ----- | --------- |
symbol | string | Instrument symbol. Send a series (e.g. XBT) to get data for the nearest contract in that series.

### API Response Schema
No information.


## Bitmex Insurance
```sql
-- fetch data
select * from bitmex_insurance
```

> response

```json
[

  {
    "currency": "string",
    "timestamp": "2020-04-18T20:55:42.859Z",
    "walletBalance": 0
  }

]
```

### Description
[Bitmex insurance](https://www.bitmex.com/app/wsAPI) is connected through webscoket so it is real-time update. And data time range is from 2019-07-11 12:00:00 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
currency      |string|
walletBalance |integer|

### Currency 
The ticker is only XBt. 

### Data Sanity
No downtime.

### API Reference
`Websocket wss://www.bitmex.com/realtime?subscribe=insurance`

### API Query Parameters
No information.

### API Response Schema
No information.


## Bitmex Leaderboard
```sql
-- fetch leaderboard ROE
select * from bitmex_leaderboard_ROE 

-- fetch leaderbard notional
select * from bitmex_leaderboard_notional
```

> response

```json
[

 {
   "time": "2019-08-28 21:26:51.23435482",
   "CREATION_TIME":"2019-08-28 21:26:51.333642",
   "Rank":1,
   "isRealName": "false",
   "name":"Splash-Alpine-Twister",
   "profit": 5003.43,
   
 }

]
```

### Description
[Bitmex leaderboard](https://leaderboard.bitfinex.com/) has a variety of frequencies, including 3 hours, 1 week, 1 month. And data time range is from 2020-04-01 00:00:00 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
CREATION_TIME| string | data timestamp
Rank          |integer |
isRealName    |boolean |
name          |string |
profit        |float |


### Data Sanity
No downtime.

### API Reference

`GET https://www.bitmex.com/api/v1/leaderboard?method={ROE/notional}`

### API Query Parameters
Name | Type | Description
-----| ----- | --------- |
method | string | ROE or notional
 
### API Response Schema
No information.


## Bitmex Liquidation
```sql
-- fetch data
select * from bitmex_liquidation where symbol = 'EOSU19'
```

> response

```json
[

 {
   "time": "2019-07-11 16:10:58.158",
   "leaveQty":50,
   "orderID":"319014a0-4495-b06c-da64-7dee1f49945e",
   "price":0.0004061,
   "symbol": "EOSU19",
   "side": "Buy",
   ""
   
 }

]
```

### Description
[Bitmex liquidation](https://www.bitmex.com/app/wsAPI) is connected through webscoket so it is real-time update. And data time range is from 2019-07-11 16:10:58.158 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
leavesQty |float|
orderID   |string|
price     |float|
symbol | string | tag values
side | string | tag values


### Tag Vlaues 
**Symbols**: ADAH20, ADAM20, ADAU19, ADAZ19, BCHH20, BCHM20, BCHZ19, BCHU20, EOSH20, EOSM20, EOSU19, EOSZ19, ETHH20, ETHM20, ETHUSD, ETHU19, ETHZ19. LTCH20, LTCM20, LTCZ19, LTCU19, TRXH20, TRXM20, TRXZ19,TRXU19, XBT7D_D95, XBT7D_U105, XBTH20, XBTM20, XBTU20, XBTUSD, XBTZ19, XBTU19, XRPH20, XRPM20, XRPU19, XRPUSD, XRPZ19

**side**: Buy, sell

### Data Sanity
No downtime.

### API Reference

`Websocket wss://www.bitmex.com/realtime?subscribe=liquidation`

### API Query Parameters
Name | Type | Description
-----| ----- | --------- |
symbol | string | Instrument symbol. Send a series (e.g. XBT) to get data for the nearest contract in that series.

### API Response Schema
No information.


## Bitmex Settlement
```sql
-- fetch data
select * from bitmex_settlement where symbol = 'XBTK15'
```

> response

```json
[

 {
   "time": "2015-05-29 12:00:00",
   "bankrupt": None,
   "optionStrikePrice": None,
   "optionUnderlyingPrice": None,
   "settledPrice":236.04,
   "settlementType": "Settlement"
   "symbol": "XBTKZ15",
   "taxBase": None,
   "taxRate": None
 }

]
```

### Description
[Bitmex settlement](https://www.bitmex.com/app/wsAPI) is connected through webscoket so it is real-time update And data time range is from 2015-05-29 12:00:00 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
bankrupt              |float|
optionStrikePrice     |float|
optionUnderlyingPrice |float|
settledPrice          |float|
settlementType        |string|
taxBase               |float|
taxRate               |float|
symbol | string | tag values


### Tag Vlaues 
**Symbols (Symbols are subject to change)**: A50G16, A50H16, A50J16, A50K16, A50M16, A50N16, A50Q16, ADAF18, ADAH18, ADAH19, ADAH20, ADAM18, ADAM19, ADAU18, ADAM18, ADAZ18, ADAZ19, BCHF18, BCHH18, BCHH19, BCHH20, BCHM18, BCHM19, BCHU18, BCHU19, BCHX17, BCHZ17, BCHZ18, BCHZ19, BFXQ16, BFXU16, BFXV16, BVOL24H, BVOL7D, B_BLOCKSZ17, B_SEGWITZ17, COIN_BH17, DAOETH, DASH7D, DASHH18, DASHJ17, DASHM17, DASHU17, DASHZ17, EOSH19, EOSH20, EOSM18, EOSM19, EOSN17, EOSU18, EOSU19, EOSZ18, EOSZ19, ETC24H, ETC7D, ETH7D, ETHH18, ETHH19, ETHH20, ETHJ17, ETHM17, ETHM18, ETHM19, ETHU17, ETHI19, ETHXBT, ETHZ17, ETHZ18, ETHZ19, FxT7D, FXCM17, FCTXBT, GNOM17, LSKXBT, LTC7D, LTCH18, LTCH19, LTCH20, LTCM18, LTCM19, LTCM20, LTCU18, LTCU19, LTCU20, LTCXBT, LTCZ18, LTCZ19, LTCZ20, NEOG18, NEOH18, QTUMU17, REP7D, SNTN17, TRXH19, TRXH20, TRXM19, TRXU18, TRXU19, TRXZ18, TRXZ19, WINZ16, XBCM17, XBCH17, XBCZ16, XBJ24H, XBJ7D, XBJM17, XBJU17, XBJZ16, XBJZ17, XBT24H, XBT48H, XBT7D, XBT7D_D90, XBT7D_D95, XBT7D_U105, XBT7D_U110, XBTH16, XBTH17, XBTH18, XBTH19, XBTH20, XBTK15, XBTM15, XBTM16, XBTM17, XBTM18, XBTM19, XBTN15, XBTQ15, XBTU15, XBTU16, XBTU17, XBTU18, XBTU19, XBTUSD, XBTV15, XBTZ15, XBTZ16, XBTZ17, XBTZ18, XBTZ19, XBU24H, XBU7D, XBUK15, XBUM15, XBUN15, XBUQ15, XBUU15, XBUZ15, XLMF18, XLMH18, XLT7D, XMR7D, XMRH18, XMRM17, XMRU17, XMRZ17, XRP7D, XRPH18, XRPH19, XRPH20, XRPM17, XRPM18, XRPM19, XRPU17, XRPU18, XRPU19, XRPZ17, XRPZ18, XRPZ19, XTZZ17, ZECH17, ZECH18, ZECM17, ZECU17, ZECZ16, ZECZ17  

### Data Sanity
No downtime.

### API Reference

`Websocket wss://www.bitmex.com/realtime?subscribe=settlement`

### API Query Parameters
Name | Type | Description
-----| ----- | --------- |
symbol | string | Instrument symbol. Send a series (e.g. XBT) to get data for the nearest contract in that series.

### API Response Schema
No information.


## Bitmex Trade
 
```sql
-- fetch data
select * from bitmex_trade where symbol = 'XBT7D_D95'
```

> response

```json
[

 {
   "time": "2019-07-11 14:59:42.056972",
   "foreignNotional":0.23265,
   "grossValue":235000000,
   "homeNotional": 23.5,
   "official_timestamp": None,
   "price": 0.00099,
   "symbol": "XBT7D_D95",
   "side": "Buy",
   "tickDirection": "PlusTick",
   "trdMatchID": "adffc000-d563-b5db-c9b6-a9ed3b304006"
 }

]
```

### Description
[Bitmex trade](https://www.bitmex.com/app/wsAPI) is connected through webscoket so it is real-time update. And data time range is from 2019-07-11 14:59:42.056972 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
foreignNotional    |float|
grossValue         |float|
homeNotional       |float|
official_timestamp |float|
price              |float|
size               |float|
tickDirection      |string|
trdMatchID         |string|
symbol | string | tag values
side | string | tag values


### Tag Vlaues 
**Symbols**: ADAH20, ADAM20, ADAU19, ADAZ19, BCHH20, BCHM20, BCHZ19, BCHU20, EOSH20, EOSM20, EOSU19, EOSZ19, ETHH20, ETHM20, ETHUSD, ETHU19, ETHZ19. LTCH20, LTCM20, LTCZ19, LTCU19, TRXH20, TRXM20, TRXZ19,TRXU19,  XBT7D_D95, XBT7D_U105, XBTH20, XBTM20, XBTU20, XBTUSD, XBTZ19, XBTU19, XRPH20, XRPM20, XRPU19, XRPUSD, XRPZ19

**side**: Buy, sell

### Data Sanity
No downtime.

### API Reference
`Websocket wss://www.bitmex.com/realtime?subscribe=trade`

### API Query Parameters
Name | Type | Description
-----| ----- | --------- |
symbol | string | Instrument symbol. Send a series (e.g. XBT) to get data for the nearest contract in that series.

### API Response Schema
No information
 
 
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

### API Response Schema
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

### API Response Schema
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

### API Response Schema
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

### API Response Schema
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


### API Response Schema
No information.



# Coinbase
[Coinbase](https://pro.coinbase.com/) is a American based exchange. Check their [api](https://docs.pro.coinbase.com/). 

## Coinbase Custody
```sql
-- fetch data
select * from coinbase_custody limit 1 
```
> response

```json
[
        {
            "time": "2020-12-11 05:32:23",
            "current_snapshot": 1583213543701198567,
            "icon": "/api/marketing/currencies/icon/9",
            "market_cap": 123395720,
            "name": "OmiseGO",
            "price": 1.121465426947944 ,
            "symbol": "omg"
          }
]
```

### Description
[Coinbase custody](https://custody.coinbase.com/assets) has a frequency of 1 hour and data time range is from 2020-12-11 05:32:23 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
current_snapshot | int | data timestamp
icon | string |
market_cap | int | 
name | string
price | float | 
symbol | string |


### Data Sanity
No downtime.

### API Reference

`GET https://api.custody.coinbase.com/api/marketing/currencies`

### API Query Parameters
Not required.

### API Response Schema
No information.


## Coinbase Orderbook
```sql
-- fetch data
select * from coinbase_orderbook limit 1 
```
> response

```json
[
        {
            "time": "2020-03-02 23:17:52",
            "snapshot": 2020-03-02 23:17:52.230351,
            "num_orders": 1,
            "price": 0.00007918,
            "sequence": 19699223,
            "size": 667,
            "symbol": "KNC-BTC",
            "type": "ask"
          }
]
```

### Description
[Coinbase orderbook](https://docs.pro.coinbase.com/#get-product-order-book) has a frequency of 30 seconds and data time range is from 2020-03-02 23:17:52.230351 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
snapshot | string | data timestamp
price | float |
size | float | 
num_orders | float
sequence | int | 
type | string | ask/bid
symbol | string | tag values

### Tag Values
**symbol**: KNC-USD, KNC-BTC, BTC-USD, ETH-USD

### Data Sanity
No downtime.

### API Reference
`GET https://api.pro.coinbase.com/products/{product-id}/book?level={level_num}`

### API Query Parameters
Name | Default | Description
-----| --------| ----------|
product-id | Yes | tickers
level | i | 1: Only the best bid and ask; 2: Top 50 bids and asks (aggregated): 3: Full order book (non aggregated)

**DETAILS**:
By default, only the inside (i.e. best) bid and ask are returned. This is equivalent to a book depth of 1 level. If you would like to see a larger order book, specify the level query parameter.
If a level is not aggregated, then all of the orders at each price will be returned. Aggregated levels return only one size for each active price (as if there was only a single order for that size at the level).

### API Response Schema
No information.



## Coinbase Trades
```sql
-- fetch data
select * from coinbase_trades limit 1 
```
> response

```json
[
        {
            "time": "2020-03-02 23:17:52",
            "timestamp": 2020-03-02 23:17:52.230351,
            "num_orders": 1,
            "price": 0.7045,
            "trade_id": 157095,
            "size": 504,
            "symbol": "KNC-BTC",
            "type": "sell"
          }
]
```

### Description
[Coinbase trade](https://docs.pro.coinbase.com/#get-trades) has a frequency of 5 minutes and data time range is from 2020-03-02 23:17:52.230351 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
timestamp | string | data timestamp
price | float |
size | float | 
num_orders | float
trade_id | int | 
type | string | sell/buy
symbol | string | tag values

### Tag Values
**symbol**: KNC-USD, KNC-BTC, BTC-USD, ETH-USD

### Data Sanity
No downtime.

### API Reference
`GET https://api.pro.coinbase.com/products/<product-id>/trades`

### API Query Parameters
Name | Required | Description
-----| --------| ----------|
product-id | Yes | tickers

**SIDE**:
The trade side indicates the maker order side. The maker order is the order that was open on the order book. buy side indicates a down-tick because the maker was a buy order and their order was removed. Conversely, sell side indicates an up-tick.

### API Response Schema
No information.



# Coinex
[Coinex](https://www.coinex.com/) is a crypto exchange. Check their [api](https://github.com/coinexcom/coinex_exchange_api/wiki).

## Coinex Orderbook
```sql
-- fetch data
select * from coinex_orderbook limit 1 
```
> response

```json
[
        {
            "time": "2020-03-13 19:51:16.957000",
            "snapshot": "2020-03-13 19:51:16.957000",
            "price": 0.1565,
            "size": 35.631,
            "symbol": "hnsusdt",
            "type": "ask"
          }
]
```

### Description
[Coinex orderbook](https://github.com/coinexcom/coinex_exchange_api/wiki/022depth) has a frequency of 30 seconds and data time range is from 2020-03-13 19:51:16.957000 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
snapshot | string | data timestamp
price | float |
size | float | 
type | string | ask/bid
symbol | string | tag values

### Tag Values
**symbol**: hnsbtc, hnsusdt

### Data Sanity
No downtime.

### API Reference
`GET https://api.coinex.com/v1/market/depth?market={}&limit=50&merge=0"`

### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------|----------|
market	|String	|Yes	| Get all market
merge	|String	|Yes	|'0', '0.1', '0.01', '0.001', '0.0001', '0.00001', '0.000001', '0.0000001', '0.00000001
limit	|Interger	|No(Default20)	|Return amount，range: 5/10/20/50

### API Response Schema
Name | Type | Description
---- | ---- | ----------|
last	|String|	Last price
time	|Long|	Updated time of Depth
asks	|Array|	Seller depth
asks[0][0]	|String|	Order price
asks[0][1]	|String|	Order amount
bids	|Array|	Buyer depth
bids[0][0]	|String|	Order price
bids[0][1]	|String|	Order amount


## Coinex Trades 
```sql
-- fetch data
select * from coinex_trades limit 1 
```
> response

```json
[
        {
            "time": "2020-03-13 19:24:12.957000",
            "timestamp": 1584127452333,
            "tradeID": 1205232182,
            "price": 0.000026426,
            "amount": 16.7853,
            "symbol": "hnsbtc",
            "type": "sell"
          }
]
```

### Description
[Coinex trades](https://github.com/coinexcom/coinex_exchange_api/wiki/023deals) has a frequency of 30 seconds and data time range is from 2020-03-13 19:24:16.957000 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
timestamp | string | data timestamp
tradeID | int |
price | float |
amount | float | 
type | string | buy/sell
symbol | string | tag values

### Tag Values
**symbol**: hnsbtc, hnsusdt

### Data Sanity
No downtime.

### API Reference
`GET https://api.coinex.com/v1/market/deals?market={}"`

### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
market	|String|	Yes	| Get makret list
last_id	|Integer|	No	|Transaction history id, send 0 to draw from the latest record.
limit	|Integer | No(default 100)|	Less than or equal to 1000

### API Response Schema
Name | Type | Description
---- | ---- | ----------
id	|Integer|	Transaction No
date	|Integer|	Transaction time
date_ms	|Integer|	Transaction time(ms)
amount	|String|	Transaction amount
price	|String|	Transaction price
type	|String|	buy/sell



# Coinflex
[Coinflex](https://coinflex.com/) is a crypto exchange that focues on futures trading. Check their [api](https://github.com/coinflex-exchange/API). 

## Coinflex Burn Fees
```sql
-- fetch data
select * from coinflex_burn_fees limit 1 
```
> response

```json
[
        {
            "time": "2019-12-30 20:29:11.657",
            "FLEX Acquisition Last 24 Hours": 39933.4489,
            "Revenue above burn threshold": 6528.39,
            "USDT to spend buying FLEX in current session": 1305.68,
            "Yesterday's Total Revenue": 27528.39,
          }
]
```

### Description
[Coinflex burn fees](https://coinflex.com/flexcoin/) has a frequency of 1 day and data time range is from 2019-12-30 20:29:11.657 to 2020-02-17 21:39:25. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
FLEX Acquisition Last 24 Hours | float |
Revenue above burn threshold | float | 
USDT to spend buying FLEX in current session | float | 
Yesterday's Total Revenue | float |

### Data Sanity
No downtime.

### Webscrapy
The data is collected thourgh webscrapying and the website has changed its format since 2020-02-17 so it is no longer available.



# Compound
[Compound](https://compound.finance/) is a cryptocurrency exchange. Check their [api](https://compound.finance/docs/api). 

## Compound borrow rates
```sql
-- fetch data
select * from compound_borrow_rates limit 1 
```
> response

```json
[
 "cToken": [{
   "borrow_rate": {"value": "0.051453109785093843"},
   "cash": {"value": "514.078443"},
   "collateral_factor": {"value": "0.80000000000000000"},
   "exchange_rate": {"value": "0.020024242770802729"},
   "interest_rate_model_address": "0x1a43bfd39b15dcf444e17ab408c4b5be32deb7f5",
   "name": "Compound USD Coin",
   "number_of_borrowers": 3,
   "number_of_suppliers": 34,
   "reserves": {"value": "0"},
   "supply_rate": {"value": "0.013237112532748109"},
   "symbol": "cUSDC",
   "token_address": "0x5b281a6dda0b271e91ae35de655ad301c976edb1",
   "total_borrows": {"value": "178.064546"},
   "total_supply": {"value": "34565.25157651"},
   "underlying_address": "0x4dbcdf9b62e891a7cec5a2568c3f4faf9e8abe2b",
   "underlying_name": "USD Coin",
   "underlying_price": {"value": "0.0041368287055953530000000000"},
   "underlying_symbol":"USDC"
  }],
 "error": null,
 "request": {
   "addresses": ["0x5b281a6dda0b271e91ae35de655ad301c976edb1"],
   "block_number": 4515576,
   "block_timestamp": 0
  }
}
]
```

### Description
[Compound borrow rates](https://compound.finance/docs/api#CTokenService) has a frequency of 1 minute and data time range is from 2019-12-13 21:52:44.471000 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
borrow_rate                 |string|
cash                        |string|
collateral_factor           |string|
exchange_rate               |string|
interest_rate_model_address |string|
name                        |string|
number_of_borrowers         |integer|
number_of_suppliers         |integer|
reserves                    |string|
supply_rate                 |string|
symbol                      |string|
token_address               |string|
total_borrows               |string|
total_supply                |string|
underlying_address          |string|
underlying_name             |string|
underlying_price            |string|
underlying_symbol           |string|


### Data Sanity
No downtime.

### API Reference
`GET https://api.compound.finance/api/v2/ctoken?meta=true`

### API Query Parameters
Type | Key | Description 
---- | --- | -----------
bytes	| addresses|	List of token addresses to filter on, e.g.: ["0x...", ,"0x..."] 
uint32	| block_number |	Only one of block_number or block timestamp should be provided.
uint32	| block_timestamp	| Only one of block_number or block timestamp should be provided. 
bool	| meta | 	Pass true to get metadata for the token addresses specified.
string	| network	|The ethereum network to use for the request

### API Response Schema
Type | Key | Description
---- | --- | ----------
Error	| error |	
CTokenRequest	| request | The request parameters are echoed in the response.
CToken	| cToken |	The list of cToken matching the requested filter.
CTokenMeta	| meta	|  Metadata for all CTokens specified



# Deribit
[Deribit](https://www.deribit.com/) is a crypto exchange that only trading derivatives such as options, futures, swap. Check their [websocket api](https://docs.deribit.com/#deribit-api-v2-0-0) and [rpc api](https://deribitexchange.gitbooks.io/deribit-api/rpc-endpoints.html).

<aside class="notice">
Deribit websocket connection is very unstable so use rpc api instead if possible.
</aside>


## Deribit Funding Rate
```sql
-- fetch funding orderbook  
select * from deribit_funding_rate 
```

> response

```json
[

 {
   'time': '2019-07-11T15:59:42.095025749Z', 
   'fundingRate': -0.0004270246217739543, 
   'symbol': 'ETH-PERPETUAL'
 }

]
```

### Description
[Deribit funding rate](https://docs.deribit.com/#perpetual-instrument_name-interval) is connected through websocket and data time range is from 2019-07-11 15:59:42.095025749 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
fundingRate | float | 
symbol | string | tag values

### Tag Vlaues 
**Symbols**: 
BTC-PERPETUAL, ETH-PERPETUAL

### Data Sanity
No downtime.

### API Reference
**Ednpoint**:
`Websocket wss://www.deribit.com/ws/api/v2`

**Message**:
```json
    {"jsonrpc": "2.0",
     "method": "public/subscribe",
     "id": 42,
     "params": {
        "channels": ["perpetual.BTC-PERPETUAL.raw"]}
    }
```

### API Parameters
Parameters | Required | Type| Enum | Description
---------- | -------- | ----| ---- | ----------
instrument_name	|true	|string		|Instrument name
interval	|true	|string	|100ms; raw|	Frequency of notifications. Events will be aggregated over this interval. The value raw means no aggregation will be applied

### API Response Schema
Name | Type | Description 
---- | ---- | -----------
data	| object	|
  ›  index_price	|number	 |Current index price
  ›  interest	|number	|Current interest
  ›  timestamp	|integer	|The timestamp (milliseconds since the Unix epoch)


## Deribit Ticker
```sql
-- fetch option ticker 
select * from deribit_optionsTicker

-- fetch ticker 
select * from deribit_ticker
```
> response

```json
[

 {
   'time': '2019-07-11T15:59:41.176999936Z', 
   'best_ask_amount': 94830, 
   'best_ask_price': 11545.5, 
   'best_bid_amount': 130, 
   'best_bid_price': 11545, 
   'current_funding': 0, 
   'delivery_price': None, 
   'estimated_delivery_price': None, 
   'funding_8h': -6.37e-05, 
   'high': 12391.5, 
   'index_price': 11548.49, 
   'last_price': 11545, 
   'low': 11072.5, 
   'mark_price': 11547.79, 
   'max_price': 11721.43, 
   'min_price': 11374.98, 
   'open_interest': 72838741, 
   'price_change': None, 
   'settlement_price': 11603.01, 
   'state': 'open', 
   'symbol': 'BTC-PERPETUAL', 
   'volume': 78539.90505946, 
   'volume_usd': None
 }

]
```

### Description
[Deribit option ticker and ticker](https://docs.deribit.com/?python#ticker-instrument_name-interval) is connected thourgh websocket and data time range for ticker is from 2019-07-11T15:59:41.176999936Z till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
ask_iv                   |float|
best_ask_amount          |float|
best_ask_price           |float|
best_bid_amount          |float|
best_bid_price           |float|
bid_iv                   |float|
change_id                |integer|
delivery_price           |float|
delta                    |float|
estimated_delivery_price |float|
gamma                    |float|
high                     |float|
index_price              |float|
interest_rate            |float|
last_price               |float|
low                      |float|
mark_iv                  |float|
mark_price               |float|
max_price                |float|
min_price                |float|
open_interest            |float|
price_change             |float|
rho                      |float|
settlement_price         |float|
state                    |string|
theta                    |float|
underlying_index         |string|
underlying_price         |float|
vega                     |float|
volume                   |float|
symbol | string | tag values

### Tag Vlaues 
**Option Symbols** ([Snapshot symbols](https://www.deribit.com/main#/options?tab=all) since symbols will increase per day due to rolling option tickers):
'BTC-10APR20-4750-C',  'ETH-9APR20-185-C'

**Futures and Swap Symbols**:
'BTC-25SEP20', 'BTC-26JUN20', 'BTC-27DEC19', 'BTC-27MAR20', 'BTC-27SEP19', 'BTC-PERPETUAL', 'ETH-25SEP20', 'ETH-26JUN20', 'ETH-27DEC19', 'ETH-27MAR20', 'ETH-27SEP19', 'ETH-PERPETUAL'

### Data Sanity
No downtime.

### API Reference
**Endpoint**:
`Websocket wss://www.deribit.com/ws/api/v2`

**Message**:
```json
{"jsonrpc": "2.0",
     "method": "public/subscribe",
     "id": 42,
     "params": {
        "channels": ["ticker.BTC-PERPETUAL.raw"]}
}
```

### API Response Schema
Check [api doc](https://docs.deribit.com/#public-ticker) 


## Deribit Orderbook
```sql
-- fetch orderbook  
select * from deribit_orderbook
```

> response

```json
[

 {
   'time': '2020-02-25T00:47:24.731618392Z', 
   'amount': 1330, 
   'price': 9618.5, 
   'symbol': 'BTC-PERPETUAL', 
   'timestamp': 1582591644630, 
   'type': 'asks'
   
 }

]
```

### Description
[Deribit orderbook](https://deribitexchange.gitbooks.io/deribit-api/rpc-endpoints.html) has a frequency of 10 or 20 seconds and data time range is from 2020-02-25T00:47:24.731618392Z till now but the data is consistently collecting for at least from 2020-03-15. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
amount    |float|
price     |float|
timestamp |integer|
type      |string|
symbol | string | tag values

### Tag Vlaues 
**Futures, Options and Swap Symbols**(Symbol Snapshot and symbols will increase per day due to rolling option tickers):
'BTC-10APR20-4750-C', 'ETH-9APR20-155-C', 'ETH-PERPETUAL'


### Data Sanity
No downtime.

### API Reference

`GET https://www.deribit.com/api/v1/public/getorderbook`

### API Query Parameters
Name | Type | Mandatory | Description | 
---- | ---- | ---------- | -------- | 
instrument	|string|REQUIRED |The instrument name for which to retrieve the order book, see getinstruments to obtain instrument names.
depth	|integer|	Not Required	|The number of entries to return for bids and asks

### API Response Schema
Fields	|Type	| Example | Description
--------| ----| ----------| ---------
bids	|list|	[800(quantity/int),10322.5(price/float), 800(cm/int)] |	The list of all bids, best bid first. See below for entry details
asks	|list| [800(quantity/int),10322.5(price/float), 800(cm/int)] 	|	The list of all asks, best ask first. See below for entry details
state	|string |"open"|	The state of the order book. Possible values include "open" and "closed".


## Deribit Trades
```sql
-- fetch orderbook  
select * from deribit_trades
```

> response

```json
[

 {
   'time': '2019-07-11T15:55:52.404Z', 
   'amount': 1, 
   'block_trade_id': None, 
   'index_price': 269.61, 
   'iv': None, 
   'liquidation': None, 
   'price': 269.55, 
   'side': 'buy', 
   'symbol': 'ETH-PERPETUAL', 
   'tick_direction': 0,
   'timestamp': None, 
   'trade_id': 'ETH-6233051', 
   'trade_seq': 5254708
 }

]
```

### Description
[Deribit trades](https://deribitexchange.gitbooks.io/deribit-api/rpc-endpoints.html) is connected thourgh websocket and data time range is from 2019-07-11T15:55:52.404Z till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
amount         |float|
block_trade_id |string|
index_price    |float|
iv             |float|
liquidation    |string|
price          |float|
tick_direction |integer|
timestamp      |integer|
trade_id       |string|
trade_seq      |integer|
symbol | string | tag values

### Tag Vlaues 
**Futures, Options and Swap Symbols**(Symbol Snapshot and symbols will increase per day due to rolling option tickers):
'BTC-10APR20-4750-C', 'ETH-9APR20-155-C', 'ETH-PERPETUAL'

### Data Sanity
No downtime.

### API Reference
**Endpoint**:
`Websocket wss://www.deribit.com/ws/api/v2`

**Message**:
```json
{
  "jsonrpc" : "2.0",
  "id" : 4497,
  "method" : "public/get_last_settlements_by_currency",
  "params" : {
    "currency" : "BTC",
    "type" : "delivery",
    "count" : 2
  }
}
```

### API Response Schema
Fields	|Type | Description
--------| ----| ----------|
amount|number|Trade amount.For perpetual and futures in USD units, for options it is amount of corresponding cryptocurrency contracts
price	|number	|Price in base currency






# Dydx
[Dydx](https://dydx.exchange/) is a crypto currency exchange. Check thier [api](https://docs.dydx.exchange/#/).

## Dydx Borrow Rates
```sql
-- fetch data
select * from compound_borrow_rates limit 1 
```
> response

```json
[
{
'time': '2019-12-13T21:09:53.898804006Z', 
'borrowIndex': '1.006031229754822259', 
'borrowInterestRateSeconds': '0.00000000010466883', 
'collateralRatio': '1.15', 
'contractAddress': '0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2', 
'createdAt': '2018-07-10T04:08:53.352Z', 
'currencyUuid': '9debe831-5ccd-448b-91f7-cd247ecddc22', 
'decimals': 18, 
'id': 0, 
'lastIndexUpdateSeconds': '1576271271', 
'marginPremium': '0', 
'name': 'Ethereum', 
'oraclePrice': '144250000000000000000', 
'spreadPremium': '0', 
'supplyIndex': '1.000753414014796151', 
'supplyInterestRateSeconds': '0.00000000000820549837405634341628924066685701737125718373287686068422216351405335', 
'symbol': 'WETH', 
'totalBorrowAPR': '0.00330083622288', 
'totalBorrowAPY': '0.0033062899817690727', 
'totalBorrowPar': '7999732470426071831156', 
'totalBorrowWei': '8047980694932323332662.809402813438501404', 
'totalSupplyAPR': '0.0002587685967242408459760974936700028998199665462000046785376301485791864456', 
'totalSupplyAPY': '0.00025880208020567785', 
'totalSupplyPar': '97453140705341277722335', 
'totalSupplyWei': '97526563267334583101049.371353402604732585', 
'updatedAt': '2018-07-10T04:08:53.352Z', 
'uuid': '9debe831-5ccd-448b-91f7-cd247ecddc22'
}
]
```

### Description
[Dydx borrow rates](https://defirate.com/dydx/) has a frequency of 1 minute and data time range is from 2019-12-13 21:09:44.88 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
borrowIndex               |string|
borrowInterestRateSeconds |string|
collateralRatio           |string|
contractAddress           |string|
createdAt                 |string|
currencyUuid              |string|
decimals                  |integer|
id                        |integer|
lastIndexUpdateSeconds    |string|
marginPremium             |string|
name                      |string|
oraclePrice               |string|
spreadPremium             |string|
supplyIndex               |string|
supplyInterestRateSeconds |string|
symbol                    |string|
totalBorrowAPR            |string|
totalBorrowAPY            |string|
totalBorrowPar            |string|
totalBorrowWei            |string|
totalSupplyAPR            |string|
totalSupplyAPY            |string|
totalSupplyPar            |string|
totalSupplyWei            |string|
updatedAt                 |string|
uuid                      |string|


### Data Sanity
No downtime.

### API Reference
`GET https://api.dydx.exchange/v1/markets`

### API Query Parameters
Not required.

### API Response Schema
No information.



# FTX
[FTX](https://ftx.com/) is a cryptocurrency exchange. Check their [api](https://docs.ftx.com/#overview).

## FTX Funding Rate
```sql
-- fetch data
select * from FTX_funding_rates limit 1 
```
> response

```json
[
    {
          'time': '2019-09-03T15:00:00Z', 
          'rate': -4.9e-05, 
          'symbol': 'BNB-PERP'
   }
]
```

### Description
[FTX funding rates](https://docs.ftx.com/#get-funding-rates) has a frequency of 1 minute and data time range is from 2019-09-03 15:00:00 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
rate |  float | 
symbol | string | tag values

### Tag Values
**Symbol (Symbols are subject to change)**: 
'ADA-PERP', 'ALGO-PERP', 'ALT-PERP', 'ATOM-PERP', 'BCH-PERP', 'BNB-PERP', 'BSV-PERP', 'BTC-PERP', 'BTMX-PERP', 'DOGE-PERP', 'DRGN-PERP', 'EOS-PERP', 'ETC-PERP', 'ETH-PERP', 'EXCH-PERP', 'HT-PERP', 'LEO-PERP', 'LINK-PERP', 'LTC-PERP', 'MATIC-PERP', 'MID-PERP', 'OKB-PERP', 'PAXG-PERP', 'PRIV-PERP', 'SHIT-PERP', 'TOMO-PERP', 'TRX-PERP', 'TRYB-PERP', 'USDT-PERP', 'XAUT-PERP', 'XRP-PERP', 'XTZ-PERP

### Data Sanity
No downtime.

### API Reference
`GET https://ftx.com/api/funding_rates`

### API Query Parameters
Name | Type | Value | Description
-----| --------| ----------| --------- |
start_time	|number|	1559881511|	optional
end_time	|number|	1559881711|	optional
future	|string|	BTC-PERP	|optional

### API Response Schema
Name | Type | Value | Description
---- | ---- | ----- | -----------
future	|string	| BTC-PERP |	
rate	|number	|0.0025	|
time	|string	|2019-06-02T08:00:00+00:00	|


## FTX Futures Statistics
```sql
-- fetch data
select * from FTX_future_stats limit 1 
```
> response

```json
[
    {
          'time': '2019-09-04T17:01:01.333594927Z', 
          'expirationPrice': None, 
          'nextFundingRate': -0.000166, 
          'nextFundingTime': '2019-09-04T18:00:00+00:00', 
          'openInterest': 3662445, 
          'predictedExpirationPrice': None, 
          'strikePrice': None, 
          'symbol': 'ALGO-PERP', 
          'volume': 2239354
   }
]
```

### Description
[FTX future stats](https://docs.ftx.com/#get-future-stats) has a frequency of 1 nimute and data time range is from 2019-09-04 17:01:01.333594927 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
expirationPrice          |float|
nextFundingRate          |float|
nextFundingTime          |string|
openInterest             |float|
predictedExpirationPrice |float|
strikePrice              |float|
volume                   |float|
symbol | string | tag values

### Tag Values
**Symbol (Symbols are subject to change)**: 
'ADA-0327', 'ADA-0626', 'ADA-1227', 'ADA-PERP', 'ALGO-0327', 'ALGO-0626', 'ALGO-0927', 'ALGO-1227', 'ALGO-PERP', 'ALT-0327', 'ALT-0626', 'ALT-0927', 'ALT-1227', 'ALT-PERP', 'ATOM-0327', 'ATOM-0626', 'ATOM-1227', 'ATOM-PERP', 'BCH-0327', 'BCH-0626', 'BCH-0927', 'BCH-1227', 'BCH-PERP', 'BERNIE', 'BIDEN', 'BLOOMBERG', 'BNB-0327', 'BNB-0626', 'BNB-0927', 'BNB-1227', 'BNB-PERP', 'BSV-0327', 'BSV-0626', 'BSV-0927', 'BSV-1227', 'BSV-PERP', 'BTC-0327', 'BTC-0626', 'BTC-0925', 'BTC-0927', 'BTC-1227', 'BTC-MOVE-0101', 'BTC-MOVE-0102', 'BTC-MOVE-0103', 'BTC-MOVE-0104', 'BTC-MOVE-0105', 'BTC-MOVE-0106', 'BTC-MOVE-0107', 'BTC-MOVE-0108', 'BTC-MOVE-0109', 'BTC-MOVE-0110', 'BTC-MOVE-0111', 'BTC-MOVE-0112', 'BTC-MOVE-0113', 'BTC-MOVE-0114', 'BTC-MOVE-0115', 'BTC-MOVE-0116', 'BTC-MOVE-0117', 'BTC-MOVE-0118', 'BTC-MOVE-0119', 'BTC-MOVE-0120', 'BTC-MOVE-0121', 'BTC-MOVE-0122', 'BTC-MOVE-0123', 'BTC-MOVE-0124', 'BTC-MOVE-0125', 'BTC-MOVE-0126', 'BTC-MOVE-0127', 'BTC-MOVE-0128', 'BTC-MOVE-0129', 'BTC-MOVE-0130', 'BTC-MOVE-0131', 'BTC-MOVE-0201', 'BTC-MOVE-0202', 'BTC-MOVE-0203', 'BTC-MOVE-0204', 'BTC-MOVE-0205', 'BTC-MOVE-0206', 'BTC-MOVE-0207', 'BTC-MOVE-0208', 'BTC-MOVE-0209', 'BTC-MOVE-0210', 'BTC-MOVE-0211', 'BTC-MOVE-0212', 'BTC-MOVE-0213', 'BTC-MOVE-0214', 'BTC-MOVE-0215', 'BTC-MOVE-0216', 'BTC-MOVE-0217', 'BTC-MOVE-0218', 'BTC-MOVE-0219', 'BTC-MOVE-0220', 'BTC-MOVE-0221', 'BTC-MOVE-0222', 'BTC-MOVE-0223', 'BTC-MOVE-0224', 'BTC-MOVE-0225', 'BTC-MOVE-0226', 'BTC-MOVE-0227', 'BTC-MOVE-0228', 'BTC-MOVE-0229', 'BTC-MOVE-0301', 'BTC-MOVE-0302', 'BTC-MOVE-0303', 'BTC-MOVE-0304', 'BTC-MOVE-0305', 'BTC-MOVE-0306', 'BTC-MOVE-0307', 'BTC-MOVE-0308', 'BTC-MOVE-0309', 'BTC-MOVE-0310', 'BTC-MOVE-0311', 'BTC-MOVE-0312', 'BTC-MOVE-0313', 'BTC-MOVE-0314', 'BTC-MOVE-0315', 'BTC-MOVE-0316', 'BTC-MOVE-0317', 'BTC-MOVE-0318', 'BTC-MOVE-0319', 'BTC-MOVE-0320', 'BTC-MOVE-0321', 'BTC-MOVE-0322', 'BTC-MOVE-0323', 'BTC-MOVE-0324', 'BTC-MOVE-0325', 'BTC-MOVE-0326', 'BTC-MOVE-0327', 'BTC-MOVE-0328', 'BTC-MOVE-0329', 'BTC-MOVE-0330', 'BTC-MOVE-0331', 'BTC-MOVE-0401', 'BTC-MOVE-0402', 'BTC-MOVE-0403', 'BTC-MOVE-0404', 'BTC-MOVE-0405', 'BTC-MOVE-0406', 'BTC-MOVE-0407', 'BTC-MOVE-0408', 'BTC-MOVE-0409', 'BTC-MOVE-0410', 'BTC-MOVE-0411', 'BTC-MOVE-0412', 'BTC-MOVE-0413', 'BTC-MOVE-0414', 'BTC-MOVE-0415', 'BTC-MOVE-0416', 'BTC-MOVE-0417', 'BTC-MOVE-0418', 'BTC-MOVE-0419', 'BTC-MOVE-0420', 'BTC-MOVE-0421', 'BTC-MOVE-0422', 'BTC-MOVE-0925', 'BTC-MOVE-0926', 'BTC-MOVE-0927', 'BTC-MOVE-0928', 'BTC-MOVE-0929', 'BTC-MOVE-0930', 'BTC-MOVE-1001', 'BTC-MOVE-1002', 'BTC-MOVE-1003', 'BTC-MOVE-1004', 'BTC-MOVE-1005', 'BTC-MOVE-1006', 'BTC-MOVE-1007', 'BTC-MOVE-1008', 'BTC-MOVE-1009', 'BTC-MOVE-1010', 'BTC-MOVE-1011', 'BTC-MOVE-1012', 'BTC-MOVE-1013', 'BTC-MOVE-1014', 'BTC-MOVE-1015', 'BTC-MOVE-1016', 'BTC-MOVE-1017', 'BTC-MOVE-1018', 'BTC-MOVE-1019', 'BTC-MOVE-1020', 'BTC-MOVE-1121', 'BTC-MOVE-1122', 'BTC-MOVE-1123', 'BTC-MOVE-1124', 'BTC-MOVE-1125', 'BTC-MOVE-1126', 'BTC-MOVE-1127', 'BTC-MOVE-1128', 'BTC-MOVE-1129', 'BTC-MOVE-1130', 'BTC-MOVE-1201', 'BTC-MOVE-1202', 'BTC-MOVE-1203', 'BTC-MOVE-1204', 'BTC-MOVE-1205', 'BTC-MOVE-1206', 'BTC-MOVE-1207', 'BTC-MOVE-1208', 'BTC-MOVE-1209', 'BTC-MOVE-1210', 'BTC-MOVE-1211', 'BTC-MOVE-1212', 'BTC-MOVE-1213', 'BTC-MOVE-1214', 'BTC-MOVE-1215', 'BTC-MOVE-1216', 'BTC-MOVE-1217', 'BTC-MOVE-1218', 'BTC-MOVE-1219', 'BTC-MOVE-1220', 'BTC-MOVE-1221', 'BTC-MOVE-1222', 'BTC-MOVE-1223', 'BTC-MOVE-1224', 'BTC-MOVE-1225', 'BTC-MOVE-1226', 'BTC-MOVE-1227', 'BTC-MOVE-1228', 'BTC-MOVE-1229', 'BTC-MOVE-1230', 'BTC-MOVE-1231', 'BTC-MOVE-2019Q4', 'BTC-MOVE-2020Q1', 'BTC-MOVE-2020Q2', 'BTC-MOVE-2020Q3', 'BTC-MOVE-2020Q4', 'BTC-MOVE-WK-0103', 'BTC-MOVE-WK-0110', 'BTC-MOVE-WK-0117', 'BTC-MOVE-WK-0124', 'BTC-MOVE-WK-0131', 'BTC-MOVE-WK-0207', 'BTC-MOVE-WK-0214', 'BTC-MOVE-WK-0221', 'BTC-MOVE-WK-0228', 'BTC-MOVE-WK-0306', 'BTC-MOVE-WK-0313', 'BTC-MOVE-WK-0320', 'BTC-MOVE-WK-0327', 'BTC-MOVE-WK-0403', 'BTC-MOVE-WK-0410', 'BTC-MOVE-WK-0417', 'BTC-MOVE-WK-0424', 'BTC-MOVE-WK-0501', 'BTC-MOVE-WK-0508', 'BTC-MOVE-WK-0515', 'BTC-MOVE-WK-1122', 'BTC-MOVE-WK-1129', 'BTC-MOVE-WK-1206', 'BTC-MOVE-WK-1213', 'BTC-MOVE-WK-1220', 'BTC-MOVE-WK-1227', 'BTC-PERP', 'BTMX-0327', 'BTMX-0626', 'BTMX-1227', 'BTMX-PERP', 'DOGE-0327', 'DOGE-0626', 'DOGE-1227', 'DOGE-PERP', 'DRGN-0327', 'DRGN-0626', 'DRGN-1227', 'DRGN-PERP', 'EOS-0327', 'EOS-0626', 'EOS-0927', 'EOS-1227', 'EOS-PERP', 'ETC-0327', 'ETC-0626', 'ETC-0927', 'ETC-1227', 'ETC-PERP', 'ETH-0327', 'ETH-0626', 'ETH-0927', 'ETH-1227', 'ETH-PERP', 'EXCH-0327', 'EXCH-0626', 'EXCH-0927', 'EXCH-1227', 'EXCH-PERP', 'HT-0327', 'HT-0626', 'HT-0927', 'HT-1227', 'HT-PERP', 'LEO-0327', 'LEO-0626', 'LEO-0927', 'LEO-1227', 'LEO-PERP', 'LINK-0327', 'LINK-0626', 'LINK-1227', 'LINK-PERP', 'LTC-0327', 'LTC-0626', 'LTC-0927', 'LTC-1227', 'LTC-PERP', 'MATIC-0327', 'MATIC-0626', 'MATIC-1227', 'MATIC-PERP', 'MID-0327', 'MID-0626', 'MID-0927', 'MID-1227', 'MID-PERP', 'OKB-0327', 'OKB-0626', 'OKB-0927', 'OKB-1227', 'OKB-PERP', 'PAXG-0327', 'PAXG-0626', 'PAXG-PERP', 'PETE', 'PRIV-0327', 'PRIV-0626', 'PRIV-PERP', 'SHIT-0327', 'SHIT-0626', 'SHIT-0927', 'SHIT-1227', 'SHIT-PERP', 'TOMO-0327', 'TOMO-0626', 'TOMO-1227', 'TOMO-PERP', 'TRUMP', 'TRX-0327', 'TRX-0626', 'TRX-0927', 'TRX-1227', 'TRX-PERP', 'TRYB-0327', 'TRYB-0626', 'TRYB-1227', 'TRYB-PERP', 'USDT-0327', 'USDT-0626', 'USDT-0927', 'USDT-1227', 'USDT-PERP', 'WARREN', 'XAUT-0327', 'XAUT-0626', 'XAUT-PERP', 'XRP-0327', 'XRP-0626', 'XRP-0927', 'XRP-1227', 'XRP-PERP', 'XTZ-0327', 'XTZ-0626', 'XTZ-1227', 'XTZ-PERP'

### Data Sanity
No downtime.

### API Reference
`GET https://ftx.com/api/futures/{future_name}/stats`

### API Query Parameters
Name | Type | Value | Description
-----| --------| ----------| --------- |
future_name | string | LINK-1227| Futures name 

### API Response Schema
Name | Type | Value | Description
-----| --------| ----------| --------- |
volume	|number	|1000.23	|quantity traded in the last 24 hours
nextFundingRate	|number	|0.00025	|upcoming funding rate (only applicable for perpetual contracts)
nextFundingTime	|string|	2019-03-29T03:00:00+00:00	|upcoming funding time (only applicable for perpetual contracts)
expirationPrice	|number|	3992.1|	price to which the future expired (only applicable if the future has expired)
predictedExpirationPrice|	number|	3993.0	|only applicable if the future has not expired
openInterest|	number	|21124.583	|number of open contracts in this future
strikePrice	|number	|8182.35009484|	price of the underlying at the beginning of the expiration day (only applicable for MOVE contracts)


## FTX Leaderboard
```sql
-- fetch data
select * from FTX_leaderboard limit 1 
```
> response

```json
[
    {
          'time': '2020-04-17T18:03:11.308176903Z', 
          'current_timestamp': '2020-04-17 18:03:11.301949', 
          'isRealName': 'False', 
          'name': 'odin@folkvang.io', 
          'rank': 1, 
          'type': 'volume'
   }
]
```

### Description
[FTX leaderboard](https://ftx.com/leaderboard) has a frequency of 1 hour and data time range is from 2020-04-17 18:03:11.308176903 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
current_timestamp |string|
isRealName        |string|
name              |string|
rank              |integer|
type  |string | tag values

### Tag Values
**Type**: 
maker_volume, volume, pnl

### Data Sanity
No downtime.

### API Reference
`GET https://ftx.com/api/leaderboard`

### API Query Parameters
Name | Type | Value | Description
-----| --------| ----------| --------- |
type	|string|	volume|	

### API Response Schema
No information. 




## FTX Option Request
```sql
-- fetch data
select * from FTX_option_request limit 1 
```
> response

```json
[
    {
          'time': '2020-02-05T06:28:37.37463808Z', 
          'id': 5536365, 
          'option_exipry': '2020-02-06T03:00:00+00:00', 
          'option_type': 'call', 
          'requestExpiry': '2020-02-06T03:00:00+00:00', 
          'side': 'buy', 
          'size': 5, 
          'status': 'open', 
          'strike_price': 9200, 
          'underlying': 'BTC'
   }
]
```

### Description
[FTX option request](https://docs.ftx.com/#list-quote-requests) has a frequency of 1 second and data time range is from 2020-02-05 06:28:37.37463808 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
id            integer
option_exipry string
option_type   string
requestExpiry string
side          string
size          float
status        string
strike_price  float
underlying    string


### Data Sanity
No downtime.

### API Reference
`GET https://ftx.com/api/options/requests`

### API Query Parameters
Not required.

### API Response Schema
Name | Type | Value | Description
---- | ---- | ----- | -----------
id	|number	|512|	
option	|dict		|option object; see below
size	|number	|1.2	
side	|string	|buy	
time	|string	|2020-01-07T22:35:54.626023+00:00	|when the request was placed
status	|string	|open	 |
requestExpiry	|string	|2020-01-08T22:35:54.626023+00:00	|when the request expires
limitPrice	|number	|10.2	|optional; omitted when the request has no limit price or it is hidden
option -> underlying	|string	|BTC |	
option -> type|	string|	call|	"call" or "put"
option -> strike|	number|	7800 |	
option -> expiry|	string|	2020-01-08T03:00:00+00:00 |



## FTX Orderbook 
```sql
-- fetch data
select * from FTX_orderbook limit 1 
```
> response

```json
[
    {
          'time': '2020-01-09T19:29:15.768404927Z', 
          'price': 121.25, 
          'size': 0.9787, 
          'snapshot': '2020-01-09 19:27:33.196682', 
          'symbol': 'BTC-MOVE-0109', 
          'type': 'ask'
   }
]
```

### Description
[FTX orderbook](https://docs.ftx.com/#get-orderbook) has a frequency of 30 second and data time range is from 2020-01-09 19:29:15.768404927 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
price    |float|
size     |float|
snapshot |string|
type     |string|
symbol | string | tag values

### Tag Values
**Symbol(Symbols are subject to change)**: 
'ADA-0327', 'ADA-0626', 'ADA-PERP', 'ALGO-0327', 'ALGO-0626', 'ALGO-PERP', 'ALT-0327', 'ALT-0626', 'ALT-PERP', 'ATOM-0327', 'ATOM-0626', 'ATOM-PERP', 'BCH-0327', 'BCH-0626', 'BCH-PERP', 'BERNIE', 'BIDEN', 'BLOOMBERG', 'BNB-0327', 'BNB-0626', 'BNB-PERP', 'BSV-0327', 'BSV-0626', 'BSV-PERP', 'BTC-0327', 'BTC-0626', 'BTC-0925', 'BTC-MOVE-0109', 'BTC-MOVE-0110', 'BTC-MOVE-0111', 'BTC-MOVE-0112', 'BTC-MOVE-0113', 'BTC-MOVE-0114', 'BTC-MOVE-0115', 'BTC-MOVE-0116', 'BTC-MOVE-0117', 'BTC-MOVE-0118', 'BTC-MOVE-0119', 'BTC-MOVE-0120', 'BTC-MOVE-0121', 'BTC-MOVE-0122', 'BTC-MOVE-0123', 'BTC-MOVE-0124', 'BTC-MOVE-0125', 'BTC-MOVE-0126', 'BTC-MOVE-0127', 'BTC-MOVE-0128', 'BTC-MOVE-0129', 'BTC-MOVE-0130', 'BTC-MOVE-0131', 'BTC-MOVE-0201', 'BTC-MOVE-0202', 'BTC-MOVE-0203', 'BTC-MOVE-0204', 'BTC-MOVE-0205', 'BTC-MOVE-0206', 'BTC-MOVE-0207', 'BTC-MOVE-0208', 'BTC-MOVE-0209', 'BTC-MOVE-0210', 'BTC-MOVE-0211', 'BTC-MOVE-0212', 'BTC-MOVE-0213', 'BTC-MOVE-0214', 'BTC-MOVE-0215', 'BTC-MOVE-0216', 'BTC-MOVE-0217', 'BTC-MOVE-0218', 'BTC-MOVE-0219', 'BTC-MOVE-0220', 'BTC-MOVE-0221', 'BTC-MOVE-0222', 'BTC-MOVE-0223', 'BTC-MOVE-0224', 'BTC-MOVE-0225', 'BTC-MOVE-0226', 'BTC-MOVE-0227', 'BTC-MOVE-0228', 'BTC-MOVE-0229', 'BTC-MOVE-0301', 'BTC-MOVE-0302', 'BTC-MOVE-0303', 'BTC-MOVE-0304', 'BTC-MOVE-0305', 'BTC-MOVE-0306', 'BTC-MOVE-0307', 'BTC-MOVE-0308', 'BTC-MOVE-0309', 'BTC-MOVE-0310', 'BTC-MOVE-0311', 'BTC-MOVE-0312', 'BTC-MOVE-0313', 'BTC-MOVE-0314', 'BTC-MOVE-0315', 'BTC-MOVE-0316', 'BTC-MOVE-0317', 'BTC-MOVE-0318', 'BTC-MOVE-0319', 'BTC-MOVE-0320', 'BTC-MOVE-0321', 'BTC-MOVE-0322', 'BTC-MOVE-0323', 'BTC-MOVE-0324', 'BTC-MOVE-0325', 'BTC-MOVE-0326', 'BTC-MOVE-0327', 'BTC-MOVE-0328', 'BTC-MOVE-0329', 'BTC-MOVE-0330', 'BTC-MOVE-0331', 'BTC-MOVE-0401', 'BTC-MOVE-0402', 'BTC-MOVE-0403', 'BTC-MOVE-0404', 'BTC-MOVE-0405', 'BTC-MOVE-0406', 'BTC-MOVE-0407', 'BTC-MOVE-0408', 'BTC-MOVE-0409', 'BTC-MOVE-0410', 'BTC-MOVE-0411', 'BTC-MOVE-0412', 'BTC-MOVE-0413', 'BTC-MOVE-0414', 'BTC-MOVE-0415', 'BTC-MOVE-0416', 'BTC-MOVE-0417', 'BTC-MOVE-0418', 'BTC-MOVE-0419', 'BTC-MOVE-0420', 'BTC-MOVE-0421', 'BTC-MOVE-0422', 'BTC-MOVE-2020Q1', 'BTC-MOVE-2020Q2', 'BTC-MOVE-2020Q3', 'BTC-MOVE-2020Q4', 'BTC-MOVE-WK-0110', 'BTC-MOVE-WK-0117', 'BTC-MOVE-WK-0124', 'BTC-MOVE-WK-0131', 'BTC-MOVE-WK-0207', 'BTC-MOVE-WK-0214', 'BTC-MOVE-WK-0221', 'BTC-MOVE-WK-0228', 'BTC-MOVE-WK-0306', 'BTC-MOVE-WK-0313', 'BTC-MOVE-WK-0320', 'BTC-MOVE-WK-0327', 'BTC-MOVE-WK-0403', 'BTC-MOVE-WK-0410', 'BTC-MOVE-WK-0417', 'BTC-MOVE-WK-0424', 'BTC-MOVE-WK-0501', 'BTC-MOVE-WK-0508', 'BTC-MOVE-WK-0515', 'BTC-PERP', 'BTMX-0327', 'BTMX-0626', 'BTMX-PERP', 'DOGE-0327', 'DOGE-0626', 'DOGE-PERP', 'DRGN-0327', 'DRGN-0626', 'DRGN-PERP', 'EOS-0327', 'EOS-0626', 'EOS-PERP', 'ETC-0327', 'ETC-0626', 'ETC-PERP', 'ETH-0327', 'ETH-0626', 'ETH-PERP', 'EXCH-0327', 'EXCH-0626', 'EXCH-PERP', 'HT-0327', 'HT-0626', 'HT-PERP', 'LEO-0327', 'LEO-0626', 'LEO-PERP', 'LINK-0327', 'LINK-0626', 'LINK-PERP', 'LTC-0327', 'LTC-0626', 'LTC-PERP', 'MATIC-0327', 'MATIC-0626', 'MATIC-PERP', 'MID-0327', 'MID-0626', 'MID-PERP', 'OKB-0327', 'OKB-0626', 'OKB-PERP', 'PAXG-0327', 'PAXG-0626', 'PAXG-PERP', 'PETE', 'PRIV-0327', 'PRIV-0626', 'PRIV-PERP', 'SHIT-0327', 'SHIT-0626', 'SHIT-PERP', 'TOMO-0327', 'TOMO-0626', 'TOMO-PERP', 'TRUMP', 'TRX-0327', 'TRX-0626', 'TRX-PERP', 'TRYB-0327', 'TRYB-0626', 'TRYB-PERP', 'USDT-0327', 'USDT-0626', 'USDT-PERP', 'WARREN', 'XAUT-0327', 'XAUT-0626', 'XAUT-PERP', 'XRP-0327', 'XRP-0626', 'XRP-PERP', 'XTZ-0327', 'XTZ-0626', 'XTZ-PERP'

### Data Sanity
No downtime.

### API Reference
`GET https://ftx.com/api/markets/{market_name}/orderbook?depth={depth}`

### API Query Parameters
Name | Type | Value | Description
-----| --------| ----------| --------- |
market_name	|string|	BTC-0628	|Required. Name of the market.
depth	|number|	35	|max 100, default 20

### API Response Schema
Name | Type | Value | Description
---- | ---- | ----- | -----------
asks|	array	|[4114.25, 6.263]	|Array with price and size
bids|	array	|[4112, 49.29]	|Array with price and size



## FTX Trades 
```sql
-- fetch data
select * from FTX_trades limit 1 
```
> response

```json
[
    {
          'time': '2019-03-05T12:26:49.486594048Z', 
          'id': 4, 
          'liquidation': False, 
          'price': 127.77, 
          'side': 'sell', 
          'size': 0.04, 
          'symbol': 'ETH-PERP', 
          'trade_time': None
   }
]
```

### Description
[FTX trade](https://docs.ftx.com/#get-trades) has a frequency of 10 minutes and data time range is from 2019-03-05 12:26:49.486594048 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
id          |integer|
liquidation |boolean|
price       |float|
side        |string|
size        |float|
trade_time  |string|
symbol | string | tag values

### Tag Values
**Symbol (Symbols are subject to change)**: 
'ADA-0327', 'ADA-0626', 'ADA-1227', 'ADA-PERP', 'ADABEAR/USD', 'ADABULL/USD', 'ADADOOM/USD', 'ADAHEDGE/USD', 'ADAMOON/USD', 'ALGO-0327', 'ALGO-0626', 'ALGO-0927', 'ALGO-1227', 'ALGO-PERP', 'ALGOBEAR/USD', 'ALGOBULL/USD', 'ALGODOOM/USD', 'ALGOHALF/USD', 'ALGOHALF/USDT', 'ALGOHEDGE/USD', 'ALT-0327', 'ALT-0626', 'ALT-0927', 'ALT-1227', 'ALT-PERP', 'ALTBEAR/USD', 'ALTBULL/USD', 'ALTDOOM/USD', 'ALTHEDGE/USD', 'ALTMOON/USD', 'ATOM-0327', 'ATOM-0626', 'ATOM-1227', 'ATOM-PERP', 'ATOMBEAR/USD', 'ATOMBULL/USD', 'ATOMDOOM/USD', 'ATOMHEDGE/USD', 'ATOMMOON/USD', 'BCH-0327', 'BCH-0626', 'BCH-0927', 'BCH-1227', 'BCH-PERP', 'BCH/USD', 'BCH/USDT', 'BCHBEAR/USD', 'BCHBEAR/USDT', 'BCHBULL/USD', 'BCHBULL/USDT', 'BCHDOOM/USD', 'BCHHEDGE/USD', 'BCHMOON/USD', 'BEAR/USD', 'BEAR/USDT', 'BEARSHIT/USD', 'BERNIE', 'BIDEN', 'BLOOMBERG', 'BNB-0327', 'BNB-0626', 'BNB-0927', 'BNB-1227', 'BNB-PERP', 'BNB/USD', 'BNB/USDT', 'BNBBEAR/USD', 'BNBBEAR/USDT', 'BNBBULL/USD', 'BNBBULL/USDT', 'BNBDOOM/USD', 'BNBHEDGE/USD', 'BNBMOON/USD', 'BSV-0327', 'BSV-0626', 'BSV-0927', 'BSV-1227', 'BSV-PERP', 'BSVBEAR/USD', 'BSVBEAR/USDT', 'BSVBULL/USD', 'BSVBULL/USDT', 'BSVDOOM/USD', 'BSVHEDGE/USD', 'BSVMOON/USD', 'BTC-0327', 'BTC-0626', 'BTC-0925', 'BTC-0927', 'BTC-1227', 'BTC-MOVE-0101', 'BTC-MOVE-0102', 'BTC-MOVE-0103', 'BTC-MOVE-0104', 'BTC-MOVE-0105', 'BTC-MOVE-0106', 'BTC-MOVE-0107', 'BTC-MOVE-0108', 'BTC-MOVE-0109', 'BTC-MOVE-0110', 'BTC-MOVE-0111', 'BTC-MOVE-0112', 'BTC-MOVE-0113', 'BTC-MOVE-0114', 'BTC-MOVE-0115', 'BTC-MOVE-0116', 'BTC-MOVE-0117', 'BTC-MOVE-0118', 'BTC-MOVE-0119', 'BTC-MOVE-0120', 'BTC-MOVE-0121', 'BTC-MOVE-0122', 'BTC-MOVE-0123', 'BTC-MOVE-0124', 'BTC-MOVE-0125', 'BTC-MOVE-0126', 'BTC-MOVE-0127', 'BTC-MOVE-0128', 'BTC-MOVE-0129', 'BTC-MOVE-0130', 'BTC-MOVE-0131', 'BTC-MOVE-0201', 'BTC-MOVE-0202', 'BTC-MOVE-0203', 'BTC-MOVE-0204', 'BTC-MOVE-0205', 'BTC-MOVE-0206', 'BTC-MOVE-0207', 'BTC-MOVE-0208', 'BTC-MOVE-0209', 'BTC-MOVE-0210', 'BTC-MOVE-0211', 'BTC-MOVE-0212', 'BTC-MOVE-0213', 'BTC-MOVE-0214', 'BTC-MOVE-0215', 'BTC-MOVE-0216', 'BTC-MOVE-0217', 'BTC-MOVE-0218', 'BTC-MOVE-0219', 'BTC-MOVE-0220', 'BTC-MOVE-0221', 'BTC-MOVE-0222', 'BTC-MOVE-0223', 'BTC-MOVE-0224', 'BTC-MOVE-0225', 'BTC-MOVE-0226', 'BTC-MOVE-0227', 'BTC-MOVE-0228', 'BTC-MOVE-0229', 'BTC-MOVE-0301', 'BTC-MOVE-0302', 'BTC-MOVE-0303', 'BTC-MOVE-0304', 'BTC-MOVE-0305', 'BTC-MOVE-0306', 'BTC-MOVE-0307', 'BTC-MOVE-0308', 'BTC-MOVE-0309', 'BTC-MOVE-0310', 'BTC-MOVE-0311', 'BTC-MOVE-0312', 'BTC-MOVE-0313', 'BTC-MOVE-0314', 'BTC-MOVE-0315', 'BTC-MOVE-0316', 'BTC-MOVE-0317', 'BTC-MOVE-0318', 'BTC-MOVE-0319', 'BTC-MOVE-0320', 'BTC-MOVE-0321', 'BTC-MOVE-0322', 'BTC-MOVE-0323', 'BTC-MOVE-0324', 'BTC-MOVE-0325', 'BTC-MOVE-0326', 'BTC-MOVE-0327', 'BTC-MOVE-0328', 'BTC-MOVE-0329', 'BTC-MOVE-0330', 'BTC-MOVE-0331', 'BTC-MOVE-0401', 'BTC-MOVE-0402', 'BTC-MOVE-0403', 'BTC-MOVE-0404', 'BTC-MOVE-0405', 'BTC-MOVE-0406', 'BTC-MOVE-0407', 'BTC-MOVE-0408', 'BTC-MOVE-0409', 'BTC-MOVE-0410', 'BTC-MOVE-0411', 'BTC-MOVE-0415', 'BTC-MOVE-0416', 'BTC-MOVE-0417', 'BTC-MOVE-0418', 'BTC-MOVE-0420', 'BTC-MOVE-0421', 'BTC-MOVE-0422', 'BTC-MOVE-0925', 'BTC-MOVE-0926', 'BTC-MOVE-0927', 'BTC-MOVE-0928', 'BTC-MOVE-0929', 'BTC-MOVE-0930', 'BTC-MOVE-1001', 'BTC-MOVE-1002', 'BTC-MOVE-1003', 'BTC-MOVE-1004', 'BTC-MOVE-1005', 'BTC-MOVE-1006', 'BTC-MOVE-1007', 'BTC-MOVE-1008', 'BTC-MOVE-1009', 'BTC-MOVE-1010', 'BTC-MOVE-1011', 'BTC-MOVE-1012', 'BTC-MOVE-1013', 'BTC-MOVE-1014', 'BTC-MOVE-1015', 'BTC-MOVE-1016', 'BTC-MOVE-1017', 'BTC-MOVE-1018', 'BTC-MOVE-1019', 'BTC-MOVE-1020', 'BTC-MOVE-1121', 'BTC-MOVE-1122', 'BTC-MOVE-1123', 'BTC-MOVE-1124', 'BTC-MOVE-1125', 'BTC-MOVE-1126', 'BTC-MOVE-1127', 'BTC-MOVE-1128', 'BTC-MOVE-1129', 'BTC-MOVE-1130', 'BTC-MOVE-1201', 'BTC-MOVE-1202', 'BTC-MOVE-1203', 'BTC-MOVE-1204', 'BTC-MOVE-1205', 'BTC-MOVE-1206', 'BTC-MOVE-1207', 'BTC-MOVE-1208', 'BTC-MOVE-1209', 'BTC-MOVE-1210', 'BTC-MOVE-1211', 'BTC-MOVE-1212', 'BTC-MOVE-1213', 'BTC-MOVE-1214', 'BTC-MOVE-1215', 'BTC-MOVE-1216', 'BTC-MOVE-1217', 'BTC-MOVE-1218', 'BTC-MOVE-1219', 'BTC-MOVE-1220', 'BTC-MOVE-1221', 'BTC-MOVE-1222', 'BTC-MOVE-1223', 'BTC-MOVE-1224', 'BTC-MOVE-1225', 'BTC-MOVE-1226', 'BTC-MOVE-1227', 'BTC-MOVE-1228', 'BTC-MOVE-1229', 'BTC-MOVE-1230', 'BTC-MOVE-1231', 'BTC-MOVE-2019Q4', 'BTC-MOVE-2020Q1', 'BTC-MOVE-2020Q2', 'BTC-MOVE-2020Q3', 'BTC-MOVE-2020Q4', 'BTC-MOVE-WK-0103', 'BTC-MOVE-WK-0110', 'BTC-MOVE-WK-0117', 'BTC-MOVE-WK-0124', 'BTC-MOVE-WK-0131', 'BTC-MOVE-WK-0207', 'BTC-MOVE-WK-0214', 'BTC-MOVE-WK-0221', 'BTC-MOVE-WK-0228', 'BTC-MOVE-WK-0306', 'BTC-MOVE-WK-0313', 'BTC-MOVE-WK-0320', 'BTC-MOVE-WK-0327', 'BTC-MOVE-WK-0403', 'BTC-MOVE-WK-0410', 'BTC-MOVE-WK-0417', 'BTC-MOVE-WK-0424', 'BTC-MOVE-WK-0501', 'BTC-MOVE-WK-0508', 'BTC-MOVE-WK-0515', 'BTC-MOVE-WK-1122', 'BTC-MOVE-WK-1129', 'BTC-MOVE-WK-1206', 'BTC-MOVE-WK-1213', 'BTC-MOVE-WK-1220', 'BTC-MOVE-WK-1227', 'BTC-PERP', 'BTC/USD', 'BTC/USDT', 'BTMX-0327', 'BTMX-0626', 'BTMX-1227', 'BTMX-PERP', 'BTMX/USD', 'BTMXBEAR/USD', 'BTMXBEAR/USDT', 'BTMXBULL/USD', 'BTMXBULL/USDT', 'BTMXDOOM/USD', 'BTMXHALF/USD', 'BTMXHEDGE/USD', 'BTMXMOON/USD', 'BULL/USD', 'BULL/USDT', 'BULLSHIT/USD', 'DOGE-0327', 'DOGE-0626', 'DOGE-1227', 'DOGE-PERP', 'DOGEBEAR/USD', 'DOGEBULL/USD', 'DOGEDOOM/USD', 'DOGEMOON/USD', 'DOOM/USD', 'DOOMSHIT/USD', 'DRGN-0327', 'DRGN-0626', 'DRGN-1227', 'DRGN-PERP', 'DRGNBEAR/USD', 'DRGNBULL/USD', 'DRGNDOOM/USD', 'DRGNHEDGE/USD', 'DRGNMOON/USD', 'EOS-0327', 'EOS-0626', 'EOS-0927', 'EOS-1227', 'EOS-PERP', 'EOSBEAR/USD', 'EOSBEAR/USDT', 'EOSBULL/USD', 'EOSBULL/USDT', 'EOSDOOM/USD', 'EOSHEDGE/USD', 'EOSMOON/USD', 'ETC-0327', 'ETC-0626', 'ETC-0927', 'ETC-1227', 'ETC-PERP', 'ETCBEAR/USD', 'ETCBULL/USD', 'ETCDOOM/USD', 'ETCHEDGE/USD', 'ETCMOON/USD', 'ETH-0327', 'ETH-0626', 'ETH-0927', 'ETH-1227', 'ETH-PERP', 'ETH/USD', 'ETH/USDT', 'ETHBEAR/USD', 'ETHBEAR/USDT', 'ETHBULL/USD', 'ETHBULL/USDT', 'ETHDOOM/USD', 'ETHHEDGE/USD', 'ETHMOON/USD', 'EXCH-0327', 'EXCH-0626', 'EXCH-0927', 'EXCH-1227', 'EXCH-PERP', 'EXCHBEAR/USD', 'EXCHBULL/USD', 'EXCHDOOM/USD', 'EXCHHEDGE/USD', 'EXCHMOON/USD', 'FTT/BTC', 'FTT/USD', 'FTT/USDT', 'HALF/USD', 'HEDGE/USD', 'HEDGESHIT/USD', 'HT-0327', 'HT-0626', 'HT-0927', 'HT-1227', 'HT-PERP', 'HTBEAR/USD', 'HTBULL/USD', 'HTDOOM/USD', 'HTHEDGE/USD', 'HTMOON/USD', 'LEO-0327', 'LEO-0626', 'LEO-0927', 'LEO-1227', 'LEO-PERP', 'LEOBEAR/USD', 'LEOBULL/USD', 'LEODOOM/USD', 'LEOHEDGE/USD', 'LEOMOON/USD', 'LINK-0327', 'LINK-0626', 'LINK-1227', 'LINK-PERP', 'LINKBEAR/USD', 'LINKBEAR/USDT', 'LINKBULL/USD', 'LINKBULL/USDT', 'LINKDOOM/USD', 'LINKHALF/USD', 'LINKHEDGE/USD', 'LINKMOON/USD', 'LTC-0327', 'LTC-0626', 'LTC-0927', 'LTC-1227', 'LTC-PERP', 'LTC/USD', 'LTC/USDT', 'LTCBEAR/USD', 'LTCBEAR/USDT', 'LTCBULL/USD', 'LTCBULL/USDT', 'LTCDOOM/USD', 'LTCHEDGE/USD', 'LTCMOON/USD', 'MATIC-0327', 'MATIC-0626', 'MATIC-1227', 'MATIC-PERP', 'MATICBEAR/USD', 'MATICBULL/USD', 'MATICDOOM/USD', 'MATICHEDGE/USD', 'MATICMOON/USD', 'MID-0327', 'MID-0626', 'MID-0927', 'MID-1227', 'MID-PERP', 'MIDBEAR/USD', 'MIDBULL/USD', 'MIDDOOM/USD', 'MIDHEDGE/USD', 'MIDMOON/USD', 'MOON/USD', 'MOONSHIT/USD', 'OKB-0327', 'OKB-0626', 'OKB-0927', 'OKB-1227', 'OKB-PERP', 'OKBBEAR/USD', 'OKBBULL/USD', 'OKBDOOM/USD', 'OKBHEDGE/USD', 'OKBMOON/USD', 'PAXG-0327', 'PAXG-0626', 'PAXG-PERP', 'PAXG/USD', 'PAXG/USDT', 'PAXGBEAR/USD', 'PAXGBULL/USD', 'PAXGHEDGE/USD', 'PETE', 'PRIV-0327', 'PRIV-0626', 'PRIV-PERP', 'PRIVBEAR/USD', 'PRIVBULL/USD', 'PRIVHEDGE/USD', 'SHIT-0327', 'SHIT-0626', 'SHIT-0927', 'SHIT-1227', 'SHIT-PERP', 'TOMO-0327', 'TOMO-0626', 'TOMO-1227', 'TOMO-PERP', 'TOMOBEAR/USD', 'TOMOBULL/USD', 'TOMODOOM/USD', 'TOMOHEDGE/USD', 'TOMOMOON/USD', 'TRUMP', 'TRX-0327', 'TRX-0626', 'TRX-0927', 'TRX-1227', 'TRX-PERP', 'TRXBEAR/USD', 'TRXBULL/USD', 'TRXDOOM/USD', 'TRXHEDGE/USD', 'TRXMOON/USD', 'TRYB-0327', 'TRYB-0626', 'TRYB-1227', 'TRYB-PERP', 'TRYB/USD', 'TRYBBEAR/USD', 'TRYBBULL/USD', 'TRYBHEDGE/USD', 'USDT-0327', 'USDT-0626', 'USDT-0927', 'USDT-1227', 'USDT-PERP', 'USDT/USD', 'USDTBEAR/USD', 'USDTBULL/USD', 'USDTDOOM/USD', 'USDTHEDGE/USD', 'USDTMOON/USD', 'WARREN', 'XAUT-0327', 'XAUT-0626', 'XAUT-PERP', 'XAUT/USD', 'XAUT/USDT', 'XAUTBEAR/USD', 'XAUTBULL/USD', 'XRP-0327', 'XRP-0626', 'XRP-0927', 'XRP-1227', 'XRP-PERP', 'XRPBEAR/USD', 'XRPBEAR/USDT', 'XRPBULL/USD', 'XRPBULL/USDT', 'XRPDOOM/USD', 'XRPHEDGE/USD', 'XRPMOON/USD', 'XTZ-0327', 'XTZ-0626', 'XTZ-1227', 'XTZ-PERP', 'XTZBEAR/USD', 'XTZBEAR/USDT', 'XTZBULL/USD', 'XTZBULL/USDT', 'XTZDOOM/USD', 'XTZHEDGE/USD', 'XTZMOON/USD'

### Data Sanity
No downtime.

### API Reference
`GET https://ftx.com/api/markets/{market_name}/trades?limit={limit}&start_time={start_time}&end_time={end_time}`

### API Query Parameters
Name | Type | Value | Description
-----| --------| ----------| --------- |
market_name	|string	|BTC-0628	|name of the market
limit	|number|	35|	optional, max 100, default 20
start_time	|number|	1559881511	|optional
end_time	|number|	1559881711 |	optional

### API Response Schema
Name | Type | Value | Description
---- | ---- | ----- | -----------
id	|number|	3855995|	trade id
liquidation	|boolean	|false	|if this trade involved a liquidation order
price	|number	|3857.75|	
side	|string	|buy	
size	|number	|0.111	
time	|string	|2019-03-20T18:16:23.397991+00:00


## FTX Trades Option
```sql
-- fetch data
select * from FTX_trades_option limit 1 
```
> response

```json
[
    {
          'time': '2020-01-13T16:31:07.307401984Z', 
          'id': 1068, 
          'option_exipry': '2020-01-14T03:00:00+00:00', 
          'option_type': 'put', 
          'price': 4.4569, 
          'size': 0.1, 
          'strike_price': 7900, 
          'underlying': 'BTC'
   }
]
```

### Description
[FTX trade options](https://ftx.com/options) has a frequency of 1 second and data time range is from 2020-01-13 16:31:07.307401984 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
id            integer
option_exipry string
option_type   string
price         float
size          float
strike_price  float
underlying    string

### Data Sanity
No downtime.

### API Reference
`GET https://ftx.com/api/options/trades`

### API Query Parameters
Not required.

### API Response Schema
No information.




# Gateio
[Gateio](https://www.gate.io/) is a crypto currency exchange. Check their [api](https://www.gate.io/api2). 

## Gateio Orderbook
```sql
-- fetch data
select * from gateio_orderbook limit 1 
```
> response

```json
[
    {
          'time': '2020-02-28T20:32:20.344462492Z', 
          'price': 1.3333, 
          'size': 692.98, 
          'snapshot': '2020-02-28 20:32:19.602171', 
          'symbol': 'hns_usdt', 
          'type': 'ask'
   }
]
```

### Description
[Gateio trades](https://www.gate.io/api2#depth) has a frequency of 30 seconds and data time range is from 2020-02-28T20:32:20.344462492Z till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
price    |float|
size     |float|
snapshot |string|
type     |string|
symbol | string | tag values

### Tag Values
**symbol**: hns_usdt, hns_btc

### Data Sanity
No downtime.

### API Reference
`GET https://data.gateio.life/api2/1/orderBook/[CURR_A]_[CURR_B]`

### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
market	|String|	Yes	| Get makret list

### API Response Schema
No information.


## Gateio Trades
```sql
-- fetch data
select * from gateio_trades limit 1 
```
> response

```json
[
    {
         'time': '2020-02-19T04:31:03.000003072Z', 
         'amount': 176.77, 
         'price': 3e-05, 
         'symbol': 'hns_btc', 
         'timestamp': 1582086663, 
         'total': 0.0053031, 
         'tradeID': 228611456, 
         'type': 'sell'
   }
]
```

### Description
[Gateio trades](https://www.gate.io/api2#history) has a frequency of 1 hour and data time range is from 2020-02-19T04:31:03.000003072Z till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
amount    |float|
price     |float|
timestamp |integer|
total     |float|
tradeID   |integer|
type      |string|
symbol | string | tag values

### Tag Values
**symbol**: hns_usdt, hns_btc

### Data Sanity
No downtime.

### API Reference
`GET https://data.gateio.life/api2/1/tradeHistory/[CURR_A]_[CURR_B]`

### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
market	|String|	Yes	| Get makret list

### API Response Schema
No information.


# HuobiDM
[Huobi Derivative Makret](https://www.hbdm.com/) is a cryptocurrency exchange that has all derivatives. Check their [api](https://docs.huobigroup.com/docs/dm/v1/en/#introduction).

## Huobidm Contract Delivery Price
```sql
-- fetch data
select * from huobidm_contract_delivery_price limit 1 
```
> response

```json
[
    {
        'time': '2020-01-29T00:14:35.339000064Z', 
        'delivery_price': 8307.7331803005, 
        'symbol': 'BTC'
   }
]
```

### Description
[Huobidm contract delivery price](https://docs.huobigroup.com/docs/dm/v1/en/#get-the-estimated-delivery-price) has a frequency of 1 minute and data time range is from 2020-01-29 00:14:35.339000064 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
delivery_price |float|
symbol | string | tag values

### Tag Values
**symbol**: 
'BCH', 'BSV', 'BTC', 'EOS', 'ETC', 'ETH', 'LTC', 'TRX', 'XRP'

### Data Sanity
No downtime.

### API Reference
`GET https://api.hbdm.com/api/v1/contract_delivery_price?symbol={symbol}`

### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
symbol	|string	|true	|Case-Insenstive.Both uppercase and lowercase are supported.e.g."BTC","ETH"...

### API Response Schema
Name | Type | Description
---- | ---- | ----------
status	|string	|Request Processing Result
delivery_price |	string	|estimated delivery price	
ts |long	|Time of Respond Generation, Unit: Millisecond



## Huobidm Contract Market Overview
```sql
-- fetch data
select * from huobidm_contract_market_overview limit 1 
```
> response

```json
[
    {
        'time': '2020-01-29T00:51:08.304Z', 
        'amount': '8579307.0972995652712865674097690524479882706', 
        'ask_amt': '270', 
        'ask_price': '11.668', 
        'bid_amt': '55', 
        'bid_price': '11.657', 
        'close': '11.657', 
        'contract_type': 'ETC_CW', 
        'count': 46701, 
        'high': '11.817', 
        'id': 1580259068, 
        'low': '10.8', 
        'open': '10.951', 
        'vol': '9525756'
   }
]
```

### Description
[Huobidm contract market overview](https://docs.huobigroup.com/docs/dm/v1/en/#get-the-estimated-delivery-price) has a frequency of 1 minute and data time range is from 2020-01-29 00:51:08.304 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
amount    |string|
ask_amt   |string|
ask_price |string|
bid_amt   |string|
bid_price |string|
close     |string|
count     |integer|
high      |string|
id        |integer|
low       |string|
open      |string|
vol       |string|
contract_type | string | tag values

### Tag Values
**Symbol (Symbols are subject to change)**: 
'BCH200131', 'BCH200207', 'BCH200214', 'BCH200221', 'BCH200228', 'BCH200306', 'BCH200313', 'BCH200320', 'BCH200327', 'BCH200403', 'BCH200410', 'BCH200417', 'BCH200424', 'BCH200501', 'BCH200626', 'BCH_CQ', 'BCH_CW', 'BCH_NW', 'BSV200131', 'BSV200207', 'BSV200214', 'BSV200221', 'BSV200228', 'BSV200306', 'BSV200313', 'BSV200320', 'BSV200327', 'BSV200403', 'BSV200410', 'BSV200417', 'BSV200424', 'BSV200501', 'BSV200626', 'BSV_CQ', 'BSV_CW', 'BSV_NW', 'BTC200131', 'BTC200207', 'BTC200214', 'BTC200221', 'BTC200228', 'BTC200306', 'BTC200313', 'BTC200320', 'BTC200327', 'BTC200403', 'BTC200410', 'BTC200417', 'BTC200424', 'BTC200501', 'BTC200626', 'BTC_CQ', 'BTC_CW', 'BTC_NW', 'EOS200131', 'EOS200207', 'EOS200214', 'EOS200221', 'EOS200228', 'EOS200306', 'EOS200313', 'EOS200320', 'EOS200327', 'EOS200403', 'EOS200410', 'EOS200417', 'EOS200424', 'EOS200501', 'EOS200626', 'EOS_CQ', 'EOS_CW', 'EOS_NW', 'ETC200131', 'ETC200207', 'ETC200214', 'ETC200221', 'ETC200228', 'ETC200306', 'ETC200313', 'ETC200320', 'ETC200327', 'ETC200403', 'ETC200410', 'ETC200417', 'ETC200424', 'ETC200501', 'ETC200626', 'ETC_CQ', 'ETC_CW', 'ETC_NW', 'ETH200131', 'ETH200207', 'ETH200214', 'ETH200221', 'ETH200228', 'ETH200306', 'ETH200313', 'ETH200320', 'ETH200327', 'ETH200403', 'ETH200410', 'ETH200417', 'ETH200424', 'ETH200501', 'ETH200626', 'ETH_CQ', 'ETH_CW', 'ETH_NW', 'LTC200131', 'LTC200207', 'LTC200214', 'LTC200221', 'LTC200228', 'LTC200306', 'LTC200313', 'LTC200320', 'LTC200327', 'LTC200403', 'LTC200410', 'LTC200417', 'LTC200424', 'LTC200501', 'LTC200626', 'LTC_CQ', 'LTC_CW', 'LTC_NW', 'TRX200131', 'TRX200207', 'TRX200214', 'TRX200221', 'TRX200228', 'TRX200306', 'TRX200313', 'TRX200320', 'TRX200327', 'TRX200403', 'TRX200410', 'TRX200417', 'TRX200424', 'TRX200501', 'TRX200626', 'TRX_CQ', 'TRX_CW', 'TRX_NW', 'XRP200131', 'XRP200207', 'XRP200214', 'XRP200221', 'XRP200228', 'XRP200306', 'XRP200313', 'XRP200320', 'XRP200327', 'XRP200403', 'XRP200410', 'XRP200417', 'XRP200424', 'XRP200501', 'XRP200626', 'XRP_CQ', 'XRP_CW', 'XRP_NW'

### Data Sanity
No downtime.

### API Reference
`GET https://api.hbdm.com/market/detail/merged?symbol={contract_type}`

### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
contract_type	|string	|true	|Case-Insenstive.Both uppercase and lowercase are supported.

### API Response Schema
Name | Type | Description
---- | ---- | ----------
status	|string	|Request Processing Result
tick |	string	|estimated delivery price	
ts |long	|Time of Respond Generation, Unit: Millisecond


## Huobidm Contract Price Limit 
```sql
-- fetch data
select * from huobidm_contract_price_limit limit 1 
```
> response

```json
[
    {
        'time': '1970-01-01T00:26:20.256885167Z', 
        'contract_code': 'BTC200131', 
        'contract_type': 'this_week',
        'high_limit': 9761.84,
        'low_limit': 9039.79, 
        'symbol': 'BTC'
   }
]
```

### Description
[Huobidm contract price limit](https://docs.huobigroup.com/docs/dm/v1/en/#contract-price-limitation) has a frequency of 1 minute and data time range is from 2020-01-29 00:51:08.304 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
contract_code |string|
high_limit    |float|
low_limit     |float|
contract_type | string |
symbol | string|

### Tag Values
**Contract Type**: 
this_week, next_week, quarter

**Symbol**:
'BCH', 'BSV', 'BTC', 'EOS', 'ETC', 'ETH', 'LTC', 'TRX', 'XRP'

### Data Sanity
No downtime.

### API Reference
`GET https://api.hbdm.com/api/v1/contract_price_limit?symbol={symbol}&contract_type={contract_type}`

### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
contract_type	|string	|true	|Case-Insenstive.Both uppercase and lowercase are supported.
symbol | string | true | Symbol name

### API Response Schema
Name | Type | Description
---- | ---- | ----------
status	|string	|Request Processing Result
symbol	|	string|	Variety code	"BTC","ETH" ...
high_limit|	decimal|	Highest Buying Price	
low_limit|	decimal|	Lowest Selling Price	
contract_code	|string|	Contract Code	eg "BTC180914" ...
contract_type	|string|	Contract Type	"this_week","next_week","quarter"
ts |long	|Time of Respond Generation, Unit: Millisecond


## Huobidm Contract Risk Info
```sql
-- fetch data
select * from huobidm_contract_risk_info limit 1 
```
> response

```json
[
    {
        'time': '2020-01-29T00:14:37.136Z',
        'estimated_clawback': 0, 
        'insurance_fund': 870.6348136893932, 
        'symbol': 'BTC'
   }
]
```

### Description
[Huobidm contract risk info](https://docs.huobigroup.com/docs/dm/v1/en/#query-information-on-contract-insurance-fund-balance-and-estimated-clawback-rate) has a frequency of 1 minute and data time range is from 2020-01-29 00:51:08.304 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
estimated_clawback |float|
insurance_fund     |float|
symbol | string|

### Tag Values
**Symbol**:
'BCH', 'BSV', 'BTC', 'EOS', 'ETC', 'ETH', 'LTC', 'TRX', 'XRP'

### Data Sanity
No downtime.

### API Reference
`GET https://api.hbdm.com/api/v1/contract_risk_info?symbol={symbol}`

### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
symbol | string | true | Symbol name

### API Response Schema
Name | Type | Description
---- | ---- | ----------
status	|string	|Request Processing Result
symbol | string | symbol name
insurance_fund |	float	| insurance fund balance
estimated_clawback | float | estimated clawback rate
ts |long	|Time of Respond Generation, Unit: Millisecond



## Huobidm Index Price 
```sql
-- fetch data
select * from huobidm_index_price limit 1 
```
> response

```json
[
    {
        'time': '2020-01-28T18:41:00.028999936Z', 
        'index_price': 285.84063562725, 
        'index_ts': 1580236860029, 
        'symbol': 'BSV'
   }
]
```

### Description
[Huobidm index price](https://docs.huobigroup.com/docs/dm/v1/en/#get-contract-index-price-information) has a frequency of 1 minute and data time range is from 2020-01-29 00:51:08.304 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
index_price |float|
index_ts    |integer|
symbol | string | Tag values
 
### Tag Values
**Symbol**: 
'BCH', 'BSV', 'BTC', 'EOS', 'ETC', 'ETH', 'LTC', 'TRX', 'XRP'

### Data Sanity
No downtime.

### API Reference
`GET https://api.hbdm.com/api/v1/contract_index?symbol={symmbol}`

### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
symbol |string	|true	| Symbol name.

### API Response Schema
Name | Type | Description
---- | ---- | ----------
status	|string	|Request Processing Result
symbol | string | symbol name
index_price |	float	| index price	
ts |long	|Time of Respond Generation, Unit: Millisecond


## Huobidm Insurance Fund
```sql
-- fetch data
select * from huobidm_insurance_fund limit 1 
```
> response

```json
[
    {
        'time': '2018-11-10T08:00:00Z', 
        'insurance_fund': 0, 
        'symbol': 'BTC'
   }
]
```

### Description
[Huobidm insurance fund](https://docs.huobigroup.com/docs/dm/v1/en/#query-history-records-of-insurance-fund-balance) has a frequency of 1 day and data time range is from 2018-11-10 08:00:00 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
index_price |float|
index_ts    |integer|
symbol | string | Tag values
 
### Tag Values
**Symbol**: 
'BCH', 'BSV', 'BTC', 'EOS', 'ETC', 'ETH', 'LTC', 'TRX', 'XRP'

### Data Sanity
No downtime.

### API Reference
`GET https://api.hbdm.com/api/v1/contract_insurance_fund?symbol={symmbol}`

### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
symbol |string	|true	| Symbol name.

### API Response Schema
Name | Type | Description
---- | ---- | ----------
status	|string	|Request Processing Result
symbol | string | symbol name
insurance_fund |	float	| insurance fund
ts |long	|Time of Respond Generation, Unit: Millisecond


## Huobidm Open Interest 
```sql
-- fetch data
select * from huobidm_open_interest limit 1 
```
> response

```json
[
    {
        'time': '2020-01-23T23:29:17.432110597Z', 
        'amount': 279899.30625102425, 
        'contract_code': 'LTC200327', 
        'contract_type': 'quarter', 
        'symbol': 'LTC', 
        'ts': 1579822034204, 
        'volume': 1537179
   }
]
```

### Description
[Huobidm open interest](https://docs.huobigroup.com/docs/dm/v1/en/#query-information-on-open-interest) has a frequency of 1 minute and data time range is from 2020-01-23 23:29:17.432110597 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
amount        |float|
contract_code |string|
contract_type |string|
ts            |integer|
volume        |float|
symbol | string | Tag values
 
### Tag Values
**Symbol**: 
'BCH', 'BSV', 'BTC', 'EOS', 'ETC', 'ETH', 'LTC', 'TRX', 'XRP'

### Data Sanity
No downtime.

### API Reference
`GET https://api.hbdm.com/api/v1/contract_his_open_interest?symbol={symmbol}`

### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
symbol |string	|true	| Symbol name.

### API Response Schema
Name | Type | Description
---- | ---- | ----------
status	|string	|Request Processing Result
symbol | string | symbol name
volume|	float	| open interst
amount_type | string | open interest unit
ts |long	|Time of Respond Generation, Unit: Millisecond


## Huobidm Orderbook
```sql
-- fetch data
select * from huobidm_orderbook limit 1 
```
> response

```json
[
    {
        'time': '2020-02-25T00:47:54.152897372Z', 
        'contract_code': 'BTC200228', 
        'current_timestamp': 1582591673815, 
        'id': 48226038904, 
        'price': 9645.21, 
        'type': 'ask', 
        'vol': 275
   }
]
```

### Description
[Huobidm orderbook](https://docs.huobigroup.com/docs/dm/v1/en/#get-market-depth) has a frequency of 30 seconds and data time range is from 2020-01-23 23:29:17.432110597 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
current_timestamp |integer|
id                |integer|
price             |float|
type              |string|
vol               |float|
contract_code | string | Tag values
 
### Tag Values
**Contract_code (Contract_code are subject to change)**: 
'BCH-USD', 'BCH200228', 'BCH200306', 'BCH200313', 'BCH200320', 'BCH200327', 'BCH200403', 'BCH200410', 'BCH200417', 'BCH200424', 'BCH200501', 'BCH200626', 'BSV-USD', 'BSV200228', 'BSV200306', 'BSV200313', 'BSV200320', 'BSV200327', 'BSV200403', 'BSV200410', 'BSV200417', 'BSV200424', 'BSV200501', 'BSV200626', 'BTC-USD', 'BTC200228', 'BTC200306', 'BTC200313', 'BTC200320', 'BTC200327', 'BTC200403', 'BTC200410', 'BTC200417', 'BTC200424', 'BTC200501', 'BTC200626', 'EOS-USD', 'EOS200228', 'EOS200306', 'EOS200313', 'EOS200320', 'EOS200327', 'EOS200403', 'EOS200410', 'EOS200417', 'EOS200424', 'EOS200501', 'EOS200626', 'ETC-USD', 'ETC200228', 'ETC200306', 'ETC200313', 'ETC200320', 'ETC200327', 'ETC200403', 'ETC200410', 'ETC200417', 'ETC200424', 'ETC200501', 'ETC200626', 'ETH-USD', 'ETH200228', 'ETH200306', 'ETH200313', 'ETH200320', 'ETH200327', 'ETH200403', 'ETH200410', 'ETH200417', 'ETH200424', 'ETH200501', 'ETH200626', 'LINK-USD', 'LTC-USD', 'LTC200228', 'LTC200306', 'LTC200313', 'LTC200320', 'LTC200327', 'LTC200403', 'LTC200410', 'LTC200417', 'LTC200424', 'LTC200501', 'LTC200626', 'TRX-USD', 'TRX200228', 'TRX200306', 'TRX200313', 'TRX200320', 'TRX200327', 'TRX200403', 'TRX200410', 'TRX200417', 'TRX200424', 'TRX200501', 'TRX200626', 'XRP-USD', 'XRP200228', 'XRP200306', 'XRP200313', 'XRP200320', 'XRP200327', 'XRP200403', 'XRP200410', 'XRP200417', 'XRP200424', 'XRP200501', 'XRP200626'

### Data Sanity
No downtime.

### API Reference
`GET https://api.hbdm.com/market/depth?symbol={symbol}&type={step}`

### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
symbol	|string	|true|	Case-Senstive.Only uppercase is supported.e.g. "BTC_CW" represents BTC “This Week”，"BTC_NW" represents BTC “Next Week”，"BTC_CQ" represents BTC “Quarter”
type	|string	|true	|Get depth data within step 150, use step0, step1, step2, step3, step4, step5（merged depth data 0-5）；when step is 0，depth data will not be merged; Get depth data within step 20, use step6, step7, step8, step9, step10, step11(merged depth data 7-11); when step is 6, depth data will not be merged.

### API Response Schema
Name | Type | Description
---- | ---- | ----------
status	|string	|Request Processing Result
asks | list | symbol name
bids |	list	| open interst
amount_type | string | open interest unit
ts |long	|Time of Respond Generation, Unit: Millisecond




## Huobidm Trade
```sql
-- fetch data
select * from huobidm_trades limit 1 
```
> response

```json
[
    {
        'time': '2020-01-29T11:34:29.923000064Z', 
        'amount': 34, 
        'direction': 'sell', 
        'id': 424745151260000, 
        'price': 0.2393, 
        'symbol': 'XRP200207'
   }
]
```

### Description
[Huobidm trades](https://docs.huobigroup.com/docs/dm/v1/en/#the-last-trade-of-a-contract) has a frequency of 1 minute and data time range is from 2020-01-29 11:34:29.923000064 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
direction |string|
id        |integer|
price     |float|
symbol | string | Tag values
 
### Tag Values
**Symbol (Symbols are subject to change)**: 
'BCH-USD', 'BCH200131', 'BCH200207', 'BCH200214', 'BCH200221', 'BCH200228', 'BCH200306', 'BCH200313', 'BCH200320', 'BCH200327', 'BCH200403', 'BCH200410', 'BCH200417', 'BCH200424', 'BCH200501', 'BCH200626', 'BSV-USD', 'BSV200131', 'BSV200207', 'BSV200214', 'BSV200221', 'BSV200228', 'BSV200306', 'BSV200313', 'BSV200320', 'BSV200327', 'BSV200403', 'BSV200410', 'BSV200417', 'BSV200424', 'BSV200501', 'BSV200626', 'BTC-USD', 'BTC200131', 'BTC200207', 'BTC200214', 'BTC200221', 'BTC200228', 'BTC200306', 'BTC200313', 'BTC200320', 'BTC200327', 'BTC200403', 'BTC200410', 'BTC200417', 'BTC200424', 'BTC200501', 'BTC200626', 'EOS-USD', 'EOS200131', 'EOS200207', 'EOS200214', 'EOS200221', 'EOS200228', 'EOS200306', 'EOS200313', 'EOS200320', 'EOS200327', 'EOS200403', 'EOS200410', 'EOS200417', 'EOS200424', 'EOS200501', 'EOS200626', 'ETC-USD', 'ETC200131', 'ETC200207', 'ETC200214', 'ETC200221', 'ETC200228', 'ETC200306', 'ETC200313', 'ETC200320', 'ETC200327', 'ETC200403', 'ETC200410', 'ETC200417', 'ETC200424', 'ETC200501', 'ETC200626', 'ETH-USD', 'ETH200131', 'ETH200207', 'ETH200214', 'ETH200221', 'ETH200228', 'ETH200306', 'ETH200313', 'ETH200320', 'ETH200327', 'ETH200403', 'ETH200410', 'ETH200417', 'ETH200424', 'ETH200501', 'ETH200626', 'LINK-USD', 'LTC-USD', 'LTC200131', 'LTC200207', 'LTC200214', 'LTC200221', 'LTC200228', 'LTC200306', 'LTC200313', 'LTC200320', 'LTC200327', 'LTC200403', 'LTC200410', 'LTC200417', 'LTC200424', 'LTC200501', 'LTC200626', 'TRX-USD', 'TRX200131', 'TRX200207', 'TRX200214', 'TRX200221', 'TRX200228', 'TRX200306', 'TRX200313', 'TRX200320', 'TRX200327', 'TRX200403', 'TRX200410', 'TRX200417', 'TRX200424', 'TRX200501', 'TRX200626', 'XRP-USD', 'XRP200131', 'XRP200207', 'XRP200214', 'XRP200221', 'XRP200228', 'XRP200306', 'XRP200313', 'XRP200320', 'XRP200327', 'XRP200403', 'XRP200410', 'XRP200417', 'XRP200424', 'XRP200501', 'XRP200626'

### Data Sanity
No downtime.

### API Reference
`GET https://api.hbdm.com/market/trade?symbol={symbol}`

### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
symbol	|string	|true|	Case-Senstive.Only uppercase is supported.e.g. "BTC_CW" represents BTC “This Week”，"BTC_NW" represents BTC “Next 

### API Response Schema
Name | Type | Description
---- | ---- | ----------
status	|string	|Request Processing Result
tick | object| trade data
ts |long	|Time of Respond Generation, Unit: Millisecond




# MXC
[MXC exchange](https://www.mxc.com/) is a crypto currency. Check their [api](https://github.com/mxcdevelop/APIDoc/tree/master/api_doc_v1) 

## MXC Trades
```sql
-- fetch data
select * from mxc_trades limit 1 
```
> response

```json
[
    {
        'time': '2020-03-05T20:20:10.715612701Z', 
        'amount': 124.7, 
        'price': 0.39951, 
        'side': 'sell', 
        'symbol': 'HNS_USDT', 
        'trade_time': '2020-03-06 04:19:48.771'
   }
]
```

### Description
[MXC trades](https://github.com/mxcdevelop/APIDoc/tree/master/api_doc_v1#%E8%8E%B7%E5%8F%96%E5%8D%95%E4%B8%AA%E5%B8%81%E7%A7%8D%E6%88%90%E4%BA%A4%E8%AE%B0%E5%BD%95%E4%BF%A1%E6%81%AF) has a frequency of 5 minute and data time range is from 2020-03-05 20:20:10.715612701 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
amount     |float|
price      |float|
side       |string|
trade_time |string| data time
symbol | string | tag values

### Tag Values
**symbol**: HNS_USDT

### Data Sanity
No downtime.

### API Reference
`GET https://www.mxc.io/open/api/v1/data/history`

### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
market	|String|	Yes	| Get makret list

### API Response Schema
Name | Type | Description
---- | ---- | ----------
tradeTime	|Integer|	Transaction time
tradePrice	|float|	Transaction price
tradeQuantity	|float|	Transaction amount
tradeType	|String|	buy/sell


## MXC Orderbook
```sql
-- fetch data
select * from mxc_orderbook limit 1 
```
> response

```json
[
    {
       'time': '2020-03-05T19:57:35.660565377Z', 
       'amount': 15.03, 
       'current_timetamp': '2020-03-05 19:57:35.634187', 
       'price': 0.40517, 
       'symbol': 'HNS_USDT', 
       'type': 'asks'
   }
]
```

### Description
[MXC orderbook](https://github.com/mxcdevelop/APIDoc/tree/master/api_doc_v1#%E8%8E%B7%E5%8F%96%E6%B7%B1%E5%BA%A6%E4%BF%A1%E6%81%AF) has a frequency of 30 seconds and data time range is from 2020-03-05T19:57:35.660565377 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
amount           |float|
current_timetamp |string|
price            |float|
type             |string| asks/bids
symbol | string | tag values

### Tag Values
**symbol**: HNS_USDT

### Data Sanity
No downtime.

### API Reference
`GET https://www.mxc.io/open/api/v1/data/depth`

### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
market	|String|	Yes	| Get makret list
depth | string | Yes | Market depth

### API Response Schema
Name | Type | Description
---- | ---- | ----------
Price	|float|	Book price
Quantity	|float|	Book amount



# OKEX
[OKEX](https://www.okex.com/) is a cryptocurrency exchange. Check their [api](https://www.okex.com/docs/en/). 


## OKEX Funding Rate
```sql
-- fetch data
select * from okex_fundingRate limit 1 
```
> response

```json
[
    {
       'time': '2019-07-11T16:00:11.902586715Z', 
       'finding_time': '2019-07-11T20:00:00.000Z', 
       'funding_rate': '-0.00033', 
       'interest_rate': '0', 
       'symbol': 'BTC-USD-SWAP'
   }
]
```

### Description
[OKEX funding rate](https://www.okex.com/docs/en/#ws_swap-rate) is connected through websocket and data time range is from 2019-07-11T16:00:11.902586715Z till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
finding_time  |string|
funding_rate  |string|
interest_rate |string|
symbol | string | tag values

### Tag Values
**Swap Symbol (Symbols are subject to change)**: 
'BCH-USD-SWAP', 'BCH-USDT-SWAP', 'BSV-USD-SWAP', 'BSV-USDT-SWAP', 'BTC-USD-SWAP', 'BTC-USDT-SWAP', 'EOS-USD-SWAP', 'EOS-USDT-SWAP', 'ETC-USD-SWAP', 'ETC-USDT-SWAP', 'ETH-USD-SWAP', 'ETH-USDT-SWAP', 'LTC-USD-SWAP', 'LTC-USDT-SWAP', 'TRX-USD-SWAP', 'TRX-USDT-SWAP', 'XRP-USD-SWAP', 'XRP-USDT-SWAP'

### Data Sanity
No downtime.

### API Reference
**Endpoint**:
`Websocket wss://real.okex.com:8443/ws/v3`

**Payload**:
`{"op": "subscribe", "args":["swap/funding_rate:BTC-USD-SWAP"]}`

### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
symbol	|String|	Yes	| Symbol name

### API Response Schema
Name | Type | Description
---- | ---- | ----------
interest_rate	|String|	interest rate
instrument_id	|String|	Contract ID , eg: BTC-USD-SWAP,BTC-USDT-SWAP
funding_time	|String|	Current funding time
funding_rate	|String|	Current funding rate
estimated_rate	|String|	next estimated funding rate
settlement_time	|String|	settlement time


## OKEX Future Stats Contract Basis
```sql
-- fetch data
select * from okex_future_stats_contractBasis limit 1 
```
> response

```json
[
    {
       'time': '2017-05-04T04:00:00Z', 
       'basis': -1582.7099999999998, 
       'contract_index_price': 2954.99, 
       'contract_price': 1372.28, 
       'contract_type': 'next_week', 
       'frequency': '1440', 
       'symbol': 'BTC'
   }
]
```

### Description
[OKEX contract basis](https://www.okex.com/markets/swap-data/btc-usd) has frequencies of 1, 5, 60 and 1440 minutes and data time range is from 2017-05-04 04:00:00 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
basis                |float|
contract_index_price |float|
contract_price       |float|
frequency | string | tag values
symbol | string | tag values

### Tag Values
**Symbol (Symbols are subject to change)**: 
'BCH', 'BSV', 'BTC', 'EOS', 'ETC', 'ETH', 'LTC', 'TRX', 'XRP'

<aside class="notice">
All symbols are in USD, i.e. BCHUSD
</aside>

**Frequency**:
1, 5, 60, 1440

### Data Sanity
No downtime.

### API Reference

`GET https://www.okex.com/api/index/v3/instruments/{symbol}-USD/candles?granularity=300&size=1000`


### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
symbol	|String|	Yes	| Symbol name
granularity | long | Yes | 
size | long | Yes | data size

### API Response Schema
No information.



## OKEX Future Stats Taker Buy Sell
```sql
-- fetch data
select * from okex_future_stats_FutureTakerBuySell limit 1 
```
> response

```json
[
    {
       'time': '2019-11-25T16:00:00Z', 
       'buy_volume': 14337074, 
       'frequency': '24', 
       'sell_volume': 14785062, 
       'symbol': 'BCH', 
       'timestamps': 1574697600000
   }
]
```

### Description
[OKEX taker buy sell volume](https://www.okex.com/markets/swap-data/btc-usd) has frequencies of 5 minutes, 1 hour, and 24 hours  and data time range is from 2019-11-25 16:00:00 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
buy_volume  |integer|
sell_volume |integer|
timestamps  |integer| data timestamp
symbol | string | tag values

### Tag Values
**Symbol (Symbols are subject to change)**: 
'BCH', 'BSV', 'BTC', 'EOS', 'ETC', 'ETH', 'LTC', 'TRX', 'XRP'

<aside class="notice">
All symbols are in USD, i.e. BCHUSD
</aside>

**Frequency**:
5, 60, 24 

### Data Sanity
No downtime.

### API Reference

`GET https://www.okex.com/v3/futures/pc/market/takerTradeVolume/{symbol}?unitType=0`


### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
symbol	|String|	Yes	| Symbol name
unitType | int| Yes | data granuality

### API Response Schema
No information.


## OKEX Future Stats Long Short Ratio Position
```sql
-- fetch data
select * from okex_future_stats_longShortPositionRatio limit 1 
```
> response

```json
[
    {
       'time': '2019-07-10T16:00:00Z', 
       'frequency': '1440', 
       'ratios': 1.36, 
       'symbol': 'BTC'
   }
]
```

### Description
[OKEX long short ratio position](https://www.okex.com/markets/swap-data/btc-usd) has frequencies of 5 minutes, 1 hour and 1 day and data time range is from 2019-07-10 16:00:00 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
ratios   |float|
frequency | string | tag values
symbol | string | tag values

### Tag Values
**Symbol (Symbols are subject to change)**: 
'BCH', 'BSV', 'BTC', 'EOS', 'ETC', 'ETH', 'LTC', 'TRX', 'XRP'

<aside class="notice">
All symbols are in USD, i.e. BCHUSD
</aside>

**Frequency**:
5, 60, 24

### Data Sanity
No downtime.

### API Reference

`GET https://www.okex.com/v3/futures/pc/market/longShortPositionRatio/{}?currency={}&unitType=0`


### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
symbol	|String|	Yes	| Symbol name
unitType | int| Yes | data granuality

### API Response Schema
No information.



## OKEX Future Stats Open Interest Volume
```sql
-- fetch data
select * from okex_future_stats_OpenInterestVolume limit 1 
```
> response

```json
[
    {
       'time': '2019-03-02T16:00:00Z',
       'frequency': '24', 
       'open_interests': 442255, 
       'symbol': 'BCH', 
       'volumes': 2245545
   }
]
```

### Description
[OKEX open interest volume](https://www.okex.com/markets/swap-data/btc-usd) has frequencies of 5, 60 and 1440 minutes and data time range is from 2019-03-02 16:00:00 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
open_interests |integer|
volumes        |integer|
frequency | string | tag values
symbol | string | tag values

### Tag Values
**Symbol (Symbols are subject to change)**: 
'BCH', 'BSV', 'BTC', 'EOS', 'ETC', 'ETH', 'LTC', 'TRX', 'XRP'

<aside class="notice">
All symbols are in USD, i.e. BCHUSD
</aside>

**Frequency**:
5, 60, 1440

### Data Sanity
No downtime.

### API Reference

`GET https://www.okex.com/v3/futures/pc/market/openInterestAndVolume/{}?unitType=0`


### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
symbol	|String|	Yes	| Symbol name
unitType | int| Yes | data granuality

### API Response Schema
No information.


## OKEX Future Stats Swap Funding Rate
```sql
-- fetch data
select * from okex_future_stats_SwapFundingRate limit 1 
```
> response

```json
[
    'time': '2018-12-13T16:00:45Z', 
    'frequency': '24', 
    'funding_rate': 0.00125, 
    'symbol': 'BTC'
]
```

### Description
[OKEX swap funding rate](https://www.okex.com/markets/swap-data/btc-usd) has frequencies of 5 minutes, 1 hour and 1 day and data time range is from 2018-12-13 16:00:45 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
funding_rate |float|
frequency | string | tag values
symbol | string | tag values

### Tag Values
**Symbol (Symbols are subject to change)**: 
'BCH', 'BSV', 'BTC', 'EOS', 'ETC', 'ETH', 'LTC', 'TRX', 'XRP'

<aside class="notice">
All symbols are in USD, i.e. BCHUSD
</aside>

**Frequency**:
5, 60, 24

### Data Sanity
No downtime.

### API Reference

`GET https://www.okex.com/v2/perpetual/pc/public/calculate/fundingRate?contract={}&interval={}`


### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
contract	|String|	Yes	| Symbol name
interval | int| Yes | data granuality

### API Response Schema
No information.


## OKEX Future Stats Top Trader Average Margin Used
```sql
-- fetch data
select * from okex_future_stats_topTraderAverageMarginUsed limit 1 
```
> response

```json
[
    'time': '2020-02-03T23:00:00Z', 
    'frequency': '60', 
    'long_position': 0.2624, 
    'short_position': 0.1834, 
    'symbol': 'BTC'
]
```

### Description
[OKEX top trader average margin used](https://www.okex.com/markets/swap-data/btc-usd) has frequencies of 5 minutes, 15 minutes and 1 hour and data time range is from 2020-02-03 23:00:00 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
long_position  |float |
short_position |float |
frequency | string | tag values
symbol | string | tag values

### Tag Values
**Symbol (Symbols are subject to change)**: 
'BCH', 'BSV', 'BTC', 'EOS', 'ETC', 'ETH', 'LTC', 'TRX', 'XRP'

<aside class="notice">
All symbols are in USD, i.e. BCHUSD
</aside>

**Frequency**:
5, 15, 60

### Data Sanity
No downtime.

### API Reference

`GET https://www.okex.com/v2/futures/pc/public/getFuturePositionRatio.do?symbol=f_usd_{}&type=0`


### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
symbol	|String|	Yes	| Symbol name
type | int| Yes | data granuality

### API Response Schema
No information.


## OKEX Future Stats Top Trader Sentimental Index
```sql
-- fetch data
select * from okex_future_stats_topTraderSentimentIndex limit 1 
```
> response

```json
[
    'time': '2020-02-03T23:00:00Z', 
    'frequency': '60', 
    'long_position': 0.2624, 
    'short_position': 0.1834, 
    'symbol': 'BTC'
]
```

### Description
[OKEX top trader sentimental index](https://www.okex.com/markets/swap-data/btc-usd) has frequencies of 5 minutes, 15 minutes and 1 hour and data time range is from 2020-02-02 17:00:00 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
long_position  float
short_position float
frequency | string | tag values
symbol | string | tag values

### Tag Values
**Symbol (Symbols are subject to change)**: 
'BCH', 'BSV', 'BTC', 'EOS', 'ETC', 'ETH', 'LTC', 'TRX', 'XRP'

<aside class="notice">
All symbols are in USD, i.e. BCHUSD
</aside>

**Frequency**:
5, 15, 60

### Data Sanity
No downtime.

### API Reference

`GET https://www.okex.com/v2/futures/pc/public/eliteScale.do?symbol=f_usd_{}&type=0`


### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
symbol	|String|	Yes	| Symbol name
type | int| Yes | data granuality

### API Response Schema
No information.



## OKEX Liquidation 
```sql
-- fetch data
select * from okex_liquidation limit 1 
```
> response

```json
[
    {
       'time': '2019-07-11T04:27:35.969000192Z', 
       'loss': '0', 
       'price': '96.48', 
       'size': '45', 
       'symbol': 'LTC-USD-SWAP', 
       'type': '3'
   }
]
```

### Description
OKEX liquidation has a frequency of 1 hour and data time range is from 2019-07-11 04:27:35.969000192 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
loss     |string|
price    |string|
size     |string|
type     |string|
symbol | string | tag values

### Tag Values
**Swap Symbol (Symbols are subject to change)**: 
'BCH-USD-SWAP', 'BCH-USDT-SWAP', 'BSV-USD-SWAP', 'BSV-USDT-SWAP', 'BTC-USD-SWAP', 'BTC-USDT-SWAP', 'DASH-USD-SWAP', 'DASH-USDT-SWAP', 'EOS-USD-SWAP', 'EOS-USDT-SWAP', 'ETC-USD-SWAP', 'ETC-USDT-SWAP', 'ETH-USD-SWAP', 'ETH-USDT-SWAP', 'LINK-USD-SWAP', 'LINK-USDT-SWAP', 'LTC-USD-SWAP', 'LTC-USDT-SWAP', 'NEO-USD-SWAP', 'NEO-USDT-SWAP', 'TRX-USD-SWAP', 'TRX-USDT-SWAP', 'XRP-USD-SWAP', 'XRP-USDT-SWAP'

### Data Sanity
No downtime.

### API Reference
`GET https://www.okex.com/api/swap/v3/instruments/liquidation`

### API Query Parameters
Not required.

### API Response Schema
No information.


## OKEX Mark Price
```sql
-- fetch data
select * from okex_markPrice limit 1 
```
> response

```json
[
    {
       'time': '2019-07-11T15:59:41.304Z', 
       'expiration': 'quarterly', 
       'mark_price': '11604.41', 
       'symbol': 'BTC-USD-190927'
   }
]
```

### Description
[OKEX mark price](https://www.okex.com/docs/en/#futures_ws-mark is connected through websocket and data time range is from 2019-07-11 15:59:41.304 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
expiration | string | tag values
mark_price | string |
symbol | string | tag values

### Tag Values
**Futures and Swap Symbol (Symbols are subject to change)**: 
'BCH-USD-200131', 'BCH-USD-200207', 'BCH-USD-200214', 'BCH-USD-200221', 'BCH-USD-200228', 'BCH-USD-200306', 'BCH-USD-200313', 'BCH-USD-200320', 'BCH-USD-200327', 'BCH-USD-200403', 'BCH-USD-200410', 'BCH-USD-200417', 'BCH-USD-200424', 'BCH-USD-200501', 'BCH-USD-200626', 'BCH-USD-SWAP', 'BCH-USDT-200131', 'BCH-USDT-200207', 'BCH-USDT-200214', 'BCH-USDT-200221', 'BCH-USDT-200228', 'BCH-USDT-200306', 'BCH-USDT-200313', 'BCH-USDT-200320', 'BCH-USDT-200327', 'BCH-USDT-200403', 'BCH-USDT-200410', 'BCH-USDT-200417', 'BCH-USDT-200424', 'BCH-USDT-200501', 'BCH-USDT-200626', 'BCH-USDT-SWAP', 'BSV-USD-200131', 'BSV-USD-200207', 'BSV-USD-200214', 'BSV-USD-200221', 'BSV-USD-200228', 'BSV-USD-200306', 'BSV-USD-200313', 'BSV-USD-200320', 'BSV-USD-200327', 'BSV-USD-200403', 'BSV-USD-200410', 'BSV-USD-200417', 'BSV-USD-200424', 'BSV-USD-200501', 'BSV-USD-200626', 'BSV-USD-SWAP', 'BSV-USDT-200131', 'BSV-USDT-200207', 'BSV-USDT-200214', 'BSV-USDT-200221', 'BSV-USDT-200228', 'BSV-USDT-200306', 'BSV-USDT-200313', 'BSV-USDT-200320', 'BSV-USDT-200327', 'BSV-USDT-200403', 'BSV-USDT-200410', 'BSV-USDT-200417', 'BSV-USDT-200424', 'BSV-USDT-200501', 'BSV-USDT-200626', 'BSV-USDT-SWAP', 'BTC-USD-190712', 'BTC-USD-190719', 'BTC-USD-190726', 'BTC-USD-190802', 'BTC-USD-190809', 'BTC-USD-190816', 'BTC-USD-190823', 'BTC-USD-190830', 'BTC-USD-190906', 'BTC-USD-190913', 'BTC-USD-190920', 'BTC-USD-190927', 'BTC-USD-191004', 'BTC-USD-191011', 'BTC-USD-191018', 'BTC-USD-191025', 'BTC-USD-191122', 'BTC-USD-191129', 'BTC-USD-191206', 'BTC-USD-191213', 'BTC-USD-191220', 'BTC-USD-191227', 'BTC-USD-200103', 'BTC-USD-200110', 'BTC-USD-200117', 'BTC-USD-200124', 'BTC-USD-200131', 'BTC-USD-200207', 'BTC-USD-200214', 'BTC-USD-200221', 'BTC-USD-200228', 'BTC-USD-200306', 'BTC-USD-200313', 'BTC-USD-200320', 'BTC-USD-200327', 'BTC-USD-200403', 'BTC-USD-200410', 'BTC-USD-200417', 'BTC-USD-200424', 'BTC-USD-200501', 'BTC-USD-200626', 'BTC-USD-SWAP', 'BTC-USDT-191213', 'BTC-USDT-191220', 'BTC-USDT-191227', 'BTC-USDT-200103', 'BTC-USDT-200110', 'BTC-USDT-200117', 'BTC-USDT-200124', 'BTC-USDT-200131', 'BTC-USDT-200207', 'BTC-USDT-200214', 'BTC-USDT-200221', 'BTC-USDT-200228', 'BTC-USDT-200306', 'BTC-USDT-200313', 'BTC-USDT-200320', 'BTC-USDT-200327', 'BTC-USDT-200403', 'BTC-USDT-200410', 'BTC-USDT-200417', 'BTC-USDT-200424', 'BTC-USDT-200501', 'BTC-USDT-200626', 'BTC-USDT-SWAP', 'EOS-USD-191213', 'EOS-USD-191220', 'EOS-USD-191227', 'EOS-USD-200103', 'EOS-USD-200110', 'EOS-USD-200117', 'EOS-USD-200124', 'EOS-USD-200131', 'EOS-USD-200207', 'EOS-USD-200214', 'EOS-USD-200221', 'EOS-USD-200228', 'EOS-USD-200306', 'EOS-USD-200313', 'EOS-USD-200320', 'EOS-USD-200327', 'EOS-USD-200403', 'EOS-USD-200410', 'EOS-USD-200417', 'EOS-USD-200424', 'EOS-USD-200501', 'EOS-USD-200626', 'EOS-USD-SWAP', 'EOS-USDT-191213', 'EOS-USDT-191220', 'EOS-USDT-191227', 'EOS-USDT-200103', 'EOS-USDT-200110', 'EOS-USDT-200117', 'EOS-USDT-200124', 'EOS-USDT-200131', 'EOS-USDT-200207', 'EOS-USDT-200214', 'EOS-USDT-200221', 'EOS-USDT-200228', 'EOS-USDT-200306', 'EOS-USDT-200313', 'EOS-USDT-200320', 'EOS-USDT-200327', 'EOS-USDT-200403', 'EOS-USDT-200410', 'EOS-USDT-200417', 'EOS-USDT-200424', 'EOS-USDT-200501', 'EOS-USDT-200626', 'EOS-USDT-SWAP', 'ETC-USD-200131', 'ETC-USD-200207', 'ETC-USD-200214', 'ETC-USD-200221', 'ETC-USD-200228', 'ETC-USD-200306', 'ETC-USD-200313', 'ETC-USD-200320', 'ETC-USD-200327', 'ETC-USD-200403', 'ETC-USD-200410', 'ETC-USD-200417', 'ETC-USD-200424', 'ETC-USD-200501', 'ETC-USD-200626', 'ETC-USD-SWAP', 'ETC-USDT-200131', 'ETC-USDT-200207', 'ETC-USDT-200214', 'ETC-USDT-200221', 'ETC-USDT-200228', 'ETC-USDT-200306', 'ETC-USDT-200313', 'ETC-USDT-200320', 'ETC-USDT-200327', 'ETC-USDT-200403', 'ETC-USDT-200410', 'ETC-USDT-200417', 'ETC-USDT-200424', 'ETC-USDT-200501', 'ETC-USDT-200626', 'ETC-USDT-SWAP', 'ETH-USD-190712', 'ETH-USD-190719', 'ETH-USD-190726', 'ETH-USD-190802', 'ETH-USD-190809', 'ETH-USD-190816', 'ETH-USD-190823', 'ETH-USD-190830', 'ETH-USD-190906', 'ETH-USD-190913', 'ETH-USD-190920', 'ETH-USD-190927', 'ETH-USD-191004', 'ETH-USD-191011', 'ETH-USD-191018', 'ETH-USD-191025', 'ETH-USD-191122', 'ETH-USD-191129', 'ETH-USD-191206', 'ETH-USD-191213', 'ETH-USD-191220', 'ETH-USD-191227', 'ETH-USD-200103', 'ETH-USD-200110', 'ETH-USD-200117', 'ETH-USD-200124', 'ETH-USD-200131', 'ETH-USD-200207', 'ETH-USD-200214', 'ETH-USD-200221', 'ETH-USD-200228', 'ETH-USD-200306', 'ETH-USD-200313', 'ETH-USD-200320', 'ETH-USD-200327', 'ETH-USD-200403', 'ETH-USD-200410', 'ETH-USD-200417', 'ETH-USD-200424', 'ETH-USD-200501', 'ETH-USD-200626', 'ETH-USD-SWAP', 'ETH-USDT-191213', 'ETH-USDT-191220', 'ETH-USDT-191227', 'ETH-USDT-200103', 'ETH-USDT-200110', 'ETH-USDT-200117', 'ETH-USDT-200124', 'ETH-USDT-200131', 'ETH-USDT-200207', 'ETH-USDT-200214', 'ETH-USDT-200221', 'ETH-USDT-200228', 'ETH-USDT-200306', 'ETH-USDT-200313', 'ETH-USDT-200320', 'ETH-USDT-200327', 'ETH-USDT-200403', 'ETH-USDT-200410', 'ETH-USDT-200417', 'ETH-USDT-200424', 'ETH-USDT-200501', 'ETH-USDT-200626', 'ETH-USDT-SWAP', 'LTC-USD-190712', 'LTC-USD-190719', 'LTC-USD-190726', 'LTC-USD-190802', 'LTC-USD-190809', 'LTC-USD-190816', 'LTC-USD-190823', 'LTC-USD-190830', 'LTC-USD-190906', 'LTC-USD-190913', 'LTC-USD-190920', 'LTC-USD-190927', 'LTC-USD-191004', 'LTC-USD-191011', 'LTC-USD-191018', 'LTC-USD-191025', 'LTC-USD-191122', 'LTC-USD-191129', 'LTC-USD-191206', 'LTC-USD-191213', 'LTC-USD-191220', 'LTC-USD-191227', 'LTC-USD-200103', 'LTC-USD-200110', 'LTC-USD-200117', 'LTC-USD-200124', 'LTC-USD-200131', 'LTC-USD-200207', 'LTC-USD-200214', 'LTC-USD-200221', 'LTC-USD-200228', 'LTC-USD-200306', 'LTC-USD-200313', 'LTC-USD-200320', 'LTC-USD-200327', 'LTC-USD-200403', 'LTC-USD-200410', 'LTC-USD-200417', 'LTC-USD-200424', 'LTC-USD-200501', 'LTC-USD-200626', 'LTC-USD-SWAP', 'LTC-USDT-191213', 'LTC-USDT-191220', 'LTC-USDT-191227', 'LTC-USDT-200103', 'LTC-USDT-200110', 'LTC-USDT-200117', 'LTC-USDT-200124', 'LTC-USDT-200131', 'LTC-USDT-200207', 'LTC-USDT-200214', 'LTC-USDT-200221', 'LTC-USDT-200228', 'LTC-USDT-200306', 'LTC-USDT-200313', 'LTC-USDT-200320', 'LTC-USDT-200327', 'LTC-USDT-200403', 'LTC-USDT-200410', 'LTC-USDT-200417', 'LTC-USDT-200424', 'LTC-USDT-200501', 'LTC-USDT-200626', 'LTC-USDT-SWAP', 'TRX-USD-191213', 'TRX-USD-191220', 'TRX-USD-191227', 'TRX-USD-200103', 'TRX-USD-200110', 'TRX-USD-200117', 'TRX-USD-200124', 'TRX-USD-200131', 'TRX-USD-200207', 'TRX-USD-200214', 'TRX-USD-200221', 'TRX-USD-200228', 'TRX-USD-200306', 'TRX-USD-200313', 'TRX-USD-200320', 'TRX-USD-200327', 'TRX-USD-200403', 'TRX-USD-200410', 'TRX-USD-200417', 'TRX-USD-200424', 'TRX-USD-200501', 'TRX-USD-200626', 'TRX-USD-SWAP', 'TRX-USDT-191213', 'TRX-USDT-191220', 'TRX-USDT-191227', 'TRX-USDT-200103', 'TRX-USDT-200110', 'TRX-USDT-200117', 'TRX-USDT-200124', 'TRX-USDT-200131', 'TRX-USDT-200207', 'TRX-USDT-200214', 'TRX-USDT-200221', 'TRX-USDT-200228', 'TRX-USDT-200306', 'TRX-USDT-200313', 'TRX-USDT-200320', 'TRX-USDT-200327', 'TRX-USDT-200403', 'TRX-USDT-200410', 'TRX-USDT-200417', 'TRX-USDT-200424', 'TRX-USDT-200501', 'TRX-USDT-200626', 'TRX-USDT-SWAP', 'XRP-USD-191213', 'XRP-USD-191220', 'XRP-USD-191227', 'XRP-USD-200103', 'XRP-USD-200110', 'XRP-USD-200117', 'XRP-USD-200124', 'XRP-USD-200131', 'XRP-USD-200207', 'XRP-USD-200214', 'XRP-USD-200221', 'XRP-USD-200228', 'XRP-USD-200306', 'XRP-USD-200313', 'XRP-USD-200320', 'XRP-USD-200327', 'XRP-USD-200403', 'XRP-USD-200410', 'XRP-USD-200417', 'XRP-USD-200424', 'XRP-USD-200501', 'XRP-USD-200626', 'XRP-USD-SWAP', 'XRP-USDT-191213', 'XRP-USDT-191220', 'XRP-USDT-191227', 'XRP-USDT-200103', 'XRP-USDT-200110', 'XRP-USDT-200117', 'XRP-USDT-200124', 'XRP-USDT-200131', 'XRP-USDT-200207', 'XRP-USDT-200214', 'XRP-USDT-200221', 'XRP-USDT-200228', 'XRP-USDT-200306', 'XRP-USDT-200313', 'XRP-USDT-200320', 'XRP-USDT-200327', 'XRP-USDT-200403', 'XRP-USDT-200410', 'XRP-USDT-200417', 'XRP-USDT-200424', 'XRP-USDT-200501', 'XRP-USDT-200626', 'XRP-USDT-SWAP'

**Expiration**:
biweekly, weekly, quarterly

### Data Sanity
No downtime.

### API Reference
**Endpoint**:
`Websocket wss://real.okex.com:8443/ws/v3`

**Futures Payload**:
`{"op": "subscribe", "args":["futures/price_range:BTC-USD-190628"]`

**Swap Payload**:
`{"op": "subscribe", "args":["swap/price_range:BTC-USD-190628"]`

### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
symbol	|String|	Yes	| Futures symbol name

### API Response Schema
Name | Type | Description
---- | ---- | ----------
instrument_id	|String|	Contract ID, e.g. BTC-USD-170310,BTC-USDT-191227
mark_price	|String|	Mark Price
timestamp	|String|	Timestamp



## OKEX Price Range
```sql
-- fetch data
select * from okex_priceRange limit 1 
```
> response

```json
[
    {
       'time': '2019-07-11T15:59:45.007000064Z', 
       'expiration': None, 
       'highest': '275.09', 
       'lowest': '264.30', 
       'symbol': 'ETH-USD-SWAP
   }
]
```

### Description
[OKEX price range](https://www.okex.com/docs/en/#ws_swap-rate) is connected through websocket and data time range is from 2019-07-11 15:59:41.304 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
lowest | string | 
highest | string |
symbol | string | tag values

### Tag Values
**Futures and swap Symbol (Symbols are subject to change)**: 
'BCH-USD-200131', 'BCH-USD-200207', 'BCH-USD-200214', 'BCH-USD-200221', 'BCH-USD-200228', 'BCH-USD-200306', 'BCH-USD-200313', 'BCH-USD-200320', 'BCH-USD-200327', 'BCH-USD-200403', 'BCH-USD-200410', 'BCH-USD-200417', 'BCH-USD-200424', 'BCH-USD-200501', 'BCH-USD-200626', 'BCH-USD-SWAP', 'BCH-USDT-200131', 'BCH-USDT-200207', 'BCH-USDT-200214', 'BCH-USDT-200221', 'BCH-USDT-200228', 'BCH-USDT-200306', 'BCH-USDT-200313', 'BCH-USDT-200320', 'BCH-USDT-200327', 'BCH-USDT-200403', 'BCH-USDT-200410', 'BCH-USDT-200417', 'BCH-USDT-200424', 'BCH-USDT-200501', 'BCH-USDT-200626', 'BCH-USDT-SWAP', 'BSV-USD-200131', 'BSV-USD-200207', 'BSV-USD-200214', 'BSV-USD-200221', 'BSV-USD-200228', 'BSV-USD-200306', 'BSV-USD-200313', 'BSV-USD-200320', 'BSV-USD-200327', 'BSV-USD-200403', 'BSV-USD-200410', 'BSV-USD-200417', 'BSV-USD-200424', 'BSV-USD-200501', 'BSV-USD-200626', 'BSV-USD-SWAP', 'BSV-USDT-200131', 'BSV-USDT-200207', 'BSV-USDT-200214', 'BSV-USDT-200221', 'BSV-USDT-200228', 'BSV-USDT-200306', 'BSV-USDT-200313', 'BSV-USDT-200320', 'BSV-USDT-200327', 'BSV-USDT-200403', 'BSV-USDT-200410', 'BSV-USDT-200417', 'BSV-USDT-200424', 'BSV-USDT-200501', 'BSV-USDT-200626', 'BSV-USDT-SWAP', 'BTC-USD-190712', 'BTC-USD-190719', 'BTC-USD-190726', 'BTC-USD-190802', 'BTC-USD-190809', 'BTC-USD-190816', 'BTC-USD-190823', 'BTC-USD-190830', 'BTC-USD-190906', 'BTC-USD-190913', 'BTC-USD-190920', 'BTC-USD-190927', 'BTC-USD-191004', 'BTC-USD-191011', 'BTC-USD-191018', 'BTC-USD-191025', 'BTC-USD-191122', 'BTC-USD-191129', 'BTC-USD-191206', 'BTC-USD-191213', 'BTC-USD-191220', 'BTC-USD-191227', 'BTC-USD-200103', 'BTC-USD-200110', 'BTC-USD-200117', 'BTC-USD-200124', 'BTC-USD-200131', 'BTC-USD-200207', 'BTC-USD-200214', 'BTC-USD-200221', 'BTC-USD-200228', 'BTC-USD-200306', 'BTC-USD-200313', 'BTC-USD-200320', 'BTC-USD-200327', 'BTC-USD-200403', 'BTC-USD-200410', 'BTC-USD-200417', 'BTC-USD-200424', 'BTC-USD-200501', 'BTC-USD-200626', 'BTC-USD-SWAP', 'BTC-USDT-191213', 'BTC-USDT-191220', 'BTC-USDT-191227', 'BTC-USDT-200103', 'BTC-USDT-200110', 'BTC-USDT-200117', 'BTC-USDT-200124', 'BTC-USDT-200131', 'BTC-USDT-200207', 'BTC-USDT-200214', 'BTC-USDT-200221', 'BTC-USDT-200228', 'BTC-USDT-200306', 'BTC-USDT-200313', 'BTC-USDT-200320', 'BTC-USDT-200327', 'BTC-USDT-200403', 'BTC-USDT-200410', 'BTC-USDT-200417', 'BTC-USDT-200424', 'BTC-USDT-200501', 'BTC-USDT-200626', 'BTC-USDT-SWAP', 'EOS-USD-191213', 'EOS-USD-191220', 'EOS-USD-191227', 'EOS-USD-200103', 'EOS-USD-200110', 'EOS-USD-200117', 'EOS-USD-200124', 'EOS-USD-200131', 'EOS-USD-200207', 'EOS-USD-200214', 'EOS-USD-200221', 'EOS-USD-200228', 'EOS-USD-200306', 'EOS-USD-200313', 'EOS-USD-200320', 'EOS-USD-200327', 'EOS-USD-200403', 'EOS-USD-200410', 'EOS-USD-200417', 'EOS-USD-200424', 'EOS-USD-200501', 'EOS-USD-200626', 'EOS-USD-SWAP', 'EOS-USDT-191213', 'EOS-USDT-191220', 'EOS-USDT-191227', 'EOS-USDT-200103', 'EOS-USDT-200110', 'EOS-USDT-200117', 'EOS-USDT-200124', 'EOS-USDT-200131', 'EOS-USDT-200207', 'EOS-USDT-200214', 'EOS-USDT-200221', 'EOS-USDT-200228', 'EOS-USDT-200306', 'EOS-USDT-200313', 'EOS-USDT-200320', 'EOS-USDT-200327', 'EOS-USDT-200403', 'EOS-USDT-200410', 'EOS-USDT-200417', 'EOS-USDT-200424', 'EOS-USDT-200501', 'EOS-USDT-200626', 'EOS-USDT-SWAP', 'ETC-USD-200131', 'ETC-USD-200207', 'ETC-USD-200214', 'ETC-USD-200221', 'ETC-USD-200228', 'ETC-USD-200306', 'ETC-USD-200313', 'ETC-USD-200320', 'ETC-USD-200327', 'ETC-USD-200403', 'ETC-USD-200410', 'ETC-USD-200417', 'ETC-USD-200424', 'ETC-USD-200501', 'ETC-USD-200626', 'ETC-USD-SWAP', 'ETC-USDT-200131', 'ETC-USDT-200207', 'ETC-USDT-200214', 'ETC-USDT-200221', 'ETC-USDT-200228', 'ETC-USDT-200306', 'ETC-USDT-200313', 'ETC-USDT-200320', 'ETC-USDT-200327', 'ETC-USDT-200403', 'ETC-USDT-200410', 'ETC-USDT-200417', 'ETC-USDT-200424', 'ETC-USDT-200501', 'ETC-USDT-200626', 'ETC-USDT-SWAP', 'ETH-USD-190712', 'ETH-USD-190719', 'ETH-USD-190726', 'ETH-USD-190802', 'ETH-USD-190809', 'ETH-USD-190816', 'ETH-USD-190823', 'ETH-USD-190830', 'ETH-USD-190906', 'ETH-USD-190913', 'ETH-USD-190920', 'ETH-USD-190927', 'ETH-USD-191004', 'ETH-USD-191011', 'ETH-USD-191018', 'ETH-USD-191025', 'ETH-USD-191122', 'ETH-USD-191129', 'ETH-USD-191206', 'ETH-USD-191213', 'ETH-USD-191220', 'ETH-USD-191227', 'ETH-USD-200103', 'ETH-USD-200110', 'ETH-USD-200117', 'ETH-USD-200124', 'ETH-USD-200131', 'ETH-USD-200207', 'ETH-USD-200214', 'ETH-USD-200221', 'ETH-USD-200228', 'ETH-USD-200306', 'ETH-USD-200313', 'ETH-USD-200320', 'ETH-USD-200327', 'ETH-USD-200403', 'ETH-USD-200410', 'ETH-USD-200417', 'ETH-USD-200424', 'ETH-USD-200501', 'ETH-USD-200626', 'ETH-USD-SWAP', 'ETH-USDT-191213', 'ETH-USDT-191220', 'ETH-USDT-191227', 'ETH-USDT-200103', 'ETH-USDT-200110', 'ETH-USDT-200117', 'ETH-USDT-200124', 'ETH-USDT-200131', 'ETH-USDT-200207', 'ETH-USDT-200214', 'ETH-USDT-200221', 'ETH-USDT-200228', 'ETH-USDT-200306', 'ETH-USDT-200313', 'ETH-USDT-200320', 'ETH-USDT-200327', 'ETH-USDT-200403', 'ETH-USDT-200410', 'ETH-USDT-200417', 'ETH-USDT-200424', 'ETH-USDT-200501', 'ETH-USDT-200626', 'ETH-USDT-SWAP', 'LTC-USD-190712', 'LTC-USD-190719', 'LTC-USD-190726', 'LTC-USD-190802', 'LTC-USD-190809', 'LTC-USD-190816', 'LTC-USD-190823', 'LTC-USD-190830', 'LTC-USD-190906', 'LTC-USD-190913', 'LTC-USD-190920', 'LTC-USD-190927', 'LTC-USD-191004', 'LTC-USD-191011', 'LTC-USD-191018', 'LTC-USD-191025', 'LTC-USD-191122', 'LTC-USD-191129', 'LTC-USD-191206', 'LTC-USD-191213', 'LTC-USD-191220', 'LTC-USD-191227', 'LTC-USD-200103', 'LTC-USD-200110', 'LTC-USD-200117', 'LTC-USD-200124', 'LTC-USD-200131', 'LTC-USD-200207', 'LTC-USD-200214', 'LTC-USD-200221', 'LTC-USD-200228', 'LTC-USD-200306', 'LTC-USD-200313', 'LTC-USD-200320', 'LTC-USD-200327', 'LTC-USD-200403', 'LTC-USD-200410', 'LTC-USD-200417', 'LTC-USD-200424', 'LTC-USD-200501', 'LTC-USD-200626', 'LTC-USD-SWAP', 'LTC-USDT-191213', 'LTC-USDT-191220', 'LTC-USDT-191227', 'LTC-USDT-200103', 'LTC-USDT-200110', 'LTC-USDT-200117', 'LTC-USDT-200124', 'LTC-USDT-200131', 'LTC-USDT-200207', 'LTC-USDT-200214', 'LTC-USDT-200221', 'LTC-USDT-200228', 'LTC-USDT-200306', 'LTC-USDT-200313', 'LTC-USDT-200320', 'LTC-USDT-200327', 'LTC-USDT-200403', 'LTC-USDT-200410', 'LTC-USDT-200417', 'LTC-USDT-200424', 'LTC-USDT-200501', 'LTC-USDT-200626', 'LTC-USDT-SWAP', 'TRX-USD-191213', 'TRX-USD-191220', 'TRX-USD-191227', 'TRX-USD-200103', 'TRX-USD-200110', 'TRX-USD-200117', 'TRX-USD-200124', 'TRX-USD-200131', 'TRX-USD-200207', 'TRX-USD-200214', 'TRX-USD-200221', 'TRX-USD-200228', 'TRX-USD-200306', 'TRX-USD-200313', 'TRX-USD-200320', 'TRX-USD-200327', 'TRX-USD-200403', 'TRX-USD-200410', 'TRX-USD-200417', 'TRX-USD-200424', 'TRX-USD-200501', 'TRX-USD-200626', 'TRX-USD-SWAP', 'TRX-USDT-191213', 'TRX-USDT-191220', 'TRX-USDT-191227', 'TRX-USDT-200103', 'TRX-USDT-200110', 'TRX-USDT-200117', 'TRX-USDT-200124', 'TRX-USDT-200131', 'TRX-USDT-200207', 'TRX-USDT-200214', 'TRX-USDT-200221', 'TRX-USDT-200228', 'TRX-USDT-200306', 'TRX-USDT-200313', 'TRX-USDT-200320', 'TRX-USDT-200327', 'TRX-USDT-200403', 'TRX-USDT-200410', 'TRX-USDT-200417', 'TRX-USDT-200424', 'TRX-USDT-200501', 'TRX-USDT-200626', 'TRX-USDT-SWAP', 'XRP-USD-191213', 'XRP-USD-191220', 'XRP-USD-191227', 'XRP-USD-200103', 'XRP-USD-200110', 'XRP-USD-200117', 'XRP-USD-200124', 'XRP-USD-200131', 'XRP-USD-200207', 'XRP-USD-200214', 'XRP-USD-200221', 'XRP-USD-200228', 'XRP-USD-200306', 'XRP-USD-200313', 'XRP-USD-200320', 'XRP-USD-200327', 'XRP-USD-200403', 'XRP-USD-200410', 'XRP-USD-200417', 'XRP-USD-200424', 'XRP-USD-200501', 'XRP-USD-200626', 'XRP-USD-SWAP', 'XRP-USDT-191213', 'XRP-USDT-191220', 'XRP-USDT-191227', 'XRP-USDT-200103', 'XRP-USDT-200110', 'XRP-USDT-200117', 'XRP-USDT-200124', 'XRP-USDT-200131', 'XRP-USDT-200207', 'XRP-USDT-200214', 'XRP-USDT-200221', 'XRP-USDT-200228', 'XRP-USDT-200306', 'XRP-USDT-200313', 'XRP-USDT-200320', 'XRP-USDT-200327', 'XRP-USDT-200403', 'XRP-USDT-200410', 'XRP-USDT-200417', 'XRP-USDT-200424', 'XRP-USDT-200501', 'XRP-USDT-200626', 'XRP-USDT-SWAP

**Expiration**:
biweekly, weekly, quarterly

### Data Sanity
No downtime.

### API Reference
**Endpoint**:
`Websocket wss://real.okex.com:8443/ws/v3`

**Futures Payload**:
`{"op": "subscribe", "args":["futures/price_range:BTC-USD-190628"]`

**Swap Payload**:
`{"op": "subscribe", "args":["swap/price_range:BTC-USD-190628"]`

### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
symbol	|String|	Yes	| Futures symbol name

### API Response Schema
Name | Type | Description
---- | ---- | ----------
timestamp	|String|	timestamp
lowest	|String|	Minimum buying price
instrument_id	|String|	Contract ID, e.g. BTC-USD-170310,BTC-USDT-191227
highest	|String	|Maximum buying price


## OKEX Orderbook
```sql
-- fetch data
select * from okex_Orderbook limit 1 
```
> response

```json
[
    {
       'time': '2019-10-01T20:17:47.402132336Z', 
       'orders_depth': '2', 
       'price_amount': '8500', 
       'price_depth': '0.0381', 
       'symbol': 'HBAR-USDT', 
       'timestamp': '2019-10-01T20:17:18.304Z', 
       'type': 'bids'
   }
]
```

### Description
[OKEX orderbook](https://www.okex.com/docs/en/#futures_ws-depth) is connected through websocket and data time range is from 2019-10-01 20:17:47.402132336 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
orders_depth |string|
price_amount |string|
price_depth  |string|
timestamp    |string|
type         |string|
symbol | string | tag values

### Tag Values
**Futures, Spot and Swap Symbol (Symbols are subject to change)**: 
'ALGO-BTC', 'ALGO-ETH', 'ALGO-USDK', 'ALGO-USDT', 'BCH-USD-200228', 'BCH-USD-200306', 'BCH-USD-200313', 'BCH-USD-200320', 'BCH-USD-200327', 'BCH-USD-200403', 'BCH-USD-200410', 'BCH-USD-200417', 'BCH-USD-200424', 'BCH-USD-200501', 'BCH-USD-200626', 'BCH-USD-200925', 'BCH-USD-SWAP', 'BCH-USDT-200228', 'BCH-USDT-200306', 'BCH-USDT-200313', 'BCH-USDT-200320', 'BCH-USDT-200327', 'BCH-USDT-200403', 'BCH-USDT-200410', 'BCH-USDT-200417', 'BCH-USDT-200424', 'BCH-USDT-200501', 'BCH-USDT-200626', 'BCH-USDT-200925', 'BCH-USDT-SWAP', 'BSV-USD-200228', 'BSV-USD-200306', 'BSV-USD-200313', 'BSV-USD-200320', 'BSV-USD-200327', 'BSV-USD-200403', 'BSV-USD-200410', 'BSV-USD-200417', 'BSV-USD-200424', 'BSV-USD-200501', 'BSV-USD-200626', 'BSV-USD-200925', 'BSV-USD-SWAP', 'BSV-USDT-200228', 'BSV-USDT-200306', 'BSV-USDT-200313', 'BSV-USDT-200320', 'BSV-USDT-200327', 'BSV-USDT-200403', 'BSV-USDT-200410', 'BSV-USDT-200417', 'BSV-USDT-200424', 'BSV-USDT-200501', 'BSV-USDT-200626', 'BSV-USDT-200925', 'BSV-USDT-SWAP', 'BTC-USD-200228', 'BTC-USD-200306', 'BTC-USD-200313', 'BTC-USD-200320', 'BTC-USD-200327', 'BTC-USD-200403', 'BTC-USD-200410', 'BTC-USD-200417', 'BTC-USD-200424', 'BTC-USD-200501', 'BTC-USD-200626', 'BTC-USD-200925', 'BTC-USD-SWAP', 'BTC-USDT', 'BTC-USDT-200228', 'BTC-USDT-200306', 'BTC-USDT-200313', 'BTC-USDT-200320', 'BTC-USDT-200327', 'BTC-USDT-200403', 'BTC-USDT-200410', 'BTC-USDT-200417', 'BTC-USDT-200424', 'BTC-USDT-200501', 'BTC-USDT-200626', 'BTC-USDT-200925', 'BTC-USDT-SWAP', 'DASH-USD-SWAP', 'DASH-USDT-SWAP', 'EOS-USD-200228', 'EOS-USD-200306', 'EOS-USD-200313', 'EOS-USD-200320', 'EOS-USD-200327', 'EOS-USD-200403', 'EOS-USD-200410', 'EOS-USD-200417', 'EOS-USD-200424', 'EOS-USD-200501', 'EOS-USD-200626', 'EOS-USD-200925', 'EOS-USD-SWAP', 'EOS-USDT-200228', 'EOS-USDT-200306', 'EOS-USDT-200313', 'EOS-USDT-200320', 'EOS-USDT-200327', 'EOS-USDT-200403', 'EOS-USDT-200410', 'EOS-USDT-200417', 'EOS-USDT-200424', 'EOS-USDT-200501', 'EOS-USDT-200626', 'EOS-USDT-200925', 'EOS-USDT-SWAP', 'ETC-USD-200228', 'ETC-USD-200306', 'ETC-USD-200313', 'ETC-USD-200320', 'ETC-USD-200327', 'ETC-USD-200403', 'ETC-USD-200410', 'ETC-USD-200417', 'ETC-USD-200424', 'ETC-USD-200501', 'ETC-USD-200626', 'ETC-USD-200925', 'ETC-USD-SWAP', 'ETC-USDT-200228', 'ETC-USDT-200306', 'ETC-USDT-200313', 'ETC-USDT-200320', 'ETC-USDT-200327', 'ETC-USDT-200403', 'ETC-USDT-200410', 'ETC-USDT-200417', 'ETC-USDT-200424', 'ETC-USDT-200501', 'ETC-USDT-200626', 'ETC-USDT-200925', 'ETC-USDT-SWAP', 'ETH-USD-200228', 'ETH-USD-200306', 'ETH-USD-200313', 'ETH-USD-200320', 'ETH-USD-200327', 'ETH-USD-200403', 'ETH-USD-200410', 'ETH-USD-200417', 'ETH-USD-200424', 'ETH-USD-200501', 'ETH-USD-200626', 'ETH-USD-200925', 'ETH-USD-SWAP', 'ETH-USDT', 'ETH-USDT-200228', 'ETH-USDT-200306', 'ETH-USDT-200313', 'ETH-USDT-200320', 'ETH-USDT-200327', 'ETH-USDT-200403', 'ETH-USDT-200410', 'ETH-USDT-200417', 'ETH-USDT-200424', 'ETH-USDT-200501', 'ETH-USDT-200626', 'ETH-USDT-200925', 'ETH-USDT-SWAP', 'HBAR-BTC', 'HBAR-USDK', 'HBAR-USDT', 'LINK-USD-SWAP', 'LINK-USDT-SWAP', 'LTC-USD-200228', 'LTC-USD-200306', 'LTC-USD-200313', 'LTC-USD-200320', 'LTC-USD-200327', 'LTC-USD-200403', 'LTC-USD-200410', 'LTC-USD-200417', 'LTC-USD-200424', 'LTC-USD-200501', 'LTC-USD-200626', 'LTC-USD-200925', 'LTC-USD-SWAP', 'LTC-USDT-200228', 'LTC-USDT-200306', 'LTC-USDT-200313', 'LTC-USDT-200320', 'LTC-USDT-200327', 'LTC-USDT-200403', 'LTC-USDT-200410', 'LTC-USDT-200417', 'LTC-USDT-200424', 'LTC-USDT-200501', 'LTC-USDT-200626', 'LTC-USDT-200925', 'LTC-USDT-SWAP', 'NEO-USD-SWAP', 'NEO-USDT-SWAP', 'TRX-USD-200228', 'TRX-USD-200306', 'TRX-USD-200313', 'TRX-USD-200320', 'TRX-USD-200327', 'TRX-USD-200403', 'TRX-USD-200410', 'TRX-USD-200417', 'TRX-USD-200424', 'TRX-USD-200501', 'TRX-USD-200626', 'TRX-USD-200925', 'TRX-USD-SWAP', 'TRX-USDT-200228', 'TRX-USDT-200306', 'TRX-USDT-200313', 'TRX-USDT-200320', 'TRX-USDT-200327', 'TRX-USDT-200403', 'TRX-USDT-200410', 'TRX-USDT-200417', 'TRX-USDT-200424', 'TRX-USDT-200501', 'TRX-USDT-200626', 'TRX-USDT-200925', 'TRX-USDT-SWAP', 'XRP-USD-200228', 'XRP-USD-200306', 'XRP-USD-200313', 'XRP-USD-200320', 'XRP-USD-200327', 'XRP-USD-200403', 'XRP-USD-200410', 'XRP-USD-200417', 'XRP-USD-200424', 'XRP-USD-200501', 'XRP-USD-200626', 'XRP-USD-200925', 'XRP-USD-SWAP', 'XRP-USDT-200228', 'XRP-USDT-200306', 'XRP-USDT-200313', 'XRP-USDT-200320', 'XRP-USDT-200327', 'XRP-USDT-200403', 'XRP-USDT-200410', 'XRP-USDT-200417', 'XRP-USDT-200424', 'XRP-USDT-200501', 'XRP-USDT-200626', 'XRP-USDT-200925', 'XRP-USDT-SWAP'


### Data Sanity
No downtime.

### API Reference
**Endpoint**:
`Websocket wss://real.okex.com:8443/ws/v3`

**Futures Payload**:
`{"op": "subscribe", "args":["futures/depth:BTC-USD-190628"]`

**Spot Payload**:
`{"op": "subscribe", "args":["spot/depth:BTC-USD"]`

### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
symbol	|String|	Yes	| Futures symbol name

### API Response Schema
Name | Type | Description
---- | ---- | ----------
asks	|List<String>	|Sell side depth
bids	|List<String>	|Buy side depth
timestamp	|String	|System time stamp
instrument_id	|String|	Contract ID，e.g .BTC-USD-191227 ,BTC-USDT-191227
checksum	|String	|checksum


## OKEX Trades
```sql
-- fetch data 
select * from okex_recentTrades limit 1 

select * from okex_spotTrades limit 1
```
> response

```json
[
    {
       'time': '2019-07-11T15:59:41.101000192Z', 
       'expiration': None, 
       'price': '11548.7', 
       'qty': None, 
       'side': None, 
       'side_1': 'buy', 
       'size': '129', 
       'symbol': 'BTC-USD-SWAP', 
       'timestamp': None, 
       'trade_id': '276009036083044400'
   }
]
```

### Description
[OKEX trades](https://www.okex.com/docs/en/#futures_ws-sub) is connected through websocket and data time range is from2019-07-11 15:59:41.101000192 till now. okex_recentTrades has the same data schema as okex_spotTrades. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
price     |string|
qty       |string|
side_1      |string| duplicated for tag value side
size      |string|
timestamp |string|
trade_id  |string|
symbol | string | tag values
side | string | tag values 

### Tag Values
**Futures, Spot and Swap Symbol (Symbols are subject to change)**: 
'ALGO-BTC', 'ALGO-ETH', 'ALGO-USDK', 'ALGO-USDT', 'BTC-USDT', 'ETH-USDT', 'HBAR-BTC', 'HBAR-USDK', 'HBAR-USDT','BCH-USD-200131', 'BCH-USD-200207', 'BCH-USD-200214', 'BCH-USD-200221', 'BCH-USD-200228', 'BCH-USD-200306', 'BCH-USD-200313', 'BCH-USD-200320', 'BCH-USD-200327', 'BCH-USD-200403', 'BCH-USD-200410', 'BCH-USD-200417', 'BCH-USD-200424', 'BCH-USD-200501', 'BCH-USD-200626', 'BCH-USD-200925', 'BCH-USD-SWAP', 'BCH-USDT-200131', 'BCH-USDT-200207', 'BCH-USDT-200214', 'BCH-USDT-200221', 'BCH-USDT-200228', 'BCH-USDT-200306', 'BCH-USDT-200313', 'BCH-USDT-200320', 'BCH-USDT-200327', 'BCH-USDT-200403', 'BCH-USDT-200410', 'BCH-USDT-200417', 'BCH-USDT-200424', 'BCH-USDT-200501', 'BCH-USDT-200626', 'BCH-USDT-200925', 'BCH-USDT-SWAP', 'BSV-USD-200131', 'BSV-USD-200207', 'BSV-USD-200214', 'BSV-USD-200221', 'BSV-USD-200228', 'BSV-USD-200306', 'BSV-USD-200313', 'BSV-USD-200320', 'BSV-USD-200327', 'BSV-USD-200403', 'BSV-USD-200410', 'BSV-USD-200417', 'BSV-USD-200424', 'BSV-USD-200501', 'BSV-USD-200626', 'BSV-USD-200925', 'BSV-USD-SWAP', 'BSV-USDT-200131', 'BSV-USDT-200207', 'BSV-USDT-200214', 'BSV-USDT-200221', 'BSV-USDT-200228', 'BSV-USDT-200306', 'BSV-USDT-200313', 'BSV-USDT-200320', 'BSV-USDT-200327', 'BSV-USDT-200403', 'BSV-USDT-200410', 'BSV-USDT-200417', 'BSV-USDT-200424', 'BSV-USDT-200501', 'BSV-USDT-200626', 'BSV-USDT-200925', 'BSV-USDT-SWAP', 'BTC-USD-190712', 'BTC-USD-190719', 'BTC-USD-190726', 'BTC-USD-190802', 'BTC-USD-190809', 'BTC-USD-190816', 'BTC-USD-190823', 'BTC-USD-190830', 'BTC-USD-190906', 'BTC-USD-190927', 'BTC-USD-191213', 'BTC-USD-191220', 'BTC-USD-191227', 'BTC-USD-200103', 'BTC-USD-200110', 'BTC-USD-200117', 'BTC-USD-200124', 'BTC-USD-200131', 'BTC-USD-200207', 'BTC-USD-200214', 'BTC-USD-200221', 'BTC-USD-200228', 'BTC-USD-200306', 'BTC-USD-200313', 'BTC-USD-200320', 'BTC-USD-200327', 'BTC-USD-200403', 'BTC-USD-200410', 'BTC-USD-200417', 'BTC-USD-200424', 'BTC-USD-200501', 'BTC-USD-200626', 'BTC-USD-200925', 'BTC-USD-SWAP', 'BTC-USDT-191213', 'BTC-USDT-191220', 'BTC-USDT-191227', 'BTC-USDT-200103', 'BTC-USDT-200110', 'BTC-USDT-200117', 'BTC-USDT-200124', 'BTC-USDT-200131', 'BTC-USDT-200207', 'BTC-USDT-200214', 'BTC-USDT-200221', 'BTC-USDT-200228', 'BTC-USDT-200306', 'BTC-USDT-200313', 'BTC-USDT-200320', 'BTC-USDT-200327', 'BTC-USDT-200403', 'BTC-USDT-200410', 'BTC-USDT-200417', 'BTC-USDT-200424', 'BTC-USDT-200501', 'BTC-USDT-200626', 'BTC-USDT-200925', 'BTC-USDT-SWAP', 'DASH-USD-SWAP', 'DASH-USDT-SWAP', 'EOS-USD-191213', 'EOS-USD-191220', 'EOS-USD-191227', 'EOS-USD-200103', 'EOS-USD-200110', 'EOS-USD-200117', 'EOS-USD-200124', 'EOS-USD-200131', 'EOS-USD-200207', 'EOS-USD-200214', 'EOS-USD-200221', 'EOS-USD-200228', 'EOS-USD-200306', 'EOS-USD-200313', 'EOS-USD-200320', 'EOS-USD-200327', 'EOS-USD-200403', 'EOS-USD-200410', 'EOS-USD-200417', 'EOS-USD-200424', 'EOS-USD-200501', 'EOS-USD-200626', 'EOS-USD-200925', 'EOS-USD-SWAP', 'EOS-USDT-191213', 'EOS-USDT-191220', 'EOS-USDT-191227', 'EOS-USDT-200103', 'EOS-USDT-200110', 'EOS-USDT-200117', 'EOS-USDT-200124', 'EOS-USDT-200131', 'EOS-USDT-200207', 'EOS-USDT-200214', 'EOS-USDT-200221', 'EOS-USDT-200228', 'EOS-USDT-200306', 'EOS-USDT-200313', 'EOS-USDT-200320', 'EOS-USDT-200327', 'EOS-USDT-200403', 'EOS-USDT-200410', 'EOS-USDT-200417', 'EOS-USDT-200424', 'EOS-USDT-200501', 'EOS-USDT-200626', 'EOS-USDT-200925', 'EOS-USDT-SWAP', 'ETC-USD-200131', 'ETC-USD-200207', 'ETC-USD-200214', 'ETC-USD-200221', 'ETC-USD-200228', 'ETC-USD-200306', 'ETC-USD-200313', 'ETC-USD-200320', 'ETC-USD-200327', 'ETC-USD-200403', 'ETC-USD-200410', 'ETC-USD-200417', 'ETC-USD-200424', 'ETC-USD-200501', 'ETC-USD-200626', 'ETC-USD-200925', 'ETC-USD-SWAP', 'ETC-USDT-200131', 'ETC-USDT-200207', 'ETC-USDT-200214', 'ETC-USDT-200221', 'ETC-USDT-200228', 'ETC-USDT-200306', 'ETC-USDT-200313', 'ETC-USDT-200320', 'ETC-USDT-200327', 'ETC-USDT-200403', 'ETC-USDT-200410', 'ETC-USDT-200417', 'ETC-USDT-200424', 'ETC-USDT-200501', 'ETC-USDT-200626', 'ETC-USDT-200925', 'ETC-USDT-SWAP', 'ETH-USD-190712', 'ETH-USD-190719', 'ETH-USD-190726', 'ETH-USD-190802', 'ETH-USD-190809', 'ETH-USD-190816', 'ETH-USD-190823', 'ETH-USD-190830', 'ETH-USD-190906', 'ETH-USD-190927', 'ETH-USD-191213', 'ETH-USD-191220', 'ETH-USD-191227', 'ETH-USD-200103', 'ETH-USD-200110', 'ETH-USD-200117', 'ETH-USD-200124', 'ETH-USD-200131', 'ETH-USD-200207', 'ETH-USD-200214', 'ETH-USD-200221', 'ETH-USD-200228', 'ETH-USD-200306', 'ETH-USD-200313', 'ETH-USD-200320', 'ETH-USD-200327', 'ETH-USD-200403', 'ETH-USD-200410', 'ETH-USD-200417', 'ETH-USD-200424', 'ETH-USD-200501', 'ETH-USD-200626', 'ETH-USD-200925', 'ETH-USD-SWAP', 'ETH-USDT-191213', 'ETH-USDT-191220', 'ETH-USDT-191227', 'ETH-USDT-200103', 'ETH-USDT-200110', 'ETH-USDT-200117', 'ETH-USDT-200124', 'ETH-USDT-200131', 'ETH-USDT-200207', 'ETH-USDT-200214', 'ETH-USDT-200221', 'ETH-USDT-200228', 'ETH-USDT-200306', 'ETH-USDT-200313', 'ETH-USDT-200320', 'ETH-USDT-200327', 'ETH-USDT-200403', 'ETH-USDT-200410', 'ETH-USDT-200417', 'ETH-USDT-200424', 'ETH-USDT-200501', 'ETH-USDT-200626', 'ETH-USDT-200925', 'ETH-USDT-SWAP', 'LINK-USD-SWAP', 'LINK-USDT-SWAP', 'LTC-USD-190712', 'LTC-USD-190719', 'LTC-USD-190726', 'LTC-USD-190802', 'LTC-USD-190809', 'LTC-USD-190816', 'LTC-USD-190823', 'LTC-USD-190830', 'LTC-USD-190906', 'LTC-USD-190927', 'LTC-USD-191213', 'LTC-USD-191220', 'LTC-USD-191227', 'LTC-USD-200103', 'LTC-USD-200110', 'LTC-USD-200117', 'LTC-USD-200124', 'LTC-USD-200131', 'LTC-USD-200207', 'LTC-USD-200214', 'LTC-USD-200221', 'LTC-USD-200228', 'LTC-USD-200306', 'LTC-USD-200313', 'LTC-USD-200320', 'LTC-USD-200327', 'LTC-USD-200403', 'LTC-USD-200410', 'LTC-USD-200417', 'LTC-USD-200424', 'LTC-USD-200501', 'LTC-USD-200626', 'LTC-USD-200925', 'LTC-USD-SWAP', 'LTC-USDT-191213', 'LTC-USDT-191220', 'LTC-USDT-191227', 'LTC-USDT-200103', 'LTC-USDT-200110', 'LTC-USDT-200117', 'LTC-USDT-200124', 'LTC-USDT-200131', 'LTC-USDT-200207', 'LTC-USDT-200214', 'LTC-USDT-200221', 'LTC-USDT-200228', 'LTC-USDT-200306', 'LTC-USDT-200313', 'LTC-USDT-200320', 'LTC-USDT-200327', 'LTC-USDT-200403', 'LTC-USDT-200410', 'LTC-USDT-200417', 'LTC-USDT-200424', 'LTC-USDT-200501', 'LTC-USDT-200626', 'LTC-USDT-200925', 'LTC-USDT-SWAP', 'NEO-USD-SWAP', 'NEO-USDT-SWAP', 'TRX-USD-191213', 'TRX-USD-191220', 'TRX-USD-191227', 'TRX-USD-200103', 'TRX-USD-200110', 'TRX-USD-200117', 'TRX-USD-200124', 'TRX-USD-200131', 'TRX-USD-200207', 'TRX-USD-200214', 'TRX-USD-200221', 'TRX-USD-200228', 'TRX-USD-200306', 'TRX-USD-200313', 'TRX-USD-200320', 'TRX-USD-200327', 'TRX-USD-200403', 'TRX-USD-200410', 'TRX-USD-200417', 'TRX-USD-200424', 'TRX-USD-200501', 'TRX-USD-200626', 'TRX-USD-200925', 'TRX-USD-SWAP', 'TRX-USDT-191213', 'TRX-USDT-191220', 'TRX-USDT-191227', 'TRX-USDT-200103', 'TRX-USDT-200110', 'TRX-USDT-200117', 'TRX-USDT-200124', 'TRX-USDT-200131', 'TRX-USDT-200207', 'TRX-USDT-200214', 'TRX-USDT-200221', 'TRX-USDT-200228', 'TRX-USDT-200306', 'TRX-USDT-200313', 'TRX-USDT-200320', 'TRX-USDT-200327', 'TRX-USDT-200403', 'TRX-USDT-200410', 'TRX-USDT-200417', 'TRX-USDT-200424', 'TRX-USDT-200501', 'TRX-USDT-200626', 'TRX-USDT-200925', 'TRX-USDT-SWAP', 'XRP-USD-191213', 'XRP-USD-191220', 'XRP-USD-191227', 'XRP-USD-200103', 'XRP-USD-200110', 'XRP-USD-200117', 'XRP-USD-200124', 'XRP-USD-200131', 'XRP-USD-200207', 'XRP-USD-200214', 'XRP-USD-200221', 'XRP-USD-200228', 'XRP-USD-200306', 'XRP-USD-200313', 'XRP-USD-200320', 'XRP-USD-200327', 'XRP-USD-200403', 'XRP-USD-200410', 'XRP-USD-200417', 'XRP-USD-200424', 'XRP-USD-200501', 'XRP-USD-200626', 'XRP-USD-200925', 'XRP-USD-SWAP', 'XRP-USDT-191213', 'XRP-USDT-191220', 'XRP-USDT-191227', 'XRP-USDT-200103', 'XRP-USDT-200110', 'XRP-USDT-200117', 'XRP-USDT-200124', 'XRP-USDT-200131', 'XRP-USDT-200207', 'XRP-USDT-200214', 'XRP-USDT-200221', 'XRP-USDT-200228', 'XRP-USDT-200306', 'XRP-USDT-200313', 'XRP-USDT-200320', 'XRP-USDT-200327', 'XRP-USDT-200403', 'XRP-USDT-200410', 'XRP-USDT-200417', 'XRP-USDT-200424', 'XRP-USDT-200501', 'XRP-USDT-200626', 'XRP-USDT-200925', 'XRP-USDT-SWAP'

**Side**:
buy, sell


### Data Sanity
No downtime.

### API Reference
**Endpoint**:
`Websocket wss://real.okex.com:8443/ws/v3`

**Futures Payload**:
`{"op": "subscribe", "args":["futures/trade:BTC-USD-190628"]`

**Swap Payload**:
`{"op": "subscribe", "args":["spot/depth:BTC-USD-SWAP"]`

**Spot Payload**:
`{"op": "subscribe", "args":["spot/depth:BTC-USD"]`


### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
symbol	|String|	Yes	| Futures symbol name


### API Response Schema
Name | Type | Description
---- | ---- | ----------
price | float | transaction price
size | float | transaction amount
timestamp	|String	|System time stamp
instrument_id	|String|	Contract ID，e.g .BTC-USD-191227 ,BTC-USDT-191227
checksum	|String	|checksum



## OKEX Open Interest Swap 
```sql
-- fetch data 
select * from okex_recentTrades limit 1 
```
> response

```json
[
    {
        'time': '2019-07-11T15:59:41.927000064Z', 
        'openInterest': '966338', 
        'symbol': 'BTC-USD-SWAP'
   }
]
```

### Description
OKEX open interest hsd s frequency of 5 minutes and data time range is from 2019-07-11 15:59:41.927000064 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
openInterest |string |
symbol | string | tag values


### Tag Values
**Futures, Spot and Swap Symbol**: 
'BCH-USD-SWAP', 'BCH-USDT-SWAP', 'BSV-USD-SWAP', 'BSV-USDT-SWAP', 'BTC-USD-SWAP', 'BTC-USDT-SWAP', 'DASH-USD-SWAP', 'DASH-USDT-SWAP', 'EOS-USD-SWAP', 'EOS-USDT-SWAP', 'ETC-USD-SWAP', 'ETC-USDT-SWAP', 'ETH-USD-SWAP', 'ETH-USDT-SWAP', 'LINK-USD-SWAP', 'LINK-USDT-SWAP', 'LTC-USD-SWAP', 'LTC-USDT-SWAP', 'NEO-USD-SWAP', 'NEO-USDT-SWAP', 'TRX-USD-SWAP', 'TRX-USDT-SWAP', 'XRP-USD-SWAP', 'XRP-USDT-SWAP


### Data Sanity
No downtime.

### API Reference
**Endpoint**:
`GET https://www.okex.com/api/swap/v3/instruments/open_interest`


### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
instrument_id	|String|	Yes	| Futures symbol name


### API Response Schema
Name | Type | Description
---- | ---- | ----------
openInterest | float | Open interest amount in USD. 
timestamp	|String	|System time stamp
instrument_id	|String|	Contract ID，e.g .BTC-USD-191227 ,BTC-USDT-191227
checksum	|String	|checksum



## OKEX Ticker
```sql
-- fetch data 
select * from okex_tikcer limit 1 
```
> response

```json
[
    {
       'time': '2019-07-11T15:59:41.463000064Z', 
       'best_ask': '100.832', 
       'best_ask_size': None, 
       'best_bid': '100.801', 
       'best_bid_size': None, 
       'expiration': 'quarterly', 
       'high_24h': '111.53', 
       'last': '100.838', 
       'last_qty': None,
       'low_24h': '95.701', 
       'open_24h': '107.153', 
       'open_interest': '3210586', 
       'symbol': 'LTC-USD-190927', 
       'volume_24h': '21717883', 
       'volume_token_24h': '2153739.959142387'
   }
]
```

### Description
[OKEX ticker](https://www.okex.com/docs/en/#futures_ws-sub) is connected through websocket and data time range is from2019-07-11 15:59:41.101000192 till now.  Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
best_ask         string
best_ask_size    string
best_bid         string
best_bid_size    string
high_24h         string
last             string
last_qty         string
low_24h          string
open_24h         string
open_interest    string
volume_24h       string
volume_token_24h string
symbol | string | tag values


### Tag Values
**Futures, Spot and Swap Symbol (Symbols are subject to change)**: 
'BCH-USD-200131', 'BCH-USD-200207', 'BCH-USD-200214', 'BCH-USD-200221', 'BCH-USD-200228', 'BCH-USD-200306', 'BCH-USD-200313', 'BCH-USD-200320', 'BCH-USD-200327', 'BCH-USD-200403', 'BCH-USD-200410', 'BCH-USD-200417', 'BCH-USD-200424', 'BCH-USD-200501', 'BCH-USD-200626', 'BCH-USD-SWAP', 'BCH-USDT-200131', 'BCH-USDT-200207', 'BCH-USDT-200214', 'BCH-USDT-200221', 'BCH-USDT-200228', 'BCH-USDT-200306', 'BCH-USDT-200313', 'BCH-USDT-200320', 'BCH-USDT-200327', 'BCH-USDT-200403', 'BCH-USDT-200410', 'BCH-USDT-200417', 'BCH-USDT-200424', 'BCH-USDT-200501', 'BCH-USDT-200626', 'BCH-USDT-SWAP', 'BSV-USD-200131', 'BSV-USD-200207', 'BSV-USD-200214', 'BSV-USD-200221', 'BSV-USD-200228', 'BSV-USD-200306', 'BSV-USD-200313', 'BSV-USD-200320', 'BSV-USD-200327', 'BSV-USD-200403', 'BSV-USD-200410', 'BSV-USD-200417', 'BSV-USD-200424', 'BSV-USD-200501', 'BSV-USD-200626', 'BSV-USD-SWAP', 'BSV-USDT-200131', 'BSV-USDT-200207', 'BSV-USDT-200214', 'BSV-USDT-200221', 'BSV-USDT-200228', 'BSV-USDT-200306', 'BSV-USDT-200313', 'BSV-USDT-200320', 'BSV-USDT-200327', 'BSV-USDT-200403', 'BSV-USDT-200410', 'BSV-USDT-200417', 'BSV-USDT-200424', 'BSV-USDT-200501', 'BSV-USDT-200626', 'BSV-USDT-SWAP', 'BTC-USD-190712', 'BTC-USD-190719', 'BTC-USD-190726', 'BTC-USD-190802', 'BTC-USD-190809', 'BTC-USD-190816', 'BTC-USD-190823', 'BTC-USD-190830', 'BTC-USD-190906', 'BTC-USD-190927', 'BTC-USD-191213', 'BTC-USD-191220', 'BTC-USD-191227', 'BTC-USD-200103', 'BTC-USD-200110', 'BTC-USD-200117', 'BTC-USD-200124', 'BTC-USD-200131', 'BTC-USD-200207', 'BTC-USD-200214', 'BTC-USD-200221', 'BTC-USD-200228', 'BTC-USD-200306', 'BTC-USD-200313', 'BTC-USD-200320', 'BTC-USD-200327', 'BTC-USD-200403', 'BTC-USD-200410', 'BTC-USD-200417', 'BTC-USD-200424', 'BTC-USD-200501', 'BTC-USD-200626', 'BTC-USD-SWAP', 'BTC-USDT-191213', 'BTC-USDT-191220', 'BTC-USDT-191227', 'BTC-USDT-200103', 'BTC-USDT-200110', 'BTC-USDT-200117', 'BTC-USDT-200124', 'BTC-USDT-200131', 'BTC-USDT-200207', 'BTC-USDT-200214', 'BTC-USDT-200221', 'BTC-USDT-200228', 'BTC-USDT-200306', 'BTC-USDT-200313', 'BTC-USDT-200320', 'BTC-USDT-200327', 'BTC-USDT-200403', 'BTC-USDT-200410', 'BTC-USDT-200417', 'BTC-USDT-200424', 'BTC-USDT-200501', 'BTC-USDT-200626', 'BTC-USDT-SWAP', 'EOS-USD-191213', 'EOS-USD-191220', 'EOS-USD-191227', 'EOS-USD-200103', 'EOS-USD-200110', 'EOS-USD-200117', 'EOS-USD-200124', 'EOS-USD-200131', 'EOS-USD-200207', 'EOS-USD-200214', 'EOS-USD-200221', 'EOS-USD-200228', 'EOS-USD-200306', 'EOS-USD-200313', 'EOS-USD-200320', 'EOS-USD-200327', 'EOS-USD-200403', 'EOS-USD-200410', 'EOS-USD-200417', 'EOS-USD-200424', 'EOS-USD-200501', 'EOS-USD-200626', 'EOS-USD-SWAP', 'EOS-USDT-191213', 'EOS-USDT-191220', 'EOS-USDT-191227', 'EOS-USDT-200103', 'EOS-USDT-200110', 'EOS-USDT-200117', 'EOS-USDT-200124', 'EOS-USDT-200131', 'EOS-USDT-200207', 'EOS-USDT-200214', 'EOS-USDT-200221', 'EOS-USDT-200228', 'EOS-USDT-200306', 'EOS-USDT-200313', 'EOS-USDT-200320', 'EOS-USDT-200327', 'EOS-USDT-200403', 'EOS-USDT-200410', 'EOS-USDT-200417', 'EOS-USDT-200424', 'EOS-USDT-200501', 'EOS-USDT-200626', 'EOS-USDT-SWAP', 'ETC-USD-200131', 'ETC-USD-200207', 'ETC-USD-200214', 'ETC-USD-200221', 'ETC-USD-200228', 'ETC-USD-200306', 'ETC-USD-200313', 'ETC-USD-200320', 'ETC-USD-200327', 'ETC-USD-200403', 'ETC-USD-200410', 'ETC-USD-200417', 'ETC-USD-200424', 'ETC-USD-200501', 'ETC-USD-200626', 'ETC-USD-SWAP', 'ETC-USDT-200131', 'ETC-USDT-200207', 'ETC-USDT-200214', 'ETC-USDT-200221', 'ETC-USDT-200228', 'ETC-USDT-200306', 'ETC-USDT-200313', 'ETC-USDT-200320', 'ETC-USDT-200327', 'ETC-USDT-200403', 'ETC-USDT-200410', 'ETC-USDT-200417', 'ETC-USDT-200424', 'ETC-USDT-200501', 'ETC-USDT-200626', 'ETC-USDT-SWAP', 'ETH-USD-190712', 'ETH-USD-190719', 'ETH-USD-190726', 'ETH-USD-190802', 'ETH-USD-190809', 'ETH-USD-190816', 'ETH-USD-190823', 'ETH-USD-190830', 'ETH-USD-190906', 'ETH-USD-190927', 'ETH-USD-191213', 'ETH-USD-191220', 'ETH-USD-191227', 'ETH-USD-200103', 'ETH-USD-200110', 'ETH-USD-200117', 'ETH-USD-200124', 'ETH-USD-200131', 'ETH-USD-200207', 'ETH-USD-200214', 'ETH-USD-200221', 'ETH-USD-200228', 'ETH-USD-200306', 'ETH-USD-200313', 'ETH-USD-200320', 'ETH-USD-200327', 'ETH-USD-200403', 'ETH-USD-200410', 'ETH-USD-200417', 'ETH-USD-200424', 'ETH-USD-200501', 'ETH-USD-200626', 'ETH-USD-SWAP', 'ETH-USDT-191213', 'ETH-USDT-191220', 'ETH-USDT-191227', 'ETH-USDT-200103', 'ETH-USDT-200110', 'ETH-USDT-200117', 'ETH-USDT-200124', 'ETH-USDT-200131', 'ETH-USDT-200207', 'ETH-USDT-200214', 'ETH-USDT-200221', 'ETH-USDT-200228', 'ETH-USDT-200306', 'ETH-USDT-200313', 'ETH-USDT-200320', 'ETH-USDT-200327', 'ETH-USDT-200403', 'ETH-USDT-200410', 'ETH-USDT-200417', 'ETH-USDT-200424', 'ETH-USDT-200501', 'ETH-USDT-200626', 'ETH-USDT-SWAP', 'LTC-USD-190712', 'LTC-USD-190719', 'LTC-USD-190726', 'LTC-USD-190802', 'LTC-USD-190809', 'LTC-USD-190816', 'LTC-USD-190823', 'LTC-USD-190830', 'LTC-USD-190906', 'LTC-USD-190927', 'LTC-USD-191213', 'LTC-USD-191220', 'LTC-USD-191227', 'LTC-USD-200103', 'LTC-USD-200110', 'LTC-USD-200117', 'LTC-USD-200124', 'LTC-USD-200131', 'LTC-USD-200207', 'LTC-USD-200214', 'LTC-USD-200221', 'LTC-USD-200228', 'LTC-USD-200306', 'LTC-USD-200313', 'LTC-USD-200320', 'LTC-USD-200327', 'LTC-USD-200403', 'LTC-USD-200410', 'LTC-USD-200417', 'LTC-USD-200424', 'LTC-USD-200501', 'LTC-USD-200626', 'LTC-USD-SWAP', 'LTC-USDT-191213', 'LTC-USDT-191220', 'LTC-USDT-191227', 'LTC-USDT-200103', 'LTC-USDT-200110', 'LTC-USDT-200117', 'LTC-USDT-200124', 'LTC-USDT-200131', 'LTC-USDT-200207', 'LTC-USDT-200214', 'LTC-USDT-200221', 'LTC-USDT-200228', 'LTC-USDT-200306', 'LTC-USDT-200313', 'LTC-USDT-200320', 'LTC-USDT-200327', 'LTC-USDT-200403', 'LTC-USDT-200410', 'LTC-USDT-200417', 'LTC-USDT-200424', 'LTC-USDT-200501', 'LTC-USDT-200626', 'LTC-USDT-SWAP', 'TRX-USD-191213', 'TRX-USD-191220', 'TRX-USD-191227', 'TRX-USD-200103', 'TRX-USD-200110', 'TRX-USD-200117', 'TRX-USD-200124', 'TRX-USD-200131', 'TRX-USD-200207', 'TRX-USD-200214', 'TRX-USD-200221', 'TRX-USD-200228', 'TRX-USD-200306', 'TRX-USD-200313', 'TRX-USD-200320', 'TRX-USD-200327', 'TRX-USD-200403', 'TRX-USD-200410', 'TRX-USD-200417', 'TRX-USD-200424', 'TRX-USD-200501', 'TRX-USD-200626', 'TRX-USD-SWAP', 'TRX-USDT-191213', 'TRX-USDT-191220', 'TRX-USDT-191227', 'TRX-USDT-200103', 'TRX-USDT-200110', 'TRX-USDT-200117', 'TRX-USDT-200124', 'TRX-USDT-200131', 'TRX-USDT-200207', 'TRX-USDT-200214', 'TRX-USDT-200221', 'TRX-USDT-200228', 'TRX-USDT-200306', 'TRX-USDT-200313', 'TRX-USDT-200320', 'TRX-USDT-200327', 'TRX-USDT-200403', 'TRX-USDT-200410', 'TRX-USDT-200417', 'TRX-USDT-200424', 'TRX-USDT-200501', 'TRX-USDT-200626', 'TRX-USDT-SWAP', 'XRP-USD-191213', 'XRP-USD-191220', 'XRP-USD-191227', 'XRP-USD-200103', 'XRP-USD-200110', 'XRP-USD-200117', 'XRP-USD-200124', 'XRP-USD-200131', 'XRP-USD-200207', 'XRP-USD-200214', 'XRP-USD-200221', 'XRP-USD-200228', 'XRP-USD-200306', 'XRP-USD-200313', 'XRP-USD-200320', 'XRP-USD-200327', 'XRP-USD-200403', 'XRP-USD-200410', 'XRP-USD-200417', 'XRP-USD-200424', 'XRP-USD-200501', 'XRP-USD-200626', 'XRP-USD-SWAP', 'XRP-USDT-191213', 'XRP-USDT-191220', 'XRP-USDT-191227', 'XRP-USDT-200103', 'XRP-USDT-200110', 'XRP-USDT-200117', 'XRP-USDT-200124', 'XRP-USDT-200131', 'XRP-USDT-200207', 'XRP-USDT-200214', 'XRP-USDT-200221', 'XRP-USDT-200228', 'XRP-USDT-200306', 'XRP-USDT-200313', 'XRP-USDT-200320', 'XRP-USDT-200327', 'XRP-USDT-200403', 'XRP-USDT-200410', 'XRP-USDT-200417', 'XRP-USDT-200424', 'XRP-USDT-200501', 'XRP-USDT-200626', 'XRP-USDT-SWAP'


### Data Sanity
No downtime.

### API Reference
**Endpoint**:
`Websocket wss://real.okex.com:8443/ws/v3`

**Futures Payload**:
`{"op": "subscribe", "args":["futures/ticker:BTC-USD-190628"]`

**Swap Payload**:
`{"op": "subscribe", "args":["swap/ticker:BTC-USD-SWAP"]`


### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
symbol	|String|	Yes	| Futures symbol name

### API Response Schema
No information



## OKEX Ticker Swap
```sql
-- fetch data 
select * from okex_tikcer_swap limit 1 
```
> response

```json
[
    {
       'time': '2020-01-29T18:49:08.165409534Z', 
       'changePercent': '0.0429', 
       'close': '9365', 
       'coinName': 'BTC', 
       'coinVolume': '76997.5945', 
       'contractId': '100', 
       'current_snapshot': '2020-01-29 18:46:56.538472', 
       'high': '9444', 
       'holdAmount': '2264193', 
       'low': '8964', 
       'open': '8979.5', 
       'symbol': 'BTC-USD-SWAP', 
       'type': 'USD', 
       'unitAmount': '100', 
       'volume': '7166582'
   }
]
```

### Description
OKEX ticker swap has a frequency of 1 second and data time range is from 2020-01-29 18:49:08.165409534 till now. Collectors are continously runing in two hosts. OKEX ticker swap is redundantly collection of OKEX ticker.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
changePercent    |string|
close            |string|
coinName         |string|
coinVolume       |string|
contractId       |string|
current_snapshot |string|
high             |string|
holdAmount       |string| Open Interest
low              |string|
open             |string|
symbol           |string|
type             |string|
unitAmount       |string|
volume           |string|
symbol | string | 


### Data Sanity
No downtime.

### API Reference
**Endpoint**
`POST https://www.okex.com/v2/perpetual/pc/public/contracts/tickers?type={}`

**Payload**
`{"symbol":symbol}`

### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
symbol	|String|	Yes	| Futures symbol name

### API Response Schema
No information


## OKEX Ticker V1
```sql
-- fetch data 
select * from okex_tikcer_v1 limit 1 
```
> response

```json
[
    {
       'time': '2019-12-20T00:50:58.201236084Z', 
       'buy': 7076.8, 
       'changePercent': -2.2865, 
       'coinVolume': 14709.1511, 
       'contractId': 201912201100018, 
       'contractType': 1, 
       'current_snapshot': '2019-12-20 00:49:39.666432', 
       'dayHigh': 0, 
       'dayLow': 0, 
       'high': 7253.9, 
       'holdAmount': 30918937, 
       'last': 7076.9, 
       'limitHigh': '7285.4', 
       'limitLow': '6860.5', 
       'low': 7046.3, 
       'markPrice': 7076, 
       'open_interest': 3091.8937, 
       'sell': 7077.5, 
       'status': 2, 
       'symbol': 'BTC-USDT-191220', 
       'unitAmount': 0.0001, 
       'usdCnyRate': 7.029, 
       'volume': 147091511
   }
]
```

### Description
OKEX ticker new version has frequency of 1 second and data time range is from 2019-12-20 00:50:58.201236084 till now. Collectors are continously runing in two hosts. OKEX ticker new version include coin denominatd open interest. 

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
buy              |float|
changePercent    |float|
coinVolume       |float|
contractId       |integer|
contractType     |integer|
current_snapshot |string|
dayHigh          |float|
dayLow           |float|
high             |float|
holdAmount       |integer|
last             |float|
limitHigh        |string|
limitLow         |string|
low              |float|
markPrice        |float|
open_interest    |float| Coin denominated open interest
sell             |float|
status           |integer|
symbol           |string|
unitAmount       |float|
usdCnyRate       |float|
volume           |float|



### Data Sanity
No downtime.

### API Reference
**Endpoint**
`POST https://www.okex.com/v2/futures/pc/market/tickers.do`

**Payload**
`{"symbol":symbol}`

### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
symbol	|String|	Yes	| Futures symbol name

### API Response Schema
No information



# Poloniex
[Poloniex](https://poloniex.com/) is a cryptocurrency exchange. Check their [api](https://docs.poloniex.com/#introduction).

## Poloniex Funding Orderbook
```sql
-- fetch data
select * from poloniex_funding_orderbook limit 1 
```
> response

```json
[
    {
       'time': '2019-10-18T20:41:17.431642305Z', 
       'amount': '4.34079922', 
       'rangeMax': 2, 
       'rangeMin': 2, 
       'rate': '0.00025000', 
       'symbol': 'ATOM', 
       'timestamp': None, 
       'type': 'offers'
   }
]
```

### Description
[Poloniex funding orderbook](https://docs.poloniex.com/#returnloanorders) has a frequency of 1 minute and data time range is from 2019-10-18 20:41:17.431642305 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
amount    |string|
rangeMax  |integer|
rangeMin  |integer|
rate      |string|
timestamp |string|
type      |string|
symbol | string | tag values

### Tag Values
**symbol**: 
ATOM, BCHABC, BCHSV, BTC, DASH, DOGE, EOS, ETC, ETH, LTC, STR, TRX, USDC, USDT, XMR, XRP

### Data Sanity
No downtime.

### API Reference
`GET https://poloniex.com/public?command=returnOrderBook&currencyPair={}&depth=100`

### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
symbol	|String|	Yes	| Symbol name
depth | string | Yes | Market depth

### API Response Schema
Name | Type | Description
---- | ---- | ----------
rate	| string |The interest rate in percentage per day charged for this loan.
amount	| string |The total number of units available at this rate and within this range.
rangeMin	| integer  |The lowest duration in days offered by the loans within this group.
rangeMax	|  integer |The highest duration in days offered by the loans within this group.


## Poloniex Leaderboard
```sql
-- fetch data
select * from poloniex_leaderboard limit 1 
```
> response

```json
[
        {
            'time': '2020-01-22T18:44:07.917126986Z', 
            'account': '10****83', 
            'current_snapshot': '2020-01-22T18:00:00.000Z', 
            'net_deposit': '7000001.00000000', 
            'rank': '1', 
            'rank_change': 0
          }
]
```

### Description
[Poloniex leaderboard](https://poloniex.com/leaderboard/matic-trading-competition) has a frequency of 1 hour and data time range is from 2020-01-22T18:44:07.917126986Z to 2020-02-17 21:39:25. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
account          string
current_snapshot string
net_deposit      string
rank             string
rank_change      integer

### Data Sanity
No downtime.

### Webscrapy
The data is collected thourgh webscrapying.



## Poloniex Trades
```sql
-- fetch data
select * from poloniex_trades limit 1 
```
> response

```json
[
    {
       'time': '2020-04-03T04:14:20.052070509Z', 
       'amount': 2.40343333, 
       'date': '2020-04-03 03:02:23', 
       'globalTradeID': 457133708, 
       'orderNumber': 12065214, 
       'price': 0.6609214, 
       'symbol': 'USDT_SNX', 
       'total': 1.58848052, 
       'tradeID': 1752, 
       'type': 'buy'
   }
]
```

### Description
[Poloniex trade](https://docs.poloniex.com/#returntradehistory-public) has a frequency of 10 minutes and data time range is from 2019-10-18 20:41:17.431642305 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
amount        float
date          string
globalTradeID integer
orderNumber   integer
price         float
total         float
tradeID       integer
type          string
symbol | string | tag values

### Tag Values
**symbol**: 
BTC_SNX, TRX_SNX, USDT_SNX

### Data Sanity
No downtime.

### API Reference
`GET https://poloniex.com/public?command=returnTradeHistory&currencyPair={}&start={}&end={}`

### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
symbol	|String|	Yes	| Symbol name
startTime | string | No | Start timestamp
endTime | string | No | End timestamp

### API Response Schema
Name | Type | Description
---- | ---- | ----------
globalTradeID	| int | The globally unique ID associated with this trade.
tradeID	| int  |The ID unique only to this currency pair associated with this trade.
date	| string  |The UTC date and time of the trade execution.
type	| string  | Designates this trade as a buy or a sell from the side of the taker.
rate	|  float |The price in base currency for this asset.
amount	|  float |The number of units transacted in this trade.
total	| float | The total price in base units for this trade.


## Poloniex Orderbook
```sql
-- fetch data
select * from poloniex_orderbook limit 1 
```
> response

```json
[
    {
       'time': '2020-04-03T01:40:20.696600872Z', 
       'amount': 99.31426668, 
       'price': 0.64999999, 
       'symbol': 'USDT_SNX', 
       'timestamp': '2020-04-03 01:40:20.648743', '
       'type': 'asks'
   }
]
```

### Description
[Poloniex orderbook](https://docs.poloniex.com/#returntradehistory-public) has a frequency of 30 seconds and data time range is from 2020-04-03T01:40:20.696600872Z till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
amount    float
price     float
timestamp string
type      string
symbol | string | tag values

### Tag Values
**symbol**: 
BTC_SNX, TRX_SNX, USDT_SNX

### Data Sanity
No downtime.

### API Reference
`GET https://poloniex.com/public?command=returnOrderBook&currencyPair={}&depth=100`

### API Query Parameters
Name | Type | Required | Description
-----| --------| ----------| --------- |
currencyPair|string|Yes|A pair like BTC_ETH or all
depth |int|No|Default depth is 50. Max depth is 100.

### API Response Schema
Name | Type | Description
---- | ---- | ----------
asks|float|	An array of price aggregated offers in the book ordered from low to high price.
bids|float| An array of price aggregated bids in the book ordered from high to low price.
isFrozen|boolean|	Indicates if trading the market is currently disabled or not.
seq	|int|An always-incrementing sequence number for this market.



# WazirX
[WazirX](https://wazirx.com/) is a cryptocurrency exchange in India. The [api](https://github.com/WazirX/wazirx-api) is listed.

## WazirX Tickers 
```sql
-- fetch data
select * from wazirx_tickers
```

> response

```json
[

 {
   "time": "2020-04-02 17:50:00",
   "buy":527000,
   "high": 529536,
   "last": 527156,
   "low": 490000,
   "open": 494950,
   "sell":528000,
   "symbol": "BTC/INR",
   "type": "SPOT",
   "volume": 69.6269
 }

]
```

### Description
WazirX tickres has a frequency of 1 hour and data time range is from 2020-04-02 17:50:00 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
buy      |float|
high     |float|
last     |float|
low      |float|
open     |float|
sell     |float|
type     |string|
volume   |float|
symbol | string | tag values

### Tag Values
Symbols are BTC/INR, XRP/INR, ETH/INR, USDT/INR, WRX/INR, MATIC/INR, LTC/INR, XRP/BTC, TRX/BTC, ETH/BTC, NCASH/BTC, ZIL/BTC, BAT/BTC, LTC/BTC, QKC/BTC, NPXS/BTC, DASH/BTC, FUN/BTC, GNT/BTC, IOST/BTC, NULS/BTC, OMG/BTC, POE/BTC, REQ/BTC, SNT/BTC, STORM/BTC, SUB/BTC, THETA/BTC, ZRX/BTC, EOS/BTC, ICX/BTC, HOT/BTC, POLY/BTC, PAX/BTC, USDC/BTC, XLM/BTC, BTT/BTC, FET/BTC, CELR/BTC, MATIC/BTC, ADA/BTC, RVN/BTC, XMR/BTC, ATOM/BTC, BNB/BTC, WRX/BTC, BTC/USDT, TRX/USDT, XRP/USDT, EOS/USDT, ETH/USDT, ICX/USDT, LTC/USDT, TUSD/USDT, NPXS/USDT, HOT/USDT, BANCA/USDT, BAT/USDT, DASH/USDT, NCASH/USDT, QKC/USDT, ZIL/USDT, ZRX/USDT, BCHABC/USDT, BCHSV/USDT, PAX/USDT, USDC/USDT, OMG/USDT, POLY/USDT, DENT/USDT, IOST/USDT, STORM/USDT, FUN/USDT, POE/USDT, GNT/USDT, SNT/USDT, THETA/USDT, REQ/USDT, SUB/USDT, CS/USDT, OCN/USDT, ZCO/USDT, STQ/USDT, XLM/USDT, XTZ/USDT, BTT/USDT, FET/USDT, TFUEL/USDT, CELR/USDT, MATIC/USDT, ADA/USDT, RVN/USDT, XMR/USDT, ATOM/USDT, ALGO/USDT, LINK/USDT, QTUM/USDT, ETC/USDT, IOTA/USDT, ZEC/USDT, WAVES/USDT, FTM/USDT, ENJ/USDT, LSK/USDT, STEEM/USDT, XVG/USDT, LOOM/USD, MANA/USDT, REP/USDT, FUEL/USDT, BLZ/USDT, XZC/USDT, NANO/USDT, SC/USDT, BTG/USDT, XEM/USDT, BTS/USDT, ARDR/USDT, STRAT/USDT, NAS/USDT, WIN/USDT, BNB/USDT, CHZ/USDT, WRX/USDT, KAVA/USDT, ANKR/USDT.

### Data Sanity
No downtime.

### API Reference
`GET https://api.wazirx.com/api/v2/tickers`

### API Query Parameters
Not required.

### API Response Schema
Fields	|Type	|Description
--------| ----| ----------|
base_unit | string |ticker code of base market
quote_unit| string | ticker code of quote asset
low | string | 24 hrs lowest price of base asset
high | string | 24 hrs highest price of base asset
last | string | Last traded price in current market
open | string | Market Open price 24hrs ago
volume | string | Last 24hrs traded volume
sell | string | Top ask order price
buy | string | Top bid order price
name | string | Display text of market
at | string  | Timestamp when ticker information is fetched



# Cosmos
[Cosmos](https://cosmos.network/) is a blockchain platform. Check their [api](https://docs.cosmos.network/).

## Cosmos Validator Ranking 
```sql
-- fetch data
select * from cosmos_validator_ranking limit 1
```
> response

```json
[

{
'time': '2020-01-14T22:11:55.440187916Z', 
'consensus_pubkey': 'cosmosvalconspub1zcjduepq6fpkt3qn9xd7u44478ypkhrvtx45uhfj3uhdny420hzgsssrvh3qnzwdpe', 
'current_snapshot': '2020-01-14 22:10:05.695135', 'delegator_shares': '13024650451734.000000000000000000', 
'details': 'We are the leading staking service provider for blockchain projects. Join our community to help secure networks and earn rewards. We know staking.', 
'identity': '90B597A673FC950E', 
'jailed': False, 
'keybase_url': 'https://s3.amazonaws.com/keybase_processed_uploads/e1378cd4d5203ded716906687ad53905_360_360.jpg', 
'max_change_rate': '0.010000000000000000', 
'max_rate': '1.000000000000000000', 
'min_self_delegation': '1', 
'moniker': 'stake.fish', 
'operator_address': 'cosmosvaloper1sjllsnramtg3ewxqwwrwjxfgc4n4ef9u2lcnj0', 
'rank': 1, 'rate': '0.040000000000000000', 
'status': 2, 
'tokens': '13024650451734', 
'unbonding_height': '0', 
'unbonding_time': '1970-01-01T00:00:00Z', 
'update_time': '2019-03-13T23:00:00Z', 
'uptime_address': 'AC2D56057CD84765E6FBE318979093E8E44AA18F', 
'uptime_missed_blocks': 0, 
'uptime_over_blocks': 100, 
'website': 'stake.fish'
}

]
```

### Description
Cosmos validator ranking has a frequency of 12 hours and data time range is from 2020-01-14 22:55:4400 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
consensus_pubkey     |string|
current_snapshot     |string|
delegator_shares     |string|
details              |string|
identity             |string|
jailed               |boolean|
keybase_url          |string|
max_change_rate      |string|
max_rate             |string|
min_self_delegation  |string|
moniker              |string|
operator_address     |string|
rank                 |integer|
rate                 |string|
status               |integer|
tokens               |string|
unbonding_height     |string|
unbonding_time       |string|
update_time          |string|
uptime_address       |string|
uptime_missed_blocks |integer|
uptime_over_blocks   |integer|
website              |string|

### Data Sanity
No downtime.

### API Reference
`GET https://api.cosmostation.io/v1/staking/validators`

### API Query Parameters
Not required.

### API Response Schema
No information.


## Cosmos Validator Status
```sql
-- fetch data
select * from cosmos_validator_status limit 1
```
> response

```json
[

{
'time': '2020-01-14T22:09:52.259536896Z', 
'block_height': 419669, 
'block_time': 7.110479, 
'bonded_tokens': 185528854760059, 
'chain_id': 'cosmoshub-3', 
'jailed_validator_num': 103, 
'not_bonded_tokens': 3038646508792, 
'total_circulating_tokens': 188567501268851, 
'total_supply_tokens': 250002065076468, 
'total_txs_num': 101530, 
'total_validator_num': 228, 
'unjailed_validator_num': 125
}

]
```

### Description
Cosmos validator status has a frequency of 12 hours and data time range is from 2020-01-14 22:55:4400 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
block_height             |integer|
block_time               |float|
bonded_tokens            |integer|
chain_id                 |string|
jailed_validator_num     |integer|
not_bonded_tokens        |integer|
total_circulating_tokens |integer|
total_supply_tokens      |integer|
total_txs_num            |integer|
total_validator_num      |integer|
unjailed_validator_num   |integer|

### Data Sanity
No downtime.

### API Reference
`GET https://api.cosmostation.io/v1/status`

### API Query Parameters
Not required.

### API Response Schema
No information.

# Hashpool
[Hashpool](https://hashpool.com/) is blockchain. Check their [api](https://support.hashpool.com/article/api-documents/).

## Hashpool Coins
```sql
-- fetch data
select * from hashpool_coins limit 1
```
> response

```json
[

      {     
          'time': '2020-04-08T17:21:32.267377023Z', 
          'coin': 'TRB', 
          'fee': 5, 
          'netHashRate': 15.35, 
          'netHashRateUnit': 'TH/s', 
          'payoutThreshould': 1, 
          'poolHashRate': 4.06, 
          'poolHashRateUnit': 'TH/s', 
          'sort': 700
      }
]
```

### Description
[Hsahpool coins](https://hashpool.com/) has a frequency of 1 hour and data time range is from 2020-04-08 17:21:32.267377023 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
coin             string
fee              float
netHashRate      float
netHashRateUnit  string
payoutThreshould float
poolHashRate     float
poolHashRateUnit string
sort             integer

### Data Sanity
No downtime.

### API Reference
`GET https://hashpool.com/api/blocks/{coin}?offset=0&limit=50`

### API Query Parameters
Name | Type | Description 
---- | ---- |----------
coin |  string | Coin symbol

### API Response Schema
Name | Type | Description 
---- | ---- | ----------
coin | string  |Coin symbol
fee |  float |  Pool mining fee percent
minPay| int | Minimum payout
poolHashrate |float | Hashrate of hashpool
poolHashrateUnit | string  |  The unit of pool hashrate
netHashrate | float  |  Total hashrate of network
netHashrateUnit | string | The unit of network hashrate



# HNScan
[HNSCAN](https://hnscan.com/) is a blockchain and they have issued token called HNS. 

## HNScan Blockchain
```sql
-- fetch data
select * from hnscan_block_info limit 1
```
> response

```json
[

      {     
          'time': '2020-03-04T23:19:29.759560883Z', 
          'averageFee': 36500, 
          'bits': 436425535, 
          'chainwork': '000000000000000000000000000000000000000000000001fb05f10db38c926e', 
          'coinbase': '6632706f6f6c;0eaeb63ca16e32df;0000000000000000', 
          'confirmations': 1, 
          'difficulty': 5045429.038128846, 
          'fees': 292000, 
          'hash': '00000000000000c09cac081eab89f6a784af4a008a9cf47e06c946a55883d2d9', 
          'height': 4853, 
          'mask': '0000000000000000000000000000000000000000000000000000000000000000', 
          'medianTime': 1583361324, 
          'merkleRoot': 'a90bfb87d502095d9e06a2a470d48759b518403c10a09c026d35c745f8518d6b', 
          'miner': 'hs1qqzlmrc6phwz2drwshstcr30vuhjacv5z0u2x9l', 
          'nextHash': None, 
          'nonce': 4189087, 
          'prevBlock': '0000000000000154466ef6ed90a0254dc50074bba469189c39ec7077ab760452', 
          'reservedRoot': '0000000000000000000000000000000000000000000000000000000000000000', 
          'size': 4540, 
          'strippedSize': 2797, 
          'treeRoot': '197fcbc1c0f5acea51221800ec407299b57b73a65e900276644f8d1360b4c332', 
          'txs': 8, 
          'version': 0, 
          'weight': 12931, 
          'witnessRoot': 'c832921f2811a66ecf5e614953caeccef5c1ef5725efe74e785d83969eb850c5'
      }
]
```

### Description
[Hnscan block info](https://hnscan.com/blocks) has a freqeuncy of 1 hour and data time range is from 2020-03-04 23:19:29.759560883 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
averageFee    |integer|
bits          |integer|
chainwork     |string|
coinbase      |string|
confirmations |integer|
difficulty    |float|
fees          |integer
hash          |string
height        |integer|
mask          |string|
medianTime    |integer|
merkleRoot    |string|
miner         |string|
nextHash      |string|
nonce         |integer|
prevBlock     |string|
reservedRoot  |string|
size          |integer|
strippedSize  |integer|
treeRoot      |string|
txs           |integer|
version       |integer|
weight        |integer|
witnessRoot   |string|

### Data Sanity
No downtime.

### API Reference
`GET https://api.hnscan.com/blocks/?offset={}&limit={}`

### API Query Parameters
Name | Type | Description 
---- | ---- |----------
offset | int | how far to gp back
limit | int | number of return data

### API Response Schema
No information. 


## HNScan Chart 
```sql
-- fetch data
select * from hnscan_chart_data limit 1
```
> response

```json
[

      {     
          'time': '2019-04-04T00:00:00Z', 
          'burned': 0, 
          'daily_tx': 182, 
          'difficulty': 0.026332745837485908, 
          'supply': 366373.032008, 
          'total_tx': 181
      }
]
```

### Description
[Hnscan chart](https://hnscan.com/charts) has a freqeuncy of 1 day and data time range is from 2019-04-04 00:00:00  till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
burned     |float|
daily_tx   |integer|
difficulty |float|
supply     |float|
total_tx   |integer|

### Data Sanity
No downtime.

### API Reference
**Difficulty**:
`GET https://api.hnscan.com/charts/difficulty?endTime={}&startTime={}`

**DailyTX**:
`GET https://api.hnscan.com/charts/dailyTransactions?endTime={}&startTime={}`

**DailyTotalTx**:
`GET https://api.hnscan.com/charts/dailyTotalTransactions?endTime={}&startTime={}`

**Supply**:
`GET https://api.hnscan.com/charts/supply?endTime={}&startTime={}`

**Burned**:
`GET https://api.hnscan.com/charts/burned?endTime={}&startTime={}`

### API Query Parameters
Name | Type | Description 
---- | ---- |----------
startTime | int | start timestamp
endTime | int | end timestamp

### API Response Schema
No information. 



## HNScan Summary
```sql
-- fetch data
select * from hnscan_summary limit 1
```
> response

```json
[

      {     
          'time': '2020-02-07T04:34:02.057248932Z', 
          'chainWork': '000000000000000000000000000000000000000000000000073571d46064ea4b', 
          'difficulty': 532765.0078885447, 
          'hashrate': 4064061692099.727, 
          'network': 'main', 
          'registeredNames': 0, 
          'unconfirmed': 0, 
          'unconfirmedSize': 0
      }
]
```

### Description
Hnscan summary has a freqeuncy of 9 minutes and data time range is from 2020-02-07 04:34:02.057248932 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
chainWork       |string|
difficulty      |float|
hashrate        |float|
network         |string|
registeredNames |integer|
unconfirmed     |integer|
unconfirmedSize |integer|

### Data Sanity
No downtime.

### API Reference
`GET https://api.hnscan.com/summary`

### API Query Parameters
Not required.

### API Response Schema
No information. 



## HNScan Status 
```sql
-- fetch data
select * from hnscan_status limit 1
```
> response

```json
[

      {     
          'time': '2020-03-03T22:11:31.390484993Z', 
          'agent': '/hsd:2.0.2/', 
          'connections': 155, 
          'difficulty': 3858106.8013179735, 
          'height': 4688, 
          'host': '138.68.61.31',
          'key': 'aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa', 
          'network': 'main', 
          'port': 12038, 
          'progress': 1, 
          'totalBytesRecv': 348831794, 
          'totalBytesSent': 770841723, 
          'uptime': 1569528, 
          'version': '0.0.0'}
      }
]
```

### Description
[Hnscan status](https://hnscan.com/status) has a freqeuncy of 9 minutes and data time range is from2020-03-03 22:11:31.390484993 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
agent          |string |
connections    |integer| 
difficulty     |float|
height         |integer |
host           |string|
key            |string|
network        |string|
port           |integer |
progress       |integer |
totalBytesRecv |integer |
totalBytesSent |integer |
uptime         |integer |
version        |string |

### Data Sanity
No downtime.

### API Reference
`GET https://api.hnscan.com/status/`

### API Query Parameters
Not required.

### API Response Schema
No information. 






# Namebase
[Namebase](https://www.namebase.io/) is a platform that can either trade crypto currency HNS or auction on website domian. Check their [api](https://github.com/namebasehq/exchange-api-documentation/blob/master/rest-api.md).

## Namebase Domain
```sql
-- fetch data
select * from namebase_domain limit 1
```
> response

```json
[

      {     
               'time': '2020-03-04T05:11:02.647999179Z', 
               'close_amount': None, 
               'current_snapshot': None, 
               'domain_type': 'bid_now', 
               'name': 'yang', 
               'release_block': None, 
               'reveal_block': 4791, 
               'total_number_bids': 21
      }
]
```

### Description
[Namebase domain](https://www.namebase.io/domains) has a frequency of 9 hours and data time range is from 2020-03-04 05:11:02.647999179 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
close_amount      |string|
current_snapshot  |integer|
name              |string|
release_block     |integer|
reveal_block      |integer|
total_number_bids |integer|
domain_type  |string | tag values

### Tag Values
**Domain Type**:
bid_now, ending_soon, ending_soon, recently_sold


### Data Sanity
No downtime.

### API Reference
**Popular**:
`https://www.namebase.io/api/domains/popular/{}`

**Ending Soon**:
`https://www.namebase.io/api/domains/ending-soon/{}`

**Anticipated**:
`https://www.namebase.io/api/domains/anticipated/{}`

**Recently Sold**:
`https://www.namebase.io/api/domains/recently-sold/{}`

### API Query Parameters
Name | Type | Description 
---- | ---- |----------
page |  string | All available web pages.

### API Response Schema
No information.


## Namebase Trade
```sql
-- fetch data
select * from namebase_trade limit 1
```
> response

```json
[

      {     
            'time': '2020-02-06T22:21:18.460645367Z', 
            'createdAt': 1581027120481, 
            'isBuyerMaker': False, 
            'price': 5.95e-05, 
            'quantity': 458.960337, 
            'quoteQuantity': 0.02730814, 
            'symbol': 'HNSBTC', 
            'tradeId': 1571
      }
]
```

### Description
[Namebase domain](https://github.com/namebasehq/exchange-api-documentation/blob/master/rest-api.md) has a frequency of 5 minutes and data time range is from 2020-02-06 22:21:18.460645367 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
createdAt     |integer|
isBuyerMaker  |boolean|
price         |float|
quantity      |float|
quoteQuantity |float|
tradeId       |integer|
symbol | string | Tag Values

### Tag Values
**Symbol**: HNSBTC

### Data Sanity
No downtime.

### API Reference
`GET https://www.namebase.io/api/v0/trade?symbol={}&timestamp={}&receiveWindow=1000&limit=1000`

### API Query Parameters
Name | Type | Mandatory | Description 
---- | ---- |----------- | --------
symbol	|STRING|	YES	
tradeId	|LONG|	NO	|Trade id to fetch from. Default gets most recent trades.
limit	|INT|	NO	|Default 100; max 1000.
receiveWindow	|LONG	|NO	
timestamp	|LONG	|YES

### API Response Schema
**Response**:
```json
[
  {
    "tradeId": 28457,
    "price": "0.00003000",
    "quantity": "500.000000",
    "quoteQuantity": "0.01500000",
    "createdAt": 1555556529865,
    "isBuyerMaker": true
  }
]
```

## Namebase Orderbook
```sql
-- fetch data
select * from namebase_orderbook limit 1
```
> response

```json
[

      {     
            'time': '2020-02-06T22:20:16.089313267Z', 
            'amount': 2290.179625, 
            'current_timetamp': '2020-02-06 22:17:52.513521', 
            'last_event_id': 74203, 
            'price': 0.0006211, 
            'symbol': 'HNSBTC', 
            'type': 'asks'
      }
]
```

### Description
[Namebase domain](https://github.com/namebasehq/exchange-api-documentation/blob/master/rest-api.md) has a frequency of 5 minutes and data time range is from 2020-02-06 22:20:16.089313267 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
amount           |float|
current_timetamp |string|
last_event_id    |integer|
price            |float|
type             |string|
symbol | string | Tag Values

### Tag Values
**Symbol**: HNSBTC

### Data Sanity
No downtime.

### API Reference
`GET https://www.namebase.io/api/v0/depth?symbol={}`

### API Query Parameters
Name | Type | Mandatory | Description 
---- | ---- |----------- | --------
symbol	|STRING|	YES	
limit	|INT|	NO	|Default 100; max 1000. Valid limits:[5, 50, 100, 500, 1000]

### API Response Schema
**Response**:
```json
{
  "lastEventId": 6828,         // The last event id this includes
  "bids": [
    ["0.00003000",  "200.000000"] // [Price level, Quantity]
  ],
  "asks": [
    ["0.00003100", "100.000000"]
  ]
}
```



# Nervos
[Nervos](https://www.nervos.org/) is a blockchain.

## Nervos Block 
```sql
-- fetch data
select * from nervos_block limit 1
```
> response

```json
[

      {     
            'time': '2019-11-21T17:39:36.469853695Z', 
            'alerts': False, 
            'chain': 'ckb', 
            'difficulty': 1598481419305342, 
            'epoch': 1357906557534226, 
            'id': '1574357944', 
            'is_initial_block_download': False, 
            'median_time': 1574357743225, 
            'type': 'statistic'
      }
]
```

### Description
[Nervos block](https://explorer.nervos.org/) has a frequency of 10 minutes and data time range is from 2019-11-21 17:39:36.469853695 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
alerts                    |boolean|
chain                     |string|
difficulty                |integer|
epoch                     |integer|
id                        |string|
is_initial_block_download |boolean|
median_time               |integer|
type                      |string|


### Data Sanity
No downtime.

### API Reference
`GET https://api.explorer.nervos.org/api/v1/statistics/blockchain_info`

### API Query Parameters
Not required.

### API Response Schema
No inforamtion.


## Nervos Hashrate
```sql
-- fetch data
select * from nervos_hashrate limit 1
```
> response

```json
[

      {     
            'time': '2019-11-21T17:48:09.097825773Z', 
            'current_epoch_average_block_time': None, 
            'current_epoch_difficulty': 1598481419305342, 
            'hash_rate': '135299530429.022742604569512264281101267', 
            'id': '1574358452', 
            'tip_block_time': 29863, 
            'type': 'index_statistic'
      }
]
```

### Description
[Nervos block](https://explorer.nervos.org/) has a frequency of 10 minutes and data time range is from 2019-11-21 17:39:36.469853695 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
current_epoch_average_block_time string
current_epoch_difficulty         integer
hash_rate                        string
id                               string
tip_block_time                   integer
type       

### Data Sanity
No downtime.

### API Reference
`GET https://api.explorer.nervos.org/api/v1/statistics/`

### API Query Parameters
Not required.

### API Response Schema
No inforamtion.




# Tether
[Tether](https://tether.to/) is a blockchian

## Tether Richlist
```sql
-- fetch data
select * from tether_richlist limit 1 
```
> response

```json
[
{'time': '2019-10-10T20:13:13.319694911Z', 
'Address': '1FoWyxwPXuj4C6abqwhjDWdz6D4PZgYRjA', 
'Amount': None, 
'Balance': '372,673,332', 
'Last Movement(UTC)': 'Oct 10 01:50 PM', 
'Remark': 'Binance', 
'Update Time': None
]
```

### Description
[Tezos richlist](https://blockspur.com/tether/richlist) has a frequency of 1 hour and data time range is from 2019-10-10 20:13:13.319694911Z till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
Address            string
Amount             float
Balance            string
Last Movement(UTC) string
Remark             string
Update Time        string

### Data Sanity
No downtime.

### Webscrapy
The data is collected thourgh webscrapying and the website 



# Tezos
[Tezos](https://stake.fish/en/tezos/) is a blockchain. 

## Tezos Leaderboard
```sql
-- fetch data
select * from tezos_leaderboard limit 1 
```
> response

```json
[
        {
            "time": "2020-02-04 05:46:48.567547",
            "current_timestamp": 2020-02-04 05:46:48.467547"
            "delegators": 65,
            "fees": 25.00% ,
            "rank": 1,
            "staked_amount": 46615903,
            "staked_amount_percentage": 0.07200000000000001,
            "validator_address": "tz1irJKkXS2DBWkU1NnmFQx1c1L7pbGg4yhk"",
            "validator_name": "Coinbase Custody"
          }
]
```

### Description
[Tezos leaderboard](https://tezos.fish/leaderboard) has a frequency of 1 hour and data time range is from 2020-02-04 05:46:48.467547 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
current_timestamp        string
delegators               string
fees                     string
rank                     integer
staked_amount            float
staked_amount_percentage float
validator_address        string
validator_name           string

### Data Sanity
No downtime.

### Webscrapy
The data is collected thourgh webscrapying and the website 




# Aggregate Exchange
All data in this section is aggregated all exchange, i.e. open interest through out all exchanges.   

##  Open Interest
```sql
-- fetch data
select * from exchange_open_interest limit 1
```

> response

```json
[

 {
   "time": "2020-04-11 01:50:00",
   "coin_denominated_open_interest":964669183078.0453,
   "coin_denominated_symbol": "XRP",
   "contract_exchange": "Bitmex",
   "contract_symbol": "XRPM20",
   "usd_denominated_open_interest": 26451229
 }

]
```

### Description
OPen Interets has a frequency of 1 minute and data time range is from 2020-04-11 01:50:00 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | data timestamp
coin_denominated_open_interest  |float|
usd_denominated_open_interest   |float|
coin_denominated_open_interest  |string|
contract_symbol | string | tag values
contract_exchange | string | tag values

### Tag Values
**contract_symbol (snaphot & symbols are subject to change)**: 
'ADA-0626', 'ADA-PERP', 'ADAM20', 'ADAUSDT', 'ALGO-0626', 'ALGO-PERP', 'ALT-0626', 'ALT-PERP', 'ATOM-0626', 'ATOM-PERP', 'ATOMUSDT', 'BATUSDT', 'BCH-0626', 'BCH-PERP', 'BCH-USD', 'BCH-USD-200417', 'BCH-USD-200424', 'BCH-USD-200501', 'BCH-USD-200626', 'BCH-USD-200925', 'BCH-USD-SWAP', 'BCH-USDT-200417', 'BCH-USDT-200424', 'BCH-USDT-200501', 'BCH-USDT-200626', 'BCH-USDT-200925', 'BCH-USDT-SWAP', 'BCH200417', 'BCH200424', 'BCH200501', 'BCH200626', 'BCHM20', 'BCHUSDT', 'BERNIE', 'BIDEN', 'BLOOMBERG', 'BNB-0626', 'BNB-PERP', 'BNBUSDT', 'BSV-0626', 'BSV-PERP', 'BSV-USD', 'BSV-USD-200417', 'BSV-USD-200424', 'BSV-USD-200501', 'BSV-USD-200626', 'BSV-USD-200925', 'BSV-USD-SWAP', 'BSV-USDT-200417', 'BSV-USDT-200424', 'BSV-USDT-200501', 'BSV-USDT-200626', 'BSV-USDT-200925', 'BSV-USDT-SWAP', 'BSV200417', 'BSV200424', 'BSV200501', 'BSV200626', 'BTC-0626', 'BTC-0925', 'BTC-11APR20-6375-C', 'BTC-11APR20-6375-P', 'BTC-11APR20-6500-C', 'BTC-11APR20-6500-P', 'BTC-11APR20-6625-C', 'BTC-11APR20-6625-P', 'BTC-11APR20-6750-C', 'BTC-11APR20-6750-P',  'BTC-24APR20-3000-C', 'BTC-24APR20-3000-P', 'BTC-24APR20-3500-C', 'BTC-24APR20-3500-P', 'BTC-24APR20-4000-C', 'BTC-24APR20-4000-P', 'BTC-MOVE-0413', 'BTC-MOVE-0414', 'BTC-MOVE-0415', 'BTC-MOVE-0416', 'BTC-MOVE-0417', 'BTC-MOVE-0418', 'BTC-MOVE-0419', 'BTC-MOVE-0420', 'BTC-MOVE-0421', 'BTC-MOVE-2020Q2', 'BTC-MOVE-2020Q3', 'BTC-MOVE-2020Q4', 'BTC-MOVE-WK-0417', 'BTC-MOVE-WK-0424', 'BTC-MOVE-WK-0501', 'BTC-MOVE-WK-0508', 'BTC-MOVE-WK-0515', 'BTC-PERP', 'BTC-PERPETUAL', 'BTC-USD', 'BTC-USD-200417', 'BTC-USD-200424', 'BTC-USD-200501', 'BTC-USD-200626', 'BTC-USD-200925', 'BTC-USD-SWAP', 'BTC-USDT-200417', 'BTC-USDT-200424', 'BTC-USDT-200501', 'BTC-USDT-200626', 'BTC-USDT-200925', 'BTC-USDT-SWAP', 'BTC200417', 'BTC200424', 'BTC200501', 'BTC200626', 'BTCUSDT', 'BTMX-0626', 'BTMX-PERP', 'DASH-USD-SWAP', 'DASH-USDT-SWAP', 'DASHUSDT', 'DOGE-0626', 'DOGE-PERP', 'DRGN-0626', 'DRGN-PERP', 'EOS-0626', 'EOS-PERP', 'EOS-USD', 'EOS-USD-200417', 'EOS-USD-200424', 'EOS-USD-200501', 'EOS-USD-200626', 'EOS-USD-200925', 'EOS-USD-SWAP', 'EOS-USDT-200417', 'EOS-USDT-200424', 'EOS-USDT-200501', 'EOS-USDT-200626', 'EOS-USDT-200925', 'EOS-USDT-SWAP', 'EOS200417', 'EOS200424', 'EOS200501', 'EOS200626', 'EOSM20', 'EOSUSDT', 'ETC-0626', 'ETC-PERP', 'ETC-USD', 'ETC-USD-200417', 'ETC-USD-200424', 'ETC-USD-200501', 'ETC-USD-200626', 'ETC-USD-200925', 'ETC-USD-SWAP', 'ETC-USDT-200417', 'ETC-USDT-200424', 'ETC-USDT-200501', 'ETC-USDT-200626', 'ETC-USDT-200925', 'ETC-USDT-SWAP', 'ETC200417', 'ETC200424', 'ETC200501', 'ETC200626', 'ETCUSDT', 'ETH-0626', 'ETH-11APR20-145-C', 'ETH-11APR20-145-P', 'ETH-11APR20-150-C', 'ETH-19APR20-185-C', 'ETH-19APR20-185-P', 'ETH-19APR20-190-C', 'ETH-19APR20-190-P', 'ETH-19APR20-195-C', 'ETH-19APR20-195-P', 'ETH-1MAY20-120-C', 'ETH-1MAY20-120-P', 'ETH-1MAY20-130-C', 'ETH-1MAY20-130-P', 'ETH-1MAY20-140-C', 'ETH-1MAY20-140-P', 'ETH-1MAY20-150-C', 'ETH-1MAY20-150-P', 'ETH-1MAY20-160-C', 'ETH-1MAY20-160-P', 'ETH-1MAY20-170-C', 'ETH-1MAY20-170-P', 'ETH-1MAY20-180-C', 'ETH-1MAY20-180-P', 'ETH-1MAY20-190-C',  'ETH-29MAY20-80-C', 'ETH-29MAY20-80-P', 'ETH-29MAY20-90-C', 'ETH-29MAY20-90-P', 'ETH-PERP', 'ETH-PERPETUAL', 'ETH-USD', 'ETH-USD-200417', 'ETH-USD-200424', 'ETH-USD-200501', 'ETH-USD-200626', 'ETH-USD-200925', 'ETH-USD-SWAP', 'ETH-USDT-200417', 'ETH-USDT-200424', 'ETH-USDT-200501', 'ETH-USDT-200626', 'ETH-USDT-200925', 'ETH-USDT-SWAP', 'ETH200417', 'ETH200424', 'ETH200501', 'ETH200626', 'ETHM20', 'ETHUSD', 'ETHUSDT', 'EXCH-0626', 'EXCH-PERP', 'HT-0626', 'HT-PERP', 'IOSTUSDT', 'IOTAUSDT', 'LEO-0626', 'LEO-PERP', 'LINK-0626', 'LINK-PERP', 'LINK-USD', 'LINK-USD-SWAP', 'LINK-USDT-SWAP', 'LINKUSDT', 'LTC-0626', 'LTC-PERP', 'LTC-USD', 'LTC-USD-200417', 'LTC-USD-200424', 'LTC-USD-200501', 'LTC-USD-200626', 'LTC-USD-200925', 'LTC-USD-SWAP', 'LTC-USDT-200417', 'LTC-USDT-200424', 'LTC-USDT-200501', 'LTC-USDT-200626', 'LTC-USDT-200925', 'LTC-USDT-SWAP', 'LTC200417', 'LTC200424', 'LTC200501', 'LTC200626', 'LTCM20', 'LTCUSDT', 'MATIC-0626', 'MATIC-PERP', 'MID-0626', 'MID-PERP', 'NEO-USD-SWAP', 'NEO-USDT-SWAP', 'NEOUSDT', 'OKB-0626', 'OKB-PERP', 'ONTUSDT', 'PAXG-0626', 'PAXG-PERP', 'PETE', 'PRIV-0626', 'PRIV-PERP', 'QTUMUSDT', 'SHIT-0626', 'SHIT-PERP', 'TOMO-0626', 'TOMO-PERP', 'TRUMP', 'TRX-0626', 'TRX-PERP', 'TRX-USD', 'TRX-USD-200417', 'TRX-USD-200424', 'TRX-USD-200501', 'TRX-USD-200626', 'TRX-USD-200925', 'TRX-USD-SWAP', 'TRX-USDT-200417', 'TRX-USDT-200424', 'TRX-USDT-200501', 'TRX-USDT-200626', 'TRX-USDT-200925', 'TRX-USDT-SWAP', 'TRX200417', 'TRX200424', 'TRX200501', 'TRX200626', 'TRXM20', 'TRXUSDT', 'TRYB-0626', 'TRYB-PERP', 'USDT-0626', 'USDT-PERP', 'VETUSDT', 'WARREN', 'XAUT-0626', 'XAUT-PERP', 'XBTM20', 'XBTU20', 'XBTUSD', 'XLMUSDT', 'XMRUSDT', 'XRP-0626', 'XRP-PERP', 'XRP-USD', 'XRP-USD-200417', 'XRP-USD-200424', 'XRP-USD-200501', 'XRP-USD-200626', 'XRP-USD-200925', 'XRP-USD-SWAP', 'XRP-USDT-200417', 'XRP-USDT-200424', 'XRP-USDT-200501', 'XRP-USDT-200626', 'XRP-USDT-200925', 'XRP-USDT-SWAP', 'XRP200417', 'XRP200424', 'XRP200501', 'XRP200626', 'XRPM20', 'XRPUSD', 'XRPUSDT', 'XTZ-0626', 'XTZ-PERP', 'XTZUSDT', 'ZECUSDT'

**contract_exchange**:
'Binance', 'Bitmex', 'Deribit', 'FTX', 'Huobi', 'Okex'


### Data Sanity
No downtime.


### API Reference
**Binance**:
Check [Binance open interest api](#binance-open-interest) 

**Bitmex**:
Check [Bitmex open interest api](#bitmex-instrument) 

**Deribit**:
Check [Deribit open interest api](#deribit-ticker)

**FTX**:
Check [FTX open interest api](#ftx-futures-statistics)

**Huobi**:
Check [Huobi open interest api](#huobidm-open-interest)

**Okex**:
Chexk [Okex open interest api](#okex-ticker-v1)



# Futures Market Data
## CME Group 
```sql
-- fetch tickers
select * from cme_futures_index
```

### Description
[CME futures index](https://www.cmegroup.com/trading/equity-index/us-index/bitcoin_quotes_globex.html) has a frequency of 1 minute and data time range is from 2020-04-15 18:35:17 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
change           |string|
close            |string|
code             |string|
exchangeCode     |string|
expirationDate   |string|
expirationMonth  |string|
high             |string|
highLimit        |string|
hoghLowLimits    |string|
last             |string|
low              |string|
lowLimit         |string|
open             |string|
percentageChange |string|
priorSettle      |string|
productCode      |string|
productId        |integer|
productName      |string|
updated          |string|
volume           |string|
symbol | string | tag values

### Tag Values
**Symbol**: BTCJ0, BTCK0, BTCM0, BTCN0, BTCQ0, BTCU0, BTCV0, BTCZ0, BTCZ1

### Data Sanity
No downtime.

### API Reference

`GET https://www.cmegroup.com/CmeWS/mvc/Quotes/Future/8478/G?quoteCodes=null`

### API Query Parameters
Not required.


### API Response Schema
No information.



## Commodity Futures Trading Commission
```sql
-- fetch tickers
select * from cftc_futures_report

```

### Description
[CFTC futures report](https://www.cftc.gov/MarketReports/CommitmentsofTraders/index.htm) has a frequency of 1 week and data time range is from 1986-01-15 00:00:00 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database time
As_of_Date_In_Form_YYMMDD       |integer|
CFTC_Commodity_Code             |integer|
CFTC_Market_Code                |string|
CFTC_Region_Code                |integer|
Change_in_Comm_Long_All         |float|
Change_in_Comm_Short_All        |float|
Change_in_NonComm_Long_All      |float|
Change_in_NonComm_Short_All     |float|
Change_in_NonComm_Spead_All     |float|
Change_in_NonRept_Long_All      |float|
Change_in_NonRept_Short_All     |float|
Change_in_Open_Interest_All     |float|
Change_in_Tot_Rept_Long_All     |float|
Change_in_Tot_Rept_Short_All    |float|
Comm_Positions_Long_All         |integer|
Comm_Positions_Long_Old         |integer|
Comm_Positions_Long_Other       |integer|
Comm_Positions_Short_All        |integer|
Comm_Positions_Short_Old        |integer|
Comm_Positions_Short_Other      |integer|
Conc_Gross_LE_4_TDR_Long_All    |float|
Conc_Gross_LE_4_TDR_Long_Old    |float|
Conc_Gross_LE_4_TDR_Long_Other  |float|
Conc_Gross_LE_4_TDR_Short_All   |float
Conc_Gross_LE_4_TDR_Short_Old   |float|
Conc_Gross_LE_4_TDR_Short_Other |float|
Conc_Gross_LE_8_TDR_Long_All    |float|
Conc_Gross_LE_8_TDR_Long_Old    |float|
Conc_Gross_LE_8_TDR_Long_Other  |float|
Conc_Gross_LE_8_TDR_Short_All   |float|
Conc_Gross_LE_8_TDR_Short_Old   |float|
Conc_Gross_LE_8_TDR_Short_Other |float|
Conc_Net_LE_4_TDR_Long_All      |float|
Conc_Net_LE_4_TDR_Long_Old      |float|
Conc_Net_LE_4_TDR_Long_Other    |float|
Conc_Net_LE_4_TDR_Short_All     |float|
Conc_Net_LE_4_TDR_Short_Old     |float|
Conc_Net_LE_4_TDR_Short_Other   |float|
Conc_Net_LE_8_TDR_Long_All      |float|
Conc_Net_LE_8_TDR_Long_Old      |float|
Conc_Net_LE_8_TDR_Long_Other    |float|
Conc_Net_LE_8_TDR_Short_All     |float|
Conc_Net_LE_8_TDR_Short_Old     |float|
Conc_Net_LE_8_TDR_Short_Other   |float|
Contract_Units                  |string|
Market_and_Exchange_Names       |string|
NonComm_Positions_Long_All      |integer|
NonComm_Positions_Long_Old      |integer|
NonComm_Positions_Long_Other    |integer|
NonComm_Positions_Short_All     |integer|
NonComm_Positions_Short_Old     |integer|
NonComm_Positions_Short_Other   |integer|
NonComm_Positions_Spread_Old    |integer|
NonComm_Positions_Spread_Other  |integer|
NonComm_Postions_Spread_All     |integer|
NonRept_Positions_Long_All      |integer|
NonRept_Positions_Long_Old      |integer|
NonRept_Positions_Long_Other    |integer|
NonRept_Positions_Short_All     |integer|
NonRept_Positions_Short_Old     |integer|
NonRept_Positions_Short_Other   |integer|
Open_Interest_All               |integer|
Open_Interest_Old               |integer|
Open_Interest_Other             |integer|
Pct_of_OI_Comm_Long_All         |float|
Pct_of_OI_Comm_Long_Old         |float|
Pct_of_OI_Comm_Long_Other       |float|
Pct_of_OI_Comm_Short_All        |float|
Pct_of_OI_Comm_Short_Old        |float|
Pct_of_OI_Comm_Short_Other      |float|
Pct_of_OI_NonComm_Long_All      |float|
Pct_of_OI_NonComm_Long_Old      |float|
Pct_of_OI_NonComm_Long_Other    |float|
Pct_of_OI_NonComm_Short_All     |float|
Pct_of_OI_NonComm_Short_Old     |float|
Pct_of_OI_NonComm_Short_Other   |float|
Pct_of_OI_NonComm_Spread_All    |float|
Pct_of_OI_NonComm_Spread_Old    |float|
Pct_of_OI_NonComm_Spread_Other  |float|
Pct_of_OI_NonRept_Long_All      |float|
Pct_of_OI_NonRept_Long_Old      |float|
Pct_of_OI_NonRept_Long_Other    |float|
Pct_of_OI_NonRept_Short_All     |float|
Pct_of_OI_NonRept_Short_Old     |float|
Pct_of_OI_NonRept_Short_Other   |float|
Pct_of_OI_Tot_Rept_Long_All     |float|
Pct_of_OI_Tot_Rept_Long_Old     |float|
Pct_of_OI_Tot_Rept_Long_Other   |float|
Pct_of_OI_Tot_Rept_Short_All    |float|
Pct_of_OI_Tot_Rept_Short_Old    |float|
Pct_of_OI_Tot_Rept_Short_Other  |float|
Pct_of_Open_Interest_All        |integer|
Pct_of_Open_Interest_Old        |integer|
Pct_of_Open_Interest_Other      |integer|
Tot_Rept_Positions_Long_All     |integer|
Tot_Rept_Positions_Long_Old     |integer|
Tot_Rept_Positions_Long_Other   |integer|
Tot_Rept_Positions_Short_All    |integer|
Tot_Rept_Positions_Short_Old    |integer|
Tot_Rept_Positions_Short_Other  |integer|
Traders_Comm_Long_All           |integer|
Traders_Comm_Long_Old           |integer|
Traders_Comm_Long_Other         |integer|
Traders_Comm_Short_All          |integer|
Traders_Comm_Short_Old          |integer|
Traders_Comm_Short_Other        |integer|
Traders_NonComm_Long_All        |integer|
Traders_NonComm_Long_Old        |integer|
Traders_NonComm_Long_Other      |integer|
Traders_NonComm_Short_All       |integer|
Traders_NonComm_Short_Old       |integer|
Traders_NonComm_Short_Other     |integer|
Traders_NonComm_Spead_Old       |integer|
Traders_NonComm_Spread_All      |integer|
Traders_NonComm_Spread_Other    |integer|
Traders_Tot_All                 |integer|
Traders_Tot_Old                 |integer|
Traders_Tot_Other               |integer|
Traders_Tot_Rept_Long_All       |integer|
Traders_Tot_Rept_Long_Old       |integer|
Traders_Tot_Rept_Long_Other     |integer|
Traders_Tot_Rept_Short_All      |integer|
Traders_Tot_Rept_Short_Old      |integer|
Traders_Tot_Rept_Short_Other    |integer|
CFTC_Contract_Market_Code | string | tag Values


###  Tag values
**CFTC_Contract_Market_Code (Market codes are subject to change)**:
001601, 001602, 00160F, 001611, 001612, 001621, 001623, 001624, 001626, 001627, 001631, 002601, 002602, 002603, 002631, 004601, 004603, 005601, 005602, 005603, 005631, 006261, 006265, 006268, 00626F, 00626U, 006391, 006392, 006393, 00639H, 00639U, 00639V, 00639W, 00639X, 00639Y, 00639Z, 0063A1, 0063A2, 0063A3, 0063A4, 0063AA, 0063AB, 0063AD, 0063AM, 0063AN, 0063AQ, 0063AR, 0063AS, 0063B1, 0063BD, 0063BF, 0063BY, 0063CA, 0063CC, 0063CD, 0063CH, 0063CJ, 0063CL, 0063D9, 0063DB, 0063DJ, 0063DK, 0063DL, 0063DN, 0063DP, 006GEC, 007601, 007631, 014601, 020601, 020604, 020631, 021397, 02141B, 02141C, 02141R, 02141V, 02165A, 02165B, 02165C, 02165E, 02165G, 02165H, 02165I, 02165J, 02165K, 02165L, 02165R, 02165T, 021A17, 021A18, 021A19, 021A28, 021A29, 021A35, 021A56, 022651, 02265J, 02265T, 02265U, 02265V, 022A05, 022A09, 022A13, 022A18, 022A22, 022A24, 022A26, 022A60, 022A62, 022A66, 023391, 023392, 023393, 023394, 023395, 023396, 023397, 023398, 023399, 02339E, 02339Q, 02339U, 02339W, 02339Y, 0233A2, 0233A3, 0233A5, 0233A6, 0233A8, 0233AG, 0233AH, 0233AM, 0233AN, 0233AQ, 0233AT, 0233AW, 0233AY, 0233B1, 0233B7, 0233BA, 0233BB, 0233BC, 0233BD, 0233BH, 0233BL, 0233BM, 0233BQ, 0233BW, 0233BY, 0233C1, 0233C9, 0233CG, 0233CH, 0233CS, 0233CU, 0233CV, 0233CW, 0233CY, 0233CZ, 0233D4, 0233DR, 0233DT, 0233DW, 0233E5, 0233EB, 0233ED, 023611, 023651, 023653, 023655, 02365A, 02365B, 02365C, 02365D, 02365E, 02365F, 02365G, 02365J, 02365K, 02365L, 02365M, 02365N, 02365O, 02365P, 02365S, 02365T, 023A09, 023A10, 023A12, 023A13, 023A26, 023A37, 023A39, 023A55, 023A56, 023A85, 023P01, 023P02, 023P03, 024651, 024652, 024653, 024656, 024658, 025601, 025608, 025651, 025652, 026603, 029641, 029642, 03265A, 03265B, 03265C, 03265J, 032741, 033661, 035650, 035651, 035652, 035653, 035654, 035655, 035656, 035657, 035658, 03565B, 03565C, 037642, 039601, 039781, 040701, 041741, 042601, 042661, 043602, 043607, 044601, 044661, 045601, 045741, 045L2T, 047741, 048741, 049601, 049741, 050641, 050642, 052641, 052644, 052645, 052732, 052733, 052734, 054641, 054642, 056641, 056642, 057642, 058641, 058643, 060611, 061641, 06260E, 063642, 063731, 064363, 064391, 064392, 064394, 064395, 064396, 06439A, 06439B, 06439C, 06439E, 06439F, 06439K, 06439L, 06439N, 06439R, 0643A5, 0643A7, 0643A8, 0643AF, 0643AP, 0643AT, 0643AU, 0643AZ, 0643B1, 0643B3, 0643B9, 0643BA, 0643BC, 0643BE, 0643BF, 0643BG, 0643BM, 0643BR, 0643BS, 0643BT, 0643BW, 0643BX, 0643BY, 0643BZ, 0643C3, 0643C4, 0643C7, 0643C8, 0643CB, 0643CC, 0643CJ, 0643CK, 0643CL, 0643CM, 0643CN, 0643CR, 0643CU, 0643CV, 0643CZ, 0643D1, 0643D4, 0643D5, 0643D7, 0643D8, 0643DB, 0643DC, 0643DF, 0643DK, 0643DL, 0643DM, 0643EA, 0643F1, 0643F2, 0643F3, 0643IB, 0643ID, 064651, 064652, 064653, 064654, 064655, 064657, 064658, 06465A, 06465B, 06465C, 06465H, 06465I, 06465K, 06465M, 06465N, 06465O, 06465P, 06465S, 06465T, 064A01, 064A02, 064A34, 064A35, 064A38, 064A39, 064A42, 064A48, 064A49, 064A50, 064A51, 064A52, 064A53, 064A54, 064A55, 064A56, 064A57, 064A58, 064A59, 064A60, 064A61, 064A62, 064A63, 064A64, 064A65, 064A66, 064A67, 064A68, 064A69, 064A71, 064A78, 064A79, 064A80, 064A82, 064A84, 064A85, 064A87, 064A88, 064AAA, 064AAB, 064BFI, 064BFJ, 064C52, 064C74, 064C75, 064C76, 064C77, 064C78, 064C79, 064C86, 064C87, 064C88, 064CXO, 064CXP, 064DEU, 064DEW, 064DLW,064DLX, 064DPQ, 064DPR, 064EAS, 064EJI, 064EJJ, 064ERM, 064ERN, 064EUY, 064EUZ, 064EVG, 064EVH, 064EWU, 064EXE, 064EXF, 064FHK, 064FHL, 064FJY, 064FKA, 064FKB, 064FKC, 064FKD, 064FKE, 064FKF, 064FZA, 064FZB, 064GAA, 064HZR, 064IAN, 066411, 066413, 066416, 06641A, 06641D, 06641F, 06641G, 06641H, 066651, 066652, 066653, 066654, 066655, 066657, 06665A, 06665B, 06665G, 06665O, 06665P, 06665Q, 06665R, 06665S, 06665T, 06665W, 06665Z, 066A19, 067411, 06741Q, 06741R, 06741G, 06741R, 06742R, 06742T, 06742U, 067651, 067653, 067655, 06765A, 06765G, 06765I, 06765J, 06765L, 06765M, 06765N, 06765O, 06765T, 0676A5, 067A49, 067A71, 067A75, 067DUI, 073732, 075651, 076651, 080732, 080734, 083731, 084602, 084605, 084691, 085691,085692, 088604, 088606, 088691, 089741, 090741, 091741, 092741, 092772, 094741, 094742, 094743, 094771, 095741, 096742, 097741, 097772, 097811, 098661, 098662, 099661, 099741, 102741, 105741, 111415, 111651, 111652, 111655, 11165J, 11165K, 11165L, 111A11, 111A31, 111A34, 111A41, 111A47, 112661, 112741, 116661, 1170E1, 120602, 120741, 121601, 122741, 12460+, 124601, 124603, 124606, 132741, 1330E1, 133741, 134741, 134742, 135731, 136611, 136612, 137611, 13874+, 138741, 138747, 138748, 138749, 13874A, 13874C, 13874E, 13874F, 13874G, 13874H, 13874J, 13874N, 13874I, 13874V, 148771, 148776, 148777, 151602, 1601, 1611, 16164H, 1621, 1624, 16264C, 16264H, 1631, 191651, 191691, 191693, 161694, 192651, 194741, 195651, 196661,196741, 197741, 20601, 20631, 209601, 20974+, 209741, 209742, 210741, 218771, 221602, 223771, 22651, 232661, 232741, 23651, 238621, 239741, 239742, 239744, 239771, 239772, 239773, 239777, 23977A, 23977C, 240741, 240743, 244041, 244042, 244741, 244742, 246601, 246602, 2446605, 246606, 247601, 247602, 249601, 251601, 252601, 252691, 253601, 255691, 256741, 2601, 260741, 261P05, 261P07, 261P08, 261P09, 26265A, 26265D, 2631, 263601, 26603, 266741, 267741, 270741, 271741, 272741, 294661, 299661, 299741, 30653, 32741, 332661, 33661, 33663, 338741, 33874A, 343601, 344601, 355691, 390741, 392261, 394741, 39601, 399661, 399741, 40701, 41741, 42601, 42661, 432661, 43602, 43874A, 44601, 44661, 44662, 45601, 4601, 492661, 494661, 499661, 52731, 531601, 532601, 54631, 54641, 5601, 5631, 56641, 57642, 58641, 594661, 597741, 597742, 599661, 60611, 61641, 62601, 63731, 66651, 66752, 67651, 67652, 694661, 70642, 71604, 73732, 75671, 76691, 794661, 799661, 80732, 80733, 80734, 80735, 83731, 84602, 84691, 85691, 85692, 86465A, 86465C, 86465D, 86465K, 86565A, 86565C, 86565D, 86565G, 86565N, 86665A, 86665B, 86665E, 86665G, 86765A, 86665C, 869652, 869654, 88604, 88691, 88741, 90741, 91741, 91811, 92741, 92811, 94741, 94742, 93743, 94771, 94811, 96741, 96742, 967652, 967654, 96765A, 97741, 98661, 98662, 99661, 99741, ZB9105.

### Data Sanity
Data is fetched through all [historical data](https://www.cftc.gov/MarketReports/CommitmentsofTraders/HistoricalCompressed/index.htm) in the website.


## Investing
```sql
-- fetch funding rate
select * from sp500_futures
```
> response

```json
[

 {
   "time": "2020-01-23T16:47:38Z",
   "CLose":915.25,
   "High": 934.25,
   "Low": 916.75,
   "Open": 933.75,
   "Volume": 11387
 }

]
```

### Description
[S&P 500 futures index](https://www.investing.com/indices/us-spx-500-futures-historical-data) has a frequency of 1 second and data time range is from 1990-02-15 00:00:00 till now. Collectors are continously runing in two hosts.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | default database timestamp
Date | string | data timestamp
Close    |float|
High     |float|
Low      |float|
Open     |float|
Volume   |float|

### Data Sanity
No downtime.

### API Reference
`GET https://www.investing.com/instruments/HistoricalDataAjax`

### API Query Parameters
**Parameters**
```
         {"curr_id":8839,
          "smllD":500066,
          "st_date":start_date,
          "end_date":end_date,
          "interval_sec":"Daily",
          "sort_col":"date",
          "sort_ord":"DESC"}
```

### API Response Schema
No information.

