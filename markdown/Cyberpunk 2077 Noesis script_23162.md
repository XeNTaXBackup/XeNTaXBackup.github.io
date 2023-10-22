## Post #1
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-12-13T21:16:16+00:00
- Post Title: Cyberpunk 2077 Noesis script

Akderebur and I worked together to make a Noesis script for that game. It works on the .mesh files extracted by rfuzzo's CP77 Tools [https://github.com/rfuzzo/CP77Tools](https://github.com/rfuzzo/CP77Tools)

Supported: 
-positions (vertices scaled correctly), UVs, normals, bone indices, bone weights, bones and bone names.

06/02/2021 EDIT : Big thanks to alphaZ, who added a lot of features to our original quick and dirty script. You can download his much more complete and actively maintained version of the script here : [viewtopic.php?f=16&t=23162&start=30#p171144](https://forum.xentax.com/viewtopic.php?f=16&t=23162&start=30#p171144)

Credits: 
-akderebur and I for researching the format and writing the original script 
-alphaZ for doing additional research and improving our original release
-rfuzzo for the CP77Tools
-SurprisedMango, Divined, Yoratoni, ZeRoY, Banishingshift for some help for the tests
## Post #2
- Username: ubern00bkye
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Nov 24, 2020 5:51 am
- Post datetime: 2020-12-14T20:19:01+00:00
- Post Title: Cyberpunk 2077 Noesis script

THANK YOU SO MUCH!! you're amazing!
## Post #3
- Username: JimmyJ
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Dec 21, 2011 8:54 am
- Post datetime: 2020-12-15T07:35:02+00:00
- Post Title: Cyberpunk 2077 Noesis script

Awesome job and big reaspect!!!
## Post #4
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-12-15T13:17:21+00:00
- Post Title: Cyberpunk 2077 Noesis script

Script updated to version 1.1

-Normal support added. Apparently we had them correct in the first place, so people curious enough to uncomment lines 327 to 330 had them already, the Noesis aspect seemed weird but the square norm is always 1 and they make sense on simple meshes so I guess they're right... Thanks to HitmanHimself for the help to confirm the format. If you prefer the old normals, put the "bComputeNormals" option to False at the top.
-LOD filtering added, the script will ignore the low poly version of the submeshes now. If you want them, put the "bHighestLODOnly" option at the top to False
-Better error handling, instead of crashing the script will print something in the console. 95% of the errors come from the wrong buffer file being grabbed so if you have an issue try to rename both the .mesh and the .buffer file

If other people are interested in the game feel free to use the code and update the script/make better tools for that game as I won't update it anymore.

Hope that helps.
## Post #5
- Username: zeroy
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 03, 2010 6:08 pm
- Post datetime: 2020-12-15T14:20:45+00:00
- Post Title: Cyberpunk 2077 Noesis script

Thanks for your work on this!
## Post #6
- Username: Yerba2033
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Dec 16, 2020 12:10 am
- Post datetime: 2020-12-15T16:12:34+00:00
- Post Title: Cyberpunk 2077 Noesis script

Are you guys able to export the meshes from the game? I would love to get my hands on the guns and some of the modeled cybernetics and 3d print them.
## Post #7
- Username: Kaem
- Rank: beginner
- Number of posts: 27
- Joined date: Wed May 23, 2012 5:28 am
- Post datetime: 2020-12-15T19:14:41+00:00
- Post Title: Cyberpunk 2077 Noesis script

Ok, I make the question no problem.

How much impossible will be export animations? No GTA 5 animations. No CP2077?
## Post #8
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-12-17T01:09:23+00:00
- Post Title: Cyberpunk 2077 Noesis script

Yeah I know, I said it was the last update but oh well...

Script updated to version 1.2, full skeleton support


Skeleton information is located in .rig files, if you put the option to load it at the top (put by default) you'll be asked to choose a .rig file. If the one you chose is not compatible, it'll ask for another. If you chose the right one it'll load the associated rig.
## Post #9
- Username: barnett2010
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Oct 23, 2020 10:58 pm
- Post datetime: 2020-12-17T06:47:04+00:00
- Post Title: Cyberpunk 2077 Noesis script

Unable to open mesh
## Post #10
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-12-17T20:54:35+00:00
- Post Title: Cyberpunk 2077 Noesis script

So I've been told that some meshes used several .rig files, as a result the script was rejecting some valid rig files as they didn't have all the bone information.
This is not an issue I can solve elegantly as :
-I can't use a hardcoded bone-parent list, some bones have different parents depending on the model
-I can't check easily if the rig is indeed compatible with the mesh as only a subset of the mesh bones info may contained in the .rig, the rest being in another one.

The only way to have a clean full skeleton would be to reverse how the game knows which .rig files to use, considering parenting can easily be fixed I only introduced a new option to deal with this.

Script updated to version 1.2.1

New option : bLoadSeveralRigFiles. This is how it works, you'll be prompted to choose .rig files until:
-all the bones will have parenting info parsed
-you press cancel
After selecting a .rig file at each stage, it will be parsed and the console output will show you the names of the bones left without parents, this will give you an idea of a possible other .rig file to grab to feed the ones missing.
If the parent is not in the original mesh however the bones will result unparented so that option needs to be used only if the first one failed.

In addition to that, I included a .txt file with the bone names on the left and all its possible parents on the right (this file was generated from all the .rig files), this will be helpful if you want to finish the job by hand.

> Reply from barnett2010 ↑Thu Dec 17, 2020 2:47 pm at Thu Dec 17, 2020 2:47 pm
>
> 
Unable to open mesh 

That error means that the .buffer wasn't find, your extraction is not correct. If not I can't help you sorry, I'm done with that game for now.
## Post #11
- Username: issacsingtong
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 19, 2020 9:16 pm
- Post datetime: 2020-12-19T13:17:32+00:00
- Post Title: Cyberpunk 2077 Noesis script

THANK YOU SO MUCH!! you're amazing!
## Post #12
- Username: sydie
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Nov 30, 2016 6:45 am
- Post datetime: 2020-12-22T09:36:42+00:00
- Post Title: Cyberpunk 2077 Noesis script

First of all - thank you Joschka and akderebur !!!
I understand that you don't want to continue updating the script, but I'm just giving an idea here - maybe we can give the morph targets some love.
This is basically the character customization.
All of the facial features you get when you start the game.
As far as I understand they're stored here:
basegame_4_gamedata\base\characters\head\player_base_heads\player_female_average\
in these .morphtarget files.
Usually morph targets are just vertex positions, there should be no faces, uvs or other bullcrap.
Maybe it's possible to load them the same way the .rig files are loaded in fmt_mesh 1.2.1 with that additional file loader.

Sample:
[https://www.dropbox.com/s/5md26ojsvnjmp ... e.zip?dl=0](https://www.dropbox.com/s/5md26ojsvnjmp67/player_female_average.zip?dl=0)

Anyway, we can also wait for the mod tools
## Post #13
- Username: mrfaceman
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Dec 23, 2020 4:22 pm
- Post datetime: 2020-12-23T08:23:25+00:00
- Post Title: Cyberpunk 2077 Noesis script

Awesome, thank you!!!
## Post #14
- Username: CharlieV
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Dec 30, 2019 5:29 pm
- Post datetime: 2020-12-25T11:53:00+00:00
- Post Title: Cyberpunk 2077 Noesis script

Really hoping someone can pick up the torch and continue work on this so that we can get intact UV's on exported models, or that something else comes along. Tried multiple weapons in multiple formats, the UV's are either dead (blank) or messed up depending on which format, don't match the textures at all (I'm not talking about being flipped).
## Post #15
- Username: JBolt97
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 30, 2020 10:08 am
- Post datetime: 2020-12-30T22:46:26+00:00
- Post Title: Cyberpunk 2077 Noesis script

Hi guys, I'm new here and new to this modeling stuff. I don't know where I would go with this question, but when I load up Noesis, and click a character, it shows a grey character (much like a PS2 character looks without texture) and like the title says, there's no texture on the character. Like no clothing, hair, just straight up grey character. Anyone know how to do get them?
## Post #16
- Username: pox911
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Mar 08, 2018 11:55 am
- Post datetime: 2020-12-30T23:29:19+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

At least for the iguana, it seems that the weight to bone index is off by one? All the bones i select show a weight of the next one in line.
## Post #17
- Username: Loomy
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Sep 12, 2015 9:16 am
- Post datetime: 2021-01-04T08:54:47+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

Big thanks for all your amazing work to bring us this script,

Noticed that quite a few of the meshes once extracted with cp77tools have their textures sharing same name, not all though, but added few lines to script to load up texture for these cases.. (wont work for all)

```
	
	matList = []
	texList = []
	
	###just above commitTriangles in vertLoop
	fName = os.path.basename(rapi.getInputName())
	meshName = fName.split(".")[0]
	texPath = dir +"\\textures\\"+meshName+"_d01.dds"

	material = NoeMaterial("submesh"+str(i), "")
	rapi.rpgSetMaterial("submesh"+str(i))
	material.setTexture(texPath)
	matList.append(material)
	###rapi.rpgCommitTriangles***

mdl.setModelMaterials(NoeModelMaterials(texList, matList))
###mdlList.append(mdl)***

```


Not sure how to load normal maps in noe, but it will usually follow same naming convention and end with *_n01".*
## Post #18
- Username: MaloneXI
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 07, 2021 8:48 pm
- Post datetime: 2021-01-07T15:20:36+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

Hi all , 

Does anyone know in what archive I could find the map of night city ? Not the game map , just the map , in map menu, the one that show the objectives etc. 

Thanx a lot.
## Post #19
- Username: Loomy
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Sep 12, 2015 9:16 am
- Post datetime: 2021-01-11T09:49:15+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

Ive have modified the script to recursively parse all material instances (.mi) & textures info from main .mesh & .buffer, & referenced external files (*.mi, *.mt, *.ml*, etc)

End up with a list of all linked texture files, and material info.  Not sure how to link specific material to which meshpart, but so far it would seem that the first few material instances found in mesh.0.buffer would correspond to the same mesh part(s) index-wise. 

Would really appreciate any help to clean it up and try and link up these textures & setup materials for noesis to be able to load & export as much of it as possible.  Still a WIP, needs alot of polishing.  Note:  change the cp77_path variable at top of file to the folder where you have extracted game data.   

Some of the info it dumps from Kojimas Head Mesh as example:

Textures List:

```
  "base\\characters\\head\\ma\\h0_732_ma_c__middle\\textures\\h0_732_ma_c__middle_d01.xbm",
  "base\\characters\\head\\ma\\h0_732_ma_c__middle\\textures\\h0_732_ma_c__middle_n01.xbm",
  "base\\characters\\head\\ma\\h0_001_ma_c__basehead\\textures\\h0_001_ma_c__basehead_tyger_d04.xbm",
  "base\\characters\\common\\skin\\face\\h0_000_ma_c__base_nd.xbm",
  "base\\characters\\head\\ma\\h0_001_ma_c__basehead\\textures\\h0_001_ma_c__basehead_rm01.xbm",
  "base\\characters\\common\\skin\\face\\h0_000_base__tintcolormask.xbm",
  "base\\characters\\common\\skin\\face\\h0_001_ma__wrnkl_stretch_n.xbm",
  "base\\characters\\common\\skin\\face\\h0_001_ma__wrnkl_squash_n.xbm",
  "base\\characters\\common\\skin\\face\\h0_001_ma__wrnkl_blood_mask_u.xbm",
  "base\\characters\\main_npc\\kojima\\h0_001_ma_a__kojima\\textures\\h0_001_ma_a__kojima_d01.xbm",
  "base\\characters\\main_npc\\kojima\\h0_001_ma_a__kojima\\textures\\h0_001_ma_a__kojima_n01.xbm",
  "base\\characters\\head\\ma\\h0_001_ma_c__basehead\\textures\\h0_001_ma_c__basehead_valentino_d04.xbm",
  "base\\characters\\head\\ma\\h0_001_ma_c__basehead\\textures\\h0_001_ma_c__basehead_d04.xbm",
  "base\\characters\\head\\ma\\h0_001_ma_c__basehead\\textures\\h0_001_ma_c__basehead_n01.xbm",
  "base\\characters\\head\\ma\\h0_001_ma_c__basehead\\textures\\h0_001_ma_c__basehead_d01.xbm",
  "base\\characters\\head\\ma\\h0_001_ma_c__basehead\\textures\\h0_001_ma_b__basehead_d03.xbm",
  "base\\characters\\head\\mba\\h0_000_mba_c__basehead\\textures\\h0_000_mba_c__basehead_d01.xbm",
  "base\\characters\\common\\character_customisation_items\\tattoos\\face\\textures\\head_tattoo__tygerclaw_01_d01.xbm",
  "base\\characters\\common\\character_customisation_items\\tattoos\\face\\textures\\head_tattoo__tygerclaw_01_e01.xbm",
  "base\\characters\\common\\character_customisation_items\\tattoos\\face\\textures\\head_tattoo__valentino_01_d01.xbm",
  "engine\\textures\\small_white.xbm"
]

```


```
    "CMaterialInstance": {
          "Normal": "base\\characters\\head\\ma\\h0_732_ma_c__middle\\textures\\h0_732_ma_c__middle_n01.xbm",
          "baseMaterial": "base\\characters\\common\\skin\\character_mat_instance\\male\\head\\male_head_02_ca_limestone.mi",
          "Albedo": "base\\characters\\head\\ma\\h0_732_ma_c__middle\\textures\\h0_732_ma_c__middle_d01.xbm",
      },
      "CMaterialInstance": {
          "CavityIntensity": 0.25,
          "DetailRoughnessBiasMin": 1,
          "MicroDetailInfluence": 1,
          "MicroDetailUVScale02": 8,
          "Normal": "base\\characters\\head\\ma\\h0_732_ma_c__middle\\textures\\h0_732_ma_c__middle_n01.xbm",
          "BloodColor": {
            "Blue": 0,
            "Alpha": 0,
            "Green": 0,
            "Red": 0
          },
          "DetailRoughnessBiasMax": 0.8500000238418579,
          "TintColorMask": "base\\characters\\common\\skin\\face\\h0_000_base__tintcolormask.xbm",
          "Detailmap_Squash": "base\\characters\\common\\skin\\face\\h0_001_ma__wrnkl_squash_n.xbm",
          "Roughness": "base\\characters\\head\\ma\\h0_001_ma_c__basehead\\textures\\h0_001_ma_c__basehead_rm01.xbm",
          "Detailmap_Stretch": "base\\characters\\common\\skin\\face\\h0_001_ma__wrnkl_stretch_n.xbm",
          "TintColor": {
            "Blue": 83,
            "Alpha": 255,
            "Green": 149,
            "Red": 131
          },
          "DetailNormalInfluence": 1,
          "MicroDetailUVScale01": 20,
          "DetailNormal": "base\\characters\\common\\skin\\face\\h0_000_ma_c__base_nd.xbm",
          "TintScale": 0.379,
          "baseMaterial": "base\\characters\\common\\skin\\character_mat_instance\\male\\head\\male_head_npc_06_limestone_tyger.mi",
          "Albedo": "base\\characters\\head\\ma\\h0_001_ma_c__basehead\\textures\\h0_001_ma_c__basehead_tyger_d04.xbm",
          "Bloodflow": "base\\characters\\common\\skin\\face\\h0_001_ma__wrnkl_blood_mask_u.xbm",
          "SkinProfile": "skip"
        }
      }
    
}
```
## Post #20
- Username: Loomy
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Sep 12, 2015 9:16 am
- Post datetime: 2021-01-11T09:55:40+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

Here is WIP script as mentioned above, check class CR2WFile, info is output to cr2w_list, cr2w_textures, cr2w_external_data variables.  Make sure to edit your cp77_path to your own extracted archives location

[https://pastebin.com/kGUQL1gG](https://pastebin.com/kGUQL1gG)
## Post #21
- Username: Loomy
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Sep 12, 2015 9:16 am
- Post datetime: 2021-01-11T20:26:48+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

> Reply from MaloneXI ↑Thu Jan 07, 2021 11:20 pm at Thu Jan 07, 2021 11:20 pm
>
> 
Hi all , 

Does anyone know in what archive I could find the map of night city ? Not the game map , just the map , in map menu, the one that show the objectives etc. 

Thanx a lot.
I believe this is it:- base\entities\cameras\3dmap\3dmap_* (found in gamedata archive)
## Post #22
- Username: Thumpist
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jan 13, 2021 3:51 pm
- Post datetime: 2021-01-13T08:08:08+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

Hi Everyone, 

I am very new to this, I basically love the vehicles in CP2077 and I have already printed a Quadra from a file I found on thingiverse but I was hoping to do some more of the CP cars. I have extracted the archive and I can view the meshs via Noesis but every mesh I open is just really low on the poly count and barely has the vehicle shape. I am sure there is something I am missing or I am over estimating what the program can do? Is what I am trying to do possible?
## Post #23
- Username: Piranjak
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 15, 2021 4:56 am
- Post datetime: 2021-01-15T01:43:38+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

Hi all, I'm having a problem which I assume is probably caused by something small and obvious, but I know basically nothing about this. I mean, really.
I got the mesh files I want with CP77Tools and put the python script in Noesis so it's all set, but when I try to open the mesh files it tells me they cannot be previewed. If I try to extract them I get the error "couldn't find a suitable buffer file". Any advice?
## Post #24
- Username: micro777
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Oct 01, 2018 5:57 am
- Post datetime: 2021-01-15T08:19:13+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

> Reply from Piranjak ↑Fri Jan 15, 2021 9:43 am at Fri Jan 15, 2021 9:43 am
>
> 
Hi all, I'm having a problem which I assume is probably caused by something small and obvious, but I know basically nothing about this. I mean, really.
I got the mesh files I want with CP77Tools and put the python script in Noesis so it's all set, but when I try to open the mesh files it tells me they cannot be previewed. If I try to extract them I get the error "couldn't find a suitable buffer file". Any advice?

Попытаться изменить значение nameToIndex,0 в строке 328 скрипта на nameToIndex,1. 
Try changing the nameToIndex,0 value in script line 328 to nameToIndex,1.
indOffFlag = buildFlagFromNames(["teOffset","Uint32"],nameToIndex,1)
## Post #25
- Username: Piranjak
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 15, 2021 4:56 am
- Post datetime: 2021-01-15T15:44:20+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

> Reply from micro777 ↑Fri Jan 15, 2021 4:19 pm at Fri Jan 15, 2021 4:19 pm
>
> 
Piranjak wrote: ↑Fri Jan 15, 2021 9:43 am
Hi all, I'm having a problem which I assume is probably caused by something small and obvious, but I know basically nothing about this. I mean, really.
I got the mesh files I want with CP77Tools and put the python script in Noesis so it's all set, but when I try to open the mesh files it tells me they cannot be previewed. If I try to extract them I get the error "couldn't find a suitable buffer file". Any advice?


Попытаться изменить значение nameToIndex,0 в строке 328 скрипта на nameToIndex,1. 
Try changing the nameToIndex,0 value in script line 328 to nameToIndex,1.
indOffFlag = buildFlagFromNames(["teOffset","Uint32"],nameToIndex,1)

Sadly still having the same issue, but thank you for taking the time.
## Post #26
- Username: nekoboinick
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 16, 2021 7:46 am
- Post datetime: 2021-01-16T01:13:35+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

> Reply from micro777 ↑Fri Jan 15, 2021 4:19 pm at Fri Jan 15, 2021 4:19 pm
>
> 
Piranjak wrote: ↑Fri Jan 15, 2021 9:43 am
Hi all, I'm having a problem which I assume is probably caused by something small and obvious, but I know basically nothing about this. I mean, really.
I got the mesh files I want with CP77Tools and put the python script in Noesis so it's all set, but when I try to open the mesh files it tells me they cannot be previewed. If I try to extract them I get the error "couldn't find a suitable buffer file". Any advice?


Попытаться изменить значение nameToIndex,0 в строке 328 скрипта на nameToIndex,1. 
Try changing the nameToIndex,0 value in script line 328 to nameToIndex,1.
indOffFlag = buildFlagFromNames(["teOffset","Uint32"],nameToIndex,1)

I am having the same issue, and your fix is sadly not working. I tried creating the file, just in case if it wasn't able to initially create the file, but it doesn't seem to work.
## Post #27
- Username: lndrx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jan 16, 2021 9:39 am
- Post datetime: 2021-01-16T03:11:07+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

> Reply from nekoboinick ↑Sat Jan 16, 2021 9:13 am at Sat Jan 16, 2021 9:13 am
>
> 
micro777 wrote: ↑Fri Jan 15, 2021 4:19 pm
Piranjak wrote: ↑Fri Jan 15, 2021 9:43 am
Hi all, I'm having a problem which I assume is probably caused by something small and obvious, but I know basically nothing about this. I mean, really.
I got the mesh files I want with CP77Tools and put the python script in Noesis so it's all set, but when I try to open the mesh files it tells me they cannot be previewed. If I try to extract them I get the error "couldn't find a suitable buffer file". Any advice?


Попытаться изменить значение nameToIndex,0 в строке 328 скрипта на nameToIndex,1. 
Try changing the nameToIndex,0 value in script line 328 to nameToIndex,1.
indOffFlag = buildFlagFromNames(["teOffset","Uint32"],nameToIndex,1)



I am having the same issue, and your fix is sadly not working. I tried creating the file, just in case if it wasn't able to initially create the file, but it doesn't seem to work.

Same here. Noesis asks for the .rig file, but even selecting what appears to be the correct file, nothing happens. Says that the rig file is invalid and keeps asking for it. If you cancel the selection, nothing is exported nor previewed.
## Post #28
- Username: lndrx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jan 16, 2021 9:39 am
- Post datetime: 2021-01-16T03:44:58+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

Extracted the archive again using CP77Tools version 0.2.0.1. Now this works! Thank you!
## Post #29
- Username: Piranjak
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 15, 2021 4:56 am
- Post datetime: 2021-01-16T14:56:19+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

> Reply from lndrx ↑Sat Jan 16, 2021 11:44 am at Sat Jan 16, 2021 11:44 am
>
> 
Extracted the archive again using CP77Tools version 0.2.0.1. Now this works! Thank you!

Using version 0.2.0.1 fixed it for me too! Thank you!
## Post #30
- Username: lndrx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jan 16, 2021 9:39 am
- Post datetime: 2021-01-16T18:16:48+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

Ok, I'm not a great programmer, but I kinda sorted what is "wrong". The new version of CP77Tools (v1.0 at this time) doesn't have any buffer files. It cleans everything leaving only the mesh file. Joschka's script 1.2.1 needs these buffer files to work. I'm trying to update the python code to point the original file "as also the buffer file".
## Post #31
- Username: lndrx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jan 16, 2021 9:39 am
- Post datetime: 2021-01-16T18:31:47+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

> Reply from lndrx ↑Sun Jan 17, 2021 2:16 am at Sun Jan 17, 2021 2:16 am
>
> 
Ok, I'm not a great programmer, but I kinda sorted what is "wrong". The new version of CP77Tools (v1.0 at this time) doesn't have any buffer files. It cleans everything leaving only the mesh file. Joschka's script 1.2.1 needs these buffer files to work. I'm trying to update the python code to point the original file "as also the buffer file".

I did it and nope. It doesn't work this way.
## Post #32
- Username: crypt
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jan 25, 2021 9:33 am
- Post datetime: 2021-01-25T16:46:42+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

Hi, I'm trying to load the .mesh files in noesis and I can't, I extracted the files several times from several versions of cp77 and no problem, but with the noesis scrypt it doesn't work, I can't see the model and when exporting in fbx or obj says file buffer error, I don't understand what can happen, I hope you can advise me, a greeting.
## Post #33
- Username: jayaqua
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 21, 2021 2:35 am
- Post datetime: 2021-02-02T20:57:51+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

so ripping the models is easy but how do you get textures from the buffer files?
## Post #34
- Username: alphaZ
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Feb 06, 2020 4:23 pm
- Post datetime: 2021-02-05T20:04:22+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

Thank you Joshcka for your amazing work on this. Sorry it took so long for me to post this here, but I have been developing a lot of new features for your plugin. I redubbed this new version "fmt_CP77mesh" to avoid confusion, since "mesh" is such a generic format name.

fmt_CP77mesh.py v1.44


New / updated features:
Textures (Import and Export):
- Preview of .xbm and .mi textures (as extracted by the latest CP77Tools), including files with multiple images inside
- Preview of other textures embedded inside meshes, particle files, and wherever else if you rename the file's extension to ".cp77tex"
- Beta texture export support for encoding images as new .buffer files by exporting as .cp77tex

Model Import:
- Imported models are rotated upright and scaled to a user-set scaling value (default 100x, found at the top of the .py file)
- Corrected bone maps when using a .rig file
- Correctly rotated normals
- Support for .morphtarget meshes (import and export) and export support for static meshes

Model Export:
- Export FBX to .mesh, writing new model data to a new .mesh.buffer file 
- Modify only the bone positions in a .mesh by exporting them with the advanced option " -bones". A copy of the picked model will be created using the bone positions from your FBX (no need to rebuild this since no .buffer file is made)
- Modify the bone positions and model data of a .mesh simultaneously by exporting with the advanced option " -meshbones"

About Model Export:
You can create a mesh mod by importing an original .mesh into Noesis and saving it as FBX, editing it in a 3d editor, then loading that FBX back into Noesis and exporting it back to .mesh over the model you originally extracted it from. Mesh editing seems to work well now as of v1.44; most of the issues with crashes and exploding verts have been fixed.

To get your mesh in-game, you need to reconstruct the .mesh file so that your new buffer is packed up and embedded inside it. The latest versions of CP77Tools can do this using the command: 
```
rebuild -p "MODDED FOLDER PATH" -b -t --keep --unsaferaw 
```


The following options are available at the top of the .py file and can be changed with a text editor:

```
meshScale = 100						#scale model to this size
bHighestLODOnly = True   	  		#if put to True, the low poly meshes will be loaded as separate models
bLoadRigFile = False 	       		#if put to True, enables user-selection of a paired rig file with the skeleton hierarchy info
bAutoDetectRig = True				#if put to True, the plugin will search for and load the closest-named .rig file to the mesh filename
bParentToRootIfNoParent = True		#if put to True, unparented bones will be parented to Root
bReadTangents = False				#if put to True, tangents are read from the file and applied to the model
bImportGarmentMesh = False			#if put to True, garment meshes will be imported along with the regular mesh
bImportExportDamageMeshes = True	#if put to True, vehicle damage meshes will be imported along with the regular mesh, and will be exported if they are detected in the fbx
bImportMorphtargets	= False			#if put to True, morphs will be imported with morphtarget files (currently broken)**
bVertexColors	= True				#if put to True, vertex colors will be read and applied to the model on import, and will be written on export
bExportAllBuffers = True			#if put to True, all buffers will be exported when saving meshes or textures, rather than just the ones modified
bConnectRigToRoot = False			#if put to True, rigs will be assembled in such a way that a connection is always made to the Noesis_Root bone
bSplitDoubleSidedMeshes = True		#If put to True, double-sided meshes (such as hair meshes) will be imported as inner and outer parts

bFlipImage = False				#if put to True, images and UVs are flipped upright on imported textures and meshes
bManualDimensions = False			#if put to True, the user can set their own texture resolution on import
bManualCompression = False			#if put to True, the user can set their own texture compression on import	
```

bReadAsSigned = True				#if put to True, textures will be decoded as signed data, making normal maps yellow instead of blue[/code]

If you want to follow the development of this version more closely, you can on the Cyberpunk Modding Discords:

Cyberpunk 2077 Modding:
[https://discord.com/invite/2bT93CkA4B](https://discord.com/invite/2bT93CkA4B)

CP77 Modding Community:
[https://discord.gg/Epkq79kd96](https://discord.gg/Epkq79kd96)

Recently updated:
-Fixed Noesis splitting some meshes
-Bone hierarchy is automatically from your extracted game files and saved to a text file "CP77ExtractedPath.txt" next to the plugin
-Single-LOD hack is applied when exporting with `bHighestLODOnly`
-Tangent space problems (causing neck seams) are fixed
-Bones are rotated upright in-place and in-world
-Morphs are automatically disabled on morphtarget export
-New advanced options "-cp77optimize" to optimize the mesh on import and "-vf [factory]" to set a morphtarget vertex factory on export
-A Maxscript is included with the plugin for use in remote-controlling Noesis from 3dsmax, for those who have it
-Double-faced hair meshes can now be imported correctly if they are split in two by enabling "bSplitDoubleSidedMeshes". These meshes must have their normals recalculated and their faces unified, but after doing that they will work correctly

Download Here:
[https://www.mediafire.com/file/zyutd5se ... 2.zip/file](https://www.mediafire.com/file/zyutd5se2dphute/fmt_CP77mesh_v1.52.zip/file)

Old versions:

```
https://www.mediafire.com/file/8gpv9grobnu9y93/fmt_CP77mesh_1.5.zip/file
https://www.mediafire.com/file/rikr6retuqophs6/fmt_CP77mesh_1.49.zip/file
http://www.mediafire.com/file/g1t443fj7nfn6tt/fmt_CP77mesh_1.48.zip/file
http://www.mediafire.com/file/kkj9orx9qsucj8o/fmt_CP77mesh_1.47.zip/file
http://www.mediafire.com/file/bouaqa47ywpa9cn/fmt_CP77mesh_1.46.zip/file
http://www.mediafire.com/file/n1a2gy9s3arc3jt/fmt_CP77mesh_1.45.zip/file
https://www.mediafire.com/file/be5a61bpwd34maw/fmt_CP77mesh_1.44.zip/file
https://www.mediafire.com/file/ks3qun82ucvb8gg/fmt_CP77mesh_1.43.zip/file
https://www.mediafire.com/file/8ufh9m9andjsjtm/fmt_CP77mesh_1.42.zip/file
https://www.mediafire.com/file/ycyad5r3baiulod/fmt_CP77mesh_1.41.zip/file
https://www.mediafire.com/file/9hkm3lajxqmu993/fmt_CP77mesh_1.4.zip/file
```

[fmt_CP77mesh_1.51.zip](https://xentaxbackup.github.io/file/19853_fmt_CP77mesh_1.51.zip)
## Post #35
- Username: JKerman
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Feb 06, 2021 7:02 am
- Post datetime: 2021-02-05T23:05:39+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

When I extract the textures, I get png and dds files named whatever_maskset. Are they for individual RGB channels? How can I tell which are the specular, AO, metallic, etc?
## Post #36
- Username: choochoomomdad
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 24, 2021 4:59 pm
- Post datetime: 2021-02-06T19:10:43+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

> Reply from alphaZ ↑Sat Feb 06, 2021 4:04 am at Sat Feb 06, 2021 4:04 am
>
> 
Thank you Joshcka for your amazing work on this. Sorry it took so long for me to post this here, but I have been developing a lot of new features for your plugin. I redubbed this new version "fmt_CP77mesh" to avoid confusion, since "mesh" is such a generic format name.

fmt_CP77mesh.py v1.43


New / updated features:
Textures (Import and Export):
- Preview of .xbm and .mi textures (as extracted by the latest CP77Tools), including files with multiple images inside
- Preview of other textures embedded inside meshes, particle files, and wherever else if you rename the file's extension to ".cp77tex"
- Beta texture export support for encoding images as new .buffer files by exporting as .cp77tex

Model Import:
- Imported models are rotated upright and scaled to a user-set scaling value (default 100x, found at the top of the .py file)
- Corrected bone maps when using a .rig file
- Correctly rotated normals
- Support for .morphtarget meshes (import and export) and export support for static meshes

Model Export:
- Export FBX to .mesh, writing new model data to a new .mesh.buffer file 
- Modify only the bone positions in a .mesh by exporting them with the advanced option " -bones". A copy of the picked model will be created using the bone positions from your FBX (no need to rebuild this since no .buffer file is made)
- Modify the bone positions and model data of a .mesh simultaneously by exporting with the advanced option " -meshbones"

About Model Export:
You can create a mesh mod by importing an original .mesh into Noesis and saving it as FBX, editing it in a 3d editor, then loading that FBX back into Noesis and exporting it back to .mesh over the model you originally extracted it from. Mesh editing is currently pretty finicky, however, and only guns, cars and hair meshes have had much success so far. Clothes and characters will often have issues with exploding faces, so that needs more research.
To get your mesh in-game, you need to reconstruct the .mesh file so that your new buffer is packed up and embedded inside it. The latest versions of CP77Tools can do this using the command: Code: Select allrebuild -p "MODDED FOLDER PATH" -b -t --keep --unsaferaw 

The following options are available at the top of the .py file and can be changed with a text editor:
Code: Select allmeshScale = 100					#scale model to this size
bOriginalTransform = False			#if put to true, the mesh will be imported where you can see its original "boneRigMatrices" transforms in a 3D editor (by checking the inverse of any bone's matrix)
bHighestLODOnly = False   	  		#if put to True, the low poly meshes won't be loaded
bLoadRigFile = False 	       		        #if put to True, enables selecting a paired rig file with the skeleton hierarchy info
bLoadSeveralRigFiles = False		        #if put to True, same as above but with several rig files and without validity check
bParentToRootIfNoParent = True		        #if put to True, unparented bones will be parented to Root
bReadTangents = False				#if put to True, tangents are read from the file and applied to the model
bWriteVerts = True				#if put to True, exported meshes will rewrite the entire .buffer file (instead of only rewriting verts within the original .buffer)

bFlipImage = False				#if put to True, images and UVs are flipped upright on imported textures and meshes
bManualDimensions = False			#if put to True, the user can set their own texture resolution on import
bManualCompression = False			#if put to True, the user can set their own texture compression on import	

If you want to follow the development of this version more closely, you can on the Cyberpunk Modding Discords:

Cyberpunk 2077 Modding (my home server):
https://discord.com/invite/2bT93CkA4B

CP77 Modding Community:
https://discord.gg/Epkq79kd96


Download Here:
https://www.mediafire.com/file/ks3qun82 ... 3.zip/file
or

How about error “wrong buffer file”?
## Post #37
- Username: truforza
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Feb 05, 2021 5:36 am
- Post datetime: 2021-02-10T21:49:46+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

Hi people. I'm hoping someone can help me figure out what I'm missing because I'm stuck with this message for every mesh i try to preview.. and the exports are nonexistent as well



I'm not sure if I missed something while extracting the game data, but I would highly apprecaiate any help. Thanks and my apologies for being a noesis noob
## Post #38
- Username: alphaZ
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Feb 06, 2020 4:23 pm
- Post datetime: 2021-02-12T01:16:43+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

> Reply from truforza ↑Thu Feb 11, 2021 5:49 am at Thu Feb 11, 2021 5:49 am
>
> 
Hi people. I'm hoping someone can help me figure out what I'm missing because I'm stuck with this message for every mesh i try to preview.. and the exports are nonexistent as well



I'm not sure if I missed something while extracting the game data, but I would highly apprecaiate any help. Thanks and my apologies for being a noesis noob
This happens because you haven't uncooked the mesh files when you extracted your game archives. There are two ways to extract files with CP77Tools: uncook and unbundle. Unbundle is what you did, and that gives you the mesh files themselves, but the actual mesh data is hidden inside some Oodle-compressed data blocks inside those mesh files. That needs your oo2ext_7_win64.dll file from your game in order to extract ("uncook"), and that's why CP77Tools needs that DLL too.

So in order to preview the meshes, they must be surrounded by their extracted data parts (called ".buffer" files). Noesis will find the uncooked buffer file that contains the model data and load it automatically, if it is in the same folder and with the same name as the .mesh file.

To uncook all mesh files from a game archive, use a command like this:

```
uncook -p "D:\GOG\Cyberpunk2077\Cyberpunk 2077\archive\pc\content\basegame_4_gamedata.archive" -w *mesh*
```
## Post #39
- Username: truforza
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Feb 05, 2021 5:36 am
- Post datetime: 2021-02-16T00:30:56+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

> Reply from alphaZ ↑Fri Feb 12, 2021 9:16 am at Fri Feb 12, 2021 9:16 am
>
> 

This happens because you haven't uncooked the mesh files when you extracted your game archives. There are two ways to extract files with CP77Tools: uncook and unbundle. Unbundle is what you did, and that gives you the mesh files themselves, but the actual mesh data is hidden inside some Oodle-compressed data blocks inside those mesh files. That needs your oo2ext_7_win64.dll file from your game in order to extract ("uncook"), and that's why CP77Tools needs that DLL too.

So in order to preview the meshes, they must be surrounded by their extracted data parts (called ".buffer" files). Noesis will find the uncooked buffer file that contains the model data and load it automatically, if it is in the same folder and with the same name as the .mesh file.

To uncook all mesh files from a game archive, use a command like this:
Code: Select alluncook -p "D:\GOG\Cyberpunk2077\Cyberpunk 2077\archive\pc\content\basegame_4_gamedata.archive" -w *mesh*

I followed your instructions to re-copy the DLL (just to be sure) and use the 'uncook' command but ended up getting flooded with loads of errors about being unable to read cr2w or something while CP77Tools created 0Kb mesh files for everything. Is this supposed to happen? I still feel like I have missed something very important..




Edit: I managed to unbundle the mesh files after uncooking and gained access to some of the models.. though the majority of them still can't be opened for some reason
## Post #40
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2021-02-21T13:39:40+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

Screenshot_1.jpg (224.24 KiB) Viewed 568 times


When i try open npc clair skirt - l1_003_wa_skirt__clair.mesh
Noesis give me this error
I extract all l1_003_wa_skirt__clair.mesh.0.buffer by l1_003_wa_skirt__clair.mesh.73.buffer
## Post #41
- Username: Hayte
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 07, 2021 12:20 am
- Post datetime: 2021-03-06T16:34:51+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

Not sure where to post this to be honest as its not strictly related to Noesis.

I am able to edit game meshes and get them into the game with CP77Tools but ran into an issue when using Blender and Maya's .fbx exporter. For some reason, this happens:




The top screenshot is how the mesh should look in game.

1. In Noesis, export .mesh to .fbx.
2. In Noesis, export .fbx over the existing .mesh.
3. Using CP77 Tools, rebuild the mesh and repack the archive.

You will always get the same results as in the first screenshot.

The bottom screenshot is what happens if you do this:

1. In Noesis, export .mesh to .fbx.
2. Open .fbx in Blender/Maya.
3. In Blender/Maya, export to .fbx.
4. In Noesis, take the Blender/Maya exported .fbx and export over .mesh
5. Using CP77Tools, rebuild the mesh and repack the archive.

No editing in Blender/Maya necessary. For some reason something is lost in the export. The jacket seams are inverted and the creases on the shoulders/arms lack depth. Its like the normals are getting screwed. There are also some shadows under the collar of the jacket which correspond to the topology of the mesh (this is much easier to see in Blender/Maya's viewport with shading).

So I've re-rigged this mesh (to stop the neck bones getting yanked down by the head when it is replaced by the FPP viewport) and fixed some geo to eliminate clipping problems under the armpits. I can get it back into the game with Noesis/CP77Tools no problem. But Blender/Maya's .fbx exporter is kind of ruining it by wrecking the normals (?)

Any insight as to what could be causing this?
## Post #42
- Username: devilsnake88
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Dec 06, 2013 12:14 am
- Post datetime: 2021-03-07T16:57:01+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

> Reply from Hayte ↑Sun Mar 07, 2021 12:34 am at Sun Mar 07, 2021 12:34 am
>
> 
...

Not sure but can't it come from the way the engines interprets normal maps?


Try to invert/flip the green channel of your normal map and see if it works in game
## Post #43
- Username: Hayte
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 07, 2021 12:20 am
- Post datetime: 2021-03-07T22:59:14+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

Yeah, this is exactly the problem. I'm working on it now and I am documenting the process (mistakes and everything).

Edit: Ok, I documented everything here: [https://forums.cdprojektred.com/index.p ... .11082448/](https://forums.cdprojektred.com/index.php?threads/modding-fbx-exporter-issue-in-blender-maya-when-viewing-fbx-mesh-ingame.11082448/)

But I hit a wall. Flipped X and Y channels does work but I think there is a leather material used that has normals inverted no matter what and I cant uncook basegame_3_nightcity without CP77Tools throwing an unhandled exception. Besides that, screwing with materials to solve a problem that manifests on .fbx export for a single player wearable is a whole can of worms I don't think I can or should open.

I tried to circumvent the problem entirely since the original goal was a rigging job so I would export only the armature using "-bones", but I'm not sure if its working? I could be making another noob error. Or if it is its only certain bone parameters like position that are being written to the .mesh? The mesh I'm trying to export has multiple armatures but it seems Noesis merges them all when exporting over the old .mesh?
## Post #44
- Username: lulzx
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 24, 2021 11:55 pm
- Post datetime: 2021-03-24T16:09:41+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

When I tried to uncook the meshes, an error occured(displayed red),saying that a json file cannot be uncooked, would anyone help me plz~~~~~
## Post #45
- Username: photojoe
- Rank: beginner
- Number of posts: 23
- Joined date: Wed Jan 27, 2016 6:49 am
- Post datetime: 2021-03-25T17:00:08+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

Are there any tutorials for extract one's 'V' character from the game?

Also what files for extracting Rig animations do i need to uncook? I know the XBM for textures, Mesh has the MorphTarget, Rig and Mesh itself, but don't know what the MI is (material index?) or other files CP22Tools can extract that I can reassemble. 

Also for extracting meshes from the game, any help figuring out where the NPC are, they seem to be in pieces like the Player mesh.
## Post #46
- Username: alphaZ
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Feb 06, 2020 4:23 pm
- Post datetime: 2021-04-05T23:55:15+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

> Reply from Hayte ↑Sun Mar 07, 2021 12:34 am at Sun Mar 07, 2021 12:34 am
>
> 
Any insight as to what could be causing this?

There was an issue with saving the normals that I only just fixed today. They should be working correctly now, though. Check my original post to see some of the things that were updated
## Post #47
- Username: uncalquera
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jul 03, 2021 7:09 am
- Post datetime: 2021-07-03T03:22:18+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

Hi there!

New here, so hello everyone 
First off, many thanks for the great tools you people are develping, awesome work 
I've been extracting the base models for the player, so far I've been able to extract the geometries for the head, eyes and body pretty much succesfully, the one problem I'm having is with the normal maps, I'm trying to use them in Maya and while the meshes work correctly, as do the Diffuse map, the normal map seems to be missing the blue channel, resulting in yellow-scale normal map, any ideas on what might be the problem there?
## Post #48
- Username: uncalquera
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jul 03, 2021 7:09 am
- Post datetime: 2021-07-04T01:36:50+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

Hi again,

So it seems there was no problem with the normal maps, they just don't have a blue channel. So my problem now is with exporting morphtargets, I tried exporting one and the resulting .fbx didn't have any morph nodes (blend shapes in Maya), any idea how can I export those to be used in a 3D software like maya, 3DS or Blender?

*edit*

So I managed to export the actual morph target node but the function seems to be currently broken (confirmed by the annotations in the script ) so it seems I've hit a wall here, not sure if there's any newer version of the script that solves this problem that i couldn't find?
## Post #49
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-07-04T02:05:40+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

> Reply from uncalquera ↑Sun Jul 04, 2021 9:36 am at Sun Jul 04, 2021 9:36 am
>
> 
Hi again,

So it seems there was no problem with the normal maps, they just don't have a blue channel. So my problem now is with exporting morphtargets, I tried exporting one and the resulting .fbx didn't have any morph nodes (blend shapes in Maya), any idea how can I export those to be used in a 3D software like maya, 3DS or Blender?

*edit*

So I managed to export the actual morph target node but the function seems to be currently broken (confirmed by the annotations in the script ) so it seems I've hit a wall here, not sure if there's any newer version of the script that solves this problem that i couldn't find?

Loomy has written instructions on how to do this on the cyberpunk modding discord.
## Post #50
- Username: uncalquera
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jul 03, 2021 7:09 am
- Post datetime: 2021-07-04T12:07:52+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

> Reply from dimis9138 ↑Sun Jul 04, 2021 10:05 am at Sun Jul 04, 2021 10:05 am
>
> 
uncalquera wrote: ↑Sun Jul 04, 2021 9:36 am
Hi again,

So it seems there was no problem with the normal maps, they just don't have a blue channel. So my problem now is with exporting morphtargets, I tried exporting one and the resulting .fbx didn't have any morph nodes (blend shapes in Maya), any idea how can I export those to be used in a 3D software like maya, 3DS or Blender?

*edit*

So I managed to export the actual morph target node but the function seems to be currently broken (confirmed by the annotations in the script ) so it seems I've hit a wall here, not sure if there's any newer version of the script that solves this problem that i couldn't find?


Loomy has written instructions on how to do this on the cyberpunk modding discord.

Hey, thanks for the answer, can't seem to find the instructions you talk about in the discord (not very familiar with it  ) can you direct me a bit on where to search there? thanks a lot
## Post #51
- Username: Persona69
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 25, 2021 11:57 am
- Post datetime: 2021-07-27T19:48:33+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

Hi does anyone knows where I can find the textures of the weapons?

So far I only have the normal map \basegame_4_gamedata\base\weapons\firearms\handgun\arasaka_tamayura\entities\meshes\textures\tpp\w_handgun__arasaka_tamayura__base1_01_n01.dds

Thanks
## Post #52
- Username: samboychips
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Sep 07, 2020 4:04 pm
- Post datetime: 2021-09-01T13:26:04+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

Can someone here possibly post what version of the game and what version of CP77Tools they're using to extract the meshes from this? I've tried various different versions with different results.

So far I've been able to get a handful out by uncooking then unbundling basegame_4_gamedata and basegame_3_nightcity, but I'm still getting meshes with missing buffers and in some cases, meshes missing entirely.
## Post #53
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2021-09-03T14:55:43+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

Some characters are made up of several different meshes, scattered throughout the archives; they don't have individual meshes.  It takes a bit of digging into the appearance and cookedappearance files to figure out which meshes and where they're located.

Current version of CP2077 is 1.3, CP2077Tools is 1.5

You may need to use the --forcebuffers command when uncooking to get buffers.
## Post #54
- Username: samboychips
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Sep 07, 2020 4:04 pm
- Post datetime: 2021-09-04T21:59:26+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

Thanks so much for that, dude!
## Post #55
- Username: muqingxuan1
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Mar 09, 2023 3:15 pm
- Post datetime: 2023-03-20T11:55:21+00:00
- Post Title: Re: Cyberpunk 2077 Noesis script

Thanks and I was wondering if there was a way to get the animation.
