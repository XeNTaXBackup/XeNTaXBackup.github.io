## Post #1
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-02-24T18:58:09+00:00
- Post Title: G3T Textures PSP Harvest Moon - Resource.bin [SOLVED]

Hello everyone, I have what may be a more unique request. I have extracted a file called "Resource.bin" from the iso of the psp game, Harvest Moon: Hero of Leaf Valley. Upon looking in a hex editor I have found several TM2 strings and this has lead me to believe that the textures inside may very well be TM2 textures.

I don't particularly care about the 3D models and reverse engineering their format, but I would love it if I could extract the the textures to use as a base for models I already have. I currently have been using screenshots to try to texture the models but this is proving to be a long and tedious process.



So if anyone could help me with extracting the textures from this I would really appreciate it, even if the extractor is just a QuickBMS script that is quite alright by me.

Thank you for any help you could provide me with.

Here's the link to the Resource.bin file: [http://ifile.it/8xc2duh/resource.bin](http://ifile.it/8xc2duh/resource.bin)
## Post #2
- Username: SkyBladeCloud
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Jun 26, 2010 5:44 am
- Post datetime: 2011-03-01T17:31:14+00:00
- Post Title: G3T Textures PSP Harvest Moon - Resource.bin [SOLVED]

hum.. Hadn´t seen this message before, but, that file uses the exact same packageing structure than the "resource.bin" file from dragoneer´s aria.

I made a decompiler+imagedecoder+text decoder+recompiler for a spanish traslation project, you may download it @ my blog along with the explanation for all.

Note that some g3t images (bitmaps) use 16 bit colors, while in dragoneer´s aria they are allways 32 bit (my tool doesn´t suppoert them...*yet*, anyway IIRC, in harvest moon textures are 32 bit)

Anyway, here is the link (spanish, use the download link for "Extractor de BIN"):

