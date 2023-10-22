## Post #1
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2012-04-23T07:33:29+00:00
- Post Title: MG2, MGR for Virtual On DC

I have some MG2 & MGR file with 78 9C header, how to decompress it. 
If someone can decompress this it would be awesome.
## Post #2
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-04-23T08:56:46+00:00
- Post Title: MG2, MGR for Virtual On DC

The file starts with xœ (78 9C) and can be decoded with zlib.

```
C:\offzip.exe -a C:\*.MG2  C:\ 0x0
```

MG2 is pvr texture, MGR is unknown model.
Looks similar to xbox360's Virtual On
[viewtopic.php?f=16&t=8020&hilit=Virtual+On](http://forum.xentax.com/viewtopic.php?f=16&t=8020&hilit=Virtual+On)
## Post #3
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2012-04-25T14:01:46+00:00
- Post Title: MG2, MGR for Virtual On DC

Is it possible to make the BMS script?

```
get NAME FILENAME
if FLAG = 0x9C78
????????? 
I don't know any more, need help.

```
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-04-25T17:35:29+00:00
- Post Title: MG2, MGR for Virtual On DC

it's just a compressed zlib file:

```
get EXT extension
string NAME += "_unpacked."
string NAME += EXT
comtype unzip_dynamic
get SIZE asize
clog NAME 0 SIZE SIZE
```
## Post #5
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2012-04-25T18:09:47+00:00
- Post Title: MG2, MGR for Virtual On DC

Thanks aluigi
