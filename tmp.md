<!--Heading-->

# **WebSocket API documentation**

EXCHANGE types
* Binance 
* CoinEx
* Poloniex
* Huobi
* Livecoin
* Otcbtc
* Gateio
* Cobinhood
<br><br>

REQUEST types
* getBalance       
* placeOrder     
* placeSubOrder      
* getAllOpenOrders      
* getAllCompletedOrders
* cancelOrder
* getOrder

---
---

<!--getBalance-->
### **getBalance**
* Request

<!--Code Block-->
```JavaScript
{
    "exchange":"EXCHANGE",
    "channel":"getBalance"
}
```
* Response
```JavaScript
{
    "channel":"getBalance",
    "data":{"symbol":amount}
}
```
_Example getBalance:_ 
```JavaScript
{
    "channel":"getBalance",
    "data":{
        "BTC":1,
        "ETH":0.05,
        ...
        }
}
```
---
<!--getBalance-->
### **getAllCompletedOrders + getAllOpenOrders + getOrder**
<p>These three requests and responses are similar, the only difference is the name of the channel. </p>
<p>The request, response and example which are shown below are using the getAllOpenOrders channel.
<br>
To change the channel, one need only replace the name of the channel.</p>

* Request

<!--Code Block-->
```JavaScript
{
    "exchange":"EXCHANGE",
    "channel":"getAllOpenOrders",
    "pair":"symbol-symbol"
}
```
* Response
```JavaScript
{
    "channel":"GetAllOpenOrders",
    "data":[{
        "OrderId":,
        "Result":,
        "Message":,
        "Amount":,
        "AmountFilled":,
        "Price":,
        "AveragePrice":,
        "OrderDate":,
        "Symbol":,
        "IsBuy":,
        "Fees":,
        "FeesCurrency":,
        "OrderStatus":
        }]
}
```
**Parameters:**

| Name | Type |
| --- | --- |
| OrderId | string |
| Result | int (matched by enum with OrderStatus) |
| Message | string |
| Amount | double |
| AmountFilled | double |
| Price | double |
| AveragePrice | double |
| OrderDate | System.DateTime |
| Symbol | string |
| IsBuy | bool |
| Fees | double |
| FeesCurrency | string |
| OrderStatus | string |


_Example GetAllOpenOrders:_
```JavaScript
{
    "channel":"GetAllOpenOrders",
    "data":[{
        "OrderId":"123456789",
        "Result":3,
        "Message":null,
        "Amount":0.01,
        "AmountFilled":0.01,
        "Price":0.052,
        "AveragePrice":0. 52,
        "OrderDate":"2018-07-24T07:10:33Z",
        "Symbol":"BTCETH",
        "IsBuy":false,
        "Fees":5.8e-7,
        "FeesCurrency":null,
        "OrderStatus":"Filled"
        }
        ...
        ]
}
```