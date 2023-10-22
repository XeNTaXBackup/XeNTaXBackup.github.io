## Post #1
- Username: Abyss Dublagens
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 18, 2020 9:17 am
- Post datetime: 2020-01-18T01:33:40+00:00
- Post Title: Bully - How do I convert .wav files to .xwb and .xsb?

Hi, I am Brazilian and new to this area, please do not call my google english translator. How do I convert .wav files to .xwb and .xsb? I'm doing a project to redouble the speech of the characters in the game Bully.

I asked the same question on your discord server and a guy told me to use ToWav, I searched a lot but I didn't find the download, he didn't answer any more messages, I don't know if he was kidding me '-', if he knows something about me answer please.
## Post #2
- Username: allangod
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 25, 2018 6:58 am
- Post datetime: 2020-01-24T00:00:32+00:00
- Post Title: Bully - How do I convert .wav files to .xwb and .xsb?

ToWav is the right tool. You could've just searched this forum for a download link. [viewtopic.php?f=17&t=7998&p=158837&hilit=ToWav#p158837](https://forum.xentax.com/viewtopic.php?f=17&t=7998&p=158837&hilit=ToWav#p158837) for some download links, but there are more probably.
## Post #3
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2020-01-24T12:22:59+00:00
- Post Title: Bully - How do I convert .wav files to .xwb and .xsb?

I think there is a misunderstanding here. TOWAV is a DECODER only, it will turn xwb to wav but will not do the reverse which you seemingly want.

You need Microsoft XACT to make new xsb/xwb from wav files, however problem is finding the same date xact the original game more or less used or it may not work.
## Post #4
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2020-01-25T04:33:55+00:00
- Post Title: Bully - How do I convert .wav files to .xwb and .xsb?

Hi Abyss Dublagens,
if you have wav files and want to create xsb/xwb, then Apollos answer is absolutely correct: you require the right version of Microsoft XACT (which is/was part of the Microsoft DirectX SKD). If you want the game (Bully) to work with your created xsb/xwb than you also have to know/use the so called cue names (these are in the original .xsb) and their assignment to the wavs (these are stored in the xwb). The game uses the cue names to 'address' (and alter) the wavs stored in the xwb.

Step-by-step:

Find out tool and file format version of the original xsb/xwb. If the files are in little endian format then my old tool xactxtract might do that. Or try Aluigis unxwb (search this forum for a download link).
 DirectX SDK from Mar2008 created xsb/xwb with Tool version 44 and file format version 42. So if your versions are higher, you'll probably require a newer SDK, otherwise maybe an older one.
 Use xactxtract to retrieve cue names and assignment to wavs from the original .xsb, if possible.
With these informations, create your xsb/xwb using XACT.
Backup & replace the original xsb/xwb files with your own and try if the game works with it.

Some more info is [here](https://forum.xentax.com/viewtopic.php?f=17&t=4391&start=15#p43840), [here ](https://forum.xentax.com/viewtopic.php?f=17&t=14198) and [here](https://forum.xentax.com/viewtopic.php?f=17&t=5486).
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-04-23T14:04:30+00:00
- Post Title: Bully - How do I convert .wav files to .xwb and .xsb?

Update on the topic:

More detailed instruction has been shared here [viewtopic.php?p=183974#p183974](https://forum.xentax.com/viewtopic.php?p=183974#p183974)

More info on the XWB/XSB file formats is in this article [http://wiki.xentax.com/index.php/XACT_XWB_XSB_XGS_Audio](http://wiki.xentax.com/index.php/XACT_XWB_XSB_XGS_Audio)
