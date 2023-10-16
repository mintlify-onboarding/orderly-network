### Orderbook

- `{symbol}@orderbook` depth 100 push every 1s

```json
{
    "id": "clientID2",
    "topic": "SPOT_WOO_USDC.e@orderbook",
    "event": "subscribe"
}
```

**Parameters**

| Name   | Type   | Required | Description                                                             |
| ------ | ------ | -------- | ----------------------------------------------------------------------- |
| id     | string | Y        | id generate by client                                 |
| event  | string | Y        | `subscribe`/`unsubscribe`                                               |
| topic  | string | Y        | `{symbol}@orderbook` |

> **Response**

```json
{
    "id": "clientID2",
    "event": "subscribe",
    "success": true,
    "ts": 1609924478533
}
```

> **Subscribed Message**

```json
{
    "topic": "SPOT_WOO_USDC.e@orderbook",
    "ts": 1614152140945,
    "data": {
        "symbol": "SPOT_WOO_USDC.e",
        "asks": [
            [
                0.31075,
                2379.63
            ],
            [
                0.31076,
                4818.76
            ],
            [
                0.31078,
                8496.1
            ],
            ...
        ],
        "bids": [
            [
                0.30891,
                2469.98
            ],
            [
                0.3089,
                482.5
            ],
            [
                0.30877,
                20
            ],
            ...
        ]
    }
}
```

### Order book update

- `{symbol}@orderbookupdate` updated orderbook push every 200ms

```json
{
    "id": "clientID2",
    "topic": "SPOT_NEAR_USDC.e@orderbookupdate",
    "event": "subscribe"
}
```

**Parameters**

| Name   | Type   | Required | Description                                           |
| ------ | ------ | -------- | ----------------------------------------------------- |
| id     | string | Y        | id generate by client                                 |
| event  | string | Y        | `subscribe`/`unsubscribe`                             |
| topic  | string | Y        | `{symbol}@orderbookupdate`                            |

> **Response**

```json
{
    "id": "clientID2",
    "event": "subscribe",
    "success": true,
    "ts": 1609924478533
}
```

> **Subscribed Message**

```json
{
    "topic":"SPOT_NEAR_USDC.e@orderbookupdate",
    "ts":1618826337580,
    "data":{
        "symbol":"SPOT_NEAR_USDC.e",
        "prevTs":1618826337380,
        "asks":[
            [
                15.15,
                3.92864
            ],
            [
                15.8,
                0
            ],
            ...
        ],
        "bids":[
            [
                14.2,
                1.03895025
            ],
            [
                13.6,
                1.0807
            ],
            ...
        ]
    }
}
```

### Trade

- Push interval: real-time push

```json
{
    "id": "clientID3",
    "topic": "SPOT_WOO_USDC.e@trade",
    "event": "subscribe"
}
```

**Parameters**

| Name   | Type   | Required | Description                              |
| ------ | ------ | -------- | ---------------------------------------- |
| id     | string | Y        | id generate by client                    |
| event  | string | Y        | `subscribe`/`unsubscribe`                |
| topic  | string | Y        | `{symbol}@trade`                         |

> **Response**

```json
{
    "id": "clientID3",
    "event": "subscribe",
    "success": true,
    "ts": 1609924478533
}
```

> **Subscribed Message**

```json
{
    "topic":"SPOT_WOO_USDC.e@trade",
    "ts":1618820361552,
    "data":{
        "symbol":"SPOT_WOO_USDC.e",
        "price":0.37988,
        "size":300,
        "side":"BUY"
    }
}
```

### 24h ticker

- Push interval: 1s

```json
{
    "id": "clientID4",
    "topic": "SPOT_WOO_USDC.e@ticker",
    "event": "subscribe"
}
```

**Parameters**

| Name   | Type   | Required | Description                              |
| ------ | ------ | -------- | ---------------------------------------- |
| id     | string | Y        | id generate by client                    |
| event  | string | Y        | `subscribe`/`unsubscribe`                |
| topic  | string | Y        | `{symbol}@ticker`                        |

> **Response**

