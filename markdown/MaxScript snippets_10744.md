## Post #1
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2013-09-02T20:53:17+00:00
- Post Title: MaxScript snippets

Hi guys, I was looking on these forums to find some maxscripting topic that would have some interesting scripting but I didn't find anything. 
So if there is one, please move this topic to there, if not, I would like people that have max knowledge, interesting snippits, questions and so on about importing models into max using maxscript to drop them in this forum topic.

Thnx
T.
## Post #2
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2013-09-02T20:58:29+00:00
- Post Title: MaxScript snippets

To start out, I would like to post one script that is breaking my ass for quite some time now

So some games store their uv's in half float precision points, but Max can only deal with float precision points, 
this is used in games like TheSettlers 7, Castlevania - Lords of Shadows and so on
So here is a script that converts this half float to a float, it may not be the best script, but it did keep me up for 2 days straight!

```
(

	sign = bit.and ( bit.shift u -15 ) 0x00000001
	exponent = bit.and ( bit.shift u -10 ) 0x0000001F
	mantis = bit.and u 0x000003FF

	if (exponent == 0) then
	(
		if(mantis == 0) then
		(
			return bit.shift sign 31
		)
		else
		(
                        tmp = bit.and mantis 0x00000400
			while ( tmp !=0  ) do
			(
				mantis = bit.shift mantis 1
				exponent -=1
			)
			exponent = exponent +1	
			mantis = bit.and mantis 0x00000400 --> should be ~0x00000400
		)
	)
	if(exponent == 31) then
	(
		if( mantis ==0) then 
			return bit.or (bit.shift sign 31) 0x7F800000
		else
			return bit.or (bit.or (bit.shift sign 31) 0x7F800000 ) (bit.shift mantis 13)
	)	
	
	exponent = exponent + (127-15)
	mantis = bit.shift mantis 13
	
	val = bit.or ( bit.or (bit.shift sign 31) ( bit.shift exponent 23) ) (mantis)
	
	fOut = fopen "test.bin" "wb"
	writelong fOut val
	fflush fOut
	fclose fOut

	fIn = fopen "test.bin" "rb"
	var = readfloat fIn
	fclose fIn
	
	return var 
)

```


Enjoy

T.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-09-27T16:16:27+00:00
- Post Title: MaxScript snippets

hah, two years later!  

that's a good idea, TM   but poor people in this poor forum (me included) aren't smart enough to support such good ideas...

I'd like to show how to process multiple files with a maxscript (I'm not too familiar with ms so don't blame me).
Dunno if I ever will code the 2nd part but here's the first (modified from [http://www.rsart.co.uk/2011/07/07/maxsc ... -handling/](http://www.rsart.co.uk/2011/07/07/maxscript-image-file-handling/)):

after some beautifying you get a function which gets you the names of the model files:

```

  model_files = #()
  model_type = ".m3g"

  -- Get all the m3g files	
  diff_files = modelFolder  + model_type  
  thefiles = getfiles diff_files
	
  for f in thefiles do	
  (
    append model_files ((getfilenamefile f) + model_type)
  )

  model_files -- return this
)	

ClearListener()
process_models "K:\\Programme\\Autodesk\\3ds Max 2013\\scripts\\RR3\\*"
print model_files
```

resulting listener output:

#("2013_hyundai_wrc_a.m3g", "2013_hyundai_wrc_b.m3g", "2013_hyundai_wrc_c.m3g", "2013_hyundai_wrc_d.m3g", "2013_mclaren_mp412c_e.m3g", "2013_mclaren_mp412c_g.m3g", "2013_mclaren_mp412c_h.m3g", "tyre_standard1_tyres.m3g")
"2013_hyundai_wrc_a.m3g"
"2013_hyundai_wrc_b.m3g"
"2013_hyundai_wrc_c.m3g"
"2013_hyundai_wrc_d.m3g"
"2013_mclaren_mp412c_e.m3g"
"2013_mclaren_mp412c_g.m3g"
"2013_mclaren_mp412c_h.m3g"
"tyre_standard1_tyres.m3g"

Now you've to erase the getOpenFileName dialogue line from your maxscript,
make a function of the whole script and process all files in the model_files list
in a for loop that calls that function.

That's how I would do it. (Didn't check it but should work.)

btw. "diff" in the original code was meant for "diffuse" now it's just "different"...
## Post #4
- Username: tank
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Feb 04, 2016 11:11 pm
- Post datetime: 2016-02-04T15:15:28+00:00
- Post Title: MaxScript snippets

Quite useful snippet, sometimes it is necessary to split smoothing groups into elements:

```
 * @file split smoothing groups into elements
 * @details File contains split smoothing groups to elements function realisation.
 * @author Aviator777 / Tank
 * @copyright
 * @version 1.0
 * @date 28.08.2015
 *---------------------------------------------------------------------------------------------------------------------
 */
 
 /*
 Notes:
 Use Editable Poly mode, before applying this script, apply to model autosmooth, or use appropriate smooth groups !
 */

global groupIDsUsed = #()

fn processSelection tmesh = 
(
	try 
	(
		local faceCount = tmesh.getNumFaces()
		for f = 1 to faceCount  do 
		(
			local groupID  = (polyop.getFaceSmoothGroup tmesh f)
			appendIfUnique groupIDsUsed groupID
		)

		for g = 1 to groupIDsUsed.count do 
		(
			local faceGroup = #()
			for i = 1 to faceCount do
			(
				local polygonGroupID  = (polyop.getFaceSmoothGroup tmesh i) as integer
				if polygonGroupID == (groupIDsUsed[g] as integer) do
				(
					append faceGroup i
				)
			)
			polyop.detachFaces tmesh faceGroup asNode:false
		)
		messageBox "Done !" title:"Information"
	)
	catch
	(
		print "Could not split smoothing groups into elements."
	)
)
rollout spl "Split tool" width:176 height:104
(
	button 'btn1' "Split Groups Into Elements" pos:[22,24] width:140 height:58 align:#left tooltip:"Split Polygon Smoothing Groups Into Elements"
	on btn1 pressed do
	(
		clearListener()
		sl = $selection
		if sl.count > 0 do 
		(
			processSelection sl[1]
		)
		
	)
)
createDialog spl
```


If anyone needs any help with maxscript, or any tips, I will be happy to help, have been writing scripts for maxscript for quite a while now.
