## Post #1
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2011-03-25T20:40:14+00:00
- Post Title: RISK: Factions

Hello!
I would request the big names of this community to check the Data_Core.wad file of RISK:Factions.
I would like to make a translation, but i think EA won't help me, to encrypt & recrypt the file. So i need a compiler. 
If someone have some time please check it for me. Thank you so much!
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-25T21:44:03+00:00
- Post Title: RISK: Factions

you need to provide one of these archives or at least the first part of it (5 or 10 megabytes are enough)
## Post #3
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2011-03-26T12:54:17+00:00
- Post Title: RISK: Factions

> Reply from aluigi
>
> you need to provide one of these archives or at least the first part of it (5 or 10 megabytes are enough)

you mean, part it with total commander, or winrar? Or how? because it is 200mb
## Post #4
- Username: ObfusXor
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Aug 21, 2010 5:52 am
- Post datetime: 2011-03-26T15:01:01+00:00
- Post Title: RISK: Factions

I've already programmed a tool to unpack the wad archieve file from Risk: Factions.

You can find more information about the archieve file and download the tool that i've created, via my blog;

```
obfusxor.wordpress.com
```


By the way,
I don't know if it's okay to give my blog address within this post.
You can let me know if it's not allowed, though.
## Post #5
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2011-03-26T20:59:04+00:00
- Post Title: RISK: Factions

You are a great guy! Thank you!
## Post #6
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2011-03-27T07:27:30+00:00
- Post Title: RISK: Factions

Now, if i decompile the Data_Core.wad. I get all the files.

```
The DATA_CORE\DATA_ALL_PLATFORMS\TEXT.xml
```
 
contains all the text which is in the game. 
But the game read the texts from the above files.

```
TEXT_003.BSF
TEXT_004.BSF
TEXT_005.BSF
TEXT_006.BSF
TEXT_010.BSF

```


If i use a hex editor, i can get the texts, but my language is very different from english so i think i can't translate it via this way. So i need a compiler which can make these files from TEXT.xml, or a decompiler which can extract these files, and then back.

The files upped to megaupload:

```
http://www.megaupload.com/?d=L3V40H8D
```
## Post #7
- Username: ObfusXor
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Aug 21, 2010 5:52 am
- Post datetime: 2011-03-27T09:22:01+00:00
- Post Title: RISK: Factions

The BSF files are the compiled ones of the "text.xml" file. Once you delete those BFS files, the game will be able to read the "text.xml". 

By the way, which language are you translating the game into?
## Post #8
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2011-03-27T10:52:58+00:00
- Post Title: RISK: Factions

I don't think so  I deleted them and i only got this:

So the game don't generate the files from the xml. 
Anyway, i would like to translate to hungarian.
## Post #9
- Username: ObfusXor
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Aug 21, 2010 5:52 am
- Post datetime: 2011-03-27T11:13:57+00:00
- Post Title: RISK: Factions

Honestly, I had tried that and it worked for me. Let's see what i've forgotten to say. 

Edit;


It seems it's working fine for me. I've deleted all those BSF file types. Text.xml is still in the folder named DATA_ALL_PLATFORMS. Once I deleted Text.xml file, too, I got the same erros that are shown in the SS that you have posted.
I'm using STEAM version, by the way.
## Post #10
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2011-03-27T11:30:38+00:00
- Post Title: RISK: Factions

nice  i'll do some research and give another try

edit: Hell, the first time, i renamed, the file to TEXT1.xml, and i forgot it
## Post #11
- Username: m7med
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Mar 31, 2011 7:15 pm
- Post datetime: 2011-03-31T12:55:46+00:00
- Post Title: RISK: Factions

hi ObfusXor 
i want to translate this game to arabic and i have done all what did you say but look



can u tell me how to fix this add arabic font
## Post #12
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2011-04-01T13:00:24+00:00
- Post Title: RISK: Factions

i have the same problem with őű but i can use öü  but it would be great if we can edit the font files.
They are located at: DATA_CORE\DATA_ALL_PLATFORMS\TEXTURES\FONT
The fonts are in .IMG format... that's all i know at this time
## Post #13
- Username: m7med
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Mar 31, 2011 7:15 pm
- Post datetime: 2011-04-01T16:01:03+00:00
- Post Title: RISK: Factions

THANKS FOR HELP BUT HOW I CAN OPEN THIS FILE FONT.IMG
## Post #14
- Username: ObfusXor
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Aug 21, 2010 5:52 am
- Post datetime: 2011-04-01T16:25:34+00:00
- Post Title: RISK: Factions

The IMG file types for the fonts contain both font image and font data (char descriptions, and additional data)
The font images are compressed with custom compression methods, not sure though. 

Even if we decompress the font images, then compressing them will be another problem to solve, 
As I assume that the exetuable file of the game contains only the decompression methods for the images, not the compression ones,
It would be really useless to program a tool just to decompress them. 

