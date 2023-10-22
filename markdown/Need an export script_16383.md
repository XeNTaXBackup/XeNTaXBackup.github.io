## Post #1
- Username: Ronny
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jun 09, 2017 10:33 pm
- Post datetime: 2017-06-10T07:09:44+00:00
- Post Title: Need an export script

Hello I am a newbie

I am very much fond of playing pc games.I do play a game kings bounty crossworlds,From these game i want an Import and Export maxscript for 3dsmax,To import models from Kings Bounty Crossworlds as well as export my Models in Kings Bounty model format.Here is a link of the sample files.

[http://www108.zippyshare.com/v/QPFmeSyO/file.html](http://www108.zippyshare.com/v/QPFmeSyO/file.html)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-06-10T08:20:32+00:00
- Post Title: Need an export script

well there is import for *.bma models in "3d Object Converter" but it is shareware   
[http://zenhax.com/viewtopic.php?p=21690#p21690](http://zenhax.com/viewtopic.php?p=21690#p21690)

i think it will be difficult to find someone to write a model import & export script for any 3d program

you can use Hex2obj for free   
cyclop.bma



cyclop_bma.png (63.11 KiB) Viewed 126 times
## Post #3
- Username: Ronny
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jun 09, 2017 10:33 pm
- Post datetime: 2017-06-10T08:47:41+00:00
- Post Title: Need an export script

I have found a video where anyone can create a Python Script for noesis but it requires a lot of hex editing.For creating the python script the correct offsets of the vertex count,Face Count,Triangle buffer and Vert buffer are required,But the problem is i have no knowledge about hex editor or hex editing.

Here is the vide: [https://www.youtube.com/watch?v=DaUpvM5Rv_Y&t=3355s](https://www.youtube.com/watch?v=DaUpvM5Rv_Y&t=3355s)
## Post #4
- Username: Ronny
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jun 09, 2017 10:33 pm
- Post datetime: 2017-06-10T11:26:43+00:00
- Post Title: Need an export script

Please anyone mark the offsets of the vertex count,Face Count,Vert Buffer and Triangle Buffer within the model file in a hex editor and send me The screenshots of the marked ones so that it would be easy enough for me.
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-06-11T01:52:48+00:00
- Post Title: Need an export script

what model file? the offsets and counts for the sample i posted before are clearly shown in the image.   
it wouldn't be practical for anyone to feed you offsets and counts because they change from one model to the next.
you are on a good way by that tutorial video link and will learn this stuff in no time, make mariokart64n proud!
## Post #6
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2017-06-11T15:13:40+00:00
- Post Title: Need an export script

I looked at the format and I would have to say this is a good format for someone that wanted to learn all this stuff

Anyway I did a mockup maxscript here:

```
	MAXSCRIPT
		Description:
			Mockup import script to import kings bounty crossworlds bma
			models.
		Written:
			mariokart64n (June 11, 2017)
		
		Notes:
			format is seems to work by stacking blocks, each block has a
			4 byte id code to identify what the block is. the maxscript was
			only written to debug some structure ideas when picking apart
			the file format. it is not written to properly read the way the
			blocks are dynamically presented. So this scripted worked
			on the few samples I was provided, but most likely will not work
			on the entire game and its files.
			
			Blocks need to be better documented before a export feature
			can be considered. The good news is that in the samples I had
			there was probably around 8 blocks, so thats not too bad ;)

*/ ----------------------------------------------------------
clearlistener()

-- f  = fopen "L:\\kings bounty crossworlds resources\\models\\elf.bma" "rb"
-- f  = fopen "L:\\kings bounty crossworlds resources\\models\\druid.bma" "rb"
f = fopen (GetOpenFileName caption:"Select any File" types: "bma files (*.bma)|*.bma|All files (*.*)|*.*|") "rb"

fn readstringbylen f = (
	str_len = readlong f #unsigned
	str = ""
	for ii = 1 to str_len do (str+=bit.IntAsChar(readbyte f #unsigned))
	str
	)

fseek f 11 #seek_set -- 41140000
if readbyte f == 32 then (
	fseek f 8 #seek_cur
	)
else (
	fseek f 4 #seek_cur
	)
bone_count = readlong f #unsigned

for i = 1 to bone_count do (
	print (readstringbylen f)
	fseek f 113 #seek_cur
	)
if readlong f #unsigned == 0x0005535B then (
	mat_count = readlong f #unsigned
	for i = 1 to mat_count do (
		format "Mat Name: %\n" (readstringbylen f)
		fseek f 0x3E #seek_cur
		str_len = 0
		while str_len < 256 do (
			str_len = readlong f #unsigned
			if str_len < 256 do (
				fseek f -4 #seek_cur
				format "\tProp: %\n" (readstringbylen f) -- type
				readbyte f #unsigned -- 0
				case (readbyte f #unsigned) of ( -- type
					2:(fseek f 3 #seek_cur;readfloat f)
					4:(fseek f 19 #seek_cur)
					5:(fseek f 83 #seek_cur)
					6:(fseek f 3 #seek_cur;format "\t\tTex Name: %\n"  (readstringbylen f);readbyte f) -- tex name
					)
				)
			)
		if str_len == 0x02238ECB then (
			format "MeshInfo @ 0x%\n" (bit.IntAsHex((ftell f-4) as integer))
			table_count = readlong f #unsigned
			fseek f (36*table_count) #seek_cur
			)
		else (
			print "mesh table block not here?"
			)
		vertArray = #()
		faceArray = #()
		if readlong f #unsigned == 0x01119C6B then (
			format "Vertices @ 0x%\n" (bit.IntAsHex((ftell f-4) as integer))
			vertex_count = readlong f #unsigned
			for i = 1 to vertex_count do (
				append vertArray [(readshort f)/327.675, (readshort f)/327.675, (readshort f)/327.675]
				vertArray[vertArray.count] = [vertArray[vertArray.count][1],vertArray[vertArray.count][3],vertArray[vertArray.count][2]]
				fseek f 18 #seek_cur
				)
			)
		else (
			print "vertex buffer not here?"
			)
		if readlong f #unsigned == 0x000141FB then (
			format "Faces @ 0x%\n" (bit.IntAsHex((ftell f-4) as integer))
			face_count = readlong f #unsigned
			for i = 1 to face_count/3 do (
				append faceArray ([readshort f, readshort f, readshort f]+1)
				)
			delete $*
			msh = mesh vertices:vertArray faces:faceArray
			)
		else (
			print "face buffer not here?"
			)
		)
	)
else (
	print "found different block after bones"
	)

format "Current Address @ 0x%\n" (bit.IntAsHex((ftell f) as integer))
fclose f

```
## Post #7
- Username: Ronny
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jun 09, 2017 10:33 pm
- Post datetime: 2017-06-11T16:49:04+00:00
- Post Title: Need an export script

Thanks for your kind help mariokart,But in This topic i also need an export script to Export my models in Kings Bounty Crossworlds .bma format.
## Post #8
- Username: Ronny
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jun 09, 2017 10:33 pm
- Post datetime: 2017-06-12T13:02:57+00:00
- Post Title: Need an export script

Please provide me a noesis python script so that i can import as well as export models from Kings Bounty.
