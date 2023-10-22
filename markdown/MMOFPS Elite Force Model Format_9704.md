## Post #1
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2012-10-02T16:14:01+00:00
- Post Title: MMOFPS Elite Force Model Format

This game is a new MMOFPS, and i found its model format are .wpk, like SUN, but can't use wpktool because it had been encrypted  There are some pic about this game 



Example file : 

```
http://www.mediafire.com/?8p6dd59zeie22md
```


Sorry about my bad Eng
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-10-02T22:40:18+00:00
- Post Title: MMOFPS Elite Force Model Format

I don't think it is encrypted. Are you sure it is the same format as SUN online? Like, did someone say it was the same format?

Ok a single wpk file contains multiple models.
Just search for MSD0 as the start of the model, search for the next occurrence, and then export it.
[eliteforce3.jpg](https://xentaxbackup.github.io/file/5872_eliteforce3.jpg)
## Post #3
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2012-10-03T02:28:16+00:00
- Post Title: MMOFPS Elite Force Model Format

> Reply from finale00
>
> I don't think it is encrypted. Are you sure it is the same format as SUN online? Like, did someone say it was the same format?

Ok a single wpk file contains multiple models.
Just search for MSD0 as the start of the model, search for the next occurrence, and then export it.

Because they are .wpk files, so i think same format as SUN online, and i had used wpk tool but couldn't decompress those files so i think they are encrypted, if i wrong, sorry about that  
Thanks for helping me  but why when i export to .wzm, noesis or max script can't load it? can you explain for me?. Sorry T_T
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-10-03T03:59:02+00:00
- Post Title: MMOFPS Elite Force Model Format

Because it has nothing to do with SUN.
## Post #5
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2012-10-03T04:11:55+00:00
- Post Title: MMOFPS Elite Force Model Format

> Reply from finale00
>
> Because it has nothing to do with SUN.

oh   would you mind telling me what type of file i need to export ? Thanks
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-10-03T15:06:39+00:00
- Post Title: MMOFPS Elite Force Model Format

It's a proprietary format, or at least one I haven't seen prior to this.
## Post #7
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2012-10-03T15:26:21+00:00
- Post Title: MMOFPS Elite Force Model Format

> Reply from finale00
>
> It's a proprietary format, or at least one I haven't seen prior to this.

oh, that game from China and Taiwan, they always encrypt files like that  Elite Force has nice model and texture so i just want to export them. Would you mind helping me about its .wpk files. i don't know a lot about Hex
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-10-03T16:06:43+00:00
- Post Title: MMOFPS Elite Force Model Format

The file table is compressed I didn't actually try to look at it but the data itself is not obfuscated you can easily get them out by searching for MSD0 strings.
Well, right before the file table data there are two integers one for the compressed size and other presumably uncompressed size so you could run it through comtype_scan2 and try to get the compression algo.
## Post #9
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2012-10-04T04:09:20+00:00
- Post Title: MMOFPS Elite Force Model Format

Maybe COMP_ASCII85( 26.dmp ) or OMP_RLEW ( 32.dmp ), i haven't used comtype before, and i use it for the file has header is MSD0 which i export from .wpk, 26.dmp and 32.dmp contains some info like this pic, but 32.dmp don't have "MS" and 26.dmp has this value, sorry if i wrong :-s, and i try to use comtype with wpk file, and output file is large capacity ( ~ 2GB )
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-10-04T16:31:06+00:00
- Post Title: MMOFPS Elite Force Model Format

No the file table is the stuff right before the first msd0 tag.
## Post #11
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2012-10-05T05:03:27+00:00
- Post Title: MMOFPS Elite Force Model Format

> Reply from finale00
>
> No the file table is the stuff right before the first msd0 tag.

maybe this , i just export value before first msd0 tag, and use comtype
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-10-05T15:39:05+00:00
- Post Title: MMOFPS Elite Force Model Format

Nope there's nothing there.
## Post #13
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2012-10-06T07:22:13+00:00
- Post Title: MMOFPS Elite Force Model Format

> Reply from finale00
>
> Nope there's nothing there.

can you tell me what i need to do to find the main file , over 100 files with hex value
## Post #14
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-08-07T01:54:43+00:00
- Post Title: MMOFPS Elite Force Model Format

use this bms script to split the model files from skin.wpk

```
do
    goto OFFSET
    get DUMMY long
    findloc NEXT_OFFSET binary "\x4d\x53\x44\x30" 0 ""
    if NEXT_OFFSET == ""
        get SIZE asize
    else
        math SIZE = NEXT_OFFSET
    endif
    math SIZE -= OFFSET
    log "" OFFSET SIZE
    math OFFSET = NEXT_OFFSET
while NEXT_OFFSET != ""

```


00000000000000a2.msd  



00000000000000a2.png (35.42 KiB) Viewed 85 times



0x14e - face count
0x3a6c - vertex count
## Post #15
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2016-08-07T03:44:54+00:00
- Post Title: MMOFPS Elite Force Model Format

finale00 made the Noesis Script for that but idk why it didn't work with the extracted files   

[here](http://himeworks.com/redirect.php?type=noesis&name=EliteForce_wpk)
## Post #16
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-09-19T03:03:53+00:00
- Post Title: Re: MMOFPS Elite Force Model Format

made a Noesis python script to open the msd model files split from skin.wpk with the bms script  


 fmt_EliteForce_msd.zip
(1023 Bytes) Downloaded 32 times


supports geometry and UVs
## Post #17
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2016-09-21T15:18:05+00:00
- Post Title: Re: MMOFPS Elite Force Model Format

> Reply from AceWell
>
> made a Noesis python script to open the msd model files split from skin.wpk with the bms script  
fmt_EliteForce_msd.zip
supports geometry and UVs

cool  thank you so much, I didn't check xentax for 2 weeks  thanks for your help
## Post #18
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2016-09-24T08:40:55+00:00
- Post Title: Re: MMOFPS Elite Force Model Format

onelove1210,

Can you give me a link to this game?
I did find a game called Elite Force , but it has not .wpk files.

(Please read your PM.)
