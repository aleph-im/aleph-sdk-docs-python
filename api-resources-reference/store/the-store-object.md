# The store object

The store object inherits from the `Message` object's structure as follows:

```
// Message info
channel:
time:
type:

// Sender info
chain:
sender:

// Content
hash_type:
item_content:
  address:
  item_type:
  item_hash:
  time:
item_hash:
item_type:
```



| Attributes                                                                                                                                       | Description                                                                                                                                                                     |
| ------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <mark style="color:blue;">**channel**</mark> - text                                                                                              | Channel of the message. Ideally, an application would decide and use one channel.                                                                                               |
| <mark style="color:blue;">**time**</mark> - float                                                                                                | Time the store was created. in seconds                                                                                                                                          |
| <mark style="color:blue;">**type**</mark> - text                                                                                                 | <p>Text representing the message object type.</p><p>Value is <code>STORE</code></p>                                                                                             |
|                                                                                                                                                  |                                                                                                                                                                                 |
| <mark style="color:blue;">**chain**</mark> <mark style="color:blue;"></mark><mark style="color:blue;"></mark> - text                             | <p>The chain used by the sender's account. <br>Value can be <code>NULS2</code>, <code>ETH</code>, <code>DOT</code>, <code>CSDK</code>, <code>SOL</code>, <code>AVAX</code></p>  |
| <mark style="color:blue;">**sender**</mark> - <mark style="color:blue;"></mark> text                                                             | Chain address who sent and is signing the Store Message.                                                                                                                        |
|                                                                                                                                                  | -                                                                                                                                                                               |
| <mark style="color:blue;">**hash\_type**</mark> - optional text                                                                                  | Defaults to sha256. This is the only supported value for now.                                                                                                                   |
| <mark style="color:blue;">**item\_content**</mark> - JSON text                                                                                   | <p>JSON string representing the content of the aggregate. </p><p>See below for the content of the string.</p>                                                                   |
|                                                                                                                                                  |                                                                                                                                                                                 |
| item\_content.<mark style="color:blue;">**type**</mark>** ** - text                                                                              | <p>A string of your choice representing what the post is. Should be simple and lowercase.</p><p>For instance, for a blog post you could have:</p><p>a "blog" or a "comment"</p> |
| item\_content.<mark style="color:blue;">**address**</mark> - text                                                                                | Chain address to associate the `Post` with.                                                                                                                                     |
| item\_content.<mark style="color:blue;">**time**</mark>** -** timestamp                                                                          | Time the object was created.                                                                                                                                                    |
| item\_content.<mark style="color:blue;">**item**</mark>_<mark style="color:blue;">**\_**</mark>_<mark style="color:blue;">**hash**</mark> - text | Text representing the file stored. It can be used to retrieve the object stored through the retrieve endpoint.                                                                  |
|                                                                                                                                                  |                                                                                                                                                                                 |
| <mark style="color:blue;">**item\_hash**</mark>** ** - hash                                                                                      | The hash of the item\_content encrypted with SHA256.                                                                                                                            |
| <mark style="color:blue;">**item\_type**</mark> - optional text                                                                                  | `ipfs`, `inline` or `storage`                                                                                                                                                   |
