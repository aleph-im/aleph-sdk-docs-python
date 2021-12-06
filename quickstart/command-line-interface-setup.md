---
description: Build, test, and manage your Aleph integration from the terminal.
---

# Command-Line Interface Setup

The Aleph Command Line Interface makes it easy to create and manage resources as well as programs for aleph virtual machines directly from the terminal.&#x20;

### Download and install

{% hint style="info" %}
<mark style="color:blue;">**\[Requirements]**</mark>&#x20;

Some cryptographic functionalities use curve secp256k1 and require installing [libsecp256k1](https://github.com/bitcoin-core/secp256k1).

> $ apt-get install -y python3-pip libsecp256k1-dev
{% endhint %}

Install the aleph-client:

```
$ pip install aleph-client
```



### Installation for development

If you want NULS2 support you will need to install nuls2-python (currently only available on github):

> $ pip install git+[https://github.com/aleph-im/nuls2-python.git](https://github.com/aleph-im/nuls2-python.git)

To install from source and still be able to modify the source code:

> $ pip install -e . or $ python setup.py develop



### Getting started

After you install the CLI, run the `$ python3 -m aleph-client --help` command. You should be getting the help prompt for the client.

Now you're ready to use the CLI to manage resources:

```
$ python3 -m aleph_client watch --indent 4 "0x8d710289e2476fdf99fb69e42c7069866cc104e06986e1ac8aa272b5d8e7d81d"
```
