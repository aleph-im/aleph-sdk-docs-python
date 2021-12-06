---
description: Register a program to run on Aleph.im virtual machines from a zip archive.
---

# 💻 Create a Program

Programs are special entries that define code to run on Aleph.im virtual machines.

Aleph.im currently supports programs written in Python that follow the [ASGI interface](https://asgi.readthedocs.io/en/latest/introduction.html).&#x20;

In practice, the easiest approach is to use an [ASGI compatible web framework](https://asgi.readthedocs.io/en/latest/implementations.html), such as [FastAPI](https://fastapi.tiangolo.com) or [Django](https://www.djangoproject.com).

### Creating a program

Tutorial on creating a hosting a program on Aleph-VM[ here](https://github.com/aleph-im/aleph-vm/blob/main/tutorials/README.md).

Example on how to develop and run a small webapp based on FastAPI[ here](https://github.com/aleph-im/aleph-vm/tree/main/examples).

### Usage

```
$ python3 -m aleph_client program <PATH HERE> <ENTRYPOINT HERE>

#example: 
python3 -m aleph_client program ./my-program main:app
```

The command will output two URLs:&#x20;

* a URL link to see the message definition of your program
* a URL to run your program

### Help

```
$ python3 -m aleph_client program --help

Usage: python3 -m aleph_client program [OPTIONS] PATH ENTRYPOINT

  Register a program to run on Aleph.im virtual machines from a zip archive.

Arguments:
  PATH        [required]
  ENTRYPOINT  [required]

Options:
  --channel TEXT           [default: TEST]
  --private-key TEXT
  --private-key-file TEXT
  --help                   Show this message and exit.
```

