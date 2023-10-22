## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-19T01:21:10+00:00
- Post Title: Call of Chaos Online

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-19T13:09:52+00:00
- Post Title: Call of Chaos Online

Which lua file describes the encryption?
Well found the code where the npks get loaded but couldn't trace the calls since they are register indirect ones.
Would need to install the full game to be able to debug it, maybe some time later. No time atm.
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-19T19:57:33+00:00
- Post Title: Call of Chaos Online

Would it be better if I uploaded the updater file would that be easier to trace?
Is there anything I could do to learn to do this on my own?
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-19T20:50:53+00:00
- Post Title: Call of Chaos Online

Well most "encryptions" are quite simple (xors, some arithmetics or the like)
Some people can figure them out just by looking at the file data. Don't know how they do that 
But esp. when it comes to more complex algorithms you need to have a look at the game exe.
I personally always do that cause you always learn something 

Well if you want to learn that, grab some x86 assembler tutorials, get a disassembler like IDA and/or a debugger like [OllyDbg](http://www.ollydbg.de) and play around.
It's all about experience.

[http://www.tuts4you.com/download.php?list.19](http://www.tuts4you.com/download.php?list.19)
This site has loads of tutorials and downloads for almost everything.
Starting with tutorials about Olly and IDA, ending with a detailed explanation of SecuROM
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-24T20:08:21+00:00
- Post Title: Call of Chaos Online

I dug some more into this and I will post what I have found

idstring "NPAK"
get version long
get FILES long
get FILETBLOFF long
get OFFSET long

then you must read the file table
there are 0x18 bytes of encrypted data which I assume is the offset/size/chechsum information
then 0x4 bytes file name length
then what appears to be a partial encrypted file name.
then it goes to the next file table entry.
I have attached a small archive and the unencrypted file names.

not all of these are used in this file but 4 of these are. you can match them using their lengths.
I got these names from the exe.
PostEffect/PP_ColorGBlurH_7Sample.psh
PostEffect/PP_ColorGBlurV_7Sample.psh
PostEffect/PP_BlendWithBlurFactor_With_Param.psh
PostEffect/PP_PixelColorBrightPassFilter.psh
PostEffect/PP_ProcessGlare.psh
PostEffect/PP_ColorGBlurH.psh
PostEffect/PP_ColorGBlurV.psh
[posteffect.rar](https://xentaxbackup.github.io/file/2057_posteffect.rar)
## Post #6
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-09-12T16:06:03+00:00
- Post Title: Call of Chaos Online

googled NPAK compression and this popped up:

[http://code.google.com/p/npk/](http://code.google.com/p/npk/)
