## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-22T07:07:53+00:00
- Post Title: The Four Seasons Cake nds lz77 compression

UPDATE: Now it works

```

comtype LZ77WII
idstring "CMPR"
get SIZE asize
math SIZE -= 4
get NAME filename
clog NAME 4 SIZE SIZE
```


........................
OLD

[viewtopic.php?f=16&t=8369](http://forum.xentax.com/viewtopic.php?f=16&t=8369)

Can't seem to get this working.

```

comtype lz77wii_raw10
idstring "CMPR"
get TYPE byte
get SIZE long
get ZSIZE asize
math ZSIZE -= 9
get NAME filename
savepos OFFSET
clog NAME OFFSET ZSIZE SIZE
```


Am I just using the wrong compression type?

Compressed and decompressed attached.
[Four Seasons Cake.7z](https://xentaxbackup.github.io/file/5098_Four Seasons Cake.7z)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-22T15:00:06+00:00
- Post Title: The Four Seasons Cake nds lz77 compression

the error is in SIZE which is a threebyte number.

you can just use "comtype LZ77WII":

```
get SIZE asize
math SIZE -= 4
clog "name.dat" 4 SIZE SIZE
```

the reason of the -4 is that the original code checks for the LZ77 signature while this one has CMPR

or use just comtype lz77wii_raw10 specifiying get SIZE threebyte
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-22T17:53:36+00:00
- Post Title: The Four Seasons Cake nds lz77 compression

Alright, it works
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-22T23:57:47+00:00
- Post Title: The Four Seasons Cake nds lz77 compression

Here's another game FF4 DS which uses lz77 compression also (well, the ones with 0x10 tag anyways)

It starts with 0x10, followed by the uncompressed size, followed by data.

So I try the same thing:

```
get SIZE asize
get NAME filename
clog NAME 0 SIZE SIZE
```


But it doesn't decompress to the correct output size lol

This one works though:

```
get type byte
get SIZE threebyte
get ZSIZE asize
math ZSIZE -= 4
get NAME filename
clog NAME 4 ZSIZE SIZE
```


What's wrong with the first one I wrote?
[p00_01a.nmdp.7z](https://xentaxbackup.github.io/file/5100_p00_01a.nmdp.7z)
## Post #5
- Username: johnsonjeven
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 12, 2016 2:58 pm
- Post datetime: 2016-10-12T07:00:03+00:00
- Post Title: The Four Seasons Cake nds lz77 compression

LZF is conceptually very similar to LZ77. Generally speaking most modern compression algorithms give roughly the same compression, and with regard to the number of cores that you can use at once, it is up to you to decide how many you want to use. Generally speaking (unless you are creating large archives) there is no reason to need more than one though. In addition, with multiple cores doing the compression, the bottleneck may become the hard drive. Legacy zip compression is akin to the Deflate method in [7-zip](http://net-informations.com/q/mis/7zip.html), and will offer the most compatibility between different compression software.

John
