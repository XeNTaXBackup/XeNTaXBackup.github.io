## Post #1
- Username: mrrrdude
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 05, 2017 2:32 am
- Post datetime: 2020-10-21T11:14:28+00:00
- Post Title: Batman Arkham Knight PS4 (Batman Justice League 3000 Sony Exclusive Skin)

Hi Everyone,

I'm relatively new to this forum though I searched for a solution here and on google. 
I want to extract the Batman Justice League 3000 Exclusive skin from PS4 and I was able to extract the pkg file and then using glidor extract tool to unpack the .xxx file into the unreal engine. I tried using glidors tool and some other tools around here (For other games) to get the meshes and textures but unfortunately nothing worked.

Is anybody able to take a look and help advice how I could go about extracting this files? 
*Attached the files that contain the .SkeletalMesh and textures that are in .Texture2D. 

[https://drive.google.com/file/d/1EXZw3D ... sp=sharing](https://drive.google.com/file/d/1EXZw3DFpTnA19u_IomDhgL1tReexvuTk/view?usp=sharing)

I have the .tfc files as well if there is of any help, please let me know.

Thank you!
M
## Post #2
- Username: mrrrdude
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 05, 2017 2:32 am
- Post datetime: 2020-11-08T14:07:53+00:00
- Post Title: Batman Arkham Knight PS4 (Batman Justice League 3000 Sony Exclusive Skin)

Hi Everyone,

Anyone interested to take a look at it?

Thank you!
## Post #3
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-11-08T16:45:21+00:00
- Post Title: Batman Arkham Knight PS4 (Batman Justice League 3000 Sony Exclusive Skin)

The link has a problem.
## Post #4
- Username: mrrrdude
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 05, 2017 2:32 am
- Post datetime: 2020-11-08T17:20:45+00:00
- Post Title: Batman Arkham Knight PS4 (Batman Justice League 3000 Sony Exclusive Skin)

> Reply from reh ↑Mon Nov 09, 2020 12:45 am at Mon Nov 09, 2020 12:45 am
>
> 
The link has a problem.

Thank you! I didn't know, please let me know if this works for you:  [https://drive.google.com/file/d/1EXZw3D ... sp=sharing](https://drive.google.com/file/d/1EXZw3DFpTnA19u_IomDhgL1tReexvuTk/view?usp=sharing)

The files above are the ones I extracted from Playable_Batman_JusticeL3000_SF.xxx using Glidord's tools and here are the files extracted from the pkg file of the PS4 build: [https://drive.google.com/file/d/1Q2y8BB ... sp=sharing](https://drive.google.com/file/d/1Q2y8BBX93uSYTwugaDo_k9w81553uQUn/view?usp=sharing)

Please let me know if you need anything else from my end.

All the best!
## Post #5
- Username: mrrrdude
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 05, 2017 2:32 am
- Post datetime: 2020-11-18T17:24:12+00:00
- Post Title: Batman Arkham Knight PS4 (Batman Justice League 3000 Sony Exclusive Skin)

> Reply from reh ↑Mon Nov 09, 2020 12:45 am at Mon Nov 09, 2020 12:45 am
>
> 
The link has a problem.

Hey, 

Hope you are doing well.
Had any chance to look at the files?

Thank you,
M
## Post #6
- Username: mrrrdude
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 05, 2017 2:32 am
- Post datetime: 2021-01-11T18:50:32+00:00
- Post Title: Batman Arkham Knight PS4 (Batman Justice League 3000 Sony Exclusive Skin)

Hey,

Is anyone able to help with this?

Thank you!
M
## Post #7
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2021-01-12T04:47:28+00:00
- Post Title: Batman Arkham Knight PS4 (Batman Justice League 3000 Sony Exclusive Skin)

The model needs to have an edition to look good. To see the UVs you have to put HalfFloat - HF.



DLC_Batman_JL3000_Skin_Body.SkeletalMesh.png (57.49 KiB) Viewed 277 times
## Post #8
- Username: mrrrdude
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 05, 2017 2:32 am
- Post datetime: 2021-01-12T10:23:57+00:00
- Post Title: Batman Arkham Knight PS4 (Batman Justice League 3000 Sony Exclusive Skin)

> Reply from reh ↑Tue Jan 12, 2021 12:47 pm at Tue Jan 12, 2021 12:47 pm
>
> 
The model needs to have an edition to look good. To see the UVs you have to put HalfFloat - HF.
DLC_Batman_JL3000_Skin_Body.SkeletalMesh.png

waaa! you just made by day! Thank you! I didn't think this was possible   Any chance you can point me to the mesh extractor tool? I think I saw it used for the Batman Arcade game, if I'm not mistake. Am I correct?
Also, what do you mean by "The model needs to have an edition to look good" ?

*Update, so I managed to use the Hex2Obj tool using your settings, though I can't figure how to extract a good shape of the model.
## Post #9
- Username: mrrrdude
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 05, 2017 2:32 am
- Post datetime: 2021-10-09T21:43:12+00:00
- Post Title: Batman Arkham Knight PS4 (Batman Justice League 3000 Sony Exclusive Skin)

Hey guys,

Would there aby anyone willing to help me find a way to extract this exclusive 3d model (Batman Justice League 3000 from Batman Arkham Knight on PS4?

Thanks!
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-10-10T06:14:20+00:00
- Post Title: Batman Arkham Knight PS4 (Batman Justice League 3000 Sony Exclusive Skin)

Well, 9 months later?  

Ok, you're talking of something like this?
.



BatmanJL3000.png (227.02 KiB) Viewed 204 times



Here you go, a little bit tricky since hex2obj doesn't support short verts combined with halffloat uvs (you might try the tools from Bigchillghost or Lazov).
Save the mesh (File/SaveAs mesh) in two ways: 1) Short_All 2) HF_all 
Open 1)*.obj file in your preferred texteditor then replace (without the quotes): "vt " by "#vt "
(Pay attention to the blank! -> " ")
Open 2)*.obj file in your preferred texteditor then replace (without the quotes): "v " by "#v "
(Pay attention to the blank! -> " ")
delete all face indices lines
f 4298/4298 4299/4299 4303/4303 
...
f 44953/44953 44954/44954 44947/44947 
Now you'll need to merge the two obj files:
----------------------------------------------------
Select all lines of the remaining block in 2)*.obj and copy them into 1)*obj
(place them before the f ... block there)


