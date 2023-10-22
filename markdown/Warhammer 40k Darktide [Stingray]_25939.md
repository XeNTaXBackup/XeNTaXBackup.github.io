## Post #1
- Username: Br1ck
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Sep 06, 2022 4:26 am
- Post datetime: 2022-10-27T11:55:59+00:00
- Post Title: Warhammer 40k Darktide [Stingray]

Has anyone tried to extract the bundle files from the darktide beta?
I tried to use two different Vermintide Bundle extractors and bitsquid unpacker without any success.
Would like to access the image/icon and translation files.
Could provide files if necessary.

I would appreciate it if someone could help me out
## Post #2
- Username: AncientV25
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 24, 2020 10:25 am
- Post datetime: 2022-10-31T15:18:36+00:00
- Post Title: Warhammer 40k Darktide [Stingray]

Vermintide 2 and VT Endtimes bundles were compressed with zlib.
Darktide bundles are compressed with oodle. Format shouldn't be significantly different from VT2 otherwise afaik.
## Post #3
- Username: schnoodle
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Nov 19, 2022 3:57 pm
- Post datetime: 2022-11-21T19:43:42+00:00
- Post Title: Warhammer 40k Darktide [Stingray]

Have you made progress on this? I'd love to know how to get in to see how the music loops work.
I tried to look into oodle from the above post, but I genuinely haven't seen anything like these game files before. No file extension or anything.
## Post #4
- Username: Br1ck
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Sep 06, 2022 4:26 am
- Post datetime: 2022-11-24T17:46:36+00:00
- Post Title: Warhammer 40k Darktide [Stingray]

You can unpack the bundle files with this:
[https://github.com/ManShanko/limn](https://github.com/ManShanko/limn)
## Post #5
- Username: Br1ck
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Sep 06, 2022 4:26 am
- Post datetime: 2022-11-24T17:52:56+00:00
- Post Title: Warhammer 40k Darktide [Stingray]

I am currently trying to decompress the translation string files which are supposed to be sjson, some autodesk json thing. Did not figure out how exactly they are compressed though. Maybe I am just dumb.
[9a115e3b8c025ae3.zip](https://xentaxbackup.github.io/file/23067_9a115e3b8c025ae3.zip)
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-11-26T18:16:37+00:00
- Post Title: Warhammer 40k Darktide [Stingray]

This "strings" file is not compressed. You can open it in hex editor (like Hex Workshop) and see for yourself.
You can spot some uncompressed texts like "Path of Trust" or "Au Strategium".

Btw, what is sjson? And why do you think this file can be converted to sjson?
## Post #7
- Username: Br1ck
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Sep 06, 2022 4:26 am
- Post datetime: 2022-11-28T11:45:22+00:00
- Post Title: Warhammer 40k Darktide [Stingray]

According to the documentation of the engine the files should be key value pairs in form of this sjson.
[https://github.com/Autodesk/sjson](https://github.com/Autodesk/sjson)
I do know that you can partially read the file, that was also the case for the compiled luajit code.
The problem is that I need to find the translations for specific keys.
## Post #8
- Username: smashbert
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 17, 2023 3:44 am
- Post datetime: 2023-04-16T19:59:03+00:00
- Post Title: Warhammer 40k Darktide [Stingray]

Hi I am completely new to trying to extract files from games. My goal is just to get a specific 3d model so I can try to make it for myself. 

I downloaded the .exe to unpack files as mentioned below but it doesn't do anything when opened. I'm way out of my league here if anyone could give me some more details as to what I need to do in order to find this specific 3d model?

> Reply from Br1ck ↑Fri Nov 25, 2022 1:46 am at Fri Nov 25, 2022 1:46 am
>
> 
You can unpack the bundle files with this:
https://github.com/ManShanko/limn
## Post #9
- Username: shrubbery
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 19, 2023 2:15 am
- Post datetime: 2023-04-18T18:24:01+00:00
- Post Title: Warhammer 40k Darktide [Stingray]

> Reply from smashbert ↑Mon Apr 17, 2023 3:59 am at Mon Apr 17, 2023 3:59 am
>
> 
Hi I am completely new to trying to extract files from games. My goal is just to get a specific 3d model so I can try to make it for myself. 

I downloaded the .exe to unpack files as mentioned below but it doesn't do anything when opened. I'm way out of my league here if anyone could give me some more details as to what I need to do in order to find this specific 3d model?
Br1ck wrote: ↑Fri Nov 25, 2022 1:46 am
You can unpack the bundle files with this:
https://github.com/ManShanko/limn

I am also new, but I managed something. I created a shortcut of the exe. Then right click on the shortcut and  select properties.
under target, I added  "C:\Program Files (x86)\Steam\steamapps\common\Warhammer 40,000 Darktide\bundle" after limn.exe

Then I ran the exe and it created a folder named "out"  and extracted the files (it took a couple of minutes).
But all the files have strange names, and I don't know which files would contain the 3D models.
I could only identify the textures, which were .dds
## Post #10
- Username: Proxy3089
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 03, 2023 12:55 pm
- Post datetime: 2023-05-03T05:02:05+00:00
- Post Title: Warhammer 40k Darktide [Stingray]

Hello. I have the same goal - to get the models out of the game. And it doesn't work either. Where should I put Limm.exe so that it decrypts the files? Can you suggest? I don't understand at all.
## Post #11
- Username: shrubbery
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 19, 2023 2:15 am
- Post datetime: 2023-05-03T15:56:26+00:00
- Post Title: Warhammer 40k Darktide [Stingray]

So yeah in the end extracting didn't work for me, but I had success ripping the files from the game.

It involves buying a 6 $/€/£ program, some additonal free programs and blender pluggins. It is not as straightforward, but in the end I managed to get the models I wanted. I didn't bother with textures, since as I've read from others, getting the textures is even harder and I don't need them for my purposes.
## Post #12
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2023-05-03T16:16:51+00:00
- Post Title: Warhammer 40k Darktide [Stingray]

Use ninjaripper.
[https://steamcommunity.com/sharedfiles/ ... 2918680531](https://steamcommunity.com/sharedfiles/filedetails/?id=2918680531)
## Post #13
- Username: KillaYushee
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 28, 2021 12:50 pm
- Post datetime: 2023-07-11T02:44:17+00:00
- Post Title: Warhammer 40k Darktide [Stingray]

There are other options, but without using ninjaripper?
