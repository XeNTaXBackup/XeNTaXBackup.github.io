## Post #1
- Username: Motoko
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jul 19, 2014 1:58 am
- Post datetime: 2021-12-08T18:22:39+00:00
- Post Title: PC: Century: Age of Ashes

Seeking some help. Game uses UE4 but has a unique archive type, programs like umodel cannot open so there's a good chance the .pak files are encrypted or something. Game is free on Steam and less than 10GB, but I can upload pak files if needed.
## Post #2
- Username: andrew21022
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Nov 11, 2019 3:23 am
- Post datetime: 2022-09-21T10:17:51+00:00
- Post Title: PC: Century: Age of Ashes

Do you still have CBT client ?
## Post #3
- Username: andrew21022
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Nov 11, 2019 3:23 am
- Post datetime: 2022-09-21T10:18:27+00:00
- Post Title: PC: Century: Age of Ashes

> Reply from Motoko ↑Thu Dec 09, 2021 2:22 am at Thu Dec 09, 2021 2:22 am
>
> 
Seeking some help. Game uses UE4 but has a unique archive type, programs like umodel cannot open so there's a good chance the .pak files are encrypted or something. Game is free on Steam and less than 10GB, but I can upload pak files if needed.

Do you still have CBT client ?
## Post #4
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2022-12-17T15:50:39+00:00
- Post Title: PC: Century: Age of Ashes

> Reply from andrew21022 ↑Wed Sep 21, 2022 6:17 pm at Wed Sep 21, 2022 6:17 pm
>
> 
Do you still have CBT client ?

I have this game. Can you help me to unack it?
## Post #5
- Username: andrew21022
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Nov 11, 2019 3:23 am
- Post datetime: 2022-12-20T10:49:58+00:00
- Post Title: PC: Century: Age of Ashes

> Reply from TokiChan ↑Sat Dec 17, 2022 11:50 pm at Sat Dec 17, 2022 11:50 pm
>
> 
andrew21022 wrote: ↑Wed Sep 21, 2022 6:17 pm
Do you still have CBT client ?


I have this game. Can you help me to unack it?

sure,thats why i am looking for it
## Post #6
- Username: LegnaX
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Dec 01, 2022 6:12 pm
- Post datetime: 2023-01-19T14:05:02+00:00
- Post Title: PC: Century: Age of Ashes

Hello.

So, I am also trying to be able to extract the files from the .pak of this game. Considering it has been made using Unreal Engine 4 and the broad compatibility of games in which assets can be downloaded using the UE Viewer tool, I expected it to be pretty easy. However, the .pak file seems to be compressed as a .pak file and encrypted. None of the .pak unpackers I tried (including the native UnrealPak command-line tool from the Unreal Engine editor) seemed to work. 

Sadly, I am blocked here. I don't know where to go from here, and I would love to be able to extract the models from this game.

Any help would be heavily appreciated! The game is free on Steam and the Epic Games Store, and it's about 11 GB in total, so it doesn't take too long to download and check. In any case, these are the contents of the actual game folder:


The actual root of the game:




Please let me know if you find anything!
## Post #7
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2023-01-22T19:20:24+00:00
- Post Title: PC: Century: Age of Ashes

Check the latest comments in the Century: Age of Ashes thread in Gildor's UE viewer [ forum](https://www.gildor.org/smf/index.php/topic,7599.15.html).  spiritovod has it working with latest version of the game.
## Post #8
- Username: LegnaX
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Dec 01, 2022 6:12 pm
- Post datetime: 2023-01-23T16:19:11+00:00
- Post Title: PC: Century: Age of Ashes

Thank you! I seem to be having issues for now, so I posted photos there asking for help (it may be an issue on my side). 
In any case, thank you very much @zardalu ! Let's see if we can manage to have it working, as I plan on extracting every model from that game (currently working on ARK, already extracted 146 out of 197
## Post #9
- Username: LegnaX
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Dec 01, 2022 6:12 pm
- Post datetime: 2023-01-24T18:18:52+00:00
- Post Title: PC: Century: Age of Ashes

