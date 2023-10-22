## Post #1
- Username: Smakkohooves
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jan 16, 2016 2:34 am
- Post datetime: 2016-10-16T05:09:46+00:00
- Post Title: Open and convert that VTEX_C files

I'm working on a project that i wish do from a long time,
But actually i'm stuck... :/

How i can easily convert these files, and relatives:
VMDL_C
VTEX_C
VMESH_C
VMAT_C
VAGRP_C
[OT: also VSND_C]

I find out that must be decompiled to "classic" valve file
But i don't find a way to do it.

I use win XP x86...

Someone can help me?

I need some library pack/plugins to open it?
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-10-17T16:29:03+00:00
- Post Title: Open and convert that VTEX_C files

You can open most the *_C files with this program:
[https://steamdatabase.github.io/ValveResourceFormat/](https://steamdatabase.github.io/ValveResourceFormat/)
## Post #3
- Username: Smakkohooves
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jan 16, 2016 2:34 am
- Post datetime: 2016-10-18T00:31:00+00:00
- Post Title: Open and convert that VTEX_C files

> Reply from herbert3000
>
> You can open most the *_C files with this program:
https://steamdatabase.github.io/ValveResourceFormat/

He tell me that is'nt a xWin32 valid application....

What i have to do?
## Post #4
- Username: OperateSystemP
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 04, 2015 9:26 am
- Post datetime: 2016-10-18T01:09:32+00:00
- Post Title: Open and convert that VTEX_C files

> Reply from Smakkohooves
>
> herbert3000 wrote:You can open most the *_C files with this program:
https://steamdatabase.github.io/ValveResourceFormat/

He tell me that is'nt a xWin32 valid application....

What i have to do?
Only thing I can think of is maybe upgrading your computer. I see no real easy way to rip things using an outdated OS like XP.
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-18T01:46:51+00:00
- Post Title: Open and convert that VTEX_C files

> Reply from OperateSystemP
>
>  .... an outdated OS like XP.
outdated in terms of products a company is trying to push on everyone 
so they can stay in business? maybe, but XP is definitely not obsolete!  

Smakkohooves, you'll have to download the source and modify and compile it for your machine
## Post #6
- Username: Smakkohooves
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jan 16, 2016 2:34 am
- Post datetime: 2016-10-18T03:43:29+00:00
- Post Title: Open and convert that VTEX_C files

> Reply from AceWell
>
> 
Smakkohooves, you'll have to download the source and modify and compile it for your machine
I have no idea how to do that...

Is a tutorial somewere? 
What programs i have to use to do that?
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-18T04:13:15+00:00
- Post Title: Open and convert that VTEX_C files

don't know, i never had any luck compiling source code for anything except for offzip   
the source looks like C# and appears to target .NET 4.5 which is Microsoft's silver bullet for XP users  

if you have any of those VTEX_C samples i will take a look and see about a script  
the source mentions LZMA compression
## Post #8
- Username: Smakkohooves
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jan 16, 2016 2:34 am
- Post datetime: 2016-10-18T07:54:17+00:00
- Post Title: Open and convert that VTEX_C files

Here a sample of the "_c" files
[Samples Of _c Files.zip](https://xentaxbackup.github.io/file/11802_Samples Of _c Files.zip)
## Post #9
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-10-18T09:27:53+00:00
- Post Title: Open and convert that VTEX_C files

> Reply from Smakkohooves
>
> Here a sample of the "_c" files
Definitely not texture files. Looks like a compiled XML file.
## Post #10
- Username: Smakkohooves
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jan 16, 2016 2:34 am
- Post datetime: 2016-10-18T11:19:46+00:00
- Post Title: Open and convert that VTEX_C files

> Reply from Gh0stBlade
>
> Smakkohooves wrote:Here a sample of the "_c" files
Definitely not texture files. Looks like a compiled XML file.
I put the smallest files in to a zip, im sure that is textures.
The files are: model,texture and sound.
These are small but the 90% of the files are from 1mb.
## Post #11
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-18T17:14:00+00:00
- Post Title: Open and convert that VTEX_C files

> Reply from Smakkohooves
>
> Here a sample of the "_c" files
well the textures aren't compressed and they are just normal dxt image data, your samples
are all dxt5 they just have custom headers with a lot of fluff, the largest mip is last in the array
## Post #12
- Username: Smakkohooves
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jan 16, 2016 2:34 am
- Post datetime: 2016-10-18T18:38:53+00:00
- Post Title: Open and convert that VTEX_C files

> Reply from AceWell
>
> Smakkohooves wrote:Here a sample of the "_c" files
well the textures aren't compressed and they are just normal dxt image data, your samples
are all dxt5 they just have custom headers with a lot of fluff, the largest mip is last in the array
 So? What i have to do to open these files?
Maybe i have to upload other "_C" files, more bigger,
 So maybe it can be more "clear".

I usually for these things use crowbar, noesis and vtf viewer.
## Post #13
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-10-18T21:07:06+00:00
- Post Title: Open and convert that VTEX_C files

Please check if this works:
[https://www.mediafire.com/?4yy5jhy3ublxc4m](https://www.mediafire.com/?4yy5jhy3ublxc4m)
I compiled the project for x86 and changed the target to .NET 4.0 (which is available for WinXP, right?)
Edit: uploaded the correct version
## Post #14
- Username: Smakkohooves
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jan 16, 2016 2:34 am
- Post datetime: 2016-10-19T01:53:38+00:00
- Post Title: Open and convert that VTEX_C files

> Reply from herbert3000
>
> Please check if this works:
https://www.mediafire.com/?ebfnbbbvec1x1nx
I compiled the project for x86 and changed the target to .NET 4.0 (which is available for WinXP, right?)
I have  4.5 actually, (i think, i check later)
I'll try it and tell you, thanks.
## Post #15
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-19T03:31:17+00:00
- Post Title: Open and convert that VTEX_C files

> Reply from Smakkohooves
>
> I use win XP x86...
> Reply from Smakkohooves
>
> I have  4.5 actually
impossible

what is the name of the game and platform these sample files came from?

edit
found this too
[https://github.com/tranek/vtex_c2tga](https://github.com/tranek/vtex_c2tga)
needs to be compiled though



edit again
*updated Oct 23*
made a Noesis python script to open your vtex_c texture samples for fun 


 tex_TheLab_vtex_c.zip
(895 Bytes) Downloaded 74 times



only supports dxt1 and dxt5 for now because i had no other sample types
## Post #16
- Username: Smakkohooves
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jan 16, 2016 2:34 am
- Post datetime: 2016-10-19T04:51:47+00:00
- Post Title: Re: Open and convert that VTEX_C files

> Reply from Smakkohooves
>
> I have  4.5 actually
impossible[/quote]
You're right im having the 4.0

> Reply from AceWell
>
> 
what is the name of the game and platform these sample files came from?
The lab, on steam, for HTC Vr... 

> Reply from AceWell
>
> 
found this too
https://github.com/tranek/vtex_c2tga
needs to be compiled though
made a Noesis python script to open your vtex_c texture samples for fun 
only supports dxt5 because i had no other types of samples and didn't know the game name so i just called it Valve
Sorry but i no have pratice with compiling/scripting, or pyton,
I just have used "xvi32" for a tiny edit on several files....

Anyway i try "project for x86 and changed the target to .NET 4.0" but still gave me that damn x32 error .....
## Post #17
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-19T05:28:26+00:00
- Post Title: Re: Open and convert that VTEX_C files

> Reply from Smakkohooves
>
> Sorry but i no have pratice with compiling/scripting, or pyton,
guess you didn't see the Noesis python script i attached to my last post, no compiling needed   
i'm gonna go ahead and change the name of it to TheLab

i need more samples of different types so i can add support for dxt1, rgba32 or whatever other formats are there
## Post #18
- Username: Smakkohooves
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jan 16, 2016 2:34 am
- Post datetime: 2016-10-19T06:33:26+00:00
- Post Title: Re: Open and convert that VTEX_C files

> Reply from AceWell
>
> I need more samples of different types so i can add support for dxt1, rgba32 or whatever other formats are there
Here new files
[https://mega.nz/#!cEgSQYwa!NAkjDAKVp2jj ... AA1_cmS-J4](https://mega.nz/#!cEgSQYwa!NAkjDAKVp2jj8IGGTKWIPyMf8l3z3OeTZAA1_cmS-J4)
## Post #19
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-19T08:31:25+00:00
- Post Title: Re: Open and convert that VTEX_C files

okay i updated the script here for dxt1 support, still need some rgba samples though   
[viewtopic.php?p=123637#p123637](http://forum.xentax.com/viewtopic.php?p=123637#p123637)
## Post #20
- Username: Smakkohooves
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jan 16, 2016 2:34 am
- Post datetime: 2016-10-19T09:08:43+00:00
- Post Title: Re: Open and convert that VTEX_C files

> Reply from AceWell
>
> still need some rgba samples though
I'm feeling dumb, what you need?
## Post #21
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-19T21:50:51+00:00
- Post Title: Re: Open and convert that VTEX_C files

i just need you to run as many vtex_c textures as you can through the script to 
see which ones still don't work, then you can upload those so i can add support  





edit

> Reply from herbert3000
>
> Please check if this works:
https://www.mediafire.com/?ebfnbbbvec1x1nx
I compiled the project for x86 and changed the target to .NET 4.0 (which is available for WinXP, right?)
Dependency Walker identifies it as 64-bit
## Post #22
- Username: Smakkohooves
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jan 16, 2016 2:34 am
- Post datetime: 2016-10-20T07:39:21+00:00
- Post Title: Re: Open and convert that VTEX_C files

> Reply from AceWell
>
> i just need you to run as many vtex_c textures as you can through the script to 
see which ones still don't work, then you can upload those so i can add support
Uh yeah, now i start to convert every file, after i send you 
The files that gave me issues
## Post #23
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-10-20T10:54:24+00:00
- Post Title: Re: Open and convert that VTEX_C files

> Reply from AceWell
>
> Dependency Walker identifies it as 64-bitYou are right, thanks for the info! I uploaded the wrong version 
This is the correct one (x86):
[https://www.mediafire.com/?4yy5jhy3ublxc4m](https://www.mediafire.com/?4yy5jhy3ublxc4m)
## Post #24
- Username: Smakkohooves
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jan 16, 2016 2:34 am
- Post datetime: 2016-10-20T15:57:00+00:00
- Post Title: Re: Open and convert that VTEX_C files

> Reply from herbert3000
>
> You are right, thanks for the info! I uploaded the wrong version 
This is the correct one (x86):
https://www.mediafire.com/?4yy5jhy3ublxc4m
Ok, now it runs....
But how i can use it? The viewer is just to see and 
The decompliler starts, then ends, but nothing happens.

Anyway im converting most of the texure files with noesis.
(If someone can do a noesis .py for models and sounds, solves all my issues about that)
## Post #25
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-10-20T17:49:50+00:00
- Post Title: Re: Open and convert that VTEX_C files

> Reply from Smakkohooves
>
> But how i can use it? The viewer is just to see and 
The decompliler starts, then ends, but nothing happens.Decompiler.exe is a console program that means you would have to run it from the command shell (cmd.exe) and pass the input file and output directory as arguments. But you don't have to care about the decompiler, the viewer has the same functionality.

You can export *.vtex_c files as .png like this: 



screenshot.png (46.46 KiB) Viewed 141 times
## Post #26
- Username: Smakkohooves
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jan 16, 2016 2:34 am
- Post datetime: 2016-10-20T18:17:41+00:00
- Post Title: Re: Open and convert that VTEX_C files

> Reply from AceWell
>
> i just need you to run as many vtex_c textures as you can through the script to 
see which ones still don't work, then you can upload those so i can add support
I try to convert all the images, i have zipped the ones that gave me issures, is  a 80mb pack, ill link it later.
## Post #27
- Username: Smakkohooves
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jan 16, 2016 2:34 am
- Post datetime: 2016-10-23T12:06:54+00:00
- Post Title: Re: Open and convert that VTEX_C files

Here is the files with errors:

[https://mega.nz/#!gNxA1DTB!Zsq96U8U9-0i ... _zqN5w2IAY](https://mega.nz/#!gNxA1DTB!Zsq96U8U9-0i7_95JG7GF5jRGDhYvAi3O_zqN5w2IAY)
## Post #28
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-24T03:13:53+00:00
- Post Title: Re: Open and convert that VTEX_C files

> Reply from Smakkohooves
>
> Here is the files with errors:
https://mega.nz/#!gNxA1DTB!Zsq96U8U9-0i ... _zqN5w2IAY
okay i updated the script in this post   
[viewtopic.php?p=123637#p123637](http://forum.xentax.com/viewtopic.php?p=123637#p123637)
it was the best i can do, there might be a problem with cube map textures
but they look better in Noesis than what the Resource Viewer displays though   
and this was the first time i ever dealt with RGBA64 images...  
enjoy!
## Post #29
- Username: Smakkohooves
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jan 16, 2016 2:34 am
- Post datetime: 2016-10-24T10:53:17+00:00
- Post Title: Re: Open and convert that VTEX_C files

> Reply from AceWell
>
> Smakkohooves wrote:Here is the files with errors:
https://mega.nz/#!gNxA1DTB!Zsq96U8U9-0i ... _zqN5w2IAY
okay i updated the script in this post   
viewtopic.php?p=123637#p123637
it was the best i can do, there might be a problem with cube map textures
but they look better in Noesis than what the Resource Viewer displays though   
and this was the first time i ever dealt with RGBA64 images...  
enjoy!
Great! Now i can convert all the textures 

Thanks

(Now i have to see for models and sounds)
## Post #30
- Username: Smakkohooves
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jan 16, 2016 2:34 am
- Post datetime: 2022-04-21T04:05:49+00:00
- Post Title: Re: Open and convert that VTEX_C files

Hello guys, news about these formats? 
Valve use it in more games, someone have 
made related scripts?
(All the  *_C files)
