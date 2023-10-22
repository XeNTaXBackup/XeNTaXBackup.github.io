## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-11-17T23:25:52+00:00
- Post Title: (PC) Mega Man X8 WSX/WPG

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-11-20T17:24:04+00:00
- Post Title: (PC) Mega Man X8 WSX/WPG

Looking into it more, seems a downside is that the bones are not given names... also seems to contain more than one model per WSX, like sub-models for projectiles. Though I am very certain of these being models.
## Post #3
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-11-26T13:22:11+00:00
- Post Title: (PC) Mega Man X8 WSX/WPG

Closeup of his in-game model:

[http://i148.photobucket.com/albums/s1/N ... vile3d.jpg](http://i148.photobucket.com/albums/s1/Nemomon/Megaman/Artwork/x8_vile3d.jpg)

And a WSX may actually contain several models. Not just one. The main character model, texture association, and sub-models. I also still believe there are also animations in there too and a bone index.
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-11-28T05:53:46+00:00
- Post Title: (PC) Mega Man X8 WSX/WPG

Ordered game. I'll help you take a look at this after dec. 10 if no one else does it in the meantime.
## Post #5
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-11-28T10:34:00+00:00
- Post Title: (PC) Mega Man X8 WSX/WPG

Oh hey, thanks! That would be very appreciated.
## Post #6
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-11T06:33:04+00:00
- Post Title: (PC) Mega Man X8 WSX/WPG

OK, time to look at this now... any information that you already have about the locations of the textures would give me a head start on that. I think you said some textures were weird... the locations on those would be nice too. Other than that... time to get started.
## Post #7
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-12-12T00:28:01+00:00
- Post Title: (PC) Mega Man X8 WSX/WPG

Textures are in the opk folder sub-folder wrg. The wrg files are mostly raw 32-bit, but some have what seems to be colormaps and are like 8-bit textures.
## Post #8
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-13T14:48:16+00:00
- Post Title: (PC) Mega Man X8 WSX/WPG

Yep, 8-bit textures. Most WPG files contain multiple textures. Each image is prefaced with a 0x12-byte header. So if you can read a header without hitting EOF, read another image, etc. Palette is 3*256 bytes and in BGR order. Bitmap palettes use RGBQUAD so you have to append a 0 alpha. The first DWORD in the header determines if file is 8-bit or 32-bit. Easy peazy. Time to work on the model format now.
## Post #9
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-12-13T17:30:10+00:00
- Post Title: (PC) Mega Man X8 WSX/WPG

Great! but what did you use to convert them? As far as I could tell, TiledGGD cannot view them properly. Only with the 32-bit ones it can.
## Post #10
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-13T17:39:26+00:00
- Post Title: (PC) Mega Man X8 WSX/WPG

C++. TileGGD can't do it because of the 24-bit palette table; it probably needs the palette to be 32-bits for it to recognize it as a bitmap. Texture extractor posted below. The model format is quite a bit harder... every section in a model file uses a 0x6C to mark it and can't really find cues to get to the actual data. There is also no obvious index buffer but I do see obvious vertex formats... going to try dumping hard-coded vertices sometime later.

EDIT: Xentax won't let me attach even a 20 KB file at the moment ha ha ha. Will try again later.
EDIT: There we go. Just place exe in game root directory and run it and wait. Written for PC version of the game.
[ripper.7z](https://xentaxbackup.github.io/file/4895_ripper.7z)
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-14T04:00:31+00:00
- Post Title: (PC) Mega Man X8 WSX/WPG

Post a couple more models.

I'm guessing the third section (in the order they are referenced in the offset table) is the largest and probably contains the mesh info?

Each section has a very similar structure though o.O
## Post #12
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-12-14T09:13:48+00:00
- Post Title: (PC) Mega Man X8 WSX/WPG

The contents of this post was deleted because of possible forum rules violation.
## Post #13
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-12-17T03:24:40+00:00
- Post Title: (PC) Mega Man X8 WSX/WPG

the wsx filesystem looks simple
LONG: Count
LONG: Data Size
LONG: Offsets (Loop*Count)

I broke down wsx and examined the parts individually.. each part is different, and I haven't found out what all the components do.

anyway I did find the geometry component, holding the vertex info. but I'm not sure how to read through the file yet. just as a test I hardcoded the offset and imported the vertex data.



in file:PL_A.wsx @ 0xFBE6, each vertex definition is 60bytes long. XYZ,nX,nY,nZ,N,U,V
at that particular offset the count was 6974, I need to back trace the number to see where the geometry definitions are stored.
## Post #14
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-17T03:30:24+00:00
- Post Title: (PC) Mega Man X8 WSX/WPG

Cool. When I have ssome time I'll see if I can use your info to finish up an extractor. So many games so little time . Triangles in the legs look a little off. Was there an index buffer?
## Post #15
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2012-01-02T12:08:57+00:00
- Post Title: (PC) Mega Man X8 WSX/WPG

pretty good! Some mess with a few triangles as howfie said but is a great deal of progress on the model format. Glad to see the UV mapping there as well.

Wonder what is causing those messy triangles? But is greatly intact overall! Hopefully will be able to read the data. I still believe some of the elements is animation data and a kind of bone system but the bones aren't named like most games, just values, or the names are Japanese... but that wouldn't be very Capcom-like. But first things first...
## Post #16
- Username: sidhi
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 10, 2013 11:35 pm
- Post datetime: 2013-05-13T02:25:28+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

I manage to grab the texture from wpg using your ripper.zip

things that left are how to extract the 3D model from the WSX ??? How can you got that nice result ???
## Post #17
- Username: aaiki14
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 09, 2011 5:05 pm
- Post datetime: 2014-08-22T13:52:57+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

> Reply from mariokart64n
>
> the wsx filesystem looks simple
LONG: Count
LONG: Data Size
LONG: Offsets (Loop*Count)

I broke down wsx and examined the parts individually.. each part is different, and I haven't found out what all the components do.

anyway I did find the geometry component, holding the vertex info. but I'm not sure how to read through the file yet. just as a test I hardcoded the offset and imported the vertex data.



in file:PL_A.wsx @ 0xFBE6, each vertex definition is 60bytes long. XYZ,nX,nY,nZ,N,U,V
at that particular offset the count was 6974, I need to back trace the number to see where the geometry definitions are stored.

how did you get and extract axl mesh?
## Post #18
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-01T16:20:30+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

I was able to make a tool for this. It's almost done.



UVs and textures also work.
## Post #19
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-02T16:18:27+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

This is the tool for Mega Man X8 Models

First use it on WSX file, you'll get all files split, including animations and whatever is there.

Then, use the same tool on the extracted files and it will only convert those which are models to OBJ files.

Or just run batch file to try and convert them all to OBJ.
[Megaman_x8.rar](https://xentaxbackup.github.io/file/11000_Megaman_x8.rar)
## Post #20
- Username: GhostTrain
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Nov 14, 2014 12:32 am
- Post datetime: 2016-06-15T19:11:22+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

(me being the ninja getting knocked down)

ok so. For someone less brainy like me, how can I fix the way certain textures are displayed?

The tools work great, but the textures, while they appear correct in their thumbnail image, 
if I open them up in any photoshop or xnview some are transparent and bright green and/or a little distorted.
Is there way to get those textures looking correct like their thumbnails do?



LookitThis.jpg (188.18 KiB) Viewed 184 times



(To be more specific the images look ok in Explorer, but not in image editors, viewers or 3D apps)
## Post #21
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-15T19:28:30+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

> Reply from GhostTrain
>
> The tools work great, but the textures...

Yes, these are not exactly correct BMP files. I was opening them with paint and saving back to correct this.
## Post #22
- Username: kinlyki
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Jun 21, 2015 12:36 am
- Post datetime: 2016-06-15T23:53:51+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

So I drag and dropped a wsx file into the tool and got a bunch of .dat files.

How do I view them?
## Post #23
- Username: GhostTrain
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Nov 14, 2014 12:32 am
- Post datetime: 2016-06-16T03:47:00+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

> Reply from daemon1
>
> GhostTrain wrote:The tools work great, but the textures... 

Yes, these are not exactly correct BMP files. I was opening them with paint and saving back to correct this.

Oh! Perfect! That did the trick.  Best fix ever. Thanks
## Post #24
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-16T15:11:16+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

> Reply from kinlyki
>
> So I drag and dropped a wsx file into the tool and got a bunch of .dat files.

How do I view them?

> Reply from daemon1
>
> This is the tool for Mega Man X8 Models

First use it on WSX file, you'll get all files split, including animations and whatever is there.

Then, use the same tool on the extracted files and it will only convert those which are models to OBJ files.

Or just run batch file to try and convert them all to OBJ.
## Post #25
- Username: kinlyki
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Jun 21, 2015 12:36 am
- Post datetime: 2016-08-20T13:52:31+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

Does anyone know where the models for those gems things that fly around Lumine's first form are?
## Post #26
- Username: UltimateSora
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Jun 24, 2011 2:56 am
- Post datetime: 2016-12-04T18:26:38+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

Hi, for some reason I'm unable to extract anything from the WSX files. I'm dragging the WSX onto the exe but it just crashes. (Image below)

[https://drive.google.com/file/d/0B8PW-L ... sp=sharing](https://drive.google.com/file/d/0B8PW-LpZ2h9MWDhCd3pMaTUzWWs/view?usp=sharing)
## Post #27
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-04T18:47:26+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

Access denied. Put this into another folder (not program files) and run. Or run cmd as admin
## Post #28
- Username: UltimateSora
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Jun 24, 2011 2:56 am
- Post datetime: 2016-12-04T21:07:26+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

> Reply from daemon1
>
> Access denied. Put this into another folder (not program files) and run. Or run cmd as admin
I've tried putting both the exe and a wsx into other folders such as Documents and C:\Folder but I get the same crash and there's no change when using the command line either.

[https://drive.google.com/file/d/0B8PW-L ... sp=sharing](https://drive.google.com/file/d/0B8PW-LpZ2h9MSkJWT1U0N0hrMms/view?usp=sharing)
## Post #29
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-05T07:41:35+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

Configure your system so the tool can open the file. Because still access denied.
## Post #30
- Username: UltimateSora
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Jun 24, 2011 2:56 am
- Post datetime: 2016-12-05T20:17:42+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

Oh I figured it out, the files were set to Read Only. Thanks.
## Post #31
- Username: kinlyki
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Jun 21, 2015 12:36 am
- Post datetime: 2016-12-20T06:42:44+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

daemon, are you sure the program converts all models?
There seems to be quite a few files that are never converted.
[http://i.imgur.com/zGwr965.png](http://i.imgur.com/zGwr965.png)
1st one can be converted.
2nd cannot be converted even though the format looks the same.
## Post #32
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-20T15:20:08+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

I DONT have the game. It worked on all files I had (people gave me). I have no other files.
## Post #33
- Username: kinlyki
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Jun 21, 2015 12:36 am
- Post datetime: 2016-12-21T00:02:20+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

These are two files inside as examples.

Could you make a plugin for Noesis to open up the .dat files instead of a program that just converts it to obj? Or is that impossible?
BTW, if I wanted to make a .bat file that makes the program run on all files in a folder, what code do I write?
[st01.rar](https://xentaxbackup.github.io/file/12098_st01.rar)
## Post #34
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-21T16:39:02+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

> Reply from kinlyki
>
> These are two files inside as examples.

Could you make a plugin for Noesis to open up the .dat files instead of a program that just converts it to obj? Or is that impossible?
BTW, if I wanted to make a .bat file that makes the program run on all files in a folder, what code do I write?

I can make a plugin, but I don't have time for this. Why don't you like OBJ? 

As for these models, they are some weapons. This is a version of tool for them.
[Megaman_x8_static.rar](https://xentaxbackup.github.io/file/12102_Megaman_x8_static.rar)
## Post #35
- Username: kinlyki
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Jun 21, 2015 12:36 am
- Post datetime: 2016-12-21T17:27:19+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

I only asked for a plugin for Noesis because it would be easier to find which model I'm looking for before converting.
## Post #36
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-21T17:56:57+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

ok. make batch, and then use noesis on OBJ files.

google how to make batch files
## Post #37
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-21T21:43:24+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

> Reply from kinlyki
>
> if I wanted to make a .bat file that makes the program run on all files in a folder, what code do I write?

here you go this works  

```
for %%G in (*.dat) do Megaman_x8_static %%G
```

this one runs Megaman_x8_static.exe, 
you'll need to change that or make another bat file for Megaman_x8.exe i guess.
## Post #38
- Username: zheneq
- Rank: advanced
- Number of posts: 43
- Joined date: Fri Jul 17, 2015 1:09 pm
- Post datetime: 2016-12-23T14:59:44+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

I actually wrote a Noesis plugin for wsx/wpg a while ago. It's a bit of a mess but should be working fine.

[https://github.com/Zheneq/Noesis-Plugins](https://github.com/Zheneq/Noesis-Plugins)
## Post #39
- Username: kinlyki
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Jun 21, 2015 12:36 am
- Post datetime: 2016-12-24T10:14:57+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

Isn't a .wsx file an archive with multiple models in it? how does that work?
## Post #40
- Username: zheneq
- Rank: advanced
- Number of posts: 43
- Joined date: Fri Jul 17, 2015 1:09 pm
- Post datetime: 2016-12-24T12:33:16+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

Noesis supports multimodel files. You can navigate to the model you need (press 3 skeletons button to go to the next one) and then 'Export from preview'.
## Post #41
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2016-12-27T00:07:41+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

You say it is a bit of a mess, but it is pretty much complete and vastly superior to simply grabbing the geometry and making a static OBJ. I'd say this format was 100%, so both a congrats and thanks are in order. I mean, holy hell, you even have animations!
## Post #42
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-27T15:31:25+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

> Reply from Darkfox
>
> You say it is a bit of a mess, but it is pretty much complete and vastly superior to simply grabbing the geometry and making a static OBJ.

To the time I got to this thread all your posts (with data) were already deleted, so I don't know what you needed and why.

I must say, you can't just "simply grab" the geometry in this game.

This is your thread and you must know it. Your question existed from 2011 and no one was able to build the geometry, everybody failed. Remember those " messy triangles? " The way they store the geometry is really weird. That's why I think he said that it's "a bit of a mess".
## Post #43
- Username: zheneq
- Rank: advanced
- Number of posts: 43
- Joined date: Fri Jul 17, 2015 1:09 pm
- Post datetime: 2016-12-27T22:41:15+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

No, I'm just saying that the code is a mess. I wanted to polish it up a little more before publishing... and forgot about it for several months. Well, maybe later I'll find time for that. =)

Messy triangles? There is nothing weird there, just some meshes are stored as plain triangles, and some as tri-strips. That's what's wrong with Axl's mesh above - tri-strip data is interpreted as plain tris.

Now I wonder why so many people need models from such an old game
## Post #44
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-28T04:24:01+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

> Reply from zheneq
>
> Messy triangles? There is nothing weird there
If you're 3d-graphics specialist, maybe. But if you're just converting models for fun, like most people here, this is not an obvious thing. All games nowadays use face indices. Not tristrips. Also there are many ways of building a tri-strip. 

> Reply from zheneq
>
> That's what's wrong with Axl's mesh above - tri-strip data is interpreted as plain tris.
No. In that case he'd end up with a model with only a few faces, and many many holes. He definitely tried to build the tristrip, but failed. Its not an easy thing to do when you never seen it before.
## Post #45
- Username: zheneq
- Rank: advanced
- Number of posts: 43
- Joined date: Fri Jul 17, 2015 1:09 pm
- Post datetime: 2016-12-28T05:57:08+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

> Reply from daemon1
>
> No. In that case he'd end up with a model with only a few faces, and many many holes.
Yep, that's right. I thought the game didn't use tri-strips much. But since it doesn't use face indices, plain tris are too excessive.

> Reply from daemon1
>
> If you're 3d-graphics specialist, maybe. But if you're just converting models for fun, like most people here, this is not an obvious thing. All games nowadays use face indices. Not tristrips.
Well... Ok. I am no 3d specialist but I studied the basics of DirectX/OpenGL once upon a time. And I didn't know this thing was kind of outdated.

> Reply from daemon1
>
> Also there are many ways of building a tri-strip.
Really? I know only one.
## Post #46
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-28T16:41:27+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

> Reply from zheneq
>
> And I didn't know this thing was kind of outdated.

Yes, among dozens of games I researched, this megaman is ONLY one using strips.

> Reply from zheneq
>
> daemon1 wrote:Also there are many ways of building a tri-strip.
Really? I know only one.

Another one is instead of "degenerated" triangles, use some kind of "stop flag" to mark the end of strip and start a new one. For example, 0xFFFF. This was actually the method I found here on xentax as an example of tristrip. This way the strip will be shorter.
## Post #47
- Username: zheneq
- Rank: advanced
- Number of posts: 43
- Joined date: Fri Jul 17, 2015 1:09 pm
- Post datetime: 2016-12-29T00:54:33+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

> Reply from daemon1
>
> Another one is instead of "degenerated" triangles, use some kind of "stop flag" to mark the end of strip and start a new one. For example, 0xFFFF. This was actually the method I found here on xentax as an example of tristrip. This way the strip will be shorter.
Thanks! Good to know.

What is really weird with this format is that it stores bone lookup indices in floats. I guess they used vertex color field or something for that purpose...
## Post #48
- Username: HorrorTroll
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 31, 2017 1:07 pm
- Post datetime: 2017-08-07T09:34:36+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

Sorry for bump but this is my Nightmare Zero mod, i was use HxD Hex Editor to change color Zero texture on PL_Z_ID_PL_001.wpg, PL_Z_L_ID_PL_001.wpg, PL_Z_WEP_ID_PL_001!





I give a download link on attachment, so you guy can test that! I was mod on Japan PC version, unknown English PC version can work or not!
[Nightmare Zero (Mod).rar](https://xentaxbackup.github.io/file/13173_Nightmare Zero (Mod).rar)
## Post #49
- Username: sahailaway
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 20, 2016 7:19 am
- Post datetime: 2017-08-07T14:30:15+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

________
## Post #50
- Username: Wanabey
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 31, 2017 4:04 pm
- Post datetime: 2017-09-01T07:06:52+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

Hi, I know that its been so long of this topic but I want to know how to reconvert the model to wsx / texture to wpg again?
## Post #51
- Username: lucasfera15
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Feb 14, 2018 3:32 am
- Post datetime: 2018-02-14T17:37:49+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

> Reply from sahailaway
>
> daemon1 was kinda right:
scrips are not enough to fix the models, On architecture/render animation stuff we are kinda accustomed to deal with those problems due the engines compability.
So using 3d design programs is possible fix the models:









Also is possible Rip the models from the other games like rockman x7:
And after a while fixing  (scales, nodes, faces, orientations.. etc etc ) this is the clean model of the glide armor

How do you rip the Booster forest stage?I have the game files and noesis,i have extracted many models,rigged characters,weapons etc,but i cant find a complete stage like booster forest,noahs park,i have only ripped SOME PARTS of gravity antonion stage...how do you get/find this model?
## Post #52
- Username: kinlyki
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Jun 21, 2015 12:36 am
- Post datetime: 2018-03-12T09:44:26+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

> Reply from sahailaway
>
> daemon1 was kinda right:
scrips are not enough to fix the models, On architecture/render animation stuff we are kinda accustomed to deal with those problems due the engines compability.
So using 3d design programs is possible fix the models:
Also is possible Rip the models from the other games like rockman x7:
And after a while fixing  (scales, nodes, faces, orientations.. etc etc ) this is the clean model of the glide armor
Could you rip Zero's and Axl's weapons from X7? I wanna see how they differ. But mostly, I want the V-Hangar.
## Post #53
- Username: Hyago
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 06, 2016 6:47 am
- Post datetime: 2019-02-22T12:13:02+00:00
- Post Title: Re: (PC) Mega Man X8 WSX/WPG

> Reply from zheneq ↑Fri Dec 23, 2016 10:59 pm at Fri Dec 23, 2016 10:59 pm
>
> 
I actually wrote a Noesis plugin for wsx/wpg a while ago. It's a bit of a mess but should be working fine.
https://github.com/Zheneq/Noesis-Plugins

It's amazing what you have done. To be able to easily view rigged models, textures and animations on Noesis is superb.
The best part is we can easily export those assets in a game engine.
If I knew about this some time ago, I'd create this [demo](https://www.youtube.com/watch?v=uMW2v5pd7t4) using this assets instead.
Thanks for the plugins!
