## Post #1
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-01-30T17:54:46+00:00
- Post Title: Soul Calibur 5

I've been trying to figure out how to mod this game. Everything is in a container format called CPK which is apparently very common among Japanese developers.

[viewtopic.php?p=64068&sid=fd4ea032eb032 ... 25b#p64068](http://forum.xentax.com/viewtopic.php?p=64068&sid=fd4ea032eb032dab581ef4aa5b91325b#p64068) - That tool can be used for extracting the CPK files. Unfortunately, you'll get no filenames, those are not stored in the CPK files.

I'm pretty sure the file formats are near identical to SC4. Textures are still dds image data with NTXR/GIDX headers as in SC4. You can use this tool for extracting the textures: [http://www.tzarsectus.com/SC4/spdddsinject.exe](http://www.tzarsectus.com/SC4/spdddsinject.exe)

I haven't looked for any models, but I'm sure they're in the same or similar format as in SC4. All characters should be in creation.cpk.

Edit: I figured out how to mod the game. I didn't notice until now that the offical CPK tools comes with a make tool which lets you define the specific ID for each file. So once I managed to get the IDs the same, the new rebuilt cpk files work just fine. I don't even need to compress them.
## Post #2
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-01-31T03:56:01+00:00
- Post Title: Soul Calibur 5

The contents of this post was deleted because of possible forum rules violation.
## Post #3
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-01-31T16:17:23+00:00
- Post Title: Soul Calibur 5

I made a csv file for every cpk file for easily recreating them: [http://www.tzarsectus.com/SC5/rebuild.rar](http://www.tzarsectus.com/SC5/rebuild.rar) (you'll need official CPK toolkit for rebuilding the cpk files)

Unfortunately, I wasn't able to extract demo.cpk, that causes an error, so there's no csv for that archive. Remember to use "-align=2048" when rebuilding cpk files.

cdata->
209 - Character Select
381 - Male creation items thumbnails
382 - Female creation items thumbnails

creation->
256 - Mitsurugi 1P
257 - Mitsurugi 2P
258 - Mitsurugi face model
259 - Maxi 1P
260 - Maxi 2P
261 - Maxi face model
262 - Voldo 1P
263 - Voldo 2P
264 - Voldo face model
265 - Siegfried 1P
266 - Siegfried 2P
267 - Siegfried face model
268 - Ivy 1P
269 - Ivy 2P
270 - Ivy face model
271 - Edge Master 1P
272 - Edge Master 2P
274 - Nightmare 1P
275 - Nightmare 2P
276 - Nightmare SC4 1P
277 - Nude female.
278 - Astaroth 1P
279 - Astaroth 2P
280 - Kamikirimusi
281 - Cervantes 1P
282 - Cervantes 2P
283 - Cervantes 3P
285 - Raphael 1P
286 - Raphael 2P
287 - Raphael face model
288 - Tira 1P
289 - Tira 2P
290 - Tira face model
291 - Hilde 1P
292 - Hilde 2P
293 - Nude female model
294 - Algol 1P
295 - Algol 2P
296 - Zasalamel SC4 1P
297 - Dampierre 1P
298 - Dampierre 2P
299 - Zwei 1P
300 - Zwei 2P
302 - Viola 1P
303 - Viola 2P
305 - Pyrrha 1P
306 - Pyrrha 2P
308 - Pyrrha Omega 1P
309 - Pyrrha Omega 2P
311 - Patroklos 1P
312 - Patroklos 2P
314 - Alpha Patroklos 1P
315 - Alpha Patroklos 2P
317 - Natsu 1P
318 - Natsu 2P
320 - Xiba 1P
321 - Xiba 2P
323 - Lexia 1P
324 - Lexia 2P
326 - Lizardman 1P
327 - Lizardman 2P
329 - Yoshimitsu 1P
330 - Yoshimitsu 2P
332 - Elysium 1P
333 - Elysium 2P
335 - Kilik 1P
336 - Kilik 2P
338 - Cervantes 3P again?
339 - Nightmare SC4 1P again?
340 - Ezio 1P
341 - Ezio 2P
342 - Siegfried SC4 1P
343 - Nightmare SC4 1P again?
344 - Edgemaster (probably grey model for CAS fight preview)
345 - CAS male face model?
346 - CAs male face model?
354 - Male face and some armour parts.
372 - Female face?
373 - Female face?
374 - Male basic clothes?
375 - Male undergarments
376 - Male undergarments
377 - Male undergarments
378 - Male undergarments
379 - Male nude base. Yoshimitsu?
380 - Male nude base. Nightmare?
381 - Male undergarments
382 - Male undergarments
382 - Male undergarments
383 - Male undergarments
384 - Hair?
388 - A helmet?
389 - Hair.
390 - Hair?
403 - Patroklos hair?
413 - Helmet?
989 - A ball.
990 - Nude CAS female base (primary CAS base with underwear)
991 - NUde CAS female base (same as above but with no underwear. probably used for items which shouldnt show the underwear)
992 - Nude CAS female base (same as above with hair? not sure what this is for)
993 - hair
1000 - Long female hair.
1005 - Tira's hair.
1015 - Viola's hair.
1160 - Female "Basic clothes"
1161 - Female undergarments
1162 - Female undergarments
1163 - Female undergarments
1164 - Female undergarments
1165 - Female undergarments
1166 - Female undergarments
1182 - Some kind of bikini.
1200 - Big female shirt.
1213 - Female shirt
1221 - Top part of female dress.
1240 - Pants.
1245 - Baggy pants.
1440 - Small armour
1446 - Female armour.

3584 - CAS male textures.
->
3588 - CAS male textures.

3589 - CAS female textures.
->
3593 - CAS female textures.

motion->
256 - Collection of animations used in CAS (all character idle animations for instance).
257 - Mitsurugi
258 - Maxi
259 - Voldo
260 - Siegfried
261 - Ivy
262 - Caused crash. (probably Edge master)
263 - Nightmare
264 - Astaroth
265 - Cervantes
266 - Raphael
267 - Tira
268 - Hilde
269 - Algol
270 - Dampierre
271 - Zwei
272 - Viola
273 - Pyrrha
274 - Omega Pyrrha
275 - Patroklos
276 - Alpha Patroklos
277 - Natsu
278 - Xiba
279 - Leixia
280 - Aeon
281 - Yoshimitsu
282 - Caused crash. (probably elysium)
283 - Caused crash. (probably kilik)
284 - Devil Jin
285 - Ezio

General character index:
Mitsurugi
Maxi
Voldo
Siegfried
Ivy
Edgemaster
Nightmare
Astaroth
Cervantes
Raphael
Tira
Hilde
Algol
Dampierre
Zwei
Viola
Pyrrha
Omega Pyrrha
Patroklos
Alpha Patroklos
Natsu
Xiba
Leixia
Aeon
Yoshimitsu
Elysium
Kilik
Devil Jin
Ezio
## Post #4
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2012-01-31T17:41:14+00:00
- Post Title: Soul Calibur 5

When i use the CRI Packed Filemaker and click on extract in the upper right, i select a folder and click on yes in the dialogbox that opens... then it says:

Error Stop. Cannot extract a file. This is invalid CPK file format.



EDIT:
should have used the right tool... haha
## Post #5
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2012-01-31T18:02:03+00:00
- Post Title: Soul Calibur 5

Sorry to be annoying but how do you repack the cpk properly?

Do i have to use the commandline tool or is it possible to use the csv's in the gui somehow?
## Post #6
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-01-31T19:37:31+00:00
- Post Title: Soul Calibur 5

> Reply from Itze
>
> Sorry to be annoying but how do you repack the cpk properly?

Do i have to use the commandline tool or is it possible to use the csv's in the gui somehow?
Use this command line when in the directory with the extracted cpk files and the proper csv:

```
cpkmakec.exe motion.csv motion.cpk -align=2048 -mask
```


Replace "motion" with whatever cpk you're rebuilding. (I don't know if the mask option is necessary, but I use it anyway)
## Post #7
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-02-01T02:07:46+00:00
- Post Title: Soul Calibur 5

The contents of this post was deleted because of possible forum rules violation.
## Post #8
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2012-02-01T16:38:46+00:00
- Post Title: Soul Calibur 5

Cool 

If anyone has problems with importing converted models, check your decimal limiter in language options... if it is "," change it to "." and vice versa... that will fix the models being just one flat line 

You might have to reconvert the model with spd ex after changing this setting in windows.
## Post #9
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-02-02T02:36:24+00:00
- Post Title: Soul Calibur 5

For SCV in noesis, thanks to mr adults:

> SC5 files will load in the next version of Noesis, whenever I get around to publishing a build. The only reason the files aren't accepted by Noesis is because they changed the NMD marker to 4E 4D 44 2E instead of 4E 4D 44 03. You can hex edit the 03 to 2E and Noesis will load it fine as-is. It won't load materials correctly though, which isn't surprising, I never completely figured out the material data in SC4 or T6.
## Post #10
- Username: skytoast
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jan 31, 2010 6:12 pm
- Post datetime: 2012-02-02T06:17:25+00:00
- Post Title: Soul Calibur 5

Guys, I know this is probably still early to ask but I would like to get information (and help) if possible.  The game is gorgeous, yes, more so than SCIV.  And for that, most would go for models and textures at that.  One thing I was disappointed with the game (both SCIV and SCV) was the limitation (or change in camera) function of the game.  What I'm talking about is the in game camera perspective in the game.  Also the camera during replays behaves differently now.

Typically while playing you get a side view 1p vs 2p like most fighting games.  The thing about SC series with its unique 8-way run mechanics and its full use of 3D.  (Most other 3D fighters still play like 2D fighters but character and stages are rendered in 3D).  There were moments in the game where it allowed you to move the camera and pan around the characters, zoom in and zoom out or fast switch the view from one character to the other and vice versa.  

You can change the perspective typically between rounds during instant replay.  The other method which allowed you greater freedom was during the game's training mode which featured instant replay functionality.  During replay, it will loop the last 6-8 sec of action.  Using the controller and holding down certain buttons would engage the camera and the user is free to move it around.   

In SCIV - the default camera controls are as follows (similar setup, just different button names):

Xbox 360
Lock/Engage camera  - hold Left Trigger
Rotate camera (around focused character)  - Left analog stick or d-pad
Zoom camera (in or out) - Right analog stick (up/down only) or x/y buttons 
Character camera switch - Left bumper or Right Trigger or B button
Camera rotate lock or hold (prevents camera rotation allowing horizontal pan) - hold Right bumper

PS3
Lock/Engage camera  - hold L2 trigger
Rotate camera (around focused character)  - Left analog stick or d-pad
Zoom camera (in or out) - Right analog stick (up/down only) or square/triangle buttons 
Character camera switch - L1 bumper or R1 Trigger or circle button
Camera rotate lock or hold (prevents camera rotation allowing horizontal pan) - hold R1 bumper

SCV
Controls are very similar except Left/L1 bumper has no functionality.

What was nice about SCIV, was the camera held its perspective between loops.  When you engaged the camera (holding down left trigger), the camera perspective would stay where ever you held it and would replay the loop from that angle.  If you left the controller alone, it would keep looping the replay in its default 1P vs 2P perspective.

In SCV, the implementation changed.  The camera now resets the perspective between loops.  It seems to engage the 3D camera first momentarily at a predefined angle then move to where ever the camera is placed at. Just leaving the controls alone, you'll notice this as the instant replay starts in 3D perspective on 1P character momentarily then move back to the 1P vs 2P side default view.  

Anyways, question is where would one go about looking for this data on camera behavior during replays and its limitation?

In the old days on the PS2 with SCIII, there were action replay/gameshark codes that allowed extended camera functionality.

[http://youtu.be/Sa7jPFIJQbE](http://youtu.be/Sa7jPFIJQbE)
## Post #11
- Username: khanbot
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Dec 13, 2011 6:12 pm
- Post datetime: 2012-02-06T14:26:58+00:00
- Post Title: Soul Calibur 5

this is good, I got a huge ton of .bin files after cpk extraction lol thanks OP

but I wanna know how do I get the .nmd files?
## Post #12
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-02-06T16:58:59+00:00
- Post Title: Soul Calibur 5

> Reply from khanbot
>
> this is good, I got a huge ton of .bin files after cpk extraction lol thanks OP

but I wanna know how do I get the .nmd files?

Just rename them to nmd. Then open one nmd in hxd, look for nmd, change the 03 of the character next to D to 2E and noesis is going to load it without any problem.
## Post #13
- Username: DeathBillZhao
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Aug 28, 2011 4:11 pm
- Post datetime: 2012-02-07T16:31:24+00:00
- Post Title: Soul Calibur 5

> Reply from Sectus
>
> I made a csv file for every cpk file for easily recreating them: http://www.tzarsectus.com/SC5/rebuild.rar

Use the tool in the OP for extracting the cpk files. Unfortunately, I wasn't able to extract demo.cpk, that causes an error, so there's no csv for that archive. Remember to use "-align=2048" when rebuilding cpk files.

cdata->
209 - Character Select
381 - Male creation items thumbnails
382 - Female creation items thumbnails

creation->
256 - Mitsurugi 1P
257 - Mitsurugi 2P
258 - Mitsurugi face model
259 - Maxi 1P
260 - Maxi 2P
261 - Maxi face model
262 - Voldo 1P
263 - Voldo 2P
264 - Voldo face model
265 - Siegfried 1P
266 - Siegfried 2P
267 - Siegfried face model
268 - Ivy 1P
269 - Ivy 2P
270 - Ivy face model
271 - Edge Master 1P
272 - Edge Master 2P
274 - Nightmare 1P
275 - Nightmare 2P
276 - Nightmare SC4 1P
277 - Nude female.
278 - Astaroth 1P
279 - Astaroth 2P
280 - Kamikirimusi
281 - Cervantes 1P
282 - Cervantes 2P
283 - Cervantes 3P
285 - Raphael 1P
286 - Raphael 2P
287 - Raphael face model
288 - Tira 1P
289 - Tira 2P
290 - Tira face model
291 - Hilde 1P
292 - Hilde 2P
293 - Nude female model
294 - Algol 1P
295 - Algol 2P
296 - Zasalamel SC4 1P
297 - Dampierre 1P
298 - Dampierre 2P
299 - Zwei 1P
300 - Zwei 2P
302 - Viola 1P
303 - Viola 2P
305 - Pyrrha 1P
306 - Pyrrha 2P
308 - Pyrrha Omega 1P
309 - Pyrrha Omega 2P
311 - Patroklos 1P
312 - Patroklos 2P
314 - Alpha Patroklos 1P
315 - Alpha Patroklos 2P
317 - Natsu 1P
318 - Natsu 2P
320 - Xiba 1P
321 - Xiba 2P
323 - Lexia 1P
324 - Lexia 2P
326 - Lizardman 1P
327 - Lizardman 2P
329 - Yoshimitsu 1P
330 - Yoshimitsu 2P
332 - Elysium 1P
333 - Elysium 2P
335 - Kilik 1P
336 - Kilik 2P
338 - Cervantes 3P again?
339 - Nightmare SC4 1P again?
340 - Ezio 1P
341 - Ezio 2P
342 - Siegfried SC4 1P
343 - Nightmare SC4 1P again?
344 - Edgemaster (probably grey model for CAS fight preview)
345 - CAS male face model?
346 - CAs male face model?
354 - Male face and some armour parts.
372 - Female face?
373 - Female face?
374 - Male basic clothes?
375 - Male undergarments
376 - Male undergarments
377 - Male undergarments
378 - Male undergarments
379 - Male nude base. Yoshimitsu?
380 - Male nude base. Nightmare?
381 - Male undergarments
382 - Male undergarments
382 - Male undergarments
383 - Male undergarments
384 - Hair?
388 - A helmet?
389 - Hair.
390 - Hair?
403 - Patroklos hair?
413 - Helmet?
989 - A ball.
990 - Nude CAS female base (primary CAS base with underwear)
991 - NUde CAS female base (same as above but with no underwear. probably used for items which shouldnt show the underwear)
992 - Nude CAS female base (same as above with hair? not sure what this is for)
993 - hair
1000 - Long female hair.
1005 - Tira's hair.
1015 - Viola's hair.
1160 - Female "Basic clothes"
1161 - Female undergarments
1162 - Female undergarments
1163 - Female undergarments
1164 - Female undergarments
1165 - Female undergarments
1166 - Female undergarments
1182 - Some kind of bikini.
1200 - Big female shirt.
1213 - Female shirt
1221 - Top part of female dress.
1240 - Pants.
1245 - Baggy pants.
1440 - Small armour
1446 - Female armour.

3584 - CAS male textures.
->
3588 - CAS male textures.

3589 - CAS female textures.
->
3593 - CAS female textures.

motion->
256 - Collection of animations used in CAS (all character idle animations for instance).
257 - Mitsurugi
258 - Maxi
259 - Voldo
260 - Siegfried
261 - Ivy
262 - Caused crash. (probably Edge master)
263 - Nightmare
264 - Astaroth
265 - Cervantes
266 - Raphael
267 - Tira
268 - Hilde
269 - Algol
270 - Dampierre
271 - Zwei
272 - Viola
273 - Pyrrha
274 - Omega Pyrrha
275 - Patroklos
276 - Alpha Patroklos
277 - Natsu
278 - Xiba
279 - Leixia
280 - Aeon
281 - Yoshimitsu
282 - Caused crash. (probably elysium)
283 - Caused crash. (probably kilik)
284 - Devil Jin
285 - Ezio

General character index:
Mitsurugi
Maxi
Voldo
Siegfried
Ivy
Edgemaster
Nightmare
Astaroth
Cervantes
Raphael
Tira
Hilde
Algol
Dampierre
Zwei
Viola
Pyrrha
Omega Pyrrha
Patroklos
Alpha Patroklos
Natsu
Xiba
Leixia
Aeon
Yoshimitsu
Elysium
Kilik
Devil Jin
Ezio

Thank you very much, Sectus. But how to open the motions use the noesis? I need some help.
## Post #14
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-02-08T00:01:33+00:00
- Post Title: Soul Calibur 5

> Reply from DeathBillZhao
>
> Thank you very much, Sectus. But how to open the motions use the noesis? I need some help.
I don't think the movesets can be opened with any program.
## Post #15
- Username: DeathBillZhao
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Aug 28, 2011 4:11 pm
- Post datetime: 2012-02-08T04:09:59+00:00
- Post Title: Soul Calibur 5

> Reply from Sectus
>
> DeathBillZhao wrote:Thank you very much, Sectus. But how to open the motions use the noesis? I need some help.
I don't think the movesets can be opened with any program.

The noesis can open the animation perfectly such as FBX. So I think the motions can be open by the noesis, too. But it seems that we need more work...

Sorry for my poor english...
## Post #16
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-02-08T20:32:47+00:00
- Post Title: Re: Soul Calibur 5

> Reply from DeathBillZhao
>
> The noesis can open the animation perfectly such as FBX. So I think the motions can be open by the noesis, too. But it seems that we need more work...

Sorry for my poor english...
Can noesis open the animations for SC4? They're in the same format, so if that wasn't possible, it definitely isn't possible with SC5.
## Post #17
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-02-08T23:44:02+00:00
- Post Title: Re: Soul Calibur 5

> Reply from DeathBillZhao
>
> Sectus wrote:DeathBillZhao wrote:Thank you very much, Sectus. But how to open the motions use the noesis? I need some help.
I don't think the movesets can be opened with any program.

The noesis can open the animation perfectly such as FBX. So I think the motions can be open by the noesis, too. But it seems that we need more work...

Sorry for my poor english...

First you have to figure out the format of the motion files and then you can make a plugin to export it.
## Post #18
- Username: viprtwo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 09, 2012 11:28 am
- Post datetime: 2012-02-09T18:47:17+00:00
- Post Title: Re: Soul Calibur 5

I was totally looking for a topic like this. Thank you.

however, this will be my first time looking into any of this type of information. What do these mods ultimately do to the game?

My understanding is 

1. export savegame data from PS3 to computer
2. extract data to CPK files
3. mod the data.
4. Reimport back to your PS3.

is that sound about right?

thanks for your help.
## Post #19
- Username: skytoast
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jan 31, 2010 6:12 pm
- Post datetime: 2012-02-10T05:29:08+00:00
- Post Title: Re: Soul Calibur 5

We are not talking about editing savegames here.  cpk files are packaged containers that have the binary files for the game itself.  Its the contents which are being changed then repackaged then sent back to the game to play on the console, mostly to change features like user created textures, equipments, etc.  Most of whats being discussed is on xbox but it'll be similar on PS3.
## Post #20
- Username: omgyouredead
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Feb 13, 2012 5:51 am
- Post datetime: 2012-02-12T22:06:13+00:00
- Post Title: Re: Soul Calibur 5

Just registered, been using this place as a resource for awhile.  Special thanks to everybody posting in this and the SC4 thread.

I decided today to attempt to bin-shuffle my way into Ezio's style for created characters in SC5. I simply replaced a bin file (2, Maxi's & Voldo's actually) with Ezio's inside motion.cpk, and repacked. This seemed at first glance to have gotten me Ezio's moves out of these characters (and customs based on them), but i notice that Maxi's/Voldo's/custom's B+Y distance attack (Ezio's) is not having any effect on my opponent when I use it, even though it's happening graphically. Also, minor skeleton-visible issues with swapping motion files.  Would love some input on this if anybody else has experimented with it, though I do understand that these files are not editable at the moment, so other than crude fileswap there might not be much to say.

Found a youtube video that seems to have accomplished placing Ezio's moves in their entirety onto another character, but I'm guessing it was done in creation.cpk instead of motion.cpk, which would place another game face on Ezio's moves, but still in a non-character-creation-friendly spot.
## Post #21
- Username: 652845095
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 31, 2011 12:22 pm
- Post datetime: 2012-02-14T08:33:21+00:00
- Post Title: Re: Soul Calibur 5

what does it mean? "change the 03 of the character next to D to 2E" no ideas about how to use hxd.....
## Post #22
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-02-14T11:22:30+00:00
- Post Title: Re: Soul Calibur 5

> Reply from omgyouredead
>
> Just registered, been using this place as a resource for awhile.  Special thanks to everybody posting in this and the SC4 thread.

I decided today to attempt to bin-shuffle my way into Ezio's style for created characters in SC5. I simply replaced a bin file (2, Maxi's & Voldo's actually) with Ezio's inside motion.cpk, and repacked. This seemed at first glance to have gotten me Ezio's moves out of these characters (and customs based on them), but i notice that Maxi's/Voldo's/custom's B+Y distance attack (Ezio's) is not having any effect on my opponent when I use it, even though it's happening graphically. Also, minor skeleton-visible issues with swapping motion files.  Would love some input on this if anybody else has experimented with it, though I do understand that these files are not editable at the moment, so other than crude fileswap there might not be much to say.

Found a youtube video that seems to have accomplished placing Ezio's moves in their entirety onto another character, but I'm guessing it was done in creation.cpk instead of motion.cpk, which would place another game face on Ezio's moves, but still in a non-character-creation-friendly spot.
An easier way would be to do this via editing the savegame. If you're talking about the video I'm thinking about, that was done via savegame editing. I personally don't know the steps to do that though.
## Post #23
- Username: viprtwo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 09, 2012 11:28 am
- Post datetime: 2012-02-15T20:58:20+00:00
- Post Title: Re: Soul Calibur 5

so just to confirm,

In order to swap models, or objects on a PS3, the ps3 needs to be modded too?
## Post #24
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-02-16T19:39:25+00:00
- Post Title: Re: Soul Calibur 5

> Reply from viprtwo
>
> so just to confirm,

In order to swap models, or objects on a PS3, the ps3 needs to be modded too?
Yes.
## Post #25
- Username: khanbot
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Dec 13, 2011 6:12 pm
- Post datetime: 2012-02-21T06:51:50+00:00
- Post Title: Re: Soul Calibur 5

hi
is it possible for someone to post a tutorial to get a high quality render from these models in max?  Please?
## Post #26
- Username: ineteye
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Apr 09, 2008 8:41 pm
- Post datetime: 2012-06-12T18:09:11+00:00
- Post Title: Re: Soul Calibur 5

Hi! Some one extract weapons or use in Noesis?... Noesis shows errors on weapons....
## Post #27
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-06-17T22:27:01+00:00
- Post Title: Re: Soul Calibur 5

> Reply from ineteye
>
> Hi! Some one extract weapons or use in Noesis?... Noesis shows errors on weapons....
[http://www.tombraiderforums.com/showpos ... tcount=135](http://www.tombraiderforums.com/showpost.php?p=6078607&postcount=135)
## Post #28
- Username: That Typical Guy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 20, 2012 1:16 am
- Post datetime: 2012-06-19T17:19:52+00:00
- Post Title: Re: Soul Calibur 5

Heya guys!
So I found this thread after searching for some stuff on how to mod Soul Calibur 5. My question is: How can I extract the Character Voices / Speech Files from the game? I've got the .cpk's and unpacked the voice.cpk but there are tons of .bin files wich Noesis won't recognize and I don't know if xbdecompress can, though I might just be doing it wrong.

Any help would be greatly appreciated!
## Post #29
- Username: andthen619
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 18, 2010 7:43 pm
- Post datetime: 2012-08-15T17:12:53+00:00
- Post Title: Re: Soul Calibur 5

anyone know how to do mods for this game... saw a bunch of crazy ones here but don't know how to do it
[http://ayasuke.exblog.jp/18326596/](http://ayasuke.exblog.jp/18326596/)
[http://ayasuke.exblog.jp/18311608/](http://ayasuke.exblog.jp/18311608/)
[http://ayasuke.exblog.jp/18483382/](http://ayasuke.exblog.jp/18483382/)
## Post #30
- Username: misquared
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Oct 26, 2010 8:32 am
- Post datetime: 2012-10-22T15:36:44+00:00
- Post Title: Re: Soul Calibur 5

Hey guys!

Does anyone have the solo model of Pyrrha Omega? and her Soul weapons? (Shield and Sword)


I'm planning to open them in noesis. But my PC can't take anymore space to accumulate all the characters
## Post #31
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2013-05-20T17:56:17+00:00
- Post Title: Re: Soul Calibur 5

someone requested I take screenshots of the character palettes in sc5, like I did in sc4
[viewtopic.php?p=44157#p44157](http://forum.xentax.com/viewtopic.php?p=44157#p44157)

you can get the sc5 screenshots here
[http://www.gamefront.com/files/23328333 ... nshots.zip](http://www.gamefront.com/files/23328333/sc5_screenshots.zip)

if you do happen to fix up any models please share them on my new forum
[http://s13.zetaboards.com/digiplay/index/](http://s13.zetaboards.com/digiplay/index/)

I want to start building content on it again

-thanks
mariokart64n
## Post #32
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-05-22T17:34:19+00:00
- Post Title: Re: Soul Calibur 5

Can someone re upload this file to another hosting service pls? I'm having problems to download the zip file >_<'

Anyway, thanks Mario.

Edit: Don't worry, those assholes blocked Mexico, I found a way on how to download crap from their servers..
## Post #33
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2013-11-21T02:57:30+00:00
- Post Title: Re: Soul Calibur 5

Just bumping this to note that Soul Calibur: Lost Swords uses the same file formats as SC5.

[http://www.tzarsectus.com/SC5/NMDtool.exe](http://www.tzarsectus.com/SC5/NMDtool.exe) - I updated this tool with a couple of features. It can now extract textures from PS3 NMD files (I don't know if replacing textures works, I don't have a modded PS3 to test that). It also supports converting NMD files between the 360 and PS3 versions.
## Post #34
- Username: WorryMan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Nov 16, 2015 3:13 am
- Post datetime: 2015-11-15T19:20:42+00:00
- Post Title: Re: Soul Calibur 5

Sorry guys, i am pretty late to the party. I am struggling to put a custom .cpk file for a xbox360 version of SC5, i unpacked the iso, putted in the modded .cpk, repack the iso, mount it.
The game loads fine, but as soon as i get to the CAS menu and try to create a female character, i get an endless loading screen.

I'm almost sure this post won't be seen by anyone (my hope would be a sectus reply since he seems to have a greater knowledge of the game than anyone else) considering it's a 3 y.o post and you all probably have lost interest in the game modding.

I know there's a patched mod for SC5 on the xbox360 already, but i sincerely find it stupid to buy a new console just to make this mod work. Please help.

Here's the custom .cpk i am trying to put into SC5:
[http://360full.net/topic/94030-soul-cal ... de-mod-12/](http://360full.net/topic/94030-soul-calibur-v-nude-mod-12/)
## Post #35
- Username: THESIERRAMAN
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Jun 06, 2012 4:31 am
- Post datetime: 2023-01-19T06:16:25+00:00
- Post Title: Re: Soul Calibur 5

Hi, Any idea how to extract models, voices scenarios etc. from Soul Calibur 5 PS3 version? I have the the humans, weapon, voices.cpk etc. but I can't extract anything from them.

Thanks
