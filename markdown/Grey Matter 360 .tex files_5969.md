## Post #1
- Username: SLIFallen
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Sep 28, 2010 11:26 pm
- Post datetime: 2011-02-02T16:11:27+00:00
- Post Title: Grey Matter 360 .tex files

Apparently the 360 version of this game has a compression type for the textures (vs. the PC version that is straight .dds) 

Providing a sample here as there are now updated tools for extracting the PAK files and blender imports provided here by the community for the 360 version.   


[HERE are some sample texture files ](http://www.highendgames.net/Lee/bulldog1.fbm.rar)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-02-02T22:16:12+00:00
- Post Title: Grey Matter 360 .tex files

they are xpr files you need to recreate the xpr header then use the xpr tool unbundler from the xbox sdk on them.
## Post #3
- Username: SLIFallen
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Sep 28, 2010 11:26 pm
- Post datetime: 2011-02-03T17:31:20+00:00
- Post Title: Grey Matter 360 .tex files

> Reply from chrrox
>
> they are xpr files you need to recreate the xpr header then use the xpr tool unbundler from the xbox sdk on them.

Way over my head. I'm no programmer.
## Post #4
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2011-02-04T11:10:09+00:00
- Post Title: Grey Matter 360 .tex files

```
# TEX to DDS converter
# by Fatduck    Feb2011
# script for QuickBMS    http://aluigi.org/papers.htm#quickbms

endian big
get DDSNAME basename
get DATASIZE asize
set XPRNAME DDSNAME
string XPRNAME += .xpr
putvarchr MEMORY_FILE 0 0
append
putdstring "XPR2" 4 MEMORY_FILE
put 0x64 long MEMORY_FILE
put DATASIZE long MEMORY_FILE
put 1 long MEMORY_FILE
putdstring "TX2D" 4 MEMORY_FILE
put 0x30 long MEMORY_FILE
put 0x34 long MEMORY_FILE
put 0x14 long MEMORY_FILE
putdstring DDSNAME 0x1C MEMORY_FILE
log MEMORY_FILE 0 DATASIZE 
append

math DATASIZE += 0x3C
log XPRNAME 0 DATASIZE MEMORY_FILE
```


This one should work!
You still need a program called unblundler to convert it back to tga!
Good Luck

Sorry, now fixed!
## Post #5
- Username: SLIFallen
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Sep 28, 2010 11:26 pm
- Post datetime: 2011-02-04T12:06:33+00:00
- Post Title: Grey Matter 360 .tex files

Wow. Awesome! Thank you!

Might someone PM me the unbundler app? Kind of overkill to have to dl/install the whole 360sdk (which is useless to the non-programmer like me) just for one little app.  

Thanks again!!

EDIT. Got it!  Thanks!
## Post #6
- Username: SLIFallen
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Sep 28, 2010 11:26 pm
- Post datetime: 2011-02-04T15:14:46+00:00
- Post Title: Grey Matter 360 .tex files

Hmmm. Does not seem to be working:

I get this:

  - error in src\quickbms.c line 8623: dumpa_direct_copy<>
Error: No such file or directory

I run quickbms (.0.4.8a) pick the script, set the input folder (using "" to get all the .tex files) and select an output folder, click save and I get this...?
## Post #7
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-06T00:13:33+00:00
- Post Title: Grey Matter 360 .tex files

great chrrox
## Post #8
- Username: SLIFallen
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Sep 28, 2010 11:26 pm
- Post datetime: 2011-02-06T13:38:01+00:00
- Post Title: Grey Matter 360 .tex files

Maybe i'm not being specific enough. Here is a screenshot of what is happening. You can clearly see the script is finding (one of) the files and in fact creates the file name in the target directory with a zero byte size.
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-02-06T15:04:21+00:00
- Post Title: Grey Matter 360 .tex files

this bms script just creates xpr files those are a known file format on the xbox 360 you need the xbox skd to extract dds images from it.

if one file is giving you trouble upload it.
also make sure you have the newest quickbms.
## Post #10
- Username: SLIFallen
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Sep 28, 2010 11:26 pm
- Post datetime: 2011-02-07T09:51:54+00:00
- Post Title: Grey Matter 360 .tex files

> Reply from chrrox
>
> this bms script just creates xpr files those are a known file format on the xbox 360 you need the xbox skd to extract dds images from it.

if one file is giving you trouble upload it.
also make sure you have the newest quickbms.

Yes, chrrox, I do understand what you are pointing out. The screenshot shows exactly that.

It is "seeing" one of the target files (angela_alpha_hair_color.tex) in the input folder (temp3) and converting it to the .xpr equivelent and placing it in (Temp5) The file is created in the output folder but it is zero bytes.

I do have the unbundler tool from the 360 sdk to use on the files AFTER they are back to .xpr's.

A sample file (folder) is in my first post at the top of this thread. Thanks!
## Post #11
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2011-02-08T12:02:12+00:00
- Post Title: Grey Matter 360 .tex files

Make sure you had copy the latest BMS script! 
I did edit it once and it should work!
## Post #12
- Username: SLIFallen
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Sep 28, 2010 11:26 pm
- Post datetime: 2011-02-08T13:05:38+00:00
- Post Title: Grey Matter 360 .tex files

> Reply from fatduck
>
> Make sure you had copy the latest BMS script! 
I did edit it once and it should work!

As stated above I am running 0.4.8a

I did finally get it to work command line ONLY. using the quickbms GUI does not work. (and the quickbms readme is contradictory (backwards) on the syntax layout. So that was confusing me even more)

A shame you cant use wildcard arguments on unbundler.exe. One file at a time, but hey, it's better than NOTHING!

Thanks to all!!
## Post #13
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-08T14:22:28+00:00
- Post Title: Grey Matter 360 .tex files

thanks a lot
## Post #14
- Username: lUIGUIPIETRO
- Rank: veteran
- Number of posts: 87
- Joined date: Sat Mar 13, 2010 10:59 pm
- Post datetime: 2011-07-26T20:31:21+00:00
- Post Title: Grey Matter 360 .tex files

how cant open xpr files?
