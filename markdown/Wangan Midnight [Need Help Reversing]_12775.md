## Post #1
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2015-04-16T21:59:47+00:00
- Post Title: Wangan Midnight [Need Help Reversing]

(random manga image for attention)


Hey guys I'm seeking help with 3d model reversal from Wangan Midnight PS3 game. This game like many previous Tokyo Xtreme Racer games includes full Shutoko expressway where you can freely roam the highway. I managed to write an extractor and documented everything I know here [https://github.com/fatalhalt/TXRExtractor](https://github.com/fatalhalt/TXRExtractor) (see wmn.h header). This particular game uses chunked zlib deflate files so it was only matter of time to figure out the archive, 3 weeks in hex editor paid off, along with help from alugi's offzip.exe giving clues what and where to look for. Around the same time aluigi figured out the archive and posted quickbms script here (thanks!): [http://zenhax.com/viewtopic.php?f=9&t=802](http://zenhax.com/viewtopic.php?f=9&t=802)

This is my first time messing with unpacking game archive or trying to import binary 3d model from an archive to 3d modeling program. I hope someone here has knowledge and little of spare time that could look at the models and point me in the right direction and save me some time.

Sample 3d model: (1.76MB) AREA_A_ROAD_MDL_000.GRID (link removed)

Smallest 3d model (3.35KB) COURSE/SHUTOKO/NIGHT/AREA_11GO_BUIL_CUT_11GO_WAN_013.GRID (link removed)


(9.85MB) TEST_CRS.7z (link removed) (complete)

I lurked the Tutorials section of this forum and followed tutorials such as [http://forum.xentax.com/viewtopic.php?f=29&t=3739](http://forum.xentax.com/viewtopic.php?f=29&t=3739) from (Shaiya) game and read posts by people like finale00, mariokart64n, or fatduck... and it all makes sense when you look at format/maxscript that has been already figured. In Wangan Midnight dumps, I can see bunch of float numbers in those models, can see in hex editor how data is divided, but I don't have enough experience to figure this out yet.

I know few people who are interested in this. From this particular game the highway course is most valuable, there aren't that many car models since Wangan Midnight is more of a pictorial manga/comic game. For car models we will be looking at Import Tuner Challenge 2006 for Xbox 360 but sadly its archives are using unknown compression that hasn't been cracked yet.

Thanks in advance!!!


keywords: genki, tokyo xtreme racer, wangan, c1, shutoko, japan, assetto corsa


edit: july 21 2015, download c1 rev2 here for Assetto Corsa:
mirror: (link removed)

video: [https://www.youtube.com/watch?v=J9g4TstsZAs](https://www.youtube.com/watch?v=J9g4TstsZAs)
- fixed car spawn
- added lap time on outer c1 route
- placed a pit stop at Shibaura PA (similar to what Shutoko Battle X game did) (got inspired by shiragiku)
- reduced overall brightness
- closed ramps/exits like shibuya/shinjuku by placing road barriers
- replaced broken billboards with sti/nismo logos
- fixed few unfinished pink textures
- added a mini map (thanks shiragiku)
- added initial AI line
- map has 2 pit stops and you can do a quick race involving 1 opponent (2 people total)
- *tip for me c1 map looked a lot better when I edited \Steam\steamapps\common\assettocorsa\content\weather\4_mid_clear\weather.ini and set BLEND=0.3 under [FOG] and then chose mid_clear weather in game setup/menu

edit: june 12 2016, download c1 rev6 here for Assetto Corsa:
22139f93bbbcb533a5e9d8fba43f1875 *c1_rev6.zip 150MB
[https://mega.nz/#!WlEUTJoZ!D5v3-HflS6wD ... -KLSaGYowU](https://mega.nz/#!WlEUTJoZ!D5v3-HflS6wDYGnoEX4YyEznBcEUtSo4J-KLSaGYowU)
- small update, mainly tweaked textures and adjusted UV maps

full FBX source to nfm's c1 rev6:
[https://mega.nz/file/HhFlFSaD#4CRnI_hZQ ... ZMQLkWfr9U](https://mega.nz/file/HhFlFSaD#4CRnI_hZQuq-jyNwE73hpdUhGG7nE1-64ZMQLkWfr9U)

wangan WIP .kn5 route (the one from 2016 that never got finished):
[https://mega.nz/file/X9tz3K4b#0Xcp-mUmL ... ZlA8KVi6bM](https://mega.nz/file/X9tz3K4b#0Xcp-mUmLU-KVYW9yMIdF1v887u-BZMrzZlA8KVi6bM)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-17T06:36:41+00:00
- Post Title: Wangan Midnight [Need Help Reversing]

using hex2obj (view link in my sig) for a quick format scan:



Area_A_road_mdl_000.JPG (39.94 KiB) Viewed 2334 times
## Post #3
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2015-04-17T06:54:06+00:00
- Post Title: Wangan Midnight [Need Help Reversing]

I recorded video of me going through the format and writing the maxscript, but it'll take a few hours to encode and upload to youtube
## Post #4
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-04-17T13:49:09+00:00
- Post Title: Wangan Midnight [Need Help Reversing]

> Reply from mariokart64n
>
> I recorded video of me going through the format and writing the maxscript, but it'll take a few hours to encode and upload to youtube
DUDE, real nice progress there!
How do you manage to import the map with every model in it's right position?
If your maxscript for importing tracks from this game is complete, it'll really help alot of people who dreamt of driving their favorite cars on that track in a mod-able game.

Also, it would be great if the maxscript also worked for cars.
Btw, nice work bro
## Post #5
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2015-04-17T18:09:21+00:00
- Post Title: Wangan Midnight [Need Help Reversing]

shak-otay thanks a lot for addresses and face/vert counts!!! this will now make it much easier to understand that file

> Reply from mariokart64n
>
> I recorded video of me going through the format and writing the maxscript, but it'll take a few hours to encode and upload to youtubeno way...youtube video just for this format? this is awesome, i watched most of your DOA videos and learned few things, maxscript will be perfect 

mariokart64n i think i will tip you soon
## Post #6
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2015-04-17T19:45:20+00:00
- Post Title: Wangan Midnight [Need Help Reversing]

alright, this video is NOTHING special, but it is pretty heavy its 2.5 hours long... :\

I recorded it live as I downloaded your files and looked through it. 
it was late when I recorded it, so I started to fall asleep in some spots.

however i believe it may help save time on your side if you are interested in learning macxscript

Video:
[https://youtu.be/zugkmEHrmMg](https://youtu.be/zugkmEHrmMg)

the maxscript is included in the video, but not completed. 
only tested on your two ORIGINAL samples, so probably will NOT work on the other files?



EDIT:
yeah just removed a byte check and changed a loop and it worked on the .car and .mdl files



 Wangan Midnight.zip
Maxscript, By mariokart64n (2.49 KiB) Downloaded 107 times
## Post #7
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2015-04-17T23:10:42+00:00
- Post Title: Wangan Midnight [Need Help Reversing]

Script working great here so far. I'm watching your video now. Thanks for your time. I will PM you shortly.

REDZOEU will be very happy to see C1 route  .
## Post #8
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2015-04-17T23:48:44+00:00
- Post Title: Wangan Midnight [Need Help Reversing]

I didn't script in the UV's, I'll do it up shortly for yeah


EDIT
Added handling for UVs, but the cars I tested do not have UVs on alot of its parts
probably the game has a paint shader that is used instead


 Wangan Midnight.zip
Maxscript, by mariokart64n (4.59 KiB) Downloaded 93 times
## Post #9
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-04-18T06:00:55+00:00
- Post Title: Wangan Midnight [Need Help Reversing]

Mother of progress.
You guys did awesome work there!
I haven't taken a look on the files yet, so i can't see for myself about the track and textures (also cars).
I'm happy that even cars can be extracted.
@nfm : Totally happy to see it   

So, good news is, WIP script can import map models with correct object positioning. I'm guessing there should be bad news too (knowing that shutokou expressway should use more than 100 texture for each part of map like in PSP version, named Street Supremacy)

Also, information about UVs... There is a high probability that body parts of cars didn't have UVs and uses paint shader instead, but there is also a probability that body has UVs too, since cars in game supports stickers/vinyls, right? (cmiiw)
## Post #10
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-04-18T07:43:09+00:00
- Post Title: Wangan Midnight [Need Help Reversing]

I imported the R34 to check some bugs.
Well, i found some. At first, i thought there should be a stock (not yet modified) GT-R R34, but no. The car is already pre-modified with bodykits in game. And it would seem the car is still missing textures.

[https://www.youtube.com/watch?v=oAiCdhQmV0c](https://www.youtube.com/watch?v=oAiCdhQmV0c) (The R34 is at 1:38)

[](http://imgur.com/K448xff)
A pic of the part that's missing it's textures.

There are only 5 extracted textures, which is main texture for racing, main texture for menu, headlights texture, taillights texture, and number plates texture. The remaining, such as emblem (badge) texture is missing. Same goes to windows textures and much more. I didn't research that much yet. Also, steering wheel is in x 0 y 0 z 0 position, and the car is missing brakedisc, calipers, and wheel model (tire included).

I haven't imported any tracks yet. So, i guess this bug report is exclusive for cars only. I'll take a look for tracks next. This concludes my bug report. Thanks in advance.  

EDIT: The windows in the pic is using RX3's texture. I kinda got it mixed up. LOL.
## Post #11
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-04-18T07:58:38+00:00
- Post Title: Wangan Midnight [Need Help Reversing]

Okay, so i tried importing tracks this time (AREA_9GO_BUIL_CUT_9GO_FREE_000.GRID)

[](http://imgur.com/Ozd26T7)

Apparently, the maxscript did not extract any texture for this file.
I also tried importing AREA_9GO_ROAD_MDL_000.GRID, 001, 002, and 003. Models are imported in their rightful position, but only few textures are extracted. It's missing road textures and much more.

[](http://imgur.com/w249esU)

And by seeing the previous picture of the subaru boss car, i imported the car and i don't have that same exact driver model, also the models are not pre-textured like the picture from posts before (or do you manually apply it in max?)

Let me know if this bug report is not clear. I'll try explaining it in "english".
## Post #12
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2015-04-18T08:51:41+00:00
- Post Title: Wangan Midnight [Need Help Reversing]

> Reply from REDZOEU
>
> I also tried importing AREA_9GO_ROAD_MDL_000.GRID, 001, 002, and 003. Models are imported in their rightful position, but only few textures are extracted. It's missing road textures and much more.
Have you tried importing AREA_ZZ_00.GTF.XTD, AREA_ZZ_01.GTF.XTD, and AREA_ZZ_02.GTF.XTD yet? From my understanding *.GTF.XTD contains bunch of DDS textures, I ended up with 642 from these 3 files, there's stuff like road/asphalt texture, road signs etc. These could be the textures that get reused a lot in other parts of highway, and any specific texture that's associated with 1 part of highway is stored in *.GRID file along with the model.
## Post #13
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-04-18T11:42:11+00:00
- Post Title: Wangan Midnight [Need Help Reversing]

> Reply from nfm
>
> and any specific texture that's associated with 1 part of highway is stored in *.GRID file along with the model.
So that applies the same to car models? And if that file with 642 texture is actually the textures for the whole shutokou, that'll save time to search all textures. I'll try researching again once I got home.
## Post #14
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2015-04-18T13:03:23+00:00
- Post Title: Wangan Midnight [Need Help Reversing]

Awesome progress i can't wait to convert all the cars my files are ready
## Post #15
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2015-04-18T16:06:27+00:00
- Post Title: Wangan Midnight [Need Help Reversing]

Tire/brakes/discs/rims are on other place, folders Wheel/Tire/Brake have those meshes and the script import part of the mesh but crash and you need to restart the 3DSmax, missing textures for badges and many materials called wired_xxxx but anyway i'm happy with the progress. The other thing that i like is you can import the driver model not many games can be imported like forza and are sitted  
[https://www.dropbox.com/s/f7x53ggtobnxx ... L.rar?dl=0](https://www.dropbox.com/s/f7x53ggtobnxxsp/BRAKE_TIRE_WHEEL.rar?dl=0)
## Post #16
- Username: Argonaut
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Sep 12, 2014 3:19 am
- Post datetime: 2015-04-18T17:17:29+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

All this beautiful work.. oh if you had only showed me this months ago, I'd have fainted! So happy to see this come to fruition.
## Post #17
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2015-04-18T17:22:56+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from KarinFutoGT
>
> Tire/brakes/discs/rims are on other place, folders Wheel/Tire/Brake have those meshes and the script import part of the mesh but crash and you need to restart the 3DSmax, missing textures for badges and many materials called wired_xxxx but anyway i'm happy with the progress. The other thing that i like is you can import the driver model not many games can be imported like forza and are sitted  
https://www.dropbox.com/s/f7x53ggtobnxx ... L.rar?dl=0

I'm sorry these files caused a crash?
I tested a few everything was ok, but missing some geo because they nest some model structures

Added a recurring loop to grab that geo, also added name support. please test


 Wangan Midnight.zip
Maxscript, by mariokart64n (4.6 KiB) Downloaded 63 times
## Post #18
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2015-04-18T17:39:02+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Thanks i can import the calipers/discs and tires/rims
## Post #19
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-04-18T17:41:00+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Looks like the whole GENKI CLUB have gathered   
It's currently 00:40 at my place. Just shut my pc off after playing lots of neptunia rebirth1. I'll try the script once i wake up @mariokartn64n . Also @KarinFutoGT, thanks for the bug report  . I also tried importing akio's driver model. He looks as handsome as he should be in Wangan Midnight Maximum Tune series (arcade game by Namco Bandai)

And lol @argonaut  . Me too still can't believe that this came into fruition. All thanks to nfm for learning hex and made an extractor, and mariokart64n for making the maxscript
## Post #20
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-04-19T05:59:25+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Okay, so i tried importing AREA_ZZ_00.GTF.XTD, AREA_ZZ_01.GTF.XTD, and AREA_ZZ_02.GTF.XTD .
AREA_ZZ_00.GTF.XTD contains Normal textures (or Bump Maps), while the 01 and 02 contains map related textures. 01 and 02 contains 555 textures, while 00 contains 87 bump map textures. In case someone doesn't know, bump map texture is the texture which is all purple, used for adding 3d-like details on lower polygon models (that's afaik).

I'm currently trying to experiment by importing one model of C1's road (AREA_C1_ROAD_MDL_000.GRID) which contains these textures after importing of model and dumping of textures :


And if someone is curious, i don't work on my models in max. I work on them in zmod, but i see no difference on trying to apply texture to each material in max and zmod (again, afaik). I'll try applying textures for the roads. If there are missing textures, then that means more bug report.
## Post #21
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-04-19T06:22:03+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

I've made another research, and found out a very VERY BIG problem.

Good news is : the new maxscript was able to import model with proper file name for every object.

Bad news is : dumped texture files are named like their source, instead of their REAL texture name. For example : AREA_00_XX_tex01.dds instead of ROAD.dds

Another bad news is : Material names are wire_xxxxxxxxx (9 digit numbers), instead of their real material names (e.g. "wire_006135006" instead of "wall")

With these problems, i can only think of these following solution :
1. Have the textures named as they should be (e.g. Wall.dds, C1.dds, Kandabashi.dds, hazard.dds, barrier.dds, etc)
2. Have the model materials named properly (e.g. Wall, C1, Kandabashi, hazard, barrier, etc)
3. Have the maxscript import map models with textures already applied

Another thing, i imported AREA_C1_BUIL_CUT_C1_AKA_000.GRID, which is highly possible, one of the buildings of C1, and no textures are dumped from the AREA_C1_BUIL_CUT_C1_AKA_000.GRID file. I know i said this before, but if the new maxscript can import the building models along with textures automatically applied like Chipicao's unity importer maxscript, it'll save hours, or days, or weeks, or even months of texture searching and manual apply.

That ends another bug report. Contact me if something is unclear.
## Post #22
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2015-04-19T17:55:34+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

sorry I don't know how to decode the material data, since there is alot of nesting and both internal and external texture calls.
the problem is there ARE NO TEXTURE NAMES in the texture files, everything is locally indexed within the model data.

anyway on the brighter side, I found a bug that was causing some missing textures do to the nesting.

here this script should dump more textures now
[Wangan Midnight.zip](https://xentaxbackup.github.io/file/9064_Wangan Midnight.zip)
## Post #23
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2015-04-19T19:35:47+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

ooh nice a lot better thank you   
[https://fbcdn-sphotos-f-a.akamaihd.net/ ... 0632_o.jpg](https://fbcdn-sphotos-f-a.akamaihd.net/hphotos-ak-xap1/t31.0-8/11149688_1045033782191358_1562173042404200632_o.jpg)
## Post #24
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-04-20T02:56:32+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Oookay...
That means there's extra work for applying texture for maps 
Or is the new maxscript import the model with textures already applied? I can't try it now. I'm currently on school (recess actually)
Judging from KarinFutoGT's pic, looks like the exhaust is already textured (cmiiw)
## Post #25
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-04-20T09:53:05+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Looks like more problems started to appear.
Since trying to convert shutokou models would be a pain in the a with our current status, i tried converting Yatabe Circuit (TEST_CRS) to see if all textures are extracted or not. While suddenly, i stumbled upon this texture while browsing all textures that i have extracted : 

[](http://imgur.com/8LTpmfS)

It seems that should be the missing grass texture. Here's a picture of all textures extracted from the GTF.XTD files of TEST_CRS (bump map textures not included)

[](http://imgur.com/Dm2guw0)

And this is in game picture of an RX-7 running on Yatabe Circuit :

[](http://imgur.com/htdQ6th)

From the in-game picture, you can see that the sides are green (which is using grass texture, that is not on the previous image)

While on the other haaand... Seems like part of the map uses the same materials like trees (cmiiw)
See this picture below :

[](http://imgur.com/AgOlbzF)

Guess there's still more problems to fix. Hope you don't mind it  
That ends another bug report. Converting the shutokou map to another game is still far from reach with this progress tbh
## Post #26
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-04-20T10:14:59+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Sorry to disturb once again. Even more :

[](http://imgur.com/n6eFn8M)

Using the new script, i imported the Skyline R34, and this happened. Exhaust and plate uses the same material. Just asking if there's something that can be done to fix this. Is all   
And sorry for the big pictures. I thought it's necessary for research purpose.
## Post #27
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-04-20T11:51:13+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Errr... I guess there's a high probability that textures could be extracted with proper file names and not to mention the models containing proper material names. I accidentally found this when importing few C1 files with the latest script :

[](http://imgur.com/tHieXRb)

Any thoughts? Try giving this a peek mariokart64n
## Post #28
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2015-04-20T13:14:51+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Textures aren't allready textured at least for me the pic is for the program 3Dsimed, i'm trying to open the parts one by one and changing the material name, the uv map is correct for everything except the body but maybe is for some shader at game, who knows...

[https://scontent-cdg.xx.fbcdn.net/hphot ... 6915_o.jpg](https://scontent-cdg.xx.fbcdn.net/hphotos-xpa1/t31.0-8/10856634_1045465358814867_2694376690435736915_o.jpg)
[https://fbcdn-sphotos-b-a.akamaihd.net/ ... 0688_o.jpg](https://fbcdn-sphotos-b-a.akamaihd.net/hphotos-ak-xpa1/t31.0-8/11174757_1045465375481532_7991680748613980688_o.jpg)
## Post #29
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-04-20T13:58:33+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from KarinFutoGT
>
> Textures aren't allready textured at least for me the pic is for the program 3Dsimed, i'm trying to open the parts one by one and changing the material name, the uv map is correct for everything except the body but maybe is for some shader at game, who knows...

https://scontent-cdg.xx.fbcdn.net/hphot ... 6915_o.jpg
https://fbcdn-sphotos-b-a.akamaihd.net/ ... 0688_o.jpg

You mean, even maps can be opened in 3DSimEd? If the material name and texture name matches, it'll make things easier.
I used 3DSimEd alot back then to extract NFS Shift and DIRT models, but can it really work with wangan midnight files? o_o
How did you do it?
## Post #30
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2015-04-20T17:08:03+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from REDZOEU
>
> KarinFutoGT wrote:Textures aren't allready textured at least for me the pic is for the program 3Dsimed, i'm trying to open the parts one by one and changing the material name, the uv map is correct for everything except the body but maybe is for some shader at game, who knows...

https://scontent-cdg.xx.fbcdn.net/hphot ... 6915_o.jpg
https://fbcdn-sphotos-b-a.akamaihd.net/ ... 0688_o.jpg

You mean, even maps can be opened in 3DSimEd? If the material name and texture name matches, it'll make things easier.
I used 3DSimEd alot back then to extract NFS Shift and DIRT models, but can it really work with wangan midnight files? o_o
How did you do it?

3Dsmax to .obj with groups, import the .obj with zmodeler 2.2.6 996 build as groups, export multiple .gmt "rFactor1" format and then edit the materials.
## Post #31
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2015-04-20T17:53:15+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

I think mariokart64n gave us all that we need to keep going and I'm sure he has his own projects.

Like he said the blocks/sub-blocks are nested and encapsulated in the model format making things harder to work on. If you read into the maxscript it is clear that the code is still work in progress so I wouldn't necessarily call most of these mishaps bugs but unimplemented features.

I will look at the garbled AREA_ZZ_02.GTF_tex_240.dds and try to debug what went wrong there during DDS texture dump. At the moment I'm learning Maxscript and looking into 3ds docs and what it takes to create/import full complete mesh.

@REDZOEU, yes, for files like AREA_C1_ROAD_MDL_000.GRID the object names match the name of dumped textures which is pretty nice.
## Post #32
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2015-04-20T21:29:27+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Those textures are raw, 8888:32bit BUT they are swizzled :\

I don't know much about it, but luckily someone else here had already programmed a GFT tool 

[viewtopic.php?f=18&t=5164](http://forum.xentax.com/viewtopic.php?f=18&t=5164)

new script includes another toggle "Convert to DDS", leave this off. then you will get GFT files
you can use the tool in that link to convert GFT to DDS properly


 Wangan Midnight.zip
(150.76 KiB) Downloaded 62 times
## Post #33
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-04-20T23:47:43+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Oh...
Sorry, the excitement got into me :\

If he's busy with his own projects, i guess i can't bother him too much. But mariokart64n's help so far has gotten us this far into importing maps and models with proper names. ALl that's left is material name and texture name.

Thanks for the help on exporting raw texture files via your newly updated maxscript though 
I might ask chipicao to help about texture names and material names. If it can't be gelped, that means more hours will be necessary to do the conversion 

@KarinFutoGT : oh, i thought 3DSimEd works with .GRID or .CAR models 
@nfm : Sorry about that. And it's good that you're learning more
## Post #34
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2015-04-21T10:09:23+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

@REDZOEU, no problem   
@mariokart64n, thanks

I modified the latest script a bit, added comments where applicable, formatted syntax, and simplified some code, functionality remains same and feature wise nothing changed. I guess it would be nice to base future changes off of this, thanks.

[https://github.com/fatalhalt/TXRExtract ... wmn/wmn.ms](https://github.com/fatalhalt/TXRExtractor/blob/master/maxscript/wmn/wmn.ms)

I'm spending some time in hex editor and maxscript, just throwing this out, file like AREA_C1_ROAD_MDL_000.GRID seems to have rougly 31 materials and 55 textures, where 4 textures are headerless DSS aka GTF that get extracted. This probably means that other 51 textures are referenced from AREA_ZZ_*.GTF.XTD files? I can see what mariokart64n mentioned that textures don't have names but are locally indexed, the relationship between materials and textures seem to be indices. That concludes about 20 hours of time :/

I also don't quite understand what should be going on in getType07() function at this moment.
[wmn.zip](https://xentaxbackup.github.io/file/9076_wmn.zip)
## Post #35
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2015-04-21T20:47:48+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

thanks for cleaning and adding comments. 

as for the type7 i assumed it was material data, I'm not sure how it works though. it looks like it works like the main file, in that it gives a type then you get different data based on what the type is. which makes sense if some materials are textured, and some are shaded.
## Post #36
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2015-04-22T20:52:15+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from mariokart64n
>
> thanks for cleaning and adding comments. 

as for the type7 i assumed it was material data, I'm not sure how it works though. it looks like it works like the main file, in that it gives a type then you get different data based on what the type is. which makes sense if some materials are textured, and some are shaded.I found out how geometry is linked to a material, and material to texture. I added handling of materials to the script. Still needs more work:
## Post #37
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-04-23T08:59:10+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Heeeeeeeell! What a progress!
With that, map conversion will be easier than ever 
Keep up the good work guys 

That tollbooth is lookin' good already.
## Post #38
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2015-04-23T16:07:33+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Soo good
## Post #39
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2015-04-25T09:37:44+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

I attached updated script. It handles good majority of maps (diffuse, specular, reflection, and opacity) and hooks them up into a 3ds Max material. I learned many things along the way.
[wmn.zip](https://xentaxbackup.github.io/file/9103_wmn.zip)
## Post #40
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2015-04-25T10:09:17+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

@mariokart64n,

Off the top of my head, the things that I found out in case you were wondering, sorry it's very late here... For each geometry there seem to be a material, so in geometry sub block unk3 would denote index to material array (mat arr being the 0x07 type we hit in getStuff() during parsing) , then in material sub block -> sub material 0x08, there would be an index to texture array, the texture sub block would then have number corresponding to nth offset in TXD section telling where to find a texture, and there in turn if you got lucky there would be a GTF texture, or just 0x10 byte entry, but looking closer at those entries there are 2 shorts where first one goes from 0~2 denoting which AREA_ZZ_*.GTF would contain the texture and next short would tell you which e.g. 157.
## Post #41
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-04-25T15:34:31+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Mother of god!
Nice work nfm!
Hard work's finally paid off 
Now i'm gonna test the newly made script on both cars and tracks. Let's hope there ain't no more problems with this newly made script, so everyone can rest easy 

Oh btw, i started playing Import Tuner Challenge again. I have re-discovered the other parts of highway that are missing from Wangan Midnight. First, it's Shibuya (sharp turn at the end of the track which is on the city, not on the highway), and second, it's Shinjuku (with Train Station's U turn that connects with the city road and the highway). I haven't discovered other parts yet since i don't remember much and i'm still struggling to beat every single opponent there is (also Wanderers).
## Post #42
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2015-04-26T07:46:56+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

wow good work finding the material information, I found it hard to interpret the material / texture indices when I found out about the external files.
your hard work really paid off i'm glad you were able to solve the missing data

> Reply from nfm
>
> @mariokart64n,

Off the top of my head, the things that I found out in case you were wondering, sorry it's very late here... For each geometry there seem to be a material, so in geometry sub block unk3 would denote index to material array (mat arr being the 0x07 type we hit in getStuff() during parsing) , then in material sub block -> sub material 0x08, there would be an index to texture array, the texture sub block would then have number corresponding to nth offset in TXD section telling where to find a texture, and there in turn if you got lucky there would be a GTF texture, or just 0x10 byte entry, but looking closer at those entries there are 2 shorts where first one goes from 0~2 denoting which AREA_ZZ_*.GTF would contain the texture and next short would tell you which e.g. 157.
## Post #43
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-04-26T10:25:09+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Track Conversion is an O-Kay 

[](http://imgur.com/WWCvVsu)

I had to scale the track model down with ZModeler's Exact Transformation tool from 1.000 to 0.030 to make the track's size equal to an example car from GTA SA (which is the ZR-350)

[](http://imgur.com/myapxWh)

Also, sorry for disturbing again. There's another problem for vehicles. I'm trying to convert the large truck (QUON.CAR is the name of the file), but material names are half named (first few had their original name, the rest are wire_xxxxxxxxx. Also, the same old problem, only 3 textures are extracted (license plate, main_day, main_night).

[](http://imgur.com/ycio1Kg)

Looks like even the body part of the truck's head uses texture, since the wire doesn't look like it has the doorlines of the front door (see [https://www.youtube.com/watch?v=zaW7i7k7Dvo](https://www.youtube.com/watch?v=zaW7i7k7Dvo) and look closely on the door while comparing it to the wires of the truck model)

Sorry for the large images. Had to.
## Post #44
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2015-04-26T13:06:57+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

I confirm what REDZOEU wrote. Some materials have no name, and are also mixed up
Spotted also some broken (unwelded) parts on the meshes. The Subaru Legacy Wagon for example has broken edges on the bumpers.
## Post #45
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2015-04-26T17:25:21+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

I only try the S30 Akio and i can say that car is correct in everything, here a screenshot for my conversion to rFactor sim.
## Post #46
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-04-27T06:43:53+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

So, we can confirm that some cars still have texture and material problem (Ahem, vehicles. Since there are trucks/lorry)
And also AREA_ZZ_00.GFT.XTD file (cmiiw about the file name) until 02 still don't have their proper file name.
Until all of this gets fixed, we can't say that the maxscript is out of it's beta phase (or W.I.P)

For now, track conversion seems to go okay, but minus for some vehicles. I haven't imported all tracks too. On nfm's screenshot, he imported the skybox along with the stars texture. I'm guessing the skybox is from the .CORE file, but when i imported that file, the skybox has mo texture (even after extracting textures from 00-02)
## Post #47
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2015-04-27T09:05:53+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Yes the last script hasn't fixed any issues with the car models, I focused more on the .GRID files. I don't think we can get named textures out of AREA_ZZ_*.GFT.XTD easily yet, to do that we would need separate script that would go through all .GRID files and build a list of names for the textures. The .GRID or .CAR models themselves use indices such as 44th or 157th file instead of names, and .GFT.XTD have no metadata what so ever.

@KarinFutoGT, that devil Z looks very nice. I looked on your facebook page but saw no download link.

I tried to make a simple track for rFactor but I keep getting plugin error and 3ds 2012 32-bit crashes (had to downgrades from 2014 x64 since there's no support) when generating .gmt file. Their SDK seems friendly at first but I found no documentation on how to make a track, there's some official pdf info on texturing/skinning a car but nothing on tracks. Then I tried simplest track in Assetto Corsa, they have a SDK on Steam that includes their own modeler than can import .FBX format from 3ds and save as .kn5 to drop it in to Assetto's track folder. Track creation is rather weird for this game, besides your track, you have to create 4 cubes 1 meter above ground and name them AC_PIT_0, AC_START_0, AC_TIME_0_L/R so car knows where to spawn and where pit stop and finish line is. I did all of that and couldn't get to that to work either, when my track loads it stops and Assetto goes to main screen. Also there's no documentation what so ever besides 1 sticky forum post. Also meshes have to be named with names like 1ROAD for track, 1GRASS if you have grass, etc, I don't think this game is suited for open world track, but I think I saw whole downtown of Paris mod for it. Either way it was very frustrating with these 2 games and I wasted tons of time troubleshooting.

I might try making simple track for GTA IV if I get motivation maybe I'll have more luck there.
## Post #48
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-04-27T14:53:13+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Well... C1_ROAD_001 (cmiiw for the name) in GTA SA
[](http://imgur.com/N5bv2jL)
[](http://imgur.com/Hr3MRTh)
[](http://imgur.com/7jCcajX)

The skyline was made by me (not released yet, but will release it along with C1 maybe). I made it to add the Tokyo Xtreme Racer atmosphere to the game
## Post #49
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2015-04-29T02:34:31+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

@REDZOEU, nice, are you using 3ds GIMS plugin to work on GTA SA map?

I can't get past this error in GIMS when doing GTA IV addon map (WPL export error:-- Type error: Call needs function or class, got: 28738):


i tried many things, simplest single meshes, 2012 32-bit 3ds, nothing...
## Post #50
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-04-29T11:28:10+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from nfm
>
> @REDZOEU, nice, are you using 3ds GIMS plugin to work on GTA SA map?

I can't get past this error in GIMS when doing GTA IV addon map (WPL export error:-- Type error: Call needs function or class, got: 28738):

i tried many things, simplest single meshes, 2012 32-bit 3ds, nothing...

Welcome to the modding scene of GTA 4 
I don't know modding for GTA 4, but i know how for SA. Are you using the Design Version of the max btw?
Also, try making the map by imitating maps in GTA 4. What i mean is, import a map model from GTA 4 that acts as an example model, and do the same thing to the c1 model (like same material settings, same parameters, etc)

And... IMO, it's easier to mod GTA by using ZModeler instead of max, but that depends on your experience on which software you're used to.
## Post #51
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2015-05-01T09:24:17+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from REDZOEU
>
> nfm wrote:@REDZOEU, nice, are you using 3ds GIMS plugin to work on GTA SA map?

I can't get past this error in GIMS when doing GTA IV addon map (WPL export error:-- Type error: Call needs function or class, got: 28738):

i tried many things, simplest single meshes, 2012 32-bit 3ds, nothing...

Welcome to the modding scene of GTA 4 
I don't know modding for GTA 4, but i know how for SA. Are you using the Design Version of the max btw?
Also, try making the map by imitating maps in GTA 4. What i mean is, import a map model from GTA 4 that acts as an example model, and do the same thing to the c1 model (like same material settings, same parameters, etc)

And... IMO, it's easier to mod GTA by using ZModeler instead of max, but that depends on your experience on which software you're used to.
@REDZOEU, thanks for the reply   ,
I was using Max Design version of 3ds, i just switched to 2016 regular 3ds trial version. I was able to create simple polygons and place them into the game with GIMS IV. But for shuto parts I'm still getting same error, but I can get around it by saving project into .3ds and restarting 3ds and continuing on. My shuto map didn't quite work and was not visible in game, and with OpenIV when previewing .wdr I wasn't able to see it there, maybe my positions is off the grid but I checked it and everything seemed fine.

Hey I was wondering how you deal with opacity map e.g. the route directions in japanese that are overlaid on top of the road? It looks like GTA IV or Assetto Corsa don't handle opacity maps. I wasn't quite sure how to handle these type of textures in the script, so i just hooked them up as opacity maps. 1 other texture that I wasn't sure how to handle was the tiremarks/burnout marks, it looks like it can be a diffuse map but it needs lower strength like 33% or something (If am making sense   ). If you know how to tweak them in 3ds material window to make them look right please share, then I could shoot for same in maxscript. I'm getting more luck with Assetto Corsa now so I'm working with that.
## Post #52
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-05-01T11:04:15+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from nfm
>
> I wasn't able to see it there, maybe my positions is off the grid but I checked it and everything seemed fine.
About that, i experienced the same problem in gta sa, but i used zmodeler, so the solution is different. I rescaled the map (since the size is humongous) and centered the pivot to the object. By centering the pivot to the object, it'll make placement easier.

I'll try explaining this the easy way then. The map model imported is already placed in the right position like in-game, but the pivot remains at x 0 y 0 z 0 after i export the map model to .obj (just so that i can import it in zmod). After i setup the map for conversion to gta sa, i didn't reset the object's pivot to the map's model position. I placed the map in x 0 y 0 z 0 in GTA SA. When i go in game, i go to x 0 y 0 z 0 coordinates, and can't find the map. Why? Because the map is further away from the pivot. The pivot is like the x y z of the map. But since the pivot is at 0 value, while the map is in (for example) x 10000 y 13862 z 100, that means the map is FAR OFF from the pivot.

> Reply from nfm
>
> Hey I was wondering how you deal with opacity map e.g. the route directions in japanese that are overlaid on top of the road?
I don't really know for games outside of GTA SA, but those texture uses alpha (or mask). For gta sa, i imported the .png (i converted .dds to .png) into TXDWorkshop, ticked "Alpha is used", and then compress the texture. In game, the model doesn't appear like a box surface, but has the shape of the alpha texture itself. I learned abit, but i guess opacity doesn't have anything to do with alpha textures (cmiiw).

> Reply from nfm
>
> 1 other texture that I wasn't sure how to handle was the tiremarks/burnout marks, it looks like it can be a diffuse map but it needs lower strength like 33% or something
If you decrease opacity down to 33%, that'll make the texture a little transparent, not making the texture use alpha texture. Here's a picture to describe what i'm saying :
[](http://imgur.com/VS9hejc)

Also, good to know that your map conversion to Asseto Corsa is going well 
And tbh, i don't know how max material works, so i can't help you when it comes to materials in max.
Correct me if i'm wrong at some part, since i'm not so knowledged in textures and materials :\
## Post #53
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2015-05-01T22:32:42+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

@REDZOEU, thanks for explanation

I learned how to adjust pivots recently and I do exactly what you said to get the positioning right. I'm in a hurry here but I will at least show you how Ginza part of shuto looks in assetto corsa:



 

Unfortunately what you see is just diffuse bitmaps, to get normal maps and opacity maps into a map would take hours to adjust each material in assetto sdk material/shader editor by hand. After figuring out how to position, adjusts units, scale, and meet other assetto map requirements, I can already drive around and it is pretty fun. Here's one more (scale is wrong here, map is too small):



Lol at the guy with flag. I will try to see if I can make a whole C1 route and see if anything bombs out. 3ds Max is crawling for me too. And it looks like assetto does alpha blending instead of opacity maps.
## Post #54
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-05-02T05:08:54+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

WHOA, DUDE!
I was shocked seeing the first picture. It's like seeing shutoko in a whole new engine. A new shutoko game incoming xD
Btw, how do you import the maps all at once? You converted the map along with buildings with ease to asseto corsa, while i have to import one part and set it up in zmod so i can convert it to gta sa.
It's a hard process, but it's the only way to convert the maps to gta sa :\

So far, i've fixed collision of map, and now map works flawlessly. Problem is, connecting parts of the map in map editor, and also CJ (player) gets darker (almost black) when he landed on the map. Before he landed on the map, he's bright.

EDIT : Tried Asseto Corsa back then with LOWEST settings. Still lagged in game. Showroom of one car where we can go in interior and open doors, i get 10-15 FPS. Asseto Corsa is out of my league
## Post #55
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2015-05-06T21:44:21+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

@REDZOEU

There's a basic guide on track creation on the assettocorsa.net forum, however to be able to view you have to register and have associate your account with Steam that has assetto license/key, but still if you want to find more details you have to spend hours reading other people' comments since there's still no official documentation. There are some impressive tracks and some are even 20kms. There exist assetto sdk which is a texture/shader GUI viewer editor for Windows that imports .fbx files and saves them as .kn5 which is a file format for assetto's tracks. I think in contrast to GTA with assetto it is much easier to specify things like collisions, you just have to name objects/meshes in 3ds like 1WALL 2WALL...and assetto physics engine does the rest.
## Post #56
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-05-09T17:41:11+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Sorry for the late reply. My conversion of shutokou to GTA SA will (probably) take a year, since the total of map object files are around 700 (road and buildings), and i have converted 3 out of them which are roads.

Also, since for a full one week until 15 or 16 may i'm out of home for school trip, the conversion will be postponed.
And about assetto corsa... I'll try to download the game again and see if i can get decent fps on map mods instead of pre-made maps. All settings on low enough is quite frustrating already.

I know assetto corsa should be modder-friendly, even for maps. I'll see what i can do with it until then 
And boy... This thread sure is quiet lately...
## Post #57
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2015-05-10T05:49:13+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from REDZOEU
>
> Sorry for the late reply. My conversion of shutokou to GTA SA will (probably) take a year, since the total of map object files are around 700 (road and buildings), and i have converted 3 out of them which are roads.

Also, since for a full one week until 15 or 16 may i'm out of home for school trip, the conversion will be postponed.
And about assetto corsa... I'll try to download the game again and see if i can get decent fps on map mods instead of pre-made maps. All settings on low enough is quite frustrating already.

I know assetto corsa should be modder-friendly, even for maps. I'll see what i can do with it until then 
And boy... This thread sure is quiet lately...Give Assetto second chance, tweak it and see if you can pull at least 30fps in game, it's a very good simulator and I bet when we get the highways done it would be blast and tons of fun to drive. Let's team up on this bro.
## Post #58
- Username: illking
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 15, 2015 8:29 am
- Post datetime: 2015-06-20T13:33:58+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Im having quite a hard time extracting WMN.DAT archive with the extractor. Could anyone give me hand? Would be much appreciated!   I have been looking to get these models for ages!
## Post #59
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2015-06-24T22:34:35+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Hello everyone, I'm attaching an updated script made by "BiggBoss93".
He told me that he didn't do anything but automatize map's import process.
He hopes that someone else will work on automatic diffuse texture application since at the moment it only sets bumpmap ones.
With this, I wish you'll find this script more helpful than the previous ones.

Cheers!
[wmn.7z](https://xentaxbackup.github.io/file/9337_wmn.7z)
## Post #60
- Username: mlfr
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 26, 2015 7:05 pm
- Post datetime: 2015-06-26T11:54:06+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

can anybody teach me how to use TXRExtractor.exe please?
## Post #61
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-06-26T16:54:42+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

To extract the .dat, you need to put the .dat in the same folder as the extractor, and also make a folder named "out" . That's all i can remember. Also Automotive Gaming, thanks for the updated script. I'll test it out the next time i use my computer.
## Post #62
- Username: mlfr
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 26, 2015 7:05 pm
- Post datetime: 2015-06-28T03:20:49+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from REDZOEU
>
> To extract the .dat, you need to put the .dat in the same folder as the extractor, and also make a folder named "out" . That's all i can remember. Also Automotive Gaming, thanks for the updated script. I'll test it out the next time i use my computer.

> i tried that and it still did not work
Dont worry i figured it out
## Post #63
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2015-06-28T08:29:55+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Here's a complete C1 track for Assetto Corsa: [https://www.dropbox.com/s/lklgxyzm64cxpwi/c1.zip?dl=0](https://www.dropbox.com/s/lklgxyzm64cxpwi/c1.zip?dl=0), place the extracted "c1" folder into \assettocorsa\content\tracks and play in practice mode. The things that I have done to it from last version from top of my head (I haven't worked on it lately)
- added fake tunnel lights and fixed missing textures
- added tokyo skytower landmark
- retextured buildings and tokyo tower
- added water
## Post #64
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2015-06-29T08:12:13+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

I noticed that the script did not unpack all the textures of cars...
i don`t have main paint texture rolling guy car, how to find this?



How to unpacked the file Import Tuner Chalenge / Shutokou Battle X, a compressed archive method?
## Post #65
- Username: AOITORI
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 30, 2015 1:34 am
- Post datetime: 2015-06-29T17:39:19+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

hello! GJ mod!  

Create a map image and configuration files It 's simplified

C1 Track MAP image  file  [https://drive.google.com/file/d/0B7VyGX ... sp=sharing](https://drive.google.com/file/d/0B7VyGXxoaVDQSDItaE52LWZjYzg/view?usp=sharing)
## Post #66
- Username: Stanced Kz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jul 01, 2015 8:26 pm
- Post datetime: 2015-07-01T12:34:10+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

I converted to GTA4  

[http://i.gyazo.com/af2c929933f8b72147b3b0b7d5c3b8ce.jpg](http://i.gyazo.com/af2c929933f8b72147b3b0b7d5c3b8ce.jpg)
[http://i.gyazo.com/b018bb68a1986b331afa0164bd169133.jpg](http://i.gyazo.com/b018bb68a1986b331afa0164bd169133.jpg)
[http://i.gyazo.com/d6a466d48f0c4faa8dcde504ea143c3e.jpg](http://i.gyazo.com/d6a466d48f0c4faa8dcde504ea143c3e.jpg)
[http://i.gyazo.com/805fa2f86d413bdb0940bd352f4d2e56.jpg](http://i.gyazo.com/805fa2f86d413bdb0940bd352f4d2e56.jpg)
## Post #67
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-07-01T13:46:09+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Nice work everyone.
Also, good job @Stanced Kz . I do own GTA 4, but i dont play it anymore. My PC can barely handle the game. I was wondering if someone could convert it to GTA SA :\
Well, i might try it on GTA 4, but lags are a problem.

Another thing, nfm, seems like the map crashed on my end. Copied the c1 folder onto my tracks folder, the game loads it. But when i enter the track using Pagani Zonda R, things went down. On loading, it says that both car and track is loaded, but when the track is about to be shown, it throws me back to AC's launcher. I saw a vid on YouTube about someone using the map, and it worked. What's wrong with my game?
## Post #68
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2015-07-01T15:36:22+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

@nfm, @Stanced Kz: great work guys
Just wondering, how many materials does the converted map have?
## Post #69
- Username: Stanced Kz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jul 01, 2015 8:26 pm
- Post datetime: 2015-07-01T17:22:06+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

@REDZOEU
Thanks!
There is no load of delay.
This is test version video
[https://youtu.be/Q9QTzi6o1tc](https://youtu.be/Q9QTzi6o1tc)

@Automotive Gaming
about 700...
## Post #70
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-07-03T07:02:38+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

@Stanced kz
Ho ho... So that's how the map looks like without material in-game...
Can't wait for it to be finished! If it's finished, i might consider getting my IV back and do whatever it takes to mod the game with my favorite cars 
And i cee you're japanese... Konnichiwa 
I also subbed your channel on YouTube. Cheers!
## Post #71
- Username: Berlik
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jul 04, 2015 8:28 am
- Post datetime: 2015-07-04T00:33:15+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Wow been wanting to do this for a long time, Good job and thank you for doing this!

If it's not a problem, can you send me the 3ds max file of this map? I'd like to make changes for Assetto Corsa map. I have worked on ac tracks and cars before they even released any tools.

Thanks!
## Post #72
- Username: bakerina
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 19, 2015 1:46 pm
- Post datetime: 2015-07-05T12:28:06+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

@nfm
Production is cheers for good work.
It is a great course.

I want to add a grid to this course.
Please permission.
## Post #73
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2015-07-06T07:59:38+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

@bakerina

sure, no problem, do what you want with the files
## Post #74
- Username: bakerina
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 19, 2015 1:46 pm
- Post datetime: 2015-07-06T11:01:52+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

@nfm
thanks!
Is I may reveal the completed file?
## Post #75
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2015-07-10T06:26:26+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from bakerina
>
> @nfm
thanks!
Is I may reveal the completed file?Yeah sure man. Please share any improvements that you made.
I did a google search for "assetto corsa c1" and saw lots of videos, people adding mini maps or tweaking lighting, it would be nice if we could all come together to 1 place and work together on this  .
## Post #76
- Username: nosfornos
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Dec 21, 2011 4:16 pm
- Post datetime: 2015-07-11T01:55:48+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

How about Tokyo Xtreme Racer : Drift 2?
## Post #77
- Username: bakerina
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 19, 2015 1:46 pm
- Post datetime: 2015-07-11T02:46:05+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

@nfm
Thank you!!

[https://mega.nz/#!r8MDmDbQ!xS685jrcOhVI ... oqUo8VI0WU](https://mega.nz/#!r8MDmDbQ!xS685jrcOhVIrGeKLaq9y7pykjns21bl_oqUo8VI0WU)

This file can be raced in 12 cars.
There is a plan to current inner loop also allows traveling.
## Post #78
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2015-07-11T03:46:33+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from bakerina
>
> @nfm
Thank you!!

https://mega.nz/#!r8MDmDbQ!xS685jrcOhVI ... oqUo8VI0WU

This file can be raced in 12 cars.
There is a plan to current inner loop also allows traveling.pretty cool, i played it  . This might help you with the modifications and make things easier:

download full c1 resources files (c1.fbx, c1.fbx.ini, c1.max, textures):
(link removed)
use this with 3ds max or ksEditor.exe, see included README.txt

With this you can change textures, change color of the water, add new buildings/geometry, delete/rename geometry and so on...
## Post #79
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2015-07-12T23:31:50+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from Berlik
>
> Wow been wanting to do this for a long time, Good job and thank you for doing this!

If it's not a problem, can you send me the 3ds max file of this map? I'd like to make changes for Assetto Corsa map. I have worked on ac tracks and cars before they even released any tools.

Thanks!Berlik I PMed you, sorry I missed your post. Get back to me if you see this, I'm interested in working with you.


@nosfornos, I did not figure out how to extract Drift 2 or Import Tuner Challenge yet and not working on them anymore, maybe someone else who is interested can crack this, I wasn't able. It would be awesome to have shinjuku and shibuya roads from Import Tuner Challenge.
## Post #80
- Username: shiragiku
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jul 19, 2015 7:18 am
- Post datetime: 2015-07-18T23:35:28+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from nfm
>
> Berlik wrote:Wow been wanting to do this for a long time, Good job and thank you for doing this!

If it's not a problem, can you send me the 3ds max file of this map? I'd like to make changes for Assetto Corsa map. I have worked on ac tracks and cars before they even released any tools.

Thanks!Berlik I PMed you, sorry I missed your post. Get back to me if you see this, I'm interested in working with you.


@nosfornos, I did not figure out how to extract Drift 2 or Import Tuner Challenge yet and not working on them anymore, maybe someone else who is interested can crack this, I wasn't able. It would be awesome to have shinjuku and shibuya roads from Import Tuner Challenge.

hi nfm. my name is Shiragiku. you can call me Shira/Shun

i already make the C1 online able up to 12 players (12pitbox)
moved the pitbox to Shibaura PA. so we can go to Inward/outward easily
[https://www.youtube.com/watch?v=0CG1zJ8ceUE](https://www.youtube.com/watch?v=0CG1zJ8ceUE)
online test
[https://www.youtube.com/watch?v=tDdaL6pV7M8](https://www.youtube.com/watch?v=tDdaL6pV7M8)

but i still have a some bug with pitbox spawn going to fix it or maybe re arrange it for better spawn.





btw.
i hope you can make NBL, Yokohane, and Wangan area too
## Post #81
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-07-19T03:45:35+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Great work, Shun!
Btw, i see you and your friend speaking Indonesian in the in-game chat, so...
Kerja yang bagus gan 
Klo agan upload map yg versi online, mungkin ane bakal beli ac versi non-bajakan deh. Hehehe
## Post #82
- Username: shiragiku
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jul 19, 2015 7:18 am
- Post datetime: 2015-07-19T04:48:12+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from REDZOEU
>
> Great work, Shun!
Btw, i see you and your friend speaking Indonesian in the in-game chat, so...
Kerja yang bagus gan 
Klo agan upload map yg versi online, mungkin ane bakal beli ac versi non-bajakan deh. Hehehe

thanks~ 
and yeah we're indonesians xD

btw. i already upload it. 
remember this only patch. you need to download the original NFM C1 folder
[https://app.box.com/files/0/f/0/1/f_33525237309](https://app.box.com/files/0/f/0/1/f_33525237309)


ditunggu main bareng nya gan  
steam ID : Shiragiku28
## Post #83
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2015-07-20T03:15:00+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from shiragiku
>
> 
btw.
i hope you can make NBL, Yokohane, and Wangan area tooSomeone get us dump of WMMT5 arcade hdd?! WMMT5 is not available here in US.
## Post #84
- Username: shiragiku
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jul 19, 2015 7:18 am
- Post datetime: 2015-07-20T11:43:46+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from nfm
>
> shiragiku wrote:
btw.
i hope you can make NBL, Yokohane, and Wangan area too Someone get us dump of WMMT5 arcade hdd?! WMMT5 is not available here in US.

we have WMMT 5 here. but i dont think any arcade centre would give me WMMT5 data.

well. i think you can make it from WM PS3.

patch for map data is out [https://app.box.com/s/fbi7j0u2s8lf0jpvckaro4h0raeyqfuu](https://app.box.com/s/fbi7j0u2s8lf0jpvckaro4h0raeyqfuu) only 318kb. lol.
## Post #85
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-07-20T12:26:11+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Still gonna wait to get more steamwallet or Assetto Corsa... 

And yeah, they won't let us do something to the machine, like plugging a recorder to record the game directly instead of off-screen recording with a camera (like how SOARS team from Korea uploaded WMMT5 videos), let alone getting datas from the game itself...

WMMT2's arcade data, however, is available for download, but MAME Emulator does not support it. Some guy in YouTube made his own personal build for arcade machine, and he ran WMMT2 in his home-made arcade machine with fully working steering and pedals (minus card readers and shifting knob).
## Post #86
- Username: shiragiku
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jul 19, 2015 7:18 am
- Post datetime: 2015-07-20T12:32:50+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from REDZOEU
>
> Still gonna wait to get more steamwallet or Assetto Corsa... 

And yeah, they won't let us do something to the machine, like plugging a recorder to record the game directly instead of off-screen recording with a camera (like how SOARS team from Korea uploaded WMMT5 videos), let alone getting datas from the game itself...

WMMT2's arcade data, however, is available for download, but MAME Emulator does not support it. Some guy in YouTube made his own personal build for arcade machine, and he ran WMMT2 in his home-made arcade machine with fully working steering and pedals (minus card readers and shifting knob).

we waiting for you bro. xD
## Post #87
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2015-07-21T07:54:33+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

edit: july 21 2015, download c1 rev2 here for Assetto Corsa:
(link removed) (NEW revision 2, 07/21/2015)
- fixed car spawn
- added lap time on outer c1 route
- placed a pit stop at Shibaura PA (similar to what Shutoko Battle X game did) (got inspired by shiragiku)
- reduced overall brightness
- closed ramps/exits like shibuya/shinjuku by placing road barriers
- replaced broken billboards with sti/nismo logos
- fixed few unfinished pink textures
- added a mini map (thanks shiragiku)
- added initial AI line
- map has 2 pit stops and you can do a quick race involving 1 opponent (2 people total)
- *tip for me c1 map looked a lot better when I edited \Steam\steamapps\common\assettocorsa\content\weather\4_mid_clear\weather.ini and set BLEND=0.3 under [FOG] and then chose mid_clear weather in game setup/menu
## Post #88
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-07-21T18:15:20+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Gonna test it out tomorrow >:) (well, actually today)
Was about to sleep when a new e-mail came in about new posts here. Hell, i should really buy Assetto Corsa so we can get this show on the road, online
## Post #89
- Username: shiragiku
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jul 19, 2015 7:18 am
- Post datetime: 2015-07-22T00:23:29+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from nfm
>
> 


edit: july 21 2015, download c1 rev2 here for Assetto Corsa:
https://www.dropbox.com/s/z4mcg2t64mqo4 ... 2.zip?dl=0 (NEW revision 2, 07/21/2015)
- fixed car spawn
- added lap time on outer c1 route
- placed a pit stop at Shibaura PA (similar to what Shutoko Battle X game did) (got inspired by shiragiku)
- reduced overall brightness
- closed ramps/exits like shibuya/shinjuku by placing road barriers
- replaced broken billboards with sti/nismo logos
- fixed few unfinished pink textures
- added a mini map (thanks shiragiku)
- added initial AI line
- map has 2 pit stops and you can do a quick race involving 1 opponent (2 people total)
- *tip for me c1 map looked a lot better when I edited \Steam\steamapps\common\assettocorsa\content\weather\4_mid_clear\weather.ini and set BLEND=0.3 under [FOG] and then chose mid_clear weather in game setup/menu

wow nice job NFM! btw. can i make this to 12 pitbox or more for Online Session?

after test:

+ more grip on the track. idk you change the physic,Elevation the road or something 
+ finally we have lap timer and racing line
+ finally we can park our car on parking slot.
+ more stable FPS because you change the overall Brightness

- we cant coming back to Pit from Rainbow Bridge. (RB Blocked)
- we cant go to Inward Route. 

maybe im going to edit this for cruising only with different name folder. so anyone can play on my C1 and your C1. 

because some player wants to play on C1 for Cruising with the other players.

btw i have a question. can i make more lap timer for inward? ( make L & R cube with name AC_TIME_1)
## Post #90
- Username: shiragiku
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jul 19, 2015 7:18 am
- Post datetime: 2015-07-22T00:56:20+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

progress for new C1 Cruise:

- Wrong Way for Inward deleted (fast_lane deleted) = works
- wall road on PA exit deleted ( now can go to pit from Rainbow bridge again ) = works
- wall road on inward and outward to Rainbow bridge deleted (now can go to rainbow bridge again) = works
- 20 Pitbox = works


- Race with 12 cars =    spawn outside map.
- cant use 2 lap timer on 1 map. so i just put outward lap timer on this map.

is out Already on RD

[http://www.racedepartment.com/downloads ... 2%A2.6818/](http://www.racedepartment.com/downloads/c1-area-c1-%E3%82%A8%E3%83%AA%E3%82%A2.6818/)
## Post #91
- Username: Takukun
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2015-07-22T08:01:19+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

See post at our Facebook page 
[https://www.facebook.com/pages/XeNTaX/143458469022795](https://www.facebook.com/pages/XeNTaX/143458469022795)
## Post #92
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2015-07-23T02:51:59+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from Mr.Mouse
>
> See post at our Facebook page 
https://www.facebook.com/pages/XeNTaX/143458469022795Cool, thanks admin, I thought for a moment that thread got locked or something...
## Post #93
- Username: drdoomslab
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Nov 22, 2014 9:40 pm
- Post datetime: 2015-07-30T19:05:28+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Hi,

This track is very enjoyable. I'd just like to thank everyone who was involved getting the data and converting it. I've had grate fun driving round in the Mazda 787 and the Audi 90 GTO/GTO s1 in AC. I also enjoyed exploring all the roots, and sometimes flying off the end of the track, lol. Grate to see how big it is.

I'd like to ask what other sims/games are people planning on converting this to?

For the Assetto Corsa track version (and maybe others) i would suggest putting the start/fin line before the pit exit or between the pit entery and exit. As it it now, after the pit exit your lap time is counted as you cross the line after you exit the pits and get onto the timed track. And then another idear i had was to split the materials to new materials for the tunnels so you can control the lighting better on the tunnel areas. If they are on different materials (you can keep the textures and uvw mapping the same) you can lower the light property's in kseditor for these area's. 

I would also like to ask where you might upload this to in the future as RD has taken down the links.
Thanks again. I look forward to updates.
Cheers.

DrDoomsLab.
## Post #94
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2015-08-02T08:22:22+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from drdoomslab
>
> Hi,
...
Hi, welcome.

You mean I should place the:
- AC_AB_START_R (placed before pit exit)
- AC_AB_START_L (placed before pit exit)
 and
- AC_AB_FINISH_R (placed before entry)
- AC_AB_FINISH_L (placed before entry) ???
The timer is counting once you spawn in the PA/pit but resets once you get onto the C1 route. But the lap time does not get saved once you finish the race, I'm not sure why.

I would like to convert this map to some game that can do basic lighting, like Project C.A.R.S or GRID. Assetto Corsa only has 1 light source, the sun, and there's no way to make night tracks unless you hack up a pp filter but even if you do it looks like crap in the end. I think same goes for rFactor 2, it doesn't do lighting very well. I mean my 1998 Sega Dreamcast can do multiple lighting better.

I don't know if I will be able to upload future updates. I've been messing around and working on rev3:

- 2 buildings redone here, the gloss on the windows reflects light, the other building has brown texture applied, these are authentic textures btw


- here the water reflects now, and that one building has been redone


- horizon textures, (that building next to mt. fuji is new)


Some things that I would like to do in rev3:
- fix flicker on some building (this is due to z-fighting problem, 2 textures are on top of each other) (10% complete...)
- add reverberating sound effect in tunnels (this is possible and been done in other tracks)
- improve road texture (remove yellow hue and increase resolution)
- surround map with horizon (done)
- retexture main/known buildings next to the road (30% complete...)
- improve water (done)
- smooth out ramp pit/PA exit/entry (almost done)
- retexture PA (started...)
- attempt to fill in void of space with something, to get rid of grayness....
- Anything else? Suggestions?

Do you know how to mod Assetto Corsa, can work with UV coords in 3ds Max or have Photoshop skills? Message me, my steam profile: [http://steamcommunity.com/profiles/76561198008059006/](http://steamcommunity.com/profiles/76561198008059006/), talk to me, motivate me, help me, make this better! Before I start working on something else
## Post #95
- Username: Berlik
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jul 04, 2015 8:28 am
- Post datetime: 2015-08-14T23:19:16+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Hey I started working on this few months ago but couldn't spend much time on it, lately been putting allot of work on this track and just found out some of you have been working on it aswell. Anyways here's my screenshots... still work in progress.

[](http://www.use.com/C4SOK?p=1) [](http://www.use.com/C4SOK?p=2) [](http://www.use.com/C4SOK?p=3) [](http://www.use.com/C4SOK?p=4) [](http://www.use.com/C4SOK?p=5)
## Post #96
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2015-08-15T01:25:30+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from Berlik
>
> Hey I started working on this few months ago but couldn't spend much time on it, lately been putting allot of work on this track and just found out some of you have been working on it aswell. Anyways here's my screenshots... still work in progress.
I like it man. Can you share the road texture with me? I'm going to send you my latest files (the rev3 in progress) so maybe you can apply some of your changes on top of mine. Feel free to reach out or chat. I posted changes to rev3 in last posts and my Steam id.
## Post #97
- Username: Berlik
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jul 04, 2015 8:28 am
- Post datetime: 2015-08-15T01:49:28+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

I have about 60+ hours in mine. I'll hit you up on steam.
## Post #98
- Username: mlfr
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 26, 2015 7:05 pm
- Post datetime: 2015-08-28T12:35:22+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

can anyone explain to me why is it when i open c1 in 3ds that the objects have no textures? thanks
## Post #99
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2015-09-17T19:45:40+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

You guys... You literally made my dream come true. For the past five years I could only imagine taking my hands over the 3D model of Shutokou.

I'm not a programmer and don't have the skills but I would really love to do something like this with Tokyo Xtreme Racer 3 which has Osaka and Nagoya. Or with any other TXR game.

My respect!

> Reply from mlfr
>
> can anyone explain to me why is it when i open c1 in 3ds that the objects have no textures? thanks
I think you must first extract the .XTD files to get the textures.
## Post #100
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2015-10-05T00:49:10+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from Takukun
>
> You guys... You literally made my dream come true.thanks.

rev3 download here, [https://mega.nz/#!fwEmTLBR!mQsk5odisFEg ... DFSI_Z4X1A](https://mega.nz/#!fwEmTLBR!mQsk5odisFEgK5YfJzdVeW1WKk0s67G7xDFSI_Z4X1A)
md5hash: d1526a9d1c7d16be5a1d97aadabbd2a8
## Post #101
- Username: lratafia
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Oct 20, 2015 9:27 am
- Post datetime: 2015-10-20T03:01:55+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Hi, what are the changes of rev 3? thanks
## Post #102
- Username: illking
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 15, 2015 8:29 am
- Post datetime: 2015-11-17T15:28:40+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Anyone have all parts of full expressway 3d model textured? A friend of mines will like to model and add the Tokyo aqualine bridge with umihotaru parking area onto this masterpiece. The texturing process is daunting though.
## Post #103
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2015-11-22T12:01:48+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from illking
>
> Anyone have all parts of full expressway 3d model textured? A friend of mines will like to model and add the Tokyo aqualine bridge with umihotaru parking area onto this masterpiece. The texturing process is daunting though.PMed you c1 download link.
## Post #104
- Username: kimdrummel
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 06, 2015 4:18 am
- Post datetime: 2015-12-05T20:21:26+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Is there still any progress being made on this? Was thinking about this whole DMCA thing. I love this being ported to Assetto Corsa. I was dreaming about doing this for rFactor 1 back in the day but with the models from TXR 3.
## Post #105
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2015-12-05T22:55:18+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from kimdrummel
>
> Is there still any progress being made on this? Was thinking about this whole DMCA thing. I love this being ported to Assetto Corsa. I was dreaming about doing this for rFactor 1 back in the day but with the models from TXR 3.I consider C1 map complete at this point. I have handed files to multiple people who have asked, I think they are playing around and trying to convert map to rFactor, you can search youtube for videos. The DMCA thing doesn't have that much impact, don't worry about it, the download link to rev3 is still here.

Main thing is the lack of a racing game that can do decent job with lighting in order to have a night map.
## Post #106
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-12-06T16:16:39+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

If someone is willing enough to convert this to GTA V, C1 would look absolutely gorgeous.
## Post #107
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2015-12-08T01:39:38+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Guys I was now seriously thinking about doing the same thing with TXR3 and I've been playing around with Hex editors and stuff, looking at the structure of the game etc. but as I have ZERO experience with Hex, reverse engineering, BMS, MaxScript and stuff (only a little programming experience) I just don't know where to start.

Is this even feasible for me to do? I am willing to learn but I fear It's too advanced as I'm a total noob...
Any help is appreciated.

Again THANK YOU for making this possible, I just can't describe how happy I am. Maybe I'm just too obsessed with Shuto expressway...
## Post #108
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-12-08T06:55:11+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Don't worry, you're not the only one. I'm the same as you. Heck, i have no idea what programming is. I helped nfm by pointing out stuff like possible file structure and stuff. He's the one doing the programming and extracting, and mariokart64n did the maxscript (and some other who helped that i forgot to mention).

If you're gonna give TXR3 a try, maybe guys like the ones said above might help you. I'm also looking forward if Osaka's model can be taken. But you know, there's an even better world than TXR3, which is Wangan Midnight Maximum Tune series. It's currently the 5th game that's available in my country, but someone uploaded the arcade files of WMMT2 on the internet. WMMT2 alone have nice looking shutokou map, from C1, New Belt Line, Yokohane, Wangan, Osaka, Hakone, and some i forgot. Newer maps like Nagoya, Fukuoka, C2, and Hakone Taikan is only available on WMMT5 (Japanese and International version have different maps, cars, and features).

Well, i'm just giving my opinion for something better than TXR3, but TXR3 itself is great too.
## Post #109
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2015-12-09T12:27:41+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from REDZOEU
>
> Don't worry, you're not the only one. I'm the same as you. Heck, i have no idea what programming is. I helped nfm by pointing out stuff like possible file structure and stuff. He's the one doing the programming and extracting, and mariokart64n did the maxscript (and some other who helped that i forgot to mention).

If you're gonna give TXR3 a try, maybe guys like the ones said above might help you. I'm also looking forward if Osaka's model can be taken. But you know, there's an even better world than TXR3, which is Wangan Midnight Maximum Tune series. It's currently the 5th game that's available in my country, but someone uploaded the arcade files of WMMT2 on the internet. WMMT2 alone have nice looking shutokou map, from C1, New Belt Line, Yokohane, Wangan, Osaka, Hakone, and some i forgot. Newer maps like Nagoya, Fukuoka, C2, and Hakone Taikan is only available on WMMT5 (Japanese and International version have different maps, cars, and features).

Well, i'm just giving my opinion for something better than TXR3, but TXR3 itself is great too.
Glad to hear that 

Sadly, there are no WMMT machines in the whole country where I live (did they even bring them to Europe?) but I agree that Maxi2 looks gorgeous (well, if we could extract 3D from WMMT5 that would be even better ). I chose TXR3 mainly because of Osaka and Nagoya. If I remember correctly, there is also an extra piece of Wangan which is missing in other TXR games.

I extracted the .chd file of Maxi2 (which is under 1GB) with the help of MAME's tool "chdman" and the header of the extracted img is ".ÿÿÿÿÿÿÿÿÿÿ....." and the image name which are repeated several times. TXR3's BUILD.TOC's header is "æi..#5®.t ®.]B®." 

These are the only things I know.

As I said I'm willing to learn, I just need some indications where even do I start xD Or is it even possible, because of Import Tuner Challenge being compressed with an unknown format, there is a chance also TXR3 is...
## Post #110
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-12-09T15:04:14+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Wow, great progress there, mate 
Now we just have to wait for someone professional enough with these type of things to help us once again. Hell, i posted few topics, and none get helped. Only this one, with the help of nfm. Let's just hope things won't just stop at only Wangan Midnight.
## Post #111
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2015-12-09T22:26:54+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from REDZOEU
>
> Wow, great progress there, mate 
Now we just have to wait for someone professional enough with these type of things to help us once again. Hell, i posted few topics, and none get helped. Only this one, with the help of nfm. Let's just hope things won't just stop at only Wangan Midnight.
Actually it's nothing you can't do. Just open up the file in the Hex editor, read the header and check if any of the stuff is human-readable/understandable.

Yeah I saw the ITC one... nobody seems to know  I'm the type of person who doesn't like to ask and pray for help but it's a dead end for me at this point.

Currently, I'm learning BMS script from some pages I found online.

Man, imagine... A game with the full complete Shuto expressway + Osaka + Nagoya etc, with the storyline(s) and gameplay of TXR and WMMT, fully moddable game engine with options of importing your own 3D cars and customizing them to your liking, multiplayer battles of 2 vs 2 or even 3 vs 3, decent traffic (not like TXR3's annoying yellow van) etc etc etc... goosebumps xD
## Post #112
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-12-10T02:13:13+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Hell, that would be japanese car culture's paradise for a game. 

Honestly speaking, i'm lazy when it comes to codes, but hearing that from you, it sounds easy. Maybe if i have time, i might do some googling to learn a little bit of stuff like maxscript, bms, and hex. But i tried learning hex once, but failed at doing so (was attempting to extract models with hex2obj for the game RIDE).

Assetto Corsa's almost close enough to what we actually want. It's just that it lacks arcade physics, customization, time, weather, story, etc. Might as well make that kind of game using Unity or any other game engines imo.
## Post #113
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2015-12-10T10:21:40+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from REDZOEU
>
> Hell, that would be japanese car culture's paradise for a game. 

Honestly speaking, i'm lazy when it comes to codes, but hearing that from you, it sounds easy. Maybe if i have time, i might do some googling to learn a little bit of stuff like maxscript, bms, and hex. But i tried learning hex once, but failed at doing so (was attempting to extract models with hex2obj for the game RIDE).

Assetto Corsa's almost close enough to what we actually want. It's just that it lacks arcade physics, customization, time, weather, story, etc. Might as well make that kind of game using Unity or any other game engines imo.
Bad news. I've been playing around with hex and found the .éUCLÿ header somewhere in the middle of BUILD.DAT file (TXR3) which I thought wasn't there. In other ps2 GENKI games i checked the files start with this header right off the bat so I thought this one, which doesn't have it at the start of the file, was extractable.

According to nfm, ITC uses the same header which points to some kind of unknown encryption. This is what i feared the most 

Man I'm disappointed. Now we really need some experts to work on this.
## Post #114
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2015-12-11T22:19:27+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

A little update.

I've been trying to extract the files from the chd of Maxi2 for the last 2 days but still I'm not successful. It is an old Sega GD ROM, you can open it with Dreamcast file explorers for that file but the difference is no files would show up except three txt files with no useful info. IsoBuster's not helpful either. Then I found online someone wrote some tools for Sega Chihiro platform, including an extractor, in C language (they weren't compiled). It seems these tools are for Linux as some libraries included are unix-based so i went and tried to compile them in CentOS 6 with gcc which threw out errors. There is also a .sh file which is the main file and makes use of MAME's chdman, bin2iso and other tools. Finally I succeeded to compile some of the tools with DevC++ on windows but the main tool (the extractor) still wouldn't compile because of some errors.

So does any of you know how to extract data from a chd (especially Chihiro's Wangan Midnight Maximum Tune)?

Next thing, I succeeded at extracting Dreamcast's Tokyo Xtreme Racer 2's 3D files. They are without an extension and are stored in .AFS archives which can be opened using some tools. I know they are low poly but hey, they don't have that weird header and are extractable  now I must find a way to import them.

Oh I almost forgot. A year ago or so I ripped the cars from TXR Portable (PSP). Poly number is very similar to TXR3's.
[gdbexpressway.png](https://xentaxbackup.github.io/file/10141_gdbexpressway.png)
## Post #115
- Username: lratafia
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Oct 20, 2015 9:27 am
- Post datetime: 2015-12-13T18:30:31+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from nfm
>
> kimdrummel wrote:Is there still any progress being made on this? Was thinking about this whole DMCA thing. I love this being ported to Assetto Corsa. I was dreaming about doing this for rFactor 1 back in the day but with the models from TXR 3.I consider C1 map complete at this point. I have handed files to multiple people who have asked, I think they are playing around and trying to convert map to rFactor, you can search youtube for videos. The DMCA thing doesn't have that much impact, don't worry about it, the download link to rev3 is still here.

Main thing is the lack of a racing game that can do decent job with lighting in order to have a night map.

hi, you know the track doesn't appear on the acServerManager, do you know how to fix that? thanks
## Post #116
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2016-01-02T11:49:27+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Cmon guys, no one?  If the strange Genki's encryption gets taken care of, then we can get another HUNDREDS of kilometers of expressways! For example:

Osaka area (Hanshin expressway):
 -loop 1
 -route 16
 -route 4
 -route 6
 -route 15

Nagoya area:
 -Ring route
 -high speed loop of Nagoya expressway (don't remember the name)

Tokyo Area:
 -Yaesu
 -Shinjuku 4
 -Shibuya 3
 -EDIT: Minato Mirai
Then there are custom cars of C1 Racing Battle and Kaido Battle with special vinyls, not mentioning the great number of tracks to race on.

Hopefully somebody can help.

Enjoy and I wish you all a happy new year!
## Post #117
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2016-01-13T15:10:47+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Oh hell, somehow new replies are not notified to me by e-mail   
Nice progress there!
Also, i'm wondering if this is nfm's youtube channel?
[https://www.youtube.com/watch?v=gkH8aG3NOrc](https://www.youtube.com/watch?v=gkH8aG3NOrc)
That's a video of Wangan for AC.
And as always, i can't be of any help with those headers stuff (i don't even know how to extract them .afs files   )
Guess all i can do is just wait
## Post #118
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2016-01-17T19:20:39+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

rev4 is here with some changes if anybody's interested, there's still tons of things I would like to see improved

c1_rev4.zip 85.9MB, md5 hash: 60c254c93c2f9666635350e60158350a
download: [link](https://mega.nz/#!mpUijQqD!xFCvPI-IZrfzYEcQ5vYLBQDtz_VyX9__03w_I4uUIlw)

[rev4]
- fixed missing AC_PIT_2, map can now work with 12 cars
- added a turn-around on rainbow bridge for a way to re-enter the pit stop
- added AC_TIME_1_L & AC_TIME_1_R boxes for split-time, general timing and ghost car recording (thanks to Aleinikov65 for mentioning)
- moved pit boxes [5,6,7,8,9,10,11] to fix AI cars spawning on the road above (thanks to Aleinikov65 for mentioning)
- added sections.ini file for track description app (by Aleinikov65)
- added TV Cameras! (and csv files for camera spline movement) (by Aleinikov65)
- made pitlane.ai file for AI to enter and leave track (this not quite works yet) (by Aleinikov65)
- redone the fastlane.ai, however AI cars still crash into the walls (by Aleinikov65)

Yeah the Wangan preview video is by me @REDZOEU
## Post #119
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2016-01-19T14:22:45+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Haha, that explains the same profile picture then   
I still can't quite enjoy the mod to the fullest (due to lags). If there's anything i could help with, let me know (If i could be of use, anyway).
I might consider making car mods for AC too, but exams are on my way, so that's a no go for now.
## Post #120
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2016-01-20T20:56:37+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Wow, that's awesome. Thanks guys!

What about SBOL? Shutokou Battle Online was the only PC SB game by Genki, and it has nice score of cars. If someone is willing to take a look it will be greatly appreciated  

samples: [https://www.dropbox.com/s/j4st00metd0xbp3/CAR.zip?dl=0](https://www.dropbox.com/s/j4st00metd0xbp3/CAR.zip?dl=0)
## Post #121
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2016-01-21T09:53:54+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from RacingFreak
>
> Wow, that's awesome. Thanks guys!

What about SBOL? Shutokou Battle Online was the only PC SB game by Genki, and it has nice score of cars. If someone is willing to take a look it will be greatly appreciated  

samples: https://www.dropbox.com/s/j4st00metd0xbp3/CAR.zip?dl=0
I wanna cry, seriously. But i can't, since C1 is now playable via AC on PC 
Well, here's an old thread by me about SBOL : [viewtopic.php?f=18&t=8716](http://forum.xentax.com/viewtopic.php?f=18&t=8716)
Just wondering if it's useful... That hope of getting models and textures from that game has ended back then, but this thread brought back the light to me.

EDIT: Wait, i just noticed that you posted a reply there too back then. LOL
## Post #122
- Username: lratafia
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Oct 20, 2015 9:27 am
- Post datetime: 2016-02-03T13:09:58+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from nfm
>
> rev4 is here with some changes if anybody's interested, there's still tons of things I would like to see improved

c1_rev4.zip 85.9MB, md5 hash: 60c254c93c2f9666635350e60158350a
download: link

[rev4]
- fixed missing AC_PIT_2, map can now work with 12 cars
- added a turn-around on rainbow bridge for a way to re-enter the pit stop
- added AC_TIME_1_L & AC_TIME_1_R boxes for split-time, general timing and ghost car recording (thanks to Aleinikov65 for mentioning)
- moved pit boxes [5,6,7,8,9,10,11] to fix AI cars spawning on the road above (thanks to Aleinikov65 for mentioning)
- added sections.ini file for track description app (by Aleinikov65)
- added TV Cameras! (and csv files for camera spline movement) (by Aleinikov65)
- made pitlane.ai file for AI to enter and leave track (this not quite works yet) (by Aleinikov65)
- redone the fastlane.ai, however AI cars still crash into the walls (by Aleinikov65)

Yeah the Wangan preview video is by me @REDZOEU

thanks a lot for the update!! this track is amazing, thanks to all involved!
## Post #123
- Username: boohHF
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 04, 2016 2:36 pm
- Post datetime: 2016-02-04T07:04:03+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

rev5 screenshot
[c1_4-2-116-14-47-21.jpg](https://xentaxbackup.github.io/file/10418_c1_4-2-116-14-47-21.jpg)
## Post #124
- Username: TrackMaD
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Feb 04, 2016 4:19 pm
- Post datetime: 2016-02-04T08:30:45+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Hey Guys, mega work on C1, luv it, Rev 5 looks awesome. Thanks
## Post #125
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2016-02-06T16:00:58+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from boohHF
>
> rev5 screenshot
Welcome to the forum, and thanks for making contributions to the rev5 of the map, many people including me will appreciate your work and new changes!
## Post #126
- Username: boohHF
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 04, 2016 2:36 pm
- Post datetime: 2016-02-06T16:16:18+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

C1 rev5
 added Inner Loop layout
 added physical roads and walls
 added reverb effects
 added surfaces joint and line on the road
 changed ai files, AI car works
 changed shaders (road tree water)
 changed grid location
 changed vending mashines at Shibaura PA
 changed some ui files
 optimized some meshes

[https://mega.nz/#!NdIVTaDZ!ChpDPELUYwUG ... n-qyIZdFcA](https://mega.nz/#!NdIVTaDZ!ChpDPELUYwUGDAPHKbkoIy3kljy3xc898n-qyIZdFcA)
## Post #127
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2016-02-06T17:40:36+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Gets better everytime. Great work
## Post #128
- Username: cruiser
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 09, 2016 6:46 pm
- Post datetime: 2016-02-09T12:26:56+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

hello everyone, im new here and know nothing about modding   
but still, i wanna contribute some effort to this beautiful project

playing TXR3 (Shutokou Battle 01) since i was young, i was blasted when i knew c1 is in AC,
thanks to the efforts of you fellows (again im new here )

long story short, i did what i can do, is to make a "slow_lane.ai"
well, the ai in rev5 is good, esp for those who like wangan battles
but for me, i rather want the ai's driving in some slow pace, like a civilian car

after 3 hours of digging and trial and error, and alot of frustration,
i finally come into this: INNER LOOP -  [https://mega.nz/#!LE1zSKZT!1RPW1IIPRCtH ... QljPnS0sMs](https://mega.nz/#!LE1zSKZT!1RPW1IIPRCtHVpq1UGcc_qUdqy9m_6aGiQljPnS0sMs)
and i ll make one for outer loop if u guys want one  

in general, the ai's cope pretty well with the tracks & others
overtake in the fast lane just in real life!


the major issue is the overlapping part of the purple line at the start line


the ai's seemingly will grind the wall for just a moment and then keep going, i guess its nothing major


trucks have less severe problem because of the the big car body


to solve this, i guess i need to edit the ai lines in ksedit, but i dont know how to load the track...

in addition, buses struggle to even get out of the pit   


lastly, i wanna ask... is it possible to add insane amount of ai's in the map?
## Post #129
- Username: TrackMaD
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Feb 04, 2016 4:19 pm
- Post datetime: 2016-03-18T10:51:57+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Hey Guys, anything else happening on this great AC mod, any WIP's or anything related, would it be possible to re-create the look of the HUD
## Post #130
- Username: lratafia
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Oct 20, 2015 9:27 am
- Post datetime: 2016-04-16T18:02:17+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

you could add traffic by adding grids every 500m or so and that would make some nice traffic
## Post #131
- Username: lratafia
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Oct 20, 2015 9:27 am
- Post datetime: 2016-05-15T16:33:36+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

hi there, any more updates coming to this track in the future? is this the only forum that keeps updated or are there any other to follow?
thanks
## Post #132
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2016-05-15T18:15:26+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

This should be the only forum though. I haven't heard news of this map's progress directly from the author or from another helper. Or the map could be considered complete now. Maybe.
## Post #133
- Username: TyreRubber
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 24, 2016 7:18 pm
- Post datetime: 2016-05-21T22:39:03+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Hi all.

I allways wanted to recreate a wangan series game and so I started, ran out of funds and project stalled.

I placed Genkis track on my game shell and this is the output. Enjoy.

Game will never be released but the good news are that Gran Turismo Sport does feature C1 loop so you can play it in super nice detail.

Screens:
[](http://postimg.org/image/u5wyzkgs1/)

[](http://postimg.org/image/tnsms8cfl/)

[](http://postimg.org/image/ppw6bcaup/)

[](http://postimg.org/image/p5qc04wdt/)

[](http://postimg.org/image/k0p4iijg1/)

[](http://postimg.org/image/wurrplm9d/)

[](http://postimg.org/image/gmg4tv2sx/)

VIDEO
[https://www.youtube.com/watch?v=3ufdUItokIc](https://www.youtube.com/watch?v=3ufdUItokIc)

Enjoy.
## Post #134
- Username: TyreRubber
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 24, 2016 7:18 pm
- Post datetime: 2016-06-11T16:30:17+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Look what I found!!

[https://www.youtube.com/watch?v=6vVavpZJxqo](https://www.youtube.com/watch?v=6vVavpZJxqo)
## Post #135
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2016-06-11T22:03:54+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Is that an addon map for ETS2? Didn't know was possible to make modded sceneries for it.
Also, great job with your game, looks sweet!
## Post #136
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2016-06-12T18:21:11+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Small update, mainly tweaked textures and adjusted UV maps



22139f93bbbcb533a5e9d8fba43f1875 *c1_rev6.zip 150MB
[https://mega.nz/#!WlEUTJoZ!D5v3-HflS6wD ... -KLSaGYowU](https://mega.nz/#!WlEUTJoZ!D5v3-HflS6wDYGnoEX4YyEznBcEUtSo4J-KLSaGYowU)

Also I found some idiot who stole this C1 map and is trying to release a game on Steam and sell it for $5 [http://steamcommunity.com/sharedfiles/f ... =681911073](http://steamcommunity.com/sharedfiles/filedetails/?id=681911073)
## Post #137
- Username: TyreRubber
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 24, 2016 7:18 pm
- Post datetime: 2016-06-14T12:37:42+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from Automotive Gaming
>
> Is that an addon map for ETS2? Didn't know was possible to make modded sceneries for it.
Also, great job with your game, looks sweet!

It is!. I tried reversing with the tools I found but no luck. The racing game has been stopped for years. Now I'm busy finishing a tank game, If I succeed enough I'll try to revive the wangan series project.
## Post #138
- Username: TyreRubber
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 24, 2016 7:18 pm
- Post datetime: 2016-06-14T13:24:54+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from nfm
>
> 

Also I found some idiot who stole this C1 map and is trying to release a game on Steam and sell it for $5 http://steamcommunity.com/sharedfiles/f ... =681911073

Crazy shit that ppl has balls big enough to rip assets and put them in a comercial project. I bet Steam will ditch this guy as quick as they get aware of this sh*t
## Post #139
- Username: lratafia
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Oct 20, 2015 9:27 am
- Post datetime: 2016-06-22T01:26:03+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

there's a guy who made extra cameras, drone like, they are very nice, they can be found on racedepartment.
thanks for the update and for keeping it alive.
## Post #140
- Username: kelnor34
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Sep 03, 2016 7:01 pm
- Post datetime: 2016-09-03T11:20:14+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Hi all,

I just wanted to say a BIG THX! for this incredible job on this fantastic road track.
I discovered it recently, and In one word: WWWOOOAAA!

So here is few screenies:
[](https://flic.kr/p/KRwH87)

[](https://flic.kr/p/LndrWs)

[](https://flic.kr/p/LFEgPK)

[](https://flic.kr/p/KRYjEP)

[](https://flic.kr/p/LNUPmM)

[](https://flic.kr/p/Lop53j)

[](https://flic.kr/p/LLP4hY)

[](https://flic.kr/p/LLPhgo)

[](https://flic.kr/p/LGNea4)

[](https://flic.kr/p/LGN96M)

[](https://flic.kr/p/LPReZg)

I have just one wish: that a night version of the (REV6) will be available soon   

Once again: THX a thousand times for this outstanding stuff!!!

Regards
## Post #141
- Username: samasama76
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Nov 03, 2015 8:33 pm
- Post datetime: 2016-09-03T16:01:11+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Nice ScreenShots!
Please tell me What's Effect Filter you use?
## Post #142
- Username: kelnor34
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Sep 03, 2016 7:01 pm
- Post datetime: 2016-09-03T17:00:51+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Hi samasama,

Thx for your comm.

I use JGSME & Content Manager with:
NGM 3.5 mod by ears1991.
Natural (kunos) or Natural Photomode HC PPfilters "slightly tweaked".
Good and bad conditions weather by Peter Boese

You can found all of them on Racedepartement.

Some more:
[](https://flic.kr/p/LHWMGB)

[](https://flic.kr/p/Lpw1fj)

[](https://flic.kr/p/LMXVRm)

[](https://flic.kr/p/KTRzYh)

Regards
## Post #143
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2016-09-08T05:20:35+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Nice screenshots kelnor34,

There is a night version of C1, I was rather impressed, search for 'assetto corsa c1' in youtube and look for videos uploaded in last week/month. You should somewhere find a file called c1-midnight_for_ac18.zip in youtube's comments.

[https://www.youtube.com/watch?v=OqyTET37kiI](https://www.youtube.com/watch?v=OqyTET37kiI)
[https://www.youtube.com/watch?v=caydxukveUY](https://www.youtube.com/watch?v=caydxukveUY)

Seems like many are using Real Life Weather 2.1.4 or aura pp filter﻿ with the night version of C1.
## Post #144
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2016-09-08T05:51:06+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Also for anyone interested in Wangan, there's an epic mod for ETS2 called 'Tokyo Bayshore' by Koutsu [https://twitter.com/KoutuuHAGE](https://twitter.com/KoutuuHAGE)





[https://www.youtube.com/watch?v=wGTlu3vlUOY](https://www.youtube.com/watch?v=wGTlu3vlUOY)

The author appears to be very dedicated and put in well over 1000 hours of work if I'm not mistaken. Unfortunately I can't read Japanese.

There are also folks who go their hands on the arcades and have dumped Wangan Midnight Maximum Tune 3 and 4!
[https://medium.com/@ValdikSS/researchin ... .2k10ynsm6](https://medium.com/@ValdikSS/researching-protection-and-recovering-namco-system-es1-arcades-1f8423fdeb3b?swoff=true#.2k10ynsm6)
[https://medium.com/@dropkickshell/syste ... .c4amwrkah](https://medium.com/@dropkickshell/system-n2-exposed-5395436c824d#.c4amwrkah)
## Post #145
- Username: kelnor34
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Sep 03, 2016 7:01 pm
- Post datetime: 2016-09-12T18:17:26+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from nfm
>
> Nice screenshots kelnor34,

There is a night version of C1, I was rather impressed, search for 'assetto corsa c1' in youtube and look for videos uploaded in last week/month. You should somewhere find a file called c1-midnight_for_ac18.zip in youtube's comments.

https://www.youtube.com/watch?v=OqyTET37kiI
https://www.youtube.com/watch?v=caydxukveUY

Seems like many are using Real Life Weather 2.1.4 or aura pp filter﻿ with the night version of C1.

Thx for the "tip" nfm,

Tried with my own "W.I.P" PPfilter & weather.... not fulfilled   

[](https://flic.kr/p/LcMtNR)

[](https://flic.kr/p/M2LChX)

[](https://flic.kr/p/LcBFsJ)

[](https://flic.kr/p/M2Lysx)
## Post #146
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2016-10-10T05:07:48+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

I found a game a while ago which contains parts of the Japanese Expressway that we don't have yet, Battle gear 4. I know that this topic is about Wangan Midnight PS3 but nonetheless i felt it would be right to post in here.
This game is only for arcade but fortunately, as it was designed for Windows, it works perfectly well on home PCs. So i tried my hand at analyzing the files and found out this game uses a similar 3D structure as GTA San Andreas. It might not be so difficult to reverse.

Car textures are stored in .txd format which can be normally viewed and exported with TXD Workshop.
For 3D, when the file extension is renamed from .rws to .dff, ZModeler imports car files, but without texture coords, normals and the model is completely black.



3DS Max with the KAM's script doesn't even want to import.

For the maps, though, nor ZModeler nor 3DS Max don't budge.
They are in the same format (.rws) but with textures integrated in the file.

Here's a screenshot of one of the map files when opened with a hex editor:



And random screenshots of the Hanshin Expressway:




As a last resort i hoped for 3D Ripper DX or Ninja Ripper to do their job but nope.

It would be nice to have some more parts of the Japanese Expressway in 3D, especially because parts of the code for importers are already written by other people.
To finish, here are some videos of the game in action:

[https://www.youtube.com/watch?v=BsfB-E0_jIg](https://www.youtube.com/watch?v=BsfB-E0_jIg)
[https://www.youtube.com/watch?v=JI1FKbxhkPk](https://www.youtube.com/watch?v=JI1FKbxhkPk)
[https://www.youtube.com/watch?v=VjMf9520nZU](https://www.youtube.com/watch?v=VjMf9520nZU)
## Post #147
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2016-10-10T13:11:45+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

That's cool. You should provide some samples for analysis.
## Post #148
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2016-10-10T14:57:45+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Thanks for considering 

Here are the car and map files + car's .txd file.

[http://www.mediafire.com/file/fvzbpdetx ... egear4.rar](http://www.mediafire.com/file/fvzbpdetx1prr13/battlegear4.rar)
## Post #149
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2016-10-11T12:33:41+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Thanks for sharing this!

You're wrong about the missing UV's though, everything is there, you just need to extract the textures first and use something else than Zmodeler2 (after resaving the imported DFF into something else). I personally prefer using Zmodeler1. Some materials might be set as black, so just recolor them to white.

Here are the R33 and R33 LM:



I tried importing the track files, but they seem to be in different format
## Post #150
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2016-10-11T14:59:35+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Now this is a big discovery! Wait until someone capable of tinkering with the map files see this
## Post #151
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2016-10-12T05:15:12+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

WOW i completely forgot about ZModeler 1. Thanks 
Though I can't import anything because it says "Your computer is low on memory" when I have enough. But it does indeed work with reimporting in zmod2.

Yep we now only need to be able to import those maps. There are other files beside the main 3d file but all are plain text config settings for the game and a small .txd file containing only some banners.

Also, another game could have japanese expressway maps, but all I found were some screenshots of a 240Z posing in front of the Rainbow bridge, too little info. And, it's only for iOS. Name's 2K Drive.
[http://www.lucidgames.co.uk/product/2kdrive/](http://www.lucidgames.co.uk/product/2kdrive/)
## Post #152
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2016-10-12T06:59:07+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

If you look carefully into my post, I didn't say importing directly with Zmod1. Import in Zmod2 and re-save as old z3d. What's the chance that there could be other japanese arcade games which use RenderWare? Even if they don't feature japanese expressway maps.

2KDrive looks great. It deserves attention by the guys who are able to hack file formats here.
## Post #153
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2016-10-12T16:23:33+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Ah yes i cofused things, thanks 

I don't know about those, this is the first one I've seen with such a game engine, but there could be more. Try looking up the games by the system on which they run, like Sega Chihiro or Naomi.

I've looked a little bit in 2K Drive game files and discovered the model files are stored in .lbc format and textures in a .pvr format.
## Post #154
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-12T23:34:56+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from Takukun
>
> Here are the .... car's .txd file.
http://www.mediafire.com/file/fvzbpdetx ... egear4.rar
i made a Noesis python script for fun to open your txd sample  


 tex_BattleGear4_txd.zip
(880 Bytes) Downloaded 36 times


supports dxt1, dxt3, dxt5 and rgba32

theres a chance a may not work with other txd files from your game, 
but if you can upload more samples of this type i will update the script.
## Post #155
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2016-10-13T00:24:09+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

WOW this is awesome, thank you for your effort  It works like a charm for car, cockpit and wheel textures.
Here are more examples that give errors if you want to optimize the code 

[http://www.mediafire.com/file/l55l8iu79 ... amples.rar](http://www.mediafire.com/file/l55l8iu79ui7szy/samples.rar)
## Post #156
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-13T02:16:05+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

okay i updated the script in my previous post to support your new samples   

it turns out to also work with the txd sample for "S.C.A.R.: Squadra Corse Alfa Romeo" from this thread   
[viewtopic.php?f=16&t=14302&p=118368](http://forum.xentax.com/viewtopic.php?f=16&t=14302&p=118368)
## Post #157
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2016-10-13T03:44:54+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

This is great, thanks for all the help  If you don't mind I updated my previous post with some more examples which I believe are the last ones.

Programming skills really are useful nowadays
## Post #158
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-13T04:19:32+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

okay i updated that post again with updated script 
[viewtopic.php?p=123473#p123473](http://forum.xentax.com/viewtopic.php?p=123473#p123473)
## Post #159
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2016-10-13T06:27:45+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Great job!! It works with some TXD's that TXDWorkshop corrupted.
## Post #160
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2016-10-13T09:52:18+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

As far as I know this script is perfect  Me and (I'm sure) others are very thankful to you!

Another thing, I found a [tool](https://sourceforge.net/projects/rwsreader/) for viewing RenderWare models. As it's only source code and I'm pretty rusty with compiling I can't check if this would work with Battle Gear map files.
## Post #161
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2016-10-13T17:04:18+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Hi guys, this is a very good topic for the Japanese track and cars models, very close to getting tracks from BattleGear4 may be able to help RWAnalizer Tool?

We also have experience of Initial D Extreme Stage for PS3 [viewtopic.php?f=16&t=14024](http://forum.xentax.com/viewtopic.php?f=16&t=14024)
I managed to unzip resources game with some help QuickBMS and get the texture of the game using the X-Ripper but get a 3d model I do not know how, maybe someone of you will be able to heal the geometry of the tracks from this game? 

It would be a list of cool to convert to Assetto Corsa.
## Post #162
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2016-10-13T17:26:26+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Yep, BG4 has a very cool pile of tracks, from Wangans to Touges, it even has Montecarlo.
Here's the list: 

[http://battlegear.net/bg4tuned/course.html](http://battlegear.net/bg4tuned/course.html)
## Post #163
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2016-10-13T18:55:51+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Thanks for reminding me of RW Analyze  It opens the map files perfectly well but from there on, i don't know what to do anymore.

Initial D Extreme Stage also has some nice tracks and car models, I hope you succeed 

Yes you're right. BG4 is not highpoly but this doesn't matter to me as long as those cool tracks can be ported.
## Post #164
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2016-11-08T02:27:23+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Hello again, as nobody can get around Genki's strange compression method, I decided to rip Minato Mirai from Shutokou Battle Zone Of Control PSP (Street Supremacy). From what I know the mesh quality is exactly the same as in Shutokou Battle 0 (Tokyo Xtreme Racer 3) with the exception of lower res textures, which can be replaced at a later time.

Firstly, I tried with an older version of Ninjaripper (because newer ones won't even inject) with the combination of PPSSPP and the result was course segments had proper scaling and orientation, the only thing I had to do is move them together in 3DS Max with vertex snapping on. The only downside was that not all meshes were ripped, only about 80-90%. I can extract meshes and textures (with inverted blue and red channel) 100% the 3D Ripper DX way though:



The problem comes in when attaching different segments together, as 3D Ripper DX extracts data corresponding to the angle you take the ingame capture at. You have to rotate to match the other segment properly.



My question is, how can I rotate 2 objects so that they snap to each other perfectly? I'm a total noob at 3DS Max btw, I use it mainly for import-export purposes. I really like the way SketchUp does it, it's possible to snap vertex to vertex while rotating so the outcome is 100% accurate, but it messes the whole material library up. Is there such a way in 3DS Max?

I can take the boring, it'll take a while but when I finish I'll post the model somewhere, that's why i want it to be perfect.

edit: grammar
## Post #165
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2016-11-08T03:15:49+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Sadly, with such ripping "strategies" the map will never be perfect. I did the same with some Gran Turismo PSP tracks, and had the same problem because of the different angle and position of the pieces.
## Post #166
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2016-11-08T03:41:04+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Hmm but if we somehow manage to rotate it right would it be possible right? I just don't want to remap everything if I do it with SketchUp. There has to be a plugin or a script somewhere...
## Post #167
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2016-11-08T04:32:03+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Nice work, Takukun! I tried lots of times ripping with Ninja Ripper, but i got lazy at moving the stuff, so yeah... 

Also, SBZOC has even far more textures than WM (cmiiw) that makes it even more confusing to apply.

Someone from the GTA SA scene managed to rip the whole C1 map from SBZOC perfectly, and properly working in-game. If i understand Japanese, i might be able to ask him how he was able to do that.

Note: AFAIK, you need to apply all textures in every map parts, export them as models, and THEN you have to create a separate file for textures, which you need to name one by one according to the textures names. It has to be the same, or else it won't work. Either this Japanese guy has a lot of spare time, or he has some kind of method to do that more easily and/or efficiently.
## Post #168
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2016-11-08T12:31:16+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from Takukun
>
> Hmm but if we somehow manage to rotate it right would it be possible right? I just don't want to remap everything if I do it with SketchUp. There has to be a plugin or a script somewhere...

You can rotate the pieces how much you prefer, but you will never have a perfect matching full track, and you also have to weld the pieces all together otherwise you would have holes between the pieces. It's not something I suggest to do, especially on long tracks.
A script to properly export the tracks is what is really needed to have the scenery in perfect conditions.
## Post #169
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2016-11-08T16:30:47+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Thanks REDZOEU  I'm gonna do this either way. The Ninjaripper one gets everything as it should be with the exception of some road signs and buildings + the car which is not needed (that's why I said it rips 80-90%). I also tried overlapping the 3D Ripper DX mesh to match the Ninjaripper one in an attempt to "add" the missing objects in 3DS Max but the outcome was horrible  too much rotating and scaling required. At the very least I'll use it as reference and rebuild the missing models.

Yeah I saw that GTA SA map. It would be nice if we could get an answer yes 

> Reply from REDZOEU
>
> Note: AFAIK, you need to apply all textures in every map parts, export them as models, and THEN you have to create a separate file for textures, which you need to name one by one according to the textures names. It has to be the same, or else it won't work.

Sorry for my bad understanding but is this about SketchUp, 3DS Max or converting to GTA SA?

Also, is this blog yours? [http://automotivebeautymods.blogspot.si ... tokyo.html](http://automotivebeautymods.blogspot.si/2015/03/c1-part-of-shutokou-expressway-tokyo.html)
Because I got the inspiration from there 

> Reply from Automotive Gaming
>
> You can rotate the pieces how much you prefer, but you will never have a perfect matching full track, and you also have to weld the pieces all together otherwise you would have holes between the pieces. It's not something I suggest to do, especially on long tracks.
A script to properly export the tracks is what is really needed to have the scenery in perfect conditions.

Yes but in theory, say we can align two 3D Ripper DX captures with the Sketchup method, then we can do the rest and it would still be perfectly okay.. Or is the ripping program the one at fault?

Yes it's gonna be long, that's why I plan to save in multiple files containing sections (I don't even have enough RAM to render the whole track at once xD). Although the main purpose is to have another laser-scanned Shuto expressway piece which can be reworked or modeled after at a later time to match WM PS3 quality.
## Post #170
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2016-11-17T20:21:27+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Okay I made some tests and i ripped the whole Minato Mirai course with minor errors (which can be fixed), the problem I'm facing is with the materials (as REDZOEU already said).

I have hundreds of objects which use the same diffuse map, but instead of using a single material they each use their own one with the same diffuse map. I need a script or a tool to merge duplicate materials which use the same textures. This way I can rename the textures faster at a later time.

Without a solution this will take months, if not years, as my spare time is diminishing.
## Post #171
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2016-11-17T20:44:18+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

I usually solve that with Deep Exploration: collapse everything, then, right click on the 3D model, then "Tools > Remove Duplicated Materials"
## Post #172
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2016-11-18T13:22:43+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Wow thanks, this does the trick
## Post #173
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2016-11-24T18:44:29+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

It's progressing slowly but steadily. What do you guys think?

EDIT: quick convert to GTA 4
## Post #174
- Username: SimRacer
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 19, 2016 2:17 am
- Post datetime: 2016-12-18T18:25:26+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

On behalf of the Assetto Corsa Community, you guys are doing great work over here, and we watch your progress with a keen eye. Sadly due to the ripped nature of the main track mesh we are not allowed to talk about it on the offical forum and Race Departement. But everyone and their dog is driving it 

I'm sure some of you are active on both those forums, but just in case, a few links to the main track modding repositories:

[http://www.assettocorsa.net/forum/index ... ips.27180/](http://www.assettocorsa.net/forum/index.php?threads/proper-technique-in-track-making-plus-tips.27180/)
[http://www.assettocorsa.net/forum/index ... ers.10174/](http://www.assettocorsa.net/forum/index.php?threads/track-materials-shaders.10174/)
[http://www.assettocorsa.net/forum/index ... ost-807165](http://www.assettocorsa.net/forum/index.php?threads/build-your-first-track-basic-guide.11239/page-65#post-807165)

[http://www.racedepartment.com/forums/as ... sions.414/](http://www.racedepartment.com/forums/assetto-corsa-modding-discussions.414/)

Keep up the good work
## Post #175
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2016-12-18T23:24:43+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Thanks for letting us know, SimRacer 

Takukun, i've been meaning to ask you, how do you convert that kind of map to GTA 4 so easily? Is there some kind of easy method of map converting for the game?
## Post #176
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2016-12-19T21:20:21+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

SimRacer thank you 

REDZOEU I just followed some tutorial on youtube and it's pretty easy, I just don't know how I'll be able to convert the entire Minato Mirai area as it exceeds the world limits. Also, I have close to no experience with limit adjusters.

Some screenshots of the current progress:







Pretty close to finishing the ripping process of what NinjaRipper can capture, what follows will be much harder as it involves rebuilding the missing meshes.
## Post #177
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2016-12-25T12:17:39+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Hello guys, 
I found a method of compression Tokyo Xtreme Racer series archive files, please let us check it who have programming skills together 
This is compressed method: [http://www.oberhumer.com/opensource/ucl/](http://www.oberhumer.com/opensource/ucl/)
Python UCL [https://github.com/jap/pyucl](https://github.com/jap/pyucl)
This confirmation compression method:


This example files Archive from ImportTunerChallenge [XBOX360]:
Main Archive: [https://www.dropbox.com/s/4m71uqaqyqs4l ... D.DAT?dl=0](https://www.dropbox.com/s/4m71uqaqyqs4lev/BUILD.DAT?dl=0)
Looks contains the names: [https://www.dropbox.com/s/61rzrm0b9gndt ... D.TOC?dl=0](https://www.dropbox.com/s/61rzrm0b9gndt1x/BUILD.TOC?dl=0)
## Post #178
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-25T19:04:57+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

QuickBMS supports that compression and there already exists a script for that game archive   
[http://aluigi.altervista.org/bms/tokyo_xtreme_racer.bms](http://aluigi.altervista.org/bms/tokyo_xtreme_racer.bms)
## Post #179
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2016-12-25T21:13:30+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Good news. I m using it and extracted archive 
I have a progress with textures.
There was a question with models and extracting them into the 3d editor.

I created a theme from Import Tuner Challenge here: [viewtopic.php?f=16&t=15644](http://forum.xentax.com/viewtopic.php?f=16&t=15644)
## Post #180
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2017-01-04T00:15:36+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

I am sorry if this turns out to be nothing but still, I'm curious, what's this??

[http://www.sb-x.jp/](http://www.sb-x.jp/)
## Post #181
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2017-01-04T03:46:16+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

@Takukun, new shutoko battle game?!
## Post #182
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2017-01-04T07:03:39+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Oh god that would be perfect  I just hope it won't be a cheap mobile game which will be discontinued after a few months.
## Post #183
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-01-04T21:07:19+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

I had contact with a former developer and he did not mention that they are doing something other than arcade machines and mobile games.
Strange domain has a name SB-X as we know Shutokou Battle X this is in the territory of Japan is our favorite Import Tuner Challenge.
Whatever it was, I played in all that is done Genki and I was not disappointed: D

Edit: I looked twitter Genki there also has information looks like this is not fake))
## Post #184
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2017-01-05T05:59:35+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

It has been confirmed. It's a mobile game. Saw this coming tho   
And i think we play it like in Drift Spirits maybe. Having free roam is kinda rare in mobile games.
## Post #185
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2017-01-05T07:53:51+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Oh god why... They could have taken another year or two to make a perfect PS4 game... Even the map can't be as detailed as on consoles. Oh well at least I hope the 3D models of cars will be extractable.
## Post #186
- Username: OkCan634
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Feb 07, 2017 9:17 pm
- Post datetime: 2017-02-07T14:58:53+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Sorry for bothering.. Do anyone knows how to extract models from IGB formats?
MT3 ISO is already out but I can't do anything with it  
[https://youtu.be/5-eGyM-4D7E](https://youtu.be/5-eGyM-4D7E)

I'm sorry if I broke any rules here , I'm new to xentax and this forum m(_ _)m
Thank you in advance.
## Post #187
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-02-07T17:33:10+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from OkCan634
>
> Sorry for bothering.. Do anyone knows how to extract models from IGB formats?
MT3 ISO is already out but I can't do anything with it  
https://youtu.be/5-eGyM-4D7E

I'm sorry if I broke any rules here , I'm new to xentax and this forum m(_ _)m
Thank you in advance.

This game uses alchemy engine. This engine was built by a lot of different games.
I did not find a solution, recently I was interested in this matter.
Game using IGB Container it contains the model and texture in itself
it mentions a script for 3ds Max 5: [http://community.istaria.com/forum/show ... nd-editing](http://community.istaria.com/forum/showthread.php?7962-AGF-gt-IGB-world-model-viewing-and-editing)
Download their possible via web.archive.org 
I was unable to use this, but maybe it will help in the research format.
## Post #188
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2017-02-15T08:57:57+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from OkCan634
>
> Sorry for bothering.. Do anyone knows how to extract models from IGB formats?
MT3 ISO is already out but I can't do anything with it  
https://youtu.be/5-eGyM-4D7E

I'm sorry if I broke any rules here , I'm new to xentax and this forum m(_ _)m
Thank you in advance.Hello, welcome to the forum. Thanks for posting this, I was not aware that Maxi 3 ISO is now available for download, definitely great news! I will be keeping eye on WMMT4 and WMMT5 (if they ever manage to surface). I know nothing at this point if ripping models from Maxi 3's .IGB is possible or even worth it considering the amount detail available. Waiting for more to come, hopefully we will see WMMT4 available for download...
## Post #189
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2017-02-15T14:57:13+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

I'm quite sure the car model quality is the same between WMMT3 and WMMT5. The car models are in .igb format as "OkCan634" stated. Don't remember about the wangan, but I can take a look if needed.
## Post #190
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2017-02-15T16:12:48+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

WMMT3 and WMMT4/5's cars are the same. IMO, it's just that they have better looking textures and more tuning parts in WMMT4/5 (also new cars). The quality of the track however, were improved in WMMT4/5 (new tracks too like the hakone turnpike/mt. taikan, shibuya, kobe, etc)

Fun fact: Majority of cars from WMMT series were taken to the mobile game "DRIFT SPIRITS" (ドリフトスピリッツ). They released an english version of the game, but it didn't last long due to lack of players. The Japanese version is still going strong however, and i'm still playing it to this second. The game even have the boss cars like Devil Z, Blackbird, Monster Supra, Reina's R32, etc (and also Initial D cars) but those cars are only obtainable via limited time events.
And no, DRIFT SPIRITS doesn't have real world tracks. They do have their own version of Tokyo Expressway though.
## Post #191
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2017-02-15T17:58:44+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

So how can we manage to import those .IGB files?  
Textures are ready to use, in .tga format:



Here's a car sample:
[http://www12.zippyshare.com/v/Lh6NSVDJ/file.html](http://www12.zippyshare.com/v/Lh6NSVDJ/file.html)
## Post #192
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2017-02-22T02:13:47+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from AMG
>
> So how can we manage to import those .IGB files?  
Textures are ready to use, in .tga format:



Here's a car sample:
http://www12.zippyshare.com/v/Lh6NSVDJ/file.html
I haven't looked into the .IGB files, I have been working with the Maxi3 ISO on PC, while it is not easy to get it running, I managed to get the game to load after week of trying:



I'm not sure what the message is saying in japanese, but I'm not getting any response from the keyboard and cannot get past this E20 screen. I need to do more more research, the game might be looking for joystick as I saw that joydev kernel module is required by the game. I managed to force enable the MMX optimization (part of 3DNow!) on my P4 and compile custom kernel to get game running on P4. 

The game itself ('main' ELF 32-bit binary) seems to be targeting an AMD K7 or higher CPU with 3DNow! SIMD extension and NVIDIA GeForce 7 series AGP gprahics card (GeForce 7600 I believe is what game was coded against). I happen to own Pentium 4 machine and GeForce 7800 AGP GPU (the last/fastest AGP card that was released from NVIDIA). Also the game comes statically linked with OpenGL userspace library/API and runs from VT which means there's no need for X11 display server or any helper libs such SDL to setup screen as the game runs straight from the console. I hope this game will be playable as I never had a chance to play the arcade.
## Post #193
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-02-22T05:18:39+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

You really are very lucky, I was trying to do the same, but used VirtualMachine constantly getting kernel error, find PC that time is really hard, all I found it at Nvidia 7600GS   
To successfully run, you graphics card BIOS update?
## Post #194
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2017-02-22T06:23:10+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

In order to run WMMT3 on a PC a similar hardware to Namco System N2 is needed:
- AMD K7/K8 CPU with 3DNow! SIMD extension (Pentium 4 will work as well with kernel hack)
- NVIDIA GeForce 7 Series AGP graphics card, either 7600GS or 7800GS model (no need to flash BIOS)
- IDE motherboard/HDD

Virtual machine won't work, real hardware is needed as the 'main' game binary is tightly coupled with NVIDIA's GL userspace library and kernel driver, if that wasn't enough the game also was statically linked against ADM display server hence no X11 is used nor library such as SDL is needed to create window/sound/video/OpenGL context as the game runs straight from VT (e.g. vt1 console).


Namco System N2 used the following environment from what I found out:
- Debian 3.1 i386 "sarge"
- NVIDIA Linux x86 1.0-8786  driver, not publicly released, can be found at /v337/modules/nvidia.o
- Linux kernel_version 2.4.31 (vermagic 2.4.31-n2 to be precise), kernel was compiled to target i686 AMD K7 CPU

Notes:
- the 'main' game binary depends on shipped nvidia.o graphics driver, if you don't load nvidia.o driver the game will display blank black screen and crash:

```
[Switching to Thread -1212197184 (LWP 11840)]
0x00000000 in ?? ()
(gdb) bt
#0  0x00000000 in ?? ()
#1  0xb7f17fe5 in pthread_once () from /lib/tls/i686/cmov/libpthread.so.0
#2  0x08c9a791 in _nv016851adm ()
#3  0x09afd624 in _nv012929adm ()
#4  0x08c9af40 in admShutdown ()
#5  0xbfe70324 in ?? () 
```


Download and install Debian
- get Debian 3.1r8 i386 "sarge" DVD, CD won't work as the repos haven't been up for years for that version of Debian and you need many dev packages that only come on DVD
- install Debian, no need for GNOME/KDE DE
- create 'arcade' unix user
*obtaining DVD and installing necessary dev packages is left as an exercise to the user*


Compile custom kernel for Namco N2 arcade
- note that the stock kernel in Debian 3.1 will not work and fail to load /v337/modules/nvidia.o graphics driver or run 'main'
- nvidia.o depends on 3DNow! CPU extensions (especially the _mmx_memcpy function in Linux kernel)
- needs following kernel options enabled:
    CONFIG_X86_USE_3DNOW=y
    CONFIG_RWSEM_XCHGADD_ALGORITHM=y
 otherwise you will see missing symbols:

```
    nvidia.o: nvidia.o: unresolved symbol _mmx_memcpy
    nvidia.o: nvidia.o: unresolved symbol rwsem_wake
    nvidia.o: nvidia.o: unresolved symbol rwsem_down_read_failed
```


- get stock .config from [https://archive.debian.net/sarge/kernel ... 4.27-2-386](https://archive.debian.net/sarge/kernel-headers-2.4.27-2-386) and get a hold of /config/686 (or get my P4.config.txt, see attachment)
  # cd /usr/src
  # wget [https://cdn.kernel.org/pub/linux/kernel ... .31.tar.gz](https://cdn.kernel.org/pub/linux/kernel/v2.4/linux-2.4.31.tar.gz)
  # tar -xvzf linux-2.4.31.tar.gz
  # cd linux-2.4.31
  # cp /path/to/config .config
  # make oldconfig
  # make menuconfig
  modify Makefile:4 and set 'EXTRAVERSION = -n2' as nvidia.o driver's vermagic is 2.4.31-n2, if you don't do this nvidia.o won't load
- compile
  # make dep
  # make -j 2
  # make bzImage
  # cp arch/i386/boot/bzImage /boot/vmlinuz-2.4.31-n2
  # make -j2 modules
  # make modules_install
  # depmod -a 2.4.31-n2
  # mkinitrd -o /boot/initrd-2.4.31-n2 2.4.31-n2
  # vim /boot/grub/menu.lst
     and add

```
          root		(hd0,0)
          kernel		/boot/vmlinuz-2.4.31-n2 root=/dev/hda1 ro 
          initrd		/boot/initrd-2.4.31-n2
          savedefault
          boot
```

# reboot


Fix shared libraries
- go to /v337/libso
  # ls -ltSh
  the symbolic links need to be fixed, looks for files with around 25 bytes, remove them and relink them, e.g.:
  # rm -f libz.so.1
  # ln -s libz.so libz.so.1
  repeat this step for other 10 libs

Run the game
# cd /v337
# . .profile $(pwd)
# sh .execrc $(pwd)


At this point the game will load and attempt to test the steering wheel and fail from what I know (see 1m 05s [https://www.youtube.com/watch?v=q5MNkq74XT0](https://www.youtube.com/watch?v=q5MNkq74XT0)). We need to figure out a way to use a keyboard or usb pad and fake them so they appears as JVS / JAMMA input devices to the WMMT3 game. I believe the game is looking for JVS device at /dev/tty0. I believe there's person who already emulated JVS and got past this step, see [https://www.reddit.com/user/dropkickshell](https://www.reddit.com/user/dropkickshell):

> "I have 4 running - emulated the JVS (works with keyboard/controller)"
[P4.config.txt.zip](https://xentaxbackup.github.io/file/12490_P4.config.txt.zip)
## Post #195
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2017-02-22T08:02:40+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Here's an image of Debian 3.1r8 distro with WMMT3 and 2.4.31-n2 Linux kernel I made based on above tutorial:
debian-3.1r8_Linux-2.4.31-n2_WMMT3.7z [https://mega.nz/#!Gk9U2bbS!c_SjgmgSSsOi ... lDU0fe0NiU](https://mega.nz/#!Gk9U2bbS!c_SjgmgSSsOi28wVo6qHE3QlHlkcDUFdblDU0fe0NiU)

Write debian-3.1r8_Linux-2.4.31-n2_WMMT3.img to IDE HDD (minimum size 16GB) with dd or win32DiskImager on Windows
# dd if=debian-3.1r8_Linux-2.4.31-n2_WMMT3.img of=/dev/hdX bs=4M

root password: foobar
Run game:
 # cd /v337/
 # ./prepend-n2-my.pl
 # sh .execrc $(pwd)

To make it work on SATA system and not kernel panic, you will need to chroot from rescue cd/usb and rebuild initrd ramdisk, so e.g. if you're trying this on AMD K8 with nForce4 chipset you would need to include sata-nv.o and run mkinitrd and reboot. This distro img should also be compatible with GeForce 6/7 PCIe cards as seen in [http://http.download.nvidia.com/XFree86 ... dix-a.html](http://http.download.nvidia.com/XFree86/Linux-x86/1.0-8776/README/appendix-a.html)
## Post #196
- Username: OkCan634
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Feb 07, 2017 9:17 pm
- Post datetime: 2017-02-22T16:17:15+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from nfm
>
> Hello, welcome to the forum. Thanks for posting this, I was not aware that Maxi 3 ISO is now available for download, definitely great news! I will be keeping eye on WMMT4 and WMMT5 (if they ever manage to surface). I know nothing at this point if ripping models from Maxi 3's .IGB is possible or even worth it considering the amount detail available. Waiting for more to come, hopefully we will see WMMT4 available for download...
Thank you very much and nice to meet you!  but I'm afraid it will be hard to get those files because all we can do in arcade is plug a capture card or HDMI link to the terminal ._ . By the way.. any plan to work on other tracks for Assetto if they are ripped? I would like to help but sadly.. All I can do is messing about shaders like wet track and porting some cars xD I'm really looking foward to see it , thank you!
## Post #197
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2017-02-25T01:16:59+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from OkCan634
>
> Thank you very much and nice to meet you!  but I'm afraid it will be hard to get those files because all we can do in arcade is plug a capture card or HDMI link to the terminal ._ . By the way.. any plan to work on other tracks for Assetto if they are ripped? I would like to help but sadly.. All I can do is messing about shaders like wet track and porting some cars xD I'm really looking foward to see it , thank you!I would love to play new tracks, I would be probably attempt to make AC tracks if they don't take too much time or nobody else decides to make them. Mt. Akina 2017 for example is very popular multiplayer map and tons of fun.
## Post #198
- Username: OkCan634
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Feb 07, 2017 9:17 pm
- Post datetime: 2017-02-25T01:29:45+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from nfm
>
> I would love to play new tracks, I would be probably attempt to make AC tracks if they don't take too much time or nobody else decides to make them. Mt. Akina 2017 for example is very popular multiplayer map and tons of fun.
Sorry for the false info.. seems like someone managed to get MT4 files from arcade now D: I'm asking him if he could upload the files for me xD 
**EDIT 25/2/2017 : The post owner said : Not for public release yet. Sorry.
[okcan.png](https://xentaxbackup.github.io/file/12523_okcan.png)
## Post #199
- Username: RogeliO
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Feb 26, 2017 12:03 pm
- Post datetime: 2017-02-26T04:07:39+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Obviously why they aren't releasing it yet, they're completing the crack so everyone wouldn't be having more problems.
## Post #200
- Username: RogeliO
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Feb 26, 2017 12:03 pm
- Post datetime: 2017-03-02T12:14:16+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Maximum Tune 4's dump and bios is decrypted. The crack will be released maybe in a few days

[https://wangan3pcblog.wordpress.com/](https://wangan3pcblog.wordpress.com/)
## Post #201
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2017-03-03T21:39:01+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from RogeliO
>
> Maximum Tune 4's dump and bios is decrypted. The crack will be released maybe in a few days

https://wangan3pcblog.wordpress.com/Many thanks, this can easily keep us busy for months, game weighs in at 30GB, 15GB of it is in cars. Seems like 3d data resides in .bin (NDLX files) and textures in .nut (NTLX files), formats are different compared to WMN for PS3. WMMT4 seemed to run on Debian 4.0 etch based distro.
## Post #202
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2017-03-03T22:18:45+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from nfm
>
> Seems like 3d data resides in .bin (NDLX files) and textures in .nut (NTLX files)

Cars 3D data seems having a different format (.mdl) than courses one
## Post #203
- Username: RogeliO
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Feb 26, 2017 12:03 pm
- Post datetime: 2017-03-04T07:00:32+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from nfm
>
> RogeliO wrote:Maximum Tune 4's dump and bios is decrypted. The crack will be released maybe in a few days

https://wangan3pcblog.wordpress.com/Many thanks, this can easily keep us busy for months, game weighs in at 30GB, 15GB of it is in cars. Seems like 3d data resides in .bin (NDLX files) and textures in .nut (NTLX files), formats are different compared to WMN for PS3. WMMT4 seemed to run on Debian 4.0 etch based distro.

No problem.

According to what I've found, the game runs on NAMCO System ES1, the same system used by Dead Heat (WMMT4's cousin).

ES1 have
Intel Q35 Motherboard
Core 2 Duo E8400
1GB DDR2 kit (512mb x2) @800mhz
GeForce 9600 GT 512 GDDR3
160GB HDD from Seagate (ST3160318AS) or Hitachi (HDS721016CLA382)
and the Debian 4.0 that you mentioned.
## Post #204
- Username: RogeliO
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Feb 26, 2017 12:03 pm
- Post datetime: 2017-03-05T13:37:01+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Hi

another update from the author's blog

WMMT5 dongles? Will this work on 4?
## Post #205
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-03-05T18:55:43+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from RogeliO
>
> Hi

another update from the author's blog

WMMT5 dongles? Will this work on 4?

Unfortunately not working, because for each version using your AES 256bit hardware key... Only for WMMT5 it is based on Windows, WMMT4 on Linux.
It can only help if you make a dump of this key, and have a copy of WMMT 5


Guys of all cars WMMT 3/4 available in DriftSpirits which is made in Unity. Interesting only track models of the WMMT4.

Screens:
AE86 in WMMT4 


AE86 in DriftSpirits/DORISUPI (in Japan)
## Post #206
- Username: nosfornos
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Dec 21, 2011 4:16 pm
- Post datetime: 2017-03-05T22:44:44+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from blackracer
>
> RogeliO wrote:
Guys of all cars WMMT 3/4 available in DriftSpirits which is made in Unity. Interesting only track models of the WMMT4.
[/img]

Only Eunos Cosmo and Celsior didn't appear in DriftSpirits...
## Post #207
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2017-03-06T13:20:48+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Also the Pajero Evolution, the Mitsubishi Starion and I think some other cars too.
## Post #208
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2017-03-06T13:58:52+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Don't forget cars like the Nissan Fairlady Z (Z33), Mercedes Benz SLK 55 (is this the right one? I'm bad with mercedes cars), BMW M6, Nissan Stagea Autech Version, Subaru Levorg, Nissan Fairlady Z (Z31), Nissan Skyline RS-X (R30) and so on... Just look at igcd.net and do a comparison. Lots of cars are missing from Drift Spirits (and texture resolution were downgraded)
## Post #209
- Username: RogeliO
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Feb 26, 2017 12:03 pm
- Post datetime: 2017-03-07T00:43:27+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Hinz replies to me and said the dongles also work on WMMT4 as well as 5,5DX and maybe 5DX+

Namco did a lazy thing of using the same dongle for international machines (YES INTERNATIONAL MACHINES USE SYSTEM ES1 and the japanese variant uses ES3).
## Post #210
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-03-07T09:59:47+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from RogeliO
>
> Hinz replies to me and said the dongles also work on WMMT4 as well as 5,5DX and maybe 5DX+

Namco did a lazy thing of using the same dongle for international machines (YES INTERNATIONAL MACHINES USE SYSTEM ES1 and the japanese variant uses ES3).

This is very strange, the key structure can be the same but the encryption method can hardly be the same, I wonder what the final will be
## Post #211
- Username: OkCan634
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Feb 07, 2017 9:17 pm
- Post datetime: 2017-03-07T16:02:53+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from blackracer
>
> 

This is very strange, the key structure can be the same but the encryption method can hardly be the same, I wonder what the final will be
I also play 5DX and You know what's the difference between 4,5,5DX,5DX+ ? It's pretty funny that only VS screen , new tacho , Extreme mode , new cars , new course and little bit about cars' feeling xD So.. 5DX+ is just a rebadged 4DX+ xDD
## Post #212
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-03-07T17:37:42+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Unfortunately, I played very little time in the WMMT4 to see the difference   
It is possible to find a WMMT5 dump?
## Post #213
- Username: RogeliO
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Feb 26, 2017 12:03 pm
- Post datetime: 2017-03-08T01:32:09+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from blackracer
>
> RogeliO wrote:Hinz replies to me and said the dongles also work on WMMT4 as well as 5,5DX and maybe 5DX+

Namco did a lazy thing of using the same dongle for international machines (YES INTERNATIONAL MACHINES USE SYSTEM ES1 and the japanese variant uses ES3).

This is very strange, the key structure can be the same but the encryption method can hardly be the same, I wonder what the final will be

It's possible since Hinz got the International variant of the Dongle which uses ES1 and WMMT4 and all the other International WMMT5, 5DX use ES1 too.
## Post #214
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2017-03-08T02:55:40+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from blackracer
>
> Unfortunately, I played very little time in the WMMT4 to see the difference   
It is possible to find a WMMT5 dump?
If a place with international version of WMMT5 or 5DX permits to plug something other than recording devices, then there could be a possibility. Here in Indonesia, even going to the back side of an arcade machine is forbidden imo (we have the international WMMT5DX machines, but restricted to play in Indonesian server only. Sometimes we do find Hong Kong players).
## Post #215
- Username: RogeliO
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Feb 26, 2017 12:03 pm
- Post datetime: 2017-03-09T14:01:15+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

WMMT4 is confirmed working

All we need to do now is wait for the crack to be released in public
## Post #216
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2017-03-09T15:59:39+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from RogeliO
>
> WMMT4 is confirmed working

All we need to do now is wait for the crack to be released in public
Just saw the post on the blog. I'm hoping this is 100% legit and will be released soon enough.
## Post #217
- Username: OkCan634
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Feb 07, 2017 9:17 pm
- Post datetime: 2017-03-10T04:06:49+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from blackracer
>
> Unfortunately, I played very little time in the WMMT4 to see the difference   
It is possible to find a WMMT5 dump?
Unfortunately not for now  As REDZOEU said.. we're only allowed to plug a capture card or HDMI. It would be good if staffs allow me to lend a dongle and HDD for 5DX xD I really want to practice TA on Shibuya.
## Post #218
- Username: SpulX
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 26, 2017 9:45 pm
- Post datetime: 2017-03-26T18:07:30+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Can someone get me the ae86's from latest wangan midnight or make a proper tutorial how to cause i am new to this and i need some nice bodykits.
## Post #219
- Username: Alv22
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 26, 2017 8:24 pm
- Post datetime: 2017-04-26T12:29:11+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

hi there, I'm new to the forum here..
so, I have downloaded the Maxi4 data and I'm looking the car logo data that stored in .nut files..
I see about file is stored in NTLX files..
any info about opening that files?
thanks in advance..
## Post #220
- Username: HiyajouMaho
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 01, 2017 11:37 am
- Post datetime: 2017-05-01T03:45:38+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

This madman has the entire thing but won't upload it due to, allegadly (according to the comments section) the large filesize.

[https://www.youtube.com/watch?v=Y2Z8sNBncA4](https://www.youtube.com/watch?v=Y2Z8sNBncA4)&
## Post #221
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2017-08-19T01:31:34+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

As promised I'm releasing the Minato Mirai area (could have been sooner if it hadn't been for my 3 jobs). It's still a mess but better than nothing. [Link](http://www.mediafire.com/file/g97p04o20ag1chr/minato.rar)
Textures were named randomly.

GTAIV quick conversion:
[https://www.youtube.com/watch?v=D4DtFIKlSS4](https://www.youtube.com/watch?v=D4DtFIKlSS4)

Minato Mirai is compatible with WMPS3 map but must be scaled down a lot.

Do whatever you want with it but bear in mind I did this with my heart.
## Post #222
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2017-08-19T05:54:13+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Watched the video. I'm amazed at how the finished map looks like! Except that the white lines on the middle lf the road and the exit kanji sign on the road having collision (which made the r33 go slightly upward).

But, hey! It's a great work   
Can you tell me how you managed to rip and position the map? You said on previous posts that you watched tutorials on YouTube. Maybe if you can even take such a big map from SBZOC, i can even get maps from Initial D Street Stage too with the same method?
## Post #223
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2017-08-19T12:23:52+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from REDZOEU
>
> Watched the video. I'm amazed at how the finished map looks like! Except that the white lines on the middle lf the road and the exit kanji sign on the road having collision (which made the r33 go slightly upward).
Thanks  It's not even close to being finished though. Normals are pretty screwed up and I would want to add lights to lamp poles and traffic but don't know how... The collisions are not a problem I just didn't feel like messing around with them.

> Reply from REDZOEU
>
> Can you tell me how you managed to rip and position the map? You said on previous posts that you watched tutorials on YouTube. Maybe if you can even take such a big map from SBZOC, i can even get maps from Initial D Street Stage too with the same method?
I used an older version of ninjaripper on ppsspp on WinXP(x86), drove through the map and captured every frame. The best thing is that the pieces are already placed and rotated the proper way. Each frame contained hundreds of pieces and missing geometry so i had to repair, sort them out, name, assign and merge textures... 

Took a shot at Street Stage:

Anything's possible if you have the will and patience.
You can emulate Initial D Arcade Stage 6 AA on PC though and give a shot at that instead...

Now to Yaesu, Shibuya, Shinjuku, Osaka and Nagoya...
## Post #224
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2017-08-19T18:14:19+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from Takukun
>
> 
I used an older version of ninjaripper on ppsspp on WinXP(x86), drove through the map and captured every frame. The best thing is that the pieces are already placed and rotated the proper way. Each frame contained hundreds of pieces and missing geometry so i had to repair, sort them out, name, assign and merge textures...
Specifically what version is it?

> Reply from Takukun
>
> 
You can emulate Initial D Arcade Stage 6 AA on PC though and give a shot at that instead...
Tried it. Didn't work. Maybe because i'm using a newer Ninja Ripper, or the emulator uses OpenGL, idk. Might make a new thread to ask for help to find out how to extract the archives and get track & car models.
## Post #225
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2017-08-20T11:13:50+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from REDZOEU
>
> Specifically what version is it?
I'm not 100% sure because i get different info in the help and exe files but i think it's 1.1.4. The version I used on Street stage was the latest though (1.6.4).
## Post #226
- Username: Hinz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 22, 2017 4:29 am
- Post datetime: 2017-08-21T20:32:07+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Hi, I'm the Hinz of Wangan 3 Forum. TeknoParrot loader will load ES3 games in the future ([https://www.twitch.tv/videos/166199446](https://www.twitch.tv/videos/166199446)). We need your help to get the dump of WMMT5 Japanese version (because ES3) to put on the loader and play.
## Post #227
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2017-08-29T08:12:37+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from Hinz
>
> Hi, I'm the Hinz of Wangan 3 Forum. TeknoParrot loader will load ES3 games in the future (https://www.twitch.tv/videos/166199446). We need your help to get the dump of WMMT5 Japanese version (because ES3) to put on the loader and play.
I can't help, but i guess other people can (and hopefully they're reading this forum and this post too). My country has WMMT5, but it's the Indonesian exclusive version, and we don't have access to plug or do something behind the game cabinets (not even a recorder for the game).
## Post #228
- Username: Hinz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 22, 2017 4:29 am
- Post datetime: 2017-08-29T14:47:42+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from REDZOEU
>
> Hinz wrote:Hi, I'm the Hinz of Wangan 3 Forum. TeknoParrot loader will load ES3 games in the future (https://www.twitch.tv/videos/166199446). We need your help to get the dump of WMMT5 Japanese version (because ES3) to put on the loader and play.
I can't help, but i guess other people can (and hopefully they're reading this forum and this post too). My country has WMMT5, but it's the Indonesian exclusive version, and we don't have access to plug or do something behind the game cabinets (not even a recorder for the game).

Thanks. Probably we got some working dump here, but we need to do A LOT work:
[http://imgur.com/a/msGBv](http://imgur.com/a/msGBv)
## Post #229
- Username: Alv22
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 26, 2017 8:24 pm
- Post datetime: 2017-09-04T14:13:13+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

just managed to borrow 5DX USB Update..
so, I just finished trying update a HDD which contains WM4 data..
I formated a HDD drive, make a partition with size 30 GB and copy WM4 data but I skip the cars data so only car folder inside the data folder..
and I run the USB updater which contains a custom Linux ES1 Maintenance Image..
keyboard is working like the switch in WM machine and the enter button is like enter in keyboard..
after the update success, I see the files inside the HDD and it makes a file named old series and update
since I try to plug the USB on normal Windows running, it wants format the FD before using it..
the USB itself is 16 GB which read and write protected, using 11 GB and 3 GB free space left on the USB..
since I think the update is 11 GB which contains all the data, but I found nothing new except that 2 files..
now, I focus to open the mdl and tex data which I would like to take the car logo data and see other things
BGM itself were a RAW and I successfully opens it with Audacity..

here are the image that I documented during update of WM4 to 5DX

[http://imgbox.com/Xs33PO9x](http://imgbox.com/Xs33PO9x)
[http://imgbox.com/cdOfbf1w](http://imgbox.com/cdOfbf1w)
[http://imgbox.com/SjUOKWSf](http://imgbox.com/SjUOKWSf)
[http://imgbox.com/WV4cIZFS](http://imgbox.com/WV4cIZFS)
## Post #230
- Username: zezopro8888
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Sep 06, 2017 10:50 am
- Post datetime: 2017-09-06T02:59:19+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

I found a video shuto expressway for assetto corsa has been completed but unfortunately it will not be shared

[https://www.youtube.com/watch?v=C9ZLzpBThVk](https://www.youtube.com/watch?v=C9ZLzpBThVk)
## Post #231
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2017-09-06T06:09:24+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from zezopro8888
>
> I found a video shuto expressway for assetto corsa has been completed but unfortunately it will not be shared

https://www.youtube.com/watch?v=C9ZLzpBThVk

Yeah, too bad they're hogging it up to themselves.
## Post #232
- Username: RemcoJZA80
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Feb 22, 2016 9:31 pm
- Post datetime: 2017-09-06T11:39:18+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

I've converted the whole shuto too, I have reworked the scale, tex etc etc which are not shown in the video.
Original plan was to release it, but because the AC engine cant handle high poly objects as collision, the game refuses to run properly without lagging in multi-player.

[https://youtu.be/8zWu_OoBNvQ](https://youtu.be/8zWu_OoBNvQ)
## Post #233
- Username: zezopro8888
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Sep 06, 2017 10:50 am
- Post datetime: 2017-09-06T13:02:36+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from RemcoJZA80
>
> I've converted the whole shuto too, I have reworked the scale, tex etc etc which are not shown in the video.
Original plan was to release it, but because the AC engine cant handle high poly objects as collision, the game refuses to run properly without lagging in multi-player.

https://youtu.be/8zWu_OoBNvQ

Please give me link download I really want to embark on this project to have a complete map
## Post #234
- Username: RemcoJZA80
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Feb 22, 2016 9:31 pm
- Post datetime: 2017-09-06T16:22:51+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Not going to happen for now, nowhere near finished.
## Post #235
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2017-09-06T17:07:14+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from RemcoJZA80
>
> I've converted the whole shuto too, I have reworked the scale, tex etc etc which are not shown in the video.
Original plan was to release it, but because the AC engine cant handle high poly objects as collision, the game refuses to run properly without lagging in multi-player.

https://youtu.be/8zWu_OoBNvQ
Whoa, nice man! Can't wait for it to be finished!
In my opinion, i guess you should split the shuto parts, rather than making it one whole giant map, since (cmiiw) AC probably load the whole map in one go.
## Post #236
- Username: RemcoJZA80
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Feb 22, 2016 9:31 pm
- Post datetime: 2017-09-07T08:50:51+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Nah, I've set it so only models within the 500 meter range get loaded
## Post #237
- Username: RogeliO
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Feb 26, 2017 12:03 pm
- Post datetime: 2017-09-26T11:26:50+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Someone from Indonesia got WMMT3 running with a PC. First test ended up with an error on the part where you choose whether to play with a card or not and the second test ended up being stuck in the loading screen after you get past the same part in the first test.

[https://www.youtube.com/watch?v=V5aF3KkHhQI&t=58s](https://www.youtube.com/watch?v=V5aF3KkHhQI&t=58s)
## Post #238
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2017-09-26T16:20:31+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from RogeliO
>
> Someone from Indonesia got WMMT3 running with a PC. First test ended up with an error on the part where you choose whether to play with a card or not and the second test ended up being stuck in the loading screen after you get past the same part in the first test.

https://www.youtube.com/watch?v=V5aF3KkHhQI&t=58s
Yeah i saw that video last week when i was browsing youtube for news on maxi tune emulation. Would be great if we can run it in windows with some kind of emulator/loader like TeknoLoader...
## Post #239
- Username: fryzz7
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 28, 2017 8:01 pm
- Post datetime: 2017-09-28T16:57:30+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

([https://www.youtube.com/watch?v=C9ZLzpBThVk](https://www.youtube.com/watch?v=C9ZLzpBThVk))

Does anyone know this person?  
When they release this masterpiece?
## Post #240
- Username: robertgt
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Oct 06, 2017 11:17 am
- Post datetime: 2017-10-06T03:35:29+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Hello all. Just found out about this beautiful track and this forum.
I have to congratulate you all for your efforts. It will be a dream come true to include the other sections for assetto.

regarding previous post: I also discovered same person on youtube. Unfortunately it seems that new section is not available for download (read the comments in following video).
[https://www.youtube.com/watch?v=7I4gBm4BSZ4](https://www.youtube.com/watch?v=7I4gBm4BSZ4)

I also see this other person: [https://www.youtube.com/watch?v=CEVy7CjFi3o](https://www.youtube.com/watch?v=CEVy7CjFi3o)
Maybe one of the modders from japanese translation in title...
There should be a group of people working on that version. If only we could find out more to see if they'd be willing to cooperate. cheers.
## Post #241
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2017-10-16T12:00:24+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

If you can do that it would be awesome.
[A guy already implemented my Minato Mirai area in his complete Shuto Expwy in AC.](https://www.youtube.com/watch?v=MV5dOZQem34) I tried to talk to him and he said he aims for a complete map but he did not specify he would release it. There are also a bunch of other guys seemingly knowing each other and making these Wangan mods but are not talking to anyone who's not Japanese...

There's [this other group of AC modders](https://www.facebook.com/groups/gentlemindperformance/permalink/605130986359524/) who seem to have had contact with them but were unsuccessful.

I think that everyone is on its own now...
## Post #242
- Username: vladKraft
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Nov 18, 2017 11:29 pm
- Post datetime: 2017-11-19T17:10:50+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Hi, can you help to convert WMMT4 model? Games have one encoding but your script does not work. I tried to do this, but my knowledge is not enough.  
Dump of game: [https://mega.nz/#!JMRGSYqD!Ai4oX87dfR6_ ... tpB3xikREY](https://mega.nz/#!JMRGSYqD!Ai4oX87dfR6_jXi_jgBMBZQh3RUdMmX2PtpB3xikREY)
Car which i want to extract: [https://drive.google.com/open?id=1BsqfL ... XttJMJW5SR](https://drive.google.com/open?id=1BsqfLc_5hVrMpkovalJd-iXttJMJW5SR)
## Post #243
- Username: zezopro8888
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Sep 06, 2017 10:50 am
- Post datetime: 2017-12-07T10:49:09+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Full track shuto complete link download, thank acpursuit.com

[http://acpursuit.altervista.org/the-new ... d-version/](http://acpursuit.altervista.org/the-new-shuto-track-huge-extended-version/)

It has been completed but still a lot of bugs, looking forward to more people can help them
## Post #244
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2017-12-07T11:07:36+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

This is BIG news. I'll test the map once i have free time from college. We could really help them by exploring the whole map and finding bugs around the map.
## Post #245
- Username: isamu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jan 13, 2018 2:10 am
- Post datetime: 2018-01-12T18:12:48+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Hi guys 

Looking forward to the full completed version of Shuto C1.

Shout out to L3g3nd1 for pointing me here.
## Post #246
- Username: jzs161aristo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jan 20, 2018 12:44 pm
- Post datetime: 2018-01-20T04:55:57+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

It seems they had gone for something on their own and moved the track away after December (link may still work, but disappeared).

Had driven a few times on the full track, didn't have much problem except ran into the wrong line and fell off...

Except I couldn't have other (computer) drivers tag along... I wonder if anyone care to fix the start boxes and make a start/finish line, e.g. on the Rainbow Bridge? I mean, I can make the AI lines on our own (so we can mix and match C1, Circular, Wangan line, Yokohama, etc clockwise/counterclockwise in a lap) but I was just looking for a way so I can do a race at the wangan circuit, much bigger than C1.

A la GT sports in AC, if you must say.
## Post #247
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2018-01-20T12:47:42+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from jzs161aristo
>
> It seems they had gone for something on their own and moved the track away after December (link may still work, but disappeared).

Had driven a few times on the full track, didn't have much problem except ran into the wrong line and fell off...

Except I couldn't have other (computer) drivers tag along... I wonder if anyone care to fix the start boxes and make a start/finish line, e.g. on the Rainbow Bridge? I mean, I can make the AI lines on our own (so we can mix and match C1, Circular, Wangan line, Yokohama, etc clockwise/counterclockwise in a lap) but I was just looking for a way so I can do a race at the wangan circuit, much bigger than C1.

A la GT sports in AC, if you must say.

I still have the very same files on me. I can upload it for you, but it'll take a long time since my internet speed is slow. And i'll upload it once i'm done with my exams, if you don't mind.
## Post #248
- Username: jzs161aristo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jan 20, 2018 12:44 pm
- Post datetime: 2018-01-20T13:30:32+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from REDZOEU
>
> 
I still have the very same files on me. I can upload it for you, but it'll take a long time since my internet speed is slow. And i'll upload it once i'm done with my exams, if you don't mind.
I have the files too, just had no idea on how to edit the track with zero knowledge on 3D studio, even with ksEditor. :/ In fact I should have found the start boxes (in ksEditor, with objects having names of START*), but don't know how to move them to other places on the track.

Should be getting off topic... hope I'm still not far away from here.
## Post #249
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2018-01-20T17:55:08+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from jzs161aristo
>
> REDZOEU wrote:
I still have the very same files on me. I can upload it for you, but it'll take a long time since my internet speed is slow. And i'll upload it once i'm done with my exams, if you don't mind.

I have the files too, just had no idea on how to edit the track with zero knowledge on 3D studio, even with ksEditor. :/ In fact I should have found the start boxes (in ksEditor, with objects having names of START*), but don't know how to move them to other places on the track.

Should be getting off topic... hope I'm still not far away from here.

Ahhh... Seems i misunderstood. You might wanna ask someone experienced for that, or just look at some other map mods for references. I have zero knowledge with track editing for ac too
## Post #250
- Username: jzs161aristo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jan 20, 2018 12:44 pm
- Post datetime: 2018-01-21T13:51:29+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Never mind, just wanted to be lazy  

After some fitting, 3dsimed looks simple enough to just fit my need of moving boxes here and there (20 days free trial though). Now I have a finish line, and seems I can start recording AI line now.

Did tried Blender, but I couldn't do the same thing easily (like finding track objects after opening, to begin with). As said, I'm just a holiday driver...

May put the start boxes later when I have time. No easy task though, and I need to learn how to rotate the start boxes so the cars won't drive in the wrong direction.

But I thought that carpark is too small as pit (think a race of 20 or more, and when the drivers go in for refuel), so I need to switch off fuel consumption and tire wearing altogether. You'll want to use the wangan straight if you want a proper pitlane, then some tent models, trucks, pit marks, blablabla... which I won't have the power of doing them. YMMV
## Post #251
- Username: Dennissaurus
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Aug 12, 2014 11:16 pm
- Post datetime: 2018-05-03T19:53:37+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Hi all... been reading through for days now, and seem to understand well, got lots of tools and cues on how to use them also, so big thanks to all for that.. BUT

WANGAN MIDNIGHT 5 ~ Any info? i got just 1 car i want from the whole game, i have the .MDL and .TEX files for it. but cannot open them/dump them hoping some of you lovely amazing people can help??
## Post #252
- Username: Dennissaurus
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Aug 12, 2014 11:16 pm
- Post datetime: 2018-05-03T20:00:13+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

[https://www.dropbox.com/home?preview=WM ... lution.rar](https://www.dropbox.com/home?preview=WMMT5+Pajero+Evolution.rar)

The .MDL and .TEX files 

please can the models be converted to DAE. or .OBJ please and textures to whatever is convenient. i dont need alpha data. the model is most important.

many thanks in advance for this
## Post #253
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2018-05-04T04:19:31+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Since no one capable has replied to your request, can i at least ask what car model do you want from the game?
## Post #254
- Username: Dennissaurus
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Aug 12, 2014 11:16 pm
- Post datetime: 2018-05-04T08:29:02+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

So, i read the 17 pages, and im still clueless. How can i extract just 1 car from Wangan Midnight 5? 

i have the .mdl and .tex files but so far, nothing is working for me. I assume (totally  ) i missed something and my lack of knowledge is destroying my chances, 
Can any of you gents point me in the direction of some tasty info/tutorial/tools i can get a hand on please? 

respect and thanks in advance
## Post #255
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2018-05-04T17:23:01+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from Dennissaurus
>
> So, i read the 17 pages, and im still clueless. How can i extract just 1 car from Wangan Midnight 5? 

i have the .mdl and .tex files but so far, nothing is working for me. I assume (totally  ) i missed something and my lack of knowledge is destroying my chances, 
Can any of you gents point me in the direction of some tasty info/tutorial/tools i can get a hand on please? 

respect and thanks in advance

Currently none of us tried to extract cars from that game. 
This topic is created mainly to do research on files for Wangan Midnight PS3, thus making the models from the game (both cars and tracks) loadable in 3d softwares like 3dsmax for example. You should know that almost all cars from WMMT4-5 exists in this mobile game called Drift Spirits (exactly the same model with lower res texture), so give the Drift Spirits page in IGCD (Internet Game Cars Database) a try to look for the car you want. Some Drift Spirits car models are already uploaded to Gamemodels website, since extracting them is a pain in the A.
## Post #256
- Username: Dennissaurus
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Aug 12, 2014 11:16 pm
- Post datetime: 2018-05-06T16:35:19+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

THANKS! I will check igcd, this was the first game i seen a Mitsubishi Pajero evolution... so hunting badly to find it  

[https://jalopnik.com/meet-the-mitsubish ... 1704009601](https://jalopnik.com/meet-the-mitsubishi-pajero-evo-the-last-forgotten-homo-1704009601)
## Post #257
- Username: gizfab
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 13, 2018 1:39 am
- Post datetime: 2018-05-12T17:42:19+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Hello Guys. Been a lurker for a whilst.

has anyone managed to Extra the Osaka Line from the WMMT Files?
## Post #258
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2018-05-15T06:16:04+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

The only successful export I managed, was via Ninjaripper, but it crashes before exporting all the models, so lots of things are missing from the map.
## Post #259
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2018-05-15T06:25:23+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from Takukun
>
> The only successful export I managed, was via Ninjaripper, but it crashes before exporting all the models, so lots of things are missing from the map.
Does that mean WMMT5 uses DirectX? If yes, which DirectX? 9 or 10 or 11?
## Post #260
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2018-05-16T11:48:26+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Actually I don't know since I used intruder and didn't bother to mess around with the settings.

Might drop a pic when I get my main pc up and working again.
## Post #261
- Username: trawa
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jun 01, 2018 11:32 am
- Post datetime: 2018-06-01T03:43:39+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from zezopro8888
>
> I found a video shuto expressway for assetto corsa has been completed but unfortunately it will not be shared

https://www.youtube.com/watch?v=C9ZLzpBThVk

> Reply from Takukun
>
> If you can do that it would be awesome.
A guy already implemented my Minato Mirai area in his complete Shuto Expwy in AC. I tried to talk to him and he said he aims for a complete map but he did not specify he would release it. There are also a bunch of other guys seemingly knowing each other and making these Wangan mods but are not talking to anyone who's not Japanese...

There's this other group of AC modders who seem to have had contact with them but were unsuccessful.

I think that everyone is on its own now...

I got my hands on the (almost) finished full layout, managed to scale the Minato Mirai area correctly and get it in-game. However I'm not advanced enough 3DS and KSeditor wise to finish it on my own. 
It's driveable but that's about it honestly, looks like ass, wrong textures, no horizon maps etc.

[https://i.imgur.com/pCKd0NT.png](https://i.imgur.com/pCKd0NT.png)
[https://i.imgur.com/nqBL0fz.jpg](https://i.imgur.com/nqBL0fz.jpg)
[https://i.imgur.com/NbntxfE.png](https://i.imgur.com/NbntxfE.png)

AFAIK these guys sign as "Wangan Workshop", both their cars and tracks are top quality but they very rarely leak or release something.
## Post #262
- Username: trawa
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jun 01, 2018 11:32 am
- Post datetime: 2018-06-30T18:41:41+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

sorry for double posting; cant find the bump thread button.  

[https://www.youtube.com/watch?v=5S-EVuP4Y9g](https://www.youtube.com/watch?v=5S-EVuP4Y9g)
overhauled it a little but i'm not good enough in 3DS Max or KSEditor to finish it. 
MM files (scaled, aligned, FBX + TEX + KN5)
[https://mega.nz/#!6ggGhSRB!AJ01aT-YPU4a ... B6i-KfwxWs](https://mega.nz/#!6ggGhSRB!AJ01aT-YPU4aHyacExkFw8Vk46MFlcqOdB6i-KfwxWs)
feel free to use them.

full Tokio-to-Yokohama loop
[https://drive.google.com/file/d/1uiE_ki ... 9cHu7/view](https://drive.google.com/file/d/1uiE_ki-RIhfSF6gEY_d0ObR3Jnb9cHu7/view)

add the .kn5 file to ww_metropolitan folder and add 

```
FILE=ww_metropolitan_expressway_part9.kn5
POSITION=0,0,0
ROTATION=0,0,0
```

in models_ww_metropolitan_expressway.ini
## Post #263
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2018-07-01T04:13:34+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Great work man! The track looks great   
I'll test it once i'm done with my exams.
By watching the video, i guess some part of the road is still rough for AC cars to use, since parts of the road in the video felt bumpy.
## Post #264
- Username: isamu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jan 13, 2018 2:10 am
- Post datetime: 2018-07-01T05:46:07+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from trawa
>
> sorry for double posting; cant find the bump thread button.  

https://www.youtube.com/watch?v=5S-EVuP4Y9g
overhauled it a little but i'm not good enough in 3DS Max or KSEditor to finish it. 
MM files (scaled, aligned, FBX + TEX + KN5)
https://mega.nz/#!6ggGhSRB!AJ01aT-YPU4a ... B6i-KfwxWs
feel free to use them.

full Tokio-to-Yokohama loop
https://drive.google.com/file/d/1uiE_ki ... 9cHu7/view

add the .kn5 file to ww_metropolitan folder and add 
Code: Select all[MODEL_9]
FILE=ww_metropolitan_expressway_part9.kn5
POSITION=0,0,0
ROTATION=0,0,0
in models_ww_metropolitan_expressway.ini

That's looks good Trawa. Are you working together with NigelAE86 on this track? How many people are working on Shuto altogether to your knowledge? I thought he was the sole person developing this track. 

Anyway, in the meantime, if you guys like Shuto and want to race or hotlap it with other Shuto fans online, I encourage you to join us on the ACPursuit 24/7 Shuto server. Hyena the Boss is the server admin. The version of the track is the shorter C1 Loop version, but it's still quite long and driving it especially online with others is incredibly fun! Furthermore, if you have a VR headset you really, and I mean ***R-E-A-L-L-Y** need to drive the Shuto track in VR!!!!!!!!!!!!!!!!!!!!!!!!!!! There is nothing.....and I mean NOTHING as immersive and orgasmic as driving this track in VR, particularly with the C1 Midnight mod!!!!!!!!!! It is a rapturous experience! 

The server is packed with a good 8-16 people at all times and we all encourage you to join us. You can grab the track, and all the necessary content from the ACP webpage:

[http://acpmoneysystem.altervista.org/ne ... sta.org%2F](http://acpmoneysystem.altervista.org/new-how-it-works/?redirect_to=http%3A%2F%2Facpmoneysystem.altervista.org%2F)

Facebook page:

[https://www.facebook.com/groups/assettocorsapursuit/](https://www.facebook.com/groups/assettocorsapursuit/)
## Post #265
- Username: trawa
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jun 01, 2018 11:32 am
- Post datetime: 2018-07-02T17:12:01+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from isamu
>
> 
That's looks good Trawa. Are you working together with NigelAE86 on this track? How many people are working on Shuto altogether to your knowledge? I thought he was the sole person developing this track.
As far as I know aside from Nigel and Remco I'm the only one that got Minato Mirai in-game and driveable. Maybe Mike Rudland but not sure.
No, we're not working together. He keeps his stuff private and I heard that he/his modding group refuse to contact with anyone not speaking japanese.

> Reply from REDZOEU
>
> Great work man! The track looks great   
I'll test it once i'm done with my exams.
By watching the video, i guess some part of the road is still rough for AC cars to use, since parts of the road in the video felt bumpy.

It's due to sheer size of the map. In Minato Mirai area you're so far from the origin (0,0,0) of the map that physics start to get really inaccurate. The further you are, the less precise are calculations. (see: geometry and force feedback loose/shaking)
Also this being a rip with low poly road mesh doesn't help either.  It's possible that using high poly road mesh for physics would help but it might  kill the performance due to the size.
## Post #266
- Username: isamu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jan 13, 2018 2:10 am
- Post datetime: 2018-07-03T00:30:18+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from trawa
>
> isamu wrote:
That's looks good Trawa. Are you working together with NigelAE86 on this track? How many people are working on Shuto altogether to your knowledge? I thought he was the sole person developing this track. 

As far as I know aside from Nigel and Remco I'm the only one that got Minato Mirai in-game and driveable. Maybe Mike Rudland but not sure.
No, we're not working together. He keeps his stuff private and I heard that he/his modding group refuse to contact with anyone not speaking japanese.

Yeah I figured that was the case so thanks for confirming that. It's too bad because the progress he's made so far is incredible.
## Post #267
- Username: trawa
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jun 01, 2018 11:32 am
- Post datetime: 2018-07-03T19:12:14+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

[https://www.youtube.com/watch?v=cRke3myd520](https://www.youtube.com/watch?v=cRke3myd520)

still need to replace some wrong/low res/placeholder textures, make proper horizon maps/track surroundings and rework shaders from scratch. 
also, UV mapping. if you know how to do it properly please share some knowledge.

standalone KN5 (ver. 07-04-2018)

NEW 07-04-2018 v2
[https://www1.zippyshare.com/v/7D5UoC3p/file.html](https://www1.zippyshare.com/v/7D5UoC3p/file.html)

also, a request: if you have access to WMMT files, can you try and extract Daikoku Futo area in best possible LOD? would be really cool to have pit area in the docks
[https://www.google.pl/maps/place/Daikok ... 39.6856297](https://www.google.pl/maps/place/Daikokufuto,+Tsurumi+Ward,+Jokohama,+Prefektura+Kanagawa+230-0054,+Japonia/@35.4586257,139.679156,4019m/data=!3m1!1e3!4m5!3m4!1s0x60185d62f5e54841:0xfe39728eacb4b8d4!8m2!3d35.4604203!4d139.6856297)

EDIT: Thanks to x4fab's hard work dynamic shaders now support track lights. You know what that means...
[https://i.redd.it/3r1c41axle811.jpg](https://i.redd.it/3r1c41axle811.jpg)
## Post #268
- Username: Pentaaa
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 17, 2018 8:44 am
- Post datetime: 2018-07-17T00:51:16+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> As far as I know aside from Nigel and Remco I'm the only one that got Minato Mirai in-game and driveable. Maybe Mike Rudland but not sure.
>
> No, we're not working together. He keeps his stuff private and I heard that he/his modding group refuse to contact with anyone not speaking japanese.

Hello there, 
Regarding that, a friend of mine and i haven been working on a full map for ages aswell. Thanks to you linking Minato here, we managed to get it imported and fully working. It works, but textures need to be fixed. We are in the process of updating Tatsumi PA to the current layout, and will then focus on fixing Minato, and hopefully implement Daikoku PA after that. 
So a thank you from us for sharing Minato with this forum!
## Post #269
- Username: isamu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jan 13, 2018 2:10 am
- Post datetime: 2018-07-17T21:45:06+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from Pentaaa
>
> As far as I know aside from Nigel and Remco I'm the only one that got Minato Mirai in-game and driveable. Maybe Mike Rudland but not sure.
No, we're not working together. He keeps his stuff private and I heard that he/his modding group refuse to contact with anyone not speaking japanese.


Hello there, 
Regarding that, a friend of mine and i haven been working on a full map for ages as well. Thanks to you linking Minato here, we managed to get it imported and fully working. It works, but textures need to be fixed. We are in the process of updating Tatsumi PA to the current layout, and will then focus on fixing Minato, and hopefully implement Daikoku PA after that. 
So a thank you from us for sharing Minato with this forum!

Hi Pentaaaaa. That is great news! You and your friend have my full support!!!!!! Wishing you the best of luck my friend, and thanks for working on Shuto. Do you expect your version to compare favorably with NigelAE's? How will your version differ from his? Do you have any WIP videos you can share with us?
## Post #270
- Username: Pentaaa
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 17, 2018 8:44 am
- Post datetime: 2018-07-18T11:21:56+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Hi Pentaaaaa. That is great news! You and your friend have my full support!!!!!! Wishing you the best of luck my friend, and thanks for working on Shuto. Do you expect your version to compare favorably with NigelAE's? How will your version differ from his? Do you have any WIP videos you can share with us?

Thank you for your kind words. Ours isn't as refined as his, atleast yet. We haven't done really much texuture work, except replacing bad textures, and the road mesh is still the old one too. As i said, ours will definitely have the new version of Tatsumi PA, and hopefully a somewhat usable Daikoku PA. I'll post two videos below for you guys to look at.

Tatsumi PA
[https://i.imgur.com/zJ1JY42.png](https://i.imgur.com/zJ1JY42.png)
[https://i.imgur.com/kAbjwNT.png](https://i.imgur.com/kAbjwNT.png)

Fukagawa Daiba Route [https://www.youtube.com/watch?v=683BrsJuiak](https://www.youtube.com/watch?v=683BrsJuiak)
Minato Test [https://www.youtube.com/watch?v=VqR-PY3Iw4U](https://www.youtube.com/watch?v=VqR-PY3Iw4U)
## Post #271
- Username: isamu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jan 13, 2018 2:10 am
- Post datetime: 2018-07-18T19:55:46+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Fantastic work! Great videos thanks for sharing!
## Post #272
- Username: graphitero
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Oct 08, 2017 12:23 am
- Post datetime: 2018-07-20T17:35:28+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

After not being able to finish the map since the wangan midnight from ps3 dont have a few spots. Soo here is the 2 links for the Shutoko directly from Wangan Midnight. Do whatever u guys want with the 3ds and anything with the w.i.p map on AC.

[https://drive.google.com/open?id=0B_p68 ... WplSld0STQ](https://drive.google.com/open?id=0B_p68lUDCZwWUzhWMWplSld0STQ)

[https://drive.google.com/open?id=0B_p68 ... XRwYWoxSWs](https://drive.google.com/open?id=0B_p68lUDCZwWaWFDRXRwYWoxSWs)
## Post #273
- Username: trawa
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jun 01, 2018 11:32 am
- Post datetime: 2018-07-20T22:10:51+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from Pentaaa
>
> Hi Pentaaaaa. That is great news! You and your friend have my full support!!!!!! Wishing you the best of luck my friend, and thanks for working on Shuto. Do you expect your version to compare favorably with NigelAE's? How will your version differ from his? Do you have any WIP videos you can share with us?

Thank you for your kind words. Ours isn't as refined as his, atleast yet. We haven't done really much texuture work, except replacing bad textures, and the road mesh is still the old one too. As i said, ours will definitely have the new version of Tatsumi PA, and hopefully a somewhat usable Daikoku PA. I'll post two videos below for you guys to look at.

Tatsumi PA
https://i.imgur.com/zJ1JY42.png
https://i.imgur.com/kAbjwNT.png

Fukagawa Daiba Route https://www.youtube.com/watch?v=683BrsJuiak
Minato Test https://www.youtube.com/watch?v=VqR-PY3Iw4U

hooooly shit, my body is ready.
if you need any help shoot me a message and I'll do my best.
## Post #274
- Username: graphitero
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Oct 08, 2017 12:23 am
- Post datetime: 2018-07-21T01:55:14+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

A friend started converting it for GTA5 a few days ago. Im trying to extract the .bin and .nut from WMMT5 to have the complete track including the aqualine.
## Post #275
- Username: dragonzheng
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 26, 2018 7:48 pm
- Post datetime: 2018-07-26T11:56:16+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from trawa
>
> sorry for double posting; cant find the bump thread button.  

https://www.youtube.com/watch?v=5S-EVuP4Y9g
overhauled it a little but i'm not good enough in 3DS Max or KSEditor to finish it. 
MM files (scaled, aligned, FBX + TEX + KN5)
https://mega.nz/#!6ggGhSRB!AJ01aT-YPU4a ... B6i-KfwxWs
feel free to use them.

full Tokio-to-Yokohama loop
https://drive.google.com/file/d/1uiE_ki ... 9cHu7/view

add the .kn5 file to ww_metropolitan folder and add 
Code: Select all[MODEL_9]
FILE=ww_metropolitan_expressway_part9.kn5
POSITION=0,0,0
ROTATION=0,0,0
in models_ww_metropolitan_expressway.ini

The link to the full Tokio-to-Yokohama loop map is dead, could u reupload it?
## Post #276
- Username: trawa
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jun 01, 2018 11:32 am
- Post datetime: 2018-07-27T08:23:00+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from dragonzheng
>
> trawa wrote:sorry for double posting; cant find the bump thread button.  

https://www.youtube.com/watch?v=5S-EVuP4Y9g
overhauled it a little but i'm not good enough in 3DS Max or KSEditor to finish it. 
MM files (scaled, aligned, FBX + TEX + KN5)
https://mega.nz/#!6ggGhSRB!AJ01aT-YPU4a ... B6i-KfwxWs
feel free to use them.

full Tokio-to-Yokohama loop
https://drive.google.com/file/d/1uiE_ki ... 9cHu7/view

add the .kn5 file to ww_metropolitan folder and add 
Code: Select all[MODEL_9]
FILE=ww_metropolitan_expressway_part9.kn5
POSITION=0,0,0
ROTATION=0,0,0
in models_ww_metropolitan_expressway.ini

The link to the full Tokio-to-Yokohama loop map is dead, could u reupload it?
[http://www.mediafire.com/file/7ub4qr7hh ... y.rar/file](http://www.mediafire.com/file/7ub4qr7hh5z1c6t/ww_metropolitan_expressway.rar/file)
[https://mega.nz/#!qxByyYQL!q34Ab2dFaTt9 ... 2TVHAbMm2k](https://mega.nz/#!qxByyYQL!q34Ab2dFaTt9Akvlvog5BQ9hLD3PbjgUf2TVHAbMm2k)
## Post #277
- Username: dragonzheng
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 26, 2018 7:48 pm
- Post datetime: 2018-07-27T15:35:55+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from trawa
>
> dragonzheng wrote:trawa wrote:sorry for double posting; cant find the bump thread button.  

https://www.youtube.com/watch?v=5S-EVuP4Y9g
overhauled it a little but i'm not good enough in 3DS Max or KSEditor to finish it. 
MM files (scaled, aligned, FBX + TEX + KN5)
https://mega.nz/#!6ggGhSRB!AJ01aT-YPU4a ... B6i-KfwxWs
feel free to use them.

full Tokio-to-Yokohama loop
https://drive.google.com/file/d/1uiE_ki ... 9cHu7/view

add the .kn5 file to ww_metropolitan folder and add 
Code: Select all[MODEL_9]
FILE=ww_metropolitan_expressway_part9.kn5
POSITION=0,0,0
ROTATION=0,0,0
in models_ww_metropolitan_expressway.ini

The link to the full Tokio-to-Yokohama loop map is dead, could u reupload it?
http://www.mediafire.com/file/7ub4qr7hh ... y.rar/file
https://mega.nz/#!qxByyYQL!q34Ab2dFaTt9 ... 2TVHAbMm2k

Thanks!!
## Post #278
- Username: trawa
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jun 01, 2018 11:32 am
- Post datetime: 2018-08-29T02:09:16+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Not much progress regarding Minato Mirai, managed to rip Daikoku Futo from Dubai Drift 2 but its a mess.


BUT

Track lights config for full metro is in the works 

[https://cdn.discordapp.com/attachments/ ... lation.png](https://cdn.discordapp.com/attachments/453615048837824514/484180620029722625/Screenshot_s14kouki_dmax_wangan_ww_metropolitan_expressway_29-8-118-4-0-34_accumulation.png)


EDIT
[https://www.youtube.com/watch?v=QBBLQStxRbU](https://www.youtube.com/watch?v=QBBLQStxRbU)
## Post #279
- Username: trawa
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jun 01, 2018 11:32 am
- Post datetime: 2018-09-09T05:40:26+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

[https://cdn.discordapp.com/attachments/ ... 8/woah.PNG](https://cdn.discordapp.com/attachments/483144847662776341/488218743093198858/woah.PNG) 
WMMT5 files but all of them are in .MDL, nothing I've tried worked so far, looks like they're encrypted.   

I'm not coding-savy at all so well, asking for help. Let your friends and friends of friends know. If we crack this open, we can get the C2 line, Osaka and Yaesu in proper quality.
## Post #280
- Username: isamu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jan 13, 2018 2:10 am
- Post datetime: 2018-09-10T00:58:40+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from trawa
>
> https://cdn.discordapp.com/attachments/ ... 8/woah.PNG 
WMMT5 files but all of them are in .MDL, nothing I've tried worked so far, looks like they're encrypted.   

I'm not coding-savy at all so well, asking for help. Let your friends and friends of friends know. If we crack this open, we can get the C2 line, Osaka and Yaesu in proper quality.

Nice find! Yes, I fully support this!! C'mon guys get the word....Trawa needs your help.
## Post #281
- Username: nosfornos
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Dec 21, 2011 4:16 pm
- Post datetime: 2018-09-17T15:56:40+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

how about eunos cosmo model from Maximum Tune series?
## Post #282
- Username: nosfornos
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Dec 21, 2011 4:16 pm
- Post datetime: 2018-09-18T13:20:40+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

this file.
[https://cdn.discordapp.com/attachments/ ... _JCESE.mdl](https://cdn.discordapp.com/attachments/481447717248434176/491599410971672596/PLC_JCESE.mdl)
## Post #283
- Username: trawa
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jun 01, 2018 11:32 am
- Post datetime: 2018-10-09T22:50:59+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

[https://www.youtube.com/watch?v=QPAhb99_yKc](https://www.youtube.com/watch?v=QPAhb99_yKc)

wangan 2.0 soon.
## Post #284
- Username: isamu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jan 13, 2018 2:10 am
- Post datetime: 2018-10-10T20:38:42+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from trawa
>
> https://www.youtube.com/watch?v=QPAhb99_yKc

wangan 2.0 soon.

OMG OMG OMG!!!!      

Trawa can you please explain what improvements we can expect in version 2.0? Will it cover the entire shuto expressway? Will it improve upon the version NigelAE drives in this video:

[https://www.youtube.com/watch?v=csZWyHMaZlo&t=4s](https://www.youtube.com/watch?v=csZWyHMaZlo&t=4s)

I posted in the comments in that video and Nigel replied saying this:

> Thank you for your polite message. And thanks for checking the video over and over. That's right. I have a lot of work to do on this track. It will take some time for a while. But do not expect too much.﻿

That was 3 months ago. Have you been working with NigelAE on improving this track since then, Trawa?
## Post #285
- Username: isamu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jan 13, 2018 2:10 am
- Post datetime: 2018-10-11T14:36:51+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Just watched the WIP video again and it looks absolutely fantastic! Great job Trawa. Looks like we'll be able to take different routes on the highway in your version? How will your version differ from the one hosted at AC Pursuit?

Also Disregard my question about Nigel, I forget about your earlier reply saying you guys aren't working together. Nigel refusing to work with people outside his "inner circle" is a real shame   He's got a Kousyu Street Night track that I'd die to get my hands on.

[https://www.youtube.com/watch?v=uyvuuLazvxQ&t=365s](https://www.youtube.com/watch?v=uyvuuLazvxQ&t=365s)
## Post #286
- Username: trawa
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jun 01, 2018 11:32 am
- Post datetime: 2018-10-13T00:23:23+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

yes
maybe
yes
won't look like ass

edit: [https://www.youtube.com/watch?v=vyHPabBo-94](https://www.youtube.com/watch?v=vyHPabBo-94)
## Post #287
- Username: trawa
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jun 01, 2018 11:32 am
- Post datetime: 2018-10-24T17:05:20+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Bayshore Route update rolled out.
[https://discordapp.com/invite/JydhbJG](https://discordapp.com/invite/JydhbJG)
## Post #288
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2018-10-25T18:06:10+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Daikoku Futo 3D model download:
[http://www.mediafire.com/file/4xq8eheag ... l.zip/file](http://www.mediafire.com/file/4xq8eheagibcox7/Final.zip/file)

Quick conversion:
[https://www.youtube.com/watch?v=kqWb7TOZ2bw](https://www.youtube.com/watch?v=kqWb7TOZ2bw)&
[2.jpg](https://xentaxbackup.github.io/file/15091_2.jpg)
## Post #289
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2018-10-26T00:48:59+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from Takukun
>
> Daikoku Futo 3D model download:
http://www.mediafire.com/file/4xq8eheag ... l.zip/file

Quick conversion:
https://www.youtube.com/watch?v=kqWb7TOZ2bw&
Sick find!
## Post #290
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2018-10-26T09:22:15+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Actually it was trawa the one to find it, I just ripped it from Dubai Drift 2/Drift Wars
## Post #291
- Username: wood5578
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Nov 10, 2018 2:56 pm
- Post datetime: 2018-11-10T07:30:25+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from trawa
>
> https://cdn.discordapp.com/attachments/ ... 8/woah.PNG 
WMMT5 files but all of them are in .MDL, nothing I've tried worked so far, looks like they're encrypted.   

I'm not coding-savy at all so well, asking for help. Let your friends and friends of friends know. If we crack this open, we can get the C2 line, Osaka and Yaesu in proper quality.

I managed to figure out the model system they used for WMMT5. Turns out the .mdl (for cars) and .bin (for tracks) are actually containers for .nud files. 



I tried it on the Fairlady (Z31) by manually splitting out a few basic nud and import it with Pokken Nud import Maxscript and it imports it properly.




Did the same process on C1 Section 1 and it works too 



What we need now is a tool that can unpack these archive.
Some of the game files are gzipped, you have to extract them first, then you should be able to export the models properly. Some extracted files will have blank extension,you can either just leave it that way or add the same extension matching the original file.
## Post #292
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2018-11-10T14:03:50+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Now THAT is a big discovery.

But there’s a problem with WMMT5 track models. They’re slightly altered. If you played WMMT5 with TeknoParrot, you can spot few and maybe lots of differences in C1’s layout compared to Wangan Midnight (PS3)/Import Tuner Challenge (XBOX360).

In fact, i tried locating the real version of Hakone on Google Maps, and the map is heavily altered. Same goes to Hakone Turnpike (in newer version of WMMT5 and also 5DX and so on).
It would be fun to get WMMT5’s Hakone to assetto though   

Anyways, what about textures?
## Post #293
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2018-11-10T14:27:47+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

@wood5578 I love you, thanks for this post.
@REDZOEU True, the maps weren't laserscanned but they can definitely be integrated with wmps3's map with some editing, I just don't know how much work is needed tho. Ripped yaesu from wmmt5 and it's not so bad.
## Post #294
- Username: mayto
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 14, 2019 5:05 am
- Post datetime: 2019-03-13T21:07:18+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Anyone have a model of Hakone extracted?
## Post #295
- Username: Dennissaurus
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Aug 12, 2014 11:16 pm
- Post datetime: 2019-04-22T19:05:49+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

[https://www.mediafire.com/file/845ml0gt ... o.zip/file](https://www.mediafire.com/file/845ml0gt6vxhkcm/CRC_V55W_Namco.zip/file)  can you take a look at this file please, now im not sure if this is because its from the "ported to pc" WMMT5, but i couldnt find any NUD data to speak of... Maybe i missed something? i really dont know but would be greatful if you could get this open?

Thanks in advance to you and anyone who assists. So far i didnt see this vehicle in any game before. would be a nice treat to mess with something i once owned.
## Post #296
- Username: Dennissaurus
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Aug 12, 2014 11:16 pm
- Post datetime: 2019-08-03T12:23:22+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from Dennissaurus ↑Mon May 07, 2018 12:35 am at Mon May 07, 2018 12:35 am
>
> 
THANKS! I will check igcd, this was the first game i seen a Mitsubishi Pajero evolution... so hunting badly to find it  

https://jalopnik.com/meet-the-mitsubish ... 1704009601

Okay been a while as life gets upto well LIFE...  The Pajero Evolution IS NOT found in other games. WMMT4 and WMMT5 only.... please can one of you legends dump that out? i uploaded files for it here already, but has been removed from dropbox. will upload again if needed?
## Post #297
- Username: Dennissaurus
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Aug 12, 2014 11:16 pm
- Post datetime: 2019-10-26T14:21:05+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

[https://www.mediafire.com/file/845ml0gt ... o.zip/file](https://www.mediafire.com/file/845ml0gt6vxhkcm/CRC_V55W_Namco.zip/file)

Re-upload of Teknoparrot version WMMT5 Pajero Evolution files 

No nud info to speak of, and idk if maybe im a moron here, but gzip didnt reveal anything either? So confusing... 

I been chasing this vehicle for over 2 years in total. Anyone want to lend a hand for a sexy Assetto Corsa and a gta V port base file?
## Post #298
- Username: darkpower
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Nov 14, 2019 5:54 am
- Post datetime: 2019-11-13T21:57:50+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Hello there! Can you help me with ripping model? I need WMMT5 Nissan Laurel c35 model. Please help me how much as you can. Because this car is my car in real life. Thank you so much!
## Post #299
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2019-11-14T09:50:51+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

hey there, for converting stuff from wmmt5 you just need to get the 3ds max pluggin for Pokken(.nud), it basically handles namco geometry files, its just as simple as importing each nud to 3ds.... google can help locating the pokken .nud script for max, else is just installing/copy-pasting it on 3ds and manually sorting the files...
## Post #300
- Username: darkpower
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Nov 14, 2019 5:54 am
- Post datetime: 2019-11-16T17:15:19+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from Machinedramon ↑Thu Nov 14, 2019 5:50 pm at Thu Nov 14, 2019 5:50 pm
>
> 
hey there, for converting stuff from wmmt5 you just need to get the 3ds max pluggin for Pokken(.nud), it basically handles namco geometry files, its just as simple as importing each nud to 3ds.... google can help locating the pokken .nud script for max, else is just installing/copy-pasting it on 3ds and manually sorting the files...

Can you upload here? I can't find out this plugin. And where is .nud files? I just found .mdl files. Thanks
## Post #301
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2019-11-16T22:51:44+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

iirc the site was [https://gbatemp.net/threads/release-pok ... ck.426437/](https://gbatemp.net/threads/release-pokken-ripping-tools-pack.426437/)
and yeah, .mdl files are gzip compressed, with 7zip you should be able to unpack wmmt5, then you get .mdl files again, those need to be stripped into the nuds, for that you need to use csplitb, the python one should be the easiest for use, when splitted using the Nud header, you get all the nud files per mdl, those then need to be imported, in this case to 3ds max using the script that these tools provide....
## Post #302
- Username: Mati
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Nov 23, 2019 6:01 am
- Post datetime: 2019-11-22T22:03:02+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

hi anyone have orginal fbx model wmmt5 or wm ps3 map ?
## Post #303
- Username: StarGTS
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 03, 2020 5:58 pm
- Post datetime: 2020-05-03T10:24:03+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Is there no version for GTA SA? 
Why are these projects not successful? For SA it would be a perfect map
## Post #304
- Username: highwaywarrior
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 13, 2020 4:29 pm
- Post datetime: 2020-10-02T21:10:51+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

deleted
## Post #305
- Username: mea
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jan 18, 2021 9:18 pm
- Post datetime: 2021-01-19T06:22:25+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from StarGTS ↑Sun May 03, 2020 6:24 pm at Sun May 03, 2020 6:24 pm
>
> 
Is there no version for GTA SA? 
Why are these projects not successful? For SA it would be a perfect map

i can do it for MTA SA all i need is just the 3d model and textures  i can generate col from it
## Post #306
- Username: mea
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jan 18, 2021 9:18 pm
- Post datetime: 2021-01-19T07:55:35+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from wood5578 ↑Sat Nov 10, 2018 3:30 pm at Sat Nov 10, 2018 3:30 pm
>
> 
trawa wrote:https://cdn.discordapp.com/attachments/ ... 8/woah.PNG 
WMMT5 files but all of them are in .MDL, nothing I've tried worked so far, looks like they're encrypted.   

I'm not coding-savy at all so well, asking for help. Let your friends and friends of friends know. If we crack this open, we can get the C2 line, Osaka and Yaesu in proper quality.

I managed to figure out the model system they used for WMMT5. Turns out the .mdl (for cars) and .bin (for tracks) are actually containers for .nud files. 



I tried it on the Fairlady (Z31) by manually splitting out a few basic nud and import it with Pokken Nud import Maxscript and it imports it properly.




Did the same process on C1 Section 1 and it works too 



What we need now is a tool that can unpack these archive.
Some of the game files are gzipped, you have to extract them first, then you should be able to export the models properly. Some extracted files will have blank extension,you can either just leave it that way or add the same extension matching the original file.

so i just use the maxscript to import nud and it will import the 3d model with it ?
## Post #307
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2021-01-24T18:33:12+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from mea ↑Tue Jan 19, 2021 2:22 pm at Tue Jan 19, 2021 2:22 pm
>
> 
StarGTS wrote: ↑Sun May 03, 2020 6:24 pm
Is there no version for GTA SA? 
Why are these projects not successful? For SA it would be a perfect map


i can do it for MTA SA all i need is just the 3d model and textures  i can generate col from it
[https://www.gtainside.com/en/sanandreas ... xpressway/](https://www.gtainside.com/en/sanandreas/maps/155736-c1-shuto-expressway/)
## Post #308
- Username: mea
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jan 18, 2021 9:18 pm
- Post datetime: 2021-01-28T20:04:36+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

yeah i saw that mod but it only has the c1 loop     


also about the gta sa conversion i started it  getting the models from some pages back  and i did everything cutting doing vertex colors optimizing collisions but after i tested it ingame it seems that the full wangan map   c1-belt lopp -bayshore -yokohane - minato  does not fit in the gta sa world   [https://cdn.discordapp.com/attachments/ ... nknown.png](https://cdn.discordapp.com/attachments/592477067766136833/804410193374871682/unknown.png)
this is what it looks like if i reach the world limit  

it can only fit like c1 + belt loop and half of yokohane and bayshore
## Post #309
- Username: TommyDev
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 21, 2021 1:41 am
- Post datetime: 2021-03-03T14:06:15+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from mea ↑Fri Jan 29, 2021 4:04 am at Fri Jan 29, 2021 4:04 am
>
> 
yeah i saw that mod but it only has the c1 loop     


also about the gta sa conversion i started it  getting the models from some pages back  and i did everything cutting doing vertex colors optimizing collisions but after i tested it ingame it seems that the full wangan map   c1-belt lopp -bayshore -yokohane - minato  does not fit in the gta sa world   https://cdn.discordapp.com/attachments/ ... nknown.png
this is what it looks like if i reach the world limit  

it can only fit like c1 + belt loop and half of yokohane and bayshore

Sadly I don't know anything about map creations for GTA SA, but where did you get the c1 loop/bayshore/yokohane/minato models from? Almost all download links seem to be dead as of now. Is there a way you could provide me with those files? Good luck with your conversion Project too.
## Post #310
- Username: nfm
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 04, 2010 8:56 am
- Post datetime: 2021-03-06T07:53:09+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Hi TommyDev and others,

I know you asked me for the files, full source to C1 Rev6 including the FBX, .ini kn5 shader/material, and blender files can be found here: [https://mega.nz/file/HhFlFSaD#4CRnI_hZQ ... ZMQLkWfr9U](https://mega.nz/file/HhFlFSaD#4CRnI_hZQuq-jyNwE73hpdUhGG7nE1-64ZMQLkWfr9U) . Btw I have shared this in the past numerous times. Anyone can use to mod it or add additions on top of rev6.

If you want the full course search for Wangan Midnight PS3 [BLJM60028] ISO torrent, you can then extract the game resources with quickbms script or my TXRExtractor_gui_v0.1.exe tool (download at [https://github.com/fatalhalt/TXRExtract ... s/tag/v0.1](https://github.com/fatalhalt/TXRExtractor/releases/tag/v0.1)). It is also there that you can find the 3ds Max script to rip your own geometry/textures/materials from vanilla Wangan Midnight PS3. I should have done a "howto" writeup long time ago, I just pushed some changes to MaxScript [https://raw.githubusercontent.com/fatal ... wmn/wmn.ms](https://raw.githubusercontent.com/fatalhalt/TXRExtractor/master/maxscript/wmn/wmn.ms) that I had laying around, with these new changes it will dump the kn5 .ini file (it will still need some basic search/replace fixup but after that it is ready for ksEditor).

And also there's the Shutoko Revival Project that has been going independent of me, I never looked deeply into nor got involved, I have been away doing other stuff, but recently I tried the "public test build" that's found on discord and ran into some decrypt error and map wouldn't load. So there's that. Well I hope I can play it once new update shows up.
## Post #311
- Username: mea
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jan 18, 2021 9:18 pm
- Post datetime: 2021-03-10T17:33:32+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

no need to extract everything 

here is the full ps3 map in sections and in .fbx format 
have fun
[https://drive.google.com/file/d/1fa-kiv ... sp=sharing](https://drive.google.com/file/d/1fa-kivm40Nf9INs8Sdatzy19sQR6qU3E/view?usp=sharing)

there is a problem in yokohane i remember  one object had scaling problem and two objects had wrong rotations i might be wrong

here is the missing part [https://cdn.discordapp.com/attachments/ ... n_part.zip](https://cdn.discordapp.com/attachments/831307832283758642/833037318667108452/mssin_part.zip) you just need to scale this correctly

you can contact me in discord if the link is broken 
mea#0401

btw i recently got hold of some wmmt 2 models i uploaded all of the models maps and cars and i already converted all of them to .fbx and fixed all the textures (except that one in hakone road_waki3)   in discord wm emulation server #wm-modding pinned messages   [https://discord.gg/r3nbd4x](https://discord.gg/r3nbd4x)
dont forget to check the readme.txt after you download the wmmt 2 models

but they are really really low poly and textures are like 124x124 so i suggest you get the wmmt 5 map its much better
maybe you can use the car models idk

and also i had some luck with battle gear 4 car models  i was able to import them into 3ds max successfully and they only had some opacity issues but other than that they are amazing  
here is how you do it

1 after you find the car models they will be in .rws format you need to download RWanalyze 
2 open RWanalyze and then open your car model  
3 go to Tools>Commands>Convert DFF to RW 3.4 > current file 
4 click file > save as > delete .rws and type .dff instead > save
5 get KAMS (GF) for 3ds max [https://gtaforums.com/topic/907323-rel- ... ipts-2018/](https://gtaforums.com/topic/907323-rel-kams-gta-scripts-2018/)
6** IMPORT THE MODEL WITH .PNG AND STANDART MATERIALS ** now you have your model inside of 3ds max 
7 to extract textures you need to download Magic TXD after you download it you can just open the texture file for your car and export > .png  

--1 it might ask for some other textures which is where magic TXD MASS EXPORT comes in 
--2 click TOOLS>MASS EXPORT > SET GAME ROOT TO  battle gear 4\data\cardata
--3 set output to anywhere you like 
--4 choose your settings for example if you set** in seperate folders** it will make a new folder for each car and put that car texture inside of it     but if you set to **with texture name**  it will export all the car textures into the CarModel folder  and all tire textures into TireModel  etc

++1 to mass convert all models into .dff you need to put all .rws files into a new folder with nothing else 
++2 now you need to rename the extension you can use Advanced Renamer [https://www.advancedrenamer.com](https://www.advancedrenamer.com)
++3 open advanced renamer and select and drop all .rws files inside then click  + Add method > Replace 
**++4 set text to be replaced as .rws  set replace with as .dff  click apply to and select extension **
++5 click start batch
++6 open RWanalyze go to Tools>Commands>Convert DFF to RW 3.4 > Batch conversion
++7 select the new file containing only the .dff files 
++8 it will convert them  but some models have a little bit of corruption so it will ask you are you sure you want to save this file ** click yes **  this will be repeated multiple times but after you are done close RWanalyze

now all of the car models can be imported in 3ds max with textures -note-- if textures dont appear try to click the viewport mode (standard)  then go materials > disable transparency > after that click > show shaded materials with maps   now your materials should show up
if you still see black materials then you can fix them with GTA Tools  provided with KAMS (GF)  script  look up you will either see GTA tools or >>  click >> or GTA tools >model fixes > fix diffuse color and new windows will pop up make sure you select all the objects you want to fix and then click fix  boom materials are visble  there are lots of car upgrades

also some materials have 0 opacity so good luck fixing all of them

tire models can be found inside TireModel  this should be obvious



the map models are weird tho  they are like 500 objects combined inside a single .dff  i couldnt find a way to import them into 3ds max
## Post #312
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2021-06-26T16:27:52+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Recently took an interest to this game too so good work everyone 

Got it working on PC so I can rip geometry via DX
## Post #313
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2021-06-29T13:11:18+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Just got my hands on MNMT6 it has RTTI info which is useful but I think a lot of it is the same as 5
## Post #314
- Username: SilverAG1464
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Feb 14, 2022 5:54 pm
- Post datetime: 2022-02-14T09:57:57+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Hi guys, can someone please provide me link to download ps3 wangan midnight map in fbx format. I am working on a personal unity project based on jdm racing. Thanks in advance
## Post #315
- Username: deadsenshi
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Mar 13, 2022 5:49 pm
- Post datetime: 2022-03-13T09:51:39+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Hello, someone knows, where the BGM's name folder? Wangan Midnight 5 DX+.
 I check all the textures, and few .bin and .lua files, but i didnt found BGM names. I will change few 5DX BGM's to MT3, but i wanted to named it right
## Post #316
- Username: srtbois
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Mar 02, 2022 7:00 am
- Post datetime: 2022-07-02T07:39:43+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

So after months of trying to figure it out: I've finally been able to rip the models from WMMT6/WMMT5 (MT5 Is untested but they're extremely similar looking at files structures). 

I'm using the maps in particular because I want some of the expressways in GTA 5. You could use this same method for ripping the models for Assetto Corsa as well but the scale needs to be adjusted. HOWEVER, I have run into a problem. A major problem. It has to do with the models being "corrupted" when importing them into 3DS Max. Not all the models do this but I've seen a particular pattern that's a red flag if I/you want to complete the porting process. The models getting corrupted have file names ending in line and route. The line files are what they sound like: the road lines (white/yellow/dash/solid). The route files are less obvious but they are the actual road surface you drive on, like the asphalt. You see why this is a major problem? 

The only reason I know what these models even are is because I got one route to work and it was a road surface. The line ones have all been corrupted but I know it's road lines because I've imported entire sections of the Hiroshima Expressway in particular and they don't have any road lines present (plus I think lines is pretty obvious). 

I'll make a post after this showing you how to actually extract the models to use in 3ds max/blender/what ever 3D Modeling software you use. 
Just wanted to make this post first to ask for any advice on how get the models to not be corrupted or possibly fix them.
## Post #317
- Username: Raph
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 30, 2022 2:58 pm
- Post datetime: 2022-09-30T07:01:39+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from wood5578 ↑Sat Nov 10, 2018 3:30 pm at Sat Nov 10, 2018 3:30 pm
>
> 
trawa wrote:https://cdn.discordapp.com/attachments/ ... 8/woah.PNG 
WMMT5 files but all of them are in .MDL, nothing I've tried worked so far, looks like they're encrypted.   

I'm not coding-savy at all so well, asking for help. Let your friends and friends of friends know. If we crack this open, we can get the C2 line, Osaka and Yaesu in proper quality.

I managed to figure out the model system they used for WMMT5. Turns out the .mdl (for cars) and .bin (for tracks) are actually containers for .nud files. 



I tried it on the Fairlady (Z31) by manually splitting out a few basic nud and import it with Pokken Nud import Maxscript and it imports it properly.




Did the same process on C1 Section 1 and it works too 



What we need now is a tool that can unpack these archive.
Some of the game files are gzipped, you have to extract them first, then you should be able to export the models properly. Some extracted files will have blank extension,you can either just leave it that way or add the same extension matching the original file.

has anyone made or found a tool that can do the splitting part?
## Post #318
- Username: srtbois
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Mar 02, 2022 7:00 am
- Post datetime: 2022-12-06T01:18:24+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

This process requires Python, a python csplitb command (using Powershell), and winrar or poweriso to open the bin files. For 3dsMax you need the tekken nud import plugin. This can be found using a quick google search. USE 3DS MAX 2017-2018 btw. The process to split the files i wrote down in a txt file:

Get Bin files from the game archive
Extract the blank file from the .bin with PowerISO/WinRar
Put the .bin extension on the blank file
Use python to extract the nud sections (you have to pre-make the output folder in order for the script to work)

./python csplitb -f D:\WMMT6MODELS\KOBE\sect109\ -s .nud -n 1 4E445744 D:\WMMT6MODELS\KOBE\A_KOBE_DAY_NML_KOBE_SECT109.bin

TEXTURES Require extracting the blank file extension file from the .nut using poweriso or winrar
Use the bms.exe tool and select the PokkenNUT.bms script, select the nut file, select an output folder. Done

Some pages I bookmarked are located here. I forgot the process for a lot of it but every tool has it's own instructions. Hope these help!
[https://gbatemp.net/threads/release-pok ... ck.426437/](https://gbatemp.net/threads/release-pokken-ripping-tools-pack.426437/) < FIND THE 3DS PLUGIN HERE
[https://tekkenmods.com/guide/48/extract ... or-modding](https://tekkenmods.com/guide/48/extracting-vanilla-tekken-5-assets-for-modding) < FOR SPLITTING THE FILES
## Post #319
- Username: CDTH06
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Sep 16, 2021 3:00 am
- Post datetime: 2023-02-24T07:47:33+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

> Reply from srtbois ↑Tue Dec 06, 2022 9:18 am at Tue Dec 06, 2022 9:18 am
>
> 
This process requires Python, a python csplitb command (using Powershell), and winrar or poweriso to open the bin files. For 3dsMax you need the tekken nud import plugin. This can be found using a quick google search. USE 3DS MAX 2017-2018 btw. The process to split the files i wrote down in a txt file:

Get Bin files from the game archive
Extract the blank file from the .bin with PowerISO/WinRar
Put the .bin extension on the blank file
Use python to extract the nud sections (you have to pre-make the output folder in order for the script to work)

./python csplitb -f D:\WMMT6MODELS\KOBE\sect109\ -s .nud -n 1 4E445744 D:\WMMT6MODELS\KOBE\A_KOBE_DAY_NML_KOBE_SECT109.bin

TEXTURES Require extracting the blank file extension file from the .nut using poweriso or winrar
Use the bms.exe tool and select the PokkenNUT.bms script, select the nut file, select an output folder. Done

Some pages I bookmarked are located here. I forgot the process for a lot of it but every tool has it's own instructions. Hope these help!
https://gbatemp.net/threads/release-pok ... ck.426437/ < FIND THE 3DS PLUGIN HERE
https://tekkenmods.com/guide/48/extract ... or-modding < FOR SPLITTING THE FILES

How I can extract textures from .tex files?
## Post #320
- Username: kaiba121321
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 27, 2023 10:00 pm
- Post datetime: 2023-06-27T14:04:29+00:00
- Post Title: Re: Wangan Midnight [Need Help Reversing]

Sorry to bother everyone here, sorry to be necroing (if I am) or w.e else wrong I am doing T_T but my limited brain capacity is not going to let me get even close to porting models using this, it is amazing but I am too dumb  As such, I was wondering if any absolute legend here managed to rip and port Aizawa's Supra, the version with a partly black front bumper. I have found a whole 1 file for this version, which is the version that sticks in my head annnnnd it's a private download so I can't even get that. I'd be willing to comission someone just to get this dang Supra on public release with a solid handling setup that's a fair representation of the anime.
