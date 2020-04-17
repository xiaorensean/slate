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

Welcome to the **VQR Data Catalogue**! The document gives you descriptions on database we are using, all available data feeds we are collecting, and all available api that we are tracking.

Database is [InfluxDB](https://docs.influxdata.com/influxdb/v1.8/),whihc is a time-series database. Few terminologies to explain, tags in the influxdb is the unqie index and it is very useful to sort tickers via taging. Measurement is another word for table in the influxdb. Time is the defalut column in the table, which means the time that data wrote into database. Currently, we have two influxbd servers, one is primary server and another one is backup server.

Host Server: 
`Host-1 (Primary): 99-79-47-186 &&&& Host-2 (Backup): 15-223-68-239`

<aside class="notice">
Ask credentials to log in.
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
[binance_future_stats_taker_buy_sell_ratio](#binance-taker-buy-sell-ratio) | Varies | Futures Data | Running
[binance_liquidation_trades](#binance-liquidation-trade) | 8 hours | Liquidation Trades Data | Running
[binance_open_interest_clean](#binance-open-interest) | 8 hours | Open Interest | Running
[binance_orderbook_futures_clean](#binance-orderbook) | 30 seconds | Orderbook Data | Running
[binance_orderbook_spot_clean](#binance-orderbook) | 30 seconds | Orderbook Data | Running
[binance_trade_futures](#binance-trade) | RealTime | Trades Data | Running
[binance_trade_spot](#binance-trade) | RealTime | Trades Data | Running
bitfinex_funding_orderbook | 30 seconds | Funding Orderbook | Running
bitfinex_funding_trade | RealTime | Funding Trades | Running
bitmex_full_orderbook | RealTime | Orderbook | Running
bitmex_funding | 8 hours | Funding | Running
bitmex_funding_rates | 8 hours | Funding | Running
bitmex_instrument | 1 minute | Market Summary | Running 
bitmex_insurance | None | None | Running
bitmex_leaderboard_notional | 1 hour | Leaderboard | Running
bitmex_leaderboard_ROE | 1 hour | Leaderboard | Running
bitmex_liquidation | RealTime | Liquidation | Running
bitmex_settlement | 1 week | Settlement | NoLongerUpated
bitmex_trade | RealTime | Trade Data | Running
bybit_funding_rate | 8 hours | Funding Rates | Running 
bybit_tickers | 1 minute | Ticker | Running
bybit_trades | RealTime | Trade Data | Running
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
        "time": "2020-04-16 20:39:55.416015"",
        "borrowLimit": 5000000",
        "dailyInterestRate": 0.0016,
        "symbol": "ADA",
        "timestamp": "2020-04-16 20:39:55.416015",
        "vipLevel": 9
    },
    ...
    
   {
   
    ...
    
    }
]
```

### Description
[Binance borrow rate](https://www.binance.com/en/margin-fee) is part of margin data listed in the website. Binance borrow rate has a frequency of 30 minutes and data time range is from 2019-12-02 21:34:09 till now. Collectors are continously runing in two hosts.

### Tag Vlaues 
Ticker tags are ADA, ATOM, BAT, BCH, BNB, BTC, BUSD, DASH, EOS, ETC, ETH, IOST, IOTA, LINK, LTC, MATIC, NEO, ONT, QTUM, RVN, TRX, USDC, USDT, VET, XLM, XMR, XRP, XTZ, ZEC. 

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | time record for writing into db
borrowLimit | float | 
dailyInterestRate | float |
timestamp | string | timestamp record for data updating
vipLevel | string |
symbol | string | symbol is tag

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
select * from binance_funding_rates_clean'
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
Binance funding rate has a frequency of 8 hours and data time range is from 2020-01-27 18:07:37 till now. Collectors are continously runing in two hosts. 

### Tag Vlaues 
No tags in the table. All available symbols are BTCUSDT ETHUSDT, BCHUSDT, XRPUSDT, EOSUSDT, LTCUSDT, TRXUSDT, ETCUSDT, LINKUSDT, XLMUSDT, ADAUSDT, XMRUSDT, DASHUSDT, ZECUSDT, XTZUSDT, BNBUSDT, ATOMUSDT, ONTUSDT, IOTAUSDT, BATUSDT, VETUSDT, NEOUSDT.

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
fundingRate | float | 
fundingTime | integer |
time | string | time record for data updating  
symbol | string | 

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
select * from binance_future_stats_long_short_ratio'
```

> response:

```json
[
    { 
         "time":"1583139600000""
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

### Tag Vlaues 
* Frequency
5 minutes, 15 minutes, 30 minutes, 1 hour, 2 hour, 4 hour, 6 hour, 12 hour, and 1 day

* Symbol
ADAUSDT, ATOMUSDT, BATUSDT, BCHUSDT, BNBUSDT, BTCUSDT, DASHUSDT, EOSUSDT, ETCUSDT, ETHUSDT, IOSUSDT, IOATUSDT, LINKUSDT, LTCUSDT, NEOUSDT,ONTUSDT,QTUMUSDT, TRXUSDT, VETUSDT, XLMUSDT, XMRUSDT, XRPUSDT, XTZUSDT, ZECUSDT

### Data Schema
fieldName | fieldType | description
--------- | --------- | ---------- |
time | string | consistent with timestamp fields
frequency | string | tag values 
long_account | string | 
short_account | string | 
long_short_account | float | 
symbol | string | tag values 
timestamp | integer | data timestamp 

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

## Binance Long Short Ratio Position

## Binance Future Stats Open Interest

## Binance Taker Buy Sell Ratio

## Binance Liquidation Trade

## Binance Open Interest

## Binance Orderbook

## Binance Trade

# BigOne
[BigOne exchange](https://big.one/) is a cryptocurrency exchange with [api documents](https://open.big.one/docs/api.html) 

## BigOne Trade

## BigOne Orderbook


### Open Interest

### Coinflex

### Cosmos

### HNScan

### Namebase

### Nervos

### Tether

### Tezos



### Bitfinex

### Bitmex


### Bigone Orderbook 

### Bybit

### Coinbase

### Coinex

### Compound

### Deribit

### Dydx

### FTX

### Gateio

### HuobiDM

### MXC

### OKEX

### Poloniex

### Wazirx


### CME Group 

### Commodity Futures Trading Commission

### Investing.com




# Kittens

## Get All Kittens

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete

