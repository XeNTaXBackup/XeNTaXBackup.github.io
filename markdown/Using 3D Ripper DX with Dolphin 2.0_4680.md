## Post #1
- Username: Sand3
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jun 26, 2010 8:52 am
- Post datetime: 2010-06-29T04:42:20+00:00
- Post Title: Using 3D Ripper DX with Dolphin 2.0?

I just loaded up Dolphin 2.0 through 3D Ripper DX and it's not giving me the 'ready to rip' message up in the corner. As I recall before, with some of the builds of Dolphin one had to change a few settings to make it work properly, but as I'm going through the menus, I can't find anything that's jumping out to me here. Has anybody had luck with these two yet and can give me some tips on how to make it work properly?
## Post #2
- Username: d2rnattakorn
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Mar 19, 2010 9:18 pm
- Post datetime: 2010-06-29T08:45:40+00:00
- Post Title: Using 3D Ripper DX with Dolphin 2.0?

Hi Sand 3, I also have the same problem with Dolphin 2.0 and 3D Ripper DX 1.8.
Somehow, the new 3D Ripper DX 1.8 dosen't seen to work.
However, when I try using the older 3D Ripper DX; like 1.7 or 1.6 with Dolphin 2.0, it seen to work OK.
Maybe you should try the older version of 3D Ripper DX and maybe update your DirectX too, its might help.
## Post #3
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2010-06-29T16:40:20+00:00
- Post Title: Using 3D Ripper DX with Dolphin 2.0?

have you tried running dx ripper in global mode? some games i cant get dx ripper to see properly and so it doesnt come up with the " ready to rip" but if you drop dx ripper into global mode sometimes it will allow you to rip stuff that way. doesnt always work, but its worth a try. Also some games seem to be more stable when running in global mode rather than directly choosing an exe file and hitting the launch button.
## Post #4
- Username: Sand3
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jun 26, 2010 8:52 am
- Post datetime: 2010-06-30T21:23:51+00:00
- Post Title: Using 3D Ripper DX with Dolphin 2.0?

I'll give both those things a try after work. Thanks guys.
## Post #5
- Username: Sand3
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jun 26, 2010 8:52 am
- Post datetime: 2010-06-30T21:46:28+00:00
- Post Title: Using 3D Ripper DX with Dolphin 2.0?

Nattakorn, do you know where I could still download the older versions?
## Post #6
- Username: d2rnattakorn
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Mar 19, 2010 9:18 pm
- Post datetime: 2010-07-01T16:12:03+00:00
- Post Title: Using 3D Ripper DX with Dolphin 2.0?

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: epopoe
- Rank: advanced
- Number of posts: 56
- Joined date: Thu Feb 11, 2010 9:22 am
- Post datetime: 2010-07-06T14:18:24+00:00
- Post Title: Using 3D Ripper DX with Dolphin 2.0?

check ur dolphin version

3d ripper dx doest work on 64bit dolphin
## Post #8
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2010-07-12T22:12:06+00:00
- Post Title: Using 3D Ripper DX with Dolphin 2.0?

There is also a 3d ripper Dx V1.8 AND 1.8.1.
Also no need to upload 3d ripper to mediafire or anywhere else, when you can DL it directly from their website.

@nattakorn
Regarding your uv's getting messed up. some thing that can happen if you take more than 1 "Rip" at a time you can get messed up TEXTURES ( not uv's ) what i mean is.  I tried snagging some of the terrain from " test drive unlimited " i took 3 rips then loaded them into the 3d app both the second and third looked VERY wrong. what had happened was..... the terrain was split into small chunks in the game, each chunk had a separate object name, but they all had the same material name. so for example the game see's it like this...

Chunk 1, material = terrain, texture= T1
Chunk 2, material = terrain, texture= T2
Chunk 3, material = terrain, texture= T3
And so on....
So when Dx ripper saves the first chunk and it always seems to gives those random names to textures, its not actually random.. say dx ripper assigns the name a1b2c3 to the material and texture names of chunk 1 ( and other names for any other objects present ) Every time it sees the same material name it will apply the same name in Dxripper

So seeing as chunks 1,2,3 all use the name "terrain" as their material. each chunk it exports will have the same texture name so all 3 can have a material and texture called a1b2c3.   
If your only exporting 1 rip, that doesnt matter . but if you rip twice when it exports the second file it saves this chunks texture  over the top of the old one some times. so when you load chunk 1 into a 3d app, it can see a texture called a1b2c3 but its from the second rip not the first ( that was over written ) so it will look all messed up.

