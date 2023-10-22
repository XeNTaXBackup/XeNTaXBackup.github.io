## Post #1
- Username: antidote
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Apr 02, 2010 11:37 pm
- Post datetime: 2014-02-03T04:58:00+00:00
- Post Title: Attempting to export Metroid Prime models leads to disaster

I've been attempting to export models from Metroid Prime to a Wavefront OBJ to import into Blender (my python skills are rather lacking), and while renders perfectly fine it always exports poorly. Is there anything you guys suggest I do when exporting objects?

Here are a couple pictures demonstrating my problem



EDIT: Retro seems to always use triangle strips with well over 10 vertices per strip (some face groups reaching 80 vertices)
## Post #2
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-02-03T11:24:08+00:00
- Post Title: Attempting to export Metroid Prime models leads to disaster

It looks like your indices are exported incorrectly. The OBJ format has a single set of indices for the whole file, it doesn't restart the "count" for every group.

For example:

```
v 2 2 2
v 3 3 3

g triangle1
f 1 2 3

v 0.5 0.5 0.5
v 0.7 0.7 0.7
v 0.2 0.2 0.2

g triangle2
f 4 5 6
```


So if you're exporting multiple objects, each with it's own set of indices (from 0 to x), you have to recalculate after each object and add the last vertex count to the new index values.
## Post #3
- Username: antidote
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Apr 02, 2010 11:37 pm
- Post datetime: 2014-02-03T12:31:13+00:00
- Post Title: Attempting to export Metroid Prime models leads to disaster

It can't be that then, because the CMDL format has global vertex, normal, and uv lists so the indices are correct.
[https://github.com/Antidote/MetPrimeToo ... Reader.cpp](https://github.com/Antidote/MetPrimeTools/blob/master/cmdlreader/CMDLReader.cpp)
## Post #4
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-02-03T13:06:04+00:00
- Post Title: Attempting to export Metroid Prime models leads to disaster

Could you upload the OBJ file from your screenshots?
## Post #5
- Username: antidote
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Apr 02, 2010 11:37 pm
- Post datetime: 2014-02-03T13:18:30+00:00
- Post Title: Attempting to export Metroid Prime models leads to disaster

Sure:
[http://dl.dropboxusercontent.com/u/21757902/samus.obj](http://dl.dropboxusercontent.com/u/21757902/samus.obj)
## Post #6
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-02-03T14:05:15+00:00
- Post Title: Attempting to export Metroid Prime models leads to disaster

This can't be right

```
g group0
f 1429 1400 1398 1381 1382 1383 1384 1385 
f 360 298 309 288 310 292 293 
f 1397 1427 1396 1424 1395 1423 1394 1420 1393 1419 1392 1416 1391 1415 1390 1412 1389 1411 1388 1408 1387 1407 1386 1404 1385 1403 1384 
f 503 497 351 353 288 319 292 
f 293 292 297 331 381 363 404 
f 1445 1401 1430 1402 1431 1405 1432 1406 1433 1409 1434 1410 1435 1413 1436 1414 1437 1417 1438 1418 1439 1421 1440 1422 1441 1425 1442 1426 1443 1428 1444 1429 1445 
f 1402 1403 1405 1404 1406 1407 1409 1408 1410 1411 1413 1412 1414 1415 1417 1416 1418 1419 1421 1420 1422 1423 1425 1424 1426 1427 1428 1400 1429 
f 5932 5948 5904 5933 5905 5934 
f 5930 5900 5899 5885 5898 5897 5926 
f 566 571 497 492 353 365 319 
```

Game meshes are usually optimized to have triangles only. I highly doubt this model has octogons and 27-gons  
There's probably an error in your OBJ-building code.
## Post #7
- Username: antidote
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Apr 02, 2010 11:37 pm
- Post datetime: 2014-02-03T19:07:23+00:00
- Post Title: Attempting to export Metroid Prime models leads to disaster

I've tried limiting it to three vertices per face, but I always get huge gaps in the mesh. Also with blender you can uncheck N-Gons as an option.

Also as previously stated, Retro likes to use huge triangle strips, some using up to 80 vertices.
## Post #8
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-02-03T19:34:03+00:00
- Post Title: Attempting to export Metroid Prime models leads to disaster

> Reply from antidote
>
> I've tried limiting it to three vertices per face, but I always get huge gaps in the mesh. Also with blender you can uncheck N-Gons as an option.

Also as previously stated, Retro likes to use huge triangle strips, some using up to 80 vertices.
Ah, but OBJ doesn't support triangle strips. Are you recalculating those into triangle lists? If not, that's your problem.
## Post #9
- Username: antidote
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Apr 02, 2010 11:37 pm
- Post datetime: 2014-02-03T19:47:39+00:00
- Post Title: Attempting to export Metroid Prime models leads to disaster

How would I go about doing that? TBH I'm not very experienced with 3D.
## Post #10
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-02-03T20:06:16+00:00
- Post Title: Attempting to export Metroid Prime models leads to disaster

Here's the algorithm I use in maxscript. I'm not very familiar with C, but maxscript is pretty straight-forward so you should be able to port it.

```
(
	fa = iArr[i]
	fb = iArr[i+1]
	fc = iArr[i+2]
	if ((fa!=fb) and (fa!=fc) and (fc!=fb)) do
	(
		if mod i 2 == 0  then append fArr [fa,fb,fc]
		else append fArr [fb,fa,fc]
	)
)
```

iArr is the initial array of indices (read "as is") and fArr is the resulting array of triangles
mod is Modulo arithmetic. For example, mod 2 2 = 0, and mod 3 2 = 1
## Post #11
- Username: antidote
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Apr 02, 2010 11:37 pm
- Post datetime: 2014-02-03T20:41:55+00:00
- Post Title: Attempting to export Metroid Prime models leads to disaster

I've actually managed to track it down to the Triangles, Trianglefans seem to work, Triangle strips also seem to work now, but plain triangles screw things up.
