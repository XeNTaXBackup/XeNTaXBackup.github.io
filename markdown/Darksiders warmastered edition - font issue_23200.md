## Post #1
- Username: mx202
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Dec 19, 2020 2:22 am
- Post datetime: 2020-12-20T20:44:49+00:00
- Post Title: Darksiders warmastered edition - font issue

Hello All

I was able to extract the English test file from the game files using Darksiders Warmastered MNFST Tool. But when I tried to unpack (ui_en.oppc) using Offzip(latest version) I got an empty file. Also, I would like to change the font of all the texts.
A screenshot in the attachments.

My game downloaded from Steam and my target language is Arabic.

I hope you help me guys with instructions and what to do first and what to do the last.

Thanks
[Capture.PNG](https://xentaxbackup.github.io/file/19214_Capture.PNG)
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-12-20T22:36:04+00:00
- Post Title: Darksiders warmastered edition - font issue

Can you upload somewhere "ui_en.oppc" file for analysis?
## Post #3
- Username: mx202
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Dec 19, 2020 2:22 am
- Post datetime: 2020-12-21T15:28:43+00:00
- Post Title: Darksiders warmastered edition - font issue

Thanks for replying.

You can download the file from [https://mega.nz/file/S1kEARhD#oLw1WV-dq ... qE7lDJD6bc](https://mega.nz/file/S1kEARhD#oLw1WV-dqFX_pLqJv751A9SmULNjF-cnaqE7lDJD6bc)

Thanks again dude.
## Post #4
- Username: ramyzahran
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-12-21T16:29:37+00:00
- Post Title: Darksiders warmastered edition - font issue

You can use this script [https://aluigi.altervista.org/bms/darksiders.bms](https://aluigi.altervista.org/bms/darksiders.bms)
with quickbms [https://aluigi.altervista.org/quickbms.htm](https://aluigi.altervista.org/quickbms.htm)
to unpack data.

[https://imgur.com/a/RwPGfEj](https://imgur.com/a/RwPGfEj)
[https://imgur.com/a/vEywrms](https://imgur.com/a/vEywrms)
## Post #5
- Username: mx202
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Dec 19, 2020 2:22 am
- Post datetime: 2020-12-21T17:49:19+00:00
- Post Title: Darksiders warmastered edition - font issue

Thanks a lot, dude.

Thant's was really helpful.

When I used my Arabic subtitle and launched the game, all the letters appeared wrongly with squares instead of real letters.


Now, I just need to use an Arabic font instead of the English font.

Please let me know how to do it to finish translating this version and Darksiders Deathinitive Edition as well.

The Arabic font can be downloaded from this link [https://mega.nz/file/CpsSFbgJ#ujVvcK6NX ... hjYyRTNMig](https://mega.nz/file/CpsSFbgJ#ujVvcK6NXeUbSUD97Uduq2ntkCPUVH13BhjYyRTNMig).
## Post #6
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-12-22T10:33:58+00:00
- Post Title: Darksiders warmastered edition - font issue

It's not that easy. You can't just use TTF font here.

You need to edit DDS font file first.
You could probably use for this GIMP or Photoshop with DDS plugin
You can easily view the image in XnView [https://imgur.com/a/vyy7mrz](https://imgur.com/a/vyy7mrz)

As for coordinates, I'm not really sure, but here are some values in GFX file.
You could use jpexs-decompiler to edit this file [https://imgur.com/a/pxY7UzO](https://imgur.com/a/pxY7UzO)
[https://github.com/jindrapetrik/jpexs-d ... sion11.3.0](https://github.com/jindrapetrik/jpexs-decompiler/releases/tag/version11.3.0)
If not here, then you should look for coordinates in other game files
or just replace existing characters in DDS texture.
## Post #7
- Username: mx202
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Dec 19, 2020 2:22 am
- Post datetime: 2020-12-23T21:10:36+00:00
- Post Title: Darksiders warmastered edition - font issue

Hey ikskoks,

Thank you a lot for explaining, Now I understand most of the idea.

Is it enough to edit the DDS file and add Arabic glyphs?

Is it that simple, or there are more things to consider?

Thanks.
## Post #8
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-12-23T23:44:02+00:00
- Post Title: Darksiders warmastered edition - font issue

Editing DDS solves the issue with font, but to make it work you have to also change the texts.

For example if you replace "Â" character with some arabic one,
you have to use Â in text instead of arabic letter to make it appear.
Of course you don't need to do it while translating, 
you can replace all characters at once using Notepad++ 
or tool like this [https://github.com/bartlomiejduda/Tools ... LACER_2.py](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/REGULAR_CHAR_REPLACER_2.py)
## Post #9
- Username: mx202
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Dec 19, 2020 2:22 am
- Post datetime: 2020-12-24T18:31:07+00:00
- Post Title: Darksiders warmastered edition - font issue

Thank you ikskoks,

You were a great help.
## Post #10
- Username: mx202
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Dec 19, 2020 2:22 am
- Post datetime: 2020-12-29T23:18:53+00:00
- Post Title: Darksiders warmastered edition - font issue

On this beautiful day,

I announce that I was defeated and couldn't modify the font file.
I raise the white flag. I give up.
## Post #11
- Username: ramyzahran
- Rank: n00b
- Number of posts: 19
- Joined date: Tue May 23, 2017 7:41 am
- Post datetime: 2021-09-12T16:46:40+00:00
- Post Title: Darksiders warmastered edition - font issue

> Reply from ikskoks ↑Tue Dec 22, 2020 12:29 am at Tue Dec 22, 2020 12:29 am
>
> 
You can use this script https://aluigi.altervista.org/bms/darksiders.bms
with quickbms https://aluigi.altervista.org/quickbms.htm
to unpack data.

https://imgur.com/a/RwPGfEj
https://imgur.com/a/vEywrms

and how can i repack the font after editing it ?
how to repack dds font into the file ui_en.oppc?

is there a tool for unpacking and repacking the font file ui_en.oppc?
## Post #12
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-09-12T18:19:08+00:00
- Post Title: Darksiders warmastered edition - font issue

Quickbms has a reimport mode which can be used for packing data.
Read more about it here [http://aluigi.zenhax.com/papers/quickbms.txt](http://aluigi.zenhax.com/papers/quickbms.txt)
## Post #13
- Username: ramyzahran
- Rank: n00b
- Number of posts: 19
- Joined date: Tue May 23, 2017 7:41 am
- Post datetime: 2021-09-12T22:51:20+00:00
- Post Title: Darksiders warmastered edition - font issue

> Reply from ikskoks ↑Mon Sep 13, 2021 2:19 am at Mon Sep 13, 2021 2:19 am
>
> 
Quickbms has a reimport mode which can be used for packing data.
Read more about it here http://aluigi.zenhax.com/papers/quickbms.txt

i tried to do the re-import but i failed, i don't understand what's wrong !!!
can you make tutorial steps to do this??
i want to unpack & edit & repack this font file:
[ui_en.zip](https://xentaxbackup.github.io/file/20784_ui_en.zip)
## Post #14
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-09-13T06:26:16+00:00
- Post Title: Darksiders warmastered edition - font issue

No, sorry. If you want to learn more about quickbms, you can check this link
[viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)

There are also plenty of tutorials on youtube
[https://www.google.com/search?client=fi ... t+tutorial](https://www.google.com/search?client=firefox-b-d&q=quickbms+reimport+tutorial)
