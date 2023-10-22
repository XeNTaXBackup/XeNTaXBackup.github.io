## Post #1
- Username: Hevon
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Dec 17, 2007 9:19 am
- Post datetime: 2009-10-30T03:15:28+00:00
- Post Title: Brutal Legend .~h and .~p files format ( Xbox360 )

Hi
I'm trying to find a way to get the model and texture for mod them or just for take a view.. i have compressed 2 files in a rar and uploaded [http://www.sendspace.com/file/xiefx9](http://www.sendspace.com/file/xiefx9) so if someone can help me    that would be awesome cause its a great game and hope to see all the models and texture from it.
( sorry for my bad english )
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-30T13:54:27+00:00
- Post Title: Brutal Legend .~h and .~p files format ( Xbox360 )

really a horrible format but I guess to have figured it:
*edit* watch the next posts
tell me if it works also with all the other files you have there.
## Post #3
- Username: Insomniac
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Apr 24, 2009 11:11 am
- Post datetime: 2009-10-30T17:45:19+00:00
- Post Title: Brutal Legend .~h and .~p files format ( Xbox360 )

I seem to be getting the following error with the script:

```
- open input file RgB_Faction.~h
- open script BL.bms

Error: invalid endian value big\par

Error: invalid datatype long\par at line 10


```
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-30T18:15:52+00:00
- Post Title: Brutal Legend .~h and .~p files format ( Xbox360 )

are you using the current version of quickbms?
have you saved the file correctly?
that one is the same script I have used here.

then as first test try the script on single files instead of the input folder directly
## Post #5
- Username: Hevon
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Dec 17, 2007 9:19 am
- Post datetime: 2009-10-30T19:06:56+00:00
- Post Title: Brutal Legend .~h and .~p files format ( Xbox360 )

work verywell with the files i uploaded but not the others
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-30T19:17:59+00:00
- Post Title: Brutal Legend .~h and .~p files format ( Xbox360 )

that error means that happened a possible overflow, so I guess that one was a xmemcompressed file.
you can try adding the following command before the "clog" one
math SIZE += 1000

so:

```
    else
        math SIZE += 1000
        clog NAME OFFSET ZSIZE SIZE 1
    endif
    ...
```
let me know if the extraction continues correctly
## Post #7
- Username: Hevon
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Dec 17, 2007 9:19 am
- Post datetime: 2009-10-30T19:46:29+00:00
- Post Title: Brutal Legend .~h and .~p files format ( Xbox360 )

work very nice now but only crash with the bigger file i have ( 400mo ).
quickbms start extracting and after 5sec it crash.
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-30T19:55:13+00:00
- Post Title: Brutal Legend .~h and .~p files format ( Xbox360 )

the crash is a typical effect of the XMemDecompress function when used on data not compressed with that algorithm.
uhmmm can you paste here the latest lines showed by quickbms before the crash?
## Post #9
- Username: Insomniac
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Apr 24, 2009 11:11 am
- Post datetime: 2009-10-30T20:10:38+00:00
- Post Title: Brutal Legend .~h and .~p files format ( Xbox360 )

> Reply from aluigi
>
> 
have you saved the file correctly?

This was my problem... for some reason the text file I pasted the script in was causing the problem.

Now, the QuickBMS script works perfectly for most of the files... but I get the same crash as Hevon for a couple of the larger files (240+ mb and 400+ mb).
## Post #10
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-30T20:51:46+00:00
- Post Title: Brutal Legend .~h and .~p files format ( Xbox360 )

