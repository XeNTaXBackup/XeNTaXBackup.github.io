## Post #1
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2020-03-05T18:59:55+00:00
- Post Title: [Wii] Suzumiya Haruhi no Heiretsu (*.sge)

Title: 涼宮ハルヒの並列 (Suzumiya Haruhi no Heiretsu)
Platform: Wii (ID: R44J8P)

Cover:


==========================================================================================================

MaxScript Importer:
Status: Importer is incomplete, only imports base geometry and only works on character models


```
doNormals = false -- broken, don't activate!
fn ReadFixedString &bstream fixedLen = (
	local str = ""
	for i = 1 to fixedLen do (
		str += bit.intAsChar (ReadByte bstream #unsigned)
		)
	str
	)
fn getpadding num alignment = (
	(mod (alignment-(mod num alignment)) alignment)
	)
fn build v t f n = (
	local msh, normMod, vi, fi
	msh = mesh vertices:v tvertices:t faces:f
	msh.numTVerts = t.count
	buildTVFaces msh
	for i = 1 to t.count do setTVert msh i t[i]
	for i = 1 to f.count do setTVFace msh i f[i]
	
	if doNormals and n.count > 0 do (
		disableSceneRedraw()
		max modify mode
		select msh
		normMod = Edit_Normals()
		normMod.selectBy = 1
		normMod.displayLength = 0.50
		normMod.showHandles = on
		
		modPanel.setCurrentObject normMod
		addModifier msh normMod
		
		normMod.EditNormalsMod.SetSelection #{1..(normMod.GetNumNormals())}
		--normMod.EditNormalsMod.Break()
		
		normMod.EditNormalsMod.Reset()
		for vi = 1 to normMod.EditNormalsMod.GetNumFaces() do (
			for fi = 1 to 3 do (
				normMod.SetNormalID vi fi f[vi][fi]
				)
			)
		for vi = 1 to n.count do (
			subobjectLevel = 1
			normMod.EditNormalsMod.SetNormal vi n[vi]
			subobjectLevel = 0
			)
		normMod.EditNormalsMod.MakeExplicit()
		enableSceneRedraw()
		)
	msh
	)
fn readFile file = (
	local f, b, hits = 0, fs = 0, v = 0
	local vpos = 0, fpos = 0, pos = 0
	local vcount = 0, vertArray = #(), tvertArray = #()
	local msh, mscale = 25.4 / 1.0
	local vert_count = 0, face_count = 0
	local faceArray = #(), i = 1, ii = 1, normArray = #()
	local maxv = 0, voffset = 0, face = [1,2,3], dmy
	local isFirst = false, w1, w2, w3, w4, b1, b2, b3, b4, maxbone = 0
	local u1,u2,u3,u4,u5,u6,u7,u8,u9,u10, strArray = #()
	local boneArray = #(), boneIds = #(), par = 0, id = 0, index
	local parArray = #(), fileStart = 0, boneAddr = 0

	f = try(fopen file "rbS")catch(undefined)
	format "File:\t%\n" file
	if f != undefined then (
		fs = getFileSize file
		-- first 20 bytes dont appear to belong to the file
		-- but rather maybe apart of the archive
		fileStart = 0x20
		
		fseek f 0x24 #seek_set
		u1 = readlong f #unsigned
		u2 = readlong f #unsigned
		u3 = readlong f #unsigned
		u4 = readlong f #unsigned
		u5 = readlong f #unsigned
		u6 = readlong f #unsigned
		u7 = readlong f #unsigned
		u8 = readlong f #unsigned
		u9 = readlong f #unsigned
		u10 = readlong f #unsigned
		
		fseek f 0xA0 #seek_set
		
		fseek f (u1 * 0x48) #seek_cur
		fseek f (getpadding (ftell f) 16) #seek_cur
		
		fseek f (u2 * 0x14) #seek_cur
		fseek f (getpadding (ftell f) 16) #seek_cur
		
		for i = 1 to u5 do (
			append strArray (ReadFixedString &f 0x18)
			)
		print strArray
		fseek f (getpadding (ftell f) 16) #seek_cur
		
		fseek f (u3 * 0x18) #seek_cur
		fseek f (getpadding (ftell f) 16) #seek_cur
		
		boneAddr = ftell f
		for i = 1 to u4 do (
			pos = ftell f + 0x28
			dmy = bonesys.createbone [0,0,0] [0,1,0] [0,1,0]
			dmy.showLinks = dmy.showLinksOnly = true
			fseek f 12 #seek_cur -- ? rotation?
			dmy.position = [readfloat f, readfloat f, readfloat f]
			dmy.position = [dmy.position.x, dmy.position.z, dmy.position.y] * mscale
			par = readlong f #unsigned + fileStart
			if par > 0 do (
				par = ((par - boneAddr) / 0x28) + 1
				
				)
			append parArray par
			append boneArray dmy
			fseek f pos #seek_set
			)
		
		for i = 1 to boneArray.count do (
			if parArray[i] > 0 do (
				boneArray[i].parent = boneArray[parArray[i]]
				)
			)
		fseek f (getpadding (ftell f) 16) #seek_cur
		
		fseek f (u10 * 0x08) #seek_cur
		fseek f (getpadding (ftell f) 16) #seek_cur
		
		
		fseek f 2 #seek_end
		while (ftell f) != 0 do (
			b = readshort f #unsigned
			fseek f -4 #seek_cur
			if b == 0xFFFF do exit
			)
		fpos = ftell f
		format "Guessed Face Start Offset @ %\n" (ftell f)
		
		while (ftell f) != 0 do (
			b = readshort f #unsigned
			fseek f -4 #seek_cur
			if b == 0xFFFF then (
				hits += 1
				) else (hits = 0)
			if hits >= 4 do exit
			)
		vpos = ftell f
		format "Guessed Vertex Start Offset @ %\n" (ftell f)
		
		while (ftell f + 16) < fs do (
			fseek f ((getpadding (ftell f) 16) + 8) #seek_cur
			b = readlong f #unsigned
			if b == 1 do exit
			)
		format "Guessed Vertex Start Offset2 @ %\n" (ftell f)
		fseek f 4 #seek_cur
		vert_count = readlong f #unsigned
		fseek f 4 #seek_cur
		face_count = readlong f #unsigned
		fseek f 4 #seek_cur
		
		for v = 1 to vert_count do (--while (ftell f) < fpos do (
			pos = ftell f + 56
			append vertArray ([readfloat f, readfloat f, readfloat f] * mscale)
			w1 = readfloat f
			w2 = readfloat f
			w3 = readfloat f
			w4 = 1.0 - (w1 + w2 + w3)
			b1 = readbyte f #unsigned
			b2 = readbyte f #unsigned
			b3 = readbyte f #unsigned
			b4 = readbyte f #unsigned
			if b1 > maxbone do maxbone = b1
			if b2 > maxbone do maxbone = b2
			if b3 > maxbone do maxbone = b3
			if b4 > maxbone do maxbone = b4
			append normArray [readfloat f, readfloat f, readfloat f]
			fseek f 4 #seek_cur
			append tvertArray [readfloat f, readfloat f, 0]
			
			vertArray[vertArray.count] = (
				[vertArray[vertArray.count].x, \
				vertArray[vertArray.count].z, \
				vertArray[vertArray.count].y]
				)
			normArray[normArray.count] = (
				[normArray[normArray.count].x, \
				normArray[normArray.count].z, \
				normArray[normArray.count].y]
				)
			
			vcount += 1
			fseek f pos #seek_set
			)
		format "Vertex Count:\t%\n" vcount
		
		fseek f fpos #seek_set
		fseek f (getpadding (ftell f) 16) #seek_cur
		format "Guessed Vertex face Offset2 @ %\n" (ftell f)
		
		voffset = 0
		maxv = 0
		isFirst = true
		for v = 1 to face_count / 3 do (
			face = (
				[readlong f #unsigned, \
				readlong f #unsigned, \
				readlong f #unsigned]
				)
			face = [face[1], face[3], face[2]]
				
			if isFirst == false and face == [0, 2, 1] then (
				
				for i = 1 to faceArray.count do (
					for ii = 1 to 3 do (
						if faceArray[i][ii] > maxv do (
							maxv = faceArray[i][ii]
							)
						)
					)
				voffset = maxv
					
				if vertArray.count > 0 do (
					try(
						format "Element:\t%\n" (ftell f - 12)
						build vertArray tvertArray faceArray normArray
						)
					catch(
						format "Error\n" 
						)
						
					faceArray = #()
					)
					
					
				format "voffset:\t%\n" voffset
				append faceArray (face + 1 + voffset)
				)
			else (
				append faceArray (face + 1 + voffset)
				)
			isFirst = false
			)
		if faceArray.count > 0 do (
			try(
				build vertArray tvertArray faceArray normArray
				)
			catch(
				format "Error\n" 
				)
			)
		) else (messagebox "error")
	format "maxbone:\t%\n" maxbone
	fclose f
	)
delete $*
readFile(
-- 	"C:\\Users\\Corey\\Downloads\\New folder\\dump\\Type6\\6792.SGE.file6"
-- 	"C:\\Users\\Corey\\Downloads\\New folder\\dump\\Type6\\7844.SGE.file6"
-- 	"C:\\Users\\Corey\\Downloads\\New folder\\dump\\Type6\\10847.SGE.file6"
	GetOpenFileName types:"Model File (*.sge)|*.sge|All files (*.*)|*.*|"
	)

```



 sge_importer_v0_1.zip
