## Post #1
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-08-31T10:18:18+00:00
- Post Title: PS3 Hyperdimension Neptunia MKII

Lightwave LSCRIPT generator. Only model and UVs are supported.
Couldn't find data where UV maps need to be offset and mirrored (as with the dragon), so you will have to do it yourself for the few models where it needs to be done.

Directions:
0.) must have visual studio 2010 CRT installed (or you must recompile with another compiler yourself).
1.) copy ism2 files and texture directory with TID files in it to somewhere safe.
2.) place exe inside where ism2 files are. Do not run this program with any ism2 files from the motion directory, animation is not supported.
3.) run exe.
4.) load generated LS files in lightwave.
5.) convert to whatever format you like.
6.) manually apply textures (program will convert TID files to DDS).
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-08-31T19:22:00+00:00
- Post Title: PS3 Hyperdimension Neptunia MKII

Bug fix + Sample
## Post #3
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-09-01T00:18:53+00:00
- Post Title: PS3 Hyperdimension Neptunia MKII

wow, good job man. haven't seen much done with lightwave before, I didnt know it had a scripter
## Post #4
- Username: 652845095
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 31, 2011 12:22 pm
- Post datetime: 2011-09-02T07:40:58+00:00
- Post Title: PS3 Hyperdimension Neptunia MKII

