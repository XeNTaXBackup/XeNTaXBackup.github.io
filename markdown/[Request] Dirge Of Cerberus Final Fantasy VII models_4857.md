## Post #1
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-08-07T18:20:55+00:00
- Post Title: [Request] Dirge Of Cerberus Final Fantasy VII models

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-08-07T18:46:29+00:00
- Post Title: [Request] Dirge Of Cerberus Final Fantasy VII models

sample file would be needed.
## Post #3
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-08-07T18:47:21+00:00
- Post Title: [Request] Dirge Of Cerberus Final Fantasy VII models

Sorry, I would have uploaded one but its way too big. Its 1.4gb.
## Post #4
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-08-07T21:02:49+00:00
- Post Title: [Request] Dirge Of Cerberus Final Fantasy VII models

> Reply from ultimaespio
>
> Sorry, I would have uploaded one but its way too big. Its 1.4gb.
Can you download any hex editor, and do a search in the kel.dat file  for "00 00 80 3f" (3f800000) and tell me how many results are found, as this will almost surely tell us if the file is compressed or encrypted. It might freeze because there might be millions of results which is a good thing, as the file will not be compressed. This will save me some time, driving to the library to pick it up only to find it compressed. Also if you could give me any Pcsx2 save state, of RedXIII in the in game model viewer that would help me out to, as it is still possible to manually get the model out of the save state, without ripping, just by looking at the data.
## Post #5
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-08-07T21:32:04+00:00
- Post Title: [Request] Dirge Of Cerberus Final Fantasy VII models

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-08-09T00:04:02+00:00
- Post Title: [Request] Dirge Of Cerberus Final Fantasy VII models

