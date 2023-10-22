## Post #1
- Username: Gruselgurke
- Rank: advanced
- Number of posts: 72
- Joined date: Sat Mar 31, 2012 1:15 am
- Post datetime: 2012-04-29T20:42:53+00:00
- Post Title: Toy Soldiers .sacb

Toy Soldiers for PC got released today. Nearly all content of the game except for audio and locales is in the "pack.sacb" file.
Doesn't seem like this format was used before.
## Post #2
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2012-05-01T15:36:13+00:00
- Post Title: Toy Soldiers .sacb

This quickbms script can unpack

```
get FILES long
math OFF = 0x60
for i = 0 < FILES
goto OFF
get NAMEOFF THREEBYTE
math NAMEOFF -= 4
get DUMMY byte
get NAMESIZE long
get UNK1 long
get UNK2 long
get OFFSET long
get ZSIZE long
get SIZE long
getdstring DUMMY 0x1c
savepos OFF
goto NAMEOFF
getdstring NAME NAMESIZE
if SIZE == ZSIZE
log NAME OFFSET SIZE
else
clog NAME OFFSET ZSIZE SIZE
endif
next i
```
## Post #3
- Username: Gruselgurke
- Rank: advanced
- Number of posts: 72
- Joined date: Sat Mar 31, 2012 1:15 am
- Post datetime: 2012-05-01T17:43:29+00:00
- Post Title: Toy Soldiers .sacb

thanks!
## Post #4
- Username: Northstar2
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 14, 2016 6:42 pm
- Post datetime: 2016-04-24T14:57:46+00:00
- Post Title: Toy Soldiers .sacb

Sorry for necroposting, but the code doesn't work on my case. It simply refuses to unpack anything and spits "0 files found in 0 seconds" error on my face.
I am confused, what am I doing wrong here?
