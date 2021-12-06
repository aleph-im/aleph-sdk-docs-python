---
description: Amend an existing Aleph message
---

# 🗃 Update a message

### Usage

```
$ python3 -m aleph_client amend <Your Post Message Item_Hash>
```

The CLI opens a dialogue where the Message Content can be changed.

* Original message displayed:

```
{
    "type": "test",
    "address": <The address that was used to create the Message>,
    "content": this is the content I want to save to Aleph",
    "time": <timestamp>
}
```

* Let's change it to:

```
{
    "type": "test",
    "address": <The address that was used to create the Message>,
    "content": {"body": "This is my updated content", "tags": "NEW_TAG"},
    "time": <timestamp>
}
```

You have multiple prompts that are available to you.&#x20;

Use **Ctrl-X and Y** to confirm and save the content and then **enter** at the next prompt about the file name.



### Help

```
$ python3 -m aleph_client amend --help

Usage:
python3 -m aleph_client amend [OPTIONS] HASH

  Amend an existing Aleph message.

Arguments:
  HASH  [required]

Options:
  --private-key TEXT
  --private-key-file TEXT
  --help                   Show this message and exit.
```
