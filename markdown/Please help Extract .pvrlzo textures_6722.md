## Post #1
- Username: warwar
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jun 04, 2011 3:36 pm
- Post datetime: 2011-06-04T07:45:10+00:00
- Post Title: Please help Extract .pvrlzo textures

Please help Extract .pvrlzo textures . It's textures file format from a little Game name  Snark Busters All Revved Up 2

i unapck game.pack but find most images  are encryption

there are some samples.

can someone here help me out?
[fragments.rar](https://xentaxbackup.github.io/file/4292_fragments.rar)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-06-11T11:02:09+00:00
- Post Title: Please help Extract .pvrlzo textures

script for quickbms:

```
get ZSIZE asize
#get SIZE long
savepos OFFSET
math ZSIZE -= OFFSET
math SIZE = ZSIZE
math SIZE *= 20 #enough?
get NAME basename
string NAME += ".pvr"
clog NAME OFFSET ZSIZE SIZE
```
## Post #3
- Username: warwar
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jun 04, 2011 3:36 pm
- Post datetime: 2011-06-12T10:13:15+00:00
- Post Title: Please help Extract .pvrlzo textures

> Reply from aluigi
>
> script for quickbms:
Code: Select allcomtype lzo1x
get ZSIZE asize
#get SIZE long
savepos OFFSET
math ZSIZE -= OFFSET
math SIZE = ZSIZE
math SIZE *= 20 #enough?
get NAME basename
string NAME += ".pvr"
clog NAME OFFSET ZSIZE SIZE

thank you very much!!!!
## Post #4
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-01-25T21:44:58+00:00
- Post Title: Please help Extract .pvrlzo textures

Sorry for the extreme dig, but the file's actually laid out like this (per the demo Stargaze Framework SDK I found):

```
char lzodata[];
uint signature = 0x7d620abd;
uint decompressed_length;
};
```


So the compressed data length is (length of file)-8, and the actual size is from the last 4 bytes. Signature in struct above should be reversed to little-endian when stored in file.
