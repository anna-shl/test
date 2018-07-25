<!--Heading-->
# **API documentation**

EXCHANGE types:
<!--UL-->
* Binance
* CoinEx
* Poloniex
* Huobi
* Livecoin
* Otcbtc
* Gateio
* Cobinhood

---
---
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
<!--Code Block-->
```JavaScript
{
    "channel":"getBalance",
    "data":{"symbol":amount}
}
```
Example _v1
```JavaScript
{
    "channel":"getBalance",
    "data":{
        "BTC":1,
        "ETH":0.05,
        ...
        }
}
