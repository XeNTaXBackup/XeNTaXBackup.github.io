## Post #1
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-08-21T16:53:59+00:00
- Post Title: hex2obj and maxscript?

well, from the beginning I was thinking of improving hex2obj (view link in my sig) in a "variable way"
to get better access to more complex model formats.

Why not making it capable of loading/executing phyton scripts for example?
But I quickly realized that it would make no sense -trying- to create a Noesis clone.

Another thought was to supply a bunch of max script templates for a special kind of models each.

So analyzing with hex2obj and then manually transferring the results to the best fitting template.

Finally ending up having a "create max script" button in hex2obj (years later, hehehe)

To give this new idea a start I made a max script for pcmesh faceindices then realized it could be simply
done using hex2obj with DWORD faceindices selected.

So this is the second try (on another format, *.pb), thus the scripts named tple2.ms (faceshape) and tple2b.ms (hair)
to be used with luci.pb only from this thread: [viewtopic.php?f=29&t=10894&start=15](http://forum.xentax.com/viewtopic.php?f=29&t=10894&start=15), post as of 8-19-2014

load luci.pb, and enter an obj file name where the results are to be saved to.
tple2.ms, faceshape

```
function ReadModelFile fName file_out=
(		
    format "-- START READING MODEL FILE --\n"
    stream = fOpen fname "rb"			-- Open the file for reading
    fSeek stream 0x7DA8C #seek_set 		-- start of vertices
    for k=1 to 8 do (							-- 8: submesh count
		print ("@ 0x"+ bit.intAsHex(ftell stream) as string)
	    for i=1 to 24 do (						-- a vertex count of 24 doesn't apply to all submeshes!
	        x  = readFloat stream
		    y  = readFloat stream
	        z  = readFloat stream
            format "v % % %\n" x y z to:file_out
        )
		format "#\n" to:file_out
        fSeek stream 512 #seek_cur			-- meet next submesh
    )
	for i=1 to 13 do (							-- a vertex count of 24 doesn't apply to all submeshes!
	    x  = readFloat stream
	    y  = readFloat stream
	    z  = readFloat stream
        format "v % % %\n" x y z to:file_out
	)

    fSeek stream 0x7D4A0 #seek_set 		-- start of face indices
	maxcnt=0
    face_cnt= 747/3
	for i=1 to face_cnt do (
		f1  = (readShort stream #unsigned) + 1
		f2  = (readShort stream #unsigned) + 1
		f3  = (readShort stream #unsigned) + 1
		if (f1>maxcnt) then maxcnt= f1
		if (f2>maxcnt) then maxcnt= f2
		if (f3>maxcnt) then maxcnt= f3
		format "f % % %\n" f1 f2 f3 to:file_out
		--print ("f " + (f1 as string) + " " + (f2 as string) + " " + (f3 as string)) to:file_out
    )
	format "max face index: %\n" maxcnt
	format "submesh count: %\n" (maxcnt/24)
    fClose stream
)

-- entry point --

ClearListener()
fname = getOpenFileName \
caption:" open 3D Model" \
types:"3D Model (*.pb)|*.pb"
--historyCategory:"3D Model pb
format "fname: %\n" fname
	
-- logging preparation
fname_out = GetSaveFileName()
if fname_out != undefined then (
   file_out = createfile fname_out
   ReadModelFile fname file_out

		--format "\n" to:file_out
   close file_out
)


```

tple2b.ms, hairmesh

```
function ReadModelFile fName file_out=
(		
    format "-- START READING MODEL FILE --\n"
    stream = fOpen fname "rb"			-- Open the file for reading
    fSeek stream 0x7ADBC #seek_set 		-- start of vertices
    for k=1 to 5 do (							-- 5: submesh count
		print ("@ 0x"+ bit.intAsHex(ftell stream) as string)
	    for i=1 to 24 do (						-- a vertex count of 24 doesn't apply to all submeshes!
	        x  = readFloat stream
		    y  = readFloat stream
	        z  = readFloat stream
            format "v % % %\n" x y z to:file_out
        )
		format "#\n" to:file_out
        fSeek stream 512 #seek_cur			-- meet next submesh
    )
	for i=1 to 13 do (							-- a vertex count of 24 doesn't apply to all submeshes!
	    x  = readFloat stream
	    y  = readFloat stream
	    z  = readFloat stream
        format "v % % %\n" x y z to:file_out
	)
	
    fSeek stream 0x7A930 #seek_set 		-- start of face indices
	maxcnt=0
    face_cnt= 570/3
	for i=1 to face_cnt do (
		f1  = (readShort stream #unsigned) + 1
		f2  = (readShort stream #unsigned) + 1
		f3  = (readShort stream #unsigned) + 1
		if (f1>maxcnt) then maxcnt= f1
		if (f2>maxcnt) then maxcnt= f2
		if (f3>maxcnt) then maxcnt= f3
		format "f % % %\n" f1 f2 f3 to:file_out
		--print ("f " + (f1 as string) + " " + (f2 as string) + " " + (f3 as string)) to:file_out
    )
	format "max face index: %\n" maxcnt
	format "submesh count: %\n" (maxcnt/24)
    fClose stream
)

-- entry point --

ClearListener()
fname = getOpenFileName \
caption:" open 3D Model" \
types:"3D Model (*.pb)|*.pb"
--historyCategory:"3D Model pb
format "fname: %\n" fname
	
-- logging preparation
fname_out = GetSaveFileName()
if fname_out != undefined then (
   file_out = createfile fname_out
   ReadModelFile fname file_out

		--format "\n" to:file_out
   close file_out
)
tple2b.ms, hairmesh

```

- Why logging the results into an obj file? 
For me this appears to be the fastest way to track down problems that might occur.



Luci_2SMs.JPG (9.72 KiB) Viewed 429 times



Missing mouth/nose to be found here: [viewtopic.php?f=16&t=11580&p=95322&hili ... 318#p95322](http://forum.xentax.com/viewtopic.php?f=16&t=11580&p=95322&hilit=luci_mask.h2o&sid=28902efff3e04b715b6dbe9206f10318#p95322)
## Post #2
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2014-08-21T21:36:20+00:00
- Post Title: hex2obj and maxscript?

How did you figure out the submesh and submesh vertex counts?
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-23T21:28:03+00:00
- Post Title: hex2obj and maxscript?

here's another template (for Fung Wan vkm) due to a user request.
converts .vkm to .obj but only the first submesh. For some reason it failed when run from the MAXScript Editor
so you'll need to start the script using the "Run Script" button.

MAXScript Listener output:

fname: C:\Users\username\Documents\PC18Body.vkm
-- START READING MODEL FILE --
face_count: 410
max face index: 307

```
(      
    format "-- START READING MODEL FILE --\n"
    stream = fOpen fname "rb"         -- Open the file for reading
    fSeek stream 0x74 #seek_set       -- vertex count of first submesh
    vertCount = readlong stream

   for i=1 to vertCount do (
       x  = readFloat stream; y  = readFloat stream; z  = readFloat stream
       format "v % % %\n" x y z to:file_out
       x  = readFloat stream; y  = readFloat stream; z  = readFloat stream
       format "vn % % %\n" x y z to:file_out
       fSeek stream 4 #seek_cur
       x  = readFloat stream; y  = readFloat stream;
       format "vt % %\n" x y to:file_out
       fSeek stream 8 #seek_cur	   
   )
   face_cnt = readlong stream
   format "face_count: %\n" face_cnt
   maxcnt = 0
   for i=1 to face_cnt do (
      f1  = (readLong stream)  + 1
      f2  = (readLong stream) + 1
      f3  = (readLong stream) + 1
      if (f1>maxcnt) then maxcnt= f1
      if (f2>maxcnt) then maxcnt= f2
      if (f3>maxcnt) then maxcnt= f3
      format "f %/%/% %/%/% %/%/%\n" f1 f1 f1 f2 f2 f2 f3 f3 f3 to:file_out
      --print ("f " + (f1 as string) + " " + (f2 as string) + " " + (f3 as string)) to:file_out
    )
   format "max face index: %\n" maxcnt
    fClose stream
)

-- entry point --

ClearListener()
fname = getOpenFileName \
caption:" open FW 3D Model" \
types:"3D Model (*.vkm)|*.vkm"
--historyCategory:"3D Model vkm
format "fname: %\n" fname
   
-- logging preparation
--fname_out = GetSaveFileName()
fname_out = fname + ".obj" 		-- Max 2013: doesn't work from the MaxScript editor; use "Run Script" button
if fname_out != undefined then (
   file_out = createfile fname_out
   ReadModelFile fname file_out

      --format "\n" to:file_out
   close file_out
)
```


> Is there an easy way to convert hex2obj info to maxscript?
It's not too hard but it would be time consuming.

There was the idea to directly create a maxscript from the hex2obj parameters.
But I finally used "C", i.e. the MakeH2O project which in collaboration with hex2obj can export models.

Normally you'd need a full format analysis before using maxscript.

That's the reason why I finally decided to do it in "C".

------------------------------------------------------------
Anyway, if you want to use parameters (you've found using hex2obj) with a maxscript you should look here:
[viewtopic.php?f=16&t=11090&p=118039#p118039](http://forum.xentax.com/viewtopic.php?f=16&t=11090&p=118039#p118039)