```json
{
    "id": "clientID4",
    "event": "subscribe",
    "success": true,
    "ts": 1609924478533
}
```

> **Subscribed Message**

```json
{
    "topic": "SPOT_WOO_USDC.e@ticker",
    "ts": 1614152270000,
    "data": {
        "symbol": "SPOT_WOO_USDC.e",
        "open": 0.16112,
        "close": 0.32206,
        "high": 0.33000,
        "low": 0.14251,
        "volume": 89040821.98,
        "amount": 22493062.21,
        "count": 15442
    }
}
```

### 24h tickers

- Push interval: 1s

```json
{
    "id": "clientID4",
    "topic": "tickers",
    "event": "subscribe"
}
```

**Parameters**

| Name   | Type   | Required | Description                              |
| ------ | ------ | -------- | ---------------------------------------- |
| id     | string | Y        | id generate by client                    |
| event  | string | Y        | `subscribe`/`unsubscribe`                |
| topic  | string | Y        | `tickers`                                |

> **Response**

```json
{
    "id": "clientID4",
    "event": "subscribe",
    "success": true,
    "ts": 1609924478533
}
```

> **Subscribed Message**

```json
{
    "topic":"tickers",
    "ts":1618820615000,
    "data":[
        {
            "symbol":"SPOT_NEAR_USDC.e",
            "open":16.297,
            "close":17.183,
            "high":24.707,
            "low":11.997,
            "volume":0,
            "amount":0,
            "count":0
        },
        {
            "symbol":"SPOT_WOO_USDC.e",
            "open":0.3515,
            "close":0.43794,
            "high":0.96674,
            "low":0.39264,
            "volume":750127.1,
            "amount":985440.5122,
            "count":396
        },
        ...
    ]
}
```

### bbo

- Push interval: 10ms

```json
{
    "id": "clientID5",
    "topic": "SPOT_WOO_USDC.e@bbo",
    "event": "subscribe"
}
```

**Parameters**

| Name   | Type   | Required | Description                              |
| ------ | ------ | -------- | ---------------------------------------- |
| id     | string | Y        | id generate by client                    |
| event  | string | Y        | `subscribe`/`unsubscribe`                |
| topic  | string | Y        | `{symbol}@bbo`                           |


> **Response**

```json
{
    "id": "clientID5",
    "event": "subscribe",
    "success": true,
    "ts": 1609924478533
}
```

> **Subscribed Message**

```json
{
    "topic": "SPOT_WOO_USDC.e@bbo",
    "ts": 1614152296945,
    "data": {
        "symbol": "SPOT_WOO_USDC.e",
        "ask": 0.30939,
        "askSize": 4508.53,
        "bid": 0.30776,
        "bidSize": 25246.14
    }
}
```

### bbos

- Push interval: 1s

```json
{
    "id": "clientID5",
    "topic": "bbos",
    "event": "subscribe"
}
```

**Parameters**

| Name   | Type   | Required | Description                              |
| ------ | ------ | -------- | ---------------------------------------- |
| id     | string | Y        | id generate by client                    |
| event  | string | Y        | `subscribe`/`unsubscribe`                |
| topic  | string | Y        | `bbos`                                   |

> **Response**

```json
{
    "id": "clientID5",
    "event": "subscribe",
    "success": true,
    "ts": 1609924478533
}
```

> **Subscribed Message**

```json
{
    "topic":"bbos",
    "ts":1618822376000,
    "data":[
        {
            "symbol":"SPOT_NEAR_USDC.e",
            "ask":15.0318,
            "askSize":370.43,
            "bid":15.9158,
            "bidSize":16
        },
        {
            "symbol":"SPOT_WOO_USDC.e",
            "ask":0.318,
            "askSize":300.163881,
            "bid":0.3179,
            "bidSize":500.941728
        },
       ...
    ]
}
```

### k-line

- `{time}`: `1m`/`5m`/`15m`/`30m`/`1h`/`1d`/`1w`/`1M`
- Push interval: 1s

