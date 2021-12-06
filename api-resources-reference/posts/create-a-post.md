---
description: Call the create_post() function to create a Post Message.
---

# Create a post

### Returns

The post object that was just created.



### Usage

```python
def create_post(
    account,
    post_content,
    post_type,
    ref,
    address,
    channel,
    session,
    api_server,
    inline,
    storage_engine,
)
```



### Required Arguments

| <mark style="color:green;">**account**</mark>         _- Account_ | <p>Address the Post should be associated with <br>or the address that submitted the Post.</p>                                                                                                                                                                                                                                               |
| ----------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <mark style="color:green;">**post\_content**</mark> _- Any_       | <p>The content to save to the <code>item_content.content</code> of the post message.</p><p></p><p><mark style="background-color:yellow;">To take full advantage of the search abilities, make the post_content an object with a <code>tags</code> key</mark>. Tags are searchable, see <a href="list-all.md">list all posts</a>.</p><p></p> |
| <mark style="color:green;">**post\_type**</mark>       _- string_ | <p>A lowercase string of your choice for the <code>item_content.type</code> of the post message.</p><p><br> ex: <code>"amend"</code>, <code>"blog"</code>, <code>"chat"</code>, <code>"comment"</code></p>                                                                                                                                  |

{% hint style="info" %}
post\_content has a limit size of just under 16Mb, the biggest document size on MongoDB. &#x20;

To save a document above 16Mb, the content should be stored in a Store Item and then make a reference for the item in a Post.&#x20;



<mark style="color:blue;">\[Next Release]</mark> Right now there is a limit of about 1Mb on the post\_content.
{% endhint %}



### Optional Arguments

* 4\. <mark style="color:green;">**ref**</mark>** ** _- Any_\
  _`Default: None`_\
  A searchable reference string of your choice to save to the `item_content.ref`. Can be the reference to another post, an address, transaction hash, etc.\

* 5\. <mark style="color:green;">**address**</mark>** ** _- string_\
  _`Default: None`_\
  Address the Post should be associated with or the address that submitted the Post. <mark style="background-color:yellow;">To post on behalf of an address that is not the account signing see the</mark> [<mark style="background-color:yellow;">aggregate section on security key</mark>](../aggregates/security-key.md)\

* 6\. <mark style="color:green;">**channel**</mark> _- string_\
  _`Default: "TEST"`_\
  Channel of the message. Ideally, an application would decide and use one channel.\

* 7\. <mark style="color:green;">**session**</mark>\
  _`Default: None`_\

* 8\. <mark style="color:green;">**api\_server**</mark>** ** _- string_\
  _`Default: "https://api2.aleph.im"`_\
  Target API server\

*   9\. <mark style="color:green;">**inline**</mark>** ** _- boolean_\
    _`Default: true`_\
    Should the message be stored as a separate file or inserted inline?&#x20;

    :information\_source: Set it to false for data that could fall under GDPR. \

* 10\. <mark style="color:green;">**storage\_engine**</mark> _- string_\
  _`Default: "storage"`_\
  Storage engine to use. Possible values: `"storage"`, "`ipfs"`\




### Example

```python
>>> from aleph_client.synchronous import create_post

>>> create_post(
      account, 
      {'content': 'test'}, 
      post_type='testtype', 
      channel='MY_CHANNEL')

{'chain': 'NULS2',
 'channel': 'MY_CHANNEL',
 'sender': 'NULSd6HgaaV62iEcTZSWoaTrA3U7Jr7Vv1nXS',
 'type': 'POST',
 'time': 1573570575.281997,
 'item_content': '{
   "type":"testtype",
   "address":"NULSd6HgaaV62iEcTZSWoaTrA3U7Jr7Vv1nXS",
   "content":{"content":"test"},
   "time":1573570575.2818618}',
 'item_hash': '02afdbf33ff2c6ddb46349298a4598a8801cec61dbaa8f3a17ba9d1ad6dd8cb1',
 'signature': 'G7yJjMCPgvX04Dd9rsz0oEuuRFa4PfuKAMOPA3Oblf6vd5YA1x15jvWLL2WycnnzYLEl0usjTiVxBl530ZOmYgw='}
```