Scaling required, I used 0.33 for z and 0.85 for x in blender, just a wild guess, though.
## Post #11
- Username: mrrrdude
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 05, 2017 2:32 am
- Post datetime: 2021-10-12T20:33:01+00:00
- Post Title: Batman Arkham Knight PS4 (Batman Justice League 3000 Sony Exclusive Skin)

> Reply from shakotay2 ↑Sun Oct 10, 2021 2:14 pm at Sun Oct 10, 2021 2:14 pm
>
> 
Well, 9 months later?  

Ok, you're talking of something like this?
.
BatmanJL3000.png

Here you go, a little bit tricky since hex2obj doesn't support short verts combined with halffloat uvs (you might try the tools from Bigchillghost or Lazov).
Save the mesh (File/SaveAs mesh) in two ways: 1) Short_All 2) HF_all 
Open 1)*.obj file in your preferred texteditor then replace (without the quotes): "vt " by "#vt "
(Pay attention to the blank! -> " ")
Open 2)*.obj file in your preferred texteditor then replace (without the quotes): "v " by "#v "
(Pay attention to the blank! -> " ")
delete all face indices lines
f 4298/4298 4299/4299 4303/4303 
...
f 44953/44953 44954/44954 44947/44947 
Now you'll need to merge the two obj files:
----------------------------------------------------
Select all lines of the remaining block in 2)*.obj and copy them into 1)*obj
(place them before the f ... block there)


Scaling required, I used 0.33 for z and 0.85 for x in blender, just a wild guess, though.

