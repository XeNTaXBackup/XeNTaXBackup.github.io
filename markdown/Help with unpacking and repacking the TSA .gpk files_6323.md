## Post #1
- Username: abcfate
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 29, 2011 10:22 pm
- Post datetime: 2011-03-29T16:09:44+00:00
- Post Title: Help with unpacking and repacking the TSA .gpk files

TSA(TOHO SKY ARENA) is a new TOHO game from Japan.
there is the file of TSA ,and it used .gpk .
Anyone can help me to unpaking and repaking the TSA .gpk files?
I tried this [viewtopic.php?f=10&t=4742&hilit=T](viewtopic.php?f=10&t=4742&hilit=T) and this [http://www.gildor.org/downloads](http://www.gildor.org/downloads)
but both Error.
may you help me, PLEASE     

A .gpk files can be download from the attachments~

I'm sorry my English is very poor
[.gpksample.rar](https://xentaxbackup.github.io/file/4136_.gpksample.rar)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-05-29T05:08:56+00:00
- Post Title: Help with unpacking and repacking the TSA .gpk files

Second this request.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-06-04T01:35:17+00:00
- Post Title: Help with unpacking and repacking the TSA .gpk files

The contents of this post was deleted because of possible forum rules violation.
[Resource.7z](https://xentaxbackup.github.io/file/4289_Resource.7z)
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-19T00:34:57+00:00
- Post Title: Help with unpacking and repacking the TSA .gpk files

Well, starting to figure out archives so I guess I'll start with the very simple files

There are two archives that are unencrypted/uncompressed (textures/mesh), which contain small things but I guess it gets you somewhere.

```
#for mesh.gpk and texture.gpk only

get files long
for i = 0 < files
	getdstring name 0x104
	get size long
	get offset long
	log name offset size
next i
```


The rest..lol I don't even know what it is.
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-19T00:54:48+00:00
- Post Title: Help with unpacking and repacking the TSA .gpk files

looks encrypted best bet is just use 3d ripper dx.
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-19T01:06:08+00:00
- Post Title: Help with unpacking and repacking the TSA .gpk files

lol that's no fun.
Well, some other people are interested in translating it to chinese so maybe they'll figure something out in the future.
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-10T18:39:42+00:00
- Post Title: Help with unpacking and repacking the TSA .gpk files

The contents of this post was deleted because of possible forum rules violation.
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-06T01:21:38+00:00
- Post Title: Help with unpacking and repacking the TSA .gpk files

Ok I'm going to try cracking this by brute force and guesswork after reading the DGTEFF again (cause there are 5 more models in the next patch)

Some things are done that make it a little more manageable:

-someone already unpacked it, so the contents are known
-the number of files in the archive is known
-the filenames and filesizes are known
-there are unencrypted archives, which may provide a hint

First I started by highlighting arbitrary bytes and noticed that the number of results matched the number of files.
So ok, that might actually be part of the filename. It is known that unencrypted gpk archives store strings in 260 bytes.
In fact, the BMS script I wrote for those is just

```
for i = 0 < FILES do
	getdstring NAME 260
	get SIZE long
	get OFFSET long
	log NAME OFFSET SIZE
next i

```


So now I just need to figure out how to decrypt it.
But...lol hmm I'm not sure how that would work.

The following archive contains 24 files, and it is known that strings are stored in 260 bytes.



Now I should probably get the patch files.
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-06T03:45:03+00:00
- Post Title: Help with unpacking and repacking the TSA .gpk files

Got a hold of the guy that wrote the unpacker and repacker.

[http://pastebin.com/ZRwgzhji](http://pastebin.com/ZRwgzhji)
[http://pastebin.com/bAiCy0yw](http://pastebin.com/bAiCy0yw)

Will require insani.py

[http://www.insani.org/tools/](http://www.insani.org/tools/)

Trying to write a quickBMS script but there's too much XOR'ing
## Post #10
- Username: rslifemanu
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 23, 2012 11:35 am
- Post datetime: 2012-02-23T09:12:52+00:00
- Post Title: Help with unpacking and repacking the TSA .gpk files

Second this request.
## Post #11
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2013-11-18T17:01:25+00:00
- Post Title: Help with unpacking and repacking the TSA .gpk files

> Reply from finale00
>
> Got a hold of the guy that wrote the unpacker and repacker.

http://pastebin.com/ZRwgzhji
http://pastebin.com/bAiCy0yw

Will require insani.py

http://www.insani.org/tools/

Trying to write a quickBMS script but there's too much XOR'ing
Can you send me the unpacker & repacker because the links are broken.
## Post #12
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2013-11-19T15:17:53+00:00
- Post Title: Help with unpacking and repacking the TSA .gpk files

> Reply from finale00
>
> Got a hold of the guy that wrote the unpacker and repacker.

http://pastebin.com/ZRwgzhji
http://pastebin.com/bAiCy0yw

Will require insani.py

http://www.insani.org/tools/

Trying to write a quickBMS script but there's too much XOR'ingWho is this guy who wrote the unpacker & repaker?
