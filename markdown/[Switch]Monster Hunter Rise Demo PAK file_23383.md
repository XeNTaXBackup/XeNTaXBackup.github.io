## Post #1
- Username: cbasic
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 31, 2021 12:24 pm
- Post datetime: 2021-02-01T05:55:15+00:00
- Post Title: [Switch]Monster Hunter Rise Demo PAK file

Monster Hunter Rise uses RE Engine and there is a huge re_chunk_000.pak packing all its assets. It can be unpacked with existing RE2/3 and DMC5 unpacking tools but there is no file list. Is any one interested in extract file names? Or any suggestions on it?
## Post #2
- Username: Shiroleinchen
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Feb 19, 2016 1:01 am
- Post datetime: 2021-04-16T22:19:46+00:00
- Post Title: [Switch]Monster Hunter Rise Demo PAK file

Hello,
I can only offer this list (i manually put to gether the 31 entries)
At this point i dont have a automatic way on getting those paths and i dont know if i can (semi) automate this.. i dont have any experience with writing hooks etc.
[https://drive.google.com/file/d/1W7brjx ... sp=sharing](https://drive.google.com/file/d/1W7brjxupeUlXd39TLCRewr2VxKhsdg5q/view?usp=sharing)
## Post #3
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2021-04-17T08:36:47+00:00
- Post Title: [Switch]Monster Hunter Rise Demo PAK file

> Reply from Shiroleinchen ↑Sat Apr 17, 2021 6:19 am at Sat Apr 17, 2021 6:19 am
>
> 
Hello,
I can only offer this list (i manually put to gether the 31 entries)
At this point i dont have a automatic way on getting those paths and i dont know if i can (semi) automate this.. i dont have any experience with writing hooks etc.
https://drive.google.com/file/d/1W7brjx ... sp=sharing

How did you get those entries manually?
Regarding hooks, MHR uses the Re2 remake engine so the re2hook would be used, but that assumes windows and an exe, not a switch.
## Post #4
- Username: Shiroleinchen
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Feb 19, 2016 1:01 am
- Post datetime: 2021-04-17T11:34:05+00:00
- Post Title: [Switch]Monster Hunter Rise Demo PAK file

> Reply from 09williamsad ↑Sat Apr 17, 2021 4:36 pm at Sat Apr 17, 2021 4:36 pm
>
> 
Shiroleinchen wrote: ↑Sat Apr 17, 2021 6:19 am
Hello,
I can only offer this list (i manually put to gether the 31 entries)
At this point i dont have a automatic way on getting those paths and i dont know if i can (semi) automate this.. i dont have any experience with writing hooks etc.
https://drive.google.com/file/d/1W7brjx ... sp=sharing


How did you get those entries manually?
Regarding hooks, MHR uses the Re2 remake engine so the re2hook would be used, but that assumes windows and an exe, not a switch.

I got those entries by using Ryujinx (an Switch Emulator similar to yuzu) I started MHR on Ryujinx and searched with Cheat Engine for the String "rom:/".

As Scan Result you get some Adresses of the strings that are currently saved in Memory. If you inspect that Memory Region you see the whole string eg. "rom:/natives/NSW/streaming/Sound/Wwise/bgm_special01_ev_str.pck.3.NSW"

i you get rid of "rom:/" from the string and convert it into murmur3 hash. The Hash you get Should match some of the file hashes from the rechunk.pak

But for my PC when i emulate MHR with Ryujinx it lags so *** much. The highest FPS i got was ~20-30.

If you need a more precise Instructions (with images and stuff) how i did it manually hit me up. Then i post a more detailed one when i have some time to spare.

And i also Tried the rehook but every time i injected it the emulator froze and crashed afterwards
## Post #5
- Username: bootyflute
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Feb 24, 2021 9:28 am
- Post datetime: 2021-04-17T19:23:37+00:00
- Post Title: [Switch]Monster Hunter Rise Demo PAK file

> Reply from Shiroleinchen ↑Sat Apr 17, 2021 7:34 pm at Sat Apr 17, 2021 7:34 pm
>
> 
09williamsad wrote: ↑Sat Apr 17, 2021 4:36 pm
Shiroleinchen wrote: ↑Sat Apr 17, 2021 6:19 am
Hello,
I can only offer this list (i manually put to gether the 31 entries)
At this point i dont have a automatic way on getting those paths and i dont know if i can (semi) automate this.. i dont have any experience with writing hooks etc.
https://drive.google.com/file/d/1W7brjx ... sp=sharing


How did you get those entries manually?
Regarding hooks, MHR uses the Re2 remake engine so the re2hook would be used, but that assumes windows and an exe, not a switch.


I got those entries by using Ryujinx (an Switch Emulator similar to yuzu) I started MHR on Ryujinx and searched with Cheat Engine for the String "rom:/".

As Scan Result you get some Adresses of the strings that are currently saved in Memory. If you inspect that Memory Region you see the whole string eg. "rom:/natives/NSW/streaming/Sound/Wwise/bgm_special01_ev_str.pck.3.NSW"

i you get rid of "rom:/" from the string and convert it into murmur3 hash. The Hash you get Should match some of the file hashes from the rechunk.pak

But for my PC when i emulate MHR with Ryujinx it lags so *** much. The highest FPS i got was ~20-30.

If you need a more precise Instructions (with images and stuff) how i did it manually hit me up. Then i post a more detailed one when i have some time to spare.

And i also Tried the rehook but every time i injected it the emulator froze and crashed afterwards

If you make any progress with any sort of automation to this I will be willing to try and get the filelist, I can emulate it pretty well and would be more than willing to help!
## Post #6
- Username: Shiroleinchen
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Feb 19, 2016 1:01 am
- Post datetime: 2021-04-17T19:46:03+00:00
- Post Title: [Switch]Monster Hunter Rise Demo PAK file

> Reply from bootyflute ↑Sun Apr 18, 2021 3:23 am at Sun Apr 18, 2021 3:23 am
>
> 
Shiroleinchen wrote: ↑Sat Apr 17, 2021 7:34 pm
09williamsad wrote: ↑Sat Apr 17, 2021 4:36 pm


How did you get those entries manually?
Regarding hooks, MHR uses the Re2 remake engine so the re2hook would be used, but that assumes windows and an exe, not a switch.


I got those entries by using Ryujinx (an Switch Emulator similar to yuzu) I started MHR on Ryujinx and searched with Cheat Engine for the String "rom:/".

As Scan Result you get some Adresses of the strings that are currently saved in Memory. If you inspect that Memory Region you see the whole string eg. "rom:/natives/NSW/streaming/Sound/Wwise/bgm_special01_ev_str.pck.3.NSW"

i you get rid of "rom:/" from the string and convert it into murmur3 hash. The Hash you get Should match some of the file hashes from the rechunk.pak

But for my PC when i emulate MHR with Ryujinx it lags so *** much. The highest FPS i got was ~20-30.

If you need a more precise Instructions (with images and stuff) how i did it manually hit me up. Then i post a more detailed one when i have some time to spare.

And i also Tried the rehook but every time i injected it the emulator froze and crashed afterwards


If you make any progress with any sort of automation to this I will be willing to try and get the filelist, I can emulate it pretty well and would be more than willing to help!

What are your PC Specs if i can ask? Or what did you do that you can emulate it pretty well? That would help me to get this properly up and running for testing and also emulate other titles as well.
## Post #7
- Username: bootyflute
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Feb 24, 2021 9:28 am
- Post datetime: 2021-04-17T22:24:50+00:00
- Post Title: [Switch]Monster Hunter Rise Demo PAK file

> Reply from Shiroleinchen ↑Sun Apr 18, 2021 3:46 am at Sun Apr 18, 2021 3:46 am
>
> 
bootyflute wrote: ↑Sun Apr 18, 2021 3:23 am
Shiroleinchen wrote: ↑Sat Apr 17, 2021 7:34 pm


I got those entries by using Ryujinx (an Switch Emulator similar to yuzu) I started MHR on Ryujinx and searched with Cheat Engine for the String "rom:/".

As Scan Result you get some Adresses of the strings that are currently saved in Memory. If you inspect that Memory Region you see the whole string eg. "rom:/natives/NSW/streaming/Sound/Wwise/bgm_special01_ev_str.pck.3.NSW"

i you get rid of "rom:/" from the string and convert it into murmur3 hash. The Hash you get Should match some of the file hashes from the rechunk.pak

But for my PC when i emulate MHR with Ryujinx it lags so *** much. The highest FPS i got was ~20-30.

If you need a more precise Instructions (with images and stuff) how i did it manually hit me up. Then i post a more detailed one when i have some time to spare.

And i also Tried the rehook but every time i injected it the emulator froze and crashed afterwards


If you make any progress with any sort of automation to this I will be willing to try and get the filelist, I can emulate it pretty well and would be more than willing to help!


What are your PC Specs if i can ask? Or what did you do that you can emulate it pretty well? That would help me to get this properly up and running for testing and also emulate other titles as well.

I recently built a new computer so I got a Ryzen 3900x, and a 3060, 16gb of ram, and a 500gb ssd.
For settings in Ryujinx the only thing I changed was expand DRAM to 6gb, but not sure it really makes a difference. I loaded up cheat engine and could find a max of about 12 or so when searching "rom:/" and it was all mostly audio files. 

Thing is I can't get it to run in Yuzu though, which I was hoping to get running but I'm mostly after 3d models from the files.
## Post #8
- Username: Shiroleinchen
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Feb 19, 2016 1:01 am
- Post datetime: 2021-04-18T15:34:43+00:00
- Post Title: [Switch]Monster Hunter Rise Demo PAK file

> Reply from bootyflute ↑Sun Apr 18, 2021 6:24 am at Sun Apr 18, 2021 6:24 am
>
> 
Shiroleinchen wrote: ↑Sun Apr 18, 2021 3:46 am
bootyflute wrote: ↑Sun Apr 18, 2021 3:23 am


If you make any progress with any sort of automation to this I will be willing to try and get the filelist, I can emulate it pretty well and would be more than willing to help!


What are your PC Specs if i can ask? Or what did you do that you can emulate it pretty well? That would help me to get this properly up and running for testing and also emulate other titles as well.


I recently built a new computer so I got a Ryzen 3900x, and a 3060, 16gb of ram, and a 500gb ssd.
For settings in Ryujinx the only thing I changed was expand DRAM to 6gb, but not sure it really makes a difference. I loaded up cheat engine and could find a max of about 12 or so when searching "rom:/" and it was all mostly audio files. 

Thing is I can't get it to run in Yuzu though, which I was hoping to get running but I'm mostly after 3d models from the files.

I have also set this setting to expand DRAM to 6gb. I have a Ryzen 5 3600 and a Nvidia RTX 2070 Super but its doesnt nearly in the range around ~30 fps which is sad   . And i hope our 3060 isnt the reason that it runs for you pretty well but for me its a lag fiesta.

And for yuzu i also can't get it even to start on yuzu.

And i also noticed it that strings are mostly wwise that cheat engine shows but i look if find a better way to get those without spending to much CPU/RAM when searching for those.
## Post #9
- Username: bootyflute
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Feb 24, 2021 9:28 am
- Post datetime: 2021-04-19T02:50:42+00:00
- Post Title: [Switch]Monster Hunter Rise Demo PAK file

> Reply from Shiroleinchen ↑Sun Apr 18, 2021 11:34 pm at Sun Apr 18, 2021 11:34 pm
>
> 
bootyflute wrote: ↑Sun Apr 18, 2021 6:24 am
Shiroleinchen wrote: ↑Sun Apr 18, 2021 3:46 am


What are your PC Specs if i can ask? Or what did you do that you can emulate it pretty well? That would help me to get this properly up and running for testing and also emulate other titles as well.


I recently built a new computer so I got a Ryzen 3900x, and a 3060, 16gb of ram, and a 500gb ssd.
For settings in Ryujinx the only thing I changed was expand DRAM to 6gb, but not sure it really makes a difference. I loaded up cheat engine and could find a max of about 12 or so when searching "rom:/" and it was all mostly audio files. 

Thing is I can't get it to run in Yuzu though, which I was hoping to get running but I'm mostly after 3d models from the files.


I have also set this setting to expand DRAM to 6gb. I have a Ryzen 5 3600 and a Nvidia RTX 2070 Super but its doesnt nearly in the range around ~30 fps which is sad   . And i hope our 3060 isnt the reason that it runs for you pretty well but for me its a lag fiesta.

And for yuzu i also can't get it even to start on yuzu.

And i also noticed it that strings are mostly wwise that cheat engine shows but i look if find a better way to get those without spending to much CPU/RAM when searching for those.

Id think it should run nearly identical but that is weird you can't get the fps to be higher, id say that if I had all the shaders cached the game would run nearly perfect for me but I also have only run around the level a few times and haven't tried to really fight anything much. 

For yuzu the best I could get is getting the game to load up until the intro cutscene/menu. 

If you get anywhere with this I will still totally do my best to help, best I could do was dump all the files and view them with a hex editor to get some names of certain meshes I was looking at but of course there's no file structure info in them really.
## Post #10
- Username: bootyflute
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Feb 24, 2021 9:28 am
- Post datetime: 2021-05-01T21:29:51+00:00
- Post Title: [Switch]Monster Hunter Rise Demo PAK file

> Reply from Shiroleinchen ↑Sun Apr 18, 2021 11:34 pm at Sun Apr 18, 2021 11:34 pm
>
> 
bootyflute wrote: ↑Sun Apr 18, 2021 6:24 am
Shiroleinchen wrote: ↑Sun Apr 18, 2021 3:46 am


What are your PC Specs if i can ask? Or what did you do that you can emulate it pretty well? That would help me to get this properly up and running for testing and also emulate other titles as well.


I recently built a new computer so I got a Ryzen 3900x, and a 3060, 16gb of ram, and a 500gb ssd.
For settings in Ryujinx the only thing I changed was expand DRAM to 6gb, but not sure it really makes a difference. I loaded up cheat engine and could find a max of about 12 or so when searching "rom:/" and it was all mostly audio files. 

Thing is I can't get it to run in Yuzu though, which I was hoping to get running but I'm mostly after 3d models from the files.


I have also set this setting to expand DRAM to 6gb. I have a Ryzen 5 3600 and a Nvidia RTX 2070 Super but its doesnt nearly in the range around ~30 fps which is sad   . And i hope our 3060 isnt the reason that it runs for you pretty well but for me its a lag fiesta.

And for yuzu i also can't get it even to start on yuzu.

And i also noticed it that strings are mostly wwise that cheat engine shows but i look if find a better way to get those without spending to much CPU/RAM when searching for those.
[https://github.com/mhvuze/MonsterHunter ... Game-Files](https://github.com/mhvuze/MonsterHunterRiseModding/wiki/Extracting-Game-Files)
## Post #11
- Username: Shiroleinchen
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Feb 19, 2016 1:01 am
- Post datetime: 2021-05-01T21:52:24+00:00
- Post Title: [Switch]Monster Hunter Rise Demo PAK file

> Reply from bootyflute ↑Sun May 02, 2021 5:29 am at Sun May 02, 2021 5:29 am
>
> 
Shiroleinchen wrote: ↑Sun Apr 18, 2021 11:34 pm
bootyflute wrote: ↑Sun Apr 18, 2021 6:24 am


I recently built a new computer so I got a Ryzen 3900x, and a 3060, 16gb of ram, and a 500gb ssd.
For settings in Ryujinx the only thing I changed was expand DRAM to 6gb, but not sure it really makes a difference. I loaded up cheat engine and could find a max of about 12 or so when searching "rom:/" and it was all mostly audio files. 

Thing is I can't get it to run in Yuzu though, which I was hoping to get running but I'm mostly after 3d models from the files.


I have also set this setting to expand DRAM to 6gb. I have a Ryzen 5 3600 and a Nvidia RTX 2070 Super but its doesnt nearly in the range around ~30 fps which is sad   . And i hope our 3060 isnt the reason that it runs for you pretty well but for me its a lag fiesta.

And for yuzu i also can't get it even to start on yuzu.

And i also noticed it that strings are mostly wwise that cheat engine shows but i look if find a better way to get those without spending to much CPU/RAM when searching for those.

https://github.com/mhvuze/MonsterHunter ... Game-Files

Oh cool the created a MHRise.lst but i wonder how they did this (just out of curiosity)
And Thank your for Shareing it wiht with me!
## Post #12
- Username: bootyflute
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Feb 24, 2021 9:28 am
- Post datetime: 2021-05-01T23:22:14+00:00
- Post Title: [Switch]Monster Hunter Rise Demo PAK file

> Reply from Shiroleinchen ↑Sun May 02, 2021 5:52 am at Sun May 02, 2021 5:52 am
>
> 
bootyflute wrote: ↑Sun May 02, 2021 5:29 am
Shiroleinchen wrote: ↑Sun Apr 18, 2021 11:34 pm


I have also set this setting to expand DRAM to 6gb. I have a Ryzen 5 3600 and a Nvidia RTX 2070 Super but its doesnt nearly in the range around ~30 fps which is sad   . And i hope our 3060 isnt the reason that it runs for you pretty well but for me its a lag fiesta.

And for yuzu i also can't get it even to start on yuzu.

And i also noticed it that strings are mostly wwise that cheat engine shows but i look if find a better way to get those without spending to much CPU/RAM when searching for those.

https://github.com/mhvuze/MonsterHunter ... Game-Files



Oh cool the created a MHRise.lst but i wonder how they did this (just out of curiosity)
And Thank your for Shareing it wiht with me!

I'm not sure how they got it, I might have to do a little digging to figure that out. And you're very welcome! I was searching around today to see if anyone has gotten it and had no luck, but searched github for monster hunter rise (as I do with random games to see what projects people have for them) and saw there was some utilities just for rise!
## Post #13
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2021-05-26T06:13:46+00:00
- Post Title: [Switch]Monster Hunter Rise Demo PAK file

A file list has been made [https://github.com/mhvuze/MonsterHunter ... Game-Files](https://github.com/mhvuze/MonsterHunterRiseModding/wiki/Extracting-Game-Files)
Texture conversion [https://github.com/AsteriskAmpersand/MHR_Tex_Chopper](https://github.com/AsteriskAmpersand/MHR_Tex_Chopper)
Model conversion [https://residentevilmodding.boards.net/ ... mesh-files](https://residentevilmodding.boards.net/thread/12520/noesis-plugin-previewing-mesh-files)

Models converted to FBX and audio converted to OGG is now in my archive: <link removed due to site policy>
Google my username to find the link, as i cannot post it here.
## Post #14
- Username: OkamiTakahashi
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 13, 2022 11:52 am
- Post datetime: 2022-01-13T04:03:59+00:00
- Post Title: [Switch]Monster Hunter Rise Demo PAK file

Apologies for the necropost, not normally something I would do, BUT, this is one of the only places online I've seen discussion of ripping from MHR- and literally the only reason I made an account.

^The archive in the above post is very nice, and I thank you again for it, but what confuses me is the way files are organized. I've seen the zips in there for player voices in both Japanese and English, but what I'm not seeing is the Monster Hunter language dub. Sure, some of the sounds are the same, such as grunts and breathing and the like- same voice actors as the Japanese dub. But it would be nice if I had those MH language voices.

The main reason I'm even interested in getting my hands on these files is for reasons not related to modding Monster Hunter Rise, but for Breath of the Wild- both Wii U and Switch versions. Option 1 for the player voices is Kengo Takanashi- and those of you Switch players with keen ears will have taken notice that it sounds familiar- because it's literally BOTW Link. While the Japanese lines have been helpful for the shorter grunts and such, I would like to be able to use some of the MH ones, provided they're short enough (such as riding a Palamute, picking up materials, carving, cooking a steak, etc), in my project- an enhanced BOTW voicepack using sounds from  Hyrule Warriors: Age of Calamity and Monster Hunter Rise. I always felt Link sounded a bit weak in BOTW, but these two games he sounded...better? Like the VA really got into the role better. And actual speaks some in MHR. It's the closest thing to an actual Link speaking since The Wind Waker tbh- though those were lines in English, not a constructed language, and I did want to include some of those short spoken lines if I could.

If any of you guys can help me out with this, I'd appreciate it. Also, MHR just dropped on Steam today, so people won't need to mod their Switches to rip the pak file now...though I've had difficulty getting it to work. Never done anything like that before Thanks again for the above archive though, it's been helpful.
