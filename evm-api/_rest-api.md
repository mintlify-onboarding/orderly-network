### Get insurance fund info

> **Request**

```shell
curl 'https://api.orderly.org/v1/public/insurance_fund'
```
```java
```
```python
import requests

url = "https://api.orderly.org/v1/public/insurance_fund"

payload={}
headers = {}

response = requests.request("GET", url, headers=headers, data=payload)
```
```javascript
var axios = require('axios');

var config = {
   method: 'get',
   url: 'https://api.orderly.org/v1/public/insurance_fund',
   headers: {}
};

axios(config)
.then(function (response) {
   console.log(JSON.stringify(response.data));
})
.catch(function (error) {
   console.log(error);
});

```

**Limit: 10 requests per 1 second per IP address**

`GET /v1/public/insurance_fund`


> **Response**

```json
{
    "success": true,
    "data" : {
      "min_insurance_fund_initial_margin_ratio": 0.3,
      "min_insurance_fund_margin_ratio" : 0.33, // max leverage 4x
      "margin_ratio": 0.8,
      "total_collateral_value": 100,
      "balance": 500000.00,
      "free_collateral": 300000.00,
      "total_account_value": 750000,
      "total_pnl_24_h" : 5000,
      "rows": [
          {
              "symbol": "PERP_BTC_USDT",
              "position_qty": 12.3,
              "cost_position": 20000,
              "last_sum_unitary_funding": 1.5,
              "max_notional":1000000,
              "settle_price": 50000,
              "average_open_price": 49000,
              "pnl_24_h": 20,
              "fee_24_h": 12,
              "mark_price": 49550,
              "timestamp": "1575014255.089"
          },
          ...
      ]
    },
    "timestamp": 1639980423855,  
}
```

**Parameters**
None



### Get TradingView localized configuration info

> **Request**

```shell
curl 'https://api.orderly.org/v1/tv/config?locale=en'
```
```java
```
```python
```
```javascript
```

**Limit: 10 requests per 1 second per IP address**

`GET /v1/tv/config`


> **Response**

```json
{
  "s": "ok",
  "d": {
    "accountSummaryRow": [
      {
        "id": "accountBalance",
        "title": "Account Balance"
      },
      {
        "id": "Equity",
        "title": "Realized P/L"
      },
      {
        "id": "Open Profit",
        "title": "Unrealized P/L"
      }
    ],
    "accountManager": [
      {
        "id": "accountSummary",
        "title": "",
        "columns": [
          {
            "id": "todayPL",
            "title": "Today's P&L"
          },
          {
            "id": "accountValue",
            "title": "Account Value"
          },
          {
            "id": "balance",
            "title": "Balance"
          },
          {
            "id": "totalMargin",
            "title": "Margin"
          },
          {
            "id": "held",
            "title": "Held"
          },
          {
            "id": "buyingPower",
            "title": "Buying Power"
          }
        ]
      }
    ],
    "durations": [
      {
        "id": "GTT",
        "title": "Good Till Time",
        "hasDatePicker": true,
        "hasTimePicker": true,
        "default": true,
        "supportedOrderTypes": [
          "stop",
          "stoplimit"
        ]
      }
    ],
    "orderCustomFields": [
      {
        "id": "commission",
        "title": "Commission",
        "tooltip": "Commission Fees",
        "alignment": "right"
      }
    ],
    "orderHistoryCustomFields": [
      {
        "id": "commission",
        "title": "Commission",
        "tooltip": "Commission Fees",
        "alignment": "right"
      }
    ],
    "positionCustomFields": [
      {
        "id": "exchangeFee",
        "title": "Exchange fee",
        "tooltip": "Exchange fee for the position",
        "alignment": "right"
      },
      {
        "id": "routeFee",
        "title": "Route fee",
        "tooltip": "Route fee for the position",
        "alignment": "right"
      }
    ],
    "pullingInterval": {
      "quotes": 500,
      "orders": 500,
      "positions": 1000,
      "accountManager": 1000,
      "balances": 1000
    }
  }
}
```

**Parameters**

| Name    | Type      | Required      | Description                                                                                 |
|---------|-----------|---------------|---------------------------------------------------------------------------------------------|
| locale  | string    | Y             |                                                                                             |



### Get TradingView history bars

> **Request**

```shell
curl 'https://api.orderly.org/v1/tv/history?symbol=SPOT_NEAR_USDC.e&resolution=D&from=0&to=1683881314470'
```
```java
```
```python
```
```javascript
```

**Limit: 10 requests per 1 second per IP address**

`GET /v1/tv/history`


> **Response**

