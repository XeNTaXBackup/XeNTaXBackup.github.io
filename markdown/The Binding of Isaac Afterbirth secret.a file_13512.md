## Post #1
- Username: traderain
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Aug 29, 2014 1:48 am
- Post datetime: 2015-11-08T13:05:29+00:00
- Post Title: The Binding of Isaac: Afterbirth secret.a file

The game's developers have locked that file down pretty hard but let's see if we can break it apart.
Its located inside the afterbirth.a file as secret.a.
There is an unpacler already for afterbirth.a [https://www.reddit.com/r/themoddingofis ... ompatible/](https://www.reddit.com/r/themoddingofisaac/comments/3rcosz/my_tools_are_now_afterbirth_compatible/)
Afterbirth.a uses a variant of MiniZ for compression: [http://code.google.com/p/miniz/](http://code.google.com/p/miniz/)
I edited game code while the game was running to perform a complete dump of every file in the archive last night, and figured out the encryption algorithm today.
It'll need to be implemented into the unpacker to make files extractable by the public, but excellent progress is being made!
Secret.a is an arch000 stored inside of afterbirth.a that uses a custom xortable for decryption. The extracted files are doubly encrypted, with what I don't know, and have plaintext text snippets at the end of them.
I suspect secret.a is just a red herring to mess with data miners.
Any help would be apriciated.
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-08T13:22:12+00:00
- Post Title: The Binding of Isaac: Afterbirth secret.a file

[http://svn.gib.me/builds/rebirth/rebirth-r47_b43.zip](http://svn.gib.me/builds/rebirth/rebirth-r47_b43.zip)
## Post #3
- Username: traderain
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Aug 29, 2014 1:48 am
- Post datetime: 2015-11-08T18:20:59+00:00
- Post Title: The Binding of Isaac: Afterbirth secret.a file

Thank you for the reply but that simply produces the .unknown files. Does the same which I linked.
