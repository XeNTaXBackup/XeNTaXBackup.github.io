## Post #1
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-01-29T06:44:07+00:00
- Post Title: RF Online Unknow rare model extracted

RF Online its a old game with good stuff thinks and fashion, in the past someone made the unpackers for this game models, and now the game have all need to unpack  and convert textures and meshes to redeable formats, but the conversor to OBJ can get a bunch of shit... hope somebody also Finale (now with good skills in Noesis) can explain wath its wrong with this extraction system. here i put all the tools necesary do this, its very easy extract.

Only need drag .RFS files inside of RFSUnPack.exe and u get .RFT if its texture, u get .MSH if its Models.
To get dds textures only need drag RFT inside of RFT-DDS.exe and now you get the .DDS files.
To get the models only need open the MshtoObj.exe Aplication and convert .MSH to .Obj format.

But .Obj are wrong extracted in rare cuts and parts like this...

I think its wrong calcualted half meshes and stored in the center of axis or something, if somebody can made the plugin for Noesis this can be very good.

Here the files samples Texture and Mesh, .exes unpackers and library i found abouth the format... thanks.

[http://www.4shared.com/rar/EWhjUKu7/PARA.html](http://www.4shared.com/rar/EWhjUKu7/PARA.html)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-29T13:24:59+00:00
- Post Title: RF Online Unknow rare model extracted

Maybe it's not applying any transformations, cause it's just skipping it.

Looks like a bunch of matrices defined for each mesh (there are 3 of them for each mesh. Don't know those 3 might be). But simply applying a single one of those matrices didn't produce any desirable results.

Anyways it looks like a good candidate for immMode rendering. For some reason I can't get the normals right though.
## Post #3
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-01-29T17:50:53+00:00
- Post Title: RF Online Unknow rare model extracted

Game have 4 folders for player models, Ani, Bone, Mesh, Tex.

Here I include the 4 Elements

[http://www.4shared.com/rar/NtdpFqL3/Player.html](http://www.4shared.com/rar/NtdpFqL3/Player.html)
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-29T18:47:23+00:00
- Post Title: RF Online Unknow rare model extracted

A single model is broken down into various meshes.
I'm guessing it makes it easier to animate?

I can't get the normals and UV's right and have no clue what the problem is.
Maybe someone can figure out what's wrong with my mesh building.

[http://xtsukihime.webs.com/Noesis%20Plu ... ine_msh.py](http://xtsukihime.webs.com/Noesis%20Plugins/fmt_RFOnline_msh.py)

All of the data is tossed into lists and each mesh constructed with with `build_mesh`
I think that's how the format works from the C# code. 

There's no format-checking here, so if you have any other msh plugins might want to remove them from the folder.
## Post #5
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-02T03:40:25+00:00
- Post Title: RF Online Unknow rare model extracted

Finale i found this, its a link of something boy nava he made lots of thinks for RF also a viewer
in the viewer its posible see something thinks, i keep a link hope this help.

[http://honor-rf.blogspot.com/2008/11/final-update.html](http://honor-rf.blogspot.com/2008/11/final-update.html)

Btw he  posted here in Xentax

[viewtopic.php?f=16&t=3031](http://forum.xentax.com/viewtopic.php?f=16&t=3031)
## Post #6
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-02T11:23:26+00:00
- Post Title: RF Online Unknow rare model extracted

> Reply from Rimbros
>
> Finale i found this, its a link of something boy nava he made lots of thinks for RF also a viewer
in the viewer its posible see something thinks, i keep a link hope this help.

http://honor-rf.blogspot.com/2008/11/final-update.html

Btw he  posted here in Xentax

viewtopic.php?f=16&t=3031well my friend I remember for convert MSH to OBJ need be select different options, you need try, sometimes you get errors, so need activate Skip Sector or something like that, don't remember exactly, but someone can take a look it, I remember 1 topic you post with format structure + source convertor, but nobody take it I think
## Post #7
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-02T17:54:51+00:00
- Post Title: RF Online Unknow rare model extracted

[viewtopic.php?f=16&t=3031](http://forum.xentax.com/viewtopic.php?f=16&t=3031)[/quote]well my friend I remember for convert MSH to OBJ need be select different options, you need try, sometimes you get errors, so need activate Skip Sector or something like that, don't remember exactly, but someone can take a look it, I remember 1 topic you post with format structure + source convertor, but nobody take it I think  [/quote]

Thanks Crit, but now i have more info, if u can read the post you can see can be extracted but all the armors items have cuts in half, and stored in the center of the axis in every program. a complete bunch of trash. I ask abouth posibilty of extract each body part complete in good position, btw i see maybe if i use 3D ripper with this mshview program i can, but the little program its missing in broken links.

Finale wath you think abouth the info on this post? can be usefully?.

[http://www.rfpoa.com/forum/showthread.php?t=71574](http://www.rfpoa.com/forum/showthread.php?t=71574)

Btw i found this programe its new since 2010


Here the link to download
[http://public.djzmo.com/?p=projects/rft ... mwo1.0.zip](http://public.djzmo.com/?p=projects/rftools/rimwo1.0.zip)

But its something rare this only extract half parts.


Another option its i hope the Blender Master Szkaradek123 can take a view of the mesh building finale made in .py format.
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-05T01:29:27+00:00
- Post Title: RF Online Unknow rare model extracted

I don't know how the transformations are applied.
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-12T22:39:06+00:00
- Post Title: RF Online Unknow rare model extracted

Alright the first matrix in the mesh is the transformation that should be applied to the vertex group.
Just update the existing tools to apply that matrix and it should be fine.



The only issue now is that the UV's are stored per-face.

There are two ways to deal with this that I can think of, but both have not been obvious or have been unsuccessful

1: immediate mode rendering. It just looks weird...like really. All the normals looked wrong and the model just looked like a bunch of blocks put together

2: per-face UV to per-vertex UV. I'll have to duplicate vertices in this case I guess.

If someone can update the script to correctly map UV's then you can at least get the meshes out.

[http://db.tt/WRtUTlF1](http://db.tt/WRtUTlF1)
## Post #10
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-13T19:31:29+00:00
- Post Title: RF Online Unknow rare model extracted

Maybe zskaradek but i think he leave the forum, or mr. adults but its so hard contact with he. then at least all its lost.
## Post #11
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-14T04:34:04+00:00
- Post Title: RF Online Unknow rare model extracted

Interesting Finale you already fix the problem of the meshes, te only think need to fix its the uvMaps, simpli amazing also the meshes are nor more half cuts and now have good position in axis.
Its posible maybe you found how nava keep out the uvmaps info in the source code posted?

Here i put 3 files, OBJ files, one its keep out with Noesis meshes are fine but not uvmap, other its keep out with msh/obj converter mesh its wrong but uvmap its fine, and other its original mesh file the objects its the same, and i put the texture also to test, hope this can help.

[http://www.4shared.com/rar/myIef1Ma/4objects.html](http://www.4shared.com/rar/myIef1Ma/4objects.html)
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-14T04:56:15+00:00
- Post Title: RF Online Unknow rare model extracted

Here's a quickbms unpacker:

```
#RF Online .RFS unpacker
#written by Tsukihime
#Feb 13, 2012

get FILES long
for i = 0 < FILES do
	savepos CURR
	math CURR += 40 #just hacking around
	get NAME string
	goto CURR
	get unk long
	get null long
	get unk2 long
	get unk3 long
	get OFFSET long
	get SIZE long
	log NAME OFFSET SIZE
next i

```


I know how the UV's are stored.

```
   #indices
   int32[3] v1, v2, v3

   #uv's
   float[3] u1, v1, w1
   float[3] u2, v2, w2
   float[3] u3, v3, w3
}

```


Or something like that.
I'm just not getting any good results when creating a uv buffer for binding, and immediate mode rendering with those matrix transforms isn't turning out as great as it seems.

I was looking at the archives and it looks like some of the meshes actually have an idstring "MESH08", and that format is almost completely different since it doesn't store the UV's with the faces.

Can nava's tool load these?
[HCM00.7z](https://xentaxbackup.github.io/file/5062_HCM00.7z)
## Post #13
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-14T06:04:02+00:00
- Post Title: RF Online Unknow rare model extracted

Maybe this explain why the nava tool have this two options.
## Post #14
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-14T06:06:15+00:00
- Post Title: RF Online Unknow rare model extracted

I'm asking because I couldn't get any results. Maybe I'm not using it properly? I wouldn't know what "sector3" is without looking at the source

EDIT: you know it just looks like a format they just left in and forgot to take out.

All of the indices are ordered like

```
3 4 5
6 7 8
9 10 11
...

n n+1 n+2

```


And each vertex is like a 64 byte struct.

Why it's completely different from the other format except the mesh header is completely beyond me.
## Post #15
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-14T06:12:02+00:00
- Post Title: RF Online Unknow rare model extracted

cant load the .obj file, but btw i put here the .obj generated by nava tool.

[http://www.4shared.com/rar/AkNIJqo4/NAVATOOL.html](http://www.4shared.com/rar/AkNIJqo4/NAVATOOL.html)

well the player mesh folders have 70% of the objects in game.
its can be fixed almost on this but cant be fixed in npc its ok  i think.
## Post #16
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-14T06:14:13+00:00
- Post Title: Re: RF Online Unknow rare model extracted

Ya it doesn't handle the MESH08. And a lot of meshes use this format.
Just open the original msh in hex editor, look at the first 6 bytes, then look at the obj output and notice that the object name is wrong.
## Post #17
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-14T06:20:12+00:00
- Post Title: Re: RF Online Unknow rare model extracted

Any chance to put uvmap in the redeable files and keep out the wrong files?. If need be adjusted manually can u explain how?.
## Post #18
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-14T06:34:46+00:00
- Post Title: Re: RF Online Unknow rare model extracted

I've already figured out the majority of the format for MESH08 models. It's easy to texture also.
It looks like they are basically static meshes and usually just accessories.



For the format with the armors and stuff, I am going to have to think about how to deal with how the UV's are defined since several attempts to deal with it haven't worked.
## Post #19
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-14T07:43:39+00:00
- Post Title: Re: RF Online Unknow rare model extracted

This its also the source code of the Client and Server of RF, i dont know if this can be usefully.

[http://hotfile.com/dl/14899672/80b1aff/ ... n.rar.html](http://hotfile.com/dl/14899672/80b1aff/RF_Online_Engine___Client___Server_Sourcecode_-_Share_by_KillerStefan.rar.html)
## Post #20
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-14T23:48:22+00:00
- Post Title: Re: RF Online Unknow rare model extracted

ok here we go, I try help my friend Rimbros making this steps.

1º Use Noesis plugin of finale00 to export objeect to OBJ
2º Using NAVA tool for convert msh to obj
3º Ok we know nava tool export UV's fine so what I do is copy the data of obj nava to obj finale00 and get it.
4º Ok here I upload 3 files

*ARMOR_UPPER_116 UVMAPFINE (Exported with NAVA TOOL)
*ARMOR_UPPER_116out UVMAPWRONG (Exported with Noesis)
*ARMOR_UPPER_116out UVMAPFIX (Fixed by me)



[RF Online 3D Samples Fix UV's](http://www.mediafire.com/download.php?q1f6a3r6o23u80i)

Examples

```
mtllib BELFEMALE_ARMOR_UPPER_116.msh.mtl

o U0
g NULL
v 0.692800 0.697200 -0.815700
v 0.945300 0.460500 -0.818500
v 0.224400 -0.026900 0.778300
v 0.000000 0.643100 0.890200
v 1.182200 -0.188300 -0.654300
v 0.000000 -0.590500 0.092200
v 0.000000 -0.143000 0.758000
v 0.480600 -0.151300 0.509800
v 1.107400 -0.204900 -0.697800
v 0.888800 0.142500 0.468400
v 1.236500 0.120800 0.388200
v 0.000000 -0.256900 0.483300
v 0.000000 0.759200 0.498600
v 0.936900 0.553700 0.558500
v 0.000000 0.886400 -0.748900
v 1.171600 -0.093200 -0.053800
v 1.000600 0.518900 -0.801300
v 0.000000 -0.244000 0.728100
v 0.778500 0.870400 -0.137400
v 0.000000 0.693200 0.873800
v 0.000000 -0.370700 0.208600
v 0.314100 -0.109200 0.772900
v 0.623400 0.565000 0.653300
v 0.473900 0.211000 0.871900
v 0.459700 0.887500 0.166500
v 0.360400 0.246200 0.862900
v 1.267300 0.529800 0.482900
v 0.000000 -0.568300 0.010200
v 0.947400 0.727700 0.401100
v 0.000000 0.851400 -0.011900
v 0.530800 -0.586100 0.076400
v 1.071300 -0.062400 0.202500
v 1.135100 -0.495100 -0.255500
v 1.036300 0.848000 -0.107400
v 1.240600 0.769600 0.322100
v 1.066000 -0.489400 -0.322900
v 0.304700 0.489400 0.883700
v 1.152700 -0.132700 -0.356900
v 0.718500 0.784400 -0.789200
v 0.000000 0.790600 -0.789400
v 0.521200 -0.565100 -0.005700
v 0.858300 -0.581200 -0.041600
v 0.819200 -0.557400 -0.136400
v 1.136400 0.554800 -0.433200
v 0.423500 0.515700 0.896401
v 0.736800 -0.275700 0.241400
v 0.624600 0.194300 0.637200
v 0.850300 -0.780900 -0.379800
v 1.055600 0.034400 -0.896401
v 0.000000 -0.873500 -0.385100
v 0.426700 -0.887400 -0.249700
v 1.145100 0.325400 -0.446600
v 1.127300 0.064100 -0.865800
v -0.692800 0.697200 -0.815700
v -0.945300 0.460500 -0.818500
v -0.224400 -0.026900 0.778300
v -1.182200 -0.188300 -0.654300
v -0.480600 -0.151300 0.509800
v -1.107400 -0.204900 -0.697800
v -0.888800 0.142500 0.468400
v -1.236500 0.120800 0.388200
v -0.936900 0.553700 0.558500
v -1.171600 -0.093200 -0.053800
v -1.000600 0.518900 -0.801300
v -0.778500 0.870400 -0.137400
v -0.314100 -0.109200 0.772900
v -0.623400 0.565000 0.653300
v -0.473900 0.211000 0.871900
v -0.459700 0.887500 0.166500
v -0.360400 0.246200 0.862900
v -1.267300 0.529800 0.482900
v -0.947400 0.727700 0.401100
v -0.530800 -0.586100 0.076400
v -1.071300 -0.062400 0.202500
v -1.135100 -0.495100 -0.255500
v -1.036300 0.848000 -0.107400
v -1.240600 0.769600 0.322100
v -1.066000 -0.489400 -0.322900
v -0.304700 0.489400 0.883700
v -1.152700 -0.132700 -0.356900
v -0.718500 0.784400 -0.789200
v -0.521200 -0.565100 -0.005700
v -0.858300 -0.581200 -0.041600
v -0.819200 -0.557400 -0.136400
v -1.136400 0.554800 -0.433200
v -0.423500 0.515700 0.896401
v -0.736800 -0.275700 0.241400
v -0.624600 0.194300 0.637200
v -0.850400 -0.780900 -0.379800
v -1.055600 0.034400 -0.896401
v -0.426700 -0.887400 -0.249700
v -1.145100 0.325400 -0.446600
v -1.127300 0.064100 -0.865800
#93 V

vt 0.2621 0.2521 0.000000
vt 0.2007 0.2755 0.000000
vt 0.2328 0.2041 0.000000
vt 0.2328 0.2041 0.000000
vt 0.2007 0.2755 0.000000
vt 0.1563 0.1874 0.000000
vt 0.1719 0.1068 0.000000
vt 0.2328 0.2041 0.000000
vt 0.1563 0.1874 0.000000
vt 0.1563 0.1874 0.000000
vt 0.1111 0.1253 0.000000
vt 0.1719 0.1068 0.000000
vt 0.0153 0.2286 0.000000
vt 0.107 0.2458 0.000000
vt 0.0681 0.2897 0.000000
vt 0.0681 0.2897 0.000000
vt 0.0083 0.272 0.000000
vt 0.0153 0.2286 0.000000
vt 0.1079 0.3397 0.000000
vt 0.1507 0.31 0.000000
vt 0.1789 0.3819 0.000000
vt 0.1789 0.3819 0.000000
vt 0.1202 0.3899 0.000000
vt 0.1079 0.3397 0.000000
vt 0.0681 0.2897 0.000000
vt 0.107 0.2458 0.000000
vt 0.1507 0.31 0.000000
vt 0.1507 0.31 0.000000
vt 0.1079 0.3397 0.000000
vt 0.0681 0.2897 0.000000
vt 0.0162 0.1758 0.000000
vt 0.0134 0.1303 0.000000
vt 0.1111 0.1253 0.000000
vt 0.1563 0.1874 0.000000
vt 0.0162 0.1758 0.000000
vt 0.1111 0.1253 0.000000
vt 0.2333 0.3495 0.000000
vt 0.2621 0.2521 0.000000
vt 0.283 0.321 0.000000
vt 0.2007 0.2755 0.000000
vt 0.2621 0.2521 0.000000
vt 0.2333 0.3495 0.000000
vt 0.2328 0.2041 0.000000
vt 0.2686 0.1586 0.000000
vt 0.2621 0.2521 0.000000
vt 0.2328 0.2041 0.000000
vt 0.1719 0.1068 0.000000
vt 0.2686 0.1586 0.000000
vt 0.2686 0.1586 0.000000
vt 0.1719 0.1068 0.000000
vt 0.2308 0.08270001 0.000000
vt 0.2941 0.1045 0.000000
vt 0.2686 0.1586 0.000000
vt 0.2308 0.08270001 0.000000
vt 0.3158 0.0528 0.000000
vt 0.2941 0.1045 0.000000
vt 0.2308 0.08270001 0.000000
vt 0.402 0.5673 0.000000
vt 0.3537 0.4333 0.000000
vt 0.4625 0.5305 0.000000
vt 0.3219 0.4745 0.000000
vt 0.3537 0.4333 0.000000
vt 0.402 0.5673 0.000000
vt 0.3046 0.6587 0.000000
vt 0.2054 0.5655 0.000000
vt 0.3219 0.4745 0.000000
vt 0.402 0.5673 0.000000
vt 0.3046 0.6587 0.000000
vt 0.3219 0.4745 0.000000
vt 0.3537 0.4333 0.000000
vt 0.3219 0.4745 0.000000
vt 0.2638 0.3822 0.000000
vt 0.2638 0.3822 0.000000
vt 0.2333 0.3495 0.000000
vt 0.283 0.321 0.000000
vt 0.2638 0.3822 0.000000
vt 0.3219 0.4745 0.000000
vt 0.2392 0.4813 0.000000
vt 0.3219 0.4745 0.000000
vt 0.2054 0.5655 0.000000
vt 0.2392 0.4813 0.000000
vt 0.2638 0.3822 0.000000
vt 0.283 0.321 0.000000
vt 0.3093 0.358 0.000000
vt 0.2638 0.3822 0.000000
vt 0.3093 0.358 0.000000
vt 0.3537 0.4333 0.000000
vt 0.1202 0.3899 0.000000
vt 0.1789 0.3819 0.000000
vt 0.1343 0.5022 0.000000
vt 0.1343 0.5022 0.000000
vt 0.0782 0.4617 0.000000
vt 0.1202 0.3899 0.000000
vt 0.4625 0.5305 0.000000
vt 0.3537 0.4333 0.000000
vt 0.4343 0.4645 0.000000
vt 0.0128 0.1096 0.000000
vt 0.1101 0.1049 0.000000
vt 0.1111 0.1253 0.000000
vt 0.1111 0.1253 0.000000
vt 0.0134 0.1303 0.000000
vt 0.0128 0.1096 0.000000
vt 0.1101 0.1049 0.000000
vt 0.1689 0.08740002 0.000000
vt 0.1719 0.1068 0.000000
vt 0.1719 0.1068 0.000000
vt 0.1111 0.1253 0.000000
vt 0.1101 0.1049 0.000000
vt 0.1689 0.08740002 0.000000
vt 0.2287 0.06660002 0.000000
vt 0.2308 0.08270001 0.000000
vt 0.2308 0.08270001 0.000000
vt 0.1719 0.1068 0.000000
vt 0.1689 0.08740002 0.000000
vt 0.2287 0.06660002 0.000000
vt 0.3132 0.0363 0.000000
vt 0.3158 0.0528 0.000000
vt 0.3158 0.0528 0.000000
vt 0.2308 0.08270001 0.000000
vt 0.2287 0.06660002 0.000000
vt 0.4707 0.544 0.000000
vt 0.4144 0.579 0.000000
vt 0.402 0.5673 0.000000
vt 0.402 0.5673 0.000000
vt 0.4625 0.5305 0.000000
vt 0.4707 0.544 0.000000
vt 0.4144 0.579 0.000000
vt 0.3201 0.6705 0.000000
vt 0.3046 0.6587 0.000000
vt 0.3046 0.6587 0.000000
vt 0.402 0.5673 0.000000
vt 0.4144 0.579 0.000000
vt 0.0162 0.1758 0.000000
vt 0.1563 0.1874 0.000000
vt 0.107 0.2458 0.000000
vt 0.107 0.2458 0.000000
vt 0.0153 0.2286 0.000000
vt 0.0162 0.1758 0.000000
vt 0.1789 0.3819 0.000000
vt 0.1507 0.31 0.000000
vt 0.2333 0.3495 0.000000
vt 0.2007 0.2755 0.000000
vt 0.2333 0.3495 0.000000
vt 0.1507 0.31 0.000000
vt 0.107 0.2458 0.000000
vt 0.1563 0.1874 0.000000
vt 0.2007 0.2755 0.000000
vt 0.2007 0.2755 0.000000
vt 0.1507 0.31 0.000000
vt 0.107 0.2458 0.000000
vt 0.1789 0.3819 0.000000
vt 0.2333 0.3495 0.000000
vt 0.2638 0.3822 0.000000
vt 0.1789 0.3819 0.000000
vt 0.2638 0.3822 0.000000
vt 0.2392 0.4813 0.000000
vt 0.2392 0.4813 0.000000
vt 0.1343 0.5022 0.000000
vt 0.1789 0.3819 0.000000
vt 0.1343 0.5022 0.000000
vt 0.2392 0.4813 0.000000
vt 0.2054 0.5655 0.000000
vt 0.1079 0.3397 0.000000
vt 0.0903 0.3514 0.000000
vt 0.0542 0.3068 0.000000
vt 0.0542 0.3068 0.000000
vt 0.0681 0.2897 0.000000
vt 0.1079 0.3397 0.000000
vt 0.0681 0.2897 0.000000
vt 0.0542 0.3068 0.000000
vt 0.0105 0.2911 0.000000
vt 0.0105 0.2911 0.000000
vt 0.0083 0.272 0.000000
vt 0.0681 0.2897 0.000000
vt 0.1202 0.3899 0.000000
vt 0.0996 0.3969 0.000000
vt 0.0903 0.3514 0.000000
vt 0.0903 0.3514 0.000000
vt 0.1079 0.3397 0.000000
vt 0.1202 0.3899 0.000000
vt 0.0782 0.4617 0.000000
vt 0.072 0.4541 0.000000
vt 0.0996 0.3969 0.000000
vt 0.0996 0.3969 0.000000
vt 0.1202 0.3899 0.000000
vt 0.0782 0.4617 0.000000
vt 0.0571 0.9804 0.000000
vt 0.1274 0.8973 0.000000
vt 0.1233 0.9646 0.000000
vt 0.0421 0.9049 0.000000
vt 0.1274 0.8973 0.000000
vt 0.0571 0.9804 0.000000
vt 0.3884 0.9754 0.000000
vt 0.3992 0.8775 0.000000
vt 0.476 0.9106 0.000000
vt 0.5573 0.9703 0.000000
vt 0.5613 0.903 0.000000
vt 0.6188 0.9405 0.000000
vt 0.4911 0.9861 0.000000
vt 0.3884 0.9754 0.000000
vt 0.476 0.9106 0.000000
vt 0.9542 0.876 0.000000
vt 0.9087 0.9546 0.000000
vt 0.9068 0.878 0.000000
vt 0.9087 0.9546 0.000000
vt 0.9542 0.876 0.000000
vt 0.9813 0.9207 0.000000
vt 0.9813 0.9207 0.000000
vt 0.9076 0.9923 0.000000
vt 0.9087 0.9546 0.000000
vt 0.9813 0.9207 0.000000
vt 0.9698 0.9949 0.000000
vt 0.9076 0.9923 0.000000
vt 0.9683 0.8726 0.000000
vt 0.9938 0.918 0.000000
vt 0.9813 0.9207 0.000000
vt 0.9813 0.9207 0.000000
vt 0.9542 0.876 0.000000
vt 0.9683 0.8726 0.000000
vt 0.9938 0.918 0.000000
vt 0.9819 0.9894 0.000000
vt 0.9698 0.9949 0.000000
vt 0.9698 0.9949 0.000000
vt 0.9813 0.9207 0.000000
vt 0.9938 0.918 0.000000
vt 0.2621 0.2521 0.000000
vt 0.2328 0.2041 0.000000
vt 0.2007 0.2755 0.000000
vt 0.2328 0.2041 0.000000
vt 0.1563 0.1874 0.000000
vt 0.2007 0.2755 0.000000
vt 0.1719 0.1068 0.000000
vt 0.1563 0.1874 0.000000
vt 0.2328 0.2041 0.000000
vt 0.1563 0.1874 0.000000
vt 0.1719 0.1068 0.000000
vt 0.1111 0.1253 0.000000
vt 0.0153 0.2286 0.000000
vt 0.0681 0.2897 0.000000
vt 0.107 0.2458 0.000000
vt 0.0681 0.2897 0.000000
vt 0.0153 0.2286 0.000000
vt 0.0083 0.272 0.000000
vt 0.1079 0.3397 0.000000
vt 0.1789 0.3819 0.000000
vt 0.1507 0.31 0.000000
vt 0.1789 0.3819 0.000000
vt 0.1079 0.3397 0.000000
vt 0.1202 0.3899 0.000000
vt 0.0681 0.2897 0.000000
vt 0.1507 0.31 0.000000
vt 0.107 0.2458 0.000000
vt 0.1507 0.31 0.000000
vt 0.0681 0.2897 0.000000
vt 0.1079 0.3397 0.000000
vt 0.0162 0.1758 0.000000
vt 0.1111 0.1253 0.000000
vt 0.0134 0.1303 0.000000
vt 0.1563 0.1874 0.000000
vt 0.1111 0.1253 0.000000
vt 0.0162 0.1758 0.000000
vt 0.2333 0.3495 0.000000
vt 0.283 0.321 0.000000
vt 0.2621 0.2521 0.000000
vt 0.2007 0.2755 0.000000
vt 0.2333 0.3495 0.000000
vt 0.2621 0.2521 0.000000
vt 0.2328 0.2041 0.000000
vt 0.2621 0.2521 0.000000
vt 0.2686 0.1586 0.000000
vt 0.2328 0.2041 0.000000
vt 0.2686 0.1586 0.000000
vt 0.1719 0.1068 0.000000
vt 0.2686 0.1586 0.000000
vt 0.2308 0.08270001 0.000000
vt 0.1719 0.1068 0.000000
vt 0.2941 0.1045 0.000000
vt 0.2308 0.08270001 0.000000
vt 0.2686 0.1586 0.000000
vt 0.3158 0.0528 0.000000
vt 0.2308 0.08270001 0.000000
vt 0.2941 0.1045 0.000000
vt 0.402 0.5673 0.000000
vt 0.4625 0.5305 0.000000
vt 0.3537 0.4333 0.000000
vt 0.3219 0.4745 0.000000
vt 0.402 0.5673 0.000000
vt 0.3537 0.4333 0.000000
vt 0.3046 0.6587 0.000000
vt 0.3219 0.4745 0.000000
vt 0.2054 0.5655 0.000000
vt 0.402 0.5673 0.000000
vt 0.3219 0.4745 0.000000
vt 0.3046 0.6587 0.000000
vt 0.3537 0.4333 0.000000
vt 0.2638 0.3822 0.000000
vt 0.3219 0.4745 0.000000
vt 0.2638 0.3822 0.000000
vt 0.283 0.321 0.000000
vt 0.2333 0.3495 0.000000
vt 0.2638 0.3822 0.000000
vt 0.2392 0.4813 0.000000
vt 0.3219 0.4745 0.000000
vt 0.3219 0.4745 0.000000
vt 0.2392 0.4813 0.000000
vt 0.2054 0.5655 0.000000
vt 0.2638 0.3822 0.000000
vt 0.3093 0.358 0.000000
vt 0.283 0.321 0.000000
vt 0.2638 0.3822 0.000000
vt 0.3537 0.4333 0.000000
vt 0.3093 0.358 0.000000
vt 0.1202 0.3899 0.000000
vt 0.1343 0.5022 0.000000
vt 0.1789 0.3819 0.000000
vt 0.1343 0.5022 0.000000
vt 0.1202 0.3899 0.000000
vt 0.0782 0.4617 0.000000
vt 0.4625 0.5305 0.000000
vt 0.4343 0.4645 0.000000
vt 0.3537 0.4333 0.000000
vt 0.0128 0.1096 0.000000
vt 0.1111 0.1253 0.000000
vt 0.1101 0.1049 0.000000
vt 0.1111 0.1253 0.000000
vt 0.0128 0.1096 0.000000
vt 0.0134 0.1303 0.000000
vt 0.1101 0.1049 0.000000
vt 0.1719 0.1068 0.000000
vt 0.1689 0.08740002 0.000000
vt 0.1719 0.1068 0.000000
vt 0.1101 0.1049 0.000000
vt 0.1111 0.1253 0.000000
vt 0.1689 0.08740002 0.000000
vt 0.2308 0.08270001 0.000000
vt 0.2287 0.06660002 0.000000
vt 0.2308 0.08270001 0.000000
vt 0.1689 0.08740002 0.000000
vt 0.1719 0.1068 0.000000
vt 0.2287 0.06660002 0.000000
vt 0.3158 0.0528 0.000000
vt 0.3132 0.0363 0.000000
vt 0.3158 0.0528 0.000000
vt 0.2287 0.06660002 0.000000
vt 0.2308 0.08270001 0.000000
vt 0.4707 0.544 0.000000
vt 0.402 0.5673 0.000000
vt 0.4144 0.579 0.000000
vt 0.402 0.5673 0.000000
vt 0.4707 0.544 0.000000
vt 0.4625 0.5305 0.000000
vt 0.4144 0.579 0.000000
vt 0.3046 0.6587 0.000000
vt 0.3201 0.6705 0.000000
vt 0.3046 0.6587 0.000000
vt 0.4144 0.579 0.000000
vt 0.402 0.5673 0.000000
vt 0.0162 0.1758 0.000000
vt 0.107 0.2458 0.000000
vt 0.1563 0.1874 0.000000
vt 0.107 0.2458 0.000000
vt 0.0162 0.1758 0.000000
vt 0.0153 0.2286 0.000000
vt 0.1507 0.31 0.000000
vt 0.1789 0.3819 0.000000
vt 0.2333 0.3495 0.000000
vt 0.2333 0.3495 0.000000
vt 0.2007 0.2755 0.000000
vt 0.1507 0.31 0.000000
vt 0.107 0.2458 0.000000
vt 0.2007 0.2755 0.000000
vt 0.1563 0.1874 0.000000
vt 0.2007 0.2755 0.000000
vt 0.107 0.2458 0.000000
vt 0.1507 0.31 0.000000
vt 0.1789 0.3819 0.000000
vt 0.2638 0.3822 0.000000
vt 0.2333 0.3495 0.000000
vt 0.1789 0.3819 0.000000
vt 0.2392 0.4813 0.000000
vt 0.2638 0.3822 0.000000
vt 0.2392 0.4813 0.000000
vt 0.1789 0.3819 0.000000
vt 0.1343 0.5022 0.000000
vt 0.1343 0.5022 0.000000
vt 0.2054 0.5655 0.000000
vt 0.2392 0.4813 0.000000
vt 0.1079 0.3397 0.000000
vt 0.0542 0.3068 0.000000
vt 0.0903 0.3514 0.000000
vt 0.0542 0.3068 0.000000
vt 0.1079 0.3397 0.000000
vt 0.0681 0.2897 0.000000
vt 0.0681 0.2897 0.000000
vt 0.0105 0.2911 0.000000
vt 0.0542 0.3068 0.000000
vt 0.0105 0.2911 0.000000
vt 0.0681 0.2897 0.000000
vt 0.0083 0.272 0.000000
vt 0.1202 0.3899 0.000000
vt 0.0903 0.3514 0.000000
vt 0.0996 0.3969 0.000000
vt 0.0903 0.3514 0.000000
vt 0.1202 0.3899 0.000000
vt 0.1079 0.3397 0.000000
vt 0.0782 0.4617 0.000000
vt 0.0996 0.3969 0.000000
vt 0.072 0.4541 0.000000
vt 0.0996 0.3969 0.000000
vt 0.0782 0.4617 0.000000
vt 0.1202 0.3899 0.000000
vt 0.4911 0.9861 0.000000
vt 0.5573 0.9703 0.000000
vt 0.5613 0.903 0.000000
vt 0.476 0.9106 0.000000
vt 0.4911 0.9861 0.000000
vt 0.5613 0.903 0.000000
vt 0.3884 0.9754 0.000000
vt 0.476 0.9106 0.000000
vt 0.3992 0.8775 0.000000
vt 0.5573 0.9703 0.000000
vt 0.6188 0.9405 0.000000
vt 0.5613 0.903 0.000000
vt 0.4911 0.9861 0.000000
vt 0.476 0.9106 0.000000
vt 0.3884 0.9754 0.000000
vt 0.9542 0.876 0.000000
vt 0.9068 0.878 0.000000
vt 0.9087 0.9546 0.000000
vt 0.9087 0.9546 0.000000
vt 0.9813 0.9207 0.000000
vt 0.9542 0.876 0.000000
vt 0.9813 0.9207 0.000000
vt 0.9087 0.9546 0.000000
vt 0.9076 0.9923 0.000000
vt 0.9813 0.9207 0.000000
vt 0.9076 0.9923 0.000000
vt 0.9698 0.9949 0.000000
vt 0.9683 0.8726 0.000000
vt 0.9813 0.9207 0.000000
vt 0.9938 0.918 0.000000
vt 0.9813 0.9207 0.000000
vt 0.9683 0.8726 0.000000
vt 0.9542 0.876 0.000000
vt 0.9938 0.918 0.000000
vt 0.9698 0.9949 0.000000
vt 0.9819 0.9894 0.000000
vt 0.9698 0.9949 0.000000
vt 0.9938 0.918 0.000000
vt 0.9813 0.9207 0.000000
#VT 450

vn -0.070427 -0.306221 0.949352
vn -0.138739 -0.201616 0.969589
vn 0.110302 0.185247 -0.976482
vn 0.000000 -0.311089 -0.950381
vn -0.873106 0.361020 0.327644
vn 0.000000 0.917317 -0.398159
vn 0.000000 0.194991 -0.980805
vn -0.361750 0.747330 -0.557346
vn -0.499343 0.572371 0.650422
vn -0.362560 0.479003 -0.799441
vn -0.286004 0.551334 -0.783729
vn 0.000000 0.969773 -0.244009
vn 0.000000 -0.949909 -0.312528
vn -0.301478 -0.099647 -0.948252
vn 0.000000 -0.803836 0.594851
vn -0.806892 0.475509 -0.350452
vn -0.523519 -0.414869 0.744185
vn 0.000000 0.767041 -0.641598
vn -0.077633 -0.996864 -0.015339
vn 0.000000 -0.477921 -0.878403
vn 0.000000 0.720356 -0.693604
vn -0.310708 0.600736 -0.736598
vn -0.418498 -0.549455 -0.723159
vn -0.376582 0.197029 -0.905188
vn -0.038695 -0.960263 -0.276400
vn 0.112905 0.142578 -0.983323
vn -0.202393 -0.356200 -0.912227
vn 0.000000 0.966470 -0.256780
vn -0.121786 -0.843794 -0.522666
vn 0.000000 -0.999109 -0.042199
vn -0.054670 0.927640 -0.369452
vn -0.478885 0.653851 -0.585789
vn -0.719718 0.691581 0.061007
vn -0.319948 -0.943846 0.082389
vn -0.031606 -0.829679 -0.557345
vn -0.464788 0.866069 0.184111
vn -0.001282 -0.040919 -0.999162
vn -0.998760 0.016243 -0.047061
vn -0.235484 -0.669559 0.704442
vn 0.000000 -0.389387 0.921074
vn -0.110963 0.952324 -0.284196
vn -0.368206 0.872554 -0.321050
vn -0.240444 0.962020 -0.129247
vn -0.907085 -0.330104 0.261207
vn -0.231847 -0.355452 -0.905484
vn -0.293870 0.610655 -0.735351
vn -0.607948 0.310036 -0.730943
vn -0.427981 0.626650 -0.651263
vn -0.325636 0.023586 0.945201
vn 0.000000 0.791536 -0.611123
vn -0.062798 0.694061 -0.717172
vn -0.997411 -0.065052 0.030638
vn -0.822478 0.056877 0.565946
vn 0.070427 -0.306221 0.949352
vn 0.138739 -0.201616 0.969589
vn -0.110302 0.185247 -0.976482
vn 0.873106 0.361020 0.327644
vn 0.361750 0.747330 -0.557346
vn 0.499343 0.572371 0.650422
vn 0.362560 0.479003 -0.799441
vn 0.286004 0.551334 -0.783730
vn 0.301478 -0.099647 -0.948252
vn 0.806892 0.475509 -0.350452
vn 0.523519 -0.414869 0.744185
vn 0.077633 -0.996864 -0.015339
vn 0.310708 0.600736 -0.736598
vn 0.418498 -0.549455 -0.723159
vn 0.376582 0.197029 -0.905188
vn 0.038695 -0.960263 -0.276400
vn -0.112905 0.142578 -0.983323
vn 0.202393 -0.356200 -0.912227
vn 0.121786 -0.843794 -0.522666
vn 0.054670 0.927640 -0.369452
vn 0.478885 0.653851 -0.585789
vn 0.719718 0.691581 0.061007
vn 0.319948 -0.943846 0.082389
vn 0.031606 -0.829679 -0.557345
vn 0.464817 0.866058 0.184087
vn 0.001282 -0.040919 -0.999162
vn 0.998760 0.016243 -0.047061
vn 0.235484 -0.669559 0.704442
vn 0.110954 0.952318 -0.284217
vn 0.368206 0.872554 -0.321050
vn 0.240469 0.962007 -0.129292
vn 0.907085 -0.330104 0.261207
vn 0.231847 -0.355452 -0.905484
vn 0.293870 0.610655 -0.735351
vn 0.607948 0.310036 -0.730943
vn 0.427979 0.626577 -0.651334
vn 0.325636 0.023586 0.945201
vn 0.062772 0.694057 -0.717179
vn 0.997411 -0.065052 0.030638
vn 0.822478 0.056877 0.565946

#s NULL
usemtl modelx_auv1143
f 11/1/11 10/2/10 32/3/32
f 32/4/32 10/5/10 46/6/46
f 42/7/42 32/8/32 46/9/46
f 46/10/46 31/11/31 42/12/42
f 12/13/12 8/14/8 22/15/22
f 22/16/22 18/17/18 12/18/12
f 24/19/24 47/20/47 23/21/23
f 23/22/23 45/23/45 24/24/24
f 22/25/22 8/26/8 47/27/47
f 47/28/47 24/29/24 22/30/22
f 21/31/21 6/32/6 31/33/31
f 46/34/46 21/35/21 31/36/31
f 14/37/14 11/38/11 27/39/27
f 10/40/10 11/41/11 14/42/14
f 32/43/32 16/44/16 11/45/11
f 32/46/32 42/47/42 16/48/16
f 16/49/16 42/50/42 33/51/33
f 38/52/38 16/53/16 33/54/33
f 5/55/5 38/56/38 33/57/33
f 39/58/39 34/59/34 17/60/17
f 19/61/19 34/62/34 39/63/39
f 15/64/15 30/65/30 19/66/19
f 39/67/39 15/68/15 19/69/19
f 34/70/34 19/71/19 29/72/29
f 29/73/29 14/74/14 27/75/27
f 29/76/29 19/77/19 25/78/25
f 19/79/19 30/80/30 25/81/25
f 29/82/29 27/83/27 35/84/35
f 29/85/29 35/86/35 34/87/34
f 45/88/45 23/89/23 13/90/13
f 13/91/13 20/92/20 45/93/45
f 17/94/17 34/95/34 44/96/44
f 28/97/28 41/98/41 31/99/31
f 31/100/31 6/101/6 28/102/28
f 41/103/41 43/104/43 42/105/42
f 42/106/42 31/107/31 41/108/41
f 43/109/43 36/110/36 33/111/33
f 33/112/33 42/113/42 43/114/43
f 36/115/36 9/116/9 5/117/5
f 5/118/5 33/119/33 36/120/36
f 2/121/2 1/122/1 39/123/39
f 39/124/39 17/125/17 2/126/2
f 1/127/1 40/128/40 15/129/15
f 15/130/15 39/131/39 1/132/1
f 21/133/21 46/134/46 8/135/8
f 8/136/8 12/137/12 21/138/21
f 23/139/23 47/140/47 14/141/14
f 10/142/10 14/143/14 47/144/47
f 8/145/8 46/146/46 10/147/10
f 10/148/10 47/149/47 8/150/8
f 23/151/23 14/152/14 29/153/29
f 23/154/23 29/155/29 25/156/25
f 25/157/25 13/158/13 23/159/23
f 13/160/13 25/161/25 30/162/30
f 24/163/24 26/164/26 3/165/3
f 3/166/3 22/167/22 24/168/24
f 22/169/22 3/170/3 7/171/7
f 7/172/7 18/173/18 22/174/22
f 45/175/45 37/176/37 26/177/26
f 26/178/26 24/179/24 45/180/45
f 20/181/20 4/182/4 37/183/37
f 37/184/37 45/185/45 20/186/20
f 41/187/41 48/188/48 43/189/43
f 51/190/51 48/191/48 41/192/41
f 28/193/28 50/194/50 51/195/51
f 43/196/43 48/197/48 36/198/36
f 41/199/41 28/200/28 51/201/51
f 5/202/5 52/203/52 38/204/38
f 52/205/52 5/206/5 53/207/53
f 53/208/53 44/209/44 52/210/52
f 53/211/53 17/212/17 44/213/44
f 9/214/9 49/215/49 53/216/53
f 53/217/53 5/218/5 9/219/9
f 49/220/49 2/221/2 17/222/17
f 17/223/17 53/224/53 49/225/49
f 61/226/61 74/227/74 60/228/60
f 74/229/74 87/230/87 60/231/60
f 83/232/83 87/233/87 74/234/74
f 87/235/87 83/236/83 73/237/73
f 12/238/12 66/239/66 58/240/58
f 66/241/66 12/242/12 18/243/18
f 68/244/68 67/245/67 88/246/88
f 67/247/67 68/248/68 86/249/86
f 66/250/66 88/251/88 58/252/58
f 88/253/88 66/254/66 68/255/68
f 21/256/21 73/257/73 6/258/6
f 87/259/87 73/260/73 21/261/21
f 62/262/62 71/263/71 61/264/61
f 60/265/60 62/266/62 61/267/61
f 74/268/74 61/269/61 63/270/63
f 74/271/74 63/272/63 83/273/83
f 63/274/63 75/275/75 83/276/83
f 80/277/80 75/278/75 63/279/63
f 57/280/57 75/281/75 80/282/80
f 81/283/81 64/284/64 76/285/76
f 65/286/65 81/287/81 76/288/76
f 15/289/15 65/290/65 30/291/30
f 81/292/81 65/293/65 15/294/15
f 76/295/76 72/296/72 65/297/65
f 72/298/72 71/299/71 62/300/62
f 72/301/72 69/302/69 65/303/65
f 65/304/65 69/305/69 30/306/30
f 72/307/72 77/308/77 71/309/71
f 72/310/72 76/311/76 77/312/77
f 86/313/86 13/314/13 67/315/67
f 13/316/13 86/317/86 20/318/20
f 64/319/64 85/320/85 76/321/76
f 28/322/28 73/323/73 82/324/82
f 73/325/73 28/326/28 6/327/6
f 82/328/82 83/329/83 84/330/84
f 83/331/83 82/332/82 73/333/73
f 84/334/84 75/335/75 78/336/78
f 75/337/75 84/338/84 83/339/83
f 78/340/78 57/341/57 59/342/59
f 57/343/57 78/344/78 75/345/75
f 55/346/55 81/347/81 54/348/54
f 81/349/81 55/350/55 64/351/64
f 54/352/54 15/353/15 40/354/40
f 15/355/15 54/356/54 81/357/81
f 21/358/21 58/359/58 87/360/87
f 58/361/58 21/362/21 12/363/12
f 88/364/88 67/365/67 62/366/62
f 62/367/62 60/368/60 88/369/88
f 58/370/58 60/371/60 87/372/87
f 60/373/60 58/374/58 88/375/88
f 67/376/67 72/377/72 62/378/62
f 67/379/67 69/380/69 72/381/72
f 69/382/69 67/383/67 13/384/13
f 13/385/13 30/386/30 69/387/69
f 68/388/68 56/389/56 70/390/70
f 56/391/56 68/392/68 66/393/66
f 66/394/66 7/395/7 56/396/56
f 7/397/7 66/398/66 18/399/18
f 86/400/86 70/401/70 79/402/79
f 70/403/70 86/404/86 68/405/68
f 20/406/20 79/407/79 4/408/4
f 79/409/79 20/410/20 86/411/86
f 82/412/82 84/413/84 89/414/89
f 91/415/91 82/416/82 89/417/89
f 28/418/28 91/419/91 50/420/50
f 84/421/84 78/422/78 89/423/89
f 82/424/82 91/425/91 28/426/28
f 57/427/57 80/428/80 92/429/92
f 92/430/92 93/431/93 57/432/57
f 93/433/93 92/434/92 85/435/85
f 93/436/93 85/437/85 64/438/64
f 59/439/59 93/440/93 90/441/90
f 93/442/93 59/443/59 57/444/57
f 90/445/90 64/446/64 55/447/55
f 64/448/64 90/449/90 93/450/93

o NULL
g 
#0 V

#VT 0


#s 
usemtl modelx_auv1144

o d=�>��=
g �?X�|��ʽTm�=
#-32296 V

#VT 0


#s �?X�|��ʽTm�=
usemtl modelx_auv1145

o 
g 
#-16710 V

#VT 0


#s 
usemtl modelx_auv1146

o 
g QA
8��!׆��g2Vi|���*>_)K;!�?
v 0.000000 0.000000 0.898488
v 0.120867 0.983238 -0.169088
v 0.643200 0.704700 0.000000
v 0.000000 0.000000 0.000000
v 0.322727 0.120867 0.987771
v 0.000000 0.643200 0.704700
v 0.000000 0.000000 0.000000
v 0.579244 0.795405 0.178347
v 0.616400 0.000000 0.567100
v 0.000000 0.000000 0.000000
v -0.053150 0.579244 0.795405
v 0.645600 0.633400 0.000000
v 0.704700 0.000000 0.000000
v 0.795405 0.178347 0.000000
v 0.061564 0.567100 0.688300
v 0.458200 0.659100 0.000000
v 0.579244 0.795405 0.178347
v 0.999454 -0.033053 0.567100
v 0.000000 0.478300 0.595900
v 0.000000 0.898488 0.435769
v 0.931701 0.011372 -0.363047
v 0.643800 0.000000 0.737600
v 0.000000 0.000000 0.931701
v -0.216937 0.898488 0.435769
v 0.644600 0.565300 0.000000
v 0.000000 0.000000 0.000000
v 0.435769 -0.053150 0.794016
v 0.000000 0.645600 0.633400
v 0.000000 0.000000 0.000000
v 0.410435 0.894939 -0.175004
v 0.565300 0.000000 0.572800
v 0.000000 0.000000 0.000000
v -0.033053 0.589831 0.806882
v 0.478300 0.595900 0.000000
v 0.530300 0.000000 0.000000
v 0.894939 -0.175004 0.000000
v -0.033053 0.572800 0.530300
v 0.478300 0.595900 0.000000
v 0.551203 -0.834324 0.008880
v -0.649788 0.123785 0.796600
v 0.000000 0.796200 0.698100
v 0.000000 0.551203 -0.834324
v 0.000033 -0.999865 -0.016460
v 0.678300 0.000000 0.926100
v 0.000000 0.000000 0.987771
v 0.123785 0.983238 -0.169088
v 0.796200 0.698100 0.000000
v 0.000000 0.000000 0.000000
v -0.834324 0.008880 0.749969
v 0.000000 0.796600 0.643800
v 0.000000 0.000000 0.000000
v 0.983238 -0.169088 -0.068212
v 0.591000 0.000000 0.727500
v 0.000000 0.000000 0.000000
v 0.008880 0.526884 -0.817050
v 0.796600 0.643800 0.000000
v 0.643800 0.000000 0.000000
v -0.817050 -0.234142 0.000033
v -0.029410 0.804800 0.593900
v 0.923500 0.573600 0.000000
v 0.000033 -0.999865 -0.016460
v -0.834324 0.008880 0.926100
v 0.000000 0.796600 0.643800
#63 V

#VT 0

vn -0.053150 0.938743 0.322727
vn 0.645600 0.633400 0.000000
vn 0.643800 0.000000 0.000000
vn -0.169088 -0.068212 0.938743
vn 0.120492 0.727500 0.643800
vn 0.724600 0.704000 0.000000
vn 0.589831 0.806882 -0.032271
vn 0.435769 -0.053150 0.571300
vn 0.000000 0.645600 0.633400
vn 0.000000 0.898488 0.435769
vn 0.938743 0.322727 0.120867
vn 0.688300 0.000000 0.643200
vn 0.000000 0.000000 0.579244
vn -0.033053 0.000000 0.998103
vn 0.478300 0.595900 0.000000
vn 0.000000 0.000000 0.000000
vn 0.806882 -0.032271 0.000000
vn 0.000000 0.571300 0.616400
vn 0.000000 0.000000 0.000000
vn 0.983238 -0.169088 -0.068212
vn 0.633400 0.000000 0.727500
vn 0.000000 0.000000 0.000000
vn -0.363047 0.794016 0.567870
vn 0.737600 0.591000 0.000000
vn 0.633400 0.000000 0.000000
vn 0.806882 -0.032271 0.898488
vn -0.216937 0.571300 0.616400
vn 0.644600 0.565300 0.000000
vn 0.794016 0.567870 -0.216937
vn 0.806882 -0.032271 0.644600
vn 0.000000 0.571300 0.616400
vn 0.000000 0.000000 0.999454
vn 0.410435 0.894939 -0.175004
vn 0.616400 0.000000 0.572800
vn 0.000000 0.000000 0.410435
vn -0.161861 0.000000 0.999454
vn 0.494800 0.496200 0.000000
vn 0.000000 0.000000 0.000000
vn -0.169088 -0.068212 0.749969
vn 0.000000 0.727500 0.643800
vn 0.000000 0.000000 0.000000
vn 0.000000 -0.985982 0.166850
vn 0.643800 0.000000 0.934800
vn 0.000000 0.000000 0.000000
vn 0.120492 0.749969 -0.649788
vn 0.724600 0.704000 0.000000
vn 0.643800 0.000000 0.000000
vn -0.985982 0.166850 0.551203
vn 0.123785 0.934800 0.678300
vn 0.796200 0.698100 0.000000
vn 0.931701 0.011372 -0.363047
vn -0.817050 -0.234142 0.737600
vn 0.000000 0.804800 0.593900
vn 0.000000 0.551203 -0.834324
vn 0.983238 -0.169088 -0.068212
vn 0.593900 0.000000 0.727500
vn 0.000000 0.000000 0.526884
vn -0.016460 0.000072 -0.999567
vn 0.926100 0.619400 0.000000
vn 0.000000 0.000000 0.000000
vn -0.817050 -0.234142 0.551203
vn 0.000000 0.804800 0.593900
vn 0.000000 0.000000 0.000000

#s QA
8��!׆��g2Vi|���*>_)K;!�?
usemtl modelx_auv1147

```
## Post #21
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-14T23:48:52+00:00
- Post Title: Re: RF Online Unknow rare model extracted

```
#
mtllib unused.mtl
g
v  1.236500 0.283200 12.570100
v  0.888800 0.304900 12.650300
v  1.071300 0.100000 12.384400
v  0.736800 -0.113300 12.423300
v  0.858300 -0.418800 12.140300
v  0.530800 -0.423700 12.258300
v  0.000000 -0.094500 12.665200
v  0.480600 0.011100 12.691700
v  0.314100 0.053200 12.954800
v  0.000000 -0.081600 12.910000
v  0.473900 0.373400 13.053800
v  0.624600 0.356700 12.819100
v  0.623400 0.727400 12.835200
v  0.423500 0.678100 13.078300
v  0.000000 -0.208300 12.390500
v  0.000000 -0.428100 12.274100
v  0.936900 0.716100 12.740400
v  1.267300 0.692200 12.664800
v  1.171600 0.069200 12.128100
v  1.135100 -0.332700 11.926400
v  1.152700 0.029700 11.825000
v  1.182200 -0.025900 11.527600
v  0.718500 0.946800 11.392700
v  1.036300 1.010400 12.074500
v  1.000600 0.681300 11.380600
v  0.778500 1.032800 12.044500
v  0.000000 1.048800 11.433000
v  0.000000 1.013800 12.170000
v  0.947400 0.890100 12.583000
v  0.459700 1.049900 12.348400
v  1.240600 0.932000 12.504000
v  0.000000 0.921600 12.680500
v  0.000000 0.855600 13.055700
v  1.136400 0.717200 11.748700
v  0.000000 -0.405900 12.192100
v  0.521200 -0.402700 12.176200
v  0.819200 -0.395000 12.045500
v  1.066000 -0.327000 11.859000
v  1.107400 -0.042500 11.484100
v  0.945300 0.622900 11.363400
v  0.692800 0.859600 11.366200
v  0.000000 0.953000 11.392500
v  0.360400 0.408600 13.044800
v  0.224400 0.135500 12.960200
v  0.000000 0.019400 12.939900
v  0.304700 0.651800 13.065600
v  0.000000 0.805500 13.072100
v  0.850300 -0.618500 11.802100
v  0.426700 -0.725000 11.932200
v  0.000000 -0.711100 11.796800
v  1.145100 0.487800 11.735300
v  1.127300 0.226500 11.316100
v  1.055600 0.196800 11.285500
v  -1.236500 0.283200 12.570100
v  -1.071300 0.100000 12.384400
v  -0.888800 0.304900 12.650300
v  -0.736800 -0.113300 12.423300
v  -0.858300 -0.418800 12.140300
v  -0.530800 -0.423700 12.258300
v  -0.314100 0.053200 12.954800
v  -0.480600 0.011100 12.691700
v  -0.473900 0.373400 13.053800
v  -0.623400 0.727400 12.835200
v  -0.624600 0.356700 12.819100
v  -0.423500 0.678100 13.078300
v  -0.936900 0.716100 12.740400
v  -1.267300 0.692200 12.664800
v  -1.171600 0.069200 12.128100
v  -1.135100 -0.332700 11.926400
v  -1.152700 0.029700 11.825000
v  -1.182200 -0.025900 11.527600
v  -0.718500 0.946800 11.392700
v  -1.000600 0.681300 11.380600
v  -1.036300 1.010400 12.074500
v  -0.778500 1.032800 12.044500
v  -0.947400 0.890100 12.583000
v  -0.459700 1.049900 12.348400
v  -1.240600 0.932000 12.504000
v  -1.136400 0.717200 11.748700
v  -0.521200 -0.402700 12.176200
v  -0.819200 -0.395000 12.045500
v  -1.066000 -0.327000 11.859000
v  -1.107400 -0.042500 11.484100
v  -0.945300 0.622900 11.363400
v  -0.692800 0.859600 11.366200
v  -0.224400 0.135500 12.960200
v  -0.360400 0.408600 13.044800
v  -0.304700 0.651800 13.065600
v  -0.850400 -0.618500 11.802100
v  -0.426700 -0.725000 11.932200
v  -1.145100 0.487800 11.735300
v  -1.127300 0.226500 11.316100
v  -1.055600 0.196800 11.285500
v  0.717900 -0.405800 10.275700
v  0.831600 -0.006100 10.268000
v  0.778000 -0.386000 10.641700
v  0.866600 0.010700 10.567900
v  0.479800 -0.709100 10.264500
v  0.588900 -0.749400 10.629300
v  0.000000 -0.882300 10.640700
v  0.000000 -0.859700 10.274300
v  0.951200 0.038300 9.996500
v  0.766500 -0.510600 9.918700
v  0.443100 -0.825600 9.819400
v  0.000000 -0.949700 9.725600
v  0.673300 0.328600 10.241700
v  0.701000 0.347400 10.514500
v  0.000000 0.466600 10.177000
v  0.000000 0.547500 10.512500
v  0.687800 0.395100 9.975400
v  0.000000 0.474200 9.918700
v  -0.718000 -0.405800 10.275700
v  -0.778000 -0.386000 10.641700
v  -0.831700 -0.006100 10.268000
v  -0.866600 0.010700 10.567900
v  -0.479800 -0.709100 10.264500
v  -0.588900 -0.749400 10.629300
v  -0.951200 0.038300 9.996500
v  -0.766500 -0.510600 9.918700
v  -0.443100 -0.825600 9.819400
v  -0.673300 0.328600 10.241700
v  -0.701000 0.347400 10.514500
v  -0.687800 0.395000 9.975400
v  0.854300 -0.397500 11.002700
v  0.866600 0.010700 10.567900
v  0.954700 0.076300 10.913000
v  0.778000 -0.386000 10.641700
v  0.989700 -0.375500 11.352100
v  1.055600 0.196800 11.285500
v  1.107400 -0.042500 11.484100
v  1.066000 -0.327000 11.859000
v  0.563200 -0.906800 11.685100
v  0.850300 -0.618500 11.802100
v  0.426700 -0.725000 11.932200
v  0.132100 -0.894100 11.549700
v  0.000000 -0.711100 11.796800
v  -0.132100 -0.894100 11.549700
v  0.000000 -0.861100 11.203500
v  0.588900 -0.749400 10.629300
v  0.610900 -0.767300 11.035000
v  0.000000 -0.882300 10.640700
v  0.263700 -0.851600 11.256400
v  0.601200 -0.937000 11.354700
v  0.852800 -0.776700 11.409500
v  0.771900 0.445500 10.841100
v  0.945300 0.622900 11.363400
v  0.701000 0.347400 10.514500
v  0.000000 0.547500 10.512500
v  0.692800 0.859600 11.366200
v  0.000000 0.666600 10.798700
v  0.000000 0.953000 11.392500
v  -0.854400 -0.397500 11.002700
v  -0.954800 0.076300 10.913000
v  -0.866600 0.010700 10.567900
v  -0.778000 -0.386000 10.641700
v  -0.989800 -0.375500 11.352100
v  -1.107400 -0.042500 11.484100
v  -1.055600 0.196800 11.285500
v  -1.066000 -0.327000 11.859000
v  -0.563200 -0.906800 11.685100
v  -0.426700 -0.725000 11.932200
v  -0.850400 -0.618500 11.802100
v  -0.588900 -0.749400 10.629300
v  -0.610900 -0.767300 11.035000
v  -0.263700 -0.851600 11.256400
v  -0.601200 -0.937000 11.354700
v  -0.852900 -0.776700 11.409500
v  -0.772000 0.445500 10.841100
v  -0.945300 0.622900 11.363400
v  -0.701000 0.347400 10.514500
v  -0.692800 0.859600 11.366200
v  1.236500 0.283200 12.570100
v  1.171600 0.069200 12.128100
v  1.442400 0.151000 12.348800
v  1.584700 0.053000 11.818500
v  1.152700 0.029700 11.825000
v  1.323700 0.265000 11.602900
v  1.788000 0.250900 11.980900
v  1.267300 0.692200 12.664800
v  1.847400 0.662500 12.018300
v  1.549900 0.654800 12.426600
v  1.136400 0.717200 11.748700
v  1.401000 0.939100 11.654400
v  1.250500 0.586600 11.536800
v  1.240600 0.932000 12.504000
v  1.482100 0.986800 12.137400
v  1.036300 1.010400 12.074500
v  1.664600 0.949400 11.864300
v  1.145100 0.487800 11.735300
v  -1.236500 0.283200 12.570100
v  -1.442500 0.151000 12.348800
v  -1.171600 0.069200 12.128100
v  -1.584700 0.053000 11.818500
v  -1.323700 0.265000 11.602900
v  -1.152700 0.029700 11.825000
v  -1.788000 0.250900 11.980900
v  -1.267300 0.692200 12.664800
v  -1.847400 0.662500 12.018300
v  -1.550000 0.654800 12.426600
v  -1.136400 0.717200 11.748700
v  -1.250500 0.586600 11.536800
v  -1.401000 0.939100 11.654400
v  -1.240600 0.932000 12.504000
v  -1.036300 1.010400 12.074500
v  -1.482200 0.986800 12.137400
v  -1.664600 0.949400 11.864300
v  -1.145100 0.487800 11.735300
v  -1.902700 -0.048600 11.415700
v  -1.788000 0.250900 11.980900
v  -2.197400 0.163100 11.649800
v  -1.584700 0.053000 11.818500
v  -1.562800 0.222700 11.134900
v  -1.323700 0.265000 11.602900
v  -1.847400 0.662500 12.018300
v  -2.266500 0.710500 11.694100
v  -1.681500 0.983600 11.214700
v  -1.250500 0.586600 11.536800
v  -1.477600 0.608700 11.057700
v  -1.401000 0.939100 11.654400
v  -2.109800 0.864800 11.271900
v  -2.268700 0.638200 11.405300
v  -2.005300 1.075700 11.474900
v  -1.901200 0.807000 11.104300
v  -1.664600 0.949400 11.864300
v  -1.791900 0.588500 11.020100
v  -1.837600 0.328800 11.062900
v  -2.045000 0.183100 11.233500
v  -2.222900 0.301100 11.375300
v  -1.748400 0.599200 10.956900
v  -2.041900 0.279500 10.743500
v  -1.996300 0.609300 10.695500
v  -1.802600 0.283500 11.011400
v  -2.063500 0.595900 10.729000
v  -2.099900 0.325600 10.764800
v  -2.057900 0.108400 11.216400
v  -2.285200 0.135100 10.937800
v  -2.281900 0.256900 11.398400
v  -2.495400 0.263500 11.109300
v  -2.336300 0.659300 11.435600
v  -2.552100 0.650600 11.148700
v  -1.880100 0.868200 11.063000
v  -2.103900 0.851500 10.782900
v  -2.365600 0.918400 10.992300
v  -2.139600 0.935700 11.270600
v  -2.295400 0.209200 10.924800
v  -2.461100 0.308500 11.057400
v  -2.508100 0.629700 11.088800
v  -2.358800 0.847200 10.963300
v  -2.150600 0.791100 10.796100
v  -2.530700 0.304100 10.122800
v  -2.384900 0.200600 10.814000
v  -2.777100 0.086700 10.325500
v  -2.186700 0.322500 10.650200
v  -3.530800 0.236200 9.331500
v  -3.400800 0.320800 9.224900
v  -2.152700 0.597800 10.616800
v  -2.501200 0.599900 10.091300
v  -2.606100 0.845500 10.170900
v  -2.237500 0.794100 10.681600
v  -3.405900 0.610200 9.224400
v  -2.559000 0.305400 10.952800
v  -3.036900 0.268100 10.532000
v  -2.603200 0.622000 10.981100
v  -3.052200 0.576600 10.537700
v  -3.717400 0.554900 9.477400
v  -3.680600 0.333300 9.451200
v  -2.449400 0.846800 10.851400
v  -2.845200 0.875000 10.363800
v  -3.592000 0.753900 9.372700
v  1.902700 -0.048600 11.415700
v  2.197400 0.163100 11.649800
v  1.788000 0.250900 11.980900
v  1.584700 0.053000 11.818500
v  1.562800 0.222700 11.134900
v  1.323700 0.265000 11.602900
v  2.266500 0.710500 11.694100
v  1.847400 0.662500 12.018300
v  1.681500 0.983600 11.214700
v  1.477600 0.608700 11.057700
v  1.250500 0.586600 11.536800
v  1.401000 0.939100 11.654400
v  2.268700 0.638200 11.405300
v  2.109800 0.864800 11.271900
v  2.005300 1.075700 11.474900
v  1.901200 0.807000 11.104300
v  1.664600 0.949400 11.864300
v  1.791900 0.588500 11.020100
v  1.837600 0.328800 11.062900
v  2.045000 0.183100 11.233500
v  2.222900 0.301100 11.375300
v  1.748400 0.599200 10.956900
v  1.996300 0.609300 10.695500
v  2.041900 0.279500 10.743500
v  1.802600 0.283500 11.011400
v  2.063500 0.595900 10.729000
v  2.099900 0.325600 10.764800
v  2.057900 0.108400 11.216400
v  2.285200 0.135100 10.937800
v  2.281900 0.256900 11.398400
v  2.495400 0.263500 11.109300
v  2.552100 0.650600 11.148700
v  2.336300 0.659300 11.435600
v  1.880100 0.868200 11.063000
v  2.103900 0.851500 10.782900
v  2.365600 0.918400 10.992300
v  2.139600 0.935700 11.270600
v  2.295400 0.209200 10.924800
v  2.461100 0.308500 11.057400
v  2.508100 0.629700 11.088800
v  2.358800 0.847200 10.963300
v  2.150600 0.791100 10.796100
v  2.530700 0.304100 10.122800
v  2.777100 0.086700 10.325500
v  2.384900 0.200600 10.814000
v  2.186700 0.322500 10.650200
v  3.530800 0.236200 9.331500
v  3.400800 0.320800 9.224900
v  2.152700 0.597800 10.616800
v  2.501200 0.599900 10.091300
v  2.237500 0.794100 10.681600
v  2.606100 0.845500 10.170900
v  3.405900 0.610200 9.224400
v  3.036900 0.268100 10.532000
v  2.559000 0.305400 10.952800
v  3.052200 0.576600 10.537700
v  2.603200 0.622000 10.981100
v  3.717400 0.554900 9.477400
v  3.680600 0.333300 9.451200
v  2.845200 0.875000 10.363800
v  2.449400 0.846800 10.851400
v  3.592000 0.753900 9.372700

vt  0.111100 0.125300 0.000000
vt  0.156300 0.187400 0.000000
vt  0.013400 0.130300 0.000000
vt  0.232800 0.204100 0.000000
vt  0.233300 0.349500 0.000000
vt  0.016200 0.175800 0.000000
vt  0.171900 0.106800 0.000000
vt  0.232800 0.204100 0.000000
vt  0.178900 0.381900 0.000000
vt  0.015300 0.228600 0.000000
vt  0.107900 0.339700 0.000000
vt  0.171900 0.106800 0.000000
vt  0.120200 0.389900 0.000000
vt  0.262100 0.252100 0.000000
vt  0.178900 0.381900 0.000000
vt  0.156300 0.187400 0.000000
vt  0.107000 0.245800 0.000000
vt  0.150700 0.310000 0.000000
vt  0.068100 0.289700 0.000000
vt  0.111100 0.125300 0.000000
vt  0.262100 0.252100 0.000000
vt  0.200700 0.275500 0.000000
vt  0.283000 0.321000 0.000000
vt  0.156300 0.187400 0.000000
vt  0.008300 0.272000 0.000000
vt  0.107900 0.339700 0.000000
vt  0.068100 0.289700 0.000000
vt  0.068100 0.289700 0.000000
vt  0.107900 0.339700 0.000000
vt  0.068100 0.289700 0.000000
vt  0.016200 0.175800 0.000000
vt  0.015300 0.228600 0.000000
vt  0.150700 0.310000 0.000000
vt  0.268600 0.158600 0.000000
vt  0.150700 0.310000 0.000000
vt  0.262100 0.252100 0.000000
vt  0.232800 0.204100 0.000000
vt  0.111100 0.125300 0.000000
vt  0.156300 0.187400 0.000000
vt  0.200700 0.275500 0.000000
vt  0.262100 0.252100 0.000000
vt  0.200700 0.275500 0.000000
vt  0.107000 0.245800 0.000000
vt  0.232800 0.204100 0.000000
vt  0.171900 0.106800 0.000000
vt  0.233300 0.349500 0.000000
vt  0.232800 0.204100 0.000000
vt  0.268600 0.158600 0.000000
vt  0.230800 0.082700 0.000000
vt  0.171900 0.106800 0.000000
vt  0.294100 0.104500 0.000000
vt  0.268600 0.158600 0.000000
vt  0.268600 0.158600 0.000000
vt  0.321900 0.474500 0.000000
vt  0.233300 0.349500 0.000000
vt  0.462500 0.530500 0.000000
vt  0.353700 0.433300 0.000000
vt  0.283000 0.321000 0.000000
vt  0.263800 0.382200 0.000000
vt  0.321900 0.474500 0.000000
vt  0.402000 0.567300 0.000000
vt  0.304600 0.658700 0.000000
vt  0.402000 0.567300 0.000000
vt  0.120200 0.389900 0.000000
vt  0.309300 0.358000 0.000000
vt  0.353700 0.433300 0.000000
vt  0.321900 0.474500 0.000000
vt  0.402000 0.567300 0.000000
vt  0.283000 0.321000 0.000000
vt  0.205400 0.565500 0.000000
vt  0.230800 0.082700 0.000000
vt  0.239200 0.481300 0.000000
vt  0.304600 0.658700 0.000000
vt  0.263800 0.382200 0.000000
vt  0.205400 0.565500 0.000000
vt  0.263800 0.382200 0.000000
vt  0.321900 0.474500 0.000000
vt  0.321900 0.474500 0.000000
vt  0.263800 0.382200 0.000000
vt  0.263800 0.382200 0.000000
vt  0.309300 0.358000 0.000000
vt  0.239200 0.481300 0.000000
vt  0.353700 0.433300 0.000000
vt  0.315800 0.052800 0.000000
vt  0.230800 0.082700 0.000000
vt  0.294100 0.104500 0.000000
vt  0.353700 0.433300 0.000000
vt  0.321900 0.474500 0.000000
vt  0.178900 0.381900 0.000000
vt  0.134300 0.502200 0.000000
vt  0.078200 0.461700 0.000000
vt  0.120200 0.389900 0.000000
vt  0.134300 0.502200 0.000000
vt  0.567100 0.688300 0.000000
vt  0.567100 0.688300 0.000000
vt  0.727500 0.643800 0.000000
vt  0.645600 0.633400 0.000000
vt  0.567100 0.688300 0.000000
vt  0.645600 0.633400 0.000000
vt  0.567100 0.688300 0.000000
vt  0.643200 0.704700 0.000000
vt  0.645600 0.633400 0.000000
vt  0.727500 0.643800 0.000000
vt  0.643200 0.704700 0.000000
vt  0.724600 0.704000 0.000000
vt  0.478300 0.595900 0.000000
vt  0.458200 0.659100 0.000000
vt  0.571300 0.616400 0.000000
vt  0.643200 0.704700 0.000000
vt  0.478300 0.595900 0.000000
vt  0.571300 0.616400 0.000000
vt  0.571300 0.616400 0.000000
vt  0.727500 0.643800 0.000000
vt  0.644600 0.565300 0.000000
vt  0.645600 0.633400 0.000000
vt  0.571300 0.616400 0.000000
vt  0.644600 0.565300 0.000000
vt  0.645600 0.633400 0.000000
vt  0.737600 0.591000 0.000000
vt  0.737600 0.591000 0.000000
vt  0.644600 0.565300 0.000000
vt  0.645600 0.633400 0.000000
vt  0.572800 0.530300 0.000000
vt  0.633800 0.773800 0.000000
vt  0.737100 0.848200 0.000000
vt  0.070900 0.859500 0.000000
vt  0.737100 0.848200 0.000000
vt  0.690400 0.883100 0.000000
vt  0.127400 0.897300 0.000000
vt  0.726900 0.774100 0.000000
vt  0.643200 0.704700 0.000000
vt  0.427500 0.762100 0.000000
vt  0.633400 0.844200 0.000000
vt  0.399200 0.877500 0.000000
vt  0.434000 0.832900 0.000000
vt  0.476000 0.910600 0.000000
vt  0.434000 0.832900 0.000000
vt  0.726900 0.774100 0.000000
vt  0.618800 0.940500 0.000000
vt  0.726900 0.774100 0.000000
vt  0.690400 0.883100 0.000000
vt  0.633400 0.844200 0.000000
vt  0.434000 0.832900 0.000000
vt  0.633800 0.773800 0.000000
vt  0.633400 0.844200 0.000000
vt  0.724600 0.704000 0.000000
vt  0.042100 0.904900 0.000000
vt  0.633400 0.844200 0.000000
vt  0.633800 0.773800 0.000000
vt  0.399200 0.877500 0.000000
vt  0.724600 0.704000 0.000000
vt  0.643200 0.704700 0.000000
vt  0.473000 0.785900 0.000000
vt  0.476000 0.910600 0.000000
vt  0.549500 0.761800 0.000000
vt  0.633800 0.773800 0.000000
vt  0.458200 0.659100 0.000000
vt  0.522600 0.817200 0.000000
vt  0.567100 0.688300 0.000000
vt  0.473000 0.785900 0.000000
vt  0.522600 0.817200 0.000000
vt  0.549500 0.761800 0.000000
vt  0.434000 0.832900 0.000000
vt  0.434000 0.832900 0.000000
vt  0.504800 0.865200 0.000000
vt  0.504800 0.865200 0.000000
vt  0.643200 0.704700 0.000000
vt  0.427500 0.762100 0.000000
vt  0.549500 0.761800 0.000000
vt  0.563000 0.837200 0.000000
vt  0.567100 0.688300 0.000000
vt  0.370200 0.135800 0.000000
vt  0.348300 0.062700 0.000000
vt  0.262100 0.252100 0.000000
vt  0.393800 0.195900 0.000000
vt  0.299100 0.216100 0.000000
vt  0.262100 0.252100 0.000000
vt  0.299100 0.216100 0.000000
vt  0.299100 0.216100 0.000000
vt  0.370200 0.135800 0.000000
vt  0.294100 0.104500 0.000000
vt  0.283000 0.321000 0.000000
vt  0.294100 0.104500 0.000000
vt  0.268600 0.158600 0.000000
vt  0.370200 0.135800 0.000000
vt  0.268600 0.158600 0.000000
vt  0.268600 0.158600 0.000000
vt  0.370200 0.135800 0.000000
vt  0.299100 0.216100 0.000000
vt  0.370200 0.135800 0.000000
vt  0.262100 0.252100 0.000000
vt  0.294100 0.104500 0.000000
vt  0.299100 0.216100 0.000000
vt  0.299100 0.216100 0.000000
vt  0.370200 0.135800 0.000000
vt  0.268600 0.158600 0.000000
vt  0.393800 0.195900 0.000000
vt  0.268600 0.158600 0.000000
vt  0.348300 0.062700 0.000000
vt  0.283000 0.321000 0.000000
vt  0.268600 0.158600 0.000000
vt  0.294100 0.104500 0.000000
vt  0.299100 0.216100 0.000000
vt  0.370200 0.135800 0.000000
vt  0.299100 0.216100 0.000000
vt  0.370200 0.135800 0.000000
vt  0.262100 0.252100 0.000000
vt  0.480100 0.163400 0.000000
vt  0.393800 0.195900 0.000000
vt  0.370200 0.135800 0.000000
vt  0.480100 0.163400 0.000000
vt  0.552100 0.375500 0.000000
vt  0.585000 0.449600 0.000000
vt  0.420700 0.270200 0.000000
vt  0.370200 0.135800 0.000000
vt  0.438500 0.018600 0.000000
vt  0.393800 0.195900 0.000000
vt  0.457200 0.105000 0.000000
vt  0.420700 0.270200 0.000000
vt  0.457200 0.105000 0.000000
vt  0.438500 0.018600 0.000000
vt  0.509100 0.243800 0.000000
vt  0.393800 0.195900 0.000000
vt  0.457200 0.105000 0.000000
vt  0.370200 0.135800 0.000000
vt  0.348300 0.062700 0.000000
vt  0.485000 0.475300 0.000000
vt  0.480100 0.163400 0.000000
vt  0.509100 0.243800 0.000000
vt  0.557400 0.225700 0.000000
vt  0.578800 0.294800 0.000000
vt  0.578800 0.294800 0.000000
vt  0.552100 0.375500 0.000000
vt  0.509100 0.243800 0.000000
vt  0.509100 0.243800 0.000000
vt  0.420700 0.270200 0.000000
vt  0.552100 0.375500 0.000000
vt  0.530600 0.315600 0.000000
vt  0.601600 0.352500 0.000000
vt  0.420700 0.270200 0.000000
vt  0.530600 0.315600 0.000000
vt  0.442000 0.338700 0.000000
vt  0.578800 0.294800 0.000000
vt  0.530600 0.315600 0.000000
vt  0.460200 0.402000 0.000000
vt  0.552100 0.375500 0.000000
vt  0.578800 0.294800 0.000000
vt  0.530600 0.315600 0.000000
vt  0.485000 0.475300 0.000000
vt  0.442000 0.338700 0.000000
vt  0.552100 0.375500 0.000000
vt  0.628700 0.401100 0.000000
vt  0.628700 0.401100 0.000000
vt  0.552100 0.375500 0.000000
vt  0.530600 0.315600 0.000000
vt  0.442000 0.338700 0.000000
vt  0.460200 0.402000 0.000000
vt  0.552100 0.375500 0.000000
vt  0.585000 0.449600 0.000000
vt  0.552100 0.375500 0.000000
vt  0.512600 0.092600 0.000000
vt  0.501400 0.027600 0.000000
vt  0.457200 0.105000 0.000000
vt  0.438500 0.018600 0.000000
vt  0.480100 0.163400 0.000000
vt  0.601600 0.352500 0.000000
vt  0.512600 0.092600 0.000000
vt  0.457200 0.105000 0.000000
vt  0.501400 0.027600 0.000000
vt  0.393800 0.195900 0.000000
vt  0.370200 0.135800 0.000000
vt  0.393800 0.195900 0.000000
vt  0.480100 0.163400 0.000000
vt  0.552100 0.375500 0.000000
vt  0.485000 0.475300 0.000000
vt  0.457200 0.105000 0.000000
vt  0.420700 0.270200 0.000000
vt  0.348300 0.062700 0.000000
vt  0.370200 0.135800 0.000000
vt  0.480100 0.163400 0.000000
vt  0.509100 0.243800 0.000000
vt  0.438500 0.018600 0.000000
vt  0.457200 0.105000 0.000000
vt  0.420700 0.270200 0.000000
vt  0.480100 0.163400 0.000000
vt  0.370200 0.135800 0.000000
vt  0.457200 0.105000 0.000000
vt  0.438500 0.018600 0.000000
vt  0.585000 0.449600 0.000000
vt  0.393800 0.195900 0.000000
vt  0.530600 0.315600 0.000000
vt  0.578800 0.294800 0.000000
vt  0.578800 0.294800 0.000000
vt  0.557400 0.225700 0.000000
vt  0.460200 0.402000 0.000000
vt  0.509100 0.243800 0.000000
vt  0.530600 0.315600 0.000000
vt  0.442000 0.338700 0.000000
vt  0.552100 0.375500 0.000000
vt  0.509100 0.243800 0.000000
vt  0.420700 0.270200 0.000000
vt  0.552100 0.375500 0.000000
vt  0.578800 0.294800 0.000000
vt  0.420700 0.270200 0.000000
vt  0.530600 0.315600 0.000000
vt  0.530600 0.315600 0.000000
vt  0.552100 0.375500 0.000000
vt  0.601600 0.352500 0.000000
vt  0.578800 0.294800 0.000000
vt  0.509100 0.243800 0.000000
vt  0.485000 0.475300 0.000000
vt  0.460200 0.402000 0.000000
vt  0.628700 0.401100 0.000000
vt  0.530600 0.315600 0.000000
vt  0.601600 0.352500 0.000000
vt  0.552100 0.375500 0.000000
vt  0.552100 0.375500 0.000000
vt  0.442000 0.338700 0.000000
vt  0.442000 0.338700 0.000000
vt  0.552100 0.375500 0.000000
vt  0.552100 0.375500 0.000000
vt  0.585000 0.449600 0.000000
vt  0.501400 0.027600 0.000000
vt  0.457200 0.105000 0.000000
vt  0.501400 0.027600 0.000000
vt  0.512600 0.092600 0.000000
vt  0.480100 0.163400 0.000000
vt  0.628700 0.401100 0.000000
vt  0.457200 0.105000 0.000000
vt  0.457200 0.105000 0.000000
vt  0.438500 0.018600 0.000000

vn  -0.286004 0.551335 -0.783729
vn  -0.362560 0.479003 -0.799441
vn  -0.478885 0.653851 -0.585789
vn  -0.293870 0.610655 -0.735351
vn  -0.368206 0.872554 -0.321050
vn  -0.054670 0.927640 -0.369452
vn  0.000000 0.969773 -0.244009
vn  -0.361750 0.747330 -0.557346
vn  -0.310708 0.600736 -0.736598
vn  -0.000000 0.767041 -0.641598
vn  -0.376582 0.197029 -0.905188
vn  -0.607948 0.310035 -0.730943
vn  -0.418498 -0.549455 -0.723159
vn  -0.231847 -0.355451 -0.905484
vn  0.000000 0.720356 -0.693604
vn  -0.000000 0.917317 -0.398159
vn  -0.301478 -0.099647 -0.948252
vn  -0.202393 -0.356200 -0.912227
vn  -0.806892 0.475509 -0.350452
vn  -0.719718 0.691581 0.061007
vn  -0.998760 0.016243 -0.047061
vn  -0.873106 0.361020 0.327644
vn  -0.235484 -0.669559 0.704442
vn  -0.319948 -0.943846 0.082389
vn  -0.523519 -0.414869 0.744185
vn  -0.077633 -0.996864 -0.015339
vn  0.000000 -0.803836 0.594851
vn  0.000000 -0.999109 -0.042199
vn  -0.121786 -0.843794 -0.522666
vn  -0.038695 -0.960263 -0.276400
vn  -0.031606 -0.829679 -0.557345
vn  0.000000 -0.949909 -0.312528
vn  0.000000 -0.477921 -0.878403
vn  -0.907085 -0.330104 0.261207
vn  -0.000000 0.966470 -0.256780
vn  -0.110963 0.952323 -0.284196
vn  -0.240444 0.962020 -0.129247
vn  -0.464788 0.866069 0.184111
vn  -0.499343 0.572371 0.650422
vn  -0.138738 -0.201616 0.969589
vn  -0.070427 -0.306221 0.949352
vn  0.000000 -0.389387 0.921074
vn  0.112905 0.142578 -0.983323
vn  0.110302 0.185247 -0.976482
vn  -0.000000 0.194991 -0.980805
vn  -0.001282 -0.040919 -0.999162
vn  0.000000 -0.311089 -0.950381
vn  -0.427981 0.626649 -0.651262
vn  -0.062798 0.694061 -0.717172
vn  0.000000 0.791536 -0.611123
vn  -0.997411 -0.065052 0.030638
vn  -0.822478 0.056877 0.565946
vn  -0.325636 0.023586 0.945201
vn  0.286004 0.551334 -0.783730
vn  0.478885 0.653851 -0.585789
vn  0.362560 0.479003 -0.799441
vn  0.293870 0.610655 -0.735351
vn  0.368206 0.872554 -0.321050
vn  0.054670 0.927640 -0.369452
vn  0.310708 0.600736 -0.736598
vn  0.361750 0.747330 -0.557346
vn  0.376582 0.197029 -0.905188
vn  0.418498 -0.549455 -0.723159
vn  0.607948 0.310035 -0.730943
vn  0.231847 -0.355451 -0.905484
vn  0.301478 -0.099647 -0.948252
vn  0.202393 -0.356200 -0.912227
vn  0.806892 0.475509 -0.350452
vn  0.719718 0.691581 0.061007
vn  0.998760 0.016243 -0.047061
vn  0.873106 0.361020 0.327643
vn  0.235484 -0.669559 0.704442
vn  0.523519 -0.414869 0.744185
vn  0.319948 -0.943846 0.082389
vn  0.077633 -0.996864 -0.015339
vn  0.121786 -0.843794 -0.522666
vn  0.038695 -0.960263 -0.276400
vn  0.031606 -0.829679 -0.557345
vn  0.907085 -0.330104 0.261207
vn  0.110954 0.952318 -0.284217
vn  0.240469 0.962007 -0.129292
vn  0.464817 0.866058 0.184087
vn  0.499343 0.572371 0.650422
vn  0.138738 -0.201616 0.969589
vn  0.070427 -0.306221 0.949352
vn  -0.110302 0.185247 -0.976482
vn  -0.112905 0.142578 -0.983323
vn  0.001282 -0.040919 -0.999162
vn  0.427979 0.626577 -0.651334
vn  0.062772 0.694057 -0.717178
vn  0.997411 -0.065052 0.030638
vn  0.822478 0.056877 0.565946
vn  0.325636 0.023586 0.945201
vn  -0.898511 0.435716 -0.053187
vn  -0.983257 -0.168989 -0.068178
vn  -0.938706 0.322734 0.121137
vn  -0.987737 -0.098890 0.120814
vn  -0.589892 0.806836 -0.032304
vn  -0.579276 0.795365 0.178418
vn  0.000000 0.998103 0.061564
vn  0.000000 0.999454 -0.033053
vn  -0.931595 0.011420 -0.363318
vn  -0.794019 0.567812 -0.217080
vn  -0.410436 0.894939 -0.175004
vn  0.270608 0.962678 0.004670
vn  -0.551279 -0.834275 0.008779
vn  -0.750021 -0.649707 0.123893
vn  0.000033 -0.999865 -0.016460
vn  0.000000 -0.985982 0.166850
vn  -0.526889 -0.816988 -0.234349
vn  -0.129889 0.476003 -0.869799
vn  0.898488 0.435769 -0.053150
vn  0.938743 0.322727 0.120867
vn  0.983238 -0.169088 -0.068212
vn  0.987771 -0.098945 0.120492
vn  0.589831 0.806882 -0.032271
vn  0.579244 0.795405 0.178347
vn  -0.359027 0.120610 -0.925501
vn  0.352969 0.360241 -0.863504
vn  0.456815 0.889057 0.029972
vn  0.551203 -0.834324 0.008880
vn  0.749969 -0.649788 0.123785
vn  -0.337272 0.358127 -0.870628
vn  -0.883782 0.365297 0.292382
vn  -0.987737 -0.098890 0.120814
vn  -0.956042 -0.022140 0.292392
vn  -0.938706 0.322734 0.121137
vn  -0.932660 0.255279 0.254908
vn  -0.325636 0.023586 0.945201
vn  -0.499343 0.572371 0.650422
vn  -0.464788 0.866069 0.184111
vn  -0.273425 0.886443 -0.373440
vn  -0.427981 0.626649 -0.651262
vn  -0.062798 0.694061 -0.717172
vn  0.218365 0.960444 -0.172811
vn  0.000000 0.791536 -0.611123
vn  -0.218365 0.960444 -0.172811
vn  0.000000 0.999454 -0.033053
vn  -0.579276 0.795365 0.178418
vn  -0.466619 0.846631 0.255896
vn  0.000000 0.998103 0.061564
vn  0.031135 0.963741 0.265017
vn  -0.163272 0.969081 0.185000
vn  -0.766145 0.636052 0.091971
vn  -0.660721 -0.628076 0.411057
vn  -0.138738 -0.201616 0.969589
vn  -0.750021 -0.649707 0.123893
vn  0.000000 -0.985982 0.166850
vn  -0.070427 -0.306221 0.949352
vn  -0.000010 -0.880856 0.473384
vn  0.000000 -0.389387 0.921074
vn  0.883714 0.365351 0.292519
vn  0.956036 -0.022170 0.292410
vn  0.987771 -0.098945 0.120492
vn  0.938743 0.322727 0.120867
vn  0.932716 0.255188 0.254794
vn  0.499343 0.572371 0.650422
vn  0.325636 0.023586 0.945201
vn  0.464817 0.866058 0.184087
vn  0.273340 0.886471 -0.373436
vn  0.062772 0.694057 -0.717178
vn  0.427979 0.626577 -0.651334
vn  0.579244 0.795405 0.178347
vn  0.466547 0.846658 0.255939
vn  -0.031135 0.963741 0.265017
vn  0.163202 0.969091 0.185008
vn  0.766105 0.636101 0.091975
vn  0.660719 -0.628071 0.411068
vn  0.138738 -0.201616 0.969589
vn  0.749969 -0.649788 0.123785
vn  0.070427 -0.306221 0.949352
vn  -0.286004 0.551335 -0.783729
vn  -0.806892 0.475509 -0.350452
vn  -0.489459 0.645569 -0.586234
vn  -0.209956 0.977383 0.025325
vn  -0.998760 0.016243 -0.047061
vn  0.300673 0.529948 0.792938
vn  -0.733200 0.428672 -0.527882
vn  -0.202393 -0.356200 -0.912227
vn  -0.770808 -0.370345 -0.518362
vn  -0.735907 -0.175024 -0.654070
vn  -0.907085 -0.330104 0.261207
vn  0.325354 -0.846513 0.421379
vn  0.779316 -0.017128 0.626397
vn  -0.031606 -0.829679 -0.557345
vn  -0.396695 -0.884247 -0.246454
vn  -0.319948 -0.943846 0.082389
vn  -0.403799 -0.903096 -0.146165
vn  -0.997411 -0.065052 0.030638
vn  0.286004 0.551334 -0.783730
vn  0.489439 0.645577 -0.586242
vn  0.806892 0.475509 -0.350452
vn  0.209966 0.977380 0.025357
vn  -0.300673 0.529948 0.792938
vn  0.998760 0.016243 -0.047061
vn  0.733285 0.428669 -0.527765
vn  0.202393 -0.356200 -0.912227
vn  0.770917 -0.370317 -0.518221
vn  0.735901 -0.175037 -0.654073
vn  0.907085 -0.330104 0.261207
vn  -0.779316 -0.017128 0.626397
vn  -0.325354 -0.846511 0.421384
vn  0.031606 -0.829679 -0.557345
vn  0.319948 -0.943846 0.082389
vn  0.396712 -0.884249 -0.246422
vn  0.403866 -0.903082 -0.146063
vn  0.997411 -0.065052 0.030638
vn  0.210616 0.955461 0.206726
vn  0.733285 0.428669 -0.527765
vn  0.783422 0.537686 -0.311681
vn  0.209966 0.977380 0.025357
vn  -0.506295 0.559756 0.656002
vn  -0.300673 0.529948 0.792938
vn  0.770917 -0.370317 -0.518221
vn  0.933855 -0.260863 -0.244673
vn  -0.232294 -0.795421 0.559772
vn  -0.779316 -0.017128 0.626397
vn  -0.566584 -0.148033 0.810598
vn  -0.325354 -0.846511 0.421384
vn  0.208042 -0.935312 -0.286198
vn  0.218167 -0.188493 -0.957535
vn  0.431167 -0.891417 -0.139534
vn  -0.703746 -0.683072 -0.195332
vn  0.403866 -0.903082 -0.146063
vn  -0.811688 -0.189270 0.552575
vn  -0.766653 0.608631 0.204479
vn  -0.131752 0.947172 -0.292417
vn  0.416092 0.485569 -0.768824
vn  -0.998537 -0.037931 0.038544
vn  -0.139571 0.490284 0.860315
vn  -0.145692 -0.213776 0.965957
vn  -0.866942 0.431009 -0.250285
vn  -0.210624 -0.021081 0.977340
vn  -0.014587 0.574656 0.818265
vn  -0.440579 0.785065 -0.435389
vn  0.480877 0.738577 0.472506
vn  0.058034 0.517418 -0.853763
vn  0.913000 0.390838 0.116953
vn  0.287637 -0.270112 -0.918861
vn  0.970879 -0.140027 0.194389
vn  -0.722443 -0.685701 -0.088825
vn  0.194090 -0.546996 0.814325
vn  0.587137 -0.758019 0.284038
vn  -0.339389 -0.643212 -0.686363
vn  0.495703 0.665868 0.557583
vn  0.866097 0.499370 -0.022485
vn  0.945482 -0.322029 0.048583
vn  0.611996 -0.621748 0.488764
vn  -0.052034 -0.663040 0.746774
vn  -0.630632 0.617448 0.470172
vn  -0.127089 0.991780 -0.014867
vn  0.010476 0.996621 -0.081466
vn  -0.697626 0.520628 0.492203
vn  0.046452 0.994263 0.096345
vn  -0.648583 0.387333 0.655220
vn  -0.797828 -0.217256 0.562379
vn  -0.750161 -0.139741 0.646321
vn  -0.466658 -0.786428 0.404674
vn  -0.423480 -0.867047 0.262479
vn  -0.579676 -0.480419 0.658160
vn  0.486605 0.666949 -0.564265
vn  0.680591 0.501072 -0.534530
vn  0.715504 -0.144835 -0.683431
vn  0.707343 -0.453936 -0.541856
vn  0.847285 -0.136495 -0.513301
vn  0.701567 0.601863 -0.381530
vn  0.291101 -0.919944 -0.262608
vn  0.195591 -0.968891 -0.151637
vn  0.300898 -0.951499 -0.064114
vn  -0.210616 0.955461 0.206726
vn  -0.783422 0.537686 -0.311681
vn  -0.733200 0.428672 -0.527882
vn  -0.209956 0.977383 0.025325
vn  0.506295 0.559756 0.656002
vn  0.300673 0.529948 0.792938
vn  -0.933855 -0.260863 -0.244673
vn  -0.770808 -0.370345 -0.518362
vn  0.232294 -0.795421 0.559772
vn  0.566584 -0.148033 0.810598
vn  0.779316 -0.017128 0.626397
vn  0.325354 -0.846513 0.421379
vn  -0.218167 -0.188493 -0.957535
vn  -0.208042 -0.935312 -0.286198
vn  -0.431167 -0.891417 -0.139534
vn  0.703746 -0.683072 -0.195331
vn  -0.403799 -0.903096 -0.146165
vn  0.811688 -0.189270 0.552575
vn  0.766653 0.608631 0.204480
vn  0.131752 0.947172 -0.292416
vn  -0.416091 0.485569 -0.768824
vn  0.998537 -0.037931 0.038544
vn  0.145692 -0.213776 0.965957
vn  0.139571 0.490284 0.860315
vn  0.866942 0.431009 -0.250285
vn  0.210624 -0.021081 0.977340
vn  0.014587 0.574656 0.818265
vn  0.440579 0.785065 -0.435389
vn  -0.480877 0.738577 0.472506
vn  -0.058034 0.517418 -0.853763
vn  -0.913000 0.390838 0.116953
vn  -0.970879 -0.140027 0.194389
vn  -0.287637 -0.270112 -0.918861
vn  0.722443 -0.685701 -0.088825
vn  -0.194090 -0.546996 0.814325
vn  -0.587137 -0.758019 0.284038
vn  0.339389 -0.643212 -0.686363
vn  -0.495703 0.665868 0.557583
vn  -0.866097 0.499370 -0.022485
vn  -0.945482 -0.322029 0.048583
vn  -0.611996 -0.621748 0.488764
vn  0.052034 -0.663040 0.746774
vn  0.630632 0.617448 0.470172
vn  -0.010476 0.996621 -0.081466
vn  0.127089 0.991780 -0.014867
vn  0.697626 0.520628 0.492203
vn  -0.046452 0.994263 0.096345
vn  0.648583 0.387333 0.655220
vn  0.797828 -0.217256 0.562379
vn  0.750161 -0.139741 0.646321
vn  0.423480 -0.867047 0.262479
vn  0.466658 -0.786428 0.404674
vn  0.579676 -0.480418 0.658160
vn  -0.680592 0.501072 -0.534530
vn  -0.486605 0.666949 -0.564265
vn  -0.707343 -0.453936 -0.541856
vn  -0.715504 -0.144835 -0.683430
vn  -0.847285 -0.136495 -0.513301
vn  -0.701567 0.601863 -0.381530
vn  -0.195591 -0.968891 -0.151637
vn  -0.291101 -0.919944 -0.262608
vn  -0.300898 -0.951499 -0.064114

g mesh0
usemtl BELFEMALE_ARMOR_UPPER_116.dds
f  1/1/1 2/2/2 3/3/3
f  3/3/3 2/2/2 4/4/4
f  5/5/5 3/3/3 4/4/4
f  4/4/4 6/6/6 5/5/5
f  7/7/7 8/8/8 9/9/9
f  9/9/9 10/10/10 7/7/7
f  11/11/11 12/12/12 13/13/13
f  13/13/13 14/14/14 11/11/11
f  9/9/9 8/8/8 12/12/12
f  12/12/12 11/11/11 9/9/9
f  15/15/15 16/16/16 6/6/6
f  4/4/4 15/15/15 6/6/6
f  17/17/17 1/1/1 18/18/18
f  2/2/2 1/1/1 17/17/17
f  3/3/3 19/19/19 1/1/1
f  3/3/3 5/5/5 19/19/19
f  19/19/19 5/5/5 20/20/20
f  21/21/21 19/19/19 20/20/20
f  22/22/22 21/21/21 20/20/20
f  23/23/23 24/24/24 25/25/25
f  26/26/26 24/24/24 23/23/23
f  27/27/27 28/28/28 26/26/26
f  23/23/23 27/27/27 26/26/26
f  24/24/24 26/26/26 29/29/29
f  29/29/29 17/17/17 18/18/18
f  29/29/29 26/26/26 30/30/30
f  26/26/26 28/28/28 30/30/30
f  29/29/29 18/18/18 31/31/31
f  29/29/29 31/31/31 24/24/24
f  14/14/14 13/13/13 32/32/32
f  32/32/32 33/33/33 14/14/14
f  25/25/25 24/24/24 34/34/34
f  35/35/35 36/36/36 6/6/6
f  6/6/6 16/16/16 35/35/35
f  36/36/36 37/37/37 5/5/5
f  5/5/5 6/6/6 36/36/36
f  37/37/37 38/38/38 20/20/20
f  20/20/20 5/5/5 37/37/37
f  38/38/38 39/39/39 22/22/22
f  22/22/22 20/20/20 38/38/38
f  40/40/40 41/41/41 23/23/23
f  23/23/23 25/25/25 40/40/40
f  41/41/41 42/42/42 27/27/27
f  27/27/27 23/23/23 41/41/41
f  15/15/15 4/4/4 8/8/8
f  8/8/8 7/7/7 15/15/15
f  13/13/13 12/12/12 17/17/17
f  2/2/2 17/17/17 12/12/12
f  8/8/8 4/4/4 2/2/2
f  2/2/2 12/12/12 8/8/8
f  13/13/13 17/17/17 29/29/29
f  13/13/13 29/29/29 30/30/30
f  30/30/30 32/32/32 13/13/13
f  32/32/32 30/30/30 28/28/28
f  11/11/11 43/43/43 44/44/44
f  44/44/44 9/9/9 11/11/11
f  9/9/9 44/44/44 45/45/45
f  45/45/45 10/10/10 9/9/9
f  14/14/14 46/46/46 43/43/43
f  43/43/43 11/11/11 14/14/14
f  33/33/33 47/47/47 46/46/46
f  46/46/46 14/14/14 33/33/33
f  36/36/36 48/48/48 37/37/37
f  49/49/49 48/48/48 36/36/36
f  35/35/35 50/50/50 49/49/49
f  37/37/37 48/48/48 38/38/38
f  36/36/36 35/35/35 49/49/49
f  22/22/22 51/51/51 21/21/21
f  51/51/51 22/22/22 52/52/52
f  52/52/52 34/34/34 51/51/51
f  52/52/52 25/25/25 34/34/34
f  39/39/39 53/53/53 52/52/52
f  52/52/52 22/22/22 39/39/39
f  53/53/53 40/40/40 25/25/25
f  25/25/25 52/52/52 53/53/53
f  54/54/54 55/55/55 56/56/56
f  55/55/55 57/57/57 56/56/56
f  58/58/58 57/57/57 55/55/55
f  57/57/57 58/58/58 59/59/59
f  7/7/7 60/60/60 61/61/61
f  60/60/60 7/7/7 10/10/10
f  62/62/62 63/63/63 64/64/64
f  63/63/63 62/62/62 65/65/65
f  60/60/60 64/64/64 61/61/61
f  64/64/64 60/60/60 62/62/62
f  15/15/15 59/59/59 16/16/16
f  57/57/57 59/59/59 15/15/15
f  66/66/66 67/67/67 54/54/54
f  56/56/56 66/66/66 54/54/54
f  55/55/55 54/54/54 68/68/68
f  55/55/55 68/68/68 58/58/58
f  68/68/68 69/69/69 58/58/58
f  70/70/70 69/69/69 68/68/68
f  71/71/71 69/69/69 70/70/70
f  72/72/72 73/73/73 74/74/74
f  75/75/75 72/72/72 74/74/74
f  27/27/27 75/75/75 28/28/28
f  72/72/72 75/75/75 27/27/27
f  74/74/74 76/76/76 75/75/75
f  76/76/76 67/67/67 66/66/66
f  76/76/76 77/77/77 75/75/75
f  75/75/75 77/77/77 28/28/28
f  76/76/76 78/78/78 67/67/67
f  76/76/76 74/74/74 78/78/78
f  65/65/65 32/32/32 63/63/63
f  32/32/32 65/65/65 33/33/33
f  73/73/73 79/79/79 74/74/74
f  35/35/35 59/59/59 80/80/80
f  59/59/59 35/35/35 16/16/16
f  80/80/80 58/58/58 81/81/81
f  58/58/58 80/80/80 59/59/59
f  81/81/81 69/69/69 82/82/82
f  69/69/69 81/81/81 58/58/58
f  82/82/82 71/71/71 83/83/83
f  71/71/71 82/82/82 69/69/69
f  84/84/84 72/72/72 85/85/85
f  72/72/72 84/84/84 73/73/73
f  85/85/85 27/27/27 42/42/42
f  27/27/27 85/85/85 72/72/72
f  15/15/15 61/61/61 57/57/57
f  61/61/61 15/15/15 7/7/7
f  64/64/64 63/63/63 66/66/66
f  66/66/66 56/56/56 64/64/64
f  61/61/61 56/56/56 57/57/57
f  56/56/56 61/61/61 64/64/64
f  63/63/63 76/76/76 66/66/66
f  63/63/63 77/77/77 76/76/76
f  77/77/77 63/63/63 32/32/32
f  32/32/32 28/28/28 77/77/77
f  62/62/62 86/86/86 87/87/87
f  86/86/86 62/62/62 60/60/60
f  60/60/60 45/45/45 86/86/86
f  45/45/45 60/60/60 10/10/10
f  65/65/65 87/87/87 88/88/88
f  87/87/87 65/65/65 62/62/62
f  33/33/33 88/88/88 47/47/47
f  88/88/88 33/33/33 65/65/65
f  80/80/80 81/81/81 89/89/89
f  90/90/90 80/80/80 89/89/89
f  35/35/35 90/90/90 50/50/50
f  81/81/81 82/82/82 89/89/89
f  80/80/80 90/90/90 35/35/35
f  71/71/71 70/70/70 91/91/91
f  91/91/91 92/92/92 71/71/71
f  92/92/92 91/91/91 79/79/79
f  92/92/92 79/79/79 73/73/73
f  83/83/83 92/92/92 93/93/93
f  92/92/92 83/83/83 71/71/71
f  93/93/93 73/73/73 84/84/84
f  73/73/73 93/93/93 92/92/92
f  94/94/94 95/95/95 96/96/96
f  95/95/95 97/97/97 96/96/96
f  98/98/98 94/94/94 99/99/99
f  94/94/94 96/96/96 99/99/99
f  99/99/99 100/100/100 101/101/101
f  99/99/99 101/101/101 98/98/98
f  94/94/94 102/102/102 95/95/95
f  102/102/102 94/94/94 103/103/103
f  98/98/98 103/103/103 94/94/94
f  103/103/103 98/98/98 104/104/104
f  101/101/101 104/104/104 98/98/98
f  104/104/104 101/101/101 105/105/105
f  106/106/106 107/107/107 95/95/95
f  106/106/106 108/108/108 109/109/109
f  97/97/97 95/95/95 107/107/107
f  109/109/109 107/107/107 106/106/106
f  102/102/102 110/110/110 95/95/95
f  106/106/106 95/95/95 110/110/110
f  110/110/110 111/111/111 108/108/108
f  108/108/108 106/106/106 110/110/110
f  112/112/112 113/113/113 114/114/114
f  114/114/114 113/113/113 115/115/115
f  116/116/116 117/117/117 112/112/112
f  112/112/112 117/117/117 113/113/113
f  117/117/117 101/101/101 100/100/100
f  117/117/117 116/116/116 101/101/101
f  112/112/112 114/114/114 118/118/118
f  118/118/118 119/119/119 112/112/112
f  116/116/116 112/112/112 119/119/119
f  119/119/119 120/120/120 116/116/116
f  101/101/101 116/116/116 120/120/120
f  120/120/120 105/105/105 101/101/101
f  121/121/121 114/114/114 122/122/122
f  121/121/121 109/109/109 108/108/108
f  115/115/115 122/122/122 114/114/114
f  109/109/109 121/121/121 122/122/122
f  118/118/118 114/114/114 123/123/123
f  121/121/121 123/123/123 114/114/114
f  123/123/123 108/108/108 111/111/111
f  108/108/108 123/123/123 121/121/121
f  124/124/124 125/125/125 126/126/126
f  127/127/127 125/125/125 124/124/124
f  128/128/128 129/129/129 130/130/130
f  128/128/128 124/124/124 126/126/126
f  128/128/128 126/126/126 129/129/129
f  130/130/130 131/131/131 128/128/128
f  132/132/132 133/133/133 134/134/134
f  135/135/135 134/134/134 136/136/136
f  137/137/137 138/138/138 136/136/136
f  139/139/139 140/140/140 141/141/141
f  139/139/139 127/127/127 140/140/140
f  124/124/124 140/140/140 127/127/127
f  135/135/135 132/132/132 134/134/134
f  135/135/135 138/138/138 142/142/142
f  143/143/143 144/144/144 132/132/132
f  143/143/143 135/135/135 142/142/142
f  140/140/140 144/144/144 143/143/143
f  131/131/131 144/144/144 128/128/128
f  124/124/124 144/144/144 140/140/140
f  124/124/124 128/128/128 144/144/144
f  143/143/143 132/132/132 135/135/135
f  144/144/144 133/133/133 132/132/132
f  131/131/131 133/133/133 144/144/144
f  142/142/142 140/140/140 143/143/143
f  140/140/140 138/138/138 141/141/141
f  140/140/140 142/142/142 138/138/138
f  125/125/125 145/145/145 126/126/126
f  145/145/145 146/146/146 129/129/129
f  125/125/125 147/147/147 145/145/145
f  129/129/129 126/126/126 145/145/145
f  145/145/145 147/147/147 148/148/148
f  146/146/146 145/145/145 149/149/149
f  149/149/149 145/145/145 150/150/150
f  149/149/149 150/150/150 151/151/151
f  150/150/150 145/145/145 148/148/148
f  152/152/152 153/153/153 154/154/154
f  155/155/155 152/152/152 154/154/154
f  156/156/156 157/157/157 158/158/158
f  156/156/156 153/153/153 152/152/152
f  156/156/156 158/158/158 153/153/153
f  157/157/157 156/156/156 159/159/159
f  160/160/160 161/161/161 162/162/162
f  137/137/137 136/136/136 161/161/161
f  138/138/138 135/135/135 136/136/136
f  163/163/163 141/141/141 164/164/164
f  163/163/163 164/164/164 155/155/155
f  152/152/152 155/155/155 164/164/164
f  137/137/137 161/161/161 160/160/160
f  137/137/137 165/165/165 138/138/138
f  166/166/166 160/160/160 167/167/167
f  166/166/166 165/165/165 137/137/137
f  164/164/164 166/166/166 167/167/167
f  159/159/159 156/156/156 167/167/167
f  152/152/152 164/164/164 167/167/167
f  152/152/152 167/167/167 156/156/156
f  166/166/166 137/137/137 160/160/160
f  167/167/167 160/160/160 162/162/162
f  159/159/159 167/167/167 162/162/162
f  165/165/165 166/166/166 164/164/164
f  164/164/164 141/141/141 138/138/138
f  164/164/164 138/138/138 165/165/165
f  154/154/154 153/153/153 168/168/168
f  168/168/168 158/158/158 169/169/169
f  154/154/154 168/168/168 170/170/170
f  158/158/158 168/168/168 153/153/153
f  168/168/168 148/148/148 170/170/170
f  169/169/169 171/171/171 168/168/168
f  171/171/171 150/150/150 168/168/168
f  171/171/171 151/151/151 150/150/150
f  150/150/150 148/148/148 168/168/168
f  172/172/172 173/173/173 174/174/174
f  175/175/175 176/176/176 177/177/177
f  175/175/175 178/178/178 174/174/174
f  176/176/176 175/175/175 173/173/173
f  173/173/173 175/175/175 174/174/174
f  179/179/179 172/172/172 174/174/174
f  180/180/180 181/181/181 178/178/178
f  174/174/174 178/178/178 181/181/181
f  181/181/181 179/179/179 174/174/174
f  182/182/182 183/183/183 184/184/184
f  179/179/179 181/181/181 185/185/185
f  185/185/185 186/186/186 187/187/187
f  186/186/186 180/180/180 188/188/188
f  186/186/186 183/183/183 187/187/187
f  180/180/180 186/186/186 181/181/181
f  186/186/186 185/185/185 181/181/181
f  183/183/183 186/186/186 188/188/188
f  187/187/187 183/183/183 182/182/182
f  177/177/177 176/176/176 184/184/184
f  189/189/189 184/184/184 176/176/176
f  184/184/184 189/189/189 182/182/182
f  190/190/190 191/191/191 192/192/192
f  193/193/193 194/194/194 195/195/195
f  193/193/193 191/191/191 196/196/196
f  195/195/195 192/192/192 193/193/193
f  192/192/192 191/191/191 193/193/193
f  197/197/197 191/191/191 190/190/190
f  198/198/198 196/196/196 199/199/199
f  191/191/191 199/199/199 196/196/196
f  199/199/199 191/191/191 197/197/197
f  200/200/200 201/201/201 202/202/202
f  197/197/197 203/203/203 199/199/199
f  203/203/203 204/204/204 205/205/205
f  205/205/205 206/206/206 198/198/198
f  205/205/205 204/204/204 202/202/202
f  198/198/198 199/199/199 205/205/205
f  205/205/205 199/199/199 203/203/203
f  202/202/202 206/206/206 205/205/205
f  204/204/204 200/200/200 202/202/202
f  194/194/194 201/201/201 195/195/195
f  207/207/207 195/195/195 201/201/201
f  201/201/201 200/200/200 207/207/207
f  208/208/208 209/209/209 210/210/210
f  209/209/209 208/208/208 211/211/211
f  212/212/212 211/211/211 208/208/208
f  211/211/211 212/212/212 213/213/213
f  210/210/210 214/214/214 215/215/215
f  214/214/214 210/210/210 209/209/209
f  216/216/216 217/217/217 218/218/218
f  217/217/217 216/216/216 219/219/219
f  215/215/215 220/220/220 221/221/221
f  220/220/220 215/215/215 222/222/222
f  220/220/220 216/216/216 223/223/223
f  216/216/216 220/220/220 222/222/222
f  222/222/222 214/214/214 224/224/224
f  214/214/214 222/222/222 215/215/215
f  216/216/216 224/224/224 219/219/219
f  224/224/224 216/216/216 222/222/222
f  225/225/225 216/216/216 218/218/218
f  216/216/216 225/225/225 223/223/223
f  208/208/208 226/226/226 212/212/212
f  226/226/226 208/208/208 227/227/227
f  210/210/210 227/227/227 208/208/208
f  227/227/227 210/210/210 228/228/228
f  215/215/215 228/228/228 210/210/210
f  228/228/228 215/215/215 221/221/221
f  229/229/229 230/230/230 231/231/231
f  230/230/230 229/229/229 232/232/232
f  233/233/233 230/230/230 234/234/234
f  230/230/230 233/233/233 231/231/231
f  226/226/226 229/229/229 225/225/225
f  229/229/229 226/226/226 232/232/232
f  235/235/235 230/230/230 232/232/232
f  230/230/230 235/235/235 236/236/236
f  237/237/237 236/236/236 235/235/235
f  236/236/236 237/237/237 238/238/238
f  238/238/238 239/239/239 240/240/240
f  239/239/239 238/238/238 237/237/237
f  231/231/231 241/241/241 229/229/229
f  241/241/241 231/231/231 242/242/242
f  239/239/239 243/243/243 240/240/240
f  243/243/243 239/239/239 244/244/244
f  243/243/243 241/241/241 242/242/242
f  241/241/241 243/243/243 244/244/244
f  234/234/234 236/236/236 245/245/245
f  236/236/236 234/234/234 230/230/230
f  245/245/245 238/238/238 246/246/246
f  238/238/238 245/245/245 236/236/236
f  246/246/246 240/240/240 247/247/247
f  240/240/240 246/246/246 238/238/238
f  247/247/247 243/243/243 248/248/248
f  243/243/243 247/247/247 240/240/240
f  248/248/248 242/242/242 249/249/249
f  242/242/242 248/248/248 243/243/243
f  249/249/249 231/231/231 233/233/233
f  231/231/231 249/249/249 242/242/242
f  225/225/225 241/241/241 223/223/223
f  241/241/241 225/225/225 229/229/229
f  223/223/223 244/244/244 220/220/220
f  244/244/244 223/223/223 241/241/241
f  220/220/220 239/239/239 221/221/221
f  239/239/239 220/220/220 244/244/244
f  221/221/221 237/237/237 228/228/228
f  237/237/237 221/221/221 239/239/239
f  228/228/228 235/235/235 227/227/227
f  235/235/235 228/228/228 237/237/237
f  227/227/227 232/232/232 226/226/226
f  232/232/232 227/227/227 235/235/235
f  225/225/225 212/212/212 226/226/226
f  212/212/212 225/225/225 218/218/218
f  212/212/212 217/217/217 213/213/213
f  217/217/217 212/212/212 218/218/218
f  250/250/250 251/251/251 252/252/252
f  251/251/251 250/250/250 253/253/253
f  254/254/254 250/250/250 252/252/252
f  250/250/250 254/254/254 255/255/255
f  251/251/251 234/234/234 245/245/245
f  234/234/234 251/251/251 253/253/253
f  250/250/250 256/256/256 253/253/253
f  256/256/256 250/250/250 257/257/257
f  256/256/256 258/258/258 259/259/259
f  258/258/258 256/256/256 257/257/257
f  260/260/260 257/257/257 255/255/255
f  257/257/257 260/260/260 258/258/258
f  250/250/250 255/255/255 257/257/257
f  253/253/253 233/233/233 234/234/234
f  233/233/233 253/253/253 256/256/256
f  256/256/256 249/249/249 233/233/233
f  249/249/249 256/256/256 259/259/259
f  252/252/252 261/261/261 262/262/262
f  261/261/261 252/252/252 251/251/251
f  262/262/262 263/263/263 264/264/264
f  263/263/263 262/262/262 261/261/261
f  265/265/265 262/262/262 264/264/264
f  262/262/262 265/265/265 266/266/266
f  254/254/254 262/262/262 266/266/266
f  262/262/262 254/254/254 252/252/252
f  246/246/246 251/251/251 245/245/245
f  251/251/251 246/246/246 261/261/261
f  263/263/263 246/246/246 247/247/247
f  246/246/246 263/263/263 261/261/261
f  264/264/264 267/267/267 268/268/268
f  267/267/267 264/264/264 263/263/263
f  268/268/268 259/259/259 258/258/258
f  259/259/259 268/268/268 267/267/267
f  264/264/264 269/269/269 265/265/265
f  269/269/269 264/264/264 268/268/268
f  258/258/258 269/269/269 268/268/268
f  269/269/269 258/258/258 260/260/260
f  267/267/267 247/247/247 248/248/248
f  247/247/247 267/267/267 263/263/263
f  249/249/249 267/267/267 248/248/248
f  267/267/267 249/249/249 259/259/259
f  270/270/270 271/271/271 272/272/272
f  272/272/272 273/273/273 270/270/270
f  274/274/274 270/270/270 273/273/273
f  273/273/273 275/275/275 274/274/274
f  271/271/271 276/276/276 277/277/277
f  277/277/277 272/272/272 271/271/271
f  278/278/278 279/279/279 280/280/280
f  280/280/280 281/281/281 278/278/278
f  276/276/276 282/282/282 283/283/283
f  283/283/283 284/284/284 276/276/276
f  283/283/283 285/285/285 278/278/278
f  278/278/278 284/284/284 283/283/283
f  284/284/284 286/286/286 277/277/277
f  277/277/277 276/276/276 284/284/284
f  278/278/278 281/281/281 286/286/286
f  286/286/286 284/284/284 278/278/278
f  287/287/287 279/279/279 278/278/278
f  278/278/278 285/285/285 287/287/287
f  270/270/270 274/274/274 288/288/288
f  288/288/288 289/289/289 270/270/270
f  271/271/271 270/270/270 289/289/289
f  289/289/289 290/290/290 271/271/271
f  276/276/276 271/271/271 290/290/290
f  290/290/290 282/282/282 276/276/276
f  291/291/291 292/292/292 293/293/293
f  293/293/293 294/294/294 291/291/291
f  295/295/295 296/296/296 293/293/293
f  293/293/293 292/292/292 295/295/295
f  288/288/288 287/287/287 291/291/291
f  291/291/291 294/294/294 288/288/288
f  297/297/297 294/294/294 293/293/293
f  293/293/293 298/298/298 297/297/297
f  299/299/299 297/297/297 298/298/298
f  298/298/298 300/300/300 299/299/299
f  300/300/300 301/301/301 302/302/302
f  302/302/302 299/299/299 300/300/300
f  292/292/292 291/291/291 303/303/303
f  303/303/303 304/304/304 292/292/292
f  302/302/302 301/301/301 305/305/305
f  305/305/305 306/306/306 302/302/302
f  305/305/305 304/304/304 303/303/303
f  303/303/303 306/306/306 305/305/305
f  296/296/296 307/307/307 298/298/298
f  298/298/298 293/293/293 296/296/296
f  307/307/307 308/308/308 300/300/300
f  300/300/300 298/298/298 307/307/307
f  308/308/308 309/309/309 301/301/301
f  301/301/301 300/300/300 308/308/308
f  309/309/309 310/310/310 305/305/305
f  305/305/305 301/301/301 309/309/309
f  310/310/310 311/311/311 304/304/304
f  304/304/304 305/305/305 310/310/310
f  311/311/311 295/295/295 292/292/292
f  292/292/292 304/304/304 311/311/311
f  287/287/287 285/285/285 303/303/303
f  303/303/303 291/291/291 287/287/287
f  285/285/285 283/283/283 306/306/306
f  306/306/306 303/303/303 285/285/285
f  283/283/283 282/282/282 302/302/302
f  302/302/302 306/306/306 283/283/283
f  282/282/282 290/290/290 299/299/299
f  299/299/299 302/302/302 282/282/282
f  290/290/290 289/289/289 297/297/297
f  297/297/297 299/299/299 290/290/290
f  289/289/289 288/288/288 294/294/294
f  294/294/294 297/297/297 289/289/289
f  287/287/287 288/288/288 274/274/274
f  274/274/274 279/279/279 287/287/287
f  274/274/274 275/275/275 280/280/280
f  280/280/280 279/279/279 274/274/274
f  312/312/312 313/313/313 314/314/314
f  314/314/314 315/315/315 312/312/312
f  316/316/316 313/313/313 312/312/312
f  312/312/312 317/317/317 316/316/316
f  314/314/314 307/307/307 296/296/296
f  296/296/296 315/315/315 314/314/314
f  312/312/312 315/315/315 318/318/318
f  318/318/318 319/319/319 312/312/312
f  318/318/318 320/320/320 321/321/321
f  321/321/321 319/319/319 318/318/318
f  322/322/322 317/317/317 319/319/319
f  319/319/319 321/321/321 322/322/322
f  312/312/312 319/319/319 317/317/317
f  315/315/315 296/296/296 295/295/295
f  295/295/295 318/318/318 315/315/315
f  318/318/318 295/295/295 311/311/311
f  311/311/311 320/320/320 318/318/318
f  313/313/313 323/323/323 324/324/324
f  324/324/324 314/314/314 313/313/313
f  323/323/323 325/325/325 326/326/326
f  326/326/326 324/324/324 323/323/323
f  327/327/327 325/325/325 323/323/323
f  323/323/323 328/328/328 327/327/327
f  316/316/316 328/328/328 323/323/323
f  323/323/323 313/313/313 316/316/316
f  308/308/308 307/307/307 314/314/314
f  314/314/314 324/324/324 308/308/308
f  326/326/326 309/309/309 308/308/308
f  308/308/308 324/324/324 326/326/326
f  325/325/325 329/329/329 330/330/330
f  330/330/330 326/326/326 325/325/325
f  329/329/329 321/321/321 320/320/320
f  320/320/320 330/330/330 329/329/329
f  325/325/325 327/327/327 331/331/331
f  331/331/331 329/329/329 325/325/325
f  321/321/321 329/329/329 331/331/331
f  331/331/331 322/322/322 321/321/321
f  330/330/330 310/310/310 309/309/309
f  309/309/309 326/326/326 330/330/330
f  311/311/311 310/310/310 330/330/330
f  330/330/330 320/320/320 311/311/311

g

```
[/code]
## Post #22
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-15T01:45:18+00:00
- Post Title: Re: RF Online Unknow rare model extracted

Thanks so much Critical, this already solve the problem of the Uv in the fixed meshes of Finale plugin   , one little question, its posible put the .msh original and the .obj from Nava tool in the same folder and then Noesis load the uvmap from the obj nava and atach this to the .msh Noesis load? 

OOO btw, i have this i forget tell before its the mshtoObj source code maybe this explain how the Uv map its parsed in .obj file.

[http://www.4shared.com/zip/BaYR8fFo/MshtoObjcode.html](http://www.4shared.com/zip/BaYR8fFo/MshtoObjcode.html)
## Post #23
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-15T07:07:54+00:00
- Post Title: Re: RF Online Unknow rare model extracted

I've updated the script with proper UV mapping. 

I finally decided to just go with one of the more inefficient solutions (I've been trying to avoid this for awhile but couldn't come up with anything)

1: read the vert coords and normals into separate lists
2: read the indices and UV's, into separate lists
3: build a new set of buffers using per-vertex UV's rather than per-face UV's. This involved duplicating a bunch of vertices in the process.
4: bind the new buffers.

The new index buffer is now basically [0, 1, 2, 3, 4, ..., n], where n is the total number of indices for that mesh.

You get a ton of duplicated vertices in the end, and I did a bunch of type conversion from bytes to float and then back to bytes (cause I quickly threw it together to see if it would work and didn't feel like doing any math to correctly splice into the byte array). I'll re-write a few things here and there to make it more efficient. But in the end it's still duplicating a bunch of vertices.

And then I copy pasted all-model loading into it.

The script is currently full of commented out code though, cause I wasn't sure if I'm going to go back and try something different in the future.



Since I'm hacking around with the format, maybe it will be a little more difficult to get bones in..................
## Post #24
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-15T07:29:35+00:00
- Post Title: Re: RF Online Unknow rare model extracted

Thanks so much Finale, btw tools to clean duplicated vertex or triangles exist in all good 3D programs. then its ok for me
## Post #25
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-15T07:34:49+00:00
- Post Title: Re: RF Online Unknow rare model extracted

I've never tried the dupe clean-up function that noesis provides.
Let's see what that does....
## Post #26
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-15T07:40:08+00:00
- Post Title: Re: RF Online Unknow rare model extracted

btw, i know something .msh load fine textures and this armor items are something dificulty to load textures, but why something .msh can be loaded and others not?... here a sample, one can loaded fine by noesis and the other cant be loaded.

[http://www.4shared.com/rar/jEGaX3JR/Meshes.html](http://www.4shared.com/rar/jEGaX3JR/Meshes.html)

UPDATED...

something its wrong with the new plugin
## Post #27
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-15T08:18:13+00:00
- Post Title: Re: RF Online Unknow rare model extracted

Thanks Critical by give a hand, but you lost in something point bro, the .obj exported with NAVA TOOL and the .obj Fixed by you are the same file.  
The object exported with Noesis its complete. Can be nice if u can take the uvmap info of the NAVA TOOL obj, and put this in the Exported witn Noesis.

*ARMOR_UPPER_116 UVMAPFINE (Exported with NAVA TOOL)
*ARMOR_UPPER_116out UVMAPWRONG (Exported with Noesis)
*ARMOR_UPPER_116out UVMAPFIX (Fixed by me)
-------------------------------------------------------------------------
Ok i changue the line 4 to from Sanae import SanaeObject and now works
but check this, OMG i know now why the nava plugin made this bonch of meshes.



Finale you have good inteligence and amazing skills, maybe this program NOESIS its limitated and this its the limit of the program can do.


 Its Mr. Adults coming?
## Post #28
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-15T13:45:56+00:00
- Post Title: Re: RF Online Unknow rare model extracted

Sanae3D isn't used in the latest script. I don't think you have the recent one.
## Post #29
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-15T15:57:36+00:00
- Post Title: Re: RF Online Unknow rare model extracted

ITS TRUEeeee, now works perfect, jajajaja. Finally a big stuff of good future space style thinks. Thank so much finale by not leave this project   , hope can check the weights in the future,   .
## Post #30
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2012-02-15T22:07:33+00:00
- Post Title: Re: RF Online Unknow rare model extracted

Found a old maxscript I wrote back on 2006. I can't believe I already have that kinds of standard in writing maxscript!
It opens RFS archive directly and double-click msh file to import mesh / export dds!

Please do not redistribute it anywhere else.
[RF_ripper.rar](https://xentaxbackup.github.io/file/5072_RF_ripper.rar)
## Post #31
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-15T23:13:16+00:00
- Post Title: Re: RF Online Unknow rare model extracted

Thanks duck, unfortunately does not support bones and weights.   Then its very closed to the one finale writhe for Noesis with the diference of the Noesis plugin come with texture preview  , but can be very nice if u can retouch this a little and add support for bones and weights.
## Post #32
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-03-05T05:35:11+00:00
- Post Title: Re: RF Online Unknow rare model extracted

> Reply from Rimbros
>
> Thanks duck, unfortunately does not support bones and weights.   Then its very closed to the one finale writhe for Noesis with the diference of the Noesis plugin come with texture preview  , but can be very nice if u can retouch this a little and add support for bones and weights.

I allready post this 20 days ago, hope somebody can keep out the bones and weights.
## Post #33
- Username: djmauro
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2008 9:49 pm
- Post datetime: 2012-11-16T20:51:27+00:00
- Post Title: Re: RF Online Unknow rare model extracted

Somewhat "dead" topic, but no reason to start a new one.

I looked into the old source code and located the c++ mesh definitions. Altho not 100% match (like  the first 2 blocks are 128 char instead of 100 bytes). But should provide info of what data types, format and where to find it

Header file with the structs. (_MESH line 263 and _OBJECT line 136)
To fix the broken comments, upload it as a txt to  [https://viewer.zoho.com/home.do](https://viewer.zoho.com/home.do)
then u can use g.translate on it.
[http://www.mediafire.com/?aiu0evaedua677z](http://www.mediafire.com/?aiu0evaedua677z)
## Post #34
- Username: djmauro
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2008 9:49 pm
- Post datetime: 2013-01-04T23:33:49+00:00
- Post Title: Re: RF Online Unknow rare model extracted

FULL EDIT... worked little on the mesh08:

```


struct mesh08
{
	
cstr [len=6] ID;
i16 numMesh;
child mshblock [count=numMesh];
}

struct mshblock
{
cstr [len=100] meshName;
cstr [len=100] boneName;

repeat 3
{
	//D3DXVECTOR4 x y z w
	float material_x;
	float material_y;
	float material_z;
	float material_w;
	
	float material_x;
	float material_y;
	float material_z;
	float material_w;
	
	float material_x;
	float material_y;
	float material_z;
	float material_w;
	
	float material_x;
	float material_y;
	float material_z;
	float material_w;
}
i16 unk1;
i16 faces;
i16 bones;
cstr [len=200] texName;
i32 x;
double x;
//i32 x;
double x;
//i32 x;
float x;
i32 x;
i32 x;
i32 x;
i32 x1;//looks like always 1
i32 somevalue;//changes when there is actual vert. data
i32 x2;//looks like always 1
i32 x;
i32 x;
i32 x;
i32 x;
i32 x;
i32 x;
i32 x;
i32 x;
i32 x;
i32 x;
i32 x;
i16 x;
i8 x;

i16 numVerts;
repeat numVerts //custom vertex format 
{
	//D3DXVECTOR4 x y z w
	float Vertex_x;
	float Vertex_y;
	float Vertex_z;
	float Vertex_w;
	//
	float normal_x;
	float normal_y;
	float normal_z;
	float normal_w;
	
	//uv map
	float tu1;//0.0f
	float tv1;//1.0f
	
	float tu2;//0.0f
	float tv2;//0.0f
	
	float tu3;//1.0f
	float tv3;//1.0f
	
	float tu4;//1.0f;
	float tv4;//0.0f
}

i16 numIdx;
repeat numIdx 
{
i16 idxBuff;
}
i16 numBones;

if (numBones > 0)
{
    repeat numBones
    {
	i32 val;
	cstr [len=100] meshName;
	cstr [len=300] unk7;
    }
   
}

}
```


The structorian strs.

just a few remaining unknown values i couldn't really make out yet.  It seems to be a multitexture (r uv-s  : diffuse, alpha, normal, spectacular).
unk5 is always 00 00 as far as i noticed.
There are some unknown values left. also - whats the actual material_x etc  for? looks like kind of bone related data? (not really sure ow bone weights etc are set in 3d files).
also the material part has the scale, position and angle info.
EDIT: updated the strs to match the rest of the mesh08 that has a kind of "bone" section.

Also, the reason many of the mesh08 wont load is the bone section and  when the  vertex value is 0 (particle/bone links or dummy) so the vertex and bugger values are 0, which breaks the script.

i don't know python. Could anyone update the script based off the info?