Yes, That's exactly what I'm looking for! To learn to extract this model, body, cape, cowl and textures. I'm really a nood when it comes to the hex editors, mostly I have no idea what I'm doing basically.
I'll try the above settings you mentioned to see if I'm going to get the same results (Though with my knowledge, probably I'm going to clip my ears in).

Thank you for taking the time to help me out!

I can say that the settings beat me, would you be able to give me a more detail walkthrough on setting up the settings in hex2obj or what tool you used to arive at the result shown in the blender screenshot?
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-10-14T09:53:46+00:00
- Post Title: Batman Arkham Knight PS4 (Batman Justice League 3000 Sony Exclusive Skin)

> Reply from mrrrdude ↑Wed Oct 13, 2021 4:33 am at Wed Oct 13, 2021 4:33 am
>
> I'm really a nood when it comes to the hex editors, mostly I have no idea what I'm doing basically.I'd suggest to read tutorials, for example from Bigchillghost.

> would you be able to give me a more detail walkthrough on setting up the settings in hex2objNo time for such, sorry. Press the 'tut' button in hex2obj, load said model in a hex editor, then check the given addresses in reh's post: 
> Reply from reh ↑Tue Jan 12, 2021 12:47 pm at Tue Jan 12, 2021 12:47 pm
>
> 
--------------

> or what tool you used to arive at the result shown in the blender screenshot?There's no other tool than hex2obj. Just joined some sub meshes in blender (ctrl j). So understanding blender basics will be your next step.
## Post #13
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-10-14T15:09:31+00:00
- Post Title: Batman Arkham Knight PS4 (Batman Justice League 3000 Sony Exclusive Skin)

Using AXE:



DLC_Batman_JL3000_Skin_Body.SkeletalMesh.png (203.89 KiB) Viewed 151 times



BBox layout at address 0x4468 is as [maxY minY maxZ minZ maxX minX], you'll need to reorganize them as [maxX maxY maxZ minX minY minZ], or scale the mesh manually.
## Post #14
- Username: joshmark
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Nov 02, 2021 11:58 pm
- Post datetime: 2022-06-08T03:59:33+00:00
- Post Title: Batman Arkham Knight PS4 (Batman Justice League 3000 Sony Exclusive Skin)

If you wouldn't mind, do you think you could post the extracted model that was generated? with textures too perhaps?
## Post #15
- Username: mrrrdude
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 05, 2017 2:32 am
- Post datetime: 2022-06-08T12:09:41+00:00
- Post Title: Batman Arkham Knight PS4 (Batman Justice League 3000 Sony Exclusive Skin)

> Reply from joshmark ↑Wed Jun 08, 2022 11:59 am at Wed Jun 08, 2022 11:59 am
>
> 
If you wouldn't mind, do you think you could post the extracted model that was generated? with textures too perhaps?

Hey! I wouldn't mind, but unfortunatly I didn't had much success with extracting the model and textures for this.
I don't have the necessary understanding about hex and process using the proposed tools   

The original files can still be accessed above thus if somone is able to help us with extracting this I would really appreacite it, am able to even offer a small reward of 20$, if somone is able to extract the 3d model completly with intact uvs and textures since I can't afford much more.
## Post #16
- Username: joshmark
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Nov 02, 2021 11:58 pm
- Post datetime: 2022-06-09T06:11:28+00:00
- Post Title: Re: Batman Arkham Knight PS4 (Batman Justice League 3000 Sony Exclusive Skin)

> Reply from Bigchillghost ↑Thu Oct 14, 2021 11:09 pm at Thu Oct 14, 2021 11:09 pm
>
> 
Using AXE:
DLC_Batman_JL3000_Skin_Body.SkeletalMesh.png


BBox layout at address 0x4468 is as [maxY minY maxZ minZ maxX minX], you'll need to reorganize them as [maxX maxY maxZ minX minY minZ], or scale the mesh manually.

I meant to quote you on my post before this, but  do you think you could post the extracted model with textures too that was generated?
