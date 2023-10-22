## Post #1
- Username: LukeAndBobPro
- Rank: beginner
- Number of posts: 30
- Joined date: Fri Jun 04, 2021 3:54 am
- Post datetime: 2021-11-28T20:09:43+00:00
- Post Title: Bus Derby (iOS) - tibberojVER .obj file

Greetings, my fellow XeNTaX users!
it's Luke here back with yet another one of those "Un-accessible" file formats!
this one is called the ".OBJ" format. and no, I'm not talking about the "Wavefront" .obj format, I'm talking about the tibberojVER .obj format. 
which serves as the main 3D model format in Dimension Technic's most popular iOS racing game "Bus Derby".
or Bus Derby: The Original for some people. and yes, it is accessible, but the problem is is that when I load it up, it shows nothing.
and yes, I've tried to use hexeditor on it, but it's very impossible to use because the tutorial doesn't properly explain the program's functions to me.
at least in my opinion. if someone could at least give me some advice on what to do with this format, that would be great.
here's the format if you need it.


 Zip.zip
(75.74 KiB) Downloaded 17 times
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-28T23:04:55+00:00
- Post Title: Bus Derby (iOS) - tibberojVER .obj file

> Reply from LukeAndBobPro ↑Mon Nov 29, 2021 4:09 am at Mon Nov 29, 2021 4:09 am
>
> I've tried to use hexeditor on it, but it's very impossible to use because the tutorial doesn't properly explain the program's functions to me.Which tutorial are you talking about? A hexeditor usually is for displaying/editing hex data (as the name states), not for showing 3D models.

Using hex2obj (view link in my sig):
.



BusDerby-red_1.png (86.63 KiB) Viewed 228 times

(Checked one sub mesh only.)
## Post #3
- Username: LukeAndBobPro
- Rank: beginner
- Number of posts: 30
- Joined date: Fri Jun 04, 2021 3:54 am
- Post datetime: 2021-11-29T14:42:33+00:00
- Post Title: Bus Derby (iOS) - tibberojVER .obj file

1st of all: Don't play "Stupid" with me! [NO OFFENSE OR PUN INTENDED]

2nd of all: I meant to say "hex2obj" instead of "hexeditor"!

and 3rd: HOW COME IT WORKS FOR YOU AND NOT ME!?!
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-29T15:50:08+00:00
- Post Title: Bus Derby (iOS) - tibberojVER .obj file

> Reply from LukeAndBobPro ↑Mon Nov 29, 2021 10:42 pm at Mon Nov 29, 2021 10:42 pm
>
> 
1st of all: Don't play "Stupid" with me! [NO OFFENSE OR PUN INTENDED]Calm down - I don't need to help you. So.
## Post #5
- Username: LukeAndBobPro
- Rank: beginner
- Number of posts: 30
- Joined date: Fri Jun 04, 2021 3:54 am
- Post datetime: 2021-11-29T17:53:16+00:00
- Post Title: Bus Derby (iOS) - tibberojVER .obj file

Shako, wait!
I didn't mean to say that!
please come back!
## Post #6
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2021-12-01T19:17:29+00:00
- Post Title: Bus Derby (iOS) - tibberojVER .obj file

> Reply from LukeAndBobPro ↑Mon Nov 29, 2021 4:09 am at Mon Nov 29, 2021 4:09 am
>
> 
I'm talking about the tibberojVER .obj format.

The red_1.obj file has references to the external textures files:
   red_lampak_color.png  (it is OK, because you sent me this file)
   red_color.tga  (??, because you sent me the red_body_color.png file)

Do you have the red_color.tga file?
## Post #7
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2021-12-02T19:59:23+00:00
- Post Title: Bus Derby (iOS) - tibberojVER .obj file

I have finished my Bus Derby *.OBJ loader module and I have released the following programs as web updates:

- 3D Object Converter v8.019	(Windows)
- i3DConverter v4.107		(macOS)
- i3DConverter v2.107		(Linux)

