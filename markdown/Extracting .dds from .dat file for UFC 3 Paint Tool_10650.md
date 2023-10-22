## Post #1
- Username: MattJabz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Aug 02, 2013 6:28 pm
- Post datetime: 2013-08-02T12:19:19+00:00
- Post Title: Extracting .dds from .dat file for UFC 3 Paint Tool

I've been researching on how to extract image files from a .dat file and I haven't had any luck. I found a tutorial and it was using BMScript but kept getting the error:

"incomplete input file number 0, can't read 15559 bytes. anyway don'y worry, it's possible that the BMS script has been written to exit in this way if it's reached the end of the archive so check it or contact its author or verify that all the files have been extracted"

Before when I opened Hex Editor, I saw DDS and DXT5. Right now I'm stuck, I don't know how to write a BMScript to extract the images. Also there is another .dat file called PAINTPRM.dat and I don't know what it does.



Right now the UFC Undisputed 3 is dead due to THQ being bankrupt, therefore there isn't any online sharing for CAFs (Create a Fighter) and paint tool. Currently, I'm researching to edit paint tools and make a CAF/paint tool injector. I thought about this when I saw Brienj's great work for WWE games.

So I found a CAFLIST.dat in the system data file and I can find names but still not understanding.



Hopefully, I will be successful with making a injector program and obtaining intermediate knowledge.

Sorry if it seems I'm asking for too much, I'm just stuck atm and this is the only place I can trust and know that will give the best advice possible to my problems. I was on this forum 2/3 years ago for the wrong reasons (craving for wwe game tools) , however now things changed and I believe I'm on this site for the right reasons.

Thanks for Reading,

God Bless.
[ufcfiles.zip](https://xentaxbackup.github.io/file/6540_ufcfiles.zip)
## Post #2
- Username: MattJabz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Aug 02, 2013 6:28 pm
- Post datetime: 2013-08-03T16:13:20+00:00
- Post Title: Extracting .dds from .dat file for UFC 3 Paint Tool

Will there be anyone to help or at least reply? I thought I would get these benefits as I donated.
## Post #3
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2013-08-03T18:28:36+00:00
- Post Title: Extracting .dds from .dat file for UFC 3 Paint Tool

The textures in PAINTDAT.DAT can be extracted using any dds extractor like DragonUnpacker.
## Post #4
- Username: MattJabz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Aug 02, 2013 6:28 pm
- Post datetime: 2013-08-03T19:33:58+00:00
- Post Title: Extracting .dds from .dat file for UFC 3 Paint Tool

> Reply from deepshit
>
> The textures in PAINTDAT.DAT can be extracted using any dds extractor like DragonUnpacker.
I just tried with many dds extractors(even the one you mentioned) and I'm just getting errors. Can anyone find a correct way for it to extract?
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-08-03T20:41:25+00:00
- Post Title: Extracting .dds from .dat file for UFC 3 Paint Tool

> Reply from MattJabz
>
> Can anyone find a correct way for it to extract?Why you don't erase the first 64 bytes of PAINTDAT.DAT and save the rest as dds? -> works.
## Post #6
- Username: MattJabz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Aug 02, 2013 6:28 pm
- Post datetime: 2013-08-04T09:36:08+00:00
- Post Title: Extracting .dds from .dat file for UFC 3 Paint Tool

> Reply from shakotay2
>
> MattJabz wrote:Can anyone find a correct way for it to extract?Why you don't erase the first 64 bytes of PAINTDAT.DAT and save the rest as dds? -> works.
I tried that and none of the software's and dds plugins could open the file. What program did you use to open it if you tried? Also why did I have to erase the first 64 bytes?

Edit: Actually I know why you erase the first 64 bytes and I managed to do it, thanks man.
## Post #7
- Username: MattJabz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Aug 02, 2013 6:28 pm
- Post datetime: 2013-08-04T13:23:36+00:00
- Post Title: Extracting .dds from .dat file for UFC 3 Paint Tool

The tricky part now is getting it into the game properly. The PAINTPRM.DAT may be the issue here, when I went on UFC 3 the game the texture file was corrupt and I'm still researching about this PRM thing. Also this first 64 bytes must mean something since I compared 2 different paint tool files and found out they were different.