```json
{
    "id": "clientID6",
    "topic": "SPOT_NEAR_USDC.e@kline_1m",
    "event": "subscribe"
}
```

**Parameters**

| Name   | Type   | Required | Description                               |
| ------ | ------ | -------- | ----------------------------------------- |
| id     | string | Y        | id generate by client                     |
| event  | string | Y        | `subscribe`/`unsubscribe`                 |
| topic  | string | N        | `{symbol}@kline_{time}`                   |

> **Response**

```json
{
    "id": "clientID6",
    "event": "subscribe",
    "success": true,
    "ts": 1609924478533
}
```

> **Subscribed Message**

```json
{
    "topic":"SPOT_NEAR_USDC.e@kline_1m",
    "ts":1618822432146,
    "data":{
        "symbol":"SPOT_NEAR_USDC.e",
        "type":"1m",
        "open":15.97,
        "close":14.76,
        "high":16.97,
        "low":14.06,
        "volume":44.00947568,
        "amount":2504584.9,
        "startTime":1618822380000,
        "endTime":1618822440000
    }
}
```

### Index price

- Push interval: 1s

```json
{
    "id": "clientID7",
    "topic": "SPOT_ETH_USDC.e@indexprice",
    "event": "subscribe"
}
```

**Parameters**

| Name   | Type   | Required | Description                               |
| ------ | ------ | -------- | ----------------------------------------- |
| id     | string | Y        | id generate by client                     |
| event  | string | Y        | `subscribe`/`unsubscribe`                 |
| topic  | string | N        | `{symbol}@indexprice`                   |

> **Response**

```json
{
   "id":"clientID7",
   "event":"subscribe",
   "success":true,
   "ts":1682241351985
}
```

> **Subscribed Message**

```json
{
   "topic":"SPOT_ETH_USDC.e@indexprice",
   "ts":1682241354000,
   "data":{
      "symbol":"SPOT_ETH_USDC.e",
      "price":1873.36
   }
}
```


### Index prices

- Push interval: 1s

```json
{
    "id": "clientID7",
    "topic": "indexprices",
    "event": "subscribe"
}
```

**Parameters**

| Name   | Type   | Required | Description      |
| ------ | ------ | -------- |------------------|
| id     | string | Y        | id generate by client |
| event  | string | Y        | `subscribe`/`unsubscribe` |
| topic  | string | N        | `indexprices`    |

> **Response**

```json
{
   "id":"clientID7",
   "event":"subscribe",
   "success":true,
   "ts":1682241351985
}
```

> **Subscribed Message**

```json
{
    "topic":"indexprices",
    "ts":1618822376000,
    "data":[
        {
           "symbol":"SPOT_BTC_USDC.e",
            "price":51234.13
        },
        {
            "symbol":"SPOT_ETH_USDC.e",
            "price":3894.34
        },
       ...
    ]
}
```



### Mark price

- Push interval: 1s

```json
{
    "id": "clientID8",
    "topic": "PERP_ETH_USDC.e@markprice",
    "event": "subscribe"
}
```

**Parameters**

| Name   | Type   | Required | Description                               |
| ------ | ------ | -------- | ----------------------------------------- |
| id     | string | Y        | id generate by client                     |
| event  | string | Y        | `subscribe`/`unsubscribe`                 |
| topic  | string | N        | `{symbol}@markprice`                   |

> **Response**

```json
{
   "id":"clientID8",
   "event":"subscribe",
   "success":true,
   "ts":1682241795883
}
```

> **Subscribed Message**

```json
{
   "topic":"PERP_ETH_USDC.e@markprice",
   "ts":1682241796000,
   "data":{
      "symbol":"PERP_ETH_USDC.e",
      "price":2300.0
   }
}
```
### Mark prices

- Push interval: 1s

```json
{
    "id": "clientID",
    "topic": "markprices",
    "event": "subscribe"
}
```

**Parameters**

| Name   | Type   | Required | Description               |
| ------ | ------ | -------- |---------------------------|
| id     | string | Y        | id generate by client     |
| event  | string | Y        | `subscribe`/`unsubscribe` |
| topic  | string | N        | `markprices`              |

