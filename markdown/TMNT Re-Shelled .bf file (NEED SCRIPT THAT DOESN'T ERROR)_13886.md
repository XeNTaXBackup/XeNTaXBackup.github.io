## Post #1
- Username: jackskellinghog
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Mar 11, 2012 11:08 am
- Post datetime: 2016-01-27T19:01:12+00:00
- Post Title: TMNT: Re-Shelled .bf file (NEED SCRIPT THAT DOESN'T ERROR)

Tried every other bf extractor. Could the edat psn additional extension be messing up with the extraction? Please help, thanks.
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2016-01-28T01:25:28+00:00
- Post Title: TMNT: Re-Shelled .bf file (NEED SCRIPT THAT DOESN'T ERROR)

Yeah, you'd need to use an EDAT decryptor first.

Better still, the XBLA version just has the .bf archive without any encryption.
## Post #3
- Username: jackskellinghog
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Mar 11, 2012 11:08 am
- Post datetime: 2016-01-29T20:21:48+00:00
- Post Title: TMNT: Re-Shelled .bf file (NEED SCRIPT THAT DOESN'T ERROR)

Ugh why didn't I think of that, thank you so much! I'll see what happens with the xbla archive.
## Post #4
- Username: jackskellinghog
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Mar 11, 2012 11:08 am
- Post datetime: 2016-01-29T20:41:08+00:00
- Post Title: TMNT: Re-Shelled .bf file (NEED SCRIPT THAT DOESN'T ERROR)

Nope still no dice, the bf extractors simply do not recognise it. This sucks
## Post #5
- Username: jackskellinghog
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Mar 11, 2012 11:08 am
- Post datetime: 2016-01-30T23:43:43+00:00
- Post Title: TMNT: Re-Shelled .bf file (NEED SCRIPT THAT DOESN'T ERROR)

I ended up using this script

# PS3 Michael Jackson - The Experience (.bf archive)

comtype lzo1x
idstring "ABE\0"
get DUMMY long
get DUMMY long
get DUMMY long
get DUMMY long
get DUMMY long
get OFFSET long
get DUMMY long
get SIZE long
get DUMMY long
get DUMMY long
get FILES long
get DUMMY long

goto OFFSET
get DUMMY long
get DUMMY long
get DUMMY long

for i = 0 < FILES
    getdstring NAME 0x50
    get DUMMY long
    get DUMMY long
    get ZSIZE long
    get DUMMY longlong
    get DUMMY long
    get DUMMY long
    get OFFSET longlong
    get SIZE long
    getdstring DUMMY 0x50

    math ZIP = 0
    if ZSIZE < SIZE
        math ZIP = 1
    endif

    savepos TMP
    goto OFFSET
    get ZSIZE long
    get SIZE long
    goto TMP
    math OFFSET += 0x20
    if ZIP == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next i

But got this error as a response (it extracted about 100 meg of the 200 meg that's supposedly stored)

[http://puu.sh/mPSeb/8aeb406011.png](http://puu.sh/mPSeb/8aeb406011.png)

Could anyone suggest a new script for this specific bf file? Thanks. (Nearly there!!)
## Post #6
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2016-01-31T15:17:58+00:00
- Post Title: TMNT: Re-Shelled .bf file (NEED SCRIPT THAT DOESN'T ERROR)

Hey Jack, what sort of Data did you manage to pull? I'm keen to get my hands on some of the models from this -- very glad someone went looking into it!
## Post #7
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2016-01-31T15:19:05+00:00
- Post Title: TMNT: Re-Shelled .bf file (NEED SCRIPT THAT DOESN'T ERROR)

For anyone looking into this

Use this BMS script

```
#
# Written by Ekey (h4x0r)
# http://www.progamercity.net
#
# script for QuickBMS http://quickbms.aluigi.org

idstring "ABE"
goto 0x18
get TABLEOFFSET long
goto 0x2C
get FILES long
goto TABLEOFFSET

for i = 0 < FILES
   get DUMMY long
   get DUMMY longlong
   getdstring NAME 108
   get OFFSET long
   get DUMMY long
   get SIZE long
   getdstring TRASH 68
    log NAME OFFSET SIZE
next i
```
## Post #8
- Username: jackskellinghog
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Mar 11, 2012 11:08 am
- Post datetime: 2017-11-28T13:15:11+00:00
- Post Title: TMNT: Re-Shelled .bf file (NEED SCRIPT THAT DOESN'T ERROR)

[https://imgur.com/a/MqV0Z](https://imgur.com/a/MqV0Z)

Sorry for such a long delay, here is what the bf file has in it. I can't extract those bins for the life of me though, if anyone could help that'd be great. Here is a sample of one of the bin files [https://mega.nz/#!2ZszzKwZ!5aq4383bfpOp ... s_EV4FsiOo](https://mega.nz/#!2ZszzKwZ!5aq4383bfpOp1CVsad9o34H1IngcGkRVks_EV4FsiOo)
