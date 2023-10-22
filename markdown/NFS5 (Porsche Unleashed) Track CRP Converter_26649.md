## Post #1
- Username: Erik The Born
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jun 10, 2015 11:01 pm
- Post datetime: 2023-04-10T14:37:48+00:00
- Post Title: NFS5 (Porsche Unleashed) Track CRP Converter?

Hello! One of my favorite childhood games is Need for Speed: Porsche Unleashed, It surprisingly still have a communities around it to this day. As with almost all retro car games NFS5 had car mods that adds new cars and such to the game but one thing that's always eluded the community is the NFS5 tracks models. They seem to be different than the car models and to this day, no proper 3d model conversion tool has been made...

3D editors like Zmodeler had a CRP filter which worked on *some* of the game cars but not the tracks. Scrap studio does not export to a usable 3D format (uses ARP and exported ARPS from tracks does not open in Zmodelers ARP filter) and NFS5 carparts editor can only get small bits of the tracks.

The NFS5 mesh CRP format in general has been researched. The good people of OpenNFS has kindly put some elbow work into it!

[https://github.com/OpenNFS/OpenNFS/tree ... ude/CrpLib](https://github.com/OpenNFS/OpenNFS/tree/main/include/CrpLib) <-The library part to handle CRP
[https://github.com/OpenNFS/OpenNFS/blob ... er.cpp#L58](https://github.com/OpenNFS/OpenNFS/blob/a3c928077add2bd5d5f3463daee6008f150a0a54/src/Loaders/NFS5/NFS5Loader.cpp#L58) <-- NFS5 Load CRP function of OpenNFS.

[https://github.com/dima424658/LibOpenNF ... e/NFS5/CRP](https://github.com/dima424658/LibOpenNFS/tree/main/include/NFS5/CRP) More CRP stuff.

[https://drive.google.com/file/d/1-htXur ... jXUQQ/view](https://drive.google.com/file/d/1-htXurYZRJJUftjdAb6gv-R_SbtjXUQQ/view) To decompress CRP to DRP, might not work with tracks though I am unsure! Or maybe not at all?

[https://github.com/OpenNFS/OpenNFS](https://github.com/OpenNFS/OpenNFS) Just in general has information.

All of this is albeit confusing for a mere NFS5 enthusiast which is why I send it here.

[https://sutopia.net/nextcloud/s/67235](https://sutopia.net/nextcloud/s/67235) Here's Authobahn.crp, its a track from the game.

If anyone here could attempt a conversion tool to obj or such, even just a bit of progress would be huge!  

Thanks!
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-04-12T14:50:04+00:00
- Post Title: NFS5 (Porsche Unleashed) Track CRP Converter?

> Reply from Erik The Born ↑Mon Apr 10, 2023 10:37 pm at Mon Apr 10, 2023 10:37 pm
>
> 
...To decompress CRP to DRP, might not work with tracks though I am unsure! Or maybe not at all?Hello.

If I were a NFS5 enthusiast I would have checked this already.  

Here's a part from Autobahn.drp:
.



carrage02.jpg (50.08 KiB) Viewed 199 times
## Post #3
- Username: Erik The Born
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jun 10, 2015 11:01 pm
- Post datetime: 2023-04-12T16:51:57+00:00
- Post Title: NFS5 (Porsche Unleashed) Track CRP Converter?

Oh I tried and it didnt work for me lol. That's why I said it might not work. Good job though, nice to see its working for you. But how did u achieve this?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-04-12T17:03:13+00:00
- Post Title: NFS5 (Porsche Unleashed) Track CRP Converter?

I selected autobahn.crp in CRP2DRP.exe (Button "Decompress") to extract it. Then used hex2obj to get some vertices.
## Post #5
- Username: Erik The Born
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jun 10, 2015 11:01 pm
- Post datetime: 2023-04-12T17:12:12+00:00
- Post Title: NFS5 (Porsche Unleashed) Track CRP Converter?

> Reply from shakotay2 ↑Thu Apr 13, 2023 1:03 am at Thu Apr 13, 2023 1:03 am
>
> 
I selected autobahn.crp in CRP2DRP.exe (Button "Decompress") to extract it. Then used hex2obj to get some vertices.

Well aren't you amazing! Looks like there might be something for track modders after all!  

[https://github.com/dima424658/LibOpenNF ... e/NFS5/CRP](https://github.com/dima424658/LibOpenNFS/tree/main/include/NFS5/CRP) <-- Maybe should include these as well in the main post.

As always hex2obj is too complicated for me to use myself, but I bet there's people there capable of doing proper work this thing!
## Post #6
- Username: Erik The Born
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jun 10, 2015 11:01 pm
- Post datetime: 2023-04-25T13:23:52+00:00
- Post Title: NFS5 (Porsche Unleashed) Track CRP Converter?

For someone attempting to make a proper converter, I attached a zip file containing a CRP format writeup. It contains information on how the format is structured.
[NFSPUCrp.zip](https://xentaxbackup.github.io/file/23714_NFSPUCrp.zip)
## Post #7
- Username: n7x1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 26, 2023 5:26 pm
- Post datetime: 2023-04-26T20:23:24+00:00
- Post Title: NFS5 (Porsche Unleashed) Track CRP Converter?

Hello the conversion tool seems to have once had this guy on the web there are several tracks from the NFS
Converted NFS PU Industrial Zone to the WorldRacing2 by Krom ([http://krom.reveur.de](http://krom.reveur.de))
[https://youtu.be/AUkzeeyf1_k](https://youtu.be/AUkzeeyf1_k)

I have long been have question of converting and reading Need for Speed Porsche formats and wait tool to conversion tracks
## Post #8
- Username: Erik The Born
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jun 10, 2015 11:01 pm
- Post datetime: 2023-05-15T11:25:32+00:00
- Post Title: NFS5 (Porsche Unleashed) Track CRP Converter?

Hello! We now have a track converter that can be used for Blender!

[https://discord.gg/stsFKfyt](https://discord.gg/stsFKfyt)

There you can download the tools for it!

23 years and we finally have some nice work done on tracks!
## Post #9
- Username: vesko
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 28, 2023 3:44 pm
- Post datetime: 2023-06-28T07:49:31+00:00
- Post Title: NFS5 (Porsche Unleashed) Track CRP Converter?

> Reply from Erik The Born ↑Mon May 15, 2023 7:25 pm at Mon May 15, 2023 7:25 pm
>
> 
Hello! We now have a track converter that can be used for Blender!

https://discord.gg/stsFKfyt

There you can download the tools for it!

23 years and we finally have some nice work done on tracks!

Hey, the invite link is invalid.. :O Could you repost it again?

That info makes me so hyped! Can't wait to start on some tracks!
## Post #10
- Username: Erik The Born
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jun 10, 2015 11:01 pm
- Post datetime: 2023-09-11T17:36:09+00:00
- Post Title: NFS5 (Porsche Unleashed) Track CRP Converter?

[https://discord.gg/5GECDjUAmS](https://discord.gg/5GECDjUAmS)

New link, this one is permanent and should not become invalid.
