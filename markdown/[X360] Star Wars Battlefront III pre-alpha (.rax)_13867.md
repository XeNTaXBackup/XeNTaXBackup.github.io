## Post #1
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-01-23T04:55:26+00:00
- Post Title: [X360] Star Wars Battlefront III pre-alpha (*.rax)

I'm trying to convert the rax models from this cancelled Free Radical game and i can get the geometry but i'm having trouble finding the UV data.
A plugin for Noesis, 3DOC or Unwrap3d would be best down the road but Hex2obj will do for now. 

This is my progress so far in Hex2obj


h2o file for this submesh

```
Vb1
16 99
0x600 3849
120400
0x0 255
```


Sample
*removed problem solved*

i thought at first this was using half float UVs with short all for which there is no switch in H2O or there was a UV block starting around 28e2e with a size of 10 but no dice. I can upload more samples if needed.
Any help here is appreciated.
## Post #2
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-01-23T05:50:11+00:00
- Post Title: [X360] Star Wars Battlefront III pre-alpha (*.rax)

Um the Uv maps could be stored in another file but i don't think it would be and after looking through the files it also looks like the bones for almost all of the characters are stored in their main OB.rax file as well.

Also it looks like you missed the hair as well in the file not sure if it's there or something they attach to the model via code but it doesn't look like it on the model

```
http://i284.photobucket.com/albums/ll18/DarthNihilus03/vlcsnap-2016-01-23-01h12m44s108_zpshqkzsfmk.png~original
```
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-01-23T14:33:43+00:00
- Post Title: [X360] Star Wars Battlefront III pre-alpha (*.rax)

The models aren't good for much without UVs and textures. i'll worry about the other submeshes in the file when i can get one completely working.

I think its worth mentioning that there are a lot of Havok engine source references in the xex file, so if anyone is familiar with meshes made for Havok your input is welcome too.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-23T17:12:18+00:00
- Post Title: [X360] Star Wars Battlefront III pre-alpha (*.rax)

At 0xF690 it looks like uvs; size UVB= 4, (WordUV for preview, SaveAs mesh: ShortALL):



ob_rax_uvs.jpg (160.69 KiB) Viewed 504 times



> Reply from AceWell
>
> i thought at first this was using half float UVs with short all for which there is no switch in H2O
One may think it's simple to add a combination such as verts shorts, uvs HF, but it would be more effort for me
than just saving the mesh in two ways: 1) Short_All 2) HF_all and then merge the two objs (as you know) since those formats are very rare, imho.

(But if you told/proved me this combination's some kind of "standard" for console games I'd think about it.  )
btw: there was a test version, iirc, where ShortAll was replaced by Short/HF or something like that.
(Is somewhere on my old PC.)
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-01-23T18:16:31+00:00
- Post Title: [X360] Star Wars Battlefront III pre-alpha (*.rax)

Awesome thanks!   
I can see where that UV block start address is possibly stored at 0x5b6
## Post #6
- Username: alvaropre
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 24, 2016 1:15 am
- Post datetime: 2016-01-23T19:24:52+00:00
- Post Title: [X360] Star Wars Battlefront III pre-alpha (*.rax)

I am trying to extract models out of the game but it seems I am not used to H2O yet. Analysing  the ob.rax posted above I see moreless where face indices and vertices start but with other models I tried I failed.

This is what I get from Grievous model.



I am almost sure that faces indices address starts at 24440 but I can't figure out where it ends.
Also I can't see a pattern regarding to vertices start.

