## Post #1
- Username: Pointman
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Mar 18, 2012 3:42 pm
- Post datetime: 2012-03-18T07:50:04+00:00
- Post Title: Madoka Magica Portable .pac file

i'm need to get the .gim sprite file inside it. please help me
[talkchara00_0b.zip](https://xentaxbackup.github.io/file/5204_talkchara00_0b.zip)
## Post #2
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2012-03-18T14:37:36+00:00
- Post Title: Madoka Magica Portable .pac file

Quickbms script for unpack

```
get UNK short
get ASIZE long
for i = 0 < FILES
getdstring NAME 0x20
get OFFSET long
get SIZE long
log NAME OFFSET SIZE
next i
```
## Post #3
- Username: Pointman
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Mar 18, 2012 3:42 pm
- Post datetime: 2012-03-18T15:15:45+00:00
- Post Title: Madoka Magica Portable .pac file

> Reply from swuforce
>
> Quickbms script for unpack
Code: Select allget FILES short
get UNK short
get ASIZE long
for i = 0 < FILES
getdstring NAME 0x20
get OFFSET long
get SIZE long
log NAME OFFSET SIZE
next i
It worked! Thank you so much!!
