---
description: >-
  Sign and broadcast the Message to either ipfs or storage. Serializes content
  object, if needed. The server adds the item_hash from the content to the
  message object.
---

# Sign and Broadcast Message

### Returns

The message with a content attribute. The content attribute value is the content that was passed in.

### Usage

```python
def submit(
    account,
    content,
    message_type,
    channel,
    api_server,
    storage_engine,
    session,
    inline,
)
```



### Required Arguments

| <mark style="color:green;">**account**</mark>** ** _- Account_ | Address that submits the Message.                                                                                         |
| -------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| <mark style="color:green;">**content**</mark> _- Dictionary_   | Object to save                                                                                                            |
| <mark style="color:green;">**message\_type**</mark> _- string_ | <p>Message Type.</p><p>Could be <code>AGGREGATE</code>, <code>POST</code> or <code>STORE</code>, <code>PROGRAM</code></p> |

### Optional Arguments

* 4\. <mark style="color:green;">**channel**</mark> _- string_\
  _`Default: "IOT_TEST"`_\
  Channel of the message. Ideally, an application would decide and use one channel.\

* 5\. <mark style="color:green;">**api\_server**</mark> _- string_\
  _`Default: "https://api2.aleph.im"`_\
  Select an API server accepting files. [https://api1.aleph.im](https://api2.aleph.im) and "[https://api2.aleph.im](https://api2.aleph.im)" are two available api servers accepting files.\

* 6\. <mark style="color:green;">**storage\_engine**</mark> _- string_\
  _`Default: "storage"`_\
  Storage engine to use. \
  Use "storage" for aleph.im built-in storage or "ipfs" for an ipfs compatible storage.\
  Possible values: `storage`, `ipfs`\

* 7\. <mark style="color:green;">**session**</mark>\
  _`Default: None`_\
  \

*   8\. <mark style="color:green;">**inline**</mark> _- boolean_\
    _`Default: True`_

    If true, the content will be serialized otherwise the content is saved to:&#x20;

    * ipfs if "ipfs" is passed as `storage_engine`&#x20;
    * storage otherwise.
