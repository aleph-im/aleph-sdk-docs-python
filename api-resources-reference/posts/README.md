# 📑 Posts

`Posts` are unique documents, posted in a certain channel and for a certain type.&#x20;

Post objects allow you to store the content of a certain type associated with an address.

<mark style="background-color:yellow;">They can be searched through</mark> thanks to a reference parameter `ref`. This reference is useful for a few things:

* To reference another post (as a comment for example).
* To reference something else (an address, a transaction hash, a location ID, etc), and specify what the post is about.
* To reference another post to amend <mark style="background-color:yellow;">(edit) it</mark>. If you create a post with type `amend` and the `ref` of the original post: all new occurrences of the original post (granted you are authorized to do it) will be shown with new content, like an "amend and replace".

The API allows you to create, update (through create with set parameters), and retrieve a list of posts.

| [create](../../cli-reference/create-a-post.md), [update](update-a-post.md) | [.create\_post()](../../cli-reference/create-a-post.md) |
| -------------------------------------------------------------------------- | ------------------------------------------------------- |
| [list all posts](list-all.md)                                              | [.get\_posts()](list-all.md)                            |