> **Response**

```json
{
   "id":"clientID9",
   "event":"subscribe",
   "success":true,
   "ts":1682242805633
}
```

> **Subscribed Message**

```json
{
   "topic":"markprices",
   "ts":1682242806000,
   "data":[
      {
         "symbol":"PERP_ETH_USDC.e",
         "price":2300.0
      },
      {
         "symbol":"PERP_NEAR_USDC.e",
         "price":2.15
      },
      {
         "symbol":"SPOT_NEAR_USDC.e",
         "price":16.0
      }
   ]
}
```

### Open interest

- Push interval: push every 1 second if open interest change and 10 seconds force update even if no change.

```json
{
    "id": "clientID10",
    "topic": "PERP_ETH_USDC.e@openinterest",
    "event": "subscribe"
}
```

**Parameters**

| Name   | Type   | Required | Description                               |
| ------ | ------ | -------- | ----------------------------------------- |
| id     | string | Y        | id generate by client                     |
| event  | string | Y        | `subscribe`/`unsubscribe`                 |
| topic  | string | N        | `{symbol}@openinterest`                   |

> **Response**

```json
{
   "id":"clientID10",
   "event":"subscribe",
   "success":true,
   "ts":1682242071080
}
```

> **Subscribed Message**

```json
{
   "topic":"PERP_ETH_USDC.e@openinterest",
   "ts":1682242080006,
   "data":{
      "symbol":"PERP_ETH_USDC.e",
      "openInterest":1.2741
   }
}
```
### Estimated funding rate

- Push interval: 15s

```json
{
    "id": "clientID11",
    "topic": "PERP_ETH_USDC.e@estfundingrate",
    "event": "subscribe"
}
```

**Parameters**

| Name   | Type   | Required | Description                               |
| ------ | ------ | -------- | ----------------------------------------- |
| id     | string | Y        | id generate by client                     |
| event  | string | Y        | `subscribe`/`unsubscribe`                 |
| topic  | string | N        | `{symbol}@estfundingrate`                 |

> **Response**

```json
{
   "id":"clientID11",
   "event":"subscribe",
   "success":true,
   "ts":1682242408023
}
```

> **Subscribed Message**

```json
{
   "topic":"PERP_ETH_USDC.e@estfundingrate",
   "ts":1682242440000,
   "data":{
      "symbol":"PERP_ETH_USDC.e",
      "fundingRate":0.00046875,
      "fundingTs":1682242440000
   }
}
```
### Liquidation push

- Push interval: push on addition/removal/update from list within 1s

```json
{
    "id": "clientID12",
    "topic": "liquidation",
    "event": "subscribe"
}
```

**Parameters**

| Name   | Type   | Required | Description                               |
| ------ | ------ | -------- | ----------------------------------------- |
| id     | string | Y        | id generate by client                     |
| event  | string | Y        | `subscribe`/`unsubscribe`                 |
| topic  | string | N        | `liquidation`                   |

> **Response**

```json
{
   "id":"clientID12",
   "event":"subscribe",
   "success":true,
   "ts":1682243349558
}
```

> **Subscribed Message**

```json
{
   "topic":"liquidation",
   "ts":1684926668235,
   "data":[
      {
         "liquidationId":1,
         "timestamp":1684821114917,
         "type":"liquidated",
         "positionsByPerp":[
            {
               "symbol":"PERP_NEAR_USDC.e",
               "positionQty":12.6,
               "liquidatorFee":0.0175
            }
         ]
      },
      ...
   ]
}
```


## Private

### Balance

- Push interval: real-time push

```json
{
    "id": "clientID3",
    "topic": "balance",
    "event": "subscribe"
}
```

**Parameters**

| Name   | Type   | Required | Description                              |
| ------ | ------ | -------- | ---------------------------------------- |
| id     | string | Y        | id generate by client                    |
| event  | string | Y        | `subscribe`/`unsubscribe`                |
| topic  | string | Y        | `balance`                                |

> **Response**

```json
{
    "id": "clientID3",
    "event": "subscribe",
    "success": true,
    "ts": 1609924478533
}
```

