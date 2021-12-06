---
description: Uses the create post endpoint to update the original post.
---

# Update a post

Update the specific post by [creating a new post](create-a-post.md) with the <mark style="color:green;">**`post_type`**</mark> `amend` and the original post __ `item_hash` as the <mark style="color:green;">**`ref`**</mark> along with the new <mark style="color:green;">**`content`**</mark>.

### Example

```python
>>> from aleph_client.synchronous import create_post

>>> create_post(
      account, 
      {'content': 'test'}, 
      post_type='amend', 
      ref="<ITEM HASH HERE>",
      channel='MY_CHANNEL')

```
