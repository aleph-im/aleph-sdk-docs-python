# List all

### Returns

A list of Messages of one msgType that have previously been created for the queried parameters.



### Usage

```python
def get_messages(
    pagination:,
    page,
    message_type,
    content_types,
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

All arguments are optional. If none are passed, all messages will be returned for the default argument values.

### Optional Arguments

* <mark style="color:green;">**pagination**</mark> _- integer_\
  _`Default: 200`_\
  Number of messages returned per page\

* <mark style="color:green;">**page**</mark> _- integer_\
  _`Default: 1`_\
  The number of pages returned\

* <mark style="color:green;">**message\_type**</mark> _- string_\
  _`Default: None`_\
  A string representing the Message type. Only one type can be queried at a time.\
  Value can be: `POST`, `AGGREGATE`, or `STORE`  \

* <mark style="color:green;">**content\_types**</mark> _- iterable of strings_\
  _`Default: None`_\
  Array of Message content types (`item_content.type`)\

* <mark style="color:green;">**refs**</mark>** ** _- iterable of strings_\
  _`Default: None`_\
  Array of Refs listed in content refs (`item_content.ref`)\

*   <mark style="color:green;">**addresses**</mark> _- iterable of strings_\
    _`Default: None`_\
    Array of addresses listed in the content address (`item_content.address`) **or** sender (`sender`) attribute of the Message.&#x20;

    If multiple addresses are passed, any message with one of the queried addresses in the content address or sender attribute will be returned.\

*   <mark style="color:green;">**tags**</mark> _- iterable of strings_\
    _`Default: None`_\
    Array of Message content content tag. (`item_content.content.tags`).

    If multiple tags are passed, messages with at least one of the tags present in the content content tags will be returned.\

* <mark style="color:green;">**hashes**</mark>** ** _- iterable of strings_\
  _`Default: None`_\
  Array of hashes listed in the item hash (`item_hash`) or transaction hash (`tx_hash`)\

*   <mark style="color:green;">**channels**</mark> _- iterable of strings_\
    _`Default: None`_

    Array of channels\

*   <mark style="color:green;">**start\_date**</mark> _- datetime or float (timestamp)_\
    _`Default: None`_\
    Filtering messages on the time attribute (`time`).

    If only the start date is passed, messages with time greater than the start date will be returned.\
    If both start and end dates are passed, messages with time in between start date and end date will be returned.\

* <mark style="color:green;">**end\_date**</mark> _- datetime or float (timestamp)_\
  _`Default: None`_\
  If only the end date is passed, messages with time less than the end date will be returned.\
  If both start and end dates are passed, messages with time in between start date and end date will be returned.\

* <mark style="color:green;">**session**</mark>\
  _`Default: None`_\
  \

* <mark style="color:green;">**api\_server**</mark> _- string_\
  _`Default: https://api2.aleph.im`_\
  Target API server