> **Subscribed Message**

```json
{
    "topic":"balance",
    "ts":1651836695254,
    "data":{
        "balances":{
            "WOO":{
                "holding":5555815.47398272,
                "frozen":0,
                "interest":0,
                "pendingShortQty":0,
                "pendingExposure":0,
                "pendingLongQty":0,
                "pendingLongExposure":0,
                "version":894,
                "staked":51370692,
                "unbonding":0,
                "vault":0,
                "averageOpenPrice":0.00000574,
                "pnl24H":0,
                "fee24H":0.01914,
                "markPrice":0.31885
            }
        }
    }
}
```

### Execution Report

- Push interval: real-time push

```json
{
    "id": "clientID3",
    "topic": "executionreport",
    "event": "subscribe"
}
```

**Parameters**

| Name   | Type   | Required | Description                              |
| ------ | ------ | -------- | ---------------------------------------- |
| id     | string | Y        | id generate by client                    |
| event  | string | Y        | `subscribe`/`unsubscribe`                |
| topic  | string | Y        | `executionreport`                        |

> **Response**

```json
{
    "id": "clientID3",
    "event": "subscribe",
    "success": true,
    "ts": 1609924478533
}
```

> **Subscribed Message**

```json
{
    "topic":"executionreport",
    "ts":1618757714353,
    "data":{
        "symbol":"SPOT_WOO_USDC.e",
        "clientOrderId":"testid",
        "orderId":4506424,
        "type":"LIMIT",
        "side":"BUY",
        "quantity":750127.1,
        "price":0.354,
        "tradeId":1870568,
        "executedPrice":0.3525,
        "executedQuantity":6620.6,
        "fee":1.98618,
        "feeAsset":"WOO",
        "totalExecutedQuantity":720891.2,
        "avgPrice":0.31344,
        "status":"PARTIAL_FILLED",
        "reason":"",
        "totalFee":216.26736,
        "visible": 750127.1,
        "timestamp":1618757714353,
        "brokerId": "",
        "brokerName": "",
        "maker":false
    }
}
```

### Execution Report for a single broker_id

- Push interval: real-time push

```json
{
    "id": "clientID3",
    "topic": "executionreport@broker",
    "event": "subscribe"
}
```

**Parameters**

| Name   | Type   | Required | Description                              |
| ------ | ------ | -------- | ---------------------------------------- |
| id     | string | Y        | id generate by client                    |
| event  | string | Y        | `subscribe`/`unsubscribe`                |
| topic  | string | Y        | `executionreport@{broker_id}`            |

> **Response**

```json
{
    "id": "clientID3",
    "event": "subscribe",
    "success": true,
    "ts": 1609924478533
}
```

> **Subscribed Message**

```json
{
    "topic":"executionreport@broker",
    "ts":1618757714353,
    "data":{
        "symbol":"SPOT_WOO_USDC.e",
        "clientOrderId":"testid",
        "orderId":4506424,
        "type":"LIMIT",
        "side":"BUY",
        "quantity":750127.1,
        "price":0.354,
        "tradeId":1870568,
        "executedPrice":0.3525,
        "executedQuantity":6620.6,
        "fee":1.98618,
        "feeAsset":"WOO",
        "totalExecutedQuantity":720891.2,
        "avgPrice":0.31344,
        "status":"PARTIAL_FILLED",
        "reason":"",
        "totalFee":216.26736,
        "visible": 750127.1,
        "timestamp":1618757714353,
        "brokerId": "broker",
        "brokerName": "Broker Name",
        "maker":false
    }
}
```

### Notifications

- Push interval: real-time push

```json
{
    "id": "clientID3",
    "topic": "notifications",
    "event": "subscribe"
}
```

**Parameters**

| Name   | Type   | Required | Description                              |
| ------ | ------ | -------- | ---------------------------------------- |
| id     | string | Y        | id generate by client                    |
| event  | string | Y        | `subscribe`/`unsubscribe`                |
| topic  | string | Y        | `notifications`            |

> **Response**

