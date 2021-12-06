---
description: >-
  Creates a FORGET Message referencing Messages where the content and
  item_content will be emptied.
---

# Forget a message

### Returns

The forget message that was just created with the content containing the reason and hashes passed in.

### Usage

```python
from aleph_client.synchronous import forget

forget(account, hashes)
```



### Required parameters

| <p><mark style="color:green;"><strong>account</strong></mark> - <em>Account</em></p><p><strong></strong></p> | <p></p><p>Account submitting the forget message. Should either be:</p><ul><li>the sender of the original message to forget OR the sender of the VM that created the message.</li><li>The address the original message was attributed to</li></ul> |
| ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <mark style="color:green;">**hashes**</mark> - _List of strings_                                             | A list of original message item hashes to forget. Multiple can be passed at once.                                                                                                                                                                 |



### Optional parameters

*   <mark style="color:green;">**reason**</mark> - _string_

    Optional description of why the messages should be forgotten.


*   <mark style="color:green;">**storage\_engine**</mark> - _string either: "ipfs" or "storage"_

    `Default: "storage"`

    Storage engine to use. Possible values: `"storage"`, "`ipfs"`


*   <mark style="color:green;">**channel**</mark> - _string_

    `Default: "TEST"`

    Channel of the message. Ideally, an application would decide and use one channel.


*   <mark style="color:green;">**address**</mark> - _string_

    `Default: None`


*   <mark style="color:green;">**session**</mark> - _Session_

    `Default: None`


*   <mark style="color:green;">**api\_server**</mark> - _string_

    `Default: "https://api2.aleph.im"`

    Target API server.

