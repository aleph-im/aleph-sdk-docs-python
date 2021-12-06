---
description: Store a content object to storage or IPFS
---

# Push Value

### Returns

A hash corresponding to the `message.item_hash` found in the `Message` object.

### Arguments

* <mark style="color:green;">**content**</mark> is **required**.&#x20;
* <mark style="color:green;">**session**</mark> is optional and defaults to None.
* <mark style="color:green;">**api\_server**</mark> is optional and defaults to aleph https://api2.aleph.im.

### To Storage

```python
def storage_push(
    content, 
    session, 
    api_server
)
```

### To IPFS

```python
def ipfs_push(
    content, 
    session, 
    api_server
) 
```