So, for anyone who's looking for a solution to this, I found a way to be able to access and extract the assets from the game (including animations) from gildor.org's forum: [https://www.gildor.org/smf/index.php/to ... 9.new.html](https://www.gildor.org/smf/index.php/topic,7599.new.html).

Small video example trying the UE Viewer with the .pak from the game and then the uncompressed one, exporting a model, importing it in Blender, importing animations, and then adding the textures: [https://mega.nz/file/4d9SABqC#WdP1sH152 ... 5gqcINPcVU](https://mega.nz/file/4d9SABqC#WdP1sH152ZdK58ISE6U022_Q65hmHPESY5gqcINPcVU)

WHAT DO YOU NEED: 
1) The game's last version (it currently works on a version of the game 1.0.59831). The game is free, and you can get it from Steam.
2) UE Viewer, last version (tested on 1589). You do NOT need the particular version for viewing materials, just the standard version from Oct 22nd, 2022 (build 1589). Link: [https://www.gildor.org/downloads](https://www.gildor.org/downloads)
3) quickbms (you can get it from here: [https://aluigi.altervista.org/quickbms.htm](https://aluigi.altervista.org/quickbms.htm)).
4) Script to unpack the game (which you can get from here: [https://mega.nz/file/ZEFyhCKY#FNHgvj6w_ ... u-420BGhAI](https://mega.nz/file/ZEFyhCKY#FNHgvj6w_f3uyjTe8TbQLTCI7wJ7NevV6u-420BGhAI) ).

WHAT TO DO, STEP BY STEP:
1) You need to go to quickbms and open the file "quickbms_4gb_files.exe". 
1.1) It will ask you to select a script. Select the one downloaded in point 4).
1.2) It will ask you to select the .pak. The one from the game is on the following path: "<install route>\CenturyAgeofAshes\Century\Content\Paks\Century-WindowsNoEditor.pak".
1.3) It will ask you to select a folder to unpack the file. Just select the folder that you want, or create a new one.
NOTE: QuickBMS may fail at some point due to a crash. If it happens, make sure that you have the folder "<extract folder>\Century\Content\Characters" completely downloaded, as it's the folder that has all the characters from the game or any folder you want. The folder looks like this when it's fully downloaded: [https://i.imgur.com/EeGQYFK.png](https://i.imgur.com/EeGQYFK.png)
2) Once the unpack finishes, open UE Viewer by executing "umodel_64.exe" or "umodel.exe". Then, fill in the following fields:
.
3) After opening, something like this should open: [https://i.imgur.com/nJByM2A.png](https://i.imgur.com/nJByM2A.png)
3.1) After this point, you can browse any asset, load animations, and extract them. Check the upper video.

NOTES: Some animations are not working and turn the model into a mess. Others do work.
## Post #10
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2023-01-31T04:21:05+00:00
- Post Title: PC: Century: Age of Ashes

> Reply from LegnaX ↑Wed Jan 25, 2023 2:18 am at Wed Jan 25, 2023 2:18 am
>
> 
So, for anyone who's looking for a solution to this, I found a way to be able to access and extract the assets from the game (including animations)

I try this, but when I try to open somethink in UE viewer  for exporting, it always chash
## Post #11
- Username: LegnaX
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Dec 01, 2022 6:12 pm
- Post datetime: 2023-01-31T23:50:59+00:00
- Post Title: PC: Century: Age of Ashes

> Reply from TokiChan ↑Tue Jan 31, 2023 12:21 pm at Tue Jan 31, 2023 12:21 pm
>
> 
LegnaX wrote: ↑Wed Jan 25, 2023 2:18 am
So, for anyone who's looking for a solution to this, I found a way to be able to access and extract the assets from the game (including animations) 


I try this, but when I try to open somethink in UE viewer  for exporting, it always chash

Make sure you are using the same version I am using and you are selecting the same settings I am using. Also, make sure you unpacked the whole game using QuickBMS. Otherwise, the assets cannot be viewed or exported. All the instructions have been detailed in my post.
## Post #12
- Username: LegnaX
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Dec 01, 2022 6:12 pm
- Post datetime: 2023-02-17T10:02:22+00:00
- Post Title: PC: Century: Age of Ashes

So, this is just a quick follow-up.

2 more members and I have managed to RIP absolutely every dragon from the game, including their assets (armature, horns, etc...). Over 150 different combinations have been found. We have also ripped every single baby dragon as well.

We put all of them into 4 different .blend files with all the assets together. The idea is to allow the people to "build" their own dragon by selecting a base body, then a material body, then the armor and the horns they want. Once they are done, they can just use those packages or delete everything else. All dragons will have alternative upscaled textures using special AI (to 2K and even 4K textures) and a hand-made IK rig to pose and animate with the dragons easily. Material nodes are also fully set up using all the textures from the dragons.

For now, all dragons are done. We will mesh-edit them to add more stuff and fix a few issues here and there, and when it's done, we will release them for free to the public. We will keep you informed!
## Post #13
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2023-02-28T20:46:19+00:00
- Post Title: PC: Century: Age of Ashes

> Reply from LegnaX ↑Wed Jan 25, 2023 2:18 am at Wed Jan 25, 2023 2:18 am
>
> 
So, for anyone who's looking for a solution to this, I found a way to be able to access and extract the assets from the game (including animations) from gildor.org's forum: https://www.gildor.org/smf/index.php/to ... 9.new.html.
Hi
I have this when use Quick BMS

UPD: Some dragons still working to export, but no show tex
[Снимок2.PNG](https://xentaxbackup.github.io/file/23455_Снимок2.PNG)
