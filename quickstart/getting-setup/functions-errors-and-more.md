---
description: A few global tips on the API system
---

# Functions, errors and more

### Account instantiated

The API Resources Reference usage and example calls assume you have an account already instantiated. See the [account reference](../../api-resources-reference/accounts/) on how to do so.

### Making Synchronous function calls

```python
from aleph_client.synchronous import fetch_aggregate

fetch_aggregate(...)
```

### Making Asynchronous function calls

```python
from aleph_client.asynchronous import create_aggregate

asyncio.run(create_aggregate(...))
```

### Function types

All functions throughout the API are **Positional\_or**_**\_**_**Keywords** argument functions.

```python
# Examples of creating an aggregate

create_aggregate(account, key, content, address, channel)

create_aggregate(account, key, content, channel=channel, api_server=api_server)

create_aggregate(account=account, key=key, content=content, channel=channel)

```

### Warning Messages & Errors

Warning Message = <mark style="background-color:orange;">"Message published on IPFS but failed to publish on P2P"</mark>. This means one of the two protocols used to publish the message by the node has failed **but one went through.**

### api\_server

Any core channel node multi-address can be used as an api\_server. You can find a list of core nodes here and their multi-address in their "info".

Example of one of the nodes multi-address that can be found on [https://account.aleph.im/](https://account.aleph.im/#/): `/ip4/`<mark style="color:purple;">**`65.21.141.116`**</mark>`/tcp/4025/p2p/QmSuf7N2753dAeiwXmXVPdNW1JBvzhb43t6wXVaR75w64S)`.&#x20;

Api Server Url would look like this:

`https://<ip-address>` or `http://<ip-address>:4024`

{% hint style="info" %}
<mark style="color:blue;">\[Future Release]</mark> The Aleph-Client will provide load-balancing in the future so the users don't have to pick one.&#x20;
{% endhint %}

Reasons for choosing a different api\_server:

* The latency decreases the closer the dApp is from the server
* Some offer HTTPS others don't (yet).&#x20;

\