which folder should i put these into？i’m a complete noob at lightwave,thanks!
[11.jpg](https://xentaxbackup.github.io/file/4681_11.jpg)
## Post #5
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-09-02T08:38:18+00:00
- Post Title: PS3 Hyperdimension Neptunia MKII

Don't use that one unless you want to look at the C++ source code.
Use the file in the second post.
[Then watch this video.](http://www.youtube.com/watch?v=o4ITTCF83w4)
## Post #6
- Username: 652845095
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 31, 2011 12:22 pm
- Post datetime: 2011-09-02T09:03:44+00:00
- Post Title: PS3 Hyperdimension Neptunia MKII

alright I see，but i get this error....maybe something wrong with the software version? LW 10 win32, could u pls post the download link of ur current use version? thanks.
[111.jpg](https://xentaxbackup.github.io/file/4682_111.jpg)
## Post #7
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-09-02T09:29:14+00:00
- Post Title: PS3 Hyperdimension Neptunia MKII

I'm using the same version. I have no download link; I actually own the retail boxed version of it that comes with 2 dvds and a black usb dongle with a green light.
I would first try moving the directory out of the directory that contains kanji.
If that doesn't work, I would try the discovery edition (I took out my dongle and it will still run and load the model, it just won't save it).
If that doesn't work, post your LS file here and I will take a look at it. It should load the first character model fine. I tested with the first 50 or so character models already.

BTW, what program did you use to extract the files from the big archive file? Also, why is the ls file in the TEXTURE directory?
Also, don't run the program with the MOTION and SCOPE directories present; delete them.
## Post #8
- Username: 652845095
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 31, 2011 12:22 pm
- Post datetime: 2011-09-02T09:44:29+00:00
- Post Title: PS3 Hyperdimension Neptunia MKII

finally i made it! yeah is the kanji's problem.i just put the model and tex files all together,anyway thanks a lot...now i need to export them into max or maya, i extracted the big archive file with the BMS? maybe...i have to check it from my own computer at home.
## Post #9
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-09-02T10:02:39+00:00
- Post Title: PS3 Hyperdimension Neptunia MKII

cool. no problem.
File > Export > FBX and you should be good to go in max or maya now.
## Post #10
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-09-02T23:19:12+00:00
- Post Title: PS3 Hyperdimension Neptunia MKII

Bug fix: Should now work with level maps as well.
Bug fix: Some models (enemies) require multiple texture maps.
## Post #11
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-09-20T01:10:38+00:00
- Post Title: PS3 Hyperdimension Neptunia MKII

Now with weights and joints. Animations are coming soon but won't be able to make it bone-based since the game appears to use infinite-length bones which is not something easily scripted in lightwave and there is no bone orientation or length data in the model format. The animation files are really easy to figure out, and just contain keyframes along with joint translation, rotation, and scale parameters (see generated text files). Is there another modeler other than lightwave that works with zero or infinite-length bones that simply just transform the weight-mapped points using local joint axes?
## Post #12
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2011-09-20T13:06:00+00:00
- Post Title: PS3 Hyperdimension Neptunia MKII

Great work there howfie. Thank you.
I'm having a problem getting the bones.
I load the model fine but when I try to load the bones I get the error Script type "generic" differs from architecture.
I may be doing something wrong, I don't know much about lightwave.
## Post #13
- Username: daisuki
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Mar 03, 2011 1:12 pm
- Post datetime: 2011-09-20T15:05:33+00:00
- Post Title: PS3 Hyperdimension Neptunia MKII

You just run the Layout then you can loading the bones.
## Post #14
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2011-09-20T15:27:35+00:00
- Post Title: PS3 Hyperdimension Neptunia MKII

> Reply from daisuki
>
> You just run the Layout then you can loading the bones.
Oh, got it. Thank you.
## Post #15
- Username: kotakoni
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 09, 2011 11:20 am
- Post datetime: 2011-12-13T07:10:23+00:00
- Post Title: PS3 Hyperdimension Neptunia MKII

This is a nice idea, but I can't even get all of the models out. I've got a later copy of the game.
## Post #16
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-13T07:54:24+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

If you have the limited edition, we need to see some sample files. What files are in the game's root directory? CPK? If so, it's the same and you must use HCS's CPKEXTRACT tool to extract the ISM2 files. Also, for a PS3, you must know how to dump and unencrypt PS3 files. Check psx-scene for more info. There are also less honorable options if desperate. Figure it out.
## Post #17
- Username: kotakoni
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 09, 2011 11:20 am
- Post datetime: 2011-12-13T21:52:16+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

> Reply from howfie
>
> If you have the limited edition, we need to see some sample files. What files are in the game's root directory? CPK? If so, it's the same and you must use HCS's CPKEXTRACT tool to extract the ISM2 files. Also, for a PS3, you must know how to dump and unencrypt PS3 files. Check psx-scene for more info. There are also less honorable options if desperate. Figure it out.
I've tried to do this, and I even have a computer that allows BDs to be ripped/extracted. I've tried a ton of PS3 extract tools already, but it just doesn't want to work. I've basically become desperate, because I've gone through so much already to extract the models, but nothing's worked so far. I've even requested that people rip them for me, but to no avail.
## Post #18
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-13T22:30:03+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

I know I saw your post on the tr forum. What version of the game do you have. It is not possible for them to haved locked it due to my extractor. I think the limited release was already out. Need screen capture of what's in your ps3game directory where all the files are.
## Post #19
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-13T22:32:30+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

I also think aluigi has an updated script to handle large cpk files.
## Post #20
- Username: kotakoni
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 09, 2011 11:20 am
- Post datetime: 2011-12-14T02:38:44+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

> Reply from howfie
>
> I also think aluigi has an updated script to handle large cpk files.
I'll try this script before going any further. I'm truly desperate to get these models. ;_; Especially Uni, Neptune, Black sister, and Purple Sister.
## Post #21
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2012-02-24T18:54:28+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

Apologies for the two-month bump, but I do feel there are a few things that should be looked into.

1. In the "Chara" folder -- 022, 023, 027, 032, 052, 057, 087, 088 and 159 don't convert with the latest program (but do with the older one), and give the following error:

```
An error occurred while reading the file.
```

Those are the only things (other than the maps, which I haven't tested yet) that don't export using the script.

2. Is it just me, or do the bones with no rigging applied to them make the rigging screwed up in Layout (and when exporting them to an FBX file)? Manually removing the unrigged bones from the *_bones.ls file seems to fix that problem, which is quite unusual.

3. The "brow_00", "eyelid_00", "mouth_00" and "pupil_00" textures are really, really screwy. Any way to get them to show up properly? Best I've been able to get is something like this:
## Post #22
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-24T20:19:40+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

Yes,some of the textures are screwy. I never was able to figure out why but I've been meaning to go back and redo all of the games I've ripped. This was like the second game I ripped and it's not as complete as I want it to be. My new ripper now exports directly to lwo for which I am testing it with onechanbara. I am far from home and only have access to blender on a laptop that only supports opengl 1.2 so I can't look into the problems at least until saturday.
## Post #23
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2012-02-28T19:18:18+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

((This post had a link to a texture file from the game, but it got trimmed.))
## Post #24
- Username: User1608
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 31, 2011 3:55 am
- Post datetime: 2012-03-08T21:07:46+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

Is there any chance of converting the other .tid images (like the character sprites used in the status menu)?
## Post #25
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2012-03-09T02:54:41+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

> Reply from User1608
>
> Is there any chance of converting the other .tid images (like the character sprites used in the status menu)?They seem to be just 32-bit RGBA images, which you can view (with the right settings) in a program such as TiledGGD.
## Post #26
- Username: User1608
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 31, 2011 3:55 am
- Post datetime: 2012-03-09T10:30:40+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

> Reply from RandomTBush
>
> User1608 wrote:Is there any chance of converting the other .tid images (like the character sprites used in the status menu)?They seem to be just 32-bit RGBA images, which you can view (with the right settings) in a program such as TiledGGD.

You're right. Thanks a bunch!
## Post #27
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2012-03-23T00:08:08+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

This was NOT fun to repair.

Before:



After:


Neptune's pupil textures, unscrambled... without its alpha channel because of the way I did so (manually in Paint Shop Pro 7, took me a good two hours). Now I just need a way to both explain how it's done, and find a program or whatever to unscramble those bloody textures because I really don't want to waste my time doing so manually... 

(EDIT: Oh, god. I just realized how the textures are stored... Heavy Weapons Guy was right -- it is just stacking! Basically, stack the image as 2x2 tiles, then 4x4 tiles, then 8x8, then 16x16, 32x32, 64x64, 128x128, 256x256 and finally 512x512! Now how would I go about converting that easily...?)

(EDIT 2: So, yeah. The bytes need to be converted from this:

```
10 11 12 13 14 15 16 17 18 19 1A 1B 1C 1D 1E 1F
20 21 22 23 24 25 26 27 28 29 2A 2B 2C 2D 2E 2F
30 31 32 33 34 35 36 37 38 39 3A 3B 3C 3D 3E 3F
40 41 42 43 44 45 46 47 48 49 4A 4B 4C 4D 4E 4F
50 51 52 53 54 55 56 57 58 59 5A 5B 5C 5D 5E 5F
60 61 62 63 64 65 66 67 68 69 6A 6B 6C 6D 6E 6F
70 71 72 73 74 75 76 77 78 79 7A 7B 7C 7D 7E 7F
80 81 82 83 84 85 86 87 88 89 8A 8B 8C 8D 8E 8F
90 91 92 93 94 95 96 97 98 99 9A 9B 9C 9D 9E 9F
A0 A1 A2 A3 A4 A5 A6 A7 A8 A9 AA AB AC AD AE AF
B0 B1 B2 B3 B4 B5 B6 B7 B8 B9 BA BB BC BD BE BF
C0 C1 C2 C3 C4 C5 C6 C7 C8 C9 CA CB CC CD CE CF
D0 D1 D2 D3 D4 D5 D6 D7 D8 D9 DA DB DC DD DE DF
E0 E1 E2 E3 E4 E5 E6 E7 E8 E9 EA EB EC ED EE EF
F0 F1 F2 F3 F4 F5 F6 F7 F8 F9 FA FB FC FD FE FF
```


to this:

```
01 03 09 0B 11 13 19 1B 41 43 49 4B 51 53 59 5B
04 06 0C 0E 14 16 1C 1E 44 46 4C 4E 54 56 5C 5E
05 07 0D 0F 15 17 1D 1F 45 47 4D 4F 55 57 5D 5F
20 22 28 2A 30 32 38 3A 60 62 68 6A 70 72 78 7A
21 23 29 2B 31 33 39 3B 61 63 69 6B 71 73 79 7B
24 26 2C 2E 36 36 3C 3E 64 66 6C 6E 74 76 7C 7E
25 27 2D 2F 35 37 3D 3F 65 67 6D 6F 75 77 7D 7F
80 82 88 8A 90 92 98 9A C0 C2 C8 CA D0 D2 D8 DA
81 83 89 8B 91 83 99 9B CA C3 C9 CB D1 D3 D9 DB
84 86 8C 8E 94 96 9C 9E C4 C6 CC CE D4 D6 DC DE
85 87 8D 8F 95 97 9D 9F C5 C7 CD CF D5 D7 DD DF
A0 A2 A8 AA B0 B2 B8 BA E0 E2 E8 EA F0 F2 F8 FA
A1 A3 A9 AB B1 B3 B9 BB E1 E3 E9 EB F1 F3 F9 FB
A4 A6 AC AE B4 B6 BC BE E4 E6 EC EE F4 F6 FC FE
A5 A7 AD AF B5 B7 BD BF E5 E7 ED EF F5 F7 FD FF
```


in order for those textures to be proper, with one "byte" referencing to a pixel (4 bytes -- ARGB).)

(EDIT 3: And [here's the same texture I showed earlier](http://img.photobucket.com/albums/v336/RandomTalkingBush/HDNMk2-GustEyelidFixed.png), now with 100% less jumble.)
## Post #28
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-03-27T02:32:00+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

wow that is one fucked up texture format lol. i am currently working on the USA version of this game now. there are a few more texture formats in this game than in the JAP version. these messed up ones are of type 0x54494487. i'll see what i can do.
## Post #29
- Username: RandomTBush
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-27T07:20:46+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

> Reply from MrAdults
>
> One of the most common forms of "swizzling" (twiddling!) you'll find comes from storing pixels or blocks in Morton coordinates.

```

def registerNoesisTypes():
	handle = noesis.register("Test hack", ".tid")
	noesis.setHandlerTypeCheck(handle, noeCheckGeneric)
	noesis.setHandlerLoadRGBA(handle, tidLoadRGBA)
	return 1

def tidLoadRGBA(data, texList):
	if noesis.getAPIVersion() < 35:
		print("ERROR: This script is not compatible with your version of Noesis! UPGRADE!")
		return 0

	w = noeUnpack(">i", data[68:72])[0]
	h = noeUnpack(">i", data[72:76])[0]
	data = data[128:]
	untwid = bytearray()
	for x in range(0, w):
		for y in range(0, h):
			idx = noesis.morton2D(x, y)
			untwid += data[idx*4:idx*4+4]

	untwid = rapi.imageDecodeRaw(untwid, w, h, "a8r8g8b8")
	texList.append(NoeTexture("hacktex", w, h, untwid, noesis.NOESISTEX_RGBA32))
	return 1

```


Fancy that.
## Post #30
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-03-27T07:28:15+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

awesome. thanks. i will add that to my library... a fixed version of my texture extractor ought to be ready in a bit... man, why do they do fucked up shit like that lol?
## Post #31
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-27T07:38:37+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

Morton storage allows for faster direct lookups from fragment/UV space...particularly to avoid page breaks in blocked/compressed pixel formats.

Your library? A dedicated texture extractor? Noesis!
## Post #32
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2012-03-27T08:23:15+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

Haha, just goes to show how much I know about texture formats, compressions, etc. (pretty much nothing). Still, it was a fairly good experience with figuring out how to decode it by myself. 

And how coincidential, too -- that was the exact same texture that I had just finished decrypting.
## Post #33
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-03-27T08:58:48+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

> Reply from MrAdults
>
> Morton storage allows for faster direct lookups from fragment/UV space...particularly to avoid page breaks in blocked/compressed pixel formats.

Your library? A dedicated texture extractor? Noesis!

Ha ha ha well regardless whether I use Python or C++ it's roughly the same amount of code. I would rather use something that I can program faster at (C++) than something I am slower at (Python). Not the most efficient loop but no big deal lol. That, and if I used Noesis, I would not understand how it works, I would just copy and paste your code. Coding it myself... I now know .

```
    ifile.seekg(head02);
    boost::shared_array<char> data(new char[head15]);
    boost::shared_array<char> copy(new char[head15]);
    ifile.read(data.get(), head15);

    for(uint32 r = 0; r < head10; r++) {
        for(uint32 c = 0; c < head09; c++) {
            uint32 morton = array_to_morton(r, c);
            uint32 copy_position = 4*r*head09 + 4*c;
            uint32 data_position = 4*morton;
            copy[copy_position++] = data[data_position + 0]; // b
            copy[copy_position++] = data[data_position + 1]; // g
            copy[copy_position++] = data[data_position + 2]; // r
            copy[copy_position++] = data[data_position + 3]; // a
           }
       }

```
## Post #34
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-03-27T09:10:51+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

Batch texture ripper for USA version. Thanks to Rich for help with the descrambling. Will rework models later. Place exe in game root directory and run.

Note: There were 10 different texture types, some of them are upside down.

```
 const unsigned int T_TYPE1 = 0x54494481; // DXT1/DXT5
 const unsigned int T_TYPE2 = 0x54494483; // uncompressed
 const unsigned int T_TYPE3 = 0x54494487; // uncompressed (all scrambled)
 const unsigned int T_TYPE4 = 0x54494489; // DXT1/DXT5 (all upside down)
 const unsigned int T_TYPE5 = 0x54494491; // DXT1/DXT5 (toon_shadow)
 const unsigned int T_TYPE6 = 0x54494493; // uncompressed
 const unsigned int T_TYPE7 = 0x54494497; // uncompressed (all scrambled)
 const unsigned int T_TYPE8 = 0x54494499; // DXT1/DXT5 (mipmapped)
 const unsigned int T_TYPE9 = 0x5449449B; // uncompressed (all upside down)

```

[ripper.7z](https://xentaxbackup.github.io/file/5235_ripper.7z)
## Post #35
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-27T09:18:49+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

Actually, Noesis supports (and was initially targeted at) native plugins written in C/C++. It exposes all of the same methods through the native API as well. You could just start a native plugin project and throw everything into that, then have access to the entire Noesis framework for all of your future work, making maintenance of your assorted tools a lot easier too as you don't have to go back and compile 50 different things every time you change/fix something in your core library.

Unless, of course, you just like to do everything yourself for the sake of having it all be "yours", in which case, don't forget to thank me in the credits.
## Post #36
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-27T09:30:52+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

Also, I was joking by hinting that few things are truly our own, and so it's silly to allow ego to keep us from making decisions that can lead to making our work better/easier/more maintainable. You didn't really have to go back and edit in a thanks for me. But thanks.
## Post #37
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2012-04-06T15:05:51+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

Super noob question:
Where is the download link for visual studio 2010 CRT?
I think the cause of convert failure is visual studio 2010 CRT.
Is this SW free or charged?
## Post #38
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-04-07T07:52:07+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

Here's a sample of Mugen Souls .
[delete](delete)
The same format was used by the developer.
## Post #39
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2012-04-07T08:49:40+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

> Reply from dj082502
>
> Here's a sample of Mugen Souls .
http://www.mediafire.com/?qveipo7havcbv6a
The same format was used by the developer.
This isn't convert, either.
I think I need some help.
## Post #40
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-07T09:09:48+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

looks like it worked. I see ls files.nothing wrong with crt. as for mugen souls it will have to wait for a while.
## Post #41
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-04-07T09:19:16+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

> Reply from leyme
>
> dj082502 wrote:Here's a sample of Mugen Souls .
http://www.mediafire.com/?qveipo7havcbv6a
The same format was used by the developer.
This isn't convert, either.
I think I need some help.

Your folder is no problem.
Please read the directions carefully.

> Directions:
>
> 0.) must have visual studio 2010 CRT installed (or you must recompile with another compiler yourself).
>
> 1.) copy ism2 files and texture directory with TID files in it to somewhere safe.
>
> 2.) place exe inside where ism2 files are. Do not run this program with any ism2 files from the motion directory, animation is not supported.
>
> 3.) run exe.
>
> 4.) load generated LS files in lightwave.
>
> 5.) convert to whatever format you like.
>
> 6.) manually apply textures (program will convert TID files to DDS).
## Post #42
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2012-04-07T09:58:04+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

