## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-04-29T15:19:40+00:00
- Post Title: Final Fantasy Dissidia NT PS4 tools

Final Fantasy Dissidia NT tools.
Also work with Warriors Allstars, Dynasty Warriors 9, Nioh, Nioh 2, Fire Emblem Warriors, may work with other games.

Usage: drop something on the tool

1. G1M will produce ASCII model and SMD skeleton
2. G1T will extract all textures in "texture" folder
3. GMPK, PG1M will extract G1M & G1T
4. MDL (from Nioh) will extract G1M
5. bin.gz (from Fire Emblem Warriors) will extract G1M & G1T

Important NOTES
- ASCII format will have extended info for correct bone rotations. Noesis plugin that reads them is included.
- If model skeleton is in separate file, you need to drag both model and skeleton, dropping the skeleton onto the EXE. Alternatively, you can run the tool with 2 parameters:
ffsnt <model> <skeleton>







All cloth submeshes extracted and correctly placed. 




[ffsnt.rar](https://xentaxbackup.github.io/file/18342_ffsnt.rar)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-02T16:36:33+00:00
- Post Title: Final Fantasy Dissidia NT PS4 tools

"Big endian" version. For console games.
[ffsntBE.rar](https://xentaxbackup.github.io/file/15208_ffsntBE.rar)
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-03T16:46:59+00:00
- Post Title: Final Fantasy Dissidia NT PS4 tools

New version. Full cloth support!

This is how it works:
Some parts of cloth meshes will be weighted normally to the main skeleton (upper parts usually).
The remaining part is supposed to work with cloth driver.
Drivers will be exported as separate meshes with skeletons. Use weight transfer (skin wrap) or other means in your favourite editor to make them work. Some give better results transferring from faces, some from skeletons.
## Post #4
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2018-05-03T20:50:41+00:00
- Post Title: Final Fantasy Dissidia NT PS4 tools

Soo 1 little thing I noticed with this...

for Fire Emblem Warriors, it works, but it doesn't put the meshes in place on the model where it should be, instead, it's just laying out on the ground. Also, it doesn't grab the full body mesh either, just physic meshes. I can send some to ya if needed. Also there's no normals or UV's either.

edit: seems to fail on grabbing NUNO (Hair) meshes too.
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-04T04:28:19+00:00
- Post Title: Final Fantasy Dissidia NT PS4 tools

> Reply from demonslayerx8
>
>  it's just laying out on the ground
it means you dont provide the skeleton to the tool
to place meshes, skeleton is needed
i completely forgot to tell that if skeleton is in separate file, you need to put is as second parameter
## Post #6
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2018-05-04T05:06:35+00:00
- Post Title: Final Fantasy Dissidia NT PS4 tools

> Reply from daemon1
>
> demonslayerx8 wrote: it's just laying out on the ground
it means you dont provide the skeleton to the tool
to place meshes, skeleton is needed
i completely forgot to tell that if skeleton is in separate file, you need to put is as second parameter
ah ok, well now I got them all in place, but sadly, doing so causes every mesh to have a lot of holes in them, but also no physic bones at all to be seen unless i do it another way, which gives no meshes and just their bones.

This is a very complicated tool.
## Post #7
- Username: kurokairaku
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Aug 13, 2015 6:54 am
- Post datetime: 2018-05-04T05:15:05+00:00
- Post Title: Final Fantasy Dissidia NT PS4 tools

So I hope you don't mind me chipping in, as someone who extracts from lots of Koei Tecmo games, I got some curiosities going.

While DSX8 outlines how the model will have holes in them, which I wish I understood why it happens, which looks similar to one of the images you posted, but heres an example image.
[https://cdn.discordapp.com/attachments/ ... nknown.png](https://cdn.discordapp.com/attachments/278347451583299585/441825929073786900/unknown.png)

The models do have rigging, as well as UV data on them.

Other issues supplied to while some bones are found for objects, (notice her long bangs things)
[https://cdn.discordapp.com/attachments/ ... nknown.png](https://cdn.discordapp.com/attachments/278347451583299585/441825923117875201/unknown.png)

they seem to be right here (not attatched unfortunately) , it still makes me wonder if bones actually exist fo rthem? Her ponytail behind is also driven by physics meshes yet bones for it are not found.

Still, the fact these meshes are in their default spot rather than xentax tool drives this tool high up my "want it to work" list. Putting the models though something other than the cheese factory would help alot.

Lastly, is rigging, or these "drivers". These drivers lack form, and often look like flat planes, Is that intentional? How does one even use such a thing. You say we could skin wrap or what not the drivers onto what comes out, Are the drivers meant to have a shape to them, but something is being knocked off, or am I misunderstanding how one can use them. For flat cloth planes it makes sense, though, going by how you are doing the images.

To use the same example of the images I showed above with the same girl and her face, the driver that comes out after combining both the 000.g1m and the 002.g1m, where the face model is located, the driver extracted is this. 

[https://cdn.discordapp.com/attachments/ ... nknown.png](https://cdn.discordapp.com/attachments/278347451583299585/441829229815005184/unknown.png)

The ponytail Driver is a flat plane, when I half expected it to come out with a more defined 3D shape. 

lastly, do you suppose you could create a python that would combine everything, rather than having to open an ascii one by one? This is a simple requests is all, and im not sure if you had that planned already. What you created so far is already amazing.

Thanks for doing this though, I look forward for when the mesh comes out cleanly at least, and thanks a lot for doing this.Also another big thanks on brinigng this info out there. You could of kept to yourself honestly, but you chose to share your work. I respect that, I really do. It helps a lot of people, and in honestly I wish I could that with some of the work I've done, though i'm borrowing talent from others.
## Post #8
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2018-05-04T19:41:29+00:00
- Post Title: Final Fantasy Dissidia NT PS4 tools

> Reply from kurokairaku
>
> 
Lastly, is rigging, or these "drivers". These drivers lack form, and often look like flat planes, Is that intentional? How does one even use such a thing. You say we could skin wrap or what not the drivers onto what comes out, Are the drivers meant to have a shape to them, but something is being knocked off, or am I misunderstanding how one can use them. For flat cloth planes it makes sense, though, going by how you are doing the images.
(...)
The ponytail Driver is a flat plane, when I half expected it to come out with a more defined 3D shape.

The drivers are what the game engine uses to calculate their physics and not exactly 'usual' bones and meshes, so they only have a base shape and aren't defined. Idk about 3ds max since i don't use it. But in Blender you can very very easily just transfer the weights from the driver cloth to the actual mesh with great results.
## Post #9
- Username: kurokairaku
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Aug 13, 2015 6:54 am
- Post datetime: 2018-05-04T20:28:32+00:00
- Post Title: Final Fantasy Dissidia NT PS4 tools

> Reply from o0Crofty0o
>
> kurokairaku wrote:
Lastly, is rigging, or these "drivers". These drivers lack form, and often look like flat planes, Is that intentional? How does one even use such a thing. You say we could skin wrap or what not the drivers onto what comes out, Are the drivers meant to have a shape to them, but something is being knocked off, or am I misunderstanding how one can use them. For flat cloth planes it makes sense, though, going by how you are doing the images.
(...)
The ponytail Driver is a flat plane, when I half expected it to come out with a more defined 3D shape. 

The drivers are what the game engine uses to calculate their physics and not exactly 'usual' bones and meshes, so they only have a base shape and aren't defined. Idk about 3ds max since i don't use it. But in Blender you can very very easily just transfer the weights from the driver cloth to the actual mesh with great results.

Yeah, the only time I had difficulty was when the driver, a flat plane, was driving a 3D object, like a large clump of  hair. I had to mess with the various skin wrap settings in order to make sure that the small area of effect translated to the entire 3D mesh. A learning experience though I now see how I can use these drivers. It works wonderful yon actual cloth like capes and skirts though, i was really suprised. Skin Morph > Choose Driver > Create Skin. The settings most I had to make sure was enabled was "weight all points" and then fiddle with the falloff and distance because you can also use it to transfer weights 1 to 1 based on the same topology, so it calculates the weights based on the distance between the source and target verts, 

In all honesty, seeing the drivers makes me understand why the hell Nights of Azure 2 had this "wall of bones" problem going on. Its the same idea.

I honestly had the idea that the driver was the simplistic model that the simulation does its calculation on, which saves on resources, rather than simulating the many more verts. Thanks for answering, now to hear on Daemon why the mesh turns into Swiss Cheese. Im sure its a reason I cant understand but I am kinda curious. Like it does half the work XD the Mesh is there with UV's and rigging data its hilarious, yet half the tri's are gon on each Quad face. If only I could understand code...
## Post #10
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-05T07:47:21+00:00
- Post Title: Final Fantasy Dissidia NT PS4 tools

> Reply from demonslayerx8
>
> This is a very complicated tool.
This tool was made in only one week, and i had no time to support everything yet.
Primary purpose was Dissidia NT, and it covered this one fine.

Soon I will update the tool to fix these "holes" and support more games, including DW8/9, Nioh and maybe more.
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-05T07:52:03+00:00
- Post Title: Final Fantasy Dissidia NT PS4 tools

I will now try to answer all questions. If I forgot anything, let me know.

> Reply from demonslayerx8
>
> no physic bones at all to be seen unless i do it another way
Skeletons for physic meshes are very simple, but they are located in separate file from the main skeleton. This is why you can only see them if you use main file as source for skeleton.

Some work need to be done to merge them, and I'm not planning to do this yet.
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-05T07:56:50+00:00
- Post Title: Final Fantasy Dissidia NT PS4 tools

> Reply from kurokairaku
>
> Other issues supplied to while some bones are found for objects
I dont understand this issue, because i don't have the model or model files.
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-05T07:59:36+00:00
- Post Title: Final Fantasy Dissidia NT PS4 tools

> Reply from kurokairaku
>
> Lastly, is rigging, or these "drivers"
I can confirm what Crofty said, drivers are used to generate cloth meshes geometry "on-the-fly" and yes, they are usually flat.

> Reply from kurokairaku
>
> lastly, do you suppose you could create a python that would combine everything, rather than having to open an ascii one by one?
I'm not making pythons. I could make the tool exporting all drivers in one file, but I dont have time for this now.
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-05T12:18:11+00:00
- Post Title: Final Fantasy Dissidia NT PS4 tools

The new version must support DW8/9, Nioh and maybe other games.
## Post #15
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2018-05-05T12:49:09+00:00
- Post Title: Final Fantasy Dissidia NT PS4 tools

Nice work as always!

Does this work with the stages for DW8/9/Nioh and FFDNTPS4 or is it only characters/cloth now?
## Post #16
- Username: kurokairaku
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Aug 13, 2015 6:54 am
- Post datetime: 2018-05-05T13:38:15+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from daemon1
>
> kurokairaku wrote:Lastly, is rigging, or these "drivers"
I can confirm what Crofty said, drivers are used to generate cloth meshes geometry "on-the-fly" and yes, they are usually flat.
kurokairaku wrote:lastly, do you suppose you could create a python that would combine everything, rather than having to open an ascii one by one?
I'm not making pythons. I could make the tool exporting all drivers in one file, but I dont have time for this now.

Thanks for taking the time to answer questions, sorry for some of my more ignorant questions since this is the first time I ever got to see such things, I only had basic understanding but I never actually applied any physic cloths in games or such. Seeing this makes a lot of sense though so thanks. In order to explain the bones part I sent over some FeW Examples of Olivia.

Sorry for assuming you make pythons, since your tool included a .py file for Noesis. Your DW8-DW9 update unfortunately didn't solve swiss cheese in FeW, but it still nice to see it updated to support new things!

The fact you made it in a week makes me wish I had your knowledge. The things I could do with understanding and coding for a very difficult file type... I still thank you for not only doing this but providing the tool for free, while also saying you will attempt to support past games as well. You are really a good person in that regard and I can't express that enough. This tool is currently the strongest I seen for G1M's, and beats steven gas machine despite the swiss cheese models, and despite the fact it can't really combine all the g1m into one loadable file to export.
## Post #17
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-05T14:14:49+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from lionheartuk
>
> Does this work with the stages
i never tried stages
## Post #18
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-05T14:58:43+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from kurokairaku
>
> Sorry for assuming you make pythons
yes if its really needed, i can make pythons.
In this case, noesis plugin can only be python, so i changed it to load my format.
meanwhile, holes issue fixed


As for your question about "bang" things, yes, these are physics bones, and you can see them extracted. I can also place these bones properly, again, this will take time. Ponytail is made from driver as said before, so it has no bones in its usual meaning.

tool updated!
## Post #19
- Username: kurokairaku
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Aug 13, 2015 6:54 am
- Post datetime: 2018-05-05T22:20:47+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from daemon1
>
> kurokairaku wrote:Sorry for assuming you make pythons
yes if its really needed, i can make pythons.
In this case, noesis plugin can only be python, so i changed it to load my format.
meanwhile, holes issue fixed

As for your question about "bang" things, yes, these are physics bones, and you can see them extracted. I can also place these bones properly, again, this will take time. Ponytail is made from driver as said before, so it has no bones in its usual meaning.

tool updated!

Brilliant, thank you very much for getting this to work even though this tool was originally meant for Dissidia. I look forward to further progress but now this is usuable. Atleast only the drivers are, due to the fact everything is segmented, on imports, duplicate armature gets imported, and not merged. In fact I have really create difficulty merging... One cant even seem. I use FBX to export out of Noesis, since 3DS Max best accepts that type, so how do you export blender?

I look forward to the update where you figure out how to just merge everything into one big file instead though. Thanks for what yo did so far. You might want to look into the normals, they are inverted on import into 3DS Max, not a problem really since I just.. flip em. Not to sure if you already know.
## Post #20
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2018-05-05T23:15:09+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

For some reason the noesis script is not working properly on the ASCII files, they don't load or export. Most of them I get the standard 'not viewable but may be exportable' thing, but if I try to export, I get another error, "WARNING: Weight contains an out of range bone index. Discarding model". I can't get it to work at all. I always seem to have a lot of trouble with unusual formats. Is there any chance these can be exported to something less complicated, like DAE? Hell, even for my purposes, since I need to re-rig them anyway, I could use them as OBJ...
## Post #21
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-06T08:12:18+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from kurokairaku
>
> I look forward to the update where you figure out how to just merge everything into one big file
I know how to do that. But I will not, because I dont have time for that.
You can do it yourself in max, blender or noesis, its not a problem.

> Reply from kurokairaku
>
> You might want to look into the normals, they are inverted on import into 3DS Max
They were totally absent since i added support for more games a few days ago.
Tool updated. Vertex normals must be correct now.
## Post #22
- Username: kurokairaku
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Aug 13, 2015 6:54 am
- Post datetime: 2018-05-06T17:58:09+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from daemon1
>
> 
I know how to do that. But I will not, because I dont have time for that.
You can do it yourself in max, blender or noesis, its not a problem.

They were totally absent since i added support for more games a few days ago.
Tool updated. Vertex normals must be correct now.

I see, I hope you do eventually find time to make your tool use everything as I'm sure not only will it improve quality of life, but allow the tool to use everything at its disposal, as to not miss bones or what not. Though that's what I hope. 

Thank you for what you gave so far and your current updates. I already started to attempt to use this tool in my current work flow of getting out all FeW Models.

Edit: Upon using I found that your latest tool ends up breaking the UV's on anything that is cloth, like this cape here.
[https://cdn.discordapp.com/attachments/ ... nknown.png](https://cdn.discordapp.com/attachments/278347451583299585/442767500829130764/unknown.png)

Since I gotta still extract the bin.gz using steven's gas machine I decided to load up the obj it got in order to port the UVW of the cape mesh. Doing that revealed that the original "swisscheese"model syndrome is still there, where every second tri is being effected somehow, the borders of the UV do not match the mesh at all. (Could just "seem" that way)
[https://cdn.discordapp.com/attachments/ ... nknown.png](https://cdn.discordapp.com/attachments/278347451583299585/442772186269220886/unknown.png)

 Otherwise hopefully the visualization of whats going on helps you in some way.
## Post #23
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2018-05-06T20:44:37+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Excuse me, I have a question.
First of all, thank you for sharing the tool with the community, I'm so glad people are still willing to share their knowledge!
Now, to the actual question. Could someone explain to me how to use the tool? I understand that the .py file is for importing the model in Noesis, but what file should I actually drop on the executable?
## Post #24
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2018-05-07T01:26:31+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from shingenseiji
>
> Excuse me, I have a question.
First of all, thank you for sharing the tool with the community, I'm so glad people are still willing to share their knowledge!
Now, to the actual question. Could someone explain to me how to use the tool? I understand that the .py file is for importing the model in Noesis, but what file should I actually drop on the executable?
simple question. you want to drag/drop the G1M files onto the exe, idk if doing the same thing for the G1T will work.
## Post #25
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2018-05-07T12:24:24+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from demonslayerx8
>
> simple question. you want to drag/drop the G1M files onto the exe, idk if doing the same thing for the G1T will work.
Ok, thank you. And where can I find the G1M files? Should I have a modded PS4 and get tHem myself or did someone share the files somewhere?
## Post #26
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2018-05-07T13:02:12+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from shingenseiji
>
> demonslayerx8 wrote:simple question. you want to drag/drop the G1M files onto the exe, idk if doing the same thing for the G1T will work.
Ok, thank you. And where can I find the G1M files? Should I have a modded PS4 and get tHem myself or did someone share the files somewhere?
oh.. the files for Dissidia NT are pretty much private, altho been looking daily for viable leaks of the game since I want them too lol
## Post #27
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2018-05-07T13:25:34+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from demonslayerx8
>
> 
oh.. the files for Dissidia NT are pretty much private, altho been looking daily for viable leaks of the game since I want them too lol
Well, shit... guess I'll have to wait till someone shares them lol. Thanks for the info.
## Post #28
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-07T15:12:40+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from kurokairaku
>
> Otherwise hopefully the visualization of whats going on helps you in some way.
it will NOT help. I need G1M files.
## Post #29
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-07T15:14:18+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from shingenseiji
>
> I understand that the .py file is for importing the model in Noesis
You can also import ASCII model directly into max or blender
## Post #30
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-07T15:17:15+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from demonslayerx8
>
> oh.. the files for Dissidia NT
are distributed between people, like it was for all games i did tools for.
It means if you have friends, you will get them soon, because everybody who has files are free to give them to their friends.
## Post #31
- Username: kurokairaku
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Aug 13, 2015 6:54 am
- Post datetime: 2018-05-07T20:26:10+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from daemon1
>
> kurokairaku wrote:Otherwise hopefully the visualization of whats going on helps you in some way.
it will NOT help. I need G1M files.

I guess I forgot to mention that Olivia, the file I did give you it happens to her as well. I should of mentioned that sorry, I was just showing it on Marth who i was working on at the time, Forgive me on that.


> Reply from daemon1
>
> demonslayerx8 wrote:oh.. the files for Dissidia NT
are distributed between people, like it was for all games i did tools for.
It means if you have friends, you will get them soon, because everybody who has files are free to give them to their friends.

its a shame though that the "friends" that do have it seem to love keeping it to them selves. When you ask nicely they normally tell you to fuck off (this is based on past experience and does not reflect recent behavior), though some will say that more in tone than in actual words. It kinda sucks that things remain within a circle to never come out. So for everyone else who doesnt have very very specific high valued friends, we gotta wait for either a public dump or someone actually nice enough to share each character.
## Post #32
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2018-05-07T21:54:51+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from kurokairaku
>
> 
its a shame though that the "friends" that do have it seem to love keeping it to them selves. When you ask nicely they normally tell you to fuck off, though some will say that more in tone than in actual words. It kinda sucks that things remain within a circle to never come out. So for everyone else who doesnt have very very specific high valued friends, we gotta wait for either a public dump or someone actually nice enough to share each character.

I remember this exact behaviour being the case with the game you and your friends need assistance with before it eventually became public recently. Besides this, I know of quite a few people who have Dissidia files. I'm sure you can find someone who doesn't tell you to ''fuck off''
## Post #33
- Username: kurokairaku
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Aug 13, 2015 6:54 am
- Post datetime: 2018-05-08T05:19:34+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from o0Crofty0o
>
> kurokairaku wrote:
its a shame though that the "friends" that do have it seem to love keeping it to them selves. When you ask nicely they normally tell you to fuck off, though some will say that more in tone than in actual words. It kinda sucks that things remain within a circle to never come out. So for everyone else who doesnt have very very specific high valued friends, we gotta wait for either a public dump or someone actually nice enough to share each character.

I remember this exact behaviour being the case with the game you and your friends need assistance with before it eventually became public recently. Besides this, I know of quite a few people who have Dissidia files. I'm sure you can find someone who doesn't tell you to ''fuck off''

With all due respect, I am not to sure what you are talking about. the accusation tone is off putting, are you claiming that I wrong you at one point? If so I am sorry. I cant say the same for my "friends" as you put it if its their actions you are putting against me then once again I am sorry. I do my best to provide support which I often don't get myself. 

All in all I'm just confused by what you meant by the whole things. For the final point I unfortunately don't know the same people as you do. Though I honestly don't care for Disiddia, at least right now, my "friends" do.  Cool models, would love to make cool things with them but you know, I dont know the right people since the people I know are more switch sided. I dont know your friends or the people you do unfortunately, never tried yet though. Been busy making sure all my own projects fine and dandy...
## Post #34
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2018-05-08T11:43:07+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from kurokairaku
>
> 
(...)the accusation tone is off putting, are you claiming that I wrong you at one point?It is more of an observation than an accusation in my case and no, you did not 'wrong' me. I am merely pointing out some hypocrisy in your own accusations of everyone telling you to ''fuck off'', when i know that this is not true.

> Reply from kurokairaku
>
> 
(...)I dont know your friends or the people you do unfortunately, never tried yet though. (...)To my knowledge, your 'friends' didn't try either so next time ask before victimizing yourself over something that did not happen.
_______

That being said I apologize for posting off-topic here. I'll stop now.
## Post #35
- Username: NovaChrystalia
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Dec 16, 2015 9:26 am
- Post datetime: 2018-05-08T13:49:31+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Probably I shouldn't be asking anything here, but does anyone mind pm'ing me the dissidia nt files? Or know someone that I may try to ask for them?
I can show proof that I bought the game, though. I just want to get Ace's model to playing around with it (writing short stories or making fan photos, I'm a big fan of type-0).
## Post #36
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-08T14:29:02+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from kurokairaku
>
> its a shame though that the "friends" that do have it seem to love keeping it to them selves. When you ask nicely they normally tell you to fuck off, though some will say that more in tone than in actual words. It kinda sucks that things remain within a circle to never come out. So for everyone else who doesnt have very very specific high valued friends, we gotta wait
All of this is absolutely NOT true.

I have no idea why you are saying that, I can only assume that you probably didn't even try to ask. After I started working with PS4 games, I posted tools for:

- Uncharted 4
- Bloodborne
- Until Dawn
- Killzone shadow fall
- Horizon zero dawn

and for all these games people were able to get files with no problems. If you check my threads, you can see it yourself.

There's only one thing I clearly don't like. It's when somebody SELL models or tools to get models. So I suggest you to edit your messages in this thread (especially the one I quote above), to not confuse other people who may read it. Otherwise I could only think that you (or your friends) are some of those bad guys who sell.
## Post #37
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2018-05-08T14:33:33+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from NovaChrystalia
>
> Probably I shouldn't be asking anything here, but does anyone mind pm'ing me the dissidia nt files? Or know someone that I may try to ask for them?
I can show proof that I bought the game, though. I just want to get Ace's model to playing around with it (writing short stories or making fan photos, I'm a big fan of type-0).
Same here. I also have bought the game but I myself don't have any knowledge in pirating PS4 to get a game's files (and not that I can bc I always update my PS4 so even if I wanted to I wouldn't be able to pirate it bc version incompatibility). I also don't have any friends that could help me since I don't frequent places such as deviantART and none of my friends are in the 3D animation/Game ripping field. I only want to rip some models such as Tidus and Jecht since I love FFX and I'd love to do fanart of them. If someone is willing to share the files, please I kindly ask to also be PM'd with the game files...
## Post #38
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-08T17:35:54+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

FEW UVs are fixed.
## Post #39
- Username: kurokairaku
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Aug 13, 2015 6:54 am
- Post datetime: 2018-05-08T19:21:41+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Alright guys I understand what you guys are saying and I apologize for acting out of line. I took my past experiences a little to much to heart (which in honesty was few in between and I was just a dumb idiot at the time) even though they do not reflect recent behaviors of people that I came into contact with. While I can't say for my friends yet again, I haven't seen or even been a victim of such behaviors in a long while. I should of learned from past experiences and not become worse from it, or use it as an excuse to say say some stuff about others undeserving. I took things the wrong way and it was wrong of me to say the things I did, sorry for that, to both Chrofty and Daemon. It was truly unwarranted and I'm sure if I tried and been respectful I would be immediately proven wrong
~~~~

Thanks for fixing FeW UV's Daemon. Sorry for not giving you Marth's file to begin with earlier as I wrongfully assumed you would of just checked with Olivia. Your tool is much appreciated and I thank you yet again. I am going to share this with the people I know who are waiting and looking to have FeW models  and such.
## Post #40
- Username: NovaChrystalia
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Dec 16, 2015 9:26 am
- Post datetime: 2018-05-08T23:33:05+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from Doctor Loboto
>
> For some reason the noesis script is not working properly on the ASCII files, they don't load or export. Most of them I get the standard 'not viewable but may be exportable' thing, but if I try to export, I get another error, "WARNING: Weight contains an out of range bone index. Discarding model". I can't get it to work at all. I always seem to have a lot of trouble with unusual formats. Is there any chance these can be exported to something less complicated, like DAE? Hell, even for my purposes, since I need to re-rig them anyway, I could use them as OBJ...
I have the same problem. 
Also tried import the ascii files into 3dsmax but it keeps telling me that the file is in improper format. I don’t know what to do ><
## Post #41
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2018-05-08T23:44:02+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from NovaChrystalia
>
> Doctor Loboto wrote:For some reason the noesis script is not working properly on the ASCII files, they don't load or export. Most of them I get the standard 'not viewable but may be exportable' thing, but if I try to export, I get another error, "WARNING: Weight contains an out of range bone index. Discarding model". I can't get it to work at all. I always seem to have a lot of trouble with unusual formats. Is there any chance these can be exported to something less complicated, like DAE? Hell, even for my purposes, since I need to re-rig them anyway, I could use them as OBJ...
I have the same problem. 
Also tried import the ascii files into 3dsmax but it keeps telling me that the file is in improper format. I don’t know what to do ><

Both of you most likely load asciis with wrong bones. You need to combine the models with the right skeleton. This works automatic if you select and drag them in the correct order as id-daemon mentioned in the tool description. Or you use this guide and paste the correct skeletons manually: [https://sta.sh/028wb1yfp8e](https://sta.sh/028wb1yfp8e)
## Post #42
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-09T17:50:34+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Tool updated. For Fire Emblem Warriors:
- it will extract G1T & G1M from .bin.gz
- UVs fixed
## Post #43
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2018-05-11T16:01:19+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Hey guys, I'm having some troubles here.
I was able to import Tidus' model into Blender, but it doesn't have any bones.
Now, I know the bones are exported in a different smd file, but my question is how can I merge both files in one?
I tried selecting the three parts of the model (the default.ascii, the Normal.ascii and the skeleton's smd file) like id-daemon says at the description and dragging them to the EXE, but nothing happens.
No new file is created with all the parts merged together.

I also have another problem where Tidus' necklace is divided in two and one of the parts is on the floor. Am I doing something wrong, or should I fix this by myself by dragging the necklace's mesh up till it fits with the other part?

Here's an image showcasing both problems, the no skeleton and the weird necklace problem:
## Post #44
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-11T16:04:48+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from shingenseiji
>
>  question is how can I merge both files in one?
you have to drag G1M files to the tool, not ASCII or SMD
## Post #45
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2018-05-11T16:21:15+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from daemon1
>
> you have to drag G1M files to the tool, not ASCII or SMD
Ohhh ok, so you mean drag the default, Normal and skeleton's G1M files all at once instead of one by one (like I did to extract the ASCII)?

EDIT: Did that and now nothing appears in blender when I import the ASCII file into it. No meshes nor skeletons at all.
## Post #46
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-11T19:58:07+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from shingenseiji
>
> Ohhh ok, so you mean drag the default, Normal and skeleton's G1M files all at once
no i mean "drag both model and skeleton" just as i said in the beginning
so drag only 2 files at a time
## Post #47
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2018-05-11T20:23:11+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from daemon1
>
> shingenseiji wrote:Ohhh ok, so you mean drag the default, Normal and skeleton's G1M files all at once
no i mean "drag both model and skeleton" just as i said in the beginning
so drag only 2 files at a time
The model is divided in two though. And I tried also dragging just two and it stills shows nothing when opening it in Blender. I don't understand why.
## Post #48
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-11T20:48:19+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from shingenseiji
>
> The model is divided in two though. And I tried also dragging just two and it stills shows nothing when opening it in Blender. I don't understand why.
you can merge them after in your editor.

you're dragging by the wrong file. Its important which file of the two is dropped onto the exe
## Post #49
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2018-05-11T21:26:01+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from daemon1
>
> you can merge them after in your editor.

you're dragging by the wrong file. Its important which file of the two is dropped onto the exe
I did drag the files by the g1m file that contains the skeleton. Here, these are all the files I have:


I selected both the p_ten100_2p1c.g1m file and the p_ten100_2p1c_default.g1m file, and I dragged them to the EXE by the p_ten100_2p1c.g1m one.
However, nothing happens. The tool just opens and closes, without extracting anything.
## Post #50
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2018-05-11T21:32:00+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

you want to drag it by the p_ten100_2p1c_default.g1m
## Post #51
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2018-05-11T21:38:32+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from demonslayerx8
>
> you want to drag it by the p_ten100_2p1c_default.g1m
Ok, that worked. Thank you so much!
## Post #52
- Username: Raijinken
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 21, 2016 3:25 pm
- Post datetime: 2018-05-12T03:31:17+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Thanks for making a tool for Dissidia NT, I really appreciate but how I would I go about ripping the files from the disc itself? I'd like to get my hands on the models and textures to make art for future NT tournaments but do I need a PS4 on lower firmware for something like that?
## Post #53
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2018-05-18T01:01:00+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

I can say that the tool also works for Hyrule Warriors Definitive Edition on the switch (doesn't work with the files on WiiU)
[DdcCKDAVQAIJDVr.jpg](https://xentaxbackup.github.io/file/14370_DdcCKDAVQAIJDVr.jpg)
## Post #54
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-18T15:07:40+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from demonslayerx8
>
> I can say that the tool also works for Hyrule Warriors Definitive Edition on the switch (doesn't work with the files on WiiU)
this is because i only support Little endian data (used on PC, PS4, switch)
i can add big endian support, then it will probably work on other platforms
## Post #55
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2018-05-20T09:18:01+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from demonslayerx8
>
> I can say that the tool also works for Hyrule Warriors Definitive Edition on the switch (doesn't work with the files on WiiU)hello, can you pass me Hyrule Warriors files via PM?
## Post #56
- Username: DillyDong
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jul 15, 2015 2:53 am
- Post datetime: 2018-05-22T02:34:30+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from demonslayerx8
>
> I can say that the tool also works for Hyrule Warriors Definitive Edition on the switch (doesn't work with the files on WiiU)
How did you get the HW files working? Are they the same extensions that work for the extractor?
## Post #57
- Username: Beyond69
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Jun 11, 2015 6:19 am
- Post datetime: 2018-05-24T18:27:00+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

could anyone share the dissidia nt files via PM, thanks
## Post #58
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2018-05-24T20:20:47+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Nice work again daemon1  !
## Post #59
- Username: SilverBelle
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue May 08, 2018 11:27 pm
- Post datetime: 2018-05-25T10:45:55+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Where can you find the GMPK files for Dissidia NT? I really want the files for Yshtola but I'm kind of at a loss of where everyone is finding the files. Any help would be appreciated!
## Post #60
- Username: ureshiiiiii
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jul 22, 2017 9:14 am
- Post datetime: 2018-05-30T07:47:33+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from SilverBelle
>
> Where can you find the GMPK files for Dissidia NT?
I'd also like to learn this too, but more specifically if the files would include DLC models like Vayne.
## Post #61
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-05-30T16:35:55+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

You guys can get the files in the usual place where you got other PS4 game dumps so far.
And usually update versions and DLCs are released for higher firmware of the PS4 that means they will not be available anytime soon.
Just remember game link files posted here are against the rules so just do that in PM.
## Post #62
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2018-06-07T03:25:38+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

getting all these driver based bones to their physic meshes is tough af to do via 3ds max... I know it's simple to do in Blender, but I'm a 3ds max user, and there's no great process with fixing these physic meshes at all.

Any chance of an update in the future that can somehow make this easier? I refuse to use blender cause I can't navigate around it's UI and it's layout.
## Post #63
- Username: tone
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Jul 03, 2017 3:40 am
- Post datetime: 2018-06-14T05:46:32+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

confirmed to work on sw4-II pc
## Post #64
- Username: PleasantPeasant
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 04, 2018 10:27 pm
- Post datetime: 2018-07-06T18:41:22+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Can someone pm me the model files for Exdeath?
## Post #65
- Username: ryukem
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Oct 09, 2015 5:59 am
- Post datetime: 2018-07-08T01:19:14+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

hello greetings, some help, I can not open nioh ASCII files any solution, with textures I have no problem
thanks for the program
## Post #66
- Username: ThatOtherSiteKappa
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 01, 2016 12:57 am
- Post datetime: 2018-07-26T18:11:02+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Any chance of adding support for Dissidia Final Fantasy Opera Omnia textures? They seem to come out corrupt. Samples: [https://mega.nz/#!AwpkyIbL!0KpSMiHYoU0M ... N7qkb07KU4](https://mega.nz/#!AwpkyIbL!0KpSMiHYoU0MTnmapYmGQ0EDtofBlj9owN7qkb07KU4)


Edit: was able to dump the cache files, and it seems the models rigging are pretty borked. Samples: [https://mega.nz/#!txxVXCLI!5835KyoE6ymk ... Gp570L4X5A](https://mega.nz/#!txxVXCLI!5835KyoE6ymkrr1DMh6FlU86c__cfySgRGp570L4X5A)

It seems It's hit or miss, some models are converting properly, while others are broken.
## Post #67
- Username: zhekm
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 06, 2016 7:00 pm
- Post datetime: 2018-09-15T05:39:35+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Can support the next effect / *. Gepk?
## Post #68
- Username: R5GAMER
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Jun 08, 2015 5:41 am
- Post datetime: 2018-10-02T09:49:12+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Great tools !!  
But it is possible to extract animation ?
## Post #69
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-10-25T14:35:30+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Also works really well with Atelier series. Tested it with the pc ports of 2 latest games (Firis and Lydie & Suelle). I guess the tool loads almost everything from Koei Tecmo
## Post #70
- Username: griffiel
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 10, 2018 12:13 pm
- Post datetime: 2018-10-26T04:41:19+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Nice work as always!

Is it possible to re-pack/convert ascii files to g1m file and put it back to the game?
## Post #71
- Username: Mochi655
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jun 05, 2018 10:59 pm
- Post datetime: 2018-11-03T14:00:59+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Fatal Frame 5 would be great. Because they are really hard to export.
## Post #72
- Username: themimegogo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Nov 06, 2018 8:07 pm
- Post datetime: 2018-11-16T18:08:27+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Question:

I've been trying to get use this to work with Dissidia Opera Omnia, but I'm just randomly drag and dropping different files into the tool as mentioned in the OP.

so far no success, I just keep getting a command prompt that immediately closes itself, I'm guessing that I am proceeding about it incorrectly. 

Would anyone be kind enough to give some advice? 


DFOO APK:
[https://apkpure.com/dissidia-final-fant ... peraOmnian](https://apkpure.com/dissidia-final-fantasy-opera-omnia/com.square_enix.android_googleplay.DFFOperaOmnian)
## Post #73
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-11-20T09:35:17+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

"Big endian" version posted. For console games:

[viewtopic.php?p=140230#p140230](http://forum.xentax.com/viewtopic.php?p=140230#p140230)
## Post #74
- Username: korea0799
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jun 22, 2016 3:44 pm
- Post datetime: 2018-12-01T12:31:02+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Hi guys,

for model of stage is availabled,

[https://imgur.com/a/mCa0OP7](https://imgur.com/a/mCa0OP7)

just load ascii file in noesis.

script source from:
[https://xnalara.org/viewtopic.php?f=17&t=1139](https://xnalara.org/viewtopic.php?f=17&t=1139)
[fmt_nxps_0_9_6(for noesis).zip](https://xentaxbackup.github.io/file/15261_fmt_nxps_0_9_6(for noesis).zip)
## Post #75
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2018-12-01T14:16:09+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from korea0799
>
> Hi guys,

for model of stage is availabled,

https://imgur.com/a/mCa0OP7

just load ascii file in noesis.

script source from:
https://xnalara.org/viewtopic.php?f=17&t=1139

This isn't really related to the software though, its just a .mesh.ascii exporter for Noesis, it'll work with almost anything noesis can load.
## Post #76
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2018-12-03T22:24:54+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

What’s the update on getting DLC characters?
Did they release any filmware hack already that allows us to get at least Vayne and Locke?
## Post #77
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-12-04T01:23:36+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from shingenseiji
>
> What’s the update on getting DLC characters?
Did they release any filmware hack already that allows us to get at least Vayne and Locke?
Nope, and things don't look too promising either, time will tell.
## Post #78
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2019-01-07T04:21:50+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Where can I find Nioh and  Npc character(Okathu) ?
I did extract archive_17.lnk  with qiuckbms
then I got lots of mdl, gt1 files

After that I've been using Ffsnt tool and still can not find it.
[a.jpg](https://xentaxbackup.github.io/file/15429_a.jpg)
## Post #79
- Username: kinlyki
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Jun 21, 2015 12:36 am
- Post datetime: 2019-01-07T11:31:09+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Does this work on Dissidia Opera Omnia? Cuz someone on deviantart said it does.
## Post #80
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2019-01-07T15:23:07+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

I found the file, but there was a new problem

Noesis loaded several files, but the majority failed
I think there's a problem with the bone

failed load and nothing exported 

Help me, thank you

[https://mega.nz/#!QNFlDIKS!NEMP_2yYFvMK ... Tfq_qoWcHM](https://mega.nz/#!QNFlDIKS!NEMP_2yYFvMKpCQXfCYBi7ru72T_VIM6uTfq_qoWcHM)
[b.jpg](https://xentaxbackup.github.io/file/15430_b.jpg)
## Post #81
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-01-07T15:38:03+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from oamio
>
> I found the file, but there was a new problem

looks like you have the skeleton in a separate file
read how to handle it in the title post
## Post #82
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2019-01-08T02:21:41+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from daemon1
>
> 
looks like you have the skeleton in a separate file
read how to handle it in the title post

Thank you for answer

If you see the attached file my uploaded, use ffsnt to extract the 00000048.mdl file and get the 04.g1m file

After that, I followed you in two ways
There is no effect

 04.g1m file extracts the 1.5mb 04.ascii file and the 04.g1m.smd file, and the smd file is 129 bytes
I did command ffsnt 04.ascii 04.g1m.smd but nothing happend
also drag two files to ffsnt not worked
## Post #83
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-01-08T15:28:20+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

use:
ffsnt 04.g1m 01.g1m

01.g1m - is the skeleton file
## Post #84
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2019-01-09T03:57:31+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from daemon1
>
> use:
ffsnt 04.g1m 01.g1m
Thank you very much 
It works very well!
## Post #85
- Username: kinlyki
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Jun 21, 2015 12:36 am
- Post datetime: 2019-01-09T06:35:30+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

No sign of an answer to my question
## Post #86
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2019-01-09T09:42:02+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

It doesn't work with Opera Omnia.
## Post #87
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2019-01-10T13:15:08+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Did anyone find Okatsu?
I've been searching for two days, but I can not find her

I did look at  hundreds of textures and mdl files.

I thought it would be in archive_10 or archive_11, but it does not.
In archive 17(33gb), there were only monsters and objects.
[Okatsu_(NO).jpg](https://xentaxbackup.github.io/file/15441_Okatsu_(NO).jpg)
## Post #88
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2019-01-11T11:56:34+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

I don't think the bms script exports the files properly, or misses some entirely. I hunted through the files multiple times for the characters but I can only find a few, we probably have to wait for proper support. I could never find Okatsu.
## Post #89
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2019-01-12T13:58:53+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Finally I found Okatsu Texture
[bb.jpg](https://xentaxbackup.github.io/file/15454_bb.jpg)
## Post #90
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2019-01-12T19:27:22+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Did you manage to find her model too?
## Post #91
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2019-01-13T01:13:05+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

It does not seem to be in file extration
Captured from running game
## Post #92
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2019-01-15T13:01:31+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Captured by a ninja ripper
The skirt is not correctly

I want you to let me know if anyone has a way

The upper part of the skirt is seen collapsed
The direction is rotated, I think it probably looks like a cloth simulation

[https://mega.nz/#!NBFi3CjS!UIsnpKAZ9sIB ... WiiR5jAvgQ](https://mega.nz/#!NBFi3CjS!UIsnpKAZ9sIBkhuYZA10KJSjuJQtOWXSUWiiR5jAvgQ)
[aa.jpg](https://xentaxbackup.github.io/file/15475_aa.jpg)
## Post #93
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2019-01-16T01:04:08+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from oamio
>
> Captured by a ninja ripper
The skirt is not correctly

I want you to let me know if anyone has a way

The upper part of the skirt is seen collapsed
The direction is rotated, I think it probably looks like a cloth simulation

https://mega.nz/#!NBFi3CjS!UIsnpKAZ9sIB ... WiiR5jAvgQ

Would you mind explaining how you were able to capture a running PS4 games meshes using a ripper designer for exe files on PC?

As I'd love to be able to do this.

I know it requires particular firmware, however beyond that, i can't imagine.
## Post #94
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2019-01-17T00:51:33+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

I worked on PC version, not Ps4
## Post #95
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2019-01-17T07:54:05+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from oamio
>
> I worked on PC version, not Ps4

Sorry, I might be misunderstanding.

You used the PC version of ninjaRipper, to Rip 3D models of final Fantasy Dissidia NT, whilst playing the game on a PS4.

Am I understanding that correctly? As if so, I was entirely unaware this was possible and this is very interesting.

Edit: Nevermind I understand now, you're ripping from a different game, but just posting in the same topic as the tools works in both.
## Post #96
- Username: xXArinXx
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Mar 28, 2018 2:38 pm
- Post datetime: 2019-01-26T09:54:08+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Long time lurker and first I would like to say thank you for all those working hard to make model ripping an easier world!

Getting straight to the point, I'm putting out a bounty. For anyone who rips Rinoa's model from Dissidia NT will be rewarded with monetary compensation. The requirements are not very high either. All I request at the very least is the model and textures, no rigging or porting required. Even a OBJ file with the textures separate would be sufficient.

Though the bounty will increase if rigging is included. And more if you manage to get both main and alternative costume models.

If this isn't allowed, then I apologize. But if you are interested, please send me a PM. And as all bounties go, it will be first in, first serve. The time limit is until the models are made public through a different source.
## Post #97
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-01-26T11:06:49+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from xXArinXx
>
> Rinoa's model from Dissidia NT
prepare to wait for several years
and bounty will NOT help

new models from PS4 will not be available for a long time
## Post #98
- Username: xXArinXx
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Mar 28, 2018 2:38 pm
- Post datetime: 2019-01-26T15:09:32+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from daemon1
>
> xXArinXx wrote:Rinoa's model from Dissidia NT
prepare to wait for several years
and bounty will NOT help

new models from PS4 will not be available for a long time

Thanks for the reply.

I'm not too savvy with ripping models from console exclusive games, but what it the cause that is limiting users to rip from a game that was previously rippable?
## Post #99
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-01-26T15:37:12+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from xXArinXx
>
> what it the cause that is limiting users
sony is that cause
game updates with new content --> becomes not available
## Post #100
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2019-01-26T21:03:53+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Thanks for the tool to extract Nioh archives!

However, as someone notices, there is indeed a problem with % of available content.
What I have noticed:
- lack of some characters models in archive_11.lnk (there are 14 DAT files that probably could be 7 pairs of model+texture, including Okatsu - assuming this is an archive with selectable player skins)
- lack of ALL weapons and ALL armors textures and probably models (except those armors that were shipped with selectable playable characters in archive_11.lnk and archive_10.lnk) but even if we have models somewhere, without textures this is a no-go 

Big chunk of game content currently left out; I suspect this content is stored in currently unused files. I believe that Nioh BMS script accurately extract all files from archves without overwriting as final size matches size of archive.
## Post #101
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-01-27T07:05:31+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from fullinu
>
> Big chunk of game content currently left out; I suspect this content is stored in currently unused files.
what do you mean under "currently unused files" ?
## Post #102
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2019-01-27T11:25:26+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from daemon1
>
> fullinu wrote:Big chunk of game content currently left out; I suspect this content is stored in currently unused files.
what do you mean under "currently unused files" ?
Well, it's only my assumption, that some textures and meshes are hidden in other files, other than GT1/MDL/G1M archives.
## Post #103
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2019-01-28T01:06:04+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from fullinu
>
> daemon1 wrote:fullinu wrote:Big chunk of game content currently left out; I suspect this content is stored in currently unused files.
what do you mean under "currently unused files" ?
Well, it's only my assumption, that some textures and meshes are hidden in other files, other than GT1/MDL/G1M archives.

It's not the case.
These characters are DLC, the content doesn't exist in the original game, its downloaded and installed onto the console after purchase.
## Post #104
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2019-01-28T01:42:29+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from lionheartuk
>
> It's not the case.
These characters are DLC, the content doesn't exist in the original game, its downloaded and installed onto the console after purchase.
You again?

Stop talking nonsense.
## Post #105
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2019-02-02T15:16:27+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> It's not the case.
>
> These characters are DLC, the content doesn't exist in the original game, its downloaded and installed onto the console after purchase.

I tested it with a complete edition, (include all dlc), and the script actually did not decompose all the files. I do not know if the names were duplicated and rewritten.
Ps. Okatsu does not dlc added characters.

At least I appreciate your opinion.
It's better than nobody cares
## Post #106
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2019-02-03T08:52:58+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from fullinu
>
> lionheartuk wrote:It's not the case.
These characters are DLC, the content doesn't exist in the original game, its downloaded and installed onto the console after purchase.
You again?

Stop talking nonsense.

I'm sorry?
I don't understand whats nonsense about this.
There are around 10 or more people using this tool to find all the meshes in this game, not to mention the countless others online.
Nobody has come across the files that are from DLC's, either stages, textures, characters,rigs or animations, in all of that time.
Thats because the files aren't in the original game disk, I don't understand how anyone can take issue with this, its not negotiable, its exactly how DLC works.

Its true that there have been some games that use DLC to simply 'unlock' files that're already in the base game, but this game isn't one of those cases.
## Post #107
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2019-02-04T10:33:06+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

The characters that are missing are not DLC though, that's the thing. I've searched for characters and bosses that are only in the main game and found two, nothing else.
## Post #108
- Username: MinimalSight
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Aug 18, 2018 10:47 pm
- Post datetime: 2019-02-09T21:43:48+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

First of all, thank you very much for these tools Daemon1!!!
But I was wondering about something:

> Reply from tone
>
> confirmed to work on sw4-II pc

Is there anyone else who managed to get this tool to work for Samurai Warriors 4-II (PC)? I saw the post quoted and tried to extract the models this way but I haven't been successful so far   
I know there's another extraction method for this game but I was hoping this tool could work too (since the models come rigged and with all their meshes in the right place with it)

Edit: So I've tried this tool with a model from another Koei game (Toukiden 2 for PC) and it worked as intended (all the meshes right in place, rigged, it converts the .g1t textures correctly too) and yet I still can't get it to work for Samurai Warriors 4-II...
Not sure what I'm doing wrong   if anyone has a clue I'd appreciate it but well I will keep trying in the meantime!
## Post #109
- Username: MinimalSight
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Aug 18, 2018 10:47 pm
- Post datetime: 2019-03-05T11:06:28+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

(Sorry for double-posting...but) I've been doing more tests and I haven't had any trouble with Toukiden 2 files yet but still no luck for SW4II 3D files...The tool gives me ascii files but it doesn't seem like the Noesis script supports them? Here's the error I have:



I've uploaded some sample files from both games if anyone wants to take a look (gdrive link since it was too big for an attachment, I hope this is ok...if not tell me and I will take down my link!)

[
https://drive.google.com/open?id=1lB6S ... RTKx744Eqm](https://drive.google.com/open?id=1lB6SLp_vKI-mPknrTUBd87RTKx744Eqm)
## Post #110
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2019-03-12T18:33:06+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

So the PC file names are just random character strings...
[files.PNG](https://xentaxbackup.github.io/file/15870_files.PNG)
## Post #111
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2019-03-12T21:14:35+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from MarieRose1301 ↑Wed Mar 13, 2019 2:33 am at Wed Mar 13, 2019 2:33 am
>
> 
So the PC file names are just random character strings...

They may look random but I think is the file name encrypted; I think DOA5 used a similar form of file name "encryption"
## Post #112
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2019-03-12T21:20:56+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from GDL ↑Wed Mar 13, 2019 5:14 am at Wed Mar 13, 2019 5:14 am
>
> 
They may look random but I think is the file name encrypted; I think DOA5 used a similar form of file name "encryption"

Figured so, sorry for bad wording lol
I think DOA6 rdb files looked like that after being extracted


Several files ~3 MB size here have some kind of headers, the others i couldn't understand anything in
## Post #113
- Username: Shuubaru
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Mar 10, 2019 8:53 am
- Post datetime: 2019-03-12T23:50:53+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

hello, i wonder if it is possible to expand the support for Dead or Alive 6? This tool works for some models which got a simple armature (simple outfits, faces, hairs with simple bone structure), but for those with too much bones it just give the error "list index out of range" on the converted ascii.

If needed, here are some sample G1M files which gives that error:
Marie costume 
[https://sta.sh/0hagjpn4rwk](https://sta.sh/0hagjpn4rwk)
Kokoro costume
[https://sta.sh/01dtus2xp4iu](https://sta.sh/01dtus2xp4iu)
## Post #114
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-03-13T09:26:14+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Why it doesn't surprise me they're trying to extract the PC version already?

Its cool btw. Specialty for the ones that want the DLC files AKA Rinoa or Yuna
## Post #115
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2019-03-13T10:14:08+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

or Snow
## Post #116
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-03-13T15:18:00+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

doa6 support will require changes
i dont have time for this
## Post #117
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2019-03-13T17:13:08+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

This is one of the files which seems somewhat close to what the ones containing 3d/tex/anim data were like on the ps4 game
[files.PNG](https://xentaxbackup.github.io/file/15886_files.PNG)
## Post #118
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-03-14T10:47:34+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Someone already begging to post models on Deviant Art:

[https://www.deviantart.com/sticklove/art/Yuna-789440375](https://www.deviantart.com/sticklove/art/Yuna-789440375)

Hope this doesn't turn in another "Private Circle Share", but now for how unpack the data
## Post #119
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2019-03-14T14:13:03+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from Darkhowlings ↑Thu Mar 14, 2019 6:47 pm at Thu Mar 14, 2019 6:47 pm
>
> 
Someone already begging to post models on Deviant Art:

https://www.deviantart.com/sticklove/art/Yuna-789440375

Hope this doesn't turn in another "Private Circle Share", but now for how unpack the data

Who's begging in there tho?
## Post #120
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2019-03-14T20:24:52+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

There is no "private circle share" and there are also no tools. I am the one that posted Yuna and they are dumps from the ram, the files themselves are encrypted.
## Post #121
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-03-15T03:45:58+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from TRDaz ↑Fri Mar 15, 2019 4:24 am at Fri Mar 15, 2019 4:24 am
>
> 
There is no "private circle share" and there are also no tools. I am the one that posted Yuna and they are dumps from the ram, the files themselves are encrypted.

Just saying, because last time it was like that and really hope this time it wouldn't turn like that.
Because, they're someones that don't want to extract just the models, but the raw CG too
## Post #122
- Username: riccochet
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Aug 11, 2014 9:55 pm
- Post datetime: 2019-03-15T15:00:27+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

What are you even going on about? Just because somebody knows how to get the models, and then still shares them doesnt make them obligated to do so. This self entitlement attitude is really killing the community. If you really wanted something you would go out and learn how to do it.
## Post #123
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-03-15T15:14:05+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from Darkhowlings ↑Fri Mar 15, 2019 11:45 am at Fri Mar 15, 2019 11:45 am
>
> last time it was like that
What are you talking about? What "last time"?
## Post #124
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-03-15T19:06:05+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from daemon1 ↑Fri Mar 15, 2019 11:14 pm at Fri Mar 15, 2019 11:14 pm
>
> 
Darkhowlings wrote: ↑Fri Mar 15, 2019 11:45 amlast time it was like that
What are you talking about? What "last time"?

When they find out how to extract the data on the PS4, they begging to share the data on a "In close Circle of friends".
For that I hope it doesn't happen the same now on how unpack the PC data...
## Post #125
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-03-15T19:15:52+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from Darkhowlings ↑Sat Mar 16, 2019 3:06 am at Sat Mar 16, 2019 3:06 am
>
> When they find out how to extract the data on the PS4, they begging to share the data on a "In close Circle of friends".
For that I hope it doesn't happen the same now on how unpack the PC data...
you're probably missing something here.
Dissidia files were never kept "In close Circle"
## Post #126
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-03-26T21:36:30+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from daemon1 ↑Sat Mar 16, 2019 3:15 am at Sat Mar 16, 2019 3:15 am
>
> 
Darkhowlings wrote: ↑Sat Mar 16, 2019 3:06 amWhen they find out how to extract the data on the PS4, they begging to share the data on a "In close Circle of friends".
For that I hope it doesn't happen the same now on how unpack the PC data...

you're probably missing something here.
Dissidia files were never kept "In close Circle"

For what I've toll; they were. Back when the PS4 model come out, I did ask around and I always got the same respond "Private Circle, so, no". Somehow, I manage to get "some" data of the game from a DeviantArt user, but it was just that.

Still, seeing nobody will be interesting on get the PC data, I may stop asking and just use what I've.
I waste 16gb...
## Post #127
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2019-03-27T00:39:55+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from Darkhowlings ↑Wed Mar 27, 2019 5:36 am at Wed Mar 27, 2019 5:36 am
>
> 

For what I've toll; they were. Back when the PS4 model come out, I did ask around and I always got the same respond "Private Circle, so, no". Somehow, I manage to get "some" data of the game from a DeviantArt user, but it was just that.

Still, seeing nobody will be interesting on get the PC data, I may stop asking and just use what I've.
I waste 16gb...
Then you asked the wrong people i assume. There were no problems for many others to get the files.

The pc data is still encrypted so it requires special methods to get any models manually. It is better to not post said method public because the devs might patch it to not work anymore. But someone at zenhax found out the decryption so you just have to be patient and can probably extract the content soon enough.
## Post #128
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2019-03-29T17:37:07+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

So the file names have been decrypted... Anything about the contents themselves?
## Post #129
- Username: Dissidis
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Mar 31, 2019 1:25 pm
- Post datetime: 2019-03-31T05:28:20+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

I have this tool, but not the Dissidia NT files to use this tool. Does anyone know where I can find the raw files? I have been searching everywhere for them. 

~Thank you
## Post #130
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-03-31T23:27:51+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from Dissidis ↑Sun Mar 31, 2019 1:28 pm at Sun Mar 31, 2019 1:28 pm
>
> I have been searching everywhere for them.
Are you sure? Because there are quite a few options once you Google it.
## Post #131
- Username: Dissidis
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Mar 31, 2019 1:25 pm
- Post datetime: 2019-04-01T00:36:03+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Yes I am sure. Unless there are options I have not looked at yet? I have been looking for a few days and nothing has been popping up for me on google.
## Post #132
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2019-04-01T05:06:00+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from Dissidis ↑Mon Apr 01, 2019 8:36 am at Mon Apr 01, 2019 8:36 am
>
> 
Unless there are options I have not looked at yet? I have been looking for a few days and nothing has been popping up for me on google.
Keep looking i guess.
PS4 games are .pkg files. I just searched quickly and its every single hit will take you to various uploaded versions, search harder.
The forum can't/won't help anyone who's attempting to get titles through non-dumping means, so its very unlikely someone here is going to share it.
## Post #133
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-04-07T16:46:04+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

So, while searching I found out they're working on a way to extract it from the Steam, but:

[https://www.zenhax.com/viewtopic.php?f=9&t=11093](https://www.zenhax.com/viewtopic.php?f=9&t=11093)

[https://zenhax.com/viewtopic.php?t=11029](https://zenhax.com/viewtopic.php?t=11029)

That is as far "new" of how extract it its going on.

Besides, that it sure looks beyond hard, or at least for me. Yet, at least its a shot for anyone reading here too. (or try they luck)
## Post #134
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2019-04-10T11:53:01+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

I stumbled upon this thread while searching for a way to get a model I'm looking for for a long time now. The tool already looks nice, but is there any place where I can get the game with all the files in it (besides downloading the free version on Steam)? I kinda want to test myself with this game... And the characters really do look nice (I already have a couple of them in use with XPS/XNALara)...
## Post #135
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-04-10T14:17:49+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from LightXPS ↑Wed Apr 10, 2019 7:53 pm at Wed Apr 10, 2019 7:53 pm
>
> 
I stumbled upon this thread while searching for a way to get a model I'm looking for for a long time now. The tool already looks nice, but is there any place where I can get the game with all the files in it (besides downloading the free version on Steam)? I kinda want to test myself with this game... And the characters really do look nice (I already have a couple of them in use with XPS/XNALara)...

Its forbidden give links here to "pirate" versions...
If they were one too.
They is no pirate or anyway to test the game as you wish, because they haven't even pitate it.

So, its just stream.
At least its free for get the data, which is what many wants to extract, without going by either try out unpacking the PS4 or ask raw data of the PS4
## Post #136
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2019-04-15T07:37:08+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from Darkhowlings ↑Wed Apr 10, 2019 10:17 pm at Wed Apr 10, 2019 10:17 pm
>
> 
Its forbidden give links here to "pirate" versions...
If they were one too.
They is no pirate or anyway to test the game as you wish, because they haven't even pitate it.

So, its just stream.
At least its free for get the data, which is what many wants to extract, without going by either try out unpacking the PS4 or ask raw data of the PS4

And Steam? What about this one? The game released not that long ago on this platform as well - and there's also the free version, which I can use as well. This could be another chance of getting the models besides the raw data, 'cause I don't own a PS4.

Speaking of them: Where - or rather: From who - could I get those?
## Post #137
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-04-15T15:16:30+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from LightXPS ↑Mon Apr 15, 2019 3:37 pm at Mon Apr 15, 2019 3:37 pm
>
> 
And Steam? What about this one? The game released not that long ago on this platform as well - and there's also the free version, which I can use as well. This could be another chance of getting the models besides the raw data, 'cause I don't own a PS4.

Speaking of them: Where - or rather: From who - could I get those?

You get I was saying the Steam and if you read back, nobody has being able ti decript the compressed data of the steam version in any page so far.
## Post #138
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2019-04-17T14:35:39+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from Darkhowlings ↑Mon Apr 15, 2019 11:16 pm at Mon Apr 15, 2019 11:16 pm
>
> 
You get I was saying the Steam and if you read back, nobody has being able ti decript the compressed data of the steam version in any page so far.

Oops... Maybe should've read through all the pages... So sorry for that!

Speaking of the decryption: Is there something in the making to get the job done for Steam? Otherwise I'd just have to ask for the raw data of the PS4...
## Post #139
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-04-18T14:02:04+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from LightXPS ↑Wed Apr 17, 2019 10:35 pm at Wed Apr 17, 2019 10:35 pm
>
> 
Darkhowlings wrote: ↑Mon Apr 15, 2019 11:16 pm
You get I was saying the Steam and if you read back, nobody has being able ti decript the compressed data of the steam version in any page so far.


Oops... Maybe should've read through all the pages... So sorry for that!

Speaking of the decryption: Is there something in the making to get the job done for Steam? Otherwise I'd just have to ask for the raw data of the PS4...

I've just say they haven't find a way to unpack the steam version.
## Post #140
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2019-04-18T23:04:17+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from Darkhowlings ↑Thu Apr 18, 2019 10:02 pm at Thu Apr 18, 2019 10:02 pm
>
> 
I've just say they haven't find a way to unpack the steam version.

don't they already have a decryption algo posted on zenhax? at least their source c code seems so be something like that
## Post #141
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2019-04-19T12:26:09+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Never thought this is going to get that hard to get this model done... But it seems there's no other way to get this done:

Is there a place/person on here who owns/knows a place for the raw (and decrypted) data of Dissidia Final Fantasy NT on PS4? If it's just the model data, I'm fine with that as well. I know there are some people out there who get those models done - I mean, I'm even on a board solely for XNALara/XPS - but some of these models already got pulled from release and/or haven't seen release so far...
## Post #142
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-04-19T13:44:50+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from MarieRose1301 ↑Fri Apr 19, 2019 7:04 am at Fri Apr 19, 2019 7:04 am
>
> 
Darkhowlings wrote: ↑Thu Apr 18, 2019 10:02 pm
I've just say they haven't find a way to unpack the steam version.


don't they already have a decryption algo posted on zenhax? at least their source c code seems so be something like that
Yes they is. I think on the last page I post the links for both pages on Zenhax were they're trying to decrypted, but, so long, they've not got any luck.
## Post #143
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-04-19T15:21:15+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from LightXPS ↑Fri Apr 19, 2019 8:26 pm at Fri Apr 19, 2019 8:26 pm
>
>  the raw (and decrypted) data of Dissidia Final Fantasy NT on PS4?
its impossible to decrypt latest (DLC) data of Dissidia Final Fantasy NT on PS4
## Post #144
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2019-04-19T19:51:15+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Does anyone happen to know what that nffo.ffz file is supposed to be? It's the one used by the pc file decryption program
## Post #145
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2019-04-20T08:57:48+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Seems like I found a model ready to be used in XNALara, but since a re-work is underway of that model I'm searching for, I don't need to decrypt/rip the model by myself anymore - which in turn means I'm out of this thread. Thanks for all the help, though!
## Post #146
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-05-21T14:27:57+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

A month later...
Its kind funny they found a way to edit the game, but, not unpack the steam data.
## Post #147
- Username: Milesgboy
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Jul 04, 2010 12:02 am
- Post datetime: 2019-06-23T21:04:43+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Is it possible to get the stage data from Hyrule Warriors? It unpacks the .bin.gz file to a g1t and .dat which seems to contain multiple g1m files I figure.
## Post #148
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2019-07-02T18:01:43+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Am I the only one without hands?

[](https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/18d493c1-65f0-4606-8ceb-9883bb0269db/ddaquah-56a669fa-595a-46ae-95ce-4388fc2265ae.jpg?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOjdlMGQxODg5ODIyNjQzNzNhNWYwZDQxNWVhMGQyNmUwIiwiaXNzIjoidXJuOmFwcDo3ZTBkMTg4OTgyMjY0MzczYTVmMGQ0MTVlYTBkMjZlMCIsIm9iaiI6W1t7InBhdGgiOiJcL2ZcLzE4ZDQ5M2MxLTY1ZjAtNDYwNi04Y2ViLTk4ODNiYjAyNjlkYlwvZGRhcXVhaC01NmE2NjlmYS01OTVhLTQ2YWUtOTVjZS00Mzg4ZmMyMjY1YWUuanBnIn1dXSwiYXVkIjpbInVybjpzZXJ2aWNlOmZpbGUuZG93bmxvYWQiXX0.rODpdKgFbJ1rRwRuHRX-4CGPaPnrKaCrm2V1ppKe02c)
## Post #149
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-07-02T22:36:35+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from TheDude ↑Wed Jul 03, 2019 2:01 am at Wed Jul 03, 2019 2:01 am
>
> 
Am I the only one without hands?
Well, unless I am missing something, last time I checked, no one can actually verify per say, PS4 still needs a higher firmware to be exploited in order to dump the games DLCs and on PC files are nameless/encrypted, someone mentioned that they changed encryption or something, so yeah.
## Post #150
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2019-07-03T06:12:48+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from TheDude ↑Wed Jul 03, 2019 2:01 am at Wed Jul 03, 2019 2:01 am
>
> 
Am I the only one without hands?

They might be in damageable g1m's
## Post #151
- Username: jooped
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jun 25, 2010 3:30 am
- Post datetime: 2019-07-03T07:49:30+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from TheDude ↑Wed Jul 03, 2019 2:01 am at Wed Jul 03, 2019 2:01 am
>
> 
Am I the only one without hands?

That's because here gloves/hands are technically weapons that can be swapped out with two other versions, they are in another g1m file
## Post #152
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2019-07-03T17:47:51+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from jooped ↑Wed Jul 03, 2019 3:49 pm at Wed Jul 03, 2019 3:49 pm
>
> 
TheDude wrote: ↑Wed Jul 03, 2019 2:01 am
Am I the only one without hands?


That's because here gloves/hands are technically weapons that can be swapped out with two other versions, they are in another g1m file

I was wondering if that was the case. I didn't feel like scrounging around in RAM trying to find it.
## Post #153
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2019-08-13T16:38:02+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Hey daemon, thanks a lot for this great tool.

Would it be possible for you to update it to make Fire emblem Three houses models work with it ? Some of them do but when there are hair or cloth it doesn't work anymore (here's a g1m example file : [https://www.mediafire.com/file/knpz4k2q ... 0.g1m/file](https://www.mediafire.com/file/knpz4k2q7hutmng/000.g1m/file))

Some textures also have a wrong offset sometimes and the output is incorrect (g1t example file : [https://www.mediafire.com/file/u0cb1tmn ... 1.g1t/file](https://www.mediafire.com/file/u0cb1tmnw5z8vv0/001.g1t/file))
## Post #154
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-09-13T05:09:02+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Now that I notice, they're some extra data on the models with the end ".gapk". So far for what I've search... it gives very odd result on Google, so, I assume nobody have being able to extract.
But, what are? Are animations or something like that? Because each character have 2 of 8mb plus a third with the name "face".
## Post #155
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-09-13T15:47:03+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from Darkhowlings ↑Fri Sep 13, 2019 1:09 pm at Fri Sep 13, 2019 1:09 pm
>
> 
...But, what are? Are animations or something like that? Because each character have 2 of 8mb plus a third with the name "face".
That is correct, their animations, each character has 3 or some have a forth one _opening.gapk, while the very first one named _face.gapk is facial MotionCapture, the rest being the in-game animations.



Capture.JPG (15.99 KiB) Viewed 277 times
## Post #156
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-09-13T16:35:30+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from mono24 ↑Fri Sep 13, 2019 11:47 pm at Fri Sep 13, 2019 11:47 pm
>
> 
Darkhowlings wrote: ↑Fri Sep 13, 2019 1:09 pm
...But, what are? Are animations or something like that? Because each character have 2 of 8mb plus a third with the name "face".

That is correct, their animations, each character has 3 or some have a forth one _opening.gapk, while the very first one named _face.gapk is facial MotionCapture, the rest being the in-game animations.
Capture.JPG
Thanks! That will lower the need of find how unpack it too, because the tool doesn't take them.
## Post #157
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2019-09-13T16:45:11+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from mono24 ↑Fri Sep 13, 2019 11:47 pm at Fri Sep 13, 2019 11:47 pm
>
> 
Darkhowlings wrote: ↑Fri Sep 13, 2019 1:09 pm
...But, what are? Are animations or something like that? Because each character have 2 of 8mb plus a third with the name "face".

That is correct, their animations, each character has 3 or some have a forth one _opening.gapk, while the very first one named _face.gapk is facial MotionCapture, the rest being the in-game animations.
Capture.JPG
I believe that the animation [ .dat](https://forum.xentax.com/viewtopic.php?f=16&t=21065) files used in FE Warriors Switch should be similar to the .gapk files, can you check on that, because I don't have the animation files from the other Koei Tecmo games.
## Post #158
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-09-13T17:39:05+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from andree ↑Sat Sep 14, 2019 12:45 am at Sat Sep 14, 2019 12:45 am
>
> I believe that the animation  .dat files used in FE Warriors Switch should be similar to the .gapk files, can you check on that, because I don't have the animation files from the other Koei Tecmo games.
Well, not sure by how much, but there you go.

 sample.zip
(30.59 KiB) Downloaded 30 times
## Post #159
- Username: axcelion
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 12, 2019 4:06 pm
- Post datetime: 2019-10-01T15:18:07+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

guys im still a noob here, i need to know what is the next step after extracting the g1m and g1t? where can i view the models? glad to hear any answer thanks
## Post #160
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-10-01T17:06:05+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from axcelion ↑Tue Oct 01, 2019 11:18 pm at Tue Oct 01, 2019 11:18 pm
>
> 
guys im still a noob here, i need to know what is the next step after extracting the g1m and g1t? where can i view the models? glad to hear any answer thanks

Noesis with a .py for see ascii data or simple for import the latest .xps xnalara models.
Other is Blender with a XNALara plugging too.

Talking of other stuff, does anyone know the passcode of this game? Or it is "000000" like the rest?
## Post #161
- Username: axcelion
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 12, 2019 4:06 pm
- Post datetime: 2019-10-02T07:52:25+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from Darkhowlings ↑Wed Oct 02, 2019 1:06 am at Wed Oct 02, 2019 1:06 am
>
> 
axcelion wrote: ↑Tue Oct 01, 2019 11:18 pm
guys im still a noob here, i need to know what is the next step after extracting the g1m and g1t? where can i view the models? glad to hear any answer thanks


Noesis with a .py for see ascii data or simple for import the latest .xps xnalara models.
Other is Blender with a XNALara plugging too.

Talking of other stuff, does anyone know the passcode of this game? Or it is "000000" like the rest?

thanks for the reply buddy, but my files are .g1m and .g1t...... the .py in noesis and the xnalara plugin in blender only sees .ascii, .xps and mesh.. do i need to convert the .g1m and .g1t files to ascii or something?? thanks    


[https://imgur.com/3vXEsGT](https://imgur.com/3vXEsGT)
## Post #162
- Username: axcelion
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 12, 2019 4:06 pm
- Post datetime: 2019-10-02T11:12:33+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

i already manage to figure out how to view it in max and blender



[https://imgur.com/BYrfLey](https://imgur.com/BYrfLey)

but my one question, do we really need to manually relocate the textures? or is there any other way to automatically relocate the texture.



[https://imgur.com/mrxKgL4](https://imgur.com/mrxKgL4)

thanks
## Post #163
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-10-02T13:24:57+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from axcelion ↑Wed Oct 02, 2019 7:12 pm at Wed Oct 02, 2019 7:12 pm
>
> 
i already manage to figure out how to view it in max and blender



https://imgur.com/BYrfLey

but my one question, do we really need to manually relocate the textures? or is there any other way to automatically relocate the texture.



https://imgur.com/mrxKgL4

thanks
Goooooooooooooooooooood question.
I've being wonder the same for months, because the game uses textures I never see. But, for the looks of it, many are packed in one single .dds, meaning, in one you find the ambient occlusion with others combined in the channels (red, blue, green) of the texture (opened on gimp or photoshop).

But, if any other knows how order them on Max, it could be a lot help, because the ones I saw on XNALara are all mess up, because they're texture sort for render on XNALara limits vs 3DMax more advance textures (Mental.Ray or Vray).
## Post #164
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-10-04T01:51:17+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from Darkhowlings ↑Wed Oct 02, 2019 1:06 am at Wed Oct 02, 2019 1:06 am
>
> Talking of other stuff, does anyone know the passcode of this game? Or it is "000000" like the rest?
What passcode are you talking exactly? If its  a FakePKG then yes its all 0s, if its a Sony retail PKG one then there's no way to get it.

> Reply from axcelion ↑Wed Oct 02, 2019 7:12 pm at Wed Oct 02, 2019 7:12 pm
>
> do we really need to manually relocate the textures? or is there any other way to automatically relocate the texture.
Relocate? you already have all required textures in one archive, G1T, after you extract it you get all required .DDSs in one folder, then you'll have to apply them manually in the desired 3D software, because the tool does NOT do that for you.

> Reply from Darkhowlings ↑Wed Oct 02, 2019 9:24 pm at Wed Oct 02, 2019 9:24 pm
>
> But, for the looks of it, many are packed in one single .dds, meaning, in one you find the ambient occlusion with others combined in the channels (red, blue, green) of the texture (opened on gimp or photoshop).
That is correct, some DDSs have the needed map textures in one of the individual channels, all has to be done manually in order to make them work.
## Post #165
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-10-04T07:30:23+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from mono24 ↑Fri Oct 04, 2019 9:51 am at Fri Oct 04, 2019 9:51 am
>
> 
Darkhowlings wrote: ↑Wed Oct 02, 2019 1:06 amTalking of other stuff, does anyone know the passcode of this game? Or it is "000000" like the rest?
What passcode are you talking exactly? If its  a FakePKG then yes its all 0s, if its a Sony retail PKG one then there's no way to get it.
Darkhowlings wrote: ↑Wed Oct 02, 2019 9:24 pmBut, for the looks of it, many are packed in one single .dds, meaning, in one you find the ambient occlusion with others combined in the channels (red, blue, green) of the texture (opened on gimp or photoshop).
That is correct, some DDSs have the needed map textures in one of the individual channels, all has to be done manually in order to make them work.

From this page for download pkg updates of game of PS4, for don't have one, it was my last option for don't ask for raw data models around, but I guess you cannot open them if it need a passcode almost impossible to get.

Yes, that was what I figure out after extract Mobius data and how texture works on that game.
But, I kind wonder how put them on 3D Max using either way standard, Mental.Ray or Vray texture materials. I ask in other forum, but nobody answer it.
## Post #166
- Username: mahachohan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 06, 2019 2:12 pm
- Post datetime: 2019-10-06T06:14:57+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Great job. I need yourl tool.
## Post #167
- Username: axcelion
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 12, 2019 4:06 pm
- Post datetime: 2019-10-07T15:36:25+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

thanks for the answer btw.. got another question.. how to get the animations?? thanks
## Post #168
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-10-07T21:38:00+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from axcelion ↑Mon Oct 07, 2019 11:36 pm at Mon Oct 07, 2019 11:36 pm
>
> how to get the animations??
Animations are NOT reversed/supported, I wish, only static/skeletal meshes, that's it.
## Post #169
- Username: shenglong
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 04, 2019 3:18 pm
- Post datetime: 2019-10-13T11:05:58+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Hi! daemon1.
I want to know, How do you correctly extract vertex structure = 0x7C size data. 
I very much hope to get your answer, thank you!
## Post #170
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-10-13T12:25:26+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

what do you mean?
## Post #171
- Username: pgw00k
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 28, 2014 7:42 am
- Post datetime: 2019-10-21T01:16:56+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from mono24 ↑Sat Sep 14, 2019 1:39 am at Sat Sep 14, 2019 1:39 am
>
> 
Well, not sure by how much, but there you go.sample.zip
Hello,mono24,I check your file and find some rule aobout the file format,I want to check more files,what game the sample get from?
## Post #172
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-10-21T18:05:19+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from pgw00k ↑Mon Oct 21, 2019 9:16 am at Mon Oct 21, 2019 9:16 am
>
> what game the sample get from?
Um, the game is DFFNT.
## Post #173
- Username: pgw00k
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 28, 2014 7:42 am
- Post datetime: 2019-10-22T01:04:02+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from mono24 ↑Tue Oct 22, 2019 2:05 am at Tue Oct 22, 2019 2:05 am
>
> 
Um, the game is DFFNT.

Thank for your reply,I also check the DFFNT *.gapk(ps4 version),the GAPK file header include animations count,and some animation informations,but I notice your file have the readable animation name,but what I found file is not.
## Post #174
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-10-22T15:27:52+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from pgw00k ↑Tue Oct 22, 2019 9:04 am at Tue Oct 22, 2019 9:04 am
>
> 
mono24 wrote: ↑Tue Oct 22, 2019 2:05 am
Um, the game is DFFNT.


Thank for your reply,I also check the DFFNT *.gapk(ps4 version),the GAPK file header include animations count,and some animation informations,but I notice your file have the readable animation name,but what I found file is not.
Quite doubt you could try the Steam version, because nobody had figure out how unpack the data.

If I remember, they did had problem extracting world map models, beside of some models they may had Morphs, because for example: on Jecht bandanna after unpack, it is all rigged to the head, but in-game it actually moves, inplaying it may it be a morph.
It is just a though anyway.
## Post #175
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-10-22T15:57:32+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from Darkhowlings ↑Tue Oct 22, 2019 11:27 pm at Tue Oct 22, 2019 11:27 pm
>
> Quite doubt you could try the Steam version, because nobody had figure out how unpack the data.
Yes it Is possible, unfortunately is kept secret among few people only, and sucks, maybe because they don't want the devs to patch it and make it worse.
## Post #176
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-10-22T20:17:44+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from mono24 ↑Tue Oct 22, 2019 11:57 pm at Tue Oct 22, 2019 11:57 pm
>
> 
Darkhowlings wrote: ↑Tue Oct 22, 2019 11:27 pmQuite doubt you could try the Steam version, because nobody had figure out how unpack the data.
Yes it Is possible, unfortunately is kept secret among few people only, and sucks, maybe because they don't want the devs to patch it and make it worse.

Is that even possible   !??? It is already the worst Final Fantasy since X-2 & all expansion of FF13+FF15.

But anyway, kind though about that. Not a surprise too.
It could be better find a way of unpack & mod the Steam version, but I hiiiiiiighly doubt it will happen.
## Post #177
- Username: pgw00k
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 28, 2014 7:42 am
- Post datetime: 2019-10-24T00:57:57+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from Darkhowlings ↑Tue Oct 22, 2019 11:27 pm at Tue Oct 22, 2019 11:27 pm
>
> 
Quite doubt you could try the Steam version
Thanks,I try Steam version,then I could decrypt and unpack some file,but the *_mot_00.gapk can not be decrypt successfully,but mot_10 is OK,somebody help?

I use the tool by this [https://www.zenhax.com/viewtopic.php?f= ... ASY#p48968](https://www.zenhax.com/viewtopic.php?f=9&t=11093&p=48968&hilit=DISSIDIA+FINAL+FANTASY#p48968)
## Post #178
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-10-24T05:11:39+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from pgw00k ↑Thu Oct 24, 2019 8:57 am at Thu Oct 24, 2019 8:57 am
>
> I use the tool by this https://www.zenhax.com/viewtopic.php?f= ... ASY#p48968
Looks like lots of people tried that in the past yet no one seemed to made it through the whole process in decrypting anything, how'd you do it?
## Post #179
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2019-10-24T15:43:14+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from mono24 ↑Thu Oct 24, 2019 1:11 pm at Thu Oct 24, 2019 1:11 pm
>
> 
pgw00k wrote: ↑Thu Oct 24, 2019 8:57 amI use the tool by this https://www.zenhax.com/viewtopic.php?f= ... ASY#p48968
Looks like lots of people tried that in the past yet no one seemed to made it through the whole process in decrypting anything, how'd you do it?

I wonder the same, specially because that tool of Zentax works in a very weird way.
Beside being outdated for the 6 months last update.
Later comes the fact that IF the model are the same format of the ps4.

But, if you're willing to try, give a shot.
## Post #180
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-10-25T01:15:01+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from Darkhowlings ↑Thu Oct 24, 2019 11:43 pm at Thu Oct 24, 2019 11:43 pm
>
> Later comes the fact that IF the model are the same format of the ps4.
Yes their all the same.

> Reply from Darkhowlings ↑Thu Oct 24, 2019 11:43 pm at Thu Oct 24, 2019 11:43 pm
>
> But, if you're willing to try, give a shot.
Try what, nothing works, no clue what is that tool about and it's process, just that multiple people tried and failed, myself included.
## Post #181
- Username: pgw00k
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 28, 2014 7:42 am
- Post datetime: 2019-10-25T09:04:47+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from mono24 ↑Thu Oct 24, 2019 1:11 pm at Thu Oct 24, 2019 1:11 pm
>
> 
Looks like lots of people tried that in the past yet no one seemed to made it through the whole process in decrypting anything, how'd you do it?

> Reply from Darkhowlings ↑Thu Oct 24, 2019 11:43 pm at Thu Oct 24, 2019 11:43 pm
>
> 
I wonder the same, specially because that tool of Zentax works in a very weird way.
Beside being outdated for the 6 months last update.
Later comes the fact that IF the model are the same format of the ps4.

But, if you're willing to try, give a shot.

yep,i make a tool for this,on ZenHax moiennepe just share how to do,and he make a ktcry.dll for games,his program is not a common tool,now i make a tool for this,unfortunately,it just run on some files,i don't know why,just like *.mot_10.gapk most is ok,and *_mot_00.gapk is not.

i share here for someone who need it,i think it is not compelete.

1.find your dafb4dd62a79856ae4a02584d9f642a10208bcc3d3de61210a73a75bfb218bc0 and rename to idxzm.
2.then move idxzm to DFFNT.exe directory.
3.just drag files your want to decrypt to .exe icon.
4.try it just like c7e41720356c02eebb4353078b956c2135a55a4ff68aaa0e172efd3c6264ef1c is OK.

and mono24,could you share more files with readable motion names like you share before?
[DFFNT2.zip](https://xentaxbackup.github.io/file/16941_DFFNT2.zip)
## Post #182
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-10-25T17:10:25+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from pgw00k ↑Fri Oct 25, 2019 5:04 pm at Fri Oct 25, 2019 5:04 pm
>
> i share here for someone who need it,i think it is not compelete.

1.find your dafb4dd62a79856ae4a02584d9f642a10208bcc3d3de61210a73a75bfb218bc0 and rename to idxzm.
2.then move idxzm to DFFNT.exe directory.
3.just drag files your want to decrypt to .exe icon.
4.try it just like c7e41720356c02eebb4353078b956c2135a55a4ff68aaa0e172efd3c6264ef1c is OK.
I guess it doesn't work for me, like, at all, unless they changed how decryption works, then this becomes obsolete, I'm no expert so I wouldn't know for sure.

> Reply from pgw00k ↑Fri Oct 25, 2019 5:04 pm at Fri Oct 25, 2019 5:04 pm
>
> and mono24,could you share more files with readable motion names like you share before?
Since you said you tested on your PS4 files, then that's where that sample is from, the PS4 version of the game.
## Post #183
- Username: zgmfx14a
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Oct 19, 2019 8:11 am
- Post datetime: 2019-12-17T03:53:11+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

How can I use this tool to extract nioh models?
## Post #184
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-12-17T17:34:44+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from zgmfx14a ↑Tue Dec 17, 2019 11:53 am at Tue Dec 17, 2019 11:53 am
>
> 
How can I use this tool to extract nioh models?
To convert the models, yes, to extract you need semory's tool, if I remember correctly.
Also the Nioh game doesn't extract properly, there will be lots of files missing, I doubt they will ever be supported fully, at least a proper extraction of the whole game.
## Post #185
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-12-17T18:05:42+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

You can dump dissidia models from ram they store the whole archive in memory when loaded.
## Post #186
- Username: zgmfx14a
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Oct 19, 2019 8:11 am
- Post datetime: 2019-12-21T15:00:40+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from mono24 ↑Wed Dec 18, 2019 1:34 am at Wed Dec 18, 2019 1:34 am
>
> 
zgmfx14a wrote: ↑Tue Dec 17, 2019 11:53 am
How can I use this tool to extract nioh models?

To convert the models, yes, to extract you need semory's tool, if I remember correctly.
Also the Nioh game doesn't extract properly, there will be lots of files missing, I doubt they will ever be supported fully, at least a proper extraction of the whole game.

Can you tell me how to do it? And do you know the Digimon Story Cyber Sleuth Hacker's Memory files. How can I unpack them? Can you tell me?
## Post #187
- Username: Enkidu115
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jan 05, 2020 5:45 pm
- Post datetime: 2020-01-07T01:38:30+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Hello, this is a little late. but i've been using this tool the past 2 days trying to rip the models of dragon quest heroes 2, it works, materials, skeleton, models it all works but i 've came across an issue with models(characters) with different separate meshes like hair, capes and the drivers that come with them, when i apply the skin weights with of the drivers to the mesh (hair in this example) it comes with less than desirable results, know the drivers are bones inherently but are exported that way, but what i've seen with dissidia, it normally works. i was wondering if anyone had any leads on that i can do?
## Post #188
- Username: Petrgold
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Feb 27, 2020 6:46 pm
- Post datetime: 2020-02-27T10:49:02+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Hello Daemon,

Are you planning to do animations ? Also new DOA6 models don't work, can you add them pls
## Post #189
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-02-27T13:05:16+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from Petrgold ↑Thu Feb 27, 2020 6:49 pm at Thu Feb 27, 2020 6:49 pm
>
> 
Hello Daemon,

Are you planning to do animations ? Also new DOA6 models don't work, can you add them pls
[viewtopic.php?f=16&t=21666](https://forum.xentax.com/viewtopic.php?f=16&t=21666)
## Post #190
- Username: speaker60
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Jun 18, 2017 12:41 am
- Post datetime: 2020-06-12T19:41:56+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Are maps extractable so far iv not seen any maps extracted and converted for Dissidia NT
Either that no one has been interested enough to do them or there not doable so i d like to know if anyone knows or anyone who can check

Iv not found/obtained the game files yet so before i tried to find them i though id check i can even do what i want with them

Im only interested in the midgar map and nothing else, i have a hobby project to rebuild a fully explorable midgar city
I already have all the maps from the remake i just wanted to take a closer look at the map from nt as i think it has models for whats missing in the remake. Ill be making alot of new models ect i just wanted to try and get what i could to help my self out

I get know one can tell me where to get the files im not asking that, just want to know if i can i get the the midgar map if i had the files 
If its yes then ill spend however long trying to find the files if i know its worth it
If anyone wants to pm me about the files you would be a god send but yer just the answer can maps be extracted with this?
## Post #191
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-06-17T07:27:30+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Nioh2 support.

This latest version must support all other previously supported games, but just in case something gets broken, i'm leaving old ffsnt.exe in the thread. Usage is the same, but now it can be run in a batch to convert all parts in all folders at once:
for /r %a in (*.g1m) do nioh2.exe "%a" 01.g1m
This will take 01.g1m from every corresponding folder as a skeleton, and convert all models in all subfolders.
## Post #192
- Username: Petrgold
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Feb 27, 2020 6:46 pm
- Post datetime: 2020-06-17T09:49:00+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Animations are planned ?
## Post #193
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-06-17T15:13:10+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from Petrgold ↑Wed Jun 17, 2020 5:49 pm at Wed Jun 17, 2020 5:49 pm
>
> 
Animations are planned ?
no
## Post #194
- Username: Petrgold
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Feb 27, 2020 6:46 pm
- Post datetime: 2020-06-19T13:06:55+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

I found a rigging problem on that file, the part behind doesn't move correctly



The part behind her head is rigged to the wrong bone. The file is CA_MARIA.
## Post #195
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-06-19T13:37:47+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from Petrgold ↑Fri Jun 19, 2020 9:06 pm at Fri Jun 19, 2020 9:06 pm
>
> 
I found a rigging problem
Its not a rigging problem. As said on the 1st page:

> Skeletons for physic meshes are very simple, but they are located in separate file from the main skeleton. This is why you can only see them if you use main file as source for skeleton.

Merging these physics skeletons to main skeleton is not supported and will NOT be supported.
## Post #196
- Username: Petrgold
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Feb 27, 2020 6:46 pm
- Post datetime: 2020-06-19T13:51:52+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from daemon1 ↑Fri Jun 19, 2020 9:37 pm at Fri Jun 19, 2020 9:37 pm
>
> 
Petrgold wrote: ↑Fri Jun 19, 2020 9:06 pm
I found a rigging problem

Its not a rigging problem. As said on the 1st page:

Skeletons for physic meshes are very simple, but they are located in separate file from the main skeleton. This is why you can only see them if you use main file as source for skeleton.


Merging these physics skeletons to main skeleton is not supported and will NOT be supported.

Ok I see. I can see these bones when only dragging the main file indeed
## Post #197
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-06-19T14:39:56+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from Petrgold ↑Fri Jun 19, 2020 9:51 pm at Fri Jun 19, 2020 9:51 pm
>
> 
Ok I see. I can see these bones when only dragging the main file indeed
unfortunately because of nioh2's relative bone layout, these bones will not even be placed correctly, as you can see
## Post #198
- Username: Petrgold
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Feb 27, 2020 6:46 pm
- Post datetime: 2020-06-19T14:45:16+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from daemon1 ↑Fri Jun 19, 2020 10:39 pm at Fri Jun 19, 2020 10:39 pm
>
> 
Petrgold wrote: ↑Fri Jun 19, 2020 9:51 pm
Ok I see. I can see these bones when only dragging the main file indeed

unfortunately because of nioh2's relative bone layout, these bones will not even be placed correctly, as you can see

I understand, don't worry. Thanks again for your work, it's already amazing to have so many games supported. 
The Noesis plugin seems to grab and place them correctly so no need to bother with that little stuff, I can just use that for the models with that issue.
## Post #199
- Username: AzothRaven
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 09, 2021 7:23 pm
- Post datetime: 2021-03-09T21:21:22+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from daemon1 ↑Fri Jun 19, 2020 10:39 pm at Fri Jun 19, 2020 10:39 pm
>
> 
Petrgold wrote: ↑Fri Jun 19, 2020 9:51 pm
Ok I see. I can see these bones when only dragging the main file indeed

unfortunately because of nioh2's relative bone layout, these bones will not even be placed correctly, as you can see

First of all thanks for your work!

Im starting in the 3d community and the ripping as well, I have been able to extract the .ink files of NIOH 2 Complete Edition, with your tool Im able to convert the G1m to ascii and smd and with the Noesis plugin it recognizes them, the issue is that so far I have not been able to actually see any model in Noesis, I can see the skeletons but not the models, I started with the Archive number 10 as a random number but haven been able to see any model so far. Im mainly interested in the weapons, I have read the thread and it says that NIOH is like broken, is that right? am I doing something wrong?
## Post #200
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-03-10T06:41:31+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

No, Nioh 2 is not broken. The only small issue is with rarely used physics bones. Model itself is always correct.
## Post #201
- Username: AzothRaven
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 09, 2021 7:23 pm
- Post datetime: 2021-03-10T14:58:25+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from daemon1 ↑Wed Mar 10, 2021 2:41 pm at Wed Mar 10, 2021 2:41 pm
>
> 
No, Nioh 2 is not broken. The only small issue is with rarely used physics bones. Model itself is always correct.

Thanks for the response! 
I extraced the files using quickbms, and from their page the script used for Nioh archive decryption. And I´m using the script found here in order to be able to see ascii files in Noesis, now, when trying to see them this happens:
[https://ibb.co/6RQRGpc](https://ibb.co/6RQRGpc)
[https://ibb.co/NZZfnPs](https://ibb.co/NZZfnPs)
[https://ibb.co/nL9DnZh](https://ibb.co/nL9DnZh)

Is it normal or am I missing a step?
## Post #202
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-03-10T15:37:18+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from AzothRaven ↑Wed Mar 10, 2021 10:58 pm at Wed Mar 10, 2021 10:58 pm
>
> 
Is it normal or am I missing a step?
read important notes about the skeleton in the 1st post
## Post #203
- Username: AzothRaven
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 09, 2021 7:23 pm
- Post datetime: 2021-03-10T20:30:46+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from daemon1 ↑Wed Mar 10, 2021 11:37 pm at Wed Mar 10, 2021 11:37 pm
>
> 
AzothRaven wrote: ↑Wed Mar 10, 2021 10:58 pm
Is it normal or am I missing a step?

read important notes about the skeleton in the 1st post

You were totally right, now i can see them an export them, you are the best, thank you for all     !!!!
## Post #204
- Username: AzothRaven
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 09, 2021 7:23 pm
- Post datetime: 2021-03-17T19:47:48+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from daemon1 ↑Wed Mar 10, 2021 11:37 pm at Wed Mar 10, 2021 11:37 pm
>
> 
AzothRaven wrote: ↑Wed Mar 10, 2021 10:58 pm
Is it normal or am I missing a step?

read important notes about the skeleton in the 1st post
Hi Daemon!

Sorry to bother you but I have been exporting all the archive.lnk using quickbms and the nioh script for it and I do get hundred of .MDL, this way i have found in the archive_01 all the weapons and armors models, some random objects, but I havent been able to find neither the mobs nor the other characters, not even in the other large archive file, (archive_17 which size is 31 GB) do you have any idea if they are located someplace else? or if I need to extract another type of file to get the MDL to then get the G1M of the models. 
Your help is priceless as always!
## Post #205
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-03-18T06:09:40+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

I've heard that there's some problem with nioh and nioh2 on PC. Encryption or something. To get all characters, you better get PS4 version of files.
## Post #206
- Username: AzothRaven
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 09, 2021 7:23 pm
- Post datetime: 2021-03-18T07:05:46+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from daemon1 ↑Thu Mar 18, 2021 2:09 pm at Thu Mar 18, 2021 2:09 pm
>
> 
I've heard that there's some problem with nioh and nioh2 on PC. Encryption or something. To get all characters, you better get PS4 version of files.
Thank you!! 
Oh alright, do you have any idea where I could download the ps4 game? Like a torrent site or something of the sort?
## Post #207
- Username: AzothRaven
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 09, 2021 7:23 pm
- Post datetime: 2021-03-18T16:53:33+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from daemon1 ↑Thu Mar 18, 2021 2:09 pm at Thu Mar 18, 2021 2:09 pm
>
> 
I've heard that there's some problem with nioh and nioh2 on PC. Encryption or something. To get all characters, you better get PS4 version of files.
I'm sorry if I bother you, I haven't been able to find a ps4 image pkg that I can extract, is there any way you could provide the 3d models? I don't even need the textures, I need the yokai forms of the main character and if possible, all the yokais. Maybe we could reach a deal or something? Thank you for your support so far
## Post #208
- Username: AzothRaven
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 09, 2021 7:23 pm
- Post datetime: 2021-05-13T10:10:47+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from daemon1 ↑Thu Mar 18, 2021 2:09 pm at Thu Mar 18, 2021 2:09 pm
>
> 
I've heard that there's some problem with nioh and nioh2 on PC. Encryption or something. To get all characters, you better get PS4 version of files.

Hi Daemon!

Thank you again for all your efforts, I have since solved the issue and have access to all the characters and models from the base game and the first 2 DLCs thanks to your tool, but I havent been able to find the data for the 3 DLC, the first Samurai, have you or anyone you know been able to find it?
## Post #209
- Username: DrakeyC
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 01, 2020 3:40 am
- Post datetime: 2021-05-22T16:12:00+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Hello. I wanted to ask something about ripping files from the game. Not models, but icons, specifically the icons used in the menus for the different character outfits and weapons, like on this screencap here.

[https://assets.rpgsite.net/images/image ... iew_03.jpg](https://assets.rpgsite.net/images/images/000/063/608/original/dissidia-final-fantasy-nt-review_03.jpg)

I had been told by someone previously that they're in "kscl" format, which cannot be extracted, but that sounds odd to me, that it can't be ripped at all? Or is it that it can be ripped and there's no way to open files of that format?
## Post #210
- Username: S0UZ
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Apr 05, 2011 6:46 pm
- Post datetime: 2021-07-30T23:07:25+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from MinimalSight ↑Sun Feb 10, 2019 5:43 am at Sun Feb 10, 2019 5:43 am
>
> 
First of all, thank you very much for these tools Daemon1!!!
But I was wondering about something:
tone wrote:confirmed to work on sw4-II pc 

Is there anyone else who managed to get this tool to work for Samurai Warriors 4-II (PC)? I saw the post quoted and tried to extract the models this way but I haven't been successful so far   
I know there's another extraction method for this game but I was hoping this tool could work too (since the models come rigged and with all their meshes in the right place with it)

Edit: So I've tried this tool with a model from another Koei game (Toukiden 2 for PC) and it worked as intended (all the meshes right in place, rigged, it converts the .g1t textures correctly too) and yet I still can't get it to work for Samurai Warriors 4-II...
Not sure what I'm doing wrong   if anyone has a clue I'd appreciate it but well I will keep trying in the meantime!
HI! Could you guide me how to unpack toukiden 2 please? Tool doesn't unpack this game.
## Post #211
- Username: Kanbara
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 09, 2019 8:57 pm
- Post datetime: 2022-03-28T16:27:27+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

Final fantasy origin is released and I managed to get some models out of it.
Unfortunately, I also found that the g1m model is somehow incompatible with the ffsnt tool which keeps showing "Unknown Weights Fromat 2".


By using the "Nioh2" tool I did got the model converted but the driver/physic parts of it are all on the grounded and likely distorted. 


And here the g1m sample from this game, the model of Sarah. Any updates of the tool would be highly appreciated!!  :
[https://drive.google.com/file/d/1Rn_p1B ... sp=sharing](https://drive.google.com/file/d/1Rn_p1BSBoCdh6KbBhmIHuLB0oyUqugdq/view?usp=sharing)
## Post #212
- Username: Insistent
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 05, 2019 3:04 pm
- Post datetime: 2022-08-25T02:18:54+00:00
- Post Title: Re: Final Fantasy Dissidia NT PS4 tools

> Reply from AzothRaven ↑Thu May 13, 2021 6:10 pm at Thu May 13, 2021 6:10 pm
>
> 
daemon1 wrote: ↑Thu Mar 18, 2021 2:09 pm
I've heard that there's some problem with nioh and nioh2 on PC. Encryption or something. To get all characters, you better get PS4 version of files.


Hi Daemon!

Thank you again for all your efforts, I have since solved the issue and have access to all the characters and models from the base game and the first 2 DLCs thanks to your tool, but I havent been able to find the data for the 3 DLC, the first Samurai, have you or anyone you know been able to find it?

Im wondering too, did you have to get ps4 files? Also what was the files name for characters? if ya dont mind  (Bosses)
