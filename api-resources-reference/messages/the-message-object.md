# The message object

```
// Message info
type:
channel:
time:

// Sender info
sender:
chain:

// Content
item_hash:
item_content:
item_type:
hash_type:
```

|                                                                  |                                                                                                                                                                                                                                                                                                                |
| ---------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <mark style="color:blue;">**channel**</mark> - text              | Channel of the message. Ideally, an application would decide and use one channel.                                                                                                                                                                                                                              |
| <mark style="color:blue;">**time**</mark> - float                | Time the message was created in seconds.                                                                                                                                                                                                                                                                       |
| <mark style="color:blue;">**type**</mark> - text                 | <p>Text representing the message object type.</p><p>Value is one of <code>POST</code>, <code>AGGREGATE</code> or <code>STORE</code></p>                                                                                                                                                                        |
|                                                                  |                                                                                                                                                                                                                                                                                                                |
| <mark style="color:blue;">**chain**</mark> - text                | <p>The chain used by the sender's account. <br>Value can be <code>NULS2</code>, <code>ETH</code>, <code>DOT</code>, <code>CSDK</code>, <code>SOL</code>, <code>AVAX</code></p>                                                                                                                                 |
| <mark style="color:blue;">**sender**</mark> - text               | Chain address who sent and is signing the Aggregate Message.                                                                                                                                                                                                                                                   |
|                                                                  |                                                                                                                                                                                                                                                                                                                |
| <mark style="color:blue;">**hash\_type**</mark> - optional text  | Defaults to sha256. This is the only supported value for now.                                                                                                                                                                                                                                                  |
| <mark style="color:blue;">**item\_content**</mark> - JSON string | <p>JSON string representing the content of the message. </p><p>The structure of the item_content depends on the type of message created. See <a href="broken-reference"><code>POST</code></a>, <a href="broken-reference"><code>AGGREGATE</code></a> or <a href="broken-reference"><code>STORE</code></a>.</p> |
| <mark style="color:blue;">**item\_hash**</mark> - hash           | The hash of the item\_content encrypted with SHA256.                                                                                                                                                                                                                                                           |
| <mark style="color:blue;">**item\_type**</mark> - option         |                                                                                                                                                                                                                                                                                                                |

