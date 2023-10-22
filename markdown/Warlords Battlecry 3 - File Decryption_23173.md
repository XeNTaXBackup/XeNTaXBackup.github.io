## Post #1
- Username: Krusty
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 15, 2020 6:53 am
- Post datetime: 2020-12-16T15:50:52+00:00
- Post Title: Warlords Battlecry 3 - File Decryption

Heyho, im new to reverse engineering.
My question: is it possible to decrypt this file without using a disassembler on the .exe file, in a reasonable time?
(The game is Warlords Battlecry 3, and its a file that contains Unit stats)

This is the Encrypted file:


heres a Decrypted version:



If its possible can someone tell me how you would approach it?
## Post #2
- Username: Krusty
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-12-16T23:36:03+00:00
- Post Title: Warlords Battlecry 3 - File Decryption

There is already a tool for decrypting and editing those ARM files.
It is Dal Gurak's Unit Editor which can be downloaded here [https://etheria.fandom.com/wiki/Tool_Downloads](https://etheria.fandom.com/wiki/Tool_Downloads)

[https://imgur.com/a/0UAm8oO](https://imgur.com/a/0UAm8oO)

In my opinion you shouldn't reverse engineer file format that was
already figured out by someone else and when some tools exist,
but if you really want to know how it was done, there is no easy way for that
if encryption algorithm is custom.

You can start with analyzing main archive format [http://wiki.xentax.com/index.php/Warlords_XCR](http://wiki.xentax.com/index.php/Warlords_XCR)
then try to figure out how game reads those ARM files inside archive and where is decryption function placed.

You can see some tutorials here [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)


Edit: There is also Advanced ARM Editor, but it does not support encrypted files
[http://www.mediafire.com/download.php?6b2n6n211h1ffok](http://www.mediafire.com/download.php?6b2n6n211h1ffok)

Edit2: Here is also mirror for Unit Editor (with working mss32.dll inside)
[http://www.mediafire.com/?ia8km28yinc1j1h](http://www.mediafire.com/?ia8km28yinc1j1h)
## Post #3
- Username: Krusty
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 15, 2020 6:53 am
- Post datetime: 2020-12-17T23:45:14+00:00
- Post Title: Warlords Battlecry 3 - File Decryption

Thanks for the reply.
Im aware that there is a tool for this kind of file already, i just wanted to to try it out for educational purpose, since i have never done anything like this before 

I will make sure to check out the tutorials and hopefully learn more about it.
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-12-18T14:42:34+00:00
- Post Title: Warlords Battlecry 3 - File Decryption

I have created documentation for this file format and also for decryption method which I was able to implement in Python
[http://wiki.xentax.com/index.php/Warlor ... tlecry_ARM](http://wiki.xentax.com/index.php/Warlords:_Battlecry_ARM)
You can check it if you are still interested in this.

You can also see my tool for decryption here
[https://github.com/bartlomiejduda/Tools ... _Battlecry](https://github.com/bartlomiejduda/Tools/tree/master/NEW%20Tools/Warlords_Battlecry)
## Post #5
- Username: Krusty
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 15, 2020 6:53 am
- Post datetime: 2020-12-19T21:27:20+00:00
- Post Title: Warlords Battlecry 3 - File Decryption

thats nice
how would you get the key?
did you inspect the .exe and searched for a function that generates it or is there a different method?
## Post #6
- Username: Krusty
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-12-20T20:09:52+00:00
- Post Title: Warlords Battlecry 3 - File Decryption

The easiest way in this case is probably load some ARM editor in IDA or in debugger like x64dbg and try to find the function for decryption.   

But other method would be analyzing game functions and trying to hook them.
This is the standard aproach when there are no editors for file format you are analyzing.
## Post #7
- Username: Krusty
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-02T17:08:00+00:00
- Post Title: Warlords Battlecry 3 - File Decryption

Btw, source code for this game is available:

> Since its release, the game's source code has become available to the public. Certain members of the community have been entitled distributors, which have special legal permissions to allocate copies of the Warlords Battlecry III source code. The interested member must agree to an NDA license in order to receive the source code. The main basis of the distribution and the head of the operation was located on The Battlefield Forums
