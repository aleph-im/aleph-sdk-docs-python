---
description: Retrieves the content value for the queried key for an address.
---

# Retrieve one key

### Returns

The content for the key.&#x20;

If no aggregate for the address and the key is found, null will be returned.

If the address doesn't have an aggregate, the resource not found error will be returned.



### Usage

```python
def fetch_aggregate(
    address,
    key,
    session,
    api_server,
)
```



### Required Arguments

| <mark style="color:green;">**address**</mark>** ** _- string_                | The chain address the aggregate was created for. |
| ---------------------------------------------------------------------------- | ------------------------------------------------ |
| <mark style="color:green;">**key**</mark>**          **           _- string_ | The key the aggregate was created for.           |



### Optional Arguments

* 3\. <mark style="color:green;">**session**</mark>\
  `Default: None`\

* 4\. <mark style="color:green;">**api\_server**</mark>** ** _- string_\
  _`Default:"https://api2.aleph.im`_\
  Target API Server



### Example

```python
>>> from aleph_client.synchronous import fetch_aggregate
>>> fetch_aggregate("0x06DE0C46884EbFF46558Cd1a9e7DA6B1c3E9D0a8",
... "profile")

{"bio": "tester", "name": "Moshe on Ethereum"}
```