that's definitely the crash of XMemDecompress.
so the only explanation is that this file "a01_avatar" is not compressed with xmemdecompress but with zlib (if was in plain-text the clog function wasn't called).

can you upload the ~h file?
probably is useful also the first megabyte of the ~p one
## Post #11
- Username: Insomniac
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Apr 24, 2009 11:11 am
- Post datetime: 2009-10-30T21:49:36+00:00
- Post Title: Brutal Legend .~h and .~p files format ( Xbox360 )

The contents of this post was deleted because of possible forum rules violation.
## Post #12
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-30T22:02:18+00:00
- Post Title: Brutal Legend .~h and .~p files format ( Xbox360 )

ok was still the problem with the SIZE value so I have decided to remove the "math SIZE >>= 1" operation, that's the complete script:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

open FDDE "~h" 0
open FDDE "~p" 1

endian big
idstring dfpf
get DUMMY long
get DUMMY long
get DUMMY long  # align?
get DUMMY long
get NAME_OFF long
get DUMMY long
get DUMMY long
get FILES long

math INFO_SIZE = FILES
math INFO_SIZE <<= 4
math INFO_OFF = NAME_OFF
math INFO_OFF -= INFO_SIZE
goto INFO_OFF

for i = 0 < FILES
    get SIZE threebyte
    get DUMMY short
    get ZSIZE threebyte
    get OFFSET threebyte
    get DUMMY byte
    get NAMEX threebyte
    get COMTYPE byte

    savepos INFO_OFF
    math NAMEX >>= 3
    math NAMEX += NAME_OFF
    goto NAMEX
    get NAME string
    goto INFO_OFF

    if COMTYPE & 2
        comtype XMemDecompress
    else
        comtype zlib
    endif

    if SIZE & 0x800000
        math SIZE -= 0x800000
    endif
    if ZSIZE & 0x800000
        math ZSIZE -= 0x800000
    endif

    #math SIZE >>= 1
    math ZSIZE >>= 1
    math OFFSET <<= 5
    if SIZE == ZSIZE
        log NAME OFFSET SIZE 1
    else
        clog NAME OFFSET ZSIZE SIZE 1
    endif
    math OFFSET += ZSIZE
next i
```
now I'm sure it will work perfectly :)
if yes remember to re-extract also the other archives extracted previously.
## Post #13
- Username: Hevon
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Dec 17, 2007 9:19 am
- Post datetime: 2009-10-30T22:57:09+00:00
- Post Title: Brutal Legend .~h and .~p files format ( Xbox360 )

A New error while extracting a 235mo file



By the way the 400mo one was extracted perfectly with the new script
## Post #14
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-30T23:09:55+00:00
- Post Title: Brutal Legend .~h and .~p files format ( Xbox360 )

that one is not an error of the script or of quickbms, it's just an invalid filename.
on a file system can't exist a file and a folder with the same name while as you can see there is the file particles/textures/fire/beastfire and then the file beastfire located in a folder with the same name of the previous one.

an idea would be to skip that file hoping there are not other invalid names.
you can do it adding the following commands before "#math SIZE >>= 1":

```
    set NAME string "particles/textures/fire/beastfire2"
endif
#math SIZE >>= 1
```
unfortunately there is not much else to do
## Post #15
- Username: Hevon
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Dec 17, 2007 9:19 am
- Post datetime: 2009-10-30T23:27:29+00:00
- Post Title: Brutal Legend .~h and .~p files format ( Xbox360 )

> Reply from aluigi
>
> that one is not an error of the script or of quickbms, it's just an invalid filename.
on a file system can't exist a file and a folder with the same name while as you can see there is the file particles/textures/fire/beastfire and then the file beastfire located in a folder with the same name of the previous one.

an idea would be to skip that file hoping there are not other invalid names.
you can do it adding the following commands before "#math SIZE >>= 1":
Code: Select allif NAME == "particles/textures/fire/beastfire"
    set NAME string "particles/textures/fire/beastfire2"
endif
#math SIZE >>= 1unfortunately there is not much else to do

I tried this code and still have the error so i changed by this


```
    set NAME string "particles/textures/fire/beastfire2"
    endif

    #math SIZE >>= 1
```

And worked   
Thanks a lot !
Now trying to find how to view the model.. find the file type and texture type but dunno how to do this
## Post #16
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-30T23:30:38+00:00
- Post Title: Re: Brutal Legend .~h and .~p files format ( Xbox360 )

ih ih ih yeah I forgot to say that you needed to delete that file before relaunching the script :)
well done
so, as far as I have understood, that single file now was the only problem of all the archives extracted with the new script, right? good
## Post #17
- Username: Hevon
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Dec 17, 2007 9:19 am
- Post datetime: 2009-10-30T23:46:51+00:00
- Post Title: Re: Brutal Legend .~h and .~p files format ( Xbox360 )

well it's weird cause the big files now work but the smaller one crash
## Post #18
- Username: Insomniac
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Apr 24, 2009 11:11 am
- Post datetime: 2009-10-31T01:55:44+00:00
- Post Title: Re: Brutal Legend .~h and .~p files format ( Xbox360 )

Yea, the smaller container files are crashing (for example, the one posted in the first post).
## Post #19
- Username: Hevon
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Dec 17, 2007 9:19 am
- Post datetime: 2009-11-09T22:55:55+00:00
- Post Title: Re: Brutal Legend .~h and .~p files format ( Xbox360 )

Any update of the script for extract all the files ? 
I hope i dont bother ask all the time i'm sorry
## Post #20
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-10T11:33:20+00:00
- Post Title: Re: Brutal Legend .~h and .~p files format ( Xbox360 )

no, the only thing you can do is uncommenting that "math SIZE >>= 1" operation (so from "#math SIZE >>= 1" to "math SIZE >>= 1") when you find files that crash and recommenting it for the others (those bigs as far as I have understood).
this is the only work-around I can suggest
## Post #21
- Username: Hevon
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Dec 17, 2007 9:19 am
- Post datetime: 2009-11-10T16:26:15+00:00
- Post Title: Re: Brutal Legend .~h and .~p files format ( Xbox360 )

ok    Thanks so much !
## Post #22
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2009-11-17T02:18:17+00:00
- Post Title: Re: Brutal Legend .~h and .~p files format ( Xbox360 )

I get this error with a 14MB file:

Here is the file, if you want to look at it. [http://www.sendspace.com/file/y466qs](http://www.sendspace.com/file/y466qs)
## Post #23
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2009-11-17T20:29:08+00:00
- Post Title: Re: Brutal Legend .~h and .~p files format ( Xbox360 )

offset 0x0C (usually 0x800) is the offset to some data, the count of which is at offset 0x18

```
{
    uint32 nameLength;
    char name[nameLength];
    uint32 unknown[3];
};

```


offset 0x1C is the size in bytes of the NAME_OFF data
the INFO_OFF value is at offset 0x3C


Should help save some of the math that is currently done.


May have some more later.  But i only have the files posted in this thread to test against at the moment.
## Post #24
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2010-09-02T16:27:31+00:00
- Post Title: Re: Brutal Legend .~h and .~p files format ( Xbox360 )

The contents of this post was deleted because of possible forum rules violation.
## Post #25
- Username: Isilfor
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Jul 20, 2010 12:01 am
- Post datetime: 2013-03-03T19:03:31+00:00
- Post Title: Re: Brutal Legend .~h and .~p files format ( Xbox360 )

> Reply from revelation
>
> 
May have some more later.  But i only have the files posted in this thread to test against at the moment.
This files from PC version. Please help with unpacking.
[http://www.sendspace.com/file/qw1y8y](http://www.sendspace.com/file/qw1y8y)
## Post #26
- Username: Isilfor
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-03-04T06:14:39+00:00
- Post Title: Re: Brutal Legend .~h and .~p files format ( Xbox360 )

Isilfor
[http://yadi.sk/d/gZwnI1di31_kQ](http://yadi.sk/d/gZwnI1di31_kQ)
Use: [http://www.mediafire.com/?x3gho8rcvfsy3g0](http://www.mediafire.com/?x3gho8rcvfsy3g0)
