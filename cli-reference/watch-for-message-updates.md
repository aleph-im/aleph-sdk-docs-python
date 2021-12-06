---
description: Watch a hash for amends and print amend hashes
---

# 🗃 Watch for message updates

{% hint style="warning" %}
[\[Bug Fix in Progress\]](https://github.com/aleph-im/aleph-client/issues/32) The command is **not currently filtering** for the item hash passed in. All messages getting created are getting returned.&#x20;
{% endhint %}

### Usage

```
$ python3 -m aleph_client watch --indent 4 <Your Original Message Hash Here>
```

### Help

```
$ python3 -m aleph_client watch --help

Usage:
python3 -m aleph_client watch [OPTIONS] REF

  Watch a hash for amends and print amend hashes.

Arguments:
  REF  [required]

Options:
  --indent INTEGER        
  --help                   Show this message and exit.
```
