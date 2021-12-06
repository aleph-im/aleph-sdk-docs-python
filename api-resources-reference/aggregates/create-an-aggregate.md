---
description: >-
  Call the .create_aggregate() function to create an aggregate of a key-value
  pair for an address.
---

# Create an aggregate

### Returns

The function will return the aggregate message object created.&#x20;



### Usage

```python
def create_aggregate(
    account,
    key,
    content,
    address,
    channel,
    session,
    api_server)
```



### Required Arguments

| <mark style="color:green;">**account**</mark>  <mark style="color:green;"></mark><mark style="color:green;"></mark>  _- Account_                                             | <p>Sender's account to use for signing. <br>The account address will be the aggregate's address if no different optional address is passed.</p> |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| <mark style="color:green;">**key**</mark> <mark style="color:green;"></mark>         <mark style="color:green;"></mark><mark style="color:green;"></mark>         _- string_ | Key to mutate                                                                                                                                   |
| <mark style="color:green;">**content**</mark>  _- object_                                                                                                                    | The value content object to save for the key.                                                                                                   |



### Optional Arguments

* 4\. <mark style="color:green;"></mark> <mark style="color:green;"></mark><mark style="color:green;">**address**</mark>  _- string_\
  _`Default: None`_\
  Address the aggregate should be associated with. \
  One can pass a <mark style="background-color:yellow;">different address than the account address to update the aggregate</mark> for this target address (see[ update for another address](update-an-aggregate.md#update-for-another-address) and [security key](security-key.md)). \
  If none is passed, the aggregate will be for the account address.\

* 5\. <mark style="color:green;">**channel**</mark> _- string_\
  _`Default: "TEST"`_\
  __Channel of the message. Ideally, an application would decide and use one channel.\

* 6\. <mark style="color:green;">**session**</mark> \
  _`Default: None`_\
  __
* 7\. <mark style="color:green;"></mark> <mark style="color:green;"></mark><mark style="color:green;">**api\_server**</mark>  _- string_\
  _`Default: "https://api2.aleph.im"`_\
  __Target API Server



### Example

```python
>>> from aleph_client.synchronous import create_aggregate

>>> create_aggregate(
...    account, 'testkey', {'a': 1, 'b': 2}, channel='MY_CHANNEL')
```
