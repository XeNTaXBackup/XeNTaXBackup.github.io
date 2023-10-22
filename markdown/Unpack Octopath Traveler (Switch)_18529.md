## Post #1
- Username: testimilate
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 01, 2018 12:02 pm
- Post datetime: 2018-08-01T04:05:27+00:00
- Post Title: Unpack Octopath Traveler (Switch)

The whole game is a .pak file after extracting the RomFS. Where I am getting stuck is the sprites are all garbled (large box with pixels thrown everywhere) after I unpack the .pak with quickbms. Anyone have any ideas? Would just like to be able to extract the spritesheets.

EDIT: It may not be the file that is bad actually. I can only see the garbled images in umodel. Is there another program that will allow you to see the 2d sprites instead?
## Post #2
- Username: testimilate
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2018-08-01T05:36:53+00:00
- Post Title: Unpack Octopath Traveler (Switch)

> Is there another program that will allow you to see the 2d sprites instead?

Maybe try this [viewtopic.php?f=33&t=15540](http://forum.xentax.com/viewtopic.php?f=33&t=15540)
## Post #3
- Username: testimilate
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 01, 2018 12:02 pm
- Post datetime: 2018-08-01T13:00:17+00:00
- Post Title: Unpack Octopath Traveler (Switch)

> Reply from ikskoks
>
>  Is there another program that will allow you to see the 2d sprites instead?

Maybe try this viewtopic.php?f=33&t=15540

Thank you for the suggestion. But, none of these seem to be able to do it. All the files are .uexp and .uassest
## Post #4
- Username: ECOYinyang
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 08, 2019 10:51 pm
- Post datetime: 2019-08-08T14:57:41+00:00
- Post Title: Unpack Octopath Traveler (Switch)

When you used Quickbms to extract the .Pak file for Octopath, did you need a script? I'm also trying to modify the sprites, but i can't seem to get into the .Pak file
## Post #5
- Username: masagrator
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Oct 17, 2018 7:45 am
- Post datetime: 2019-08-09T09:04:24+00:00
- Post Title: Unpack Octopath Traveler (Switch)

This tool can convert UE4 Switch DXT5 and RBGA textures in both ways, but if you want to convert it to be readable by game, then it's getting little complicated, espiecially for small textures (height below 128).
[https://gbatemp.net/threads/noesis-mod- ... e4.535571/](https://gbatemp.net/threads/noesis-mod-tiling-texture-for-ue4.535571/)

> Both functions are working only with *.uasset (+ *.uexp & *.ubulk, but it's loaded by *.uasset file only)
>
> 
>
> How to untile texture:
>
> Copy assets (uasset + uexp) to noesis folder. Drop *.uasset file ready for untiling to "Unswizzle.cmd". It will create PNG with the same name.

And about repacking pak files
[https://gbatemp.net/threads/how-to-unpa ... es.531784/](https://gbatemp.net/threads/how-to-unpack-and-repack-unreal-engine-4-files.531784/)
## Post #6
- Username: ECOYinyang
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 08, 2019 10:51 pm
- Post datetime: 2019-08-09T18:33:08+00:00
- Post Title: Unpack Octopath Traveler (Switch)

> Reply from masagrator ↑Fri Aug 09, 2019 5:04 pm at Fri Aug 09, 2019 5:04 pm
>
> 
This tool can convert UE4 Switch DXT5 and RBGA textures in both ways, but if you want to convert it to be readable by game, then it's getting little complicated, espiecially for small textures (height below 128).
https://gbatemp.net/threads/noesis-mod- ... e4.535571/
Both functions are working only with *.uasset (+ *.uexp & *.ubulk, but it's loaded by *.uasset file only)

How to untile texture:
Copy assets (uasset + uexp) to noesis folder. Drop *.uasset file ready for untiling to "Unswizzle.cmd". It will create PNG with the same name.


And about repacking pak files
https://gbatemp.net/threads/how-to-unpa ... es.531784/
Will this also work for the Steam version?
## Post #7
- Username: masagrator
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Oct 17, 2018 7:45 am
- Post datetime: 2019-08-10T00:55:42+00:00
- Post Title: Unpack Octopath Traveler (Switch)

PC Textures are not tiled, so you don't need Noesis, you can use UEViewer for unpacking Textures.

In case of pak tutorial - yes, because Octopath on PC is not encrypted.
