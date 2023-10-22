## Post #1
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2011-10-02T04:27:02+00:00
- Post Title: Castlevania: Harmony of Despair

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-10-09T20:38:39+00:00
- Post Title: Castlevania: Harmony of Despair

nice simple format

edit other files may hold more than 1 dds file. if you find one, upload it (though i could guess it now)

```
# script for QuickBMS by WRS
endian big

idstring "\x19\x75\x11\x20"
get DUMMY long
get DUMMY long
get DUMMY long
get STRLEN long
get DATAPNTR long
get SIZE long
get ZSIZE long
getdstring STR STRLEN

clog STR DATAPNTR ZSIZE SIZE

```
## Post #3
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2011-10-11T12:18:54+00:00
- Post Title: Castlevania: Harmony of Despair

Amazing! Thanks WRS, works perfectly.  Just FYI to anyone else who wants to look at these .dds files, their channels have been swapped, R=G, G=R, B=A, A=B, once you assign them properly then all is well.
## Post #4
- Username: unlimited32
- Rank: beginner
- Number of posts: 38
- Joined date: Sat Oct 16, 2010 8:27 pm
- Post datetime: 2011-10-16T11:05:25+00:00
- Post Title: Castlevania: Harmony of Despair

> Reply from zardalu
>
> Amazing! Thanks WRS, works perfectly.  Just FYI to anyone else who wants to look at these .dds files, their channels have been swapped, R=G, G=R, B=A, A=B, once you assign them properly then all is well.

wow but how do i swap everithing right? i am using photoshop!!
## Post #5
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2011-10-16T13:40:34+00:00
- Post Title: Castlevania: Harmony of Despair

> Reply from unlimited32
>
> zardalu wrote:Amazing! Thanks WRS, works perfectly.  Just FYI to anyone else who wants to look at these .dds files, their channels have been swapped, R=G, G=R, B=A, A=B, once you assign them properly then all is well.

wow but how do i swap everithing right? i am using photoshop!!

Go to the menu and choose Image –> Adjustments –> Channel Mixer… Now you can change the Red Output Channel and set the value for Red to 0% and change the Green value to 100%. On the Green output Channel you set the Green Source Channel to 0% and Red to 100%. Instead for the alpha channel u need to go on the channel menu on the right and copy the alpha channel in the blu channel and the blue channel in the alpha channel.

I tried with that swap combination of channels but i think there is something wrong...maybe because i converted the dds to tga..but 
i don't think that this is the real problem. I will try to swap other channels. If somebody has a screenshot of the real color of this 
map please post it here.
## Post #6
- Username: unlimited32
- Rank: beginner
- Number of posts: 38
- Joined date: Sat Oct 16, 2010 8:27 pm
- Post datetime: 2011-10-21T17:52:10+00:00
- Post Title: Castlevania: Harmony of Despair

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2011-10-24T15:19:09+00:00
- Post Title: Castlevania: Harmony of Despair

The contents of this post was deleted because of possible forum rules violation.
## Post #8
- Username: unlimited32
- Rank: beginner
- Number of posts: 38
- Joined date: Sat Oct 16, 2010 8:27 pm
- Post datetime: 2011-10-25T14:11:13+00:00
- Post Title: Castlevania: Harmony of Despair

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2011-10-29T11:17:09+00:00
- Post Title: Castlevania: Harmony of Despair

The contents of this post was deleted because of possible forum rules violation.
## Post #10
- Username: unlimited32
- Rank: beginner
- Number of posts: 38
- Joined date: Sat Oct 16, 2010 8:27 pm
- Post datetime: 2011-10-29T17:24:30+00:00
- Post Title: Castlevania: Harmony of Despair

The contents of this post was deleted because of possible forum rules violation.
## Post #11
- Username: piratesephiroth
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Nov 08, 2009 6:05 pm
- Post datetime: 2018-05-15T14:38:11+00:00
- Post Title: Castlevania: Harmony of Despair

I just began looking at this game so I tweaked the script to extract arcs that contain multiple files

```

idstring "\x19\x75\x11\x20"
get DUMMY long
get FILECOUNT long
get DUMMY long

for i = 0 < FILECOUNT
    get FNAME_OFFSET long
    get FILE_OFFSET long
    get SIZE long
    get ZSIZE long
    savepos CHECKPOINT
    goto FNAME_OFFSET
    get FNAME string
    if SIZE == ZSIZE
        log FNAME OFFSET SIZE
    else
        clog FNAME FILE_OFFSET ZSIZE SIZE
    endif
    goto CHECKPOINT
next i

```