Maxscript that works with 3dsmax (2.22 KiB) Downloaded 46 times



==========================================================================================================
Notes:

Model extraction method requested by Zerks over at the Xentax Discord, much credit goes to [Bigpet for cracking the games custom RLE](https://forum.xentax.com/viewtopic.php?p=98099#p98099)

> Reply from Bigpet ↑Sun Sep 07, 2014 7:42 am at Sun Sep 07, 2014 7:42 am
>
> 
I forgot to do an end write-up of this, and there doesn't seem to be too much interest in this. But I guess I should just give you the unfinished work I did.

So this is what I made back then to decode the images
Code: Select all//decode the custom RLE CONTAINS ERRORS ATM
std::vector<char> MisakaArchive::decodeRLE(std::vector<char> buffer)
{
	const char BACK_FLAG = 0x80;
	const char REPEAT_FLAG = 0x40;
	const char LHDR_FLAG = 0x20;

	std::vector<char> result;

	int cur_src = 0;
	int cur_dst = 0;
	int cur_bck = 0;

	while (cur_src < buffer.size()){
		char src = buffer[cur_src++];
		int amt = 0;

		if (src & BACK_FLAG){
			amt = (src & 0x60) >> 5;
			amt += 4;
			cur_bck = (src & 0x1F) << 8 | reinterpret_cast<unsigned char &>(buffer[cur_src++]);
			assert(cur_bck>0);
			cur_bck = cur_dst - cur_bck;
			int subcopy = amt;
			while (cur_dst - cur_bck < subcopy){
				int subcopy_amt = (cur_dst - cur_bck);
				copy_data(result, result, cur_dst, cur_bck, subcopy_amt);
				subcopy -= subcopy_amt;
				cur_bck += subcopy_amt;
				cur_dst += subcopy_amt;
			}
			copy_data(result, result, cur_dst, cur_bck, subcopy);

			cur_bck += subcopy;
			cur_dst += subcopy;
		}
		else if ((src & 0xE0) == 0x60)
		{
			amt = src & 0x1F;
			amt += 4;
			assert(cur_dst > cur_bck);
			int subcopy = amt;
			while (cur_dst - cur_bck < subcopy){
				int subcopy_amt = (cur_dst - cur_bck);
				copy_data(result, result, cur_dst, cur_bck, subcopy_amt);
				subcopy -= subcopy_amt;
				cur_bck += subcopy_amt;
				cur_dst += subcopy_amt;
			}
			copy_data(result, result, cur_dst, cur_bck, subcopy);

			cur_bck += subcopy;
			cur_dst += subcopy;
		}
		else if (src & REPEAT_FLAG){
			amt = (src & 0x10) ? (src & 0x0F) << 8 | reinterpret_cast<unsigned char &>(buffer[cur_src++]) : src & 0x1F;
			amt += 4;
			result.insert(result.begin() + cur_dst, amt, buffer[cur_src++]);
			cur_dst += amt;
		}
		else if (src & LHDR_FLAG){
			amt = ((src & 0x1F) << 8) | reinterpret_cast<unsigned char &>(buffer[cur_src++]);
			copy_data(result, buffer, cur_dst, cur_src, amt);
			cur_src += amt;
			cur_dst += amt;
		}
		else if (src == 0x00){
			break;
		}
		else
		{
			amt = src & 0x1F;
			copy_data(result, buffer, cur_dst, cur_src, amt);
			cur_src += amt;
			cur_dst += amt;
		}

	}
	return result;
}


This has still some bugs in it but you can find this and the actually working hackishly direct MIPS ASM to C++ translation here: https://github.com/Bigpet/KatagawaBinParser
## Post #2
- Username: Zerks
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 12, 2019 4:32 am
- Post datetime: 2020-03-05T21:29:53+00:00
- Post Title: [Wii] Suzumiya Haruhi no Heiretsu (*.sge)

Amazing job man! This is incredible. Thank you so much.
## Post #3
- Username: Zeak6464
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 06, 2020 12:10 am
- Post datetime: 2020-03-05T21:52:49+00:00
- Post Title: [Wii] Suzumiya Haruhi no Heiretsu (*.sge)

Amazing that you got this far !
## Post #4
- Username: potosakertomo420
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 13, 2022 3:57 am
- Post datetime: 2022-12-12T20:01:57+00:00
- Post Title: [Wii] Suzumiya Haruhi no Heiretsu (*.sge)

kinda new to all of this

how do i use this script and is there any way to open it in blender instead
