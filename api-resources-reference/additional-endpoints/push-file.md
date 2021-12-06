---
description: Push files to storage or IPFS.
---

# Push File

### Returns&#x20;

The functions return the file\_hash for the pushed file.

{% hint style="warning" %}
function\_push\_file pushes the file to someplace that will be garbage collected. Use [.create\_store()](../store/create-a-file.md) to create a STORE Message for it.
{% endhint %}

### Arguments

* <mark style="color:green;">**file\_content**</mark> is **required**.&#x20;
* <mark style="color:green;">**session**</mark> is optional and defaults to `None`.
* <mark style="color:green;">**api\_server**</mark> is optional and defaults to aleph `https://api2.aleph.im`.

### To Storage

```python
def storage_push_file(
    file_content,
    session,
    api_server
)
```

### To IPFS

{% hint style="info" %}
If **you've already stored** a file in an IPFS storage, you can still create a file using the [.create\_store() ](../store/create-a-file.md)to "pin" it, by passing the:\
{  ..., storage\_engine: "**ipfs**" , file\_hash: _ **<**_**ipfs item hash>** , ... }
{% endhint %}

```python
def ipfs_push_file(
    file_content,
    session,
    api_server
)
```
