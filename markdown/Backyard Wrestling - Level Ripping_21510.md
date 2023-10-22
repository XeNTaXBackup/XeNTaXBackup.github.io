## Post #1
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-12-18T00:37:17+00:00
- Post Title: Backyard Wrestling - Level Ripping

Hey guys,
since the extraction of rigged characters and most of the textures worked out so great, I wanted to thank the forum members that made these scripts for me. THANK YOU ALL VERY MUCH!    

Now I want to know if its possible to rip the level files. With albinoleopards script I could extract the main archive and convert all the models to .3ds files. (Scripts can be found here: [viewtopic.php?f=16&t=19370&p=157960#p157960](https://forum.xentax.com/viewtopic.php?f=16&t=19370&p=157960#p157960) )

I've found out that all of one levels models are stored in a bigger .mesh file when extracting the main archive. Heres a list:

FILE NAME_______________FILE SIZE_______________LEVEL
96.mesh_________________2.189 KB________________Backyard
107.mesh________________3.462 KB________________Truck Stop
118.mesh________________3.524 KB________________Mansion
129.mesh________________2.741 KB________________Gentlemans Club
140.mesh________________2.756 KB________________Mall
151.mesh________________2.944 KB________________Slaughter House
161.mesh________________2.662 KB________________TV Studio
171.mesh________________2.563 KB________________TV Studio 2
181.mesh________________3.522 KB________________Mansion 2

Inbetween those numbers are a couple .data files that may contain textures and other information about the level......11 data files to be exact.
A script to extract the games textures can be found here: [viewtopic.php?f=18&t=21387](https://forum.xentax.com/viewtopic.php?f=18&t=21387)

Back in the day when I've found albinoleopards scripts, I came up with my own list for the first levels .mesh files contents:

```

001=floor?
002=wall?
003=ceilling?
004=wall2?
005=wall3?
006=wall4?
007=plane?
008=45plank?
009=BBQGrill
010=BBQGrillTop
011=TreehouseTree
012=45plank?
013="
014="
015="
016=shackles?
017=plane?
018=pylone?
019=treeleavesplane?
020=plane?
021=pylone2?
022=planesheer?
023=grassleave?
024=pylone3?
025=45plane?
026=mattress
027=ClutterCan1
028=ClutterCan2
029=ClutterCan3
030=cartrunk
031=carhood
032=carwindshield?
033=carrearwindow?
034=carbase
035=carbumper
036=houseladder
037=shoppingcart
038=skybox?
039="
040=electricitybox?
041=swingingcouchplank
042=frameswingingcouch
043=frameswingingcouch2
044=pillowswingingcouch
045=swingingcouch
046=?
047=boat
048=plane?
049=brickstack1
050=brickstack2
051=step?
052=step2?
053=bigplane?
054=?
055=?
056=?
057=box?
058="
059="
060="
061=trashmetal?
062=box?
063=treeleaves?
064=treeleaves2?
065=45box?
066=ClutterCan4
067=ClutterCan5
068=ClutterCan6
069=trashmetal?
070=box?
071=box?
072=treehouseplank?
073="?
074=plane?
075="?
076=smallplane?
077=pylone4?
078=ClutterCan7
079=Brickstack3
080=Brickstack4
081=fence?
082=fence2?
083=steelchair
084=box?
085=box?
086=pylone5?
087=Lighttube1
088=Lighttube2
089=Lighttube3
090=plane?
091=plane?
092=plane?
093=pylone6?
094=plane?
095=pylone7?
096=plane?
097=plane?
098=plane?
099=planecover?
100=boat2
101=pillarbroken
102=pillar
103=brickstack5
104=pillarbroken2
105=pillar2
106=bendplane?
107=thickplane?
108=thickplane?
109=thickplane?
110=thickplane?
111=thickplane?
112=trashcan
113=box?
114=box?
115=trashcancover
116=smallthickplane?
117=smallthickplane?
118=smallthickplane?
119=thickplane?
120=box?
121=box?
122=basketball
123=barbedwirebattop
124=barbedwirebatlow
125=treeleaves?
126=treeleaves?
127=treeleaves?
128=traintrack
129=treeleaves?
130=backgroundhouse
131=bendmetalfence?
132=?
133=hilllow?
134=hilllow2?
135=treeleaves?
136=treeleaves?
137=treeleaves?
138=treeleaves?
139=traintrack2
140=traintrack3
141=traintrack4
142=traintrack5
143=hillpart?
144=hillpart?
145=hillpart?
146=doubleplane?
147=hillpartlong?
148=hillpartlong?
149=hillpartlong?
150=hillpartlong?
151=treeleaves?
152=treeleaves?
153=smallplank?
154=clothline?
155=wallplane?
156=wallplane?
157=wallplane?
158=smallplank?
159=wallplane?
160=trainloknwheels
161=traincarriages
162=nakedtree
163=treeleavesortrash?
164=steelchair2
165=box?
166=box?
167=tire
168=box?
169=box?
170=tire2
171=box?
172=box?
173=fuelcan
174=tablelegsplate
175=tablelegs
176=brokentable1?
177=brokentable2?
178=tablelegsplate2
179=tablelegs2
180=tablelegs3
181=brokentable3?
182=tablelegsfull
183=tablelegsplate2
184=brokentable4?
185=swingingcouchpillow?
186=box?
187=carpentertablelegsbroken1
188=carpentertablelegs1
189=carpentertablelegsbroken2
190=roofplane?
191=plank?
192=plank?
193=stickweapon1?
194=stickweapon2?
195=stickweapon3?
196=stickweapon4?
197=stickweapon5?
198=stickweapon6?
199=box?
200=plane?
201=fridge
202=traintrack6
203=cartripod1
204=cartripodalt1?
205=rig1?
206=cartripod2
207=cartripodalt2?
208=rig2?
209=cartripodalt3?
210=cartripod3
211=hillpartlong?
212=hillpart?
213=hillpartbend?
214=hillpartbend?
215=skybox?
216=plane?
217=flatbox?
218=roundplatform?
219=smallbox?
220=boiler?
221=mattress2
222=palespike?
223=cardoorweapon
224=box?
225=box?
226=cardboardbox?
227=lframe1(tagbonusgame)
228=lframe2
229=lframe3
230=lframe4
231=lframe5
232=lframe6
233=lframe7
234=lframe8
235=lframe9
236=lframe10
237=lframe11
238=lframe12
239=brokentable1
240=brokentable2
241=tablelegsfull1
242=tablelegsfull2
243=box?
244=box?
245=box?
246=box?
247=boxingbag
248=box?
249=doublerail?
250=roofpart
251=roundplatform2?
252=boxhollow?
253=bendplank1?
254=bendplank2?
255=box?
256=box?
257=pole1?
258=flashlight?
259=pole2?
260=bird?
261=plane?
262=plane?
263=cardboardbox?
264=bigfueltank?
265=bigfueltank?
266=boiler?
267=boiler?
268=roundtablesth?
269=roundtablesth?
270=pole?
271=roundtablesth?
272=longcardboardbox?
273=smallpolesth?
274=carinterior
275=pole?
276=pole?
278=floorplane?
279=floorplane?
280=longbox?
281=longbox?
282=longbox?
283=carfrontbumper
284=boatpart?
285=backgroundboxes?
286=symetrical???
287=crossplane?
288=crossplane?
289=crossplane?
290=crossplane?
291=Hayburnsxxx
292=edgedstick?
293=roofplane?
294=smallroofplane?
295=houseroofpanel
296=groundbrickwall?
297=houseroofpanel2
298=edgedstick?
299=houseroofplank?
300=topplane?
301=shortplank?
302=houseroofjimney?
303=houseroofplane?
304=smallhouseroofplane?
305=backgroundhouse2
306=crossplane?
307=garagetiles?
308=footpath?
309=hillsidelongsteps?
310=crossplane?
311=crossplane?
312=footpath?
313=backgroundhouselowpoly
314=roofplank?
315=roofplank?
316=roofplank?
317=garageroof
318=hillsidelongmoresteps?
319=crossplane?
320=crossplane?
321=crossplane?
322=hillsidelongevenmoresteps?
323=roofpath?
324=verticallongpath?
325=tallbox?
326=housedoorframe?
327=longverticalpath?
328=longbox?
329=longbox?
330=longbox?
331=crossplane?
332=byfence1
333=byfence2
334=byfence3
335=byfence4
336=byfence5
337=roofbox?
338=verticalplane?
339=roofplane?
340=brokenroofboard
341=brokenroofboard
342=byhouseroof
343=neighborhouseroof
344=houseroofmetalplane
345=crossplane?
346=byfence6
347=byfence7
348=byfence8
349=byfence9
350=byfence10
351=byfence11
352=byfence12
353=byfence13
354=bytree1
355=bytree2
356=bush1
357=bytree3
358=bush2
359=bush3
360=roofplane?
361=bgwall?
362=crossplane?
363=hillsidebottomcorner?
364=crossplane?
365=traintracksx
366=hillsidemiddel?
367=traintracksx
368=hillsidemiddel?
369=crossplane?
370=crossplane?
371=crossplane?
372=traintracksx
373=hillsidemiddel?
374=crossplane?
375=crossplane?
376=doubleplane?
377=hillsideshort?
378=traintracksx
379=doubleplane?
380=plane?
381=plane?
382=plane?
383=plane?
384=plane?
385=plane?
386=plane?
387=plane?
388=plane?
389=plane?
390=plane?
391=plane?
392=crossplane?
393=crossplane?
394=crossplane?
395=crossplane?
396=crossplane?
397=crossplane?
398=crossplane?
399=crossplane?
400=crossplane?
401=crossplane?
402=neighborhouseroof?
403=tallplane?
404=crossplane?
405=crossplane?
406=crossplane?
407=crossplane?
408=crossplane?
409=crossplane?
410=backyardbigfloor?
411=crossplane?
412=longbox?
413=ramp?
414=smallramp?
415=cutplane?
416=smallbox?
417=crossplane?
418=hillsidelong?
419=hillsidelong?
420=boatseatdashboard
421=boattrailerstand?
422=roofplank?
423=housewallpart?
424=housewindowwallparts?
425=shortroofplank?
426=housefront
427=doubleangledroofplanks?
428=metalroofplane
429=housewall?
430=housewall?
431=bigbox?
432=bigbox?
433=windowwallpart
434=hillside?
435=hillside45?
436=doubleplane?
437=longtraintracks
438=doubleplane?
439=doubleplane?
440=traintrackslong
441=traintracks
442=hillsideshort45?
443=hillside?
444=hillsideshort45?
445=hillside?
446=traintrackslong
447=doubleplane?
448=longplane?
449=longplane?
450=byfloorneighbor?
```


......this took quite a while haha

I now kindly want to ask you guys again to help me export the games levels. I can provide you with this list and the files for the backyard level. There should be positions/locations in the .mesh file ,right?
Heres the files that go with level.96 backyard:
[https://cdn.discordapp.com/attachments/ ... _Level.zip](https://cdn.discordapp.com/attachments/656650335858720798/656654887987314699/Backyard_Level.zip)

I gave it a try with rdtechladys guide on ripping ps2 games.....the models always come out distorted and double just slightly above themselfes......so it would take forever to get them right and clean....just to have something not very ideal or close to the original...
heres a screenshot of that progress, though:


With all that being said, i want to thank you guys again for being such an awesome community and helping others like me getting there hands on some models to share with everybody 
thank you for reading this.
Peace
## Post #2
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-12-24T11:05:55+00:00
- Post Title: Backyard Wrestling - Level Ripping

*christmas bump*  
Merry christmas everyone
## Post #3
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-01-05T18:10:02+00:00
- Post Title: Backyard Wrestling - Level Ripping

Did anyone give it a try?
## Post #4
- Username: Starbrain
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Nov 27, 2017 7:41 pm
- Post datetime: 2020-01-16T16:10:40+00:00
- Post Title: Backyard Wrestling - Level Ripping

I gave it a try with the provided scripts. As Blender can't open the level .mesh files (getting various error messages), i converted them to .3ds format with the bms script. The meshes look just fine in Noesis, but i am stuck since there is no script/tool to handle the correct placement of all objects. Or am i missing something here?
## Post #5
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-01-18T04:08:28+00:00
- Post Title: Backyard Wrestling - Level Ripping

> Reply from Starbrain ↑Fri Jan 17, 2020 12:10 am at Fri Jan 17, 2020 12:10 am
>
> 
(...) there is no script/tool to handle the correct placement of all objects. Or am i missing something here?

That's the point!
I was hoping that the provided Information was enough to make mass importing the submeshes with the right coordinates relatively easy for the mighty shakotay2 or bigchillghost.
So far we only have Albino Leopards script that extracts 3d models and textures out of BYWs Main Archive.
Ohh and luckily the character Format has been figured out aswell 

I just hope however that a skilled Person or at least a Trained eye is gonna have a look at it and get us closer to ripping BYWs levels.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-18T09:50:48+00:00
- Post Title: Backyard Wrestling - Level Ripping

> Reply from Henchman800 ↑Wed Dec 18, 2019 8:37 am at Wed Dec 18, 2019 8:37 am
>
> I gave it a try with rdtechladys guide on ripping ps2 games.....the models always come out distorted and double just slightly above themselfes......so it would take forever to get them right and clean....just to have something not very ideal or close to the original...So the distorted objects have correct positions/translations?

Then it should be possible to extract those position/translation values from each object and apply them to the intact ones in FurryFan's .3ds files.
(just as a thought - should be easier than to deal with that strange bms script  )

> just to have something not very ideal or close to the original...I don't understand - looks much better to me than the edgy objects in the 3ds files:
.



96-mesh.png (53.84 KiB) Viewed 101 times
## Post #7
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-01-20T14:37:26+00:00
- Post Title: Backyard Wrestling - Level Ripping

> I don't understand - looks much better to me than the edgy objects in the 3ds files
Haha danke man!
I did my pest to clean out everything in the frame. The resulting mesh comes out as one object and i use a subsurf modifier along with some sharp edges and a nice hdri for lightning......so this might be the reason u prefer my image over the straight extracted map objects 

Did you take a look at the files bms scripts? im afraid they dont help that much, right? objects come out with wrong scaling and positions. they are the correct ones with correct uvs and all that. the best thing would be to have a script that puts them all in one .obj with correct rotation/position/scale....
is there any info in the .mesh file that might give position data?

Thx for participating here man
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-20T14:57:11+00:00
- Post Title: Backyard Wrestling - Level Ripping

> Reply from Henchman800 ↑Mon Jan 20, 2020 10:37 pm at Mon Jan 20, 2020 10:37 pm
>
> is there any info in the .mesh file that might give position data?Dunno.
In case you used only a .mesh (and no other files) with the "rdtechladys guide on ripping ps2 games" I'd say 'yes'.

btw: there's bounding boxes I guess, but they won't help too much:
.



bbox.jpg (128.76 KiB) Viewed 82 times
## Post #9
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-01-20T17:56:02+00:00
- Post Title: Backyard Wrestling - Level Ripping

[https://youtu.be/iHlJ3qO4lys](https://youtu.be/iHlJ3qO4lys)
Thats rdladys tutorial. The result is basically a 3d-screenshot. However it has a hard time trying to mimic the 3rd axes.

Yeah, the bounding Boxes make up a big Portion of what i Found within the .mesh file.
Is there also names scattered in there?
Or are the positionvalues just randomly placed?
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-20T19:25:33+00:00
- Post Title: Backyard Wrestling - Level Ripping

> Reply from Henchman800 ↑Tue Jan 21, 2020 1:56 am at Tue Jan 21, 2020 1:56 am
>
> Is there also names scattered in there?Search for "MIP_" for example in 96.mesh gives 212 findings.

> Or are the positionvalues just randomly placed?You mean that "position data"? There's some "suspects"; I'll try that out when I have time

well, I always know this script of mine would come in handy sooner or later (1.5 years later  ):

> Reply from shakotay2 ↑Fri Jul 13, 2018 3:03 am at Fri Jul 13, 2018 3:03 am
>
> 

(and I really fear to have a deja vue facing the ordering problem again, shxt)
## Post #11
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-01-20T20:46:20+00:00
- Post Title: Backyard Wrestling - Level Ripping

Sorry, i didnt quite get it.....the scripts i uploaded are yours?

EDIT:
Sorry.....i just used the arrow in the quote field^^


I just saw this! So you already Made it Happen before!
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-20T20:49:52+00:00
- Post Title: Backyard Wrestling - Level Ripping

nooo, I linked to a blender script of mine (for REO) in my previous post
## Post #13
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-01-20T20:56:19+00:00
- Post Title: Backyard Wrestling - Level Ripping

So you wanna use the same method for backyard wrestling?

> Search for "MIP_" for example in 96.mesh gives 212 findings.
The .mesh-file Exports 450 models though.....might the 212 mip-assets just be the bounding boxes?
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-20T21:02:07+00:00
- Post Title: Backyard Wrestling - Level Ripping

> Reply from Henchman800 ↑Tue Jan 21, 2020 4:56 am at Tue Jan 21, 2020 4:56 am
>
> 
So you wanna use the same method for backyard wrestling?Would make sense to me - but it requires the above mentioned "suspects" to be the position data we need...

> The .mesh-file Exports 450 models though.....might the 212 mip-assets just be the bounding boxes?who knows? You need to analyze the mesh file to find it out.
(guess there's 450 bBoxes...)
## Post #15
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-01-20T22:13:29+00:00
- Post Title: Backyard Wrestling - Level Ripping

> Reply from shakotay2 ↑Tue Jan 21, 2020 5:02 am at Tue Jan 21, 2020 5:02 am
>
> You need to analyze the mesh file to find it out.
(guess there's 450 bBoxes...)

I dont Think so. The Arena is limited to whats fenced and a little space on the car, treehouse and Porch roof.
Theres gotta be reference on the scaling of the submeshes itself aswell.
The other files i delivered Contain Sounds and textures.....at least two of them do.....i dont know about the others...
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-21T22:04:09+00:00
- Post Title: Re: Backyard Wrestling - Level Ripping

This is what I got and it looks more "exploded" than correctly moved:
.



96-mesh exploded.png (93.42 KiB) Viewed 94 times


(there's a certain chance that the offsets where assigned to the wrong objects)
Because I don't have any clue about the "ordering rules" of
for curSelObj in bpy.data.objects:
(some oddities when logging the filenames, need to check that)

Another possibility: the offsets are not the offsets we search for.

(btw: first 6 offsets are identical, but that's not the problem here, I think.)
## Post #17
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-01-22T06:39:06+00:00
- Post Title: Re: Backyard Wrestling - Level Ripping

> Reply from shakotay2 ↑Wed Jan 22, 2020 6:04 am at Wed Jan 22, 2020 6:04 am
>
> 
This is what I got and it looks more "exploded" than correctly moved

Haha omg yeah....can't really make out, if just any object is placed right ^^
Shouldn't the order just be like the 3ds-files list i posted?
Im super excited for your next try man
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-22T13:59:28+00:00
- Post Title: Re: Backyard Wrestling - Level Ripping

yeah, I had a bug where about 25 objects didn't "follow the rules" which spoiled the whole thing - fixed and set them to absolute position 0.0 0.0 0.0 (+ rel pos) all.
.



96 mesh, 2nd try.png (58.67 KiB) Viewed 87 times


rotations (if any) not applied; chair need to be rotated by 90° for example (in one axis at least)
## Post #19
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-01-23T15:21:37+00:00
- Post Title: Re: Backyard Wrestling - Level Ripping

> Reply from shakotay2 ↑Wed Jan 22, 2020 9:59 pm at Wed Jan 22, 2020 9:59 pm
>
> 
yeah, I had a bug where about 25 objects didn't "follow the rules" which spoiled the whole thing - fixed and set them to absolute position 0.0 0.0 0.0 (+ rel pos) all.
rotations (if any) not applied; chair need to be rotated by 90° for example (in one axis at least)

(Sorry...im doing this from my phone, cuz im filming in another city   )

The stuff i marked red seem to have the right Positions! Great job man  

You seem to have the Hollywood Swing correct already 
The long planes on your screenshots right hold Alpha Images as grass leaves.
Ohhh man, we are so close 
Thank you for putting work into it man 

EDIT: some of the objects should share the same location, singe they are demaged versions of destructable objects. Like the porch pillars, house Walls and the boat.
## Post #20
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-02-21T02:09:56+00:00
- Post Title: Re: Backyard Wrestling - Level Ripping

> Reply from shakotay2 ↑Wed Jan 22, 2020 9:59 pm at Wed Jan 22, 2020 9:59 pm
>
> 
yeah, I had a bug where about 25 objects didn't "follow the rules" which spoiled the whole thing - fixed and set them to absolute position 0.0 0.0 0.0 (+ rel pos) all.

So is there two ways of storing coordinates and Rotation data for objects in the level files?

> Reply from shakotay2 ↑Wed Jan 22, 2020 9:59 pm at Wed Jan 22, 2020 9:59 pm
>
> 
EDIT: some of the objects should share the same location, singe they are demaged versions of destructable objects. Like the porch pillars, house Walls and the boat.

...or this table

Could (if there is) two ways of coordinate/Rotation storage be used for positioning Static objects and the ones that are moved by physics/animation?
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-02-21T12:02:42+00:00
- Post Title: Re: Backyard Wrestling - Level Ripping

> Reply from Henchman800 ↑Fri Feb 21, 2020 10:09 am at Fri Feb 21, 2020 10:09 am
>
> 
So is there two ways of storing coordinates and Rotation data for objects in the level files?Why do you think so?
I dunno, I somehow lost the focus on the problem after 4 weeks - there's hundreds of 15 minutes jobs I do (well, to be honest, this one was a two hours job plus a hard week of research for REO in summer 2018  ).

You may have a look for yourself at the result:
[2nd-try-load_3ds.zip](http://www.uploadmb.com/dw.php?id=1582285846)

move script:

```
                #print(vertex.co)           
                vertex.co.x += xpos[i]; vertex.co.y += ypos[i] ; vertex.co.z += zpos[i]
            i += 1

```

well, had another look at this and surprisingly it's only two objects which don't "follow the rules" (don't have the search signature for the pos offset, in the 96.mesh file)
(Can't recall about the 25 objects I spoke of before. I expanded/changed the signature once or twice - maybe it was simply wrong before, who knows...  )
## Post #22
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-02-21T16:36:06+00:00
- Post Title: Re: Backyard Wrestling - Level Ripping

> Reply from shakotay2 ↑Fri Feb 21, 2020 8:02 pm at Fri Feb 21, 2020 8:02 pm
>
> 
Why do you think so?
Since there is two categories of objects:
-static meshes like the house or the trees
-moveable objects like weapons and damaged versions

To be honest...i dunno...

> well, to be honest, this one was a two hours job plus a hard week of research for REO in summer 2018  .

Danke dir dafür alter 
Vorallem dafür, dass du deine Zeit nicht nur für mein Fan Projekt, sondern auch für alle community Mitglieder opferst um so etwas möglich zu machen.
Danke!


> You may have a look for yourself at the result

I definitely will!
Im pretty busy with finishing a movie till Deadline on 28th of February, though.
However i might load it into blender tonight
