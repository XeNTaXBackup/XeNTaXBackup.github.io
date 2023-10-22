## Post #1
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-05-23T20:12:37+00:00
- Post Title: Kingdom Hearts Birth By Sleep models

I'm interested in the models from Kingdom Hearts Birth By sleep for the PSP. I have tried to extract files from BBS0.Dat in the USRDIR folder on the iso, but Jaedernaub freaked out and said "too many files".

But I did manage to get some textures in tm2 format.

The models themselves are not GMO, I have tried Mradults' tool on the.dat and it couldn't find anything.

I'm not able to upload the .dat file, its 858mb, which is way to big for me to upload.

Would anyone be interested in having a look at this?
## Post #2
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-05-26T04:10:09+00:00
- Post Title: Kingdom Hearts Birth By Sleep models

ultimaespio are you the same people from qhimm ?
## Post #3
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-05-26T19:06:54+00:00
- Post Title: Kingdom Hearts Birth By Sleep models

Hmm yes I am, why?
## Post #4
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-05-29T01:05:46+00:00
- Post Title: Kingdom Hearts Birth By Sleep models

UE try looking at it in a hexeditor, it may take time to load, but you might find common data structures in there as DAT is often used as a package file extension. Usually DATs I've seen as packages are unencrypted... though not always.

EDIT: I've seen jaedernaub dump a few thousand files before, I think that message meant that it was finding errors when trying to dump the files. Or that it was recognizing a header in the DAT that said there were more files than could fit inside the space.

Try turning off impertinent file ripping options like sound and 2D images if you already have the textures.
## Post #5
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2010-06-03T03:45:36+00:00
- Post Title: Kingdom Hearts Birth By Sleep models

All files are in BBS0.dat.

I don't know the exact format, but it's easy to find files,
they are 0x800 aligned (like a DVD)

from searching this file i found out

inside are
- 5 PMF Videos

```
02E1F800	00005C3F	pmf	PSP Video File
05515000	0000AA2A	pmf	PSP Video File
0B5B3000	00016B66	pmf	PSP Video File
163D6800	0002C7AD	pmf	PSP Video File
```


- ARC Files
- LuaQ Files (compiled lua 5.1 scripts) <- gamescript ^^
- AT3 Files
- and some tm2 files

inside of ARC Files are the Game Files,
- SEDBSSCF - Sound files
- PAM files (Animation ?)
- PMO files (3D Models ?)
- EAD files
- FEP files
- TXA files (texture ?)
- TEX files (texture ?)
- tm2 files (texture)
- CTD files (Text Files, plain SHIFT-JIS)
- and many more...


i think that PMO files are the 3D Models, 
because i can see some mesh, bone and texture data, 
but i'm unable to translate it into
readable form (maybe native PSP data)

the texture is common RGBA.

