## Post #1
- Username: Reaper00
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 30, 2016 8:11 am
- Post datetime: 2016-04-30T00:31:41+00:00
- Post Title: How to extract Rumble roses XX models & Animations?

Hello, I'm new to this site and to ripping and modding 3D models, I wanted to ask how would I go about extracting the Rumble Roses XX models and animations that are in the game itself if possible. I've researched through this site and youtube, from what I've found I need a modded Xbox 360 console and a way to transfer files into my PC for modding with a software like 3DS Max. Is this true? If so, are the animations extracted in same way? 

Thanks for any and all replies
## Post #2
- Username: dick12121
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jun 26, 2012 10:18 pm
- Post datetime: 2016-04-30T12:22:58+00:00
- Post Title: How to extract Rumble roses XX models & Animations?

> how would I go about extracting the Rumble Roses XX models

Hi, first you need to unpack the iso file. You should get several *.pac files.

  -- /pac/ch/*.pac => has default models of each character.
  -- /pac/ed/*.pac => has common swimsuits.

Use QuickBMS and the attached bms script to extract files from *.pac files.
[http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)

About File formats:

  -- PAC file has consecutive PACH files.
  -- PACH file has consecutive raw files such as YOBJ (model), TEX (includes DDS textures) and so on.

After you got raw files, checkout Mr. Mario's video. [https://youtu.be/P9Y-OaOqpxg](https://youtu.be/P9Y-OaOqpxg)
His maxscript allows you to import models into 3ds Max, trial version is fine.

> are the animations extracted in same way?

I haven't seen anyone does it.
[rrxx.zip](https://xentaxbackup.github.io/file/10857_rrxx.zip)
## Post #3
- Username: bootht
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 01, 2020 11:17 pm
- Post datetime: 2020-07-01T16:56:27+00:00
- Post Title: How to extract Rumble roses XX models & Animations?

> Reply from dick12121 ↑Sat Apr 30, 2016 8:22 pm at Sat Apr 30, 2016 8:22 pm
>
> 
> how would I go about extracting the Rumble Roses XX models

Hi, first you need to unpack the iso file. You should get several *.pac files.

  -- /pac/ch/*.pac => has default models of each character.
  -- /pac/ed/*.pac => has common swimsuits.

Use QuickBMS and the attached bms script to extract files from *.pac files.
http://aluigi.altervista.org/quickbms.htm

About File formats:

  -- PAC file has consecutive PACH files.
  -- PACH file has consecutive raw files such as YOBJ (model), TEX (includes DDS textures) and so on.

After you got raw files, checkout Mr. Mario's video. https://youtu.be/P9Y-OaOqpxg
His maxscript allows you to import models into 3ds Max, trial version is fine.

> are the animations extracted in same way?

I haven't seen anyone does it.

I'm so sorry disturbing you now....
The QuickBMS with that BMS dosen't works for the "sound.pac"
Is there anyway which could resolve this?
## Post #4
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-07-05T07:30:06+00:00
- Post Title: How to extract Rumble roses XX models & Animations?

Do anyone have Rumble Roses XX iso.
