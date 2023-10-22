## Post #1
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-05-16T18:14:14+00:00
- Post Title: SW Rogue Squadron 3 - GameCube - .pool & .cdata

hello

after unpack archives , i find some  unknow files
 someone can take a look on them, to unpack them ?

extension .pool and .cData

[http://www.filedropper.com/pool](http://www.filedropper.com/pool)
## Post #2
- Username: Acewell
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-05-18T17:42:07+00:00
- Post Title: SW Rogue Squadron 3 - GameCube - .pool & .cdata

This should work for the cData files (quickbms script).

```
# By Gh0stBlade
ENDIAN BIG

get MAGIC long
get FILES long

for i = 0 < FILES
    get UNK00 long
    get OFFSET long
    get UNK01 long
    get SIZE long
    log i OFFSET SIZE
next i

```
## Post #3
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-05-19T16:18:34+00:00
- Post Title: SW Rogue Squadron 3 - GameCube - .pool & .cdata

hello, and thks

it seems to work ... but it overpass some files ...

archive .cData is 300 Mo, and the unpack folder is 100 Mo
by the way, this is a very good start
