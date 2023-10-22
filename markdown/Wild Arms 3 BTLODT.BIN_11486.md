## Post #1
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2014-05-05T02:02:53+00:00
- Post Title: Wild Arms 3 BTLODT.BIN

So a while back, I viewed the BTLODT.BIN file on Wild Arms 3's disc, and found some files. I can recognize the meaning behind the extensions of said files as well, other than .tim files.

.mdl = Model
.msh = Mesh
.bne = Bone
.anm = Animation

Problem is I don't know how to extract the files inside the .bin, and there a ton of these files. If possible, would someone please explain how to extract the files inside the bin?

BTLODT.BIN: [http://www.mediafire.com/download/38793 ... BTLODT.BIN](http://www.mediafire.com/download/3879337c2sqr6du/BTLODT.BIN)
## Post #2
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-05-07T07:28:12+00:00
- Post Title: Wild Arms 3 BTLODT.BIN

That file is mostly all texture data raw RGBA in fact all of it is I think



one.BMP (255.56 KiB) Viewed 541 times
## Post #3
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2014-05-07T17:20:31+00:00
- Post Title: Wild Arms 3 BTLODT.BIN

> Reply from cra0
>
> That file is mostly all texture data raw RGBA in fact all of it is I think
one.BMP
Textures of a summon is what that is, it seems.

What's strange is that the guy over at PS23DFormat found a way to extract some collection of what seems to be terrain. I am aware that texture files can be stored in .tim, this being a PS2 game and all. He said the rest of the data was compressed, but I see file extensions that can be easily associated with 3D models, including some command known as "adm2mdl".
## Post #4
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-05-07T23:14:30+00:00
- Post Title: Wild Arms 3 BTLODT.BIN

> Reply from SmashFan127
>
> cra0 wrote:That file is mostly all texture data raw RGBA in fact all of it is I think
one.BMP
Textures of a summon is what that is, it seems.

What's strange is that the guy over at PS23DFormat found a way to extract some collection of what seems to be terrain. I am aware that texture files can be stored in .tim, this being a PS2 game and all. He said the rest of the data was compressed, but I see file extensions that can be easily associated with 3D models, including some command known as "adm2mdl".

any other example files?
## Post #5
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2014-05-07T23:46:08+00:00
- Post Title: Wild Arms 3 BTLODT.BIN

> Reply from cra0
>
> SmashFan127 wrote:cra0 wrote:That file is mostly all texture data raw RGBA in fact all of it is I think
one.BMP
Textures of a summon is what that is, it seems.

What's strange is that the guy over at PS23DFormat found a way to extract some collection of what seems to be terrain. I am aware that texture files can be stored in .tim, this being a PS2 game and all. He said the rest of the data was compressed, but I see file extensions that can be easily associated with 3D models, including some command known as "adm2mdl".

any other example files?
There seems to be .bin files inside this archive, like it was meant to store extra data. There is an extension known as .bi2, which I assume is another storage archive alongside the .dat files inside. I can assume .vu1 and .vu2 files are associated with UVs and there are .adm files which are converted into in-game 3D models.

There are .mt1, .mt2, and .mth files which I can assume are material files.

Besides the .dmy files, which I think are dummy files, the rest of the extensions are listed here.

.v1p
.v2p
.bnp
.bnx
.pal
.anp
.bxp
.bx8
.anx
.anz
.mss
.msb
.bwh
## Post #6
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-05-08T03:31:49+00:00
- Post Title: Wild Arms 3 BTLODT.BIN

Alright I'll take a closer look

ah yeah I see what you mean

```
MARGS	=	-x-

EFFIDX		=	$01D00000	# ADR address
EFFADR		=	$01D00100	# BIN address

.PATH.bin	=	bin
.PATH.bi2	=	bin
.PATH.s0	=	dat
.PATH.o0	=	tmp
.PATH.bmp	=	bmp;..\monster\bmp
.PATH.tim	=	bmp
.PATH.tx4	=	tmp
.PATH.twh	=	tmp
.PATH.mdl	=	mdl
.PATH.anm	=	anm
.PATH.fam	=	anm
.PATH.bne	=	bne
.PATH.msh	=	msh
.PATH.vu1	=	vu
.PATH.vu2	=	vu
.PATH.mt1	=	vu
.PATH.mth	=	vu
.PATH.mt2	=	vu
.PATH.v1p	=	tmp
.PATH.v2p	=	tmp
.PATH.bnp	=	tmp
.PATH.bx8	=	tmp
.PATH.pal	=	tmp
.PATH.anp	=	tmp
.PATH.bxp	=	tmp
.PATH.dmy	=	dmy
.PATH.anx	=	anx
.PATH.anz	=	tmp
.PATH.mss	=	dat
.PATH.msb	=	bin
.PATH.adm	=	adm
.PATH.bwh	=	tmp
.PATH.hd	=	..\..\snd\btlse
.PATH.ton	=	bmp;..\monster\bmp

.bne.mt1:
	mkpkt $*.bne msh\$&.msh -Ovu\$&
	$(CV) -ptmp\$&.v1p vu\$&.vu1
.bne.mth:
	mkpkt $*.bne msh\$&.msh -Ovu\$& -H
	ren vu\$&.mt1 $&.mth
	$(CV) -ptmp\$&.v1p vu\$&.vu1
.bne.mt2:
	mkpkt $*.bne msh\$&.msh -D -Ovu\$&
	$(CV) -ptmp\$&.v2p vu\$&.vu2

.tim.tx4:
#	midb $*.tim tmp\$&.tx4 -O544
	@$(CV) -p$@ $(**:.tim=.tim/$220~$11800)
.tim.pal:
	setstp $*.tim -Otmp\$&.tip
	@$(CV) -t$@ tmp\$&.tip/$14~$200
.tim.twh:
	midb $*.tim tmp\$&.twh -O0 -S16

.bmp.bx8:
	@$(CV) -c$@ $(**:.bmp=.bmp/$436~$10000)
#	@$(CV) -p$@ $(**:.bmp=.bmp/$436~$10000)
.bmp.pal:
	@$(CV) -t$@ $(**:.bmp=.bmp/$36~$200)
.bmp.bwh:
	midb $*.bmp tmp\$&.bwh -O16 -S16

.s0.o0:
	@$(AS) $(AARGS) dat\$&.s0,$@

.anm.bxp:
#	anmbox bne\$&.bne msh\$&.msh anm\$&.anm -otmp\$&

.anx.anz:
	anx2anz $*.anx tmp\$&.anz

.mss.msb:
	msscv $*.mss bin\$&.msb

# Šî–{ƒ‚ƒfƒ‹
.adm.mdl:
	adm2mdl -x- -n -d:$(BTL_PATH)\over $*
	anmbox bne\$&.bne msh\$&.msh anm\$&.anm -otmp\$&

# adm‚©‚çanpƒf

```
## Post #7
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2014-05-18T07:51:57+00:00
- Post Title: Wild Arms 3 BTLODT.BIN

> Reply from cra0
>
> Alright I'll take a closer look

ah yeah I see what you mean
Code: Select allAARGS	=	/p /ows+ /oc+ /m /ol?		# /l <-> /p
MARGS	=	-x-

EFFIDX		=	$01D00000	# ADR address
EFFADR		=	$01D00100	# BIN address

.PATH.bin	=	bin
.PATH.bi2	=	bin
.PATH.s0	=	dat
.PATH.o0	=	tmp
.PATH.bmp	=	bmp;..\monster\bmp
.PATH.tim	=	bmp
.PATH.tx4	=	tmp
.PATH.twh	=	tmp
.PATH.mdl	=	mdl
.PATH.anm	=	anm
.PATH.fam	=	anm
.PATH.bne	=	bne
.PATH.msh	=	msh
.PATH.vu1	=	vu
.PATH.vu2	=	vu
.PATH.mt1	=	vu
.PATH.mth	=	vu
.PATH.mt2	=	vu
.PATH.v1p	=	tmp
.PATH.v2p	=	tmp
.PATH.bnp	=	tmp
.PATH.bx8	=	tmp
.PATH.pal	=	tmp
.PATH.anp	=	tmp
.PATH.bxp	=	tmp
.PATH.dmy	=	dmy
.PATH.anx	=	anx
.PATH.anz	=	tmp
.PATH.mss	=	dat
.PATH.msb	=	bin
.PATH.adm	=	adm
.PATH.bwh	=	tmp
.PATH.hd	=	..\..\snd\btlse
.PATH.ton	=	bmp;..\monster\bmp

.bne.mt1:
	mkpkt $*.bne msh\$&.msh -Ovu\$&
	$(CV) -ptmp\$&.v1p vu\$&.vu1
.bne.mth:
	mkpkt $*.bne msh\$&.msh -Ovu\$& -H
	ren vu\$&.mt1 $&.mth
	$(CV) -ptmp\$&.v1p vu\$&.vu1
.bne.mt2:
	mkpkt $*.bne msh\$&.msh -D -Ovu\$&
	$(CV) -ptmp\$&.v2p vu\$&.vu2

.tim.tx4:
#	midb $*.tim tmp\$&.tx4 -O544
	@$(CV) -p$@ $(**:.tim=.tim/$220~$11800)
.tim.pal:
	setstp $*.tim -Otmp\$&.tip
	@$(CV) -t$@ tmp\$&.tip/$14~$200
.tim.twh:
	midb $*.tim tmp\$&.twh -O0 -S16

.bmp.bx8:
	@$(CV) -c$@ $(**:.bmp=.bmp/$436~$10000)
#	@$(CV) -p$@ $(**:.bmp=.bmp/$436~$10000)
.bmp.pal:
	@$(CV) -t$@ $(**:.bmp=.bmp/$36~$200)
.bmp.bwh:
	midb $*.bmp tmp\$&.bwh -O16 -S16

.s0.o0:
	@$(AS) $(AARGS) dat\$&.s0,$@

.anm.bxp:
#	anmbox bne\$&.bne msh\$&.msh anm\$&.anm -otmp\$&

.anx.anz:
	anx2anz $*.anx tmp\$&.anz

.mss.msb:
	msscv $*.mss bin\$&.msb

# Šî–{ƒ‚ƒfƒ‹
.adm.mdl:
	adm2mdl -x- -n -d:$(BTL_PATH)\over $*
	anmbox bne\$&.bne msh\$&.msh anm\$&.anm -otmp\$&

# adm‚©‚çanpƒf
This is certainly good to know. I thank you.

What would be the best way to start the next step in getting the data for viewing? My apologies for having not much else to say, I am excited to see where this goes.

EDIT: Apparently, searching the file using the model format's values in a hex editor reveals that BTLODT.BIN does indeed carry a lot of models, varying from what appears to be terrain, and possible character and enemy models.

Here is the model format as found by PS23DFormat:

4ByteNumberofVertexesORunknown
00 40 1E 31
12 04 00 00
4ByteFloatingPointWeight
{4ByteFloatingPointVertexes(X,Y,Z), 4ByteFloatingPointWeight, 4ByteFloatingPointNormalMappings(X,Y,Z), 4ByteFloatingPointWeight, 4ByteFloatingPointTextureUVCoords(U,V), 4ByteFloatPointWeight, 4ByteUnknownInteger}
