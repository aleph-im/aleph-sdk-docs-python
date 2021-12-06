---
description: >-
  Writing to the network requires a blockchain account which will serve as the
  account on the resource generated.
---

# Writing to the Network

{% hint style="success" %}
Posting to the network is done in two steps:

1. Connect a blockchain account
2. Create a resource
{% endhint %}

### 1. Connect a blockchain account

The aleph-client currently supports the following chains:

* NULS 1.0 and NULS 2.0
* Ethereum
* Polkadot - Substrate
* Cosmos SDK
* Solana

Whether you connect to an existing blockchain account or create a new one, the account returned by the library is an object responding to 2 functions:

* .get\_address()
* .get\_public_\__key()

```python
// Example of an account imported or created through aleph-client

account.get_address()
account.get_public_key()
```

#### ➡️  With an existing blockchain account private key

You can connect **any existing blockchain account** by using the relevant chain module and passing in the **private key or mnemonics** of the account.

{% tabs %}
{% tab title="Cosmos" %}
```python
from aleph_client.chains.cosmos import CSDKAccount

account = CSDKAccount("<Your Private Key Here>")
```
{% endtab %}

{% tab title="Ethereum" %}
```python
from aleph_client.chains.ethereum import ETHAccount

account = ETHAccount("<Your Private Key Here>")
```
{% endtab %}

{% tab title="NULS" %}
```python
from aleph_client.chains.nuls1 import NULSAccount

account = NULSAccount("<Your Private Key Here>")
```



```python
from aleph_client.chains.nuls2 import NULSAccount

account = NULSAccount("<Your Private Key Here>")
```
{% endtab %}

{% tab title="Polkadot" %}
```python
from aleph_client.chains.substrate import DOTAccount

account = DOTAccount("<Your Mnemonics Here>")
```
{% endtab %}

{% tab title="Solana" %}
```python
from aleph_client.chains.sol import SOLAccount

account = SOLAccount("<Your Private Key Here>")
```
{% endtab %}
{% endtabs %}

#### ➡️  Without a private key

Aleph-Client will try to find a "device.key" file in the current folder and use it to instantiate the account. If none is found, a new device.key file will be created with a random key.

Choose the blockchain you would like to use and import the get\_fallback_\__account function for the relevant chain module.

```python
# Replace "chains.ethereum" by chains.yourchain as above 
from aleph_client.chains.ethereum import get_fallback_account

account = get_fallback_account()
```

{% hint style="info" %}
More details on importing and creating an account are available[ here](../../api-resources-reference/accounts/)
{% endhint %}

### 2. Create a Resource

```python
from aleph_client.chains.ethereum import ETHAccount
from aleph_client.synchronous import create_post

account = ETHAccount("<Your Private Key Here>")

response = create_post(
    account, 
    {'content': 'test'}, 
    post_type='testtype', 
    channel='MY_CHANNEL')

```

🎉 A `Message` object, with a POST type, has been created and is returned.

{% code title="RESPONSE" %}
```python
{'chain': 'NULS2',
 'channel': 'MY_CHANNEL',
 'sender': 'NULSd6HgaaV62iEcTZSWoaTrA3U7Jr7Vv1nXS',
 'type': 'POST',
 'time': 1573570575.281997,
 'item_content': 
     '{"type":"testtype",
       "address":"NULSd6HgaaV62iEcTZSWoaTrA3U7Jr7Vv1nXS",
       "content":{"content":"test"},
       "time":1573570575.2818618}',
 'item_hash': '02afdbf33ff2c6ddb46349298a4598a8801cec61dbaa8f3a17ba9d1ad6dd8cb1',
 'signature': 'G7yJjMCPgvX04Dd9rsz0oEuuRFa4PfuKAMOPA3Oblf6vd5YA1x15jvWLL2WycnnzYLEl0usjTiVxBl530ZOmYgw='}
```
{% endcode %}

{% hint style="info" %}
All **post**, **aggregate**, and **store** **resources** created in Aleph are inherently <mark style="background-color:green;">Message</mark> Objects. Depending on the type of resource created, the **item\_content** object keys will differ.
{% endhint %}

### 3. Going further

Learn more about how you can create, update and query [Post](../../api-resources-reference/posts/), [Aggregate](../../api-resources-reference/aggregates/) and [Store](../../api-resources-reference/store/) objects.&#x20;
