## Post #1
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2014-12-05T22:10:34+00:00
- Post Title: Final fantasy XIII PC wmp video format

Hi, i tried to convert this wmp format to common video format, since i read somewhere it is actually a *.bik format. So then i change the extension to *.bik and I try demux it using radgametools and vgmtoolbox but got no luck. So i hope someone here can help me to  solve this format. here's the smallest sample that i can provide:

[https://mega.co.nz/#!dFsAETrL!iOR1-Nzf7 ... ylKbOS54XA](https://mega.co.nz/#!dFsAETrL!iOR1-Nzf7LybvGVz2bx79b8cHxhZ4qp30ylKbOS54XA)

Thanks for your attention
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-12-06T12:39:31+00:00
- Post Title: Final fantasy XIII PC wmp video format

Yes, you are right. It's Bink2 format and you can convert it with Rad Video Tools into .AVI container.
## Post #3
- Username: jadentheman
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Oct 24, 2014 7:21 am
- Post datetime: 2014-12-06T16:58:48+00:00
- Post Title: Final fantasy XIII PC wmp video format

My post from the other thread

> Reply from jadentheman
>
> Regarding videos someone from Gamefaqs found the offsets to replace the pre-rendered scenes on PC.


http://www.gamefaqs.com/boards/846192-f ... i/70394566

Only issue is the PC version can't read H.264 files and only Bink 1 & 2. this is because it's using the Bink library for reading videos files. I really wish square used libavcodec or any open source mp4 library, but whatever we can mod I guess.

If someone could theoretically get libavcodec libraries to run alongside this game I bet we can use the PS3 files directly since libavcodec can read both h.264 and aa3 encoded video/audio respectively (well not directly still got to put it in mp4 container )

Is it possible to take libavcodec and make FF13 use it to read h264 videos of PS3 version?
## Post #4
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2014-12-06T19:23:35+00:00
- Post Title: Final fantasy XIII PC wmp video format

> Reply from merlinsvk
>
> Yes, you are right. It's Bink2 format and you can convert it with Rad Video Tools into .AVI container.

Sorry,but i always got "error opening .bk2 file" when opening it with Rad Video Tools.Since its bik2 format, i assume that the extension is *.bk2 not *.bik, thats how i rename the wmp files.Did i do something wrong here?or i must hex editing the bytes so it will "readable" on Rad Video Tools?
## Post #5
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-12-06T19:55:28+00:00
- Post Title: Final fantasy XIII PC wmp video format

> Reply from aagems
>
> or i must hex editing the bytes so it will "readable" on Rad Video Tools?

Exactly. Remove first 16 bytes. Bink2 video starts with "KB2" mark.
## Post #6
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2014-12-06T20:20:53+00:00
- Post Title: Final fantasy XIII PC wmp video format

Ok,thanks for your help.Work flawlessly
## Post #7
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2014-12-06T20:42:02+00:00
- Post Title: Final fantasy XIII PC wmp video format

Sorry,got problem again.The files play directly by double click it,but if i open it with rad video tools,it give me an "error opening files" and converting it also give me the same error.Here's a screenshot from sample files that i upload in hex editor after deleting first 16 bytes



This is before deleting the 16 first bytes



anything wrong??
## Post #8
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-12-06T21:39:02+00:00
- Post Title: Final fantasy XIII PC wmp video format

I don't know, it works for me.
## Post #9
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2014-12-07T10:45:49+00:00
- Post Title: Final fantasy XIII PC wmp video format

This is weird, i have similar version rad video tools like you.But i cant get it to work.Do you install k-lite codec pack or quick time?i have it on my pc. Do you mind to explain step by step how you work on those sample till converting it to avi. Maybe i miss something?
## Post #10
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-12-07T12:03:14+00:00
- Post Title: Final fantasy XIII PC wmp video format

I have only AAC and AC3 codecs installed. Nothing else. Actually there is no "work". Open .wmp, delete first 16 bytes, save as .bk2. That's all.
Do you have latest Rad Video Tools?
## Post #11
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2014-12-07T14:09:46+00:00
- Post Title: Final fantasy XIII PC wmp video format

Ok,thank you very much. It works now   I'm doing something wrong in saving the file in hex editor,thats why it doesnt work when converting using Rad Video Tools
## Post #12
- Username: blade22
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Sep 07, 2016 3:07 am
- Post datetime: 2016-09-06T19:10:34+00:00
- Post Title: Final fantasy XIII PC wmp video format

Ok..so I installed the PC version and want to extract the video and audio to convert it in media player format but don't have much idea.

> Reply from aagems
>
> Ok,thank you very much. It works now   I'm doing something wrong in saving the file in hex editor,thats why it doesnt work when converting using Rad Video Tools
I am also getting the same error after saving the file in Hex editor..what you did to make it work ?