here some extracted files (1 ARC, 3 PMO, 1 SEDBSSCF and scan results)
[http://www.filebeam.de/temp/khbbs_some_files.rar](http://www.filebeam.de/temp/khbbs_some_files.rar)
## Post #6
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-06-03T11:53:34+00:00
- Post Title: Kingdom Hearts Birth By Sleep models

Thanks, PMO does sound likely, I mean, GMO is a format used in most psp games, so PMO could just be an altered version of that?

The other .DAT have pmf files inside of them i think, but i'll check that.
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-06-03T17:25:42+00:00
- Post Title: Kingdom Hearts Birth By Sleep models

i got the bone section figured out simple format 2 4x4 matrix with the rotation inverted.
ill look at the mesh section the image section has a tim2 header so i am assuming they are valid
## Post #8
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2010-06-03T18:49:01+00:00
- Post Title: Kingdom Hearts Birth By Sleep models

> Reply from chrrox
>
> i got the bone section figured out simple format 2 4x4 matrix with the rotation inverted.
ill look at the mesh section the image section has a tim2 header so i am assuming they are valid

Yes they are valid tm2 files, mesh2rdm can convert them.
Here another PMO, a bit bigger, 282 KB, it has 4 texture files.

[http://filebeam.com/f5deb8ac9ec38b017a7f5fb6aff3da8b](http://filebeam.com/f5deb8ac9ec38b017a7f5fb6aff3da8b)

i think the mesh section is native PSP, like FF7CC *.raw
## Post #9
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-06-03T19:27:12+00:00
- Post Title: Kingdom Hearts Birth By Sleep models

Oh, that model is the Fairy Godmother 

Going by the textures that is lol.

If its needed, i can forward you towards the Crisis Core format, but i think its really out of date now.

Falo, what did you use to extract the PMO and TIM2 files?
## Post #10
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2010-06-04T14:46:37+00:00
- Post Title: Kingdom Hearts Birth By Sleep models

> Reply from ultimaespio
>
> Oh, that model is the Fairy Godmother 

Going by the textures that is lol.

If its needed, i can forward you towards the Crisis Core format, but i think its really out of date now.

Falo, what did you use to extract the PMO and TIM2 files?

any Hex Editor should work.
here 2 quickbms scripts,

extract_pmo.txt should extract 858 PMO's,
extract_tm2_from_pmo.txt extracts all tm2 files from any PMO.

the biggest PMO is #424 (Terra-Xehanort)

the script is not complete, it uses ((BONOffset - Offset) + 32 + (BoneCount * 160)) to calculate Size, this will not work for pmo's without bones
until i know how to read the mesh it's the only solution.
[pmo_scripts.rar](https://xentaxbackup.github.io/file/3108_pmo_scripts.rar)
## Post #11
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-06-04T14:57:51+00:00
- Post Title: Kingdom Hearts Birth By Sleep models

Thanks, I was using Hex Workshop to extract them, but i must have got it wrong somewhere, I was extracting about 40+ PMO files as one 

I'm making a list of the characters I have found so far:

106 - Master eraqus
404 - HP Goofy
601 - Scrooge mcduck
700 - Armour Terra
702 - Ven
704 - Aqua
706 - Terra

I've had to open the .PMO files in hex workshop to see their model name. The model name is similar to how they are named in KH2. For example Ven's code is P01EX00.

I'll post a breakdown of what each code means:

B - Boss
F - Props, like treasure Chests
H - highpoly (Cutscene models)
M - Monster (Unversed)
P - Playable character/summon
W - Weapon

The EX in Ven's code means that he loads in many different places. The EX changes depending on where each character loads:

SB - Sleeping Beauty/Enchanted Dominion
SW - Snow White/Dwarf Woodlands
CD - Cinderella/Castle of Dreams
RG - Radiant Garden
YT - Mysterious Tower, Probably stands for Yen Sids Tower, rather than mysterious tower.
DP - Land of Departure, I wouldnt have figured this one out if i hadn't seen Master Eraqus there lol.

Those are the only ones I've seen in bbs so far, but its most likely that the other worlds have similar codes.

Here's something that I find really interesting, there seems to be a pattern with the PMO files, it seems to go Character, *unknown*, character again. So is it possible that the unknown pmo files are actually the animations?
## Post #12
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2010-06-04T21:17:12+00:00
- Post Title: Kingdom Hearts Birth By Sleep models

here my progress so far:

// File Header always 160 Byte
0x0 - 4 Byte - Signature // "PMO" & 0x00
0x8 - 2 Byte - Texture Count // Texture is always TIM2 (*.tm2)
0xC - 4 Byte - BON Offset
0x10 - 4 Byte - Mesh Offset
0x1C - 4 Byte - Unknown Offset

// Mesh Header: 20 or 24 Byte
0x0 - 2 Byte - Count1
0x2 - 1 Byte - ??? // maybe DataType1
0x3 - 1 Byte - StructSize1
0x4 - 2 Byte - ???
0x6 - 2 Byte - ???
0x8 - 1 Byte - ???
0x9 - 1 Byte - Count2
0xA - 1 Byte - ??? // maybe DataType2
0xB - 1 Byte - StructSize2
0xC - 4 Byte - ???
0x10 - 4 Byte - ???

to calculate the size of 1 Mesh Group:
(Count1 * StructSize1) + (Count2 * StructSize2)

the most difficult part is the DataType,
every type is different decoded,
for 0xFF it seams that it's 3x short, XYZ
here a test: [http://www.imagebanana.com/view/iot3ze6/test_246.jpg](http://www.imagebanana.com/view/iot3ze6/test_246.jpg)
## Post #13
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-06-04T21:22:36+00:00
- Post Title: Kingdom Hearts Birth By Sleep models

Looks as if things are taking some sort of shape 

What model is that?
## Post #14
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2010-06-04T21:39:28+00:00
- Post Title: Kingdom Hearts Birth By Sleep models

No idea, it looks like a chair or table, it is a very simple model, only two mesh groups, no texture, it is 246.pmo (6 KB File).
## Post #15
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2010-06-05T07:31:56+00:00
- Post Title: Kingdom Hearts Birth By Sleep models

The whole format is actually quiet easy! But I don't have my note on hand(can't get it back until next Tuesday)!
0x10 is the offset of Deformable Mesh and 0x1C is the offset of Static Mesh!

For the TIM2 image, there is a file size in there!
offset 06 is the Header Type
If  Header Type = 0, file size is located at offset 0x10
Id Header Type = 1, file size is located at offset 0x80

More Information on TIM2 format can be found in my own BBS: [http://gameresearch.5d6d.com/thread-146-1-1.html](http://gameresearch.5d6d.com/thread-146-1-1.html)
Use "Guess" to logon, and Password is "guess"
[kh.jpg](https://xentaxbackup.github.io/file/3112_kh.jpg)
## Post #16
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-06-05T12:52:35+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

For tim2, file we can convert tim2 file to png using MrAdults amazing tools "mesh2rdm"
Here is the link :
[http://www.richwhitehouse.com/index.php ... rdmv45.zip](http://www.richwhitehouse.com/index.php?content=inc_projects.php&filemirror=mesh2rdmv45.zip)
To use it just make a new notepad type "mesh2rdm file.tm2 outfile.png" in the notepad,then rename .txt with .bat then press enter on the bat file
## Post #17
- Username: GameAreAwesome
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jun 07, 2010 1:49 pm
- Post datetime: 2010-06-08T06:48:01+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Falo
>
> ultimaespio wrote:Oh, that model is the Fairy Godmother 

Going by the textures that is lol.

If its needed, i can forward you towards the Crisis Core format, but i think its really out of date now.

Falo, what did you use to extract the PMO and TIM2 files?

any Hex Editor should work.
here 2 quickbms scripts,

extract_pmo.txt should extract 858 PMO's,
extract_tm2_from_pmo.txt extracts all tm2 files from any PMO.

the biggest PMO is #424 (Terra-Xehanort)

the script is not complete, it uses ((BONOffset - Offset) + 32 + (BoneCount * 160)) to calculate Size, this will not work for pmo's without bones
until i know how to read the mesh it's the only solution.

How do I extract it with hex editor?
## Post #18
- Username: GameAreAwesome
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jun 07, 2010 1:49 pm
- Post datetime: 2010-06-08T07:31:42+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Hey guys I have extracted alot of tm2 and have made to easy models anyway the most thing Im looking for is the map models (if there are any) and the font for all the letters and numbers its maybe a texture file or maybe a PGF file(psp font file) or maybe a txt files anyway can anybody try to find that for me because Im trying to edit some stuff with the game files and put them back into the game so please help me
## Post #19
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2010-06-08T13:22:06+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from sorayahya
>
> Hey guys I have extracted alot of tm2 and have made to easy models anyway the most thing Im looking for is the map models (if there are any) and the font for all the letters and numbers its maybe a texture file or maybe a PGF file(psp font file) or maybe a txt files anyway can anybody try to find that for me because Im trying to edit some stuff with the game files and put them back into the game so please help me

after decrypting BBS1, BBS2 and BBS3 dat, i found more *.pmo files, the map models could be in BBS2.dat, every *.pmo there don't have bones (my script won't work) but from the tex names, it could be (kg10_05ts.tm2, kg10_sky.tm2, etc.)

(to decrypt them you need a CFW PSP, jpcsp rev >1500 and Jpcsp Connector)

i wrote another bms script for extracting *.arc files
the first (0.arc) file has all the font files

cmdfont.clu, FontIcon.mtx, menufont.inf, menufont.clu, menufont.mtx, ...
mtx is the texture file, every letter is 8x8 or 16x16, but it's not TIM2, i can't decode them fully

for the model files, i'm still not able to read them fully, but i'm now able to read any mesh header without errors,
(i use 010 Editor Templates to read them)
here my basic header format:

```
if (DataCount1 == 0)
{
    short DataCount1_1;
}
byte Mesh_unk1;
byte DataSize1;
short Mesh_unk2;
byte Mesh_unk3;
byte MeshType;
byte Mesh_unk4;
byte DataCount2;
byte Mesh_unk5;
byte Mesh_unk6;
byte Mesh_unk7[8];
```


so far i know 4 MeshType's
0x30, 0x31, 0x40, 0x41

0x30 and 0x40 have a 20 byte header
0x31 and 0x41 have a 24 byte header

all 4 are used in static and deformable mesh, but i'm not able to understand the mesh format,
it seams easy, but i get only junk in my 3D Viewer after exporting to obj
i can't identify what is vertice, normal or uv....
i try to read them as signed shorts, don't know if this is wrong, i'm not good in reversing 3d models.

```
Printf("v %d %d %d\n", MeshData[0], MeshData[1], MeshData[2]);
```

[extract_arc.rar](https://xentaxbackup.github.io/file/3122_extract_arc.rar)
## Post #20
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-06-08T13:50:08+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Falo, fatduck managed it on the last page, so maybe you could just ask him how he managed it, or you could forward this to someone else who knows more that can help you?  

valvoga, sorayahya, I see what you've done.
## Post #21
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-06-09T03:23:18+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

how to extract the PMO and TIM2 files using hex editor and quick bms script please help i don't understand because im a noob if you don't mind please explain it in details how to do it please
## Post #22
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2010-06-24T17:53:09+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I successfully encoded BBS1\BBS2\BBS3. Is there a way just to filter out the TM2 files?
## Post #23
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2010-06-25T02:32:05+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

After very very long thinking and many failed trys:
[http://www.imagebanana.com/view/jiba9ahh/test.jpg](http://www.imagebanana.com/view/jiba9ahh/test.jpg)

It's a common psp format, at first i thought it was half-float but it is  "signed short / 100" like ff7cc.
Vertices are now readable ^^, next normals and uv, i hope i can finish it this weekend.

> I successfully encoded BBS1\BBS2\BBS3. Is there a way just to filter out the TM2 files?
I could write you a bms script, but most of the tm2 files are textures and useless without models.

//edit
small update:
[http://www.imagebanana.com/view/2xxgns52/test2.jpg](http://www.imagebanana.com/view/2xxgns52/test2.jpg)

now my c prog reads size 12,14,16,18, Verts, Normals and uv, model output is perfect but no faces...
i found some data which could be faces, but 74 faces for 402 Verts in Mesh0 seams a bit strange...
## Post #24
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-06-25T09:31:00+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

try just using the faces as if the verts are in the correct order a lot of psp games do this where there is no face data in the files they are just in tri-strip order.
## Post #25
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2010-06-25T12:35:03+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from chrrox
>
> try just using the faces as if the verts are in the correct order a lot of psp games do this where there is no face data in the files they are just in tri-strip order.

doesn't work
[http://www.imagebanana.com/view/5onjo20o/faces.jpg](http://www.imagebanana.com/view/5onjo20o/faces.jpg)

maybe my code is wrong

```
			for(numFaces=numFaces+numData1;y<numFaces;y=y+3)
			{
				fprintf(outfile,"f %d %d %d\n",y+1,y+2,y+3);
			}
```
## Post #26
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2010-06-25T17:11:44+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Falo
>
> After very very long thinking and many failed trys:
http://www.imagebanana.com/view/jiba9ahh/test.jpg

It's a common psp format, at first i thought it was half-float but it is  "signed short / 100" like ff7cc.
Vertices are now readable ^^, next normals and uv, i hope i can finish it this weekend.
I successfully encoded BBS1\BBS2\BBS3. Is there a way just to filter out the TM2 files?
I could write you a bms script, but most of the tm2 files are textures and useless without models..

That's no problem, I'm looking for all plain textures. A script would be very helpful.
## Post #27
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-06-25T23:41:09+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I think we should ask fatduck he already extract the model see in page 1
## Post #28
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2010-06-26T07:18:16+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

// edit 1

after again some hours testing different combinations i got it to work,

the strange table is very simple, let's say we have 100 Vertices,
this table could be then 25, 20, 15, 10, 10, 5, 5, 5, 5, 0  (25+20+15+10+10+5+5+5+5+0 = 100)

```
{
	if(Table[x] != 0) // special case 0 -> no face
	{
		for(int i=1,i+2<Table[x];i++,numVerts++)
		{
			fprintf(outfile,"f %d %d %d\n",numVerts+1,numVerts+2,numVerts+3);
		}
		numVerts=numVerts+3;
	}
}
```

so what does this code ?:
simple it skips 2 faces...

here an exported Aqua Model:
[http://www.imagebanana.com/view/kb0noouu/aqua.jpg](http://www.imagebanana.com/view/kb0noouu/aqua.jpg)
it's 90% finished, it just need some code tweaks and i have a fully working exporter. (some very little Faces are missing....)

// update 1:
[http://www.imagebanana.com/view/aiyw16s/aqua.jpg](http://www.imagebanana.com/view/aiyw16s/aqua.jpg)
[http://www.imagebanana.com/view/ly98aum/eraqus.jpg](http://www.imagebanana.com/view/ly98aum/eraqus.jpg)
[http://www.imagebanana.com/view/8iaej2vk/Vanitas.jpg](http://www.imagebanana.com/view/8iaej2vk/Vanitas.jpg)
[http://www.imagebanana.com/view/8295do2t/Zack.jpg](http://www.imagebanana.com/view/8295do2t/Zack.jpg)

faces are completly fixed now and UV data works but need some work,
PS: this is how to decode UV

```
fprintf(outfile,"vt %f %f\n",TextureU/128,(TextureV+128)/128);
```


// update 2:
[http://www.imagebanana.com/view/zxaitryn/Vanitas2.jpg](http://www.imagebanana.com/view/zxaitryn/Vanitas2.jpg)
it was just a small bug UV works now complete,
the last few bugs are from rendering and tm2 exporter alpha color bug (fixable with Game Graphic Studio / Photoshop)

i'm working now on decoding normals and reversing structSize 20,22,24,26,28 (building/world models)
## Post #29
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2010-06-27T22:31:52+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Wow that look really great.
## Post #30
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-06-28T00:00:48+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Woah nice 

...thats a rather mean choice for an avatar...
## Post #31
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-06-28T00:56:44+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Wow that is awesome thanks for all of your hard work falo
## Post #32
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2010-07-01T11:32:47+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

The contents of this post was deleted because of possible forum rules violation.
## Post #33
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-07-01T13:02:57+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I've tested the obj converter...there is no geometry at all. I have tried 702.pmo and 396.pmo, and there is no geometry in either of them.

I read in the readme about formats with bones, I think MrAdults has a documentation of collada .dae files on his website somewhere if you want to try that?
## Post #34
- Username: fadedsoulz
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jul 02, 2010 3:46 am
- Post datetime: 2010-07-02T03:32:10+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Which .dat are the maps/worlds stored in?
## Post #35
- Username: fadedsoulz
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jul 02, 2010 3:46 am
- Post datetime: 2010-07-02T04:20:45+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

for some reason, i can't get any .pmo files out of BBS2.dat, it only gives me 2 folders. For the rest, 0,1,3, it works fine.
## Post #36
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2010-07-02T08:07:53+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from fadedsoulz
>
> Which .dat are the maps/worlds stored in?
all Maps are in BBS2.dat, world models have a wm in it's name

> Reply from fadedsoulz
>
> for some reason, i can't get any .pmo files out of BBS2.dat, it only gives me 2 folders. For the rest, 0,1,3, it works fine.

it will not work with BBS2.dat, all PMO's there don't have bones and most of them have shared textures -> crash the script
## Post #37
- Username: fadedsoulz
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Jul 02, 2010 3:46 am
- Post datetime: 2010-07-02T11:29:08+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Is there any way to extract the files in BBS2.dat?
## Post #38
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-07-05T12:47:44+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Just thought i'd say this:

These models are not to be ported to another game. You know who you are, and whoever spilled the beans and told you, is in some pile of trouble when i find out who they are.

They are not meant to be used like that, and if you persist, I may have to get this thread removed.

Understood? Good.

Any progress Falo?
## Post #39
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-07-20T13:23:48+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Falo, you wrapped the tm2 files around Aqua, Vanitas, and others in just the right way. When I exported the files and reintegrated them with 3D Studio Max and other 3D programs, I found that in some of them, the eye and mouth textures came out all weird. How do I fix the eyes and mouth, and more importantly, how do I use bones.txt to make the models poseable?
## Post #40
- Username: philip92dk
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Jul 26, 2010 3:52 am
- Post datetime: 2010-07-30T21:11:09+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

i need a tutorial on how to extract the files in BBS.dat can somone help me?
## Post #41
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2010-08-03T13:50:56+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

The contents of this post was deleted because of possible forum rules violation.
## Post #42
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-08-03T15:52:34+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I had trouble extracting the _793_.pmo file. Apparently, there are so many textures, it crashes before extracting any more than a few broken tm2 files. Also, I don't know how to implement the bones.txt files on the 3D models. In addition, many of the textures for the faces and mouths do not wrap correctly on some of the models. Is there anyone who can remedy any of those problems?
## Post #43
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-08-09T05:44:05+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from valvoga
>
> For tim2, file we can convert tim2 file to png using MrAdults amazing tools "mesh2rdm"
Here is the link :
http://www.richwhitehouse.com/index.php ... rdmv45.zip
To use it just make a new notepad type "mesh2rdm file.tm2 outfile.png" in the notepad,then rename .txt with .bat then press enter on the bat file

I've tried this with little luck. I have had "mesh2rdm file.tm2 outfile.png" without quotes in the .bat and it seems to do nothing. I try changing file to the actual file name and it still doesn't seem to do anything. I have mesh2rdm and the .bat and the .tm2 in the same folder. Why isn't it working?

---

Also I tried dragging and dropping a .pmo onto kh_pmo.exe and this is all I get:



As you can see it does say it dumped them but I don't see anything in the folder with the .pmo and kh_pmo.exe so is it dumping it somewhere else or is it just not working correctly for some reason? It closes immediately after flashing onto the screen I had to do some clever print screening to see what it said.

Any help would be greatly appreciated. I'd love to start learning and assisting with this.

Edit: Good news! I figured out that kh_pmo.exe was extracting the models just as it said it was. It was just dumping them in my "C:\Documents and Settings\Username\" folder instead. Kind of an odd place but as long as I can find them I'm happy.

As for the .tm2 problems I never did figure out how to do it with mesh2rdm but then I found [Noesis](http://oasis.xentax.com/index.php?content=downloads)! It was able to export them to .png and .tga with ease.

So now I have been able to produce this:



Looks a whole lot like Ventus to me!   He's got some uv issues with his face and some parts of his arm and other random areas don't seem to have a UV map at all. But it's definite progress for me thanks to all you who have contributed tools.

I have him set to unshaded though because I had to make him display both the front and back faces because half of them are flipped. I'm not sure if this is an issue with the normals or what but it's an issue I'd love to be able to solve. Thanks for what you've done so far. Any news of more developments would be great.
## Post #44
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-08-10T03:57:07+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Alright well I'm making progress. I've been able to rip and animate Aqua for artistic purposes (such as my avatar).

But things aren't perfect. The models have the entire mesh/geometry but it appears as if every other face is reversed. So they are still there but can only be seen through the opposite side or from inside the model. They look like this:



But if the right settings are applied it is possible to make the model look more natural. What I've been doing is making the faces "two-sided" or telling the program to "draw backfaces". Essentially meaning that I cause the program to show the reversed face just as if it were facing forward like it should be. Though these edges appear darker and still make the model look bad so I just disable lighting on the model. One such method of that is making the material layer for the texture emmisive so there are no shadows on it.

With the correct settings applied the model looks like this:



And now the model appears more natural. I can proceed to bone, animate, pose it etc. But I must admit this is more a work around than a perfect fix. I would love it if anyone can suggest to me anything to fix this problem. Doing this manually is an option but 1000-3000 individual triangles to do it to is quite tedious.

This may also have to do with the normals. Does anyone have any suggestions? As you can see by my avatar I can get them to look just fine but like I said it's a work around and not an actual solution to the real problem.

Any ideas how to fix this better or would it just be best to wait for Falo to release an updated version of his converter?
## Post #45
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-08-10T07:10:29+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I don't know how to implement the bones.txt files on the 3D models. Have you been able to get them to work?
## Post #46
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-08-10T12:32:29+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Hey,that was awesome zerox,aqua look awesome
to implement bone you can ask MrAdults zerox ,since he can implement bone in smd
But MrAdults hasn't been here for a long time cause he is taking a vacation
You're awesome zerox
## Post #47
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-08-10T12:36:07+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Zerox, you just needed to make a bat file for it  Coz you didnt use one, thats why the ended up in a random folder.

The flipped geometry is a problem with the normals, Falo hasnt figured those out yet.
## Post #48
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-08-10T13:24:30+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

The flipped faces are caused by the order of face indexes written in the obj file. 
You can try playing with that order. 
I wrote an exporter for kingdom hearts models some time ago, i had the exact same problem with the normals.
However i still haven't figured it out... My only guess is that the KH BBS game engine doesn't care about the normals at all...
## Post #49
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-08-10T19:04:08+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from ultimaespio
>
> Zerox, you just needed to make a bat file for it  Coz you didnt use one, thats why the ended up in a random folder.

The flipped geometry is a problem with the normals, Falo hasnt figured those out yet.

Well hopefully Falo or someone else can figure out the problem soon. And I'll take note of that and try using a .bat file next time. Maybe I sound like a total noob here but what would I put into the .bat file then?

> Reply from valvoga
>
> Hey,that was awesome zerox,aqua look awesome
to implement bone you can ask MrAdults zerox ,since he can implement bone in smd
But MrAdults hasn't been here for a long time cause he is taking a vacation
You're awesome zerox

Well I had to do lots of fixing to it but yeah I'm able to get the models looking decent. I would love such a method but I guess since he's gone we'll have to wait. Premade bones would be easier than adding them myself.

> Reply from ChrisSquareFan
>
> The flipped faces are caused by the order of face indexes written in the obj file. 
You can try playing with that order. 
I wrote an exporter for kingdom hearts models some time ago, i had the exact same problem with the normals.
However i still haven't figured it out... My only guess is that the KH BBS game engine doesn't care about the normals at all...
I would try looking at the obj file to figure that out but I'll be honest, I currently have no idea where to even begin with that. But I wouldn't mind learning.

Is that an exporter for KH1 or KH2? I'd be interested in looking at it. Who knows maybe by comparing what you did there with what Falo has done here maybe everyone could work together to figure out a fix? 

As for the BBS engine not caring about normals at all I hardly doubt that's true. It's probably just something with the way we (as in Falo) is reading the mesh. I'm sure there is some way to fix it we just haven't found it yet. If the BBS engine didn't care about normals they couldn't do lighting in the game without major issues.  

> Reply from Mirrorman95
>
> I don't know how to implement the bones.txt files on the 3D models. Have you been able to get them to work?
I haven't but I'd love it if someone could figure it out.

-----------

So I'm just learning the basics of programming in C and such things at the moment so this may not even be possible. But is it possible for one of us to continue where Falo left off? I'm not sure what all went into his converter but if it's something someone could experiment with and continue that would be an worth while effort until Falo comes back I think. Course we may need his source code then I suppose.
## Post #50
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-08-10T19:15:51+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

For the BAT File:

```
kh_pmo.exe IN.pmo OUT.obj
```


Change IN to the PMO file you want, then change OUT into whatever you want to call the obj file.

I know absolutely nothing about programming, so I cant help :/ But maybe when Mr Adults comes back he might help. Unless theres someone else who knows how to do this sorta stuff that just isnt saying anything?
## Post #51
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-08-10T19:17:53+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Yeah that's what I figured it'd be like. Just wanted to make sure. Haha thanks. With luck someone can make more progress on this. Especially on the UV issues with some models like Terra.
## Post #52
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-08-11T08:35:04+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Is there a post where i can see the pmo file format and what was found so far?
## Post #53
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-08-11T11:45:39+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Most of Falo's posts on the 1st page should help you. Are you planning on helping with the format?
## Post #54
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-08-11T14:20:26+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Yes, i'm thinking of creating an exporter that supports .fbx file format. 
FBX works for both maya and 3ds max. 
Without fbx you'd have to import the obj file and create a script for creating bones (3ds max) / joints (maya) and for skinning. 
With fbx you get everithing in one file: model mesh skinned to bones/joints and texture maps.
## Post #55
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-08-11T15:30:21+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I've been able to get the normals correct after the model is converted. I have found that importing the models into Blender (free 3D program) and going into Edit Mode, Go to Mesh > Normals > Recalculate Outside. Or you could press Ctrl+N and make sure you have all the faces selected. Doing such will fix most the normals making it a whole lot less to fix after the fact.

It by no means is a perfect method considering you still have to manually reflip some faces by hand. But it's a lot less work than it would have been before by about 100x.



Before this I would have said that the models initially looked like they went through a blender. But seeing as the blender is what is doing the fixing this time I'm not sure I can say that anymore.

Either way a real fix when we convert it straight from the pmo to the obj would be even better.
## Post #56
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-08-11T15:39:29+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from ChrisSquareFan
>
> Yes, i'm thinking of creating an exporter that supports .fbx file format. 
FBX works for both maya and 3ds max. 
Without fbx you'd have to import the obj file and create a script for creating bones (3ds max) / joints (maya) and for skinning. 
With fbx you get everithing in one file: model mesh skinned to bones/joints and texture maps.

Yeah that would be better. Falo's posts should help you with that.

> Reply from Zerox
>
> I've been able to get the normals correct after the model is converted. I have found that importing the models into Blender (free 3D program) and going into Edit Mode, Go to Mesh > Normals > Recalculate Outside. Or you could press Ctrl+N and make sure you have all the faces selected. Doing such will fix most the normals making it a whole lot less to fix after the fact.

It by no means is a perfect method considering you still have to manually reflip some faces by hand. But it's a lot less work than it would have been before by about 100x.

http://img440.imageshack.us/img440/2426 ... nanima.png

Before this I would have said that the models initially looked like they went through a blender. But seeing as the blender is what is doing the fixing this time I'm not sure I can say that anymore.

Either way a real fix when we convert it straight from the pmo to the obj would be even better.

I think that's what I did with my Aqua model. Just couldnt remember how I did it  A proper fix would be really nice. Any way we could help ChrisSquareFan?
## Post #57
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2010-08-11T23:45:51+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Figured i would chime in real quick.

Still working on confirming a lot of the findings, as i have not looked to deeply into getting a better method of extracting the PMO files from the main files yet.  Since i have not coded anything up to actually convert the data, i figured hopefully this will be helpful for others to help verify until i can post a more complete description of what i have so far.

```
		{
			uint32 texCoord : 2; // texture coordinate format: 0 - none, 1 - uint8, 2 - uint16, 3 - float
			uint32 unknown0 : 5; // unsure of bit size, but when this is not zero, diffuse color is present in vertex data
			uint32 position : 2; // position format: 0 - none, 2 - int16, 3 - float > Still look
			uint32 skinning : 1; // only seems to be set when there are joint weights present?
			uint32 unknown1 : 4;
			uint32 jointCnt : 4; // maximum joint index used? (index count = joint count + 1 - or just use (jointCnt + skinning)
			uint32 unknown2 : 6;
			uint32 diffuse  : 4; // seems to only be set when a diffuse color is present in header
			uint32 dataType : 4; // 0x30 - tri-list, 0x40 - tri-strip - ?
		} dataFlags;

```


So far this has allowed my 010 Editor template to successfully parse all the data i have found so far, but as i said i am still confirming some things against more files.

```
			{
				local uint32 jointCount = dataFlags.skinning + dataFlags.jointCnt;
				if (jointCount > 0)
				{
					uint8  jointWeights[jointCount];
				}
				
				if (dataFlags.texCoord > 0)
				{
					switch (dataFlags.texCoord)
					{
					case 1:
						uint8  textureCoord[2];
						break;
					case 2:
						FSkip((0x02 - ((FTell() - startof(this)) & 0x01)) & 0x01);
						uint16 textureCoord[2];
						break;
					case 3:
						FSkip((0x04 - ((FTell() - startof(this)) & 0x03)) & 0x03);
						float  textureCoord[2];
						break;
					default:
						Printf("Unrecognized texture coordinate format! - 0x%08X\n", FTell());
						break;
					}
				}
				
				if (dataFlags.unknown0 != 0)
				{
					FSkip((0x04 - ((FTell() - startof(this)) & 0x03)) & 0x03);
					uint32 diffuseColor <format = hex>;
				}
				
				if (dataFlags.dataFlags.position != 0)
				{
					switch (dataFlags.position)
					{
					case 2:
						FSkip((0x02 - ((FTell() - startof(this)) & 0x01)) & 0x01);
						int16  position[3];
						break;
					case 3:
						FSkip((0x04 - ((FTell() - startof(this)) & 0x03)) & 0x03);
						float3 position;
						break;
					default:
						Printf("Unrecognized position format! - 0x%08X\n", FTell());
						break;
					}
				}
				
				local uint32 paddingSize = vertexSize - (FTell() - startof(this));
				if (paddingSize > 0)
				{
					uint8  padding[paddingSize];
				}
			} vertex;

```


The main things to note is the padding considerations necessary to ensure data type start on the correct byte.  The most common padding byte value is 0xAB, so if you get a value containing that you are more than likely covering the wrong bytes for that data type.  So for the moment i have just chosen alignments that work for the data i have come across so far.

If things work out, i will probably just go ahead and thrown from output statements in the template to convert to obj and see what happens.  In the meantime i guess we can working on vofirming or denying these things and see what else there is.

Let me know if something doesn't makes sense or i have made a silly mistake somewhere, heh.

Hope that helps.

What else are others working on deciphering?


EDIT: Update for float position information....still looking for whether or not positions can be 8-bit values...
## Post #58
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-08-12T02:52:33+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

revelation I wish I knew how to use that information you posted but I am not sure where to start as I'm inexperienced with information like that. Any advice on where to learn what it all means would be something I would look into for sure.

Anyway I was curious is there an easy way to convert a big batch of .pmo models using Kh_pmo.exe? The .bat method works great but it only works for one at a time. I was considering trying just dragging and dropping a bunch on at once. But I was wondering if there was a way to get the ones within folders by just selecting one big folder overall that contains everything.

As it stands right now I think that we essentially have two major problems. The normals being flipped upon conversion. And some models not retaining UV mapping data. There are other things like bones and animations but I think the other two are the more critical ones at this point in time.

Personally I would really like the problems with messed up UV data fixed. I'm willing to try to help fix it if anyone can at least give me a starting point on what we know already and how I might proceed.
## Post #59
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2010-08-12T03:39:32+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I am not sure how the current converter in this thread is handling the faces.  But the face ordering should just be a matter of handling the change between each face when converting tri-strips, versus not having to with tri-lists.  So far, unless there is something i have not seen, i have not found any normal data in the files, and more than likely all lighting is baked directly into the textures.  The UV information should also just be a matter of handling the correct alignment of the data in the vertex information, which is mainly what i posted above covers.  But i will have to see once i actually attempt converting some of the data given what i have found out so far.  Probably going to try that here in a sec since i have tested against a good deal of the files i have extracted so far.  Still looking for any more inconsistencies in the current way i am handling things so that all cases are covered.  Will have to see i guess.
## Post #60
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-08-12T04:12:48+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Ah well alright. It may very well be that's how they did the lighting it just seems odd to do it that way though. If you think you have a fix for the UV data when converting I recommend you try these files:

p03ex00.pmo (Terra Low Poly) and p01ex00.pmo (Ventus Low Poly)

Both have UV issues. Ventus has less issues but there definitely is missing UV data.



But the low poly Terra is worse. He has absolutely no UV data retained when converting him with Falo's converter. I could post both the files if you want. I'm happy to help where I can.
## Post #61
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-08-12T21:51:07+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Hang on, Zerox, how did you get them to extract with those names? My extracted pmo's are named 1.pmo 2.pmo. How did you get them to extract with their original names?
## Post #62
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-08-13T00:32:35+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I used Falo's BMS script. On all of the BBS# files. It does dump numbered pmo's your correct. But it also dumps named pmo's within folders. That's all there is to it.
## Post #63
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-08-13T00:34:22+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Hmm interesting
## Post #64
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-08-13T00:43:20+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Did you not get such files or did you extract them differently? They were in plain sight for me.
## Post #65
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-08-13T13:48:32+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I only used it on BBS0.dat, maybe thats why.

ChrisSquareFan I see you were on Yaz0r's forum 

Hopefully someone can work these models out, with bones and everything 

Didnt Falo say something about the normals being auto calculated?
## Post #66
- Username: denetsu
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jul 05, 2010 2:03 pm
- Post datetime: 2010-08-14T03:09:32+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Where are stored the animations?
## Post #67
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-08-15T07:22:59+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I'd like to start assisting with figuring out the model format. I'm new to reverse engineering and stuff though. So could anyone perhaps help me to go through what's already been figured out about the format so I could help out more? Or really any other format is fine. I'd just like to eventually be able to help out with these models more.
## Post #68
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-08-15T14:59:47+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I looked into the pmo file, looks manageable. I'm also studying fbx sdk to make a fbx exporter.
## Post #69
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-08-15T15:07:33+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Zerox
>
> I'd like to start assisting with figuring out the model format. I'm new to reverse engineering and stuff though. So could anyone perhaps help me to go through what's already been figured out about the format so I could help out more? Or really any other format is fine. I'd just like to eventually be able to help out with these models more.

I know, its awful wanting to help but not being able to.

> Reply from ChrisSquareFan
>
> I looked into the pmo file, looks manageable. I'm also studying fbx sdk to make a fbx exporter.

Great! FBX supports bones doesnt it?
## Post #70
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-08-15T15:09:33+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from ultimaespio
>
> I only used it on BBS0.dat, maybe thats why.

ChrisSquareFan I see you were on Yaz0r's forum 

Hopefully someone can work these models out, with bones and everything 

Didnt Falo say something about the normals being auto calculated?
Yeah, that was ages ago though ^^
At that time i managed to make an exporter using yaz0r's tool, and after that my own exporter,
but the normals got out wrong
That is how i did this:
[http://xdeviantchris.deviantart.com/gallery/#/d2588bn](http://xdeviantchris.deviantart.com/gallery/#/d2588bn)
Also, this  :
[http://www.youtube.com/watch?v=OG_3p-eu26s](http://www.youtube.com/watch?v=OG_3p-eu26s)
## Post #71
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-08-15T15:12:28+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from ultimaespio
>
> Great! FBX supports bones doesnt it?
Yes it does
## Post #72
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-08-15T15:13:10+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Such a tease 

Would you mind uploading the kh1 exporter with bones if you still have it? That would be real nice  

...I feel as if I've asked that before :S lol
## Post #73
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-08-15T17:19:19+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

The contents of this post was deleted because of possible forum rules violation.
## Post #74
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-08-15T18:22:54+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Don't you worry about that, I will not.
## Post #75
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-08-18T16:55:34+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Ah some interesting tools. Not all of them are useful to me but they're interesting. Perhaps it's just my lack of understanding on how to effectively use them together but that's fine.

Anyway, has anyone made any progress at all on this? It would be great to have the model format figured out completely before the release of the game.
## Post #76
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-08-18T17:26:28+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Well I actually thought that, when its released in English, more people will be interested in it.
## Post #77
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2010-08-23T14:58:33+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Hmm well i was able to extract the pmo files from the bbs#.dat and also used quickBMS to extract  TM2 files but thats about it,when i open them through mesh2rdm the textures are all scrambled like and well really hard to understand ^^" so is there anyway to view them properly?? ^^" i mean i tried what Zerox did and that was through Noesis But when i open Noesis and open the tm2 files in that and in the above bar click file --> export,it just creates the same file  idk what to do now  can anyone help me please ^^
## Post #78
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-08-24T07:49:53+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Make sure you export the tm2 files as .png or .tga by adding that to the end of the file name.
## Post #79
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2010-08-24T08:04:19+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Zerox
>
> Make sure you export the tm2 files as .png or .tga by adding that to the end of the file name.

Hmmw well i opened the tm2 file in noesis and this was my before the exoprt



and this was after the export



so as you can see the result is the same
## Post #80
- Username: Panzah
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Jul 22, 2010 5:11 am
- Post datetime: 2010-08-24T08:37:57+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Are you a newbie? That's exactly how textures look. There is nothing wrong with them. If you though that textures are models, then you are wrong.
Models are 3D meshes made out of polygons (triangles of different sizes and shapes placed in three dimensional space). Textures are what you could call a "skin" which is put on the model. I don't really know how to explain it to a person who doesn't seem to know what he's doing so well, I guess this will have to do.
Basicly, what you exported are textures and they are just fine, nothing wrong with them.
## Post #81
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2010-08-24T08:42:23+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Panzah
>
> Are you a newbie? That's exactly how textures look. There is nothing wrong with them. If you though that textures are models, then you are wrong.
Models are 3D meshes made out of polygons (triangles of different sizes and shapes placed in three dimensional space). Textures are what you could call a "skin" which is put on the model. I don't really know how to explain it to a person who doesn't seem to know what he's doing so well, I guess this will have to do.
Basicly, what you exported are textures and they are just fine, nothing wrong with them.

actually yeah im a newbie ^^" and well i know i extracted textures BUT then how can we extract models??

EDIT:Kk guys i founded out that .obj file is actually the model and i opened it up in Blender and got this result



So now can anyone tell me on HOW exactly CAN i apply textures on it,and is there an easier program then Blender since its camera controls are really bad ^^"
## Post #82
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-08-24T18:21:30+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Yeah the .objs are the exported models. And I will admit I have no idea how to use Blender for anything other than importing and exporting. An easy alternative I can think of is Milkshape 3D, though it's not nearly as capable as Blender, it is more simplistic and user friendly. You can start it out with a 30 day free trial and then it's only $20 USD.
## Post #83
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2010-08-24T18:52:52+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Zerox
>
> Yeah the .objs are the exported models. And I will admit I have no idea how to use Blender for anything other than importing and exporting. An easy alternative I can think of is Milkshape 3D, though it's not nearly as capable as Blender, it is more simplistic and user friendly. You can start it out with a 30 day free trial and then it's only $20 USD.

ahh thanks zeorx ^^ i already have a registered milkshop  and well that aside can you tell me that how can i apply textures to these models?? ^^
## Post #84
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-08-25T22:23:52+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Well in Milkshape you select the geoset group you want to give a texture and then in the materials tab select the material with your texture and double click it to assign it or just click the assign button.

All off-topic aside is anyone trying to make any progress on this?
## Post #85
- Username: Panzah
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Jul 22, 2010 5:11 am
- Post datetime: 2010-08-28T13:08:53+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Zerox
>
> Well in Milkshape you select the geoset group you want to give a texture and then in the materials tab select the material with your texture and double click it to assign it or just click the assign button.

All off-topic aside is anyone trying to make any progress on this?

Well, I guess nobody is working on this anymore, and I too would like to have a good exporter that would support normals and hopefully bones along with all the weights aswell.
## Post #86
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-08-28T13:12:29+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Or maybe ChrisSquareFan is working on it, and just hasnt posted in a while. He's maybe busy or doesn't know that the forum has just come back after the attack.
## Post #87
- Username: philip92dk
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Jul 26, 2010 3:52 am
- Post datetime: 2010-08-28T14:19:53+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

how do i export PMO and tm2 from the iso ?
## Post #88
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2010-08-28T18:28:55+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Most information about the format has already been posted in this thread in one form or another, and i was hoping the flag information would be helpful to the original tool developers in this thread.  But seeing as they have not posted since then, i don't even know if they have seen the information.  Unfortunately this format was not at the top of my todo list yet, and i don't have any direct contact with either Falo or fatduck.

There are still some things to figure out regarding how the flags work...i will see if i can make some time to look into things more.

In the meantime i guess i will post this for others that may know what to do with it:

```
 * pmo.bt - Structure definitions for Kingdom Hearts: Birth by Sleep - pmo file related entities.
 *
 *****************************************************************************
 * Revision History:
 *  2010/08/11 - revel8n - Original
 */

#include "common-types.bt"

SetReadOnly(true);

// #pragma displayname("pmo structures")
// #pragma fileextensions(".pmo")

// #pragma byteorder(little_endian)
LittleEndian();

// mark used bytes with a light green background
SetBackColor(cLtGreen);

BitfieldDisablePadding();

enum GsPSM //<uint32> 
{
// Pixel Storage Format (0 = 32bit RGBA)

	GS_PSMCT32		= 0,
	GS_PSMCT24		= 1,
	GS_PSMCT16		= 2,
	GS_PSMCT16S		= 10,
	GS_PSMT8		= 19,
	GS_PSMT4		= 20,
	GS_PSMT8H		= 27,
	GS_PSMT4HL		= 36,
	GS_PSMT4HH		= 44,
	GS_PSMZ32		= 48,
	GS_PSMZ24		= 49,
	GS_PSMZ16		= 50,
	GS_PSMZ16S		= 58,
};

enum <uint8> IMG_TYPE 
{
	IT_RGBA			= 3,
	IT_CLUT4		= 4,
	IT_CLUT8		= 5,
};

enum <uint8> CLT_TYPE
{
	CT_A1BGR5		= 1,
	CT_XBGR8		= 2,
	CT_ABGR8		= 3,
};

typedef struct
{
    uint64 TBP0 :14; // Texture Buffer Base Pointer (Address/256)
    uint64 TBW  : 6; // Texture Buffer Width (Texels/64)
    GsPSM  PSM  : 6; // Pixel Storage Format (0 = 32bit RGBA)
    uint64 TW   : 4; // width = 2^TW
    uint64 TH   : 4; // height = 2^TH
    uint64 TCC  : 1; // 0 = RGB, 1 = RGBA
    uint64 TFX  : 2; // TFX  - Texture Function (0=modulate, 1=decal, 2=hilight, 3=hilight2)
    uint64 CBP  :14; // CLUT Buffer Base Pointer (Address/256)
    GsPSM  CPSM : 4; // CLUT Storage Format
    uint64 CSM  : 1; // CLUT Storage Mode
    uint64 CSA  : 5; // CLUT Offset
    uint64 CLD  : 3; // CLUT Load Control
} GsTex0;

struct PMO_TEXTURE_HEADER
{
	// 0x00
	SetBackColor(cLtBlue);
	uint32 dataOffset <format = hex>;
	SetBackColor(cLtYellow);
	char   resourceName[0x0C];
	// 0x10
	SetBackColor(cLtGreen);
	uint32 unknown0x10[4];
	
	if (dataOffset < FileSize())
	{
		local int64 filePos = FTell();

		FSeek(dataOffset);
		// TM2 File Structure
		struct TM2_FILE
		{
			SetBackColor(cLtBlue);
			// tm2 File Header Structure - 0x10 (16) bytes
			struct TM2_HEADER
			{
				char   fileID[4]; // usually 'TIM2' or 'CLT2'
				uint8  version;   // format version
				uint8  id;        // format id
				uint16 imageCount;
				uint32 padding[2];
			} fileHeader; // file header
			
			struct
			{
				struct TM2_IMAGE_DATA
				{
					SetBackColor(cLtGreen);
					struct TM2_PICTURE_HEADER
					{
						// 0x00
						uint32 totalSize  <format = hex>;
						uint32 clutSize   <format = hex>;
						uint32 imageSize  <format = hex>;
						uint16 headerSize <format = hex>;
						uint16 clutColors;
						// 0x10
						uint8  format;
						uint8  mipMapCount;
						CLT_TYPE clutType;
						IMG_TYPE imageType;
						uint16 width;
						uint16 height;
						
						GsTex0 GsTex0b; //[8];
						// 0x20
						GsTex0 GsTex1b; //[8];
						uint32 GsRegs;
						uint32 GsTexClut;
					} pictureHeader;
					
					SetBackColor(cLtRed);
					struct
					{
						uint8  data[pictureHeader.imageSize];
					} imagePixels;
					
					SetBackColor(cLtYellow);
					struct
					{
						uint8  data[pictureHeader.clutSize];
					} imageCLUT;
				} imageData[fileHeader.imageCount] <optimize = false>;
			} imageData;
		} textureData;
		
		FSeek(filePos);
	}
};

struct PMO_MESH_HEADER(uint32 skeletonOffset)
{
	SetBackColor(cLtBlue);
	// 0x00
	uint16 vertexCount;
	
	if (vertexCount == 0)
		break;
		
	uint8  textureID;
	uint8  vertexSize;
	SetBackColor(cLtBlue);
	struct
	{
		uint32 texCoord : 2; // texture coordinate format: 0 - none, 1 - uint8, 2 - uint16, 3 - float
		uint32 unknown9 : 2; //
		uint32 unknown0 : 3; // unsure of bit size, but when this is not zero, diffuse color is present in vertex data
		uint32 position : 2; // position format: 0 - none, 2 - int16, 3 - float
		uint32 skinning : 1; // only seems to be set when there are joint weights present?
		uint32 unknown1 : 4;
		uint32 jointCnt : 4; // maximum joint index used? (index count = joint count + 1 - or just use (jointCnt + skinning)
		uint32 unknown2 : 6;
		uint32 diffuse  : 1; // seems to only be set when a diffuse color is present in header
		uint32 unknown3 : 3;
		uint32 dataType : 4; // 0x30 - tri-list, 0x40 - tri-strip - ?
	} dataFlags;
	SetBackColor(cLtBlue);
	uint8  unknown0x08;
	uint8  triStripCount;
	uint8  unknown0x0A[2];
	
	if (skeletonOffset != 0)
	{
		uint8  jointIndices[8];
	}
	
	if (dataFlags.diffuse & 1)
	{
		uint32 diffuseColor <format = hex>;
	}
	
	//Printf("Format flags for vertex size (0x%02X) - 0x%08X\n", vertexSize, dataFlags.flagValue);
	
	if (dataFlags.dataType == 3 && (vertexCount % 3) != 0)
		Printf("Tri-list vertex count mis-match (0x%02X) - 0x%08X\n", vertexCount, FTell());
	
	if (triStripCount > 0)
	{
		SetBackColor(cLtGreen);
		uint16 triStripLengths[triStripCount];
	}
	
	SetBackColor(cLtRed);
	struct
	{
		union
		{
			struct
			{
				local uint32 jointCount = dataFlags.skinning + dataFlags.jointCnt;
				if (jointCount > 0)
				{
					uint8  jointWeights[jointCount];
				}
				
				if (dataFlags.texCoord > 0)
				{
					switch (dataFlags.texCoord)
					{
					case 1:
						uint8  textureCoord[2];
						break;
					case 2:
						FSkip((0x02 - ((FTell() - startof(this)) & 0x01)) & 0x01);
						uint16 textureCoord[2];
						break;
					case 3:
						if (vertexSize != 0x10 && vertexSize != 0x14 && vertexSize != 0x18)
							Printf("Float texture coordinates at offset 0x%08X.\n", FTell());
						FSkip((0x04 - ((FTell() - startof(this)) & 0x03)) & 0x03);
						float2 textureCoord;
						break;
					default:
						Printf("Unrecognized texture coordinate format! - 0x%08X\n", FTell());
						break;
					}
				}
				
				if (dataFlags.unknown0 != 0)
				{
					switch (dataFlags.unknown0)
					{
					case 1:
						FSkip((0x04 - ((FTell() - startof(this)) & 0x03)) & 0x03);
						uint32 diffuseColor <format = hex>;
						break;
					case 2:
						uint8  diffuseColor[3] <format = hex>;
						break;
					default:
						Printf("Unrecognized color format! - 0x%08X\n", FTell());
						break;
					}
					
					if (vertexSize != 0x14 && vertexSize != 0x18 && vertexSize != 0x10)
					{
						Printf("Diffuse color present on unexpected vertex size (0x%02X) at 0x%08X\n", vertexSize, FTell());
					}
				}
				
				if (dataFlags.position != 0)
				{
					switch (dataFlags.position)
					{
					case 2:
						FSkip((0x02 - ((FTell() - startof(this)) & 0x01)) & 0x01);
						int16  position[3];
						break;
					case 3:
						FSkip((0x04 - ((FTell() - startof(this)) & 0x03)) & 0x03);
						float3 position;
						break;
					default:
						Printf("Unrecognized position format! - 0x%08X\n", FTell());
						break;
					}
				}
				
				local uint32 paddingSize = vertexSize - (FTell() - startof(this));
				if (paddingSize > 0)
				{
					uint8  padding[paddingSize];
				}
			} vertex;
			uint8 dataBytes[vertexSize];
		} vertexData[vertexCount] <optimize = false>;
	} vertexData;
	
	FSkip((0x4 - (FTell() & 0x3)) & 0x3);
};

struct PMO_JOINT
{
	SetBackColor(cLtBlue);
	uint16 index;
	uint16 padding0;
	
	uint16 parent;
	uint16 padding1;
	
	uint16 unknown0x08; // skinning index?
	uint16 padding2;
	
	uint32 unknown0x0C;
	
	// 0x10
	SetBackColor(cLtYellow);
	char   name[0x10];
	// 0x20
	SetBackColor(cLtGreen);
	float4x4 transform;
	float4x4 transformInverse;
};

struct PMO_SKEL_HEADER
{
	SetBackColor(cLtBlue);
	char   dataTag[4]; // 'BON'
	uint32 unknown0x04;
	uint32 jointCount;
	uint16 unknown0x0C; // number of skinned joints?
	uint16 unknown0x0E; // skinning start index
	
	struct PMO_JOINT jointData[jointCount];
};

struct PMO_HEADER
{
	SetBackColor(cLtBlue);
	// 0x00
	char   fileTag[4]; // 'PMO'
	uint8  unknown0x04[4];
	uint16 textureCount; //
	uint16 unknown0x0A;
	uint32 skeletonOffset <format = hex>;
	// 0x10
	uint32 meshOffset0 <format = hex>;
	uint16 triangleCount;
	uint16 vertexCount;
	float  unknown0x18; // radius?
	uint32 meshOffset1 <format = hex>;
	// 0x20
	SetBackColor(cLtGreen);
	float4 boundingBox[8];
};

struct PMO_FILE
{
	SetBackColor(cLtBlue);
	struct PMO_HEADER header;
	
	if (header.textureCount > 0)
	{
		struct
		{
			struct PMO_TEXTURE_HEADER textureInfo[header.textureCount] <optimize = false>;
		} textureInfo;
	}
	
	if (header.meshOffset0 != 0)
	{
		FSeek(header.meshOffset0);
		struct
		{
			while (!FEof())
			{
				struct PMO_MESH_HEADER meshInfo(header.skeletonOffset);
				
				if (meshInfo.vertexCount == 0)
					break;
			}
		} meshInfo0;
	}
	
	if (header.meshOffset1 != 0)
	{
		FSeek(header.meshOffset1);
		struct
		{
			while (!FEof())
			{
				struct PMO_MESH_HEADER meshInfo(header.skeletonOffset);
				
				if (meshInfo.vertexCount == 0)
					break;
			}
		} meshInfo1;
	}
	
	if (header.skeletonOffset != 0)
	{
		FSeek(header.skeletonOffset);
		struct PMO_SKEL_HEADER skeletonInfo;
	}
};

struct PMO_FILE fileInfo;

```


Hope it helps...

EDIT:
Changes representing new findings...
## Post #89
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-08-29T02:16:43+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Ah looks like lots of helpful information revelation. Sadly I don't know how I would go about using it as I'm a noob in such an area. Although perhaps I have something that can help. Today I came across a simple converter used for converting League of Legend's .SCO models to .OBJ models. .Sco is a proprietary format same as our PMD models we're attempting to convert.

The creator of this converter posted their source code for their converter. I figured that maybe the source code for their converter could be used to help us in the creation of our own converter for these models. So here's their source code for their converter:

```
//Converts the LoL's .sco model format into the .obj model format
#include<iostream>
#include<fstream>
#include<vector>
#include<string>
#include<sstream>
using namespace std;

struct vector3 {
    float x,y,z;
};
struct vector2 {
    float x,y,z;
};
struct face {
    vector<int> index;
};


int main(int argc, char* argv[]) {
    ifstream fin;   //file input stream
    ofstream fout;  //file output stream
    int vertcount;  //number of vertecies
    int facecount;  //number of faces

    if (argc < 2) {
        cout << "error: no input files\n";
        exit(1);
    }
    
    fin.open(argv[1]);  //open the first arguement from the command line
    if (fin.fail()) {
        cout << "error: failed to read: " << argv[1];
        exit(1);
    }
    if (argc == 2) {
        fout.open(string(string(argv[1]) + string(".obj")).c_str());
    } else {
        fout.open(argv[2]);
    }
    if (fout.fail()) {
        cout << "Failed to open the output file\n";
        exit(1);
    }
    while(!fin.eof()) {
        string line;
        stringstream ss;
        string tmp;

        getline(fin,line);
        ss << line;
        ss >> tmp;
        if (tmp == "Verts=") {
            //read in the vertecies
            ss >> vertcount;  
            for (int i = 0; i < vertcount; i++) {
                vector3 vtx;
                fin >> vtx.x >> vtx.y >> vtx.z;
                //output the verts in the obj format
                fout << "v " << vtx.x << " " << vtx.y << " " << vtx.z << "\n";
            }
            cout << "read " << vertcount << " vertecies" << "\n";
        }
        if (tmp == "Faces=") {
            int vtc = 1;   //vertex counter, set initially to 1 because the obj format starts at 1 for indexing
            ss >> facecount;
            
            for (int i = 0; i < facecount; i++) {
                face f;
                int facesize;   //number of verts per face
                fin >> facesize;
                for (int j = 0; j < facesize; j++) {
                    int v;
                    fin >> v;
                    f.index.push_back(v);
                }
                fin >> tmp;
                for (int j = 0; j < facesize; j++) {
                    //read in the UV coordinates
                    vector2 vt;
                    fin >> vt.x >> vt.y;
                    fout << "vt " << vt.x << " " << 1.0 - vt.y << "\n";
                    
                }
                fout << "f ";
                for (int j = 0; j < (int)f.index.size(); j++) {
                   fout << f.index[j] + 1 << "/" << vtc << " ";
                   vtc ++;
                }
                fout << "\n";
                getline(fin,tmp);
            }
            cout << "read " << facecount << " faces" << "\n";
        }
    }
}
```


I found this here: [http://www.leagueoflegends.com/board/sh ... php?t=6296](http://www.leagueoflegends.com/board/showthread.php?t=6296)

I hope this is of some help.
## Post #90
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-08-31T14:01:56+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I'm back from my well deserved 2 week vacation, sorry to keep you waiting. 
Anyway, to make you guys feel better, I'm still studying the FBX SDK and I already started coding an application so keep watching for progress ^^.
## Post #91
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-08-31T14:17:31+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Where the H did Falo go? He hasn't posted in months.
## Post #92
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-08-31T14:25:12+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

He hasn't been online since the 2nd of July. He's probably busy with real life stuff.
## Post #93
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-08-31T16:13:31+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from ChrisSquareFan
>
> I'm back from my well deserved 2 week vacation, sorry to keep you waiting. 
Anyway, to make you guys feel better, I'm still studying the FBX SDK and I already started coding an application so keep watching for progress ^^.
This is the best news I've heard in a while!  I'm glad to see you back. Perhaps the information revelation posted will be of some use to you. I'm happy to hear of progress and I wish you the best of luck. I'd settle for any method of viewing these models with proper UV maps even if there wasn't an export function. But seen as your going for making them convert to an easily viewable format that's all the better.
## Post #94
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-02T12:23:22+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I'm glad you are happy. 

I've chosen FBX mainly because of the presence of bones. It's far better to export directly with bones then without bones. 
Without bones you only get a "still" mesh, so it's not interesting; plus, the process of skinning the mesh is often tedious.

At the moment I'm integrating KH1 models in my exporter. It's better this way because i have complete info on the file format.
## Post #95
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-09-02T14:45:23+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Ah progress is good!  So with the keeping of the bones is there a chance of keeping animations as well?  

And that's awesome news to hear the adding of KH1 models though they're fairly accessible already via yaz0r's viewer. Just curious but are you adding this support before or after attempting BBS models?
## Post #96
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-09-02T15:45:28+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

fbx seems to be getting more messy and buggy with every release, at least in max, I think you should study collada and the opencollada that exist, I think it is the next fbx thingy
## Post #97
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-09-02T20:15:34+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from pixellegolas
>
> fbx seems to be getting more messy and buggy with every release, at least in max, I think you should study collada and the opencollada that exist, I think it is the next fbx thingy

This is something I must protest against. Collada (DAE) is a terrible format in many ways. There are so many alterations to the same format that importers and exporters for them can't even work with each other. And even if you did get separate importers and such for the many variations not every program exports in the same version so you can end up dealing with many versions of the same format and it gets really messy. I have had programs that exported collada models that even programs like Cinema 4D that natively support it couldn't open it because there were too many alterations in the format.

I do not intend to flame you in any way but I highly disagree that Collada is the way to go. It had a really promising start but as time goes by many will tell you that it just isn't what it was supposed to be. Even higher end programs like 3dsmax 2011 can't import Collada files.

He's already doing FBX and Autodesk has a free converter that can easily convert all the variations of FBX making it accessible to everyone with ease. It is by far the better choice in my opinion.
## Post #98
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-09-02T20:24:01+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Yeah, like I can export a DAE with Blender, and it will import into 3ds max 9, but wont open again in Blender.  

Better off with FBX, since that loads it WITH textures already applied, and bones.
## Post #99
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-02T20:30:05+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

fbx is not buggy, it's just that it was kinda messed up from a version. 
I'll make the exporter so it will support different versions of fbx format.
About that collada thing... sounds like a weird format to me, like.. uncommon. what 3ds max are you using? i always recommend maya
btw, i used to work with 3ds max but now i cant switch back to it since i started maya XD
## Post #100
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-09-02T20:40:16+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I just said, 3ds max 9 xD

I've tried using Maya, I find it incredibly hard to use.
## Post #101
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-09-02T20:52:10+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I use 3dsmax 2011 and Maya 2011. Or rather I have student licenses to both but Maya is just incredibly hard for me to navigate. Thank you so much for sticking with FBX.  I realize this isn't your only thing in life but any idea if you'll have a working demo up for us any time soon?
## Post #102
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-03T06:01:08+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Zerox
>
> I realize this isn't your only thing in life but any idea if you'll have a working demo up for us any time soon?
Yup, but for KH1, no BBS yet. Maya is not so hard to use, just look for video tutorials. When i switched to maya it took me one day to learn all the basic stuff.
Now i feel weird when i use 3D studio max, but i still love it ^^
## Post #103
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-09-03T08:44:17+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

well the only reason I mentioned FBX as buggy is because I use a gameengine called gamecore. FBX works tip top until 3ds max came with the newer versions. Gamecore practically had to create custom fbx importers and change alot because the newer version of fbx was so different.

I really don't mind any format or prefer a certain but would be nice with a file format that does not change so much that completely new routines has to be made.

I use umodel with unreal models and the .psk .psa are tip top, really works well.

But to conclude, fbx is probably great and it was probably a version error as stated by chrissquare
## Post #104
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-05T01:27:04+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Here's first progress:
## Post #105
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2010-09-05T09:41:39+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from pixellegolas
>
> well the only reason I mentioned FBX as buggy is because I use a gameengine called gamecore. FBX works tip top until 3ds max came with the newer versions. Gamecore practically had to create custom fbx importers and change alot because the newer version of fbx was so different.

I really don't mind any format or prefer a certain but would be nice with a file format that does not change so much that completely new routines has to be made.

I use umodel with unreal models and the .psk .psa are tip top, really works well.

But to conclude, fbx is probably great and it was probably a version error as stated by chrissquare

have you tried with dae format? It can contain mesh,bone and UV cordinates, finally this format it was not so changed since the first version, so it has less compatibility problem than the Fbx format. Open collanda is a valid plugin for almost all max versions....bye
## Post #106
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-05T09:56:29+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

the exporter i make supports any version of FBX, so there won't be any problem if that importer worked with only a certain version
of FBX. Simply export to the desired version of FBX and it should work.
## Post #107
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2010-09-05T20:41:03+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Hi there, has somebody else here problems to decrypt the BBS1.dat, BBS2.dat and BBS3.dat from the NA release of Birth by Sleep? Maybe there is a better method available than using the dnas decrypter by hrmifaxi.
## Post #108
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-09-06T14:42:13+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I haven't tried Azurfan but you could always stick to the Japanese iso. The models are the same visually so there's no need to use the NA version.
## Post #109
- Username: TheRPGPlayer
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 27, 2010 7:05 am
- Post datetime: 2010-09-07T00:49:22+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Hello!

(I apologize if this is the most n00bish question ever but...)

Right now I am continuing to try and learn how to create 3D models but I can never find good references and templates that would help me. Then I googled and found this thread. And I'm assuming that what you guys are doing is extracting all the BBS models into a .obj (or any other file type), correct? Well, I do have the UMD copy of BBS with me but I do not have CFW nor' can my PSP be hacked. Is there another way to be able to extract these models?

Thanks!
## Post #110
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-09-07T01:15:25+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Hello TheRPGPlayer, and welcome to the internet. Here at the internet anything and everything are downloadable if you look hard enough. You don't need to rip an iso from your own UMD when you could just google search a download link for it instead.

Based on the rules I'm pretty sure I can't provide a link as to where you can find such things. In fact I'm probably on the fringe of the rules already. I definitely encourage you to obtain it from your own game rather than other more questionable methods.
## Post #111
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2010-09-07T10:50:04+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Zerox
>
> I haven't tried Azurfan but you could always stick to the Japanese iso. The models are the same visually so there's no need to use the NA version.

You're right, but what about the models of the new keyblades and the new secret boss and his weapons. I really wanted to do something with them.
## Post #112
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-09-07T14:57:53+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Seems to me you aren't using Falo's QuickBMS script. It extracts the pmo's and such for you. Give that a try on the NA release and you should be successful.
## Post #113
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2010-09-08T17:24:43+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I'm using it already but because BBS1-BBS3 are encyrpted the script won't find anything.
## Post #114
- Username: Panzah
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Jul 22, 2010 5:11 am
- Post datetime: 2010-09-09T05:49:36+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

What he says is true.
They changed something in the english version, most likely the encryption. None of the tools that worked with Jap BBS work with NA or EUR one.
I wish someone could make a universal extract for all the files, since I was hoping to get my hands on the pmf and at3 files aswell.
If anyone picks this up and makes a proper extractor for the NA version, I'll be very grateful. By the way espio, it's Aurenasek from Qhimm here. Cheers mate.
## Post #115
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-09-10T05:14:33+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Well I'd say it's a minor complication for now considering we already have access in the japan release. We just need to wait patiently for ChrisSquareFan.
## Post #116
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-09-14T01:39:15+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Falo where are you ?
## Post #117
- Username: Venitas1432
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Sep 15, 2010 1:27 am
- Post datetime: 2010-09-14T17:35:26+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

So, Zerox, I don't suppose all these quality problems mean that you wouldn't be able to produce an image where you compare TAV's heights ala this image???: [http://varika.pair.com/mp3/KH%20Models/ ... 20Side.jpg](http://varika.pair.com/mp3/KH%20Models/Org%20Heights%20Side.jpg)

If you can't, I'd understand.
## Post #118
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-09-14T21:22:21+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I'd be fully capable of such an image if what you want is height comparisons. Why you'd ask me specifically I don't know but I am capable of such yes.

I'll see what I can do.

How goes the wonderful FBX conversion project?
## Post #119
- Username: Venitas1432
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Sep 15, 2010 1:27 am
- Post datetime: 2010-09-14T23:38:50+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Zerox
>
> I'd be fully capable of such an image if what you want is height comparisons. Why you'd ask me specifically I don't know but I am capable of such yes.

I'll see what I can do.

How goes the wonderful FBX conversion project?

Thank you, I'd appreciate that. Thanks.
## Post #120
- Username: sprayer
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Sep 10, 2010 2:09 pm
- Post datetime: 2010-09-15T07:49:29+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Venitas1432 dude, you lazy man
## Post #121
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2010-09-15T08:39:20+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

The contents of this post was deleted because of possible forum rules violation.
## Post #122
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2010-09-15T19:16:10+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I am not really interested in this game, but what a quick 3-minute look resulted in is:

```
long Unknown (ArchiveVersion?)
long[3] null
res{
long Offset
long Size
long Unknown (FileID?)
long[5] Name
}
```

Anyone with a bit experience in archives can make a BMS script in no time xD But I don't feel like it at the moment lol sorry ^^

You could even extract it in a simple hex editor by hand, no compression is applied.
## Post #123
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-15T20:51:20+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Sorry to keep you waiting . I'm at the point of extracting textures from KH1 mdls files. 
Until now i managed to export:
geometry, bones, UVs, normals (the normals are still flipped though).

Here's a Jasmine with a stupid texture (sorry, no working textures yet).
File here: [http://filebeam.com/a818eb5b5d03198037488b35120537b6](http://filebeam.com/a818eb5b5d03198037488b35120537b6) 
After i get the textures right you'll have the exporter to play with ^^
## Post #124
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-09-15T20:52:47+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

...Is that a picture of Cloud that she's using? lol
## Post #125
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-15T20:55:59+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

it sure is
## Post #126
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-09-16T04:16:21+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Awesome. =D That's fantastic progress. One large step closer to BBS models. I have the highest faith in you ChrisSquareFan. I'm stoked. =D
## Post #127
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-17T08:21:29+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

i'm happy you are ^^
## Post #128
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-17T20:06:45+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

ok, can anyone share some info on how to read the color (RGBA) stored in tim2 files? 
i tried the "normal" way but a i get a the same imaged tiled 4x4 and no color whatsoever.
maybe i have to read 4 blocks of data to get the color?
## Post #129
- Username: sprayer
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Sep 10, 2010 2:09 pm
- Post datetime: 2010-09-18T11:04:31+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

ChrisSquareFan fbx for what program? because on max 2008,2011 don't work skin

tim2 you can open in xnview-but alpha dont work, or noesis.
or you asking about something else?
## Post #130
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-09-18T14:53:51+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Noesis is the only program that I know of that can read .Tm2 files properly. Why not ask Mr. Adults directly for help on that? He did say all the stuff the program uses to convert things is in the .dll that comes with it. Maybe there is some way to examine that for the information you need?
## Post #131
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-09-19T01:17:16+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

That is awesome ChrisSquareFan
I think you should ask MrAdults about tm2 file
## Post #132
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-09-19T04:33:21+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from ChrisSquareFan
>
> ok, can anyone share some info on how to read the color (RGBA) stored in tim2 files? 
i tried the "normal" way but a i get a the same imaged tiled 4x4 and no color whatsoever.
maybe i have to read 4 blocks of data to get the color?
can you post some file sample i think i could help you on it, just fixed my own function to load then in opengl ^^
## Post #133
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-09-19T09:31:16+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

A quick google shows this which I'm pretty sure is everything you need to know regarding tm2:
[http://dutils.googlecode.com/svn-histor ... mage_tm2.d](http://dutils.googlecode.com/svn-history/r14/trunk/simple_image/simple_image_tm2.d)
See [http://dutils.googlecode.com/svn-histor ... ple_image/](http://dutils.googlecode.com/svn-history/r14/trunk/simple_image/) for referenced functions.
## Post #134
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-19T10:17:29+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Thanks!
## Post #135
- Username: ssjkeigo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Sep 20, 2010 4:44 pm
- Post datetime: 2010-09-20T09:13:03+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Falo
>
> ultimaespio wrote:Oh, that model is the Fairy Godmother 

Going by the textures that is lol.

If its needed, i can forward you towards the Crisis Core format, but i think its really out of date now.

Falo, what did you use to extract the PMO and TIM2 files?

any Hex Editor should work.
here 2 quickbms scripts,

extract_pmo.txt should extract 858 PMO's,
extract_tm2_from_pmo.txt extracts all tm2 files from any PMO.

the biggest PMO is #424 (Terra-Xehanort)

the script is not complete, it uses ((BONOffset - Offset) + 32 + (BoneCount * 160)) to calculate Size, this will not work for pmo's without bones
until i know how to read the mesh it's the only solution.

is there a function that uses the txt's you provided? im clueless. you said any hex editor right? im on HxD and totally clueless.
## Post #136
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-20T14:17:50+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

little update, to keep you hyped; yeah, thats too much yellow XD
also i discovered that i can export to 3ds, collada (dunno what's that), obj format and earlier versions of fbx.



untitled.PNG (125.71 KiB) Viewed 144 times
## Post #137
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-09-21T00:40:54+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Chrissquarefan i think the yellow problem is in .tm2 file
Like when im extracting bleach heat the soul 7 model,the texture (tm2) is kinda yellowish
So the yellow problem must be tm2 file problem if im not mistaken,i will ask Mr.Adults about this yellow problem
## Post #138
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-21T13:53:26+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

it's not always yellow. some models are red.
## Post #139
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-09-21T15:30:57+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Wait so is Alice and such still Kindgom Hearts 1? I wasn't aware that they used .tm2 files for textures.
## Post #140
- Username: ssjkeigo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Sep 20, 2010 4:44 pm
- Post datetime: 2010-09-21T15:32:08+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

So I finally decrypted the jp BBS#'s and was raring to go when I saw 8000+ textures. Then it hit me. Wait a sec, there's no way to encrypt everything back to the .dat's is there? That totally sucks for guys like me who want to modify textures.
## Post #141
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-09-22T00:08:40+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Oh sometime the texture turn red too,thanks for the info chrissquarefan
## Post #142
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-22T11:04:06+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

fixed the color issue. now i have what seems to be interlace issues. 
i'll use what mr adults sent



untitled.PNG (121.54 KiB) Viewed 93 times
## Post #143
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-09-22T11:45:59+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Awesome work chrissquarefan 
Woo hoo its gonna be great
## Post #144
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-22T12:48:12+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

i used the swapping trick but i still get errors on the image.. what am i missing?



texture5.png (10.54 KiB) Viewed 89 times
## Post #145
- Username: SirLoon
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 19, 2009 12:26 am
- Post datetime: 2010-09-22T14:58:23+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from ChrisSquareFan
>
> i used the swapping trick but i still get errors on the image.. what am i missing?
texture5.png
hmm can they use some bits in sprite block for reflection? bcause if i remmember correctly those gray places were brighter ingame
## Post #146
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-22T15:06:51+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

i don't know.. i think i used all the data provided. the tim2 doesn't have a header, so it's hard to guess
if there is any compression or extra data..
## Post #147
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-09-22T15:11:49+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Drop MrAdults a pm, he'll probably know. Do you want/would the texture ripped from model viewer wx to help you at all?
## Post #148
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-22T15:43:16+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

don't know if that will help. i'll ask mr adults
## Post #149
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-23T11:12:07+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from ultimaespio
>
> Drop MrAdults a pm, he'll probably know. Do you want/would the texture ripped from model viewer wx to help you at all?
yeah, i think so
## Post #150
- Username: yaz0r
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Sep 23, 2010 4:32 pm
- Post datetime: 2010-09-23T11:32:25+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

The palette issue is probably the same as what I had on KH1/2 on PS2. The palette is not linear and must be reordered for it to work properly.
## Post #151
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-09-23T11:42:03+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Here it is anyway:
## Post #152
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-23T11:56:06+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from yaz0r
>
> The palette issue is probably the same as what I had on KH1/2 on PS2. The palette is not linear and must be reordered for it to work properly.
Hello yaz0r, it's nice to see you again ^^
Yeah, i thought of that, but reordered by what criteria? I reordered the palette by swapping colors at every 4 blocks of 8 colors. 
It looks like the glitches occur at only certain places in the texture.
## Post #153
- Username: yaz0r
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Sep 23, 2010 4:32 pm
- Post datetime: 2010-09-23T12:01:58+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Check your pm, I sent you the code I use to reorder KH1/2 palettes
## Post #154
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-23T15:13:44+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Finally done! 
There are still some issues with missing geometry on some models.



hurray.PNG (133.57 KiB) Viewed 93 times
## Post #155
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-09-23T19:57:13+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Wow yaz0r's back. There's something I thought I'd never see. Either way I'm so glad he was able to help you fix the color issues.

Yuffie looks just fine to me. What happens to be missing?
## Post #156
- Username: yaz0r
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Sep 23, 2010 4:32 pm
- Post datetime: 2010-09-23T20:42:25+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I was never really gone. I continued to tinker with a bunch of model formats, but never really posted anything.
## Post #157
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-09-23T21:07:40+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Ah I see. So based on the fact that your here in this thread does that mean you have interest in helping us figure out the BBS model format so we can view them?
## Post #158
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-23T21:52:57+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Zerox
>
> Wow yaz0r's back. There's something I thought I'd never see. Either way I'm so glad he was able to help you fix the color issues.

Yuffie looks just fine to me. What happens to be missing?

Not on yuffie, other models. For example, Leon's belt is missing some faces. That's because there are some 'special'
faces on the models whose corresponding bones are harder to read. I'll look more into it.
[http://filebeam.com/c5d2f2e9ec82a6b574274bc7756c9f88](http://filebeam.com/c5d2f2e9ec82a6b574274bc7756c9f88)
Enjoy. You need to put the mdls in the same folder with the app and rename it "Sora.mdls"
You need .NET framework
## Post #159
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-09-23T22:14:07+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Awesome an alpha trial. You need .NET Framework 4.0 to be exact.

On an side note I was able to convert and view Young Master Xehanort. Kind of exciting since you can only see him from behind in BBS.
## Post #160
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-23T22:17:41+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Awesome! I can see they didn't work too much on the face proportions (the mouth looks a bit too small), but he still looks kinda handsome  
From what i red, the next KH games will center around Xehanort btw
## Post #161
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-09-24T08:19:45+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

This is aweeeeeesome ChrisSquareFan
## Post #162
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-09-24T11:04:24+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

"Can't locate msvcp100d.dll"

I have .NET Framework 4.0, what else do I need?
## Post #163
- Username: sprayer
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Sep 10, 2010 2:09 pm
- Post datetime: 2010-09-24T11:25:46+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from ultimaespio
>
> "Can't locate msvcp100d.dll"

I have .NET Framework 4.0, what else do I need?
you need put in same folder
msvcp100d.dll
msvcr100d.dll
just google it and download
## Post #164
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-24T11:36:24+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Well, i think you may need VC++ redist 2010
[http://www.microsoft.com/downloads/en/d ... bf0912db84](http://www.microsoft.com/downloads/en/details.aspx?FamilyID=a7b7a05e-6de6-4d3a-a423-37bf0912db84)
## Post #165
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-24T11:50:47+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

i wanna make a cool interface. if you have ideas post some drawings ^^
## Post #166
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-09-24T11:53:58+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

It's ok, I got it to work with the 2 dll's that sprayer posted.

I may have an out of date fbx importer for 3ds max 9, none of the bones have names, they are just blank.

Oh, and how did Zerox manage to get Xehanort?

I'll try and think of an interface
## Post #167
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-24T12:00:08+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

sorry, there are lots of bugs, i'll try to fix them when i have the time.
## Post #168
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-09-24T12:07:40+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Oh, right. I thought it was my Import Script  

No worries.
## Post #169
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-24T14:17:12+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

You can try fbx converter to convert to 3ds format
[http://usa.autodesk.com/adsk/servlet/pc ... d=10775855](http://usa.autodesk.com/adsk/servlet/pc/item?siteID=123112&id=10775855)
## Post #170
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2010-09-25T06:08:33+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Azurfan
>
> Hi there, has somebody else here problems to decrypt the BBS1.dat, BBS2.dat and BBS3.dat from the NA release of Birth by Sleep? Maybe there is a better method available than using the dnas decrypter by hrmifaxi.

> Reply from Panzah
>
> What he says is true.
They changed something in the english version, most likely the encryption. None of the tools that worked with Jap BBS work with NA or EUR one.

BBS1 - 3.dat uses the PGD encryption, you need the decrypt keys to decrypt them, 
you can get these keys with JPCSP or from an decrypted EBOOT.BIN and then modify 
dnas decrypter to work with NA/EU, (this works also with hbl if you don't have a CFW PSP).

I can send you a modified that works with EU, but i don't have the keys for NA.

> Reply from Panzah
>
> I wish someone could make a universal extract for all the files, since I was hoping to get my hands on the pmf and at3 files aswell.
If anyone picks this up and makes a proper extractor for the NA version, I'll be very grateful. By the way espio, it's Aurenasek from Qhimm here. Cheers mate.
PMF, just use a Hex Editor to get them, AT3 the same it isn't hard to do, the game does not compress any files, you just have to copy&paste them.
Like KH1 and KH2, BBS uses a FileHash System, it's easy to find names, but hard to reverse the algo if you don't understand PSP MIPS.

I wasn't away, but i had other stuff to do.
For my Exporter, thanks for the pmo.bt i fixed many things with it, but i'm no 3D expert, i still can't find the normals to make a proper model.

[http://www.imagebanana.com/view/4xfkqsed/TVA.jpg](http://www.imagebanana.com/view/4xfkqsed/TVA.jpg)
[http://www.imagebanana.com/view/6f72kk1v/Aqua.jpg](http://www.imagebanana.com/view/6f72kk1v/Aqua.jpg)
## Post #171
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-09-25T06:11:59+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Falo, do you have another version of the converter?
## Post #172
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-09-25T09:45:45+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Holy moley,that is really near a perfect model wow
Awesome work falo
## Post #173
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-09-26T00:05:02+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Normals or not it looks like you've fixed a great deal with this version. I'd love it if you posted a new version of your pmo converter or if you could assist ChrisSquareFan in making his FBX exporter. Then again if you did both that'd be great too.
## Post #174
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2010-09-26T08:27:53+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

hmm guys ive just got this one problem and if someone can help me will you please ^^ Since as you can see Vanitas textures seems like his helmet has cracked and are messed up and i also used the flip UVs in Noesis when changing it to.png format ^^" so can anyone help me please on how can i fix this messed up textures.
## Post #175
- Username: SirLoon
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 19, 2009 12:26 am
- Post datetime: 2010-09-26T10:08:08+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Aurangzeb56
>
> hmm guys ive just got this one problem and if someone can help me will you please ^^ Since as you can see Vanitas textures seems like his helmet has cracked and are messed up and i also used the flip UVs in Noesis when changing it to.png format ^^" so can anyone help me please on how can i fix this messed up textures.
i dont see it clearly but it looks like if you look inside helmet. Try flip normals
## Post #176
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2010-09-26T10:11:25+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from SirLoon
>
> Aurangzeb56 wrote:hmm guys ive just got this one problem and if someone can help me will you please ^^ Since as you can see Vanitas textures seems like his helmet has cracked and are messed up and i also used the flip UVs in Noesis when changing it to.png format ^^" so can anyone help me please on how can i fix this messed up textures.


i dont see it clearly but it looks like if you look inside helmet. Try flip normals

in Noesis or 3DS Max?? ^^"
## Post #177
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-09-27T00:35:41+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

If you don't know which program he's referencing try it in both.
## Post #178
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2010-09-27T03:33:23+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Zerox
>
> If you don't know which program he's referencing try it in both.

hmmm well i never could find the flip normlas option in 3Ds Max,so i would appreciate it if someone could tell me where it is ^^

Although i found something else that makes the model a but clearer (some models like not the hooded xehanort models,hell ruin if you try that on him ) well i just select the whole model,right click ->object properties -> and tick vertex channel display and ok then the model becomes like this 



ALTHOUGH im still having some problems like as you can see with their faces ^^"





SO can anyone tell me how to fix that?? ^^"
## Post #179
- Username: sprayer
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Sep 10, 2010 2:09 pm
- Post datetime: 2010-09-27T08:13:20+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Aurangzeb56 

[](http://funkyimg.com/viewer.php?img=/2/928/461/1.jpg)
[](http://funkyimg.com/viewer.php?img=/2/858/295/2.jpg)

actually you need to do more thing like attach all object in one, weld vertex this threshold, but its another story =)
i dont understand why you do this without bones
## Post #180
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-27T09:11:58+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Aurangzeb56
>
> Zerox wrote:If you don't know which program he's referencing try it in both.

hmmm well i never could find the flip normlas option in 3Ds Max,so i would appreciate it if someone could tell me where it is ^^

there's a modifier in 3ds max that support flipping normals
[http://www.recipester.org/Recipe:Flip_n ... x_35682020](http://www.recipester.org/Recipe:Flip_normals_in_3ds_MAx_35682020)
## Post #181
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-09-27T09:36:17+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from yaz0r
>
> I was never really gone. I continued to tinker with a bunch of model formats, but never really posted anything.

Did you see this? 

[viewtopic.php?f=29&t=4909](http://forum.xentax.com/viewtopic.php?f=29&t=4909)
## Post #182
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2010-09-27T10:47:15+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from sprayer
>
> Aurangzeb56 




actually you need to do more thing like attach all object in one, weld vertex this threshold, but its another story =)
i dont understand why you do this without bones

oh thanks sprayer ill see what i can do ^^ and well since i dont think theres anyway to extract bones so i just do this for fun  and even if this DOES extract bones to,i don't know how to apply bones ^^"
## Post #183
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2010-09-28T09:27:09+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Falo
>
> Azurfan wrote:Hi there, has somebody else here problems to decrypt the BBS1.dat, BBS2.dat and BBS3.dat from the NA release of Birth by Sleep? Maybe there is a better method available than using the dnas decrypter by hrmifaxi.
Panzah wrote:What he says is true.
They changed something in the english version, most likely the encryption. None of the tools that worked with Jap BBS work with NA or EUR one.

BBS1 - 3.dat uses the PGD encryption, you need the decrypt keys to decrypt them, 
you can get these keys with JPCSP or from an decrypted EBOOT.BIN and then modify 
dnas decrypter to work with NA/EU, (this works also with hbl if you don't have a CFW PSP).

I can send you a modified that works with EU, but i don't have the keys for NA.

That would be great, I own the EU version myself so that shouldn't be a problem. Although if you could upload the decrypted files altogether that would be the best.
## Post #184
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-28T15:42:03+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

the exporter is very close to a final. i only need to release a test version to see if i missed some models.
after this it's BBS time 
many thanks go to yaz0r   



riku.jpg (63.58 KiB) Viewed 197 times
## Post #185
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2010-09-28T18:41:11+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from ChrisSquareFan
>
> the exporter is very close to a final. i only need to release a test version to see if i missed some models.
after this it's BBS time 
many thanks go to yaz0r   
riku.jpg

nice work ^^ so thats 3DS Max right?? XD
## Post #186
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-29T06:52:12+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

it's maya
## Post #187
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2010-09-29T07:13:36+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

a kh1 model exporter  when the test release?
## Post #188
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-09-29T23:57:25+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Wow that is aweeeeeesome chrissquarefan
And you deserve a cookie
## Post #189
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-30T08:37:54+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Devilot
>
> a kh1 model exporter  when the test release?
probably today, i'll make a very quick user interface.
just so you know, the requirments are:
.NET framework 4, VC++ 2010 redist:
[http://www.microsoft.com/downloads/en/d ... bf0912db84](http://www.microsoft.com/downloads/en/details.aspx?FamilyID=a7b7a05e-6de6-4d3a-a423-37bf0912db84)

sorry if this is a bother, only windows 7 users might not need to install .net framework
## Post #190
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2010-09-30T09:16:09+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I dunno. I believe I can install it quite easily, as the others can.
## Post #191
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-30T20:46:17+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

The test version:
[http://filebeam.com/6df0f73f4ba448b49280f7e54f0f220e](http://filebeam.com/6df0f73f4ba448b49280f7e54f0f220e)
Launch UI.exe. Only fbx works now, do not use paths with spaces.
Also, you must turn backface culling on in your 3d software.
Enjoy!
## Post #192
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-09-30T21:45:05+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Works great, doesnt work with highpoly models though. But you prob already know that
## Post #193
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-09-30T22:02:48+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from ultimaespio
>
> Works great, doesnt work with highpoly models though. But you prob already know that
yeah, i'm working on that...
## Post #194
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2010-10-01T04:36:02+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from ChrisSquareFan
>
> ultimaespio wrote:Works great, doesnt work with highpoly models though. But you prob already know that 
yeah, i'm working on that...

hmm when i click the export button it gives me this error
## Post #195
- Username: enrique3
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 23, 2010 5:03 pm
- Post datetime: 2010-10-01T09:20:07+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Hi!

A cordial greeting to all! My name is Enrique, and I've followed this theme scrupulously.
Thank you very much in advance, whom they share their tools or applications, in order to achieve these great models!
I've achieved some models, using Falo's instructions.

I hope that you excuse my ignorance, but I became confused with ChrisSquareFan's new exporter, I see that it can work very well, but my question is the next:
Works this exporter for this game? ( KHBBS ).
Can you help me? In advance many thanks!
I want to know how do I export the PMO to MDL?

Thanks and greetings!
## Post #196
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2010-10-01T10:12:52+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

The contents of this post was deleted because of possible forum rules violation.
## Post #197
- Username: dzre
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Sep 26, 2010 3:02 am
- Post datetime: 2010-10-01T12:48:22+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Could anyone export the texture from the map where there's only the round platform with Ventus on it and the one where it's half ventus half vanitas?
If someone can do it, thanks in advance! I would do it myself since I have the game and a PSP, but the PSP is kind of borrowed so I can't really put a CFW on it.
Unless there's some other way I can dump the UMD and decrypt the .DAT files? I guess no one is willing to upload the whole .DAT files either.
EDIT: Ah, I guess you can dump the UMD without CFW but that doesn't help much.
## Post #198
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-10-01T12:49:45+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

@Falo
Maybe, have you tried adding materials on it? It might just be the object colour.

Does anyone know how to get rid of that box around the model when you import it?
## Post #199
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-10-01T16:33:57+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Falo
>
> 
@ChrisSquareFan
Is this normal ?
http://www.imagebanana.com/view/cfry83o1/export.jpg
nope, looks like it doesn't work well with 3d studio max 
i have to ensure that it works at least with maya and max
## Post #200
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-10-01T18:09:41+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from ChrisSquareFan
>
> Falo wrote:
@ChrisSquareFan
Is this normal ?
http://www.imagebanana.com/view/cfry83o1/export.jpg
nope, looks like it doesn't work well with 3d studio max 
i have to ensure that it works at least with maya and max
i figured it out, it's about the bind pose. when i import the file into 3ds max the max assumes the binding pose in a wrong way. maya seems to do this in a different way. thanks for the feedback
## Post #201
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-10-01T18:11:41+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from ChrisSquareFan
>
> ChrisSquareFan wrote:Falo wrote:
@ChrisSquareFan
Is this normal ?
http://www.imagebanana.com/view/cfry83o1/export.jpg
nope, looks like it doesn't work well with 3d studio max 
i have to ensure that it works at least with maya and max
i figured it out, it's about the bind pose. when i import the file into 3ds max the max assumes the binding pose in a wrong way. maya seems to do this in a different way. thanks for the feedback

Oh, I never noticed that problem. I thought he was talking about the green and black thing, ignore me then
## Post #202
- Username: Soraoscuro
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Oct 01, 2010 2:31 am
- Post datetime: 2010-10-01T23:20:59+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

The contents of this post was deleted because of possible forum rules violation.
## Post #203
- Username: dzre
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Sep 26, 2010 3:02 am
- Post datetime: 2010-10-02T10:58:19+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Soraoscuro
>
> Could you please post the source code for the decrypter? I'm interested in knowing how it works.

I'm not an expert on these things but I think the decrypter uses PSP's built-in encryption functions so you can't really know what it's doing. Otherwise you wouldn't need the PSP for it at all.
I.e. there's probably nothing interesting in the source code of the plugin or whatever is used to decrypt.
## Post #204
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2010-10-02T18:10:47+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

The contents of this post was deleted because of possible forum rules violation.
## Post #205
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-10-03T10:21:22+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

What was the missing dll? I only got a warning message in 3ds max and a distorted mesh. The textures are not showing at all.
## Post #206
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2010-10-03T11:19:36+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from ChrisSquareFan
>
> What was the missing dll? I only got a warning message in 3ds max and a distorted mesh. The textures are not showing at all.

well the missing dll error is on page 13 (the last post) and well my model is perfectly fine,just the whole model is like one joint so putting texture in any thing will give the texture to the whole model
## Post #207
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-10-03T13:50:43+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Have anyone tried extracting cloud and sephiroth kh1 with chrissquarefan fbx exporter ??
## Post #208
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2010-10-03T16:08:13+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Still have a number of small errors in both KH1 and KH:BBS, but i am making progress.  Hopefully i can fix the remaining issues.

[](http://img709.imageshack.us/i/xigbarkhbbs.jpg/)[](http://img820.imageshack.us/i/xehanortkhbbs.jpg/)[](http://img831.imageshack.us/i/215f02cd0000khbbs.jpg/)[](http://img811.imageshack.us/i/253dp01kb02khbbs.jpg/)[](http://img713.imageshack.us/i/297f07rg0001khbbs.jpg/)
[](http://img716.imageshack.us/i/372kg5002lpkhbbs.jpg/)[](http://img706.imageshack.us/i/425b10ex00hkhbbs.jpg/)[](http://img832.imageshack.us/i/sephirothkh.jpg/)[](http://img716.imageshack.us/i/cloudkh.jpg/)[](http://img836.imageshack.us/i/boatkh.jpg/)
## Post #209
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-10-03T16:10:08+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Oh, wow! Looks good. So what are the remaining issues?

@Valvoga, yes.
## Post #210
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2010-10-03T16:11:34+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from revelation
>
> Still have a number of small errors in both KH1 and KH:BBS, but i am making progress.  Hopefully i can fix the remaining issues.

woa your BBS models are so straight and no errors in UV either
## Post #211
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-10-03T16:18:33+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I may be pushing it a bit, but...is there any chance of getting KH1 maps? They look really interesting, I'd like to have a play around with them.
## Post #212
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2010-10-03T16:26:33+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Well in KH there are some errors with vertices that have multiple weighted position values.  These are usually found in models with high-poly faces.

With BBS in most of those models the faces are actually still flipped, which should hopefully be easier to remedy.  There are also issues where the offsetting of the vertex data based on the flags as i had listed earlier in the thread; seem to be off with some models.  Still need to check my code to ensure i have implemented it all correctly.  Some models do have uv issues, but i think that may be due to the incorrect offsets causing errors in the data retrieval and flipped faces.

Will have to see how it goes.

Edit:
Ok, fixed the flipped faces, heh.  Forgot to check a flag, silly me.
Still think the offset issue is there, but i will be testing more and see what i can make of it.
## Post #213
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-10-03T23:02:58+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

wow that is aweeeeeeeeeeesome revelation
## Post #214
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-10-03T23:51:51+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

So revelation your working on your own converter for both then huh?

It seems to me it'd be beneficial to all of you working on converters if you coordinated your findings. Though this is not my place to say. I think it's awesome you found the flipped face issue. That's been one of the biggest issues so we've had without any idea on how to fix it.

Although I think I see what you mean about your converter not being 100% error free yet. Looks like Braig's eyes are disfigured.



Like as if one eye was going up and the other was going down.

But it seems your well on your way.
## Post #215
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2010-10-04T00:37:32+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Yes, the textures were off for some textures that were not power of 2.  The GsTex0 structure in the TIM2 data has the intended texture size.  Use that for the actual texture size allocation, and just skip the pad bytes when filling if the image size differs.  Seems to work great now.

As far as coordinating my efforts, i already have.  The information in the template i posted earlier in the thread has all the information i have used to get to this point.  There have been a few corrections, and i will update those shortly.  Anything else, feel free to ask.

[](http://img59.imageshack.us/i/xigbar2khbbs.jpg/)

Now i just need to look into a more reliable way to properly extract the *.dat files.
## Post #216
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-10-04T03:22:54+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I must say that looks significantly better well done. So quickBMS isn't enough for getting at the .dat files for you huh?
## Post #217
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-10-04T09:01:58+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Braig look awesome,awesome work revelation
## Post #218
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-10-05T16:08:18+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

To fix flip face issue you must check a flag, and generate faces using indexes by alternating order, like this:

```
		for(...) //generate faces
		{
			mesh->BeginPolygon();
			if(flip)
			{
				mesh->AddPolygon(j);
				mesh->AddPolygon(j + 1);
				mesh->AddPolygon(j + 2);
			}
			else
			{
				mesh->AddPolygon(j + 2);
				mesh->AddPolygon(j + 1);
				mesh->AddPolygon(j);
			}

			flip = !flip;//the trick is here!
			mesh->EndPolygon();
		}
```
## Post #219
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-10-06T03:00:34+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

When will a more accurate exporter be released?
## Post #220
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-10-06T10:58:04+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

when I'll have time..
## Post #221
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-10-06T11:15:13+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Mirrorman95
>
> When will a more accurate exporter be released?

It'll be done when its done. Just be patient and wait. People have lives you know, and don't sit around making model exporters all day.
## Post #222
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-10-06T14:11:50+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

But what about Falo? Doesn't he know anything more about the model-unpacking process than he did two months ago when he released the current version? Couldn't he make the files opensource so other people could work on it?
## Post #223
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-10-06T22:29:32+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

High Poly update. It seems I'm missing some data...



Capture.PNG (52.88 KiB) Viewed 56 times
## Post #224
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2010-10-06T23:22:05+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

That's about what i am getting in KH, and is the only error i have left at the moment.

[](http://img546.imageshack.us/i/error2kh.jpg/)

Something to do with the way the transform needs to be handled for indices in the matrix table that are >= 0x100, i think.  Still looking into it.
## Post #225
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-10-07T07:35:45+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from revelation
>
> That's about what i am getting in KH, and is the only error i have left at the moment.



Something to do with the way the transform needs to be handled for indices in the matrix table that are >= 0x100, i think.  Still looking into it.

At first i thought the weights were the problem, but it looks like some vertexes are bound to incorrect joints because of erroneous reading.
## Post #226
- Username: dzre
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Sep 26, 2010 3:02 am
- Post datetime: 2010-10-07T17:07:35+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

[http://cl.ly/6888ce70e720e44622e7](http://cl.ly/6888ce70e720e44622e7)
Here are the maps I meant. I would just need the tm2 textures from them I don't even need the working 3D model. Anyone got them extracted?
## Post #227
- Username: yaz0r
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Sep 23, 2010 4:32 pm
- Post datetime: 2010-10-09T08:55:02+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I never really advertised it, but I have support for KH2 animations and maps btw.
## Post #228
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-10-09T17:16:04+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

And would knowledge on how to get to them or a tool be something you were willing to share yaz0r? Otherwise I don't see why you'd mention it.

Anyway I was curious if anyone had been playing around with the American or European versions of the game and found and got the Mysterious Figure working yet?

I'm curious to see if his model has any kind of face texture at all.
## Post #229
- Username: yaz0r
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Sep 23, 2010 4:32 pm
- Post datetime: 2010-10-09T19:54:43+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I'm thinking of releasing something KH2 related yeah. It's still a bit work in progress atm.
## Post #230
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-10-09T21:25:34+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Work in progress or not a way to view KH2 maps or maps from any of the KH games would be amazing. I've done cool things with Falo's work in progress converter: 


or Vanitas Unmasked

But I'll be honest I'd be capable of neater looking things than blank renders if I had access to levels even in just a viewer so I could put my renders on top of viewer screenshots.
## Post #231
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-10-09T21:29:40+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

^ You know that's like a massive spoiler right? 

Yeah, I like to make artwork with the models I extract. Maps are quite handy, because it gives the image more life than just a dull background. Animations are quite helpful too, for when I want to base a pose on a certain animation.
## Post #232
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-10-09T21:38:37+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Meh I figured anyone who comes to this thread will already know about Vanitas' identity. Especially when you consider Falo's avatar. But I swapped it to Vanitas Remnant instead as that's a little less spoiler heavy.
## Post #233
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-10-09T21:43:55+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Just in case anyone hadn't finished it yet, that's all 

Anyway, I think we should keep a list of the models we find. Since they are numbered like 1.pmo 2.pmo and so on...I think it would be helpful for people to find the models they want.
## Post #234
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-10-09T23:21:11+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

How did you get the bone structure file to work right?
## Post #235
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2010-10-10T00:10:46+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

The contents of this post was deleted because of possible forum rules violation.
## Post #236
- Username: Dimitree
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Sep 23, 2010 3:16 am
- Post datetime: 2010-10-13T00:43:38+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

does anyone could tell me which kind of file contains the room7maps models on KH1? it's likely not a mdls like the characters. anyone managed to rip them?
btw a really great work, I really enjoyed young xehanort and the Disney town model! amazing
## Post #237
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-10-13T00:49:11+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Exactly what I mean. Though so far I've only been able to get untextured levels from any of the games I've tried.
## Post #238
- Username: yaz0r
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Sep 23, 2010 4:32 pm
- Post datetime: 2010-10-13T13:09:41+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Afaik, KH1 stores maps in .ard files.
## Post #239
- Username: Dimitree
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Sep 23, 2010 3:16 am
- Post datetime: 2010-10-13T14:39:01+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from yaz0r
>
> Afaik, KH1 stores maps in .ard files.

yes sure, like every other object in the game, everything is stored in .ard files (you get MDLS, MSET, EVM, WMN, etc, from an ARD), but the point is, which kind of file inside this ard archive is the one for the maps? and how to view them?
a million dollar question
## Post #240
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2010-10-16T18:41:14+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

think it's possible to get only the models/textures of the weapons?
## Post #241
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-10-16T18:42:03+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I'm actually lost now, what are we talking about?
## Post #242
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2010-10-16T19:30:37+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

as per topic, birth by sleep models!
## Post #243
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-10-17T03:11:45+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Well to attempt at getting back on-topic, ChrisSquareFan have you made any progress with Birth By Sleep models at all as you seem to be the only one who may be interested in the release of a public converter? It has been a week since you last posted here and even just something on any attempts at the KH1 models would be good to me, just any sort of update would be nice.
## Post #244
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-10-17T03:55:29+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Yeah, the KH1 model formats should have their own topic. Meanwhile, I've got messed up faces on my models and I can't get any from the English version because there hasn't been an update for the converter in months! I mean seriously, I mean I know Falo has a life, and he's done so much for us, but hasn't he got something new? I just don't understand. Unless I being rude for saying this; I mean no offense and don't expect this to come off as such. But unless there's a new program for extracting Buzz and Woody from KH2, I don't think anyone gives a darn about it on this topic.
## Post #245
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-10-17T04:15:45+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

For what it's worth Falo did release a new dumper for KH 1 and 2 to dump more models and if you know how to use it properly you can indeed get to Buzz and Woody I have them on my hard drive and such. Though I would like to point out they have no textures and there is no UV maps on them either for any non-existent texture.

But the reason he didn't mention it here is probably because it's not about Birth By Sleep. Though he did show new screen shots of more successfully converted models he didn't release anything and I'm not sure he intends to ever release anything further. Though admittedly if he doesn't intend to release anything some sort of notification that he doesn't intend to would be courteous.
## Post #246
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-10-17T04:17:01+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

you should not post mean things in a topic because your are tired of waiting if you want it so bad reverse the format yourself.
I could help with he format if the program was open source but it is not and  i am not going to re invent the wheel here so just wait till he is ready then he will share his work.
## Post #247
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2010-10-17T04:49:46+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Quite frankly, unless you are able to take the information in this thread, which already outlines the entire PMO format for the most part (enough to produce the images i posted), you can't really make requests of what someone else does with their spare time.

Admittedly, i usually have no use for model converters, so it has always been low on my priority list, but i do plan on looking into a number of the other formats i am interested in, and if i get around to figuring out and posting the information before those that are actually working on conversion, more power to them to integrate it into their work if/when they get the chance.

i haven't added skeletal animation support to my code yet, and have a number of other areas to cleanup and otherwise fix before things are at a point i am comfortable with.  That, combined with the fact i work on a number of different formats besides these, mean i am usually jumping back and forth between format investigation and RL duties.

The more format investigation and information provided the better.  Means less work for me if others also provide their knowledge on what they have already figured out.  A good number of formats i have queued up are ones where there are tools for viewing/conversion, but no actual information on the underlying formats, which are far more useful to me.

Outside of that, i'll be looking to see what i can make of the stage data when i can, and i plan on continuing with both KH1 and KH2 in the future (look up my first post in the forums and you may get a hint on some of the other formats i plan on completing at some point, if i haven't already, heh).
## Post #248
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2010-10-17T06:36:53+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Zerox
>
> Though he did show new screen shots of more successfully converted models he didn't release anything and I'm not sure he intends to ever release anything further. Though admittedly if he doesn't intend to release anything some sort of notification that he doesn't intend to would be courteous.

I have other stuff to do, i'm a student and i currently work on the .hack games & KH Re:Coded

The reason i didn't released a new version is, it's not finished, but you shouldn't wait for a new release from me,
i say it again, i don't have any 3D knowledge, i just know how to analyse files/convert values etc. 
i started to work on this converter just for fun, my goal was to view the models, which is possible now.

here the current state:

with normals: [http://www.imagebanana.com/view/sza9a0h ... ormals.png](http://www.imagebanana.com/view/sza9a0h1/withNormals.png)
without normals: [http://www.imagebanana.com/view/4r2h0nvt/noNormals.png](http://www.imagebanana.com/view/4r2h0nvt/noNormals.png)

It's somehow a little flipped faces bug and uv bug if you look at Terra's face.
## Post #249
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2010-10-17T09:50:23+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

any idea on how that could be fixed?
## Post #250
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-10-17T15:36:39+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

KH1 here now:

[viewtopic.php?f=16&t=5221](http://forum.xentax.com/viewtopic.php?f=16&t=5221)

Please try to keep this thread about BBS, and the new one about KH1.
## Post #251
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-10-18T03:38:54+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from chrrox
>
> you should not post mean things in a topic because your are tired of waiting if you want it so bad reverse the format yourself.
I could help with he format if the program was open source but it is not and  i am not going to re invent the wheel here so just wait till he is ready then he will share his work.

I didn't mean to offend anyone; I just wanted there to be less discussion of KH1 on the topic.
## Post #252
- Username: yaz0r
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Sep 23, 2010 4:32 pm
- Post datetime: 2010-10-18T03:53:06+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Regarding the normals issue, are those the normals from the model data, or regenerated? Afaik, the game doesn't need normals to display the models, because there is no real lighting in KH games (except in the case of tron model of KH2 that do use normals I think).
So, in case they come from the model data, there is no real guarantee that they are correct to begin with.
## Post #253
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2010-10-18T03:57:41+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from yaz0r
>
> Regarding the normals issue, are those the normals from the model data, or regenerated? Afaik, the game doesn't need normals to display the models, because there is no real lighting in KH games (except in the case of tron model of KH2 that do use normals I think).

I know nothing about how 3D works, they are generated, i just set them all to "vn 1.0 1.0 1.0" and it worked...
## Post #254
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2010-10-18T04:07:28+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Ah, well, i can confirm that so far, none of the 858 pmo files i have extracted have contained normals.
## Post #255
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2010-10-19T15:23:27+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Zerox
>
> Well to attempt at getting back on-topic, ChrisSquareFan have you made any progress with Birth By Sleep models at all as you seem to be the only one who may be interested in the release of a public converter? It has been a week since you last posted here and even just something on any attempts at the KH1 models would be good to me, just any sort of update would be nice.

nothing about bbs, sorry, just kh1. at the moment i'm rewriting a component
## Post #256
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-10-21T05:34:53+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Mirrorman95
>
> Yeah, the KH1 model formats should have their own topic. Meanwhile, I've got messed up faces on my models and I can't get any from the English version because there hasn't been an update for the converter in months! I mean seriously, I mean I know Falo has a life, and he's done so much for us, but hasn't he got something new? I just don't understand. Unless I being rude for saying this; I mean no offense and don't expect this to come off as such. But unless there's a new program for extracting Buzz and Woody from KH2, I don't think anyone gives a darn about it on this topic.

As it turns out, Falo's new KH2 dumper allowed me to extract the Buzz and Woody models from KH2. So, never mind.
## Post #257
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2010-10-21T10:24:00+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

huh? where is it?
## Post #258
- Username: grass
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Oct 22, 2010 2:01 am
- Post datetime: 2010-10-21T18:13:50+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Hi, guys, stumbled across this forum looking for a topic similar to this one.

I have a request.
Could anyone rip several models from Birth by Sleep in order to do a height comparison?

I had a few in mind:
1. Model of KH2 Sora and/or Roxas next to Ven. (Amazingly, some people aren't convinced they're the same height >_>)

*SPOILER* Sora and Roxas' models should be in the game, assuming that the secret ending is using in-game models and not a video format. *SPOILER*

2. Also, I'm sure you've seen that image comparing the heights of the Organization floating around the web, so I was wondering if, for reference, someone could do a comparison similar to that, ie:
Terra/Braig/Dilan/Even/Elaeus/Ienzo/Isa/Lea/Ven

3. Lastly, a comparison of the heights of the Mysterious Figure (optional boss exclusive to the international release) next to Master Xehanort in his Organization cloak, young Master Xehanort, Terra, Ansem the Wise in his Organization cloak, and KH2 Riku.
Doing this could presumably rule out a few theories.

If anyone could do any of these, I'd be extremely thankful. I can't really offer anything than my undying gratitude. xD
Or if no one could do it, I was wondering if someone could point me in the right direction.

Thanks in advance!
## Post #259
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-10-21T18:23:32+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I think the secret ending is pre-rendered. I could be wrong. But its hard to search thorough the models because there isn't a model viewer, you have to convert them manually to find out what they are.
## Post #260
- Username: grass
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Oct 22, 2010 2:01 am
- Post datetime: 2010-10-21T18:31:30+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

If it's pre-rendered, I'll be pissed. 

Nomura even said it wasn't:

> --- Of course you usually have a secret movie at the end, do you have one this time too?
>
> Nomura: Yes there is one. Except this time it isn’t a pre-rendered movie that gives a hint as to how the story will develop later, but is shown like an event scene. There is dialog, and in all it runs about ten minutes. It is set up as one episode. Instead of showing us what will happen in the future, it is more like a true ending. I would really like everyone to see it. There are characters that will only show up there in it as well.
## Post #261
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2010-10-22T03:51:37+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from grass
>
> 
1. Model of KH2 Sora and/or Roxas next to Ven. (Amazingly, some people aren't convinced they're the same height >_>)

*SPOILER* Sora and Roxas' models should be in the game, assuming that the secret ending is using in-game models and not a video format. *SPOILER*It's a pre-rendered movie, no Sora, Axel, Xion, Ansem.
But Sora should have a different height, because Sora = Vanitas, Ventus = Roxas
Sora != Roxas

> Reply from grass
>
> 
2. Also, I'm sure you've seen that image comparing the heights of the Organization floating around the web, so I was wondering if, for reference, someone could do a comparison similar to that, ie:
Terra/Braig/Dilan/Even/Elaeus/Ienzo/Isa/Lea/Veni tried it, this is the result:
[http://www.imagebanana.com/view/16vi405e/noname.png](http://www.imagebanana.com/view/16vi405e/noname.png)

looks a little bit strange, because, now i know what this unknown float in the header is, it's the model scale...
without it, all models are scaled to 1.0

Edit:
here a new pic:
[http://www.imagebanana.com/view/8znr2sqf/noname2.png](http://www.imagebanana.com/view/8znr2sqf/noname2.png)

was easy to fix:

```
            VerticeX *= pmoHeader.modelScale;
            VerticeY *= pmoHeader.modelScale;
            VerticeZ *= pmoHeader.modelScale;
```


> Reply from grass
>
> 
3. Lastly, a comparison of the heights of the Mysterious Figure (optional boss exclusive to the international release) next to Master Xehanort in his Organization cloak, young Master Xehanort, Terra, Ansem the Wise in his Organization cloak, and KH2 Riku.
Doing this could presumably rule out a few theories.i looked through every model file, i cannot find him
## Post #262
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-10-22T04:48:23+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

And this is the problem grass. Model viewing is never perfect, though it can get close sometimes. But things such as side by side height measurements can easily be rigged and messed up both intentionally and unintentionally.

A character's height and overall size could easily be incorrect versus another character by something just as simple as being more zoomed in on the model, or perhaps you were scaling all axis's of the model by like .8 to make them fit a different scale and then you forget that later and when you put the models side by side they could all be at different scaling values yet again messing up height values.

Take this image for example:

[http://varika.pair.com/mp3/KH%20Models/ ... 20Side.jpg](http://varika.pair.com/mp3/KH%20Models/Org%20Heights%20Side.jpg)

I know from looking at these models without touching any sorta zoom or repositioning at all that these height values are off. A lot of the characters are near the same height Lexaues included. It just appears that he's taller because the model is zoomed in more. He's tall but not to such an extent. And this is the problem. It's not easy to set these up for accuracy and you can't guarantee that someone else did the work accurately.

Take Falo's image for example. He was very careful and did everything properly but there apparently is some sort of scaling value used in the game that wasn't taken into factor so the characters are all relatively the same height with different body proportions such as Ienzo having a huge head and such, well rather huge everything compared to some of the characters next to him. But this is just because the game just renders him at a smaller scaling value which makes him look natural.

It is my opinion that such height comparison images just have too much room for error no matter how careful the person producing the image is, and as such they shouldn't be given any sort of credibility.

Edit: Also the end movie is indeed pre-rendered without the models actually being in the game. It just isn't pre-rendered CGI with the high detail that we're used to seeing on the ps2 games. The only thing I could even find close to that would be a model of Riku that was as he appears in KH2. Though I'm not sure where such a model actually was used in-game.
## Post #263
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2010-10-22T05:39:28+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Zerox
>
> Edit: Also the end movie is indeed pre-rendered without the models actually being in the game. It just isn't pre-rendered CGI with the high detail that we're used to seeing on the ps2 games. The only thing I could even find close to that would be a model of Riku that was as he appears in KH2. Though I'm not sure where such a model actually was used in-game.

The Riku model was used in Terra's Story, when you meet Sora & Riku as kids on Destiny Island,
Terra gives Riku the keyblade ability, then he sees him as Riku from KH2. (the scene does make no sense...)

but it's not like in KH2,
BBS: 7172 Vertices, 4750 Faces
KH2: 14511 Vertices, 4837 Faces

I can understand him, he wanna know who the Unknown (Mysterious Figure) is, but we all know it already, he
uses the same weapons as Xemnas, he tests Aqua, Ven, Terra like he did with Sora in KHFM and KH is still in the Xehanort Saga,
so who could it be ? only Xemnas or (again, like nobody&unversed) a new form of enemy born from Xehanort/Vanitas, but we will know it when KH3DS comes out. (*Spoiler*Master Xehanort comes back from the death...*Spoiler*)

back to Topic,
i will try to release a new version of my converter this weekend, 
after fixing some things and playing through Fallout New Vegas ^^
## Post #264
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-10-22T06:02:53+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Ah okay that's why its there. Thank you for clarifying as I haven't played through Terra's story yet. I also knew the models weren't the same. It's easy to tell just by the texture maps.

Though admittedly that last bit of your post was the best news in this thread for a while now. You just made my day about 50 times all at once.
## Post #265
- Username: grass
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Oct 22, 2010 2:01 am
- Post datetime: 2010-10-22T18:47:02+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Zerox
>
> And this is the problem grass. Model viewing is never perfect, though it can get close sometimes. But things such as side by side height measurements can easily be rigged and messed up both intentionally and unintentionally.

A character's height and overall size could easily be incorrect versus another character by something just as simple as being more zoomed in on the model, or perhaps you were scaling all axis's of the model by like .8 to make them fit a different scale and then you forget that later and when you put the models side by side they could all be at different scaling values yet again messing up height values.

It is my opinion that such height comparison images just have too much room for error no matter how careful the person producing the image is, and as such they shouldn't be given any sort of credibility.

Ah, I see. Well, it doesn't hurt to try just to get some kind of estimate of height.

> Reply from Falo
>
> It's a pre-rendered movie, no Sora, Axel, Xion, Ansem.
But Sora should have a different height, because Sora = Vanitas, Ventus = Roxas
Sora != Roxas

Bummer. 
Well, do you mean that Sora should have the same height? Because if Sora=Vanitas and Ventus=Roxas (and someone for some god awful reason is claiming that Ven is taller than Roxas when it's obvious he's the same height), then Sora=Ventus because we know that Sora=Roxas based on height comparison.

> Reply from Falo
>
> 
Edit:
here a new pic:
http://www.imagebanana.com/view/8znr2sqf/noname2.png

was easy to fix:
Code: Select all            //apply model scale
            VerticeX *= pmoHeader.modelScale;
            VerticeY *= pmoHeader.modelScale;
            VerticeZ *= pmoHeader.modelScale;

Wow, great! Really appreciate it. 
I'll be sure to credit you if I post it elsewhere.

Thanks man.
## Post #266
- Username: Soraoscuro
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Oct 01, 2010 2:31 am
- Post datetime: 2010-10-24T16:25:26+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Falo
>
> grass wrote:
1. Model of KH2 Sora and/or Roxas next to Ven. (Amazingly, some people aren't convinced they're the same height >_>)

*SPOILER* Sora and Roxas' models should be in the game, assuming that the secret ending is using in-game models and not a video format. *SPOILER*
It's a pre-rendered movie, no Sora, Axel, Xion, Ansem.
But Sora should have a different height, because Sora = Vanitas, Ventus = Roxas
Sora != Roxas
grass wrote:
2. Also, I'm sure you've seen that image comparing the heights of the Organization floating around the web, so I was wondering if, for reference, someone could do a comparison similar to that, ie:
Terra/Braig/Dilan/Even/Elaeus/Ienzo/Isa/Lea/Veni tried it, this is the result:
http://www.imagebanana.com/view/16vi405e/noname.png

looks a little bit strange, because, now i know what this unknown float in the header is, it's the model scale...
without it, all models are scaled to 1.0

Edit:
here a new pic:
http://www.imagebanana.com/view/8znr2sqf/noname2.png

was easy to fix:
Code: Select all            //apply model scale
            VerticeX *= pmoHeader.modelScale;
            VerticeY *= pmoHeader.modelScale;
            VerticeZ *= pmoHeader.modelScale;
grass wrote:
3. Lastly, a comparison of the heights of the Mysterious Figure (optional boss exclusive to the international release) next to Master Xehanort in his Organization cloak, young Master Xehanort, Terra, Ansem the Wise in his Organization cloak, and KH2 Riku.
Doing this could presumably rule out a few theories.i looked through every model file, i cannot find him

Mysterious Figure model is b01ex00, just so you know
## Post #267
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2010-10-24T19:08:58+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Soraoscuro
>
> Mysterious Figure model is b01ex00, just so you know

true,but still a ripper for the English version still hasn't came out,and i think it would be hard to rip the model directly from that file you gave me before of MF.
## Post #268
- Username: Soraoscuro
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Oct 01, 2010 2:31 am
- Post datetime: 2010-10-24T20:03:24+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Aurangzeb56
>
> Soraoscuro wrote:Mysterious Figure model is b01ex00, just so you know 

true,but still a ripper for the English version still hasn't came out,and i think it would be hard to rip the model directly from that file you gave me before of MF.

Hard? Lol, no. I can do it anytime.

Edit:
## Post #269
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2010-10-25T05:22:53+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Soraoscuro
>
> Aurangzeb56 wrote:Soraoscuro wrote:Mysterious Figure model is b01ex00, just so you know 

true,but still a ripper for the English version still hasn't came out,and i think it would be hard to rip the model directly from that file you gave me before of MF.

Hard? Lol, no. I can do it anytime.

Edit:

>.< how were you able extract the model?? XD
## Post #270
- Username: GameAreAwesome
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jun 07, 2010 1:49 pm
- Post datetime: 2010-10-25T10:17:48+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Soraoscuro
>
> Aurangzeb56 wrote:Soraoscuro wrote:Mysterious Figure model is b01ex00, just so you know 

true,but still a ripper for the English version still hasn't came out,and i think it would be hard to rip the model directly from that file you gave me before of MF.

Hard? Lol, no. I can do it anytime.

Edit:

Hey If Im not wrong he got this model from an older game of kingdom hearts Probably from KH2
## Post #271
- Username: Soraoscuro
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Oct 01, 2010 2:31 am
- Post datetime: 2010-10-25T11:59:19+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

The contents of this post was deleted because of possible forum rules violation.
## Post #272
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-10-25T14:33:57+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Did Falo say he would upload a new converter this weekend?
Also, Soraoscuro, back at KH-Vids you had a means to play 358/2 in Traverse Town. I requested the gamemod on your page, but you never responded. What happened?
## Post #273
- Username: Soraoscuro
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Oct 01, 2010 2:31 am
- Post datetime: 2010-10-25T15:29:44+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Mirrorman95
>
> Did Falo say he would upload a new converter this weekend?
Also, Soraoscuro, back at KH-Vids you had a means to play 358/2 in Traverse Town. I requested the gamemod on your page, but you never responded. What happened?

Well, I had to do that manually, and you have to replace a room using the method I used. It would be better if I just hacked the room mod for the game wich is pretty easy. This thread isn't about Days so, if you want to keep talking about this either PM me or add me on MSN.
## Post #274
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-10-25T20:31:56+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I'd just like to say thank you for the Mysterious Figure model. Any chance you found his weapon(s) as well? I'd love to get the pmo for them.
## Post #275
- Username: Soraoscuro
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Oct 01, 2010 2:31 am
- Post datetime: 2010-10-25T23:26:11+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Zerox
>
> I'd just like to say thank you for the Mysterious Figure model. Any chance you found his weapon(s) as well? I'd love to get the pmo for them.

The weapons themselves are not a model, just an effect, like Xemnas' blades. The texture should be in the game though, I will try to search for it.
## Post #276
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-10-25T23:53:03+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Soraoscuro that was awesome,how did you extract Mysterius figure model ?
Are currently creating an extractor for KHBBS too ?
## Post #277
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2010-10-26T05:29:46+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Forgot to post this.  Just a simple modification to the quickbms script posted earlier in the thread.  Extracts the files with numerical names, but the lines for naming them based on the textures names is still present if you just uncomment them.  Hope it helps.

JP Version: 858 pmo files
US Version: 897 pmo files (Mysterious Figure is 424)

Still working on a way to properly extract the bbs#.dat files.

i also apologize for putting a txt file in a rar file, heh.  Never did like the forum attachment system, always seem to have problems with it.

Hope it helps.
[extract_pmo_v3.bms.rar](https://xentaxbackup.github.io/file/3554_extract_pmo_v3.bms.rar)
## Post #278
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-10-26T06:44:35+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Well as I don't have access to my Japanese BBS*.dat files due to my laptop having boot issues, I decided to give your new bms script on the data that the game installs onto the psp as it was named similarly. Though despite them being named BBS1.dat, BBS2.dat, BBS3.dat, not a one gave me a model using the new script.

So I guess it just means we have to use it on the files extracted from the UMD iso instead.
## Post #279
- Username: Soraoscuro
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Oct 01, 2010 2:31 am
- Post datetime: 2010-10-26T17:53:01+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from valvoga
>
> Soraoscuro that was awesome,how did you extract Mysterius figure model ?
Are currently creating an extractor for KHBBS too ?

No, I extracted it manually by using a hex editor.

> Reply from revelation
>
> Still working on a way to properly extract the bbs#.dat files.

I'm working on that too but... I can't figure out the LBA >_>
## Post #280
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-10-27T04:56:08+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Thanks a lot for the replied soraoscuro
Soraoscuro i want to ask how did you extract the model (.pmo) to 3ds max
how did you convert the model from pmo to other universal model format like .max
## Post #281
- Username: Soraoscuro
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Oct 01, 2010 2:31 am
- Post datetime: 2010-10-27T09:02:20+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from valvoga
>
> Thanks a lot for the replied soraoscuro
Soraoscuro i want to ask how did you extract the model (.pmo) to 3ds max
how did you convert the model from pmo to other universal model format like .max

I used Falo's converter (it's in this thread, in previous pages). His converter extracts the textures, bones and the model as an .obj file you can load up in 3DS Max, I dunno about other 3D model viewers.
## Post #282
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-10-27T12:43:54+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

So, Mradults has updated Noesis, and this one lets you add your own file formats through plugins...

I was thinking that, instead of having to write a new viewer/converter, someone could just make a plugin for BBS in Noesis.
## Post #283
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-10-30T00:52:50+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from ultimaespio
>
> So, Mradults has updated Noesis, and this one lets you add your own file formats through plugins...

I was thinking that, instead of having to write a new viewer/converter, someone could just make a plugin for BBS in Noesis.

I think this is a splendid idea! But as Falo said he intended to release his updated converter soon, we just have to wait for him to finish Fallout New Vegas, I don't see how important such would be. Though admittedly having the converter all in one place would be nice.

Edit: Well it's the weekend now. I'm hopeful that Falo may have a wonderful gift for us.
## Post #284
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-10-30T23:04:07+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Happy Halloween everyone
## Post #285
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-11-02T02:08:10+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Will we be able to extract the 3D models pertaining to Jungle Book?
## Post #286
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-11-02T06:34:22+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

In theory such is possible MirrorMan. Though they'd probably only exist as level data which is only in a primitive state as far as anyone here's ability to view levels goes. But perhaps there are a few doodads you may find that you could convert, things like trees and the like.

Anyway it's been 10 days since Falo posted saying he might release his converter updated. And I must say I'm still anxiously awaiting it. I just hope he's near the end of Fallout New Vegas by now.

After all I saw that in his last image he showed that he'd fixed the UV issues on Terra and Ven's armors. I'd love to be able to take a closer look but currently all I get is a garbled mess. But I'll just be patient.

[http://www.imagebanana.com/view/4xfkqsed/TVA.jpg](http://www.imagebanana.com/view/4xfkqsed/TVA.jpg)
## Post #287
- Username: Soraoscuro
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Oct 01, 2010 2:31 am
- Post datetime: 2010-11-07T02:32:16+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Mirrorman95
>
> Will we be able to extract the 3D models pertaining to Jungle Book?

Apparently there doesn't seem to be any, but I believe there must be one since there are FULLY textured and finished maps inside the game.
## Post #288
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-11-07T03:55:38+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

That's going to work. Although, the 358/2 model post is all but dead now.
## Post #289
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-11-09T16:57:37+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

So...any updates at all? Seems this thread is dying off a bit.

Remember that you can just write a plugin for Noesis now, rather than having to create your own viewer/dumper.

Btw Zerox, I've been meaning to ask, did you rig that model of Aqua yourself, or did you manage to use the bones.txt?
## Post #290
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-11-09T18:23:31+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Indeed. Most chatter died off when Falo said he was going to release a new converter but that was two weeks ago. 

I'd be willing to look at making plug-ins for Noesis but somewhere I missed that documentation for it or anywhere that mentioned it. I may just have looked in the wrong place but if you could help point me in the right direction that'd be wonderful. It's in 1.9 right? 

I wish I could of used the bones.txt but I just rigged it myself. Sorry to disappoint.
## Post #291
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-11-09T18:27:22+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I thought you had, I was thinking there was no way you could have used the bones.txt  

Actually its 2.3 now. If you download that you'll find a sample one in the plugins folder, but it looks incredibly complicated :/
## Post #292
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-11-10T03:57:06+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I would recommend the Quake 2 MD2 importer/exporter example for beginners, it's pretty dead-simple. But if you don't know C/C++, you won't understand it. I have noticed most of the major model RE's here on Xentax seem to write standalone tools in C/C++, though. Except chrrox, who is the main player that seems to like sticking with maxscript.
## Post #293
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2010-11-13T02:59:14+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Just some image to hype you guys, and hopefully get this topic further to its conclusion.  The format has already been posted and now, well, you asked, and i went ahead and set aside a little bit of time to convert my code for you...

[](http://img813.imageshack.us/i/noesiskhbbs427.jpg/)[](http://img696.imageshack.us/i/noesiskhbbs447.jpg/)[](http://img97.imageshack.us/i/noesiskhbbs424.jpg/)[](http://img168.imageshack.us/i/noesiskhbbs37.jpg/)

Still some issues with vertex colors with alpha and joint weights, but hopefully i can get those fixed as well.
## Post #294
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-11-13T05:39:42+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I realize you say that there are still things to work out but that is the best news I have ever seen. Especially if that plug in sees the light of day. Even if it doesn't go any further than it already has. It's capable of much more than Falo's converter's old release is by the looks of it.

I wish I had more time to learn and look at how you did it myself.
## Post #295
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-11-13T10:19:28+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

That is a breakthrough for kh model wow
That is awesome revelation
## Post #296
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-11-13T13:10:26+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Wow, great job  

They look so much better now. So, what's the problems with joint weights?
## Post #297
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-11-13T18:14:05+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

When will someone come out with a new PMO extraction or conversion script? And how do you make the tm2 files into pngs that actually look like the real game textures?
## Post #298
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-11-13T20:02:48+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Just want to thank revelation in public for being the first person to take the initiative and make a Noesis plugin.  He exposed some bugs in the Noesis plugin system in the process too, so I'll be putting a new version up today or tomorrow that fixes those bugs, and his plugin will probably be following soon after.
## Post #299
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2010-11-14T20:34:15+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Thanks go to MrAdults for his tool and help getting you a working KHBBS plugin for Noesis. [http://oasis.xentax.com/index.php?content=plugins](http://oasis.xentax.com/index.php?content=plugins)  Source code is included for those interested, and any bug reports or fixes are greatly appreciated.  Hope this is useful to those of you interested in investigating the models further.
## Post #300
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-11-14T20:42:31+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Congrats, your the first to ever make a public plugin for Noesis  

One thing I've noticed with HQ Aqua 396.pmo, is that there are a lot of meshes, 74 to be exact.

451.pmo is Master Xehanort, only he has that weird Rainbow texture that Woody and Buzz have in KH2.

MISSING LILO AND STICH CHARACTER 524.PMO

Wendy Pleakley, that one with the one eye and annoying voice.

653.pmo is Pluto, but I don't recall seeing him in BBS at all :/

243.pmo is the Door to Kingdom Hearts...though I don't recall seeing that either.

759.pmo appears to be a disney keyblade, though I don't recognise it.
## Post #301
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-11-14T23:26:48+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Noesis shows me nothing but weird lines when viewing most obj files. Is there a graphics card requirement for fixing that?
## Post #302
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-11-15T02:03:53+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Everyone please help
I already put kingdom_hearts_bbs.dll in plugins folder but i still can't open .pmo file in noesis
And i use noesis 2.4.i try to see the list of known format in noesis tab but there is no .pmo file support
Please help
## Post #303
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-11-15T02:24:20+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I am like so happy that I could kiss you and I'm not even joking. I never would have imagined that something so great would ever be finished for this! I am so very thankful to you revelation, and Mr. Adults too for making his plugin system. I can now convert models with ease that took me hours of converting, mesh repair, uv map repair and re-rigging. Oh this makes my life so much easier to look at these models up close.

THANK YOU!

Now to report on it. It seems that it always exports a blank texture called "defaulttexture.png" every time. It's not an issue but it's just excess. Also when I try to out put as a tga instead of png it still exports a png. Some models appear to be half transparent but it's a small issue that's fixable outside Noesis. Thank you so much!
## Post #304
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-11-15T02:33:55+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Mirrorman95
>
> Noesis shows me nothing but weird lines when viewing most obj files. Is there a graphics card requirement for fixing that?
Upload an example file, please.

> Reply from valvoga
>
> Everyone please help
I already put kingdom_hearts_bbs.dll in plugins folder but i still can't open .pmo file in noesis
And i use noesis 2.4.i try to see the list of known format in noesis tab but there is no .pmo file support
Please help
Do other plugin formats like Bayonetta and Quake 2 MD2 show up? Also, it would be under "K" in the list for Kingdom, not P. Also, what is the full path name for the folder you're running Noesis from? Which version of Windows are you under? Do you have Windows UAC enabled or disabled?
## Post #305
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2010-11-15T02:50:01+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

The meshes mentioned that show up rainbow colored, actually do not have textures.  There are a few other meshes that have textures, but whose offsets do not point to valid TIM2 information when used.  Until a proper way for extracting data from the dat files is made, i cannot tell why this is the case.

Some meshes still show up as semi-transparent at times as there are some textures whose palette seems to have alpha values that max at 0x80 instead of 0xFF and there is no way i have seen to tell if this is correct or if it should be adjusted. A lot of ps2 image data usually has alpha values that max at 0x80, so i will investigate further and see if i should treat these as such as well.

i guess technically i don't really need the default material i create.  Noesis seemed to behave fine when a mesh referenced a texture index that did not exist, but i was just trying to be on the safe side.
## Post #306
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-11-15T02:59:35+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Yeah, you can also set the texture index on a material to -1 if it's not valid. That's probably the safest thing, since everything checks if it's >= 0. I think everything checks if it's < numTextures too, but I'm less sure about that.

And...I just put a fix up as 2.41 which should correct the default texture output type not being obeyed.
## Post #307
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-11-15T03:45:43+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from MrAdults
>
> Mirrorman95 wrote:Noesis shows me nothing but weird lines when viewing most obj files. Is there a graphics card requirement for fixing that?
Upload an example file, please.
I have attached a screencap of Noesis. When I try to open OBJs exported from Falo's PMO script, I only see lines extending outward no matter what I do, and when I turn wireframe off I get nothing. When I try to open any OBJs exported from ModelViewerWXD3D9 with 3D Ripper DX, it can only export and not view them.
The PMO plugin, I must say, is working excellently. I only hope that one day, someone will figure out how to make a MDLX plugin for the Noesis program.
[OBJs.png](https://xentaxbackup.github.io/file/3607_OBJs.png)
## Post #308
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-11-15T04:49:32+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Ah thank you for the update Mr. Adults. And again thank you revelation.
## Post #309
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-11-15T05:11:51+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

@MrAdults
Yes Bayonetta and Quake 2 MD2 are showing up 


I already check under "K" but there is no kingdom


The full path name is "C:\Documents and Settings\a\Desktop\KH"
I already tried in other computer but still can't

Im using window xp sp2

Here is the noesis folder and plugin folder




And i already tried using noesis 2.41 but still the plugin doesn't show up
And thanks a lot for your attention MrAdults
## Post #310
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-11-15T05:49:42+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Mirrorman95: I need the actual obj file to see what's going on.

valvoga: Well, since the plugins are working, there are only two real possibilities. 1, you aren't really running Noesis 2.41. Make sure you have extracted it to the right place and what have you. 2, the DLL is failing to load due to a dependency. This would be quite strange since I believe revelation based the project file on my other plugins which you are able to load just fine. Try looking at the KH plugin DLL with Dependency Walker and see if it shows any errors. [http://www.dependencywalker.com/](http://www.dependencywalker.com/)
## Post #311
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-11-15T06:07:24+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from MrAdults
>
> Mirrorman95: I need the actual obj file to see what's going on.

valvoga: Well, since the plugins are working, there are only two real possibilities. 1, you aren't really running Noesis 2.41. Make sure you have extracted it to the right place and what have you. 2, the DLL is failing to load due to a dependency. This would be quite strange since I believe revelation based the project file on my other plugins which you are able to load just fine. Try looking at the KH plugin DLL with Dependency Walker and see if it shows any errors. http://www.dependencywalker.com/

I have uploaded the OBJ here:
[http://www.brickshelf.com/gallery/mirro ... wm_001.obj](http://www.brickshelf.com/gallery/mirrorman95/Zatth/_8_g12wm_001.obj)
## Post #312
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-11-15T06:27:06+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

The file is generally in bad form, and crashes Max 9's obj importer outright. And its triangle windings are messed up. But the next version of Noesis will choke it down, since it's technically compliant to the obj spec.
## Post #313
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-11-15T06:36:43+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I'm glad to hear that.

Also, has anyone figured out how to view MDLX files on a program other than ModelViewerXVD3D9?
## Post #314
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-11-15T07:06:29+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Thanks a lot MrAdults now its working after i know where the error is
Also thanks a lot for the KHBBS model extractor,
Revelation and MrAdults you two are an awesome heroes 
Thanks a lot,thanks for your magnificent epic work revelation and MrAdults
## Post #315
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-11-15T15:35:14+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Ok, I think we should start making a reference list. I'll add them to the first post.

If you find a model, post it and I'll add it.

Check my list first so that you don't waste your time posting it if I've already got it
## Post #316
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-11-15T16:02:17+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I'm all for compiling a list of what's what. But shouldn't we make the list on Xentax's wiki? That way we could all update it.
## Post #317
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-11-15T16:22:38+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Do we need permission to post on the wiki? If not then I'll just copy it over. I'll keep it on the first post too though.
## Post #318
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2010-11-15T16:38:25+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

You may also need to specify which version you are referencing, as the US release has a few more files and the numbering will be different from the JP release.

Hopefully we can get to the point of having actual file names, or at least the hash values for them.
## Post #319
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-11-15T16:39:56+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Yeah, proper names would really help. The ones we have now are all jumbled up, in some random order.

I forgot to mention, the plugin loads tiny parts of level geometry from pmo's in BB2.dat. They aren't textured though.
## Post #320
- Username: Soraoscuro
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Oct 01, 2010 2:31 am
- Post datetime: 2010-11-15T21:16:41+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Ultimaespio. PMO number 759 isn't an unused keyblade, it's Victory Line, this keyblade:



> Reply from valvoga
>
> Thanks a lot MrAdults now its working after i know where the error is
Also thanks a lot for the KHBBS model extractor,
Revelation and MrAdults you two are an awesome heroes 
Thanks a lot,thanks for your magnificent epic work revelation and MrAdults

How did you get it working? It still doesn't work for me, the file format doesn't appear.
## Post #321
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-11-15T22:23:14+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

You need to add the plugin to the program.
## Post #322
- Username: Soraoscuro
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Oct 01, 2010 2:31 am
- Post datetime: 2010-11-15T22:29:37+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Mirrorman95
>
> You need to add the plugin to the program.

I put the plugin in the plugins folder, but it still doesn't work.

EDIT:
525.pmo = One of the Lost Boys (The fat one)
527.pmo = Dilan
529.pmo = Doc (Dwarf)
531.pmo = Mickey with Starseeker
533.pmo = Chip
534.pmo = Dale
535.pmo = Fairy Godmother
537.pmo = Daisy (UNUSED MODEL)
539.pmo = Ven in blanket
540.pmo = Ven in blanket but without shirt (No texture)
541.pmo = Frozen Ven
543.pmo = Grand Councilwoman
545.pmo = Smee
547.pmo = Lea
549.pmo = Red Fairy from Sleeping Beauty
551.pmo = Grumpy
553.pmo = Red Firecracker
554.pmo = Blue Firecracker
555.pmo = Yellow Firecracker
556.pmo = Cinderella's Stepmother
558.pmo = Chip (again)
560.pmo = Dale (again)
562.pmo = KH2 Riku (No Texture)
563.pmo = Ventus armor frozen (Unfinished texturing)
565.pmo = Isa
567.pmo = Green fairy from Sleeping beauty
569.pmo = Happy
571.pmo = Happy (again)
573.pmo = Drizella
575.pmo = Huey
576.pmo = Dewey
577.pmo = Louie
579.pmo = Kid Sora
581.pmo = Kid Kairi
583.pmo = Blue Fairy from Sleeping Beauty
585.pmo = Sleepy
587.pmo = Anastasia
589.pmo = That cow guy from Disney Castle
591.pmo = Kid Riku
593.pmo = Kairi's grandmother
595.pmo = Maleficent's raven
597.pmo = Bashful
599.pmo = Jaq
601.pmo = Scrooge
615.pmo = Moogle
617.pmo = Darkside
618.pmo = Merlin
625.pmo = Moogle
628.pmo = Pot of "Hunny"
629.pmo = Jaq
847.pmo = Terra's Ultima Cannon
849.pmo = Aqua's Keyblade Rider
850.pmo = Aqua's Keyblade Rider (Disney Town version)
852.pmo = Terra's Keyblade Rider
853.pmo = Terra's Keyblade Rider (Disney Town version)
855.pmo = Ven's Keyblade Rider
856.pmo = Ven's Keyblade Rider (Disney Town version)
## Post #323
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-11-15T23:42:37+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

valvoga/Soraoscuro: Can you explain what you were doing wrong? It would be useful for anyone else that has problems, as well as for me to know how I might improve the user experience and make things more obvious. Although I didn't think I could get much more obvious than "put the file in this folder, restart the app". 

I think it might also be not the best use of time to chronicle these PMO files in their current state. As revelation mentioned, there are regional differences. But more importantly, the script produces a lot of ~1KB files which do not seem to contain all of the data that they should. I haven't looked into this at all personally, but I'd say there might be a problem in the bms script in terms of getting the file size. Or, the containers may be fragmented across some sector boundaries or something. Or they're just false-positives. I'm just guessing blind there, but in any case, it'd probably be good to at least get that 1KB-file issue sorted before making lists.
## Post #324
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2010-11-16T00:03:24+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

The 1k files are usually correct.  These appear to mostly be collision meshes from what i have seen.  There are other files that contain offsets for textures that don't point to the usual TIM2 block, so i truncate those in the bms script i posted.  i cant determine yet whether this simply contains a different texture storage method or if they reference the data in some other way.  Hopefully the actual archive structure fr the dat files can be determined at some point.  Haven't taken the time to look into it all that deeply yet.  But, yeah, even then there could be things still missed in the current interpretation of the format since they are simply brute-forced out of the archive.

Are there any 1k ones that fail to load?
## Post #325
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-11-16T00:47:49+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Okay I'm not sure why but for some reason my numbers aren't matching up with yours at all. What BBS#.dat are you extracting them from?

Edit: Okay I was looking at BBS1.dat's dumped files. It appears the list is made from BBS0.dat. I'd be good if you specified that.
## Post #326
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2010-11-16T01:32:12+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Thanks for noesis plugin!
I try made fast render with blender, and I have this result:



Why model is too "squared"?
I export in md5.
## Post #327
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-11-16T01:50:45+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from revelation
>
> The 1k files are usually correct.  These appear to mostly be collision meshes from what i have seen.  There are other files that contain offsets for textures that don't point to the usual TIM2 block, so i truncate those in the bms script i posted.  i cant determine yet whether this simply contains a different texture storage method or if they reference the data in some other way.  Hopefully the actual archive structure fr the dat files can be determined at some point.  Haven't taken the time to look into it all that deeply yet.  But, yeah, even then there could be things still missed in the current interpretation of the format since they are simply brute-forced out of the archive.

Are there any 1k ones that fail to load?

Oh, I didn't even know you had posted a script. I've been using the one Falo posted on page 1 of this thread. With that, almost all of the 1k files fail to load, due to bad offsets in the files. I'll re-dump with your script and let you know if I still run into trouble. (I'm guessing I won't)
Edit: Yeah, my bad. Your latest script gets rid of all those 1KB garbage files.

grotesque: The default normal generation only smooths between faces which share a single vertex. Most of the KHBBS models are broken up with not many shared verts, so you get those blocky results. You can add -smoothnorm 0.001 or something like that to your "Advanced options" in the Noesis export. Or smooth the normals in your modeling app. Normal smoothing isn't enabled by default, because it takes a good bit of time on more complex models.
Edit 2: Oh, and md5mesh is probably a bad idea. That format does not even store normals. So those screwed normals are the result of your modeling app generating them for import. (and likely also not smoothing normals spatially) I guess a -vertcull 0.01 0.01 0.01 might also do the job, unless it still can't collapse the verts due to UV space being inconsistent with model space.
## Post #328
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-11-16T02:09:05+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I didn't notice you wrote one either. I'll re dump them again, i'll probably have to change the list too. It didnt take very long to do before.


Falo's script doesnt seem to dump all the models either, there are some missing. Only a few of the world map ones show.
## Post #329
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-11-16T03:16:39+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

@MrAdults
@Soraoscuro

Sorry for the late reply MrAdults
For those who having problem with the KHBBS plugin,like the file format doesn't appear in the Noesis list

Note : if you have the previous Version Noesis in other folder or other drive be sure to delete it first and Just use the latest version of noesis

Here is the solution :
1.Make a new folder in your desktop and name that new folder "Noesis"
2.Then download the latest version of Noesis,Noesis 2.42,then extract it in "Noesis" folder that you create earlier
3,Then download Revelation KHBBS plugin,the extract it in "Noesis" folder then copy kingdom_hearts_bbs.dll to plugins folder 
4.Then after that open noesis,if the file format still don't show up restart your pc,and after you restart your pc you will see the format "Kingdom Heart BBS(.PMO)"

I hope its working for you too and I hope this will help you
## Post #330
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-11-16T03:27:36+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I extracted the 3 dat files and using that new pmo bms script that doesn't drop pmos into folders I found hundreds more models, especially in bbs2.dat.
## Post #331
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-11-16T10:08:15+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

You can view a few maps in bbs1.dat with the new extractor. I've noticed though, that the ones from bb2.dat are incredibly broken.
## Post #332
- Username: Soraoscuro
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Oct 01, 2010 2:31 am
- Post datetime: 2010-11-16T11:35:46+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from valvoga
>
> @MrAdults
@Soraoscuro

Sorry for the late reply MrAdults
For those who having problem with the KHBBS plugin,like the file format doesn't appear in the Noesis list

Note : if you have the previous Version Noesis in other folder or other drive be sure to delete it first and Just use the latest version of noesis

Here is the solution :
1.Make a new folder in your desktop and name that new folder "Noesis"
2.Then download the latest version of Noesis,Noesis 2.42,then extract it in "Noesis" folder that you create earlier
3,Then download Revelation KHBBS plugin,the extract it in "Noesis" folder then copy kingdom_hearts_bbs.dll to plugins folder 
4.Then after that open noesis,if the file format still don't show up restart your pc,and after you restart your pc you will see the format "Kingdom Heart BBS(.PMO)"

I hope its working for you too and I hope this will help you

It still doesn't work for me D; It still doesn't detect it. I tried changing the plugin name to an already existing plugin like Bayonetta's and now it detects the pmos in the explorer but it won't open them.
## Post #333
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-11-16T14:33:31+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Soraoscuro
>
> It still doesn't work for me D; It still doesn't detect it. I tried changing the plugin name to an already existing plugin like Bayonetta's and now it detects the pmos in the explorer but it won't open them.
Hm, that makes absolutely no sense. There are no actual references to any existing plugins at all in Noesis itself, and file name is completely irrelevant as long as the extension is .dll. What you say makes it sound like something is fundamentally broken in the Windows library caching on your machine.
## Post #334
- Username: SirLoon
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 19, 2009 12:26 am
- Post datetime: 2010-11-17T01:42:56+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Mirrorman95
>
> MrAdults wrote:Mirrorman95 wrote:Noesis shows me nothing but weird lines when viewing most obj files. Is there a graphics card requirement for fixing that?
Upload an example file, please.
I have attached a screencap of Noesis. When I try to open OBJs exported from Falo's PMO script, I only see lines extending outward no matter what I do, and when I turn wireframe off I get nothing. When I try to open any OBJs exported from ModelViewerWXD3D9 with 3D Ripper DX, it can only export and not view them.
The PMO plugin, I must say, is working excellently. I only hope that one day, someone will figure out how to make a MDLX plugin for the Noesis program.
maybe its too late, but your problem looks like changed local setings and your windows use , as separator instead . I hope it is this problem
## Post #335
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-11-17T16:40:09+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from SirLoon
>
> Mirrorman95 wrote:MrAdults wrote:Noesis shows me nothing but weird lines when viewing most obj files. Is there a graphics card requirement for fixing that?
Upload an example file, please.
I have attached a screencap of Noesis. When I try to open OBJs exported from Falo's PMO script, I only see lines extending outward no matter what I do, and when I turn wireframe off I get nothing. When I try to open any OBJs exported from ModelViewerWXD3D9 with 3D Ripper DX, it can only export and not view them.
The PMO plugin, I must say, is working excellently. I only hope that one day, someone will figure out how to make a MDLX plugin for the Noesis program.
maybe its too late, but your problem looks like changed local setings and your windows use , as separator instead . I hope it is this problem

The newest version of Noesis solved the problem. I still can't see textures, but the models look like models now.
## Post #336
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-11-20T15:23:34+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I've come across a problem with Ven's eyes:



His pupils sink into his eyeballs. This only happens with Ven for some reason.
## Post #337
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-11-20T22:05:29+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Looks to me like you just have blending disabled, and the eyelashes not blending causes it it look inset.
## Post #338
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-11-21T01:33:14+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

ultimaespio, it seems your screenshot lacks transparency all together. Most notably on the zipper of his jacket. Make sure you export the textures to a format that actually is capable of real transparency. That may be a large part of your problem.
## Post #339
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-11-21T03:17:26+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Is there any way to extract a 3D model of Xion from Birth By Sleep or 358/2 Days? Besides the Heartless exclusive to 358/2, the Bugs in Re:Coded, and Jiminy's Journal, Xion is the only character we don't have a 3D model for. And someone already extracted the XIII Moogle. Why can't we find all the Blank Points models anyway?
## Post #340
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-11-21T04:54:17+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Mirrorman95
>
> Is there any way to extract a 3D model of Xion from Birth By Sleep or 358/2 Days? Besides the Heartless exclusive to 358/2, the Bugs in Re:Coded, and Jiminy's Journal, Xion is the only character we don't have a 3D model for. And someone already extracted the XIII Moogle. Why can't we find all the Blank Points models anyway?

That someone who ripped the XIII Moogle would be me. But it was by no means an easy process. I had resurrect it from this mess:



But I ended with this after several hours:



I would LOVE to get a Xion model just to look at how they modeled her hair as I've been unsuccessful in recreating her hair perfectly no matter how much I try. To get a Hi-Res one such as the one seen in Blank Points would be fantastic, though as I believe the video is pre-rendered, or at least we've been unsuccessful in finding where the models are stored, that's not going to happen. Though I'd be just as happy with the low poly one from 358/2 Days, but no one with the skills necessary as well as the time to do it seems to be around at the moment. If we figured out Days format we'd have Re: Coded as well as they're identical.
## Post #341
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-11-21T05:49:00+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Can anyone figure this out?
## Post #342
- Username: Panzah
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Jul 22, 2010 5:11 am
- Post datetime: 2010-11-21T08:54:44+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

For those that don't know, I can confirm that the whole BBS Secret Ending "Blank Points" is Pre-Rendered, which means there is no way of getting the models used there without busting into Square Enix.
## Post #343
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-11-22T12:43:00+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Panzah
>
> For those that don't know, I can confirm that the whole BBS Secret Ending "Blank Points" is Pre-Rendered, which means there is no way of getting the models used there without busting into Square Enix.

Yeah, that is true. There are no models of Sora or Kairi in their kh2 costumes. You can tell by watching the video that its pre-rendered.

MrAdults, Zerox, I do have transparency enabled, its just the model that I was using. I've tried another Ven, and that was fine. Some KH2 models do that sometimes, it's fixed by moving the pupil bone slightly forward.

Anyway, found the old model of Aqua:



Interestingly, the textures are 512x512 for this one.
## Post #344
- Username: Panzah
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Jul 22, 2010 5:11 am
- Post datetime: 2010-11-22T15:00:58+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Found it on the same day the Noesis plugin was released, it's not anything special though. There also is a pre-censored Aqua model in the files, as in with whole back of her body open up to her waist, not just top.
## Post #345
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-11-22T15:02:38+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Panzah
>
> Found it on the same day the Noesis plugin was released, it's not anything special though. There also is a pre-censored Aqua model in the files, as in with whole back of her body open up to her waist, not just top.

Which .dat is it in, and what number is it?

Found it 

I've edited the kh wiki so that the Trivia section in Deep Space mentions Pleakley, but someone keeps taking it off
## Post #346
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-11-28T07:40:57+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I made a Xion Face Model with Faceworx. The trick is getting the ears right.
[http://www.brickshelf.com/gallery/mirro ... /xion3.obj](http://www.brickshelf.com/gallery/mirrorman95/Zatth/xion3.obj)
[http://www.brickshelf.com/gallery/mirro ... /xion3.mtl](http://www.brickshelf.com/gallery/mirrorman95/Zatth/xion3.mtl)
[http://www.brickshelf.com/gallery/mirro ... /xion3.jpg](http://www.brickshelf.com/gallery/mirrorman95/Zatth/xion3.jpg)
## Post #347
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-11-28T21:58:58+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Nice attempt at a Xion head but to be honest there are flaws with it. The hair is part of the face mesh which really it should pop out. To be honest it only looks okay from the front. XD Sorry.

> Reply from ultimaespio
>
> Anyway, found the old model of Aqua:



Interestingly, the textures are 512x512 for this one.

I can't seem to find it I've looked at every model in BBS0.dat's dump. So where did you find it and what version American or Japanese?
## Post #348
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-11-28T22:02:35+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

It's in BB1.dat, Jap version. Can't remember the number, but it's one of the biggest pmo's. So just arrange them in Noesis by size and you'll find it.

You can find Ven's awakenings and a part of Disney Town in there too.
## Post #349
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-11-28T22:43:26+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I know the face is messed up, but I don't have a non-BMD0 render of her face without the hair sticking out, and the ears don't come out right. So it's just close to a PS2-quality model of Xion's head that I know how to produce so far.
Also, is there a way to extract the files out of P2s? I've kind of been asking this a few times, but I never really got a response.
## Post #350
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-11-29T04:47:43+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Console Tool 3.0 has come out, but it can't view BMD0 or NSBMD files.
## Post #351
- Username: dzre
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Sep 26, 2010 3:02 am
- Post datetime: 2010-11-29T18:39:13+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Could you post the ven's awakenings' textures here?
## Post #352
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-12-01T02:21:06+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Well I found the previous versions of Aqua's model. They were both in BBS3.dat. I also found a unfinished Bruiser unversed that has a texture without any real shading on it in BBS3.dat as well. Both in the japanese version.

I was able to find the "No Name" Keyblade in the English version of BBS's .dat files. But I can't seem to find any of his weapons. Has anyone had any luck finding them even just the textures for them?
## Post #353
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-12-01T02:51:24+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I personally have not found that. Also, does anyone have the models or textures for the Tron-styled Keyblades?
## Post #354
- Username: Panzah
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Jul 22, 2010 5:11 am
- Post datetime: 2010-12-01T03:13:27+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Mysterious Figure's weapons are FX based, just like Xemnas' etheral blades. Basicly, there is no model file for them, they are just FX effects.
## Post #355
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2010-12-01T03:25:20+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from dzre
>
> Could you post the ven's awakenings' textures here?

Check your private messages.

> Reply from Mirrorman95
>
> I personally have not found that. Also, does anyone have the models or textures for the Tron-styled Keyblades?

That's too bad. And no I don't have them, though really that's a question better suited to a KH2 thread such as this: [viewtopic.php?f=16&t=5394](http://forum.xentax.com/viewtopic.php?f=16&t=5394)

> Reply from Panzah
>
> Mysterious Figure's weapons are FX based, just like Xemnas' etheral blades. Basicly, there is no model file for them, they are just FX effects.

Like I said or textures, but I don't think anyone has found them.
## Post #356
- Username: Panzah
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Jul 22, 2010 5:11 am
- Post datetime: 2010-12-01T03:35:51+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

If anything, I'd say they are in BBS2. There's so many files there though I just CBA to even check, since almost everything there is map props.
## Post #357
- Username: Soraoscuro
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Oct 01, 2010 2:31 am
- Post datetime: 2010-12-02T07:34:08+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Zerox
>
> Well I found the previous versions of Aqua's model. They were both in BBS3.dat. I also found a unfinished Bruiser unversed that has a texture without any real shading on it in BBS3.dat as well. Both in the japanese version.

I was able to find the "No Name" Keyblade in the English version of BBS's .dat files. But I can't seem to find any of his weapons. Has anyone had any luck finding them even just the textures for them?

All keyblades are in BBS1.dat. Their name is something like wXXyy00, XX being the number of the weapon, 01, 02, (...) and yy being the name of the character who weilds it "te=Terra, ve=Ventus, aq=Aqua". Example: w01ve00 = Ven's starting keyblade.
## Post #358
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-12-09T04:02:04+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Is there a way to make a special pmo extractor for bbs2.dat? One that doesn't clump up some of the files into big files containing several PMOs, TIM2s, and other files? Or even one that doesn't break up the geometry? Or even an extractor for some of the non-pmf non-pmo non-at3 files? Not to be a bother, but I'm just asking if anyone has made new developments for this game's files. If not, does anyone know which files represent Castle Oblivion? Also, is there a BCD file viewer?
## Post #359
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-12-16T00:51:49+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

No one's posted in this topic in a week, so I might gain some insight by posting again.
How do I view bcd files? And also, in which BBS2 ARC is the Castle Oblivion geometry located?
## Post #360
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-12-17T02:11:16+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Since no one else has been posting on the topic, I would like to point out that Falo said he'd release a new version of the converter two months ago and hasn't posted on XeNTaX since.
## Post #361
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-12-17T16:27:58+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

The only viewable levels are Ven's awakenings. Nobody has replied to your questions because nobody knows which ones could be castle oblivion.
## Post #362
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-12-18T01:59:33+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Then is there a way to extract W_EX010_TR.mdlx or any map file from KH2FM+?
## Post #363
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-12-24T06:01:42+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Does anyone know how to use PAM animation files, or extract the Lub files, from the game?
## Post #364
- Username: adventgamer
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Dec 22, 2010 5:36 am
- Post datetime: 2010-12-26T00:39:37+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Please could someone upload the 3d models of
Aqua's armour
Ven's armour
Vanitas' armour

from birth by sleep any 3d model type which blender can import i can use
please as i need these for some cosplays i am making for a convention
the higher the polycount the better
## Post #365
- Username: adventgamer
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Dec 22, 2010 5:36 am
- Post datetime: 2010-12-26T00:46:34+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Mirrorman95
>
> Then is there a way to extract W_EX010_TR.mdlx or any map file from KH2FM+?

The 'W_EX' files are the weapons files not the map files
and i can extract models from KH2FM+ as well as KHFM and i'm working on RE:COM but i just can do BBS which is why i need help
## Post #366
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-12-26T03:37:25+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I know W_EX010_TR.mdlx isn't a world model. Does anyone have a copy?
## Post #367
- Username: adventgamer
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Dec 22, 2010 5:36 am
- Post datetime: 2010-12-26T04:19:43+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Mirrorman95
>
> I know W_EX010_TR.mdlx isn't a world model. Does anyone have a copy?
i have all the W_EX files and there isn't a 'W_EX_010_TR' if you tell me what weapon it is i can give you a copy of the 3d model in both the mdlx and any 3d file that blender can import/export including .dae,.3ds,.obj etc
## Post #368
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-12-26T19:53:28+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Just to put this out there, there are LuaQ files all throughout the game, not just in lub files. I don't know how to open or use files with the Lua51 header, nor do I know their function, but I bet someone who works with such files could tell me.

Adventgamer, there is obj/W_EX010.mdlx , which is the Kingdom Key. There is also obj/W_EX010_20.mdlx , which is the Oblivion. But for each one of those, there is a duplicate keyblade slightly modified for a few of the worlds, like NM for Nightmare and TR for Tron. If you look in Falo's new nametable for Kingdom Hearts II, which I believe is included in his KH1/KH2 dumper tools, there is a entry with the filepath of obj/W_EX010_20.mdlx , which is the Space Paranoids version of the Oblivion Keyblade. I cannot find that file, but I know it is in there, because W_EX010_20 is in the game's code, and because Sora can wield a Tron-styled version of the Oblivion Keyblade in Kingdom Hearts 2. I want that MDLX file, or at least its texture, or even a textured DAE. Do you or anyone else know how to accomplish this?
## Post #369
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-12-31T17:53:01+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I think I have found the model. It is still compressed, but it is there. It is at [http://www.brickshelf.com/gallery/mirro ... essed.mdlx](http://www.brickshelf.com/gallery/mirrorman95/Zatth/w_ex010_20_tr_compressed.mdlx) .
## Post #370
- Username: NecessAndAry
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Dec 28, 2010 9:51 am
- Post datetime: 2011-01-10T02:28:16+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

DELETED
## Post #371
- Username: iceywind
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Oct 27, 2010 10:05 am
- Post datetime: 2011-01-12T04:16:53+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Could someone possibly post a file/s with all the pmo's? I've been trying for the past few hours just to get a bbs.iso or the .DAT files without any luck.
## Post #372
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-01-14T15:39:26+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from iceywind
>
> Could someone possibly post a file/s with all the pmo's? I've been trying for the past few hours just to get a bbs.iso or the .DAT files without any luck.

Technically speaking, that's illegal. You are stating that you are trying to obtain a digital copy of the game, and without proof of purchase, you are violating copyright protection laws. That is why it would be illegal to distribute or link to any source of information regarding the location of copies of the game or its main files to download. If you don't own the game, you don't have the right to view or extract the files within it. The fact that we're making programs to extract and view the models in and of itself is barely legal. So if you want to download illegally obtained files, don't ask here please.
## Post #373
- Username: Nexus Elite ns
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2009 1:11 am
- Post datetime: 2011-01-14T19:04:00+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I'm curious, how do you extract out the DAT files from that psp game?
## Post #374
- Username: iceywind
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Oct 27, 2010 10:05 am
- Post datetime: 2011-01-15T20:34:53+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Mirrorman95
>
> iceywind wrote:Could someone possibly post a file/s with all the pmo's? I've been trying for the past few hours just to get a bbs.iso or the .DAT files without any luck.

Technically speaking, that's illegal. You are stating that you are trying to obtain a digital copy of the game, and without proof of purchase, you are violating copyright protection laws. That is why it would be illegal to distribute or link to any source of information regarding the location of copies of the game or its main files to download. If you don't own the game, you don't have the right to view or extract the files within it. The fact that we're making programs to extract and view the models in and of itself is barely legal. So if you want to download illegally obtained files, don't ask here please.

Sorry, I didn't clarify. I do own the game. I just didn't know how you all were getting the dat files and pmo's from it. I did finally extract the dat files now I need to extract the pmo's. Is this where a hex editor comes in?
## Post #375
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-01-17T19:53:08+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from iceywind
>
> Mirrorman95 wrote:iceywind wrote:Could someone possibly post a file/s with all the pmo's? I've been trying for the past few hours just to get a bbs.iso or the .DAT files without any luck.

Technically speaking, that's illegal. You are stating that you are trying to obtain a digital copy of the game, and without proof of purchase, you are violating copyright protection laws. That is why it would be illegal to distribute or link to any source of information regarding the location of copies of the game or its main files to download. If you don't own the game, you don't have the right to view or extract the files within it. The fact that we're making programs to extract and view the models in and of itself is barely legal. So if you want to download illegally obtained files, don't ask here please.

Sorry, I didn't clarify. I do own the game. I just didn't know how you all were getting the dat files and pmo's from it. I did finally extract the dat files now I need to extract the pmo's. Is this where a hex editor comes in?

Unless you have custom firmware, only the BBS0.dat will be able to be extracted from. Download QuickBMS in order to run this BMS script, which is the latest PMO BMS script but with the file-naming system of the previous script, which will extract the PMOs into a series of folders based on the PMO's first identified texture, which is generally named based on the PMO's model type and world abbreviation, except for the ones with no textures, each of which are low-poly versions of the previously numbered textured PMO.
Next, download Noesis from oasis.xentax.com and the Kingdom Hearts plugins in order to view the models. Note that you must extract the Kingdom Hearts dlls to Noesis's plugins folder, and on some computers Noesis doesn't even recognize the plugins. After viewing the model, you can export it to another format, but you have to select UV flip to import/view it on other programs correctly, and you must also modify the exported files with either a hex editor or Notepad in order for it to find the textures. If you export to OBJ, which does not retain bone information, you must make an MTL file in the same folder that points each material## to the appropriate texture file, and replace the word ./rdmexport.mtl with that MTL's name.
If you do have custom firmware, you can try to decrypt the BBS1-3.dats as well, by downloading JPCSP, using JPCSP Connector, decrypting the eboot with ISO Tool and replacing it in the ISO with UMDGen, running the ISO on jpcsp, connecting JPCSP to your custom firmware PSP with JPCSP Connector installed, and after your PSP decrypts the dats, they will each appear as tmp\ULUS10505\umd\File-######\PGDfile.raw.decrypted in your JPCSP folder, after which you can extract the PMOs from them as you could with BBS0.dat. I don't have custom firmware on my PSP, so I haven't tried this, but you could decrypt the files this way.
[extract_pmo_vB.zip](https://xentaxbackup.github.io/file/3812_extract_pmo_vB.zip)
## Post #376
- Username: extreamlycasual
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 18, 2011 8:29 am
- Post datetime: 2011-01-18T00:54:40+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

hello all. this is the first time i've posted on here.  i have a couple questions about chrissquarefan's fbx exporter thing.  first, where can i find it. i've seen lots of reference to it but i haven't actually found it....  second, what can it do? does it just convert the mdls files to fbx? does it keep the animations? PLEASE say it keeps the animations! if it keeps the animations with the fbx files, then i could import the files directly into unity3d. .... or some one who's much better at game makeing could.....

so, what exactly does it do? does it just convert the models to a new file type, or does it keep the animations with it?
## Post #377
- Username: iceywind
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Oct 27, 2010 10:05 am
- Post datetime: 2011-01-18T01:47:43+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Mirrorman95
>
> Unless you have custom firmware, only the BBS0.dat will be able to be extracted from. Download QuickBMS in order to run this BMS script, which is the latest PMO BMS script but with the file-naming system of the previous script, which will extract the PMOs into a series of folders based on the PMO's first identified texture, which is generally named based on the PMO's model type and world abbreviation, except for the ones with no textures, each of which are low-poly versions of the previously numbered textured PMO.

Thanks. I already have Noesis and the KH plugin and I know that works ( i looked at Cinderella's Carrage that was posted in the beginning of this thread). QuickBMS is what I need then. That's just what I needed to know
## Post #378
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-01-20T18:32:34+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

BBSFM has many, many more models.

New one's I've found:

BBS0.DAT

Advert for KH3D
KH1 Sora 698.pmo
KH1 Riku 710.pmo
KH1 Kairi 723.pmo
Ansem, Seeker of Darkness 759.pmo
Xemnas 761.pmo

My list on the first post does not work with this, they don't match.

EDIT: Models are only in BBS0.dat now, that's probably why there's so many more.
## Post #379
- Username: siro1987
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jun 13, 2010 7:02 am
- Post datetime: 2011-01-21T01:57:11+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from ultimaespio
>
> BBSFM has many, many more models.

EDIT: Models are only in BBS0.dat now, that's probably why there's so many more.

BBS0.dat only? Could you find any enemies model from there?
## Post #380
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2011-01-21T08:37:38+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

BBS1 -3.dat are encrypted again, so the dnas decrypter has to be modified again too. I never really unterstood, how Falo got the decrypt key, but maybe someone here has.

> Reply from Falo
>
> BBS1 - 3.dat uses the PGD encryption, you need the decrypt keys to decrypt them,
you can get these keys with JPCSP or from an decrypted EBOOT.BIN and then modify
dnas decrypter to work with NA/EU, (this works also with hbl if you don't have a CFW PSP).
## Post #381
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-01-22T06:52:00+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from extreamlycasual
>
> hello all. this is the first time i've posted on here.  i have a couple questions about chrissquarefan's fbx exporter thing.

It was never finished so don't worry about it. End of story.

> Reply from siro1987
>
> ultimaespio wrote:BBSFM has many, many more models.

EDIT: Models are only in BBS0.dat now, that's probably why there's so many more.

BBS0.dat only? Could you find any enemies model from there?

There are only a few boss models in BBS0.dat, and the unversed are pretty much non-existant,there's still models in the other .dat files we just have to figure out how to decrpyt them. Neither the Armor of the Master or No Heart are in BBS0.dat and they're the new stuff that don't quite have anything the same to obtain elsewhere.

Edit: Okay dnas decrpytor can be found here: [http://gbatemp.net/t227842-the-prometheus-method?&st=0](http://gbatemp.net/t227842-the-prometheus-method?&st=0)

I tried running this unchanged on my 6.35 Pro Hen and while it runs just fine it isn't capable of decrypting the Final Mix BBS#.dat files.

Hopefully someone can figure more out.
## Post #382
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-01-22T08:58:16+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Zerox
>
> extreamlycasual wrote:hello all. this is the first time i've posted on here.  i have a couple questions about chrissquarefan's fbx exporter thing.

It was never finished so don't worry about it. End of story.
siro1987 wrote:ultimaespio wrote:BBSFM has many, many more models.

EDIT: Models are only in BBS0.dat now, that's probably why there's so many more.

BBS0.dat only? Could you find any enemies model from there?

There are only a few boss models in BBS0.dat, and the unversed are pretty much non-existant,there's still models in the other .dat files we just have to figure out how to decrpyt them. Neither the Armor of the Master or No Heart are in BBS0.dat and they're the new stuff that don't quite have anything the same to obtain elsewhere.

Edit: Okay dnas decrpytor can be found here: http://gbatemp.net/t227842-the-prometheus-method?&st=0

I tried running this unchanged on my 6.35 Pro Hen and while it runs just fine it isn't capable of decrypting the Final Mix BBS#.dat files.

Hopefully someone can figure more out.

Did you try trying to run it on JPCSP with JPCSP connector?
## Post #383
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2011-01-22T10:39:22+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

That won't work either I think. The key in the dnas decryptor has to be changed to the one in the Eboot.bin of the Final Mix. Falo posted a dna decryptor [here](http://www.mediafire.com/download.php?1l5wq1ugy2tmrdd), where only some byts are changed but it works perfectly fine on the European version.

So I'm wondering to things:
#How to get the decrypt key with JPCSP or from an decrypted EBOOT.BIN.
#How to modify the dnas decrypter to put the key inside. I think we need an uncompiled version of it to do so.
## Post #384
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-01-22T16:05:51+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Azurfan
>
> That won't work either I think. The key in the dnas decryptor has to be changed to the one in the Eboot.bin of the Final Mix. Falo posted a dna decryptor here, where only some byts are changed but it works perfectly fine on the European version.

So I'm wondering to things:
#How to get the decrypt key with JPCSP or from an decrypted EBOOT.BIN.
#How to modify the dnas decrypter to put the key inside. I think we need an uncompiled version of it to do so.

No, dnas decryptor isn't needed as long as you decrypt the eboot. If you decrypt the eboot, JPCSP will recognize the game and start the decryption process, which will be handled on a real PSP. People have decrypted the USA version in this method at EmuNewz; it's the only way JPCSP can play Birth By Sleep.
## Post #385
- Username: philip92dk
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Jul 26, 2010 3:52 am
- Post datetime: 2011-01-22T22:26:05+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

is there a 3d model of xion in Final Mix  ?
## Post #386
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-01-22T22:27:16+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Not in BBS0.dat. Maybe in the others but we can't check at the moment.
## Post #387
- Username: philip92dk
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Jul 26, 2010 3:52 am
- Post datetime: 2011-01-22T22:30:48+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

why not?
## Post #388
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-01-22T22:37:46+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from philip92dk
>
> why not?

Because no one has decrypted the other three DAT files yet. If we could modify DnaS Decrypter, or just utilize JPCSP on a CFW PSP, we could probably do this, but I'm reluctant to void the warranty on my PSP with custom firmware, so we'll just have to wait.
## Post #389
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-01-23T01:14:19+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Wasn't Reconnect Secret Ending Video only in the American release? Perhaps if that is the case then maybe BBS1-4.dat on the American game actually did have Xion and other models and maybe it really wasn't pre-rendered. So we never got into those files so maybe those models were there.

I know that in Final Mix there's the new secret video for Kingdom Hearts BBS Volume 2, and it has flashes of Sora, Kairi, Riku, Xemnas, and Ansem. All of their models are in FM's BBS0.dat. But the majority of the unversed as well as No Heart and Armor of the Master aren't in BBS0.dat so there has to be other models in the rest of the .dat files. So it's quite possible that if we figure out how to decrypt these files efficiently we may be able to find models of Xion and others as well.

I found this on emunewz that talks about how to decrypt the American version of the game, I have to use the google cached version to view it as it appears the real site is down. Maybe someone can make heads or tails of it. [Click here to go to emunewz.net](http://webcache.googleusercontent.com/search?q=cache:DSCiu04zrecJ:www.emunewz.net/forum/archive/index.php/thread-2214.html+JPCSP+decrypt+BBS&cd=5&hl=en&ct=clnk&gl=us)

Here's another link about decrypting BBS#.dat files on a previous version: [http://forums.psp-hacks.com/f119/kingdo ... a-t260150/](http://forums.psp-hacks.com/f119/kingdom-hearts-birth-by-sleep-crack-tutorial-beta-t260150/)
## Post #390
- Username: philip92dk
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Jul 26, 2010 3:52 am
- Post datetime: 2011-01-23T01:23:59+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I am 80% sure that xion model is in fm because Ansem Seeker of Darkness and Xemnas was in the secret episode movie am i 100% sure if guys finds Riku blindfolded   (if she not in the game i will collect a Suicide Squad and infiltrat Square Enix  )
## Post #391
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-01-23T03:10:01+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

For those who said that the other BBS#.dat didn't contain any models, they were sure wrong there. I just dumped 22,660 pmo files from BBS2.dat alone.

I found some BBS tools and amazingly I found a dnas decryptor that works on final mixes .dat files! And now I can dump tons of pmos. I only have a 1GB memory stick at the moment (waiting for my 8GB to arrive from Hong Kong) so I'm having to do each BBS#.dat file individually I'll let you know the results soon.

I've attached the version of Dnas Decrpytor I used to accomplish this feat. Instructions are in the readme contained in the .zip.

It should be noted you don't need Custom Firmware to use it. I did this with 6.35 HEN Pro which now has a version released that works on Original Firmware.
[bbs_dnas_decryptor.zip](https://xentaxbackup.github.io/file/3833_bbs_dnas_decryptor.zip)
## Post #392
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-01-23T03:32:15+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I'm going to try this IMMEDIATELY. But I thought Hen WAS custom firmware. If I download it to my PSP-1000, will it void my warranty? Do I need to update to 6.35 before I can use it?
## Post #393
- Username: sonia
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jan 19, 2011 1:24 pm
- Post datetime: 2011-01-23T03:44:56+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

im gonna try this soon nice info zerox
## Post #394
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-01-23T03:58:23+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

HEN = Home Brew Enabler, it's like CFW only with half the power. And the best part is that after you tun off (not standby) your psp it reverts to normal firmware. It will not void your warranty as it leaves no trace. There's versions for many firmwares just look for the firmware that maches yours.


So status update: BBS1.dat hasn't yielding anything of interest that is new. It's a load of characters that we have already but there may be stuff in with them, I've only skimmed.

BBS2.dat is almost all level geometry, some are textured but most aren't. There's a few character models here.

BBS3.dat seems to contain many new character models such as No Heart and Armor of the Master.
## Post #395
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-01-23T04:02:35+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Zerox
>
> HEN = Home Brew Enabler, it's like CFW only with half the power. And the best part is that after you tun off (not standby) your psp it reverts to normal firmware. It will not void your warranty as it leaves no trace. There's versions for many firmwares just look for the firmware that maches yours.


So status update: BBS1.dat hasn't yielding anything of interest that is new. It's a load of characters that we have already but there may be stuff in with them, I've only skimmed.

BBS2.dat is almost all level geometry, some are textured but most aren't. There's a few character models here.

BBS3.dat seems to contain many new character models such as No Heart and Armor of the Master.

I have 6.20 OFW. Do I need to update to 6.35 before I can decrypt the DATs or can I use 6.20 Hen Pro to decrypt the Final Mix DATs?

EDIT: Turns out it worked! My HBL 6.20 PSP-1000 decrypted the files perfectly wthout HEN!
## Post #396
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-01-23T04:03:56+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

In theory 6.20HEN should work.
## Post #397
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-01-23T04:20:15+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I found Twilight Thorn in BBS3.DAT.
## Post #398
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-01-23T05:38:42+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Yeah I saw him. There's also the old 512x512 Alpha Aqua model with the darkened colors (got into this even after being remade twice   ) and an even EARLIER model that has textures that aren't even complete and the UV map isn't fully done. Really gives you a good idea what a WIP model of Squeenix modeler's looks like.

There's also this heartless:



All of that is in BBS3.dat and to my dismay there isn't a Xion model in there. I'm working on BSS1.dat now.
## Post #399
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-01-23T06:21:09+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Hey. I wanted to say how happy I am that plenty of people are still interested in KH game research. I was also ecstatic to see someone whose name starts with 'y' still active in game research. And I died when I read that he had worked out KH2 animations. 

I've been out of the loop for a few years and I just found Noesis and Falo's new dumper. So now I have shiny new things to play with. Although I will always have a fascination for mdlx models. I think I would have a stroke if someone came out with a viewer that supported highpoly cutscene animation for KH2 models. I also nearly died when I saw someone had made progress with viewing maps from BBS... just amazing! 

I'm wish I could contribute more, but I'm useless with reverse engineering, hex editing, programming... All I can do is decent rigging in 3dsmax. Sometime, I'd like to try my hand at facial rigging. Using bones, not morph targets. 

So yeah, great to see KH related model/map research is still alive and well! I wish I could contribute and help out more... but sadly it's not my area of expertise.  Anyway, great progress on everything, guys!
## Post #400
- Username: Krisan Thyme
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Jan 15, 2011 4:04 am
- Post datetime: 2011-01-23T09:07:33+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from SoftIce
>
> I've been out of the loop for a few years and I just found Noesis and Falo's new dumper. So now I have shiny new things to play with. Although I will always have a fascination for mdlx models. I think I would have a stroke if someone came out with a viewer that supported highpoly cutscene animation for KH2 models.
I'm pretty sure I could die happily if I had my hands on a means of properly extracting KH2's MDLX models, skeletons intact. This stuff with BBS is quite awesome to be sure, but I'd adore seeing a Noesis plugin for KH2, or just some proper tools for model\skeletal extraction.
## Post #401
- Username: Trishty
- Rank: advanced
- Number of posts: 63
- Joined date: Mon Jul 05, 2010 9:37 pm
- Post datetime: 2011-01-23T09:32:20+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I search all BBS1 BBS2 BBS3, but not found Xion. May be she in BBS4 T_T!
How to decrypt BBS4?
## Post #402
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-01-23T09:33:35+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Krisan Thyme
>
> SoftIce wrote:I've been out of the loop for a few years and I just found Noesis and Falo's new dumper. So now I have shiny new things to play with. Although I will always have a fascination for mdlx models. I think I would have a stroke if someone came out with a viewer that supported highpoly cutscene animation for KH2 models.
I'm pretty sure I could die happily if I had my hands on a means of properly extracting KH2's MDLX models, skeletons intact. This stuff with BBS is quite awesome to be sure, but I'd adore seeing a Noesis plugin for KH2, or just some proper tools for model\skeletal extraction.

Revelation's working on that, but his computer's been down for a while, so when he can he'll release a Noesis binary.
## Post #403
- Username: Krisan Thyme
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Jan 15, 2011 4:04 am
- Post datetime: 2011-01-23T10:19:03+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Mirrorman95
>
> Revelation's working on that, but his computer's been down for a while, so when he can he'll release a Noesis binary.
That's really a shame to hear about his computer.. What happened exactly, do you know? Certainly awesome news to hear he's planning a release for that though.. I had no idea it was even in the works.
## Post #404
- Username: siro1987
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jun 13, 2010 7:02 am
- Post datetime: 2011-01-23T10:57:32+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I even tried to use a PSP emulator on PC to run PBP files in dnas_decryptor, but still failed to export anything...
## Post #405
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2011-01-23T12:00:10+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Thanks for your great find Zerox, all is working smoothly now.

> Reply from Trishty
>
> I search all BBS1 BBS2 BBS3, but not found Xion. May be she in BBS4 T_T!
How to decrypt BBS4?
BBS4 isn't encrypted, there are mostly the movies in there and not much more.
## Post #406
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-01-23T14:25:32+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Trishty
>
> I search all BBS1 BBS2 BBS3, but not found Xion. May be she in BBS4 T_T!
How to decrypt BBS4?

I fear I've had the same luck and haven't found her.

I've started looking in the NA dat files now.
## Post #407
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-01-23T15:49:55+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Krisan Thyme
>
> Mirrorman95 wrote:Revelation's working on that, but his computer's been down for a while, so when he can he'll release a Noesis binary.
That's really a shame to hear about his computer.. What happened exactly, do you know? Certainly awesome news to hear he's planning a release for that though.. I had no idea it was even in the works.

He had power issues and he needs to re-setup his computer in order to get it to work again.
## Post #408
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2011-01-24T02:49:16+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

One question though that,when i use the bbs_dnas_decryptor it changes the output file to .dat,so do i have to use an hex editor to rip the files or just use that old quick bms script made for the jap version?
## Post #409
- Username: Krisan Thyme
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Jan 15, 2011 4:04 am
- Post datetime: 2011-01-24T02:50:28+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Mirrorman95
>
> Krisan Thyme wrote:Mirrorman95 wrote:Revelation's working on that, but his computer's been down for a while, so when he can he'll release a Noesis binary.
That's really a shame to hear about his computer.. What happened exactly, do you know? Certainly awesome news to hear he's planning a release for that though.. I had no idea it was even in the works.

He had power issues and he needs to re-setup his computer in order to get it to work again.
Ugh, I hope it wasn't anything like what I dealt with a few years back.. Well, best of wishes to the man. I hope he gets it sorted out without too much trouble or cost to him.
## Post #410
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-01-24T04:07:52+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Aurangzeb56
>
> One question though that,when i use the bbs_dnas_decryptor it changes the output file to .dat,so do i have to use an hex editor to rip the files or just use that old quick bms script made for the jap version?

The PMO extractor is universal; it will extract all the PMOs from any decrypted game. I modified the existing two scripts and posted it a page or two ago to output the files in folders like the first script but not black out when extracting geometry files like the second script.
## Post #411
- Username: Trishty
- Rank: advanced
- Number of posts: 63
- Joined date: Mon Jul 05, 2010 9:37 pm
- Post datetime: 2011-01-25T03:20:47+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I extracted all of the PMO in the U.S. version and not find Xion always T_T! Maybe she just in FMV "Hidden truths" (PMF in BBS4.dat) without model.
## Post #412
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-01-25T03:42:24+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Trishty
>
> I extracted all of the PMO in the U.S. version and not find Xion always T_T! Maybe she just in FMV "Hidden truths" (PMF in BBS4.dat) without model.

I think the extra models were only there in the first place because of KH3D, which has shown Sora, Riku, Kairi, Ansem, Xemnas, and Twilight Thorn in current trailers, but not Xion, who is not. Just so you know, the largest character PMO in BBS0.dat is now Ansem, and the third biggest PMO in BBS0.dat is the KH3D Demo logo. Makes you wonder why they used so much space in the game for extra models when they weren't even used in the game.
## Post #413
- Username: Panzah
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Jul 22, 2010 5:11 am
- Post datetime: 2011-01-25T04:42:49+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Square has never been clean with their games, FF7 Crisis Core Aerith and Tonberry models can be found in Dissidia...
## Post #414
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-01-25T15:24:43+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

We need BBS map files sorted out. Someone posted pictures of the Land of Departure a while back, can't remember who it was though.

It would be nice to see if there are any unused maps.
## Post #415
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-01-25T15:30:39+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from ultimaespio
>
> We need BBS map files sorted out. Someone posted pictures of the Land of Departure a while back, can't remember who it was though.

It would be nice to see if there are any unused maps.

Falo was the only one who ever made a completed BBS map, and it had no textures. I don't see how they'd be any use to use if we can't reconstruct them again.
## Post #416
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-01-25T15:44:11+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

On Page 14 Revelation had a chunk of the Land of Departure.

I'm sure I remember someone posting a picture of a full map of LoD...
## Post #417
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-01-25T16:25:54+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Revelation's LoD picture was of a dumpable pmo model, nothing like a. Complete map. I've seen it many times in the dumpable models in each version. It's nothing to get excited about.

Falo is the only one to get close even. And that doesn't do much for you as he isn't around again.

The only thing I can think of is that there is some other file type that has different pmos inside it that it places them where they go inside the map. This map container file could contain our texture files that correspond with our untextured map chunks.
## Post #418
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-01-25T16:49:45+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

The maps could be pmo, but just a different type of pmo. Similar to Crisis Core.
## Post #419
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-01-25T22:34:43+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from ultimaespio
>
> The maps could be pmo, but just a different type of pmo. Similar to Crisis Core.

The BCD maps aren't pmos. They're a bunch of PMOs. Almost every ARC file in BBS2.dat contains a single BCD file that makes up an area of a world. All the broken geometry found by extracting all of BBS2.dat's PMOs are the bits and pieces of those files. The textures of the BCD files are of a different format altogether and were beyond Falo's reach, so when he posted the dc_05 room model early on in this topic, he could only make the mesh. I found a PMO that looked like an open doughnut, but by closer inspection it was merely the larger of the three circles that make up Mickey's head at the entrance to the raceway which Falo reconstructed. Since Falo could construct at least one BCD, the main problem will be to find out how to convert those internal textures, and then we can have at least one complete BCD model.
## Post #420
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-01-25T23:01:02+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

The contents of this post was deleted because of possible forum rules violation.
## Post #421
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-01-26T20:37:52+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

If you use the arc extractor that Falo posted to get the arc files, then use the pmo extractor, you can get chunks of the maps. You will get a few pmo files, but if you convert them you can piece them together in your modelling software.

The textures are TM2 and you have to use Jaeder Naub to get them.

There are Definitely parts missing.
## Post #422
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-01-26T20:57:43+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Wow. The tree house and part of the stairs from destiny islands. That's awesome!

I wish I could help with developing more dumper tools or with file formats but I know nothing about programming/hex editing/reverse engineering. Sorry I can't help anyone.  

I wanted to say thanks to Chris for his KH mdls exporter. Edit: I've also figured out the issue's i've had with it. All's good. 
The bind pose is still imploded, but unchecking and rechecking 'always deform' in max's skin modifier fixes it. 
Chris, you are beyond awesome for making that little program to convert mdls.
## Post #423
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2011-02-25T21:15:44+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Thank you! It's as little as the time I had for it XD. Minna-san, sorry for the disappointment...
Anyway, recently I've been playing with Dissidia 012 Prologus models and rediscovered my passion for 3D once again . 
->DeviantArt [http://xdeviantchris.deviantart.com/#/d382va1](http://xdeviantchris.deviantart.com/#/d382va1)
I would love to bring my exporter back from the dead with support for BBS :>
Only one question, I know it's silly, but  where can I find a model dumper? XD
## Post #424
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2011-02-25T22:34:55+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I don't think there's a dumper for BBS/358-2 days yet!
## Post #425
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-02-26T00:47:53+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Devilot
>
> I don't think there's a dumper for BBS/358-2 days yet!

There are PMO, TM2, and AT3 extractors for Birth by Sleep, which all work, and ReCoded and 358/2, which happen to use the same game engine, have DSLazy, DSDecmp, and NinUnpack to extract and unpack its files, and LowLines' Console Tool 2.0 to view them. The only qualm is that the BBS pam and 358/2 BCA0 animation files have yet to be cracked.
## Post #426
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2011-02-26T07:32:29+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

can you provide links for ChrisSquareFan?
## Post #427
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-02-27T00:12:37+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from ChrisSqureFan
>
> Thank you! It's as little as the time I had for it XD. Minna-san, sorry for the disappointment...

No thank you!   That mdls to fbx exporter made my day. Animating rigged models is much fun.   

Okay, here's some links for anyone who missed them.
Falo's pmo bms script and Revelation's modified version:
Falo's first version is on page 1.
Revelation's modified version is on page 19.
Falo's other version is on page 25.

Other Stuff that pertains to BBS models:
Falo's arc extractor bms script is on page 2.
Zerox posted a BBS decryptor on page 27.

Noesis now has two plugins written by Revelation that support BBS (pmo) and KH (mdls) formats. 
[http://oasis.xentax.com/index.php?content=home](http://oasis.xentax.com/index.php?content=home)

I'm in the process of reconstructing the destiny island level pmo files back into one large file. None of them are textured, but I think the uv coordinates are preserved (thank you G-D!) 

You can dump tim2 files off of the decrypted bbs2.dat with Jaeder Naub [http://www.jaedernaub.com](http://www.jaedernaub.com). The only problem is that it doesn't keep their texture names, so there's no way to know what texture goes to what unless you go through them all (at least, that's how it is for me.)   

And because there's no way I can sort through 5,000+ files, I think I'm going to see if I can just use 3dripper and pcsx2 and rip dds versions of the textures I want.
## Post #428
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-02-27T02:00:17+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

The textures are there, you just can't find them as easy. You're more likely to find them in the game than to map different textures onto models from another game. Besides, that entire place--both the small and large island--is already fully exportable to Blender via kkdf2's KH2map program. Really, the only reason one would go about doing it that way is if you just want to have the PSP version of Destiny Islands and are willing to go about the work of remapping the textures in order to get them, which, if you are, is a perfectly reasonable endeavor, but just realize it will take up a whole lot of time.
## Post #429
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-02-27T06:05:31+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Mirrorman95
>
> The textures are there, you just can't find them as easy. You're more likely to find them in the game than to map different textures onto models from another game. Besides, that entire place--both the small and large island--is already fully exportable to Blender via kkdf2's KH2map program. Really, the only reason one would go about doing it that way is if you just want to have the PSP version of Destiny Islands and are willing to go about the work of remapping the textures in order to get them, which, if you are, is a perfectly reasonable endeavor, but just realize it will take up a whole lot of time.

Oh yeah, I exported the kh2 cutscene version so I could fool around with it and try to render it or something in max. The little island lost a lot of 3d detail though, which the psp version still has. Looking at the UV cords of the little island though, they look the same as the psp island. I might try and see what happens if I put the kh2 little island textures on the psp one, although I think the resolution is lower. If the kh2 cutscene version had the same or pretty similar detail as the psp one, I'd have just stuck with that. I can see why it wouldn't though, it would probably have taken up a ton of memory that was useless, since the cutscene shows it so far away. No one was ever meant to look at the little island up close like I was doing.   

I'm not at the point where I'd redo uvs for the whole island, but if they're already intact and all I need is to get the textures... the temptation is too great.
## Post #430
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2011-02-27T10:03:14+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Thank you SoftIce for the links.
## Post #431
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-02-27T22:05:57+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Just so you know, if you unpack Re:coded, W01 11 is the destiny islands model, W01 12 is the destiny islands textures, and 13 is the bridge. I got it to work on the first Console Tool Demo 2 after finding the btx0, because the one that views the characters correctly didn't texture map correctly and can't be 3D Via'd. It looks almost perfect when I view it in the Tool, but 3D Via does not preserve textures correctly when it captures a model. I have the 3D Via model, in convertible DAE format, at [http://www.3dvia.com/models/96A7F18C9EB08294/](http://www.3dvia.com/models/96A7F18C9EB08294/) .
## Post #432
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-02-28T22:08:00+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from ChrisSquareFan
>
>  Thank you SoftIce for the links.

Sure, no problem! After all you've contributed, I'm glad I was able to actually assist you even a tiny bit with something, even it was just finding links to save you the time.   I don't know anything about programming, so I can't actually contribute anything of value or progress here, which I feel bad about.   It is pretty interesting to read through the thread from page 1 and see the evolution of reverse engineering a file format (if that's what this was called.)

If you and the other authors are okay with it, (Falo and Revelation and anyone else I forgot - sorry), I could put all of the bms scripts, and other tools that they have contributed into one zip and upload that to mediafire so everyone has single source for the progress made so far in this thread. I could put the author's name in front of the regular file name on the scripts and files, so people know who contributed what and also for crediting.  If you were okay with it, I could include your mdls fbx exporter tool as well (with your name added in front so people know who made it.) I don't know if you'd want your drop box included though, you'd probably want that left out and just for people that stumble upon the post you made in the thread. 

That was just a thought that I had. Or, maybe when he has time, Mr Mouse could add the tools too the 'tools' section of the website, if all the authors are all okay with it. 

I didn't do anything like that though, since I don't have permission from Falo or Revelation or any of the other programmers that contributed tools in this thread, so I just listed the pages their posts were found on. 

> Reply from Mirrorman95
>
> Just so you know, if you unpack Re:coded, W01 11 is the destiny islands model, W01 12 is the destiny islands textures, and 13 is the bridge. I got it to work on the first Console Tool Demo 2 after finding the btx0, because the one that views the characters correctly didn't texture map correctly and can't be 3D Via'd. It looks almost perfect when I view it in the Tool, but 3D Via does not preserve textures correctly when it captures a model. I have the 3D Via model, in convertible DAE format, at http://www.3dvia.com/models/96A7F18C9EB08294/ .

Oh, thanks so much for the info! I forgot all about Re:coded. Whoops. Isn't that the game that was written for cell phone platforms? Thanks so much for uploading the model and textures too!! You're too nice! I had just gone to the trouble of starting up pcsx2 and 3dripper to grab some textures, but this way is much easier. With pcsx2,  ZeroGS captures meshs with no depth data, and screwed up textures, but still, it retains material IDs, while Gsdx9 captures textures okay, but captures no meshes at all. I was going to use the pancake mesh as a mat id reference, along with the small island from the kh2 cutscene, but now things look a lot easier. 

I know about Console Tool Demo, is btx0 the first texture for the map model? Sorry, I hate bugging people with stupid questions.   

Thanks again!
## Post #433
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-02-28T22:43:31+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Coded was originally for Phones, yeah. But Square remade it for the DS a few months back.

Btw anyone got a link for this console tool?
## Post #434
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-03-01T04:57:39+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Console Tool is at [http://www.romhacking.net/forum/index.php?topic=8407.0](http://www.romhacking.net/forum/index.php?topic=8407.0)
After you extract all the files with DSLazy, NinUnpack, and DSDecmp, use the Console Tool to view mi/wd/W01_dump/12.BTX0 and then /11/11.BMD0 to see it correctly.
And propl.nl/random/ appears to have just made a new DSDecmp called DSDecmpGH. I wonder what was updated.

Anyway, I just used Keytotruth's latest patch to create an English iso of my Birth By Sleep Final Mix game, but I don't know how to play an iso on my PSP that isn't already on a UMD. How do I do this?
## Post #435
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-03-02T17:24:30+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Mirrorman95
>
> And Zerox appears to have just made a new DSDecmp called DSDecmpGH. I wonder what was updated.

Anyway, I just used Keytotruth's latest patch to create an English iso of my Birth By Sleep Final Mix game, but I don't know how to play an iso on my PSP that isn't already on a UMD. How do I do this?

I did wha?  I haven't touched DS roms or heck even a real DS system or game since December. So you obviously have some invalid information there.

As for playing your new english final mix game, check your pms as I'm not sure I'm allowed to post how to play isos here.
## Post #436
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-03-02T18:45:21+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Zerox
>
> Mirrorman95 wrote:And Zerox appears to have just made a new DSDecmp called DSDecmpGH. I wonder what was updated.

Anyway, I just used Keytotruth's latest patch to create an English iso of my Birth By Sleep Final Mix game, but I don't know how to play an iso on my PSP that isn't already on a UMD. How do I do this?

I did wha?  I haven't touched DS roms or heck even a real DS system or game since December. So you obviously have some invalid information there.

As for playing your new english final mix game, check your pms as I'm not sure I'm allowed to post how to play isos here.

You're right. I'm terribly sorry. I didn't mean to assume. Whoever came up with DSDecmp made an update at [http://www.propl.nl/random/](http://www.propl.nl/random/) .
## Post #437
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2011-03-04T22:54:10+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from SoftIce
>
> 
If you and the other authors are okay with it, (Falo and Revelation and anyone else I forgot - sorry), I could put all of the bms scripts, and other tools that they have contributed into one zip and upload that to mediafire so everyone has single source for the progress made so far in this thread. I could put the author's name in front of the regular file name on the scripts and files, so people know who contributed what and also for crediting.  If you were okay with it, I could include your mdls fbx exporter tool as well (with your name added in front so people know who made it.) I don't know if you'd want your drop box included though, you'd probably want that left out and just for people that stumble upon the post you made in the thread.

It's OK with me. I think you could put them on Xentax's 'tools' section too. 
Thanks for all the help!
## Post #438
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-03-05T17:42:22+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Half of the model viewing has come from Revelation's KH1, BBS, and soon-to-be KH2 plugins for Mr. Adult's Noesis. The other half, which involve model animation, comes from kkdf2's map & kh2 viewer & anb converter and yaz0r's KH1&2 tool. The file ripping has come mainly from Falo (did Revelation release one) and his PMO & TM2 & ARC & AT3 BBS extractors and updated versions of yaz0r's KH1&2Dump, not to mention yaz0r's updated KH2FM Dump, and kkdf2's file ripper. At some point I combined Falo and Revelation's extractors, or whoever redid the extractor, to extract all the files like the second ripper, but file name them like the first ripper.
## Post #439
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2011-03-06T12:17:32+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

wonder if it's possible to transfer the animations of the KH games to 3ds max! maybe with a Noesis plugin
## Post #440
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-03-06T20:26:45+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Devilot
>
> wonder if it's possible to transfer the animations of the KH games to 3ds max! maybe with a Noesis plugin

No, not unless someone like Revelation or yaz0r or Falo or kkdf2 made such a thing due to their unique line of expertise the mdls format. God knows I have absolutely no idea how these work; they're just like black boxes to me.
## Post #441
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2011-03-07T21:36:54+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

more than 3D Ripper does not work on Vista and does not allow animation ripping.
## Post #442
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-03-08T02:02:07+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Devilot
>
> more than 3D Ripper does not work on Vista and does not allow animation ripping.

Not true. I have a laptop running on Windows Vista and have used 3D Ripper DX may times to rip 3D models from ModelViewerDX D3D9 and kkdf2's mdlx viewer. But yes, it cannot rip animations.
## Post #443
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2011-03-09T09:06:45+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

how can it work on Vista if it stops at Directx 9?
## Post #444
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-03-09T16:43:19+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

You're confusing software with hardware. And although my Vista can hardly implement it, it's updated to DirectX 10. You can update DirectX as much as you want, it's only a matter if your graphics card can handle it. And my Vista laptop handles 3D Ripper DX with ModelViewerD3D9 just fine. ModelViewerD3D9 may not work for other reasons, though.
## Post #445
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-03-09T19:36:38+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Devilot, have you tried using Yaz0r's older modelviewer release? The new releases don't work with my computer, but the older one does.
## Post #446
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-03-10T14:49:47+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

You've got your KH2 plugin now. You may stop asking 

Animation plugins would be niiice
## Post #447
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-03-10T23:07:34+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from ultimaespio
>
> You've got your KH2 plugin now. You may stop asking 

Animation plugins would be niiice

... *cries* I'm just so happy. lol
## Post #448
- Username: yaz0r
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Sep 23, 2010 4:32 pm
- Post datetime: 2011-03-10T23:49:01+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from ultimaespio
>
> 
Animation plugins would be niiice

Guess that could be done in theory. I don't really know what is the status with animation support in neosis.
## Post #449
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-03-11T06:51:54+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I do wonder there as well, the export options suggest that Noesis supports PSK and PSA (personal favorite format to work with, high support in various programs), as well as MD5mesh and MD5anim formats. So animation support is likely there, plugin wise I am not sure but would love to see. Though this stems from 3D enthusiasm as I only own KH1.

So if possible, by all means, you have my support. It would definitely be fun to see them in motion.
## Post #450
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-03-11T10:33:34+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Animations are supported, and you can export them into .dae as well. It would just need an .mset plugin, but if the formats are different between KH1 and 2 then there would need to be separate mset plugins.
## Post #451
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-03-11T15:26:17+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

You'd need Visual C++ in order to create plugins, and you can only get it by buying it or on a 30-day trial basis. If there are any free ones out there, please let me know. I'd suggest starting with an mset plugin for KH2 since that's the game we can do the most with; export maps and models, unpack, repack, etc. Also, there are animations in the eh_l folder and the eh folder that were missed, like the n_zz160 animations that are necessary to move the Guardian. If I could understand this; if I had sufficient documentation on the way msets work, I could maybe try to see what I can do. Please note however that I've been learning AP Java and have little to no experience with C/++/#, so it would be harder to make a plugin for Noesis, since it uses C++ plugins. I could still do possibly do it, but then again I still don't know how msets work.
## Post #452
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-03-11T15:49:38+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Animation support is there (both skeletal and vertex), with sequences, and in fact FFX's animations are already supported too. The framework is also quite generic and allows you to drag and drop any animation file (or even a model with animations in it) to apply those animations to the currently loaded model.

You can also compile plugins with Microsoft Visual Studio 2005 Express Edition, which is completely free. There may be a free 2008 EE too, I've never looked.
## Post #453
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-03-12T00:25:58+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Darkfox
>
> I do wonder there as well, the export options suggest that Noesis supports PSK and PSA

That's odd, the PSA option doesn't show up for me. Is that a separate plugin that you downloaded?
## Post #454
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-03-12T02:18:52+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

It exports them by default or can be set to export in another. It can load PSA but seems PSK and PSA separately only (not mesh AND animation viewed as one).

An animation must exist first though, won't export a PSA if there is no animations.
[NoesisExport.jpg](https://xentaxbackup.github.io/file/4048_NoesisExport.jpg)
## Post #455
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-03-12T05:44:05+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Ah! Thanks for the explanation. I was viewing kh2 models so that's why it never appeared. lol
## Post #456
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-03-12T06:31:41+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Darkfox
>
> It exports them by default or can be set to export in another. It can load PSA but seems PSK and PSA separately only (not mesh AND animation viewed as one).

An animation must exist first though, won't export a PSA if there is no animations.
Nah, that's not the case. Just load the PSK, then drag and drop the PSA onto the preview window and answer "no" when it asks you if you want to load the model instead of apply it to the scene. You can apply any model/anim file as animations to an existing model, provided the bone counts and/or bone names match. Then you can export the combined form with the "export from preview" option.
## Post #457
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-03-12T07:13:04+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Yeah, sorry... I hope animation support for them gets added. Just a matter of when a plugin is made for it.

> Nah, that's not the case. Just load the PSK, then drag and drop the PSA onto the preview window and answer "no" when it asks you if you want to load the model instead of apply it to the scene. You can apply any model/anim file as animations to an existing model, provided the bone counts and/or bone names match. Then you can export the combined form with the "export from preview" option.

Oh, hey! Thanks a lot for that!  Really glad you pointed that out since I plan to make good use of that in the future!
## Post #458
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-03-12T17:31:24+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

If you want to export your KH1/2 meshes, and you want them the same size as the BBS ones, export them with a 0.01 scale.
## Post #459
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-03-13T00:24:12+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from ultimaespio
>
> If you want to export your KH1/2 meshes, and you want them the same size as the BBS ones, export them with a 0.01 scale.

Thanks for the tip! Um, if I want the BBS ones to be the same size as the KH1/2 ones, would I export them with a scale of.. uh, 100? (haha I fail at math.)
## Post #460
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-03-13T05:56:43+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from SoftIce
>
> ultimaespio wrote:If you want to export your KH1/2 meshes, and you want them the same size as the BBS ones, export them with a 0.01 scale.

Thanks for the tip! Um, if I want the BBS ones to be the same size as the KH1/2 ones, would I export them with a scale of.. uh, 100? (haha I fail at math.)
You sir are correct! I'm so excited about this plugin I may dig in KH2 models again.
## Post #461
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-03-13T07:47:16+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Glad to see new plugins being added, hope to see a mset plugin (or two if msets for KH2 are different) in the near future, then support can be considered pretty much complete (as far as import goes regarding KH1 and 2).
## Post #462
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-03-13T12:54:21+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

What's really interesting, is that the KH2 Riku in BBS s the exact same model as the PS2 one. Only difference is that the ps2 one has a few more bones.
## Post #463
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-03-16T20:53:08+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Zerox
>
> SoftIce wrote:ultimaespio wrote:If you want to export your KH1/2 meshes, and you want them the same size as the BBS ones, export them with a 0.01 scale.

Thanks for the tip! Um, if I want the BBS ones to be the same size as the KH1/2 ones, would I export them with a scale of.. uh, 100? (haha I fail at math.)
You sir are correct! I'm so excited about this plugin I may dig in KH2 models again.

Sweet! Hah I fail at math slightly less than I previously thought I did. I'm so freaking excited that Revelation created the KH2 plugin. Glorious high poly rigged KH2 Kairi, Riku and Sora... A dream come true. I'm considering trying to find Xion's model from 365 days now, because she technically has the same body dimensions as Kairi and that would mean I would have an organization style coat for Kairi... 

Kairi in an org style trench coat... I want badly...
## Post #464
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-03-16T21:33:26+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Larxene's coat not work?
## Post #465
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-03-17T13:24:13+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

woo hoo
Thanks a lot to revelation
## Post #466
- Username: Panzah
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Jul 22, 2010 5:11 am
- Post datetime: 2011-03-18T02:48:31+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from SoftIce
>
> I'm considering trying to find Xion's model from 365 days now, because she technically has the same body dimensions as Kairi and that would mean I would have an organization style coat for Kairi...

Unless a 358/2 Days uber low poly Xion model would satisfy you, there are no other models of her. The one seen in BBS' secret ending is sadly not in the game data.
## Post #467
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-03-18T20:30:00+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from ultimaespio
>
> Larxene's coat not work?

Larxene's quite a bit taller than Kairi (I think she's even a tad taller than Riku  ), and her legs and arms are quite longer, but as she's female she's the best fit if I can't get Xion.  Seriously, the people from DI are all super short... I decided to just NOT logically think of height when I look at models side by side, it's just too weird. 

> Reply from Panzah
>
> Unless a 358/2 Days uber low poly Xion model would satisfy you, there are no other models of her. The one seen in BBS' secret ending is sadly not in the game data.

Oh dang it. The 358 days model is super low poly? (and yay for totally messing up the name there.) Well, I'm still going after her model because once i get fixated on a goal I can't leave it alone. *cough* If anything the low poly could work as a guideline for larxene's coat. If I can even get the BDM0/MDL0 to work.
## Post #468
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2011-03-25T14:00:56+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Maybe they'll release a PS2 version of 358/2 days and then you'll have Xion's model too. 
I really hope they will since I'm not 100% satisfied with the graphics on DS.
Or who knows, maybe something on the 3DS, why not?
## Post #469
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-03-25T14:03:31+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

They won't do a ps2 remake now. Ps2 games are quickly disappearing from stores.
## Post #470
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2011-03-25T14:07:40+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Then PSP, it hasn't vanished yet. And they'll name it Kingdom Hearts 358/2 days RePSPd (j/k)
## Post #471
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-03-25T14:28:17+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from ChrisSquareFan
>
> Maybe they'll release a PS2 version of 358/2 days and then you'll have Xion's model too. 
I really hope they will since I'm not 100% satisfied with the graphics on DS.
Or who knows, maybe something on the 3DS, why not?

We couldn't get the models out of Re:Chain of Memories, which implemented a much more advanced level of the PS2 software, and no one could figure out how to get the models from that. If they ever made any new PS2 games, we may never crack it.
On the other hand, 3DS will probably be so similar to the NDS that we can just rip out the models. But we won't have KH3D until at least late this year, if not longer.
## Post #472
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-03-25T23:03:15+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> On the other hand, 3DS will probably be so similar to the NDS that we can just rip out the models. But we won't have KH3D until at least late this year, if not longer.

And hopefully the general format would be similar to Wii's MDL0. Though, given it is Square would likely be another proprietary format. However, some of their Wii titles used MDL0, so hmmm...
## Post #473
- Username: ChrisSquareFan
- Rank: advanced
- Number of posts: 59
- Joined date: Tue Aug 10, 2010 9:09 pm
- Post datetime: 2011-03-27T15:15:31+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Mirrorman95
>
> 
We couldn't get the models out of Re:Chain of Memories, which implemented a much more advanced level of the PS2 software, and no one could figure out how to get the models from that. If they ever made any new PS2 games, we may never crack it.
On the other hand, 3DS will probably be so similar to the NDS that we can just rip out the models. But we won't have KH3D until at least late this year, if not longer.

What exactly do you mean by a more advanced level of PS2 software? Data encryption?
Anyway, I don't know too much about PS2's components or software, but what I do know is related to 3DS,
and from what i red there's a new anti-piracy system embedded in the hardware. Don't know what to expect for now,
but I remain optimist in what we can do
## Post #474
- Username: eurik
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Apr 06, 2011 3:33 pm
- Post datetime: 2011-04-06T08:23:26+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Hi there! Nice to meet everyone xD! I just found this forum and let me say, I am so excited bcuz I am pretty sure I now know where to get my help. Alright, so at the start of this, it may seem off topic, but it IS about KH:BBS models. So bare with me please xD.

Alright, I play an online game called Mabinogi. I use alot of appearance mods, and I'm pretty good at making weapons. I have worked with KH stuff before like the mod I imported here


I also recently was able to finish the Incomplete and Complete "X" Blades for the game as well using a program called Metasequoia seen here


Now, I have also been working on animation mods for the game so I can hold it exactly like Vanitas(No image for that), and I also want his outfit, which I know CAN be done. Anyway, I have been following this forum only recently and I will admit I have a hard time understanding some of the things you guys say. So, here's the issues I am having.

As I said, I want the outfit. And I have got it into 3d max pretty nicely seen here


Only a few things wrong such as the following

1st, the helmet is all wierd


2nd, the belt texture is also having trouble


and finally, I can't seem to get the(for lack a better word) skirt to have transparency and I made sure to select to transparency when making it into a png file(the texture that is.)


I would love some help regarding these issues. And, again, I am using 3d max for this part.

Now, I don't know if this is all in vain. Mainly because I actually need to do this in Metasequoia. But whenever I load the .obj file(only .3ds, .mqo, and .obj files are loadable in Metasequoia) I get this result


I would really appreciate some help. This is the last piece of the puzzle. The only Thing I need for my full custom Vanitas Mod in Mabinogi. Does anyone know how to fix the model in Metasequoia? And if not, does anyone know how to fix the 3d max problem and MAYBE export it flawlessly for use in Metasquoia?

I really appreciate any help in advance. Thanx a ton xD
## Post #475
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-04-06T13:53:15+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from eurik
>
> Hi there! Nice to meet everyone xD! I just found this forum and let me say, I am so excited bcuz I am pretty sure I now know where to get my help. Alright, so at the start of this, it may seem off topic, but it IS about KH:BBS models. So bare with me please xD.

Alright, I play an online game called Mabinogi. I use alot of appearance mods, and I'm pretty good at making weapons. I have worked with KH stuff before like the mod I imported here
http://i1201.photobucket.com/albums/bb3 ... 656125.png

I also recently was able to finish the Incomplete and Complete "X" Blades for the game as well using a program called Metasequoia seen here
http://i1201.photobucket.com/albums/bb3 ... 46603f.png

Now, I have also been working on animation mods for the game so I can hold it exactly like Vanitas(No image for that), and I also want his outfit, which I know CAN be done. Anyway, I have been following this forum only recently and I will admit I have a hard time understanding some of the things you guys say. So, here's the issues I am having.

As I said, I want the outfit. And I have got it into 3d max pretty nicely seen here
http://i1201.photobucket.com/albums/bb3 ... a78cf5.png

Only a few things wrong such as the following

1st, the helmet is all wierd
http://i1201.photobucket.com/albums/bb3 ... 2196bc.png

2nd, the belt texture is also having trouble
http://i1201.photobucket.com/albums/bb3 ... 4f2807.png

and finally, I can't seem to get the(for lack a better word) skirt to have transparency and I made sure to select to transparency when making it into a png file(the texture that is.)
http://i1201.photobucket.com/albums/bb3 ... 4f2807.png

I would love some help regarding these issues. And, again, I am using 3d max for this part.

Now, I don't know if this is all in vain. Mainly because I actually need to do this in Metasequoia. But whenever I load the .obj file(only .3ds, .mqo, and .obj files are loadable in Metasequoia) I get this result
http://i1201.photobucket.com/albums/bb3 ... a72921.png

I would really appreciate some help. This is the last piece of the puzzle. The only Thing I need for my full custom Vanitas Mod in Mabinogi. Does anyone know how to fix the model in Metasequoia? And if not, does anyone know how to fix the 3d max problem and MAYBE export it flawlessly for use in Metasquoia?

I really appreciate any help in advance. Thanx a ton xD

The way to fix it is to convert your PMOs through Senor Casaroja's Noesis and not through Falo's triangle-flipping converter.
## Post #476
- Username: eurik
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Apr 06, 2011 3:33 pm
- Post datetime: 2011-04-07T23:07:02+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Mirrorman95
>
> eurik wrote:Hi there! Nice to meet everyone xD! I just found this forum and let me say, I am so excited bcuz I am pretty sure I now know where to get my help. Alright, so at the start of this, it may seem off topic, but it IS about KH:BBS models. So bare with me please xD.

Alright, I play an online game called Mabinogi. I use alot of appearance mods, and I'm pretty good at making weapons. I have worked with KH stuff before like the mod I imported here
http://i1201.photobucket.com/albums/bb3 ... 656125.png

I also recently was able to finish the Incomplete and Complete "X" Blades for the game as well using a program called Metasequoia seen here
http://i1201.photobucket.com/albums/bb3 ... 46603f.png

Now, I have also been working on animation mods for the game so I can hold it exactly like Vanitas(No image for that), and I also want his outfit, which I know CAN be done. Anyway, I have been following this forum only recently and I will admit I have a hard time understanding some of the things you guys say. So, here's the issues I am having.

As I said, I want the outfit. And I have got it into 3d max pretty nicely seen here
http://i1201.photobucket.com/albums/bb3 ... a78cf5.png

Only a few things wrong such as the following

1st, the helmet is all wierd
http://i1201.photobucket.com/albums/bb3 ... 2196bc.png

2nd, the belt texture is also having trouble
http://i1201.photobucket.com/albums/bb3 ... 4f2807.png

and finally, I can't seem to get the(for lack a better word) skirt to have transparency and I made sure to select to transparency when making it into a png file(the texture that is.)
http://i1201.photobucket.com/albums/bb3 ... 4f2807.png

I would love some help regarding these issues. And, again, I am using 3d max for this part.

Now, I don't know if this is all in vain. Mainly because I actually need to do this in Metasequoia. But whenever I load the .obj file(only .3ds, .mqo, and .obj files are loadable in Metasequoia) I get this result
http://i1201.photobucket.com/albums/bb3 ... a72921.png

I would really appreciate some help. This is the last piece of the puzzle. The only Thing I need for my full custom Vanitas Mod in Mabinogi. Does anyone know how to fix the model in Metasequoia? And if not, does anyone know how to fix the 3d max problem and MAYBE export it flawlessly for use in Metasquoia?

I really appreciate any help in advance. Thanx a ton xD

The way to fix it is to convert your PMOs through Senor Casaroja's Noesis and not through Falo's triangle-flipping converter.

I was able to fix the appearance in Metasequoia. Even completed the editing to make it non T-stance so I could make it proprtioned for Mabinogi. But my issues now is transparency. The, for lack of a better word, skirt part is suppose to have transparency on it where the purple is. How do I make it transparent in Metasequoia? I have the transparent color selected in the png texture, but it doesn't appear transparent.
## Post #477
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-04-08T00:22:50+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from eurik
>
> 
I was able to fix the appearance in Metasequoia. Even completed the editing to make it non T-stance so I could make it proprtioned for Mabinogi. But my issues now is transparency. The, for lack of a better word, skirt part is suppose to have transparency on it where the purple is. How do I make it transparent in Metasequoia? I have the transparent color selected in the png texture, but it doesn't appear transparent.

I don't use that program, but maybe it will appear transparent if you render it? Is there some kind of alpha channel in that program?
## Post #478
- Username: eurik
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Apr 06, 2011 3:33 pm
- Post datetime: 2011-04-08T02:34:29+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from SoftIce
>
> eurik wrote:
I was able to fix the appearance in Metasequoia. Even completed the editing to make it non T-stance so I could make it proprtioned for Mabinogi. But my issues now is transparency. The, for lack of a better word, skirt part is suppose to have transparency on it where the purple is. How do I make it transparent in Metasequoia? I have the transparent color selected in the png texture, but it doesn't appear transparent.

I don't use that program, but maybe it will appear transparent if you render it? Is there some kind of alpha channel in that program?

there is, but I don't understand it at all o.o
## Post #479
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-04-21T00:43:20+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Does anyone know where the battle voice clips are? I suspect they must either be in BBS0.DAT or BBS3.DAT, but no matter how much I look, I can't seem to find them.
I have managed to discover that there are hundreds of SFX and some voice clips in BBS3 that aren't with the rest in BBS0, including:
"I keep forgetting — don't mess with Keyblade wielders. But you know what? That just means I made the right choice! Well... he wanted me to buy time, and I'd say he got it."
"Aqua!"
"Go take what Ventus owes you, and take Aqua's life!"
"Master... Why is Vanitas still free?
"Ah yes. Well, I did my best to contain him the moment he emerged, but... He managed to escape."
"Now that my body is about to perish, you and I will have to join together."
"We meet again, boy."
"Mickey!"
"D'oh... My kart musta sprung a spring! You yahoos just wait--next time, I'll clobber all of you!"
## Post #480
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2011-04-22T09:36:27+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

are the models of the secret ending movie " a fragmented passage" of Final Mix BBS obtainable? I am confused.
## Post #481
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-04-23T01:21:14+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

It turns out that PSound, a sound ripper designed for PS1 and PS2 games, found many more sound files in BBS3.DAT than either AA3Get or Majik's Sound Extr, sound rippers specifically designed to extract PSP sounds. Sound Extr, by the way, is more accurate than AA3Get in extracting at3s, and can handle vag files as well. In BBS3.DAT, AA3Get found 385 aa3s, Sound Extr found 784 at3s, and PSound found 1682 WAVs. It appears that the only files it extracted from the four dat files were sound effects that weren't saved as at3 files.
And thus, I still don't know where the battle clips are. I think I've at least pinpointed them to BBS3, though. This is a list of quotes from said clips that I still need to find:
"Join now with your better half!"
"Show me anguish!"
"What's yours is mine!"
"Playtime's over."
"Why?" -Vanitas's last words
"Only now have I truly won."
"Let the darkness die!"
"You have lost!"
"Reload!"
"Farewell!"
"You're done."
"Into sleep you fall, forever!"
## Post #482
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2011-04-23T08:24:27+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

yes, it does. it tends to find many repetitions, however. no doubt because some bosses have multiple storylines versions that behave in the same way.
## Post #483
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-04-23T16:41:06+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Where are the battle sounds? I can't find them in any of the aa3 or at3 files.
Does anyone know where they are?
## Post #484
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2011-04-24T09:27:32+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

you mean SFXs? like a keyblade slash?
## Post #485
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-04-24T16:31:52+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

No, I mean what they say during gameplay, like "you're done" or "show me anguish".
## Post #486
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-04-24T17:06:47+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

If you've got the Dissidia modding suite, you can rip all of the at3's using that. I've got some of the voices using that. But I used it on the full iso rather than on the individual files.
## Post #487
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-04-24T19:47:21+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I used Sound Extr to rip all the at3 files. They comprise all of the dialogue and music played in the game's cutscenes. But I can't find any of the vocal files during gameplay. The closest I've managed are the dialogue the characters say right after the a tutorial battle, like "I'm in trouble tomorrow". If this modding suite can find more at3 files in Birth by Sleep than the others can, I'll gladly use it.

Looking at the files, the PMFs it extracts are all cut off before they should, it extracts the SSCF files but they are just background noises and such and I don't have anything that can play them, and the AT3 files still look like the same ones.

Does anyone at least know of an older version of JPCSP that extracts ALL the sound files it handles to a tmp folder? I need a way to GET THOSE FILES. Like "Only now have I truly won.", and "Why?", Vanitas's last words. They ALL elude me! I can't find any battle AT3s. Maybe someone can tell me how to read the memory off JPCSP so that I can find the files myself. There must be an answer, but I don't know what. I'm not even sure they're AT3 anymore, since every AT3 extractor hasn't shown to be conclusive.
## Post #488
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2011-04-25T08:56:32+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

it's weird. PSound extracts almost all of the battle quotes you want. maybe it works like the KH1 games, where you have to scan the battle model in order to find the quotes?
## Post #489
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-04-26T03:54:40+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Devilot
>
> it's weird. PSound extracts almost all of the battle quotes you want. maybe it works like the KH1 games, where you have to scan the battle model in order to find the quotes?

Could you please give me an example of a title of a sound file that has one or more of those battle quotes? It would help me a lot.
## Post #490
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2011-04-26T15:24:23+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

gimme a day to return to my PC. send me a PM to remind me.
## Post #491
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-04-26T22:01:54+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

At this point, I think they're ECM files, which are in the same ARC as many PMOs are, including boss battle Vanitas. The ECM files are probably compressed or encrypted sound files, which is why PSound and ATRAC extractors can't find them.

Could I use a RAM dump to potentially obtain the sounds as they're being sent to the memory?
## Post #492
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2011-04-27T20:37:05+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

on that I can't tell. I did not even know of the existance of a program called soundextractor.
## Post #493
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-05-02T01:48:35+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Thanks for the info mirrorman
## Post #494
- Username: Truthkey
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jul 24, 2010 5:39 am
- Post datetime: 2011-05-03T19:26:10+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Battle sounds such as "Darkness waits!" or "Show me anguish!" are inside SSCF files (.scd extension). I made a program to rip them from the game easily, the problem is that there is no SSCF player, thus, we can't convert/play them.
## Post #495
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-05-03T23:09:25+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Truthkey
>
> Battle sounds such as "Darkness waits!" or "Show me anguish!" are inside SSCF files (.scd extension). I made a program to rip them from the game easily, the problem is that there is no SSCF player, thus, we can't convert/play them.

Is there a link to your SSCF ripper? All I have is the Dissidia Modding Suite, and the SSCF files it rips are larger than the actual files.
## Post #496
- Username: Truthkey
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jul 24, 2010 5:39 am
- Post datetime: 2011-05-03T23:18:01+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Mirrorman95
>
> Truthkey wrote:Battle sounds such as "Darkness waits!" or "Show me anguish!" are inside SSCF files (.scd extension). I made a program to rip them from the game easily, the problem is that there is no SSCF player, thus, we can't convert/play them.

Is there a link to your SSCF ripper? All I have is the Dissidia Modding Suite, and the SSCF files it rips are larger than the actual files.

Dissidia modding suite is not gonna extract the right the right SSCFs since KHBBS uses a different header keyword for their SSCF packages.

As I previously mentioned... I created a tool to rip those SSCFs along with (almost) all the other files in the game. The program rips all AT3, SSCF, PMO, PAM, OLO, SEB, FEP, TIM2 and CTD and allows you to reinsert the files back again in the game as long as they are smaller or equal to the original file (since no one has successfully cracked BBS's LBA).

I can send you a small beta of the program through PM if you really need it since I'm not going to publish it until I finish it 100%.
## Post #497
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-05-03T23:20:49+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I don't want it that badly; I can get it when it's finished. Is this the program you've been talking about on Twitter?
## Post #498
- Username: Truthkey
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jul 24, 2010 5:39 am
- Post datetime: 2011-05-03T23:26:50+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Mirrorman95
>
> I don't want it that badly; I can get it when it's finished. Is this the program you've been talking about on Twitter?

Didn't know you followed my Twitter but yeah, that's what I've been working on. It's a program for people to mod the game at will, textures, events, animations, sounds, music, effects, etc. It shouldn't take me much time to finish it, maybe two or three days, not more.

Anyways, it's not like we're going anywhere with these SSCF files since they don't seem hearable/convertible, that is, unless you find an expert in audio formats.
## Post #499
- Username: eurik
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Apr 06, 2011 3:33 pm
- Post datetime: 2011-05-04T10:56:51+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Hey, I have a few questions, and the KH1 Model Topic isn't really active at the moment... Anyway, I am having.... a little trouble understanding how the kh1_file_dumper.exe works.... Like, I don't find anything actually explaining it.... I mean, I have the readme.txt and it says

KH1 dumper:
- copy KINGDOM.IDX and make a ISO into the same folder as kh1_file_dumper.exe
- make a *.bat or run from commandline

Usage:


kh1_file_dumper.exe kh.iso KINGDOM.IDX [options]



options:

"-dN" = dump from "ard files" NameTable (like yaz0r's dumper)

"-dM" = dump all Music files (dat(bgm+wd),wd,vset,vsb)

"-dE" = dump all Event files (evm,dpp,dpx)
"-dO" = dump Other files (ard,evm,wdt,dat,dbt,wpn,se,mag)
"-dT" = dump all files from nametbl.txt

umm.... ok? what does that mean? How do I get the nametbl.txt? or how do I simply dump the wpn files? It says Options -dO or -dT, but what does that mean? when I open the program, it says please press any key to continue, so I try to enter one of those things and it doesn't work. Or I place the kh.iso and .idx on the .exe it says pleas enter file name. so I try the -dt or -do and it says file not found. Why are these instructions not very... instructual? xD. Anyway, I simply want to get all the weapons from KH1. Help please? I appreciate everything in advance
## Post #500
- Username: Truthkey
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jul 24, 2010 5:39 am
- Post datetime: 2011-05-04T11:34:15+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from eurik
>
> Hey, I have a few questions, and the KH1 Model Topic isn't really active at the moment... Anyway, I am having.... a little trouble understanding how the kh1_file_dumper.exe works.... Like, I don't find anything actually explaining it.... I mean, I have the readme.txt and it says

KH1 dumper:
- copy KINGDOM.IDX and make a ISO into the same folder as kh1_file_dumper.exe
- make a *.bat or run from commandline

Usage:


kh1_file_dumper.exe kh.iso KINGDOM.IDX [options]



options:

"-dN" = dump from "ard files" NameTable (like yaz0r's dumper)

"-dM" = dump all Music files (dat(bgm+wd),wd,vset,vsb)

"-dE" = dump all Event files (evm,dpp,dpx)
"-dO" = dump Other files (ard,evm,wdt,dat,dbt,wpn,se,mag)
"-dT" = dump all files from nametbl.txt

umm.... ok? what does that mean? How do I get the nametbl.txt? or how do I simply dump the wpn files? It says Options -dO or -dT, but what does that mean? when I open the program, it says please press any key to continue, so I try to enter one of those things and it doesn't work. Or I place the kh.iso and .idx on the .exe it says pleas enter file name. so I try the -dt or -do and it says file not found. Why are these instructions not very... instructual? xD. Anyway, I simply want to get all the weapons from KH1. Help please? I appreciate everything in advance

kh1_file_dumper.exe -dT kh.iso KINGDOM.IDX

or

kh1_file_dumper.exe kh.iso KINGDOM.IDX -dT

One of those should work.
## Post #501
- Username: eurik
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Apr 06, 2011 3:33 pm
- Post datetime: 2011-05-04T21:31:09+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I type that in when it says please enter file name? because I did that and it didn't work. Tried both and it just said file not found...
## Post #502
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-05-05T02:14:06+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Truthkey
>
> Mirrorman95 wrote:I don't want it that badly; I can get it when it's finished. Is this the program you've been talking about on Twitter?

Didn't know you followed my Twitter but yeah, that's what I've been working on. It's a program for people to mod the game at will, textures, events, animations, sounds, music, effects, etc. It shouldn't take me much time to finish it, maybe two or three days, not more.

Anyways, it's not like we're going anywhere with these SSCF files since they don't seem hearable/convertible, that is, unless you find an expert in audio formats.

Modding animations... Does this mean that creating new pmo models may be something you may be implementing? It'd be fun to insert Sora or Riku to play as.
## Post #503
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-05-05T03:33:06+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Zerox
>
> Truthkey wrote:Mirrorman95 wrote:I don't want it that badly; I can get it when it's finished. Is this the program you've been talking about on Twitter?

Didn't know you followed my Twitter but yeah, that's what I've been working on. It's a program for people to mod the game at will, textures, events, animations, sounds, music, effects, etc. It shouldn't take me much time to finish it, maybe two or three days, not more.

Anyways, it's not like we're going anywhere with these SSCF files since they don't seem hearable/convertible, that is, unless you find an expert in audio formats.

Modding animations... Does this mean that creating new pmo models may be something you may be implementing? It'd be fun to insert Sora or Riku to play as.

It kind of sounds like a tool to extract and repack these files, though I'm not sure that the program could tell you which animations do what. He probably implements something similar for his Final Mix patcher.
## Post #504
- Username: eurik
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Apr 06, 2011 3:33 pm
- Post datetime: 2011-05-05T05:22:32+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

So do any of you know how to fix the issue of extracting the weaponmodels? if not, does anyone have a list of the weapon model names? like xa_ex_5020.wpn or whatnot? I would much appreciate it if you could helpme out here. Or if anyone has all the KH1 keyblades in .obj format. I am attempting to create a mass mod in the MMO I play and it would be great for some help. I have all KH2 keyblades, and KHBBS keyblades. again, any help is much appreciated.
## Post #505
- Username: Truthkey
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jul 24, 2010 5:39 am
- Post datetime: 2011-05-05T09:55:13+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Zerox
>
> Truthkey wrote:Mirrorman95 wrote:I don't want it that badly; I can get it when it's finished. Is this the program you've been talking about on Twitter?

Didn't know you followed my Twitter but yeah, that's what I've been working on. It's a program for people to mod the game at will, textures, events, animations, sounds, music, effects, etc. It shouldn't take me much time to finish it, maybe two or three days, not more.

Anyways, it's not like we're going anywhere with these SSCF files since they don't seem hearable/convertible, that is, unless you find an expert in audio formats.

Modding animations... Does this mean that creating new pmo models may be something you may be implementing? It'd be fun to insert Sora or Riku to play as.

Unfortunately my knowledge doesn't go that far. If I had some files with the PMO and OBJ structures I could work on a converter for both formats, but I know barely nothing about 3D model formats or 3D animation formats.
I wish someone skillful enough can create a converter TO pmo. That'd be amazing.
## Post #506
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-05-05T23:24:27+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Noesis is a program that can convert PMO to OBJ and several other formats with bones intact. Every other polygon wouldn't be flipped like in Falo's converter, so you have a much cleaner file to use in custom game engines, texture modification, and all that. Unfortunately, there are colorful shaders in some PMOs without textures that can be viewed in Noesis, but they can't be converted by anything.

If anyone wants to take a crack at the animation file structure, I've got a couple of PAMs from the game. Of course, Xeeynamo has made an ARC extractor to unpack/repack ARCs and their contents, so that would work too. I seriously have no idea how they work.
## Post #507
- Username: Truthkey
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jul 24, 2010 5:39 am
- Post datetime: 2011-05-09T23:12:50+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

The contents of this post was deleted because of possible forum rules violation.
## Post #508
- Username: Nexus Elite
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Apr 16, 2011 1:36 am
- Post datetime: 2011-06-12T13:45:41+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I a bit curious, how do you extract the DAT files? I can't seem to find out how to.
## Post #509
- Username: Bla buhu
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 10, 2011 6:50 pm
- Post datetime: 2011-07-10T11:07:59+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Is it possible to bring a texture of a keyblade from KH2 to KHBBSFM ? Like oblivion or the old ultima weapon
## Post #510
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-07-10T12:44:45+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

If you mean port weapons over, then no.
## Post #511
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2011-09-18T22:25:57+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Has somebody saved Truthkey's extractor? His and Xeeynamo's tools seem to be offline or I just didn't search in the right places.

I'm really interested in the battle effects right now, which seem to be stored in the tex files. Unfortunately they seem to be quite different from their KHII pendant pax.
## Post #512
- Username: dragicorn
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Sep 18, 2011 3:21 am
- Post datetime: 2011-10-20T01:49:21+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Does anyone know if you actually can view the BBS models with animations? I have the newest version of Neosis with the plugins downloaded and put in the folder path, but they still don't open PMO models, nor can I find .pma files in my Birth By Sleep cd when I try to extract them. I can extract pmo files and view them as Obj, but I cant seem to view SMD except by 3ds studio and blender, and I can't figure out how to use textures or view animations with those tools even after reading the entire programs (they don't give step by step instructions!)

Is there a PAM viewer? is there a smd viewer? Does smd carry animations?

I'm new to this but have been following closely for about a year and a half. I don't understand the coding and can't really contribute to any of you, but I've much appreciated the help you contributed... it's sooo confusing though. I don't wish to use the models... I just want to view them... but my game doesn't work on my device... none of them do anymore... T_T

EDIT: Okay... ahem, by not viewing, I mean broken, and the PSPs sell out and don't restock for months, and they are swamped at their low prices. I can't even get the PSP to turn on O: I never dropped it or had water spilled on it... it just died after over use... I think.
## Post #513
- Username: GovanifY
- Rank: advanced
- Number of posts: 59
- Joined date: Thu Apr 17, 2014 4:25 am
- Post datetime: 2014-04-25T17:25:13+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

What an old topic!

Anyways, I just partly figured out the LBA of BBS. B\c, afaik, truthkey/Keytotruth never really reversed it, that's why we can't have the real names of the files and the support to add new files etc...
I just looked a little bit on BBS0.DAT and I realized that he contains the LBA of BBS. If ya want to know, the hashes aren't like kh2, but 6bytes length. I just partly reversed it, so I can't really say(or do) anything interesting but maybe I'll be able to, one day, just made a clear extractor of bbs, w/ real names etc...

I've not so many things to say, but that's still somethin', so see ya!, GovanifY
## Post #514
- Username: jasonpatrick72
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Mar 16, 2015 9:58 am
- Post datetime: 2015-03-16T02:03:40+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Hey Guys!

Im new here so excuse me if this has been asked before.

But does anyone know how to apply the textures to the KH models in Cinema 4D? I'm still somewhat new to the program, but not a complete newb. 

When I  apply the textures to the respective obj's they come out wrong and funky...

I've extracted both the models and textures with Noesis

If anyone is interested in some screenshots, I will gladly post them.

Also does anyone know how to extract the animation from KH models and apply them in C4D as well?
## Post #515
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2015-03-16T03:44:05+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from jasonpatrick72
>
> Hey Guys!

Im new here so excuse me if this has been asked before.

But does anyone know how to apply the textures to the KH models in Cinema 4D? I'm still somewhat new to the program, but not a complete newb. 

When I apply the textures to the respective objs they come out wrong and funky...

I've extracted both the models and textures with Noesis

If anyone is interested in some screenshots, I will gladly post them.

Also does anyone know how to extract the animation from KH models and apply them in C4D as well?Noesis tends to flip the UVs when exporting models. Select the "Flip UVs" option when you export them and they should look better. If that's not it, I suggest you post screenshots.
## Post #516
- Username: jasonpatrick72
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Mar 16, 2015 9:58 am
- Post datetime: 2015-03-16T15:18:05+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from Mirrorman95
>
> jasonpatrick72 wrote:Hey Guys!

Im new here so excuse me if this has been asked before.

But does anyone know how to apply the textures to the KH models in Cinema 4D? I'm still somewhat new to the program, but not a complete newb. 

When I apply the textures to the respective objs they come out wrong and funky...

I've extracted both the models and textures with Noesis

If anyone is interested in some screenshots, I will gladly post them.

Also does anyone know how to extract the animation from KH models and apply them in C4D as well?Noesis tends to flip the UVs when exporting models. Select the "Flip UVs" option when you export them and they should look better. If that's not it, I suggest you post screenshots.

Ok. I'll try that when I get home from work later. Thanks for the tip!
## Post #517
- Username: mysis
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Aug 14, 2014 6:45 pm
- Post datetime: 2015-04-14T18:01:27+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

so I updated the existing bbs plugin for noesis to load the ps3 models in noesis, found some untextured models like xehanort. also models like old aqua, xemnas, ansem sod etc are still present
to do: gtf loading
## Post #518
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2015-04-14T21:01:45+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

That's amazing! Can you upload your plugin somewhere?
## Post #519
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-04-20T22:04:09+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

very interesting search, gratz for the new work, have plans to make it public?
## Post #520
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2015-05-31T12:52:17+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

It would be really interesting to know how many models were upgraded, great work mysis.
## Post #521
- Username: thomasco19
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 16, 2015 10:37 am
- Post datetime: 2015-07-16T13:30:23+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Has anyone ripped the models specific to the Final Mix version of BBS, like the Armor of the Master(Eraqus' Armor)? I've tried to rip them myself to no avail. Or at least what a definite way I can rip them from BBSFM because I've tried and they don't appear.
## Post #522
- Username: Fireon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Sep 08, 2015 9:48 pm
- Post datetime: 2015-09-09T01:42:58+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Can anyone know how to extract BBS (or BBS FM) font and edit it?

I want to translate this game to my native language.
## Post #523
- Username: Fileking
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Aug 05, 2015 7:41 am
- Post datetime: 2016-02-13T15:27:08+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

Dose any one have master eraqus armor even in pmo form ??? i need to find that 3d model
## Post #524
- Username: FirstNameBasis
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Sep 22, 2016 11:38 am
- Post datetime: 2016-09-22T18:55:31+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

> Reply from GovanifY
>
> What an old topic!

Anyways, I just partly figured out the LBA of BBS. B\c, afaik, truthkey/Keytotruth never really reversed it, that's why we can't have the real names of the files and the support to add new files etc...
I just looked a little bit on BBS0.DAT and I realized that he contains the LBA of BBS. If ya want to know, the hashes aren't like kh2, but 6bytes length. I just partly reversed it, so I can't really say(or do) anything interesting but maybe I'll be able to, one day, just made a clear extractor of bbs, w/ real names etc...

I've not so many things to say, but that's still somethin', so see ya!, GovanifY

Hey, did you ever make any progress on reversing the LBA? I've been working at extracting files using KeyToTruths program and labeling almost everything I come by (Expanding on the files already labeled in TruthKey's extractor package), Trying to figure out model swapping, and Working on various smaller things in the extracted files. I dont know how LBA's Work but i am interested in learning if it means helping progress modding of this game for everybody. 

Google did not make it easy what-so-ever for trying to even figure out what LBA means so would you be able to share information on it?
## Post #525
- Username: Alphonse123
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 13, 2016 8:20 am
- Post datetime: 2016-12-25T15:14:45+00:00
- Post Title: Re: [Request] Kingdom Hearts Birth By Sleep models

I have a question, in which file is located the map of the jungle book? Is that I want to make the characters and add them to the map...
## Post #526
- Username: mysis
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Aug 14, 2014 6:45 pm
- Post datetime: 2017-02-22T18:13:39+00:00
- Post Title: Re: Kingdom Hearts Birth By Sleep models

Heres the plugin for the ps3 bbs pmos  HD textures arent loaded as I havent got around doing that yet  


[kingdom_hearts_bbs_ps3.rar](https://xentaxbackup.github.io/file/12495_kingdom_hearts_bbs_ps3.rar)
## Post #527
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2017-02-22T18:40:33+00:00
- Post Title: Re: Kingdom Hearts Birth By Sleep models

Wow, thank you mysis.
## Post #528
- Username: kinlyki
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Jun 21, 2015 12:36 am
- Post datetime: 2018-02-08T15:45:22+00:00
- Post Title: Re: Kingdom Hearts Birth By Sleep models

I know this is a necro, but does anyone know where I can get the facial animation textures for the low-poly models? Blinking for example. I'm also looking for the same thing for KH2.
## Post #529
- Username: Hero May Cry
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Sep 06, 2021 9:20 pm
- Post datetime: 2021-09-06T13:22:00+00:00
- Post Title: Re: Kingdom Hearts Birth By Sleep models

Anyone know if you could also use this method to extract the animation files along with the Model files for FBX?
