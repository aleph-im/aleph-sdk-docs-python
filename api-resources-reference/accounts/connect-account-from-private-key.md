# Connect Account from private key

You can connect **any existing blockchain account** by using the relevant chain module and passing in the **private key or mnemonics** of the account.

{% tabs %}
{% tab title="Cosmos" %}
**Usage**

```
CSDKAccount(
    private_key=None,
    hrp="cosmos")
```

* &#x20;<mark style="background-color:green;"></mark> <mark style="background-color:green;"></mark><mark style="background-color:green;">**private\_key**</mark> <mark style="background-color:green;"></mark><mark style="background-color:green;"></mark> _- string_

__

**Example**

```python
from aleph_client.chains.cosmos import CSDKAccount

account = CSDKAccount("<Your Private Key Here>")
```
{% endtab %}

{% tab title="Ethereum" %}
**Usage**

```
ETHAccount(
    private_key=None)
```

* <mark style="background-color:green;">**private\_key**</mark> _- string_

__

**Example**

```python
from aleph_client.chains.ethereum import ETHAccount

account = ETHAccount("<Your Private Key Here>")
```
{% endtab %}

{% tab title="NULS" %}
**Usage for Nuls1**

```
NULSAccount(
    private_key=None,
    chain_id=8964)
```



* &#x20;<mark style="background-color:green;"></mark> <mark style="background-color:green;"></mark><mark style="background-color:green;">**private\_key**</mark> <mark style="background-color:green;"></mark><mark style="background-color:green;"></mark> _- string_
*   chain\_id _- integer_

    `Default: 8964`

****

**Usage for Nuls2**

```
NULSAccount(
    private_key=None,
    chain_id=1,
    prefix="NULS")
```

****

* <mark style="background-color:green;">**private\_key**</mark> _- string_
* chain\_id _- integer_
*   prefix _- string_

    `Default: "NULS"`





**Examples for Nuls 1 and 2**

```python
from aleph_client.chains.nuls1 import NULSAccount

account = NULSAccount("<Your Private Key Here>")
```



```python
from aleph_client.chains.nuls2 import NULSAccount

account = NULSAccount("<Your Private Key Here>")
```
{% endtab %}

{% tab title="Substrate" %}
**Usage**

```
DOTAccount(
    mnemonics=None,
    address_type=42)
```

****

*   &#x20;<mark style="background-color:green;">**mnemonics**</mark> _- account mnemonics phrase_

    Should be passed in order to instantiate the account


*   &#x20;<mark style="background-color:green;">address\_type</mark> _- optional integer_

    `Default: 42`

    Generic Substrate has `00101010b` as the address type, `42` is in decimal.





**Example**

```python
from aleph_client.chains.substrate import DOTAccount

account = DOTAccount("<Your Mnemonics Here>")
```
{% endtab %}

{% tab title="Solana" %}
**Usage**

```
SOLAccount(
    private_key=None)
```

****

*   <mark style="background-color:green;">**private\_key**</mark> _- string_

    The private key for the account



**Example**

```python
from aleph_client.chains.sol import SOLAccount

account = SOLAccount("<Your Private Key Here>")
```
{% endtab %}
{% endtabs %}



Accounts will respond to the following functions:

* .get\_address()
* .get\_public_\__key()
