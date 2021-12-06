---
description: Retrieves the value for the queried keys or all keys for an address.
---

# List all keys & values

### Returns

A dictionary of keys and their value object.



### Usage

```python
def fetch_aggregates(
    address,
    keys,
    session,
    api_server,
)
```



### Required Arguments

| <mark style="color:green;">**address**</mark>** ** _- string_ | The chain address the aggregate was created for. |
| ------------------------------------------------------------- | ------------------------------------------------ |



### Optional Arguments

* 2\. <mark style="color:green;">**keys**</mark>** ** _- Iterable of strings_\
  _`Default: None`_\
  Keys to retrieve for the address. <mark style="background-color:yellow;">If none are passed,</mark> <mark style="color:yellow;background-color:yellow;">**all keys and values**</mark> <mark style="background-color:yellow;">are returned.</mark>\

* 3\. <mark style="color:green;">**session**</mark>\
  _`Default: None`_\
  this is the explanation\

* 4\. <mark style="color:green;">**api\_server**</mark>** ** _- string_\
  _`Default: "https://api2.aleph.im"`_\
  Target API server



### Example

```python
>>> from aleph_client.synchronous import fetch_aggregates
>>> fetch_aggregates(account.get_address(), 'testkey')
{'a': 1, 'b': 2}
```
