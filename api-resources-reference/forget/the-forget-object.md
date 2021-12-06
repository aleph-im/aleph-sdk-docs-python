# The forget Object

The forget object inherits from the `Message` object's structure as follows:

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
  reason:
  hashes
item_hash:
item_type:
```



| Attributes                                                                                                           | Description                                                                                                                                                                    |
| -------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <mark style="color:blue;">**channel**</mark> - text                                                                  | Channel of the message. Ideally, an application would decide and use one channel.                                                                                              |
| <mark style="color:blue;">**time**</mark> - float                                                                    | Unix timestamp when the message was published (in seconds).                                                                                                                    |
| <mark style="color:blue;">**type**</mark> - text                                                                     | <p>Text representing the message object type.</p><p>Value is <code>FORGET</code></p>                                                                                           |
|                                                                                                                      |                                                                                                                                                                                |
| <mark style="color:blue;">**chain**</mark> <mark style="color:blue;"></mark><mark style="color:blue;"></mark> - text | <p>The chain used by the sender's account. <br>Value can be <code>NULS2</code>, <code>ETH</code>, <code>DOT</code>, <code>CSDK</code>, <code>SOL</code>, <code>AVAX</code></p> |
| <mark style="color:blue;">**sender**</mark> - <mark style="color:blue;"></mark> text                                 | Chain address who sent and is signing the Store Message.                                                                                                                       |
|                                                                                                                      | -                                                                                                                                                                              |
| <mark style="color:blue;">**hash\_type**</mark> - optional text                                                      | Defaults to sha256. This is the only supported value for now.                                                                                                                  |
| <mark style="color:blue;">**item\_content**</mark> - JSON text                                                       | <p>JSON string representing the content of the forget. </p><p>See below for the content of the string.</p>                                                                     |
|                                                                                                                      |                                                                                                                                                                                |
| item\_content.<mark style="color:blue;">**reason**</mark>** ** - string                                              | A description of why the messages are being forgotten.                                                                                                                         |
| item\_content.<mark style="color:blue;">**hashes**</mark> - list of strings                                          | List of message item hashes to be removed.                                                                                                                                     |
|                                                                                                                      |                                                                                                                                                                                |
| <mark style="color:blue;">**item\_hash**</mark>** ** - hash                                                          | The hash of the item\_content encrypted with SHA256.                                                                                                                           |
| <mark style="color:blue;">**item\_type**</mark> - optional text                                                      | Storage methods used for the content. Value can be: `ipfs`, `inline` or `storage`                                                                                              |





