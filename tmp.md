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
```JSON
{
    "exchange":"EXCHANGE",
    "channel":"getBalance"
}
```
* Response
<!--Code Block-->
```JSON
{
    "channel":"getBalance",
    "data":{"symbol":amount}
}
```
Example _v1
```JSON
{
    "channel":"getBalance",
    "data":{
        "BTC":1,
        "ETH":0.05,
        ...
        }
}


### **getBalance**
* Request
<!--Code Block-->
```JSON
{
    "exchange":"EXCHANGE",
    "channel":"getBalance"
}
```
* Response
<!--Code Block-->
```JSON
{
    "channel":"getBalance",
    "data":{"symbol":amount}
}
```
Example _v1
```JSON
{
    "channel":"getBalance",
    "data":{
        "BTC":1,
        "ETH":0.05,
        ...
        }
}