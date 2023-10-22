## Post #1
- Username: ChiLLf2d
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Nov 18, 2012 4:14 am
- Post datetime: 2013-04-05T01:27:43+00:00
- Post Title: [Request] Need help to understand this .ba animation file...

Hi guys, recently I have been working on Last Chaos mmo side project, I am stuck on the .ba animation files of this game. I found similar script for .ba animation files for another game and it is on Xentax forum, here is the link [viewtopic.php?f=16&p=38957](http://forum.xentax.com/viewtopic.php?f=16&p=38957). It would really help me to go on further with this project, also I have question about the .bm files for this game, I am able to open the model files for this game but apparently there are some _TAG_.bm files which are not open-able, if anyone can look on those as well would be really appreciated.

These .bm files are openable with Cinema 4D R12, I will attach a full folder of Healer class, you can see all the .bm files and .ba file with animations and the _TAG_ file.

link to download [http://www.mediafire.com/download.php?29gogqess1215zq](http://www.mediafire.com/download.php?29gogqess1215zq)


cheers
## Post #2
- Username: ChiLLf2d
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Nov 18, 2012 4:14 am
- Post datetime: 2013-04-06T21:57:01+00:00
- Post Title: [Request] Need help to understand this .ba animation file...

anyone?  the importer from Kingdom under fire are able to list .bm files but unable to open just says console error if someone can look into that, thanks!
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-04-09T09:19:34+00:00
- Post Title: [Request] Need help to understand this .ba animation file...

> Reply from ChiLLf2d
>
> anyone?  the importer from Kingdom under fire are able to list .bm files but unable to open just says console error if someone can look into that, thanks!What importer do you speak of? Is it a python file (*.py)?
Mesh format of hw_bd_000.bm seems to be fairly simple:
verts 3 floats, normals 3 floats, tex 2 floats
faces (2 byte indices)

[](http://www.pic-upload.de/view-18878244/hw_bd_000.bm.jpg.html)
## Post #4
- Username: ChiLLf2d
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Nov 18, 2012 4:14 am
- Post datetime: 2013-04-12T22:37:43+00:00
- Post Title: [Request] Need help to understand this .ba animation file...

if you go to the thread [viewtopic.php?f=16&p=38957](http://forum.xentax.com/viewtopic.php?f=16&p=38957) and see the attachment by Szkaradek123, he made an .blend file that imports .bm file 3D models and another .ba which imports 3D animation..... which are similar file types used in Last Chaos, .bm is used for 3D models, .ba is used for Animation but that .blend file does not seem to open models from Last Chaos and that is what I was trying to get at.... 


well honestly I can open models in C4D but I could not get any source to edit the .ba files for animation editing.... Last Chaos .ba file contains multiple animations in one file which trigger from their names, I want to be able to take those animations out and modify them... let say I wanted to duplicate one animation and be able to replace other... 

ex: one class .ba file contains  so_attk_01   so_attk_02 so_attk_03  and I want to completely get rid of so_attk_01 and replace so_attk_01 with so_attk_02,  I would need a tool to delete so_attk_01 from that .ba file and duplicate so_attk_02 then rename the copy to so_attk_01,   so when in game when character does so_attk_01 it is actually a copy of so_attk_02....

I just need a simple tool to edit the last chaos .ba file to be able to remove, copy, rename, and add the animations inside the .ba file... thanks ^^
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-04-13T00:31:45+00:00
- Post Title: [Request] Need help to understand this .ba animation file...

> Reply from ChiLLf2d
>
> I just need a simple tool to edit the last chaos .ba file to be able to remove, copy, rename, and add the animations inside the .ba file... thanks ^^TinyGuy is the one who should have the knowledge about this. You could try to contact him. 
His Last Chaos modelviewer shows animations.
The version v.0.80.0 can export DirectX files but as far as I can see there's no animation data/keys contained.
You might try a newer version. (I didn't try Model viewer 2013 because my Avira reported a virus. Maybe you'll find a clean download.)

edit: if there's no connection to TinyGuy and  never version don't allow editing the ba-file you could try it for yourself. At absolute offset 0x8 of hw.ba there's the animation count (DW, 0x85= 133). Changing it to 0x0A results in only 10 animation to be displayed by the modelviewer.

Then search for the animation headers (relative offsets):

```

00000   xx 00 00 00 21 00 00 00  44 61 74 61 5C 43 68 61   …...!...Data\Cha
00010   72 61 63 74 65 72 5C 48  65 61 6C 65 72 5C 68 77   racter\Healer\hw
00020   5F 61 5F 64 61 6D 2E 41  41 08 00 00 00 68 77 5F   _a_dam.AA....hw_
00030   61 5F 64 61 6D 2F 88 08  3D 10 00 00 00 00 00 00   a_dam/ˆ.=.......
00040   00 00 00 00 00 00 00 00  00 83 00 00 00 05 00 00   .........ƒ......
00050   00 42 69 70 30 31                                  .Bip01
```


xx should be 00 for all headers except the first one (it's 0x85, that's the low byte of the animation count DWORD and it's at relative offset 0 in the snippet so don't be confused. Name.AA is also different for the other 132 anims.)

Try to delete one animation in a hex ediitor (from start of one header to the succeeding one).
Change animation count to 0x84 (at absolute address 0x8).
Check whether the game accepts this modified hw.ba.

If so exchanging or overwriting anims should also be possible by moving blocks via hex edit.
(You can easily find the blocks by doing a search for ".AA")
## Post #6
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2013-04-13T06:41:10+00:00
- Post Title: [Request] Need help to understand this .ba animation file...

> Reply from ChiLLf2d
>
> These .bm files are openable with Cinema 4D R12, I will attach a full folder of Healer class, you can see all the .bm files and .ba file with animations and the _TAG_ file.

Hi ChiLLf2d, I am wondering how could you open the files in Cinema 4D R12!? 
There are tons of encrypted values inside the .bm file!?

As far as I know, the format is completely different form knigdom Under Fire?
## Post #7
- Username: ChiLLf2d
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Nov 18, 2012 4:14 am
- Post datetime: 2013-04-14T18:22:49+00:00
- Post Title: [Request] Need help to understand this .ba animation file...

Sorry I didn't clarify myself, I am able to open .bm files in C4D with "ChaosKit" released on Elitepvpers which allows you to import and export .bm files...   also there is a tool by Wizatek that allows the user to rename the animations in .ba file that's about it...
