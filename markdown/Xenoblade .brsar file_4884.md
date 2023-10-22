## Post #1
- Username: Romored
- Rank: beginner
- Number of posts: 20
- Joined date: Fri May 14, 2010 7:52 pm
- Post datetime: 2010-08-14T11:41:14+00:00
- Post Title: Xenoblade .brsar file

Using Falo's scripts, I succesfully managed to extract the audio files from "snd.pkb", in Xenoblade game disc.
But now there's something wrong. The files I extract with quickbms have .dat extention, but looking into them with an hex editor, they look like some kind of .brsar files. I tried to extract them using brsar_unpack.exe, and even if it recognises the number of sounds contained into each file (information contained into the header, though), it just skips every entry and doesn't extract nothing. I tried using VGMToolbox, too, but to no avail. I read somewhere that brsar_unpack can't extract Stereo WAVs, but I can't believe that ALL sounds of that game are in stereo!!! I tried with every file, but the result was always the same.
I attach one of the files, so maybe you can find a solution. The problem is probably that the sounds contained are in a different format than older .brsar files. Some of the headers I can locate are RSEQ, RWAR and RWAV.
[66.7z](https://xentaxbackup.github.io/file/3327_66.7z)
## Post #2
- Username: Romored
- Rank: beginner
- Number of posts: 20
- Joined date: Fri May 14, 2010 7:52 pm
- Post datetime: 2010-09-13T07:33:00+00:00
- Post Title: Xenoblade .brsar file

I solved by opening the files with VGMToolbox: it extracts .rwav files that are perfectly readable with vgmstream. They can also be converted with Winamp, if you have the right plug-in.
## Post #3
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2012-12-27T15:33:54+00:00
- Post Title: Xenoblade .brsar file

i extract file but where the plugin you talking about this
## Post #4
- Username: iamatmylimit
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Jan 30, 2011 3:35 pm
- Post datetime: 2012-12-27T21:36:07+00:00
- Post Title: Xenoblade .brsar file

you dont need the plugin for winamp if you have VGMToolbox.since you cant find the plugin(for winamp) id suggest you use VGMToolbox.Better to get 1 program instead of looking for 2.
## Post #5
- Username: hshadow
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 21, 2014 11:27 am
- Post datetime: 2014-08-21T03:34:52+00:00
- Post Title: Xenoblade .brsar file

Hi. I know this is an old post but is the only lead I found. Do any of you still have the VGMToolbox aorund there? I tried to download it, several versions of the ones on SourceForge but they won't work. 7-zip just keep throwing up the error "cannot open file as archive". I just want the sounds from Xenoblade Chronicles. Thanks.
