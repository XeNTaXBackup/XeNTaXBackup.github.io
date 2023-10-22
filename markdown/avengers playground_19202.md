## Post #1
- Username: justshopatkmart43
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 06, 2012 2:57 pm
- Post datetime: 2018-12-17T10:06:58+00:00
- Post Title: avengers playground

Does anyone know which of these file types is the true model file?

I'm not sure if the models are in the .bin files, or the .lulmodel files 

Any help would be appreciated
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-12-17T12:30:36+00:00
- Post Title: avengers playground

yep the models are in the lullmodel files.  



metronome-ironman_lullmodel.PNG (110.54 KiB) Viewed 466 times



and you can convert all the ktx textures to png with PVRTexToolCLI and this bat file contents

```
for %%G in ("*.ktx") do PVRTexToolCLI -i "%%G" -o "%%~nG.dds" -d "%%~nG.png" -f r8g8b8a8
```
## Post #3
- Username: justshopatkmart43
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 06, 2012 2:57 pm
- Post datetime: 2018-12-17T12:49:41+00:00
- Post Title: avengers playground

> Reply from Acewell
>
> yep the models are in the lullmodel files.  
metronome-ironman_lullmodel.PNG

and you can convert all the ktx textures to png with PVRTexToolCLI and this bat file contents
Code: Select allfor %%G in ("*.ktx") do PVRTexToolCLI -i "%%G" -o "%%~nG.dds" -d "%%~nG.png" -f r8g8b8a8
Wow, thanks for the info on the textures. About the models, will they all work on those settings you have in the screenshot, or does it differ per model, I'm particularly interested in the hulk model?


edit:  I ran the bat file with the ktx file, the PVRTexToolCLI.exe in the same folder and it made a small png file with nothing in it, and a corrupt dds file. Did you try with these textures?
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-12-17T13:50:57+00:00
- Post Title: avengers playground

> Reply from Jaydenthetank
>
> About the models, will they all work on those settings you have in the screenshot, or does it differ per model, I'm particularly interested in the hulk model?
all settings are the same except the step 1 and 3 start addresses and counts.
different models rarely have identical number of vertices and faces.

> Reply from Jaydenthetank
>
> Did you try with these textures?
trick question? of course i did and they converted fine.
## Post #5
- Username: justshopatkmart43
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 06, 2012 2:57 pm
- Post datetime: 2018-12-17T14:03:42+00:00
- Post Title: avengers playground

> Reply from Acewell
>
> Jaydenthetank wrote:About the models, will they all work on those settings you have in the screenshot, or does it differ per model, I'm particularly interested in the hulk model?
all settings are the same except the step 1 and 3 start addresses and counts.
different models rarely have identical number of vertices and faces.
Jaydenthetank wrote:Did you try with these textures?
trick question? of course i did and they converted fine.
Not a trick question, are you able to send your .exe file, I tried one from github which is quite old, and 32/64 bit ones from the power vr kit. Does it need something installed to run correctly?
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-12-17T15:32:26+00:00
- Post Title: avengers playground

....
## Post #7
- Username: justshopatkmart43
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 06, 2012 2:57 pm
- Post datetime: 2018-12-17T23:50:33+00:00
- Post Title: avengers playground

