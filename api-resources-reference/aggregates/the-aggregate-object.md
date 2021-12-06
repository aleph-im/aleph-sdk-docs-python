# The aggregate object

The aggregate object inherits from the [`Message`](broken-reference) object structure as follows:

```
{
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
    key:
    address:
    content:
    time:
  item_hash:
  item_type:
}
```

| <mark style="color:blue;">**channel**</mark> - text                 | Channel of the message. Ideally, an application would decide and use one channel.                                                                                              |
| ------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <mark style="color:blue;">**time**</mark> - float                   | Time the aggregate was created in seconds.                                                                                                                                     |
| <mark style="color:blue;">**type**</mark> - text                    | <p>Text representing the message object type.</p><p>Value is <code>AGGREGATE</code>.</p>                                                                                       |
|                                                                     |                                                                                                                                                                                |
| <mark style="color:blue;">**chain**</mark> - text                   | <p>The chain used by the sender's account. <br>Value can be <code>NULS2</code>, <code>ETH</code>, <code>DOT</code>, <code>CSDK</code>, <code>SOL</code>, <code>AVAX</code></p> |
| <mark style="color:blue;">**sender**</mark> -text                   | Chain address who sent and is signing the Aggregate Message.                                                                                                                   |
|                                                                     | -                                                                                                                                                                              |
| <mark style="color:blue;">**hash\_type**</mark> - optional text     | Defaults to sha256. This is the only supported value for now.                                                                                                                  |
| <mark style="color:blue;">**item\_content**</mark> - JSON string    | <p>JSON string representing the content of the aggregate. </p><p>See below for the content of the string.</p>                                                                  |
|                                                                     |                                                                                                                                                                                |
| items\_content.<mark style="color:blue;">**key**</mark> - text      | The indexed key to reference the value (`item_content.content`) is stored under.                                                                                               |
| item\_content.<mark style="color:blue;">**address**</mark> - text   | Chain address to associate the `Aggregate` with.                                                                                                                               |
| item\_content.<mark style="color:blue;">**content**</mark> - object | Value object stored for the key.                                                                                                                                               |
| item\_content.<mark style="color:blue;">**time**</mark> - timestamp | Time the object was created.                                                                                                                                                   |
|                                                                     |                                                                                                                                                                                |
| <mark style="color:blue;">**item\_hash**</mark> - hash              | The hash of the item\_content encrypted with SHA256.                                                                                                                           |
| <mark style="color:blue;">**item\_type**</mark> - optional text     | `ipfs`, `inline` or `storage`                                                                                                                                                  |
