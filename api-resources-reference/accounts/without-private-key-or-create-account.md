---
description: >-
  If you don’t want to handle the private key yourself, you can use the
  “fallback” helper.
---

# Without private key or Create Account

Aleph-Client will try to find a "device.key" file in the current folder and use it to instantiate the account. If none is found, a new device.key file will be created with a random key.

Choose the blockchain you would like to use and import the get\_fallback_\__account function for the relevant chain module.

{% tabs %}
{% tab title="Cosmos" %}
```python
from aleph_client.chains.cosmos import get_fallback_account

account = get_fallback_account()
```
{% endtab %}

{% tab title="Ethereum" %}
```python
from aleph_client.chains.ethereum import get_fallback_account

account = get_fallback_account()
```
{% endtab %}

{% tab title="NULS" %}
```python
from aleph_client.chains.nuls1 import get_fallback_account

account = get_fallback_account()
```



```python
from aleph_client.chains.nuls2 import get_fallback_account

account = get_fallback_account()
```
{% endtab %}

{% tab title="Polkadot" %}
```python
from aleph_client.chains.substrate import get_fallback_account

account = get_fallback_account()
```
{% endtab %}

{% tab title="Solana" %}
```python
from aleph_client.chains.sol import get_fallback_account

account = get_fallback_account()
```
{% endtab %}
{% endtabs %}
