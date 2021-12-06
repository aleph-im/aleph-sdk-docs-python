---
description: >-
  Use the *create_aggregate* endpoint to update a specific key value from an
  existing Aggregate.
---

# Update a key

{% hint style="info" %}
Since creating an Aggregate message mutates the value of the specific key, if the key exists, the value object will be updated (mutated) with the object you are saving.
{% endhint %}

### Example

```python
>>> from aleph_client.synchronous import create_aggregate, fetch_aggregate

>>> create_aggregate(
...    account, 'testkey', {'a': 1, 'b': 2}, channel='MY_CHANNEL')

>>> fetch_aggregate(account.get_address(), 'testkey')
{'a': 1, 'b': 2}

# UPDATING THE AGGREGATE
>>> create_aggregate(
...    account, 'testkey', {'a': 2, 'c': 4}, channel='MY_CHANNEL')

>>> fetch_aggregate(account.get_address(), 'testkey')
{'a': 2, 'b': 2, 'c': 4}
```

### Update for another address

To update a target address that is not yours, the target address should have a [<mark style="color:blue;">**security key**</mark>](security-key.md) in their aggregate where your address and the aggregate keys allowed to be changed are listed in an <mark style="color:blue;">**authorizations**</mark> object value.

```python
>>> fetch_aggregate('TARGET_ADDRESS', 'security')
{'authorizations': [
  {
    'address': 'YOUR_ADDRESS',
    'types': ['AGGREGATE'],
    'aggregate_keys': ['testkey']
  }
]}

>>> create_aggregate(
...    account, 'testkey', {'a': 1, 'b': 2}, channel='MY_CHANNEL',
...    address='TARGET_ADDRESS')
```

