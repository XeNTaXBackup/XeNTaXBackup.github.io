## Post #1
- Username: hyndai
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Jun 04, 2008 4:55 am
- Post datetime: 2012-07-08T17:30:27+00:00
- Post Title: 1953 KGB Unleashed

How extract *.dat files, all the header is RCFS looks sample files

Common.dat ( 440 Ko ) 

```
http://dl.free.fr/eb0MtbjyG
```


Music.dat ( 44Mo )

```
http://dl.free.fr/iqwsfwKyu
```
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-08T21:00:11+00:00
- Post Title: 1953 KGB Unleashed

AES
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-07-09T15:32:32+00:00
- Post Title: 1953 KGB Unleashed

md5 is an hashing algorithm, not an encryption one.

I have noticed the 8bytes alignment so I think to blowfish
## Post #4
- Username: Moo
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Jul 25, 2012 7:04 am
- Post datetime: 2012-07-25T12:29:00+00:00
- Post Title: 1953 KGB Unleashed

It seems to use MD4/MD5/SHA-1 and SHA-256. This is based on the magic numbers used - other things may use the same numbers... Too complex for me 
Maybe something like [http://en.wikipedia.org/wiki/SHACAL](http://en.wikipedia.org/wiki/SHACAL).
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-07T08:36:39+00:00
- Post Title: 1953 KGB Unleashed

Looked this game again. Full cycle: SHA-2 (SHA-256) -> MD5 -> AES -> XOR

btw: RCFS Engine - Copyright (C) 2o12, Rafal Cyran [ajron@vtools.pl]
