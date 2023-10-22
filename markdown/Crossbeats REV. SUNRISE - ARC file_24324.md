## Post #1
- Username: Wrland
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Nov 22, 2020 10:46 pm
- Post datetime: 2021-08-06T17:56:16+00:00
- Post Title: Crossbeats REV. SUNRISE - ARC file

its possible to extract .arc file from crossbeats REV. SUNRISE?? (with QuickBMS?)

link:[https://mega.nz/file/PNwmRD6K#HzFxR-m1o ... ghAjTC5P40](https://mega.nz/file/PNwmRD6K#HzFxR-m1oMCYUxEfJO1FSnbRf-blkAtoBghAjTC5P40)
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-08-06T21:34:27+00:00
- Post Title: Crossbeats REV. SUNRISE - ARC file

You can use offzip:

```
offzip.exe -a se_default.arc out1
```
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2021-08-07T16:54:03+00:00
- Post Title: Crossbeats REV. SUNRISE - ARC file

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "ARC\x00"
get VERSION short #7
get FILES short

for i = 0 < FILES
   getdstring PATH 64
   get EXT_HASH long
   get ZSIZE long
   math ZSIZE &= 0x3FFFFFFF
   get SIZE long
   get OFFSET long
   
   string NAME p= "%s.%08X" PATH EXT_HASH
   
   if ZSIZE == SIZE
       log NAME OFFSET SIZE
   else
       clog NAME OFFSET ZSIZE SIZE
   endif
next i
```


File extensions is hashed, so in this case here a desc for them

```
0x15D782FB - sbkr
0x1BCC4966 - stqr
0x064A3AD8 - xml
0x255D51CD - ogg
```
