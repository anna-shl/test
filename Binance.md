<!--Heading-->

# **Binance**

**Hard-Limits**

* 1,200 request weight per minute (keep in mind that this is not necessarily the same as 1,200 requests)
* 10 orders per second
* 100,000 orders per 24 hours

---
---
The Binance exchange has 5 standard levels that will always be performed, these levels are initialize the exchange.
<br>
The 6th level is the one that will execute the request.

**Initialization**
<br>
<span style="color:red;">The request and responses formats are located in this link: 
    [Requsest and response](https://github.com/anna-shl/test/blob/master/tmp.md) </span>

1. The RequestHandler class contains all the request task types, each request creates an instance of the exchange. The request types are as follows: GetBalance, PlaceOrder, PlaceSubOrder, GetAllOpenOrders, GetAllCompletedOrders CancelOrder and GetOrder.

2.	The standard URLs are created, Base URL, Base URL for the web socket, Private URL and a withdrawal URL.
When the public constructor of the ExchangeBinanceAPI is called the abstract classes come in to use.
3.	ExchangeAPI class is one of the abstract classes which initialize the functions and parameters that will be used. 
The APIs list is initialized with all the exchanges that our project provides.
The RequestMethod is initialized as “GET” and RequestTimeout, RequestWindow, RequestCachePolicy and the cache itself are initialized as well.
NonceStyle and NonceOffsetare declared.

4.	Once initialization is done we advance with the constructor of the ExchangeBinanceAPI.
The requestWindow, NonceStyle, NonceOffset, SymbolSeparator, SymbolIsReversed are initialized.

5.	After creating the Binance instance we continue in the RequestHandler class.
In this stage there is a need to use the private and public keys which are stored in the BaseAPI class for now. In this development stage, the keys are stored in the code. As the project grows the keys will be encrypted and stored in the database.

**Channel: “getBalance”**
<br>There are a few tasks to perform before retrieving the balance of the account. <br>
In the ExchangeBinanceAPI class noncePayload dictionary is created and stored in a “payload” variable.<br>
A nonce is generated and placed in the “payload” by the name: nonce.<br>
A recWindow is placed in the “payload”.<br>
The request method (“GET”) is established. <br>
A timestamp is placed in the “payload”.<br>
Once these tasks are completed a response is sent to the client with the name of the channel (“getBalance”) and the data. The data consists of currencies and their amount which the exchange provides.<br>

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
**Channel: getAllOpenOrders**