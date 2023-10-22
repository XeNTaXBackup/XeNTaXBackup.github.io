## Post #1
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2022-02-25T03:17:11+00:00
- Post Title: [PC] Elden Ring (.BDT / .BHD)

Hi everyone

Elden Ring is finally out but it looks like FromSoftware has changed up the game archives a bit from Dark Souls.

The game uses Kraken compression from what I can find.

[Here is 100MB of each primary data archive as well as the full header file.](https://mega.nz/folder/yc00XLTK#hnL208xpJD-mBuiGburGDQ)

Hopefully someone can make a working BMS script to extract these.

Thanks
## Post #2
- Username: dddwa
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Feb 02, 2022 10:06 am
- Post datetime: 2022-02-25T04:09:48+00:00
- Post Title: [PC] Elden Ring (.BDT / .BHD)

> Reply from brendan19 ↑Fri Feb 25, 2022 11:17 am at Fri Feb 25, 2022 11:17 am
>
> 
Hi everyone

Elden Ring is finally out but it looks like FromSoftware has changed up the game archives a bit from Dark Souls.

The game uses Kraken compression from what I can find.

Here is 100MB of each primary data archive as well as the full header file.

Hopefully someone can make a working BMS script to extract these.

Thanks

have you tried this? [viewtopic.php?t=14223](https://forum.xentax.com/viewtopic.php?t=14223)
## Post #3
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2022-02-25T05:35:28+00:00
- Post Title: [PC] Elden Ring (.BDT / .BHD)

@dddwa
I did try BinderTool but I think the RSA keys need to be changed for it work.

I've also now uploaded the game's executable file as well if anyone wants it
## Post #4
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2022-02-27T14:52:48+00:00
- Post Title: [PC] Elden Ring (.BDT / .BHD)

Hi, dudes!
Any progress with Elden ring unpacking?
## Post #5
- Username: michanlew
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Apr 29, 2012 8:21 am
- Post datetime: 2022-03-04T08:39:42+00:00
- Post Title: [PC] Elden Ring (.BDT / .BHD)

> Reply from TokiChan ↑Sun Feb 27, 2022 10:52 pm at Sun Feb 27, 2022 10:52 pm
>
> 
Hi, dudes!
Any progress with Elden ring unpacking?

Есть инструмент UXM доступен тут [https://discord.com/channels/5298028282 ... 1998149643](https://discord.com/channels/529802828278005773/529900741998149643)
## Post #6
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2022-03-04T10:04:15+00:00
- Post Title: [PC] Elden Ring (.BDT / .BHD)

> Reply from michanlew ↑Fri Mar 04, 2022 4:39 pm at Fri Mar 04, 2022 4:39 pm
>
> 
TokiChan wrote: ↑Sun Feb 27, 2022 10:52 pm
Hi, dudes!
Any progress with Elden ring unpacking?


Есть инструмент UXM доступен тут https://discord.com/channels/5298028282 ... 1998149643

Translation "There is a UXM tool available here".

Please post that tool as an attachment, as we cannot see the channel or server you are linking to, without already being in it.
## Post #7
- Username: kzoacn
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 04, 2022 9:57 pm
- Post datetime: 2022-03-04T13:59:02+00:00
- Post Title: [PC] Elden Ring (.BDT / .BHD)

Someone post the RSA keys in the issue forum of BinderTool [https://github.com/Atvaark/BinderTool/issues/44](https://github.com/Atvaark/BinderTool/issues/44)

However, it seems From software slightly changed its BHD5 format.
## Post #8
- Username: Klaus
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Mar 01, 2016 5:59 am
- Post datetime: 2022-03-04T14:07:47+00:00
- Post Title: [PC] Elden Ring (.BDT / .BHD)

> Reply from 09williamsad ↑Fri Mar 04, 2022 6:04 pm at Fri Mar 04, 2022 6:04 pm
>
> 
michanlew wrote: ↑Fri Mar 04, 2022 4:39 pm
TokiChan wrote: ↑Sun Feb 27, 2022 10:52 pm
Hi, dudes!
Any progress with Elden ring unpacking?


Есть инструмент UXM доступен тут https://discord.com/channels/5298028282 ... 1998149643


Translation "There is a UXM tool available here".

Please post that tool as an attachment, as we cannot see the channel or server you are linking to, without already being in it.

It's intended for a steam version of the game, and not working for every file yet.
## Post #9
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2022-03-04T20:13:06+00:00
- Post Title: [PC] Elden Ring (.BDT / .BHD)

Ekey made an unpacker [https://github.com/Ekey/ER.BDT.Tool/releases](https://github.com/Ekey/ER.BDT.Tool/releases)
## Post #10
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2022-03-05T21:26:27+00:00
- Post Title: [PC] Elden Ring (.BDT / .BHD)

> Reply from 09williamsad ↑Sat Mar 05, 2022 4:13 am at Sat Mar 05, 2022 4:13 am
>
> 
Ekey made an unpacker https://github.com/Ekey/ER.BDT.Tool/releases

This tool is not working properly...

As requested in the description, even if I specify the path of the file, the tool does not properly recognize 'oo2core_6_win64.dll'. The same error message appears when I copy 'oo2core_6_win64.dll' in the game folder and paste it into the folder where the tool is located. 

Specific 'oo2core_6_win64.dll' file recognized by this tool should be attached along with this tool.
## Post #11
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2022-03-05T21:28:12+00:00
- Post Title: [PC] Elden Ring (.BDT / .BHD)

> Reply from uroborostestsubject ↑Sun Mar 06, 2022 5:26 am at Sun Mar 06, 2022 5:26 am
>
> 
This tool is not working properly...
As requested in the description, even if I specify the path of the file, the tool does not properly recognize 'oo2core_6_win64.dll'. The same error message appears when I copy 'oo2core_6_win64.dll' in the game folder and paste it into the folder where the tool is located. 
Specific 'oo2core_6_win64.dll' file recognized by this tool should be attached along with this tool.
It worked fine when I tried it with the dll from Elden Ring.
It could be your antivirus blocking it, or something like that.
## Post #12
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2022-03-05T21:31:45+00:00
- Post Title: [PC] Elden Ring (.BDT / .BHD)

> Reply from 09williamsad ↑Sun Mar 06, 2022 5:28 am at Sun Mar 06, 2022 5:28 am
>
> 
uroborostestsubject wrote: ↑Sun Mar 06, 2022 5:26 am
This tool is not working properly...
As requested in the description, even if I specify the path of the file, the tool does not properly recognize 'oo2core_6_win64.dll'. The same error message appears when I copy 'oo2core_6_win64.dll' in the game folder and paste it into the folder where the tool is located. 
Specific 'oo2core_6_win64.dll' file recognized by this tool should be attached along with this tool.

It worked fine when I tried it with the dll from Elden Ring.
It could be your antivirus blocking it, or something like that.

Nah... This is the tool's own message. I ran this tool with all the vaccines off. Nevertheless, this tool is sending me a message that it does not recognize 'oo2core_6_win64.dll' file. Perhaps your 'oo2core_6_win64.dll' file is consistent with what the tool requires.
## Post #13
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2022-03-05T21:37:26+00:00
- Post Title: [PC] Elden Ring (.BDT / .BHD)

> Reply from uroborostestsubject ↑Sun Mar 06, 2022 5:31 am at Sun Mar 06, 2022 5:31 am
>
> 
Nah... This is the tool's own message. I ran this tool with all the vaccines off. Nevertheless, this tool is sending me a message that it does not recognize 'oo2core_6_win64.dll' file. Perhaps your 'oo2core_6_win64.dll' file is consistent with what the tool requires.
DLL i used from the game files [https://mega.nz/file/LCAjwKxT#8McgPq0VO ... HDxSqtibx4](https://mega.nz/file/LCAjwKxT#8McgPq0VOjAC0MVlfq10upKTTNcfIEl6YHDxSqtibx4)
Would not attach as a zip.
## Post #14
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2022-03-05T21:39:32+00:00
- Post Title: [PC] Elden Ring (.BDT / .BHD)

> Reply from 09williamsad ↑Sun Mar 06, 2022 5:37 am at Sun Mar 06, 2022 5:37 am
>
> 
uroborostestsubject wrote: ↑Sun Mar 06, 2022 5:31 am
Nah... This is the tool's own message. I ran this tool with all the vaccines off. Nevertheless, this tool is sending me a message that it does not recognize 'oo2core_6_win64.dll' file. Perhaps your 'oo2core_6_win64.dll' file is consistent with what the tool requires.

DLL i used from the game files https://mega.nz/file/LCAjwKxT#8McgPq0VO ... HDxSqtibx4
Would not attach as a zip.

Thank you. I'll test it out.
## Post #15
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2022-03-05T21:46:43+00:00
- Post Title: [PC] Elden Ring (.BDT / .BHD)

> Reply from 09williamsad ↑Sun Mar 06, 2022 5:37 am at Sun Mar 06, 2022 5:37 am
>
> 
uroborostestsubject wrote: ↑Sun Mar 06, 2022 5:31 am
Nah... This is the tool's own message. I ran this tool with all the vaccines off. Nevertheless, this tool is sending me a message that it does not recognize 'oo2core_6_win64.dll' file. Perhaps your 'oo2core_6_win64.dll' file is consistent with what the tool requires.

DLL i used from the game files https://mega.nz/file/LCAjwKxT#8McgPq0VO ... HDxSqtibx4
Would not attach as a zip.

'[ERROR]: Unable to initialize oo2core_6_win64.dll module. Copy this library from game folder!'

Even if I paste the DLL file you provided into the folder with the tool and run it, this message appears. I don't know what to do. haha
## Post #16
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2022-03-06T13:30:54+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

You probably need to unlock the executable and libraries (dll).

```
BouncyCastle.Crypto.dll
ER.Unpacker.exe
```


Like this
## Post #17
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2022-03-06T15:28:43+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

Hi it's been a while since I extracted DS3/BB files so I'm probably doing this wrong, but can someone remind me how to get the files out of the .mapbnd, .chrbnd, texbnd, etc.?

Using latest steam version of the game, I can get those files out of the .BDT / .BHD archives, but I can't get the models/textures out of the .mapbnd, .chrbnd, texbnd files.

If I use Ekey's tool to try I get this:

ER.Unpacker.exe "F:\EREX\map\m10\m10_00_00_00\m10_00_00_00_envmap_00_high_00.tpfbnd" "F:\TEST"
ELDEN RING Binder Unpacker
(c) 2022 Ekey (h4x0r) / v0.0.1.41767

[INFO]: Project File Loaded: 88302


Unhandled Exception: Org.BouncyCastle.Security.InvalidKeyException: Not an RSA key
   at Org.BouncyCastle.Crypto.Engines.RsaCoreEngine.Init(Boolean forEncryption, ICipherParameters parameters)
   at ER.Unpacker.BinderCipher.iDecryptByRSA(String m_BinderFile)
   at ER.Unpacker.BinderUnpack.iDoIt(String m_BinderFile, String m_DstFolder)
   at ER.Unpacker.Program.Main(String[] args)

Any help appreciated,
## Post #18
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2022-03-06T16:29:03+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

General Elden Ring model ripping process.
There are converted models and audio in my archive, site policy means I cannot post a link to it here, but if you google my username you should find it.

Tools:
1. ER BDT Tool [https://github.com/Ekey/ER.BDT.Tool/releases](https://github.com/Ekey/ER.BDT.Tool/releases)
2. Binder Tool [https://github.com/Atvaark/BinderTool](https://github.com/Atvaark/BinderTool)
3. BloodBorne_model tool [viewtopic.php?f=16&t=17332&start=375#p181131](https://forum.xentax.com/viewtopic.php?f=16&t=17332&start=375#p181131)
4. Noesis [https://richwhitehouse.com/index.php?co ... ojects.php](https://richwhitehouse.com/index.php?content=inc_projects.php)

Steps:
1. Use ER.Unpacker.exe on each bhd file as per the instruction on its github page, "Usage: ER.Unpacker.exe "BHD_FILE" "UNPACK_DIRECTORY""
You need oo2core_6_win64.dll from the game files in the same folder as ER.Unpacker for it to work.
2. Use BinderTool to unpack dcx files, there may be dcx files in dcx files so you may have to do this multiple times.
3. Use BinderTool to unpack any files with a extension ending in bnd, there may be bnd files in bnd files so you may have to do this multiple times.
i.e. animbnd, texbnd, etc.
4. Use BinderTool to unpack/convert the tpf textures to DDS.
5. Use BloodBorne_model.exe to convert the flver models to smd and ascii
6. Use Noesis to convert the smd to your desired format, if you are not importing it directly into your intended program.
7. Use Noesis to convert the DDS textures to DDS or another format, this is optional as the DDS format exported may be incompatible with your intented program.

There is a PowerShell script in my archive which automates steps 2 to 5.
## Post #19
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2022-03-06T18:57:00+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

Exactly what I needed!  Thanks 09williamsad
## Post #20
- Username: Graelyth
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat May 11, 2019 9:50 pm
- Post datetime: 2022-03-07T18:32:37+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

Unpacker still isn't opening for me. I unblocked the files, ran as admin , disabled antivirus. Not sure what I'm doing wrong 

EDIT:  nvm I was just messing up the syntax, but now im getting the same error as uroborostestsubject. I've got the dll copied to the same directory so I'm not sure if what's wrong.
"[ERROR]: Unable to initialize oo2core_6_win64.dll module. Copy this library from game folder!"
## Post #21
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2022-03-08T11:21:22+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

Are you running through a BAT file?
## Post #22
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2022-03-08T14:28:12+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

> Reply from michanlew ↑Fri Mar 04, 2022 4:39 pm at Fri Mar 04, 2022 4:39 pm
>
> 
TokiChan wrote: ↑Sun Feb 27, 2022 10:52 pm
Hi, dudes!
Any progress with Elden ring unpacking?


Есть инструмент UXM доступен тут https://discord.com/channels/5298028282 ... 1998149643

Ухм есть, но почему-то не пашет
Новый скачать не могу, тк нет доступа к серверу
[Снимок2.PNG](https://xentaxbackup.github.io/file/21905_Снимок2.PNG)
## Post #23
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2022-03-08T14:31:33+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

> Reply from 09williamsad ↑Sat Mar 05, 2022 4:13 am at Sat Mar 05, 2022 4:13 am
>
> 
Ekey made an unpacker https://github.com/Ekey/ER.BDT.Tool/releases

Thanks! will try
## Post #24
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2022-03-08T14:40:26+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

> Reply from 09williamsad ↑Mon Mar 07, 2022 12:29 am at Mon Mar 07, 2022 12:29 am
>
> 
General Elden Ring model ripping process.
There are converted models and audio in my archive, site policy means I cannot post a link to it here, but if you google my username you should find it.

Tools:
1. ER BDT Tool https://github.com/Ekey/ER.BDT.Tool/releases
2. Binder Tool https://github.com/Atvaark/BinderTool
3. BloodBorne_model tool viewtopic.php?f=16&t=17332&start=375#p181131
4. Noesis https://richwhitehouse.com/index.php?co ... ojects.php

Steps:
1. Use ER.Unpacker.exe on each bhd file as per the instruction on its github page, "Usage: ER.Unpacker.exe "BHD_FILE" "UNPACK_DIRECTORY""
You need oo2core_6_win64.dll from the game files in the same folder as ER.Unpacker for it to work.
2. Use BinderTool to unpack dcx files, there may be dcx files in dcx files so you may have to do this multiple times.
3. Use BinderTool to unpack any files with a extension ending in bnd, there may be bnd files in bnd files so you may have to do this multiple times.
i.e. animbnd, texbnd, etc.
4. Use BinderTool to unpack/convert the tpf textures to DDS.
5. Use BloodBorne_model.exe to convert the flver models to smd and ascii
6. Use Noesis to convert the smd to your desired format, if you are not importing it directly into your intended program.
7. Use Noesis to convert the DDS textures to DDS or another format, this is optional as the DDS format exported may be incompatible with your intented program.

There is a PowerShell script in my archive which automates steps 2 to 5.

Do ER.BDT.tool must be used with command line?
Run as admin no have effect

UPD I run with CMD, but this have error message:
"ER.Unpacker" не является внутренней или внешней
командой, исполняемой программой или пакетным файлом.

(ER.Unpacker not a command, programm or exe file)
What's wrong?
## Post #25
- Username: Klaus
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Mar 01, 2016 5:59 am
- Post datetime: 2022-03-08T15:56:23+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

> Reply from TokiChan ↑Tue Mar 08, 2022 10:40 pm at Tue Mar 08, 2022 10:40 pm
>
> 

Do ER.BDT.tool must be used with command line?
Run as admin no have effect

UPD I run with CMD, but this have error message:
"ER.Unpacker" не является внутренней или внешней
командой, исполняемой программой или пакетным файлом.

(ER.Unpacker not a command, programm or exe file)
What's wrong?

Maybe you're running it from a wrong emplacement, like the default C:\Users\<username> ? 
You must use the full path to the executable.
## Post #26
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2022-03-08T16:09:56+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

> Reply from TokiChan ↑Tue Mar 08, 2022 10:40 pm at Tue Mar 08, 2022 10:40 pm
>
> 
Do ER.BDT.tool must be used with command line?
Run as admin no have effect

UPD I run with CMD, but this have error message:
"ER.Unpacker" 
(ER.Unpacker not a command, programm or exe file)
What's wrong?

As per the instructions, it is command line tool.
You have to cd /d to the folder containing it, then run it in command line with the bhd file and output folder paramaters.
## Post #27
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2022-03-08T16:17:03+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

> Reply from 09williamsad ↑Wed Mar 09, 2022 12:09 am at Wed Mar 09, 2022 12:09 am
>
> 
TokiChan wrote: ↑Tue Mar 08, 2022 10:40 pm
Do ER.BDT.tool must be used with command line?
Run as admin no have effect

UPD I run with CMD, but this have error message:
"ER.Unpacker" 
(ER.Unpacker not a command, programm or exe file)
What's wrong?


As per the instructions, it is command line tool.
You have to cd /d to the folder containing it, then run it in command line with the bhd file and output folder paramaters.

I try, but it still not working
[Снимок22.PNG](https://xentaxbackup.github.io/file/21906_Снимок22.PNG)
## Post #28
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2022-03-08T16:18:11+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

> Reply from Klaus ↑Tue Mar 08, 2022 11:56 pm at Tue Mar 08, 2022 11:56 pm
>
> 

Maybe you're running it from a wrong emplacement, like the default C:\Users\<username> ? 
You must use the full path to the executable.

I try as the example
## Post #29
- Username: Klaus
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Mar 01, 2016 5:59 am
- Post datetime: 2022-03-08T16:25:01+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

> Reply from TokiChan ↑Wed Mar 09, 2022 12:17 am at Wed Mar 09, 2022 12:17 am
>
> 
I try, but it still not working
Your line is good if the unpacker is there, but you need to run it from : F:\0extra\dsrings\Game\
Not C:\WINDOWS\system32
## Post #30
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2022-03-08T16:31:16+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

> Reply from Klaus ↑Wed Mar 09, 2022 12:25 am at Wed Mar 09, 2022 12:25 am
>
> 
TokiChan wrote: ↑Wed Mar 09, 2022 12:17 am
I try, but it still not working

Your line is good if the unpacker is there, but you need to run it from : F:\0extra\dsrings\Game\
Not C:\WINDOWS\system32

Ok, now it have an effect.
But what mean it?
How I can reg bouncy.castle as a key?
[2222.PNG](https://xentaxbackup.github.io/file/21907_2222.PNG)
## Post #31
- Username: yaqdhan
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Mar 19, 2020 7:49 pm
- Post datetime: 2022-03-09T04:21:43+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

> Reply from Klaus ↑Wed Mar 09, 2022 12:25 am at Wed Mar 09, 2022 12:25 am
>
> 
TokiChan wrote: ↑Wed Mar 09, 2022 12:17 am
I try, but it still not working

Your line is good if the unpacker is there, but you need to run it from : F:\0extra\dsrings\Game\
Not C:\WINDOWS\system32

welp, I got the same message as OP
[Desktop Screenshot 2022.03.09 - 05.17.53.17.png](https://xentaxbackup.github.io/file/21910_Desktop Screenshot 2022.03.09 - 05.17.53.17.png)
## Post #32
- Username: Warpavp2
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Jan 04, 2015 8:01 am
- Post datetime: 2022-03-09T06:25:47+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

[ERROR]: Unable to initialize oo2core_6_win64.dll module. Copy this library from game folder!

This error just keeps happening, no idea how to fix this. I have my directories exact ://...
## Post #33
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2022-03-09T07:32:44+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

> Reply from yaqdhan ↑Wed Mar 09, 2022 12:21 pm at Wed Mar 09, 2022 12:21 pm
>
> 
welp, I got the same message as OP
You have to cd /d into the folder where the tool is.
Read the other posts.
## Post #34
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2022-03-09T07:33:12+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

> Reply from Warpavp2 ↑Wed Mar 09, 2022 2:25 pm at Wed Mar 09, 2022 2:25 pm
>
> 
[ERROR]: Unable to initialize oo2core_6_win64.dll module. Copy this library from game folder!
This error just keeps happening, no idea how to fix this. I have my directories exact ://...
As per the instructions, you have to copy that dll to where the tool is.
## Post #35
- Username: Klaus
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Mar 01, 2016 5:59 am
- Post datetime: 2022-03-09T08:16:55+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

To make it simpler, extract the whole ER.Unpacker archive in the game directory, where are .bhd and oo2core_6_win64.dll.
## Post #36
- Username: yaqdhan
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Mar 19, 2020 7:49 pm
- Post datetime: 2022-03-09T12:54:57+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

> Reply from 09williamsad ↑Wed Mar 09, 2022 3:32 pm at Wed Mar 09, 2022 3:32 pm
>
> 
yaqdhan wrote: ↑Wed Mar 09, 2022 12:21 pm
welp, I got the same message as OP

You have to cd /d into the folder where the tool is.
Read the other posts.

Ya, I understood that much, that's why I extracted the tool in the same folder as the game files.
## Post #37
- Username: yaqdhan
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Mar 19, 2020 7:49 pm
- Post datetime: 2022-03-09T13:23:57+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

As you can see, I cded into the game directory where both the game files and the tool archives are located and it's still giving me the same message
[Desktop Screenshot 2022.03.09 - 14.19.24.57-min.png](https://xentaxbackup.github.io/file/21913_Desktop Screenshot 2022.03.09 - 14.19.24.57-min.png)
## Post #38
- Username: Warpavp2
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Jan 04, 2015 8:01 am
- Post datetime: 2022-03-09T17:35:27+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

> Reply from 09williamsad ↑Wed Mar 09, 2022 3:33 pm at Wed Mar 09, 2022 3:33 pm
>
> 
Warpavp2 wrote: ↑Wed Mar 09, 2022 2:25 pm
[ERROR]: Unable to initialize oo2core_6_win64.dll module. Copy this library from game folder!
This error just keeps happening, no idea how to fix this. I have my directories exact ://...

As per the instructions, you have to copy that dll to where the tool is.

Right. I did that. I made a copy of the .dll and put it in every folder possible too. Is there a prerequisite file we need downloaded? Like a framework? I have not tried extracting the tool directly into the ER folder but i’ll try that now. Idk what cd/d means sorry.

EDIT: So I put the unpacker into the main game folder with the .dll and it still gives me the same error.
## Post #39
- Username: Warpavp2
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Jan 04, 2015 8:01 am
- Post datetime: 2022-03-09T18:15:38+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

I got it to work: For those confused I will try to write this out the best I can.

I was receiving the error: Unable to load the .dll file (the oo2 or whatever). 

What I did: Change the harddrive that the unpacker is running from to the exact harddrive you have it installed.
By default mine was using C 
(If you open the CMD tool you'll see it runs it from POSSIBLY the C drive. Unless your unpacker is installed in the C main drive folder (just plainly C:) then you are fine)

Extract the ER.Unpacker in the main C/D/V/X/Y/Z Folder you want. For me I used X:
TO CHANGE THE DIRECTORY
Type cd/d X: or cd/d D: or cd/d F: to change to WHERE YOU UNPACKED IT.

You need to use type the ER.Unpacker PLAIN because it already recognizes where your file is.
COPY THE .DLL TO THAT SAME AREA. Wherever your Er.Unpacker is.

Then in the CMD just type
ER.Unpacker "File location of BHD" "File location of extraction folder"
EXAMPLE:
IF YOU CHANGED YOUR HARDDRIVE LOCATION FOR THE CMD THE FIRST LETTER ON YOUR SIDE OF THE SCREEN WILL BE WHERE IT READS THE ER.UNPACKER
Ex: 
C:\> ER.Unpacker.exe etc etc etc
V:\> ER.Unpacker.exe etc etc etc

I used X
So I wouldnt have to type anything but the ER.Unpacker.exe because it would show up like this
X:\> ER.Unpacker.exe
The full line will look like this once you have the correct paths located
X:\> ER.Unpacker.exe "FILE LOCATION OF BHD" "FILE LOCATION OF EXTRACTION TO FOLDER"

It just works this way, idk why it just does. Make sure the.dll is in the same area as the ER.Unpacker and all it's other files.

REMEMBER: If you are running ER.UNPACKER.EXE FROM C:/ BUT IT'S EXTRACTED IN G:/ IT WILL NOT WORK UNLESS THE CMD IS CHANGED TO THAT DRIVE. TO make it easier just extract the Unpacker stuff in the main drive folder.
## Post #40
- Username: tsfgsg
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu May 06, 2021 11:58 pm
- Post datetime: 2022-03-09T19:12:27+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

I followed all of the advice above but got the following I/O error while unpacking. Tried with multiple BHD's, same error. Any ideas?




screen.png (19.55 KiB) Viewed 153 times
## Post #41
- Username: yaqdhan
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Mar 19, 2020 7:49 pm
- Post datetime: 2022-03-09T19:29:10+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

> Reply from tsfgsg ↑Thu Mar 10, 2022 3:12 am at Thu Mar 10, 2022 3:12 am
>
> 
I followed all of the advice above but got the following I/O error while unpacking. Tried with multiple BHD's, same error. Any ideas?


screen.png

I got it to work. Here is what I think you have to do :
Firstly, you have to make sure that both the bhd and its correspondent bdt file are in the same folder. Secondly, your game files(bhd and bdt) and the tool files must NOT have the same DIRECTORY. The output folder can be anywhere though. Thirdly, copy past the oo2core_6_win64.dll game file inside the tool folder. Finally, and this is probably the most important part, make sure that none of your directories include any spaces, so instead of naming it Elden Ring Archives, change it to eldenringarchives. Also, pay close attention to the syntax and capitalize your letters when you need to. Otherwise this is all you have to do. Hope this helps
[Desktop Screenshot 2022.03.09 - 20.03.21.67.png](https://xentaxbackup.github.io/file/21915_Desktop Screenshot 2022.03.09 - 20.03.21.67.png)
## Post #42
- Username: tsfgsg
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu May 06, 2021 11:58 pm
- Post datetime: 2022-03-09T19:47:31+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

Damn same error after fixing to account for your advice. Here's my current layout, I have 3 folders:

C:\Eldenring (contains a bunch of bdt and bhd files and the oo2core_6_win64.dll)
C:\Extracted (destination folder)
C:\Tool (contains ER.Unpacker batch and exe files, BouncyCastle.Crypto.dll, a copy of the oo2core_6_win64.dll, and a Projects folder that came with the tool)

Here is exactly how I entered everything in cmd, and the resulting identical error: 




screen 2.png (18.45 KiB) Viewed 144 times
## Post #43
- Username: Warpavp2
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Jan 04, 2015 8:01 am
- Post datetime: 2022-03-09T19:54:51+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

> Reply from tsfgsg ↑Thu Mar 10, 2022 3:47 am at Thu Mar 10, 2022 3:47 am
>
> 
Damn same error after fixing to account for your advice. Here's my current layout, I have 3 folders:

C:\Eldenring (contains a bunch of bdt and bhd files and the oo2core_6_win64.dll)
C:\Extracted (destination folder)
C:\Tool (contains ER.Unpacker batch and exe files, BouncyCastle.Crypto.dll, a copy of the oo2core_6_win64.dll, and a Projects folder that came with the tool)

Here is exactly how I entered everything in cmd, and the resulting identical error: 


screen 2.png

Don't put the tool in a tool folder
it has to be straight up
C:\>ER.Unpacker.exe
## Post #44
- Username: Warpavp2
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Jan 04, 2015 8:01 am
- Post datetime: 2022-03-09T19:58:16+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

SIDE QUESTION:
(I posted this in DS3 too)
Does anyone know how to backtrack data find where the SOURCE of a talisman would come from?
Trying to find Companion Jar and what rewards it through the data files, but a good way would see how they do it in other games like DS3

If it is a drop from a mob what data files would I be looking for for a drop loot table?
If it is a quest reward is there a data string that shows steps or quest reward for the item/source?
Is there a source data file and what extensions? Thanks!

I was succesful to pull all the data files, but I don't know where this data0-3 would be.
## Post #45
- Username: tsfgsg
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu May 06, 2021 11:58 pm
- Post datetime: 2022-03-09T20:07:52+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

> Reply from Warpavp2 ↑Thu Mar 10, 2022 3:54 am at Thu Mar 10, 2022 3:54 am
>
> 
tsfgsg wrote: ↑Thu Mar 10, 2022 3:47 am
Damn same error after fixing to account for your advice. Here's my current layout, I have 3 folders:

C:\Eldenring (contains a bunch of bdt and bhd files and the oo2core_6_win64.dll)
C:\Extracted (destination folder)
C:\Tool (contains ER.Unpacker batch and exe files, BouncyCastle.Crypto.dll, a copy of the oo2core_6_win64.dll, and a Projects folder that came with the tool)

Here is exactly how I entered everything in cmd, and the resulting identical error: 


screen 2.png


Don't put the tool in a tool folder
it has to be straight up
C:\>ER.Unpacker.exe

No change, just took everything out of the Tool folder and just put it directly on the C:\ drive. Same exact error
## Post #46
- Username: Warpavp2
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Jan 04, 2015 8:01 am
- Post datetime: 2022-03-09T20:12:29+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

are you typing .exe
What does your full command look like?
## Post #47
- Username: tsfgsg
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu May 06, 2021 11:58 pm
- Post datetime: 2022-03-09T20:18:00+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

> Reply from Warpavp2 ↑Thu Mar 10, 2022 4:12 am at Thu Mar 10, 2022 4:12 am
>
> 
are you typing .exe
What does your full command look like?

Just tried it both ways, here ya go. It looks like I've done everything correctly and it literally starts unpacking an asset (even creating that asset folder inside the destination folder) and then fails.




screen 3.png (44.78 KiB) Viewed 424 times
## Post #48
- Username: Warpavp2
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Jan 04, 2015 8:01 am
- Post datetime: 2022-03-09T20:22:10+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

It says an I/O Error, no idea what that means. Do you have enough memory or something? Maybe try it all in a different drive? I never made a copy of my elden ring folder, I just extract from the regular steam one. I can't help with the I/O issue, sorry!
## Post #49
- Username: yaqdhan
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Mar 19, 2020 7:49 pm
- Post datetime: 2022-03-09T20:36:28+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

> Reply from tsfgsg ↑Thu Mar 10, 2022 4:18 am at Thu Mar 10, 2022 4:18 am
>
> 
Warpavp2 wrote: ↑Thu Mar 10, 2022 4:12 am
are you typing .exe
What does your full command look like?


Just tried it both ways, here ya go. It looks like I've done everything correctly and it literally starts unpacking an asset (even creating that asset folder inside the destination folder) and then fails.


screen 3.png
You could also use UXM (credits to Meowmaritus)
[https://drive.google.com/file/d/1uNmWTD ... sp=sharing](https://drive.google.com/file/d/1uNmWTD3pfDGPzEabcB3laMEJyVc_0qsp/view?usp=sharing)
## Post #50
- Username: xxdeathknight72xx
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 14, 2017 10:01 pm
- Post datetime: 2022-03-10T15:37:17+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

> Reply from yaqdhan ↑Thu Mar 10, 2022 4:36 am at Thu Mar 10, 2022 4:36 am
>
> 
tsfgsg wrote: ↑Thu Mar 10, 2022 4:18 am
Warpavp2 wrote: ↑Thu Mar 10, 2022 4:12 am
are you typing .exe
What does your full command look like?


Just tried it both ways, here ya go. It looks like I've done everything correctly and it literally starts unpacking an asset (even creating that asset folder inside the destination folder) and then fails.


screen 3.png

You could also use UXM (credits to Meowmaritus)
https://drive.google.com/file/d/1uNmWTD ... sp=sharing

Thank you, this worked perfectly for me when I couldn't get the ER.Unpacker to work properly 

I'm new to this modding and was confused at first so I'll lay out my process in the hopes it may help someone like me

Tools needed are found above and on page 2:
UMX
BinderTool
BloodBorne_model
Noesis

My process I got to work to export files is
Unpack using above UXM. Direct program to your Elden Ring.exe - Unpack only, no need to patch
(Going forward I'll use Character 2180 as an example)
Once unpacked, navigate to Elden Ring/Game/chr 
Find file c2180.chrbnd.dcx
select and drag that file directly onto BinderTool.exe
You'll now see a fiel created in Elden Ring/Game/chr called "c2180.chrbnd"
Do the same with c2180.chrbnd - Drag it onto BinderTool.exe
You'll now see a folder created called c2180
Now navigate through that folder ELDEN RING\Game\chr\c2180\GR\data\INTERROOT_win64\chr\c2180
Select and drag c2180.flver onto BloodBorne_model.exe
You'll now see an .ascii and .smd file are created
Open Noesis and navigate to this directory , ELDEN RING\Game\chr\c2180\GR\data\INTERROOT_win64\chr\c2180
Open .smd file and file>export to your desired format

I have no idea what files are what models and I have no idea how to batch this process to save time

If anyone knows and can share that would be awesome!
## Post #51
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2022-03-12T17:37:14+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

Hi, guys!
Lost UV on fur and feathers in c3181 and c4500
[- - ---.jpg](https://xentaxbackup.github.io/file/21936_- - ---.jpg)
## Post #52
- Username: dirkthedude
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Mar 14, 2022 5:14 pm
- Post datetime: 2022-03-14T09:35:25+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

Howdy y'all! Brand new here. First off, wanted to thank y'all for all the hard work! Second, I have a question about the armor models specifically. I followed the steps to convert the flver with the bloodborne exe, and got the ASCII and SMD file types. Popped the SMD into Noesis. Apparently, the UVs are messed up on them. The only way I can get the UVs to look even remotely okay is by just taking the FBX file and converting that into an SMD with Noesis while having the flip UVs option ticked.

However, the UVs are still looking pretty rough in Blender. Anything I can do about this? I'm assuming something went wrong in the converting process or from the files that were converted that already exist out there on the interwebs. I'm at a loss and really wanting my Raging Wolf set, lol.

To clarify, I've only tried converting the already unpacked files from the reply above with the steps on how to do it. I haven't actually tried unpacking myself which honestly might be the problem.
## Post #53
- Username: Cardboardman21
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 15, 2022 3:03 am
- Post datetime: 2022-03-14T19:08:42+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

Hello everyone! I’ve been searching for a way to get a specific armor model from the game Imp Head (Wolf)
[https://eldenring.wiki.fextralife.com/Imp+Head+(Wolf)](https://eldenring.wiki.fextralife.com/Imp+Head+%28Wolf%29)

Is this something easily done with the tools above? If not does anyone by chance have this model they could send me?

Thank you.
## Post #54
- Username: Chulio
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 15, 2022 10:07 pm
- Post datetime: 2022-03-15T14:16:03+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

I have no idea about that stuff at all, but would it be possible to extract the weapon thumbnails?
If so, could someone point me in the right direction?

Cheers
## Post #55
- Username: olylanboy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 31, 2012 9:24 pm
- Post datetime: 2022-03-16T05:38:09+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

any idea about repacking .bdt/bhd ?
## Post #56
- Username: xsploit
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 17, 2022 1:42 pm
- Post datetime: 2022-03-17T05:43:48+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

Does anyone have the sound files?
## Post #57
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2022-03-17T23:16:22+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

I think we need to solve the UV problems(especially fur and hair)  more quickly than any other problem. I used all existing tools to check if the UV map is working properly, but some human models' hair and fur UV maps are completely messed up. In this case, there is no other way but to unwrap the UV map and modify the pieces of the UV map one by one...

It's very inefficient in terms of time, and it's too hard work. I think we need a new patch for the UV map. If you are an expert in the program, I would appreciate it if you could create a new tool for the UV map to work properly.
## Post #58
- Username: dirkthedude
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Mar 14, 2022 5:14 pm
- Post datetime: 2022-03-18T14:38:14+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

> Reply from uroborostestsubject ↑Fri Mar 18, 2022 7:16 am at Fri Mar 18, 2022 7:16 am
>
> 
I think we need to solve the UV problems(especially fur and hair)  more quickly than any other problem. I used all existing tools to check if the UV map is working properly, but some human models' hair and fur UV maps are completely messed up. In this case, there is no other way but to unwrap the UV map and modify the pieces of the UV map one by one...

It's very inefficient in terms of time, and it's too hard work. I think we need a new patch for the UV map. If you are an expert in the program, I would appreciate it if you could create a new tool for the UV map to work properly.

That's the issue I'm having with the armor pieces. All the UVs are either messed up or missing textures. For example, Vargam, his helmet is only half right. The "chainmail" texture is either just messed up beyond recognition or missing entirely. But I agree. The UVs seem to be the biggest issue as of right now.
## Post #59
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2022-03-20T05:59:52+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

I tested the mohg's wing mesh, but it's still daemon's tool problem. The front UV of the wing is normal, but the back UV is completely messed up.. Model's bone and weight values can be modified somehow, but if the UV is messed up, no action can be taken. If the UV is flipped, it can be fixed, but if it's mixed up like this, there's really no way to fix it... I would like anyone to come up with a proper solution to this problem with the UV of hair and fur.
## Post #60
- Username: eldpine
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 21, 2022 7:53 pm
- Post datetime: 2022-03-21T12:02:52+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

Hi! I'm new. I hope this is an appropriate place to share this. If there's somewhere else that would be a good place to post this, please let me know.

I ran automated speech-to-text against Elden Ring's audio files to help me find some specific voice lines. I can imagine that the Python script I wrote and the speech-to-text results might be useful to others besides myself, in sorting through the game's huge number of unorganized audio files.

The speech-to-text results are extremely imperfect. But, in the end, "with these foolish and i'm still grass" was still enough for me to identify which audio file out of the nearly 20,000 in the Data0/sounds archive contained the isolated high-quality audio of Margit saying, "Put these foolish ambitions to rest."

---

Here are a few samples:

Put these foolish ambitions to rest.
[http://www.sndup.net/syjy](http://www.sndup.net/syjy) 
[https://i.imgur.com/OJ5VdEM.png](https://i.imgur.com/OJ5VdEM.png)

Heresy is not native to the world. It is but a contrivance.
[http://www.sndup.net/zjtf](http://www.sndup.net/zjtf) 
[https://i.imgur.com/muL6VGJ.png](https://i.imgur.com/muL6VGJ.png)

Well, if you really are that gullible...
[http://www.sndup.net/f368](http://www.sndup.net/f368) 
[https://i.imgur.com/mxA6Clz.png](https://i.imgur.com/mxA6Clz.png)

---

Here is the Python script's output, a list of the speech-to-text results for Elden Ring's audio files. normal_11680.ogg is apparently the first audio file (in ascending numeric order) which contains actual voice audio, as opposed to sound effects and ambient noises. For completeness' sake, the generally nonsensical, sometimes profane speech-to-text results for numbers lower than 11680 are also included. However, speech-to-text for audio files under 10kb in size has been omitted from this data.

[https://files.pineapplemachine.com/publ ... o-text.zip](https://files.pineapplemachine.com/public/misc/Elden%20Ring%20speech-to-text.zip)

Here you can find the Python script I used along with some documentation about how to reproduce this work that I did. If someone has access to a speech-to-text service that produces more accurate results than [Sphinx](https://cmusphinx.github.io/), for example, then they might modify the part of the script which carries out speech-to-text and produce their own massive text file. Or in case someone really wants the speech-to-text results even for the smallest audio files.

[https://gist.github.com/pineapplemachin ... f887e6a4ef](https://gist.github.com/pineapplemachine/77e64c92aa75757e235dd4f887e6a4ef)

---

I hope that this can all prove useful to others who have been trying to sort out Elden Ring's audio files!
## Post #61
- Username: atvaark
- Rank: advanced
- Number of posts: 52
- Joined date: Fri Aug 28, 2015 10:19 pm
- Post datetime: 2022-03-25T20:10:29+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

I just published [version v0.7.0-pre4 of BinderTool](https://github.com/Atvaark/BinderTool/releases/tag/v0.7.0-pre4) with the latest contributions by [googleben](https://github.com/googleben) and [gomsoup](https://github.com/gomsoup).
This should add bdt extraction support with an updated dictionary in addition to a couple of new quite helpful command line flags.
## Post #62
- Username: phrauz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 19, 2022 2:27 pm
- Post datetime: 2022-04-19T12:38:31+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

Hey everyone! After couple of hours of learning, I was finally able to get Maliketh's model and couple of textures in [there](https://imgur.com/a/ats0sL3) (still struggling at furs and hairs), and to my surprise, the model already had a skeleton. The thing is, though, I can't do anything with the hkx anim files. It doesn't open in Havok Viewer (says unable to detect format from stream.) I'd guess, it's about at which havok version it was created? I had bloodborne animations, so tried to look at the hex codes to compare, and it looks different. Is there a way that I can open these files?
## Post #63
- Username: wardialer6000
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jun 09, 2016 2:05 am
- Post datetime: 2022-04-19T14:32:47+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

since i only use POSED 3D models, i already grabbed ranni with intel GPA frame analyzer and restored her for 3D RESIN printing.  its on thingiverse among other BLENDs i've posted.  other data is also available in intel GPA frame anazlyzer as i'm sure someone already pointed out in this thread, but the exported OBJ lack UV data.  i've injected UV into OBJ by rotating cells in a spreadsheet but that's a roundabout way of doing things... i'm sure there's a cleaner and more efficient way.  there's also a bunch of transform matrices you can use but i'm not smart enough to make sense of them since i don't really need them for mesh restoration.

i'll ask my question about ripping from switch emulators yuzu and ryujinx in another thread so as not to hijack this one.
## Post #64
- Username: Tekkamanchronos
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 24, 2015 1:50 am
- Post datetime: 2022-05-09T01:44:46+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

> Reply from phrauz ↑Tue Apr 19, 2022 8:38 pm at Tue Apr 19, 2022 8:38 pm
>
> 
Hey everyone! After couple of hours of learning, I was finally able to get Maliketh's model and couple of textures in there (still struggling at furs and hairs), and to my surprise, the model already had a skeleton. The thing is, though, I can't do anything with the hkx anim files. It doesn't open in Havok Viewer (says unable to detect format from stream.) I'd guess, it's about at which havok version it was created? I had bloodborne animations, so tried to look at the hex codes to compare, and it looks different. Is there a way that I can open these files?
Any luck on the animation research?
## Post #65
- Username: phrauz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 19, 2022 2:27 pm
- Post datetime: 2022-05-11T07:22:42+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

> Reply from Tekkamanchronos ↑Mon May 09, 2022 9:44 am at Mon May 09, 2022 9:44 am
>
> 
phrauz wrote: ↑Tue Apr 19, 2022 8:38 pm
Hey everyone! After couple of hours of learning, I was finally able to get Maliketh's model and couple of textures in there (still struggling at furs and hairs), and to my surprise, the model already had a skeleton. The thing is, though, I can't do anything with the hkx anim files. It doesn't open in Havok Viewer (says unable to detect format from stream.) I'd guess, it's about at which havok version it was created? I had bloodborne animations, so tried to look at the hex codes to compare, and it looks different. Is there a way that I can open these files?

Any luck on the animation research?

Sadly, no. I tried reading some threads and watching some videos on the older From games to grasp bits and pieces, but after a week had to take a break for schoolwork. Don't really know when I'm gonna get back to it, but it'll probably take 2-3 months or so.
## Post #66
- Username: 3301
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 11, 2021 10:47 pm
- Post datetime: 2022-05-15T22:48:32+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

Small .bat scripts for batch processing.
Contains :
BinderTool.exe (for .xxxbnd)
BloodBorne_model.exe (for .flver)
BAT scripts for:
Convert any .xxxbnd files.
Convert .flver files to .ascii and .smd
Convert .tpf files to .dds
Removing .xxxbnd, .flver and .tpf files from current folder.

Link : [https://cloud.mail.ru/public/W7GM/o5AsRFmiq](https://cloud.mail.ru/public/W7GM/o5AsRFmiq)
## Post #67
- Username: zlohort
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 12, 2022 4:32 am
- Post datetime: 2022-07-19T13:19:41+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

> Reply from uroborostestsubject ↑Fri Mar 18, 2022 7:16 am at Fri Mar 18, 2022 7:16 am
>
> 
I think we need to solve the UV problems(especially fur and hair)  more quickly than any other problem. I used all existing tools to check if the UV map is working properly, but some human models' hair and fur UV maps are completely messed up. In this case, there is no other way but to unwrap the UV map and modify the pieces of the UV map one by one...

It's very inefficient in terms of time, and it's too hard work. I think we need a new patch for the UV map. If you are an expert in the program, I would appreciate it if you could create a new tool for the UV map to work properly.

Try this blender plug-in. It crashes at some complex models like Radagon or some other packages, but it imports the UV maps correctly.

[https://github.com/FelixBenter/FromSoft ... r-Importer](https://github.com/FelixBenter/FromSoftware-Blender-Importer)

It imports only one layer of UV maps as I know.

Here is my fork which imports all bones not only first bone tree, don't know if the author fixed this issue on his side:
[https://github.com/Zloihort/FromSoftwar ... r-Importer](https://github.com/Zloihort/FromSoftware-Blender-Importer)

The plug-in also keeps material names for meshes, and keeps bone names as in FLVER, without to rename the "_" symbol to "-" or how the BloodBorneTools does.
## Post #68
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2022-11-01T22:21:14+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

Now I try understand how to dl this version, because I no see button (release) XD
I have version before ER update was added
## Post #69
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2022-11-13T16:35:16+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

So,I try to use DS map studio by Katalash, but it crashes.
I install all required frameworks,but it still crash.
Do someone know how to fix it?

And do someone work with fix for fur/hair UV extraction?
## Post #70
- Username: zlohort
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 12, 2022 4:32 am
- Post datetime: 2023-05-08T08:30:41+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

> Reply from TokiChan ↑Wed Nov 02, 2022 6:21 am at Wed Nov 02, 2022 6:21 am
>
> 
Now I try understand how to dl this version, because I no see button (release) XD
I have version before ER update was added

Sorry for late reply.
In order to install that plug-in you need to download the source code, then archive it via winrar or 7zip. The resulted archive is a blender plug-in installer.

Or here is a link to my version on gdrive:
[https://drive.google.com/file/d/1J917lI ... yWz_b/view](https://drive.google.com/file/d/1J917lICJGanehAgeJ3JMVGl3cSHyWz_b/view)

I'm not sure if it works on latest Blender(3.5) but should work for version 3.0-3.1 for sure.
Don't forget to put in the add-on settings of the plug-in the path to the Yabber.
Also if it doesn't work - disable the import textures option.

Since the fur has several UV maps, I'm not sure if it will get the correct layer(for instance the hair of the Zamor's warrior has the first UV layer a b/w gradient and the second is the hair strands), but I saw how BloodborneTools messes the capes UV sometimes for ER. The plug-in will read the capes UVs correctly.

Don't use it for rigging, it doesn't change the axis orientation(you will need to rotate the meshes X 90 Z 180 in order to get the right position) and doesn't mirror the meshes(but you still can mirror X manually in blender in order to fix this issue).
## Post #71
- Username: Odinv6
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 22, 2023 2:14 am
- Post datetime: 2023-08-22T22:12:27+00:00
- Post Title: Re: [PC] Elden Ring (.BDT / .BHD)

The Plugin doesnt work for me at all.When setting it up it cant see or open .dcx or .bnd with it. If anyone that got it working can help me out you can reach me under my discord odin_v2
