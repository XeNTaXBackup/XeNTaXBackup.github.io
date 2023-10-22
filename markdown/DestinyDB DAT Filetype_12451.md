## Post #1
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2015-01-01T00:55:07+00:00
- Post Title: DestinyDB DAT Filetype

Hello guys, I was able to get some help from Shakotay regarding the DestinyDB GEOM/DAT model format. And have converted some of the files from GEOM into DAT files using Offzip. However I am having trouble with quite a few of the models and I am hoping that someone here could help maybe by helping to create a script either for 3ds max or QuickBMS, or adding onto the existing script so that we can convert all the DAT files over to a OBJ filetype.

 Any help would be appreciated here as myself and others I have tried to get help from are lost as far as converting anything else over to a OBJ format other than the helmet models. 

[www.uploadmb.com/dw.php?id=1419193932](http://www.uploadmb.com/dw.php?id=1419193932)

So far the current script only works for converting over the helmet models from DAT to OBJ using 3DS Max. This script is included in this download.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-01-01T14:13:50+00:00
- Post Title: DestinyDB DAT Filetype

There's a typo in my script:

if (vertStride==16) then vertex_ vertCount2 vertStride2 stream file_out

the bold '2' must be erased.

I thought you were on your way understanding maxscript.  

Seems you didn't even read the script?

I changed 3 lines to let it load LLightmail (one submesh only, didn't check for others):

```
local str = ""
	strLen = readShort stream #unsigned
    for i = 1 to strLen do 
        str += bit.intAsChar (readByte stream #unsigned)	
    str
)

fn vertex_ vertCount vertStride stream file_out= (
	for i=1 to vertCount do (
    x  = readFloat stream; y  = readFloat stream; z  = readFloat stream
    format "v % % %\n" x y z to:file_out
    -- normals skipped and maybe other data; depends on vertex stride
    fSeek stream (vertStride-12) #seek_cur      
    )
)

function ReadModelFile fName file_out=
(     
    format "-- START READING MODEL FILE --\n"
    stream = fOpen fname "rb"         -- Open the file for reading
    stringCount = readlong stream   

    for i=1 to stringCount do (
        s = readStrLenString(stream); print (s)
    )
    unk = readlong stream -- 02 000000?
	s = readStrLenString(stream); print (s) -- string hash? whatever
	unk = readlong stream; unk = readlong stream
	vertCount = readlong stream
	vertStride = readlong stream	
	format "VBsize: %\n" vertStride
	if (vertStride==16) then (		
		unk = readByte stream
		fSeek stream (vertStride*vertCount) #seek_cur      
		unk = readlong stream
	)
	else (
		--unk = readlong stream; unk = readShort stream #unsigned
		delta = readlong stream -- 03 000000 or 02 000000 ?	
		fSeek stream delta #seek_cur  
	)
	print ("@ 0x"+ bit.intAsHex(ftell stream) as string)
	
	if (vertStride==24) then vertex_ vertCount vertStride stream file_out	--
    print ("# ---------------------")	
	print ("@ 0x"+ bit.intAsHex(ftell stream) as string)		
	vertCount2 = readlong stream
	if (vertCount2 != vertCount) then format "different vert counts!\n\n"
	vertStride2 = readlong stream
	format "VBsize2: %\n" vertStride2
    delta = readlong stream -- 03 000000 ?	
    fSeek stream delta #seek_cur      
	if ((vertStride==16)or(vertStride2==32)or(vertStride2==48)) then vertex_ vertCount vertStride2 stream file_out
	else
    for i=1 to vertCount*2 do (		--
       x  = readFloat stream; y  = readFloat stream; z  = readFloat stream
	   --r = x*x+y*y+z*z; no = (i+1) /2
	   --if (r>1.001) or (r<0.999) then format "normals error at no%\n" no
	   --if (mod i 2) == 0 then
           --format "vn % % %\n" x y z to:file_out
		--else
           --format "vt % %\n" x y to:file_out		
       -- normals skipped
       fSeek stream (8) #seek_cur      
    )
	print ("@ 0x"+ bit.intAsHex(ftell stream) as string)
	faceIndexCount = readlong stream
	
	TriStrips=#()	
	for i=1 to faceIndexCount / 3 do (
		f1 = readShort stream #unsigned+1; f2 = readShort stream #unsigned+1; f3 = readShort stream #unsigned+1		
		append TriStrips f1; append TriStrips f2; append TriStrips f3
	)
	format "TriStrips.cnt: %\n" TriStrips.count
	print ("@ 0x"+ bit.intAsHex(ftell stream) as string)
	
	fIndList=#()	
	f1 = TriStrips[1]; f2 = TriStrips[2]; f3 = TriStrips[3]
	faceDir = 1
	for i=4 to TriStrips.count do
    (       
		--format "% % %\n" f1 f2 f3
       if ( (f1 != f2) and (f1 != f3) and (f2 != f3) ) do
	   --if ( (f1 != f3) and (f2 != f3) ) do
       (
		  --format "% % %\n" f1 f2 f3
          if faceDir == 1  then ( append fIndList f1; append fIndList f2; append fIndList f3)
          else (append fIndList f1; append fIndList f3; append fIndList f2)
		  
       )
	   faceDir *= -1
	   f1=f2; f2=f3 
	   f3 = TriStrips[i];
    )	
	format "fIndList.cnt: %\n" fIndList.count		
	for i=1 to fIndList.count-2 by 3 do
	    format "f % % %\n" fIndList[i] fIndList[i+1] fIndList[i+2] to:file_out
	    --format "f %/%/% %/%/% %/%/%\n" fIndList[i] fIndList[i] fIndList[i] fIndList[i+1] fIndList[i+1] fIndList[i+1] fIndList[i+2] fIndList[i+2] TriStrips[i+2] to:file_out

    fClose stream
)

-- entry point --

ClearListener()
fname = getOpenFileName \
caption:" open DestinyDB 3D Model" \
types:"3D Model (*.dat)|*.dat"
--historyCategory:"3D Model dat
format "fname: %\n" fname
   
-- logging preparation
--fname_out = GetSaveFileName()
fname_out = fname + ".obj"
--if fname_out != undefined then (
   file_out = createfile fname_out
   ReadModelFile fname file_out

      --format "\n" to:file_out
   close file_out
--)
```




LLightmail.JPG (12.8 KiB) Viewed 67 times



Could be that this line
if ((vertStride==16)or(vertStride2==32)or(vertStride2==48)) then vertex_ vertCount vertStride2 stream file_out
doesn't work for vertex stride 16 (cause I didn't re-check vertex stride 16 meshes).

Find out how to solve it for yourself in case a problem occurs with vertex stride 16.

edit: other armor parts can be loaded, too.
## Post #3
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2015-01-01T15:18:50+00:00
- Post Title: DestinyDB DAT Filetype

Still trying to understand all of it, and messing up more than accomplishing anything. Coding is really not my forte.
