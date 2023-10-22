## Post #1
- Username: gerardoosanchezz
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Sep 11, 2015 9:11 am
- Post datetime: 2016-01-20T02:01:23+00:00
- Post Title: help in endianess

Hey happy new year for everyone!!
Well im traying to convert this [http://www.mediafire.com/download/y326o ... npacked.db](http://www.mediafire.com/download/y326onmk20oa0d2/fifa_ng_db_unpacked.db)
in this [http://www.mediafire.com/download/g0qw3 ... a_ng_db.db](http://www.mediafire.com/download/g0qw3mvtuwr4vbp/fifa_ng_db.db) and vice versa
Its from xbox to pc.
I tried with Quickbms with -E funtion but just some bits are in inverse and others not, (one guy convert it but he doesnt want to share his code). 
With funtion -E


Converted


So i hope you can helpme it be usefull for many people
Well thanks in advance!
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-01-21T00:09:38+00:00
- Post Title: help in endianess

are you using quickbms? post the script to unpack it
## Post #3
- Username: gerardoosanchezz
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Sep 11, 2015 9:11 am
- Post datetime: 2016-01-21T01:56:54+00:00
- Post Title: help in endianess

> Reply from WRS
>
> are you using quickbms? post the script to unpack it

How?
The second one is converted yet.

For converter to pc i use Chunkzlx script.

[http://aluigi.altervista.org/bms/chunklzx.bms](http://aluigi.altervista.org/bms/chunklzx.bms)

For funtion -E i use this script

```
math OFFSET = 4
math SIZE -= OFFSET
goto OFFSET
math SIZE /= 4
for i = 0 < SIZE
    get TMP long
next i
```


Can you help me? please