```json
{
    "id": "clientID3",
    "event": "subscribe",
    "success": true,
    "ts": 1609924478533
}
```

> **Subscribed Message**

```json
{
    "topic": "notifications",
    "data": {
        "id": 12345, // notification id
        "messageType": "ORDER_FILLED", // ORDER_FILLED
        "title": "Your order has been filled",
        "type": "TRADE",  // TRADE / SYSTEM
        "level": "GENERAL", // GENERAL / IMPORTANT
        "contentSummary": "Your order to buy 1 NEAR/USDC.e has been filled: 0.5/1 at 1.9876.",
        "content": "<p>Your order to buy 1 NEAR/USDC.e has been filled: 0.5/1 at 1.9876.</p>",
        "contentRaw": { // below example is for a ORDER_FILLED content
            "symbol": "SPOT_NEAR_USDC.e",
            "side": "BUY",
            "orderId": 1,
            "executedPrice": 1.9876, 
            "executedQuantity": 0.5,
            "executedTimestamp": 1567382401000 
        }
    },
    "timestamp": 1679021265398
}
```

### Position push

- Push interval: push on update

```json
{
    "id": "clientID3",
    "topic": "position",
    "event": "subscribe"
}
```

**Parameters**

| Name   | Type   | Required | Description                              |
| ------ | ------ | -------- | ---------------------------------------- |
| id     | string | Y        | id generate by client                    |
| event  | string | Y        | `subscribe`/`unsubscribe`                |
| topic  | string | Y        | `position`            |

> **Response**

```json
{
    "id": "clientID3",
    "event": "subscribe",
    "success": true,
    "ts": :1682244308139
}
```

> **Subscribed Message**

```json
{
   "topic":"position",
   "ts":1684926050966,
   "data":{
      "positions":[
         {
            "symbol":"PERP_ETH_USDC.e",
            "positionQty":3.1408,
            "costPosition":5706.51952,
            "lastSumUnitaryFunding":0.804,
            "sumUnitaryFundingVersion":0,
            "pendingLongQty":0.0,
            "pendingShortQty":-1.0,
            "settlePrice":1816.9,
            "averageOpenPrice":1804.51490427,
            "unsettledPnl":-2.79856,
            "pnl24H":-338.90179488,
            "fee24H":4.242423,
            "markPrice":1816.2,
            "estLiqPrice":0.0,
            "version":179967,
            "imrwithOrders":0.1,
            "mmrwithOrders":0.05,
            "mmr":0.05,
            "imr":0.1
         }
      ]
   }
}
```


### Liquidation on account push

- Push interval: push on update

```json
{
    "id": "clientID5",
    "topic": "liquidationsaccount",
    "event": "subscribe"
}
```

**Parameters**

| Name   | Type   | Required | Description               |
| ------ | ------ | -------- |---------------------------|
| id     | string | Y        | id generate by client     |
| event  | string | Y        | `subscribe`/`unsubscribe` |
| topic  | string | Y        | `liquidationsaccount`     |

> **Response**

```json
{
    "id": "clientID5",
    "event": "subscribe",
    "success": true,
    "ts": 1609924478533
}
```

> **Subscribed Message**

