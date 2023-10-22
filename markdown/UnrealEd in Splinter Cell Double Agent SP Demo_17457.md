## Post #1
- Username: Nicknine
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Oct 04, 2015 3:29 am
- Post datetime: 2017-12-26T15:54:56+00:00
- Post Title: UnrealEd in Splinter Cell Double Agent SP Demo

Not sure if this the correct forum, please move the thread appropriately if needed.

So I've recently discovered that the Singleplayer demo of Splinter Cell: Double Agent on PC has a bunch of developer tools including UnrealEd that are not present in the retail version of the game.
I've tried launching UnrealEd but ran into numerous issues. First off, all Unreal packages in this game are packed into ULNC files. Thankfully, they can be extracted with Watto Game Extractor (extracted contents should go into the root of SCDA-Offline dir). Once I did extract the packages UnrealEd started throwing "Ran out of virtual memory" error.

> Ran out of virtual memory. To prevent this condition, you must free up more space on your primary hard disk.
>
> 
>
> History: FMallocWindows::Malloc <- FMallocWindows::Realloc <- 00000000 1976565848 FArray <- FArray::Realloc <- 247070731*8 <- FUnrealfileSummary<< <- LoadSummary <- ULinkerLoad::ULinkerLoad <- UObject::GetPackageLinker <- ULinkerLoad::VerifyImport <- ValidateImports <- ULinkerLoad::Verify <- ULinkerLoad::ULinkerLoad <- UObject::GetPackageLinker <- UObject::LoadPackage <- UEditorEngine::Init <- InitEngine
At this point, I got stuck. My best guess from the call stack is that it has to do with a package format mismatch (UnrealEd build is too old or too new for the packages) but I'm not sure.

Any help with getting this thing to run would be greatly appreciated.

Demo: [https://www.fileplanet.com/169143/16000 ... gleplayer]](https://www.fileplanet.com/169143/160000/fileinfo/Splinter-Cell:-Double-Agent-Demo-%5BSingleplayer%5D)
Watto Game Extractor: [http://www.watto.org/game_extractor.html](http://www.watto.org/game_extractor.html)
## Post #2
- Username: halfway
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Aug 24, 2017 1:50 pm
- Post datetime: 2017-12-28T04:06:00+00:00
- Post Title: UnrealEd in Splinter Cell Double Agent SP Demo

splinter cell games not created with unreal engine... ubisoft just change format and method of their games to a fake methot... like Farcry 3 and they saying Farcry developed with DUNIA ENGINE... but it's a lie from ubisoft... so, nobody fault 
I got dunia engine but that's not was like farcry3
even assassins creed! or other u is of the games! that's why nobody cant edit this games...
## Post #3
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2017-12-28T05:09:41+00:00
- Post Title: UnrealEd in Splinter Cell Double Agent SP Demo

> Reply from halfway
>
> splinter cell games not created with unreal engine... ubisoft just change format and method of their games to a fake methot... like Farcry 3 and they saying Farcry developed with DUNIA ENGINE... but it's a lie from ubisoft... so, nobody fault 
I got dunia engine but that's not was like farcry3
even assassins creed! or other u is of the games! that's why nobody cant edit this games...

Double agent was created with Unreal Engine 2.5, its not debatable, its a fact.

They've customised the output format it seems, but the game was 100% created using UE2.5

Far Cry 3 was also not made using Dunia engine, thats Far Cry 2, 1 was CriEngine, 3 is something else they haven't publicly announced.

you can't just expect to get the engine online and open the games files, theres a format difference between the source files and the packaged output files in every engine.
## Post #4
- Username: halfway
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Aug 24, 2017 1:50 pm
- Post datetime: 2017-12-28T12:08:58+00:00
- Post Title: UnrealEd in Splinter Cell Double Agent SP Demo

[quote="lionheartuk"
Double agent was created with Unreal Engine 2.5, its not debatable, its a fact.

They've customised the output format it seems, but the game was 100% created using UE2.5

Far Cry 3 was also not made using Dunia engine, thats Far Cry 2, 1 was CriEngine, 3 is something else they haven't publicly announced.
> you can't just expect to get the engine online and open the games files, theres a format difference between the source files and the packaged output files in every engine.

you right... but that was an other engine... they just created on unreal engine and developed in other engine... ubisift has a secret engine... ask to GHOST DEAD, he know that... becuase he's a game enginer and game desiner... i saw real unreal engine and working with zlib... thats not zlib!
you can found everything in .exe file
## Post #5
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2017-12-29T06:16:23+00:00
- Post Title: UnrealEd in Splinter Cell Double Agent SP Demo

> Reply from halfway
>
> [quote="lionheartuk"
Double agent was created with Unreal Engine 2.5, its not debatable, its a fact.

They've customised the output format it seems, but the game was 100% created using UE2.5

Far Cry 3 was also not made using Dunia engine, thats Far Cry 2, 1 was CriEngine, 3 is something else they haven't publicly announced.

you can't just expect to get the engine online and open the games files, theres a format difference between the source files and the packaged output files in every engine.

you right... but that was an other engine... they just created on unreal engine and developed in other engine... ubisift has a secret engine... ask to GHOST DEAD, he know that... becuase he's a game enginer and game desiner... i saw real unreal engine and working with zlib... thats not zlib!
you can found everything in .exe file

You're missunderstanding.

Unreal is zlib, yes, but its customised unreal, they have the unreal engine source code, they've edited the output for their own needs.
I'm also a game designer and 3D Artist working in the industry, with friends working at Crytek, they used unreal engine 2.5D and customised it, 100% it is unreal.
## Post #6
- Username: 3A2watup
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Aug 16, 2018 8:04 am
- Post datetime: 2018-08-16T00:08:27+00:00
- Post Title: UnrealEd in Splinter Cell Double Agent SP Demo

Did you manage to fix that issue?
## Post #7
- Username: 3A2watup
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Aug 16, 2018 8:04 am
- Post datetime: 2018-08-16T17:00:33+00:00
- Post Title: UnrealEd in Splinter Cell Double Agent SP Demo

I don't have experience with messing around in this, but I've tried myself and have saw different errors. Isn't there a chance of those extracted files from Watto being corrupted or incomplete in some way? Sorry for bumping this thread by the way..

EDIT: If you open ThirdEchelonLauncher you can see logs if you try to run the editor with it
