## Post #1
- Username: projinf3d
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jul 17, 2016 8:56 am
- Post datetime: 2016-10-07T06:05:52+00:00
- Post Title: SWBF3 Ninja Ripper - Star Destroyer UV issues

Hi All...

I've becoming reasonably proficient with the Ninja Ripper & 3ds Max, matching correct .dds with .rip, importing correct UV Coord's etc but this model has me stumped for the majority of the meshes!? 

I'm working on the Star Destroyer model ripped from Star Wars Battlefront online 'Death Star' expansion pack. So far Ive managed to successfully map some meshes of the ship for eg: thrusts, command bridge, shields or antenna (the two spherical objects on top of command bridge) but the rest I am struggling to match up for the main chassis and other parts.

I get the impression some of the textures for the rest of the ship need to be somewhat merged together on different scales!? It seems some of the bump maps detail are just a portion to some of the diffuses!?.. but i could be wrong??..

The .rip & texture map files attached belong to each other but unable to get correct UV coord's!??

[http://s000.tinyupload.com/?file_id=723 ... 1128075601](http://s000.tinyupload.com/?file_id=72385323201128075601)

Help please
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-07T20:08:29+00:00
- Post Title: SWBF3 Ninja Ripper - Star Destroyer UV issues

you mean Dice SWBF   
it looks like this rip file has 2 UV sets



Mesh_0008_rip.png (13.22 KiB) Viewed 89 times



the UVs on the left are at position 60/64
the UVs on the right are at position 68/72 and match your sample texture

i think 68/72 would be 17 and 18 for U and V in the plugin setting
## Post #3
- Username: projinf3d
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jul 17, 2016 8:56 am
- Post datetime: 2016-10-08T02:33:28+00:00
- Post Title: SWBF3 Ninja Ripper - Star Destroyer UV issues

> Reply from AceWell
>
>  i think 68/72 would be 17 and 18 for U and V in the plugin setting

Well there you go!... for some cautious reason I assumed there was set sequence rule of 'even number/odd number' (16/17; 18/19 etc) .. and no other combinations as the plugins default was '6/7'!?.. Great to know more UV channel options!... Thanks for that!!!   

I'll see how i go with the other textures as I have a feeling these maybe applied differently!?...
