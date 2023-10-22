## Post #1
- Username: ScientistVasiliy
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Oct 18, 2020 2:29 am
- Post datetime: 2020-11-23T20:52:55+00:00
- Post Title: Valkyria Chronicles 2 fonts

Hello, i again need help with Valkyria Chronicles 2. I need to open fonts file ODIN_FONT_16.BF1 and edit it, but i just don't know how to do it. 
The header is: 
53 46 4E 54 E0 9E 03 00 60 00 00 00 00 00 00 10 00 00 00 00 E0 9E 03 00 00 C0 00 00 00 00 00 00 05 00 00 00 2C 00 00 00 40 00 00 00 60 00 00 00 80 18 00 00 A0 8C 03 00 C0 9C 03 00 D0 9E 03 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 4D 46 4E 54 00 18 00 00 20 00 00 00 00 00 00 00 (SFNTаћ..`...........аћ...А..........,...@...`...Ђ... Њ..Ањ..Рћ..................................MFNT.... .......). 
I tryed to find any information about SFNT or MFNT formats, but nothing usefull. Maybe someone here can help with it?
[ODIN_FONT_16.zip](https://xentaxbackup.github.io/file/19072_ODIN_FONT_16.zip)
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-11-23T23:44:16+00:00
- Post Title: Valkyria Chronicles 2 fonts

You can read some documentation here [http://wiki.xentax.com/index.php/Valkyr ... cles_2_BF1](http://wiki.xentax.com/index.php/Valkyria_Chronicles_2_BF1)
Currently there are many unknown chunks, so editing is not possible.
## Post #3
- Username: ScientistVasiliy
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Oct 18, 2020 2:29 am
- Post datetime: 2020-11-24T06:13:39+00:00
- Post Title: Valkyria Chronicles 2 fonts

> Reply from ikskoks ↑Tue Nov 24, 2020 7:44 am at Tue Nov 24, 2020 7:44 am
>
> 
You can read some documentation here http://wiki.xentax.com/index.php/Valkyr ... cles_2_BF1
Currently there are many unknown chunks, so editing is not possible.
Thanks, but how you and said, with this not big information editing is impossible. Even extraction, i tryed bmds script form ZenHex, but it just making from one BF1 file another 5 files: 3 MFNT files, 1 MFGT and 1 HFPR, which are just divided BF1 file.
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-11-24T22:15:40+00:00
- Post Title: Valkyria Chronicles 2 fonts

I was able to extract image data using raw texture cooker [https://i.imgur.com/4J1aX4R.png](https://i.imgur.com/4J1aX4R.png)
It seems that MFNT chunk contains r1_unom graphics.
## Post #5
- Username: ScientistVasiliy
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Oct 18, 2020 2:29 am
- Post datetime: 2020-11-25T11:38:27+00:00
- Post Title: Valkyria Chronicles 2 fonts

> Reply from ikskoks ↑Wed Nov 25, 2020 6:15 am at Wed Nov 25, 2020 6:15 am
>
> 
I was able to extract image data using raw texture cooker https://i.imgur.com/4J1aX4R.png
It seems that MFNT chunk contains r1_unom graphics.
I downloaded this programm and set the same settings like on your screenshot, but it's just not showing picture. If i am pressing button "try and convert" it's really converting file to .dds, but there are no fonts, only some trash. 
What can be the problem?
## Post #6
- Username: ScientistVasiliy
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-11-25T16:27:58+00:00
- Post Title: Valkyria Chronicles 2 fonts

I have answered by Facebook, but I'll leave here solution for others:

You need to download TexConv [https://github.com/Microsoft/DirectXTex/wiki/Texconv](https://github.com/Microsoft/DirectXTex/wiki/Texconv)
and put it in Rawtex's directory.
