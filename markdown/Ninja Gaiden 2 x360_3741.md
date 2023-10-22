## Post #1
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-09-27T10:23:28+00:00
- Post Title: Ninja Gaiden 2 x360

Hi there !!
Ninja Gaiden 2 is one of the best games out there and you sure know how gorgeous the models are!! (if you don't then you better check out)

Through my drills, something started to show up: the MODELS baby !  !!
Now admire this work in progress pic, this model has undergone heavy weld/unify modifications under max so the converter is far from being refined. More is still to come !!
[Ryu.JPG](https://xentaxbackup.github.io/file/2383_Ryu.JPG)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-09-27T12:02:51+00:00
- Post Title: Ninja Gaiden 2 x360

Very Nice I look forward to your release
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-09-27T21:50:31+00:00
- Post Title: Ninja Gaiden 2 x360

Excellent work!
## Post #4
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-09-28T12:56:04+00:00
- Post Title: Ninja Gaiden 2 x360

Now the busty sonia, WoHooooo!! 
[Sonia.JPG](https://xentaxbackup.github.io/file/2392_Sonia.JPG)
## Post #5
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-09-29T11:12:21+00:00
- Post Title: Ninja Gaiden 2 x360

HI there !!
The work on ng2 looks promissing but the textures have a weird format, I can't figure it out: they ressemble to DDS but they aren't !!! some of them are compressed and I read somewhere that xbox 360 gpu now accepts compressed texture data directly (a new kind of texture compression not the DXT1..5 compressions) and some other textures are uncompressed and look just like the regular DDS !! I included 2 textures: one compressed and one uncompressed, take a look at these and see if you can do something 
[Textures.zip](https://xentaxbackup.github.io/file/2402_Textures.zip)
## Post #6
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-10-01T13:57:09+00:00
- Post Title: Ninja Gaiden 2 x360

Nobody ??   
Oh come on, give the old man some help
## Post #7
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-10-01T15:36:27+00:00
- Post Title: Ninja Gaiden 2 x360

cant help you to look because i am at work but have you tried it in different dds viewers like that ati tool for textures?
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-10-01T16:19:36+00:00
- Post Title: Ninja Gaiden 2 x360

ill look at it tonight I think i can help it should be the standard 360 swizzle method.
I have a script somewhere on my hard drive to convert them ill dig it up.
## Post #9
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2009-10-03T02:08:32+00:00
- Post Title: Ninja Gaiden 2 x360

do a 32bit swap operation on the compressed.bin you posted and toss a DXT1 header on it.



I encountered this when hacking DOA4, you can actually find that thread here on xentax, unfortunately the information concerning it is long gone 

EDIT
would you be interested in extracting models from any of these 360 games;
BulletWitch
Ninety Nine Nights
Circle of Doom
Golden Axe
Onechanbara

I've been eye ball'n those models for awhile
## Post #10
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-10-04T13:45:25+00:00
- Post Title: Ninja Gaiden 2 x360

Great !! thanks guys !!!
But can you be more precise, the 32bit swap: is it a byte or a bit swap?
I checked the DOA4 thread and honnestly I didn't understand, can you explain the swizzle thing?

> would you be interested in extracting models from any of these 360 games;
Generally, when the data is compressed I don't bother searching for the decompression. Other than that, I only have a few games:
- Infinite Undiscovery, not very interresting
- Midnight Club Losangeles, I'd like to extract the city models but the data is compressed and I'm too bad at decompression 
- Halo 3, plenty of tools out there, though I'd love to have the musics.
- Ninja Gaiden 2, en cours...
- Tenchu Z, model data is easy to extract but I'm very busy right now, maybe later.
- Gears of War 2, excelent game but nothing very interresting to extract, uses the unreal engine 3 anyways.
- Soul Calibur 4, models are pretty but the data is compressed, I can't move on!

As to the games you mentioned, I think I'll choose these:
Ninety Nine Nights, has some gorgeous models
OneechanBara, maybe!

Let me know if the data on these games is compressed or not, ok?
## Post #11
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2009-10-04T15:05:58+00:00
- Post Title: Ninja Gaiden 2 x360

I believe for the 32"bit" swap it basically takes 4bytes and reverses em. 01 02 03 04 = 04 03 02 01... but you can preform this action any time. and also might have some connection to the algorithm.. ? but won't effect the outcome of the swizzle.. cause well all it's doing is reversing the file..

also the games I mentioned above should all be uncompressed.. minus golden axe.. I got no clue. back when I had my modded 360 running I had these all ripped on my PC. and I was working heavily with extracting DDS textures.   

and it might be nice to know that theswizzle is quite simple.  ...um but I don't have a programmer background. I'm more the visual arts guy, 2d/3d... that's why my explanations of the swizzle are kinda out there. but hopefully I can hit some reasoning of understanding.

>at first I was lucky, tecmo left in reused content in DOA4 from DOAU from the original xbox. I compared the pixels one-by-one in paintshop. and like a puzzle rearranged the texture whole again. I found the pixels were grouped then swapped to another area of the image in a mathematical increment. by studying textures from DOA4 and other 360 games my study grew and after 3months I was able to unswizzle any DDS texture from any 360 game. paintshop jasc gave me an ability to record image editing operations, so I was able to record my actions when unswizzling an image by hand.

..anyway enough history, basically we had a paint solution that was no good for mass converting textures. so me and jamesinator had a look at the hex in the dds file. and we basically came up with the same algorithm for the swizzle.

the original algorithm was documented.. but online only.. >_< and after my 360 bit the dust.. I dropped all interest in modding. hence the algo was lost over 3years.. but i'll try to explain what I recall, least it'll give you a starting point.

what we found is that the first 4bytes always remain untouched. then the next 4bytes would be relocated 16bytes after.then after doing that 8times the 9th set of 4bytes would not relocate. then after that is just repeats..   hmm actually I don't remember much.

however there's a paintshop solution to this. there's also an illegal solution, but I can't get my hands on it. apparently there's something in the 360SDK that will swizzle and unswizzle for you. if you get your hands on that plz share
## Post #12
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-10-04T16:48:29+00:00
- Post Title: Ninja Gaiden 2 x360

Fatduck discovered the format of Ninety Nine Nights 

```
  dword     ??
  dword     ??
  dword     ??
  dword     numGeometry
  dword     numBones
  dword     ??
}
struct Geometry {
  dword         ofs
  dword         ??
  dword         ??
  dword         FaceType
  dword         numVerts
  dword         numFaces
  <unknown>5 
  dword         nLen
  char[nLen]    ??String
  dword         nLen
  char[nLen]    ??String 
  dword         ??
  char[256]    MaterialName
  float_4        colorRGBA
  float_4        colorRGBA
  float_4        colorRGBA
  float            MatValue
  dword_7     TextureType
  char[255]_7   TextureName
  Byte_7        TextureFlag
  dword_3     DataType
  <Data>    Vert, Normal, UV, Weight, Face etc...
  dword         usedBones
  struct BoneData 
    dword       nLen
    char[nLen]  BoneName
  }
  
  float_6       bounding  
}


```


This game also uses swizzle textures.
The files are compressed but I have a quickbms script that can extract them if you need it.
## Post #13
- Username: magnum
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jul 27, 2009 3:43 am
- Post datetime: 2009-10-07T01:57:38+00:00
- Post Title: Ninja Gaiden 2 x360

Standard xbox 360 swizzle method? Any chance you can explain what that is, or post a script? I've been trying to deswizzle some xbox 360 (DDS) textures, and have had no luck.

Edit:

Actually, scratch that, looks like I figured it out... (Mario, you rock!)
## Post #14
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2009-10-08T02:07:40+00:00
- Post Title: Ninja Gaiden 2 x360

I spent 3 long months deciphering that stuff. also what chrrox meant about the standard swizzle, was about the scripts I made.

but it's not standard, he's wrong about that.

I've discovered 4 different types of swizzle algos, I just call them "the 360 swizzle" to generalize it. the DXT1 swizzle is most commonly used.
## Post #15
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-10-08T09:50:30+00:00
- Post Title: Ninja Gaiden 2 x360

Hello,
Guys you're going to be pleased!!! Dead or Alive Extreme 2 models and Ninja Gaiden 2 models share the extact same format, which means that soon there will be one converter for both of these games, isn't that fantastic???? I'm very excited and the pic below shows exactly how I feel, the moderators should include something like this in the icons and I'm sure as hell tecmo is not going to be happy 
Ok seriously now ... can I post the pics here or is it too nude to be shown, from what I know, doax2 is a +12 game but the base models are nude (they don't have clothes that is) the girls are busty but aren't so +18 so I think this shouldn't a problem.
Right now only the vertex data is extracted + some face problems, soon there will be a support for texture coords and more.
[pg035.jpg](https://xentaxbackup.github.io/file/2429_pg035.jpg)
## Post #16
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-10-08T10:53:50+00:00
- Post Title: Re: Ninja Gaiden 2 x360

There is no problem in showing the models. We are not a kids site.
## Post #17
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-10-09T16:00:17+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Ok here you go: this is the ayane model that I had to adjust the different body parts to fit together and unified many of the faces and left some. Enjoy !!
If Xentax isn't the best game research place in the world then now it is !!!
[Ayane.jpg](https://xentaxbackup.github.io/file/2430_Ayane.jpg)
## Post #18
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-10-09T16:22:21+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Nice
## Post #19
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-10-10T08:25:47+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Not bad getting the models out.  I made a nude version of DOAX2 about a year ago, but I've never given it out to anyone but close friends.  Don't want to deal with Tecmo coming after me.    

It would be cool to edit the models too, but they did a pretty good job on what is in the game already.  Good luck to you!
## Post #20
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-10-10T09:40:45+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Hi there!!
Here's more, there is some progress in the face indices and still no texture coords, now the program works for stages too, this time I didn't touch the unify nor the weld buttons in max!!
But first things first, I'll post an .afs extractor for Doax2 and a .ng2 extractor for Ninja Gaiden 2 soon.
Now I need to sleep a little ...
[Shop.jpg](https://xentaxbackup.github.io/file/2434_Shop.jpg)
## Post #21
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-10-17T09:44:50+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Ng2 Extractor
Ninja Gaiden 2 has .ng2 files that contain the different data for the game, I searched these files and didn't find any file allocation table so I went blind on this one.
Of course the most importatnt part in the .ng2 files is the character & stage models, there are some effect models that get overwritten but that's not important (who cares about the damn effects anyway) There are also some char_dat2 & itm_dat2 files that will be skipped!!!
The models are extracted as GMD (game model ?) files that contain the regular XPR2 chunks + some MPH (morph) and ANIM chunks.
Since there aren't many .ng2 files (about 20) I made this extractor process them all at once, the extracted files will be in the corresponding directories for the original .ng2.
The good thing about the GMD files is that they have a name that will be used as a filename so you'll get something like this: e_nin_a.gmd, e: enemy, nin: ninja, a (a, b, c, ...)
As usual, put the program in the root directory where the dfferent .ng2 file are then watch the magic, it'll take about 15 minutes and now you have all the GMD files ready.
This is just the model extractor, a model converter will be available soon!
[Ng2 Extractor.zip](https://xentaxbackup.github.io/file/2458_Ng2 Extractor.zip)
## Post #22
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2009-10-17T11:30:40+00:00
- Post Title: Re: Ninja Gaiden 2 x360

awesome, if the converter works on DOAX2, it'll open a large resource of models.

can't wait to make some renders with em
## Post #23
- Username: Mike
- Rank: n00b
- Number of posts: 10
- Joined date: Sun May 13, 2007 3:46 am
- Post datetime: 2009-10-17T19:45:27+00:00
- Post Title: Re: Ninja Gaiden 2 x360

> Reply from Surveyor
>
> Ng2 Extractor
Ninja Gaiden 2 has .ng2 files that contain the different data for the game, I searched these files and didn't find any file allocation table so I went blind on this one.
Of course the most importatnt part in the .ng2 files is the character & stage models, there are some effect models that get overwritten but that's not important (who cares about the damn effects anyway) There are also some char_dat2 & itm_dat2 files that will be skipped!!!
The models are extracted as GMD (game model ?) files that contain the regular XPR2 chunks + some MPH (morph) and ANIM chunks.
Since there aren't many .ng2 files (about 20) I made this extractor process them all at once, the extracted files will be in the corresponding directories for the original .ng2.
The good thing about the GMD files is that they have a name that will be used as a filename so you'll get something like this: e_nin_a.gmd, e: enemy, nin: ninja, a (a, b, c, ...)
As usual, put the program in the root directory where the dfferent .ng2 file are then watch the magic, it'll take about 15 minutes and now you have all the GMD files ready.
This is just the model extractor, a model converter will be available soon!

awesome, 
it would be cool if your conveter could export morph and skinning data.
since my currently tool(given by my friend) can export mesh and bone only.
## Post #24
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2009-10-18T01:36:28+00:00
- Post Title: Re: Ninja Gaiden 2 x360

the skinning is weird, they combine static objects with skin objects. don't know about ng though.. probably the same.
## Post #25
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-10-18T09:40:22+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Doax2 AFS Extractor
This is just the old xbox AFS used for many games. The weird thing is that TECMO kept the AFS structure as little endian (xbox 360 is big endian) of course the data inside these AFS archives are big endian.
There aren't many afs files for Doax2 so I made the extractor process them one after the other in a single shot!

AFS Files:
avt	avatar models
boat	maybe racing boats
chr	the characters, yay!!
cmn	common data?
itm	items
mot	motion
snd	character voices
spr	2d sprites for the HUD
stg	stages
werone	swimsuits for ayane, kokoro, christie, helena &	hitomi
wertwo	swimsuits for christie, helena, hitomi, leifang, lisa, kasumi & tina

The tricky part is that on some of the afs files, there are duplicate filenames: you get one filename for more than one file. This is found in itm.afs, werone.afs and wertwo.afs. An example is that for a character swimsuit, 3 swimsuits shares the same filename, this would be a waste to get only one suit out of three.
A solution to this problem was to have a rename-on-the-fly mechanism when extracting the content. The way these filenames are junked into the afs files, I doubt the game uses them, it might use some hardcoded file index, this is clearly seen in itm.afs where parts of the extensions are simply not there!!!!

Just put the extractor where all the afs files are (yes all of them or else the program crashes) then you'll see the files extracted to their respective directories.
Something to notice is that most of the game files when looked at in the hex editor are xpr2 (models) or cat (I don't know what these do)
[Doax2 Afs Extractor.zip](https://xentaxbackup.github.io/file/2461_Doax2 Afs Extractor.zip)
## Post #26
- Username: Mike
- Rank: n00b
- Number of posts: 10
- Joined date: Sun May 13, 2007 3:46 am
- Post datetime: 2009-10-18T10:54:06+00:00
- Post Title: Re: Ninja Gaiden 2 x360

> Reply from Mario_Kart
>
> the skinning is weird, they combine static objects with skin objects. don't know about ng though.. probably the same.

As shown in the attached picture, the body part are in one piece. 
it seems, not possible to deform the mesh by morph target. 
and the bones ware present, i was petty sure that they are using skinning technic.
[rtm000fpv1.jpg](https://xentaxbackup.github.io/file/2463_rtm000fpv1.jpg)
## Post #27
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2009-10-18T20:30:23+00:00
- Post Title: Re: Ninja Gaiden 2 x360

i see, but still doax2 might be different. it's based of its counter part, doa4. which is a fighting game where tecmo cut corners to allow them better frame rates.

i know for a fact that in doa2u the models are not 1 piece.

NG and DOA may be slightly different, and that's what I was trying to say before...
## Post #28
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-10-21T12:35:02+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Okaay, I see someone has got a working converter, this is good but I got some questions:
question1: where are the breast bones ? I know breasts don't have bones but there must be something to influence them to bounce as they usually do and I don't see anything!!
question2: where are the finger bones??
question3: does the converter export textures too or are you using some other tool?
question4: will you release the converter or is it only a see-but-dont-touch thing?

Mario_Kart, indeed ng2 models and doax2 are different. Both character models have body parts but in doax2, the parts are all cramped together just like the older doax used to be, you need to adjust them but in Ng2, the parts are already adjusted.
For stages, no difference!!

Ok now for some fresh news ... face indices are now fixed!!! models look clearer and look at the pic below: there's a beautifully modeled xbox 360 in there!!
These models are way too detailed and they are used ingame!!!! the 360 is really a beast!!!
There are some faces that need to be flipped but I'm done with this, now it's time to move on to something else ... Textures and texture coords are my destiny!!
I'll soon post the first release here, but before I'll need to fix a strange Windows bug that crashes the converter whenever I run it outside Visual Studio !!!
I'll keep you posted on the progress!
[Shop2.JPG](https://xentaxbackup.github.io/file/2471_Shop2.JPG)
## Post #29
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2009-10-21T21:33:57+00:00
- Post Title: Re: Ninja Gaiden 2 x360

any luck with the UV's?

voltron had trouble figuring out the mapping method
## Post #30
- Username: onionhead
- Rank: beginner
- Number of posts: 37
- Joined date: Tue Oct 27, 2009 10:02 am
- Post datetime: 2009-10-27T14:30:31+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Mike: do u mind posting the model for Sonia plz, cuz i don have ninja gaiden 2 to extract from. thanks
## Post #31
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-10-28T12:04:18+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Hello,
The strange bug that I told you about earlier is still there and the converter works only inside VisualStudio with the F5 push, not even the Ctrl+F5 maybe this is due to the too many allocations, I don't know. Anyways it'll take some time before there will be any release, I'm happy I don't wrork on deadlines!!!
Something I find strange is that although there isn't any normals exported, the models look like if they had normals, the different parts are correctly shaded. Only in the Doax2 character models, they look flat-shaded, they will need a vertex weld.
Now here's some pics to show that things are progressing  just be patient 
[Shade.JPG](https://xentaxbackup.github.io/file/2483_Shade.JPG)
## Post #32
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-10-29T10:30:35+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Hi!!
I finally fixed the damn bug!!! This was due to the incorrect sizes on the xpr files, hell it took me hours to figure out 8(
Now the converter is ready for a first release !! version 1.00 (or alpha) supports only vertex data: no texture coords, no textures, no skin weights, nothing but position data !!
This converter is made for both Dead or Alive Extreme 2 & Ninja Gaiden 2, just type in the model name and the converter will create the corresponding OBJ file, it's better if you place the converter in the same directory of the original model and just type its name, ex: in doax2/chr/ type in vayAA.tpr 
Oh, by the way, models are too small and thus I scaled them to x100.

Now that I think of it, I'll probably change course and write a MaxScript generator to import the models into 3dsmax (no more OBJ converter), this way it'll be easier to import skin weights (if I figure them out that is)
MaxScript will also come in handy with the batch select-verts/weld/select-elements/unify routine for doax2 character models.

From what I tested, this program works on every sort of models (characters, stages, items, swimsuits, ...) but let me know if you find any bugs!
Well next there will be texture coords support, correct texture export and maybe skinning (I said maybe).
Enjoy!!
[Tecmo Model Converter.zip](https://xentaxbackup.github.io/file/2484_Tecmo Model Converter.zip)
## Post #33
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-10-29T11:40:45+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Surveyor, is there any normal map in NG2!? I found some normal map in other game(I know it's a bit off topic) use type 0x7C! I guess it a UV16 dds!? And also I have some problem on dtx1(0x52) with size <= 64!
Do you know how to unswizzle it!? 

And if you upload some NG2 models file to me, I can help you on material/texture coordinates etc. stuff!
## Post #34
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2009-10-30T01:43:45+00:00
- Post Title: Re: Ninja Gaiden 2 x360

post the file, I can try to unswizzle it
## Post #35
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-10-30T08:20:24+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Thanks Mario. Here is the xpr file, you can download it from megaupload: [http://www.megaupload.com/?d=UYJCW9AG](http://www.megaupload.com/?d=UYJCW9AG)

It's a game call Enchanted Arms, actually even dxt1 and dxt5 have problems as well!?(It just doesn't look rignt, alpha channel in Red plan etc) Unswizzle method is correct, just the color not so right!

PS: The text file inside told you where is the location of each image and size etc. Do you have any refrence of DDS cubic maps as well! TXCM is  cubic maps and since I never found one so I don't know how the data stored in files!
## Post #36
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2009-10-30T15:38:00+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Can you upload some character models ?
Unfortunately I don't find a downloadable demo version on the Net.
## Post #37
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-10-31T13:52:26+00:00
- Post Title: Re: Ninja Gaiden 2 x360

> Surveyor, is there any normal map in NG2!? I found some normal map in other game(I know it's a bit off topic) use type 0x7C! I guess it a UV16 dds!? And also I have some problem on dtx1(0x52) with size <= 64!
>
> Do you know how to unswizzle it!?
Yes Ng2 uses some normal maps, not extensively though (as they really should), the work on the texture coords is promissing but the deswizzling is giving me headaches ...
I use the doa4tpr to view/extract the textures to test, and I'm planning to write a texture extractor/deswizzler, I found some code on the net that deswizzles ARGB32 but I'm stuck on the DXTn formats. ARGB32 is found in Doax2 sprites (used for menu display) and it works perfectly.
You might also be interrested to know that there are some additional formats: 0x53 something between DXT1 & DXT5, 0x02 very weird, maybe some ARGB16!! I think I'll just use MarioKart scripts to get the job done as I had enough of this!!!
The pic here demonstrates the brilliance of the ARGB32 deswizzler I found!!
I'll keep you posted on the progress ...
[ARGB32.JPG](https://xentaxbackup.github.io/file/2486_ARGB32.JPG)
## Post #38
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2009-10-31T15:09:24+00:00
- Post Title: Re: Ninja Gaiden 2 x360

it's been over 3years and nobody has yet to convert my scripts into proper code  

by the way, the diagswap in the script just grabs a chunk of data and replaces it 16bytes down the file
## Post #39
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-11-06T21:12:59+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Hi everyone!!
There's some new stuff here: the texture coords now are supported, it wasn't the most difficult part but textures are still giving me headaches, I think I'll leave this to MarioKart since he's the one complaining   
One more thing to say is that the converter posted earlier outputs an .MS file into the d:/ called bone.ms, well this is a max script file that generates the bones, I forgot to ommit this in the release because it's still under research but since it's there then you can try it to see 
A new release with texture coords will be soon posted here at xentax !!
[UVUnwrap.JPG](https://xentaxbackup.github.io/file/2501_UVUnwrap.JPG)
## Post #40
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-11-08T09:52:05+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Ok here's the latest release with texture coord support, enjoy!!
You'll need to guess what texture to use because I didn't figure that out yet, this'll be the next step: know what textures go to which object in the scene, then there'll be texture support with deswizzling, bone skinning and morphing ... A lot of work and only one man to do it 
[Tecmo Model Converter.zip](https://xentaxbackup.github.io/file/2508_Tecmo Model Converter.zip)
## Post #41
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2009-11-08T10:05:42+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Surveyor,

Can you attach some (original) character models ?
Unfortunately I did not find a downloadable demo version (game) on the Net.
## Post #42
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2009-11-08T19:15:27+00:00
- Post Title: Re: Ninja Gaiden 2 x360

awesome, render time
## Post #43
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-11-11T21:00:38+00:00
- Post Title: Re: Ninja Gaiden 2 x360

> Reply from Surveyor
>
> Surveyor,

Can you attach some (original) character models ?
Unfortunately I did not find a downloadable demo version (game) on the Net.
Sorry man I can't, the connection here is a 12 Kb/sec max so try to imagine how much does it take to upload 500 Mb of data. The term "Surfing the net" doesn't apply for us, down here we're only "Navigating" the net 

I finally completed a working texture extractor, it is based on a code written by an unknown japanese person and supplied by MarioKart so I'd like to thank them alot!!!
The program strangely crashes for textures smaller than 64x64 in dxt1 and 128x128 in dxt5 formats, but in this age of HD gaming, The number of this (small) textures is next to zero!!
There is also some bugs in the deswizzling of some small textures, I don't know why and I don't plan to fix this 
As usual, the program will batch process all the files present in its execution directory and the sub directories, this greatly saves time!!
This texture extractor is intended for Ninja Gaiden 2 & Dead or alive extreme 2 but might also work on Dead or Alive 4, who knows!!
A file worth extracting and viewing the textures is the "csn_card.ctb" present in doax2/stage directory: this holds the casino cards that got very nice poses of the girls and they are 512x1024 wohoo!!!
Well, Enjoy!!
[Tecmo Texture Extractor.zip](https://xentaxbackup.github.io/file/2525_Tecmo Texture Extractor.zip)
## Post #44
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2009-11-12T01:46:26+00:00
- Post Title: Re: Ninja Gaiden 2 x360

aww, i was hoping you'd fix the 64x64 error.
## Post #45
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2009-11-12T05:46:02+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Surveyor,

I don't need the full game (500 MB ?), I need some sample model files only.

Can you send me ( [kz_3d@tvn.hu](mailto:kz_3d@tvn.hu)) some (.zip packed) files if it is possible ?
## Post #46
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2009-11-12T10:02:18+00:00
- Post Title: Re: Ninja Gaiden 2 x360

The work done so far on this game is amazing.
You've done a really good job, thankyou.
I wonder if this tool would work on the PS3 sigma 2... depending on whether its the same formats and same packaging i guess.

> Surveyor,
>
> 
>
> I don't need the full game (500 MB ?), I need some sample model files only.
>
> 
>
> Can you send me ( kz_3d@tvn.hu) some (.zip packed) files if it is possible ?
>
> Surveyor,
>
> 
>
> I don't need the full game (500 MB ?), I need some sample model files only.
>
> 
>
> Can you send me ( kz_3d@tvn.hu) some (.zip packed) files if it is possible ?

I've been warned (kinda) here for downloading a game because I didnt state that I already owned it but had it lent out.
Whereas you dont have the game at all, I don't know if its best to send you the files or not, if its allowed then il send you the files from my NG2 disc, but id rather get a second opinion 1st.

The game itself isnt 500meg, this is only the models and textures, the actual dvd is like basically 4 gigabyte, though this extra space is for the music, the programming and whatever else (Im too tired to think of what else is used here right now).
## Post #47
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-11-12T10:24:31+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Hi

> Surveyor,
>
> I don't need the full game (500 MB ?), I need some sample model files only.
You really must understand that my connection sessions do not exceed 20 minutes and they are not many, I don't have internet at home and when I'm online, it's at work or at the internet café. still 20 minutes with this connection is very little to upload even 6mb of model data. I suggest you ask the other members, I'm sure they'll not refuse you
## Post #48
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2009-11-12T15:59:03+00:00
- Post Title: Re: Ninja Gaiden 2 x360

The contents of this post was deleted because of possible forum rules violation.
## Post #49
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2009-11-12T20:30:35+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Darko, 

Thank you for your help (sample file).
## Post #50
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2009-11-12T20:45:15+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Surveyor,

I converted the uploaded (by Darko) r_son_a.gmd file into .obj format with the "Tecmo Model Converter.exe".
I googled into the converted .obj file and I think all texture coords are zeros (vt 0.000000 0.000000 0.000000)
## Post #51
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2009-11-12T22:08:58+00:00
- Post Title: Re: Ninja Gaiden 2 x360

> Reply from Karpati
>
> Surveyor,

I converted the uploaded (by Darko) r_son_a.gmd file into .obj format with the "Tecmo Model Converter.exe".
I googled into the converted .obj file and I think all texture coords are zeros (vt 0.000000 0.000000 0.000000)

That's weird, I've been adding textures to the objects in 3ds max 9 and they're ok, I haven't any problem until now.
## Post #52
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2009-11-13T02:19:08+00:00
- Post Title: Re: Ninja Gaiden 2 x360

yea the converter fails to construct a UV map for some objects.
## Post #53
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-11-14T09:52:43+00:00
- Post Title: Re: Ninja Gaiden 2 x360

I solved the material assignement problem and now you can see in the object name what textures to use, the name will be something like this:
Part_x_y__texA_TexB_TexC
A: diffuse map
B: specular map
C: normal map
If the texture you're looking for is unavailable then this is because it's small (less than 128x128 and the texture extractor can't handle it) or the texture is 0x0 (yeah happens sometimes)
If there's only one texture then this might be the diffuse map only.
[Tecmo Model Converter.zip](https://xentaxbackup.github.io/file/2529_Tecmo Model Converter.zip)
## Post #54
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-11-14T09:56:11+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Seems that the texture extractor doesn't works for very large textures, I fixed that and now 2048x2048 textures work just fine.
I think 2048x2048 is the maximum resolution xbox 360 can handle.
[Tecmo Texture Extractor.zip](https://xentaxbackup.github.io/file/2530_Tecmo Texture Extractor.zip)
## Post #55
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2009-11-14T14:58:04+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Hey, thanks man, great work!
## Post #56
- Username: onionhead
- Rank: beginner
- Number of posts: 37
- Joined date: Tue Oct 27, 2009 10:02 am
- Post datetime: 2009-11-14T20:19:17+00:00
- Post Title: Re: Ninja Gaiden 2 x360

thanks for your hard work. now im hoping someone could make a NG sigma 2 convertor, that would be perfect.
## Post #57
- Username: famesethu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Nov 06, 2009 8:22 pm
- Post datetime: 2009-11-16T14:12:33+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Hey Guys,
I just got the Ninja Gaiden 2 demo.
The replies to the download link said it will work properly.
I extracted the .7z file and got A file with No extension.
The file name is "72BBCAC8E3CD70B3245C2F5CA98281F3D18F677554" (no extension)

Full file path = Content\0000000000000000\544387D7\00080000\72BBCAC8E3CD70B3245C2F5CA98281F3D18F677554

The readme file with it says
"Once you download the file you will need to burn the "Content" folder on to a CD and then place the disk in your XBOX to upload the file to your unit.When you unzip the download, burn the CONTENT folder right on the disc, then pop it in the 360, then go to games library and recently downloaded."

I need to read the .ng2 format files from this 857MB file.
can any one help Please....  
Thanks...
## Post #58
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2009-11-18T13:47:01+00:00
- Post Title: Re: Ninja Gaiden 2 x360

This probably wont be very useful to you but im gonna say it anyways.

Can you please explain that again in more detail...

And even if the filename is crazy you can still Hexedit it.

perhaps try to run an xbox emu (if there are any that even OPEN anything yet...let alone play shit.) and that should error if its an invalid image file.

Though to be honest it sounds like someones just uploaded some useless shit to me, that happens sometimes (why someone would waste their bandwidth uploading the wrong file, il never understand...).
## Post #59
- Username: famesethu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Nov 06, 2009 8:22 pm
- Post datetime: 2009-11-18T18:19:52+00:00
- Post Title: Re: Ninja Gaiden 2 x360

No the demo's not a fake.i found .ng2,.gmd extensions in the file through hexeditor.
as there is no emulator for xbox like pcsx or something i cant try to mount if it appears to be an image.
still i've no idea how to extract the .ng2 files from it.
## Post #60
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2009-11-18T20:50:04+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Im still stuck with the NG2 one ive got here now.
Still unsure how to extract it, to be honest i KNOW i need to burn it to a dvd but my dvd burner isnt the correct type needed for all this unfortunatly.

If you find anything out please try to mention it to me, im basically giving up and leaving the 7gig image laying on my desktop for now.
## Post #61
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2009-11-19T00:16:06+00:00
- Post Title: Re: Ninja Gaiden 2 x360

The contents of this post was deleted because of possible forum rules violation.
## Post #62
- Username: onionhead
- Rank: beginner
- Number of posts: 37
- Joined date: Tue Oct 27, 2009 10:02 am
- Post datetime: 2009-11-22T19:21:12+00:00
- Post Title: Re: Ninja Gaiden 2 x360

is someone kind enough to upload sonias weapon too. plz
## Post #63
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2009-12-03T04:18:19+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Maybe I'm requesting too much, buy Is it possible to add support for doa 4 models?? I was trying to extract eliot with 2 extractors but it was a mess.
## Post #64
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2009-12-03T05:26:49+00:00
- Post Title: Re: Ninja Gaiden 2 x360

who, this guy? O_o
## Post #65
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2009-12-03T05:57:57+00:00
- Post Title: Re: Ninja Gaiden 2 x360

> Reply from Mario_Kart
>
> who, this guy? O_o

Yeah
## Post #66
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2009-12-03T21:07:42+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Dm2
## Post #67
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2009-12-04T04:23:41+00:00
- Post Title: Re: Ninja Gaiden 2 x360

> Reply from Mario_Kart
>
> Dm2
 Ok
## Post #68
- Username: onionhead
- Rank: beginner
- Number of posts: 37
- Joined date: Tue Oct 27, 2009 10:02 am
- Post datetime: 2009-12-24T01:03:09+00:00
- Post Title: Re: Ninja Gaiden 2 x360

can someone post the gmd file for Ryu Hayabusa. plz?
## Post #69
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2009-12-26T20:30:12+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Any progress on 3d max import script?
## Post #70
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2010-01-07T09:31:00+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Hi there,
I discovered that on the character models, there are some morph meshes that represent the different boidy parts in different situations, a very easy to understand example is the boobs, the different meshes shown below represent the different poses the boobs can take, these are the extremes (in order: base, left, right, up, down, forward, backward)



Morphs.JPG (42.4 KiB) Viewed 1214 times


The problem is that I don't know how to make use of these under max (morph modifier), any ideas?
I also found that all the character models fellow a fixed body structure scheme, so it's possible to guess the different body parts at export time (at this moment just giving them correct names: chest, belly, leg, ...)
Anybody interrested?
## Post #71
- Username: onionhead
- Rank: beginner
- Number of posts: 37
- Joined date: Tue Oct 27, 2009 10:02 am
- Post datetime: 2010-01-08T02:35:23+00:00
- Post Title: Re: Ninja Gaiden 2 x360

1) pick the first mesh which is your main mesh that you want to animate. then add a morpher modifier to it.
2) then click on the empty tab and pick object from scene.
3) repeat step 2 until you added every single morph target.
4) use the spinner beside each morph target to test if the main mesh morphs
5) then link this to the body of the character and hide all the morph targets.
[Morph_show.jpg](https://xentaxbackup.github.io/file/2697_Morph_show.jpg)
## Post #72
- Username: beatme
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jan 15, 2010 1:27 am
- Post datetime: 2010-01-14T17:39:48+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Ninja Gaiden II isn't an easy game, i want to have some guide that will lead to a victory in Ryu Hayabusa's toughest adventure.
## Post #73
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2010-01-14T21:25:57+00:00
- Post Title: Re: Ninja Gaiden 2 x360

> Reply from beatme
>
> Ninja Gaiden II isn't an easy game, i want to have some guide that will lead to a victory in Ryu Hayabusa's toughest adventure.

A: Ninja Gaiden 2 is only a little Harder then the 1st Ninja gaiden Game (which is suprisingly easy honestly... until very hard mode, same as mentor in number 2)

B: This forum isn't related to game guides, if you want a guide then i suggest checking out gamefaqs, but to be honest game guides can only give you directions to go...they cant make you BETTER at a game,  they just help you find the things you didnt know the location of the 1st time through.

This forum is specifically for game modding/ file extracting.
## Post #74
- Username: onionhead
- Rank: beginner
- Number of posts: 37
- Joined date: Tue Oct 27, 2009 10:02 am
- Post datetime: 2010-01-20T23:09:17+00:00
- Post Title: Re: Ninja Gaiden 2 x360

anyone working on a ninja gaiden sigma 2 extractor?
## Post #75
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-01-20T23:16:56+00:00
- Post Title: Re: Ninja Gaiden 2 x360

its not possible all ps3 games are encrypted.
## Post #76
- Username: onionhead
- Rank: beginner
- Number of posts: 37
- Joined date: Tue Oct 27, 2009 10:02 am
- Post datetime: 2010-01-22T03:09:22+00:00
- Post Title: Re: Ninja Gaiden 2 x360

that sounds bad, so its totally impossible eh? unless they release a pc version rite? man i was hoping to acquire momiji,ayane and rachel for my fight scene
## Post #77
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-01-22T04:32:27+00:00
- Post Title: Re: Ninja Gaiden 2 x360

There is a way to get the files decrypted but you need a debug ps3.
## Post #78
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2010-02-01T10:27:45+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Hi there,
Well I spent nights and nights trying to figure out the skinning for Doax2/Ng2 only to find out that these models are far complicated, they make use of morphing extensively and bones are nowhere to be found.
I did somehow manage to fix the models matrices so now the different body parts are there where they are supposed to be, or at least, because in doax2 character models, the body isn't fully reconstructed, but for the rest of the data (heads, swimsuits, eyes, ...) things work well.
The pic below shows one of the very few models that I succeeded to rig, and given the difficulty to set the skinning, I imagine the animations are a lot harder.
All in all, I think I'll give up on this model format and move on to somthing else. I'll upload the new converter once I finalize it.
[TecmoSkin.jpg](https://xentaxbackup.github.io/file/2758_TecmoSkin.jpg)
## Post #79
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2010-02-22T10:51:52+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Hi,
I did some experiments with the newly got PS3 files from ninja gaiden sigma, having in mind that those ps3 files would be much detailed as stated by the developer many times, but judjing by what I got, I'd say both versions are exactly the same (in terms of poly count)
I was a little disapointed, given that I was too excited and spent nearly 1 day rewriting the tecmo converter to suit the new format 
And since it's here (the new converter, the ps3 one) I don't mind sharing it along with the other new converter (xbox360) 
The pic below shows both versions (360 and ps3) and nobody can tell which model belongs to which version.
[Sigma2.JPG](https://xentaxbackup.github.io/file/2792_Sigma2.JPG)
## Post #80
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2010-02-22T10:53:41+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Now here are the converters you've been all waiting for 
Off Topic: Okay this is getting ridiculous, I'm here on the forums for nearly 1 year, and still can't attach more than one file per post, so I'm obliged to write more than 1 post when I have more than 1 file to show (I don't know if it's me or the forums), anybody has any ideas?
Now here's some instructions for the sigma converter: you need to give the mesh file an extension, whatever it is, the converter works only on mesh files that have the 'TMC' tag on their header, so you need to be sure (using a hex editor) that the processed file is a true TMC.
For the xbox 360 converter, things stay the same, except that now (as mentioned earlier) models are correctly assembled, but the main flaw here is that models aren't smooth shaded at all!!
[Tecmo Converters.zip](https://xentaxbackup.github.io/file/2794_Tecmo Converters.zip)
## Post #81
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2010-02-22T15:50:55+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Stupid question:

How to get the sigma 2 files? I have all the Ng2's files and also Doax2's for model sharing, but NG2S's I think only a few people can have access to the files.

Hope someone could share some files in a near future.
## Post #82
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2010-02-22T22:03:01+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Awesome, only Problem now is...My CD drive cant read my Ninja gaiden 2 xbox disc(though this is normal tbh..).

And I cant seem to find a way to extract the files form the disc otherwise.
## Post #83
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-02-23T03:43:56+00:00
- Post Title: Re: Ninja Gaiden 2 x360

i can't run the second program.
for the ps3 files
Tecmo Model Converter v1.05 Sigma.exe
gives me a side by side configuration error.
## Post #84
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2010-02-23T09:26:14+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Thats the same error I get with it.

Though...I guess I have no use for it anyway due to not being able to get the PS3 disc onto PC...
## Post #85
- Username: orbbu
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Jan 20, 2010 5:36 pm
- Post datetime: 2010-02-23T11:55:00+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Hi Surveyor, great job ! and thanks for sharing 

One (silly ?) question, about the textures, I've tryed to import the .obj file in Maya, and the textures are not visible... does the converter link the .dds textures to the model or should I manually associate them one by one ? -.-

And one request, can you make a version of your converter to batch convert all the files in the same directory without having to manually type each filename ? (I'm using the x360 version)

Thanks in advance
## Post #86
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2010-02-23T13:42:18+00:00
- Post Title: Re: Ninja Gaiden 2 x360

orbbu, 

You can Use the cmd prompt, to batch rename files.

Open cmd prompt and navigate to the working directory then type  "rename *.??? *.???" without the quotes  (the question marks are the file extension.
## Post #87
- Username: orbbu
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Jan 20, 2010 5:36 pm
- Post datetime: 2010-02-23T14:57:09+00:00
- Post Title: Re: Ninja Gaiden 2 x360

@toonhound:

Thanks, but actually I'm not trying to batch rename my files, I'm trying to convert them using the tool from Surveyor, when running the tool, it prompt for a filename that I have to type manually, so, for converting all the files, I have to run the tool and type the filename for each file...
## Post #88
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2010-02-23T19:25:05+00:00
- Post Title: Re: Ninja Gaiden 2 x360

I see what you're saying now as I just tried the converter out myself.

Oh well copy and paste is our friend for the time being I guess.
## Post #89
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2010-02-24T09:18:40+00:00
- Post Title: Re: Ninja Gaiden 2 x360

> Reply from lionheartuk
>
> i can't run the second program.
for the ps3 files
Tecmo Model Converter v1.05 Sigma.exe
gives me a side by side configuration error.
Yeah you are right...
I recently switched to MS Visual Studio 2005, it seems that there are some fuzzy project settings inside this IDE, of course things work fine for me (the same computer is used to code/test the converters)
Here's the fixed converter, and one thing to notice is that this one is much larger than the 1st.
Enjoy 

> One (silly ?) question, about the textures, I've tryed to import the .obj file in Maya, and the textures are not visible... does the converter link the .dds textures to the model or should I manually associate them one by one ? -.-
No, you need to attach the textures yourself.

> And one request, can you make a version of your converter to batch convert all the files in the same directory without having to manually type each filename ? (I'm using the x360 version)
No, this would be risky, if the converter behaves correctly for one file, there is no guarantee that it'll do so on thousands of files, it may screw you computer if it misses 2 megabytes per model (just an example).
[Tecmo Model Converter v1.05 Sigma.zip](https://xentaxbackup.github.io/file/2798_Tecmo Model Converter v1.05 Sigma.zip)
## Post #90
- Username: orbbu
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Jan 20, 2010 5:36 pm
- Post datetime: 2010-02-24T11:32:30+00:00
- Post Title: Re: Ninja Gaiden 2 x360

OK, I see ...

About the textures, maybe its possible to "guess" what texture go with what surface, by calculating the size (or ratio ?) of the surface & the texture ? Just a suggestion, I'm not sure if it is possible to implement, but it may be worth a try...

For the batch convert, if you could give me your source codes, I think I could try to implement the batch convert (and see about this bug you mentionned, anyway this could only crash the program, I don't think it would do any harm to my pc  ), you can PM me with the src if you want, of course if you don't want to publish your source I would understand, no worries
## Post #91
- Username: onionhead
- Rank: beginner
- Number of posts: 37
- Joined date: Tue Oct 27, 2009 10:02 am
- Post datetime: 2010-02-24T15:51:03+00:00
- Post Title: Re: Ninja Gaiden 2 x360

sorry for being a noob. i own Ninja gaiden sigma 2, but how do i get the files.

edit: sry let me reword this, is there anywhere that host these files or should i say will anybody upload these files.
## Post #92
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-02-24T18:35:22+00:00
- Post Title: Re: Ninja Gaiden 2 x360

the only way to get the files is to use a debug ps3
## Post #93
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2010-02-24T21:00:17+00:00
- Post Title: Re: Ninja Gaiden 2 x360

You would think people would have read the comments by now...
Its mentioned several times in this topic alone, and within others, AND in its OWN topic somewhere.
## Post #94
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2010-02-25T03:48:24+00:00
- Post Title: Re: Ninja Gaiden 2 x360

> Reply from Surveyor
>
> Hi there,
Well I spent nights and nights trying to figure out the skinning for Doax2/Ng2 only to find out that these models are far complicated, they make use of morphing extensively and bones are nowhere to be found.
I did somehow manage to fix the models matrices so now the different body parts are there where they are supposed to be, or at least, because in doax2 character models, the body isn't fully reconstructed, but for the rest of the data (heads, swimsuits, eyes, ...) things work well.
The pic below shows one of the very few models that I succeeded to rig, and given the difficulty to set the skinning, I imagine the animations are a lot harder.
All in all, I think I'll give up on this model format and move on to somthing else. I'll upload the new converter once I finalize it.

Hi Surveyor,

First off I'd like to say thanks for the great tools,

I don't know if this will be of any help or if you're even still interested in these models anymore but I started playing with the DOAX2 models in 3ds max 2009 and I attached the parts that were out of place. here is the world coordinates (the green indicates the ones I snapped aligned). I also assembled the alternate feet in standing position.  

I'm posting this in case it would be possible to implement the coordinates into the model import itself without having to do it manually.
[vcr1obj.pdf](https://xentaxbackup.github.io/file/2806_vcr1obj.pdf)
## Post #95
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2010-02-26T03:15:11+00:00
- Post Title: Re: Ninja Gaiden 2 x360

> Reply from Surveyor
>
> For the xbox 360 converter, things stay the same, except that now (as mentioned earlier) models are correctly assembled, but the main flaw here is that models aren't smooth shaded at all!!

After a little more fiddling with these models I found that by simply exporting the .obj and re-importing it, the smooth shading is back.

I did an STL check on the model and it appears on first import all the faces are separate with open edges, which I guess also makes for a much bigger file size.

I'm working on a maxscript that will export/re-import and postion all the pieces.
there is probably a better solution but I'm no expert.
## Post #96
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2010-02-26T15:03:34+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Here is a very simple maxscript that I'm working on that will take DOAX2 vay01 body, place her feet exactly on the grid and assemble the rest.

I'm very new to maxscript so if someone out there can make this script better please feel free to do so and re-post it with credit in the script to yourself , also I think this will only work in 3ds max 2009 but I'm not sure.

If this is useful to anyone and would like me to continue posting updated scripts [ex. adding head and other models] then please post some comments.
[Assemble_Body.rar](https://xentaxbackup.github.io/file/2812_Assemble_Body.rar)
## Post #97
- Username: Annoying Worlock
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 01, 2010 2:53 am
- Post datetime: 2010-02-28T19:59:44+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Thanks for attaching the files. I am also searching for this files. I can play now my Ninja Gaiden 2 x 360.
## Post #98
- Username: Andersen
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Mar 07, 2010 5:52 am
- Post datetime: 2010-03-07T14:13:42+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Hey,
Would anyone know or can figure out, how to get the ng2 stuff out from the dlc packs? 

[http://www.sendspace.com/file/q18p88](http://www.sendspace.com/file/q18p88)

There's some pretty cool models in the DLC's so it would be a shame for them not to see the light of day:)
## Post #99
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-04-07T21:22:35+00:00
- Post Title: Re: Ninja Gaiden 2 x360

I decided to attack this format a few days ago, and sent Surveyor a message asking if he could provide any framework code/specs, but it looks like he still hasn't been on to check his messages...and in the mean time I guess I've busted the format open pretty well already. 

Good news is, I figured out how the normals are packed! Here you can see one of the bodies being shaded properly with its original normals.
[](http://img59.imageshack.us/i/doax2shade.jpg/)

I also got all the texture stuff sorted out, and object hierarchy data works correctly 100% of the time.
[](http://img175.imageshack.us/i/doax2pix.jpg/)

I still haven't looked into finding/using weighting data, but I'm guessing it's in there (even though vertex morphs appear to be used for The Jiggle and more elaborate hand movements and such). I definitely saw morph frames for the breasts and I think there are some for the hands too. Once I have taken a look at weights and figured out whether they'll be easy to get at, I'll post some source so Surveyor can update his tools (or I guess I might release a tool if Surveyor has already moved on and doesn't want to address the normals/skinning issues).

Oh yeah, I don't have any NG2 assets sitting around to test those too (even though I own NG2 for x360, I don't have the image in conveniently extractable form). I'll check that out later once I can get a hold of some.
## Post #100
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2010-04-08T00:46:09+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Hello MrAdults,
Good to see you here as well, heh.  i had been looking into things in this area to help Surveyor out, and unfortunately i got busy and had not had the time to finish verifying everything.

Glad to see you had more time to get things going than i did.

From what you have stated so far i am assuming you are not using the 360 format vertex declaration information found in the GeoDecl section of the ObjGeo data in the files.  Of course this assumes the Ninja Gaiden 2 data is similar to what you have parsed so far, as i do not currently have access to DOA data.

The vertex declarations list the offsets, data types, and usage as normally done with direct3d, but the format is slightly different on the 360.

Unfortunately my template is not far enough along to give you a good structuring of the data, i will see what i can do about that to help you out.  Let me know if there is anything in particular i can provide in the meantime (if i know it, or can investigate it further..).  i'll see what other information i can dig up for you from what notes i have.

The index data is still usually still UBYTE4, but the weight data is usually FLOAT16_4 (as in 4 half floats), and un fortunately they are not always packed back to back, so it is possible to mistake them for texture coordinates if not careful.  But they usually appear as the last data in the vertex specification, but as mentioned it would be safer to parse the vertex declarations for accurate offsets, types, usage, etc.

i really need to get an app up and running to visualize mesh, texture, and animation data better as with your apps.  Would really help to allow me to get more of these formats off my plate and finalized as much as possible.
## Post #101
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-04-08T01:58:50+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Oh, no, I am using the element declaration structures and using them to reliably find position/uv/normal. I dunno what gave you the impression I wasn't, though.  Unless I'm missing something. Everything that's been rendered/handled presently should be as "by the book" as possible, but I'll only know for sure if it's bullet-proof once I get my hands on some NG2 data. But, at least, all the girls, stages, and costumes seem to appear correct right out of the box.
Edit: Oh, right, since I said I hadn't found the weighting data, you probably assumed I wasn't using the decl info. I'd figured it was somewhere in the other components that I hadn't mapped out yet, but hadn't actually figured out which one yet. (and still haven't, but I suppose it's just a matter of actually looking at the data, once I get around to it)

I have proper handling for all of the morph targets as well, although I'm not sure they do anyone much good, except for making things like this!
[http://www.youtube.com/watch?v=vgkKprVyQl8](http://www.youtube.com/watch?v=vgkKprVyQl8)
## Post #102
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2010-04-08T02:16:22+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Heh, ok, cool.  i stand corrected.  i meant to phrase that sentence as a question anyway; my lack of typing skills at work.

Dang, i feel like i am moving so slow lately.

Glad to see the progress.
## Post #103
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-04-08T03:09:47+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Haha, yeah, this stuff is time-consuming. I've just been on a self-imposed "vacation" for the past week, which involves nothing but a rotation of hanging around outside by the pool, watching television shows I'm weeks behind on, and tearing games apart. If only life could be so sweet forever...  I've gotta get back to work next week, but maybe I can nail a couple more games before it's back to slaving in the corporate abyss.
## Post #104
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-04-09T20:09:47+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Well, I extracted my NG2 image, and all those models work just the same as the DOA ones:

[http://img94.imageshack.us/img94/7870/ng2pix.jpg](http://img94.imageshack.us/img94/7870/ng2pix.jpg)

Lots of elaborate stage models in that one.  I took a like at those .ng2 files too, Surveyor, but I also saw no file index. I looked around at the other file types in the image too for some kind of index list but couldn't find one. I guess it's probable that the lists are hardcoded in the binary...or something encrypted or compressed with a weird compression type somewhere. So I just used your tool to extract the gmd's. Unfortunately, this means the actual animation data is still buried somewhere inside those ng2's (since the GMD ANM chunk is always practically empty, it's probably just referring to another "global" animation table or something).

But anyway, I wanted to figure out the skeletal data, so I've been focusing on DOA still (where the animation data is clearly visible in the mot pack). I checked out those mot files, though, and again, there's no base bone/hierarchy data to be found (again unless it is weirdly encrypted/compressed, which wouldn't make much sense, at least not for the base pose). I've also noted that many pieces on the DOA girl models don't contain ANY weights! This even includes the "breast piece", even though I would've thought for sure those boobies were still boned in addition to utilizing morph targets. I mapped out "vtn1.tpr" (Tina's body) like so in terms of weights-per-mesh (I only noted the actual object counts, but all draw lists under each object happen to have identical counts on this one). Index values omitted means *0* weights:

> 3 - 2 weights
>
> 4 - 2 weights
>
> 5 - 2 weights
>
> 6 - 4 weights
>
> 7 - 2 weights
>
> 11 - 3 weights
>
> 13 - 2 weights
>
> 15 - 2 weights
>
> 16 - 2 weights
>
> 20 - 2 weights
>
> 21 - 3 weights
>
> 22 - 2 weights
>
> 23 - 2 weights
>
> 24 - 2 weights
>
> 25 - 4 weights
>
> 26 - 2 weights
>
> 30 - 3 weights
>
> 32 - 2 weights
>
> 34 - 2 weights
>
> 35 - 2 weights
>
> 39 - 2 weights
>
> 40 - 3 weights

And here's the kicker: None of the vertex components in Tina's body are *actually* bone indices. I've verified this to be 100% certain by mapping them all out (and the type of data can be determined, 100% of the time, using the decl info...so there's no mistake here). Here's the common cases for vertex sizes 32-48 in Tina (no vertex sizes above 48 exist in the model):

> 32-byte Vertex
>
> --
>
> 00-12: Position
>
> 12-16: Normal
>
> 16-20: UV1
>
> 20-24: UV2 (seems 100% identical to UV1 in DOA models)
>
> 24-28: UV3 (seems 100% identical to UV1 in DOA models)
>
> 28-32: Tangent/Binormal (decoded just like Normal)
>
> 
>
> 40-byte Vertex
>
> --
>
> 00-12: Position
>
> 12-16: Normal
>
> 16-20: UV1
>
> 20-24: UV2 (seems 100% identical to UV1 in DOA models)
>
> 24-28: UV3 (seems 100% identical to UV1 in DOA models)
>
> 28-32: Tangent/Binormal (decoded just like Normal)
>
> 32-40: 2 weights (complete 32-bit floats)
>
> 
>
> 44-byte Vertex
>
> --
>
> 00-12: Position
>
> 12-16: Normal
>
> 16-20: UV1
>
> 20-24: UV2 (seems 100% identical to UV1 in DOA models)
>
> 24-28: UV3 (seems 100% identical to UV1 in DOA models)
>
> 28-32: Tangent/Binormal (decoded just like Normal)
>
> 32-44: 3 weights (complete 32-bit floats)
>
> 
>
> 48-byte Vertex
>
> --
>
> 00-12: Position
>
> 12-16: Normal
>
> 16-20: UV1
>
> 20-24: UV2 (seems 100% identical to UV1 in DOA models)
>
> 24-28: UV3 (seems 100% identical to UV1 in DOA models)
>
> 28-32: Tangent/Binormal (decoded just like Normal)
>
> 32-48: 4 weights (complete 32-bit floats)

However, those "weight" values seem like they definitely are weights, they always add up to 1.0 and occasionally 0 out components at the start or middle as a way of saying "no weight influence here".

So this leaves us with two possibilities: Either there's a max of 4 bones per draw (this would be insane!), or there's another set of per-vertex bone indices somewhere (actually, this is kind of insane too, but less insane). But where could they possibly be? They damn sure aren't anywhere in the XPR2, and DOAX2 has no concept of "GMD" structure, and they damn sure aren't in the motion data, and...well, I don't see any other files in DOAX2 to even consider searching in.

But I did notice that the Hie chunk contains, after the "bone" index and its parent index, a count WORD, and then WORD's (either "bone" or mesh indices) up to count. I had assumed this was simply "children" or something, but count is always a value from 0-3 (in every single DOA model), and when you consider that the "base bone" plus the "count bones" would add up to 1-4 bones for the weights....crazy as it seems, it does support the "4 bones per draw" theory. So I went ahead and tried those out in various combinations (as both indexes into the "bone" list and into the mesh list) to fill out the bone index array for each surface and supplement the actual weight values, but, nothing I tried looked right.

So, I have no ideas now, really. Surveyor, revelation, any thoughts on this madness?
## Post #105
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-04-09T21:47:50+00:00
- Post Title: Re: Ninja Gaiden 2 x360

I have seen developers hide the file names inside the xex / xbe files in xbox360 games i can try to pull the name table out for you if you post the file.
## Post #106
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-04-09T23:03:09+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Well slap my ass! Thanks for mentioning that chrrox, or I probably wouldn't have even bothered looking for a freely available xex decryption tool. I'd just assumed such things would be crushed by Microsoft immediately.

Well, after decrypting NG2's xex, sure enough, there's the full file table. Seems like NG2's animations are "mtn" files, most likely very similar or identical to DOAX2's "mot" files. Unfortunately, though, this does not solve the mystery of either format regarding bone weights.

Also, chrrox, I still haven't gotten around to investigating those Fist of the North Star files. I'll have a look once I've either solved or given up on proper skeletal/bone index data in these Tecmo models.
## Post #107
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2010-04-10T00:32:38+00:00
- Post Title: Re: Ninja Gaiden 2 x360

The list of indices at the end of each joint are indeed the children.  There a few gmd files for NG2 that have more then 3 children, a couple have had 5 in some of the files i have seen.  Unfortunately as with most of the other formats i have worked, as i have mentioned my code base is not in a state that easily allows me to visually verify things out of the hex editor.  But i have stepped through those indices and the parent value as i have mapped them match and seem to verify the parent child relationship.  i will see if i can get my code u pand running to render properly and see what happens.  Do you have the DOA file you mentioned earlier so that i could possibly compare aginst what i am seeing within the NG2 files?  Otherwise i will see what i can do in the meantime, heh.  i will probably go ahead and atleast output the vertex declarations for the files i am investigating and start mapping what indices are being reported for the vertices as well.
## Post #108
- Username: Andersen
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Mar 07, 2010 5:52 am
- Post datetime: 2010-04-10T13:31:55+00:00
- Post Title: Re: Ninja Gaiden 2 x360

The contents of this post was deleted because of possible forum rules violation.
## Post #109
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-04-11T00:32:22+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Well, I think there is some legit skeletal data in NG2, but none in most (maybe all) of the DOAX2 girls. They use morph targets and seem to be animated by unique "influence lists" in a pretty fascinating way, although this is purely a guess based on what I was able to make out with only a hex editor and some screwing around with bits to try to decode the motion stream. NG2 models probably use that extensively as well, though I didn't actually look at NG2's motion data.

But since it's its own unique flavor of data that I in reality have no clue whatsoever about, I'm just gonna throw in the towel on this one and release source for my toolset module right here. Primarily for other programmers that happen upon this in the future and go "man, why didn't they post specs or source?!", since I know Surveyor and revelation already have most of this stuff documented privately.  As usual, it's just ripped right out of the rest of my toolset and is in my sloppy-as-hell hammered-out-overnight style, so it's only enough to get the proper specs for anyone who wants to do their own project with this data.
[model_tpr.zip](https://xentaxbackup.github.io/file/2921_model_tpr.zip)
## Post #110
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2010-04-11T08:21:38+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Hi,

> Would anyone know or can figure out, how to get the ng2 stuff out from the dlc packs?
The fiend hayabusa you posted here contains 2 gmd files + some other data, the texture extractor works on both models but not the model converter as they changed the data base adress to something else. I'll have a deeper look, meanwhile, you can use a hex editor and get the 2 gmd's and apply the texture extractor on them.

> Unfortunately, though, this does not solve the mystery of either format regarding bone weights.
It'll probably help if you have the ng2 sigma (ps3) models, from what I saw, ps3 files seem clearer, unfortunately I deleted them when I dropped the reasearch on this format, You can ask Chrrox if he still has them.
It's also worth mentioning that all doax2 body models share the same structure in terms of vertex buffer and index buffer alignement: 

In a post on page 6, I showed a rigged model of a robot enemy, I've chosen this model because it's a robot and robots have rigid limbs so there's only one bone per vertex. skin weights turned out to be correct, and I used the joints in the "Hie" chunk to get this pose which leads to the conclusion that these "joints" actually play a role in animation. But when sikn weights are applied to soft bodies (hayabusa or sonia) they don't map correctly to the joints (for example left thumb bone influences right leg vertices) so there's probably a bone group chunk somewhere to be discovered.
All this still doesn't explain how animation is being performed, for example the hands on ng2 characters: they have 1 joint and still move beautifully unlike in doax2 where the girls look like if they had plastic hands and there's a very limited set of hand poses (when they push against sand, the hand pose looks horribly unrealistic) IMO, Tecmo developers used morphing on Doax2 then switched to bone animation in Ng2.

In an interview with the developers (present in the Softimage website - showcasing how incredible softimage is), they talked about how they used motion capture to get face animation and the pic below shows plenty of face bones which can't be found in the model files, one way to make sure skin weights are indeed used (I hardly imagine a next gen engine relying on morphing) is to print these weights as shown in the pic below.

I've been through many japanese made games and one thought always comes into my mind: the only thing japanese developers excel at is art, their programming is a total mess, don't you agree ? 
[bones.JPG](https://xentaxbackup.github.io/file/2923_bones.JPG)
## Post #111
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-04-11T09:55:06+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Yeah, displaying weights like that might help. Assuming you have the bone index data on the verts in NG2, to know how to color according to bone reference. As mentioned, they don't exist in the DOAX2 models, but I really haven't looked for bone indices in the NG2 models at all. If you think there is traditional bone data, I guess you must have spotted them.  But something bone-like surely exists in DOAX2, still (something to utilize those "indexless" weights), and it's got to be buried in the motion data if it's anywhere. So if NG2 uses traditional bones, it's pretty likely it uses bones AND whatever DOAX2 is using.

Actually, I should say DOAX2 *does* seem to use "bones", the bones we see in the Hie chunk. But what's missing are the bone indexes, which leads me to believe those bones are not used in a traditional manner. If they really animated the bodies normally with vertex morphs, there would be a whoooole shitload of data.  No way that's in the motion files, cause you can see quite plainly in most sections they are not compressed (and never mind that, the cost of all those morph frames in memory would be horrifying, with their vertex counts).

Those motion files have pretty clearly defined offset tables and sections, and some of the data streams are easily-readable, but I haven't actually tried parsing the sections out and examining each. A lot of the data in there could easily be a "reference list" for the weightless verts, if you want to interpret it that way. But man, that just seems so ridiculous, to store those arrays in your motion data, that I don't even buy into the theory enough to try it out. Then again, if it's not there, it's nowhere. What a mess indeed.

I did notice that in the DOAX2 girls, for example, the whole lower torso does seem to only have a couple different locations it seems to want to be weighted to. In fact, I can map out those weights to a couple bones from the Hie chunk, and it does look perfect (can bend it nice and fluid in Max with the Hie skeleton). But I haven't seen references to those bones anywhere in the actual XPR2... But it really makes the silly "only 4 bones per draw" limitation quite believable for the DOAX2 models. Quite possible the mot data just contains that obscure "which 4 bones to use for which surface" connection inside of it.

I'm quite curious if revelation has seen anything I didn't in Tina's body XPR.

Team Ninja does seem to have done some weird crap in here, and from what I do know for sure of the DOAX2 models, there sure is a hell of a lot of vertex memory going to waste. But, at least in NG2's case, it's hard to argue with the final performance+visuals they managed to pull out.
## Post #112
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-04-11T13:47:28+00:00
- Post Title: Re: Ninja Gaiden 2 x360

my theory through observing the game play, was that they based the mechanics off the old arcade version of DOA1. meaning your character has no skinning, just animating nodes which a series of blocks are connected to.

so in the new DOA, they used the same principle. not uncommmon really, they dice the models into pieces and make everything a static mesh attached to the animation nodes. then on only certain required meshes, need for skinning. they applied some sort of vertex blending, to deform that particular mesh.

like example

[HAND(Static)] - [Wrist(Skinned)] - [Forearm(Static)] - [Elbow(Skinned)] - [UpperArm(Static)] - [Shoulder(Skinned)]


when I asked my friend if he could find anything in the CAT files for DOAu for xbox1. all he found where specious vertex lists
your write these points into a 3d editor and its pretty clear what they were. they just appear to be the edge vertices where each Skinned mesh joins to each static mesh. so basically they are attaching or welding each skinned piece to every static piece. but again looking at the game play, no mesh welding for smoothing is preformed.. many of times you can see those mesh parts separate O.O

so thats where my theory comes to. DOA never used skinning at all. just static meshes, a vertex welding or attachment list held the skinned parts to each static part. although the skinned meshes are not really skinned, because I believe the engine uses some auto rigging method, to blend the transitions together when they deform. not sure why they wanted to avoid this?

anyway these are my thoughts being a gamer of DOA, since I first played it on PS1.

thanks for reading;
-mariokart64n
## Post #113
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-04-11T20:44:01+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Hi Mario_Kart (haven't I seen you post on my web site before?),

I had suspect something like this too, except it's not so much "welding data" as it is just a very small batch of "bones" as seen in the Hie data of this format (in DOAX2's case, dunno about previous titles).

You definitely can't see any "seams" whatsoever in DOAX2 and the girls all bend very nicely. But I believe the bones we see combined with vertex morphs and just a few bones per surface (since the meshes are split up so much) would be more than enough for those results.

It's a bizarrely primitive method, though, if it is really what they've done. Rare for a game made this generation, or even the last! Although supposedly Team Ninja's programmers are the best in the world at what they do, at least according to Itagaki, so who am I to question? 

Edit: Oh yeah, Surveyor, I took a look at that DLC too, but I noticed there are big chunks of crap spread throughout all the files! It exists in some of the textures too (you can see the corrupted areas if you try to take the data as-is, or at least I can). Must be an oddity of the "LIVE" container, or could it just be a bad rip?
## Post #114
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2010-04-12T09:27:37+00:00
- Post Title: Re: Ninja Gaiden 2 x360

> Although supposedly Team Ninja's programmers are the best in the world at what they do at least according to Itagaki
And who the hell is Itagaki?? Well there's something very unique in this ng2 engine (comapred with the current gen engines) is that instead of going bumpy on low res models (John Carmack's bump map everything approach) this engine uses high res models and very little bump maps, getting the same performance/visuals as a regular engine, but here artists don't have to go through the process of downscaling their models and are free to unleash their artistic rage (and thus are artistically better games)
## Post #115
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-04-12T22:06:34+00:00
- Post Title: Re: Ninja Gaiden 2 x360

> Reply from Surveyor
>
> Although supposedly Team Ninja's programmers are the best in the world at what they do at least according to Itagaki
And who the hell is Itagaki?? Well there's something very unique in this ng2 engine (comapred with the current gen engines) is that instead of going bumpy on low res models (John Carmack's bump map everything approach) this engine uses high res models and very little bump maps, getting the same performance/visuals as a regular engine, but here artists don't have to go through the process of downscaling their models and are free to unleash their artistic rage (and thus are artistically better games)

Kind of...although really, the raw triangle counts on Ryu for example are only around 35k-40k - it fools you, because there is a separate "shell" mesh in the same model file! You can delete a whole layer from the model and it looks exactly the same. I don't know if they chose to use this method to render a separate specular layer or what, although that would be even more silly if so. It definitely is not a LOD, because the geometry is identical.

So compared to this, games like FF13 use similar triangle counts (25k-45k, usually), but with fully normal-mapped models, which clearly came from many-millions-of-triangles, hand-sculpted models. In this regard, I think Team Ninja didn't do a great job.  But their art does still look great, in the game, and it runs blazingly fast. I think, in the end, this is all a render guy should wish for, so they still did their job well enough.
## Post #116
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-04-13T01:27:55+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Hi to all. Can we convert the model already with bones and weights?
## Post #117
- Username: undead
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 03, 2010 9:04 am
- Post datetime: 2010-04-13T03:01:54+00:00
- Post Title: Re: Ninja Gaiden 2 x360

nop
## Post #118
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2010-04-14T05:19:55+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Well,
After all that not sure how many people are still even looking into this format, heh.

Not too much new, although i have had the chance to find a verify a few things.  As such i think i have found the joint indices necessary for the DOA skinning data.  As mentioned it does appear to usually max at around 4 indices, if they are present at all.

```
{
	// 0x00
	union
	{
		uint64 tagValue      <format = hex>;
		char   tagString[8];
	} dataTag;
	
	uint16 unknown0x08[2]  <format = hex>;
	uint32 headerSize      <format = hex>;
	// 0x10
	uint32 dataSize        <format = hex>;
	uint32 tableCount; // total offset array count
	uint32 dataCount; // number of valid entries in table
	uint32 unknown0x1C;
	// 0x20
	uint32 tableOffset     <format = hex>;
	uint32 unknown0x24[3];
	
	local int64 filePos = FTell();
	FSeek(startof(this) + tableOffset);
	uint32 dataOffsets[tableCount] <format = hex>;
	FSeek(filePos);
};

struct OBJECT_INFO_DATA
{
	// 0x00
	uint32 index;
	uint32 unknown0x04;
	uint32 unknown0x08;
	uint32 unknown0x0C;
	// 0x10
	uint32 unknown0x10[4];
	// 0x20
	float3x4 unknown0x20;
};

struct OBJECT_INFO
{
	struct DATA_HEADER header;
	
	// 0x30
	uint16 unknown0x30;
	uint16 unknown0x32;
	uint32 unknownIndex; // since Geo, Info, and Joint counts usually match, i am assuming just a local copy of this structures index
	uint32 unknown0x38;
	uint32 jointCount;
	
	struct OBJECT_INFO_DATA unknownData;
	
	if (jointCount > 0)
	{
		uint16 jointIndices[jointCount];
	}
	
	if (header.tableCount > 0 && header.dataCount > 0)
	{
		struct
		{
			local int64 dataOffset = 0;
			local uint32 dataNum = 0;
			for (dataNum = 0; dataNum < header.tableCount; ++dataNum)
			{
				if (header.dataOffsets[dataNum] != 0)
				{
					local int64 filePos = FTell();
					dataOffset = (startof(parentof(this)) + header.dataOffsets[dataNum]);
					FSeek(dataOffset);
					struct OBJECT_INFO_DATA objectData;
					FSeek(filePos);
				}
			}
		} childData;
	}
}

```


Sorry for the syntax, as this is only part of a larger template for 010 Editor.  If not obvious these structures correspond to the objInfoMeat_s and objInfoHdr_s structures from the code posted by MrAdults.  The only real important thing here is the jointCount value at about 0x3C bytes into the ObjInfo data and the associated list of indices after the initial data structures floats.

Hopefully those that have a more readily available rendering framework for these formats will be able to test and verify and/or disprove this information.  Hopefully this will work out for the DOA information.

Unfortunately, so far i have not found too many files that have this information present when it come to NG2 data.  Since the joint indices are present in the actual vertex data, unlike DOA, i am assuming a similar list, initial joint and count, or other sort of indicator is present somewhere to specify which joints are actually used for each mesh.  Still a good bit of unknowns as you can tell from some of the information above.

i really need to make some time to get some real coding in, heh.

Hope it helps.
## Post #119
- Username: undead
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 03, 2010 9:04 am
- Post datetime: 2010-04-14T05:32:44+00:00
- Post Title: Re: Ninja Gaiden 2 x360

first of all thanks for the tools

could someone tell me how to solve the smooth problem
I'm new at this and I could not solve
## Post #120
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-04-14T07:17:47+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Nice find, revelation!
[http://img89.imageshack.us/i/tinapose.jpg/](http://img89.imageshack.us/i/tinapose.jpg/)

There's a bit of hierarchical dysfunction going on (some chains are flattened, surely compensated for in motion data), but all the weights work nicely with the bones they're associated with.

I can't believe there ended up being a 4-bones-per-draw limit after all, but it looks like we've finally got evidence to demonstrate such. 

Oh yeah, and those indices are actually into the *mesh* list, then you use the index of the bone which is pointed at by the mesh.

> Reply from undead
>
> first of all thanks for the tools

could someone tell me how to solve the smooth problem
I'm new at this and I could not solve
Surveyor knows how to decode normals now, so it'll probably be fixed whenever he gets around to updating his tool. Otherwise you'll have to smooth out normals manually, but auto-smoothing probably won't look perfect on many models.
## Post #121
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2010-05-11T10:33:56+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Hi,
I fixed the texture extractor and now it works for every texture size, including the ones smaller than 128x128. I just thought some people might still be intrrested so here it is 
Have fun 
[Tecmo Texture Extractor.zip](https://xentaxbackup.github.io/file/3030_Tecmo Texture Extractor.zip)
## Post #122
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-05-12T02:48:44+00:00
- Post Title: Re: Ninja Gaiden 2 x360

great, glad to finally hear the small size glitch is fixed. this will make mass rippingalot easier.
## Post #123
- Username: kapatan
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri May 21, 2010 8:03 am
- Post datetime: 2010-05-23T14:31:45+00:00
- Post Title: Re: Ninja Gaiden 2 x360

I am newcomer in this forum.

Hi Surveyor.
Very very thanks for powerful tool.

Unfortunately these extractor don't support doa4.
Could you make a model extractor supported doa4?
I don't have 3dsmax, so I can't use Voltthorn's extractor.

I want to ask you when you have time.
## Post #124
- Username: andthen619
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 18, 2010 7:43 pm
- Post datetime: 2010-06-09T23:20:41+00:00
- Post Title: Re: Ninja Gaiden 2 x360

can some post volthorn's extractor for doa4 please
## Post #125
- Username: CDD Xtreme
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Jun 14, 2010 3:24 pm
- Post datetime: 2010-06-14T08:56:28+00:00
- Post Title: Re: Ninja Gaiden 2 x360

> Reply from undead
>
> first of all thanks for the tools

could someone tell me how to solve the smooth problem
I'm new at this and I could not solve

( Re - Edit ) - iM not gonna nother ..,I mean bother ....
I should have found this topic sooner before this was virtually hollow.
## Post #126
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-06-14T09:39:00+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Why noesis won't export weight data from ninja gaiden 2 models?
## Post #127
- Username: CDD Xtreme
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Jun 14, 2010 3:24 pm
- Post datetime: 2010-06-17T16:51:28+00:00
- Post Title: Re: Ninja Gaiden 2 x360

> Reply from Tosyk
>
> Why noesis won't export weight data from ninja gaiden 2 models?

Well that was a close ride - we almost had what we wanted but atleast we didnt go back empty handed, from this point this topic might be dead soon....Im just Amazed at how underground this thing is - throughout all of google I could only find a select few pages dedicated on Doax 2 with this being in the lead . Well done everyone!
## Post #128
- Username: Andersen
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Mar 07, 2010 5:52 am
- Post datetime: 2010-06-17T21:19:29+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Surveyor, Did you ever find a way to export the gmd's from the dlc and the export mesh and texture from the gmd's? And if so, could you tell me how you done this?
## Post #129
- Username: Cirith
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 16, 2010 3:45 am
- Post datetime: 2010-06-26T20:35:04+00:00
- Post Title: Re: Ninja Gaiden 2 x360

The contents of this post was deleted because of possible forum rules violation.
## Post #130
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-06-26T21:12:22+00:00
- Post Title: Re: Ninja Gaiden 2 x360

why would you want the online game they are a lot worse then the models in the  360 game
## Post #131
- Username: Cirith
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 16, 2010 3:45 am
- Post datetime: 2010-06-27T13:38:16+00:00
- Post Title: Re: Ninja Gaiden 2 x360

> Reply from chrrox
>
> why would you want the online game they are a lot worse then the models in the  360 game

I want's to extract they from this files..and then i found the way how to import another model's and suit's to this game...i have not Xbox and very like PC fightings (DOA OL is one of it)

This is Ayane suits from this game (DOA OL) [http://www.picamatic.com/view/3924365_ayane_numbers/](http://www.picamatic.com/view/3924365_ayane_numbers/)
## Post #132
- Username: onionhead
- Rank: beginner
- Number of posts: 37
- Joined date: Tue Oct 27, 2009 10:02 am
- Post datetime: 2010-06-29T12:45:47+00:00
- Post Title: Re: Ninja Gaiden 2 x360

i have found an iso for NG2 but the contents inside are only files like BUP .. IFO VOB files and i have no idea what to use to extract the gmd files? is there like a extractor for this?
## Post #133
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2010-06-29T19:29:28+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Damm, I'm gonna post this thrice:

Look for xbox backup creator and you'll have access to the game data ¬¬
## Post #134
- Username: sidneymadmax
- Rank: beginner
- Number of posts: 35
- Joined date: Fri Sep 17, 2010 11:10 pm
- Post datetime: 2010-09-19T19:03:41+00:00
- Post Title: Re: Ninja Gaiden 2 x360

[http://i50.tinypic.com/2qajkid.jpg](http://i50.tinypic.com/2qajkid.jpg)

NG2 in which file this I did not think this kid...
## Post #135
- Username: Arrow96
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Oct 08, 2010 2:09 pm
- Post datetime: 2010-10-20T14:03:35+00:00
- Post Title: Re: Ninja Gaiden 2 x360

> Reply from onionhead
>
> i have found an iso for NG2 but the contents inside are only files like BUP .. IFO VOB files and i have no idea what to use to extract the gmd files? is there like a extractor for this?

GameMaker, WinAmp and jetAudioBasic can help you extract your gmd files.
## Post #136
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2010-10-20T18:47:52+00:00
- Post Title: Re: Ninja Gaiden 2 x360

> Reply from sidneymadmax
>
> http://i50.tinypic.com/2qajkid.jpg

NG2 in which file this I did not think this kid...

I one of the files of Dead or Alive 4.
## Post #137
- Username: sidneymadmax
- Rank: beginner
- Number of posts: 35
- Joined date: Fri Sep 17, 2010 11:10 pm
- Post datetime: 2010-10-21T17:11:34+00:00
- Post Title: Re: Ninja Gaiden 2 x360

> Reply from Darko
>
> sidneymadmax wrote:http://i50.tinypic.com/2qajkid.jpg

NG2 in which file this I did not think this kid...

I one of the files of Dead or Alive 4.
is to pass me link (tpr)
## Post #138
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-10-30T18:17:10+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Surveyor can you look at Sigma 2 files from the PS3. I ran your converter but get this error:

```
| Model converter Fevrier 2010

model filename: rei.gmd
models: 137
vbuffers: 0
ibuffers: 0
Invalid HieLay chunk at [531824] !
```


maybe a endian difference? I dont have xbox sigma files to compare with.

here are PS3 samples;
[http://www.mediafire.com/?iyyzo626ai646ej](http://www.mediafire.com/?iyyzo626ai646ej)
## Post #139
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2010-10-30T19:03:51+00:00
- Post Title: Re: Ninja Gaiden 2 x360

> Reply from mariokart64n
>
> Surveyor can you look at Sigma 2 files from the PS3. I ran your converter but get this error:
Code: Select all| Surveyor's Ninja Gaiden 2 Sigma
| Model converter Fevrier 2010

model filename: rei.gmd
models: 137
vbuffers: 0
ibuffers: 0
Invalid HieLay chunk at [531824] !

maybe a endian difference? I dont have xbox sigma files to compare with.

here are PS3 samples;
http://www.mediafire.com/?iyyzo626ai646ej

Wanna the 360 files??
## Post #140
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-10-30T23:53:06+00:00
- Post Title: Re: Ninja Gaiden 2 x360

thanks, but I heard the PS3 version had new and better models. not interested in the outdated 360 ones.
## Post #141
- Username: spartan00j
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Oct 31, 2010 10:57 am
- Post datetime: 2010-10-31T17:18:01+00:00
- Post Title: Re: Ninja Gaiden 2 x360

i would like the tools posted to work on the ps3 as well. i have ninja gaiden sigma 2 ps3 files extracted and ready to be converted. please Surveyor do this for the fans, the hackers, and the people who want to use the models in animations. like me
## Post #142
- Username: LastSamurai
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 23, 2010 4:39 pm
- Post datetime: 2010-11-16T14:52:22+00:00
- Post Title: Re: Ninja Gaiden 2 x360

cheers Surveyor 

heya all, just want to drop a post here as well... you guys are awesome and thank you for the hard work done here so far
Also, and I think along other people, would like to have a look at the Ninja Gaiden Sigma 2 content, if only the .GMD format could be read. You folks think is possible?


edit:

PS3 version and xbox360
[http://www.eurogamer.net/articles/digit ... cle?page=3](http://www.eurogamer.net/articles/digitalfoundry-ninjagaiden2-faceoff-article?page=3)
## Post #143
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2011-02-25T04:43:35+00:00
- Post Title: Re: Ninja Gaiden 2 x360

hope this thread doesn't die

I finally got the ninja gaiden sigma 2 files and just learned how to extract the psarc files and obtained the model files.
I am hoping to learn to get the 3d models out some day
## Post #144
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2011-02-27T04:41:29+00:00
- Post Title: Re: Ninja Gaiden 2 x360

any one mind sharing the extracted 3d models of the characters? thanks
## Post #145
- Username: PS3Fan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Mar 06, 2011 3:43 pm
- Post datetime: 2011-03-06T08:28:51+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Hi I'm a bit new at this, but I read through all 10 pages of the thread here and still can't extract anything from the sample .gmd files that were posted sporadically along the thread.

All I really need is for a high res standard pose image of Ayane or Rachel (standing up, arms out to sides, palms down, all parts attached, ) from the front and one side, no hair, no clothing, and one with clothing and hair, as well as a front and side close up shot of the head I can try to replicate a model in Maya 2011 from the ground up.  

Thank you very much.
## Post #146
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2011-03-10T10:03:34+00:00
- Post Title: Re: Ninja Gaiden 2 x360

not possible, all the Ninja Gaiden models I found so far are clothed all parts attached. They only need to render all the parts in one piece so there's no reason for Tecmo to render the girls naked and then render the cloth separately. You can try DOAX models.
## Post #147
- Username: sidneymadmax
- Rank: beginner
- Number of posts: 35
- Joined date: Fri Sep 17, 2010 11:10 pm
- Post datetime: 2011-04-12T18:13:54+00:00
- Post Title: Re: Ninja Gaiden 2 x360

thanks for everything I got = D

[http://sidneymadmax.deviantart.com/gall ... 4#/d3ba2ew](http://sidneymadmax.deviantart.com/gallery/?offset=24#/d3ba2ew)
## Post #148
- Username: XLAX
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Oct 04, 2011 8:18 am
- Post datetime: 2011-10-15T00:52:35+00:00
- Post Title: Re: Ninja Gaiden 2 x360

any news with this?
## Post #149
- Username: khanbot
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Dec 13, 2011 6:12 pm
- Post datetime: 2012-03-02T15:11:52+00:00
- Post Title: Re: Ninja Gaiden 2 x360

> Reply from Modman69
>
> Surveyor wrote:For the xbox 360 converter, things stay the same, except that now (as mentioned earlier) models are correctly assembled, but the main flaw here is that models aren't smooth shaded at all!!

After a little more fiddling with these models I found that by simply exporting the .obj and re-importing it, the smooth shading is back.

I did an STL check on the model and it appears on first import all the faces are separate with open edges, which I guess also makes for a much bigger file size.

hi, could you please if you read this, explain how to accomplish this?  i guess I am having this no smooth shading problem, i tried exporting from max and importing again but it didn't solve anything.  
thanks
## Post #150
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-03-03T05:17:11+00:00
- Post Title: Re: Ninja Gaiden 2 x360

> Reply from khanbot
>
> Modman69 wrote:Surveyor wrote:For the xbox 360 converter, things stay the same, except that now (as mentioned earlier) models are correctly assembled, but the main flaw here is that models aren't smooth shaded at all!!

After a little more fiddling with these models I found that by simply exporting the .obj and re-importing it, the smooth shading is back.

I did an STL check on the model and it appears on first import all the faces are separate with open edges, which I guess also makes for a much bigger file size.


hi, could you please if you read this, explain how to accomplish this?  i guess I am having this no smooth shading problem, i tried exporting from max and importing again but it didn't solve anything.  
thanks

Are you using noesis??
## Post #151
- Username: khanbot
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Dec 13, 2011 6:12 pm
- Post datetime: 2012-03-03T05:44:05+00:00
- Post Title: Re: Ninja Gaiden 2 x360

No, not neosis.  I've been using tools provided in this thread, ng2 extractor, tecmo model converter and tecmo texture extractor, all posted by surveyor.    

Is there any other way??

Do neosis works????
## Post #152
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-03-03T07:44:45+00:00
- Post Title: Re: Ninja Gaiden 2 x360

> Reply from khanbot
>
> No, not neosis.  I've been using tools provided in this thread, ng2 extractor, tecmo model converter and tecmo texture extractor, all posted by surveyor.    

Is there any other way??

Do neosis works????

Hell yeah, just export your model to collada format and use the plugins provided by the open collada site, it also supports DOAX2 and you can get models fully rigged.

[http://oasis.xentax.com/index.php?content=downloads](http://oasis.xentax.com/index.php?content=downloads)
## Post #153
- Username: khanbot
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Dec 13, 2011 6:12 pm
- Post datetime: 2012-03-03T10:05:46+00:00
- Post Title: Re: Ninja Gaiden 2 x360

> Reply from Darko
>
> 
Hell yeah, just export your model to collada format and use the plugins provided by the open collada site, it also supports DOAX2 and you can get models fully rigged.

http://oasis.xentax.com/index.php?content=downloads

yesss!!!  thanks man, you seems to always save the day whenever I pop a noob question!!   

so just to make sure I am getting it right, I open .gmd straight into neosis, or after the extraction I open the .obj into it?  hopefully this be my last question on this one!
## Post #154
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-03-03T15:36:56+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Open the gmd through you navigation tree tool, then go to file>export and there you select the format you want (collada, smd, psk, obj, fbx, etc...) select your texture format, tick flip uv and rotate options and in command type "-scale 100". Make sure you select a select a folder where you want to export your model if not, your model will be exported in the same folder where you have your gmd (normally you have all your game files in one folder). And that's all.

One thing I forgot to metion, noesis doesn't support NG2 weights, only DOAX2.

Byep
## Post #155
- Username: khanbot
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Dec 13, 2011 6:12 pm
- Post datetime: 2012-03-03T15:54:09+00:00
- Post Title: Re: Ninja Gaiden 2 x360

got it, tested, solved.  
Thanks again!
## Post #156
- Username: Vashey
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Mar 15, 2011 9:47 pm
- Post datetime: 2012-03-06T07:05:59+00:00
- Post Title: Re: Ninja Gaiden 2 x360

EDIT:

Ok so I got through Tenchu Z files with Gaelx360 and then I extracted all the content, here is what I have:



(I don't know how he made this soft but he is a genius, I ask myself why you didn't precise that you use this thing to drill into 360 games)

Then I check the .bin in the "model/bin " with an extractor, and thats what I get:



Basically I'm stuck here, I don't know what else to do.


Also I was wondering if you people could upload Sonia's model (from NG2) with textures please?


Thanks a lot.
## Post #157
- Username: Vashey
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Mar 15, 2011 9:47 pm
- Post datetime: 2012-03-07T20:20:25+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Ok apparently I have to use Hex Editor to get into theses files, I don't understand it all but please if you got any extra info guys let me know.
## Post #158
- Username: Kaiyena
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 08, 2015 3:49 am
- Post datetime: 2015-08-07T20:03:26+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Any way I'd be able to get the sound effects? I know this topic is old, but hey.
## Post #159
- Username: Doutor Gori
- Rank: n00b
- Number of posts: 11
- Joined date: Tue May 02, 2017 3:15 pm
- Post datetime: 2017-10-07T18:39:49+00:00
- Post Title: Re: Ninja Gaiden 2 x360

I hate to dig up topics, but could anyone tell me where the texts are for a translation?

And what tools for that?
## Post #160
- Username: Qmemavos
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jan 30, 2016 9:32 pm
- Post datetime: 2018-09-04T12:00:03+00:00
- Post Title: Re: Ninja Gaiden 2 x360

Edit: Sorry, now it's working. Thanks for your hard work

Guys, sorry for digging this up. That exe " NG2 Extractor" when i'm starting it, it just crashes, the same while dragging ng2 files to it. Doesn't it work because i am using Windows 7 64 or is it a plugin need to be used with another program? Thanks in advance
## Post #161
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2018-10-03T16:22:57+00:00
- Post Title: Re: Ninja Gaiden 2 x360

are motion files stored in the gmd file or the ng2 archive ?

Cos the NG2 extrator only dumps .gmd files
## Post #162
- Username: GEO
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Sep 01, 2019 2:25 pm
- Post datetime: 2021-02-25T07:25:17+00:00
- Post Title: Re: Ninja Gaiden 2 x360

How do you fix the glitched mesh? like there seems to be multiple layers of the same mesh of some sort.

and how do I know exactly what character I'm ripping?

I'm looking for Alexei, Rasetsu and Genshin's fiend form