[http://skybladecloud.wordpress.com/drag ... omhakcing/](http://skybladecloud.wordpress.com/dragoneer%C2%B4s-aria-ensayo-de-romhakcing/)
## Post #3
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-03-02T16:39:56+00:00
- Post Title: G3T Textures PSP Harvest Moon - Resource.bin [SOLVED]

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: SkyBladeCloud
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Jun 26, 2010 5:44 am
- Post datetime: 2011-03-02T17:56:37+00:00
- Post Title: G3T Textures PSP Harvest Moon - Resource.bin [SOLVED]

indeed, those examples are 16-bit textures...
Ive been quite busy latelly, but im plannig to add 16 bit support (they should be RGB656 LE images, I guess), let´s see what can I do...
## Post #5
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-03-02T19:09:23+00:00
- Post Title: G3T Textures PSP Harvest Moon - Resource.bin [SOLVED]

Well I'll wait patiently and be fully understanding if you don't ever get around to it. Thanks.
## Post #6
- Username: SkyBladeCloud
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Jun 26, 2010 5:44 am
- Post datetime: 2011-03-02T19:14:17+00:00
- Post Title: G3T Textures PSP Harvest Moon - Resource.bin [SOLVED]

Easy, they are ARGB 1555 LE images, but for some reason, textures have some ugly green edgen in certain spots when i decode them... huhm....
The rest seem to be perfect...
## Post #7
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-03-02T19:19:01+00:00
- Post Title: G3T Textures PSP Harvest Moon - Resource.bin [SOLVED]

Oh hey that's great news! Glad to hear things are actually going quite well. Guess it might now be such a long wait after all.
## Post #8
- Username: SkyBladeCloud
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Jun 26, 2010 5:44 am
- Post datetime: 2011-03-02T19:35:13+00:00
- Post Title: G3T Textures PSP Harvest Moon - Resource.bin [SOLVED]

Hell yeah! I found the green spot bug!! ^_^
I´ll compile the new version and upload it in some minutes...
## Post #9
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-03-02T19:42:16+00:00
- Post Title: G3T Textures PSP Harvest Moon - Resource.bin [SOLVED]

Sir I salute you! I couldn't have even dreamed you'd figure it out so fast!
## Post #10
- Username: SkyBladeCloud
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Jun 26, 2010 5:44 am
- Post datetime: 2011-03-02T19:44:58+00:00
- Post Title: G3T Textures PSP Harvest Moon - Resource.bin [SOLVED]

Alright, I uploaded the link @ my blog, so download it again and try, I know it works with the files you posted, but there could be 24 bit textures too (IDK... maybe...), so if it trows another error, or I broke anything, let me know and I´ll fix it. Regards:

Sky
## Post #11
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-03-02T20:36:02+00:00
- Post Title: G3T Textures PSP Harvest Moon - Resource.bin [SOLVED]

Eiffel 65 anyone?



I must say it works fantastically! The textures are marked as having been swizzled which is why it's in blue tones and such I'd guess. But even so it will be much easier to recolor these textures from this than to do screenshot copy and pastes. Thanks!
## Post #12
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2011-03-02T20:46:54+00:00
- Post Title: G3T Textures PSP Harvest Moon - Resource.bin [SOLVED]

you can also use xnview to swap color rgb->bgr or else i think it is just an simple error of byte swap before exporting
## Post #13
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-03-02T23:26:36+00:00
- Post Title: G3T Textures PSP Harvest Moon - Resource.bin [SOLVED]

The contents of this post was deleted because of possible forum rules violation.
## Post #14
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-03-03T01:30:49+00:00
- Post Title: G3T Textures PSP Harvest Moon - Resource.bin [SOLVED]

wow
this is great zerox
## Post #15
- Username: SkyBladeCloud
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Jun 26, 2010 5:44 am
- Post datetime: 2011-03-03T09:44:10+00:00
- Post Title: G3T Textures PSP Harvest Moon - Resource.bin [SOLVED]

> Reply from Zerox
>
> Eiffel 65 anyone?



I must say it works fantastically! The textures are marked as having been swizzled which is why it's in blue tones and such I'd guess. But even so it will be much easier to recolor these textures from this than to do screenshot copy and pastes. Thanks!

LOOOL OKOK, i actually have a function in my code called "swpColors()" to do that, but I thought they 16 bit images were ARGB, but from what you say, they are ABGR. (no big deal, I´ll fix it later).

Anyway, Im glad it worked, and I have a question: Did you actually make a maxscript to get the 3D models? Or are them custom-made by yourself? Cos I´m trying to learn 3D mapping and it seems impossible for me... (I even tryied to map the g3d format, for my Dragoneer´s Arie project, and I was unable (-_-")) And I hope you could teach me something about it.... Indeed the model you posted is perfect, and yes, more of them would help me to learn ^_^... Thanks:

Sky

UPDATE: Updated the link in my blog with the lastest version, that shows correct colors with 16bit images too.
## Post #16
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-03-04T19:18:35+00:00
- Post Title: Re: G3T Textures PSP HarvestMoon - Resource.bin

The contents of this post was deleted because of possible forum rules violation.
## Post #17
- Username: SkyBladeCloud
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Jun 26, 2010 5:44 am
- Post datetime: 2011-03-04T19:52:43+00:00
- Post Title: Re: G3T Textures PSP HarvestMoon - Resource.bin

> Any idea what would be causing this? I included some example (already converted forgot to throw in the unconverted files) textures of what they look like before. It only happens on the eye and mouth textures nothing else. I'd be happy to upload some of the G3T textures like this that are bugging or something if you'd be willing to take a look.

Those textures have the lowest resolution of them all, the image library might be filtering them, causing that effect. Upload mote g3t, and I´ll be having a look at them.

> Perhaps I worded my posts a bit poorly, the reason I did not need anyone to reverse engineer the model format was because I already had a method of converting them.

But how can you do it? I´ve been having a look at the g3d you uploaded (i assume it´s the model), and i cant find the meaning of the data. I can decode any uncompressed image format, i even know some openGL libraries to code 3D graphic software, but i feel so dumb cos i cant reverse engineer a 3D format (-_-")(and this one seems easy). So my question is: How did you learn? Beacause I wanna learn too 

About dragoneer´s aria, the 3D file format is the same too, so I guess there is no problem there...

EDIT: YAY! ^_^ I just found the blind eyes bug, lol, it was really dumb XD (what can i say... everytime i get to code for fun like this, is after a day of hard work...). I´ll upload a perfect 16-bit decoding version in some minutes.. or one hour or so... XD...

EDIT2: here... Try this one...

[http://db.tt/M3n8Mf7](http://db.tt/M3n8Mf7)
## Post #18
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-03-04T23:33:41+00:00
- Post Title: Re: G3T Textures PSP HarvestMoon - Resource.bin

The contents of this post was deleted because of possible forum rules violation.
## Post #19
- Username: SkyBladeCloud
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Jun 26, 2010 5:44 am
- Post datetime: 2011-03-05T14:38:39+00:00
- Post Title: Re: G3T Textures PSP HarvestMoon - Resource.bin

Amazing! Didnt know about the 3D dumping trick xD. Regarding the broken textures, they are a subformat of the g3t and have nothing to do with the rest of images (only the same extensio), Im trying to figure it out as well, but as i dont know how it should be shown, IDK if ill make it xD...
## Post #20
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-03-05T20:33:00+00:00
- Post Title: Re: G3T Textures PSP HarvestMoon - Resource.bin

Well that's interesting. Well the eyes were harder to restore than the mouths and not all the mouth textures are like that so I'll just fake the ones that don't work that's quite alright thanks for your help you've given me so far.

Here's the blog you can get the 3D dumper from: [http://drakon.ixan.net/?p=315](http://drakon.ixan.net/?p=315)
Doesn't work on all games but it works just fine on Harvest Moon and Dragoneer's Aria. =D
## Post #21
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-03-06T02:46:28+00:00
- Post Title: Re: G3T Textures PSP HarvestMoon - Resource.bin

Thanks a lot for the info zerox
At last we can rip dragoneer aria model
## Post #22
- Username: syrishh
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 03, 2023 1:50 am
- Post datetime: 2023-08-02T18:37:13+00:00
- Post Title: Re: G3T Textures PSP HarvestMoon - Resource.bin

Do you guys have a link of dragoner's aria extractor cant find when i browse help me pls