Maybe someone in this forum can give some tips, I've already read the H2O tutorial and I am really interested in this game models extraction..
[ob.rar](https://xentaxbackup.github.io/file/10357_ob.rar)
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-01-23T20:02:15+00:00
- Post Title: [X360] Star Wars Battlefront III pre-alpha (*.rax)

GenGrievousSWBF3.png (40.26 KiB) Viewed 487 times



You were pretty close but this file has a different FVFsize and your vertice start address was off. 

h2o file

```
Vb1
24 99
0x2840 4935
120400
0x1F6F0 4

```


as for tips i can only speak from a non programmer point of view, this is what i posted in another thread
[viewtopic.php?p=113195#p113195](http://forum.xentax.com/viewtopic.php?p=113195#p113195)
## Post #8
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-01-25T04:02:20+00:00
- Post Title: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #9
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-01-26T08:21:50+00:00
- Post Title: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-01-26T19:37:20+00:00
- Post Title: [X360] Star Wars Battlefront III pre-alpha (*.rax)

i had to reduce the face count to 2256 to get a clean mesh preview



HansoloST.png (33.11 KiB) Viewed 426 times



first submesh h2o (lower body)

```
Vb1
24 99
0x3B80 671
120400
0x148F0 4

```


next submesh h2o (right arm)

```
Vb1
24 99
0x7A68 522
120400
0x1536C 4

```


I'm guessing 4 or 5 submeshes based on the number of texture call blocks at the start of the file.
The formats i have seen that store data like this usually have a table with offsets somewhere in the file.
## Post #11
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-01-26T19:57:43+00:00
- Post Title: [X360] Star Wars Battlefront III pre-alpha (*.rax)

This here is the reason we need a noesis script even if we don't have texture support yet cause having to get out the different submeshs than the UV maps as a different .obj is just to time consuming and annoying.
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-26T21:35:50+00:00
- Post Title: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from JakeGreen
>
> cause having to get out the different submeshs than the UV maps as a different .obj is just to time consuming and annoying.not more time consuming and annoying than performing a full format analysis - besides that you do the latter once for all models, admitted

But since I try it for one model only in most cases I prefer the quick 'n dirty method
## Post #13
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-01-27T01:59:18+00:00
- Post Title: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #14
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-01-27T07:51:47+00:00
- Post Title: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #15
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-01-27T08:00:51+00:00
- Post Title: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from Wobble
>
> Got it.
I didn't understand why the file was called hansolo_stormtrooper until now. 
solo.JPG

Yeah there is a challenge mission in the game to escape the death star and luke and han stay in their stormtrooper gear as they get to the falcon.

Any chance you could give a link to the model?
## Post #16
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-01-27T14:27:57+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #17
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-01-29T01:54:12+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #18
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-01-29T02:09:05+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from Wobble
>
> Does anyone know, are the models found here:
https://facepunch.com/showthread.php?t=1304034

and here:
https://facepunch.com/showthread.php?t=1339877

from the same SWBF3 Pre-alpha game?

If they were, I thought I might try to use the textures found there, and use them here, but models don't appear to be the same.
UV maps are not the same either.

I tried to compare models with roughly the same filename.  Didn't match up.

Yeah those models aren't from this build they are from a much later build after they changed a few of the models.
## Post #19
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-01-29T03:44:26+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #20
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-01-29T07:06:50+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from Wobble
>
> So, if you have to put a date on it, these pre-alpha files here are the oldest files?  Wikipedia says the SWBF3 game was cancelled in 2008.
But, all of these pak/str data files are dated 2012.

I'm not really sure about that it probably says 2012 on them cause that was when it was probably ripped onto someones pc from the pre-alpha disc, but the game was canceled like in the very first months of 2009 cause a build of it was made in November 2008.
## Post #21
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-01-29T19:33:21+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #22
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-01-29T23:36:34+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #23
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-05T04:31:42+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #24
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-02-05T04:35:04+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from Wobble
>
> Can't do much with textures, so I'm done.  UU3D downloads page has plugin for it.

Ah man i'm grateful you did this but damn i still hate that it's for this tool.
## Post #25
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-05T04:38:27+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #26
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-02-05T07:47:59+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

Alright so the plugin is great (if you're just wanting to view the models   ), i've tried it on the demo version of Unwrap 3d pro and so far every character but the clone pilot (rep_clonepilot) doesn't load but like you said above some have trig...ect errors all over the place and i seen that on a few characters like master ferroda,sith witch and ventress isn't even visible but loads into unwrap.

All in all this is really awesome and if someone can take the data from this and put it into a noesis plugin that would be amazing.

All of the models are by far in proper poly count to be used in SWBF2 so in a way they could recreate the game (somewhat) in there so problem.
## Post #27
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-02-08T01:21:51+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

These are the characters i saw with errors
maceWindu
leiapostepi6
masterferroda (both models)
shara
young_obi_wan
krayt
jawa
rep_clonepilot
snowtrooper
asajj_ventress
boba_fett
count_dooku
darth_vader
darthmaul
sith_witch
general_grievous

You'll need to use Hex2obj on those. I threw Maul in that list because it looks like part of his cloth is missing.
There is some good looking models in this game, i want those ship interiors the most though.  

edit
added General Greivous to the list
## Post #28
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-02-08T02:00:29+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from AceWell
>
> These are the characters i saw with errors
maceWindu
leiapostepi6
masterferroda (both models)
shara
young_obi_wan
krayt
jawa
rep_clonepilot
snowtrooper
asajj_ventress
boba_fett
count_dooku
darth_vader
darthmaul
sith_witch

You'll need to use Hex2obj on those. I threw Maul in that list because it looks like part of his cloth is missing.
There is some good looking models in this game, i want those ship interiors the most though.

Yeah those are the ones i've found along with many of the ships...ect having the same problem along with the Rep_Starfighter.

I'm finally getting Unwrap 3d tomorrow so i can view these models in 3ds max.

I have a feeling Wobble will fix this soon so we can get out all the meshes without them being deformed.

But like i said in my last post if the guys over at Gametoast got these models they could just about recreate the classes,ships,heroes in SWBF2 and since there is already a mod out there for space to ground it'd almost be complete.
## Post #29
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-11T20:33:07+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #30
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-02-11T21:52:33+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from Wobble
>
> The problem with some of these models, is that some of their vertex formats appear to be wrong. Vertex formats can be floats or packed words, and their type is indicated in a header.  But, the actual data might be the opposite, and that's where everything fails.  And there can be up to 5 different vertex buffers.  It's a mess.

btw, the rax plugin can load x2t textures now.

Okay so i'm not sure what's going on here but i select the texture folder and hit okay and nothing happens the program seems to lock up but you can still press okay or cancel but nothing, i have to crash it in task manager but if i don't select the texture folder and just leave it as is the models load but no textures.

EDIT: okay it seems that the SE version of UU3D doesn't work with the importing of the textures and locks up when you select the folder but if you use Ultimate Unwrap 3D Pro (x64) i used the demo version to test it an it works but for some reason on x2_texbone_cloth it only got out the normal maps and some hair texture and just about any other character just the normal map.

I own the SE version just so you know and hoping you can fix it.
## Post #31
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-12T09:30:40+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #32
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-02-12T10:10:12+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from Wobble
>
> The plugin can't do anything about x2t textures with zero headers.  It doesn't guess either.
So, if you want the plugin to load them, you'll have to use a hex editor and replace those zero values with something valid.

If the plugin crashes, uncheck the option "Convert textures to file".  If it doesn't crash, then it means the crash is related to converting textures.  

I've just added a guard to protect against non-zero bad headers.  This should prevent crashes from bad hex edits, where someone might change values that are bigger than the real image.

After you tried to download it again, and it still crashes, send a bug report.

No see the plugin works fine when it comes to the textures i'm kinda happy it's only getting out normal maps only and sometimes the diffuse, but my problem here is the plugin just completely refuses to work with the Ultimate Unwrap 3D SE (x86) when you select the assets\bf\tex_xb_v7\textures folder but if you have the location to stay as default like assets\bf\ob_xb_v184\characters\cutscene_models\x2_texbone_cloth the model loads just fine. here is a video of that.

Ultimate Unwrap 3D Pro (x64) Demo works 100% fine exporting and loading the textures when i select the assets\bf\tex_xb_v7\textures folder.

I was going to show there at the end the demo version of Ultimate Unwrap 3D Pro (x64) working just fine with the plugin but for some reason Action! was causing the view ports to freeze and become white,fraps was stupid and only was getting the UV map view port.
## Post #33
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2016-02-12T13:01:42+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

Jake, i confirm this ..
I have the SE version 32 bits ...
I must use the default folder or it crash if I select one
But even, many textures aren't load
The folder BG and Capital ships , most of meshes cannot be loaded or crash
## Post #34
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-02-12T14:50:20+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from JakeGreen
>
> ..my problem here is the plugin just completely refuses to work with the Ultimate Unwrap 3D SE (x86) when you select the assets\bf\tex_xb_v7\textures folder but if you have the location to stay as default like assets\bf\ob_xb_v184\characters\cutscene_models\x2_texbone_cloth the model loads just fine.
what version are you using? this works in my Ultimate Unwrap 3D SE (x86) 2.50.42 but i have not updated to 2.50.43 yet
## Post #35
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-12T15:39:32+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #36
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-02-12T17:17:54+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from Wobble
>
> I see the video.  You can take it down if you want.

I have never seen that problem before.  If the plugin did crash or freeze, I don't think you would be able to check those marks after clicking OK.  The dialog would be locked up.  So, that is odd behavior.

I have Win7 Pro 64-bit, and SE works ok here.
x2_texbone_cloth loads here ok, with normalmap textures.

I don't have Windows 8/8.1, so I can't test it there.
Tested it on Windows 10 64-bit, everything works as expected.

Download the rax plugin again, and try one more time.

Well i'm using windows 10 64bit and SE version 2.50.43, sadly i can't try 2.50.42 cause you can't download older versions. but i did redownload it and it still didn't work.

I hate to do it but i guess i can use the demo version of pro to get textures and than use my SE version to convert them models.
## Post #37
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-12T18:35:57+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #38
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-13T18:25:54+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #39
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2016-02-13T18:59:29+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from Wobble
>
> Haven't given up just yet.
tributary.JPG

nice , i'm looking for it !! the pluggin don't work really with this model ...
you have a new pluggin or find a new way ??
i cannot find associate textures
## Post #40
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-13T19:47:08+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #41
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-02-13T20:14:07+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from Wobble
>
> CZW wrote:
nice , i'm looking for it !! the pluggin don't work really with this model ...
you have a new pluggin or find a new way ??
i cannot find associate textures

I know, I haven't released it.  It's not completely finished.  Does the browsing texture folder work for you?  The last update should have fixed it.
Sadly no it doesn't work I even tried moving my folder out of my external hard drive and still nothing.
## Post #42
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2016-02-13T20:14:49+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from Wobble
>
> CZW wrote:
nice , i'm looking for it !! the pluggin don't work really with this model ...
you have a new pluggin or find a new way ??
i cannot find associate textures

I know, I haven't released it.  It's not completely finished.  Does the browsing texture folder work for you?  The last update should have fixed it.

i look every day, if the new pluggin change something ...
but no .. sadly


interior loading, crash the program  ...

and no texture load

i test on the Imp_escapepod , but no texture
Interdictor, it load only white textures, but nothing into the output folder

for the Nebulon, i load only 60% of texture
on Mon Cal, no texture load

W10 64 bits + UU3D SE v2.x

last time i have see this kind of failure, it come from symbols ... between . and , for separators ...
## Post #43
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-13T21:25:08+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #44
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-13T22:57:30+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #45
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-02-14T03:22:04+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from Wobble
>
> Round 2!
It's ready now.

maceWindu
leiapostepi6
masterferroda (both models)
shara
young_obi_wan
krayt
jawa
rep_clonepilot
snowtrooper
asajj_ventress
boba_fett
count_dooku
darth_vader
darthmaul
sith_witch
general_grievous


All fixed, except clonepilot.  It's somewhat different that all the others.  Another day.

Um shara isn't fixed she is still missing her body. but great job on getting these working.
## Post #46
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-14T09:10:30+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #47
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-02-14T09:21:00+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from Wobble
>
> JakeGreen wrote:
Um shara isn't fixed she is still missing her body. but great job on getting these working.

That's how it's suppose to be.  The other LODs are like this too.  

I don't know how SWBF3 uses Shara, but you probably only see her face in a hologram or communications message.

Nope this is how you see her ingame.
## Post #48
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-14T09:34:15+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #49
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-02-14T12:26:38+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

edit
all fixed

edit
regarding shara, the file size (135 KB) is consistent with those having a full body mesh
## Post #50
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-14T13:03:05+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #51
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-14T16:26:49+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #52
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2016-02-14T20:28:24+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

Where is this plugin. Is this a plugin for Ultimate Unwrap?
## Post #53
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-14T21:30:05+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #54
- Username: ginev
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Feb 15, 2016 6:53 pm
- Post datetime: 2016-02-17T00:51:47+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

When i open model in Unwrap 3d how i can save it let say to obj because i can't with the demo version.If there is other version for that,link it to me guys.
## Post #55
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-17T05:58:25+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #56
- Username: ginev
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Feb 15, 2016 6:53 pm
- Post datetime: 2016-02-17T11:03:15+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

Ohh no my dreams are crushed 

I can't make scripts on my own.My only hope is one day someone to make a script for Noesis.
For now i only going to watch the models in Unwrap 3d and to think for what i might use them in future...hopefully.
Thanks for the answer.
## Post #57
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-18T03:18:27+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #58
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-02-18T03:58:19+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from Wobble
>
> Rax plugin now loads havok.rax and novodex.rax files.  They are simple formats with straight vertex/trig lists.  No UVs or anything else interesting.  Both Havok and Novodek are physics APIs, btw, so I assume they don't need anything else.

Have you ever looked into the mesh not holding the skin modifier when exported like your SWBF 2015 script works with the bones rigged to the mesh but the SWBF3 one doesn't.
## Post #59
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-18T17:15:59+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #60
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-19T06:15:16+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #61
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2016-02-21T10:40:41+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

your last pluggin, is great !! more things can be loaded ... miss only ships interior and textures for ships ( nothing is load ) , station cannot be loaded
## Post #62
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-21T15:57:53+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #63
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-02-21T19:14:35+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from Wobble
>
> CZW wrote:your last pluggin, is great !! more things can be loaded ... miss only ships interior and textures for ships ( nothing is load ) , station cannot be loaded

I think the data in havok.rax and novodex.rax contain the same mesh data for interiors/backgrounds.
So, you can at least see what you're missing.

Also added a fix to include some missing vertex weights.

I know it may not be able to be done but there are still a few models that don't have a proper uv map a couple being the DH17 and the Munificent, Do you have any plans to try and fix that soon?
## Post #64
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-22T00:38:54+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #65
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-02-26T07:36:16+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from Wobble
>
> JakeGreen wrote:
I know it may not be able to be done but there are still a few models that don't have a proper uv map a couple being the DH17 and the Munificent, Do you have any plans to try and fix that soon?

Ok, I added a fix for these two models specifically.  The data that tells how these UVs are stored appear to be wrong.

Any chance you could look at the empire weapons cause it seem that almost all of them have uv problems.
## Post #66
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-28T23:35:19+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #67
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-02-28T23:38:56+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from Wobble
>
> Pick one specific model, and I'll take a look at it.  After that, I'm done.  Can't do anything more with this format.

Ah damn right well the E11, but you should really release your source so someone else can finished it cause getting out some of the maps and ship interiors would really help some peoples projects.
## Post #68
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-02-29T03:53:32+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #69
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-03-02T06:16:09+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

+1 for the shared source, you've done an awesome job ironing out this rax format and i know you said there was variations in some files but i'd like to see what format specs you have so far so we can continue the research. I think it could eventually lead to something that can import the bigger level files too.  

edit



rep_pilot.png (233.02 KiB) Viewed 310 times
## Post #70
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-03-02T20:32:58+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #71
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-21T07:09:26+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

since known format specs aren't being shared except for the vague table in Han's model on the first page i guess
we have to figure this out from the start if there is to be hope for extending support to the bigger rax models.   
i just don't know why anyone would keep game format specs to themselves on a game research forum   


*.rax format research reboot

I'm going to start with Han's stormtrooper model since there was nothing mentioned except this 
[viewtopic.php?p=115108#p115108](http://forum.xentax.com/viewtopic.php?p=115108#p115108)
I know this looks messy, so bear with me.   

big-endian
0x00 - 4bytes - stored start address of some unk table near the end of the file
0x10 - 4bytes - stored address that takes you 20 bytes after "deft"
0x28 - 4bytes - stored start address of where that first unk table data is
0x2c - 4bytes - stored start address of material data (0x60)
0x30 - 4bytes - number of materials (4) --each material block is 288 bytes

0x60 - start material data - 1st material
---- 0x60 4bytes - diffuse texture name
---- 0x70 4bytes - normal map texture name
---- 0x80 4bytes - specular texture name 
0x180 - 2nd material
0x2a0 - 3rd material
0x3c0 - 4th material

-loop through the 3 texture names in each material block (4)
you reached the end of material data when you see "deft" which i assume is the start of skeleton data.

i know nothing of the "deft" data so i skip it to a submesh info table starting at 0x2d00
116 byte stride, the last block in this table has 112 byte stride
loop through this table the same number of submeshes
i have yet to see anything that indicates how many submeshes there are
i guess you could just use the number of names as the variable here?

0x2c8c - technically the start of first block, but it is empty, so i will skip to next one ????
0x2d00 - first block - each block starts with 00 00 00 01 FF FF 
----0x2d06 - 2bytes - the number of bytes relative from the end of the table to read the string for submesh name 
----0x2d6c - 4bytes - offset to submesh info
0x2d74 - 2nd block
0x2de8 - 3rd block
0x2e5c - 4th block
0x2ed0 - 5th block
0x2f44 - 6th block 
0x2fb8 - 7th block
0x302c - 8th block
0x309c - ends table, names are relative to this address

0x30a3 - start array of submesh names (8 in total)

0x30e8 - first submesh info starts with "00 00 10 03"
----00 00 10 03 - 4bytes
----vertex count - 4bytes
----face indices count - 4bytes
----0x30fc - 4bytes - number of material groups indicated by "FACE"
----0x3108 - 4bytes - stored address of where "FACE_OPA" starts 
----0x310c - 4bytes - stored address of some unk
----0x3110 - 4bytes - stored address of where bounding box data is stored?
----0x3134 - 4bytes - stored address of where "POS" starts
------POS starts a 16 byte stride table, the last integer likely indicates where in the vertex stride certain data is stored for that submesh
----0x3148 - 4bytes - stored address of where "RGB" starts
----0x31d4 - 4bytes - stored address of where the first "FACE" starts
-----if more than one material is assigned to the submesh the stride will be 24 bytes untill the next one
----0x31e0 - start "FACE", first material group
------0x31f0 - relative offset of indices assigned to this submesh, indices start at 0x17600 in this model
------------0 for this integer because it starts with this submesh and only has 1 mat group, so it begins at 0x17600
0x3200 - next submesh 
0x3380 - next submesh
0x34a0 - next submesh
0x35c0 - next submesh
0x36e0 - next submesh
0x3800 - next submesh
0x3980 - last submesh, starts with "00 00 10 0B", i am unsure why this is different from the rest

some of thes block start with "00 00 10 0B" , "00 00 10 03" or "00 00 00 02", i bet this is significant in some way.


16 bytes after the last submesh "FACE" section is the start of more data

0x3b00 - 4bytes - unk
0x3b04 - 4bytes - unk
0x3b08 - 4bytes - offset to some unkown table near end of the file
0x3b0c - 4bytes - offset to end of UV data
0x3b10 - 4bytes - stored start address of face indices data block (0x175e0) indicated by "FACE"
-------- 20 bytes after that address (0x175f4) is the stored start address (0x17600) where word face indices actually start 
0x3b18 - 4bytes - stored start address of a table with 40 byte stride
----0x3b1c - 4bytes - stored address of where "POS" starts
----0x3b20 - 4bytes - stored start address of vertex block
----0x3b28 - 4bytes - vertex stride(?) (24) --if integer is 0 stride is usually 16
----0x3b30 - 4bytes - stored address of where "RGB" starts
----0x3b34 - 4bytes - stored start address of UV data

According to what we see in the Hex2obj image here
[viewtopic.php?p=115086#p115086](http://forum.xentax.com/viewtopic.php?p=115086#p115086)
The vertices are stored as shorts and the UVs are word with 4 byte stride per vertex


I attached the *.rax sample used for this outline if anyone else wants to have a look


 Han_stormtrooper.zip
(63.53 KiB) Downloaded 51 times



I'll post more as i figure it out   
If anyone else here can shed light on offsets/flags etc in this *.rax format feel free to jump in!
## Post #72
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-01-21T11:44:21+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #73
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-22T01:51:05+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from Wobble
>
> Because in the end, I was the only coder participating in this discussion.  Everyone else, except the end-users, lost interest.  If people want to discuss and exchange file format information on this forum, there has to be more than one coder participating in the discussion.
gameFormats != pentagonSecrets 

anyway i attached the han solo sample used for the outline in my previous post
for anyone else that want to have a look, if you need more just ask and i will provide
## Post #74
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-01-22T02:56:21+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #75
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-23T08:29:06+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

Don't worry i'm not asking for anything here, already did that last year and you responded, you don't have to explain your reasons for not sharing info. 

Now back to topic, i am going to look at a simple weapon with smaller file size next to take a break from
the hansolo model and i will attach the sample to this post and type out what i see in it later today maybe
## Post #76
- Username: Kiriller12
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Sep 07, 2016 8:57 pm
- Post datetime: 2017-03-05T14:36:20+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

So, can anyone say how to extract models from the game? Do I need to unpack smth?
## Post #77
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-03-05T18:18:01+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from AceWell
>
>  to take a break from the hansolo modelwhy? Han is good. Contains allmost everything we need:



rax.jpg (239.52 KiB) Viewed 122 times


I'm asking myself why you didn't create a Noesis script so far?

I'm about to create a Make_obj project (with 'C' source) for it which I was planning since a year now. ( But dunno if 'rax' is the very best start.)
Just trying to find  the best pattern for getting the start adresses (0x3B80, 0x148F0).

Here is the project to be found: [viewtopic.php?f=29&t=15955&p=128256&hil ... 2o#p128256](http://forum.xentax.com/viewtopic.php?f=29&t=15955&p=128256&hilit=make_h2o#p128256)

This is the result:
[](https://www.pic-upload.de/view-32802746/Han-startrooper.jpg.html)

cheers

well, Ace, I see you're going for patterns (00 00 10  03)
## Post #78
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-03-06T22:14:23+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from shakotay2
>
> I'm asking myself why you didn't create a Noesis script so far?
I could easily make one to open that Han model, but the rax format is inconsistent from one model to the next and it wouldn't work for many.
until now all research was done behind closed doors and compiled into a closed source plugin that no one is learning anything from.
hopefully this new open research will give a basic understanding of this format that can be extended to work with currently unsupported rax models.
## Post #79
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-03-06T22:36:59+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

well, as you may know I'm not a friend of a full format analysis because it's tedious, annoying, boring.

Any 3D model extracting project I started relies on pattern searches (which have some caveats, though).
And magic tables (with offsets and counts) some times.

For the rax format it might have different categories of models.

I could try to check different models from time to time - maybe there's some similarities in them that are not to obvious on a first glance.
## Post #80
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-03-06T23:04:10+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

thats fine, thanks for helping, there is however no pressure here for anyone to do anything, 
i will continue to contribute my findings here over time regardless.   
if you or anyone would like some unsupported samples to look at i will upload them  

i'm fairly certain there are different categories of these rax files from what i've seen.  


> Reply from Kiriller12
>
> So, can anyone say how to extract models from the game? Do I need to unpack smth?
use Quickbms and this script
[http://aluigi.altervista.org/bms/swbf3.bms](http://aluigi.altervista.org/bms/swbf3.bms)
## Post #81
- Username: Kiriller12
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Sep 07, 2016 8:57 pm
- Post datetime: 2017-03-07T14:46:00+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from AceWell
>
> 
use Quickbms and this script
http://aluigi.altervista.org/bms/swbf3.bms

Thanks, I already found it. Is there some plugin for 3d editing software, besides Ultimate Unwrap3D?
## Post #82
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-03-07T21:57:46+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from AceWell
>
> if you or anyone would like some unsupported samples to look at i will upload themas a second step I'd like to check a sample where you partially could extract some meshes from. (Checking models where you didn't get any meshes from would be a last step.)
## Post #83
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-03-07T22:52:42+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from Kiriller12
>
> Is there some plugin for 3d editing software, besides Ultimate Unwrap3D?
we're working on it   


> Reply from shakotay2
>
> I'd like to check a sample where you partially could extract some meshes from.
that could be difficult, because usually it either works or it doesn't, and its hard to say if something is incomplete unless its  obvious like a missing arm or head etc, 
and when i say unsupported i mean the U3D plugin will not open it or open it properly.
here is something that looks complete but the UVs are possibly destroyed  

```
http://www.mediafire.com/file/lao8a42l6ln1660/imp_interdictor_exterior.zip
```


edit
here is h2o file for first submesh with working UVs

```
Vb1
20 99
0x3600 17953
120300
0x5B0A4 20
```

the actual start address for the UV block is at 0x5b0a0 (this address is stored at 0x34f4 )
but you have to skip 4 bytes to display it properly in Hex2obj.
20 byte stride for the UVs, there must be flag that indicates this change.



edit again
h2o for 2nd submesh

```
Vb1
20 99
0xB2B40 212
120300
0xE3690 16
```

this submesh and the rest are clumped together unlike the first one, all the vertices and UVs run together.
the start address for the 2nd submesh vertex data is stored at 0x3508
the start address for the 2nd submesh UV data is stored at 0x351c
the UVs here have a 16 byte stride and are stored as floats instead of halffloats like the first submesh.

okay it looks like some of this stored data under the "POS" sections (0x3528 and 0x3598) is lining up with the change in stride from one submesh to another.
the first "UV2" 16 bytes of data has 0x14 staored at 0x3584
the second "UV2" 16 bytes of data has 0x10 stored at 0x35f4
still don't know how to tell whether the data is going to be floats or halffloats though.
## Post #84
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-03-08T06:50:09+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from AceWell
>
> here is something that looks completewell, I see, the pattern 00 00 10 xx is not valid here. So we've two categories of *.rax files (at least) where that pattern applies and where not?
(I'll care for ob.rax asap, will have to  include some debug lines into Make_obj.)
## Post #85
- Username: Kiriller12
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Sep 07, 2016 8:57 pm
- Post datetime: 2017-03-08T11:57:15+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from AceWell
>
> Kiriller12 wrote:Is there some plugin for 3d editing software, besides Ultimate Unwrap3D?
we're working on it

Good news
## Post #86
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-03-10T20:20:23+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from AceWell
>
> still don't know how to tell whether the data is going to be floats or halffloats though.should be solvable, atm I've this, some addresses set manually, though:



ob-rax.JPG (59.48 KiB) Viewed 63 times



Maybe someone could check the uvs for bogus?
[Makeobj_log ob uvs err.zip](http://www.uploadmb.com/dw.php?id=1489176856)
## Post #87
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-03-11T04:38:20+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

[out]
## Post #88
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-03-11T07:07:39+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from shakotay2
>
> Maybe someone could check the uvs for bogus?
awesome, the UVs are lining up with the textures so that's a good sign and now i think i know what 
all those "FACE" sections are for in the submesh data blocks, they might be material groups   

the first submesh has 7 of these
24byte stride * 7 here
0x8544 - 1st submesh 1st material group - at 0x8560 = 0x0
0x8568 - 1st submesh 2nd material group - at 0x8584 = 0x3c78
0x8592 - 1st submesh 3rd material group - at 0x8608 = 0xacf8
0x8616 - 1st submesh 4th material group - at 0x8632 = 0xd674
0x8640 - 1st submesh 5th material group - at 0x8656 = 0xd6b0
0x8664 - 1st submesh 6th material group - at 0x8680 = 0xecdc
0x8688 - 1st submesh 7th material group - at 0x8704 = 0xf678 

you can see the value increases after each one and could be indexing the indices length,
the 4byte integer at 0x1eb happens to store a 7 too which seems to indicate the
number of these "FACE" blocks and looks consistent with the other submesh data blocks.

also i think an identifier for different rax categories could be the letters that preceed "TOP",
for instance in the Han solo rax sample you had "CHRTOP" at 0x4c and in the ship sample
you have "BTOP" at 0x4c .
## Post #89
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-03-11T08:23:02+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

Hi Ace,
see you'll crack this format sooner or later!  
(addresses are decimal here: "8544 - 1st submesh 1st material group - at 8560")

I've checked all FACE entries:
# 0x0 0x3c78 0xacf8 0xd674 0xd6b0 0xecdc 0xf678
----------
# 0x10884
----------
# 0x10fbc
----------
# 0x11034 0x1193a 0x11946
----------
# 0x11e9e
----------
# 0x11f1c 0x171d8 0x17208 0x17358 0x1a5b0 0x1a9c4 0x1aac0
----------
# 0x1aaf0
----------
# 0x1adfc 0x1b86a
----------
# 0x1b876
----------
# 0x1b9f0 0x1c0d4
----------
# 0x1c14c
----------
# 0x1c170
----------
# 0x1c7e8
----------
# 0x0
----------

For the first submesh it's 0 15480 44280 54900 54960 60636 63096 (decimal), but the face indices count is 33858.
But they are modulo 4 so they might be face indices (0, 3870, 11070,.., 15744) ?
For submesh 6 it's # 73500 94680 94728 95064 107952 108996 109248 -> 18375..27312
so this should do the trick.

(As offsets (0x3C78 - 0xF678) the values are too small, imho, since the first submesh covers 0x3600-0x5B094.)

Introduced some new groups:
[Makeobj_ob-rax.zip](http://www.uploadmb.com/dw.php?id=1489222332)
Looks promissing, although I could see two one-face-only groups on a quick glance.



ob_rax-SM_0_0.JPG (90.14 KiB) Viewed 43 times


All thanks go to AceWell!
## Post #90
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-03-11T09:30:46+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

cool thanks shakotay!  

> Reply from shakotay2
>
> (As offsets (0x3C78 - 0xF678) the values are too small, imho, since the first submesh covers 0x3600-0x5B094.)
yeah i was just reading the values as they were stored in hexadecimal, i was thinking
those offsets were the position within the total face indices data size already known from 
face count read in before that, so 0x10A640 would be position 0x0 and the length of the 
first mat group would extend to 0x3c78 from 0x10A640

my theory for the last mat group
face indices (33858) * 2 = 67716 - 63096 (0xf678) = 4620 /2
so the last mat group would be assigned to the last 2310 faces out of the submesh total faces  


EDIT
the entire face buffer is 0x1c866 or 116838 bytes long
the buffer begins at 0x10a641, this is considered the starting point, or 0x0 for the material groups
it looks to me like the positions given for the "FACE" groups are the absolute values within the face buffer
even the last material group in the last submesh has the value 0x1c7e8 supports this theory

so for the last material group in the last submesh
0x1c866 - 0x1c7e8 = 0x7e (126)
126 / 2 = 63 

in theory the last material group in the last submesh is assigned to the last 63 faces indices in the buffer
this could be way off but it at first glance it makes sense to me and it seems to work with all the numbers given
## Post #91
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-03-11T09:45:56+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from AceWell
>
> 
face indices (33858) * 2 = 67716 - 63096 (0xf678) = 4620 /2
so the last mat group would be assigned to the last 2310 faces out of the submesh total facesFor the first submesh, yes, I'd say so.

(But I've made a stupid error with absolute/relative face indices, some + is required.
Submesh 6 should have 7 groups.)

well, it's not a simple '+', those crazy dev bastards might have used the same principles for building groups as the ones from FH3?
(Gosh, I really hope I don't have to work with median face indices and do a quicksorting which was a bad idea for early FH3 extractor versions.)

see this is so annoying:
f 2724/2724 2725/2725 2726/2726
f 2725/2725 2727/2727 2726/2726
f 742/742 744/744 743/743
f 741/741 742/742 743/743
f 743/743 752/752 741/741
f 750/750 741/741 752/752
f 750/750 752/752 751/751
f 749/749 750/750 751/751
f 745/745 746/746 747/747
f 748/748 747/747 746/746
f 747/747 748/748 741/741
f 750/750 747/747 741/741
f 2720/2720 2721/2721 2722/2722
f 2721/2721 2723/2723 2722/2722
f 2723/2723 2713/2713 2722/2722

Simple solutions looks good for some submesh but misses too many groups (reason see at end of post):



ob-rax-simple.JPG (97.17 KiB) Viewed 190 times

(seems I'll have to do a "per submesh" sorting at least)

edit: I did that sorting, it looked ok for the first submesh but not for the rest.

For the unsorted thingie it's weird:

There's this maximum faceindex, # 12. maxFI 27928 (might be wrong calculated, not sure)
and there's the values from the "FACE " tables:

# 27324
# ----------
# 27519 28186 < which don't make too much sense down from here
# ----------
# 28189
# ----------
# 28284 28725
# ----------
# 28755
# ----------
# 28764
# ----------
# 29178
# ----------
# 0
## Post #92
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2017-12-26T20:57:23+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

AceWell

have you find a way to read the UVmap from the Shipyard ? and the Tributary ? it don't work with Unwrap3D pluggin ...
regards
## Post #93
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-09T05:48:36+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from CZW
>
> have you find a way to read the UVmap from the Shipyard ? and the Tributary ? it don't work with Unwrap3D pluggin ...
no, not yet. i set this project aside for now, i will return to it some time this year though.
## Post #94
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2018-01-09T18:16:29+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from AceWell
>
> CZW wrote:have you find a way to read the UVmap from the Shipyard ? and the Tributary ? it don't work with Unwrap3D pluggin ...
no, not yet. i set this project aside for now, i will return to it some time this year though.

Dont worry
I know you are able to do it ^^
I have the time ...
Just I need finally to see fixed those models, inside and outside, with the right textures ..
Bump me when you can work on it .. thks
## Post #95
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2021-04-03T15:28:31+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

Acewell, have you find a way to export the Shipyard and the tributary, with interiors ??
regards

[https://drive.google.com/file/d/1y-CrhG ... sp=sharing](https://drive.google.com/file/d/1y-CrhGylUnXhaaRLVOY4e76pkFmv0LF2/view?usp=sharing)
## Post #96
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-04-05T14:09:31+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

uvs are hard to track, here's some of the easier ones:
.



tributary_exterior.png (27.99 KiB) Viewed 93 times
## Post #97
- Username: kboykboy
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jul 21, 2020 2:08 am
- Post datetime: 2021-04-05T23:20:43+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

hey, i am very new to reverse engineering (this is the first time i ever tried) i have been working on trying to make a blender plugin to import the maps, i was able to make a tool that can import most of Tatooine and some meshes of a couple other maps, but i ran into an issue, most of the models for maps seem to be stored different then the normal models, doing a short with a FVF size of 16 works for normal models (24 FVF size for skeletal meshes) and it works for some of the map models but most don't work, i cant figure out how those meshes are stored, i was hoping someone here would have some information about that, thanks xD
[tat2.jpeg](https://xentaxbackup.github.io/file/19852_tat2.jpeg)
## Post #98
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-04-06T06:11:41+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

Without a map sample no one can tell, I guess.
## Post #99
- Username: kboykboy
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jul 21, 2020 2:08 am
- Post datetime: 2021-04-06T07:53:03+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

my bad lol, here is Tatooine, Coruscant and Cato Neimoidia [https://www.mediafire.com/file/b1ick60l ... s.rar/file](https://www.mediafire.com/file/b1ick60liia0tbd/Samples.rar/file) Tatooine works for about 95% of the models, but Cato and Coruscant don't have any working models
## Post #100
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-04-06T15:52:55+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

yeah, it's a matter of finding the suiting face indices blocks:
.



Coruscant.png (255.22 KiB) Viewed 72 times
## Post #101
- Username: kboykboy
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jul 21, 2020 2:08 am
- Post datetime: 2021-04-06T19:17:08+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

Ayye you got it working, weird i cant even get the verts working, do you think you could show me how you have it set up in Hex2Obj? and thank you very much for your time.

the top was my attempt to get the verts from one of the coruscant meshes and the bottom i was trying Tatooine
[Untitled.jpeg](https://xentaxbackup.github.io/file/19860_Untitled.jpeg)
## Post #102
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-04-06T22:12:06+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

Here you go:
.



Coruscant_uvs.png (81.94 KiB) Viewed 67 times


(The uvs look a little bit strange - I tested a sub mesh, one of those center circle objects, and they looked ok to me.)
## Post #103
- Username: kboykboy
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jul 21, 2020 2:08 am
- Post datetime: 2021-04-06T23:03:50+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

Thank you so much, because of you i may actually get my plugin working so thank you again xD
## Post #104
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2021-06-18T14:01:40+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

hi

do you plan you share your plugin ?

regards
## Post #105
- Username: kboykboy
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jul 21, 2020 2:08 am
- Post datetime: 2021-06-24T20:17:54+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from CZW ↑Fri Jun 18, 2021 10:01 pm at Fri Jun 18, 2021 10:01 pm
>
> 
hi

do you plan you share your plugin ?

regards

most likely, I took a break from it for awhile but I should finish most of it soon, I for the most part got the meshes working, but now I need to set up material assigning and also find the positions of the models so they can be properly placed in the map
## Post #106
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2021-06-24T20:53:34+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

thx for your input

this plugin could work on all meshes or just on map ??
because, the archive than i have posted, cannot be imported by the old  plugin

regards
## Post #107
- Username: kboykboy
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jul 21, 2020 2:08 am
- Post datetime: 2021-06-25T03:56:54+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from CZW ↑Fri Jun 25, 2021 4:53 am at Fri Jun 25, 2021 4:53 am
>
> 
thx for your input

this plugin could work on all meshes or just on map ??
because, the archive than i have posted, cannot be imported by the old  plugin

regards

i hope to get it working for everything but the focus is the maps
## Post #108
- Username: benprice1995
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat May 25, 2019 7:37 am
- Post datetime: 2021-11-09T22:38:49+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

Hey any update on this please?
## Post #109
- Username: jdogs
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 17, 2022 12:40 pm
- Post datetime: 2022-02-17T05:46:31+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from benprice1995 ↑Wed Nov 10, 2021 6:38 am at Wed Nov 10, 2021 6:38 am
>
> 
Hey any update on this please?

Yes, here is a huge update. Someone (me) wrote a program that rips 98% of the map models from the game. Check out this video. Theres a link to the program that gets models out of the rax files. Watch through the video to understand how to get the models out of the game by hand. [https://youtu.be/7nr3qzDD1cY](https://youtu.be/7nr3qzDD1cY)
## Post #110
- Username: jdogs
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 17, 2022 12:40 pm
- Post datetime: 2022-02-23T07:05:55+00:00
- Post Title: Re: [X360] Star Wars Battlefront III pre-alpha (*.rax)

> Reply from kboykboy ↑Fri Jun 25, 2021 11:56 am at Fri Jun 25, 2021 11:56 am
>
> 
CZW wrote: ↑Fri Jun 25, 2021 4:53 am
thx for your input

this plugin could work on all meshes or just on map ??
because, the archive than i have posted, cannot be imported by the old  plugin

regards


i hope to get it working for everything but the focus is the maps

kboy, you still around? Would you be interested in finishing that plugin with me? I know all the information we need to get models. Its a matter of expanding on your code to do additional things like rip animations. Believe me, it can be done.
