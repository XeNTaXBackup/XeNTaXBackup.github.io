## Post #1
- Username: Trishty
- Rank: advanced
- Number of posts: 63
- Joined date: Mon Jul 05, 2010 9:37 pm
- Post datetime: 2012-08-03T18:40:47+00:00
- Post Title: [Tutorial] Ripping PS2 3D Model with picture

[](http://i771.photobucket.com/albums/xx353/trishty/tut.png)
Source: [http://www.spriters-resource.com/commun ... ?tid=20541](http://www.spriters-resource.com/community/showthread.php?tid=20541)
Special Thanks [o0DemonBoy0o](http://www.spriters-resource.com/community/member.php?action=profile&uid=16208)

Tool need:
[PCSX2](http://pcsx2.net)
[Texmod](http://code.google.com/p/texmod/)
[XnView](http://www.xnview.com/)
3D program

Click Picture to Enlarge
Setup PCSX2 with all the default plugins.
in the plugin settings set the GSdx renderer to "Direct3D9 (Software)"
[](http://i771.photobucket.com/albums/xx353/trishty/tut2.png)
Now save, exit, and open up Texmod
click on the folder icon and goto where you installed PCSX2 and select the pcsx2.exe
now go to logging mode and make sure Draw Control and Texture Info, Show Texture on upper left corner, and Replace Texture (with a green texture) are all checked.
on output format set the type that you want, I use TGA, and on Log with set the key that you want to capture the texture with, I use ENTER.

Alright now click run and open the game you want the model from. I will be using Dirge Of Cerberus.
[](http://i771.photobucket.com/albums/xx353/trishty/tut1.png)
Once you are at the point in the game where you want the model press SHIFT+F8 to capture the scene.
[](http://i771.photobucket.com/albums/xx353/trishty/tut3.png)
Now go to config in pcsx2 and select Video(GS)>Plugin settings and change the renderer to Direct3D9 (Hardware) and push ok. 
[](http://i771.photobucket.com/albums/xx353/trishty/tut4.png)
now use + and - to go through all of the textures. you can press * to go through the textures that are currently visible on the screen.
Each texture you find will be replaced with a transparent green one like this
[](http://i771.photobucket.com/albums/xx353/trishty/tut5.png)
Use XnView open .tga -> Image -> Swap RGB->BGR
[](http://i771.photobucket.com/albums/xx353/trishty/tut7.png)
Now go to where you installed PCSX2 and open the snaps folder. In there you will find a snapshot of the scene you captured, a .gs file and an obj file. open the obj in your 3d program. 
[](http://i771.photobucket.com/albums/xx353/trishty/tut8.png)
now when you open the model it should look really long like this
just select all of it and scale it by it's y-axis until it stars looking normal
[](http://i771.photobucket.com/albums/xx353/trishty/tut9.png)
[](http://i771.photobucket.com/albums/xx353/trishty/tut10.png)
now for some reason PCSX2 seems to capture everything twice so just select and delete what you find is extra or unnecessary.

you may have noticed that the about half the model if black. just select the polygons that are and flip it's normals. 
[](http://i771.photobucket.com/albums/xx353/trishty/tut11.png)
Now find an object and apply its texture. you may get something like this.

what you need to do is flip the UVs vertically and scale them down since they are way over sized. do this for every object and once you are done you should have everything complete
[](http://i771.photobucket.com/albums/xx353/trishty/tut12.png)
[](http://i771.photobucket.com/albums/xx353/trishty/tut13.png)
[](http://i771.photobucket.com/albums/xx353/trishty/tut14.png)
fin
[](http://i771.photobucket.com/albums/xx353/trishty/tut15.png)
## Post #2
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2012-08-03T22:54:37+00:00
- Post Title: [Tutorial] Ripping PS2 3D Model with picture

thanks for posting a little more detail on the UV flipping, I learn best by example...
## Post #3
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-08-04T01:34:59+00:00
- Post Title: [Tutorial] Ripping PS2 3D Model with picture

What PCSX2 revision did you use in ripping your model? I did manage to rip things off a Strawberry Shortcake game, but while it is intact, some of the faces end up getting culled.
## Post #4
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-08-04T01:37:21+00:00
- Post Title: [Tutorial] Ripping PS2 3D Model with picture

thanks a lot for great tutorial, very cool work.
## Post #5
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2012-08-04T09:18:53+00:00
- Post Title: [Tutorial] Ripping PS2 3D Model with picture

I was looking into it again, and I think that scaling to 0.3 is better than 0.5, it should take care of the small nuances

For the UV part, I got it flipped, but scaling seems to be an issue, is there a rough estimate that I can key in rather than clicking and dragging.  That approach seems to use a lot of my computers resources...


EDIT: AHHH nevermind, its just taking time moving things around...
## Post #6
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2012-08-04T20:07:06+00:00
- Post Title: [Tutorial] Ripping PS2 3D Model with picture

Here's some pictures that illustrate the issue I'm facing with this method,

I didn't flip normals on this guy yet, because it would seem like a lot of work for a distorted model.

Maybe its all about the camera angle; I'm not sure.  But this also apparently affects the UV layout.  It appears that after rescaling, that your map is still in the appropriate shape, however what I've found for my files are that some are rotated,tapered and frequently overlap. 
So i'm having to go through the slow process of re-organizing/mapping...I'll post process pictures of what I'm dealing with soon to help out anybody else having this issue
## Post #7
- Username: omfgpota
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Apr 13, 2010 9:52 pm
- Post datetime: 2012-08-05T12:03:35+00:00
- Post Title: [Tutorial] Ripping PS2 3D Model with picture

hi can i ask how you managed to get the obj files? because all i get are the bmp snapshot and the gs files. is there any option to turn on the obj? I tired this on persona 3 fes

thanks
## Post #8
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2012-08-05T15:38:11+00:00
- Post Title: [Tutorial] Ripping PS2 3D Model with picture

> Reply from omfgpota
>
> hi can i ask how you managed to get the obj files? because all i get are the bmp snapshot and the gs files. is there any option to turn on the obj? I tired this on persona 3 fes

thanks

well you need to select on the DX9 plugin on render DX9 (Software) then ingame shift+F8 , also what version of pcsx2 are you runing?
i have some problems in windows 7 x64 so i use and old revision that works , this a good alternative to 3Dripper and 3dvia.
## Post #9
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2012-08-05T15:44:50+00:00
- Post Title: [Tutorial] Ripping PS2 3D Model with picture

Please help.
## Post #10
- Username: Trishty
- Rank: advanced
- Number of posts: 63
- Joined date: Mon Jul 05, 2010 9:37 pm
- Post datetime: 2012-08-05T16:52:15+00:00
- Post Title: [Tutorial] Ripping PS2 3D Model with picture

> Reply from huckleberrypie
>
> What PCSX2 revision did you use in ripping your model? I did manage to rip things off a Strawberry Shortcake game, but while it is intact, some of the faces end up getting culled.

Maybe your game use backface culling same as FF7DC in my tutorial. I think you must rip front, back and combine it in 3d program

> Reply from omfgpota
>
> hi can i ask how you managed to get the obj files? because all i get are the bmp snapshot and the gs files. is there any option to turn on the obj? I tired this on persona 3 fes

thanks

I have try PCSX2 0.9.9.4891 and 0.9.8 official (tested in Win7 64bit and WinXP 32bit). Bolt of it work fine.
Really hope they can make PCSX2 rip model in T-pose

> Reply from youngmark
>
> http://img543.imageshack.us/img543/3892/53467947.png
Please help.
I found this [http://www.guildwarsguru.com/forum/texm ... 53495.html](http://www.guildwarsguru.com/forum/texmod-dohi-t10353495.html)
turn off your antivirus may help

PS: Have anyone know how to fix "not enough memory to create 84246 texture-vertices"?
I tried import .obj(10MB) to 3ds max11 in win7 64bit ram4G and i still got this error
## Post #11
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2012-08-05T23:40:48+00:00
- Post Title: [Tutorial] Ripping PS2 3D Model with picture

Voila, 
Here's what I've done so far, I still need fix some of the UV mapping on his forearms, but the layout was all sloppy and 6 forearms all piled on top of eachother slightly off, makes it hard to work with..



I'm using 0.9.8 on a win64 machine and things worked out fine...

> PS: Have anyone know how to fix "not enough memory to create 84246 texture-vertices"?
>
> I tried import .obj(10MB) to 3ds max11 in win7 64bit ram4G and i still got this error

Yeah I took a look at some of the DOC models and mine wouldn't run either...
## Post #12
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2012-08-06T17:07:26+00:00
- Post Title: [Tutorial] Ripping PS2 3D Model with picture

> Reply from Trishty
>
> 
PS: Have anyone know how to fix "not enough memory to create 84246 texture-vertices"?
I tried import .obj(10MB) to 3ds max11 in win7 64bit ram4G and i still got this error

I couldn't help notice that the model you got was from the model viewer, I believe the poly count on that is way higher than the in-game models,  I was able to import an in game model just fine on my system. One of the in-game models of vincent I have is down to 3,292 polys and 9,876 verts....
## Post #13
- Username: omfgpota
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Apr 13, 2010 9:52 pm
- Post datetime: 2012-08-06T23:43:51+00:00
- Post Title: [Tutorial] Ripping PS2 3D Model with picture

I tried it on pcsx2 v1.0.0 and yup i tried all dx9 versions both software and hardware, but to no avail i still capture only the gs file and the bmp. maybe it doesnt work on this game(p3fes) or this version i suppose? I'll try the version that you've said which is 0.9.8. 

thanks, i'll update you soon
## Post #14
- Username: Jecht
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jan 26, 2012 9:32 am
- Post datetime: 2012-08-11T19:11:18+00:00
- Post Title: [Tutorial] Ripping PS2 3D Model with picture

> Reply from omfgpota
>
> I tried it on pcsx2 v1.0.0 and yup i tried all dx9 versions both software and hardware, but to no avail i still capture only the gs file and the bmp. maybe it doesnt work on this game(p3fes) or this version i suppose? I'll try the version that you've said which is 0.9.8. 

thanks, i'll update you soon

It work on that one. I've probe by my self to and it work.
Sadly it not work in lower versions.



Now for the thing: IT JUST WHAT I WAS WAITING FOR YEARS!!! more for some games that they don't extract some models! Like the post I've done month ago of get the keyblades of the KH1, well. with this its plenty possible:







Include, it work plenty good with not lost of anything thing!

^GTA SA BTW


If any ask: I've done with the emu 9.8 on windows 32 AND XP OLD. include just have 256 of video (HALF) and just the enough CPU for make work just one video plugin on the list of the emu (the first one).


And it looks like it can get some scenery but get one big one it gonna be hell hard...
## Post #15
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2012-08-11T22:53:00+00:00
- Post Title: [Tutorial] Ripping PS2 3D Model with picture

I think the camera angle is a big factor for this method to work, I was trying this on Resident Evil:Code Veronica and even from an attempted straight angle, all I got was a weirdly scaled mode....  My guess is that for games where you can orient the camera will work well for this method...
## Post #16
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2012-08-14T21:12:45+00:00
- Post Title: Re: [Tutorial] Ripping PS2 3D Model with picture

Awesome! i will try it next weekend, Dirge of Cerberus! Here we go
## Post #17
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-09-01T23:16:39+00:00
- Post Title: Re: [Tutorial] Ripping PS2 3D Model with picture

How can I move in this program? I press every button on keybord and doesn't work o.o
## Post #18
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2012-10-22T07:37:22+00:00
- Post Title: Re: [Tutorial] Ripping PS2 3D Model with picture

I'm having trouble trying to apply textures to all those meshes. Can you make some kind of video tutorial on that?
## Post #19
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2012-10-25T03:56:32+00:00
- Post Title: Re: [Tutorial] Ripping PS2 3D Model with picture

it's ripping from the viewport, not the actual geometry from memory... IE, the VRAM not the RAM...

What this means is that the perspective you see in the 2D screen has actually been applied to the geometry itself. You must correct for the perspective, which can take a bit of work and a lot of intuition... For instance, look at the floor, usually this is made up of squares, but will appear to be trapezoids (tapered box shapes)... you have to use this to determine what the FOV is and use some sort of geometry modifier in your chosen 3D program to correct it... 

What can be even worse is if your game rip has curved lines all over the floor instead of straight ones... this means your FOV is not an angle but a curve, like a quadratic function, which you must correct for...

This is one of the main reasons ripping from an emulator is a pain... coupled with large amounts of probably failure to capture anything at all. I haven't tried the new texmod, but I'm hoping high and expecting nothing.
## Post #20
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2012-10-25T10:16:49+00:00
- Post Title: Re: [Tutorial] Ripping PS2 3D Model with picture

If only they make ps2 emulator using dolphin techniques.
## Post #21
- Username: Noxury
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Sep 26, 2015 12:37 am
- Post datetime: 2015-09-25T16:50:13+00:00
- Post Title: Re: [Tutorial] Ripping PS2 3D Model with picture

Hello Xentax-Forum,

Is there any way/tool then to:
- extract the mesh vertecies data from the rendering process,
- manipulate the actual camera by rendering in tweakable fov-values / orthographic mode to have not a disorted 3d model?
