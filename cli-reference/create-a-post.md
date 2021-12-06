---
description: Create a Post Message on Aleph.im.
---

# 📑 Create a post

### Usage

```
$ python3 -m aleph_client post
```

The CLI is prompting you to enter the post\_content. This should be a valid JSON and can be obtained either from a file or from a user input.

```
$ {"body": "My custom content"}
```

Click Ctrl-D (or Ctrl-Z on Windows) to save the post.&#x20;

### Help

```
$ python3 -m aleph_client post --help

Usage: 
python3 -m aleph_client post [OPTIONS]
 
  Post a message on Aleph.im.

Options:
  --path TEXT
  --type TEXT              [default: test]
  --channel TEXT           [default: TEST]
  --private-key TEXT
  --private-key-file TEXT
  --help                   Show this message and exit.
```
