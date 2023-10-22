## Post #1
- Username: Idioteche
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 17, 2013 3:50 am
- Post datetime: 2013-04-16T20:43:29+00:00
- Post Title: Saints of Virtue - PC (.WRS, ACKNEX)

Hey guys, I recently started playing this creepy religious game called Saints of Virtue. I was interested in unpacking the levels, but I'm not sure how to go about doing so. I tried gobread, since it is listed as having support for .WRS files. However, gobread fails to recognize the file type, even when I set it manually with the proper command. I assume this is because the .WRS support was written for more modern games (Bagger Simulator), and the game I'm trying to unpack is from 1999. I looked into the version numbers of ACKNEX, and going by the release date of the game is was probably developed using version 3 from 1997, although I could be wrong. I tried to find a distribution of ACKNEX-3, but the website hosting the file no longer allows it to be downloaded. (Throws a 404, here's the link - [http://server.conitec.net/down/a3.zip](http://server.conitec.net/down/a3.zip))

Here are the files I'm trying to unpack:
[https://www.dropbox.com/s/5uw70as2hezek ... Virtue.zip](https://www.dropbox.com/s/5uw70as2hezektw/Saints%20of%20Virtue.zip)

If anyone could help me out, I'd really appreciate it.
## Post #2
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2013-04-17T13:21:21+00:00
- Post Title: Saints of Virtue - PC (.WRS, ACKNEX)

This Quickbms script can unpack

```
endian big
get asize asize
do
getdstring name 13
get zsize long
get size long
savepos offset
clog name offset zsize size
math offset += zsize
goto offset
while offset < asize
```
## Post #3
- Username: Idioteche
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 17, 2013 3:50 am
- Post datetime: 2013-04-18T02:54:12+00:00
- Post Title: Saints of Virtue - PC (.WRS, ACKNEX)

Awesome dude, it works! Lots of thanks!

I also have another question; how would I go about recreating a .wrs file with newly modified files? I tried repacking it with the new ones as a smaller size, but the game just crashes.