(Ohh, I hear you say "Why don't you reverse the decompression method?", Nah. I don't have the time for it.)

Ps.

I thought, you'd like to see the font image, though.
## Post #15
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2011-04-02T11:02:16+00:00
- Post Title: RISK: Factions

obfuxor, if you have some time, can you please make an another version of your .wad decompiler which works on windows 7 64 bit, because if i would publish my translation, it will make a lot of problem to a lot of people. Thank you!
## Post #16
- Username: ObfusXor
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Aug 21, 2010 5:52 am
- Post datetime: 2011-04-02T16:37:10+00:00
- Post Title: Re: RISK: Factions

It should already work on Windows 7 64-bit.
Could you tell me, what kind of error do you get when you try to use it on the 64-bit OS?
## Post #17
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2011-04-02T19:21:02+00:00
- Post Title: Re: RISK: Factions

It starts but if i input the file name and press enter, it writes out everything ok, and dead before finish the extraction of the first file, no error message, nothing...
It works perfectly on my laptop with win 7 32 bit, anyway, there is a chance that the problem is in my pc
## Post #18
- Username: ObfusXor
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Aug 21, 2010 5:52 am
- Post datetime: 2011-04-07T18:03:28+00:00
- Post Title: Re: RISK: Factions

Your message is not quite helpful to solve the problem without testing the tool here on my own, hunpatrik.
I don't have Windows7 64bit installed on my machine.
But, i will try it on VM when i have free time.

By the way, I've already programmed a tool for TDX <-> DDS conversions.
I'm also tring to get more information about the font files (.IMG)...
When I finish programming the font parser tool, i will release them both on my blog.
Maybe a new version for WAD archive unpacker, too, to be able fix your problem.
## Post #19
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2011-04-08T08:32:35+00:00
- Post Title: Re: RISK: Factions

Thank you  
I will do the test today on vmware, i have time for it
## Post #20
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2011-05-13T16:19:41+00:00
- Post Title: Re: RISK: Factions

Obfusxor i need your help!
I'm finished the translating of Risk Factions, but i need some help with your tool. 
I would like to ask you to please reprogram the tool, to can it work from commandline
for example "tool.exe -e C:\Data_Core.wad" or something like that, it's very importat to me. Thank you!
## Post #21
- Username: ObfusXor
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Aug 21, 2010 5:52 am
- Post datetime: 2011-05-14T21:05:47+00:00
- Post Title: Re: RISK: Factions

Thanks for reporting the bug, hunpatrik.
I've released a new version of the application that you can now use the application with command-line arguments without any problem.
## Post #22
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2011-05-14T22:24:52+00:00
- Post Title: Re: RISK: Factions

Thank you for the fast reply, and help
## Post #23
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2011-05-15T10:19:24+00:00
- Post Title: Re: RISK: Factions

Now it works great on 32bit, but on x64 it only says "Unknow operation type" can you please fix it?
## Post #24
- Username: ObfusXor
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Aug 21, 2010 5:52 am
- Post datetime: 2011-05-15T11:33:26+00:00
- Post Title: Re: RISK: Factions

EXE compressor that I used for the application was buggy for x64, i think. 
I've tried to fix it but I can't test it here right now.
Please check the newest version released and if you still have any other problems and let me know.
## Post #25
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-05-15T12:28:03+00:00
- Post Title: Re: RISK: Factions

Nope, nothing changed. Try to not compress.
## Post #26
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2011-05-15T15:20:28+00:00
- Post Title: Re: RISK: Factions

yes if i use "tool.exe c:\data_core.wad" i get:  "Unknow operation type"  (i use this on 32bit)
and if i use "tool.exe -e c:\data_core.wad" i get:
"the archive file has been opened successfully.
pls wait while the files are being extracted.
data_core\...ach9_d.jpg" and the program stops
anyway if i use this type i get "the file is missing c:\-e" so please fix the first command
## Post #27
- Username: ObfusXor
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Aug 21, 2010 5:52 am
- Post datetime: 2011-05-15T16:52:58+00:00
- Post Title: Re: RISK: Factions

I've fixed all the problems you've mentioned, hunpatrik.
I've tested the application on Win7 x64, it's working fine here.
Please check the blog for the newest version of the application.
## Post #28
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2011-05-15T17:19:55+00:00
- Post Title: Re: RISK: Factions

> Reply from ObfusXor
>
> I've fixed all the problems you've mentioned, hunpatrik.
I've tested the application on Win7 x64, it's working fine here.
Please check the blog for the newest version of the application.

You didn't put out new link
## Post #29
- Username: ObfusXor
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Aug 21, 2010 5:52 am
- Post datetime: 2011-05-15T17:24:01+00:00
- Post Title: Re: RISK: Factions

Check again, I did pack the wrong version of the application, and deleted it. 
I'm really tired today, that's why mistakes are everywhere.
## Post #30
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2011-05-15T18:05:22+00:00
- Post Title: Re: RISK: Factions

ofcourse  works great thank you