How to get the 3D Object Converter v8.019:
Download the 3D Object Converter from [ http://3doc.i3dconverter.com](http://3doc.i3dconverter.com) and install it or download and use the portable version.
After it just use the Help/Check for updates... function to get the v8.019.

How to get the i3DConverter macOS v4.107:
Download the i3DConverter from [ http://www.i3dconverter.com](http://www.i3dconverter.com) and install it.
After it just use the Help/Check for updates... function to get the v4.107.

How to get the i3DConverter Linux v2.107:
Download the i3DConverter from [ http://www.i3dconverter.com](http://www.i3dconverter.com) and install it.
After it just use the Help/Check for updates... function to get the v2.107.
## Post #8
- Username: LukeAndBobPro
- Rank: beginner
- Number of posts: 30
- Joined date: Fri Jun 04, 2021 3:54 am
- Post datetime: 2022-03-24T16:23:54+00:00
- Post Title: Bus Derby (iOS) - tibberojVER .obj file

I know this is hard-to-solve question, but how in the world do I get the texture files from these "DTI" files?


 TextureFiles.zip
(14.21 KiB) Downloaded 14 times
## Post #9
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-03-24T17:26:06+00:00
- Post Title: Bus Derby (iOS) - tibberojVER .obj file

@LukeAndBobPro : It's a container for jpeg (rgb data) and zlib compressed data (raw alpha channel). You can use attached script to extract both from such containers. Though in both provided samples alpha data can be ignored, apparently.

Update: Updated script is now converting raw data to respective dds files. It can now handle different dti format as well.



 dti_textures_extract_v2.zip
(771 Bytes) Downloaded 12 times
## Post #10
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-03-24T20:32:18+00:00
- Post Title: Bus Derby (iOS) - tibberojVER .obj file

[fmt_tibberojVER.zip](https://xentaxbackup.github.io/file/22007_fmt_tibberojVER.zip)
## Post #11
- Username: LukeAndBobPro
- Rank: beginner
- Number of posts: 30
- Joined date: Fri Jun 04, 2021 3:54 am
- Post datetime: 2022-03-25T13:41:01+00:00
- Post Title: Bus Derby (iOS) - tibberojVER .obj file

Well, that was quick.
Thanks! I guess?
## Post #12
- Username: LukeAndBobPro
- Rank: beginner
- Number of posts: 30
- Joined date: Fri Jun 04, 2021 3:54 am
- Post datetime: 2022-03-25T15:07:43+00:00
- Post Title: Bus Derby (iOS) - tibberojVER .obj file

> Reply from Durik256 ↑Fri Mar 25, 2022 4:32 am at Fri Mar 25, 2022 4:32 am
>
>  Look, I appreciate you trying to help, but I've already found a solution on how to import the files already.
## Post #13
- Username: LukeAndBobPro
- Rank: beginner
- Number of posts: 30
- Joined date: Fri Jun 04, 2021 3:54 am
- Post datetime: 2022-03-25T15:08:33+00:00
- Post Title: Bus Derby (iOS) - tibberojVER .obj file

> Reply from Spiritovod ↑Fri Mar 25, 2022 1:26 am at Fri Mar 25, 2022 1:26 am
>
> 
@LukeAndBobPro : It's a container for jpeg (rgb data) and zlib compressed data (raw alpha channel). You can use attached script to extract both from such containers. Though in both provided samples alpha data can be ignored, apparently.


dti_textures_extract.zip it works perfectly, thanks!
## Post #14
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-03-25T15:15:51+00:00
- Post Title: Bus Derby (iOS) - tibberojVER .obj file

> Reply from LukeAndBobPro ↑Fri Mar 25, 2022 11:07 pm at Fri Mar 25, 2022 11:07 pm
>
> 
but I've already found a solution on how to import the files already.
you're not alone... maybe someone needs it too.
## Post #15
- Username: LukeAndBobPro
- Rank: beginner
- Number of posts: 30
- Joined date: Fri Jun 04, 2021 3:54 am
- Post datetime: 2022-03-25T16:24:11+00:00
- Post Title: Bus Derby (iOS) - tibberojVER .obj file

I understand that, Durik256.
it's fine if you keep it here just incase somebody needs it.
## Post #16
- Username: LukeAndBobPro
- Rank: beginner
- Number of posts: 30
- Joined date: Fri Jun 04, 2021 3:54 am
- Post datetime: 2022-04-03T17:10:29+00:00
- Post Title: Re: Bus Derby (iOS) - tibberojVER .obj file

Hello again, Spiritovod.
Your script works well, but doesn't work with the last 19 files I have right here in this link.
[https://drive.google.com/file/d/1KmxrDd ... x_cL0/view](https://drive.google.com/file/d/1KmxrDdcvR-E2IJOoiEiBCtxNj2Lx_cL0/view)
## Post #17
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-04-03T20:05:13+00:00
- Post Title: Re: Bus Derby (iOS) - tibberojVER .obj file

@LukeAndBobPro: I've update the script in the same post, it can now handle different dti format from provided samples and also converts raw data to respective dds files.
