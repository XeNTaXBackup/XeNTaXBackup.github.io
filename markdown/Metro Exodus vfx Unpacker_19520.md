## Post #1
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2019-02-19T02:11:36+00:00
- Post Title: Metro Exodus vfx Unpacker

Hi,

I'm sharing the vfx unpacker tool for the new Metro game.
Please let me know if you encounter any issue while unpacking.
You can selectively unpack files only you need using filter.

```
------- celikeins - 2019.02.16 --------
Usage: metro-vfx-unpacker.exe <command> <vfx file> [<filter>]
<command> is x or l: x to extract files, l to only list names without extracting
<vfx file>: vfx file
Optional <filter>: Filter to filter files by name
Examples:
The following command line will extract all files:
 metro-vfx-unpacker.exe x content.vfx
The following command line will extract only files with 'localization' in their path:
 metro-vfx-unpacker.exe x content.vfx localization
The following command line will list all files in the archive:
 metro-vfx-unpacker.exe l content.vfx

```

[metro-vfx-tool.zip](https://xentaxbackup.github.io/file/15750_metro-vfx-tool.zip)
## Post #2
- Username: AveryBlue
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Feb 24, 2019 9:42 am
- Post datetime: 2019-02-24T02:12:12+00:00
- Post Title: Metro Exodus vfx Unpacker

Hey Friend,

I've been searching the internet for a way to Extract the Files from Metro Exodus, specifically the Audio Files, and I found your tool. I tried using it and ran into some trouble. I was hoping you could help me. I saw where you said to make a shortcut of the EXE and in the properties target line of the shortcut I wrote ("D:\Remix\Metro Exodus\Tools\metro-vfx-tool\metro-vfx-unpacker.exe" x content.vfx) like instructed. I then moved Content.vfx to the folder the EXE was in and ran the shortcut. It generated a directory of folders but the directory was empty. I am also having trouble getting this to unpack the rest of the files as they are all in Vfs0, vfs1, vfs2, esc formats. When I try running the shortcut with files with the vfs extensions it doesn't work at all. I was wondering if I was somehow doing this wrong or if you knew a better way to rip the audio files from this game?

Thank you for your time,
Avery
## Post #3
- Username: alexsimm
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 09, 2019 12:45 am
- Post datetime: 2019-02-24T13:19:53+00:00
- Post Title: Metro Exodus vfx Unpacker

How to convert textures .512 .1024 ...?
## Post #4
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2019-02-24T23:07:01+00:00
- Post Title: Metro Exodus vfx Unpacker

> Reply from AveryBlue ↑Sun Feb 24, 2019 10:12 am at Sun Feb 24, 2019 10:12 am
>
> 
Hey Friend,

I've been searching the internet for a way to Extract the Files from Metro Exodus, specifically the Audio Files, and I found your tool. I tried using it and ran into some trouble. I was hoping you could help me. I saw where you said to make a shortcut of the EXE and in the properties target line of the shortcut I wrote ("D:\Remix\Metro Exodus\Tools\metro-vfx-tool\metro-vfx-unpacker.exe" x content.vfx) like instructed. I then moved Content.vfx to the folder the EXE was in and ran the shortcut. It generated a directory of folders but the directory was empty. I am also having trouble getting this to unpack the rest of the files as they are all in Vfs0, vfs1, vfs2, esc formats. When I try running the shortcut with files with the vfs extensions it doesn't work at all. I was wondering if I was somehow doing this wrong or if you knew a better way to rip the audio files from this game?

Thank you for your time,
Avery

Hi Avery,

You should move EXE to the content.vfx folder. Because, content.vfx is index file and the actual content of files are in the vfs files.

Your welcome,
## Post #5
- Username: AveryBlue
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Feb 24, 2019 9:42 am
- Post datetime: 2019-02-25T19:52:06+00:00
- Post Title: Metro Exodus vfx Unpacker

Ah I see!

With your help I was able to get it to work. Thank you so much, sir!
## Post #6
- Username: alexsimm
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 09, 2019 12:45 am
- Post datetime: 2019-02-25T21:21:33+00:00
- Post Title: Metro Exodus vfx Unpacker

> Reply from alexsimm ↑Sun Feb 24, 2019 9:19 pm at Sun Feb 24, 2019 9:19 pm
>
> 
How to convert textures .512 .1024 ...?
?!
## Post #7
- Username: Dizcordum
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Mar 01, 2019 10:32 am
- Post datetime: 2019-03-01T02:46:59+00:00
- Post Title: Metro Exodus vfx Unpacker

What image format do textures have?
png? tga?
how to convert them?
## Post #8
- Username: Dizcordum
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Mar 01, 2019 10:32 am
- Post datetime: 2019-03-01T03:18:08+00:00
- Post Title: Metro Exodus vfx Unpacker

i tryed an old metro LL 4a game engine textures conventer to dds format
but seems it has wrong encrypting script that final result outgoing an image mess
## Post #9
- Username: DandoSVK
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 03, 2018 12:42 am
- Post datetime: 2019-03-01T08:22:13+00:00
- Post Title: Metro Exodus vfx Unpacker

Can you import the models properly into 3DS Max for example? old Redux (.mesh, .model and other Metro formats) importers dont work and models are mess
## Post #10
- Username: binlv
- Rank: advanced
- Number of posts: 65
- Joined date: Wed Apr 12, 2017 8:36 am
- Post datetime: 2019-03-01T15:44:48+00:00
- Post Title: Metro Exodus vfx Unpacker

> Reply from rengareng ↑Tue Feb 19, 2019 10:11 am at Tue Feb 19, 2019 10:11 am
>
> 

For text:
The newest lng is in the patch_01_shared.vfx/vfs0 file
Unpack it with rengareng or iOrange tool
Edit it with rengareng tool
Make a folder eg: "patch" and put there without subfolders
Use my script to insert it, select patch_01_shared.vfx, then patch folder, rename the NEW vfx file, backup original

For font:
They are in the content files
Unpack them with rengareng tool then convert them to dds with Prodnik a1tt tool
Or save them directly as dds with iOrange tool
Edit them eg with Paint.NET and DDS FileType Plus plugin
Save as BC7 (Linear, DX 11+) Generate Mip Map
Cut the first 148 byte
Compress it with LZ4.exe best mode
Cut first 11 and last 8 byte from the compressed file
You can use my dds helper to do these 3 step above if you not familiar with hex editor
Rename to original name
Make a folder eg: "content" and put there without subfolders 
Use my script to insert them, select content.vfx, then content folder, rename the NEW vfx file, backup original

rengareng vfx tool: https://zenhax.com/viewtopic.php?f=9&t=9523
rengareng lng tool: https://zenhax.com/viewtopic.php?f=12&t ... 573#p43573
iOrange and Prodnik tool: https://www.gameru.net/forum/index.php? ... 71879&st=0
Paint.NET: https://www.getpaint.net/
Paint.NET DDS FileType Plus: https://forums.getpaint.net/topic/11173 ... 019-02-07/
LZ4: https://github.com/lz4/lz4/releases/tag/v1.8.3

Texttool sources: https://zenhax.com/viewtopic.php?f=12&t=645

by swuforce
## Post #11
- Username: Firephoenix1342
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jan 25, 2019 9:32 pm
- Post datetime: 2019-03-06T10:42:26+00:00
- Post Title: Metro Exodus vfx Unpacker

How to use this tool? I moved the program to the folder with the game, when I start it opens only for a moment, and then closes and nothing else happens.
## Post #12
- Username: Neurolepticer
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Dec 09, 2017 12:06 pm
- Post datetime: 2019-03-22T21:15:38+00:00
- Post Title: Metro Exodus vfx Unpacker

MetroEX v0.1  Tool 
Works with static meshes and textures




Download:
[https://www.gameru.net/forum/index.php? ... try1651324](https://www.gameru.net/forum/index.php?showtopic=50840&st=440&p=1651324&#entry1651324)
## Post #13
- Username: anthony78880
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Mar 04, 2019 2:21 am
- Post datetime: 2019-03-30T18:23:36+00:00
- Post Title: Metro Exodus vfx Unpacker

I downloaded the tool could you tell me how to extract Metro Exodus
## Post #14
- Username: benchmark7770
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 24, 2019 9:56 pm
- Post datetime: 2019-06-24T14:02:09+00:00
- Post Title: Metro Exodus vfx Unpacker

Thank you for this tool : rengareng

I managed to extract and convert the textures, using your tool. 

But now i am stuck at the process of repacking everything, your instructions say use my script, 
which script is that? and how to use it? what tool to use while repacking and how to repack?

Thanks again.
## Post #15
- Username: soopytwist
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Dec 02, 2017 1:58 am
- Post datetime: 2020-06-14T13:05:06+00:00
- Post Title: Metro Exodus vfx Unpacker

Hi all. I realise the last post on this was a year ago but can someone please tell me how to repack the content?

I've got my content folder all unpacked and looking for a particular sound file. The .vba files I know to change the file extension to .ogg for editing, then saving them as .vba again. Now I need to repack it all back to content.vfx so how to I do that?

Also, I haven't found the sound file I'm looking for yet. It's Sam's breathing in the Sam's Story DLC. He breaths heavily throughout the entire campaign even during cutscenes and over his own spoke dialogue! I'm sure it's a bug. I want to find those samples, silence them and put them back into the game so he no longer breathes (except when choking or using the gas mask obviously).
## Post #16
- Username: soopytwist
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Dec 02, 2017 1:58 am
- Post datetime: 2020-06-14T14:38:08+00:00
- Post Title: Re: Metro Exodus vfx Unpacker

Okay, found the files I was looking for. Changed them to ogg, edited them, changed them back to vba and put them in content\sounds etc etc. However it would seem the game doesn't use the modified files in the same folder structure, so either there's a config command to enable this or I have to repack back to content.vfx.

Help?