O.K. I'll be more careful.
Thank you, all
## Post #43
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2012-04-07T17:53:40+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

I have a noob question.
Where is Select LScript.
## Post #44
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-07T18:17:19+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

Skip to part where model is loaded. 
[http://www.youtube.com/watch?v=o4ITTCF83w4](http://www.youtube.com/watch?v=o4ITTCF83w4)
## Post #45
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-04-10T10:40:02+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

> Reply from leyme
>
> 
I have a noob question.
Where is Select LScript.

Try this. 
As you can see in the picture above.
First, click on a Utilities.
Then click the Script button to open..
## Post #46
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2012-04-10T14:09:48+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

Thank you for your explanation.
## Post #47
- Username: hazamajackson
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 28, 2012 6:52 am
- Post datetime: 2012-04-28T05:36:59+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

what are the requirements for the hyperdimension neptunia mkii program?
## Post #48
- Username: HeavensFall
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 15, 2012 8:07 pm
- Post datetime: 2012-05-07T07:25:43+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

Could someone please give a link to The Neptune model file W/ Textures?
i am trying to find her and rig her!!!
preferably an SMD format
## Post #49
- Username: HatsuneMiku15
- Rank: n00b
- Number of posts: 10
- Joined date: Mon May 07, 2012 7:13 pm
- Post datetime: 2012-05-07T12:40:32+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

Where do I download the Microsoft Visual Studio? ^^;; Sorry for the newbie question xD
## Post #50
- Username: REverSouL
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 08, 2012 11:57 pm
- Post datetime: 2012-05-08T16:02:21+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

Can someone post Neptune's Sprite, it would be most appreciated.
## Post #51
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2012-09-18T22:19:09+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

Sorry for resurrecting such an old thread but:
the D/L links are all gone 

Anyone still have a copy of the files from this thread?

thanks
-Darkstar
## Post #52
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-09-19T07:08:01+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

> Reply from Darkstar
>
> Sorry for resurrecting such an old thread but:
the D/L links are all gone 

Anyone still have a copy of the files from this thread?

thanks
-Darkstar
Here
[viewtopic.php?p=70058#p70058](http://forum.xentax.com/viewtopic.php?p=70058#p70058)
## Post #53
- Username: systemchester
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Apr 02, 2010 9:44 am
- Post datetime: 2012-09-19T16:56:43+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

> Reply from dj082502
>
> Darkstar wrote:Sorry for resurrecting such an old thread but:
the D/L links are all gone 

Anyone still have a copy of the files from this thread?

thanks
-Darkstar
Here
viewtopic.php?p=70058#p70058
this one can't generat ls files it only convert pictures
so help me!
## Post #54
- Username: tomatopasta
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Aug 17, 2012 2:49 am
- Post datetime: 2012-09-20T21:58:18+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

I had managed to rip some graphics from mugen souls with the random ripper from howfie, it is at it best form, the color doesnt show correctly.
[001.jpg](https://xentaxbackup.github.io/file/5822_001.jpg)
## Post #55
- Username: tomatopasta
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Aug 17, 2012 2:49 am
- Post datetime: 2012-09-21T10:40:03+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

Some sample graphics under EVENT\STILL\PICT directory:
How to fix it?
(gahh, cannot upload more than 1 attachments in a single post, what a strange rules.)
[206.jpg](https://xentaxbackup.github.io/file/5824_206.jpg)
## Post #56
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2012-11-03T16:21:07+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

Did you remove the model converter?
## Post #57
- Username: LuchiaL
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jun 30, 2012 3:35 pm
- Post datetime: 2012-11-04T18:26:59+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

It does not generate a LS file for me.
## Post #58
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2013-04-28T12:19:50+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

Yeah, it's a shame that he removed the converter. Nobody seems to have a copy of it

@tomatopasta: your color channels are off. try swapping r/g/b around
## Post #59
- Username: Akane
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu May 02, 2013 3:05 am
- Post datetime: 2013-05-01T22:09:43+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

Well, the good news is I happened to find the source code to howfie's Neptunia MkII ripper on his Google Code page. A glance through the code indicates this one /does/ work with the model files, so, once I get it compiled I'll drop a nice, fat, binary blob for everyone else. I myself am working with stuff from Victory, but given the formats are about the same (if not outright the same, given RandomTalkingBush's success) they seem to work.
## Post #60
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-05-02T03:13:00+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

that one is not done. thats why i took the old one down cuz i was working on a new one. but go ahead and try lol.
## Post #61
- Username: Akane
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu May 02, 2013 3:05 am
- Post datetime: 2013-05-05T14:11:14+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

Well, in which case, if possible, would you be so kind as to provide a copy of the old tool, if you happen to have one?
## Post #62
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-08-27T15:35:51+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

Can someone reupload the script pls??
## Post #63
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2013-08-30T00:18:23+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

> Reply from Darko
>
> Can someone reupload the script pls??[http://www.mediafire.com/?7bowodf9ebd6ps8](http://www.mediafire.com/?7bowodf9ebd6ps8)

There ya go.
## Post #64
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-08-30T02:34:40+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

> Reply from RandomTBush
>
> Darko wrote:Can someone reupload the script pls??http://www.mediafire.com/?7bowodf9ebd6ps8

There ya go.

Thanks man
## Post #65
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2013-11-20T17:20:30+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

Works perfectly!

Can you maybe update your program for Neptunia Victory? Many of the character models there seem to have an additional unknown section in the ISM2 file (see [here](http://pastebin.ca/2477530) for the log)

The corresponding ISM2 file can be found here (400k):

```
https://mega.co.nz/#!ZscHQL6B!Gd0Fg0_2H8wQFaX5zlJG0WRDB9lWubtBK4DaP_JKvDQ
```


Many of the monsters work fine though, so only the main characters seem to be affected
## Post #66
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2013-11-21T10:25:06+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

> Reply from Darkstar
>
> Works perfectly!

Can you maybe update your program for Neptunia Victory? Many of the character models there seem to have an additional unknown section in the ISM2 file (see here for the log)

The corresponding ISM2 file can be found here (400k):
Code: Select allhttps://mega.co.nz/#!ZscHQL6B!Gd0Fg0_2H8wQFaX5zlJG0WRDB9lWubtBK4DaP_JKvDQ

Many of the monsters work fine though, so only the main characters seem to be affectedI just hex-edited the files and bypassed that problem when I extracted the models a while back.
## Post #67
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2013-11-21T12:12:48+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

> Reply from RandomTBush
>
> I just hex-edited the files and bypassed that problem when I extracted the models a while back.
Yeah, that would work if I knew a bit more about the format  Do you have the source code (or a description of the fileformat with the various sections etc.) available somewhere?

Anyways, it looks like the models I was looking for (the idol versions of Rom and Ram) are not inside the data files (it seems that with Victory they changed the DLC content to actually provide the models and textures, instead of just "unlocking" pre-existing content as was the case on the first 2 installments). Looks like I'll have to buy the DLC and try to capture the PKG file with a proxy server or something...
## Post #68
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2013-11-22T04:21:05+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

> Reply from Darkstar
>
> RandomTBush wrote:I just hex-edited the files and bypassed that problem when I extracted the models a while back.  
Yeah, that would work if I knew a bit more about the format  Do you have the source code (or a description of the fileformat with the various sections etc.) available somewhere?

Anyways, it looks like the models I was looking for (the idol versions of Rom and Ram) are not inside the data files (it seems that with Victory they changed the DLC content to actually provide the models and textures, instead of just "unlocking" pre-existing content as was the case on the first 2 installments). Looks like I'll have to buy the DLC and try to capture the PKG file with a proxy server or something...I don't have the source code on me (nor would I understand it -- I'm not a coder). And to be fair, the DLC costumes from mk2 are the same way. I'll do you a favor though, I'll pack up the "fixed" and DLC models for ya so you can use the current extractor with those. Don't mind the missing textures for the alternate costumes -- they're just recycled from the original models.
## Post #69
- Username: Yuredacy2311
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Aug 31, 2011 8:36 am
- Post datetime: 2016-08-27T15:47:52+00:00
- Post Title: Re: PS3 Hyperdimension Neptunia MKII

hi,
 Sorry bring back old thread, but anyone still keep that howfie's lightwave script? 
 Thanks a lot.
