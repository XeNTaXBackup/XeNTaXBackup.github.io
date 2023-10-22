## Post #1
- Username: yohanc
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jun 12, 2016 1:59 am
- Post datetime: 2017-02-27T18:03:46+00:00
- Post Title: [Help] Extracting Cars: Fast As Lighting (Gameloft)?

Hi guys,
I want to extract the lighting mcqueen model and the other, from Cars: Fast As Lighting, a Gameloft game
It's a free game, you can download the file here
[http://play.mob.org/game/cars_fast_as_lightning.html](http://play.mob.org/game/cars_fast_as_lightning.html)
or only the "Cars.bar" and "Costumes.bar" files
[http://www.mediafire.com/file/uhm5ffad3crcwjh/CARS.zip](http://www.mediafire.com/file/uhm5ffad3crcwjh/CARS.zip)

I have searched the game models, and it is located in the Cars.bar and Costumes.bar
I have used the dragon unpacker and 7zip to unpack the .bar files, but there is a problem the extracted image files (tga) cannot be open,
and the model files in .bdae files, I have tried to open it using Chipicao's GT Racing 2 BDAE Importer, but it can't open the bdae files
[viewtopic.php?f=16&t=11095&hilit=milestone](http://forum.xentax.com/viewtopic.php?f=16&t=11095&hilit=milestone)

Any idea guys with the texture (tga) error and the model bdae?
Thank You
## Post #2
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-02-28T16:54:54+00:00
- Post Title: [Help] Extracting Cars: Fast As Lighting (Gameloft)?

Some model samples from the game would help.
## Post #3
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-03-01T06:05:49+00:00
- Post Title: [Help] Extracting Cars: Fast As Lighting (Gameloft)?

gun.PNG (48.42 KiB) Viewed 246 times



I'm unable to test it with textures though.
## Post #4
- Username: yohanc
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jun 12, 2016 1:59 am
- Post datetime: 2017-03-01T08:25:26+00:00
- Post Title: [Help] Extracting Cars: Fast As Lighting (Gameloft)?

> Reply from Wobble
>
> I don't write scripts, but I wrote a plugin that can load it
Hi Wobble, thanks for your help!
Can you share the pluggin & teach me how to use it?
And what software did you use to extract the "Cars.bar" and "Costumes.bar"?
I especially need the "Lighting McQueen" and "Tow-Mater" model

> Reply from Wobble
>
> I'm unable to test it with textures though.
Yeah, I still have problem with the texture too, I still can't open the extracted tga
## Post #5
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-03-01T09:50:21+00:00
- Post Title: [Help] Extracting Cars: Fast As Lighting (Gameloft)?

Oops wrong person, wrong game.  Somebody else sent me a bdae file for a different game at the same time you posted this message.  It obviously wasn't you then.

I don't have any bdae files from this Cars game, btw.
## Post #6
- Username: yohanc
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jun 12, 2016 1:59 am
- Post datetime: 2017-03-01T12:07:46+00:00
- Post Title: [Help] Extracting Cars: Fast As Lighting (Gameloft)?

Wobble, Here is the "Cars.bar" and "Costumes.bar" files
[http://www.mediafire.com/file/uhm5ffad3crcwjh/CARS.zip](http://www.mediafire.com/file/uhm5ffad3crcwjh/CARS.zip)

You can extract the .bar files using 7zip or dragon unpacker
(But please note that most of the tga file is not working if you extract the .bar files using 7zip or dragon unpacker, probably there are another tools that can extract the .bar files better with the working texture (tga) files)

Extract the Cars.bar using the 7zip or dragon unpacker, inside it there're "MCQUEEN_high.bdae" and "MATER_high.bdae"
Can you help me, and look into those .bdae files plz
Thx
## Post #7
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-03-01T19:19:51+00:00
- Post Title: [Help] Extracting Cars: Fast As Lighting (Gameloft)?

Got it loaded:



mcqueen.JPG (29.27 KiB) Viewed 219 times



I see 3 variations of data in .TGA filenames:
- Real TGA file
- KTX file
- Pkzipped file of multiple KTX files (rename to .zip to open)

These KTX files have a header id of "KTX 11".  Never heard of them before, but you can probably find some converter tools here:
[https://www.khronos.org/opengles/sdk/tools/KTX/](https://www.khronos.org/opengles/sdk/tools/KTX/)
## Post #8
- Username: yohanc
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jun 12, 2016 1:59 am
- Post datetime: 2017-03-02T04:19:31+00:00
- Post Title: [Help] Extracting Cars: Fast As Lighting (Gameloft)?

Thanks Wobble, I have tried it and it worked
But I can't export it as .obj file because I only use the demo version
So can you plz help me convert this "MCQUEEN_high.bdae" and "MATER_high.bdae" into .obj file?

Update: Thanks Wobble for sending me the converted obj files