> Reply from Acewell
>
> Jaydenthetank wrote:are you able to send your .exe file
Code: Select allhttps://www.mediafire.com/file/8lq6hc8b93jjwp3/PVRTexToolCLI.zip/fileCode: Select allPVRTexToolCL version 4.20
SDK Version: 18.1@5086772
PVRTexLib 4.20 | JpegLib version 8` | LibPNG version 1.5.12
Thanks I found the problem, I just needed to put everything in the same folder then it works without having to install anything. The model part is still tricky though, is there a tutorial you recommend to follow for hex2obj so I can extract the hulk model?
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-12-18T03:41:59+00:00
- Post Title: avengers playground

no tutorial is going to help you here, the info you need is acquired from recognizing patterns and some trial and error.
you can use the given iron man sample to see what you need to look for in the other lullmodel files.
## Post #9
- Username: justshopatkmart43
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 06, 2012 2:57 pm
- Post datetime: 2018-12-18T10:14:19+00:00
- Post Title: avengers playground

> Reply from Acewell
>
> no tutorial is going to help you here, the info you need is acquired from recognizing patterns and some trial and error.
you can use the given iron man sample to see what you need to look for in the other lullmodel files.
Thanks for the info, managed to get hulk based on what you had with iron man, but the others don't seem to be so easy. Does the pattern always have to start with 1 2 3 on the first line?
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-12-18T12:44:32+00:00
- Post Title: avengers playground

> Reply from Jaydenthetank
>
> Does the pattern always have to start with 1 2 3 on the first line?
not always, but in these samples it does.
okoye is the only character that uses dword indices instead of word.



metronome-okoye.lullmodel.PNG (69.14 KiB) Viewed 416 times
## Post #11
- Username: justshopatkmart43
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 06, 2012 2:57 pm
- Post datetime: 2018-12-18T13:29:26+00:00
- Post Title: avengers playground

> Reply from Acewell
>
> Jaydenthetank wrote:Does the pattern always have to start with 1 2 3 on the first line?
not always, but in these samples it does.
okoye is the only character that uses dword indices instead of word.
metronome-okoye.lullmodel.PNG

Managed to get nebula, I got the pattern on captain america to start with 123, and followed the same structure you used with iron man, and did the indices count calculation correct, but there is no mesh? I apologize for the questions, but this hex software is new to me so idk what I'm doing wrong. You have been a big help!
## Post #12
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-12-18T15:51:47+00:00
- Post Title: avengers playground

you almost had it, here is captain america settings 



metronome-captainamerica.lullmodel.PNG (76.85 KiB) Viewed 400 times
## Post #13
- Username: silkroad820420
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jan 22, 2019 7:52 pm
- Post datetime: 2019-01-26T04:23:53+00:00
- Post Title: avengers playground

> Reply from Acewell
>
> you almost had it, here is captain america settings 
metronome-captainamerica.lullmodel.PNG

hi,can you show the hulk settings? please
## Post #14
- Username: silkroad820420
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jan 22, 2019 7:52 pm
- Post datetime: 2019-01-26T04:53:42+00:00
- Post Title: avengers playground

> Reply from Acewell
>
> yep the models are in the lullmodel files.  
metronome-ironman_lullmodel.PNG

and you can convert all the ktx textures to png with PVRTexToolCLI and this bat file contents
Code: Select allfor %%G in ("*.ktx") do PVRTexToolCLI -i "%%G" -o "%%~nG.dds" -d "%%~nG.png" -f r8g8b8a8

how to use  this bat file ?

When I open .ktx files, PVRtextool seeing message: "Please check that astcenc.exe is in path" ,how to fix that?
## Post #15
- Username: justshopatkmart43
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 06, 2012 2:57 pm
- Post datetime: 2019-01-26T06:51:35+00:00
- Post Title: avengers playground

> Reply from silkroad820420
>
> Acewell wrote:yep the models are in the lullmodel files.  
metronome-ironman_lullmodel.PNG

and you can convert all the ktx textures to png with PVRTexToolCLI and this bat file contents
Code: Select allfor %%G in ("*.ktx") do PVRTexToolCLI -i "%%G" -o "%%~nG.dds" -d "%%~nG.png" -f r8g8b8a8

how to use  this bat file ?

When I open .ktx files, PVRtextool seeing message: "Please check that astcenc.exe is in path" ,how to fix that?

I gave the answer to that error in the thread
## Post #16
- Username: silkroad820420
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jan 22, 2019 7:52 pm
- Post datetime: 2019-01-26T14:56:00+00:00
- Post Title: Re: Avengers playground AR

> Reply from Jaydenthetank
>
> silkroad820420 wrote:Acewell wrote:yep the models are in the lullmodel files.  
metronome-ironman_lullmodel.PNG

and you can convert all the ktx textures to png with PVRTexToolCLI and this bat file contents
Code: Select allfor %%G in ("*.ktx") do PVRTexToolCLI -i "%%G" -o "%%~nG.dds" -d "%%~nG.png" -f r8g8b8a8

how to use  this bat file ?

When I open .ktx files, PVRtextool seeing message: "Please check that astcenc.exe is in path" ,how to fix that?

I gave the answer to that error in the thread

yes, I tried it ,and set astcenc.exe to environment PATH. but it still not working ,I don't know why

update：find the problem,already fixed that
## Post #17
- Username: PorkydaCorgi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Nov 11, 2014 10:44 am
- Post datetime: 2019-04-23T16:09:41+00:00
- Post Title: Re: Avengers playground AR

Hey, so I've been working to try and get all the models out of this since the recent update that added in End Game models too.
I'm a complete noob at Hex2Obj, but I've gotten the 3 shown previously out and Nebula, but I'm having trouble with others.

Black Widow in particular, I have her exported but her entire mesh is flat along one axis. Does anyone happen to know what could be causing that?



blackwidowparameters.png (14.29 KiB) Viewed 376 times


Her whole mesh seems to be there, just flattened.

Also is anyone interested in sharing the other meshes they've gotten out, or at least the hex numbers they used? Would be a great help!
## Post #18
- Username: justshopatkmart43
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 06, 2012 2:57 pm
- Post datetime: 2019-04-25T03:41:07+00:00
- Post Title: Re: Avengers playground AR

I ripped all the new ones, I'll pm you them. The meshes are not flat, you just wrote in the wrong numbers. Also I don't believe any of the designs are actually from endgame except captain marvel
## Post #19
- Username: Ar7579009
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Apr 28, 2019 10:28 pm
- Post datetime: 2019-04-28T14:40:24+00:00
- Post Title: Re: Avengers playground AR

> Reply from Acewell ↑Tue Dec 18, 2018 11:51 pm at Tue Dec 18, 2018 11:51 pm
>
> 
you almost had it, here is captain america settings  
metronome-captainamerica.lullmodel.PNG
Acewell 
Please share 3d models with me 
If not interested please describe me your whole process of extraction and ripping models
## Post #20
- Username: Ar7579009
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Apr 28, 2019 10:28 pm
- Post datetime: 2019-04-29T05:01:32+00:00
- Post Title: Re: Avengers playground AR

> Reply from Jaydenthetank ↑Thu Apr 25, 2019 11:41 am at Thu Apr 25, 2019 11:41 am
>
> 
I ripped all the new ones, I'll pm you them. The meshes are not flat, you just wrote in the wrong numbers. Also I don't believe any of the designs are actually from endgame except captain marvel

Please send me some of them model 
I am trying to extract them from some days but i can't understand the process or doesn't have requored tools 
Please send me some 3d model other wise tell me your whole process
## Post #21
- Username: PorkydaCorgi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Nov 11, 2014 10:44 am
- Post datetime: 2019-04-29T11:50:34+00:00
- Post Title: Re: Avengers playground AR

> Reply from Jaydenthetank ↑Thu Apr 25, 2019 11:41 am at Thu Apr 25, 2019 11:41 am
>
> 
I ripped all the new ones, I'll pm you them. The meshes are not flat, you just wrote in the wrong numbers. Also I don't believe any of the designs are actually from endgame except captain marvel
Yeah I'm aware they're not meant to be flat, like I said I got others out I've just been having trouble with getting the right numbers on the rest. If you could pm me them that would be very kind! I still haven't seen Endgame yet, but I think Black Widow's model is from it. Or at least the head, the outfit might just be from Infinity War.
## Post #22
- Username: Cyntharia
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 03, 2019 7:19 am
- Post datetime: 2019-05-02T23:25:07+00:00
- Post Title: Re: Avengers playground AR

Heyo ^^".
Would anyone here mind sending me some of the models and textures.
I don't really care which ones,but I'd love everything new or related to Guardians or Thor .
It would be really kind and make my week.
Thanks in advance and have a nice day everyone
## Post #23
- Username: MisterPrawn
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Jan 30, 2014 12:36 pm
- Post datetime: 2019-05-03T02:10:21+00:00
- Post Title: Re: Avengers playground AR

Has there been any updates to this, lately? I'm asking because I would like to rip models from the Detective Pikachu update that landed to the Android Playground today. I can provide samples, if needed.
## Post #24
- Username: SSingh511
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Sep 23, 2015 12:52 pm
- Post datetime: 2019-05-03T03:01:07+00:00
- Post Title: Re: Avengers playground AR

Is it possible to make a quickBMS script for this? It'll be really helpful especially for non humanoid characters like Rocket and Pokemon charactes from Detective Pikachu movie as they can't be rigged
## Post #25
- Username: justshopatkmart43
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 06, 2012 2:57 pm
- Post datetime: 2019-05-03T03:16:39+00:00
- Post Title: Re: Avengers playground AR

I don't think anyone will bother making a script for bones/weights/anim for an app that will likely be abandoned by google soon. Augmented reality apps don't last as it's more of a gimmick
## Post #26
- Username: SSingh511
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Sep 23, 2015 12:52 pm
- Post datetime: 2019-05-03T03:38:57+00:00
- Post Title: Re: Avengers playground AR

Models look well-detailed so worth a shot...  
Edit: For those having trouble with PVRTexToolCLI can directly use GUI... just download ascentc.exe from GitHub and place it in System32 folder...

@JayDenTheTank Can you help me regarding how to find face indices count and vertices start address.... I am trying to extract Captain Marvel's model and Detective Pikachu
## Post #27
- Username: justshopatkmart43
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 06, 2012 2:57 pm
- Post datetime: 2019-05-03T07:01:02+00:00
- Post Title: Re: Avengers playground AR

Here are all the pokemon models 'link removed'    I have already ripped the avengers ones but that was done on my pc which I am not near currently
## Post #28
- Username: Ar7579009
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Apr 28, 2019 10:28 pm
- Post datetime: 2019-05-03T18:23:22+00:00
- Post Title: Re: Avengers playground AR

> Reply from justshopatkmart43 ↑Fri May 03, 2019 11:16 am at Fri May 03, 2019 11:16 am
>
> 
I don't think anyone will bother making a script for bones/weights/anim for an app that will likely be abandoned by google soon. Augmented reality apps don't last as it's more of a gimmick

 I'm noob with Hex Editor 
I got some 3d Models from Marvel Avengers Playground AR Apk after Extraction.
i converted Iron man, captain america and okoye FROM .LULLMODEL to .OBJ by copying values provided by Acewell. in short i didn't worked in this process.
please someone help me in understanding Hex Software and process and how can I rip 3d models from .LULLMODEL using Hex editor and hex2obj.  
also post W.I.P. screnshots if it is possible especially when you find offsets, submeshes and uv offset
if someone is also interested in this topic contact these user they already did this:
[https://forum.xentax.com/memberlist.php](https://forum.xentax.com/memberlist.php) ... le&u=47635
[https://forum.xentax.com/memberlist.php](https://forum.xentax.com/memberlist.php) ... le&u=44234
[https://forum.xentax.com/memberlist.php](https://forum.xentax.com/memberlist.php) ... le&u=44234
here's .lullmodel [https://sta.sh/023dxt3eo9io](https://sta.sh/023dxt3eo9io)
I asked from playground developer according to them they're preparing to develop more ar games based on AlaDdin, Godzilla: king of monsters and Avatar 2
So, making script is'nt a bad option
## Post #29
- Username: G1fan
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jun 23, 2018 3:03 pm
- Post datetime: 2019-05-03T19:39:14+00:00
- Post Title: Re: Avengers playground AR

If someone could hit me up with the avengers models, or their values required by hex2obj that would be appreciated.
## Post #30
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-05-05T02:58:55+00:00
- Post Title: Re: Avengers playground AR

Here's the Noesis script I wrote 4 months ago and it still works well.
[fmt_AvengerAR_lullmodel_rpg.zip](https://xentaxbackup.github.io/file/16176_fmt_AvengerAR_lullmodel_rpg.zip)
## Post #31
- Username: RogerDelmar
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue May 14, 2019 3:49 pm
- Post datetime: 2019-05-14T10:56:01+00:00
- Post Title: Re: avengers playground

Hi. I have extracted the Detective Pikachu AR Stickers using the Nosis plugin above. However, I'm having issues putting the extracted png textures on the model. I'm using Blender and the texture is covering the whole model, not part of it like it's supposed to. Plus, it's multiple textures. If you all know of a solution to fix the texture issues, please let me know. Thank You.
## Post #32
- Username: justshopatkmart43
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 06, 2012 2:57 pm
- Post datetime: 2019-05-14T11:46:32+00:00
- Post Title: Re: avengers playground

Haven't tried the noesis script yet, but it could be flipped UV's
## Post #33
- Username: RogerDelmar
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue May 14, 2019 3:49 pm
- Post datetime: 2019-05-14T16:48:28+00:00
- Post Title: Re: avengers playground

> Reply from justshopatkmart43 ↑Tue May 14, 2019 7:46 pm at Tue May 14, 2019 7:46 pm
>
> 
Haven't tried the noesis script yet, but it could be flipped UV's

I'll see if that's the case. I'll re-export it to make sure. Thanks.
## Post #34
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-05-15T00:36:54+00:00
- Post Title: Re: avengers playground

> Reply from RogerDelmar ↑Tue May 14, 2019 6:56 pm at Tue May 14, 2019 6:56 pm
>
> the texture is covering the whole model, not part of it like it's supposed to.
Coz the models are loaded as single meshes whose polygons are broken into discrete faces, thanks to which you can quadify the models with any 3D apps:



bw.jpg (112.59 KiB) Viewed 139 times
## Post #35
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-05-15T00:41:44+00:00
- Post Title: Re: avengers playground

Use this script for loading as grouped meshes.
[fmt_AvengerAR_lullmodel_std.zip](https://xentaxbackup.github.io/file/16244_fmt_AvengerAR_lullmodel_std.zip)
## Post #36
- Username: justshopatkmart43
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 06, 2012 2:57 pm
- Post datetime: 2019-05-15T01:32:21+00:00
- Post Title: Re: avengers playground

> Reply from Bigchillghost ↑Wed May 15, 2019 8:36 am at Wed May 15, 2019 8:36 am
>
> 
RogerDelmar wrote: ↑Tue May 14, 2019 6:56 pmthe texture is covering the whole model, not part of it like it's supposed to.
Coz the models are loaded as single meshes whose polygons are broken into discrete faces, thanks to which you can quadify the models with any 3D apps:
bw.jpg
I have never had good quadify results but that looks super clean. What app did you use to do that?
## Post #37
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-05-15T01:48:05+00:00
- Post Title: Re: avengers playground

> Reply from justshopatkmart43 ↑Wed May 15, 2019 9:32 am at Wed May 15, 2019 9:32 am
>
> What app did you use to do that?
3Ds Max it is.
## Post #38
- Username: justshopatkmart43
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 06, 2012 2:57 pm
- Post datetime: 2019-05-16T11:59:32+00:00
- Post Title: Re: avengers playground

> Reply from Bigchillghost ↑Wed May 15, 2019 9:48 am at Wed May 15, 2019 9:48 am
>
> 
justshopatkmart43 wrote: ↑Wed May 15, 2019 9:32 amWhat app did you use to do that?

3Ds Max it is.
Which version, I'm using quite an old Max, so that's probably the problem
## Post #39
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-05-16T12:36:12+00:00
- Post Title: Re: avengers playground

You still don't get it. There's only one way to quadify these discrete faces, which has nothing to do with the algorithm or the version of the application. That means that any program abled to remove the shared edge of two adjacent triangles can do the job. Note that it works only for models containing at least 2 mesh groups.
## Post #40
- Username: RogerDelmar
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue May 14, 2019 3:49 pm
- Post datetime: 2019-05-16T17:39:23+00:00
- Post Title: Re: avengers playground

> Reply from Bigchillghost ↑Wed May 15, 2019 8:41 am at Wed May 15, 2019 8:41 am
>
> 
Use this script for loading as grouped meshes.

I'll test that out. Thank You so much!
## Post #41
- Username: RogerDelmar
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue May 14, 2019 3:49 pm
- Post datetime: 2019-05-16T17:40:33+00:00
- Post Title: Re: avengers playground

Oh, and for reference, I'm learning Blender.
## Post #42
- Username: Valamis
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Oct 25, 2018 7:18 am
- Post datetime: 2019-07-26T17:51:00+00:00
- Post Title: Re: avengers playground

Hi.
I have problem with Charizard lullmodel. When I preview it it has no textures. Also no textures after exporting model. I need help  
Also there is no material.