Here is a sample model from the save state [http://ps23dformat.wikispaces.com/file/ ... sample.dat](http://ps23dformat.wikispaces.com/file/view/modelsample.dat) (Pcsx2 save states are just renamed zip file), The model is loaded in PS2 RAM at offset 18DFE80
It uses 2ByteSignedIntegers
## Post #7
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-08-09T00:30:09+00:00
- Post Title: [Request] Dirge Of Cerberus Final Fantasy VII models

Thanks, I didnt know you could work that out from a savestate. Do you have the game yourself?
## Post #8
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2010-08-28T08:36:27+00:00
- Post Title: [Request] Dirge Of Cerberus Final Fantasy VII models

Hi gentlemen,,I found a  way to extract the container.
There is a filelist.bin in disk's parent directory,it let me think of ff13's container structure.
I viewed both of the filelist,,they're the same structure in hexeditor.
So i used aluigi's bms script of ff13 to open it,,1st time,it failed,,then i rename
filist.bin into Filelist_scru.x360 ,and rename KEL.DAT into White_scru.x360,,

Haha aluigi's script extract everything!!!

here is the stuff i found in KEL.DAT



Now,,it's time to dig 3d model out!!!please help~
Some samples here
[http://www.2shared.com/file/Xefqh00b/samples.html](http://www.2shared.com/file/Xefqh00b/samples.html)
## Post #9
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-08-28T12:46:12+00:00
- Post Title: [Request] Dirge Of Cerberus Final Fantasy VII models

Would you mind uploading that somewhere else, like megaupload or mediafire please? Thanks.

I can't get the FF13 script to work for mine for some reason :/
## Post #10
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2010-08-28T12:53:42+00:00
- Post Title: [Request] Dirge Of Cerberus Final Fantasy VII models

> Reply from ultimaespio
>
> Would you mind uploading that somewhere else, like megaupload or mediafire please? Thanks.

I can't get the FF13 script to work for mine for some reason :/

Sure,,here they are,, with more samples,,[http://www.megaupload.com/?d=2TLP0AO8](http://www.megaupload.com/?d=2TLP0AO8)

my bms script here
[http://www.megaupload.com/?d=XB2ETOP5](http://www.megaupload.com/?d=XB2ETOP5)

The other 2 container could be movies or music,i can't extract anything with this method.
## Post #11
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-08-28T13:15:14+00:00
- Post Title: [Request] Dirge Of Cerberus Final Fantasy VII models

Thanks. Looking at the file extensions, I'd say that .mod is the models. Looks like you managed to extract maps too.

I'll add this to the first post for people to look through.

EDIT: Then again, looking at the size of those .map files, I doubt that they are maps at all. the file size is only 400kb, and that seems way too small.

CONFIRMED .mod IS model data!

```
model...rfd..M...... ...........model...bmd..M..BMD
```


I found that with hex workshop.
## Post #12
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2010-08-28T13:29:28+00:00
- Post Title: [Request] Dirge Of Cerberus Final Fantasy VII models

in the data\zone\ folder,,has lots of bgmxxx_.at3,,,sexxxx_.at2,,nothing else,,,probablly music and sound,,,could map the same as .mod?
## Post #13
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-08-28T13:39:36+00:00
- Post Title: [Request] Dirge Of Cerberus Final Fantasy VII models

I think so, I've checked through 2 of the .mod files you gave out, and one of them had:

```
E:\map\master\z142\m012\
```


The other one didn't have anything like that in at all. Unless this is a level object...I dunno.

That was 00000ba3.mod
## Post #14
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2010-08-29T12:34:41+00:00
- Post Title: [Request] Dirge Of Cerberus Final Fantasy VII models

new samples,,  .tex,,,have chance to be textures~
[http://www.megaupload.com/?d=2ZTDGJ1S](http://www.megaupload.com/?d=2ZTDGJ1S)
## Post #15
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-08-29T13:27:43+00:00
- Post Title: [Request] Dirge Of Cerberus Final Fantasy VII models

The map files contain different sections in them, but the main section after the long list of about 1000 addresses (in the b98.map file) that end at offset 153D contains the following structure:
Each map file is composed of hundreds of sub-meshes that reference the level grid.
1. The first component of each sub mesh is an optional section that is the reference:
"02 00 00 00 GG 00 00 00 YY YY YY YY RR RR RR RR
4ByteFloatCoord#1(X,Y,Z) 4ByteFloatWeight
4ByteFloatCoord#2(X,Y,Z) 4ByteFloatWeight
4ByteFloatCoord#3(X,Y,Z) 4ByteFloatWeight
4ByteOffsetAddressList" Padded with zeros until next whole multiple of 16bytes
Where GG is the number of addresses to follow near the end of this component.
YY YY YY YY is an 4byte offset
RR RR RR RR is probably some type of offset or reference , but about half the time it is 0

2. The component section is mandatory, and is always 16bytes in size:
00 80 06 61 unknown12ByteData

3. The third component is mandatory:
06 80 XX 60 data..... unknown padding
where the data is XX number of 4byte arrays
the data does not appear to be either floats or integers.

4. The fourth component is mandatory and is about 17 bytes in size without counting padding:
30 XX XX XX FF XX XX 00 00 XX XX 00 00 00 00 00 00
each XX is an unknown variable
5. The fifth component is mandatory and contains most important data which is the vertexes:
02 00 00 05 XX 80 VV 69 00 00 00 00 00 00 data.... unknownpadding
Where the data is VV number of 2ByteSignedVertexes(X,Y,Z)
6. The sixth component is mandatory:
00 00 00 05 00 00 00 17 unknown padding
## Post #16
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2010-08-30T05:15:12+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Thanks a lot FurryFan,great job^^b
According to the pattern you found.
I pick a little .map data as sample..less complexity
maybe it can help you figure out the 
remaining unknown float/variables


File is here
[http://www.mediafire.com/?i1uxmt030bi5u1h](http://www.mediafire.com/?i1uxmt030bi5u1h)
## Post #17
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-08-30T10:56:02+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Yes I will work on it. In English the first part of the file is called the "Header". It should be no problem I have a little bit done and will get the rest done soon.
## Post #18
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2010-09-03T00:54:32+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

FurryFan,,do you think .mod extention is another type of container?
Because all .mod header have rfd and bmd with lots of small chuncks you found
,and  not every xxx.mod have the same xxx.tex with them.
## Post #19
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-09-03T10:59:44+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Yes there is some overlap in the different files. I'll work on the header today after classes. I already made some progress on it.
## Post #20
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-09-03T18:32:49+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

The following applies to most if not all of the MAP files:

The 4byteoffset at 0hC is the size of the file.


The 4Byteoffset 0h68 is the number of 4byte addresses (lets call this OmegaList until I figure out what it is for) in the list that the pointer (add+0h30) at offset 0h74 points to.

The 4byteoffset 0h6C is the number of 16byteFloatoffsets in OmegaFloats that the pointer at offset 0h70points to (add+0h30.

The 4byteoffset 0h1D0 is the number of 4byte addresses in AlphaList that the pointer at offset 0h94 points to (add+0h30)
## Post #21
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2010-09-03T23:51:18+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

About the .rfd extention,I noticed there is a file called effect.rfd located in /data/effect/ folder.
Perhaps it's only a function of light effect something being used by the map scene,anyway,,i put that file here.

[http://www.megaupload.com/?d=R5ZVPHIC](http://www.megaupload.com/?d=R5ZVPHIC)

Another 4 rfd files found in data/etc/folder
[http://www.megaupload.com/?d=333G1FOD](http://www.megaupload.com/?d=333G1FOD)

They look like some kind of texture format though.
## Post #22
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2010-09-04T00:26:55+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

i was starting with the .mod file but seems the format is global to a number of others as well...

```
{
	SetBackColor(cLtBlue);
	// 0x00
	char   fileTag[8]; // 'model'
	char   dataTag[4]; //
	uint32 dataSize    <format = hex>;
};

```


The data tag member determines what is contained in each section, with most files starting with a 'rfd' section, which is simply a list of data offsets...

```
{
	SetBackColor(cLtBlue);
	// 0x00
	uint16 dataCount;
	uint16 unknown0x04            <format = hex>;
	
	SetBackColor(cLtGreen);
	uint32 dataOffsets[dataCount] <format = hex>;
};

```


The offsets point to another header structure which again the contents of which are controlled by the data tag, 'bmd', 'mod', 'tm2', 'chi', etc...

Hope that helps for now...
## Post #23
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-09-16T23:29:46+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Sorry to bump, any new progress with this?
## Post #24
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-12-03T15:45:25+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Ok so I've been reading around on another forum, and the files that are extracted here are just garbage. The FF13 script is totally different to Cerberus, so we get junk when we extract.

Apparently we have to use a program called offzip to extract them, has anyone got this tool and know how to use it?
## Post #25
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-12-10T17:13:43+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

i converted a texture but they are swizzled so there is no interest in getting models witout textures
## Post #26
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-03-09T21:11:53+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Here are 2 new samples ,,one is extracted by offzip,,,the other is dumped from emulator(pcsx2)
You can compare their pattern. 
[http://www.sendspace.com/file/u43pde](http://www.sendspace.com/file/u43pde)

I can't tell float's pattern, it seems to be encrypted.It has a strange array in the front of each vertex chunk,8 bytes each.Don't know what's the purpose.
Could it be bit-rotation? Or maybe half-float?
## Post #27
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-03-10T00:17:47+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

I hope we can extract the model
## Post #28
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-03-10T15:25:42+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Part of the Header of extracted.dat says evm. Not sure if that is a model, I've heard evm somewhere but I can't remember where...
## Post #29
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-03-10T23:55:13+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

> Reply from ultimaespio
>
> Part of the Header of extracted.dat says evm. Not sure if that is a model, I've heard evm somewhere but I can't remember where...

I'll look others,,was digging "MOD" ones only.
Makuchan said he had seen successful extrated model in Final Fantasy Project forum.
[http://ffproject.net/](http://ffproject.net/)

but sadly it's closed atm.

I've never seen though,,,Does anyone know how to contact with the owner of that forum?
Maybe he has some old data stored...

Btw,here are 2 new samples i found,,i believe one of them is the building..take a look if you're interested.
[http://www.sendspace.com/file/gexphf](http://www.sendspace.com/file/gexphf)
## Post #30
- Username: Cloud452
- Rank: veteran
- Number of posts: 91
- Joined date: Sat Oct 23, 2010 9:50 pm
- Post datetime: 2011-03-11T01:03:06+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Wish I could offer some help. I'm surprised nothing has been found with Japanese blogs, as I recall it took a tool created by someone in Japan to extract the movie files from DoC.
## Post #31
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-03-11T04:56:56+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

From vertices dump of 3200b000.dat,,,it's shape look like part of street,not character.



you can check it by following script yourself:P

```
caption:"Model File" \
types:" Model File(*.dat)|*.dat" \

f = fopen fname "rb"
fsize = getFileSize fname
clearlistener()

Vert_array = #()
Normal_array = #()
UV_array = #()
Face_array = #()
print "file size check"
print fsize

c = 0
fseek f 160 #seek_cur
while c != 1 do (
  sig1 = readlong f #unsigned
  sig2 = readlong f #unsigned
  sig3 = readlong f #unsigned
  sig4 = readlong f #unsigned
  
  cur_pos = ftell f
  
  if sig1 == 2 do(
    	
	vx = readfloat f
	vy = readfloat f
	vz = readfloat f
	unknown1 = readfloat f
	append Vert_array[vx,vy,vz,unknown1]
  
  )----if sig1 = 2
  
  if cur_pos >= (fsize - 64) do (
    c =1
  )----if cur_pos >= (fsize - 64)

)---- while c != 1

print Vert_array.count
--print Vert_array

msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = Vert_array.count
buildTVFaces msh
--for j = 1 to UV_array.count     do setTVert  msh j UV_array[j]
--for j = 1 to Face_array.count   do setTVFace msh j Face_array[j]
--for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]
--convertTo msh PolyMeshObject



gc()
fflush f
fclose f


```
## Post #32
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-03-11T10:35:56+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

^^ I missed that  Yeah, it does look like a street. Looks as if you've found part of map. Hard to tell from just verts lol.

@Cloud452 Yeah, that's just movies. Standard format, can be extracted from any game that uses it.
## Post #33
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-03-11T11:43:39+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

A littele progress for "MOD" data.
Please look the red rectangle in the picture.


you can see ,,data pattern changes once it meet this kind of signature
hex 00 00 00 00 xx 00 yy zz

xx is the data counter,in the picture i posted,it's value shows 53(dec)
Then I found each data section's lengh is 6 bytes.
So if you multiply 53 by 6,,result is 318(dec) ,then you offset current postion by 318.you will find another 00 00 00 00 xx 00 yy zz signature.

6 bytes for each one,,it's not likely  half floats,,or it only can save 3 values..it likely to be kind of compression method .

you can see each of the section has big difference in their value,so i assume each of them must be manipulated by differnt decompress operation.
But,,besides "data counter" there seems to be no index or something else help to figure out which kind of "operation" it should use to decompress the data in each section.
## Post #34
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-03-14T10:51:12+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

i really hope that MrAdults gonna help us extracting the model
## Post #35
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-03-19T14:51:21+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Flat mesh captured by Game Assassin,,it's assembled by 1275 small pieces of small objects,,
If you use GA,it will give you non-back cull mesh,,,UV seems okay,,,but you know this is not the best way,the model will distorted a bit.And it's not t-posed.
I will keep trying and digging,,please let me know if anyone find useful information,thx:)
## Post #36
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-03-19T14:55:08+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

I'm glad people are still interested in this  

I've managed to get some mesh with 3dvia before, but it was flat with parts missing. You can stretch it out so it's right again though. There's no uv's with them either.

3dRipperDX can get uv's, but no mesh. Heh...
## Post #37
- Username: Cloud452
- Rank: veteran
- Number of posts: 91
- Joined date: Sat Oct 23, 2010 9:50 pm
- Post datetime: 2011-03-19T20:30:59+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Always happy to see some progress, falconcool!
## Post #38
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-03-21T04:04:21+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

thats no good, the game cull and faces not seen by the front facing camera..

whats the status on getting the game files dumped?
## Post #39
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-03-21T07:35:42+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

PCSX2 r3878, Zero GS plugin
rename D3DX9.mod into D3DX9.dll  and place it into your emulator's executable folder.(If the GA flag doesn't show up).
sample i captured is here
[http://www.sendspace.com/file/pw90l0](http://www.sendspace.com/file/pw90l0)

This is my GA setting
## Post #40
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2011-03-21T20:54:11+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

> Reply from falconcool
>
> PCSX2 r3878, Zero GS plugin
rename D3DX9.mod into D3DX9.dll  and place it into your emulator's executable folder.(If the GA flag doesn't show up).

Hi my friend falconcool, I don't know if this will help you but "3dhobby" post this image in the darkmatter forum looks like he have the bonus material of the game (the "model viewer")
[yuffie.png](https://xentaxbackup.github.io/file/4089_yuffie.png)
## Post #41
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-03-21T21:03:09+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

That is interesting.

@Mario we still don't have a proper file dumper.
## Post #42
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-03-21T23:34:15+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

[/quote]

Hi my friend falconcool, I don't know if this will help you but "3dhobby" post this image in the darkmatter forum looks like he have the bonus material of the game (the "model viewer")[/quote]

Thanks,,would you give me the link please?I can't find it in darkmatter2,,
Darkmatter1 seems disappeared.
He must find the way to null out the animation like mario did in Xenosaga3.
## Post #43
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-03-22T00:00:18+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

oh so its impossible to extract the model from archive
## Post #44
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-03-22T14:09:07+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Falconcool here:

[http://darkmatter2.gamersjudgement.com/ ... st&p=16210](http://darkmatter2.gamersjudgement.com/index.php?showtopic=2587&view=findpost&p=16210)

If you can't read it, i'll quote:

> I have ripped Yuffie but it miss the UV.
>
> 
>
> If someone know a tool for transfer UV it will help me a lot.
>
> 
>
> Edit:I have found a way (for the face at least)
## Post #45
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-03-22T21:49:19+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

[quote="ultimaespio"]Falconcool here:

[http://darkmatter2.gamersjudgement.com/ ... st&p=16210](http://darkmatter2.gamersjudgement.com/index.php?showtopic=2587&view=findpost&p=16210)

If you can't read it, i'll quote:

[quote]

Thanks ultimaespio:)
## Post #46
- Username: Cloud452
- Rank: veteran
- Number of posts: 91
- Joined date: Sat Oct 23, 2010 9:50 pm
- Post datetime: 2011-03-23T00:24:07+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Wow... I wonder how far away we are from a full method to rip the models, UVmaps and textures intact....
## Post #47
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2011-03-23T08:20:42+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

> Reply from falconcool
>
> 

Thanks,,would you give me the link please?I can't find it in darkmatter2,,
Darkmatter1 seems disappeared.
He must find the way to null out the animation like mario did in Xenosaga3.

> Reply from ultimaespio
>
> Falconcool here:
http://darkmatter2.gamersjudgement.com/ ... st&p=16210
If you can't read it, i'll quote:

My bro' Falconcool sorry for the late answer and thanks to ultimaespio, Dirge Of Cerberus and xenosaga 3 have one thing in common the internal model viewer, i don't have the game to test it but as you see it possible rip the models in this way.

Let me know if I can help you with something else..

Best regards
## Post #48
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-03-23T09:58:16+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

I talked a bit with 3dhobby,,there still have some problems with Game Assassin,but we're working on it.In the mean time,I found another type of "MOD" file,,i really feel this could be part of character.

file is here,
[http://www.sendspace.com/file/nn6rtq](http://www.sendspace.com/file/nn6rtq)

When using offzip,,it only decompress about 500 files each time,you have to assign the offset value yourself to extract the next 500 files,,
this file is extracted from kel.dat,,about 75% from begining.
I'm working on it:)
## Post #49
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-03-23T10:01:47+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Cool beans 

It would be easier with a proper extractor. Does offzip give filenames and extensions? When I last ripped, I only got hundreds of .dat files.
## Post #50
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-03-23T10:11:37+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

> Reply from ultimaespio
>
> Cool beans 

It would be easier with a proper extractor. Does offzip give filenames and extensions? When I last ripped, I only got hundreds of .dat files.

i think it's file name come from it's offset value,,the file name probablly saved in filelist.bin,,you can use offzip to extract this file,,you will see lots of strings in the files it extracted.
But,,i think offzip extracted correct extension names,,like mod,,evm,,,,you can check them yourself.
## Post #51
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-03-24T04:40:58+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Although GA is hard to use,but i got few information from it's shader information.

1st,,this is the model i ripped with GA,,


now,,please look it's rendering method,,Tri-list,,but not sure  how raw index data stored.



Next,,vertex data,,please look these values,,only x,y are changing,,but z-values are the same.


Now,,compare the possible "MOD" file we have found..I think"bmd" has possiblity to be mesh files.


I didn't touch it because i thought it's values are too regular,,was wondering it's building models(rectangle shape).
## Post #52
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-03-25T14:41:06+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Good news guys,,I found where the model stored.
Try look the header has "smd" string.
No encryption,simple 4 bytes little endian floats,I use cheat engine to modify the file loaded into ram,,
The first kind "mod" i mentioned with strange array in the front is the animation or bone data.because when i messed around with it's header values,,animation length and bone shape changed.

I modified some floats in the ram in the "smd" part,,and this happened,,no doubt it's model data!!



So,,forget about the first one,,let's just search "smd"part,,It's very close now!!!,thanks for you guys provided lots of valuable informations!!!
## Post #53
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-03-25T14:44:02+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Good Job  Well done, I mean really well done
## Post #54
- Username: Cloud452
- Rank: veteran
- Number of posts: 91
- Joined date: Sat Oct 23, 2010 9:50 pm
- Post datetime: 2011-03-25T22:56:55+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Huzzah for progress!
## Post #55
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-03-26T00:22:10+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

i hope MrAdults gonna help you extract the model
falconcool since you've gone this far how about asking help from MrAdults,i think MrAdult can help you extract the model since MrAdult create a lot of model extractor for a lot of game
## Post #56
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-03-26T10:58:12+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

This is the pattern I found today,,


```
 0x4  float data 00 80 xx 60  ,xx is float count
  ----xx floats data(these floats affect vertex location,seems to be z-direction offset value here)
 0x4  unknown data 01 80 yy 6E ,yy is section count,,each section is 4 bytes
  ----yy 4 bytes data(only the 4th byte affect the vertex location,,the 1st- 3rd byte doesn't affect location or UV,,very strange here)
 0x4  unknown data 00 80 zz 79,zz is section count,each section is 4 bytes
  ---- zz 4 bytes  data(This part is related to face normal)
 some unknown data in the end


```


I tried to modify the 2nd and 3rd type of data's value,and found they affect the location of vertex too,,I don't figure out it's type yet,,not sure if it's offset value or it's original coordinate .

I don't know if Mr Adult interested with this game,but I'm sure  his help can help us to get the models sooner. I won't blame him if he doesn't help,,this kind of format really sucks><
I'll try to do what i can.
## Post #57
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-03-28T12:36:01+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

I spend some time to modify the floats in the 1st section.
I found something maybe useful,,if you try to move the first float after the signature (hex: 00 80 xx 60) in each section..You will find the vertex moved,,but towerd different direction for each different section.
So it means,,each section probablly uses different coordinate system..Probablly like Soul Calibur 3 ,,
Or,,there should be an unit vector to show it's direction if the 1st section floats are offset values.
I feel sick about this kind of format;;

here is the example,,you can see 2 vertices offseted tower 2 different directions ;/


more vertices modification test,,


you can see all of the floats seems "originates" from same point,very interesting ,this should be kind of clue
## Post #58
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-03-29T03:03:13+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

The coodrdinate stored at type 3,,same compression method as FF13,FF14.

I've dumped some visible shapes:)

Type 3 section update

```
Short / 32768.0 ---- x coordinate
Short / 32768.0 ----y coordinate
Short / 32768.0 ----z coordinate


```


extracted mesh is located at axis origin,have to scale/offset them into their correct location,working on it!!

[Uncompeleted] maxscript of vertex dumper,,you have to assign type1 offset value manually for each section.Still not imply offset and scale factor

```
caption:"Model File" \
types:" Model File(*.dat)|*.*|" \

f = fopen fname "rb"
fsize = getFileSize fname
clearlistener()

Vert_array = #()
Normal_array = #()
UV_array = #()
Face_array = #()
print "file size check"
print fsize

fseek f 0x2600 #seek_set ------you have to assign address offset manually for each section.

float_array = #()
vx_array = #()
vy_array = #()
vz_array = #()
type2_array = #()
type3_array = #()

sig1 = readshort f
data_count1 = readbyte f #unsigned
sig2 = readbyte f

for i =1 to data_count1 do( 
 
 ukn_f = readfloat f
 append float_array[ukn_f,0]
  
)----for i = 1 to datacount1

sig1 = readshort f
data_count2 = readbyte f #unsigned
sig2 = readbyte f

for j = 1 to data_count2 do(
  
  t2x = (readbyte f #signed)  
  t2y = (readbyte f #signed)  
  t2z = (readbyte f #signed)  
  
  t2fac = readbyte f #unsigned as float
  
  --t2x /= t2fac
  --t2y /= t2fac
  --t2z /= t2fac

  append type2_array[t2x,t2y,t2z]

)----for j = 1 to data_count2

sig1 = readshort f
data_count3 = readbyte f #unsigned
sig2 = readbyte f

for k = 1 to data_count3 do(
  
  t3x = (readshort f #signed) / 32768.0 
  t3y = (readshort f #signed)  /32768.0
  t3z = (readshort f #signed)  /32768.0
  
  append Vert_array[t3x,t3y,t3z]

)----for k = 1 to data_count2

print Vert_array
type3_array
msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = Vert_array.count
buildTVFaces msh
--for j = 1 to UV_array.count     do setTVert  msh j UV_array[j]
--for j = 1 to Face_array.count   do setTVFace msh j Face_array[j]
--for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]
--convertTo msh PolyMeshObject
msh.scale = [100,100,100]



gc()
fflush f
fclose f


```
## Post #59
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-03-29T10:27:04+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Great  

You mind uploading a sample file please? I don't have any to test it with. Thanks.
## Post #60
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-03-29T11:36:26+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

2 of them,,one is extracted by offzip,the other is dumped from ram.
plese help to find out remaining unknown pattern
1.correct offset and scale value
2.face index 
3.UV,
thx:)

[http://www.sendspace.com/file/aevqvb](http://www.sendspace.com/file/aevqvb)
## Post #61
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-03-29T11:39:52+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

I'd like to but I haven't a clue about any of it, sorry :/

If there's some kind of tutorial on cracking this stuff, I'd give it a try.
## Post #62
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-03-29T11:51:40+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Try type2,,4 bytes stuff,,the 4th byte looks like to be kind of index,,,1st-3rd could be UV or offset,,i'm testing,,,try "readbyte #signed /256.0" to convert interger into float.
## Post #63
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-03-29T11:54:58+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

I'll try what you were doing with pcsx2 and cheat engine. Only thing is, I don't have a save with the model viewer unlocked. I'll have to find one somewhere.

EDIT: Got a complete save, but the Character viewer is empty. There's no action replay codes to unlock it either.

I'm using the eu version btw.

Edit: got it working. Found Yuffie's mesh file, changed one value and it crashed. Ooops.

Edit 2: found a way to disable objects. There was a string that went 94 01 at the start of the file. I changed the 01 to 09 and...



Note that the reason she has so many arms is because of the graphics plugin lol

EDIT 3: Think i've found uvs. find [ebragd]] in the file, and they are round about there. I changed DE 03 0C to DE 99 0C and Yuffie's left sock turned brown.
## Post #64
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-03-30T08:30:31+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Still no luck with UV ,offset,face index and normal,,but i updated my script a bit..It can dump all sections has the signature i mentioned.here is the preview of the result,,it already showed the contour of the face
## Post #65
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-03-30T12:08:55+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Cool  I wonder who that model is?

It looks like a highpoly model going by the face.

I've just thought, this game was released round about the same time as FF12 wasn't it? Do you think they'd use a similar format? Probably just talking out of my butt here.
## Post #66
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-03-30T12:32:59+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

It's part of Shalua Rui's model,,If I remember her name right,:P
FF12's floats are all visible,,the common point is both of the game seperate the models into 
dozens of very small pieces .They're stick together in the center of the head,so it looks still messy
in the picture.
## Post #67
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-03-30T12:35:35+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Oh, I see. Do you think we should ask someone to help us with this?
## Post #68
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-03-30T12:48:01+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

I think this is an open thread to the public,,people who interested with this game will help if they
find something useful(at least I hope so),,It's not necessary to ask someone's help.Although I really hope more ppl join this thread .It will be much more efficient with mutiple ppl join this thread to crack this format..So go ahead if you know someone interested with this game.But don't force them to do this.


pattern updata

```
0x4  float data 00 80 xx 60  ,xx is float count
  ----xx floats data(these floats affect vertex location,seems to be kind of scale factor)
0x4  signature 01 80 yy 6E ,yy is vertex count,,nx = readbyte / 256.0,ny = readbyte / 256.0,nz =readbyte / 256.0 ,unknown = readbyte
0x4  signature 00 80 zz 79,zz is vertex count,each section is 6 bytes
  ---- vx = readshort /32768.0 ,vy = readshort /32768.0,vz =readshort /32768.0
some unknown data in the end(not always exit,,searching pattern atm)

```
## Post #69
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-03-30T12:57:53+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Oh nonono I wouldn't force anyone into it no. Definitely not.
## Post #70
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-03-30T23:49:50+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Ask MrAdults i think he will help you with the model
## Post #71
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-03-31T14:48:40+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

What have I done? lol
## Post #72
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2011-04-01T17:18:12+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

> Reply from falconcool
>
> pattern updata
Code: Select all0x16 signature of data starting 00 00 00 20 C0 C0 C0 C0 02 01 00 01 00 00 00 00
0x4  float data 00 80 xx 60  ,xx is float count
  ----xx floats data(these floats affect vertex location,seems to be kind of scale factor)
0x4  signature 01 80 yy 6E ,yy is vertex count,,nx = readbyte / 256.0,ny = readbyte / 256.0,nz =readbyte / 256.0 ,unknown = readbyte
0x4  signature 00 80 zz 79,zz is vertex count,each section is 6 bytes
  ---- vx = readshort /32768.0 ,vy = readshort /32768.0,vz =readshort /32768.0
some unknown data in the end(not always exit,,searching pattern atm)
nearly that you are burning, also to help a little 0x79 one is the normals   
0x60 is vertex weighting 
0x6e is vertex
0x65 seems to be uv's

this is ps2 giftags, also thoses giftages can change according to the first byte that can be 0x00, 0x01 ,0x02,0x03 etc...
## Post #73
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-04-01T23:02:29+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Thank you Codeman,that helps much,I'll rewrite my maxscript.
This is the header information i found


Watch the blue rectangle in the picture.It's value is
0x 05 00 00 00 25 49 52 40 E0 03 00 00 10 00 00 00
This part is very tricky,
the first 4 bytes long,,0x 05 00 00 00 ----this is the counter of the signature of data starting( 0x 00 00 00 20 C0 C0 C0 C0 ......,16 bytes stuff),,Remember there is sometimes addtional data behind 0x00 80 zz 79? When "signature count" meet this value,,the first section of "additional data" appear.
In the picture,the value is 5.

the second float is general scale factor,I tested in the emulator with cheatengine.This factor scale each mesh in the file. in this case,the value is 0x 25 49 52 40,,decimal value is 3.2857144

the 3rd long is offset value from the 1st byte of the "blue rectangle" in the picture to the first"additional data" ,in this case,the value is 0x E0 03 00 00,,decimal value is 992

the 4th long is unknown for now.
## Post #74
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2011-04-02T23:26:24+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

> Reply from Cloud452
>
> Wow... I wonder how far away we are from a full method to rip the models, UVmaps and textures intact....

Are you talking about the 3d capture method? There is a way but i'm NOT sure if it will work in this game

> Reply from inferry
>
> 
So, in resume:
-Get mesh from 3Dvia
-Get UV from 3Dripper
-Pass UV to mesh.
-Find a way to correct perspective issue.
-Rig.
-Export.
-Eat a donut.
-Upload archive here.
## Post #75
- Username: LynMs
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 03, 2011 9:29 am
- Post datetime: 2011-04-03T03:11:22+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

If you could give me any pcsx2 state of preservation, it might freeze, because the result may be a few million is a good thing, because the file will not be compressed. This will save me some time to drive to the library to pick it up only to find its compression,
## Post #76
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-04-03T08:52:20+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Pattern about those "addtional data" offseted from 1st byte of blue rectangle.


It's 8 bytes in each section. size always be "signature number"(first long) x 8 bytes.
Each 8 bytes stores data as 4 short...
I will say the first short is kind of index,,because it's constantly increasing.
The 2nd to 4th shorts in each section can be float,,I am guessing it's offset value of each vertex chunk.short(signed) / 32768.0,,,testing now.

Edit,,nope,,these values are not offset of each vertex chunk.
## Post #77
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-04-04T00:46:20+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

I think i found face index.It looks like Tri-strip array.
3 more signatures(or tags) pattern update:

```
0x 02 01 00 01 03 C0 aa 6E :
Data type,4 bytes for each section,,always be 0x 7D 7D 7D 80,aa is section count
Maybe padding?

type 5:
0x 02 01 00 01 02 80 bb 65 :
Data type,4 bytes for each section,bb is section count,according to Modman's vif tag data,,this part could be UV.

type 6:
0x 02 C0 cc 72 :
Data type,1 bytes for each section,cc is section count.Great chance this is face index,looks like tri-strip.

```
## Post #78
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-04-05T12:17:28+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

These are all the data patterns,i think.
The remaining problem.
1. maximum vertex index  value in face index arrayis less than total vertex count .I can't find out additional vertex look like bounding box to offset the mesh.Could some of the vertex stick together need to be welded?

2.Can't find the correct offset value for each vertex chunk.Will try to dig skeleton part later.

3.Codeman..I don't think those tags you posted are the same for this game.
0x60 ,,pretty sure this is normal.try calculate those value,,you will find they all have the same distance from origin,,all unit vectors.

0x79 ,,This is the vertex coordinate,I've extracted visible shapes of vertex from this section.

the first 4 bytes floats,,i don't think they are weights either,,When you change it's value in cheatengine,,models vertex moves just like "scaled" but wrong "weighted"
## Post #79
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-04-05T12:20:40+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Would that put the verts into the correct places, instead of being randomly scattered about?
## Post #80
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-04-05T12:45:29+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

> Reply from ultimaespio
>
> Would that put the verts into the correct places, instead of being randomly scattered about?

Here is the list of the data which affects the model's location.
1. 0x 00 80 aa 60 --aa floats.----these floats are kind of scale factor of the vertex.
2.0x 01 80 bb  6E-- the 4th byte affect vertex location,,don't have rule..if you change this value..the vertex will go very far out of screen or game crash.
3. 0x 00 80 cc 79 --- these are original vertex from the origin(0,0,0)
4.additional data  ---not figure out this part yet,,,but the 2nd-4th short cause model to change shape.

well,I suggest you try to multply divide,add.subtract the values of 1,2,4,try whatever possible calculation,,and find out if the resulting value is the correct offset.
## Post #81
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2011-04-05T14:31:12+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

ps2 vif tag are very tricky to handle solely on a visual basis if you do not take all the commands and flags into account.

For instance the "patterns" you are seeing of this form:

```
04 04 00 01
04 01 00 01

```

are set cycle commands.  The specify how often values are either read or written into memory.  As an example:

```

```

would cause a value to be written ever other line (of 16 bytes).

```

```

would cause a value to be written ever 4 lines.  And there are various other combinations.

The command that causes execution of the current set of vif commands after transfer is:

```

```


The "patterns"

```
## C0 ?? 7*

```

etc, specify an unpack command, where:
## is the address to store the unpacked data that follows, specified in multiples of 16-bytes (qwc, quad word count)

80/C0 is actually a set of flag bits where 0x80 is flg, and 0x40 specifies whether a value should be treated as signed or unsigned

?? is the number of values to unpack

6/7 is the actual unpack command specifier, but the full structure contains a flag specifying whether the unpack is masked or not (which just happens to be in the 1's position which is why the 6 becomes 7 in the full structure)

* is actual a combination of two 2-bit values, vn, and vl (each possible to be 0 - 3)
vn - is the number of components
vl - is the data type of the components
where:

```
- 0 is 1-component
- 1 is 2-components
- 2 is 3-components
- 3 is 4 components
vl
- 0 are 32-bit values
- 1 are 16-bit values
- 2 are  8-bit values
- 3 are rgb5a1 values (16-bit)

```


As an example
6E: the E is actually a combination of 0x0C and 0x2, or 11 10, which is vn = 3, vl = 2.  So this means each component has 4 values that are 1-byte each
6C: would then be 0xC and 0x0, 11 00, vn = 3 vl = 0, So each component would be 4 32-bit values.

Using this information you can determine the size of the data that follows the unpack command:
C would be four (4) 32-bit (4-byte) values, or 16-bytes total per complete value.  If the number of values specified by ?? is 0x2E (46), then 46 * 16 = 736 (0x2E0) bytes of data.
9 would be three (3) 16-bit (2-byte) values, or 46 * 6 = 266 (0x114) bytes of data.

This can be used to help determine what some data can be, at least initially.  In the case of E this could possibly be rgba color values.  But not this does not have to be the case, it can be any type of value that can be store in 4 8-bit values.
In the same way C could be any set of four 32-bit values.  If they happen to be valid floats, it could possibly be a vertex, but at the same time you could use this same format to store non-float values, or a set of float values that make up a matrix.  But again it can be any data that technically fits within the data size computed from the component type and counts.

Masking can also affect the way data is stored.  There are a number of storage rules for taking things like this into account, as well as ones that modify how values are manipulated before and after they are read.

After unpacking, the data can look a bit different depending on how the developer chose to store things.  Often you can see another complete set of structures which themselves could be interpreted as offsets, counts, etc. in much the same way as the original containing format may have been.

There are a number of games which use these tags, and once understood become a good bit easier to deal with, at least initially.

The values above are a bit of a rough estimate as well, since the actual bits of the structure can possibly cause the commands to look a bit different should those features be used.  Actual documentation on the commands would go further into detail on these subjects.

```
{
	struct
	{
		uint16 imm;
		uint8  num;
		uint8  cmd : 7;
		uint8  stl : 1; // interrupt flag
	} commnd;
	struct
	{
		uint8  cl;
		uint8  wl;
		uint8  num;
		uint8  cmd : 7;
		uint8  stl : 1; // interrupt flag
	} stcycl;
	struct
	{
		uint16 adr : 10;
		uint16 pad : 4;
		uint16 usn : 1;
		uint16 flg : 1;
		uint8  num;
		uint8  vl  : 2;
		uint8  vn  : 2;
		uint8  m   : 1;
		uint8  cmd : 2;
		uint8  stl : 1; // interrupt flag
	} unpack;
};

```


Hope that helps for now.


Did not know where to post this since it can apply for any ps2 format which uses these commands.
## Post #82
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-04-06T02:07:43+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

I found the offset value,3 normal 4 bytes floats,It's stored in the skeleton data..
So ,it means we have to assemble the skeleton first.
Here is the prove,


Here is the skeleton(t-posed) dumped from ram
[http://www.sendspace.com/file/atcv12](http://www.sendspace.com/file/atcv12)
## Post #83
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-04-06T20:46:03+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Skeleton data pattern


Only one pattern in this kind of data.Still have unknown values,,but this is what i found.

```
4 bytes long bone index
12 bytes unknown
64 bytes transform matrix1
4 bytes long parent bone index
12 bytes unknown
3x4 bytes float : x,y,z offset value.
4 bytes unknown.
16 bytes unknown :4 floats?

```


Edit1 : the first short of "addition data" in the mesh should be the bone index.
## Post #84
- Username: Cloud452
- Rank: veteran
- Number of posts: 91
- Joined date: Sat Oct 23, 2010 9:50 pm
- Post datetime: 2011-06-03T15:23:26+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Any new progress?
## Post #85
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-07-28T13:54:37+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Hey guys, it's been a while.

Any new progress? We're so close to getting something now, it would be a shame to stop.

I might go and mess with cheat engine again to see what I can find. Hope someone helps
## Post #86
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-10-09T02:30:13+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

I find interesting values in those "additional data chunk"
look the orange and blue rectangles i marked,,these values seems to be 4 "bits"values,,not hex short,
and they're paired,please look the picture below.


and,,i read the gif tags again,i have few questions.
for example
i find 0x0080##60  -----seems to be weight,   6/7 said to be masked tag.
  Can anyone explain how masked stuff working here?
thx.
## Post #87
- Username: Trishty
- Rank: advanced
- Number of posts: 63
- Joined date: Mon Jul 05, 2010 9:37 pm
- Post datetime: 2011-10-09T11:54:00+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

I want to ask you this falconcool.
I have saw the image in page 3 that you can rip model use GA and page 4 you can make model in T-pose. Can you rip this model?
I have try use GA to rip but i alway fail, these file can't import
## Post #88
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2011-10-09T14:27:53+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

> Reply from Trishty
>
> I want to ask you this falconcool.
I have saw the image in page 3 that you can rip model use GA and page 4 you can make model in T-pose. Can you rip this model?
I have try use GA to rip but i alway fail, these file can't import

GA only rips back-cull meshes in this title,vertex index changed for each ripped model,it's useless unless you want use them to build new models from scratch.
The information of how to get t-posed one was in my darkmatter's forum pm,since Mario closed it,and i forgot to write it down,,so it gonna take a while to find out how to get t-pose again.
It's done by Cheatengine,good luck
## Post #89
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-10-09T17:27:02+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Great, some progress again  

Sorry Falconcool, I read your PM and forgot to reply :/
## Post #90
- Username: Trishty
- Rank: advanced
- Number of posts: 63
- Joined date: Mon Jul 05, 2010 9:37 pm
- Post datetime: 2011-10-10T08:47:37+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Thanks for these information falconcool, I think i can make a model with 2 side front and back rip by 3dripperdx
## Post #91
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-02-15T23:25:35+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

bump

looking for tools etc to get the files, some thigns were linked to megaupload (now gone)


if you can give me a summary of the project status, I'll have a look into the format this weekend  (long weekend for us canadians)
## Post #92
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2012-02-16T15:43:00+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

The contents of this post was deleted because of possible forum rules violation.
## Post #93
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-02-16T21:41:30+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

got more samples?

theres really only 2 in there.

one is is different then the other, looks like one is a container full of other sub files?

edit
..nevermind that was a container it pops out like 10 other small mesh files
## Post #94
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2012-02-16T22:10:01+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

No, sorry. They were the only ones that Falconcool uploaded.

I think he just used Cheatengine to extract some of them.
## Post #95
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-02-17T03:19:00+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

The contents of this post was deleted because of possible forum rules violation.
## Post #96
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2012-02-18T21:50:29+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Just thought, Furryfan said that you can get the models from within a savestate...do you think we'd be able to just get the models that way? Might be easier, might not :/
## Post #97
- Username: kaspar
- Rank: n00b
- Number of posts: 15
- Joined date: Wed May 04, 2011 1:43 am
- Post datetime: 2012-04-28T11:10:58+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

> Reply from falconcool
>
> Hi gentlemen,,I found a  way to extract the container.
There is a filelist.bin in disk's parent directory,it let me think of ff13's container structure.
I viewed both of the filelist,,they're the same structure in hexeditor.
So i used aluigi's bms script of ff13 to open it,,1st time,it failed,,then i rename
filist.bin into Filelist_scru.x360 ,and rename KEL.DAT into White_scru.x360,,

Haha aluigi's script extract everything!!!

This didn't work for me (not whith those names) so I made some attempts and finally got it!

Now I want to share my method to this great community that helped me a lot in past (thx guys you're great    )

Here how I did it (really very similar)

1- take FILELIST.BIN and KEL.DAT (in E419C51B folder) files from the disc and copy them in the SAME folder
2- download quick bms and ff13 aluigi script
3- rename KEL.DAT in white_imgu.x360.bin and FILELIST.BIN in filelist_imgu.x360.bin
4- open quick bms and choose ff13 script then chose filelist_imgu.x360.bin and finally the folder you want to save the extracted files in
5- when will ask if overwrite the data/effect/effect.rfd file type all and let it finish 

that's all!   (I hope this work for who was not able to do it whith fancool method)

Thx to fancool anyway (i could never did it whithout his post    )

P.S. sorry for my bad english I hope there are not too many errors in my explanation
## Post #98
- Username: kela51
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jul 16, 2012 12:06 am
- Post datetime: 2012-07-15T16:14:08+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

hi all i'm new on this forum,i would like to know if you have any news?  

sorry for my english!
## Post #99
- Username: Trishty
- Rank: advanced
- Number of posts: 63
- Joined date: Mon Jul 05, 2010 9:37 pm
- Post datetime: 2012-07-30T13:22:31+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Hi guys! I successful with PCSX2 0.9.9 (Shift+F8 screen capture)

falconcool, I hope you still can make model in T-pose

Tutorial how to rip PS2 models here:
[http://spriters-resource.com/community/ ... ?tid=20541](http://spriters-resource.com/community/showthread.php?tid=20541)
## Post #100
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2012-08-01T16:19:37+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Good Stuff
## Post #101
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2012-08-04T15:37:53+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

That works, but it's still a bit...meh.

There was another guy on the Darkmatter forum that managed to rip Yuffie in a tpose. Dunno how he did it though.

I have a new sample file for Yuffie if anyone wants to take a look at it (You'll have to pm me due to new rules)

The model format is actually .SM2, and the files have names just like Kingdom Hearts and Dissidia. For example Yuffie is: n002_L01.

Hopefully now we'll get somewhere, if anyone wants to take a look.

Textures are also separate files. The header says "texture.txd"
## Post #102
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2012-08-06T21:31:48+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

> Reply from ultimaespio
>
> That works, but it's still a bit...meh.

There was another guy on the Darkmatter forum that managed to rip Yuffie in a tpose. Dunno how he did it though.

I have a new sample file for Yuffie if anyone wants to take a look at it (You'll have to pm me due to new rules)

The model format is actually .SM2, and the files have names just like Kingdom Hearts and Dissidia. For example Yuffie is: n002_L01.

Hopefully now we'll get somewhere, if anyone wants to take a look.

Textures are also separate files. The header says "texture.txd"

Gawd yeah i agree with this... Dirge of Cerberus has such epic models >< 
Too bad the format seems so hard =/ Hope it gets figured out one day
## Post #103
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2012-10-01T10:26:33+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Is this still going on? I'd love to see a Lucrecia model out of all this. You want I should try to use DX Ripper on this to see if it outputs T-Pose?
## Post #104
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2012-12-15T21:35:22+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

I imported Yuffie's skeleton; that's gotta count for something right...?
## Post #105
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2012-12-16T13:14:50+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

NOW We're getting somewhere!
## Post #106
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2012-12-28T17:00:30+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Please release this script!
## Post #107
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2012-12-28T20:33:17+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

What are you going to do with just bone data?
## Post #108
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2013-01-02T02:16:47+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

The textures and models can be captured with PCSX2, but only this importer can extract the skeletons.
## Post #109
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-01-02T11:30:11+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

There is now ps2 vif tag support in noesis. It is only exposed to the dll side of things right now but it is on the roadmap to be added to python. Once it is added into python I should be able to code up a noesis plugin for this.
## Post #110
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2013-01-02T17:48:55+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

OMG please doo *_*
## Post #111
- Username: Mirrorman95
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-01-09T21:40:57+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Noesis 4.03 is out with VIFcode unpacking exposed to Python. Also, if you do the trick of renaming FILELIST.BIN to FILELIST_scru.x360.BIN and renaming KEL.DAT to white_scru.x360.bin, Noesis will extract them with proper filenames and paths. Although the decompressed filelist still uses blank names for lots of the RFD's, they'll still get the right extension.
## Post #112
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2013-01-20T21:49:56+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Does Chrrox know VIF support has been added? Because he hasn't said anything about this since he said "I'll start working on a DoC plugin when PS2 VIF tag support has been added to the Python side of Noesis."
## Post #113
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2013-01-20T21:51:53+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

He likely does, just chill
## Post #114
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2013-02-12T12:01:38+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Well, it's been another month, so I'm assuming everyone's just given up on a Dirge of Cerberus plugin. Then again, there is already a plugin for 3DSmax to extract the Dirge of Cerberus models' skeletons, and one could always rip the models and textures out with GSDX and TexMod, so you could reconstruct any given model from that.  A plugin would just greatly simplify this process, right? I hope I'm not being too rude or ignorant for asking.
## Post #115
- Username: kela51
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jul 16, 2012 12:06 am
- Post datetime: 2013-03-25T17:19:17+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

I hope rip this game can be possible.Thanks for your work on this.
## Post #116
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-04-06T21:16:53+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Well I was going to try out the skinning, but I forgot how it works in Maxscript.   
Maybe someone else can check it out......

( The extension ms is not allowed? )
F*** it, here's the code:

```
fname = getOpenFileName \ 
caption:"Dirge of Cerberus: Final Fantasy VIIl" \
types:"DoC game model(*.*)|*.*" \
historyCategory:"Dirge of Cerberus Presets"
f = fopen fname "rb"

-- 	Wik

-- 	Alsø wik

-- 	Alsø alsø wik

-- 	Wi nøt trei a høliday in Sweden this yer?

-- 	See the løveli lakes

-- 	The wonderful telephøne system

-- 	And mani interesting furry animals


pos=0
MainTableArr=#()
demBones = #()



-- 	The Producers would like to thank The Forestry Commission
-- 	Doune Admissions Ltd, Keir and Cowdor Estates, Stirling
-- 	University, and the people of Doune for their help in the
-- 	making of this film.
-- 	The Characters and incidents portrayed and the names used
-- 	are fictitious and any similarity to the names, characters,
-- 	or history of any person is entirely accidental and
-- 	unintentional.
-- 					Signed RICHARD M. NIXON


fn ReadFixedString bstream fixedLen = (
	local str =""
	for i=1 to fixedLen do (
		str+=bit.intAsChar (ReadByte bstream #unsigned)
	)
	str
)

fn align4 file = (
	ch=ftell file
	msk=0xF
	b1=bit.and ch msk
	case of (
		(b1 >0 and b1 <4): ch+=(4-b1)
		(b1 >4 and b1 <8): ch+=(8-b1)
		(b1 >8 and b1 <12): ch+=(12-b1)
		(b1 >12): ch+=(16-b1)
		default: ch+=0
	)
	fseek file ch #seek_set
)

fn align16 file = (
	ch=ftell file
	msk=0xF
	b1=bit.and ch msk
	case of (
		(b1 != 0): ch+=(16-b1)
		default: ch+=0
	)
	fseek file ch #seek_set
)

fn find4CycleTrimmer file = (
	ch=readlong file
	if ch != 16778244 then
		while ch != 16778244 do (
			ch=readlong file
		)
	fseek file -4 #seek_cur
)


fn store_count file array_arg= (
	fseek file 2 #seek_cur
	count=readbyte f
	append array_arg count
	fseek file -3 #seek_cur
)



-- 	  Including the majestic møøse 

-- 	  A Møøse once bit my sister ...

-- 	  No realli!  She was Karving her initials on the møøse
-- 	  with the sharpened end of an interspace tøøthbrush given
-- 	  her by Svenge - her brother-in-law - an Oslo dentist and
-- 	  star of many Norwegian møvies:  "The Høt Hands of an Oslo
-- 	  Dentist", "Fillings of Passion", "The Huge Mølars of Horst
-- 	  Nordfink".

fn ar_store outArray tmpArray i = (
	d=2^7-1
	case of (
		(i==1): append outArray tmpArray[1]
		(i==2): ( a=tmpArray[1]; b=tmpArray[2]; append outArray [a,b]	)
		(i==3): ( a=tmpArray[1]/d; b=tmpArray[2]/d; c=tmpArray[3]/d; append outArray [a,c,b] )
		(i==4): ( a=tmpArray[1]; b=tmpArray[2]; c=tmpArray[3]; d=tmpArray[4]; append outArray [a,b,c,d] )
		default: append outArray tmpArray[1]
	)
)

fn unpack_to outArray i:vn = (
	--  Usage:		 unpack_to yourArray
	--  Optional:	 unpack_to yourArray i:x 	where x is <= vn
	--  Example:    unpack_to Normal_array i:3
	vn = 0
	addr=readbyte f
	flag=readbyte f
	count=readbyte f
	comm_spec=readbyte f
	vnMSK=0xC
	vlMSK=3
	vna=bit.and comm_spec vnMSK
	vn=bit.shift vna -2
	vn+=1
	if i==0 then i=vn
	vl=bit.and comm_spec vlMSK
	case of (
		(vl==0): (
			for x=1 to count do (
				tmpArray=#()
				for y=1 to vn do ( p=readfloat f; append tmpArray p )
				ar_store outArray tmpArray i
			)
		)
		(vl==1): (
			for x=1 to count do (
				tmpArray=#()
				for y=1 to vn do ( p=readshort f; append tmpArray p )
				ar_store outArray tmpArray i
			)
		)
		(vl==2): (
			for x=1 to count do (
				tmpArray=#()
				for y=1 to vn do ( p=readbyte f; append tmpArray p )
				ar_store outArray tmpArray i
			)
		)
		(vl==3): (
			for x=1 to count do (
				tmpArray=#()
				for y=1 to vn do ( p=readshort f; append tmpArray p )
				ar_store outArray tmpArray i
			)
		)
	)
	vn = 0
)




-- 	We apologise for the fault in the
-- 	subtitles.  Those responsible have been
-- 	sacked.

models=ReadFixedString f 8
rfd=readstring f
fsize=readlong f
tableCount=readshort f-1
unk2=readshort f
for x = 1 to tableCount do (
	mrOffset=readlong f
	append MainTableArr mrOffset
)
skelOff=readlong f


fseek f skelOff #seek_set
SkeletonStart=ReadFixedString f 12	--	skeletonskd
endOfFile = readlong f-1
Off_REL=ftell f
SK2=SM2=ReadFixedString f 4
unk1=readlong f
smdNamesCount=readshort f
unk2=readshort f
namesStart=readlong f
unk3=readlong f
boneCount=readlong f
matrix1Table_Start=readlong f		--	the ones not used by the bones / used for pre-multiplying vertices...?
fseek f (Off_REL + matrix1Table_Start) #seek_set
matrix1Offs=#()
for i = 1 to boneCount do (
	o=readlong f
	append matrix1Offs o
)
fseek f (Off_REL + matrix1Offs[1]) #seek_set

for x = 1 to boneCount do (
	o11 = readfloat f; o12 = readfloat f; o13 = readfloat f; o14 = readfloat f
	o21 = readfloat f; o22 = readfloat f; o23 = readfloat f; o24 = readfloat f
	o31 = readfloat f; o32 = readfloat f; o33 = readfloat f; o34 = readfloat f
	o41 = readfloat f; o42 = readfloat f; o43 = readfloat f; o44 = readfloat f
	thing1=(matrix3[o11,o12,o13][o21,o22,o23][o31,o32,o33][o41,o42,o43])
	
	hash=ReadFixedString f 0x30

	BIndex=readlong f + 1
	unk1=readlong f
	unk2=readlong f
	unk3=readlong f
	m11 = readfloat f; m12 = readfloat f; m13 = readfloat f; m14 = readfloat f
	m21 = readfloat f; m22 = readfloat f; m23 = readfloat f; m24 = readfloat f
	m31 = readfloat f; m32 = readfloat f; m33 = readfloat f; m34 = readfloat f
	m41 = readfloat f * 8; m42 = readfloat f * 8; m43 = readfloat f * 8; m44 = readfloat f * 8
	thing2=(matrix3[m11,m13,m12][m31,m33,m32][m21,m23,m22][m41,m43,m42])
	
	BParent=readshort f + 1
	unk=readshort f
	if BParent == 65536 then BParent = 1
	unk4=readlong f
	BLength=readfloat f
	unk5=readfloat f
	
	rTemp=thing1.rotationpart as matrix3
	newBone = bonesys.createbone	\
	thing2.row4	\
	(thing2.row4 + .01 * (normalize thing2.row1)) \
	(normalize thing2.row3)
	newBone.width  = .01
	newBone.height = .01
	newBone.transform = inverse thing2
	newBone.setBoneEnable false 0
	newBone.wirecolor = yellow
	newbone.showlinks = true
	newBone.pos.controller      = TCB_position ()
	newBone.rotation.controller = TCB_rotation ()
	if (x != 1) then (
		newBone.parent = demBones[BParent]
	)
	demBones[x] = newBone
)
select $Bone001
rotate $ (angleaxis 180.0 [0,1,0])
move $ [0,0,56.0]




for i = 3 to MainTableArr.count do (
	Weights_array=#()
	uv_Array=#()
	vert_Array=#()
	Face_array=#()
	Normal_array=#()
	smallestChunkCounts=#()
	unkLongs=#()
	prettyColors=#()
	unkN1=#()
	unkBytes=#()
	bone_Array=#()
	boneID_Array=#()
	
	fseek f MainTableArr[i] #seek_set	--	SMD
	SMD_start=ftell f
	smdName=ReadFixedString f 12
	nextSMD=readlong f
	nextSMD_loc=(SMD_start + nextSMD)
	SM2=ReadFixedString f 4
	unkCount1=readbyte f
	longNullCount=readbyte f
	unkCount2=readbyte f
	unkCount3=readbyte f
	unk1=readshort f
	mainObjCount=readbyte f
	nullByte=readbyte f
	nullLongA=readlong f
	nullLongB=readlong f
	unk10=readlong f
	unk11=readlong f
	unk100=readlong f
	ThisIsImportantStupid=ftell f
	unk101=readlong f
	unk110=readlong f
	unk111=readlong f
	unk1000=readlong f
	fseek f (longNullCount*4) #seek_cur
	tableArrMajor=#()
	for x = 1 to mainObjCount do (		--	smd sub-objects
		t=readlong f
		append tableArrMajor t
	)
	tempVar = deepcopy tableArrMajor
	deleteItem tempVar 1
	append tempVar skelOff
	for y = 1 to tableArrMajor.count do (
		countArray=#()
		nextSubBlock=(ThisIsImportantStupid + tableArrMajor[y])
		_nextSubBlock=(ThisIsImportantStupid + tempVar[y])
		fseek f nextSubBlock #seek_set
		bonesOff=ftell f
		subObjCount=readlong f		--	sub sub-objects - weights, vertices
		unk1001=readlong f
		boneTableOff=readlong f
		ten=readlong f
		for LillianGish = 1 to subObjCount do (		-- Total babe!
			unkA=readlong f		--	Start		00 00 00 20
			unkB=readlong f
			set_cycle=readlong f
			anotherStupidNull=readlong f
			store_count f countArray
			unpack_to Weights_array
			unpack_to uv_Array
			unpack_to vert_Array
			align16 f
		)
		boneTMP=#()
		boneTMP2=#()
		fseek f (boneTableOff + bonesOff) #seek_set
		for TonyCurtis = 1 to subObjCount do (
			boneID=readshort f
			tempName="bone"
			boneName = tempName + formattedPrint boneID format:"#03u"
			something=readshort f
			somethingElse=readshort f
			YoMamma=readshort f
			append boneTMP boneName
			append boneTMP2 boneID
		)
		n=0
		for a in countArray do (		--	store Bone ID for each vertex?
			n+=1							--  this seems like the wrong way of going about it.......??????? 
			for b = 1 to a do (
				append bone_Array boneTMP[n]
			)
		)
		
--		******************
--		SMALLEST CHUNKS
--		******************
		
		--find4CycleTrimmer f --	skip ahead a few bytes to start of smallest chunks ( 04 04 00 01 )
		
-- 		( currently commented out until someone finds something useful to do with the data )
		/*while (pos < _nextSubBlock-64) and (pos < nextSMD_loc-64) do (
 			pos=ftell f
			fourCycleTrimmerShindaiwa=readlong f
			unpack_to unkLongs
			twoCycleTrimmerToro=readlong f
			unpack_to prettyColors
			twoCycleTrimmerCraftsman=readlong f
			unpack_to unkN1
			unpack_to unkBytes
			align4 f
			end=readlong f	--	00 00 00 17
			ch=readlong f		--  check for set cycle command - sometimes there's 0x20 bytes between chunks
			if ch==0 then (align16 f; fseek f 0x20 #seek_cur)
				else fseek f -4 #seek_cur
		)*/
	
	)
	msh=mesh vertices:Vert_array faces:Face_array
	msh.numTVerts=Vert_array.count
	select msh
	rotate $ (angleaxis 180.0 [0,1,0])
	move $ [0,0,56.0]
-- 	buildTVfaces msh
	
	
-- 	max modify mode
-- 	skinMod = skin()
-- 	addModifier msh skinMod
-- 	modPanel.setCurrentObject skinMod
-- 	
-- 	for i = 1 to  bone_Array.count do (
-- 		maxbone = getnodebyname bone_Array[i]
-- 		skinOps.addBone skinMod maxbone 1
-- 	)
-- 	
-- 	for j = 1 to Vert_array.count do (
-- 		skinOps.ReplaceVertexWeights skinMod j bone_Array[j] Weights_array[j]
-- 	)
	
	msh.name=smdName
)

/*
--   Mynd you, møøse bites Kan be pretty nasti...

--   We apologise again for the fault in the subtitles.  Those
--   responsible for sacking the people who have just been sacked
--   have been sacked.




--   Møøse trained by				TUTTE HERMSGERVORDENBROTBORDA

--   Special Møøse Effects		OLAF PROT
--   Møøse Costumes				SIGGI CHURCHILL
--   Møøse Choreographed by      HORST PROT III
--   Miss Taylor's Møøses by     HENGST DOUGLAS-HOME
--   Møøse trained to mix
--   concrete and sign com-
--   plicated insurance
--   forms by						JURGEN WIGG
--   Møøses' noses wiped by		BJORN IRKESTOM-SLATER WALKER

--   Large møøse on the left
--   half side of the screen
--   in the third scene from
--   the end, given a thorough
--   grounding in Latin,
--   French and "O" Level
--   Geography by					BO BENN

--   Suggestive poses for the
--   Møøse suggested by			VIC ROTTER
--   Antler-care by				LIV THATCHER




--   The directors of the firm hired to
--   continue the credits after the other
--   people had been sacked, wish it to
--   be known that they have just been
--   sacked.
*/







fclose f






/*
Executive Producer
        JOHN GOLDSTONE & "RALPH" The Wonder Llama

  EARL J. LLAMA
  MIKE Q. LLAMA III
  SY LLAMA
  MERLE Z. LLAMA IX
  Directed By
  40 SPECIALLY TRAINED
  ECUADORIAN MOUNTAIN LLAMAS
  6 VENEZUELAN RED LLAMAS
  142 MEXICAN WHOOPING LLAMAS
  14 NORTH CHILEAN GUANACOS
  (CLOSELY RELATED TO THE LLAMA)
  REG LLAMA OF BRIXTON
  76000 BATTERY LLAMAS
  FROM "LLAMA-FRESH" FARMS NEARE PARAGUAY
*/
```
## Post #117
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2013-04-10T18:09:09+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

This is a 3DS Max script for importing Dirge of Cerberus models, sans UVs?
## Post #118
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-04-10T18:37:59+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Well, sans almost everything actually.  ಥ_ಥ
But by God all the offsets are in there and it parses the data pretty quick! ┌( ಠ_ಠ)┘
## Post #119
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2013-04-15T18:56:08+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

So what does it actually do then?
## Post #120
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-04-16T03:16:18+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

It'll import the skeleton and all the vertex data.
Like I said, I was going to try skinning the vertices to the bones and see what happened, but I forgot how the skinning code works and got busy trying to keep the weeds from taking over my yard and then my allergies went nuts and almost killed me to death.   

Here's some more random junk:
These are the bone-vertex assignments. You can look at the skeleton in Max, pick a bone, then using Cheat Engine + PCSX2 change one of those values and predict, with 100% reliability, what will happen i.e., what bone those block of vertices will reattach themselves to.


Also, like I mentioned in the code, those other matrices in the skeleton data have their own offset table which would imply they're pretty important. Wasn't sure if the verts need to be pre-multiplied with those or not.
## Post #121
- Username: kela51
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jul 16, 2012 12:06 am
- Post datetime: 2013-05-08T13:10:05+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

work in progress
## Post #122
- Username: kela51
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jul 16, 2012 12:06 am
- Post datetime: 2013-06-11T15:47:40+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Sorry but any progress?
## Post #123
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2013-07-02T21:41:30+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Is anyone still working on this plugin, or is Dirge of Cerberus a dead topic?
## Post #124
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2013-07-09T13:52:30+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

I've never really looked at Chaos up close, so not so sure how official this is, but it looks like someone managed to rip it:


[http://www.trishroom.com/threads/chaos- ... rus.36186/](http://www.trishroom.com/threads/chaos-dirge-of-cerberus.36186/)
## Post #125
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-07-09T15:49:33+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

what are you talking about?

> Another model from me give credits if used 
>
> it has bones but no animations yet will be updating him soon (and also Lightning and Noblesse still have to animate them ) Model, Texture, Bones (and animation in the future) are made by me 
>
> 
>
> Chaos ( my favorite  )
## Post #126
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2013-07-09T16:04:56+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Yeah I misread that. Wasn't until I checked the textures to see concept art I realised what he meant.

Anyway, searched for that Yuffie sample I ripped a while ago in the games dump. She's in file13121.rfd, and it seems that the rfd is just a container with the models (SM2), texture animations, something called marker. Looks like there's a few of them in there as well. Yuffie's got 10 of them by the look of things.
## Post #127
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2013-08-14T19:22:51+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

How difficult would it be to complete TheDude's maxscript to support skinning and UVs from the SM2s?
## Post #128
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2013-08-14T20:24:47+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Looks like the old consoles formats are more dificult to figure out than newer consoles or pc games, or is it just me?
## Post #129
- Username: kela51
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jul 16, 2012 12:06 am
- Post datetime: 2013-10-12T16:07:43+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

> Reply from GDL
>
> Looks like the old consoles formats are more dificult to figure out than newer consoles or pc games, or is it just me?

You probably right..
## Post #130
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2013-10-12T23:55:53+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

> Reply from kela51
>
> GDL wrote:Looks like the old consoles formats are more dificult to figure out than newer consoles or pc games, or is it just me? 

You probably right..
But we made some progress, right? We at least have a script that will allow 3DSMax to import a little of the data from each model.
## Post #131
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2013-10-27T14:47:03+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

I just tried the maxscript out now. Forgot all about it :/

Anyway, it doesn't do anything for me. I'm trying to import the ones extracted from Noesis, but it comes out with the error "--No ""Select""function for undefined".

Also, using the internal name from the sample falconcool posted years ago, I managed to locate Shalua at file13154.rfd.

If you search inside it for n014, it appears 40 times, going by some of the text in there I think there's animation in there too.

If you open that up in hex:

Bytes C-E are the rfd's full size in hex, backwards.

Byte 14 onwards is the offset list, so the texanm one starts at 0x70, marker at 0xA0, and the models are listed after that, with the first one at 0x4E0.

Jump to 0x4E0, and it's the start of the model, n014_L01smd. 0x4EC-4ED is the full size of the model, 87C0 bytes.

After going through cheat engine, the character values are:

e000 - Weiss
e001 - Azul
e002 - Arch Azul
e003 - Rosso
e004 - Arachnero
e006 - Nero*
e009 - Hojo
e049 - Weiss
e050 - Azul
e052 - Rosso
e067 - Turks
e070 - Turks training robot
e071 - SOLDIER class robot
n000 - Reeve
n001 - Yuffie in cloak
n002 - Yuffie
n003 - Cid
n004 - Cait Sith
n014 -Shalua
n013 - Shelke
n015 - Lucrecia*
n017 - WRO*
n040 - Grimoire
p000 - Vincent
p001 - Galian Beast
p002 - Chaos
p003 - Invisible?
p004 - Invisible?
p005 - Vincent
p006 - Invisible?
p007 - Playble Chaos
p008 - Invisible
p009 - Turk Vincent
p010 - Turk Vincent
p012 - Vincent (on Shera)
p013 - Playable Turk Vincent
p014 - Purple Vincent
p015 - Purple Vincent
p200 - Vincent
p201 - Galian Beast

* Multiple models in the model viewer, possibly in separate files.





p014, weird purple Vincent:


looks suspiciously like a manikin from the Dissidia games...
## Post #132
- Username: kela51
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jul 16, 2012 12:06 am
- Post datetime: 2013-10-30T20:52:00+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Yeah! It´s on a good way Ultima Espio! Thx
## Post #133
- Username: Cloud452
- Rank: veteran
- Number of posts: 91
- Joined date: Sat Oct 23, 2010 9:50 pm
- Post datetime: 2014-05-13T00:42:45+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

I know that perhaps there would be something to post if progress had been made... but as I hope this won't die.... no progress within the past half year?
## Post #134
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-05-14T11:55:55+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

> Reply from ultimaespio
>
> 
looks suspiciously like a manikin from the Dissidia games...

If you remember at the start of DoC there was a scene where vincent was being seen by some googles, he had this texture instead of the normal one.



Sorry for the 1080p high definition image
## Post #135
- Username: xbeton0L
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Dec 16, 2011 10:40 pm
- Post datetime: 2014-07-21T01:48:54+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

I really wish I knew enough to contribute something for this.
Tetsuya Nomura's designs were on fire back in the day.

Until then, my watch begins.
## Post #136
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-07-26T01:22:44+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

This is probably my favorite game ever, so if i ever get an idea how the file format or the Ps2 does the stuff i will probably work on it after i finish my first file format importing.
## Post #137
- Username: Cloud452
- Rank: veteran
- Number of posts: 91
- Joined date: Sat Oct 23, 2010 9:50 pm
- Post datetime: 2014-12-14T01:17:03+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

> Reply from Seyren
>
> This is probably my favorite game ever, so if i ever get an idea how the file format or the Ps2 does the stuff i will probably work on it after i finish my first file format importing.

That's good to hear. After all these years, I'm surprised we've not gotten much further.
## Post #138
- Username: Trishty
- Rank: advanced
- Number of posts: 63
- Joined date: Mon Jul 05, 2010 9:37 pm
- Post datetime: 2014-12-14T10:35:55+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Hi! This is my Vincent, I created from scratch based on watching the ripped model. 
Ripped model is not T-pose, so I have to take a lot of time to complete him. If someone still knows how to use cheat engine to make the T-pose please let me know, thank you very much!
## Post #139
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2014-12-14T13:25:16+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Back on page 8 of this topic, The Dude posted a MaxScript that can extract the skeletons of Dirge of Cerberus model files. According to page 7, those files can be extracted from the game disc using aluigi's FF13 BMS script. The headers p000, p005, and p200 were determined to belong to Vincent's models, so if you extract the game and isolate any of those within the .rfd files, you can run them through The Dude's MaxScript and get a skeleton of Vincent. You can then align your model to that skeleton and obtain a T-pose.

By the way, I really like the Vincent model! It's looks as amazing as your Death Penalty model. I wonder if you're planning to remake the whole Limit Forms sweep.
## Post #140
- Username: Trishty
- Rank: advanced
- Number of posts: 63
- Joined date: Mon Jul 05, 2010 9:37 pm
- Post datetime: 2014-12-14T14:22:03+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Actually I'm talking about this T-pose
[viewtopic.php?p=52272#p52272](http://forum.xentax.com/viewtopic.php?p=52272#p52272)

Ripped model cannot be used because it mess up and backface culling, but I can redraw a new model based on watching it so if have a T-pose ripped model that would be more easy for me to draw ^v^
## Post #141
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2014-12-14T14:56:47+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Whoa!! This is as amazing as it was surprising!!!
## Post #142
- Username: truston
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Dec 15, 2014 5:42 pm
- Post datetime: 2015-12-21T06:35:11+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

hello! 
since people can rip models from DCFF7, I wonder if anyone can rip all FMV videos from DCFF7 (US)? I love the FMV, and I created a new request topic, to ask for FMV extractor for this game. 
link: [viewtopic.php?f=36&t=13706](http://forum.xentax.com/viewtopic.php?f=36&t=13706)

anyone has a way to do this? 
============================
thank u everyone! merry christmas!
## Post #143
- Username: sqand
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 19, 2016 7:08 am
- Post datetime: 2016-06-20T17:23:52+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Wow, I picked this game to play with because I had it lying around, I had no idea it had such a history!  I do have one question that I hope someone can help with...

As falconcool mentioned, aluigi's BMS script for FFXIII had enough info to get the data out of filelist.bin/kel.dat, but with a twist: only some of the files had names in filelist.bin. One of the files extracted was "file.txt", which has records like this:

```
g1Mil5b6ypnehnRXD0QGm7:47136:data/event/scene/ev0001/sound/se_0002.at2
ouUIzREgdp9a3g5Xpcwo57:10272:data/event/scene/ev0740/sound/70803yf.at2
FsNXix9xhPBKZnfk_jDok7:232:data/event/scene/ev2000/string.bin
wpwZwb7mKFyCJTCn2olXbA:4024:data/event/scene/ev2000/scr000.class
```


So field 2 seems to be the file's size in bytes, since the numbers there match up with the extracted files, and the third field is obviously the filename/path, but I haven't yet figured out the first field. They're all 22 characters long, so they must be a base64 encoded 128-bit hash.  I tried just MD5ing the data, but that's not it. Has anyone seen something like this before?

Thanks, and sorry if this thread is one that should have been left in the graveyard.
## Post #144
- Username: sqand
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 19, 2016 7:08 am
- Post datetime: 2016-06-26T18:01:44+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

> Reply from revelation
>
> ps2 vif tag are very tricky to handle solely on a visual basis if you do not take all the commands and flags into account.

For instance the "patterns" you are seeing of this form:
Code: Select all02 01 00 01
04 04 00 01
04 01 00 01

are set cycle commands.  The specify how often values are either read or written into memory.  As an example:
Code: Select all02 01 00 01

would cause a value to be written ever other line (of 16 bytes).
Code: Select all04 01 00 01

would cause a value to be written ever 4 lines.  And there are various other combinations.

The command that causes execution of the current set of vif commands after transfer is:
Code: Select all00 00 00 17


The "patterns"
Code: Select all## 80 ?? 6*
## C0 ?? 7*

etc, specify an unpack command, where:
## is the address to store the unpacked data that follows, specified in multiples of 16-bytes (qwc, quad word count)

80/C0 is actually a set of flag bits where 0x80 is flg, and 0x40 specifies whether a value should be treated as signed or unsigned

?? is the number of values to unpack

6/7 is the actual unpack command specifier, but the full structure contains a flag specifying whether the unpack is masked or not (which just happens to be in the 1's position which is why the 6 becomes 7 in the full structure)

* is actual a combination of two 2-bit values, vn, and vl (each possible to be 0 - 3)
vn - is the number of components
vl - is the data type of the components
where:
Code: Select allvn
- 0 is 1-component
- 1 is 2-components
- 2 is 3-components
- 3 is 4 components
vl
- 0 are 32-bit values
- 1 are 16-bit values
- 2 are  8-bit values
- 3 are rgb5a1 values (16-bit)


As an example
6E: the E is actually a combination of 0x0C and 0x2, or 11 10, which is vn = 3, vl = 2.  So this means each component has 4 values that are 1-byte each
6C: would then be 0xC and 0x0, 11 00, vn = 3 vl = 0, So each component would be 4 32-bit values.

Using this information you can determine the size of the data that follows the unpack command:
C would be four (4) 32-bit (4-byte) values, or 16-bytes total per complete value.  If the number of values specified by ?? is 0x2E (46), then 46 * 16 = 736 (0x2E0) bytes of data.
9 would be three (3) 16-bit (2-byte) values, or 46 * 6 = 266 (0x114) bytes of data.

This can be used to help determine what some data can be, at least initially.  In the case of E this could possibly be rgba color values.  But not this does not have to be the case, it can be any type of value that can be store in 4 8-bit values.
In the same way C could be any set of four 32-bit values.  If they happen to be valid floats, it could possibly be a vertex, but at the same time you could use this same format to store non-float values, or a set of float values that make up a matrix.  But again it can be any data that technically fits within the data size computed from the component type and counts.

Masking can also affect the way data is stored.  There are a number of storage rules for taking things like this into account, as well as ones that modify how values are manipulated before and after they are read.

After unpacking, the data can look a bit different depending on how the developer chose to store things.  Often you can see another complete set of structures which themselves could be interpreted as offsets, counts, etc. in much the same way as the original containing format may have been.

There are a number of games which use these tags, and once understood become a good bit easier to deal with, at least initially.

The values above are a bit of a rough estimate as well, since the actual bits of the structure can possibly cause the commands to look a bit different should those features be used.  Actual documentation on the commands would go further into detail on these subjects.
Code: Select allunion VIFtag
{
	struct
	{
		uint16 imm;
		uint8  num;
		uint8  cmd : 7;
		uint8  stl : 1; // interrupt flag
	} commnd;
	struct
	{
		uint8  cl;
		uint8  wl;
		uint8  num;
		uint8  cmd : 7;
		uint8  stl : 1; // interrupt flag
	} stcycl;
	struct
	{
		uint16 adr : 10;
		uint16 pad : 4;
		uint16 usn : 1;
		uint16 flg : 1;
		uint8  num;
		uint8  vl  : 2;
		uint8  vn  : 2;
		uint8  m   : 1;
		uint8  cmd : 2;
		uint8  stl : 1; // interrupt flag
	} unpack;
};


Hope that helps for now.


Did not know where to post this since it can apply for any ps2 format which uses these commands.

Okay, I didn't want to ghost this thread, so a little bit of a (personal) progress report, I finally have read enough to understand what revelation was talking about here.  VIF is pretty incredible.  What I'm trying to figure out now is: there must be some loading code somewhere that parses the RFD files into its constituent SMDs etc, and then loads the contents of those files into memory, and then DMA transfers them via VIF.  So the SMD file must have some standard header data, and then I expect the payload is one or more DMAtags. What I'm trying to figure out now is whether the loading code strips the header data, and if so how much, and what kind of DMA transfer it uses to send the VIF data.
## Post #145
- Username: Gzun
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 28, 2017 6:02 am
- Post datetime: 2017-10-27T22:05:11+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Hello sorry for revive old thread but has there been more progress on this game? Models look amazing even for PS 2 game.
## Post #146
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-10-07T18:35:56+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

This request will be filled soon:

[viewtopic.php?f=16&t=18904](http://forum.xentax.com/viewtopic.php?f=16&t=18904)
## Post #147
- Username: Skully of Boreal
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 15, 2020 2:20 am
- Post datetime: 2021-02-12T23:17:29+00:00
- Post Title: Re: [Request] Dirge Of Cerberus Final Fantasy VII models

Hi, is it still possible if I can get a request for Grimoire Valentine? I friend of mine loves the game and has been looking for a model of his for a while. His birthday's coming up in a few days and I wanna surprise him. If this form is dead, well, thanks anyway ^^
