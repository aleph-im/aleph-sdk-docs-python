---
description: Update the code of an existing program.
---

# 💻 Update a program

{% hint style="warning" %}
<mark style="color:orange;">\[Issue Reported]</mark> [https://github.com/aleph-im/aleph-vm/issues/88#issuecomment-942367880](https://github.com/aleph-im/aleph-vm/issues/88#issuecomment-942367880)
{% endhint %}

### Usage

```
$ python3 -m aleph_client update <Hash Here> <Path Here>
```

### Help

```
$ python3 -m aleph_client update [OPTIONS] HASH PATH

  Update the code of an existing program.

Arguments:
  HASH  [required]
  PATH  [required]

Options:
  --private-key TEXT
  --private-key-file TEXT
  --print-message / --no-print-message [default: print-message]
  --help                   Show this message and exit.
```
