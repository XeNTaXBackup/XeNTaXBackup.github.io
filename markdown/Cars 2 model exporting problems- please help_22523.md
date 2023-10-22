## Post #1
- Username: xpunkrockyugox
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Aug 11, 2020 7:55 am
- Post datetime: 2020-08-11T00:13:28+00:00
- Post Title: Cars 2 model exporting problems- please help

So as stated in the title, I've been trying to extract the character models from the Cars 2 game (version from Steam) to convert for SFM, Gmod and things like that. I've done something similar in the past where I used QuickBMS and NifSkope along with Blender to rip the stages from Wizard101 for use in MMD, but this is proving to be way, way harder than the Wizard101 stages thing. 
For starters, the character model and texture are in a .oct file. I followed the links for the programs from the Cars 2 game modding Wiki page ([https://modcars.fandom.com/wiki/Cars_2](https://modcars.fandom.com/wiki/Cars_2)), but unfortunately it's basically dead over there. Doing more research I found out that Disney Infinity character models are in the same format, so I used the Disney Infinity Model Extractor ([viewtopic.php?t=11187](https://forum.xentax.com/viewtopic.php?t=11187)) on the Axelrod.vbuf file like it said, and exported it as a .obj file. It wouldn't open in Blender, just giving me an error, and when I double clicked it the default 3D viewer thing showed me this crazy looking paperwad thing.
I'm super new to hacking/decoding and 3D modeling in general, so I'm super lost and would be extremely grateful if someone could help me figure out what's happening here and how I can get the model to open- without turning into a paperwad, that is- and save as a normal format. If needed I can provide a Google Drive link to the game folder in question or share more screenshots, just let me know any information that might be useful. Thanks!   
[Annotation 2020-08-09 222127.png](https://xentaxbackup.github.io/file/18583_Annotation 2020-08-09 222127.png)
## Post #2
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-08-11T04:32:08+00:00
- Post Title: Cars 2 model exporting problems- please help

It would be nice to have some sample files.
## Post #3
- Username: xpunkrockyugox
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Aug 11, 2020 7:55 am
- Post datetime: 2020-08-11T13:37:05+00:00
- Post Title: Cars 2 model exporting problems- please help

> Reply from reh ↑Tue Aug 11, 2020 12:32 pm at Tue Aug 11, 2020 12:32 pm
>
> 
It would be nice to have some sample files.

Absolutely, here's the zipped version of the original folder directly from the game: [https://drive.google.com/file/d/18vppy1 ... sp=sharing](https://drive.google.com/file/d/18vppy120s018MC_bDRDQqUhapP6N-yNs/view?usp=sharing)
And here's the folder with my attempts at conversion: [https://drive.google.com/file/d/13MPlV_ ... sp=sharing](https://drive.google.com/file/d/13MPlV__hDc--lDsa5lCFiTJJJPo3rZgs/view?usp=sharing)
The version of Blender I'm running is 2.83.4- the latest version as of when I downloaded it. 
Just let me know if you'd like any other files  
[Fail.png](https://xentaxbackup.github.io/file/18585_Fail.png)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-08-11T21:21:17+00:00
- Post Title: Cars 2 model exporting problems- please help

Format appears to be rather simple - only hurdle using hex2obj (view link in my sig) is the fact that vertices follow after uvs.

Load axelrod_0.bin into hex2obj.
Then you've to modify the flat "mesh" .obj created using axelrod_0_uv.h2o by replacing "v " by "vt " lines and copy/paste them into the obj created using axelrod_0_mesh.h2o. (Be sure to have 
g submesh_0
f 1/1 2/2 3/3 
f 3/3 2/2 4/4 
f 2/2 9/9 4/4 
f 4/4 9/9 10/10 
f 9/9 11/11 10/10 
...
in that obj.)


 axelrod_0_0.zip
(220.46 KiB) Downloaded 18 times

(In case you fail just use the contained obj file.  )
## Post #5
- Username: xpunkrockyugox
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Aug 11, 2020 7:55 am
- Post datetime: 2020-08-12T16:48:59+00:00
- Post Title: Cars 2 model exporting problems- please help

Thank you so much!! I do have a few problems though...
- I don't really understand the thing with the numbers and .bins, I'm not very tech savvy when it comes to this kind of behind the scenes stuff >.< So I have to convert the .oct to a .bin somehow then open it in this Hex2OBJ program and plug in those numbers, if I'm understanding you correctly?
- The link to the program wasn't working, it just took me to a website with a bunch of fake download things and wouldn't actually give me the zip file.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-08-12T17:19:18+00:00
- Post Title: Cars 2 model exporting problems- please help

> Reply from xpunkrockyugox ↑Thu Aug 13, 2020 12:48 am at Thu Aug 13, 2020 12:48 am
>
> So I have to convert the .oct to a .bin somehowNo - the bin is the binary copy of .vbuf+ .ibuf file(s). If you can't use hex2obj you'll have to wait for someone coding a (python) script.
.



axelrod.png (191.82 KiB) Viewed 205 times



> - The link to the program wasn't working, ...Trust me, it is. Look at the bottom of that site:
File to download: hex2o__0.24e3.zip(842.36 Kb)

(161 downloads of that version so far)
## Post #7
- Username: xpunkrockyugox
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Aug 11, 2020 7:55 am
- Post datetime: 2020-08-12T19:15:30+00:00
- Post Title: Cars 2 model exporting problems- please help

This is amazing!! Sorry for not really understanding the hex2obj thing right off, I'm... kind of a noob to anything involving hexadecimals or raw data editing. I really do want to learn how to use it though, and do this myself for the other models. I don't think I need a Python script that'll do it for me in Blender- I actually tried to get one and it didn't work.
Edit: The main things I'm confused about are the .bin thing (specifically, how to turn the .vbuf and .ibuf files into one .bin) and the v by vt thing- I'm not quite sure if you're telling me to add a "t" after every lone v I see or to delete any line that starts with v or vt. Again, really sorry for being kind of a dummy, this is my very first reverse engineering feat.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-08-12T22:51:54+00:00
- Post Title: Cars 2 model exporting problems- please help

> Reply from xpunkrockyugox ↑Thu Aug 13, 2020 3:15 am at Thu Aug 13, 2020 3:15 am
>
> Edit: The main things I'm confused about are the .bin thing (specifically, how to turn the .vbuf and .ibuf files into one .bin)Create a .txt file (rename to .cmd finally) with this single line:
copy /b axelrod_0.vbuf + axelrod_0.ibuf axelrod_0.bin
and execute it in the folder where vbuf/ibuf files reside.

> and the v by vt thing- I'm not quite sure if you're telling me to add a "t" after every lone v I see or to delete any line that starts with v or vt.That's basic office knowledge (notepad, menu edit/replace).  
Open .obj file in your preferred texteditor then replace (without the quotes): "v " by "vt "

btw: that's not the usual approach when using hex2obj, it's just required because for this 3D format uv (texture) coordinates come before vertices. (For many if not most formats the order is like such: vertices normals uvs)
## Post #9
- Username: xpunkrockyugox
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Aug 11, 2020 7:55 am
- Post datetime: 2020-08-12T23:45:52+00:00
- Post Title: Cars 2 model exporting problems- please help

I apologize for continuing to ask stupid questions, but when I opened the axelrod.bin file in Hex2OBJ, it just gave me an error message when I tried to save it as an H20 file. I'm really confused about this and feel bad for being so confused...   So am I supposed to open the .bin in a hex editor and get the vertex and face ranges or whatever the tutorial said? 
Like I said, I'm totally over my head right now, but as confused as I am, that's also how eager I am to learn it so I won't be confused anymore!
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-08-13T08:21:25+00:00
- Post Title: Cars 2 model exporting problems- please help

> Reply from xpunkrockyugox ↑Thu Aug 13, 2020 7:45 am at Thu Aug 13, 2020 7:45 am
>
> , but when I opened the axelrod.bin file in Hex2OBJ, it just gave me an error message when I tried to save it as an H20 file.The .bin file is NOT saved as H2O file, the params (addresses, counts) are.
Rename or delete existing H2O files to save another one.

> So am I supposed to open the .bin in a hex editor and get the vertex and face ranges or whatever the tutorial said?That's the idea. (In this case the H2O files exist already.)
## Post #11
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-08-13T11:39:47+00:00
- Post Title: Cars 2 model exporting problems- please help

> Reply from shakotay2 ↑Thu Aug 13, 2020 6:51 am at Thu Aug 13, 2020 6:51 am
>
> it's just required because for this 3D format uv (texture) coordinates come before vertices.
Isn't it possible to use the absolute addresses for positions and uvs?

> Reply from xpunkrockyugox ↑Thu Aug 13, 2020 3:15 am at Thu Aug 13, 2020 3:15 am
>
> 
The main things I'm confused about are the .bin thing (specifically, how to turn the .vbuf and .ibuf files into one .bin) and the v by vt thing- I'm not quite sure if you're telling me to add a "t" after every lone v I see or to delete any line that starts with v or vt.
You don't have to do any of that actually. This is where AMR will come in handy. 



axelrod_0.png (153.68 KiB) Viewed 177 times
## Post #12
- Username: xpunkrockyugox
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Aug 11, 2020 7:55 am
- Post datetime: 2020-08-13T19:13:28+00:00
- Post Title: Cars 2 model exporting problems- please help

> Reply from shakotay2 ↑Thu Aug 13, 2020 4:21 pm at Thu Aug 13, 2020 4:21 pm
>
> 
xpunkrockyugox wrote: ↑Thu Aug 13, 2020 7:45 am, but when I opened the axelrod.bin file in Hex2OBJ, it just gave me an error message when I tried to save it as an H20 file.The .bin file is NOT saved as H2O file, the params (addresses, counts) are.
Rename or delete existing H2O files to save another one.
So am I supposed to open the .bin in a hex editor and get the vertex and face ranges or whatever the tutorial said? That's the idea. (In this case the H2O files exist already.)

Ohhh, so if I'm understanding, you made the H2O file and I can use that on the other models/bins I want to export? (I'm just trying to find out how to do it myself because I have at least 8 other characters I'm interested in exporting. I just used Axelrod as my guinea pig because he was one of the first ones in the characters folder. I'm not gonna bug anybody for help with the others, just trying to get a process down here. ^^)
## Post #13
- Username: xpunkrockyugox
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Aug 11, 2020 7:55 am
- Post datetime: 2020-08-13T19:26:59+00:00
- Post Title: Cars 2 model exporting problems- please help

> Reply from Bigchillghost ↑Thu Aug 13, 2020 7:39 pm at Thu Aug 13, 2020 7:39 pm
>
> 
shakotay2 wrote: ↑Thu Aug 13, 2020 6:51 amit's just required because for this 3D format uv (texture) coordinates come before vertices.

Isn't it possible to use the absolute addresses for positions and uvs?
xpunkrockyugox wrote: ↑Thu Aug 13, 2020 3:15 am
The main things I'm confused about are the .bin thing (specifically, how to turn the .vbuf and .ibuf files into one .bin) and the v by vt thing- I'm not quite sure if you're telling me to add a "t" after every lone v I see or to delete any line that starts with v or vt.

You don't have to do any of that actually. This is where AMR will come in handy.  
axelrod_0.png

That's amazing!! Thank you so much. I'm curious though- where do you get the numbers for the polygon indices and stuff? Do I use a hex editor there?
## Post #14
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-08-14T00:02:22+00:00
- Post Title: Cars 2 model exporting problems- please help

> Reply from xpunkrockyugox ↑Fri Aug 14, 2020 3:26 am at Fri Aug 14, 2020 3:26 am
>
> 
Do I use a hex editor there?
Surely you do. 

> Reply from xpunkrockyugox ↑Fri Aug 14, 2020 3:26 am at Fri Aug 14, 2020 3:26 am
>
> 
I'm curious though- where do you get the numbers for the polygon indices and stuff?
For polygon indices, the count equals the size of the ibuf file divided by 2. You can get the vertex count by clicking the Calculated button after interpreting the indices. The normals are at a separate chunk right after the one that combines the uvs and the positions. You can get this value by copying the end address from the digest message box after interpreting the uvs. For the rest of the params, just use the same ones shown in the screenshot.

P.S.: a little advice, edit your quotes next time to remove the unnecessary parts.
## Post #15
- Username: xpunkrockyugox
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Aug 11, 2020 7:55 am
- Post datetime: 2020-08-15T03:02:51+00:00
- Post Title: Cars 2 model exporting problems- please help

> Reply from Bigchillghost ↑Fri Aug 14, 2020 8:02 am at Fri Aug 14, 2020 8:02 am
>
> 
For polygon indices, the count equals the size of the ibuf file divided by 2. You can get the vertex count by clicking the Calculated button after interpreting the indices. The normals are at a separate chunk right after the one that combines the uvs and the positions. You can get this value by copying the end address from the digest message box after interpreting the uvs. For the rest of the params, just use the same ones shown in the screenshot.

P.S.: a little advice, edit your quotes next time to remove the unnecessary parts.

Thanks! Sorry about the long quotes earlier, I'm new to this site lol 
Thank you so much for the formula stuff! I couldn't have made this progress without all of y'all's help, very grateful for the advice and instructions  
As for the textures, I got inconsistent results using the TextureRipper tool from MarvelMods. Does AMR have an option to get textures out? I just used the TextureRipper on the .oct file twice and got two slightly different looking textures. I want to make sure to get the textures looking just right so that I can apply the UV correctly.
## Post #16
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-08-15T11:16:23+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

> Reply from xpunkrockyugox ↑Sat Aug 15, 2020 11:02 am at Sat Aug 15, 2020 11:02 am
>
> 
Does AMR have an option to get textures out?
Nop. That's not a task for AMR. You can use PVRTexTool to unwrap the pixel data but for this game, the textures are already in ordinary dds formats. 
However the nested format of the oct container is really annoying so instead of parsing the whole file structure, I just searched for the "TexturePool" mapping identifier to locate the textures and extract them to the drive.

Here's the mentioned Noesis script.


 fmt_Car2_oct.zip
(1.49 KiB) Downloaded 34 times



There're also a "VertexBufferPool" and a "IndexBufferPool" recorded in the oct file. But aside from the size of the vbuf/ibuf file, there's no vertex/indices count so guess you'll have to calculate them yourself.
## Post #17
- Username: xpunkrockyugox
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Aug 11, 2020 7:55 am
- Post datetime: 2020-08-15T13:23:25+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

> Reply from Bigchillghost ↑Sat Aug 15, 2020 7:16 pm at Sat Aug 15, 2020 7:16 pm
>
> 

Nop. That's not a task for AMR. You can use PVRTexTool to unwrap the pixel data but for this game, the textures are already in ordinary dds formats. 
However the nested format of the oct container is really annoying so instead of parsing the whole file structure, I just searched for the "TexturePool" mapping identifier to locate the textures and extract them to the drive.

Here's the mentioned Noesis script.
fmt_Car2_oct.zip

Thanks again! I assume that Noesis is something like QuickBMS that I can use to extract the DDS textures, right? Here's what the TextureFinder tool gave me, I think I'll try one of those methods you mentioned too, because that would likely give me a higher quality output instead of getting it sorta mixed up like this one did because the only bits I recognize in the picture are his hat-roof thing, hood and license plate XD
[texture01.jpg](https://xentaxbackup.github.io/file/18610_texture01.jpg)
## Post #18
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-08-15T13:43:48+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

> Reply from xpunkrockyugox ↑Sat Aug 15, 2020 9:23 pm at Sat Aug 15, 2020 9:23 pm
>
> 
Thanks again! I assume that Noesis is something like QuickBMS that I can use to extract the DDS textures, right?
This is one of the textures you'll get with the Noesis script.



axelrod_body_d_wii.png (162.03 KiB) Viewed 199 times



Just throw the script into the "plugins\python" folder of Noesis and load the oct files within the application. You'll see what's extracted from the debug window.
## Post #19
- Username: xpunkrockyugox
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Aug 11, 2020 7:55 am
- Post datetime: 2020-08-18T20:35:49+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

Hey there!I just wanted to say thanks again for all the help. I got the Axlerod model working perfectly now! Well, perfectly for someone that doesn't know how to animate in Blender yet, that is lol
I've moved on to converting another one by myself, but I'm stuck on the AMR step right now, it keeps giving me this goofy error message every time I do. The way I got that number, by the way, was using the Disney Infinity model exporter and opening the .obj file in Notepad++. I'll provide a Google Drive link to the one I'm working on now ([https://drive.google.com/file/d/16CKlAd ... sp=sharing](https://drive.google.com/file/d/16CKlAdQ-pmVUeeLIFFp30wJ-Zn8PL-ay/view?usp=sharing)) but all I really need is just to know how to find out the actual vertex count in a way that AMR likes so that I can easily do this process by myself for the rest of them. (I'm actually planning on making a Youtube tutorial video on how I did this and walking the viewers through converting one random Cars model!) 
Again, I'm just confused about what exactly I got stuck on here because with Axlerod I didn't get stuck there, and would like to know how I can fix it so that I can do the others without problems. Thanks!  

Edit: Nvm, turns out my problem was that I had the wrong normals address XD
[Annotation 2020-08-18 152922.png](https://xentaxbackup.github.io/file/18623_Annotation 2020-08-18 152922.png)
## Post #20
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-08-19T13:01:31+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

> Reply from xpunkrockyugox ↑Wed Aug 19, 2020 4:35 am at Wed Aug 19, 2020 4:35 am
>
> 
I've moved on to converting another one by myself, but I'm stuck on the AMR step right now, it keeps giving me this goofy error message every time I do.
You really need to know what you're actually doing instead of complaining about the tool being stupid to you.
As I've said already:



pacer.png (164.14 KiB) Viewed 180 times



> Reply from xpunkrockyugox ↑Wed Aug 19, 2020 4:35 am at Wed Aug 19, 2020 4:35 am
>
> 
The way I got that number, by the way, was using the Disney Infinity model exporter and opening the .obj file in Notepad++.
Which is totally unnecessary. 

> Reply from xpunkrockyugox ↑Wed Aug 19, 2020 4:35 am at Wed Aug 19, 2020 4:35 am
>
> 
all I really need is just to know how to find out the actual vertex count in a way that AMR likes so that I can easily do this process by myself for the rest of them.
AMR doesn't LIKE or prefer any specific vertex count. What it does is to simply check whether the param you input is a valid vertex count (>= 3) and compatible for all attributes in the file scope.
## Post #21
- Username: xpunkrockyugox
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Aug 11, 2020 7:55 am
- Post datetime: 2020-08-20T23:19:44+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

That makes sense. Sorry for making that mistake lol
Moving on though, I am curious what this glitching I'm getting when exporting some of the models means. Not sure what happened but some of the vertices are scrambled once I open the .FBX in Blender. I'm going to include both these screenshots of AMR and of Grem, and 2 different models that come out glitchy no matter what end address I use. Again, sorry for asking so many questions. I mostly knew what I was doing, following that same streamlined, easy to understand process. But it didn't look right in the case of these two rebels. Got a couple of rogue vertices and I'm not sure if I'll have to manually drag them back into place with Blender, or if I've made a mistake in the numbers.
[https://drive.google.com/file/d/1ejjQgD ... sp=sharing](https://drive.google.com/file/d/1ejjQgDFSIaa2cUOByutspwNxur001DTW/view?usp=sharing)
[https://drive.google.com/file/d/1kWQSw6 ... sp=sharing](https://drive.google.com/file/d/1kWQSw6r20EymqfvoEOrLoylrckJzseoZ/view?usp=sharing)
[Annotation 2020-08-20 181507.jpg](https://xentaxbackup.github.io/file/18629_Annotation 2020-08-20 181507.jpg)
## Post #22
- Username: xpunkrockyugox
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Aug 11, 2020 7:55 am
- Post datetime: 2020-08-21T16:32:12+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

> Reply from Bigchillghost ↑Wed Aug 19, 2020 9:01 pm at Wed Aug 19, 2020 9:01 pm
>
> 
You really need to know what you're actually doing instead of complaining about the tool being stupid to you.
Right, my bad. Sorry for complaining instead of actually taking a minute to figure out what was wrong because it turned out I had skipped one of those steps. >.< Generally speaking this is a pretty straightforward and easy to understand process, like for Acer and Axlerod, but unfortunately we've also got a few rebels like Grem and the generic Yugo model, that have some weird rogue vertices glitches. 
Is there anything that can be done to prevent those rogue vertex glitches or will I just have to manually move them back into place in Blender?
Here's a picture of the Yugo model in Blender looking weird.



yugo_glitch.png (155.87 KiB) Viewed 161 times
## Post #23
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-08-21T18:03:17+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

> Reply from xpunkrockyugox ↑Fri Aug 21, 2020 7:19 am at Fri Aug 21, 2020 7:19 am
>
> Again, sorry for asking so many questions.
First of all, no one blames you for asking questions. What I'm disapproving is that disrespectful tone.

> Reply from xpunkrockyugox ↑Fri Aug 21, 2020 7:19 am at Fri Aug 21, 2020 7:19 am
>
> 
I mostly knew what I was doing, following that same streamlined, easy to understand process.
You might be able to handle most single-mesh models with that workaround, without knowing the principles and logics behind it. But this model is involving the concept of submeshes which can't be explained in a word or two. Try to understand the connections between these params and the data at corresponding addresses.


Preview of all 3 submeshes:



gremlinAll.png (122.44 KiB) Viewed 158 times
## Post #24
- Username: xpunkrockyugox
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Aug 11, 2020 7:55 am
- Post datetime: 2020-08-22T02:45:27+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

> Reply from Bigchillghost ↑Sat Aug 22, 2020 2:03 am at Sat Aug 22, 2020 2:03 am
>
> 
First of all, no one blames you for asking questions. What I'm disapproving is that disrespectful tone.

Oh crap, I'm sorry. I didn't know I sounded disrespectful. I really didn't mean to D:

> Reply from Bigchillghost ↑Sat Aug 22, 2020 2:03 am at Sat Aug 22, 2020 2:03 am
>
> 
You might be able to handle most single-mesh models with that workaround, without knowing the principles and logics behind it. But this model is involving the concept of submeshes which can't be explained in a word or two. Try to understand the connections between these params and the data at corresponding addresses.

Mm, I think I understand. I'll have to download those pictures and study them, kinda see if I can tell what's going on.  I've learned a lot about how 3D modeling works over the course of this project, so that's definitely a good thing! ^^
## Post #25
- Username: xpunkrockyugox
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Aug 11, 2020 7:55 am
- Post datetime: 2020-08-22T16:28:58+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

> Reply from Bigchillghost ↑Sat Aug 22, 2020 2:03 am at Sat Aug 22, 2020 2:03 am
>
> 
You might be able to handle most single-mesh models with that workaround, without knowing the principles and logics behind it. But this model is involving the concept of submeshes which can't be explained in a word or two. Try to understand the connections between these params and the data at corresponding addresses.

Hmm... I've been looking at the picture, opening up the files in AMR and even trying to look at it in a hex editor, and I'm not entirely sure how you got the numbers to plug in in the screenshot you sent me. I'm probably being kind of a pain rn, and I do apologize in advance, but could I possibly ask where you got the numbers from in the Grem screenshot? I have to say, it's really amazing and impressive that you can do this hex editing and params stuff so easily!
## Post #26
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-08-23T06:51:38+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

> Reply from xpunkrockyugox ↑Sun Aug 23, 2020 12:28 am at Sun Aug 23, 2020 12:28 am
>
> 
I've been looking at the picture, opening up the files in AMR and even trying to look at it in a hex editor
EVEN? Observing the data within a hex editor is what you're supposed to start with. 

> Reply from xpunkrockyugox ↑Sun Aug 23, 2020 12:28 am at Sun Aug 23, 2020 12:28 am
>
> 
but could I possibly ask where you got the numbers from in the Grem screenshot?
Refer to the below image:



gremlin_ibuf_grouping.png (156.39 KiB) Viewed 134 times



As you can see the indices are in ascending order as they generally are. And you'll encounter the 1st jump discontinuity, or say, a pretty obvious gap between the two values, at address 0x5364. Then the indices are ascending again untill you encounter the 2nd jump discontinuity at address 0x53C4, and so on you'll find the 3rd jump discontinuity at address 0x71A0, and the 4th at address 0x7278. Then you can test these indices in AMR using the address of the jump discontinuities you found, combined with the addresses of different vertex chunks in the vbuf file, which can be acquired only from a hex editor.
Then you'll see the indices between the 1st and the 3rd jump discontinuities actually belong to the same submesh group, so as those from the the 3rd jump discontinuity to the end of file. So all together there're 3 submeshes, as you've seen in my previous post.

> Reply from xpunkrockyugox ↑Sun Aug 23, 2020 12:28 am at Sun Aug 23, 2020 12:28 am
>
> 
I have to say, it's really amazing and impressive that you can do this hex editing and params stuff so easily!
So you see, it's nothing magical but only some trials and errors based on experience. And it's obvious that you can't handle such cases without looking into the data itself. So I suggest you to learn from the beginning. Check the 1st link in my signature if you're interested.
## Post #27
- Username: xpunkrockyugox
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Aug 11, 2020 7:55 am
- Post datetime: 2020-08-23T17:17:29+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

> Reply from Bigchillghost ↑Sun Aug 23, 2020 2:51 pm at Sun Aug 23, 2020 2:51 pm
>
> 
EVEN? Observing the data within a hex editor is what you're supposed to start with.

Oops lol
I don't know how to read hex numbers and addresses, so that was why I saved checking it for last   I suppose that would be my first step, learning how to read what the hex editor tells me! I was looking at it and frantically searching for the exact things you typed and getting myself utterly lost on the first screenful of addresses  

> Reply from Bigchillghost ↑Sun Aug 23, 2020 2:51 pm at Sun Aug 23, 2020 2:51 pm
>
> 
As you can see the indices are in ascending order as they generally are. And you'll encounter the 1st jump discontinuity, or say, a pretty obvious gap between the two values, at address 0x5364. Then the indices are ascending again untill you encounter the 2nd jump discontinuity at address 0x53C4, and so on you'll find the 3rd jump discontinuity at address 0x71A0, and the 4th at address 0x7278. Then you can test these indices in AMR using the address of the jump discontinuities you found, combined with the addresses of different vertex chunks in the vbuf file, which can be acquired only from a hex editor.
Then you'll see the indices between the 1st and the 3rd jump discontinuities actually belong to the same submesh group, so as those from the the 3rd jump discontinuity to the end of file. So all together there're 3 submeshes, as you've seen in my previous post.

So you see, it's nothing magical but only some trials and errors based on experience. And it's obvious that you can't handle such cases without looking into the data itself. So I suggest you to learn from the beginning. Check the 1st link in my signature if you're interested.

Thank you so much! I think hopefully that's the last time I'll go "HALP I'M A NOOB NUMBERS NOT NUMBERING RIGHT!!"    I really can't say thanks enough for all the help and patient thorough explanations, very grateful ^^

Edit- when looking for the vertex chunks in the .vbuf, do I also look for JDs or are they signified in a different way?
## Post #28
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-08-24T12:34:22+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

> Reply from xpunkrockyugox ↑Mon Aug 24, 2020 1:17 am at Mon Aug 24, 2020 1:17 am
>
> 
I was looking at it and frantically searching for the exact things you typed and getting myself utterly lost on the first screenful of addresses
Believe me, most people feel the same when they attempted to take the shortcut instead of learning from the beginning. Yet not much people have the passion and patience to learn for themselves. So you're doing quite well so far. Keep going!  

> Reply from xpunkrockyugox ↑Mon Aug 24, 2020 1:17 am at Mon Aug 24, 2020 1:17 am
>
> 
when looking for the vertex chunks in the .vbuf, do I also look for JDs or are they signified in a different way?
Depends on how you define the discontinuity. The following figure should help you understand the trick.
## Post #29
- Username: xpunkrockyugox
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Aug 11, 2020 7:55 am
- Post datetime: 2020-08-25T03:14:02+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

> Reply from Bigchillghost ↑Mon Aug 24, 2020 8:34 pm at Mon Aug 24, 2020 8:34 pm
>
> 
Believe me, most people feel the same when they attempted to take the shortcut instead of learning from the beginning. Yet not much people have the passion and patience to learn for themselves. So you're doing quite well so far. Keep going!  
Depends on how you define the discontinuity. The following figure should help you understand the trick.

Thanks! 
I've hit a bit of a problem in analyzing this however. This time I did something different and tried to take notes of everything I was doing and connections I made between the numbers. (I decided to practice with the Gremlin model you already did, using the screenshots for reference and trying to arrive at all those same numbers the way that you got them so I might be able to try that process with any other multi-mesh ones I run across.)



Annotation 2020-08-24 220559.jpg (119.38 KiB) Viewed 117 times


I'm trying to figure out where the 168 for the vertices count on the windshield/last submesh came from, would you mind letting me know how you got that last one?
## Post #30
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-08-26T14:51:37+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

> Reply from xpunkrockyugox ↑Tue Aug 25, 2020 11:14 am at Tue Aug 25, 2020 11:14 am
>
> This time I did something different and tried to take notes of everything I was doing and connections I made between the numbers.
Make sure to use proper terms like position address, normal stride, texcoord type etc. instead of phrases like "top address", to avoid confusion.

> Reply from xpunkrockyugox ↑Tue Aug 25, 2020 11:14 am at Tue Aug 25, 2020 11:14 am
>
> 
I'm trying to figure out where the 168 for the vertices count on the windshield/last submesh came from, would you mind letting me know how you got that last one?
You've already been told:

> Reply from Bigchillghost ↑Sun Aug 23, 2020 2:51 pm at Sun Aug 23, 2020 2:51 pm
>
> 
Then you'll see the indices between the 1st and the 3rd jump discontinuities actually belong to the same submesh group, so as those from the the 3rd jump discontinuity to the end of file.
## Post #31
- Username: xpunkrockyugox
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Aug 11, 2020 7:55 am
- Post datetime: 2020-08-26T15:35:59+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

> Reply from Bigchillghost ↑Wed Aug 26, 2020 10:51 pm at Wed Aug 26, 2020 10:51 pm
>
> 
You've already been told:
Bigchillghost wrote: ↑Sun Aug 23, 2020 2:51 pm
Then you'll see the indices between the 1st and the 3rd jump discontinuities actually belong to the same submesh group, so as those from the the 3rd jump discontinuity to the end of file.
Oops- I actually ended up reading over that again and realizing that was already answered shortly after I posted that question, my mistake   
I'll go ahead and change that to put in the right labels- I've been working on the Yugo one myself. I found over 25 jump discontinuities but 3 different buffers, so I'm just trying to see which JD addresses are also integral multiples of 3. Since you only had 4 on your diagram, I'm wondering if it's normal to find that many JDs and then kind of narrow it down based on which ones will work. 



Annotation 2020-08-26 103233.jpg (71.92 KiB) Viewed 115 times


Here's the little notes I made so far. Given that I was able to successfully replicate the results and the numbers you got with the Gremlin model, I have confidence that multimesh models won't be so daunting anymore
## Post #32
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-08-26T23:52:25+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

> Reply from xpunkrockyugox ↑Wed Aug 26, 2020 11:35 pm at Wed Aug 26, 2020 11:35 pm
>
> 
I found over 25 jump discontinuities
These are not the so-called jump discontinuities.  
You need to understand that the data in the ibuf are all two-byte little-endian short integers. So you need to read from the right to the left.
## Post #33
- Username: xpunkrockyugox
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Aug 11, 2020 7:55 am
- Post datetime: 2020-08-27T15:41:17+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

> Reply from Bigchillghost ↑Thu Aug 27, 2020 7:52 am at Thu Aug 27, 2020 7:52 am
>
> 
These are not the so-called jump discontinuities.  
You need to understand that the data in the ibuf are all two-byte little-endian short integers. So you need to read from the right to the left.

Oof, I guess that means I probably need to start all over then >.< 
So is the right way to find them taking each pair of bytes, reading them right to left, and comparing them to see if they're in order that way? 
I'm using HxD for my hex editor, so here's what it looks like when I open the .ibuf.



Annotation 2020-08-27 140022.jpg (115.7 KiB) Viewed 98 times


Edit: I found an option in HxD to put them into groups of 2 so I switched the attachment to have that image instead. Will comparing those give me a more accurate depiction of where the jump discontinuities truly are? Should I read the last two numbers first and compare those instead of the first two so I'm looking at it in little-endian?
## Post #34
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-08-27T23:56:19+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

> Reply from xpunkrockyugox ↑Thu Aug 27, 2020 11:41 pm at Thu Aug 27, 2020 11:41 pm
>
> 
So is the right way to find them taking each pair of bytes, reading them right to left, and comparing them to see if they're in order that way?
Not exactly.

> Reply from xpunkrockyugox ↑Thu Aug 27, 2020 11:41 pm at Thu Aug 27, 2020 11:41 pm
>
> 
I'm using HxD for my hex editor
If that works for you.

> Reply from xpunkrockyugox ↑Thu Aug 27, 2020 11:41 pm at Thu Aug 27, 2020 11:41 pm
>
> 
I found an option in HxD to put them into groups of 2 so I switched the attachment to have that image instead. Will comparing those give me a more accurate depiction of where the jump discontinuities truly are?
No. It actually make it harder.

> Reply from xpunkrockyugox ↑Thu Aug 27, 2020 11:41 pm at Thu Aug 27, 2020 11:41 pm
>
> 
Should I read the last two numbers first and compare those instead of the first two so I'm looking at it in little-endian?
Not necessarily.
## Post #35
- Username: xpunkrockyugox
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Aug 11, 2020 7:55 am
- Post datetime: 2020-08-29T01:01:16+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

> Reply from Bigchillghost ↑Fri Aug 28, 2020 7:56 am at Fri Aug 28, 2020 7:56 am
>
> 

No. It actually make it harder.

Oh, ok. Thanks for telling me. What would the best way be, then? ^^
## Post #36
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-08-31T05:20:56+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

> Reply from xpunkrockyugox ↑Sat Aug 29, 2020 9:01 am at Sat Aug 29, 2020 9:01 am
>
> 
What would the best way be, then?
I suggest to use a hex editor that supports color schemes, which's more friendly to human eyes, and easier for recognizing bytes in different ranges.

The proper way is to work on the byte level and focus on the values of the most significant byte (MSB) of the indices. If you can't read the values parallelly, set the columns to a smaller value like 4, then scroll down and find every suspicious address where the data encounter an abnormal change that's causing the discontinuity. 

You also need to check the amount of vertices of every vertex chunk first to have something for reference. Simply divide the datasize by its stride to get the exact count.
## Post #37
- Username: xpunkrockyugox
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Aug 11, 2020 7:55 am
- Post datetime: 2020-09-01T01:11:29+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

> Reply from Bigchillghost ↑Mon Aug 31, 2020 1:20 pm at Mon Aug 31, 2020 1:20 pm
>
> 
I suggest to use a hex editor that supports color schemes, which's more friendly to human eyes, and easier for recognizing bytes in different ranges.

Ok, I think that definitely could help, I know that my eyes kinda glaze over and get tired when looking at all those numbers sometimes and it can be easy to lose my place  Which hex editor do you use/recommend? ^^
## Post #38
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-09-01T04:43:13+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

Refer to this post.
[viewtopic.php?p=139002#p139002](https://forum.xentax.com/viewtopic.php?p=139002#p139002)
## Post #39
- Username: xpunkrockyugox
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Aug 11, 2020 7:55 am
- Post datetime: 2020-09-02T20:59:18+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

> Reply from Bigchillghost ↑Tue Sep 01, 2020 12:43 pm at Tue Sep 01, 2020 12:43 pm
>
> 
Refer to this post.
viewtopic.php?p=139002#p139002

Thanks! I'll download it right away. Before I saw that notification, however, I ended up looking at the Yugo .ibuf a little more. I thought I'd share with you the way I would spot the jump discontinuities, so that you can just check and see if that's ok. Last time you told me that listing all the places where there was a huge difference in the bytes, so I want to make sure I'm doing this right!  



Annotation 2020-09-02 155053.jpg (149.11 KiB) Viewed 66 times
## Post #40
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-09-03T12:58:18+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

> Reply from xpunkrockyugox ↑Thu Sep 03, 2020 4:59 am at Thu Sep 03, 2020 4:59 am
>
> Last time you told me that listing all the places where there was a huge difference in the bytes
I don't know if you actually understand what a jump discontinuity means. The reason I chose this term is that it's a really vivid concept for such situation. 
(reference image from Wikipedia)


Of course it's not totally in accordance with the definition since these values are discrete afterall, which's also why you need to focus on the MSB of the values. Normally I'd say it's a jump discontinuity if there's a difference over 4 between the MSBs of the two values. Another important thing is, that you shouldn't just conclude without looking at the nearby values. If you don't know what a MSB is, better google for it first.
## Post #41
- Username: xpunkrockyugox
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Aug 11, 2020 7:55 am
- Post datetime: 2020-09-03T15:19:00+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

> Reply from Bigchillghost ↑Thu Sep 03, 2020 8:58 pm at Thu Sep 03, 2020 8:58 pm
>
> 
Of course it's not totally in accordance with the definition since these values are discrete afterall, which's also why you need to focus on the MSB of the values. Normally I'd say it's a jump discontinuity if there's a difference over 4 between the MSBs of the two values. Another important thing is, that you shouldn't just conclude without looking at the nearby values. If you don't know what a MSB is, better google for it first.

Thanks for the illustration- I'm looking at the Wikipedia for both MSB and discontinuities right now. My process up until this point was look at two bytes at once and then look at the next two, comparing the first number of each (Like, for example, if I had 2A 05 then 00 0F, I would look at the 2A and 00 because that was the largest byte on the left. Therefore there's a big gap between the two values because 2A is so much greater than 00 and I just ignored the number on the right. I'm starting to think I confused big-endian with little-endian lol)
Of course I've never been super math savvy, but I am still extremely interested in this whole thing regardless of how much math I have to learn!
## Post #42
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-09-03T16:16:21+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

> Reply from xpunkrockyugox ↑Thu Sep 03, 2020 11:19 pm at Thu Sep 03, 2020 11:19 pm
>
> 
Like, for example, if I had 2A 05 then 00 0F ... I'm starting to think I confused big-endian with little-endian lol
Yes, you should read them in little-endian, which's from the right to the left, as I've already said. So it's 0x52a followed by 0xf00, which's almost 3 times of the former value. 

> Reply from xpunkrockyugox ↑Thu Sep 03, 2020 11:19 pm at Thu Sep 03, 2020 11:19 pm
>
> 
but I am still extremely interested in this whole thing regardless of how much math I have to learn!
The jump discontinuity is indeed a mathematical concept, but this situation isn't actually a math related problem so simply try to follow the idea of this so-called "gap".
## Post #43
- Username: xpunkrockyugox
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Aug 11, 2020 7:55 am
- Post datetime: 2020-09-04T14:46:47+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

> Reply from Bigchillghost ↑Fri Sep 04, 2020 12:16 am at Fri Sep 04, 2020 12:16 am
>
> 
Yes, you should read them in little-endian, which's from the right to the left, as I've already said. So it's 0x52a followed by 0xf00, which's almost 3 times of the former value.

Yeah, it's definitely starting to make more sense now ^^ Looking at the .ibuf the MSBs (on the right, of course!) don't actually typically change too much while the LSBs have a lot of fluctuation. No wonder I found over 36 when I was reading the data wrong!  

> Reply from Bigchillghost ↑Fri Sep 04, 2020 12:16 am at Fri Sep 04, 2020 12:16 am
>
> 
The jump discontinuity is indeed a mathematical concept, but this situation isn't actually a math related problem so simply try to follow the idea of this so-called "gap".

I'll definitely do that, thanks! ^^
But that being said, is the formula/analysis thing I did for how you got the numbers for the Gremlin model correct? I think I included a screenshot that had all of those steps, if I didn't just let me know. I'd just like to make sure that I'm following the right steps to plug in the addresses for the Yugo/others ^^
## Post #44
- Username: xpunkrockyugox
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Aug 11, 2020 7:55 am
- Post datetime: 2020-09-05T15:33:46+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

> Reply from Bigchillghost ↑Thu Aug 27, 2020 7:52 am at Thu Aug 27, 2020 7:52 am
>
> 
These are not the so-called jump discontinuities.  
You need to understand that the data in the ibuf are all two-byte little-endian short integers. So you need to read from the right to the left.

Hey there BCG, quoting this one because it was the last one that related to the addresses in the Yugo file ^^ I've run into a problem when working on the second Yugo submesh. The first one worked just fine, it only contained the axles.



Annotation 2020-09-05 102308.jpg (204.51 KiB) Viewed 37 times


I'm getting a vertex overflow error message here using these values, and I plugged in all the appropriate numbers from the Yugo files, using the same "formula" (I know it's not really a formula in a math sense, but I just mean that I used the numbers in the same locations- like the first number after the normals buffer, address of first JD, etc. Formula was the best word I could think of to use there ^^) that I figured out from your Gremlin screenshots. In my screenshot I tried to put everything where it was visible- the "formula" from the Gremlin model, the numbers from the Yugo one, and what I had in AMR. 
I'm wondering if there's any mistakes you spot that jump out right away there in that picture, like if I added a wrong step into the Gremlin formula thing. Thanks!
## Post #45
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-09-06T08:11:36+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

You should upload some clearer images.
## Post #46
- Username: xpunkrockyugox
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Aug 11, 2020 7:55 am
- Post datetime: 2020-09-07T16:43:55+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

> Reply from Bigchillghost ↑Sun Sep 06, 2020 4:11 pm at Sun Sep 06, 2020 4:11 pm
>
> 
You should upload some clearer images.

Ah, sorry, my bad! I just resized the screenshots so that they would fit within the Xentax site file limits. I'll go ahead and use an Imgur link for the full sized version   
[https://imgur.com/a/WQ9yT5W](https://imgur.com/a/WQ9yT5W)
Hopefully this'll work better ^^ (also if I need to provide more screenshots, from this point forward I'll upload them this way instead of compressing them so they end up blurry and unclear)
## Post #47
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-09-08T13:10:05+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

Well, apparently you noticed the integral-multiple-of-3 trick, which I forgot to memtion. Another auxiliary criterion is to check if there're duplicate faces in the indices. For this ibuf, there's another face using the indices 0, 1, 2 at address 0x32EE, which is easy to spot. And once you knew the vertex count of the 2nd vertex block, it's not hard to find where the indices end.

> Reply from xpunkrockyugox ↑Sat Sep 05, 2020 11:33 pm at Sat Sep 05, 2020 11:33 pm
>
> 
I'm getting a vertex overflow error message here using these values, and I plugged in all the appropriate numbers from the Yugo files
There's a vertex color data chunk after the normal block of the 1st submesh, meaning you can't always assume that the normals come right after the position block. Guess that's why you end up taking these addresses for the vertex attributes? 

The "vertex overflow error message" means you're using wrong params, so you need to check if the vertex count and the addresses you filled in are correct, by measuring the actual amount of the vertex block, instead of using the calculated value from the digest message.

Anyway here is the answer to your "trial":


Preview of all submeshes:



bg_yugoAll.png (106.62 KiB) Viewed 40 times
## Post #48
- Username: xpunkrockyugox
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Aug 11, 2020 7:55 am
- Post datetime: 2020-09-08T15:53:17+00:00
- Post Title: Re: Cars 2 model exporting problems- please help

> Reply from Bigchillghost ↑Tue Sep 08, 2020 9:10 pm at Tue Sep 08, 2020 9:10 pm
>
> 
There's a vertex color data chunk after the normal block of the 1st submesh, meaning you can't always assume that the normals come right after the position block. Guess that's why you end up taking these addresses for the vertex attributes?
Ah, gotcha. So does that mean I accidentally used a vertex color data block where I wrote that the normals were?

> Reply from Bigchillghost ↑Tue Sep 08, 2020 9:10 pm at Tue Sep 08, 2020 9:10 pm
>
> 
The "vertex overflow error message" means you're using wrong params, so you need to check if the vertex count and the addresses you filled in are correct, by measuring the actual amount of the vertex block, instead of using the calculated value from the digest message.

Sorry if you've already said this before- but I don't recall if I ever learned how to measure the vertex block size. Again, I hope that's not a stupid question of me to ask 
I will, of course, do the same thing for this I did for the Gremlin and sorta reverse-engineer the numbers to figure out where in the file they came from. Thank you so much for the screenshot dude
