---
description: >-
  Call the .create_store() function to create a store object message and save a
  file.
---

# Create a file

### Returns

The store object that was just created with a couple of extra attributes.

{% hint style="info" %}
If you've already stored a file in an IPFS storage, you can still create a file using the .create\_store() to "pin" it, by passing the:\
{  ..., storage\_engine: "**ipfs**" , file\_hash: _ **<**_**ipfs item hash>** , ... }

See how to [push a file in IPFS file storage](../additional-endpoints/push-file.md).
{% endhint %}

### Usage

```python
def create_store(
    account,
    address,
    file_content,
    file_hash,
    guess_mime_type,
    ref,
    storage_engine,
    extra_fields,
    channel,
    session,
    api_server,
)
```



### Required Arguments

| <mark style="color:green;">**account**</mark> _- Account_ | Account the Store should be associated with or the account that submitted the Store. |
| --------------------------------------------------------- | ------------------------------------------------------------------------------------ |



### Optional Arguments

* 2\. <mark style="color:green;">**address**</mark>** ** _- string_\
  _`Default: None`_\
  Address the Store should be associated with or the address that submitted the Store. <mark style="background-color:yellow;">To store on behalf of an address that is not the account signing see the</mark> [<mark style="background-color:yellow;">aggregate section on security key</mark>](../aggregates/security-key.md)\
  \

*   3\. <mark style="color:green;">**file\_content**</mark>** ** _- bytes_\
    _`Default: None`_\
    File content is ignored if a file\_hash is passed. The file you want to store. file_\__content will be pushed to either storage or ipfs function of the storage\_engine chosen.

    **REQUIRED if no `file_hash`**\

* 4\. <mark style="color:green;">**file\_hash**</mark>** ** _- string_\
  _`Default: None`_\
  This takes precedence over the `file_content`\
  Use this if you already have uploaded the file to storage or ipfs yourself.\
  **REQUIRED if no `file_content`**\

* 5\. <mark style="color:green;">**guess\_mime\_type**</mark> _- boolean_\
  ****_`Default: False` _ \
  __If set to True and no mime\_type is passed in the extra\_fields argument, the mime\_type will be set to magic.from\_buffer \

* 6\. <mark style="color:green;">**ref**</mark> _- string_\
  _`Default: None`_\
  ****if ref is present, it will be assigned to the ref key of extra\_fields.\

* 7\. <mark style="color:green;">**storage\_engine**</mark>** ** _- string_\
  _`Default: "storage"`_\
  Storage engine to use. \
  Use "storage" for aleph.im built-in storage or "ipfs" for an ipfs compatible storage. Possible values: `storage`, `ipfs`\

*   8\. ** **<mark style="color:green;">**extra\_fields**</mark>** ** _- dictionary_\
    ****_`Default: None`_

    <mark style="background-color:yellow;">Any custom fields to save alongside the file in the message item\_content.</mark>\
    ****Mime type can be passed through this { mime\_type: \<mime type here> }. See guess mime type argument for details.\

* 9\. <mark style="color:green;">**channel**</mark>** ** _- string_\
  _`Default: "TEST"`_\
  __Channel of the message. Ideally, an application would decide and use one channel.\

* 10\. <mark style="color:green;">**session**</mark>\
  _`Default: None`_\
  __
*   11\. <mark style="color:green;">**api\_server**</mark>** ** _- string_\
    _`Default: "https://api2.aleph.im`_\
    __Select an API server accepting files.

    ex: [https://api1.aleph.im](https://api2.aleph.im) and "[https://api2.aleph.im](https://api2.aleph.im)" are two available API servers accepting files.