```json
{
    "topic":"liquidationsaccount",
    "ts":1641439456774,
    "data":[
          {
              "liquidation_id": 101,
              "timestamp": 1663313562090,
              "transfer_amount_to_insurance_fund": 0,
              "positions_by_perp" : [
                {
                    "symbol" : "PERP_BTC_USDC.e", 
                    "position_qty": 1.23,
                    "cost_position_transfer": 1350,
                    "transfer_price": 18123.43,
                    "liquidator_fee": 0.015,
                    "insurance_fund_fee": 0.015,
                    "abs_liquidation_fee": 3520,
                },
                {
                    "symbol" : "PERP_ETH_USDC.e",
                    "position_qty": 1.23,
                    "cost_position_transfer": 1350,
                    "transfer_price": 18123.43,
                    "liquidator_fee": 0.015,
                    "insurance_fund_fee": 0.015,
                    "abs_liquidation_fee": 3520,
                },
                {
                    "symbol" : "PERP_NEAR_USDC.e",
                    "position_qty": 1.23,
                    "cost_position_transfer": 1350,
                    "transfer_price": 18123.43,
                    "liquidator_fee": 0.015,
                    "insurance_fund_fee": 0.015,
                    "abs_liquidation_fee": 3520,
                },
                {
                    "symbol" : "PERP_WOO_USDC.e",
                    "position_qty": 1.23,
                    "cost_position_transfer": 1350,
                    "transfer_price": 18123.43,
                    "liquidator_fee": 0.015,
                    "insurance_fund_fee": 0.015,
                    "abs_liquidation_fee": 3520,
                }
              ]
          },
          {
              "liquidation_id": 102,
              "transfer_amount_to_insurance_fund": 0,
              "positions_by_perp" : [
                {
                    "symbol" : "PERP_ETH_USC",
                    "position_qty": 1.23,
                    "cost_position_transfer": 1350,
                    "transfer_price": 18123.43,
                    "liquidator_fee": 0.015,
                    "insurance_fund_fee": 0.015,
                    "abs_liquidation_fee": 3520,
                },
                {
                    "symbol" : "PERP_NEAR_USDC.e",
                    "position_qty": 1.23,
                    "cost_position_transfer": 1350,
                    "transfer_price": 18123.43,
                    "liquidator_fee": 0.015,
                    "insurance_fund_fee": 0.015,
                    "abs_liquidation_fee": 3520,
                },
              ]
          },
    ]
}

```


### Liquidator liquidations push

- Push interval: push on addition/removal/update from list within 1s
- 1 user_id can have many liquidation_ids 

```json
{
    "id": "clientID3",
    "topic": "liquidatorliquidations",
    "event": "subscribe"
}
```

**Parameters**

| Name   | Type   | Required | Description                              |
| ------ | ------ | -------- | ---------------------------------------- |
| id     | string | Y        | id generate by client                    |
| event  | string | Y        | `subscribe`/`unsubscribe`                |
| topic  | string | Y        | `liquidatorliquidations`            |

> **Response**

```json
{
    "id": "clientID3",
    "event": "subscribe",
    "success": true,
    "ts": :1682244882617
}
```

> **Subscribed Message**

```json
{
   "topic":"liquidatorliquidations",
   "ts":1684821114917,
   "data":{
      "liquidationId":1,
      "timestamp":1684821114917,
      "type":"liquidated",
      "positionsByPerp":[
         {
            "symbol":"PERP_NEAR_USDC.e",
            "positionQty":12.6,
            "costPositionTransfer":20.05668,
            "transferPrice":1.5918,
            "liquidatorFee":0.0175,
            "absLiquidatorFee":0.350992
         }
      ]
   }
}
```


### PnL Settlement

- Push interval: real-time push on update

```json
{
    "id": "clientID3",
    "topic": "settle",
    "event": "subscribe"
}
```

**Parameters**

| Name   | Type   | Required | Description               |
| ------ | ------ | -------- |---------------------------|
| id     | string | Y        | id generate by client     |
| event  | string | Y        | `subscribe`/`unsubscribe` |
| topic  | string | Y        | `settle`                  |

> **Response**

```json
{
    "id": "clientID3",
    "event": "subscribe",
    "success": true,
    "ts": 1609924478533
}
```

> **Subscribed Message**

```json
{
    "topic": "settle",
    "data": {
        "id": 10001,
        "old_balance": 4050,
        "new_balance": 3050,
        "settled_amount": -1000,
        "requested_time": 1575014255089, // Unix epoch time in ms
        "settled_time": 1575014255910 // Unix epoch time in ms
        "status": "COMPLETED"
    },
    "timestamp": 1679021265398
}
```

Example response if there is an error.


## Error Response

```json
{
    "id": "clientID7",
    "event": "subscribe",
    "success": false,
    "ts": 1614141150601,
    "errorMsg": "invalid symbol SPOT_WOO_USDC.e"
}
```

Example response if there is an error.
