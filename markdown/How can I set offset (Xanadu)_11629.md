## Post #1
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-06-25T14:05:31+00:00
- Post Title: How can I set offset? (Xanadu)

Hi,   . Can someone help me..? 
Headersize is CA 44 00 00. And the first file(data/wave/xnse562.wav) starts at 44DAh(10h + 44CAh) and the file size is 8A B6 01 00.. and so on.



How can I set offset? I attached only header file. This is because original packed file is too big. So I can't attached it. Packed file also contains header file. 

<xanadu.lpack Information> - header + packed files
xanadu.lpack.header
44DAh - file start (44DAh = 10h + CA 44 00 00)
4BF167F9h - file end (4BF167F9h =  10h + CA 44 00 00 + 1F 23 F1 4B)

```

get files long
get Headersize long
get TotalPackSize long
get null long
for i = 0 < files
   get namesize long
   getdstring name namesize
   get size long
log name offset size
next i
```
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-06-25T19:29:03+00:00
- Post Title: How can I set offset? (Xanadu)

Well endian little and

```
get Headersize long
get TotalPackSize long
get null long

set offset long Headersize
math offset += 16

for i = 0 < files
   get namesize long
   getdstring name namesize
   get size long
   log name offset size
   math offset += size # add more if needed
next i
```


Anyway you need cut 1-3mb from front file.
## Post #3
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-06-26T02:56:19+00:00
- Post Title: How can I set offset? (Xanadu)

> Reply from Ekey
>
> Well endian little and
Code: Select allget files long
get Headersize long
get TotalPackSize long
get null long

set offset long Headersize
math offset += 16

for i = 0 < files
   get namesize long
   getdstring name namesize
   get size long
   log name offset size
   math offset += size # add more if needed
next i

Anyway you need cut 1-3mb from front file.

Thanks a lot!!
