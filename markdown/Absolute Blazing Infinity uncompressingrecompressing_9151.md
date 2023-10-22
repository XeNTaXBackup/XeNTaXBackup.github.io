## Post #1
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-06-27T03:46:46+00:00
- Post Title: Absolute Blazing Infinity uncompressing/recompressing

hey guys iv been trying to uncompressed the files for this game there are only 2 types of files .xwb and .dat
i have tried Xbdecompression and that didn't work ( i can never seem to get that program to work) so if anyone is willing to help me i can send them the files for the game  to see if they can make a uncompressor / recompresser
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-06-27T09:32:59+00:00
- Post Title: Absolute Blazing Infinity uncompressing/recompressing

xwb is the archive of music files, try unxwb:
[http://aluigi.org/papers.htm#unxwb](http://aluigi.org/papers.htm#unxwb)
## Post #3
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-06-27T12:46:54+00:00
- Post Title: Absolute Blazing Infinity uncompressing/recompressing

nice the unxwb worked thank you if i send you the dat files? would you be able to look into it?
(the audio extracts but its a loud buzzing noise XD)
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-06-28T12:09:23+00:00
- Post Title: Absolute Blazing Infinity uncompressing/recompressing

this is the script for the dat files:

```
    get OFFSET long
    if OFFSET == 0
        cleanexit
    endif
    get SIZE long
    log "" OFFSET SIZE
next
```
## Post #5
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-06-28T12:44:34+00:00
- Post Title: Absolute Blazing Infinity uncompressing/recompressing

kk thanks i will give it a try right now

hmm only 1 thing extracted from the files and there way to small
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-06-30T02:22:56+00:00
- Post Title: Absolute Blazing Infinity uncompressing/recompressing

I have tried with all the dat files you provide and everything works correctly, the size of the output folder is close to the one of the archive so it's ok.
## Post #7
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-06-30T04:31:41+00:00
- Post Title: Absolute Blazing Infinity uncompressing/recompressing

> Reply from aluigi
>
> I have tried with all the dat files you provide and everything works correctly, the size of the output folder is close to the one of the archive so it's ok.

okay i tryed the script on a different pc and it worked like a charm but it wont work on the dat files inside would you be able to make a new script for the ones inside if i send them to you ?
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-06-30T12:32:32+00:00
- Post Title: Absolute Blazing Infinity uncompressing/recompressing

I guess you are referring to the big files that you have extracted from the original dat archive, like 0000000f.dat from main_rel.dat.

it's not the same format, indeed this 0000000f.dat file is a sequence of compressed files and there is no index table inside it.
so it's a perfect job for offzip:
offzip -a 0000000f.dat c:\output_folder 0
## Post #9
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-06-30T14:14:52+00:00
- Post Title: Absolute Blazing Infinity uncompressing/recompressing

> Reply from aluigi
>
> I guess you are referring to the big files that you have extracted from the original dat archive, like 0000000f.dat from main_rel.dat.

it's not the same format, indeed this 0000000f.dat file is a sequence of compressed files and there is no index table inside it.
so it's a perfect job for offzip:
offzip -a 0000000f.dat c:\output_folder 0

THANK YOU  SOOO MUCH !!! everything worked perfect  thanks for this now its time to look in all theses files lol


just got 1 more thing can you look into .art and .clc?


( and i found out that some of the small dat files have models in them just  cant get to them XD)
## Post #10
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-06-30T20:09:00+00:00
- Post Title: Absolute Blazing Infinity uncompressing/recompressing

I guess art and the others are not archives so not stuff for me.
## Post #11
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-06-30T22:09:26+00:00
- Post Title: Absolute Blazing Infinity uncompressing/recompressing

kk  ^_^ thanks for all your help
## Post #12
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-07-09T14:42:01+00:00
- Post Title: Absolute Blazing Infinity uncompressing/recompressing

> Reply from aluigi
>
> I guess art and the others are not archives so not stuff for me.
i just have 1 more question would you be able to look into the small dat files im trying to find the script and im having no luck at all
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-07-09T15:33:55+00:00
- Post Title: Absolute Blazing Infinity uncompressing/recompressing

if the dat was inside those you extracted with the script it's a file and so not for me
