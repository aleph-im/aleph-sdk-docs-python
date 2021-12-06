# The post object

The post object inherits from the `Message` object's structure as follows:

```javascript
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
  type:
  address:
  content:
  time:
  ref:
item_hash:
item_type:
forgotten_by:
```



| Attributes                                                                                                           | Description                                                                                                                                                                     |
| -------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <mark style="color:blue;">**channel**</mark> - text                                                                  | Channel of the message. Ideally, an application would decide and use one channel.                                                                                               |
| <mark style="color:blue;">**time**</mark> - float                                                                    | Time the post was created in seconds.                                                                                                                                           |
| <mark style="color:blue;">**type**</mark> - text                                                                     | <p>Text representing the message object type.</p><p>Value is<code>POST</code></p>                                                                                               |
|                                                                                                                      |                                                                                                                                                                                 |
| <mark style="color:blue;">**chain**</mark> <mark style="color:blue;"></mark><mark style="color:blue;"></mark> - text | <p>The chain used by the sender's account. <br>Value can be <code>NULS2</code>, <code>ETH</code>, <code>DOT</code>, <code>CSDK</code>, <code>SOL</code>, <code>AVAX</code></p>  |
| <mark style="color:blue;">**sender**</mark>** ** - <mark style="color:blue;"></mark> text                            | Chain address who sent and is signing the Post Message.                                                                                                                         |
|                                                                                                                      | -                                                                                                                                                                               |
| <mark style="color:blue;">**hash\_type**</mark> - optional text                                                      | Defaults to sha256. This is the only supported value for now.                                                                                                                   |
| <mark style="color:blue;">**item\_content**</mark> - JSON text                                                       | <p>JSON string representing the content of the aggregate. </p><p>See below for the content of the string.</p>                                                                   |
|                                                                                                                      |                                                                                                                                                                                 |
| item\_content.<mark style="color:blue;">**type**</mark>** ** - text                                                  | <p>A string of your choice representing what the post is. Should be simple and lowercase.</p><p>For instance, for a blog post you could have:</p><p>a "blog" or a "comment"</p> |
| item\_content.<mark style="color:blue;">**address**</mark> - text                                                    | Chain address to associate the `Post` with.                                                                                                                                     |
| item\_content.<mark style="color:blue;">**content**</mark>** ** - object                                             | <p>An object containing the content you want to save. <br>For instance, for a blog post you could have:<br>{ body: "This is my content" }</p>                                   |
| item\_content.<mark style="color:blue;">**content.tags**</mark>** ** - obje                                          |                                                                                                                                                                                 |
| item\_content.<mark style="color:blue;">**time**</mark>** -** timestamp                                              | Time the object was created.                                                                                                                                                    |
| item\_content.<mark style="color:blue;">**ref**</mark> - text                                                        | <p>A text representing a reference.</p><p>Present if a ref was passed during creation.</p>                                                                                      |
|                                                                                                                      |                                                                                                                                                                                 |
| <mark style="color:blue;">**item\_hash**</mark>** ** - hash                                                          | The hash of the item\_content encrypted with SHA256.                                                                                                                            |
| <mark style="color:blue;">**item\_type**</mark> - optional text                                                      | `ipfs`, `inline` or `storage`                                                                                                                                                   |
| <mark style="color:blue;">**forgotten\_by**</mark> - hash                                                            | Item hash from the forget message that triggered the removal of this post content.                                                                                              |

