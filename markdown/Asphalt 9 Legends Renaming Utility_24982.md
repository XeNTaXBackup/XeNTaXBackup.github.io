## Post #1
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-01-23T16:32:26+00:00
- Post Title: Asphalt 9: Legends Renaming Utility

Renaming utility for Asphalt 9: Legends hash sequence files. Python 2/3 is required.

Usage:
1. extract all assets in all packages (obbs/split apks or whatever) and place all hash sequence files into a single folder;
2. place "restoreFileHierarchy.py" and the name mapping file into the above folder;
3. start cmd.exe from the above folder and run the following command:

```

```

where map_file is the path of the name mapping file (see following posts), and input_dir is the the path of the hash sequence files, and output_dir is the path for the renamed files. If not specified, map_file would be "manifest.map", and input_dir & output_dir both set to the path where the script is executed.
So if your name mapping file is indeed named "manifest.map" then you can simply just run

```

```

and that's it.
4. use the BMS script to assign extensiones to the remaining files that're not renamed. Files would then be copied into a folder named "nameless".
[A9RenameUtility.zip](https://xentaxbackup.github.io/file/21665_A9RenameUtility.zip)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-01-23T16:37:31+00:00
- Post Title: Asphalt 9: Legends Renaming Utility

Converted manifest map file that combined all files from v2.9.0 of the China version and 8000+ files from v3.2.2 of the Worldwide version (most are duplicate):


 manifest.7z
(248.42 KiB) Downloaded 86 times



Complete manifest map for v3.5.2a:
[viewtopic.php?p=186018#p186018](viewtopic.php?p=186018#p186018)

Complete manifest map for v3.6.3a:
[viewtopic.php?p=186210#p186210](viewtopic.php?p=186210#p186210)

If a password is required, you can either try guessing it, or send me a message (if that's possible) or leave a comment here.
Either way, read the last line of my signature!
## Post #3
- Username: Vitalik
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Apr 07, 2021 5:03 pm
- Post datetime: 2022-01-26T20:16:56+00:00
- Post Title: Asphalt 9: Legends Renaming Utility

> Reply from Bigchillghost ↑Mon Jan 24, 2022 12:32 am at Mon Jan 24, 2022 12:32 am
>
> 
Renaming utility for Asphalt 9: Legends hash sequence files. Python 2/3 is required.

Very thank for your hard work with this game.
I try and all work good. Now I have GameOptions.json file. I know decode this file in normal format is big problem.I write some people from russian forum 4pda.to but they also cant decode in normal view. 
On holidays I try change original  GameOptions.json other file GameOptions.json with my settings from old version game.In normal view format.
Maybe this can works in game...
Need try.

Thank for all help.
## Post #4
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2022-01-28T14:36:23+00:00
- Post Title: Asphalt 9: Legends Renaming Utility

I'm so thankful for your fantastic work. This script works just excellent. It's so easy now to find all the necessary files
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-01-29T01:08:32+00:00
- Post Title: Asphalt 9: Legends Renaming Utility

> Reply from TomWin ↑Fri Jan 28, 2022 10:36 pm at Fri Jan 28, 2022 10:36 pm
>
> 
I'm so thankful for your fantastic work
I hate to put this straightforward but do me a favor and hit the thank button will you?!! Actions always speak louder than fancy words.
## Post #6
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2022-01-31T13:42:14+00:00
- Post Title: Asphalt 9: Legends Renaming Utility

Sure. Thank you again!

> Reply from Bigchillghost ↑Sat Jan 29, 2022 9:08 am at Sat Jan 29, 2022 9:08 am
>
> 
TomWin wrote: ↑Fri Jan 28, 2022 10:36 pm
I'm so thankful for your fantastic work

I hate to put this straightforward but do me a favor and hit the thank button will you?!! Actions always speak louder than fancy words.
## Post #7
- Username: Slad
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jan 29, 2022 1:21 am
- Post datetime: 2022-02-02T17:37:46+00:00
- Post Title: Asphalt 9: Legends Renaming Utility

> Reply from Bigchillghost ↑Mon Jan 24, 2022 12:32 am at Mon Jan 24, 2022 12:32 am
>
> 
Renaming utility for Asphalt 9: Legends hash sequence files. Python 2/3 is required.

Usage:
1. extract all assets in all packages (obbs/split apks or whatever) and place all hash sequence files into a single folder;
2. place "restoreFileHierarchy.py" and the name mapping file into the above folder;
3. start cmd.exe from the above folder and run the following command:
Code: Select allpython restoreFileHierarchy.py [map_file] [input_dir] [output_dir]

where map_file is the path of the name mapping file (see following posts), and input_dir is the the path of the hash sequence files, and output_dir is the path for the renamed files. If not specified, map_file would be "manifest.map", and input_dir & output_dir both set to the path where the script is executed.
So if your name mapping file is indeed named "manifest.map" then you can simply just run
Code: Select allpython restoreFileHierarchy.py

and that's it.
4. use the BMS script to assign extensiones to the remaining files that're not renamed. Files would then be copied into a folder named "nameless".

Hey, i can't understand what to put on the "python restoreFileHierarchy.py [map_file] [input_dir] [output_dir]" to make it work. Can you give an example? I've done everything right, place the files in the right places and etc.
## Post #8
- Username: Slad
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jan 29, 2022 1:21 am
- Post datetime: 2022-02-02T17:53:06+00:00
- Post Title: Asphalt 9: Legends Renaming Utility

Also i want to add, i'm running the "python restoreFileHierarchy.py", because the map file is named manifest. When i run it in cmd it says, that 0 files have been renamed among the 18708 in list. What should i do?
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-02-03T04:09:36+00:00
- Post Title: Asphalt 9: Legends Renaming Utility

Well first of all, it is suggested NOT to quote the full context of the entire main post coz it might be updated in the future and you're making the thread too overwhelmed and more difficult for mantainance. Also it's usually unclear which part of the context you're refering to, or if you've actually read and absorbed it.

> Reply from Slad ↑Thu Feb 03, 2022 1:37 am at Thu Feb 03, 2022 1:37 am
>
> 
i can't understand what to put on the "python restoreFileHierarchy.py [map_file] [input_dir] [output_dir]" to make it work. Can you give an example? I've done everything right, place the files in the right places and etc.
The "[]" is a habitual notation for optional arguments and "<>" is usually used as a placeholder of required arguments. The meaning of each argument has already been explained in the first post, but if you just want an example, here's one:

```

```

Mind the double quotation marks coz they're necessary for path with spaces.

> Reply from Slad ↑Thu Feb 03, 2022 1:53 am at Thu Feb 03, 2022 1:53 am
>
> 
Also i want to add, i'm running the "python restoreFileHierarchy.py", because the map file is named manifest. When i run it in cmd it says, that 0 files have been renamed among the 18708 in list. What should i do?
I saw in the other thread you've got some files renamed so the question is, what did you do exactly regarding extracting the unnamed files? You're NOT supposed to use the Zip64Unpacker script in [this post](viewtopic.php?p=153848#p153848) for that task.
## Post #10
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2022-02-10T19:20:16+00:00
- Post Title: Asphalt 9: Legends Renaming Utility

Pardon, where can I find manifest.map from v3.3.5 in game files or at least information about file names to add it to current manifest.map?

Thanks in advance.
## Post #11
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-02-11T00:53:48+00:00
- Post Title: Asphalt 9: Legends Renaming Utility

> Reply from TomWin ↑Fri Feb 11, 2022 3:20 am at Fri Feb 11, 2022 3:20 am
>
> 
where can I find manifest.map from v3.3.5 in game files or at least information about file names to add it to current manifest.map?
Read the 2nd paragraph in this post:
[viewtopic.php?p=181403#p181403](viewtopic.php?p=181403#p181403)

Nowadays it can only be partially dumped through memory.
## Post #12
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2022-06-20T07:21:28+00:00
- Post Title: Asphalt 9: Legends Renaming Utility

hey guys, can anyone pls update the manifest.map file as there's latest version 3.5.2a of Asphalt 9 game?
## Post #13
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-07-20T14:01:00+00:00
- Post Title: Asphalt 9: Legends Renaming Utility

Complete manifest.map for v3.5.2a here:


 manifest.7z
(198.79 KiB) Downloaded 50 times



What's left unrenamed are the original encrypted manifest files of each split package so you can just ignore them.
## Post #14
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-07-31T07:01:37+00:00
- Post Title: Asphalt 9: Legends Renaming Utility

Complete manifest.map for v3.6.3a:


 manifest.7z
(207.24 KiB) Downloaded 85 times
## Post #15
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2022-08-05T12:10:36+00:00
- Post Title: Asphalt 9: Legends Renaming Utility

I'm not able to extract the latest manifest.map file since winrar asked me for a password.
## Post #16
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-08-05T15:50:57+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

> Reply from UB833 ↑Fri Aug 05, 2022 8:10 pm at Fri Aug 05, 2022 8:10 pm
>
> 
winrar asked me for a password.
You knew the magic words.
## Post #17
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2022-08-06T03:39:25+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

> Reply from Bigchillghost ↑Fri Aug 05, 2022 11:50 pm at Fri Aug 05, 2022 11:50 pm
>
> 
UB833 wrote: ↑Fri Aug 05, 2022 8:10 pm
winrar asked me for a password.

You knew the magic words.

BTW I have no idea that I knew the magic words, but seriously I don't even know the password to extract the archive.
## Post #18
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-08-06T05:33:51+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

> Reply from UB833 ↑Sat Aug 06, 2022 11:39 am at Sat Aug 06, 2022 11:39 am
>
> 
BTW I have no idea that I knew the magic words
Read the last line of my signature.
## Post #19
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2022-08-06T11:16:41+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

> Reply from Bigchillghost ↑Sat Aug 06, 2022 1:33 pm at Sat Aug 06, 2022 1:33 pm
>
> 
UB833 wrote: ↑Sat Aug 06, 2022 11:39 am
BTW I have no idea that I knew the magic words

Read the last line of my signature.

I can't see your last line of your signature bcuz I'm super dumb, is it red font or the blue?
## Post #20
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2022-08-10T12:22:22+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

> Reply from Bigchillghost ↑Sun Jul 31, 2022 3:01 pm at Sun Jul 31, 2022 3:01 pm
>
> 
Complete manifest.map for v3.6.3a:
manifest.7z
Hi, thanks for that update. I was doing it manually in notepad only for models, but it's a lot of work. I have no idea how to dump memory 

However this last manifest is password protected. Could you please help with unzipping it?

Thanks in advance.
## Post #21
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-08-10T12:56:29+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

> Reply from TomWin ↑Wed Aug 10, 2022 8:22 pm at Wed Aug 10, 2022 8:22 pm
>
> 
However this last manifest is password protected. Could you please help with unzipping it?
PMed you.
## Post #22
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-08-10T13:40:08+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

> Reply from Bigchillghost ↑Sat Aug 06, 2022 1:33 pm at Sat Aug 06, 2022 1:33 pm
>
> 
Read the last line of my signature.

> Reply from UB833 ↑Sat Aug 06, 2022 7:16 pm at Sat Aug 06, 2022 7:16 pm
>
> 
is it red font or the blue?
Very clever comment indeed. I see the hilariousness of it now... 

But's your choise.
## Post #23
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2022-08-10T14:41:29+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

I think I've tried every combination I could lol...can't figure out the password. Help pls!

EDIT: BTW the game is available on Steam as well now...with files categorized. This will save some more time!
.pack are easily extracted by renaming to .zip then run the renaming utility.   Thanks for this great tool, saves a lot of time.



"mdc.pack" , "mde.pack & "tex.pack" are the ones we need mostly.
## Post #24
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-08-10T16:06:38+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

> Reply from taruncreation ↑Wed Aug 10, 2022 10:41 pm at Wed Aug 10, 2022 10:41 pm
>
> 
I think I've tried every combination I could lol...can't figure out the password. Help pls!
PM sent.
## Post #25
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2022-08-10T16:28:57+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

I tried converting the texture from the Steam version...shows "error allocating memory"...what am I doing wrong?
[car_Italdesign_DaVinci_details_nm.tga.jtex.7z](https://xentaxbackup.github.io/file/22624_car_Italdesign_DaVinci_details_nm.tga.jtex.7z)
## Post #26
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-08-11T01:00:57+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

> Reply from taruncreation ↑Thu Aug 11, 2022 12:28 am at Thu Aug 11, 2022 12:28 am
>
> shows "error allocating memory"...what am I doing wrong?
Did you update to the latest version?
[viewtopic.php?p=181929#p181929](viewtopic.php?p=181929#p181929)
## Post #27
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2022-08-11T15:48:30+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

Thanks , I didn't had the latest version...but now the converted .pvr is blank when I open it in PVRTexTool.

[https://app.box.com/s/7bqmf1g1xd2074ls0kp3crxres96o88n](https://app.box.com/s/7bqmf1g1xd2074ls0kp3crxres96o88n)
## Post #28
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-08-11T23:46:54+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

> Reply from taruncreation ↑Thu Aug 11, 2022 11:48 pm at Thu Aug 11, 2022 11:48 pm
>
> 
but now the converted .pvr is blank when I open it in PVRTexTool.
They're using different pixel formats for these textures. You should try with the Android version. No time for further research on that atm, sorry.
## Post #29
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-08-12T15:53:48+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

Apparently PC version from steam is more organized and it's still shipped with manifests included. 

How to: extract "pack" with 7zip, use python script to rename extracted files (for more info read the first post, default manifest name is "__manifest_NX_100__" here), convert jtex/tga textures to dds with quickbms script. 
Credits to Bigchillghost for renaming script.



 Asphalt9 tools PC.zip
(1.32 KiB) Downloaded 62 times
## Post #30
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2022-08-14T02:33:14+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

> Reply from Spiritovod ↑Fri Aug 12, 2022 11:53 pm at Fri Aug 12, 2022 11:53 pm
>
> 
Apparently PC version is more organized and it's still shipped with manifests included. 

How to: extract "pack" with 7zip, use python script to rename extracted files (for more info read the first post, default manifest name is "__manifest_NX_100__" here), convert jtex/tga textures to dds with quickbms script. 
Credits to Bigchillghost for renaming script.


Asphalt9 tools PC.zip

Works like charm , thanks a lot
## Post #31
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2022-08-16T13:18:55+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

Sorry but how to copy files from WindowsApps to another folder or how to open these? I have access to WindowsApps but I'm unable to open/copy these files. Thanks in advance.
## Post #32
- Username: Mike Oxmaul
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Dec 05, 2014 9:54 pm
- Post datetime: 2022-08-17T20:58:20+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

Can you send me a password for manifest.7z 3.6.3a, please?
## Post #33
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2022-08-18T13:49:17+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

> Reply from TomWin ↑Tue Aug 16, 2022 9:18 pm at Tue Aug 16, 2022 9:18 pm
>
> 
Sorry but how to copy files from WindowsApps to another folder or how to open these? I have access to WindowsApps but I'm unable to open/copy these files. Thanks in advance.

This might help :
[https://answers.microsoft.com/en-us/win ... df85e265a9](https://answers.microsoft.com/en-us/windows/forum/all/windows-10-apps-folder-permission-to-copy-and/fcb7db14-3c19-4ad4-8fb1-b0df85e265a9) 

I did something similar some time back. But still I was able to copy from A8 but not A9...i tried everything but copying from A9 PC version was impossible. Best would be to use the Steam version now , not much Hassle.
## Post #34
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2022-09-12T05:29:05+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

Can anyone help me?

I used the manifest.map file and A9Tool but one of the model has 46 KB while jmodel has 1.5MB. Anyone know why? The version of A9 is 3.6.3a.

[https://mega.nz/file/9LxXAazC#fTbRY5vQW ... 9Ntcd1-MVI](https://mega.nz/file/9LxXAazC#fTbRY5vQWYh6nPpOlA27rEFfC7CR7IyTh9Ntcd1-MVI)

Thx in advance
## Post #35
- Username: Koce
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Apr 14, 2010 11:33 am
- Post datetime: 2022-10-01T05:19:53+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

> Reply from Bigchillghost ↑Mon Jan 24, 2022 12:37 am at Mon Jan 24, 2022 12:37 am
>
> 
Converted manifest map file that combined all files from v2.9.0 of the China version and 8000+ files from v3.2.2 of the Worldwide version (most are duplicate):
manifest.7z


Complete manifest map for v3.5.2a:
viewtopic.php?p=186018#p186018

Complete manifest map for v3.6.3a:
viewtopic.php?p=186210#p186210

If a password is required, you can either try guessing it, or send me a message (if that's possible) or leave a comment here.
Either way, read the last line of my signature!

Can you send me the password?
## Post #36
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2022-10-01T12:30:51+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

> Reply from Koce ↑Sat Oct 01, 2022 1:19 pm at Sat Oct 01, 2022 1:19 pm
>
> 
Bigchillghost wrote: ↑Mon Jan 24, 2022 12:37 am
Converted manifest map file that combined all files from v2.9.0 of the China version and 8000+ files from v3.2.2 of the Worldwide version (most are duplicate):
manifest.7z


Complete manifest map for v3.5.2a:
viewtopic.php?p=186018#p186018

Complete manifest map for v3.6.3a:
viewtopic.php?p=186210#p186210

If a password is required, you can either try guessing it, or send me a message (if that's possible) or leave a comment here.
Either way, read the last line of my signature! 


Can you send me the password?

You need to guess it by yourself.. I'll give you the hint but I won't tell you the answer. "What would you say to your family/friends when you already got something that you actually wanted or you got support from something that you wanted to have?" Again, don't submit your answer to the hint, otherwise it'll be a huge spoiler
## Post #37
- Username: Koce
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Apr 14, 2010 11:33 am
- Post datetime: 2022-10-02T05:27:46+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

> Reply from UB833 ↑Sat Oct 01, 2022 8:30 pm at Sat Oct 01, 2022 8:30 pm
>
> 
Koce wrote: ↑Sat Oct 01, 2022 1:19 pm
Bigchillghost wrote: ↑Mon Jan 24, 2022 12:37 am
Converted manifest map file that combined all files from v2.9.0 of the China version and 8000+ files from v3.2.2 of the Worldwide version (most are duplicate):
manifest.7z


Complete manifest map for v3.5.2a:
viewtopic.php?p=186018#p186018

Complete manifest map for v3.6.3a:
viewtopic.php?p=186210#p186210

If a password is required, you can either try guessing it, or send me a message (if that's possible) or leave a comment here.
Either way, read the last line of my signature! 


Can you send me the password?


You need to guess it by yourself.. I'll give you the hint but I won't tell you the answer. "What would you say to your family/friends when you already got something that you actually wanted or you got support from something that you wanted to have?" Again, don't submit your answer to the hint, otherwise it'll be a huge spoiler
Can you send it to me via PM?

Can
## Post #38
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-10-05T13:34:04+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

In case if someone is interested, I've checked latest PC global version from steam (updated a few hours ago) and manifests are still included there.
## Post #39
- Username: Koce
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Apr 14, 2010 11:33 am
- Post datetime: 2022-10-06T12:36:43+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

> Reply from Spiritovod ↑Wed Oct 05, 2022 9:34 pm at Wed Oct 05, 2022 9:34 pm
>
> 
In case if someone is interested, I've checked latest PC global version from steam (updated a few hours ago) and manifests are still included there.
Yes they are i just get Jaguar Project 8
## Post #40
- Username: Nowzly
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Dec 07, 2022 10:12 pm
- Post datetime: 2022-12-07T15:00:15+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

> Reply from taruncreation ↑Thu Aug 18, 2022 9:49 pm at Thu Aug 18, 2022 9:49 pm
>
> 
TomWin wrote: ↑Tue Aug 16, 2022 9:18 pm
Sorry but how to copy files from WindowsApps to another folder or how to open these? I have access to WindowsApps but I'm unable to open/copy these files. Thanks in advance.


This might help :
https://answers.microsoft.com/en-us/win ... df85e265a9 

I did something similar some time back. But still I was able to copy from A8 but not A9...i tried everything but copying from A9 PC version was impossible. Best would be to use the Steam version now , not much Hassle.

You can use this to bypass encrypted file system protection:
[https://github.com/Wunkolo/UWPDumper](https://github.com/Wunkolo/UWPDumper)

The .pack files are practically the same as Steam version , but the manifest is encrypted.
## Post #41
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-04-05T06:06:15+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

any update on renaming script for v 4.0.0j? and can anyone fix the Vanda Dendrobium model being 48kb after extract?
## Post #42
- Username: Mike Oxmaul
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Dec 05, 2014 9:54 pm
- Post datetime: 2023-05-10T13:38:08+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

Hi, can anyone help me with proper unpacking a PC (Steam) version of Asphalt 9?
I've seen a message about manifest file, that this is should be stored inside, but I can't find it.
I've downloaded a game, then unpacked all *.pack files through 7-Zip into one folder and can't find "__manifest_NX_100__" file or something with readable name which can look similar to what I need. The root folder with the game also doesn't have the manifests, it looks like a folder with some kind of CEF application.
I've also tried to find it in .exe resources, but still can't find it.
So how can I find that manifest? If it's stored inside game memory when the game is launched, what data I should type to find a result? Is that a XML? JSON? Something else? Usually I use Cheat Engine to find something like that in the memory.
## Post #43
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-05-10T15:22:08+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

@Mike Oxmaul: Steam version from 6 Feb 2023 is the last one where they've shipped manifests within packages. In more recent ones it's unwrapped in memory at runtime, like for mobile versions. You can still get older versions through depot downloader if needed.
## Post #44
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-07-13T07:25:08+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

any update on dump script for newer and recent version of Asphalt 9?
## Post #45
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-09-28T03:35:08+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

dead forum bcuz of BigChillGhost being busy with something else. for update of A9 renaming script for recent version of A9

EDIT: typo for being word beig
## Post #46
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-09-29T09:18:35+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

No idea why you're complaining.   The tutorial had been released already last year:
[viewtopic.php?t=26100](viewtopic.php?t=26100)
## Post #47
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-09-29T09:36:19+00:00
- Post Title: Re: Asphalt 9: Legends Renaming Utility

> No idea why you're complaining.  The tutorial had been released already last year:
>
> viewtopic.php?t=26100
I'm extremely sorry, I'm not complaining tbh.  it's just that I'm lacking more 3d models to dump from the recent update like the CC850 and other cars and the script is old enough to stop support of 4.3.0h version of Asphalt 9.

EDIT: and I didn't knew about that tutorial which I don't have experience with.
