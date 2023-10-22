## Post #1
- Username: vallex
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Oct 07, 2014 4:55 am
- Post datetime: 2015-08-20T18:21:54+00:00
- Post Title: Trine 3 .fbi Textures

Hi, all!
I try to decompress the Trine 3  textures: 

```
# comtype lzss0
comtype lz4
# and many other comtypes I've already tried
goto 33
get zsize long
get size long
get NAME filename
string NAME += ".dds"
clog NAME 41 zsize size

```


I uploaded compressed .fbi and decompressed .dds for example:
[http://www.mediafire.com/download/2e0ns ... a_face.fbi](http://www.mediafire.com/download/2e0ns98anlt7c8d/zoya_face.fbi)
[http://www.mediafire.com/download/j55p0 ... a_face.dds](http://www.mediafire.com/download/j55p015aa8g9h9z/zoya_face.dds)

(Decompressed I took by DX Ripper)

Can anyone help with this?
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-08-20T20:19:30+00:00
- Post Title: Trine 3 .fbi Textures

wrong subforum!

did you try all comtypes?

create a bat or cmd file with this line contained:
call comtype_scan2 D:\test\comtype_scan2.bms D:\test\zoya_face.fbi D:\test [10000000]

where D:\test is the folder which contains quickbms.exe, comtype_scan.bat, comtype_scan2.bms
and zoya_face.fbi, the file to be decompressed

(if one of the created *.dmp file has a size of 1,398,256 bytes it's very likely to contain the decompressed dds data)
## Post #3
- Username: vallex
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Oct 07, 2014 4:55 am
- Post datetime: 2015-08-20T22:08:06+00:00
- Post Title: Trine 3 .fbi Textures

Thanks for the advice, but - no result. The file is still compressed. Apparently they used their own algorithm, unfortunately..
The only algorithm that approximates the uncompressed file is number 231
## Post #4
- Username: vallex
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Oct 07, 2014 4:55 am
- Post datetime: 2015-08-21T11:22:54+00:00
- Post Title: Trine 3 .fbi Textures

Finaly I have this:



zoya_face.fbi.jpg (150.4 KiB) Viewed 244 times



Can you help me?
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-08-21T14:09:50+00:00
- Post Title: Trine 3 .fbi Textures

nearest hit I had:



zoya_face_lz4_uncompressed.JPG (59.36 KiB) Viewed 236 times
## Post #6
- Username: vallex
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Oct 07, 2014 4:55 am
- Post datetime: 2015-08-21T14:44:14+00:00
- Post Title: Trine 3 .fbi Textures

Мaybe dictionary can help, but I don't know how to use it in LZ4
## Post #7
- Username: vallex
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Oct 07, 2014 4:55 am
- Post datetime: 2015-08-25T20:23:56+00:00
- Post Title: Trine 3 .fbi Textures

My best shot until now after reordering the sequence of the bits:



zoya_face.fbi2.jpg (148.68 KiB) Viewed 210 times
## Post #8
- Username: vallex
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Oct 07, 2014 4:55 am
- Post datetime: 2015-08-26T23:16:56+00:00
- Post Title: Trine 3 .fbi Textures

I did it!



zoya_face_fbi.png (249.97 KiB) Viewed 197 times



Maxscript code:

```
fn LZ4_decompress input = (
	local i = 0, j = 0, n = input.count, out = #(), l, token, literals_length, end, offset, match_length, pos
	while i < n do (
		token = input[i+=1]
		literals_length = bit.shift token -4
		if literals_length > 0 do (
			l = literals_length + 240
			while l == 255 do (
				l = input[i+=1]
				literals_length += l
			)
			end = i + literals_length
			while i < end do out[j+=1] = input[i+=1]
		) 
		if i < n-1 do (
			offset = bit.or input[i+=1] (bit.shift input[i+=1] 8)
			if not (offset == 0 or offset > j) do (
				match_length = bit.and token 0xf
				l = match_length + 240
				while l == 255 and i<n do (
					l = input[i+=1]
					match_length += l
				)
				pos = j - offset
				end = j + match_length + 4
				while j < end do out[j+=1] = out[pos+=1]
			)
		)
	)
	out
)
fn convertTrine3Tex fbi = (
	if fbi == undefined do return false
	local u, f, magic, version, width, height, mip, floats, other, zsize, size, tmp, un, data
	local dir = getfilenamepath fbi, file = getfilenamefile fbi
	local dxt1 = 827611204, dxt3 = 861165636, dxt5 = 894720068, ati2 = 843666497
	local dxt = #(dxt1, dxt5, dxt5 ,ati2) 
	f = fopen fbi "rb"
	magic = readlong f
	if magic != 4017 do return false
	version = readshort f
	if version > 4 do return false
	staff = readshort f
	width = readshort f
	height = readshort f
	mip = readbyte f
	floats = [readfloat f, readfloat f, readfloat f, readfloat f]
	other = [readshort f, readshort f]
	zsize = readlong f
	size = readlong f
	if doesfileexist (dir + file + ".lz4") then (
		tmp = fopen (dir + file + ".lz4") "rb"
		un = for i=1 to size collect readbyte tmp #unsigned
		fclose tmp
	) else (
		data = for i=1 to zsize collect readbyte f #unsigned
		un = LZ4_decompress data
	)
	fclose f
	gc()
	u = fopen (dir + file + ".dds") "wb"
	writelong u 542327876
	writelong u 124
	writelong u 135175
	writelong u height
	writelong u width
	for i=1 to 2 do writelong u 0
	writelong u mip
	for i=1 to 11 do writelong u 0
	writelong u 32
	writelong u 4
	writelong u dxt[version]
	for i=1 to 5 do writelong u 0
	writelong u 4198408
	for i=1 to 4 do writelong u 0
	local all =un.count, b, p = 0, q = 0, r = 0
	case version of (
		1: ( -- DXT1
			b = all/4
			for i=1 to all/8 do (
				for j=0 to 1 do writebyte u un[i+j+p] #unsigned
				for j=0 to 1 do writebyte u un[i+b+j+p] #unsigned
				for j=0 to 3 do writebyte u un[i+b*2+j+q] #unsigned
				p += 1
				q += 3
			)
		)
		2: ( -- DXT5
			b = all/8
			for i=1 to all/16 do (
				writebyte u un[i] #unsigned
				writebyte u un[i+b/2] #unsigned
				for j=0 to 5 do writebyte u un[i+b+j+p] #unsigned
				for j=0 to 1 do writebyte u un[i+b*4+j+q] #unsigned
				for j=0 to 1 do writebyte u un[i+b*5+j+q] #unsigned
				for j=0 to 3 do writebyte u un[i+b*6+j+r] #unsigned
				p += 5
				q += 1
				r += 3
			)
		)
		3: ( -- DXT5 - Alpha Only
			b = all/8
			for i=1 to all/8 do (
				writebyte u un[i] #unsigned
				writebyte u un[i+b] #unsigned
				for j=0 to 5 do writebyte u un[i+b*2+j+p] #unsigned
				for j=0 to 7 do writebyte u 255 #unsigned
				p += 5
			)
		)
		4: ( -- ATI2
			b = all/16		
			for i=1 to all/16 do (
				writebyte u un[i] #unsigned
				writebyte u un[i+b] #unsigned
				for j=0 to 5 do writebyte u un[i+b*2+j+p] #unsigned
				writebyte u un[i+b*8] #unsigned
				writebyte u un[i+b*9] #unsigned
				for j=0 to 5 do writebyte u un[i+b*10+j+p] #unsigned
				p += 5
			)
		)
		default: for i in un do writebyte u i #unsigned
	)
	fclose u
)
convertTrine3Tex (getOpenFileName historyCategory:"Trine 3 Textures" types:"Trine 3 .fbi (*.fbi)")
/*
dir = getSavePath initialDir:@"d:\test\data\root\instance_base\entity\object\water\"
if dir != undefined and doesfileexist dir do (
	files = getAllFiles dir #(".fbi")
	for file in files do convertTrine3Tex file
)
*/


```

PS:
You can expect soon a script for importing Trine 3 .fbm models in 3D Studio Max. This is the reason to use this subforum
## Post #9
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2015-08-27T03:20:51+00:00
- Post Title: Trine 3 .fbi Textures

Nice work vallex. I'm not a fan of Trine but the visuals were fantastic. Might have to grab the game if the models are good.
## Post #10
- Username: vallex
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Oct 07, 2014 4:55 am
- Post datetime: 2015-08-31T19:17:42+00:00
- Post Title: Trine 3 .fbi Textures

I'm ready with .fbm model importer:

[viewtopic.php?f=16&t=13269](http://forum.xentax.com/viewtopic.php?f=16&t=13269)

Grab!
## Post #11
- Username: ItsMeLenny
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 17, 2016 8:00 am
- Post datetime: 2016-08-06T08:51:17+00:00
- Post Title: Trine 3 .fbi Textures

I'd like to convert this to python but am having a bit of trouble.
I know the Trine 1 and Trine 2 textures open in Blender and Gimp without any need to convert them to DDS.
Does this script uncompress and then convert to DDS on top of it?
I was able to convert the model importers to python.
