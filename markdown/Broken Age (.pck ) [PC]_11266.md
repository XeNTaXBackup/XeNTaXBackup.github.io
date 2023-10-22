## Post #1
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2014-02-28T16:32:17+00:00
- Post Title: Broken Age (.pck ) [PC]

Who can help with the extract the pck file?THX!

Samples:
data.pck
[http://www12.zippyshare.com/v/92896868/file.html](http://www12.zippyshare.com/v/92896868/file.html)
## Post #2
- Username: mappy2012
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-02-28T17:03:50+00:00
- Post Title: Broken Age (.pck ) [PC]

```
math size - 0xC
goto size
get files short
get FTsize long
get DATAsize long
goto DATAsize

for i = 0 < files
   get FULLNAME basename
   log MEMORY_FILE 0 0
   savepos offset
   getdstring dummy 0x14
   get size long
   get size2 long
   get NAMEsize long
   getdstring dummy 0xA
   savepos TMP
   get key byte
   goto TMP
   if key <= 0x80
      set key = 0x80
   endif
   get FILEoffset long
   math FILEoffset + 0x1e
   getdstring name NAMEsize
   putdstring name NAMEsize MEMORY_FILE
   filexor key MEMORY_FILE
   goto 0x00 MEMORY_FILE
   getdstring name NAMEsize MEMORY_FILE
   filexor ""
   string FULLNAME + "/"
   string FULLNAME + name
   log FULLNAME FILEoffset size
next i
```
## Post #3
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2014-02-28T17:24:24+00:00
- Post Title: Broken Age (.pck ) [PC]

Thanks a lot!!!
## Post #4
- Username: kofola
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Mar 10, 2014 12:12 am
- Post datetime: 2014-03-10T11:47:34+00:00
- Post Title: Broken Age (.pck ) [PC]

Some tools for extract/import game lang text? I needed
## Post #5
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-03-10T16:08:25+00:00
- Post Title: Broken Age (.pck ) [PC]

kofola
Texts in lua-scripts
## Post #6
- Username: kofola
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Mar 10, 2014 12:12 am
- Post datetime: 2014-03-11T08:14:47+00:00
- Post Title: Broken Age (.pck ) [PC]

Have you some good viewer for *.lua. files?
And where is language text and dialog?
## Post #7
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-03-11T21:14:20+00:00
- Post Title: Broken Age (.pck ) [PC]

kofola
Use unluac and luac =)
## Post #8
- Username: kofola
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Mar 10, 2014 12:12 am
- Post datetime: 2014-03-13T22:51:18+00:00
- Post Title: Broken Age (.pck ) [PC]

> Reply from Haoose
>
> kofola
Use unluac and luac =)

yop, but where is located texts for translate?
## Post #9
- Username: kofola
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Mar 10, 2014 12:12 am
- Post datetime: 2014-03-15T16:13:39+00:00
- Post Title: Broken Age (.pck ) [PC]

????????????
## Post #10
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-03-15T16:49:30+00:00
- Post Title: Broken Age (.pck ) [PC]

In data.pck if I remember correctly.
## Post #11
- Username: kofola
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Mar 10, 2014 12:12 am
- Post datetime: 2014-03-15T17:05:39+00:00
- Post Title: Broken Age (.pck ) [PC]

Yeah Merlin i have exported this, but Its many folders in pack.
So i dont know where is "lang" files.

Thank you for any help.
## Post #12
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2014-03-15T19:12:23+00:00
- Post Title: Broken Age (.pck ) [PC]

data\Dialog\Linecodes
## Post #13
- Username: az654
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Oct 31, 2014 4:39 am
- Post datetime: 2014-10-30T20:44:33+00:00
- Post Title: Broken Age (.pck ) [PC]

Is there any way to re import the extracted files to the pck?

thanks
## Post #14
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-10-31T06:54:32+00:00
- Post Title: Broken Age (.pck ) [PC]

Yes. The script Haoose posted can be used also for reimporting files back to .pck.

Example:

```
quickbms -r -w script.bms data.pck unpacked_folder
```


Or read section 3 in quickbms.txt
## Post #15
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2015-04-30T14:50:25+00:00
- Post Title: Broken Age (.pck ) [PC]

.tex files [http://zenhax.com/viewtopic.php?f=7&t=888](http://zenhax.com/viewtopic.php?f=7&t=888)
## Post #16
- Username: akislb99
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 14, 2015 6:45 pm
- Post datetime: 2015-06-14T11:00:01+00:00
- Post Title: Re: Broken Age (.pck ) [PC]

Hello!
I've successfully extracted the files from the data.pck, edited the language scripts (the new file is smaller than the original), but I couldn't repack the files using the reinport function of QuickBMS. I've attached a screenshot of the error message.
What should I do?  
[quickbms.jpg](https://xentaxbackup.github.io/file/9307_quickbms.jpg)
## Post #17
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2015-06-14T20:32:38+00:00
- Post Title: Re: Broken Age (.pck ) [PC]

akislb99
Try this tool [https://yadi.sk/d/ei_O2_XdhFSXg](https://yadi.sk/d/ei_O2_XdhFSXg) (BATool by Thief1987)
## Post #18
- Username: akislb99
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 14, 2015 6:45 pm
- Post datetime: 2015-06-15T12:24:13+00:00
- Post Title: Re: Broken Age (.pck ) [PC]

Thanks for the help but I finally managed to successfully unpack and repack the .pck files using QuickBMS, I've made only a silly mistake when repacking (I've selected the data folder itself and not the folder containing the data folder). 

However, even though the packing and unpacking now works, I have problems with editing the lua scripts. I've used the mentioned unluac.jar program to decompile the scripts, but even if I compile it without editing the decompiled file, I get a smaller file and if I pack the new script into the data.pck file, the game doesn't work, after the Double Fine splash screen the game stops and I get a strange picture (see the attachment). The unpacking and repacking works fine with the original files, not there is the problem.

I think that some important data may be lost during the decompilation because if I decompile and compile the smaller already compiled file, the sizes of the two compiled files will match (even after more cycles of this decompile/compile process). I could not find any more working lua decompilers, is there any? What should I try?  

I haven't used the word "(de)compile" so many times in any post yet...
[brokenage.jpg](https://xentaxbackup.github.io/file/9314_brokenage.jpg)
## Post #19
- Username: sigmagamma
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 05, 2022 12:53 am
- Post datetime: 2022-02-08T19:19:37+00:00
- Post Title: Re: Broken Age (.pck ) [PC]

Help anyone?
I'm unable to unpack data.pck correctly with the script. filenames come out as gibberish, see image.
Looks like BAtool isn't available either anymore at that address.
Thanks for any help 

Edit: I was able to extract the game files using "game extractor", but I imagine I'll still need quickbms to work in order to repack them, so the above question's still relevant.

Other than the texts which I've found, there are the font files - I found two sets of files with fnt and font extensions in pdata.pck, but I'm not sure how to open or modify those.

Again, thanks for any help.
[quickbms.jpg](https://xentaxbackup.github.io/file/21750_quickbms.jpg)
