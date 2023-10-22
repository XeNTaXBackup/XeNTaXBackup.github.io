## Post #1
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2016-10-30T23:47:12+00:00
- Post Title: Carmageddon Max Damage (.zad)

Hello

 I have a sample vehicle from the recently released "Carmageddon Max Damage" from steam port. I'd like to see if or how we could make a tool to turn the .zad file formate into something like an OBJ format. thank you for your time.

[https://www.mediafire.com/?ndxgi456c06w011](https://www.mediafire.com/?ndxgi456c06w011)
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-10-31T21:47:45+00:00
- Post Title: Carmageddon Max Damage (.zad)

The .zad file is a simple zip.
Inside there are a couple of files, MDL = 3D model, TDX = texture, and some other file types.

I only had a quick look at c_body.MDL, haven't converted the faces yet, vertices only:
## Post #3
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2016-10-31T22:34:31+00:00
- Post Title: Carmageddon Max Damage (.zad)

> Reply from herbert3000
>
> The .zad file is a simple zip.
Inside there are a couple of files, MDL = 3D model, TDX = texture, and some other file types.

I only had a quick look at c_body.MDL, haven't converted the faces yet, vertices only:

 that's fantastic. cause when I'd tried to rip with say ninja ripper the meshes were in several different peices and peicing them together would be a nightmare to say the least. and intel anylizer would not inject into the game so I had to go for the archive files. this helps me imensly thank you so so much.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-10-31T23:23:35+00:00
- Post Title: Carmageddon Max Damage (.zad)

there's some fiddeling required to get the submeshes but should go:



c_body-mdl.JPG (84 KiB) Viewed 133 times



I faced some odd behaviour of hex2obj which claimed to have unmatching
vertexcount/max faceindex count while in Strip mode although displaying they were equal.

As a workaround switch to noStr mode where you'll find the first submesh to end after 7998 face indices (roundabout).
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-31T23:50:46+00:00
- Post Title: Carmageddon Max Damage (.zad)

Noesis has native support for those *.tdx textures as "Stainless TDX Texture"
## Post #6
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-11-02T21:37:14+00:00
- Post Title: Carmageddon Max Damage (.zad)

I believe that the hierarchy of the models (and the relative position of the submodels) can be found in car.CNT.

c_body.MDL is only the chassis

@0xB2: face count = 23256 

struct face {
  int unknown; // always 0
  int index1;
  int index2;
  int index3;
}

@0x5AE36: vertex count = 23441

struct vertex {
  float x;
  float y;
  float z;
  float nx; // vertex normals, I guess
  float ny;
  float nz;
  float u;
  float v;
  float unknown;
  float unknown;
  byte unknown; // usually FF or 00
  byte unknown; // usually FF or 00
  byte unknown; // usually FF or 00
  byte unknown; // usually FF or 00
}



screenshot.jpg (162.53 KiB) Viewed 117 times
## Post #7
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2016-11-02T22:35:18+00:00
- Post Title: Carmageddon Max Damage (.zad)

> Reply from herbert3000
>
> I believe that the hierarchy of the models (and the relative position of the submodles) can be found in car.CNT.

c_body.MDL is only the chassis

@0xB2: face count = 23256 

struct face {
  int unknown; // always 0
  int index1;
  int index2;
  int index3;
}

@0x5AE36: vertex count = 23441

struct vertex {
  float x;
  float y;
  float z;
  float nx; // vertex normals, I guess
  float ny;
  float nz;
  float u;
  float v;
  float unknown;
  float unknown;
  byte unknown; // usually FF or 00
  byte unknown; // usually FF or 00
  byte unknown; // usually FF or 00
  byte unknown; // usually FF or 00
}
screenshot.jpg

 holy crap how the hell did you do that? cause I've been trying to decompile the MDL's ever since it was found to be a zip format and had no luck in working with them. but I think you are pretty right. but what program would work with .CNT file? anyways thanks for your work so far it means a lot.
## Post #8
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-11-03T06:09:07+00:00
- Post Title: Carmageddon Max Damage (.zad)

I (or rather we) should have googled the file format first 

As it turns out there's a program called [Flummery](http://www.carmageddon.com/forum/topic/26916) that can import Carmageddon files but unfortunately Max Damage isn't supported (yet).
However, I checked the source code of the [MDL](https://github.com/MaxxWyndham/ToxicRagers/blob/master/ToxicRagers/Stainless/Formats/sMDL.cs) and CNT formats and they are exactly the same except for the version byte in the file header.
## Post #9
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2016-11-03T07:46:31+00:00
- Post Title: Carmageddon Max Damage (.zad)

> Reply from herbert3000
>
> I (or rather we) should have googled the file format first 

As it turns out there's a program called Flummery that can import Carmageddon files but unfortunately Max Damage isn't supported (yet).
However, I checked the source code of the MDL and CNT formats and they are exactly the same except for the version byte in the file header.

 you make a good point.  then again with the precurser game "Carmageddon Rencarnation" we were supposed to get modding tools because stianless knows that their games (fun as they are) are kept alive thanks to the thriving modding community. but we never got those tools. my hope is with this reworked game that they just released to steam is that they finally give us those tools....unless the community beats them to it first.

 thanks for the information at this time I'll see what more I can do and try to post the results if I can make headway. thanks again for the post.
## Post #10
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-11-03T16:53:39+00:00
- Post Title: Carmageddon Max Damage (.zad)

Thanks for the background info. That sucks, hopefully they release those tools soon.

And here's a little update about the Flummery tool: Although I somehow managed to import the model, most of the textures just don't show up. I had to ignore some data that wasn't present in previous versions of the game. Obviously, saving the model back in the 'Max Damage' format also doesn't work.



screenshot.jpg (232.44 KiB) Viewed 99 times
## Post #11
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-11-03T18:48:18+00:00
- Post Title: Carmageddon Max Damage (.zad)

> Reply from herbert3000
>
> ...I checked the source code of the MDL and CNT formats and they are exactly the same except for the version byte in the file header.
yep if you go to 0x02 in the mdl and change the 03 to 02 (Reincarnation = version 6.2 ?)
you can open it in Noesis with the native Stainless mdl format plugin.  



c_body_mdl.png (147.28 KiB) Viewed 96 times



here is a bms script to change the mdl version from 6.3 to 6.2
save the output to a new folder and not in the same location as the source files
then afterwards you can overwrite the source files with the modified ones   
then you can open the mdl or cnt files with Noesis

```
get NAME filename
set MEMORY_FILE binary "\x45\x23\x02\x06"
log NAME 0 0x4 MEMORY_FILE
append
get SIZE asize
math OFFSET = 0x4
math SIZE - OFFSET
log NAME OFFSET SIZE
```
## Post #12
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2016-11-04T01:10:32+00:00
- Post Title: Carmageddon Max Damage (.zad)

this is why I love this forum so much. you guys actually try to help people and I honestly cannot thank you enough for the help with this and some of my other pet projects it really appreciated thank you guys.

 as to the recompiling back to max damage...I'd love that a lot if it can happen as I have fans of a 3d modeling project I was working on whom wanted me to port my models to this game and hopefully one day I can. this at least gets me to their models for study and understanding of what it will take to do that porting in the future and that means a lot guys so again thanks so much.
## Post #13
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-11-04T02:22:50+00:00
- Post Title: Carmageddon Max Damage (.zad)

Oh, I didn't expect them to actually change the format for Max Damage. I'll loosen up the minor version check in the next Noesis so you don't have to mess with the data to view it. If it's still loading fine with the version change, it sounds like nothing was meaningfully changed data or structure wise.

This support was actually done for the iOS Carmageddon game back in 2012, I was pretty amazed that they changed virtually nothing all the way through Reincarnation in the model format itself.
## Post #14
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2016-11-05T02:12:25+00:00
- Post Title: Carmageddon Max Damage (.zad)

> Reply from MrAdults
>
> This support was actually done for the iOS Carmageddon game back in 2012, I was pretty amazed that they changed virtually nothing all the way through Reincarnation in the model format itself.

As the old adage goes, "Don't fix it if it ain't broke."
## Post #15
- Username: addmixbb
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 27, 2021 5:05 pm
- Post datetime: 2021-03-27T09:35:02+00:00
- Post Title: Carmageddon Max Damage (.zad)

Is there any chance that .wad files work similarly? I'm having trouble finding a way to open one.
