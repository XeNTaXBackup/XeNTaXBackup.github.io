## Post #1
- Username: ghf50
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Feb 04, 2011 10:47 pm
- Post datetime: 2013-03-26T15:19:09+00:00
- Post Title: Resident Evil 6 [Reloaded] setup.exe 's music

Any one have any ideas about how rip music from this setup.exe 
I'v used PE tool to dump full of this exe file and view it use resource viewer, but no luck.
I can't find any module like 'xm' or 'it'.

Any one have any ideas?
sorry for my poor english
## Post #2
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-05-04T01:58:17+00:00
- Post Title: Resident Evil 6 [Reloaded] setup.exe 's music

> Reply from ghf50
>
>  Any one have any ideas about how rip music from this setup.exe 
I'v used PE tool to dump full of this exe file and view it use resource viewer, but no luck.
I can't find any module like 'xm' or 'it'.

Any one have any ideas?
sorry for my poor english
Most likely because RELOADED obfuscates their code
## Post #3
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-05-04T16:29:50+00:00
- Post Title: Resident Evil 6 [Reloaded] setup.exe 's music

They used Inno Setup for the installation, so you can use [Inno Setup Unpacker](http://sourceforge.net/projects/innounp/) (and better use  that GUI which you can find on Download page) and retrieve that music that way.
And it's .mp3 file located in {tmp} folder
