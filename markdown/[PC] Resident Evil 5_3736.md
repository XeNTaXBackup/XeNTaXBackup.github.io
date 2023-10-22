## Post #1
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-09-26T09:29:31+00:00
- Post Title: [PC] Resident Evil 5

Hello!
I finally got the Resident Evil 5 for PC and here I will be posting some tools that will help you mess/mod the game 

Re5Extract:
Caution: before you start make sure you delete one of the shader archives: if you use Dx9 then delete shader10.arc, otherwise (Dx10) just delete shader.arc.

This tool will extract the .arc archives and let you mess with the different models and textures. This is very similar to the Dmc4Extract that was posted earlier here at Xentax.

There is one thing I noticed: when I use the program on another drive than c: it doesn't extract anything!! I don't know why but you better make sure your files are in c: !!

Anyways, put the program in the "nativePc" directory and launch it, if you're lucky enough, you'll see the files extracted to the correct locations so you can apply the noArchive patch (will be released soon).

Let me know if this works !!
Later !!
[Re5Extract.zip](https://xentaxbackup.github.io/file/2373_Re5Extract.zip)
## Post #2
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2009-09-26T23:44:45+00:00
- Post Title: [PC] Resident Evil 5

Great work! I hope to see more stuff from you.

One big problem I've had lately is that I can't figure out the extensions for the mercs definition files (inside s400.arc, inside the soft\merce and soft\merceex directories). They have the header XFS, but that's not the extension they're supposed to have. And unlike most other files, the game is actually okay with not loading them at all. So I can't find out the correct extension via error messages.
## Post #3
- Username: ResiHax
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Sep 27, 2009 7:54 am
- Post datetime: 2009-09-27T00:22:22+00:00
- Post Title: [PC] Resident Evil 5

Ah, yes.  That's good.  No more constant renaming of those silly extensions.  This'll help a lot.

+Thanked
## Post #4
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2009-09-27T00:41:20+00:00
- Post Title: [PC] Resident Evil 5

By the way, one thing to note. Some files are different, but have the exact same filename and placed in the same directory. For instance, the model files for Wesker in em80.arc and em81.arc are both pawn\em\em80\model\em8000.mod, but one of them is the model for Wesker without coat and the other with coat. I think it's the same for many other files too. So if you're planning to extract absolutely all the arcs to the same destination, you'll end up with files with different data occasionally overwriting other files.
## Post #5
- Username: ResiHax
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Sep 27, 2009 7:54 am
- Post datetime: 2009-09-27T00:43:15+00:00
- Post Title: [PC] Resident Evil 5

> Reply from Sectus
>
> By the way, one thing to note. Some files are different, but have the exact same filename and placed in the same directory. For instance, the model files for Wesker in em80.arc and em81.arc are both pawn\em\em80\model\em8000.mod, but one of them is the model for Wesker without coat and the other with coat. I think it's the same for many other files too. So if you're planning to extract absolutely all the arcs to the same destination, you'll end up with files with different data occasionally overwriting other files.
=Problem all the time.

Noting that, it seems even Safari Chris and Normal Chris have the same file name.

We'd need an .arc injector or repacker to get past this.  The DMC4 one is for DMC4 only and doesn't work.
## Post #6
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-09-27T10:22:06+00:00
- Post Title: [PC] Resident Evil 5

Hiii!!
Here's more on RE5 PC: Re5Tex: as the name suggests, this tool will convert the TEX texture files into the readable DDS.

This is the same as the Dmc4Tex but I added the DXT3 support.
Becareful though, the original TEX files will be overwritten by the DDS files so make sure you apply this program not to the data you play with.

Later 
[Re5Tex.zip](https://xentaxbackup.github.io/file/2382_Re5Tex.zip)
## Post #7
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2009-09-27T10:50:24+00:00
- Post Title: [PC] Resident Evil 5

> Reply from ResiHax
>
> We'd need an .arc injector or repacker to get past this.  The DMC4 one is for DMC4 only and doesn't work.
Making a repacker is much easier than making an injector, because RE5 use Zlib compression, which is free. DMC4 use modified LZX compression, which source is unknow.
## Post #8
- Username: echelon
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Sep 23, 2009 7:46 am
- Post datetime: 2009-09-27T11:22:58+00:00
- Post Title: [PC] Resident Evil 5

Nice work Surveyor. For some reason your tool is throwing errors at me but probably I'm doing something wrong, since it works for the others. (Can't open ARC file [pathToRE5\nativePc] and so on...).
Btw: Won't be long until my repacker is done.
## Post #9
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2009-09-27T11:46:44+00:00
- Post Title: [PC] Resident Evil 5

Can I Modify Subtitle Text and applied font faces for the game? of course I'm hungry for translating this game onto my language which isn't in ANSI, so I need ReDraw font texture if is it and then change text into russian text (translating not in Russian)
## Post #10
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2009-09-27T14:59:25+00:00
- Post Title: [PC] Resident Evil 5

do you figured out how to extract uv on mod files ?
if not it is quite simple just divide uv[0] and uv[1] by 65535

// D3DDECLTYPE_SHORT4N  POSITION '//must divide  all vals by 32767
// D3DDECLTYPE_UBYTE4  BLENDINDICES  '//must divide  all vals by 255
// D3DDECLTYPE_UBYTE4N  BLENDWEIGHT  '//must divide  all vals by 255
// D3DDECLTYPE_UBYTE4N  NORMAL '//must divide  all vals by 255
// D3DDECLTYPE_UBYTE4N  TANGENT '//must divide  all vals by 255
// D3DDECLTYPE_FLOAT16_2 TEXCOORD '//must divide  all vals by 65535
// D3DDECLTYPE_FLOAT16_2 TEXCOORD '//must divide  all vals by 65535
//D3DDECLTYPE_SHORT2N  POSITION '//must divide  all vals by 32767
//D3DDECLTYPE_DEC3N '//must divide  all vals by 511

all those are packed to get more performance on gpu 

(sorry for my poor english)
then in the obj extractor just add vt value1 value2

i am currently working on a *.mod viewer for re5 and found that some models use subobjects from others models
to avoid the pancake effect i think you must recalculate each vertex using bones (using vertexweights).
i have coded a ms3d loader that use some asm for realtime animation , based on it i think i will easily do a viewer for re5 on my spare time...
## Post #11
- Username: JeffT
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 16, 2009 4:15 pm
- Post datetime: 2009-09-27T15:01:03+00:00
- Post Title: [PC] Resident Evil 5

Can anyone write a repacker for RE5 .arc format please.
## Post #12
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2009-09-27T15:36:45+00:00
- Post Title: [PC] Resident Evil 5

> Reply from JeffT
>
> Can anyone write a repacker for RE5 .arc format please.
 +1
## Post #13
- Username: ResiHax
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Sep 27, 2009 7:54 am
- Post datetime: 2009-09-27T15:47:35+00:00
- Post Title: [PC] Resident Evil 5

> Reply from JeffT
>
> Can anyone write a repacker for RE5 .arc format please.

I'm sure someone is.

However, something we discovered at RE4&5PC was that the game possibly crashes if the .arc file is a different size.  However this could be incorrect.
## Post #14
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-09-27T16:15:29+00:00
- Post Title: [PC] Resident Evil 5

The archives are just zlib it should be easy to write a repacker though the files may be slightly bigger in size when done.
## Post #15
- Username: ResiHax
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Sep 27, 2009 7:54 am
- Post datetime: 2009-09-27T17:12:07+00:00
- Post Title: [PC] Resident Evil 5

> Reply from chrrox
>
> The archives are just zlib it should be easy to write a repacker though the files may be slightly bigger in size when done.
Which is a problem based on our info.
## Post #16
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-09-27T17:50:21+00:00
- Post Title: Re: [PC] Resident Evil 5

no I mean its not a problem as in the game can load different sized files
also you could edit the cut scenes to load a different named model easily so if you had the extractor just add a 1 at the end or something.
## Post #17
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2009-09-28T11:34:55+00:00
- Post Title: Re: [PC] Resident Evil 5

hi there , i manage to actually render bones hierarchy + vertex points offseted to the bone position quite good not ?
next step is to render using triangles ( since i figured out the indices), uv coordinates are already ok and normals also, just need to rebuild triangles and load textures :p
[re5chris_Tpose_in_xandreale.jpg](https://xentaxbackup.github.io/file/2391_re5chris_Tpose_in_xandreale.jpg)
## Post #18
- Username: echelon
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Sep 23, 2009 7:46 am
- Post datetime: 2009-09-28T11:45:07+00:00
- Post Title: Re: [PC] Resident Evil 5

Here is an updated version of the unpacker / repacker I made.
Features:
- unpack any re5 arc
- repack any re5 arc from a folder
- extract all re5 arcs with one click

[Download ArcTool (rapidshare)](http://rapidshare.com/files/286018306/RE5ArcTool091.zip)
[Download ArcTool (mirror)](http://cgtatti.net/RE5ArcTool091.zip)

more info: [http://z6.invisionfree.com/Resident_Evi ... opic=10046](http://z6.invisionfree.com/Resident_Evil_4_PC/index.php?showtopic=10046)

Edit: This looks great  shadowmoy, keep it up
## Post #19
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-09-28T13:09:54+00:00
- Post Title: Re: [PC] Resident Evil 5

Bonjour!!
this is the noArchive patch that will let you play the game with the files outside the archives. This is very useful for modders who want to make modifications to the Models/textures/animations without worrying about repacking the stuff.

The problem is, on the computer I tested the game, everything crashes after about 20 seconds of gameplay (no mods, no extractions, no patches, just the neat original game). This computer has the (somewhat) old ATI x1550 although the readme says this graphic card will run the game!! This is very frustrating since I only got to test some of the file extensions, for the others (extensions), the game didn't survive to load them (ask for them)

So I decided to patch the archives to the known file extensions only. That's what I got:
- sound files when patched don't seem to crash the game
- effect files when patched crash the game (by crash I mean the "Don't send message" after "press start" page)
- and most importantly: the textures when patched crash the game !!!!! I really don't understand!!!!
- for the rest of the known extensions, everything is ok (models/anims/messages..)

Now here's a list of all the extensions used by the game, these are the known ones

```
#define ARCEXT_TEXTURE			0x241F5DEB		// tex
#define ARCEXT_MOTION			0x76820D81		// lmt
#define ARCEXT_MODEL			0x58A15856		// mod
#define ARCEXT_VIBRATION			0x358012E8		// vib
#define ARCEXT_MESSAGE			0x10C460E6		// msg
#define ARCEXT_LSP			0x60DD1B16		// lsp
#define ARCEXT_SDL			0x4C0DB839		// sdl
#define ARCEXT_STP			0x671F21DA		// stp
#define ARCEXT_IDM			0x2447D742		// idm
#define ARCEXT_MTG			0x4E2FEF36		// mtg
#define ARCEXT_LCM			0x39C52040		// lcm
#define ARCEXT_JEX			0x2282360D		// jex
#define ARCEXT_CHN			0x3E363245		// chn
#define ARCEXT_AHC			0x5802B3FF		// ahc
#define ARCEXT_HIT			0x0253f147		// hit
#define ARCEXT_RTEXTURE			0x7808EA10		// rtex, not used, all textures empty
#define ARCEXT_CUBEMAP			0x4D894D5D		// for all the stages, header: XFS, loads without

// effects
#define ARCEXT_EFFECT_EAN		0x4E397417		// ean
#define ARCEXT_EFFECT_EFL		0x6D5AE854		// efl
#define ARCEXT_EFFECT_EFS		0x02833703		// efs
#define ARCEXT_EFFECT_RTT		0x276DE8B7		// rtt
#define ARCEXT_EFFECT_AEF		0x557ECC08		// for all the stages, header: XFS, loads without
#define ARCEXT_EFFECT_ADH		0x1EFB1B67		// adh
#define ARCEXT_EFFECT_CEF		0x758B2EB7		// cef

// sounds
#define ARCEXT_SOUND_SPC		0x7E33A16C		// spc
#define ARCEXT_SOUND_SRD		0x2D12E086		// srd
#define ARCEXT_SOUND_SRQ		0x1BCC4966		// srq
#define ARCEXT_SOUND_STQ		0x167DBBFF		// stq
#define ARCEXT_SOUND_REVWIN		0x232E228C		// rev_win
#define ARCEXT_SOUND_EQU		0x2B40AE8F		// equ
#define ARCEXT_SOUND_SCS		0x0ECD7DF4		// scs
#define ARCEXT_SOUND_SDS		0x0315E81F		// sds
#define ARCEXT_SOUND_MSE		0x4CA26828		// mse
#define ARCEXT_SOUND_ASE		0x07437CCE		// ase
#define ARCEXT_SOUND_SNGW		0x7D1530C2		// sngw, ogg

```

The fellowing are untested files but extensions are given according to their header
Missing extensions are: at3, xma, bgm, pth, ptl, lom, los, way, nav, 

```
#define ARCEXT_UNK09		0x430B4FF4		// XFS
#define ARCEXT_UNK12		0x5898749C		// XFS
#define ARCEXT_UNK14		0x38F66FC3		// XFS
#define ARCEXT_UNK15		0x039D71F2		// XFS
#define ARCEXT_UNK17		0x176C3F95		// XFS
#define ARCEXT_UNK18		0x2C4666D1		// XFS
#define ARCEXT_UNK19		0x266E8A91		// XFS
#define ARCEXT_UNK20		0x15302EF4		// XFS
#define ARCEXT_UNK21		0x19A59A91		// XFS
#define ARCEXT_UNK24		0x1ED12F1B		// XFS
#define ARCEXT_UNK26		0x65B275E5		// XFS
#define ARCEXT_UNK29		0x754B82B4		// XFS
#define ARCEXT_UNK30		0x017A550D		// XFS
#define ARCEXT_UNK34		0x1BA81D3C		// XFS
#define ARCEXT_UNK35		0x4F16B7AB		// XFS
#define ARCEXT_UNK36		0x585831AA		// XFS

// I'm not too sure about these either
#define ARCEXT_CCL		0x0026E7FF		// CCL
#define ARCEXT_HAVOK		0x36E29465		// havok HVK
#define ARCEXT_FSM		0x66B45610		// FSM
#define ARCEXT_SBC		0x51FC779F		// SBC
#define ARCEXT_NAV		0x4EF19843		// NAV
#define ARCEXT_WAY		0x5F36B659		// WAY
#define ARCEXT_OBJ		0x0DADAB62		// OBJ
#define ARCEXT_SHP		0x5204D557		// SHP
#define ARCEXT_SHW		0x60524FBB		// SHW
#define ARCEXT_CDG		0x2DC54131		// CDF, present only for pl02 model

#define ARCEXT_SOUND_SND12	0x46810940		// XFS
#define ARCEXT_SOUND_SND13	0x538120DE		// XFS

```


Anyways, below is the patcher that will work only for the extensions that didn't crash the game. There is also the UnPatcher: this will revert to original ARC status when you mess things up with the Patcher (happens sometimes)

As usual, just put the program in the naticePc directory and it will recursively scan the subfolders.

And since I don't think I'll continue the work on the patcher as I don't have any computer that can run the game properly, I'll post the source code here so people can make their own patchers.
[Re5Patch + Unpatch.zip](https://xentaxbackup.github.io/file/2393_Re5Patch + Unpatch.zip)
## Post #20
- Username: ResiHax
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Sep 27, 2009 7:54 am
- Post datetime: 2009-09-28T20:10:51+00:00
- Post Title: Re: [PC] Resident Evil 5

Very nice, the patch will help reduce file sizes of downloads.  However it makes the .arc repacker obsolete...
Well, we can assume that the patch won't work for everyone.
## Post #21
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-09-29T11:04:30+00:00
- Post Title: Re: [PC] Resident Evil 5

Ok guys here's the Mod2Obj converter, this is just the old Dmc4Model.exe, I only tweaked the scaling factors to get rid of the pancake effect. Other than that the program works perfectly on RE5, texture coords are ok, on object names you'll get a hint to what texture to use on that object. On stages the scaling is correct but the games scales them to x10 I think.
Still the skinning is missing, me and poly are struggling to figure out the bone offseting system and it's damn hard. The source code has already been posted in the DMC4 thread if you want to scratch the inside of you brain to help imporove stuff here and everybody is invited!!
[Mod2Obj.zip](https://xentaxbackup.github.io/file/2401_Mod2Obj.zip)
## Post #22
- Username: echelon
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Sep 23, 2009 7:46 am
- Post datetime: 2009-09-29T12:16:13+00:00
- Post Title: Re: [PC] Resident Evil 5

Just awesome.
## Post #23
- Username: Stars
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Sep 29, 2009 6:41 pm
- Post datetime: 2009-09-29T16:34:13+00:00
- Post Title: Re: [PC] Resident Evil 5

Hello friends, I'm new here and would like to ask you something, I'm very noob in these things editing games, etc ... But I ask one thing. 
Capcom confirmed that it withdrew the coop splitscreen mode for PC, but said the code is the same as the 360, ps3 ... and still contends, that a hacker simply appear, copy the code and make a patch that someone will be able to this code to make a patch to add splitscreen mode in RE5 pc?

Sry my english.
## Post #24
- Username: ResiHax
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Sep 27, 2009 7:54 am
- Post datetime: 2009-09-29T18:59:49+00:00
- Post Title: Re: [PC] Resident Evil 5

> Reply from Surveyor
>
> Ok guys here's the Mod2Obj converter, this is just the old Dmc4Model.exe, I only tweaked the scaling factors to get rid of the pancake effect. Other than that the program works perfectly on RE5, texture coords are ok, on object names you'll get a hint to what texture to use on that object. On stages the scaling is correct but the games scales them to x10 I think.
Still the skinning is missing, me and poly are struggling to figure out the bone offseting system and it's damn hard. The source code has already been posted in the DMC4 thread if you want to scratch the inside of you brain to help imporove stuff here and everybody is invited!!

Any possible way of making an OBJtoMOD converter?
## Post #25
- Username: echelon
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Sep 23, 2009 7:46 am
- Post datetime: 2009-09-30T11:21:46+00:00
- Post Title: Re: [PC] Resident Evil 5

Hey Surveyor could you give me some insight on the structure of the TEX header?
It doesn't seem to have a fixed length. I found the width and height and probably the mipmap count. But the header doesn't seem to be fixed length and I also can't find a length byte or a trailer. So simply don't know where it ends and where the data begins. Maybe you could give me a hint since you already wrote a converter? Thanks a lot!

edit: DXT1 TEX header mostly seems to be 0x48, 0x50, 0x54 bytes long. DXT5 is often a bit longer... I really don't get it. o_O
## Post #26
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2009-09-30T11:55:45+00:00
- Post Title: Re: [PC] Resident Evil 5

> Reply from Surveyor
>
> Ok guys here's the Mod2Obj converter, this is just the old Dmc4Model.exe, I only tweaked the scaling factors to get rid of the pancake effect. Other than that the program works perfectly on RE5, texture coords are ok, on object names you'll get a hint to what texture to use on that object. On stages the scaling is correct but the games scales them to x10 I think.
Still the skinning is missing, me and poly are struggling to figure out the bone offseting system and it's damn hard. The source code has already been posted in the DMC4 thread if you want to scratch the inside of you brain to help imporove stuff here and everybody is invited!!

offsetting is quite easy :

you have the bbox so :

here is how to do it in fbsl :

```
Dim !h, !w, !l


w = Abs(header.BBoxMin.x) + Abs(header.BBoxMax.x)
h = Abs(header.BBoxMin.y) + Abs(header.BBoxMax.y)
l = Abs(header.BBoxMin.z) + Abs(header.BBoxMax.z)
'//then divide all vertex by 32767 and multiply by respective size and offset the pos
For i = 0 To header.vertexcount - 1
	vertexf[i].x = !(vertex[i].vert[0] / !32767 * w) - w / 2
	vertexf[i].y = (!vertex[i].vert[1] / !32767 * h)
	vertexf[i].z = (!vertex[i].vert[2] / !32767 * l) - l / 2 + header.BSphere.z
Next



```
## Post #27
- Username: Stars
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Sep 29, 2009 6:41 pm
- Post datetime: 2009-09-30T12:14:52+00:00
- Post Title: Re: [PC] Resident Evil 5

Does anyone get what I asked?

THX
## Post #28
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2009-09-30T17:51:22+00:00
- Post Title: Re: [PC] Resident Evil 5

not possible, on pc version you have online mode but the splitscreen version have been removed certainly from the engine, in counterpart they have add more content , better graphics , models, etc.. to the pc version
## Post #29
- Username: Stars
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Sep 29, 2009 6:41 pm
- Post datetime: 2009-09-30T17:59:40+00:00
- Post Title: Re: [PC] Resident Evil 5

Yes, it was removed, but the very capcom said simply copy the code splitscreen on consoles and applies it in the pc version.
## Post #30
- Username: ResiHax
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Sep 27, 2009 7:54 am
- Post datetime: 2009-09-30T19:38:31+00:00
- Post Title: Re: [PC] Resident Evil 5

Surveyor, would you be willing to work on a OBJ to MOD converter for DMC4 & RE5, or release the source code for your MOD2OBJ, it should be easy enough, just kinda reverse the process... I think...
## Post #31
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2009-10-01T03:58:38+00:00
- Post Title: Re: [PC] Resident Evil 5

> Reply from Surveyor
>
> Bonjour!!
Now here's a list of all the extensions used by the game, these are the known ones
Code: Select all#define ARCEXT_SHADER		0x50F9DB3E		// bfx
#define ARCEXT_TEXTURE			0x241F5DEB		// tex
#define ARCEXT_MOTION			0x76820D81		// lmt
#define ARCEXT_MODEL			0x58A15856		// mod
#define ARCEXT_VIBRATION			0x358012E8		// vib
#define ARCEXT_MESSAGE			0x10C460E6		// msg
#define ARCEXT_LSP			0x60DD1B16		// lsp
#define ARCEXT_SDL			0x4C0DB839		// sdl
#define ARCEXT_STP			0x671F21DA		// stp
#define ARCEXT_IDM			0x2447D742		// idm
#define ARCEXT_MTG			0x4E2FEF36		// mtg
#define ARCEXT_LCM			0x39C52040		// lcm
#define ARCEXT_JEX			0x2282360D		// jex
#define ARCEXT_CHN			0x3E363245		// chn
#define ARCEXT_AHC			0x5802B3FF		// ahc
#define ARCEXT_HIT			0x0253f147		// hit
#define ARCEXT_RTEXTURE			0x7808EA10		// rtex, not used, all textures empty
#define ARCEXT_CUBEMAP			0x4D894D5D		// for all the stages, header: XFS, loads without

// effects
#define ARCEXT_EFFECT_EAN		0x4E397417		// ean
#define ARCEXT_EFFECT_EFL		0x6D5AE854		// efl
#define ARCEXT_EFFECT_EFS		0x02833703		// efs
#define ARCEXT_EFFECT_RTT		0x276DE8B7		// rtt
#define ARCEXT_EFFECT_AEF		0x557ECC08		// for all the stages, header: XFS, loads without
#define ARCEXT_EFFECT_ADH		0x1EFB1B67		// adh
#define ARCEXT_EFFECT_CEF		0x758B2EB7		// cef

// sounds
#define ARCEXT_SOUND_SPC		0x7E33A16C		// spc
#define ARCEXT_SOUND_SRD		0x2D12E086		// srd
#define ARCEXT_SOUND_SRQ		0x1BCC4966		// srq
#define ARCEXT_SOUND_STQ		0x167DBBFF		// stq
#define ARCEXT_SOUND_REVWIN		0x232E228C		// rev_win
#define ARCEXT_SOUND_EQU		0x2B40AE8F		// equ
#define ARCEXT_SOUND_SCS		0x0ECD7DF4		// scs
#define ARCEXT_SOUND_SDS		0x0315E81F		// sds
#define ARCEXT_SOUND_MSE		0x4CA26828		// mse
#define ARCEXT_SOUND_ASE		0x07437CCE		// ase
#define ARCEXT_SOUND_SNGW		0x7D1530C2		// sngw, ogg

The fellowing are untested files but extensions are given according to their header
Missing extensions are: at3, xma, bgm, pth, ptl, lom, los, way, nav, 
Code: Select all#define ARCEXT_UNK08		0x30ED4060		// XFS
#define ARCEXT_UNK09		0x430B4FF4		// XFS
#define ARCEXT_UNK12		0x5898749C		// XFS
#define ARCEXT_UNK14		0x38F66FC3		// XFS
#define ARCEXT_UNK15		0x039D71F2		// XFS
#define ARCEXT_UNK17		0x176C3F95		// XFS
#define ARCEXT_UNK18		0x2C4666D1		// XFS
#define ARCEXT_UNK19		0x266E8A91		// XFS
#define ARCEXT_UNK20		0x15302EF4		// XFS
#define ARCEXT_UNK21		0x19A59A91		// XFS
#define ARCEXT_UNK24		0x1ED12F1B		// XFS
#define ARCEXT_UNK26		0x65B275E5		// XFS
#define ARCEXT_UNK29		0x754B82B4		// XFS
#define ARCEXT_UNK30		0x017A550D		// XFS
#define ARCEXT_UNK34		0x1BA81D3C		// XFS
#define ARCEXT_UNK35		0x4F16B7AB		// XFS
#define ARCEXT_UNK36		0x585831AA		// XFS

// I'm not too sure about these either
#define ARCEXT_CCL		0x0026E7FF		// CCL
#define ARCEXT_HAVOK		0x36E29465		// havok HVK
#define ARCEXT_FSM		0x66B45610		// FSM
#define ARCEXT_SBC		0x51FC779F		// SBC
#define ARCEXT_NAV		0x4EF19843		// NAV
#define ARCEXT_WAY		0x5F36B659		// WAY
#define ARCEXT_OBJ		0x0DADAB62		// OBJ
#define ARCEXT_SHP		0x5204D557		// SHP
#define ARCEXT_SHW		0x60524FBB		// SHW
#define ARCEXT_CDG		0x2DC54131		// CDF, present only for pl02 model

#define ARCEXT_SOUND_SND12	0x46810940		// XFS
#define ARCEXT_SOUND_SND13	0x538120DE		// XFS


Anyways, below is the patcher that will work only for the extensions that didn't crash the game. There is also the UnPatcher: this will revert to original ARC status when you mess things up with the Patcher (happens sometimes)

As usual, just put the program in the naticePc directory and it will recursively scan the subfolders.

And since I don't think I'll continue the work on the patcher as I don't have any computer that can run the game properly, I'll post the source code here so people can make their own patchers.
One small correction to that list. I was messing around with the files in the character arcs with your arc extraction tool, and I learned that .obj should be .oba and .unk34 should be .nck
## Post #32
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2009-10-01T05:33:04+00:00
- Post Title: Re: [PC] Resident Evil 5

hm any method to covert the dds back to tex?

bth is it posible to delet the arc files for save the hdd on my portable pc?
## Post #33
- Username: echelon
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Sep 23, 2009 7:46 am
- Post datetime: 2009-10-01T13:43:06+00:00
- Post Title: Re: [PC] Resident Evil 5

I'm working on DDS to TEX and it works for a lot of textures. But there are still some that don't work. Also it's not a direct conversion. I basically just hash filenames to headers. That's not really a good way to do it. But I just don't understand most of the TEX header. If anyone knows more about the header other than width height and midmap count then please tell me :)
## Post #34
- Username: ResiHax
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Sep 27, 2009 7:54 am
- Post datetime: 2009-10-01T19:30:40+00:00
- Post Title: Re: [PC] Resident Evil 5

> Reply from echelon
>
> I'm working on DDS to TEX and it works for a lot of textures. But there are still some that don't work. Also it's not a direct conversion. I basically just hash filenames to headers. That's not really a good way to do it. But I just don't understand most of the TEX header. If anyone knows more about the header other than width height and midmap count then please tell me
Mip Map goes to 1x1 and Copy/pasting the header and changing the extension supposedly works.
## Post #35
- Username: echelon
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Sep 23, 2009 7:46 am
- Post datetime: 2009-10-01T20:04:01+00:00
- Post Title: Re: [PC] Resident Evil 5

The length of the tex header isn't fixed. So I wouldn't know what to paste.
Hashing the original headers to filenames, width and height works quite well now. Just needs some more tweaking I think.
Still it would be much nicer if we'd know the structure of the tex header. Especially that variable length thing confuses me, since I can't find any bytes that would indicate the ending of the header.
## Post #36
- Username: ResiHax
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Sep 27, 2009 7:54 am
- Post datetime: 2009-10-01T20:05:50+00:00
- Post Title: Re: [PC] Resident Evil 5

I see.  Well, the header for each type of texture should be the same. DxT1, Dxt5 etc.

I DO really wish someone could enlighten me (us) on Converting models BACK to .mod.
## Post #37
- Username: echelon
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Sep 23, 2009 7:46 am
- Post datetime: 2009-10-01T23:00:45+00:00
- Post Title: Re: [PC] Resident Evil 5

> Reply from ResiHax
>
> I see.  Well, the header for each type of texture should be the same. DxT1, Dxt5 etc.

It is not. That's part of the problem.
Updated Version of ArcTool available at [http://z6.invisionfree.com/Resident_Evi ... opic=10046](http://z6.invisionfree.com/Resident_Evil_4_PC/index.php?showtopic=10046).
Featuring DDS to Tex converter. However textures of stage files are not supported, yet.
[Direct download here](http://cgtatti.net/re5/ArcTool092.zip)

ps: I think Surveyor is working on obj to mod. Don`t know the progress status, though.
## Post #38
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2009-10-02T07:47:25+00:00
- Post Title: Re: [PC] Resident Evil 5

The size of DDS header is always 128byte. The TEX header is 44, I think. So cut out the DDS header, paste the first 44bytes of TEX, rename to TEX and done.
This works for DMC4.

Just try out.
## Post #39
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2009-10-02T14:36:11+00:00
- Post Title: Re: [PC] Resident Evil 5

ok some news from my reaschearch on MOD mesh  format :

first the objects groups C:

must be in reality : 

the game rendering is performed by using :

HRESULT DrawIndexedPrimitiveUP(
  D3DPRIMITIVETYPE PrimitiveType,  ==>D3DPT_TRIANGLESTRIP ==5
  UINT MinVertexIndex,      could be 0 or maybe it use cobject::usFlag[6]
  UINT NumVertices,         cobject::usFlag[4]
  UINT PrimitiveCount,      cobject::uiCount
  CONST void * pIndexData,  ==>pointer to  index array  data
  D3DFORMAT IndexDataFormat, == >D3DFMT_INDEX16
  CONST void* pVertexStreamZeroData,  ==>pointer to  vertex array  data
  UINT VertexStreamZeroStride  ==>sizeof(vertex) or 0 (zero)
);
index array set by IDirect3DDevice9::SetIndices(IDirect3DIndexBuffer9 * pIndexData)
)
or maybe better choice :


IDirect3DDevice9::SetFVF(...)
IDirect3DDevice9::SetIndices(...)
IDirect3DDevice9::SetStreamSource(...)
IDirect3DDevice9::DrawPrimitiveUP(...)
so their are parts of the params stored in the model  for rendering quickly different streams and fvf formats 


i think it also use this method :
[http://msdn.microsoft.com/en-us/library ... px#seealso](http://msdn.microsoft.com/en-us/library/ee418549%28VS.85%29.aspx#seealso)


struct cObject //lot of infos are based on  IDirect3DDevice9::DrawIndexedPrimitiveUP
{
	unsigned short			usId;				// id from the indes table
	unsigned short			usMatId;			// material Id
	unsigned short			usFlag[8];			// 0xFF01, 0, the 3rd flag determines what vertex declaration to use
	unsigned int			uiBase1;			// base multiple of 32
	unsigned int			uiZero;
	unsigned int			uiStart;			// start index
	unsigned int			uiCount;			// faces (indices - 2) ->DrawIndexedPrimitiveUP ::PrimitiveCount
	unsigned int			uiBase;
	unsigned short			uiInconnu[6];
};


usFlag[1] : ???
usFlag[2] : ???
usFlag[3] : determines what vertex declaration to use
usFlag[4] : vertexcount =>  == (usFlag[6]-usFlag[5]+1) ->DrawIndexedPrimitiveUP :: NumVertices
usFlag[5] : last vertex offset in vertex array to draw ->
usFlag[6] : first vertex offset in vertex array to draw ->DrawIndexedPrimitiveUP
usFlag[7] : ???
usFlag[8] : ???

so :
uiInconnu[1] == ????
uiInconnu[2] == first vertexid used by the group in the vertex array (not in vertex index array) 
uiInconnu[1] == ????
uiInconnu[1] == ????
uiInconnu[5] == offset to the next cObject to draw based on the adress of cObject data in file : 
something like m_uiObjectOffset-uiInconnu[5] give an adress to another cobject (it is related to witch lodmesh you draw i think)
uiInconnu[6] == ????


so groups must also contain a flag to choose the lod to draw or an incremant to the cobject offset using uiInconnu[5] to select
the mesh lod level to draw if it is near or far from the screen

primitive type is D3DPT_TRIANGLESTRIP ==5 and use a stripped indexed multires mesh 
-> based on IDirect3DDevice9::DrawPrimitiveUP  params or else to draw the mesh the only way to select a multires mesh is to offset the groups data  then 
each group say what group to draw next and the last group drawn must have a specific flag to say "end"

so i don't now yet if this assumption is correct but i want to be able to export only lodmesh0 to any 3dfileformat that support bones,
actually i fixed some issues in my opengl rendering, also if using this offset method their will no more be need to set the backfacing on export...
## Post #40
- Username: echelon
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Sep 23, 2009 7:46 am
- Post datetime: 2009-10-03T05:47:18+00:00
- Post Title: Re: [PC] Resident Evil 5

Wow, impressive research shadowmoy. I guess this is good news on cracking down on the .mod format.

I also massivley updated the arctool. Conversion not based on hashing anymore and much more stable.
Supports ARC extraction, ARC repack (with auto conversion), DDS to TEX, TEX to DDS
[http://rapidshare.com/files/288017237/ArcTool095.zip](http://rapidshare.com/files/288017237/ArcTool095.zip)
[Mirror](http://cgtatti.net/re5/ArcTool095.zip)
[Instructions](http://cgtatti.net/re5/Instructions.txt)
## Post #41
- Username: zeeh
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Jul 26, 2009 9:10 am
- Post datetime: 2009-10-03T12:16:07+00:00
- Post Title: Re: [PC] Resident Evil 5

I have noticed that not all TEX files are DDS. File font00_j.TEX is a 32-bit BMP (alpha channel).
## Post #42
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-10-04T13:52:22+00:00
- Post Title: Re: [PC] Resident Evil 5

> Any possible way of making an OBJtoMOD converter?

> Surveyor, would you be willing to work on a OBJ to MOD converter for DMC4 & RE5, or release the source code for your MOD2OBJ, it should be easy enough, just kinda reverse the process... I think...

I don't think so, a lot of the MOD data is still ignored when converting to OBJ, maybe once we have a complete understanding of the MOD format.

> Hey Surveyor could you give me some insight on the structure of the TEX header?

Sure, here's what I use for my tex converter:
struct cTexHeader
{
	unsigned int		uiTag;		// TEX
	unsigned short		usVersion;	// 0x70
	unsigned short		usType;	// 0x02, 0x22, 0x32, ...
	unsigned int		uiMipmaps;	// 0x000001XX, XX is mipmap count
	unsigned short		usWidth;
	unsigned short		usHeight;
	unsigned int		uiZero;		// rarely somthing else
	unsigned int		uiFormat;	// DXT1, DXT5, ARGB8, P8 (not supported here)
	float				fScale[4];	// some floating points
};

> offsetting is quite easy
I wasn't speaking about this, the bone offseting is the way bones influence vertices, it seems that MOD files have some table that indexes another table that indexes a 3rd table and we didn't figure out the relationship yet.

> One small correction to that list. I was messing around with the files in the character arcs with your arc extraction tool, and I learned that .obj should be .oba and .unk34 should be .nck
well thanks for the update Sectus, as promissed here is the source code for the patcher since I'm no longer able to run the game (with or without the patch).

> bth is it posible to delet the arc files for save the hdd on my portable pc?
No, the game crashes.

> ps: I think Surveyor is working on obj to mod. Don`t know the progress status, though.
Who said that ??? I'm not working on anything, I'm on VACATION!!!!

> ok some news from my reaschearch on MOD mesh format
very nice shadowmoy, it's good to see some progress coming from somebody other than me  keep it up!!
[Re5ToolsSrc.zip](https://xentaxbackup.github.io/file/2418_Re5ToolsSrc.zip)
## Post #43
- Username: echelon
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Sep 23, 2009 7:46 am
- Post datetime: 2009-10-04T18:19:52+00:00
- Post Title: Re: [PC] Resident Evil 5

> Sure, here's what I use for my tex converter:
>
> struct cTexHeader
>
> {
>
> unsigned int uiTag; // TEX
>
> unsigned short usVersion; // 0x70
>
> unsigned short usType; // 0x02, 0x22, 0x32, ...
>
> unsigned int uiMipmaps; // 0x000001XX, XX is mipmap count
>
> unsigned short usWidth;
>
> unsigned short usHeight;
>
> unsigned int uiZero; // rarely somthing else
>
> unsigned int uiFormat; // DXT1, DXT5, ARGB8, P8 (not supported here)
>
> float fScale[4]; // some floating points
>
> };

I figured out most of this myself by now, but thanks anyway!

> Who said that ??? I'm not working on anything, I'm on VACATION!!!!

haha..., I was just guessing that would be the logical next step 
But hey have fun on your Vacation! 

> since I'm no longer able to run the game (with or without the patch).
That's too bad, I hope you'll continue working on it anyway. No more research from your side would be a great loss for this game.
## Post #44
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2009-10-04T18:22:46+00:00
- Post Title: Re: [PC] Resident Evil 5

Surveyor>do you found any way to load some infos from SDL files , i figured out that some models are based on muliple *.mod files, their bbox are not good to rebuild the mesh width,height and depth to rebuild the vertex arrays to fit the bones , so , i figured hex editing files that each mesh can have a fig_model.SDl file associated that gives the mesh hierarchy : mesh1.mdl, mesh2.mdl,mesh3.mdl etc... starting form that it also contain some others infos related to global mesh scaling, positioning, parent hierarchy etc...

also , loading a multiple mesh based mesh , include one more processing : 
each mesh contain hierarchical bones, that is to say a body can have multiple head, merging the bones onto one global skeleton, so it involve also that each mdl contain each sub-skeleton  animation frames, this way you can animate each sub model using it's hown skeletal animation (facial animation, body animation etc...

MT framework 2.0 is a fucking engine based on simplifying skeleton to sub parts to be able to change body parts form the skeletal based object this way it reduce the time dev and cost by reusing base ressources and also avoid to rerig a complete mesh every time you want to change the model...

this is one part of  the magic of capcom MT framework hehe


another problem if you want to use your own models : you need to found out the stripification algorythm they use for stripping vertex indices, witch is far far far away to be easy ..., because it is multires mesh in the same stripped indices array.

i am working on the relation ship between multipart models, to be able to rescale then correctly according to their sub-skeleton
## Post #45
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2009-10-04T18:53:24+00:00
- Post Title: Re: [PC] Resident Evil 5

re: found out the bbox problem ,so  i will try to build a MOD2SMD exporter to verify bones assignements, i think each vertex.bone[0] is the assignated bone and the others are used for vertex weight like ms3d format, so if it work as expected, i will try to wrote a MOD2MS3D exporter, but first of all i need to found out where the lodmesh id adress is stored or how it is calculated to avoid exporting the lodmesh, to only export the lod0 mesh.
## Post #46
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2009-10-04T19:12:22+00:00
- Post Title: Re: [PC] Resident Evil 5

some more interesting infos on models textures :

if the texture filename contain :

_BM  : base model texture
_CMM : detail map texture used to add so more realistic effect on _BM map
_NM : normal map to add relief to the 2d texture _BM
_MM : bump map texture used to modify lighting effect on model

starting from this : each material will stroe a flag to say if it use one or more of them for rendering 

also materials fcolors are not  d3dmaterials but seems to contains lighting values to recalculate the lighting : specular or/and diffuse lighting based engine :
it recalculate the lighting using the normals and tangents from each vertex on realtime !!! fucking hard to figure out !!!


some more interesting things : on materials uilayers :

actually i have found this :

uilayer[0] = materialid for texturename finishing by _BM :: the base texture
uilayer[1] = materialid for texturename finishing by _NM :: the normal map texture
uilayer[2] = materialid for texturename finishing by _MM or _CMM:: the Bump map texture
uilayer[7] = materialid for texturename finishing by _DM_HQ :: a nore detailled normal map texture (highter res)

based on this i have tried to export to obj only groups that use the layers 0,1 and 2 and get a lot less lod models exported, some improvement  in getting the mesh lod 0 level (ie the hight res one)
## Post #47
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2009-10-04T19:32:58+00:00
- Post Title: Re: [PC] Resident Evil 5

ok here is the model vertex repositionning way (fbsl code)

```
dim !h,!w,!l

w= (header.BBoxMax.x)- (header.BBoxMin.x) 
h= (header.BBoxMax.y) - (header.BBoxMin.y) 
l= (header.BBoxMax.z) -(header.BBoxMin.z) 


For i = 0 To header.vertexcount - 1
	vertexf[i].x = !(vertex[i].vert[0] / !32767* w) + header.BBoxMin.x
	vertexf[i].y = (!vertex[i].vert[1] / !32767 * h)+ header.BBoxMin.y
	vertexf[i].z = (!vertex[i].vert[2] / !32767 * l) + header.BBoxMin.z
next

```

it rescale and reposition the models and sub models to the good position and scale
## Post #48
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2009-10-04T20:46:36+00:00
- Post Title: Re: [PC] Resident Evil 5

ok mens here is my first exporter version, it export all lodmesh + generate the .MTL file , normals need to be fixed (bad rotation)
just drop the *.mod file or the *.58A15856 on it 
the outputed files work with milkshape3d and all 3d applications

Edit : thanks for reporting it echelon : yes for my test i used fixed path, now fixed, just drop now !!!
[re5mod2obj.zip](https://xentaxbackup.github.io/file/2425_re5mod2obj.zip)
## Post #49
- Username: venomtrk
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Sep 28, 2009 5:36 am
- Post datetime: 2009-10-04T21:47:43+00:00
- Post Title: Re: [PC] Resident Evil 5

I want to edit subtitles and translate Turkish Language. How can i do it , i can extract some arc files but can not edit them. Help please.
## Post #50
- Username: echelon
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Sep 23, 2009 7:46 am
- Post datetime: 2009-10-04T22:36:59+00:00
- Post Title: Re: [PC] Resident Evil 5

Wow shadowmoy, just amazing stuff. Keep it up!
Tool doesn't work 100% for me right now though: 
E:\pl2100.mod
[000199] RS:6 Call err 22 : FileOpen failed to open file '.\pl1200.mod' with mode 'BINARY'
[000199] [BUFFER] >> [SCRIPT PAUSED] <<

It does work if I rename the mod file to 1200.mod. Maybe you accidentaly hardcoded the filename?

venomtrk: Try checking out the Devil may cry 4 topic in this forum. I think you can get an MGS converter there. Maybe that will help decrypting those files.
## Post #51
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2009-10-05T06:46:06+00:00
- Post Title: Re: [PC] Resident Evil 5

> Reply from venomtrk
>
> I want to edit subtitles and translate Turkish Language. How can i do it , i can extract some arc files but can not edit them. Help please.

There is a MSGEditor to DMC4, but doesn't support the RE5 MSG format. You can convert into txt, but that's all. The msg file doesn't work. Maybe some day.
Until that, you can start with the textures or you can wait.
## Post #52
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2009-10-05T16:10:56+00:00
- Post Title: Re: [PC] Resident Evil 5

huh! you peaple... are working on so difficult - modifying objects and so on, but such more easy, i think, is not solved! - editing text of the game?   

may be bcoz that wants only 2 persons - Turkish & Georgian? either modding wants all
## Post #53
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2009-10-05T16:31:31+00:00
- Post Title: Re: [PC] Resident Evil 5

ok i will try to add the mod2smd today if i get enought time else it will be released tomorow ...
## Post #54
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2009-10-07T18:16:21+00:00
- Post Title: Re: [PC] Resident Evil 5

found one model that don't export correctly : excella head : \pawn\em\em85\model\evf0400.mod in uEm85Excella.arc
all other parts are ok but the uv of the head are wrong, perhaps a different vertex format ?

edit : seems not , but instead of uvw mapping it use spherical or cylindrical mapping (fucking format ) so, if anayone now how to calculate a vertex uv from a vertex pos using spherical mapping i will be glad to had the code or simply an algo to rebuild the uvw mapping from  vertices
## Post #55
- Username: echelon
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Sep 23, 2009 7:46 am
- Post datetime: 2009-10-10T16:20:26+00:00
- Post Title: Re: [PC] Resident Evil 5

> Reply from shadowmoy
>
> found one model that don't export correctly : excella head : \pawn\em\em85\model\evf0400.mod in uEm85Excella.arc
all other parts are ok but the uv of the head are wrong, perhaps a different vertex format ?

edit : seems not , but instead of uvw mapping it use spherical or cylindrical mapping (fucking format ) so, if anayone now how to calculate a vertex uv from a vertex pos using spherical mapping i will be glad to had the code or simply an algo to rebuild the uvw mapping from  vertices

Try checking out this post:
[http://www.gamedev.net/community/forums ... _id=399506](http://www.gamedev.net/community/forums/topic.asp?topic_id=399506)
## Post #56
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2009-10-11T16:25:09+00:00
- Post Title: Re: [PC] Resident Evil 5

thanks for the link but i already found how to do it  thanks again
## Post #57
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2009-10-14T08:45:12+00:00
- Post Title: Re: [PC] Resident Evil 5

does anyone tried like me to replace the sheva head skin by the excella one and notice something ?
## Post #58
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2009-10-14T09:31:56+00:00
- Post Title: Re: [PC] Resident Evil 5

ok ok some infos : 
how the mt framework work ?

it use a special skeleton innovative tool  so what ??
quite simple you know the sims 3 ? you can customise your model faces and body and get lot of different models from the same basic mesh no ?

so to say it simply :
they get a hi res female model , rig it then
they apply some skeleton sizing  on height, lenght, width  to each body part, then modify the skeleton facial bones starting form the same mesh
then they get sheva and excella at hight polys mesh, from this , they generated lod models by deacreasing the poly count for in game models and get the hight res ones for videos sequences, then they just have to modify the uv mapping to fit their owns and do the textures, that is to say they sortened the 3d dev time of all characters reusing a base one , a simple trick to verify it : get the sheva african costume model, select the face , go to uv mapping and rescale it by 2 times the bounding sphere raduis and just move it by the same on y axis and you will notice that the head fit 90% of  excella's face texture (only hairs and ears have been uv modified)

so if anyone want excella's model ingame he will need to edit vertex pos from sheva's african model or another with full head and remap some stuff like ears etc... and it will be possible to use the clone ingame BUT the model will be smaller than excella's original one because of the bones positions, since i don't know how works havok, i can say it could be possible to also move the skeleton base position to rescale the model's skeleton, if i got time i will try first the bone pos mod to check if it is possible, if it work as i thought we can start to do some custom models based on the actual ones polys and vertices....
## Post #59
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-10-14T09:48:06+00:00
- Post Title: Re: [PC] Resident Evil 5

C:\> shadowmoy
where can i download xandreale model viewer ?
## Post #60
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2009-10-14T09:55:06+00:00
- Post Title: Re: [PC] Resident Evil 5

you can't because i don't release it actually :p
## Post #61
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-10-14T09:56:54+00:00
- Post Title: Re: [PC] Resident Evil 5

ooh sad
## Post #62
- Username: ResiHax
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Sep 27, 2009 7:54 am
- Post datetime: 2009-10-17T15:33:25+00:00
- Post Title: Re: [PC] Resident Evil 5

> Reply from shadowmoy
>
> you can't because i don't release it actually :p

It might be a good idea to release it.  Unless it isn't finished, if that's the case, keep going.
## Post #63
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2009-10-19T10:52:00+00:00
- Post Title: Re: [PC] Resident Evil 5

yes my 3d editor will be free and released as soon as i added some missing parts on it, actually it render ms3d animation really well, also have a model optimiser/cleaner but it lacks actaully on editing tools witch is what i am currently working on , it will be released when and only when i added all the basics edition tools needed.
## Post #64
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2009-10-19T19:35:36+00:00
- Post Title: Re: [PC] Resident Evil 5

chek this out :
from the unknow part of data in the mod file i managed to figure out this :
so it could be 2 things :
- spherical uv mapping 
or binormals used in normal mapping

so if i could figure out how this data is used i will be able to re- uvmap corectly all exported groups even if they are normal mapped

if you think it could be somthing else , let's speak of it here
[unknow_mod_data.jpg](https://xentaxbackup.github.io/file/2465_unknow_mod_data.jpg)
## Post #65
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2009-10-22T10:09:55+00:00
- Post Title: Re: [PC] Resident Evil 5

Can anyone tell me where I can find mod2smd converter? I have seen in this thread that you said about him.
## Post #66
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2009-10-22T10:55:41+00:00
- Post Title: Re: [PC] Resident Evil 5

yes i speak about it but actually the exporter to smd is not working correctly, because i have wrong bones assignement, and actually working on normal maps rebuilding, so it is not yet released, because it is not fixed.
## Post #67
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2009-10-22T11:14:17+00:00
- Post Title: Re: [PC] Resident Evil 5

2 shadowmoy:

Understood. 

Pleases the fact that work on the tool is not stopped. I'll stay tuned. Thanks.
## Post #68
- Username: ResiHax
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Sep 27, 2009 7:54 am
- Post datetime: 2009-10-31T16:19:22+00:00
- Post Title: Re: [PC] Resident Evil 5

It seems that Surveyor found something for DMC4, maybe it'll be incorporated into RE5 sometime soon.
## Post #69
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-11-12T10:18:31+00:00
- Post Title: Re: [PC] Resident Evil 5

Hi guys!!
To be honest I only tested the new converter on one model of RE5 and it seemed to work though, the reason is that re5 models have more than one LOD inside and with a slow computer, it takes too long to load so I was a bit lazy on those models. But here's a pic of the model I tested, this is one of the main characters that looks a little gothic but I'm sure this isn't the game mood (I didn't play the game btw but an african gothic ???)
This quickly made pose shows how well skinning behaves under max, It's strange because however I tried, I couldn't set the vertex weights correctly: ex: a vertex originally influenced by 2 bones will be inluenced by 3 under max !!!! where the hell did he get the 3rd bone?!?!
Ok the release will be available soon 
[Gothic.JPG](https://xentaxbackup.github.io/file/2526_Gothic.JPG)
## Post #70
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2009-11-13T14:57:26+00:00
- Post Title: Re: [PC] Resident Evil 5

so you managed to found out the vertex weight datas and some more bones infos ?
nice job !!!
the model you show is sheva, a sweet african girl when textured :op

i don't have found any indexes to remove the lods models actually, i think the 1000 3000 3 values from the header could be the key but not found anything with it :/
## Post #71
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-11-14T09:50:44+00:00
- Post Title: Re: [PC] Resident Evil 5

> Reply from Surveyor
>
> i think the 1000 3000 3 values from the header could be the key but not found anything with it
Naaah, these are the fogging parameters, the LOD indices are somewhere else !!
## Post #72
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2009-11-16T20:38:45+00:00
- Post Title: Re: [PC] Resident Evil 5

yeh i think so   
i was thinking they could be stored in groups structs for faster link using some kind of offsets,because i found start indice stored twice in groups datas, so it could also provide a start indice in the indice array to jump to the next lod sub indice list in the strips...
not a lot of free time to work on the tools currently
## Post #73
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-11-17T21:18:33+00:00
- Post Title: Re: [PC] Resident Evil 5

Hi guys,
The new converter is released, you can grab it from the DMC4 thread here on xentax!!!
I'm counting on you to try it out on different models
## Post #74
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2009-11-22T09:39:03+00:00
- Post Title: Re: [PC] Resident Evil 5

ok so here is the fixed uv version of the mod2obj exporter, still need to fix normals and groups backfacing

(Edit: attachement removed)
## Post #75
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2009-11-22T11:37:18+00:00
- Post Title: Re: [PC] Resident Evil 5

so the same with fixed backfacing problem :
[re5_mod2obj_v3.rar](https://xentaxbackup.github.io/file/2544_re5_mod2obj_v3.rar)
## Post #76
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2009-11-22T21:37:53+00:00
- Post Title: Re: [PC] Resident Evil 5

ok i will need beta testers and a lot of feedback with this one : the aim is to remove the lodmesh not needed (degenerated mesh) and export only the original one

so here is the alpha 3.1 version:
[re5_mod2obj_v31a.rar](https://xentaxbackup.github.io/file/2547_re5_mod2obj_v31a.rar)
## Post #77
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2009-12-03T15:58:49+00:00
- Post Title: Re: [PC] Resident Evil 5

> Reply from venomtrk
>
> I want to edit subtitles and translate Turkish Language. How can i do it
+2

Is there any progress to it? Help us in it, peaple.
## Post #78
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2009-12-04T07:59:51+00:00
- Post Title: Re: [PC] Resident Evil 5

Please delete this message
## Post #79
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2009-12-04T08:00:34+00:00
- Post Title: Re: [PC] Resident Evil 5

+3   

> Reply from Gocha
>
> venomtrk wrote:I want to edit subtitles and translate Turkish Language. How can i do it 
+2

Is there any progress to it? Help us in it, peaple.
## Post #80
- Username: hansekkert
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 08, 2009 6:52 am
- Post datetime: 2009-12-07T23:02:05+00:00
- Post Title: Re: [PC] Resident Evil 5

> Reply from shadowmoy
>
> ok i will need beta testers and a lot of feedback with this one : the aim is to remove the lodmesh not needed (degenerated mesh) and export only the original one

so here is the alpha 3.1 version:

ok, there are no double meshes any more, but only the low poly lod is left. All high poly meshes have been erased.

hope this helps a little.

btw. sorry for my english
## Post #81
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2009-12-09T14:14:29+00:00
- Post Title: Re: [PC] Resident Evil 5

I've been trying to mod some of the enemy layouts for RE5 which has been all about editing XFS files. I thought I might as well share some mapping I've done of one of the files, which is s402_em00.15302ef4. This is the type of file which includes all the enemy definitions for each stage in the game. The header starts with some kind of list of all the variables (lists length maybe?), then a list of strings which is all the names of the variables, then a few more variables which is of the header including one important byte which specifies how many definitions are in this file. I think "01 00 00 00" is used as a separator for variables within a definition.

So here's some quick info about the variables I've identified in the em## files so far. Sorry about the rather ugliness of the picture:

The glowy red small lines show the start and end of each enemy definition. Which is about 1B6 in total length (this varies as at least 2 variables in the definition can have any length).

1: This is part of the header and not of any enemy definitions. This byte simply defines how many definitions are in this file in total. In this case "0C" which is 12. (this is from one of the em00 files by the way)

2: This is the type of enemy. cSetInfoEm10 is the type of majini you fight throughout the entire game. You can replace this with another string of different length.

3: This is the specific type of enemy. uEm10 being town majini. uEm14 would be army majini and there's many other variants. This variable can also be of any length.

4: This is the spawn position of the enemy (mPosition as shown in header). It's 3 variables which are 4 bytes each for X, Y and Z. I haven't messed around a lot with this, but I know the second variable of those is for height.

5: This is the angle the enemy will look at when spawning (mAngle). I haven't messed a lot around with it, so I couldn't say much about it.

6: This is the scale of the enemy (mScale), as with position, it's 3 variables which are 4 bytes each for X, Y and Z.

7: This is the amount of health for the enemy (mLife). In this case "20 03" = 320 (hex) = 800 (decimal).

8: This is the amount of ammo the enemy carries for his weapon (it'll be visible on his back). FF FF FF FF means practically unlimited ammo. You'll usually see this as 00 00 00 00. This only counts for throwable weapons like molotov cocktails, small axes, dynamite and etc.

9: The first byte of these is the actual weapon the enemy is carying. In this case "59" being the steel pipe. (by the way, steel pipe can only be carried as one weapon, so the ammo count above won't matter)

10: This defines the probability of the enemy turning into a las plagas monster. "04" being 100% probability for some reason

11: This is the type of las plagas monster he'll turn into. 00 is none, 01 is longneck/cephalo, 02 is crab/duvalia and 04 is flying las plagas/kipepeo.

12: This variable simply defines whether or not the enemy is lefthanded (mbLefty). 01 means he's a lefty, 00 means right handed.

I made one small mistake with the picture. The 5th variable highlighted is 4 bytes long, not 3.
## Post #82
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-12-14T10:26:41+00:00
- Post Title: Re: [PC] Resident Evil 5

Hi Sectus,
Me too I've been messing with XFS and SDL files for some time now, I didn't test the variables in the game I just tried to interprete them.
Did you actually test the vars in the game or are you only refering to the var names in the XFS header?
The main difference between XFS and SDL files is the offsets to the data chunks, there are no offsets in XFS files which makes reading variable data more difficult (must be read sequentially), besides there are a lot of var types to consider (floats, ints, chars, arrays, ...) an on top of that there are some unknown data structures!
I was working on a XFS/SDL decompiler similar to the PLA decompiler released earlier, the "01 00 00 00" isn't a separator, I'd rather think it as the data array size, if it's one (in the majority of cases, but not always) then this space holds one value only.

And by the way, I forgot to mention that the new Mod2Max converter was posted on the DMC4 thread, it'll help you with RE5 models + texture coords are 100% working!
## Post #83
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2009-12-14T11:55:01+00:00
- Post Title: Re: [PC] Resident Evil 5

> Reply from Surveyor
>
> Hi Sectus,
Me too I've been messing with XFS and SDL files for some time now, I didn't test the variables in the game I just tried to interprete them.
Did you actually test the vars in the game or are you only refering to the var names in the XFS header?
The main difference between XFS and SDL files is the offsets to the data chunks, there are no offsets in XFS files which makes reading variable data more difficult (must be read sequentially), besides there are a lot of var types to consider (floats, ints, chars, arrays, ...) an on top of that there are some unknown data structures!
I was working on a XFS/SDL decompiler similar to the PLA decompiler released earlier, the "01 00 00 00" isn't a separator, I'd rather think it as the data array size, if it's one (in the majority of cases, but not always) then this space holds one value only.

And by the way, I forgot to mention that the new Mod2Max converter was posted on the DMC4 thread, it'll help you with RE5 models + texture coords are 100% working!

Awesome, great work dude.
Is there a new upcoming release for the MOD2OBJ converter at all? with 100% fixed UV's?
## Post #84
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2009-12-14T14:29:01+00:00
- Post Title: Re: [PC] Resident Evil 5

> Reply from Surveyor
>
> Hi Sectus,
Me too I've been messing with XFS and SDL files for some time now, I didn't test the variables in the game I just tried to interprete them.
Did you actually test the vars in the game or are you only refering to the var names in the XFS header?
The main difference between XFS and SDL files is the offsets to the data chunks, there are no offsets in XFS files which makes reading variable data more difficult (must be read sequentially), besides there are a lot of var types to consider (floats, ints, chars, arrays, ...) an on top of that there are some unknown data structures!
I was working on a XFS/SDL decompiler similar to the PLA decompiler released earlier, the "01 00 00 00" isn't a separator, I'd rather think it as the data array size, if it's one (in the majority of cases, but not always) then this space holds one value only.

And by the way, I forgot to mention that the new Mod2Max converter was posted on the DMC4 thread, it'll help you with RE5 models + texture coords are 100% working!
All the stuff I've highlighted are stuff I've tested ingame, and all the changes work as it should.

Some random examples...
[http://screenshot.xfire.com/screenshot/ ... 4fd041.png](http://screenshot.xfire.com/screenshot/natural/5b602d09fe27196f7de14c6f442a296c044fd041.png) - Enemy with high mScale
[http://screenshot.xfire.com/screenshot/ ... f2c0b5.png](http://screenshot.xfire.com/screenshot/natural/fe43ced0611ad9e31ffdac4820c8e59b41f2c0b5.png) - Big man majini with bowgun (normally they never use any weapon in game besides their fists)
[http://www.youtube.com/watch?v=gdyHU-0xjdY](http://www.youtube.com/watch?v=gdyHU-0xjdY) - This is a test variant of Public Assembly I worked on where I tried a ton of different values for enemy types, and weapons and health values for them.
[http://www.youtube.com/watch?v=IkssUOIEVwA](http://www.youtube.com/watch?v=IkssUOIEVwA) - Here's an example where I was able to modify an array in one of the FSM XFS files which controls spawning. I managed to modify it so that one batch of 4 enemies would spawn 14 enemies instead. (more info about those arrays here: [http://z6.invisionfree.com/Resident_Evi ... 9891&st=90](http://z6.invisionfree.com/Resident_Evil_4_PC/index.php?showtopic=9891&st=90) - one of the last posts in that thread)
[http://www.youtube.com/watch?v=t19A2uxlNRQ](http://www.youtube.com/watch?v=t19A2uxlNRQ) - And this was another method of adding more enemies I found. Many XFS files (for stages at least) are loaded automatically no matter what the filename is. So I was able to duplicate "EmSetStart" (which defines which enemies spawn instantly in a mercenaries stage), edit the spawn arrays in those file to point to different Em## files. And then it would spawn 48 enemies instantly, instead of the normal 12. (I also changed the position of each enemy to be on the same spot so it was quicker to test)

What you say about 01 00 00 00 makes sense. The only type of file I've edited with an array are the FSM files in stages, those have an array listing all the enemy entries for the em## files. I'm not completely sure what all the data in the array means, but I figured out enough to be able to change the size of the array and modify the data I wanted to change . Anyway, besides those FSM files, I've only edited item## and em## XFS files and they seem to have no arrays listed. And in those files 01 00 00 00 is a reliable way to find the start of each new variable defined.

I'm happy that RE5 is more moddable than I thought thanks to so much being defined in those easily available XFS files, but doing all the modding via a hex editor is a huge chore. I hope there will be some progress in completely figuring out the XFS format.
## Post #85
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2009-12-17T16:14:18+00:00
- Post Title: Re: [PC] Resident Evil 5

hi,

first i would like to thank you all for the work on reversing models.

i have a small question,is there a way to explorer levels?
i mean,is it possible to walk into unwanted-in-game area?

or a cam hack?

greets!
## Post #86
- Username: Surveyor
- Rank: veteran
- Number of posts: 97
- Joined date: Mon Mar 16, 2009 4:43 pm
- Post datetime: 2009-12-23T10:42:48+00:00
- Post Title: Re: [PC] Resident Evil 5

> Is there a new upcoming release for the MOD2OBJ converter at all? with 100% fixed UV's?
Hey, I thought UV coords were already 100% working, tell me which model poses the problem and I'll fix that!

> All the stuff I've highlighted are stuff I've tested ingame
From what I understood (correct me if I'm wrong) the game accepts any filename or extension as long as there is valid data inside?

> I'm happy that RE5 is more moddable than I thought thanks to so much being defined in those easily available XFS files
I wouldn't say soo, I spent hundreds of hours to code a working SDL decompiler, I just don't plan to spend the same amout of time on the XFS decompiler!!!

> i have a small question,is there a way to explorer levels? i mean,is it possible to walk into unwanted-in-game area?
IMO, this is easilly done by modifying the collision meshes so they don't prevent you from going anywhere you want. By deleteing all the walls but not the grounds (or else you would fall to the end of the universe), the collision files are the SBC files located in the scr directories of the stages.
## Post #87
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2009-12-24T11:36:36+00:00
- Post Title: Re: [PC] Resident Evil 5

> Reply from Surveyor
>
> From what I understood (correct me if I'm wrong) the game accepts any filename or extension as long as there is valid data inside?
For the most part, I think so. I'm pretty sure everything in stage/s###/soft/fsm/ will be loaded no matter the filename is (probably even subdirectories), I was able to make the game load more files for enemy spawns that way. For stage/s###/soft/ I think it follows a more strict filename format, but it's pretty straightforward. Like the em files always needs be called something like "s200_em00". But the game will load those as long as they're named correctly, like if you create "s200_em19", it'll load that and you can reference that file in the FSM spawn files.
## Post #88
- Username: omni
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 25, 2009 5:49 pm
- Post datetime: 2009-12-24T11:41:37+00:00
- Post Title: Re: [PC] Resident Evil 5

How about those *m* variables, any info on them and how they work? E.G. mAtackType.
## Post #89
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2009-12-24T22:41:55+00:00
- Post Title: Re: [PC] Resident Evil 5

> Reply from omni
>
> How about those *m* variables, any info on them and how they work? E.G. mAtackType.
There's many variables I haven't tested yet, or haven't been able to figure out. I usually see mAttackType as 00. It could be the variable which defines whether the enemy starts as idle or not, who knows.

I recently figured out where the different player camera changes are defined. The .ahc files define those (which are also of the XFS format). Stage .arcs have .ahc files which acts as a modifier (like in the very start of 1-2 in the room with the jeep it's a bit further zoomed out than normal). And the .ahc files in player .arcs define the basic camera (there's 3 sets of position and FOV values per camera, which are above the camera name... TRANS_DEFAULT is the normal camera, TRANS_THROW is the camera for holding any non-weapon, READY_DEFAULT is for aiming guns, READY_THROW is for aiming grenades and knife).

Normal camera swapped with TRANS_THROW, so that you get a much wider view when walking around with a gun (which you do most of the time):
[](http://www.xfire.com/profile/sectus/screenshots/?ss_file=317d85c37d9b7d3d780c17e0fc40d2a7e4a4ae2f.jpg)[](http://www.xfire.com/profile/sectus/screenshots/?ss_file=e205c2a1483761f0b8c0b0b401a995741a111dcf.jpg)

Very low FOV which basically acts as a super zoom:
[](http://www.xfire.com/profile/sectus/screenshots/?ss_file=341f988377ac53fc463bbc3b57247abc9ae2df81.jpg)
## Post #90
- Username: omni
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 25, 2009 5:49 pm
- Post datetime: 2009-12-24T23:12:43+00:00
- Post Title: Re: [PC] Resident Evil 5

> Reply from Sectus
>
> I usually see mAttackType as 00.
You mean those 00 right next to each variable or something else? Aren't those just separators?
## Post #91
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2009-12-25T02:55:40+00:00
- Post Title: Re: [PC] Resident Evil 5

> Reply from omni
>
> Sectus wrote:I usually see mAttackType as 00.
You mean those 00 right next to each variable or something else? Aren't those just separators?
The 00 after the separator. You can look at my hex screenshot as an example. The mAttackType variable is 2 variables before mbLefty (marked as 12), and the entire variable is listed as "01 00 00 00 00 00 00 00", the first "01 00 00 00" is just a separator (or well, it can be looked as such in this case), and the following "00 00 00 00" is the value of the variable.

By the way, you'll have to read values from right to left (I dunno how common this is in data files). So for instance "20 03 00 00" will be interpreted as "03 20" by the game.
## Post #92
- Username: omni
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 25, 2009 5:49 pm
- Post datetime: 2009-12-25T09:00:16+00:00
- Post Title: Re: [PC] Resident Evil 5

Ah, now I get it. Thanks.
## Post #93
- Username: judash137
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 07, 2010 4:22 pm
- Post datetime: 2010-06-09T08:03:52+00:00
- Post Title: Re: [PC] Resident Evil 5

How can I convert this Sheva model to use in 3Dmax? 
I tried Lost.Planet.ARC.Exctactor and Dmc4Model to convert pl1200.58A15856 into pl1200.OBJ but when i'm importing this OBJ by 3Dmax 2009 it show an error messeger:

"Vertex Cooordinate too big adjust vertex-scale"

Can any one help me? 

Here is the model pack :
[http://www.mediafire.com/?jwngntxkijh](http://www.mediafire.com/?jwngntxkijh)

Here is the main body model file after extract by Lost.Planet.ARC.Exctactor :
[http://www.mediafire.com/?d2gk2tvjuyh](http://www.mediafire.com/?d2gk2tvjuyh)

Here is the model file after convert to file.OBJ by Dmc4Model:
[http://www.mediafire.com/?m30nvje0mzd](http://www.mediafire.com/?m30nvje0mzd)
## Post #94
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2010-07-19T19:44:55+00:00
- Post Title: Re: [PC] Resident Evil 5

Is there a way to edit the texts of this game??
## Post #95
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2010-07-20T07:04:26+00:00
- Post Title: Re: [PC] Resident Evil 5

I found this...


-important-
* you have to make some files like "mes_event_e.txt"
-- making Original txt files.--
1. open original mes_event_e.msg file with HxD
2. click left side( in Hex value) and press "Ctrl + a" to select all,
and press "Ctrl+c"
3. make new text file, open it with notepad. and copy.
4. delete "space bar" <- this mean is makeing like this
00 03 05 07 -> 00030507

5. rename new text file mes_event_e.txt

* To use this java source, you need to install java runtime and eclipse
1. down java runtime and install. (i recommand it for develper)
2. install eclipse ths lastest version.

* Making project.
1. run eclipse and make new project.
2. click src in left tree - right click - new - class : class name is Re5MsgEditor
3. copy source below.

*Locate files
1. go to your workspace (when run eclipse first time. it will be created)
2. go to Re5MsgEditor folder
3. you can see bin, scr, folder
4. make "Original" and "Decoded" folder
5. put mes_event_e.txt file in Original folder

* run source
// decoding("mes_event_e");
if you want to decode mes_event_e.txt, delete "//"

*add source
if font don't support the character of your language.
go to findHex and add your character

```


public class Re5MsgEditor {

public static void main(String[] args)
{


// decoding("mes_event_e");
// decoding("mes_item_e");
// decoding("mes_stage1_e");
// decoding("mes_stage2_e");
// decoding("mes_stage3_e");
// decoding("mes_stage5_e");
// decoding("mes_system_e");
// decoding("mes_file_e");

// encoding("mes_event_e");
// encoding("mes_item_e");
// encoding("mes_stage1_e");
// encoding("mes_stage2_e");
// encoding("mes_stage3_e");
// encoding("mes_stage5_e");
// encoding("mes_system_e");
encoding("mes_file_e");

}

public static void decoding(String fileName)
{

File file = new File("Original\\"+fileName+".txt");
File de_file = new File("Decoded\\"+fileName+"_decoded.txt");

try
{
FileReader fr = new FileReader(file);
BufferedReader br = new BufferedReader(fr);
FileWriter fw = new FileWriter(de_file);
BufferedWriter bw = new BufferedWriter(fw);

for(int j = 0 ; j < 128 ; j++) br.read();

String readString = br.readLine();
String Hex ="";

int count = 0;


for(int i = 0 ; i < readString.length() ; i++)
{
count++;

Hex = Hex + readString.charAt(i);
if(count == 8)
{
if(!Hex.equalsIgnoreCase("00000104"))
{
if(fileName.equalsIgnoreCase("mes_item_e")) bw.write(find_mes_item_e_Alpa(Hex));
else bw.write(findAlpa(Hex));

}else
{
bw.write("#");
bw.newLine();
}

Hex = "";
count = 0;
}

}
br.close();
fr.close();
bw.close();
fw.close();


}catch(Exception e){}
}

public static void encoding(String fileName)
{

File o_file = new File("Original\\"+fileName+".txt");
File file = new File("Decoded\\"+fileName+"_decoded.txt");
File en_file = new File(fileName+"_encoded.txt");
try
{
FileReader o_fr = new FileReader(o_file);
BufferedReader o_br = new BufferedReader(o_fr);
FileReader fr = new FileReader(file);
BufferedReader br = new BufferedReader(fr);
FileWriter fw = new FileWriter(en_file);
BufferedWriter bw = new BufferedWriter(fw);

String Ori_Data = o_br.readLine();
String Header = "";
String Code = "";

for(int h = 0 ; h < 128 ; h++ ) Header = Header + Ori_Data.charAt(h);
bw.write(Header);

while(true)
{
Code = br.readLine();

if(Code == null) break;
for(int i = 0 ; i < Code.length() ; i++)
{
char ch = Code.charAt(i);
if(ch == '[')
{
for(int j = 0 ; j < 8 ; j++)
{
i = i + 1;
bw.write(Code.charAt(i));
}
}else if(ch == ']') bw.write("");
else if(ch == '#') bw.write("00000104");

else
{
if(fileName.equalsIgnoreCase("mes_item_e")) bw.write(find_mes_item_e_Hex(ch));
else bw.write(findHex(ch));
}

}
}

o_br.close();
o_fr.close();
br.close();
fr.close();
bw.close();
fw.close();


}catch(Exception e){}
}

public static String findAlpa(String ch)
{

String Alpa = ch;

if(Alpa.equalsIgnoreCase("00003B00")) Alpa ="0";
else if(Alpa.equalsIgnoreCase("02003B00")) Alpa ="1";
else if(Alpa.equalsIgnoreCase("04003B00")) Alpa ="2";
else if(Alpa.equalsIgnoreCase("06003B00")) Alpa ="3";
else if(Alpa.equalsIgnoreCase("08003B00")) Alpa ="4";
else if(Alpa.equalsIgnoreCase("0A003B00")) Alpa ="5";
else if(Alpa.equalsIgnoreCase("0C003B00")) Alpa ="6";
else if(Alpa.equalsIgnoreCase("0E003B00")) Alpa ="7";
else if(Alpa.equalsIgnoreCase("10003B00")) Alpa ="8";
else if(Alpa.equalsIgnoreCase("12003B00")) Alpa ="9";
else if(Alpa.equalsIgnoreCase("14003B00")) Alpa ="!";
else if(Alpa.equalsIgnoreCase("16003B00")) Alpa ="?";
else if(Alpa.equalsIgnoreCase("18003B00")) Alpa ="(";
else if(Alpa.equalsIgnoreCase("1A003B00")) Alpa =")";
else if(Alpa.equalsIgnoreCase("1C003B00")) Alpa =" ";
else if(Alpa.equalsIgnoreCase("1E003B00")) Alpa ="&";
else if(Alpa.equalsIgnoreCase("20003B00")) Alpa =":";
else if(Alpa.equalsIgnoreCase("22003B00")) Alpa =";";
else if(Alpa.equalsIgnoreCase("24003B00")) Alpa =",";
else if(Alpa.equalsIgnoreCase("26003B00")) Alpa =".";
else if(Alpa.equalsIgnoreCase("28003B00")) Alpa ="|";
else if(Alpa.equalsIgnoreCase("2A003B00")) Alpa ="^";
else if(Alpa.equalsIgnoreCase("2C003B00")) Alpa ="~";
else if(Alpa.equalsIgnoreCase("2E003B00")) Alpa ="-";
else if(Alpa.equalsIgnoreCase("30003B00")) Alpa ="+";
else if(Alpa.equalsIgnoreCase("32003B00")) Alpa ="/";
else if(Alpa.equalsIgnoreCase("34003B00")) Alpa ="@";
else if(Alpa.equalsIgnoreCase("36003B00")) Alpa ="$";
else if(Alpa.equalsIgnoreCase("38003B00")) Alpa ="A";
else if(Alpa.equalsIgnoreCase("3A003B00")) Alpa ="B";
else if(Alpa.equalsIgnoreCase("3C003B00")) Alpa ="C";
else if(Alpa.equalsIgnoreCase("3E003B00")) Alpa ="D";
else if(Alpa.equalsIgnoreCase("40003B00")) Alpa ="E";
else if(Alpa.equalsIgnoreCase("42003B00")) Alpa ="F";
else if(Alpa.equalsIgnoreCase("44003B00")) Alpa ="G";
else if(Alpa.equalsIgnoreCase("46003B00")) Alpa ="H";
else if(Alpa.equalsIgnoreCase("48003100")) Alpa ="I";
else if(Alpa.equalsIgnoreCase("4A003A00")) Alpa ="J";
else if(Alpa.equalsIgnoreCase("4C003B00")) Alpa ="K";
else if(Alpa.equalsIgnoreCase("4E003B00")) Alpa ="L";
else if(Alpa.equalsIgnoreCase("50003B00")) Alpa ="M";
else if(Alpa.equalsIgnoreCase("52003B00")) Alpa ="N";
else if(Alpa.equalsIgnoreCase("54003B00")) Alpa ="O";
else if(Alpa.equalsIgnoreCase("56003B00")) Alpa ="P";
else if(Alpa.equalsIgnoreCase("58003B00")) Alpa ="Q";
else if(Alpa.equalsIgnoreCase("5A003B00")) Alpa ="R";
else if(Alpa.equalsIgnoreCase("5C003B00")) Alpa ="S";
else if(Alpa.equalsIgnoreCase("5E003B00")) Alpa ="T";
else if(Alpa.equalsIgnoreCase("60003B00")) Alpa ="U";
else if(Alpa.equalsIgnoreCase("62003B00")) Alpa ="V";
else if(Alpa.equalsIgnoreCase("64003B00")) Alpa ="W";
else if(Alpa.equalsIgnoreCase("66003B00")) Alpa ="X";
else if(Alpa.equalsIgnoreCase("68003B00")) Alpa ="Y";
else if(Alpa.equalsIgnoreCase("6A003B00")) Alpa ="Z";
else if(Alpa.equalsIgnoreCase("6C003B00")) Alpa ="a";
else if(Alpa.equalsIgnoreCase("6E003B00")) Alpa ="b";
else if(Alpa.equalsIgnoreCase("70003B00")) Alpa ="c";
else if(Alpa.equalsIgnoreCase("72003B00")) Alpa ="d";
else if(Alpa.equalsIgnoreCase("74003B00")) Alpa ="e";
else if(Alpa.equalsIgnoreCase("76003B00")) Alpa ="f";
else if(Alpa.equalsIgnoreCase("78003B00")) Alpa ="g";
else if(Alpa.equalsIgnoreCase("7A003B00")) Alpa ="h";
else if(Alpa.equalsIgnoreCase("7C003500")) Alpa ="i";
else if(Alpa.equalsIgnoreCase("7E002F00")) Alpa ="j";
else if(Alpa.equalsIgnoreCase("80003B00")) Alpa ="k";
else if(Alpa.equalsIgnoreCase("82003B00")) Alpa ="l";
else if(Alpa.equalsIgnoreCase("84003B00")) Alpa ="m";
else if(Alpa.equalsIgnoreCase("86003B00")) Alpa ="n";
else if(Alpa.equalsIgnoreCase("88003B00")) Alpa ="o";
else if(Alpa.equalsIgnoreCase("8A003B00")) Alpa ="p";
else if(Alpa.equalsIgnoreCase("8C003B00")) Alpa ="q";
else if(Alpa.equalsIgnoreCase("8E003B00")) Alpa ="r";
else if(Alpa.equalsIgnoreCase("90003B00")) Alpa ="s";
else if(Alpa.equalsIgnoreCase("92003B00")) Alpa ="t";
else if(Alpa.equalsIgnoreCase("94003B00")) Alpa ="u";
else if(Alpa.equalsIgnoreCase("96003B00")) Alpa ="v";
else if(Alpa.equalsIgnoreCase("98003B00")) Alpa ="w";
else if(Alpa.equalsIgnoreCase("9A003B00")) Alpa ="x";
else if(Alpa.equalsIgnoreCase("9C003B00")) Alpa ="y";
else if(Alpa.equalsIgnoreCase("9E003B00")) Alpa ="z";
else if(Alpa.equalsIgnoreCase("1A013B00")) Alpa ="_";
else if(Alpa.equalsIgnoreCase("00000304")) Alpa ="%";

else
{

Alpa = "["+ch+"]";
//System.out.println(Alpa);
}

return Alpa;
}

public static String findHex(char ch)
{
String le = "";
char hex = ch;


if(hex == '0') le = "00003B00";
else if(hex == '1') le = "02003B00";
else if(hex == '2') le = "04003B00";
else if(hex == '3') le = "06003B00";
else if(hex == '4') le = "08003B00";
else if(hex == '5') le = "0A003B00";
else if(hex == '6') le = "0C003B00";
else if(hex == '7') le = "0E003B00";
else if(hex == '8') le = "10003B00";
else if(hex == '9') le = "12003B00";
else if(hex == '!') le = "14003B00";
else if(hex == '?') le = "16003B00";
else if(hex == '(') le = "18003B00";
else if(hex == ')') le = "1A003B00";
else if(hex == ' ') le = "1C003B00";
else if(hex == '&') le = "1E003B00";
else if(hex == ':') le = "20003B00";
else if(hex == ';') le = "22003B00";
else if(hex == ',') le = "24003B00";
else if(hex == '.') le = "26003B00";
else if(hex == '|') le = "28003B00";
else if(hex == '^') le = "2A003B00";
else if(hex == '~') le = "2C003B00";
else if(hex == '-') le = "2E003B00";
else if(hex == '+') le = "30003B00";
else if(hex == '/') le = "32003B00";
else if(hex == '@') le = "34003B00";
else if(hex == '$') le = "36003B00";
else if(hex == 'A') le = "38003B00";
else if(hex == 'B') le = "3A003B00";
else if(hex == 'C') le = "3C003B00";
else if(hex == 'D') le = "3E003B00";
else if(hex == 'E') le = "40003B00";
else if(hex == 'F') le = "42003B00";
else if(hex == 'G') le = "44003B00";
else if(hex == 'H') le = "46003B00";
else if(hex == 'I') le = "48003100";
else if(hex == 'J') le = "4A003A00";
else if(hex == 'K') le = "4C003B00";
else if(hex == 'L') le = "4E003B00";
else if(hex == 'M') le = "50003B00";
else if(hex == 'N') le = "52003B00";
else if(hex == 'O') le = "54003B00";
else if(hex == 'P') le = "56003B00";
else if(hex == 'Q') le = "58003B00";
else if(hex == 'R') le = "5A003B00";
else if(hex == 'S') le = "5C003B00";
else if(hex == 'T') le = "5E003B00";
else if(hex == 'U') le = "60003B00";
else if(hex == 'V') le = "62003B00";
else if(hex == 'W') le = "64003B00";
else if(hex == 'X') le = "66003B00";
else if(hex == 'Y') le = "68003B00";
else if(hex == 'Z') le = "6A003B00";
else if(hex == 'a') le = "6C003B00";
else if(hex == 'b') le = "6E003B00";
else if(hex == 'c') le = "70003B00";
else if(hex == 'd') le = "72003B00";
else if(hex == 'e') le = "74003B00";
else if(hex == 'f') le = "76003B00";
else if(hex == 'g') le = "78003B00";
else if(hex == 'h') le = "7A003B00";
else if(hex == 'i') le = "7C003500";
else if(hex == 'j') le = "7E002F00";
else if(hex == 'k') le = "80003B00";
else if(hex == 'l') le = "82003B00";
else if(hex == 'm') le = "84003B00";
else if(hex == 'n') le = "86003B00";
else if(hex == 'o') le = "88003B00";
else if(hex == 'p') le = "8A003B00";
else if(hex == 'q') le = "8C003B00";
else if(hex == 'r') le = "8E003B00";
else if(hex == 's') le = "90003B00";
else if(hex == 't') le = "92003B00";
else if(hex == 'u') le = "94003B00";
else if(hex == 'v') le = "96003B00";
else if(hex == 'w') le = "98003B00";
else if(hex == 'x') le = "9A003B00";
else if(hex == 'y') le = "9C003B00";
else if(hex == 'z') le = "9E003B00";
else if(hex == '_') le = "1A013B00";
else if(hex == '%') le = "00000304";

else System.out.print(hex);
return le;
}

public static String find_mes_item_e_Alpa(String ch)
{

String Alpa = ch;

if(Alpa.equalsIgnoreCase("00003C00")) Alpa ="0";
else if(Alpa.equalsIgnoreCase("02003C00")) Alpa ="1";
else if(Alpa.equalsIgnoreCase("04003C00")) Alpa ="2";
else if(Alpa.equalsIgnoreCase("06003C00")) Alpa ="3";
else if(Alpa.equalsIgnoreCase("08003C00")) Alpa ="4";
else if(Alpa.equalsIgnoreCase("0A003C00")) Alpa ="5";
else if(Alpa.equalsIgnoreCase("0C003C00")) Alpa ="6";
else if(Alpa.equalsIgnoreCase("0E003C00")) Alpa ="7";
else if(Alpa.equalsIgnoreCase("10003C00")) Alpa ="8";
else if(Alpa.equalsIgnoreCase("12003C00")) Alpa ="9";
else if(Alpa.equalsIgnoreCase("14003C00")) Alpa ="!";
else if(Alpa.equalsIgnoreCase("16003C00")) Alpa ="?";
else if(Alpa.equalsIgnoreCase("18003C00")) Alpa ="(";
else if(Alpa.equalsIgnoreCase("1A003C00")) Alpa =")";
else if(Alpa.equalsIgnoreCase("1C003C00")) Alpa =" ";
else if(Alpa.equalsIgnoreCase("1E003C00")) Alpa ="&";
else if(Alpa.equalsIgnoreCase("20003C00")) Alpa =":";
else if(Alpa.equalsIgnoreCase("22003C00")) Alpa =";";
else if(Alpa.equalsIgnoreCase("24003C00")) Alpa =",";
else if(Alpa.equalsIgnoreCase("26003C00")) Alpa =".";
else if(Alpa.equalsIgnoreCase("28003C00")) Alpa ="|";
else if(Alpa.equalsIgnoreCase("2A003C00")) Alpa ="^";
else if(Alpa.equalsIgnoreCase("2C003C00")) Alpa ="~";
else if(Alpa.equalsIgnoreCase("2E003C00")) Alpa ="-";
else if(Alpa.equalsIgnoreCase("30003C00")) Alpa ="+";
else if(Alpa.equalsIgnoreCase("32003C00")) Alpa ="/";
else if(Alpa.equalsIgnoreCase("34003C00")) Alpa ="@";
else if(Alpa.equalsIgnoreCase("36003C00")) Alpa ="$";
else if(Alpa.equalsIgnoreCase("38003C00")) Alpa ="A";
else if(Alpa.equalsIgnoreCase("3A003C00")) Alpa ="B";
else if(Alpa.equalsIgnoreCase("3C003C00")) Alpa ="C";
else if(Alpa.equalsIgnoreCase("3E003C00")) Alpa ="D";
else if(Alpa.equalsIgnoreCase("40003C00")) Alpa ="E";
else if(Alpa.equalsIgnoreCase("42003C00")) Alpa ="F";
else if(Alpa.equalsIgnoreCase("44003C00")) Alpa ="G";
else if(Alpa.equalsIgnoreCase("46003C00")) Alpa ="H";
else if(Alpa.equalsIgnoreCase("48003C00")) Alpa ="I";
else if(Alpa.equalsIgnoreCase("4A003C00")) Alpa ="J";
else if(Alpa.equalsIgnoreCase("4C003C00")) Alpa ="K";
else if(Alpa.equalsIgnoreCase("4E003C00")) Alpa ="L";
else if(Alpa.equalsIgnoreCase("50003C00")) Alpa ="M";
else if(Alpa.equalsIgnoreCase("52003C00")) Alpa ="N";
else if(Alpa.equalsIgnoreCase("54003C00")) Alpa ="O";
else if(Alpa.equalsIgnoreCase("56003C00")) Alpa ="P";
else if(Alpa.equalsIgnoreCase("58003C00")) Alpa ="Q";
else if(Alpa.equalsIgnoreCase("5A003C00")) Alpa ="R";
else if(Alpa.equalsIgnoreCase("5C003C00")) Alpa ="S";
else if(Alpa.equalsIgnoreCase("5E003C00")) Alpa ="T";
else if(Alpa.equalsIgnoreCase("60003C00")) Alpa ="U";
else if(Alpa.equalsIgnoreCase("62003C00")) Alpa ="V";
else if(Alpa.equalsIgnoreCase("64003C00")) Alpa ="W";
else if(Alpa.equalsIgnoreCase("66003C00")) Alpa ="X";
else if(Alpa.equalsIgnoreCase("68003C00")) Alpa ="Y";
else if(Alpa.equalsIgnoreCase("6A003C00")) Alpa ="Z";
else if(Alpa.equalsIgnoreCase("6C003C00")) Alpa ="a";
else if(Alpa.equalsIgnoreCase("6E003C00")) Alpa ="b";
else if(Alpa.equalsIgnoreCase("70003C00")) Alpa ="c";
else if(Alpa.equalsIgnoreCase("72003C00")) Alpa ="d";
else if(Alpa.equalsIgnoreCase("74003C00")) Alpa ="e";
else if(Alpa.equalsIgnoreCase("76003C00")) Alpa ="f";
else if(Alpa.equalsIgnoreCase("78003C00")) Alpa ="g";
else if(Alpa.equalsIgnoreCase("7A003C00")) Alpa ="h";
else if(Alpa.equalsIgnoreCase("7C003C00")) Alpa ="i";
else if(Alpa.equalsIgnoreCase("7E003C00")) Alpa ="j";
else if(Alpa.equalsIgnoreCase("80003C00")) Alpa ="k";
else if(Alpa.equalsIgnoreCase("82003C00")) Alpa ="l";
else if(Alpa.equalsIgnoreCase("84003C00")) Alpa ="m";
else if(Alpa.equalsIgnoreCase("86003C00")) Alpa ="n";
else if(Alpa.equalsIgnoreCase("88003C00")) Alpa ="o";
else if(Alpa.equalsIgnoreCase("8A003C00")) Alpa ="p";
else if(Alpa.equalsIgnoreCase("8C003C00")) Alpa ="q";
else if(Alpa.equalsIgnoreCase("8E003C00")) Alpa ="r";
else if(Alpa.equalsIgnoreCase("90003C00")) Alpa ="s";
else if(Alpa.equalsIgnoreCase("92003C00")) Alpa ="t";
else if(Alpa.equalsIgnoreCase("94003C00")) Alpa ="u";
else if(Alpa.equalsIgnoreCase("96003C00")) Alpa ="v";
else if(Alpa.equalsIgnoreCase("98003C00")) Alpa ="w";
else if(Alpa.equalsIgnoreCase("9A003C00")) Alpa ="x";
else if(Alpa.equalsIgnoreCase("9C003C00")) Alpa ="y";
else if(Alpa.equalsIgnoreCase("9E003C00")) Alpa ="z";
else if(Alpa.equalsIgnoreCase("1A013C00")) Alpa ="_";
else if(Alpa.equalsIgnoreCase("00000304")) Alpa ="%";

else
{

Alpa = "["+ch+"]";
System.out.println(Alpa);
}

return Alpa;
}

public static String find_mes_item_e_Hex(char ch)
{
String le = "";
char hex = ch;


if(hex == '0') le = "00003C00";
else if(hex == '1') le = "02003C00";
else if(hex == '2') le = "04003C00";
else if(hex == '3') le = "06003C00";
else if(hex == '4') le = "08003C00";
else if(hex == '5') le = "0A003C00";
else if(hex == '6') le = "0C003C00";
else if(hex == '7') le = "0E003C00";
else if(hex == '8') le = "10003C00";
else if(hex == '9') le = "12003C00";
else if(hex == '!') le = "14003C00";
else if(hex == '?') le = "16003C00";
else if(hex == '(') le = "18003C00";
else if(hex == ')') le = "1A003C00";
else if(hex == ' ') le = "1C003C00";
else if(hex == '&') le = "1E003C00";
else if(hex == ':') le = "20003C00";
else if(hex == ';') le = "22003C00";
else if(hex == ',') le = "24003C00";
else if(hex == '.') le = "26003C00";
else if(hex == '|') le = "28003C00";
else if(hex == '^') le = "2A003C00";
else if(hex == '~') le = "2C003C00";
else if(hex == '-') le = "2E003C00";
else if(hex == '+') le = "30003C00";
else if(hex == '/') le = "32003C00";
else if(hex == '@') le = "34003C00";
else if(hex == '$') le = "36003C00";
else if(hex == 'A') le = "38003C00";
else if(hex == 'B') le = "3A003C00";
else if(hex == 'C') le = "3C003C00";
else if(hex == 'D') le = "3E003C00";
else if(hex == 'E') le = "40003C00";
else if(hex == 'F') le = "42003C00";
else if(hex == 'G') le = "44003C00";
else if(hex == 'H') le = "46003C00";
else if(hex == 'I') le = "48003C00";
else if(hex == 'J') le = "4A003C00";
else if(hex == 'K') le = "4C003C00";
else if(hex == 'L') le = "4E003C00";
else if(hex == 'M') le = "50003C00";
else if(hex == 'N') le = "52003C00";
else if(hex == 'O') le = "54003C00";
else if(hex == 'P') le = "56003C00";
else if(hex == 'Q') le = "58003C00";
else if(hex == 'R') le = "5A003C00";
else if(hex == 'S') le = "5C003C00";
else if(hex == 'T') le = "5E003C00";
else if(hex == 'U') le = "60003C00";
else if(hex == 'V') le = "62003C00";
else if(hex == 'W') le = "64003C00";
else if(hex == 'X') le = "66003C00";
else if(hex == 'Y') le = "68003C00";
else if(hex == 'Z') le = "6A003C00";
else if(hex == 'a') le = "6C003C00";
else if(hex == 'b') le = "6E003C00";
else if(hex == 'c') le = "70003C00";
else if(hex == 'd') le = "72003C00";
else if(hex == 'e') le = "74003C00";
else if(hex == 'f') le = "76003C00";
else if(hex == 'g') le = "78003C00";
else if(hex == 'h') le = "7A003C00";
else if(hex == 'i') le = "7C003C00";
else if(hex == 'j') le = "7E003C00";
else if(hex == 'k') le = "80003C00";
else if(hex == 'l') le = "82003C00";
else if(hex == 'm') le = "84003C00";
else if(hex == 'n') le = "86003C00";
else if(hex == 'o') le = "88003C00";
else if(hex == 'p') le = "8A003C00";
else if(hex == 'q') le = "8C003C00";
else if(hex == 'r') le = "8E003C00";
else if(hex == 's') le = "90003C00";
else if(hex == 't') le = "92003C00";
else if(hex == 'u') le = "94003C00";
else if(hex == 'v') le = "96003C00";
else if(hex == 'w') le = "98003C00";
else if(hex == 'x') le = "9A003C00";
else if(hex == 'y') le = "9C003C00";
else if(hex == 'z') le = "9E003C00";

else if(hex == '_') le = "1A013C00";
else if(hex == '%') le = "00000304";

else System.out.print(hex);
return le;
}



}

```
## Post #96
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2010-07-21T13:07:23+00:00
- Post Title: Re: [PC] Resident Evil 5

> Reply from oyunceviri
>
> I found this...


-important-
* you have to make some files like "mes_event_e.txt"
-- making Original txt files.--
1. open original mes_event_e.msg file with HxD
2. click left side( in Hex value) and press "Ctrl + a" to select all,
and press "Ctrl+c"
3. make new text file, open it with notepad. and copy.
4. delete "space bar" <- this mean is makeing like this
00 03 05 07 -> 00030507

5. rename new text file mes_event_e.txt

* To use this java source, you need to install java runtime and eclipse
1. down java runtime and install. (i recommand it for develper)
2. install eclipse ths lastest version.

* Making project.
1. run eclipse and make new project.
2. click src in left tree - right click - new - class : class name is Re5MsgEditor
3. copy source below.

*Locate files
1. go to your workspace (when run eclipse first time. it will be created)
2. go to Re5MsgEditor folder
3. you can see bin, scr, folder
4. make "Original" and "Decoded" folder
5. put mes_event_e.txt file in Original folder

* run source
// decoding("mes_event_e");
if you want to decode mes_event_e.txt, delete "//"

*add source
if font don't support the character of your language.
go to findHex and add your character

Hey man, thanks, i'm creating a tool in delphi to translate the texts, it was already in development, but now some codes that you posted helped me, thanks.

Hey, did you know about this other msg format?? [viewtopic.php?f=21&t=3945&hilit=lost+planet](http://forum.xentax.com/viewtopic.php?f=21&t=3945&hilit=lost+planet)

Its from lost planet, i'm working on it too but the enconding is different from the re5.
## Post #97
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2010-08-04T18:11:22+00:00
- Post Title: Re: [PC] Resident Evil 5

Admin edit: tool was shared without permission. Removed by request. Don't do it again.

Here is a MSG2 tool of RE5 with source code. It can extract and repack the .MSG2 files.

See the "how to use" inside the .rar to guide you.

.net required to run this tool.

Enjoy
## Post #98
- Username: FunctionX
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 05, 2010 5:03 am
- Post datetime: 2010-08-07T17:54:42+00:00
- Post Title: Re: [PC] Resident Evil 5

Hey guys this is my first post here, and sorry for bump by the way  
My friend is trying to convert RE5 weapons to other game, and hes using re5_mod2obj_v31a
But after using mod2obj the files is very low poly, is this the latest version of mod2obj ? are we doing something wrong ?
## Post #99
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-08-07T18:20:26+00:00
- Post Title: Re: [PC] Resident Evil 5

sounds like your getting the lod meshes.
## Post #100
- Username: jopopo1986
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Oct 20, 2010 5:35 am
- Post datetime: 2010-10-19T21:48:56+00:00
- Post Title: Re: [PC] Resident Evil 5

Hi ,

Im trying to extrract cinematic movie of resident evil 5 but in Folder C:\Program Files\Capcom\Resident evil 5\Native PC\Movie , there is only 3 .wmv video files.
I would like found all cinematic movie of the game so i tried to use "RE5ArcTool.exe" but the movie folder is empty...

If anybody can help me, it will be nice.

Thank you.
## Post #101
- Username: jopopo1986
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-10-19T22:30:17+00:00
- Post Title: Re: [PC] Resident Evil 5

the movies are real time ....
## Post #102
- Username: pixeldamage
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Oct 26, 2010 8:26 pm
- Post datetime: 2011-01-18T19:18:50+00:00
- Post Title: Re: [PC] Resident Evil 5

Is there a way of getting the stage files from the src folders to work? i.e I have tried converting several .mod files from these and brought the obj files into max only to find a box made of thousands of triangles. I got one section from s404 which was a bunch of pipes (first recognisable scene element!) but even those had a lot of missing triangles. I really love this game and want to dissect the environment / stage / level in max. Is the mod2obj tool known to be buggy with stage files? I've found it ok with character models but aren't having much luck with the stages. Thanks in advance.
## Post #103
- Username: shekooo1986
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 08, 2011 5:46 am
- Post datetime: 2011-08-07T22:30:57+00:00
- Post Title: Re: [PC] Resident Evil 5

Hi ... i just downloaded the game from torrent and can't wait 2 play it , the problem is some of the game files is missing in NativePc folder 

i think i downloaded most of subfolders in it but (system) folder and it's contents (shader.arc & shader10.arc .... etc ) can't find them .

so plz anyone could help me uploading this files and i'll b greatful ... Thanx
## Post #104
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-08-08T05:50:15+00:00
- Post Title: Re: [PC] Resident Evil 5

As far as I know this is not a warez site. Buy it, or download a good release!
## Post #105
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-10-10T02:47:59+00:00
- Post Title: Re: [PC] Resident Evil 5

> Reply from oyunceviri
>
> I found this...


-important-
* you have to make some files like "mes_event_e.txt"
-- making Original txt files.--
1. open original mes_event_e.msg file with HxD
2. click left side( in Hex value) and press "Ctrl + a" to select all,
and press "Ctrl+c"
3. make new text file, open it with notepad. and copy.
4. delete "space bar" <- this mean is makeing like this
00 03 05 07 -> 00030507

5. rename new text file mes_event_e.txt

* To use this java source, you need to install java runtime and eclipse
1. down java runtime and install. (i recommand it for develper)
2. install eclipse ths lastest version.

* Making project.
1. run eclipse and make new project.
2. click src in left tree - right click - new - class : class name is Re5MsgEditor
3. copy source below.

*Locate files
1. go to your workspace (when run eclipse first time. it will be created)
2. go to Re5MsgEditor folder
3. you can see bin, scr, folder
4. make "Original" and "Decoded" folder
5. put mes_event_e.txt file in Original folder

* run source
// decoding("mes_event_e");
if you want to decode mes_event_e.txt, delete "//"

*add source
if font don't support the character of your language.
go to findHex and add your character
Code: Select allimport java.io.*;


public class Re5MsgEditor {

public static void main(String[] args)
{


// decoding("mes_event_e");
// decoding("mes_item_e");
// decoding("mes_stage1_e");
// decoding("mes_stage2_e");
// decoding("mes_stage3_e");
// decoding("mes_stage5_e");
// decoding("mes_system_e");
// decoding("mes_file_e");

// encoding("mes_event_e");
// encoding("mes_item_e");
// encoding("mes_stage1_e");
// encoding("mes_stage2_e");
// encoding("mes_stage3_e");
// encoding("mes_stage5_e");
// encoding("mes_system_e");
encoding("mes_file_e");

}

public static void decoding(String fileName)
{

File file = new File("Original\\"+fileName+".txt");
File de_file = new File("Decoded\\"+fileName+"_decoded.txt");

try
{
FileReader fr = new FileReader(file);
BufferedReader br = new BufferedReader(fr);
FileWriter fw = new FileWriter(de_file);
BufferedWriter bw = new BufferedWriter(fw);

for(int j = 0 ; j < 128 ; j++) br.read();

String readString = br.readLine();
String Hex ="";

int count = 0;


for(int i = 0 ; i < readString.length() ; i++)
{
count++;

Hex = Hex + readString.charAt(i);
if(count == 8)
{
if(!Hex.equalsIgnoreCase("00000104"))
{
if(fileName.equalsIgnoreCase("mes_item_e")) bw.write(find_mes_item_e_Alpa(Hex));
else bw.write(findAlpa(Hex));

}else
{
bw.write("#");
bw.newLine();
}

Hex = "";
count = 0;
}

}
br.close();
fr.close();
bw.close();
fw.close();


}catch(Exception e){}
}

public static void encoding(String fileName)
{

File o_file = new File("Original\\"+fileName+".txt");
File file = new File("Decoded\\"+fileName+"_decoded.txt");
File en_file = new File(fileName+"_encoded.txt");
try
{
FileReader o_fr = new FileReader(o_file);
BufferedReader o_br = new BufferedReader(o_fr);
FileReader fr = new FileReader(file);
BufferedReader br = new BufferedReader(fr);
FileWriter fw = new FileWriter(en_file);
BufferedWriter bw = new BufferedWriter(fw);

String Ori_Data = o_br.readLine();
String Header = "";
String Code = "";

for(int h = 0 ; h < 128 ; h++ ) Header = Header + Ori_Data.charAt(h);
bw.write(Header);

while(true)
{
Code = br.readLine();

if(Code == null) break;
for(int i = 0 ; i < Code.length() ; i++)
{
char ch = Code.charAt(i);
if(ch == '[')
{
for(int j = 0 ; j < 8 ; j++)
{
i = i + 1;
bw.write(Code.charAt(i));
}
}else if(ch == ']') bw.write("");
else if(ch == '#') bw.write("00000104");

else
{
if(fileName.equalsIgnoreCase("mes_item_e")) bw.write(find_mes_item_e_Hex(ch));
else bw.write(findHex(ch));
}

}
}

o_br.close();
o_fr.close();
br.close();
fr.close();
bw.close();
fw.close();


}catch(Exception e){}
}

public static String findAlpa(String ch)
{

String Alpa = ch;

if(Alpa.equalsIgnoreCase("00003B00")) Alpa ="0";
else if(Alpa.equalsIgnoreCase("02003B00")) Alpa ="1";
else if(Alpa.equalsIgnoreCase("04003B00")) Alpa ="2";
else if(Alpa.equalsIgnoreCase("06003B00")) Alpa ="3";
else if(Alpa.equalsIgnoreCase("08003B00")) Alpa ="4";
else if(Alpa.equalsIgnoreCase("0A003B00")) Alpa ="5";
else if(Alpa.equalsIgnoreCase("0C003B00")) Alpa ="6";
else if(Alpa.equalsIgnoreCase("0E003B00")) Alpa ="7";
else if(Alpa.equalsIgnoreCase("10003B00")) Alpa ="8";
else if(Alpa.equalsIgnoreCase("12003B00")) Alpa ="9";
else if(Alpa.equalsIgnoreCase("14003B00")) Alpa ="!";
else if(Alpa.equalsIgnoreCase("16003B00")) Alpa ="?";
else if(Alpa.equalsIgnoreCase("18003B00")) Alpa ="(";
else if(Alpa.equalsIgnoreCase("1A003B00")) Alpa =")";
else if(Alpa.equalsIgnoreCase("1C003B00")) Alpa =" ";
else if(Alpa.equalsIgnoreCase("1E003B00")) Alpa ="&";
else if(Alpa.equalsIgnoreCase("20003B00")) Alpa =":";
else if(Alpa.equalsIgnoreCase("22003B00")) Alpa =";";
else if(Alpa.equalsIgnoreCase("24003B00")) Alpa =",";
else if(Alpa.equalsIgnoreCase("26003B00")) Alpa =".";
else if(Alpa.equalsIgnoreCase("28003B00")) Alpa ="|";
else if(Alpa.equalsIgnoreCase("2A003B00")) Alpa ="^";
else if(Alpa.equalsIgnoreCase("2C003B00")) Alpa ="~";
else if(Alpa.equalsIgnoreCase("2E003B00")) Alpa ="-";
else if(Alpa.equalsIgnoreCase("30003B00")) Alpa ="+";
else if(Alpa.equalsIgnoreCase("32003B00")) Alpa ="/";
else if(Alpa.equalsIgnoreCase("34003B00")) Alpa ="@";
else if(Alpa.equalsIgnoreCase("36003B00")) Alpa ="$";
else if(Alpa.equalsIgnoreCase("38003B00")) Alpa ="A";
else if(Alpa.equalsIgnoreCase("3A003B00")) Alpa ="B";
else if(Alpa.equalsIgnoreCase("3C003B00")) Alpa ="C";
else if(Alpa.equalsIgnoreCase("3E003B00")) Alpa ="D";
else if(Alpa.equalsIgnoreCase("40003B00")) Alpa ="E";
else if(Alpa.equalsIgnoreCase("42003B00")) Alpa ="F";
else if(Alpa.equalsIgnoreCase("44003B00")) Alpa ="G";
else if(Alpa.equalsIgnoreCase("46003B00")) Alpa ="H";
else if(Alpa.equalsIgnoreCase("48003100")) Alpa ="I";
else if(Alpa.equalsIgnoreCase("4A003A00")) Alpa ="J";
else if(Alpa.equalsIgnoreCase("4C003B00")) Alpa ="K";
else if(Alpa.equalsIgnoreCase("4E003B00")) Alpa ="L";
else if(Alpa.equalsIgnoreCase("50003B00")) Alpa ="M";
else if(Alpa.equalsIgnoreCase("52003B00")) Alpa ="N";
else if(Alpa.equalsIgnoreCase("54003B00")) Alpa ="O";
else if(Alpa.equalsIgnoreCase("56003B00")) Alpa ="P";
else if(Alpa.equalsIgnoreCase("58003B00")) Alpa ="Q";
else if(Alpa.equalsIgnoreCase("5A003B00")) Alpa ="R";
else if(Alpa.equalsIgnoreCase("5C003B00")) Alpa ="S";
else if(Alpa.equalsIgnoreCase("5E003B00")) Alpa ="T";
else if(Alpa.equalsIgnoreCase("60003B00")) Alpa ="U";
else if(Alpa.equalsIgnoreCase("62003B00")) Alpa ="V";
else if(Alpa.equalsIgnoreCase("64003B00")) Alpa ="W";
else if(Alpa.equalsIgnoreCase("66003B00")) Alpa ="X";
else if(Alpa.equalsIgnoreCase("68003B00")) Alpa ="Y";
else if(Alpa.equalsIgnoreCase("6A003B00")) Alpa ="Z";
else if(Alpa.equalsIgnoreCase("6C003B00")) Alpa ="a";
else if(Alpa.equalsIgnoreCase("6E003B00")) Alpa ="b";
else if(Alpa.equalsIgnoreCase("70003B00")) Alpa ="c";
else if(Alpa.equalsIgnoreCase("72003B00")) Alpa ="d";
else if(Alpa.equalsIgnoreCase("74003B00")) Alpa ="e";
else if(Alpa.equalsIgnoreCase("76003B00")) Alpa ="f";
else if(Alpa.equalsIgnoreCase("78003B00")) Alpa ="g";
else if(Alpa.equalsIgnoreCase("7A003B00")) Alpa ="h";
else if(Alpa.equalsIgnoreCase("7C003500")) Alpa ="i";
else if(Alpa.equalsIgnoreCase("7E002F00")) Alpa ="j";
else if(Alpa.equalsIgnoreCase("80003B00")) Alpa ="k";
else if(Alpa.equalsIgnoreCase("82003B00")) Alpa ="l";
else if(Alpa.equalsIgnoreCase("84003B00")) Alpa ="m";
else if(Alpa.equalsIgnoreCase("86003B00")) Alpa ="n";
else if(Alpa.equalsIgnoreCase("88003B00")) Alpa ="o";
else if(Alpa.equalsIgnoreCase("8A003B00")) Alpa ="p";
else if(Alpa.equalsIgnoreCase("8C003B00")) Alpa ="q";
else if(Alpa.equalsIgnoreCase("8E003B00")) Alpa ="r";
else if(Alpa.equalsIgnoreCase("90003B00")) Alpa ="s";
else if(Alpa.equalsIgnoreCase("92003B00")) Alpa ="t";
else if(Alpa.equalsIgnoreCase("94003B00")) Alpa ="u";
else if(Alpa.equalsIgnoreCase("96003B00")) Alpa ="v";
else if(Alpa.equalsIgnoreCase("98003B00")) Alpa ="w";
else if(Alpa.equalsIgnoreCase("9A003B00")) Alpa ="x";
else if(Alpa.equalsIgnoreCase("9C003B00")) Alpa ="y";
else if(Alpa.equalsIgnoreCase("9E003B00")) Alpa ="z";
else if(Alpa.equalsIgnoreCase("1A013B00")) Alpa ="_";
else if(Alpa.equalsIgnoreCase("00000304")) Alpa ="%";

else
{

Alpa = "["+ch+"]";
//System.out.println(Alpa);
}

return Alpa;
}

public static String findHex(char ch)
{
String le = "";
char hex = ch;


if(hex == '0') le = "00003B00";
else if(hex == '1') le = "02003B00";
else if(hex == '2') le = "04003B00";
else if(hex == '3') le = "06003B00";
else if(hex == '4') le = "08003B00";
else if(hex == '5') le = "0A003B00";
else if(hex == '6') le = "0C003B00";
else if(hex == '7') le = "0E003B00";
else if(hex == '8') le = "10003B00";
else if(hex == '9') le = "12003B00";
else if(hex == '!') le = "14003B00";
else if(hex == '?') le = "16003B00";
else if(hex == '(') le = "18003B00";
else if(hex == ')') le = "1A003B00";
else if(hex == ' ') le = "1C003B00";
else if(hex == '&') le = "1E003B00";
else if(hex == ':') le = "20003B00";
else if(hex == ';') le = "22003B00";
else if(hex == ',') le = "24003B00";
else if(hex == '.') le = "26003B00";
else if(hex == '|') le = "28003B00";
else if(hex == '^') le = "2A003B00";
else if(hex == '~') le = "2C003B00";
else if(hex == '-') le = "2E003B00";
else if(hex == '+') le = "30003B00";
else if(hex == '/') le = "32003B00";
else if(hex == '@') le = "34003B00";
else if(hex == '$') le = "36003B00";
else if(hex == 'A') le = "38003B00";
else if(hex == 'B') le = "3A003B00";
else if(hex == 'C') le = "3C003B00";
else if(hex == 'D') le = "3E003B00";
else if(hex == 'E') le = "40003B00";
else if(hex == 'F') le = "42003B00";
else if(hex == 'G') le = "44003B00";
else if(hex == 'H') le = "46003B00";
else if(hex == 'I') le = "48003100";
else if(hex == 'J') le = "4A003A00";
else if(hex == 'K') le = "4C003B00";
else if(hex == 'L') le = "4E003B00";
else if(hex == 'M') le = "50003B00";
else if(hex == 'N') le = "52003B00";
else if(hex == 'O') le = "54003B00";
else if(hex == 'P') le = "56003B00";
else if(hex == 'Q') le = "58003B00";
else if(hex == 'R') le = "5A003B00";
else if(hex == 'S') le = "5C003B00";
else if(hex == 'T') le = "5E003B00";
else if(hex == 'U') le = "60003B00";
else if(hex == 'V') le = "62003B00";
else if(hex == 'W') le = "64003B00";
else if(hex == 'X') le = "66003B00";
else if(hex == 'Y') le = "68003B00";
else if(hex == 'Z') le = "6A003B00";
else if(hex == 'a') le = "6C003B00";
else if(hex == 'b') le = "6E003B00";
else if(hex == 'c') le = "70003B00";
else if(hex == 'd') le = "72003B00";
else if(hex == 'e') le = "74003B00";
else if(hex == 'f') le = "76003B00";
else if(hex == 'g') le = "78003B00";
else if(hex == 'h') le = "7A003B00";
else if(hex == 'i') le = "7C003500";
else if(hex == 'j') le = "7E002F00";
else if(hex == 'k') le = "80003B00";
else if(hex == 'l') le = "82003B00";
else if(hex == 'm') le = "84003B00";
else if(hex == 'n') le = "86003B00";
else if(hex == 'o') le = "88003B00";
else if(hex == 'p') le = "8A003B00";
else if(hex == 'q') le = "8C003B00";
else if(hex == 'r') le = "8E003B00";
else if(hex == 's') le = "90003B00";
else if(hex == 't') le = "92003B00";
else if(hex == 'u') le = "94003B00";
else if(hex == 'v') le = "96003B00";
else if(hex == 'w') le = "98003B00";
else if(hex == 'x') le = "9A003B00";
else if(hex == 'y') le = "9C003B00";
else if(hex == 'z') le = "9E003B00";
else if(hex == '_') le = "1A013B00";
else if(hex == '%') le = "00000304";

else System.out.print(hex);
return le;
}

public static String find_mes_item_e_Alpa(String ch)
{

String Alpa = ch;

if(Alpa.equalsIgnoreCase("00003C00")) Alpa ="0";
else if(Alpa.equalsIgnoreCase("02003C00")) Alpa ="1";
else if(Alpa.equalsIgnoreCase("04003C00")) Alpa ="2";
else if(Alpa.equalsIgnoreCase("06003C00")) Alpa ="3";
else if(Alpa.equalsIgnoreCase("08003C00")) Alpa ="4";
else if(Alpa.equalsIgnoreCase("0A003C00")) Alpa ="5";
else if(Alpa.equalsIgnoreCase("0C003C00")) Alpa ="6";
else if(Alpa.equalsIgnoreCase("0E003C00")) Alpa ="7";
else if(Alpa.equalsIgnoreCase("10003C00")) Alpa ="8";
else if(Alpa.equalsIgnoreCase("12003C00")) Alpa ="9";
else if(Alpa.equalsIgnoreCase("14003C00")) Alpa ="!";
else if(Alpa.equalsIgnoreCase("16003C00")) Alpa ="?";
else if(Alpa.equalsIgnoreCase("18003C00")) Alpa ="(";
else if(Alpa.equalsIgnoreCase("1A003C00")) Alpa =")";
else if(Alpa.equalsIgnoreCase("1C003C00")) Alpa =" ";
else if(Alpa.equalsIgnoreCase("1E003C00")) Alpa ="&";
else if(Alpa.equalsIgnoreCase("20003C00")) Alpa =":";
else if(Alpa.equalsIgnoreCase("22003C00")) Alpa =";";
else if(Alpa.equalsIgnoreCase("24003C00")) Alpa =",";
else if(Alpa.equalsIgnoreCase("26003C00")) Alpa =".";
else if(Alpa.equalsIgnoreCase("28003C00")) Alpa ="|";
else if(Alpa.equalsIgnoreCase("2A003C00")) Alpa ="^";
else if(Alpa.equalsIgnoreCase("2C003C00")) Alpa ="~";
else if(Alpa.equalsIgnoreCase("2E003C00")) Alpa ="-";
else if(Alpa.equalsIgnoreCase("30003C00")) Alpa ="+";
else if(Alpa.equalsIgnoreCase("32003C00")) Alpa ="/";
else if(Alpa.equalsIgnoreCase("34003C00")) Alpa ="@";
else if(Alpa.equalsIgnoreCase("36003C00")) Alpa ="$";
else if(Alpa.equalsIgnoreCase("38003C00")) Alpa ="A";
else if(Alpa.equalsIgnoreCase("3A003C00")) Alpa ="B";
else if(Alpa.equalsIgnoreCase("3C003C00")) Alpa ="C";
else if(Alpa.equalsIgnoreCase("3E003C00")) Alpa ="D";
else if(Alpa.equalsIgnoreCase("40003C00")) Alpa ="E";
else if(Alpa.equalsIgnoreCase("42003C00")) Alpa ="F";
else if(Alpa.equalsIgnoreCase("44003C00")) Alpa ="G";
else if(Alpa.equalsIgnoreCase("46003C00")) Alpa ="H";
else if(Alpa.equalsIgnoreCase("48003C00")) Alpa ="I";
else if(Alpa.equalsIgnoreCase("4A003C00")) Alpa ="J";
else if(Alpa.equalsIgnoreCase("4C003C00")) Alpa ="K";
else if(Alpa.equalsIgnoreCase("4E003C00")) Alpa ="L";
else if(Alpa.equalsIgnoreCase("50003C00")) Alpa ="M";
else if(Alpa.equalsIgnoreCase("52003C00")) Alpa ="N";
else if(Alpa.equalsIgnoreCase("54003C00")) Alpa ="O";
else if(Alpa.equalsIgnoreCase("56003C00")) Alpa ="P";
else if(Alpa.equalsIgnoreCase("58003C00")) Alpa ="Q";
else if(Alpa.equalsIgnoreCase("5A003C00")) Alpa ="R";
else if(Alpa.equalsIgnoreCase("5C003C00")) Alpa ="S";
else if(Alpa.equalsIgnoreCase("5E003C00")) Alpa ="T";
else if(Alpa.equalsIgnoreCase("60003C00")) Alpa ="U";
else if(Alpa.equalsIgnoreCase("62003C00")) Alpa ="V";
else if(Alpa.equalsIgnoreCase("64003C00")) Alpa ="W";
else if(Alpa.equalsIgnoreCase("66003C00")) Alpa ="X";
else if(Alpa.equalsIgnoreCase("68003C00")) Alpa ="Y";
else if(Alpa.equalsIgnoreCase("6A003C00")) Alpa ="Z";
else if(Alpa.equalsIgnoreCase("6C003C00")) Alpa ="a";
else if(Alpa.equalsIgnoreCase("6E003C00")) Alpa ="b";
else if(Alpa.equalsIgnoreCase("70003C00")) Alpa ="c";
else if(Alpa.equalsIgnoreCase("72003C00")) Alpa ="d";
else if(Alpa.equalsIgnoreCase("74003C00")) Alpa ="e";
else if(Alpa.equalsIgnoreCase("76003C00")) Alpa ="f";
else if(Alpa.equalsIgnoreCase("78003C00")) Alpa ="g";
else if(Alpa.equalsIgnoreCase("7A003C00")) Alpa ="h";
else if(Alpa.equalsIgnoreCase("7C003C00")) Alpa ="i";
else if(Alpa.equalsIgnoreCase("7E003C00")) Alpa ="j";
else if(Alpa.equalsIgnoreCase("80003C00")) Alpa ="k";
else if(Alpa.equalsIgnoreCase("82003C00")) Alpa ="l";
else if(Alpa.equalsIgnoreCase("84003C00")) Alpa ="m";
else if(Alpa.equalsIgnoreCase("86003C00")) Alpa ="n";
else if(Alpa.equalsIgnoreCase("88003C00")) Alpa ="o";
else if(Alpa.equalsIgnoreCase("8A003C00")) Alpa ="p";
else if(Alpa.equalsIgnoreCase("8C003C00")) Alpa ="q";
else if(Alpa.equalsIgnoreCase("8E003C00")) Alpa ="r";
else if(Alpa.equalsIgnoreCase("90003C00")) Alpa ="s";
else if(Alpa.equalsIgnoreCase("92003C00")) Alpa ="t";
else if(Alpa.equalsIgnoreCase("94003C00")) Alpa ="u";
else if(Alpa.equalsIgnoreCase("96003C00")) Alpa ="v";
else if(Alpa.equalsIgnoreCase("98003C00")) Alpa ="w";
else if(Alpa.equalsIgnoreCase("9A003C00")) Alpa ="x";
else if(Alpa.equalsIgnoreCase("9C003C00")) Alpa ="y";
else if(Alpa.equalsIgnoreCase("9E003C00")) Alpa ="z";
else if(Alpa.equalsIgnoreCase("1A013C00")) Alpa ="_";
else if(Alpa.equalsIgnoreCase("00000304")) Alpa ="%";

else
{

Alpa = "["+ch+"]";
System.out.println(Alpa);
}

return Alpa;
}

public static String find_mes_item_e_Hex(char ch)
{
String le = "";
char hex = ch;


if(hex == '0') le = "00003C00";
else if(hex == '1') le = "02003C00";
else if(hex == '2') le = "04003C00";
else if(hex == '3') le = "06003C00";
else if(hex == '4') le = "08003C00";
else if(hex == '5') le = "0A003C00";
else if(hex == '6') le = "0C003C00";
else if(hex == '7') le = "0E003C00";
else if(hex == '8') le = "10003C00";
else if(hex == '9') le = "12003C00";
else if(hex == '!') le = "14003C00";
else if(hex == '?') le = "16003C00";
else if(hex == '(') le = "18003C00";
else if(hex == ')') le = "1A003C00";
else if(hex == ' ') le = "1C003C00";
else if(hex == '&') le = "1E003C00";
else if(hex == ':') le = "20003C00";
else if(hex == ';') le = "22003C00";
else if(hex == ',') le = "24003C00";
else if(hex == '.') le = "26003C00";
else if(hex == '|') le = "28003C00";
else if(hex == '^') le = "2A003C00";
else if(hex == '~') le = "2C003C00";
else if(hex == '-') le = "2E003C00";
else if(hex == '+') le = "30003C00";
else if(hex == '/') le = "32003C00";
else if(hex == '@') le = "34003C00";
else if(hex == '$') le = "36003C00";
else if(hex == 'A') le = "38003C00";
else if(hex == 'B') le = "3A003C00";
else if(hex == 'C') le = "3C003C00";
else if(hex == 'D') le = "3E003C00";
else if(hex == 'E') le = "40003C00";
else if(hex == 'F') le = "42003C00";
else if(hex == 'G') le = "44003C00";
else if(hex == 'H') le = "46003C00";
else if(hex == 'I') le = "48003C00";
else if(hex == 'J') le = "4A003C00";
else if(hex == 'K') le = "4C003C00";
else if(hex == 'L') le = "4E003C00";
else if(hex == 'M') le = "50003C00";
else if(hex == 'N') le = "52003C00";
else if(hex == 'O') le = "54003C00";
else if(hex == 'P') le = "56003C00";
else if(hex == 'Q') le = "58003C00";
else if(hex == 'R') le = "5A003C00";
else if(hex == 'S') le = "5C003C00";
else if(hex == 'T') le = "5E003C00";
else if(hex == 'U') le = "60003C00";
else if(hex == 'V') le = "62003C00";
else if(hex == 'W') le = "64003C00";
else if(hex == 'X') le = "66003C00";
else if(hex == 'Y') le = "68003C00";
else if(hex == 'Z') le = "6A003C00";
else if(hex == 'a') le = "6C003C00";
else if(hex == 'b') le = "6E003C00";
else if(hex == 'c') le = "70003C00";
else if(hex == 'd') le = "72003C00";
else if(hex == 'e') le = "74003C00";
else if(hex == 'f') le = "76003C00";
else if(hex == 'g') le = "78003C00";
else if(hex == 'h') le = "7A003C00";
else if(hex == 'i') le = "7C003C00";
else if(hex == 'j') le = "7E003C00";
else if(hex == 'k') le = "80003C00";
else if(hex == 'l') le = "82003C00";
else if(hex == 'm') le = "84003C00";
else if(hex == 'n') le = "86003C00";
else if(hex == 'o') le = "88003C00";
else if(hex == 'p') le = "8A003C00";
else if(hex == 'q') le = "8C003C00";
else if(hex == 'r') le = "8E003C00";
else if(hex == 's') le = "90003C00";
else if(hex == 't') le = "92003C00";
else if(hex == 'u') le = "94003C00";
else if(hex == 'v') le = "96003C00";
else if(hex == 'w') le = "98003C00";
else if(hex == 'x') le = "9A003C00";
else if(hex == 'y') le = "9C003C00";
else if(hex == 'z') le = "9E003C00";

else if(hex == '_') le = "1A013C00";
else if(hex == '%') le = "00000304";

else System.out.print(hex);
return le;
}



}

Thanks! Could you support those chars:

> ä
>
> ç
>
> è
>
> é
>
> ê
>
> ë
>
> ì
>
> í
>
> î
>
> ï
>
> ò
>
> ó
>
> ô
>
> ö
>
> ù
>
> ú
>
> û
>
> ü
>
> Ą
>
> Ć
>
> Ĕ
>
> Ű
>
> Ů
>
> Ý
>
> Ă
>
> Đ
>
> ą
>
> ę
>
> ě
>
> ĺ
>
> ŕ
>
> ř
>
> ś
>
> š
>
> ť
>
> ű
>
> ů
>
> ý
>
> ź
>
> ž
>
> ż
>
> ă
>
> ð
>
> ţ
>
> Г
>
> Е
>
> Ё
>
> И
>
> П
>
> ь
>
> Ў
>
> а
>
> б
>
> в
>
> г
>
> е
>
> ё
>
> з
>
> и
>
> к
>
> н
>
> о
>
> п
>
> р
>
> с
>
> у
>
> ъ
>
> я
>
> є
>
> ѕ
>
> ќ
>
> џ
>
> ћ
>
> Í
>
> Ó
>
> Ô
>
> à
>
> á
>
> â
>
> э
>
> Ê

Thanks! I don't know hexvalue=normal char. Could you help me?
