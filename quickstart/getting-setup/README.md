---
description: >-
  Get up and running with the Aleph-Client python client library and start
  developing your Aleph integration.
---

# API Setup

{% hint style="success" %}
Integrating with Aleph requires two steps:

1. Install the client library in your application so that you can interact with the Aleph API
2. Make an API request
{% endhint %}

### 1. Import the Aleph-Client in your dApp

> **Requirements**
>
> Some cryptographic functionalities use curve secp256k1 and require installing [libsecp256k1](https://github.com/bitcoin-core/secp256k1).
>
> `$ apt-get install -y python3-pip libsecp256k1-dev`

```
$ pip install aleph-client
```

### 2. Make an API call

To check the integration is working, make a basic API request within your project.&#x20;

Here we are retrieving the 3 last Posts that were made with a post type of "chat" and with a reference of "hall". We'll go into more details about post types and references in the [Post Resource Reference](../../api-resources-reference/posts/list-all.md).

```python
from aleph_client.synchronous import get_posts

get_posts(types=['chat'], refs= ['hall'], pagination=3)
```

Aleph returns an object with a `posts` key containing an array of all the posts that were made with the query params we requested.

The response should look like this:&#x20;

```python
{
  'posts': [
    {'_id': {'$oid': '616515877eb99b436b86c06c'}, 'chain': 'ETH', 'item_hash': 'da0e0539b68b3e60e98add4720f2db0a663cf4bda9e519dd21a494b608b6cbfc', 'sender': '0xd529b1894491a0a26B18939274ae8ede93E81dbA', 'type': 'chat', 'channel': 'TEST', 'confirmed': True, 'content': {'body': 'bifi'}, 'item_content': '{"type":"chat","address":"0xd529b1894491a0a26B18939274ae8ede93E81dbA","content":{"body":"bifi"},"time":1634014592.392,"ref":"hall"}', 'item_type': 'inline', 'signature': '0x1485ecb8a35ff78f3ac6b4e2eb48ffb115871b052495c38fbf6e2e2eb8a9cf992f23d0725d99fe52cf8b9dee11c1b29b52bef88d633fad809123b7ed5e494e0f1c', 'size': 131, 'time': 1634014592.392, 'confirmations': [{'chain': 'ETH', 'height': 13401891, 'hash': '0x592d4aa9c087103733073700aa502441a334b28e0f02a689e364a5e948002449'}], 'original_item_hash': 'da0e0539b68b3e60e98add4720f2db0a663cf4bda9e519dd21a494b608b6cbfc', 'original_signature': '0x1485ecb8a35ff78f3ac6b4e2eb48ffb115871b052495c38fbf6e2e2eb8a9cf992f23d0725d99fe52cf8b9dee11c1b29b52bef88d633fad809123b7ed5e494e0f1c', 'original_type': 'chat', 'hash': 'da0e0539b68b3e60e98add4720f2db0a663cf4bda9e519dd21a494b608b6cbfc', 'original_ref': 'hall', 'address': '0xd529b1894491a0a26B18939274ae8ede93E81dbA', 'ref': 'hall'}, 
    {'_id': {'$oid': '615cfa717eb99b436b2fd32f'}, 'chain': 'ETH', 'item_hash': '67243b6b2cd85d6f5b4659dfd9254ab962895cb8f4501cf3b88eb347b2c0dfb6', 'sender': '0x7C7743637c451B17c3289ad178E373B2Cac617B5', 'type': 'chat', 'channel': 'TEST', 'confirmed': True, 'content': {'body': 'test message'}, 'item_content': '{"type":"chat","address":"0x7C7743637c451B17c3289ad178E373B2Cac617B5","content":{"body":"test message"},"time":1633483308.211,"ref":"hall"}', 'item_type': 'inline', 'signature': '0xd74dacc75ed4b50a7c5a425128795e72c7ceedc540b7c9fabc6fce16ad5bafba470f714a62a4915180c074bf1d0d4e3e5e108f1b354685de93632d9022d6984f1c', 'size': 139, 'time': 1633483308.211, 'confirmations': [{'chain': 'ETH', 'height': 13362643, 'hash': '0x2d08c7ca8afb5cc8c232b7fb3b46b906b6ee38badf0e8de2afc2cb35c87081da'}], 'original_item_hash': '67243b6b2cd85d6f5b4659dfd9254ab962895cb8f4501cf3b88eb347b2c0dfb6', 'original_signature': '0xd74dacc75ed4b50a7c5a425128795e72c7ceedc540b7c9fabc6fce16ad5bafba470f714a62a4915180c074bf1d0d4e3e5e108f1b354685de93632d9022d6984f1c', 'original_type': 'chat', 'hash': '67243b6b2cd85d6f5b4659dfd9254ab962895cb8f4501cf3b88eb347b2c0dfb6', 'original_ref': 'hall', 'address': '0x7C7743637c451B17c3289ad178E373B2Cac617B5', 'ref': 'hall'}, 
    {'_id': {'$oid': '61584004233a497a714d1b92'}, 'chain': 'ETH', 'item_hash': '59b2353ed904f95ae11e3c78a5813631040d1e13b0a6505e6d44006099ef072c', 'sender': '0x63c9e115f8b3b5C889d11dC88b0F6bc2ACe1fcA8', 'type': 'chat', 'channel': 'TEST', 'confirmed': True, 'content': {'body': 'a little slow ngl'}, 'item_content': '{"type":"chat","address":"0x63c9e115f8b3b5C889d11dC88b0F6bc2ACe1fcA8","content":{"body":"a little slow ngl"},"time":1633173507.785,"ref":"hall"}', 'item_type': 'inline', 'signature': '0xea0437f0591b6293036b200a90c0c56d664010a96272797e273308fe8d001c6c546caf5d878fa4406fe8458b5117f0c12da14b469ece1ee799de5b208a5325121c', 'size': 144, 'time': 1633173507.785, 'confirmations': [{'chain': 'ETH', 'height': 13339562, 'hash': '0x16dd4a0726f976addc094f29676ffdfaec29a05479d23a2c7da7310d0acf0f86'}], 'original_item_hash': '59b2353ed904f95ae11e3c78a5813631040d1e13b0a6505e6d44006099ef072c', 'original_signature': '0xea0437f0591b6293036b200a90c0c56d664010a96272797e273308fe8d001c6c546caf5d878fa4406fe8458b5117f0c12da14b469ece1ee799de5b208a5325121c', 'original_type': 'chat', 'hash': '59b2353ed904f95ae11e3c78a5813631040d1e13b0a6505e6d44006099ef072c', 'original_ref': 'hall', 'address': '0x63c9e115f8b3b5C889d11dC88b0F6bc2ACe1fcA8', 'ref': 'hall'}
  ], 
  'pagination_page': 1, 
  'pagination_total': 449, 
  'pagination_per_page': 3, 
  'pagination_item': 'posts'
}
```

### 3. Next Steps - Writing to the Network

Once you have successfully made an API _GET_ request, **connect a blockchain account and write to the aleph.im network**&#x20;
