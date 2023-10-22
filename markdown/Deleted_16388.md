## Post #1
- Username: diimashups
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jun 17, 2016 5:00 am
- Post datetime: 2017-06-10T19:20:06+00:00
- Post Title: Deleted

deleted
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-06-11T06:18:38+00:00
- Post Title: Deleted

.ipk sample required
## Post #3
- Username: diimashups
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jun 17, 2016 5:00 am
- Post datetime: 2017-06-11T10:41:13+00:00
- Post Title: Deleted

deleted
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-06-11T11:07:58+00:00
- Post Title: Deleted

comment out line 30 of the bms script like this 

```
    //string FNAME += NAME
```
## Post #5
- Username: diimashups
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jun 17, 2016 5:00 am
- Post datetime: 2017-06-11T11:18:26+00:00
- Post Title: Deleted

deleted
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-06-11T11:29:56+00:00
- Post Title: Deleted

ah so you want the folder structure too? here  


 Just_Dance_ipk.zip
(528 Bytes) Downloaded 24 times
## Post #7
- Username: diimashups
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jun 17, 2016 5:00 am
- Post datetime: 2017-06-11T11:31:29+00:00
- Post Title: Deleted

deleted
## Post #8
- Username: diimashups
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jun 17, 2016 5:00 am
- Post datetime: 2017-06-11T11:38:55+00:00
- Post Title: Deleted

deleted
## Post #9
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-06-11T11:44:13+00:00
- Post Title: Deleted

i couldn't tell ya, game modding is not my area
## Post #10
- Username: diimashups
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jun 17, 2016 5:00 am
- Post datetime: 2017-06-11T12:00:33+00:00
- Post Title: Deleted

deleted
## Post #11
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-06-11T12:27:27+00:00
- Post Title: Deleted

heres a bms script to clean up the *.png.ckd image headers for viewing as dds  

```

idstring "\x00\x00\x00\x09\x54\x45\x58\x00"
get NAME basename
get SIZE asize
math SIZE - 0x2c
string NAME - ".png"
string NAME1 = NAME
string NAME1 + ".png.ckd.header" 
log NAME1 0x0 0x2c
string NAME + ".dds"
log NAME 0x2c SIZE

```
## Post #12
- Username: diimashups
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jun 17, 2016 5:00 am
- Post datetime: 2017-06-11T12:46:53+00:00
- Post Title: Deleted

deleted
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-06-11T13:10:37+00:00
- Post Title: Deleted

not to sound sophisticated but for me it looks as if the script in the opening post only needed some swapping such like this:

```
        get DUMMY long
        get DUMMY long
    endif
    get NAMESZ long
    getdstring NAME NAMESZ
    get PATHSZ long
    getdstring PATH PATHSZ
```
because the filename ("NAME") appears first in the (Just Dance 2017) .ipk then the path to follow.

(where FNAME= PATH + NAME)

just my two cents
## Post #14
- Username: justdancemaster2004
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 04, 2017 3:24 am
- Post datetime: 2018-10-05T15:36:17+00:00
- Post Title: Deleted

Um....

Do you know which songs are in each bundle

like Bundle_0
Bundle_1

I really need it for mods
