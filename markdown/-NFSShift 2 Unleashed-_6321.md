## Post #1
- Username: toolieo
- Rank: veteran
- Number of posts: 123
- Joined date: Sun Mar 21, 2010 9:16 pm
- Post datetime: 2011-03-29T03:08:06+00:00
- Post Title: -NFS:Shift 2 Unleashed-

Hello All,

Thought id start this as not much has changed since Shift 1. The .bff format is the same as shift 1 so QuickBMS and the Shift 1 .BFF script is the way to go. There is a post on zmodeler for Oleg for the model files and do somewhat import into zmodeler already, including materials; So I do think Shift 2 will be modifiable within couple of days or at least hope so.

[](http://img641.imageshack.us/img641/9797/31211498.jpg)

Does anyone know if this game can be run unpacked? I don't exactly know where to start, I made a small batch file just like shift 1 but there is a few new more files. I couldn't find the original creator for the Shift 1 unpacked batch file so I am not sure if they written every file down or did they get a program to copy the names.

Sample: (Porsche 918 .bff Extracted)
[http://www.gamefront.com/files/20169182/Porsche_918.rar](http://www.gamefront.com/files/20169182/Porsche_918.rar)

If anyone needs another file or something to figure it out, sure. In the mean time I will be seeing what I can do.
## Post #2
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2011-03-29T04:15:28+00:00
- Post Title: -NFS:Shift 2 Unleashed-

Tested with -loose Commandline like for Shift 1 ?

( shift2.exe -loose ) or whatever the name of the Shift 2 executable is. 

Even it is in German you can clearly see what it is 



Verknüpfung = Shortcut
Ziel = Target
## Post #3
- Username: toolieo
- Rank: veteran
- Number of posts: 123
- Joined date: Sun Mar 21, 2010 9:16 pm
- Post datetime: 2011-03-29T05:17:17+00:00
- Post Title: -NFS:Shift 2 Unleashed-

Seems to unpack just like shift 1 except have to add the new files too.

[http://www.nogripracing.com/forum/showt ... 27&page=46](http://www.nogripracing.com/forum/showthread.php?t=227627&page=46)
## Post #4
- Username: toolieo
- Rank: veteran
- Number of posts: 123
- Joined date: Sun Mar 21, 2010 9:16 pm
- Post datetime: 2011-03-29T12:59:02+00:00
- Post Title: -NFS:Shift 2 Unleashed-

Unpacking is easy I managed to make a batch file that extracts all .bff files, however the game refused to load once the "-loose" option is put on. 

I do thank Jdoug and Action over at NoGripRacing forums for the tips and also progress they are also doing.   

This is my batch file >>> [http://www.gamefront.com/files/20170313 ... Shift2.rar](http://www.gamefront.com/files/20170313/game_unpackShift2.rar)<<< Extraction requires the same as Shift 1 extracting.  You need QuickBMS *Latest* and NFSShift.bms script put all and my batch file in the main directory and it should start.   

There must be something else blocking it.
## Post #5
- Username: prudislav
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 13, 2010 6:48 am
- Post datetime: 2011-03-29T13:22:47+00:00
- Post Title: -NFS:Shift 2 Unleashed-

anybody found where are text files? I found only subtitles for Movies
## Post #6
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2011-03-29T15:28:18+00:00
- Post Title: -NFS:Shift 2 Unleashed-

I dont have the game yet but I think they are binary
## Post #7
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2011-03-29T19:38:33+00:00
- Post Title: -NFS:Shift 2 Unleashed-

[](http://www.abload.de/image.php?img=loosean4g.png)
## Post #8
- Username: AMG63
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Feb 19, 2011 7:17 pm
- Post datetime: 2011-03-30T05:02:48+00:00
- Post Title: -NFS:Shift 2 Unleashed-

I have a problem here  When i import my car(SLS AMG) to zmodeler, it does not look like a car  
[](http://img801.imageshack.us/i/52182181.jpg/)
I followed Tool831's instructions and used his batch file  
How can someone help?
## Post #9
- Username: toolieo
- Rank: veteran
- Number of posts: 123
- Joined date: Sun Mar 21, 2010 9:16 pm
- Post datetime: 2011-03-30T14:12:11+00:00
- Post Title: -NFS:Shift 2 Unleashed-

Further research turns out CRC errors can occur if you have a out dated QuickBMS. So Shift 1 .BFF script does work however running the game with "-loose" fails to either read or find the files.  I ain't a .exe or pro coder so I couldn't tell. 

Its just a big confusion at the moment.
------

Here is my updated batch. This fixed the problem skipping vehicle files and tracks also few other folders.

[http://www.gamefront.com/files/20170313 ... Shift2.rar](http://www.gamefront.com/files/20170313/game_unpackShift2.rar)

Make sure you have the newest QuickBMS otherwise CRC errors will happen.
## Post #10
- Username: vagos21
- Rank: veteran
- Number of posts: 128
- Joined date: Thu Feb 10, 2011 5:48 pm
- Post datetime: 2011-04-01T12:35:11+00:00
- Post Title: -NFS:Shift 2 Unleashed-

> Reply from AMG63
>
> I have a problem here  When i import my car(SLS AMG) to zmodeler, it does not look like a car  

I followed Tool831's instructions and used his batch file  
How can someone help?

does this help? WIP



shift2-mclarenF1.jpg (220.48 KiB) Viewed 628 times
## Post #11
- Username: gpfan
- Rank: beginner
- Number of posts: 33
- Joined date: Sat Apr 02, 2011 2:59 am
- Post datetime: 2011-04-01T19:02:26+00:00
- Post Title: -NFS:Shift 2 Unleashed-

So how did you achive that?  Did you create a new way to extract correctly .BFF or are you developing a new tool to do it right?
## Post #12
- Username: vagos21
- Rank: veteran
- Number of posts: 128
- Joined date: Thu Feb 10, 2011 5:48 pm
- Post datetime: 2011-04-02T00:00:31+00:00
- Post Title: -NFS:Shift 2 Unleashed-

> Reply from gpfan
>
> So how did you achive that?  Did you create a new way to extract correctly .BFF or are you developing a new tool to do it right?

the bff script from shift 1 works perfectly, i'm just making an import script for 3ds max, it can load shift 1 cars too.
## Post #13
- Username: Freakydevil
- Rank: n00b
- Number of posts: 10
- Joined date: Mon May 03, 2010 12:38 am
- Post datetime: 2011-04-02T05:41:12+00:00
- Post Title: -NFS:Shift 2 Unleashed-

Will you share that script with us?

Would be a great day then
## Post #14
- Username: AMG63
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Feb 19, 2011 7:17 pm
- Post datetime: 2011-04-02T07:32:54+00:00
- Post Title: -NFS:Shift 2 Unleashed-

> Reply from vagos21
>
> AMG63 wrote:I have a problem here  When i import my car(SLS AMG) to zmodeler, it does not look like a car  

I followed Tool831's instructions and used his batch file  
How can someone help? 

does this help? WIP
shift2-mclarenF1.jpg
yeep  can you upload your script? Ill appreciate that. Thanx
## Post #15
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-04-04T00:51:37+00:00
- Post Title: -NFS:Shift 2 Unleashed-

> Reply from vagos21
>
> does this help? WIP
i see nice progress here, well done vagos21
## Post #16
- Username: vagos21
- Rank: veteran
- Number of posts: 128
- Joined date: Thu Feb 10, 2011 5:48 pm
- Post datetime: 2011-04-04T01:32:28+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

as said before, it's WIP, when it's done it will be here, hopefully soon. i work on importing tracks at the same time and don't have much free time, so it will take a while
## Post #17
- Username: toolieo
- Rank: veteran
- Number of posts: 123
- Joined date: Sun Mar 21, 2010 9:16 pm
- Post datetime: 2011-04-04T05:24:30+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

@People who have zmodeler:

Oleg (Creator of zmodeler) has the Shift 2 import filter work in progress at the moment. 



Thread is here: [http://forum.zmodeler2.com/viewtopic.php?t=5139](http://forum.zmodeler2.com/viewtopic.php?t=5139)
## Post #18
- Username: Veegie
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Apr 05, 2010 2:54 am
- Post datetime: 2011-04-05T03:21:45+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

Nice to see some progress guys.
I'll definitely be watching this thread.
I'd love to get my hands on fixing up some of their models to a bit higher resolution.

EDIT: It seems the import filter for ZModeler was released. Does anyone know where it can be downloaded?
## Post #19
- Username: vagos21
- Rank: veteran
- Number of posts: 128
- Joined date: Thu Feb 10, 2011 5:48 pm
- Post datetime: 2011-04-07T15:32:22+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

some progress on the maxscript, anyone interested?



mc12.jpg (176.4 KiB) Viewed 380 times
## Post #20
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-04-07T15:36:45+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

> Reply from vagos21
>
> some progress on the maxscript, anyone interested?
mc12.jpg
keep going, great work as always
## Post #21
- Username: vagos21
- Rank: veteran
- Number of posts: 128
- Joined date: Thu Feb 10, 2011 5:48 pm
- Post datetime: 2011-04-07T17:03:53+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

and a rough test on track import!



spa.jpg (221.9 KiB) Viewed 369 times
## Post #22
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-04-07T17:12:15+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

> Reply from vagos21
>
> and a rough test on track import!
spa.jpg
it's cool importing all games stuff directly into the 3ds max
## Post #23
- Username: Veegie
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Apr 05, 2010 2:54 am
- Post datetime: 2011-04-07T19:29:17+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

> Reply from vagos21
>
> some progress on the maxscript, anyone interested?
Very!
I look forward to giving it a try.
## Post #24
- Username: SandroX
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Apr 20, 2010 3:43 am
- Post datetime: 2011-04-07T22:24:58+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

> Reply from vagos21
>
> some progress on the maxscript, anyone interested?
Of course!  I prefer work in Max than in ZM2 or 3dsimed..
## Post #25
- Username: SoniKalien
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 13, 2011 11:02 am
- Post datetime: 2011-04-09T04:34:35+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

> Reply from vagos21
>
> some progress on the maxscript, anyone interested?

Yep +1 You're awesome with the maxscripts
## Post #26
- Username: gpfan
- Rank: beginner
- Number of posts: 33
- Joined date: Sat Apr 02, 2011 2:59 am
- Post datetime: 2011-04-10T20:28:21+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

Will you upload the files?
## Post #27
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2011-04-12T10:02:10+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

That's a great work  thanks for keep working on it
## Post #28
- Username: vagos21
- Rank: veteran
- Number of posts: 128
- Joined date: Thu Feb 10, 2011 5:48 pm
- Post datetime: 2011-04-12T10:54:17+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

here is a first release of both the scripts:
import car or track!
please read the top of the script for know bugs/limitations!
car script is not totally complete yet, it doesn't import all cars, will be working on it.

have fun using them, and always remember, the models are property of EA games 

many thanks to chipicao for helping in the long research of the files!


 shift2 car track.zip
(8.13 KiB) Downloaded 145 times
## Post #29
- Username: Veegie
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Apr 05, 2010 2:54 am
- Post datetime: 2011-04-12T18:17:43+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

It seems that it should bring up a folder selection prompt window when the script is run.
I'm currently running 3ds Max 2011 x64 - When I run the script nothing seems to happen.
Am I doing something wrong?

EDIT: I even, in futility, manually changed the J:\etc file path that was within the script to my personal one, but to no avail.
## Post #30
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2011-04-12T19:19:24+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

Did you evaluate a few times before you ran the script?

Open the script listener (F11) and show us what errors you get.
## Post #31
- Username: Veegie
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Apr 05, 2010 2:54 am
- Post datetime: 2011-04-12T19:31:51+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

I ran the script (tried both the car and the track) within the MAXScript Listener, but with no luck.
It just remains completely blank as if the script was empty.
There's no sign of any initialization.

If I open the script in the editor itself, highlight everything, and hit enter, the Listener does show a bit of population.

```
  name:<data>; Public,
  offset:<data>; Public,
  size:<data>; Public)
#Struct:elmts(
  firstChild:<data>; Public,
  nextSibling:<data>; Public,
  numChildren:<data>; Public,
  firstAttr:<data>; Public,
  numAttrs:<data>; Public)
#Struct:attrs(
  type:<data>; Public,
  num_values:<data>; Public,
  val:<data>; Public,
  nextAttr:<data>; Public,
  id:<data>; Public)
#Struct:colls(
  unknown1:<data>; Public,
  unknown2:<data>; Public,
  unknown3:<data>; Public,
  id:<data>; Public)
#Struct:amatrix(
  position:<data>; Public,
  orientation:<data>; Public)
#()
#()
undefined
27482
readCarXML()
importPart()
readMaterials()
readAlignedString()
getFilesRecursive()
applyuvw()

```
## Post #32
- Username: vagos21
- Rank: veteran
- Number of posts: 128
- Joined date: Thu Feb 10, 2011 5:48 pm
- Post datetime: 2011-04-12T21:42:27+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

for those new to installing/using maxscripts, this will be useful info:

[http://www.scriptspot.com/3ds-max/tutor ... in-3ds-max](http://www.scriptspot.com/3ds-max/tutorials/script-installation-in-3ds-max)

and here's a link to the tutorial i had for the TDU2 scripts, the first step contains installing/using a maxscript

[viewtopic.php?f=10&t=5747&start=109](http://forum.xentax.com/viewtopic.php?f=10&t=5747&start=109)

good luck!
## Post #33
- Username: Veegie
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Apr 05, 2010 2:54 am
- Post datetime: 2011-04-12T22:17:12+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

Thanks for the clarification 




```
"Loading Materials and Textures..."
"Done!"
"Importing meshes..."
-- Error occurred in importPart(); filename: C:\Program Files\Autodesk\3ds Max 2011\Scripts\Shift2 car import.mcr; position: 3874; line: 129
--  Frame:
--   b6: undefined
--   amesh: undefined
--   position: [0,0,0]
--   numchars: undefined
--   UVWarr: #()
--   orientation: [0,0,0,1]
--   numVertProps: undefined
--   normarr: #()
--   varr: #()
--   hasnormals: false
--   f: undefined
--   b7: undefined
--   b8: undefined
--   b1: undefined
--   partName: undefined
--   b2: undefined
--   farr: #()
--   faceMatID: #()
--   b3: undefined
--   filename: "C:\Users\Nate\Desktop\shift2\Huayra\vehicles\Pagani_C9\PAGANI_C9_KIT04_BODY_LODA.meb"
--   b4: undefined
--   numverts: undefined
--   NumBones: undefined
--   b5: undefined
--   multiplier: undefined
--   bytesToJump: undefined
--   numPrims: undefined
--   called in readCarXML(); filename: C:\Program Files\Autodesk\3ds Max 2011\Scripts\Shift2 car import.mcr; position: 3080; line: 92
--  Frame:
--   texpath: "C:\Users\Nate\Desktop\shift2\Huayra\vehicles\Pagani_C9\PAGANI_C9_KIT04_BODY_LODA.meb"
--   num_matrices: 41
--   modelpath: "C:\Users\Nate\Desktop\shift2\Huayra\vehicles\pagani_c9"
--   name: "PAGANI_C9_KIT04_BODY_LODA"
--   f: <File:C:\Users\Nate\Desktop\shift2\Huayra\vehicles\pagani_c9\pagani_c9.vhf>
--   filepath: "vehicles\Pagani_C9\PAGANI_C9_KIT04_BODY_LODA.meb"
--   matrixIdx: 19
--   words: #("C:", "Users", "Nate", "Desktop", "shift2", "Huayra", "vehicles", "pagani_c9")
--   filename: "C:\Users\Nate\Desktop\shift2\Huayra\vehicles\pagani_c9\pagani_c9.vhf"
--   lastname: "pagani_c9"
--   called in anonymous codeblock; filename: C:\Program Files\Autodesk\3ds Max 2011\Scripts\Shift2 car import.mcr; position: 1789; line: 40
--  Frame:
--   modelpath: "C:\Users\Nate\Desktop\shift2\Huayra\vehicles\pagani_c9"
>> MAXScript MacroScript Error Exception: -- Unknown property: "count" in undefined <<
```
## Post #34
- Username: vagos21
- Rank: veteran
- Number of posts: 128
- Joined date: Thu Feb 10, 2011 5:48 pm
- Post datetime: 2011-04-13T08:24:05+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

i'm trying to upload the fixed script that works, but i'm getting this error:

"Could not upload attachment to ./files/33067_ab3922fc3d3548d2c98f7d116cb0cad4."
a server problem i suppose?

i'll try again later!
## Post #35
- Username: vagos21
- Rank: veteran
- Number of posts: 128
- Joined date: Thu Feb 10, 2011 5:48 pm
- Post datetime: 2011-04-13T22:40:57+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

Sorry i tried 3 times to upload it and i keep getting the same error, anyone having the same problem? is it a temporary server problem?
## Post #36
- Username: Veegie
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Apr 05, 2010 2:54 am
- Post datetime: 2011-04-14T00:35:01+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

Maybe try rapidshare or megaupload as a temporary solution.
## Post #37
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2011-04-14T04:17:16+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

I loaded Monza, with few problems, many polys are missing  

[](http://img846.imageshack.us/i/monz.jpg/)

Uploaded with [ImageShack.us](http://imageshack.us)
## Post #38
- Username: quadcoremax
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 30, 2011 8:33 pm
- Post datetime: 2011-04-15T15:16:00+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

Thanks for your tool !

Still, I also have a 'count' issue like Veegie...
I might port Shift tracks to Racer (racer.nl)...
Testing it with XP SP3 + 3DS MAX 2009
## Post #39
- Username: kudan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 12, 2010 1:47 am
- Post datetime: 2011-04-16T05:03:10+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

script in any occasion does nothing :\
i tried max 2009 32\64 and 2011

i tried to place it to the main ui but no luck does nothing
any ideas?
## Post #40
- Username: D1Racer
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jun 07, 2010 9:21 am
- Post datetime: 2011-04-16T09:15:27+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

Great tool, Thanks 

Works well for me, on Max 2011 x64 bit. Only issue is some parts appear doubled but with no mesh. Anyway no biggy at all.

One request though, could you make it import the meshes from the cockpit .bml too please
## Post #41
- Username: justspeeding
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 02, 2010 3:33 am
- Post datetime: 2011-04-16T18:29:26+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

> Reply from Veegie
>
> Thanks for the clarification 



Code: Select all"Importing car: C:\Users\Nate\Desktop\shift2\Huayra\vehicles\pagani_c9"
"Loading Materials and Textures..."
"Done!"
"Importing meshes..."
-- Error occurred in importPart(); filename: C:\Program Files\Autodesk\3ds Max 2011\Scripts\Shift2 car import.mcr; position: 3874; line: 129
--  Frame:
--   b6: undefined
--   amesh: undefined
--   position: [0,0,0]
--   numchars: undefined
--   UVWarr: #()
--   orientation: [0,0,0,1]
--   numVertProps: undefined
--   normarr: #()
--   varr: #()
--   hasnormals: false
--   f: undefined
--   b7: undefined
--   b8: undefined
--   b1: undefined
--   partName: undefined
--   b2: undefined
--   farr: #()
--   faceMatID: #()
--   b3: undefined
--   filename: "C:\Users\Nate\Desktop\shift2\Huayra\vehicles\Pagani_C9\PAGANI_C9_KIT04_BODY_LODA.meb"
--   b4: undefined
--   numverts: undefined
--   NumBones: undefined
--   b5: undefined
--   multiplier: undefined
--   bytesToJump: undefined
--   numPrims: undefined
--   called in readCarXML(); filename: C:\Program Files\Autodesk\3ds Max 2011\Scripts\Shift2 car import.mcr; position: 3080; line: 92
--  Frame:
--   texpath: "C:\Users\Nate\Desktop\shift2\Huayra\vehicles\Pagani_C9\PAGANI_C9_KIT04_BODY_LODA.meb"
--   num_matrices: 41
--   modelpath: "C:\Users\Nate\Desktop\shift2\Huayra\vehicles\pagani_c9"
--   name: "PAGANI_C9_KIT04_BODY_LODA"
--   f: <File:C:\Users\Nate\Desktop\shift2\Huayra\vehicles\pagani_c9\pagani_c9.vhf>
--   filepath: "vehicles\Pagani_C9\PAGANI_C9_KIT04_BODY_LODA.meb"
--   matrixIdx: 19
--   words: #("C:", "Users", "Nate", "Desktop", "shift2", "Huayra", "vehicles", "pagani_c9")
--   filename: "C:\Users\Nate\Desktop\shift2\Huayra\vehicles\pagani_c9\pagani_c9.vhf"
--   lastname: "pagani_c9"
--   called in anonymous codeblock; filename: C:\Program Files\Autodesk\3ds Max 2011\Scripts\Shift2 car import.mcr; position: 1789; line: 40
--  Frame:
--   modelpath: "C:\Users\Nate\Desktop\shift2\Huayra\vehicles\pagani_c9"
>> MAXScript MacroScript Error Exception: -- Unknown property: "count" in undefined <<
same for me max 2010 86x and I'm correctly install the script I did it more than ones but not working also the track is not working 
I try to import zolder and pagani c9 (huyara)
looks great keep going and I look forword to import it in max
## Post #42
- Username: D1Racer
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jun 07, 2010 9:21 am
- Post datetime: 2011-04-16T22:14:39+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

Follow the tutorial for installing a maxscript for TDU as posted above, make sure to hit ctrl E about 4 times, I was getting same errors until I done this, I hit Ctrl E 4 times and then it imported fine (Pagani C9).
## Post #43
- Username: SoniKalien
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 13, 2011 11:02 am
- Post datetime: 2011-04-17T04:54:19+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

Script working fine here. Everyone you just gotta make sure you choose the right folder to import.

> Reply from D1Racer
>
> Works well for me, on Max 2011 x64 bit. Only issue is some parts appear doubled but with no mesh. Anyway no biggy at all.

I suspect those empty meshes are deformers for damage etc.
## Post #44
- Username: justspeeding
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 02, 2010 3:33 am
- Post datetime: 2011-04-17T07:53:33+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

he 

I test the AC cobra and it works fine 
Great tool but the pagani c9  is not working

here is a screen of the error
[](http://trackmania-carpark.com/imagespark/resume.php?rd=even/up/&nd=4daa9ecf023af.jpg)

I gonne try to do a other car to 
 let you know the progres
## Post #45
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2011-04-17T15:29:31+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

Are you able to write a 3DS Max Export Script? 

(Max to Shift 2)
## Post #46
- Username: Veegie
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Apr 05, 2010 2:54 am
- Post datetime: 2011-04-17T22:14:16+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

> Reply from SoniKalien
>
> Script working fine here. Everyone you just gotta make sure you choose the right folder to import.
What folder are you recommending?
Every folder I've tried has given the same error.
vehicles\*vehicle_name*
## Post #47
- Username: vagos21
- Rank: veteran
- Number of posts: 128
- Joined date: Thu Feb 10, 2011 5:48 pm
- Post datetime: 2011-04-18T15:31:20+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

Please everyone, before posting the same problems repeatedly please read everything i write in my posts, i said it won't work on all cars, it won't import all objects from tracks. and since maxscript is really slow and bad sometimes, i'm planning on a 3rd party software tool to convert any car to obj, which can be imported to ANY 3d editing software. it's going well till now, and works on all cars. you'll have it in a few days when it's mostly done. just be patient and remember it's still test season 

Edit: No, i don't plan to sell it like zmodeler,
        and no, it won't to export back to shift 2 i don't have much time to look into the full details of the game files
## Post #48
- Username: D1Racer
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jun 07, 2010 9:21 am
- Post datetime: 2011-04-18T17:06:29+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

I look foward to this, thank you for your efforts
## Post #49
- Username: justspeeding
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 02, 2010 3:33 am
- Post datetime: 2011-04-18T17:40:31+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

> Reply from vagos21
>
> Please everyone, before posting the same problems repeatedly please read everything i write in my posts, i said it won't work on all cars, it won't import all objects from tracks. and since maxscript is really slow and bad sometimes, i'm planning on a 3rd party software tool to convert any car to obj, which can be imported to ANY 3d editing software. it's going well till now, and works on all cars. you'll have it in a few days when it's mostly done. just be patient and remember it's still test season 

Edit: No, i don't plan to sell it like zmodeler,
        and no, it won't to export back to shift 2 i don't have much time to look into the full details of the game files

he thx to  make the program. 
and sorry for the dubble post 
I tested the pagani zonda R and works fine only some iverted face of the body work or blended mode but this is not importend know you are making the prog
## Post #50
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2011-04-18T18:45:12+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

Import script works but I get some normal Errors on the Models. ?!

(Like Roof on Audi R8 LMS)
## Post #51
- Username: Veegie
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Apr 05, 2010 2:54 am
- Post datetime: 2011-05-06T18:57:34+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

As we approach three weeks without an update, is this still being developed?
## Post #52
- Username: justspeeding
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 02, 2010 3:33 am
- Post datetime: 2011-05-09T17:28:36+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

In my test i did 
there are the cars that are not working  the one that have moving parts like wing that comming out of the car like the lexus and the stirling moss and so 
mybe that helps you 


hope you continu the job
## Post #53
- Username: justspeeding
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 02, 2010 3:33 am
- Post datetime: 2011-05-23T18:13:58+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

I saw on a other forum that he is buzzy by making  good shades for the program he is making so mybe there is hope he will update us soon
## Post #54
- Username: vagos21
- Rank: veteran
- Number of posts: 128
- Joined date: Thu Feb 10, 2011 5:48 pm
- Post datetime: 2011-05-25T12:09:32+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

Sorry for the very long absence, i've been too busy with work and other things in life that really slowed down the development of the tool! i wanted to post some shots of it but the attachments weren't working...

anyway, good news is i want to put more effort in it, so there's already an obj export function, and now trying to handle hierarchy and changing textures/materials, also export to .X format that supports it, then i added support for TDU2 cars/meshes import, with automatic 2db->dds texture conversion, as soon as something is completely ready i'll post it! there might also be plans for importing pssg files from DIRT 2 and 3, but i'll see if i have more time for that.

i'm developing this along with chipicao who's testing it and helped a lot, he's free to share any kind of screenshot he likes on any forum
## Post #55
- Username: Justdragos
- Rank: advanced
- Number of posts: 69
- Joined date: Tue Feb 21, 2012 3:19 pm
- Post datetime: 2013-06-09T20:31:08+00:00
- Post Title: Re: -NFS:Shift 2 Unleashed-

hy! Could you guys put a link to the script, i don't know how to create one .
