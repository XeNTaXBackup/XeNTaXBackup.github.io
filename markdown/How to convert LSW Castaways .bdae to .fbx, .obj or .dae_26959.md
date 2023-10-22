## Post #1
- Username: holladolla12
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jul 07, 2023 8:06 pm
- Post datetime: 2023-07-08T17:37:16+00:00
- Post Title: How to convert LSW Castaways .bdae to .fbx, .obj or .dae

I have trouble finding a way converting these files from .bdae and .tx format to a more common format.
Can anyone help out?

Link to files: [https://mega.nz/folder/dxNzVJxR#w3wPY9IbqRbfJmfCWPdDQw](https://mega.nz/folder/dxNzVJxR#w3wPY9IbqRbfJmfCWPdDQw)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-07-08T20:25:11+00:00
- Post Title: How to convert LSW Castaways .bdae to .fbx, .obj or .dae

Please use forum  search! (click on up arrow:)

> Reply from reh ↑Sun Mar 22, 2020 1:27 pm at Sun Mar 22, 2020 1:27 pm
>
> 

Using hex2obj (view link in my sig) with .dat file:
.



helmets_CaptainRex-dat.png (71.05 KiB) Viewed 181 times
## Post #3
- Username: holladolla12
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jul 07, 2023 8:06 pm
- Post datetime: 2023-07-09T06:26:44+00:00
- Post Title: How to convert LSW Castaways .bdae to .fbx, .obj or .dae

I used this modified gcbf bms script and it made the .png files displayable, also the hex of the files appear to be much more coherent after extracting them through quickbms.

> Reply from Bigchillghost ↑Tue Feb 12, 2019 11:31 pm at Tue Feb 12, 2019 11:31 pm
>
> 
Or use this modified one:
gcbf_versus.zip
The .tx files seem to be just navigators for applying textures in the game (my guess).
The .bdae files now start with "BRES" in hex code, however the output doesn't seem to have changed when used with HextoObj.
Are the models really that janky or do I need to play around more with the settings of the program?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-07-09T10:27:00+00:00
- Post Title: How to convert LSW Castaways .bdae to .fbx, .obj or .dae

> Reply from holladolla12 ↑Sun Jul 09, 2023 2:26 pm at Sun Jul 09, 2023 2:26 pm
>
> The .bdae files now start with "BRES" in hex code, however the output doesn't seem to have changed when used with HextoObj.Did you get the same result for the helmet as in my previous post?

> Are the models really that janky or do I need to play around more with the settings of the program?Depends on. Each model needs its own parameters, of course.
## Post #5
- Username: holladolla12
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jul 07, 2023 8:06 pm
- Post datetime: 2023-07-09T10:58:04+00:00
- Post Title: How to convert LSW Castaways .bdae to .fbx, .obj or .dae

> Reply from shakotay2 ↑Sun Jul 09, 2023 6:27 pm at Sun Jul 09, 2023 6:27 pm
>
> 
Did you get the same result for the helmet as in my previous post?
I did yeah, although I was expecting a helmet, not a messy mesh lookalike...
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-07-09T13:52:37+00:00
- Post Title: How to convert LSW Castaways .bdae to .fbx, .obj or .dae

> Reply from holladolla12 ↑Sun Jul 09, 2023 6:58 pm at Sun Jul 09, 2023 6:58 pm
>
> I did yeah, although I was expecting a helmet, not a messy mesh lookalike...That's the result of my 15-minutes-check (as mostly always  ).

Maybe some parts are missing from bdae extraction or there's sub meshes to be re-arranged. I have no idea.
## Post #7
- Username: holladolla12
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jul 07, 2023 8:06 pm
- Post datetime: 2023-07-10T12:32:58+00:00
- Post Title: How to convert LSW Castaways .bdae to .fbx, .obj or .dae

> Reply from shakotay2 ↑Sun Jul 09, 2023 9:52 pm at Sun Jul 09, 2023 9:52 pm
>
> 
Maybe some parts are missing from bdae extraction or there's sub meshes to be re-arranged. I have no idea.

Could you tell me if there's a trick to determining what the start address and the count number is, I seem to have trouble getting it to work?   

> Reply from shakotay2 ↑Sun Jul 09, 2023 7:23 pm at Sun Jul 09, 2023 7:23 pm
>
> 
Usually I don't care for textures. Load it into irfanView for example, as a raw file 2048x1024, 8 BPB to see what it looks like.

What dimensions and what number of BPB should I use to get my .tx files to open? (Also asking how to know for different ones in the future  )
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-07-10T12:45:18+00:00
- Post Title: How to convert LSW Castaways .bdae to .fbx, .obj or .dae

> Reply from holladolla12 ↑Mon Jul 10, 2023 8:32 pm at Mon Jul 10, 2023 8:32 pm
>
> Could you tell me if there's a trick to determining what the start address and the count number is, I seem to have trouble getting it to work?There's no trick (except learning to read/understand hex data). There's dozens if not hundreds of posts (different formats) with hex screenshots which show where the counts are located; preceeding the vertex block in most cases or in magic tables. Search for the counts as hex values in files. Sometimes you'll need to search for blocksizes (= FVFsize x vertex_count).

> What dimensions and what number of BPB should I use to get my .tx files to open?Take square root of filesize to estimate dimensions (1024x1024 for an 1 MB file). If BPP8 doesn't show results try others.
## Post #9
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-07-13T13:25:19+00:00
- Post Title: How to convert LSW Castaways .bdae to .fbx, .obj or .dae

> Reply from shakotay2 ↑Sun Jul 09, 2023 4:25 am at Sun Jul 09, 2023 4:25 am
>
> 
Please use forum  search! (click on up arrow:)
after qbms



Itm_Helmets_captainRex_ucp.bdae.png (69.81 KiB) Viewed 83 times


*(I have already made several plugins for other .bdae , but this look even weirder )

i made plugin for Noesis, for "Star Wars Lego IOS" format: [*.bdae]