first time i ran into this was when i was trying to rip some cars from a game. The main body work for all the cars had the same material name " Body ". first rip was something like a Nissan skyline and the second rip a Ferrari .
When i came to load the nissan it was messed up because it was trying to use the ferrari textures rather than the nissan.

But that only happens if you rip several times in the same session. if you close dx ripper ( by quitting the game ) then reloading them, when it rips it will assign a new random name for the material "terrain". So if i know im gonna be ripping a few times from a game, after each rip i will move the .3dr and all the textures into a folder, call it something like " object 1 " then quit the game. reload 3d ripper and the game, then take my second rip, move it into another folder called " object 2 " and so on.....
I havnt had a single problem with UV's being incorrect ever, but miss-assigned textures ( well its not really miss-assigned its more a case of , a new file over-writing an old file by accident ) ive had a lot of those in the past.
Also quite often it doesnt rip the "colour texture" ( diffuse ) it rips the shadow map instead, as the shadow map is usually the top most layer to a texture it thinks that is the diffuse map. It does this a lot in UT3 based games.
Also while i remember another thing that can happen which looks like a nasty texturing error but isnt... this happens a quite often in driving games... the main body of the car doesnt actually have a diffuse colour map assigned to it, it will just have a colour value ( thats how you are allowed to change the cars colour in game) but it does have a reflection map assigned to it.  when you rip that car in dx ripper, it sees that reflection map as being the only texture assigned to the car body so it presumes it must be a diffuse texture . so it maps the reflection as if its the diffuse, which never looks good  

So i would double check to make sure none of those above problems are actually occurring (as they are all easily fixable) rather than busted uv coordinates which can be a bitch to try and fix by hand.

Hope something there helps... Nobby
.P.S. sorry it was such a long post, i just kept remembering different problems id ran into regarding incorrectly displayed textures from Dxripper.
## Post #9
- Username: d2rnattakorn
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Mar 19, 2010 9:18 pm
- Post datetime: 2010-07-15T15:25:04+00:00
- Post Title: Using 3D Ripper DX with Dolphin 2.0?

> Reply from Nobby
>
> 
@nattakorn
Regarding your uv's getting messed up. some thing that can happen if you take more than 1 "Rip" at a time you can get messed up TEXTURES ( not uv's ) what i mean is.  I tried snagging some of the terrain from " test drive unlimited " i took 3 rips then loaded them into the 3d app both the second and third looked VERY wrong. what had happened was..... the terrain was split into small chunks in the game, each chunk had a separate object name, but they all had the same material name. so for example the game see's it like this...

Thank so much Nobby.
After reading your post, I give its another try.
This time I did a singer rip but I still had the same messed up UV as the image below. I also try to scale/ explan the UV up but it not help.
[](http://www.postimage.org/image.php?v=PqvneQS)

As for the textures, they seem to rip find.
[](http://www.postimage.org/image.php?v=Pqvpdz0)

However, when I look at object that is't character, the UV seem to be OK.
[](http://www.postimage.org/image.php?v=TsRqsu9)

I also know that The new Incredible Hulk game for PC also have messed up UV when rip with 3d ripper Dx.

At this point, I am thinking that it much be something from Dolphin that messed up the UV at rip
or maybe it is the way that this game do their shaders...or something.

If you or anyone know how I can fix this plases let me know.
Thank you.
## Post #10
- Username: darkmatter78
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Jul 07, 2010 12:33 am
- Post datetime: 2010-12-11T09:00:52+00:00
- Post Title: Using 3D Ripper DX with Dolphin 2.0?

> Reply from nattakorn
>
> Nobby wrote:
As for the textures, they seem to rip find.



If you or anyone know how I can fix this plases let me know.
Thank you.

Hi. Did you ever get a solution to this problem? I should say that I just now tried with the pc game and got the same UV issues with the character only, as well. So it is not Dolphin. I have noticed this problem with several games and mainly occurring with characters, not other objects. It is a real pain to have to recreate each UV in Max. Almost more time than it is worth, with a few exceptions.

And Nobby. Your explanation was the best I have heard and helped a lot in my understanding of it but it does not apear to be the issue here. Perhaps in a few games, but the majority of problems I run into is UV based only. You say you never have a UV problem? Could you possibly try with the Incredible Hulk pc game or Marvel Ultimate Alliance? Or Wall-E? If you do not have them I can go back and make a list of what has this problem. It is often, though. At LEAST 33% of all attempts result in this. Thanks to all.
