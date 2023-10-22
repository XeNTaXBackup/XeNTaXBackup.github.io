## Post #1
- Username: noyou1998
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 06, 2023 12:24 pm
- Post datetime: 2023-10-06T04:28:57+00:00
- Post Title: Ripping models from Beatles Rockband

Hi all
I managed to get a hand on my old Ps3 version of The Beatles: Rockband, and i was able to dump it to my pc with some help. I have the .ISO file. I was wondering how i can go about ripping models and textures from the game directly? I tried using NinjaRipper, but it does not seem to work, and i really do not want to become a patreon for the 2.0 version, and i don't like that it only rips whats shown in the game currently, and not ripping everything in the game entirely. Is there another way to go about this? I cannot seem to find any concrete answers. Any help is appreciated! Thanks
## Post #2
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-10-06T19:03:18+00:00
- Post Title: Ripping models from Beatles Rockband

> Reply from noyou1998 ↑Fri Oct 06, 2023 12:28 pm at Fri Oct 06, 2023 12:28 pm
>
> 
Hi all
I managed to get a hand on my old Ps3 version of The Beatles: Rockband, and i was able to dump it to my pc with some help. I have the .ISO file. I was wondering how i can go about ripping models and textures from the game directly? I tried using NinjaRipper, but it does not seem to work, and i really do not want to become a patreon for the 2.0 version, and i don't like that it only rips whats shown in the game currently, and not ripping everything in the game entirely. Is there another way to go about this? I cannot seem to find any concrete answers. Any help is appreciated! Thanks

Take a look at this thread: 

[viewtopic.php?t=21409](https://forum.xentax.com/viewtopic.php?t=21409)

I have a .py script to import the milo files into Blender, however they don't import skeleton/weights and many of the object positioning is wrong currently. There hasn't been any update or fix the script for over 2 years now but I can upload it here if someone wants to take a look at it and fix it up or make their own version that works.
[io_import_milops3.zip](https://xentaxbackup.github.io/file/24409_io_import_milops3.zip)
## Post #3
- Username: noyou1998
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 06, 2023 12:24 pm
- Post datetime: 2023-10-07T02:16:00+00:00
- Post Title: Ripping models from Beatles Rockband

> Reply from AxelNoir ↑Sat Oct 07, 2023 3:03 am at Sat Oct 07, 2023 3:03 am
>
> 
noyou1998 wrote: ↑Fri Oct 06, 2023 12:28 pm
Hi all
I managed to get a hand on my old Ps3 version of The Beatles: Rockband, and i was able to dump it to my pc with some help. I have the .ISO file. I was wondering how i can go about ripping models and textures from the game directly? I tried using NinjaRipper, but it does not seem to work, and i really do not want to become a patreon for the 2.0 version, and i don't like that it only rips whats shown in the game currently, and not ripping everything in the game entirely. Is there another way to go about this? I cannot seem to find any concrete answers. Any help is appreciated! Thanks


Take a look at this thread: 

viewtopic.php?t=21409

I have a .py script to import the milo files into Blender, however they don't import skeleton/weights and many of the object positioning is wrong currently. There hasn't been any update or fix the script for over 2 years now but I can upload it here if someone wants to take a look at it and fix it up or make their own version that works.

Oh i was looking at this thread, but what stopped me was that i did not have the .dat files, and i have no idea how to get them
## Post #4
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-10-07T12:53:56+00:00
- Post Title: Ripping models from Beatles Rockband

> Reply from noyou1998 ↑Sat Oct 07, 2023 10:16 am at Sat Oct 07, 2023 10:16 am
>
> 
Oh i was looking at this thread, but what stopped me was that i did not have the .dat files, and i have no idea how to get them

I don't think you read the thread correctly then, if I'm not mistaken you don't need the .dat files, just use the Rockband tools to extract the milo ps3 files, which you can then import into blender using the script I linked previously.

[https://github.com/HENDRIX-ZT2/rockband-tools](https://github.com/HENDRIX-ZT2/rockband-tools)

Think there is also a tool out there called ark explorer or something along those lines that lets you view the ark files and extract the milos that way. I don't remember what the business with the dat files is but I don't think I needed them, the dat files i think are inside the milo_ps3 file but with the script I linked previously you can import the milo directly into Blender, though it is unfinished and not correct.
## Post #5
- Username: noyou1998
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 06, 2023 12:24 pm
- Post datetime: 2023-10-08T22:56:30+00:00
- Post Title: Ripping models from Beatles Rockband

> Reply from AxelNoir ↑Sat Oct 07, 2023 8:53 pm at Sat Oct 07, 2023 8:53 pm
>
> 
noyou1998 wrote: ↑Sat Oct 07, 2023 10:16 am
Oh i was looking at this thread, but what stopped me was that i did not have the .dat files, and i have no idea how to get them


I don't think you read the thread correctly then, if I'm not mistaken you don't need the .dat files, just use the Rockband tools to extract the milo ps3 files, which you can then import into blender using the script I linked previously.

https://github.com/HENDRIX-ZT2/rockband-tools

Think there is also a tool out there called ark explorer or something along those lines that lets you view the ark files and extract the milos that way. I don't remember what the business with the dat files is but I don't think I needed them, the dat files i think are inside the milo_ps3 file but with the script I linked previously you can import the milo directly into Blender, though it is unfinished and not correct.

I guess i didn't! Only thing is though, i do not see any milo files in the ISO i have, which is another problem. Not sure how i can find those.
## Post #6
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-10-08T23:03:26+00:00
- Post Title: Ripping models from Beatles Rockband

> Reply from noyou1998 ↑Mon Oct 09, 2023 6:56 am at Mon Oct 09, 2023 6:56 am
>
> 
I guess i didn't! Only thing is though, i do not see any milo files in the ISO i have, which is another problem. Not sure how i can find those.

Yeah they're inside the ark files. Unfortunately I don't remember what I used to export the ark files, but I used the PS3 version of the game to extract the iso, then something like Ark Explorer or tool, not sure which, to extract each ark file which had the milo files inside of them.
## Post #7
- Username: noyou1998
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 06, 2023 12:24 pm
- Post datetime: 2023-10-09T03:24:49+00:00
- Post Title: Ripping models from Beatles Rockband

> Reply from AxelNoir ↑Mon Oct 09, 2023 7:03 am at Mon Oct 09, 2023 7:03 am
>
> 
noyou1998 wrote: ↑Mon Oct 09, 2023 6:56 am
I guess i didn't! Only thing is though, i do not see any milo files in the ISO i have, which is another problem. Not sure how i can find those.


Yeah they're inside the ark files. Unfortunately I don't remember what I used to export the ark files, but I used the PS3 version of the game to extract the iso, then something like Ark Explorer or tool, not sure which, to extract each ark file which had the milo files inside of them.

Did some digging, and it looks like that tool was called Ark Tools, and the guy who made it doesn't have it on his blog anymore, but i was able to find it off of a forum thankfully. Unfortunately, V7 does not want to read my files. It keeps saying that it does not find any files. I am wondering if i need to find the previous version or something?