```json
{
  "s": "ok",
  "t": [
    1547942400,
    1547942460,
    1547942520
  ],
  "o": [
    3667,
    3662.25,
    3664.29
  ],
  "h": [
    3667.24,
    3664.47,
    3664.3
  ],
  "l": [
    3661.55,
    3661.9,
    3662.43
  ],
  "c": [
    3662.25,
    3663.13,
    3664.01
  ],
  "v": [
    34.7336,
    2.4413,
    11.7075
  ]
}
```

**Parameters**

| Name       | Type      | Required | Description                                                                                 |
|------------|-----------|----------|---------------------------------------------------------------------------------------------|
| symbol     | string    | Y        |                                                                                             |
| resolution | string    | Y        |                                                                                             |
| from       | timestamp | Y        |                                                                                             |
| to         | timestamp | Y        |                                                                                             |


### Get TradingView symbol info

> **Request**

```shell
curl 'https://api.orderly.org/v1/tv/symbol_info?group=MSFT'
```
```java
```
```python
```
```javascript
```

**Limit: 10 requests per 1 second per IP address**

`GET /v1/tv/symbol_info`


> **Response**

```json
{
  "s": "ok",
  "symbol": [
    "VIXG2019",
    "AAPLE",
    "EURUSD"
  ],
  "description": [
    "Volatility Index",
    "Apple Inc",
    "EUR/USD"
  ],
  "currency": [
    "USD",
    "USD",
    "USD"
  ],
  "base-currency": [
    null,
    null,
    "EUR"
  ],
  "exchange-listed": [
    "CBOE",
    "NASDAQ",
    "FOREX"
  ],
  "exchange-traded": [
    "CBOE",
    "NASDAQ",
    "FOREX"
  ],
  "minmovement": [
    1,
    1,
    1
  ],
  "minmovement2": [
    0,
    0,
    0
  ],
  "fractional": [
    false,
    false,
    false
  ],
  "pricescale": [
    100,
    100,
    100000
  ],
  "root": [
    "VIX",
    null,
    null
  ],
  "root-description": [
    "Volatility Index",
    null,
    null
  ],
  "has-intraday": [
    true,
    true,
    true
  ],
  "has-no-volume": [
    false,
    false,
    true
  ],
  "type": [
    "futures",
    "stock",
    "forex"
  ],
  "is-cfd": [
    true
  ],
  "ticker": [
    "VIXG2019",
    "AAPLE",
    "EURUSD"
  ],
  "timezone": [
    "America/New_York",
    "America/New_York",
    "America/New_York"
  ],
  "session-regular": [
    "0000-2359:23456",
    "0930-1600",
    "1700-1700"
  ],
  "session-extended": [
    "0000-2359:23456",
    "0400-2000",
    "1700-1700"
  ],
  "session-premarket": [
    null,
    "0400-0930",
    null
  ],
  "session-postmarket": [
    null,
    "1600-2000",
    null
  ],
  "supported-resolutions": [
    [
      "1",
      "3",
      "5",
      "15",
      "30",
      "60",
      "240",
      "D",
      "W"
    ],
    [
      "1",
      "3",
      "5",
      "15",
      "30",
      "60",
      "240",
      "D",
      "W"
    ],
    [
      "1",
      "3",
      "5",
      "15",
      "30",
      "60",
      "240",
      "D",
      "W"
    ]
  ],
  "has-daily": [
    true,
    true,
    true
  ],
  "intraday-multipliers": [
    [
      "1",
      "3",
      "5",
      "15",
      "30",
      "60",
      "240"
    ],
    [
      "1",
      "3",
      "5",
      "15",
      "30",
      "60",
      "240"
    ],
    [
      "1",
      "3",
      "5",
      "15",
      "30",
      "60",
      "240"
    ]
  ],
  "has-weekly-and-monthly": [
    false,
    false,
    false
  ],
  "pointvalue": [
    10,
    1,
    0.00001
  ],
  "expiration": [
    20190213,
    null,
    null
  ],
  "bar-source": [
    "trade",
    "bid",
    "ask"
  ],
  "bar-transform": [
    "openprev",
    "openprev",
    "none"
  ],
  "bar-fillgaps": [
    "true",
    "true",
    "false"
  ],
  "isin": [
    "ZAE000190252",
    "ZAE0001201977",
    "ZAE000567432"
  ],
  "wkn": [
    "A12ABB",
    "A66RTT",
    "A13DDE"
  ]
}
```

**Parameters**

| Name  | Type      | Required | Description                                                                                 |
|-------|-----------|----------|---------------------------------------------------------------------------------------------|
| group | string    | Y        |                                                                                             |



