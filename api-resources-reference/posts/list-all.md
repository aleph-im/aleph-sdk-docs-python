---
description: >-
  Use the .get_posts() function to get the latest version of each post returned
  by the query.
---

# List all posts

### Returns

**An object** containing a **posts array** as well as **details on the number** of posts and pages returned:

{% code title="STRUCTURE OF THE RETURNED OBJECT" %}
```python
{   
    posts: [ { ... }, { ... }, { ... }],   
    pagination_page: 1,  
    pagination_total: 3,  
    pagination_per_page: 200,  
    pagination_item: 'posts' 
}
```
{% endcode %}

The "post objects" within the array returned are made of a combination of:

* the post message object
* additional details to help referencing the original post (original\_...)
* the `post.item_content` object attributes (`type, content, address, time`) are merged in at the top level of the post result

{% code title="STRUCTURE OF EACH OBJECT IN THE POSTS ARRAY" %}
```python
# Regular Post Message
channel:
time:
chain:
sender:
hash_type:
item_content:
  type:
  address:
  content:
  time:
  ref:
item_hash:
item_type:

# Details from original
original_item_hash
original_signature
original_tx_hash
original_type
original_ref
hash

# item_content object merged in
type:
content:
address:
time:
ref:

# Additional info from server
size:
confirmations:
confirmed:

```
{% endcode %}

### Usage

```python
def get_posts(
    pagination,
    page,
    types,
    refs,
    addresses,
    tags,
    hashes,
    channels,
    start_date,
    end_date,
    session,
    api_server,
)
```



### Required Arguments

All arguments are optional. If none are passed, all posts will be returned for the default argument values.

### Optional Arguments

* <mark style="color:green;">**pagination**</mark>** ** _- integer_\
  _`Default: 200`_\
  Number of messages returned per page\

* <mark style="color:green;">**page**</mark>** ** _- integer_\
  _`Default: 1`_\
  The number of pages returned\

*   <mark style="color:green;">**types**</mark>** ** _- Iterable of strings_\
    _`Default: None`_\
    Posts with the "post\_types" in the`item_content.type` as well as any last amended post where the original post type was "post\_types"

    \
    The value can be an **** array **of one type** or **multiple types**.&#x20;

    ex: `["blog", "comment"]`  \

* <mark style="color:green;">**refs**</mark> _- Iterable of strings_\
  _`Default: None`_\
  Array of Refs listed in content refs (`item_content.ref`)\

*   <mark style="color:green;">**addresses**</mark>** ** _- Iterable of strings_\
    _`Default: None`_\
    Array of addresses listed in the content address (`item_content.address`) **or** sender (`sender`) attribute of the Message.&#x20;

    If multiple addresses are passed, any post with one of the queried addresses in the content address or sender attribute will be returned.\

*   <mark style="color:green;">**tags**</mark>** ** _- Iterable of strings_\
    _`Default: None`_\
    Array of post content content tag. (`item_content.content.tags`).

    If multiple tags are passed, posts with at least one of the tags present in the content content tags will be returned.\

* <mark style="color:green;">**hashes**</mark> _- Iterable of strings_\
  _`Default: None`_\
  Array of hashes listed in the item hash (`item_hash`) or transaction hash (`tx_hash`)\

*   <mark style="color:green;">**channels**</mark> _- Iterable of strings_\
    _`Default: None`_

    Array of channels\

*   <mark style="color:green;">**start\_date**</mark>** ** _- datetime or float (timestamp)_\
    _`Default: None`_\
    Filtering posts on the time attribute (`time`).

    If only the start date is passed, posts with time greater than the start date will be returned.\
    If both start and end dates are passed, posts with time in between start date and end date will be returned.\

* <mark style="color:green;">**end\_date**</mark>** ** _- datetime or float (timestamp)_\
  _`Default: None`_\
  If only the end date is passed, posts with time less than the end date will be returned.\
  If both start and end dates are passed, posts with time in between start date and end date will be returned.\

* <mark style="color:green;">**session**</mark>\
  _`Default: None`_\
  \

* <mark style="color:green;">**api\_server**</mark>** ** _- string_\
  _`Default: "https://api2.aleph.im"`_\
  Target API server



### Example

```python
from aleph_client.asynchronous import get_posts

await get_posts(
    types=['chat'], 
    refs= ['hall'], 
    pagination=3)
```

{% hint style="info" %}
In the response, the `item_content` object attributes (`type, content, address, time`) are merged in the post message object to be easily reachable. `Item_content` is still available in the message object as well.
{% endhint %}

{% hint style="info" %}
The `original_` fields are here in case you amended the post.&#x20;
{% endhint %}

{% hint style="info" %}
This function retrieves the latest version of all posts. If a post was updated twice after the original version was created, only the last updated post will show.&#x20;

To see all the changes made to a post, check the [next header item](list-all.md#history-for-a-post) (To retrieve all changes made to a post)
{% endhint %}



### History for a post

{% hint style="danger" %}
**To retrieve all updates made to a specific post** and the original post, **use** [**list all messages**](../messages/list-all.md) **endpoint** rather than list all posts referencing the original item hash.\
\
When using list all posts with the item\_hash reference, any updated posts, including amends of amends will get displayed whether or not they were performed by the account address. \
**In addition, the original post cannot be retrieved by this endpoint.**&#x20;
{% endhint %}



