## Post #1
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2011-05-17T16:44:23+00:00
- Post Title: The Witcher 2

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-17T20:37:50+00:00
- Post Title: The Witcher 2

I doubt this format will be supported they seem to have ripped off unreal engine's format without actually using the unreal engine.
## Post #3
- Username: voltagex
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 18, 2011 7:04 am
- Post datetime: 2011-05-17T23:08:27+00:00
- Post Title: The Witcher 2

Smaller sample at [http://filevo.com/dnvemmwnixa7.html](http://filevo.com/dnvemmwnixa7.html)

The retail/GOG/Steam releases all seem to be set up differently in the way the files are laid out in the game directory. 

The folder CookedPC would point to Unreal though - but I thought this engine was custom?
## Post #4
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-05-18T06:15:08+00:00
- Post Title: The Witcher 2

> Reply from chrrox
>
> I doubt this format will be supported they seem to have ripped off unreal engine's format without actually using the unreal engine.What? their archive format looks nothing like unreal packages.
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-18T10:43:57+00:00
- Post Title: The Witcher 2

you got an extractor working?
## Post #6
- Username: destiny7
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 18, 2011 7:03 pm
- Post datetime: 2011-05-18T11:29:00+00:00
- Post Title: The Witcher 2

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: zeeh
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Jul 26, 2009 9:10 am
- Post datetime: 2011-05-18T15:26:18+00:00
- Post Title: The Witcher 2

en0.w2strings seems to have an encrypted/xored block.
## Post #8
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-05-18T20:29:20+00:00
- Post Title: The Witcher 2

> Reply from chrrox
>
> you got an extractor working?Yes, I have not committed my code to my repository yet though.
## Post #9
- Username: zeeh
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Jul 26, 2009 9:10 am
- Post datetime: 2011-05-18T20:51:49+00:00
- Post Title: The Witcher 2

> Reply from Rick
>
> chrrox wrote:you got an extractor working?Yes, I have not committed my code to my repository yet though.

Good news  I wish it works with *.w2strings files too.
## Post #10
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-05-18T20:52:33+00:00
- Post Title: The Witcher 2

It won't, w2strings files are another beast entirely, not an archive file.
## Post #11
- Username: voltagex
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 18, 2011 7:04 am
- Post datetime: 2011-05-19T00:37:20+00:00
- Post Title: The Witcher 2

> Reply from Rick
>
> chrrox wrote:you got an extractor working?Yes, I have not committed my code to my repository yet though.

Is it GitHub or something so I can subscribe to your commits?
## Post #12
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-05-19T01:14:09+00:00
- Post Title: The Witcher 2

> Reply from voltagex
>
> Is it GitHub or something so I can subscribe to your commits?[http://cia.vc/stats/project/red](http://cia.vc/stats/project/red)
[http://svn.gib.me/public/red](http://svn.gib.me/public/red)
## Post #13
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-05-19T01:16:33+00:00
- Post Title: The Witcher 2

I'll probably commit my unpacking code soon; today I've been working on the w2scripts file (got most of it read -- need to write disassembler ).
## Post #14
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-19T11:11:59+00:00
- Post Title: The Witcher 2

ok here is a basic bms its not done yet.
but you re right the file format is not that bad.

```
get unk01 long
get files long
get unk02 long
get tableoff long
goto tableoff
for i = 0 < files
get nsize short
getdstring name nsize
get unk03 long
get unk04 long
get size long
get null01 long
get offset long
get null02 long
get zsize long
get null03 long
log name offset zsize
next i

```


Can you help me understand this

```
            {
                var op = input[i++];
                var control = (op >> 5) & 0x07;
                
                if (control == 0)
                {
                    // uncompressed blob
                    int length = 1 + (op & 0x1F);
                    Array.Copy(input, i, output, o, length);
                    i += length;
                    o += length;
                }
                else
                {
                    int length;

                    if (control == 7)
                    {
                        length = 6 + input[i++];
                    }
                    else
                    {
                        length = control - 1;
                    }
                    length += 3;

                    int offset = (op & 0x1F) << 8;
                    offset |= input[i++];

                    offset = o - 1 - offset;

                    if (offset + length > o)
                    {
                        while (length > 0)
                        {
                            output[o++] = output[offset++];
                            length--;
                        }
                    }
                    else
                    {
                        Array.Copy(output, offset, output, o, length);
                        o += length;
                    }
                }
            }


```


also the bit about the cd key needed for dlc packages.
## Post #15
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-05-19T18:18:43+00:00
- Post Title: The Witcher 2

That's the compression scheme Witcher 2 uses in its archive files. As for the CDKey -- file names are obfuscated in DLC DZIPs using the CDKey.
## Post #16
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-19T23:56:31+00:00
- Post Title: Re: The Witcher 2

ah the compression is lzf
## Post #17
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-05-20T00:29:28+00:00
- Post Title: Re: The Witcher 2

Thanks, it was simple enough that I didn't go hunting for what algo it was.
## Post #18
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-20T01:40:41+00:00
- Post Title: Re: The Witcher 2

here is the bms script.
you need to use the 64 bit quickbms to extract it all.

```
comtype COMP_LZF
get unk01 long
get files long
get unk02 long
get tableoff longlong
for i = 0 < files
goto tableoff
get nsize short
getdstring name nsize
get unk03 long
get unk04 long
get size longlong
get offset longlong
get zsize longlong
savepos tableoff
goto offset
get offadd long
math offset + offadd
math zsize - offadd
clog name offset zsize size
next i

```
## Post #19
- Username: voltagex
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 18, 2011 7:04 am
- Post datetime: 2011-05-20T04:11:51+00:00
- Post Title: Re: The Witcher 2

How do you guys work this stuff out so quickly? I'd love to learn to write unpackers.
## Post #20
- Username: voltagex
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed May 18, 2011 7:04 am
- Post datetime: 2011-05-20T04:18:59+00:00
- Post Title: Re: The Witcher 2

Edit: I'm an idiot
## Post #21
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-05-20T04:53:09+00:00
- Post Title: Re: The Witcher 2

> Reply from voltagex
>
> Rick, that code is pretty cool, but it's missing Gibbed.Helpers - are you keeping it secret?No, if you export with a proper SVN client it will pull it from an external.
## Post #22
- Username: Nemmay
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri May 20, 2011 2:58 pm
- Post datetime: 2011-05-20T06:59:51+00:00
- Post Title: Re: The Witcher 2

Hey Rick, took a look at your code, pretty neat; sadly, I don't understand most of it, haha. Have you made any progress on reversing the process and repacking into a dzip?
## Post #23
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-05-20T07:12:57+00:00
- Post Title: Re: The Witcher 2

Don't need to, the game will override dzip contents with those that are on the disk.
## Post #24
- Username: Nemmay
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri May 20, 2011 2:58 pm
- Post datetime: 2011-05-20T07:25:45+00:00
- Post Title: Re: The Witcher 2

> Reply from Rick
>
> Don't need to, the game will override dzip contents with those that are on the disk.

So, you just place the folder where the dzip would usually be and the game will use it?

EDIT: Just tried it, doesn't seem to work. I don't want to sound too needy, but you sure there wouldn't be away you can release something to repack it into dzip for the heck of it?
## Post #25
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-05-20T07:54:54+00:00
- Post Title: Re: The Witcher 2

It does work as far as I can tell.

IE:

From pack0.dzip: engine\textures\icons\witcher.xbm
Placed in CookedPC\engine\textures\icons\witcher.xbm

The game will read the one on the disk.
## Post #26
- Username: Nemmay
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri May 20, 2011 2:58 pm
- Post datetime: 2011-05-20T08:02:44+00:00
- Post Title: Re: The Witcher 2

> Reply from Rick
>
> It does work as far as I can tell.

IE:

From pack0.dzip: engine\textures\icons\witcher.xbm
Placed in CookedPC\engine\textures\icons\witcher.xbm

The game will read the one on the disk.

Say, if you used your legit serial to deserialize your .dlc file and extract it, how would you get it back into dzip form for it to work? I've tried this, and it wont load anything from just a folder.
## Post #27
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-05-20T08:25:52+00:00
- Post Title: Re: The Witcher 2

Why would you want to repack DLC?
## Post #28
- Username: Nemmay
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri May 20, 2011 2:58 pm
- Post datetime: 2011-05-20T08:28:39+00:00
- Post Title: Re: The Witcher 2

> Reply from Rick
>
> Why would you want to repack DLC?

They wont load from just a folder, only dzip.
## Post #29
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-20T11:56:38+00:00
- Post Title: Re: The Witcher 2

To export the svn just use
"C:\Program Files\Subversion\bin\svn.exe" export [http://svn.gib.me/public/red](http://svn.gib.me/public/red) C:\red\
## Post #30
- Username: Psientist
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Feb 17, 2011 9:27 pm
- Post datetime: 2011-05-20T19:02:22+00:00
- Post Title: Re: The Witcher 2

.XBM textures? What manner of witchcraft is this?!

Seriously though, anyone got a program to recommend for err... doing anything with them?
## Post #31
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-05-20T20:24:05+00:00
- Post Title: Re: The Witcher 2

I'm working on a viewer/editor for W2RC files.
## Post #32
- Username: kimono
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 01, 2009 6:10 am
- Post datetime: 2011-05-20T23:31:05+00:00
- Post Title: Re: The Witcher 2

Your work is much appreciated Rick, thanks for all this. Psientist I had made a thread in another section about the texture format although chorrax replied saying they were infact in the dds format and need a header added, unfortunately I'm not sure of what he means. Either way thanks again for the hard work lads
## Post #33
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-21T00:29:23+00:00
- Post Title: Re: The Witcher 2

here is a converter
use the xbm to dds converter like this
c:\quickbms\quickbms.exe -F "*.xbm" c:\xbm.bms c:\xbm_folder c:\extracted

```

findloc start string \x3A\x5C
print "%start%"
goto start
get null string
get name basename
string name + .dds
getdstring null 0xA
get width long
get height long
get null byte
get mips long
get null byte
get type short
savepos offset
get size asize
set size2 size
math size2 - offset

if type == 0x20
putVarChr MEMORY_FILE 0x57 0x31 byte
endif
if type == 0x30
putVarChr MEMORY_FILE 0x57 0x33 byte
endif
if type == 0x40
putVarChr MEMORY_FILE 0x57 0x35 byte
endif
putVarChr MEMORY_FILE 0xC height long
putVarChr MEMORY_FILE 0x10 width long
append
log MEMORY_FILE offset size2
append
math size2 + 0x80
log name 0 size2 MEMORY_FILE



```
## Post #34
- Username: Psientist
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Feb 17, 2011 9:27 pm
- Post datetime: 2011-05-21T00:48:17+00:00
- Post Title: Re: The Witcher 2

yer a regular saint chrrox, many thanks!
## Post #35
- Username: incarn
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jan 01, 2010 9:47 am
- Post datetime: 2011-05-21T02:57:25+00:00
- Post Title: Re: The Witcher 2

I cannot seem to find the 64 bit version of quickbms?

Neither google, nor the forums search helps me.. (I may be beyond help though)

Using the standard V of quickbms I get 
"Error: the variable index is invalid, there is an error in this tool"

win 7 64 bit

EDIT:  You may all stop panicing now. Calm down. I found the 64Bit version. Feel free to have a non-alcoholic beverage on me.
## Post #36
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-05-21T03:31:11+00:00
- Post Title: Re: The Witcher 2

> Reply from incarn
>
> I cannot seem to find the 64 bit version of quickbms?

Neither google, nor the forums search helps me.. (I may be beyond help though)

Using the standard V of quickbms I get 
"Error: the variable index is invalid, there is an error in this tool"

win 7 64 bit

EDIT:  You may all stop panicing now. Calm down. I found the 64Bit version. Feel free to have a non-alcoholic beverage on me.
Easy:
[http://aluigi.org/papers.htm#quickbms](http://aluigi.org/papers.htm#quickbms)
## Post #37
- Username: Nemmay
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri May 20, 2011 2:58 pm
- Post datetime: 2011-05-21T04:32:58+00:00
- Post Title: Re: The Witcher 2

```
or DLC archives?)
   at Gibbed.RED.FileFormats.PackageFile.Deserialize(Stream input, Nullable`1 de
cryptKey) in C:\Users\Cody\Desktop\redNew\trunk\Gibbed.RED.FileFormats\PackageFi
le.cs:line 148
   at Gibbed.RED.FileFormats.PackageFile.DeserializeWithCDKey(Stream input, Stri
ng cdkey) in C:\Users\Cody\Desktop\redNew\trunk\Gibbed.RED.FileFormats\PackageFi
le.cs:line 87
   at Gibbed.RED.Unpack.Program.Main(String[] args) in C:\Users\Cody\Desktop\red
```


When using a legit cdkey, it doesn't work with extracting the .dlc. I'm a 100% sure that the key was right, can you give an example of the command line stuff with the cdkey so I know I did it right? Thanks.
## Post #38
- Username: redavatar
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat May 21, 2011 4:12 pm
- Post datetime: 2011-05-21T08:33:53+00:00
- Post Title: Re: The Witcher 2

> Reply from chrrox
>
> here is a converter
use the xbm to dds converter like this
c:\quickbms\quickbms.exe -F "*.xbm" c:\xbm.bms c:\xbm_folder c:\extracted

Hey, thanks a lot for that! But is there a way to do the opposite? Otherwise there's little use since we can't convert our DDS files back to XBM for the game to use them.
## Post #39
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2011-05-21T09:30:34+00:00
- Post Title: Re: The Witcher 2

> Reply from chrrox
>
> here is a converter...
this is not a valid script, he's wrong on some textures (\environment_levels\detailmaps\* for example), and another is wrong with the size.
there is corrected script (make nomips DDS textures):

```

findloc c_type string "TCM_"
goto c_type
getct c_type string 0x8C

#TCM_None - ???
#TCM_DXTNoAlpha,TCM_Normals - DXT1
#TCM_DXTAlpha, TCM_NormalsHigh - DXT5
if c_type == "TCM_DXTAlpha"
	putvarchr MEMORY_FILE 0x57 0x35 byte #DXT5
endif
if c_type == "TCM_NormalsHigh"
	putvarchr MEMORY_FILE 0x57 0x35 byte #DXT5
endif

findloc start string \x3a\x5c
goto start
get null string
get name basename
string name + .dds
getdstring null 0x06
get mips long
get width long
get height long
get MaxSize long
get size long
savepos offset

putVarChr MEMORY_FILE 0xC height long
putVarChr MEMORY_FILE 0x10 width long
append
log MEMORY_FILE offset size
append

math size + 0x80
log name 0 size MEMORY_FILE

```
## Post #40
- Username: Psientist
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Feb 17, 2011 9:27 pm
- Post datetime: 2011-05-21T09:51:34+00:00
- Post Title: Re: The Witcher 2

The old script ended up turning some images like this: 

I'll try your script hhrhhr, many thanks!
## Post #41
- Username: oveja
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Feb 24, 2011 4:35 am
- Post datetime: 2011-05-21T10:08:24+00:00
- Post Title: Re: The Witcher 2

How do *.w2strings the decryption?
The file header("CR2Ws") is different.
## Post #42
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-21T11:32:07+00:00
- Post Title: Re: The Witcher 2

I dint really test it much lol.
people just kept bugging me alot for one.
it was a few character textures that had errors all it took was changing txt 1 to 5.
## Post #43
- Username: guilhermetutilo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat May 21, 2011 8:05 pm
- Post datetime: 2011-05-21T12:11:21+00:00
- Post Title: Re: The Witcher 2

Someone managed to extract the texts of the game? I'm trying to translate into Portuguese
## Post #44
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2011-05-21T17:06:23+00:00
- Post Title: Re: The Witcher 2

tools for xbm->tga and tga->xbm converting: [witcher2_texture_converter.zip](http://narod.ru/disk/13588000001/witcher2_texture_converter.zip.html) (thx chrrox for initial edition :)

usage: put quickbms.exe with unpacked files.

xbm2dds.cmd path_to_xbm
it make backup of original .xbm and produce 2 files:
filename_DXT(1,5).bin - some binary info need for export
filename_DXT(1,5).tga - your texture

when texture edited you can use next script: dds2xbm.cmd path_to_tga, it make new .xbm.
don't convert .tga files without _DXT1 or _DXT5 suffix.

example:
..

p.s.
nvcompress.exe and nvdecompress.exe take from [GPU Accelerated Texture Compression x64](http://developer.nvidia.com/gpu-accelerated-texture-compression) by NVidia, maybe they are not working on 32-bit system.
## Post #45
- Username: guilhermetutilo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat May 21, 2011 8:05 pm
- Post datetime: 2011-05-21T17:26:11+00:00
- Post Title: Re: The Witcher 2

> Reply from hhrhhr
>
> tools for xbm->tga and tga->xbm converting: witcher2_texture_converter.zip (thx chrrox for initial edition 

usage: put quickbms.exe with unpacked files.

xbm2dds.cmd path_to_xbm
it make backup of original .xbm and produce 2 files:
filename_DXT(1,5).bin - some binary info need for export
filename_DXT(1,5).tga - your texture

when texture edited you can use next script: dds2xbm.cmd path_to_tga, it make new .xbm.
don't convert .tga files without _DXT1 or _DXT5 suffix.

example:
..

p.s.
nvcompress.exe and nvdecompress.exe take from GPU Accelerated Texture Compression x64 by NVidia, maybe they are not working on 32-bit system.

You hava a pack/unpack dzip files?? Because i want to translate to brazilian portugese
## Post #46
- Username: redavatar
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat May 21, 2011 4:12 pm
- Post datetime: 2011-05-21T17:27:06+00:00
- Post Title: Re: The Witcher 2

Great this is what I needed! I made my own dice-game graphics in the first game (sensual fantasy theme using Luis Royo images - fit the game theme more) and want to do the same now. If anyone wants the result, let me know and I'll post them!
## Post #47
- Username: nyates
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 22, 2011 2:41 am
- Post datetime: 2011-05-21T18:43:22+00:00
- Post Title: Re: The Witcher 2

Im trying to manually find a way to edit a loot table to insert items into the game. Not necessarily new ones, but existing ones. The loot tables in globals/loot tables dont seem to really correlate to what the mobs are dropping in game. Nor, when edited do they drop what I politely ask them to. 

Any thoughts?

I also edited items/def_shops in an attempt to edit the inventory of a shop. See if that route would work. No luck. Ummmm... Any thoughts on that either?
## Post #48
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-05-21T19:12:58+00:00
- Post Title: Re: The Witcher 2

Shop inventories are probably saved and regenerated "daily" (game daily), have you waited 24 hours?
## Post #49
- Username: nyates
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 22, 2011 2:41 am
- Post datetime: 2011-05-21T19:18:31+00:00
- Post Title: Re: The Witcher 2

Yeah, I waited 24 hours. Meditated or whatever for a bit. 2 days even. Bought the item I replaced, let it respawn. The old item is not even in the def_shops list anymore, but respawns just the same. My file is in the right spot I believe... CookedPC\items\def_shops.xml or whatever. Wonder what I'm doing wrong...

I didn't even fabricate a new line item, I just copied one from one store and added it to another. Should have been ok. Perhaps there's a corresponding file somewhere that needs edited as well in order for this to take. Sigh


EDIT:
I got it. My stupid program was auto "correcting" the format to .csv. 

Sigh. Working now. Thanks everyone.
## Post #50
- Username: chalon
- Rank: n00b
- Number of posts: 16
- Joined date: Sun May 22, 2011 3:20 am
- Post datetime: 2011-05-21T19:41:41+00:00
- Post Title: Re: The Witcher 2

> Reply from oveja
>
> How do *.w2strings the decryption?
The file header("CR2Ws") is different.

They don't have CR2Ws at the beginning, they have 0xc9000000.

It looks like some kind of lookup table with compression and/or encryption. The beginning of the file appears to be sets of 5 bytes (probably an address or index?), followed by the lookup key string in ASCII. So that section wouldn't be too hard to figure out most likely. The problem is after all the lookups, the data is just all mangled.

> Reply from nyates
>
> Yeah, I waited 24 hours. Meditated or whatever for a bit. 2 days even. Bought the item I replaced, let it respawn. The old item is not even in the def_shops list anymore, but respawns just the same. My file is in the right spot I believe... CookedPC\items\def_shops.xml or whatever. Wonder what I'm doing wrong...

Try leaving the area, move some ways away, and come back. Even without changing the shops XML, if you stay at the vendor and just meditate, the inventory will not be refreshed.
## Post #51
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2011-05-23T01:57:28+00:00
- Post Title: Re: The Witcher 2

hi, has anyone made any headway in cracking the w2ent files? they look like they're responsible for assigning model parts. could be very useful for a character replacement mod.
## Post #52
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-05-23T02:06:02+00:00
- Post Title: Re: The Witcher 2

It's a generic resource format that's used to instantiate native C++ classes with data, not specific to w2ent.
## Post #53
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2011-05-23T02:08:58+00:00
- Post Title: Re: The Witcher 2

so you already opened it or do you mean there's already a program that opens it?
## Post #54
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-05-23T02:12:27+00:00
- Post Title: Re: The Witcher 2

I'm working on it now, it's a big complex beast of a format.
## Post #55
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2011-05-23T02:23:06+00:00
- Post Title: Re: The Witcher 2

alright. thanks
## Post #56
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-05-23T05:06:16+00:00
- Post Title: Re: The Witcher 2

I've committed my most recent code which has W2RC related stuff -- though note it's not in any shape for saving this data back out, it's still in the research phase.
## Post #57
- Username: Sanya
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Mar 17, 2011 5:36 pm
- Post datetime: 2011-05-23T16:47:15+00:00
- Post Title: Re: The Witcher 2

What about unpacking game models formats?

Any chances that it would be done soon? ^^
## Post #58
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-23T17:28:31+00:00
- Post Title: Re: The Witcher 2

The model format is not hard its the file structure around the model data that is a beast to deal with as rick said.
I will look at his code and if i can understand whats going on I will attemp to make an importer.
## Post #59
- Username: inforsir
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 24, 2011 3:45 am
- Post datetime: 2011-05-23T19:53:09+00:00
- Post Title: Re: The Witcher 2

> Reply from nyates
>
> Yeah, I waited 24 hours. Meditated or whatever for a bit. 2 days even. Bought the item I replaced, let it respawn. The old item is not even in the def_shops list anymore, but respawns just the same. My file is in the right spot I believe... CookedPC\items\def_shops.xml or whatever. Wonder what I'm doing wrong...

I didn't even fabricate a new line item, I just copied one from one store and added it to another. Should have been ok. Perhaps there's a corresponding file somewhere that needs edited as well in order for this to take. Sigh


EDIT:
I got it. My stupid program was auto "correcting" the format to .csv. 

Sigh. Working now. Thanks everyone.

mind telling me how u did that i kinda need help with it : \



now with the extractor i cant get it to work every time i try it tells me that "the bms script uses more agruments than how much is supported by this tool"

most liky mean im a idoit and dont know how to use c:\quickbms\quickbms.exe -F "*.xbm" c:\xbm.bms c:\xbm_folder c:\extracted  assuming that this is use for the directory for a shortcut to it.
would also mean i dont know what script to use

basically my prob is how to extract the dzip : \
## Post #60
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2011-05-23T21:19:00+00:00
- Post Title: Re: The Witcher 2

For .dzip, use the quickbms_64, create a new text document, copy paste chroxx script into it, save it and drop the file over quickbms_64, then select pack0.dzip, after that another window will popup where to extract the files, that's all. 

For .xbm textures, do it like this, extract the convertor, copy quickbms.exe in the same folder, drop the xbm2tga over quickbms exe, select the texture (copy it first in the same folder) and same as above select where to save it (in the same folder will be good) now you'll get a .dds file and a .bin one, so to get the .tga file drop the .dds file over nvdecompress.exe and your done, you have your .tga file.
## Post #61
- Username: inforsir
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 24, 2011 3:45 am
- Post datetime: 2011-05-24T01:59:19+00:00
- Post Title: Re: The Witcher 2

okay its giving me this dono why heres a pic but i did every thing u said for the dzips

[](http://imageshack.us/photo/my-images/714/unledzcp.png/)

Uploaded with [ImageShack.us](http://imageshack.us)
## Post #62
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-24T03:29:37+00:00
- Post Title: Re: The Witcher 2

you need to run the 64 bit exe
## Post #63
- Username: inforsir
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 24, 2011 3:45 am
- Post datetime: 2011-05-24T03:42:48+00:00
- Post Title: Re: The Witcher 2

> Reply from chrrox
>
> you need to run the 64 bit exe
 that is the 64 bit

unless theres another .exe in the folder im on windows 7 2 that might be in it
## Post #64
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2011-05-24T04:12:21+00:00
- Post Title: Re: The Witcher 2

save the text document as a bms file.
## Post #65
- Username: inforsir
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 24, 2011 3:45 am
- Post datetime: 2011-05-24T04:42:03+00:00
- Post Title: Re: The Witcher 2

> Reply from odrin
>
> save the text document as a bms file.

just saved it as a .bms but it still comes up with the same error and i did it as cmihai said and saved it as a .bms, so right now i have no idea what im doin wrong lol
## Post #66
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2011-05-24T04:45:46+00:00
- Post Title: Re: The Witcher 2

when you save it again select unicode under encoding.
## Post #67
- Username: inforsir
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 24, 2011 3:45 am
- Post datetime: 2011-05-25T12:49:39+00:00
- Post Title: Re: The Witcher 2

> Reply from nyates
>
> Yeah, I waited 24 hours. Meditated or whatever for a bit. 2 days even. Bought the item I replaced, let it respawn. The old item is not even in the def_shops list anymore, but respawns just the same. My file is in the right spot I believe... CookedPC\items\def_shops.xml or whatever. Wonder what I'm doing wrong...

I didn't even fabricate a new line item, I just copied one from one store and added it to another. Should have been ok. Perhaps there's a corresponding file somewhere that needs edited as well in order for this to take. Sigh


EDIT:
I got it. My stupid program was auto "correcting" the format to .csv. 

Sigh. Working now. Thanks everyone.

lol i finaly got it extracted ever time i edit one to add  the elder items to a shop it wont work : \ or im doin it wrong
## Post #68
- Username: Fernandojj
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 25, 2011 10:15 pm
- Post datetime: 2011-05-25T14:20:44+00:00
- Post Title: Re: The Witcher 2

Hello everyone, please someone help me with redoing the dds to bms file
example
dds texture revenue
bms file texture final
## Post #69
- Username: oveja
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Feb 24, 2011 4:35 am
- Post datetime: 2011-05-25T16:49:54+00:00
- Post Title: Re: The Witcher 2

Don't the decoding method *.w2strings?
I would like to translate this game.
## Post #70
- Username: guilhermetutilo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat May 21, 2011 8:05 pm
- Post datetime: 2011-05-25T17:24:33+00:00
- Post Title: Re: The Witcher 2

anyone have the unpack/pack for dzip ??? I want to translate this game to portuguese
## Post #71
- Username: rockmassif
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 22, 2011 4:23 am
- Post datetime: 2011-05-25T18:39:15+00:00
- Post Title: Re: The Witcher 2

I just unpacked the .dzip files.

I'm thinking about a "harder difficulty mod", and yet, I couldn't manage to find the necessary files. Any ideas where they might be?
## Post #72
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2011-05-25T18:47:14+00:00
- Post Title: Re: The Witcher 2

> Reply from guilhermetutilo
>
> anyone have the unpack/pack for dzip ??? I want to translate this game to portuguese

Relax dude, let the guys do their job. Tell me, where is 'your' god now?
Don't you ask him for a tool? Your god fails???
## Post #73
- Username: guilhermetutilo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat May 21, 2011 8:05 pm
- Post datetime: 2011-05-25T18:48:59+00:00
- Post Title: Re: The Witcher 2

> Reply from Herdell
>
> guilhermetutilo wrote:anyone have the unpack/pack for dzip ??? I want to translate this game to portuguese

Relax dude, let the guys do their job. Tell me, where is 'your' god now?
Don't you ask him for a tool? Your god fails???

HEHEHEHE yes i'm relax and waiting for de unpack, tanks
## Post #74
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2011-05-25T19:09:07+00:00
- Post Title: Re: The Witcher 2

> Reply from guilhermetutilo
>
> Herdell wrote:guilhermetutilo wrote:anyone have the unpack/pack for dzip ??? I want to translate this game to portuguese

Relax dude, let the guys do their job. Tell me, where is 'your' god now?
Don't you ask him for a tool? Your god fails???    

 

HEHEHEHE yes i'm relax and waiting for de unpack, tanks

you can unpack the dzip files already. there's instructions a few pages back.
## Post #75
- Username: sugarshock
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu May 26, 2011 3:44 am
- Post datetime: 2011-05-25T20:07:11+00:00
- Post Title: Re: The Witcher 2

The contents of this post was deleted because of possible forum rules violation.
## Post #76
- Username: Arxel
- Rank: n00b
- Number of posts: 18
- Joined date: Thu May 26, 2011 6:32 am
- Post datetime: 2011-05-25T22:35:03+00:00
- Post Title: Re: The Witcher 2

What about .w2speech files?
Where can we find some text files with quest description etc? .w2speech or .w2strings?
I do not want to translate, for something else..
## Post #77
- Username: guilhermetutilo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat May 21, 2011 8:05 pm
- Post datetime: 2011-05-26T01:06:02+00:00
- Post Title: Re: The Witcher 2

> Reply from odrin
>
> you can unpack the dzip files already. there's instructions a few pages back.

Thanks


WEEE i unpack the dzip file, anyone know where is the dialog file?
## Post #78
- Username: chalon
- Rank: n00b
- Number of posts: 16
- Joined date: Sun May 22, 2011 3:20 am
- Post datetime: 2011-05-26T09:19:10+00:00
- Post Title: Re: The Witcher 2

> Reply from Arxel
>
> What about .w2speech files?
Where can we find some text files with quest description etc? .w2speech or .w2strings?
I do not want to translate, for something else..

w2strings has the localized text strings w2speech has the localized conversation audio. I don't think either formats are accessible yet.
## Post #79
- Username: Arxel
- Rank: n00b
- Number of posts: 18
- Joined date: Thu May 26, 2011 6:32 am
- Post datetime: 2011-05-26T09:58:37+00:00
- Post Title: Re: The Witcher 2

So we wait for .2wstring then.. Hope someone will unzip it soon 
I had access to game lot earlier, but when I started to learn how to unzip files I was not able to handle .dzip.. Too hard for a newbe.. Lot to learn yet..
## Post #80
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2011-05-26T20:02:13+00:00
- Post Title: Re: The Witcher 2

hi rick, i checked your project logs and it says something about packers and unpackers. does this mean it's almost ready? if i wanted to test it out, what do i have to do?

i have the svn files, but there's just code.
## Post #81
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-05-26T20:22:31+00:00
- Post Title: Re: The Witcher 2

> Reply from odrin
>
> hi rick, i checked your project logs and it says something about packers and unpackers. does this mean it's almost ready? if i wanted to test it out, what do i have to do?

i have the svn files, but there's just code.
as i remember rick always giving only code
## Post #82
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-26T20:29:28+00:00
- Post Title: Re: The Witcher 2

its not hard to compile it but its not ready for mainstream use yet the file name he is testing is still hard coded.
## Post #83
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-05-26T20:44:15+00:00
- Post Title: Re: The Witcher 2

anyway for those who want to try i compiled Gibbed.RED.Unpack, i don't have this game, tool attached
[Gibbed.RED.Unpack.zip](https://xentaxbackup.github.io/file/4263_Gibbed.RED.Unpack.zip)
## Post #84
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2011-05-26T21:03:20+00:00
- Post Title: Re: The Witcher 2

thanks. i see two application files. but neither seem to do anything when i click on them.

do i need quickbms?
## Post #85
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-05-26T21:12:50+00:00
- Post Title: Re: The Witcher 2

> Reply from odrin
>
> thanks. i see two application files. but neither seem to do anything when i click on them.

do i need quickbms?
it's [command line](http://en.wikipedia.org/wiki/Command_Prompt) tool
## Post #86
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2011-05-26T21:25:54+00:00
- Post Title: Re: The Witcher 2

haha ok. i seem to be in over my head here. maybe i'll just wait for the public version.
## Post #87
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-05-26T22:50:57+00:00
- Post Title: Re: The Witcher 2

My tools are generally made so they can be invoked by dragging and dropping a file onto the exe -- in this case drag pack0.dzip onto Unpack and it will unpack it.
## Post #88
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2011-05-26T23:01:29+00:00
- Post Title: Re: The Witcher 2

oh i was dragging and dropping w2ent files in there. i also used the command line thing and it says -e can open ent files?
## Post #89
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-05-26T23:05:33+00:00
- Post Title: Re: The Witcher 2

Unpack is for dzip, not W2RC.
## Post #90
- Username: sugarshock
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu May 26, 2011 3:44 am
- Post datetime: 2011-05-26T23:45:13+00:00
- Post Title: Re: The Witcher 2

So is there anyone who would be willing to help me out with my problem(end of page five)?
I would be VERY grateful to anyone who can offer some insight.

Edit:

could someone upload their Quickbms folder for me, just in case there is something wrong with my files?
## Post #91
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2011-05-27T09:02:21+00:00
- Post Title: Re: The Witcher 2

Is there a way to view the .usm movies or extract/convert them to something viewable?
## Post #92
- Username: oveja
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Feb 24, 2011 4:35 am
- Post datetime: 2011-05-27T12:24:35+00:00
- Post Title: Re: The Witcher 2

> Reply from Modman69
>
> Is there a way to view the .usm movies or extract/convert them to something viewable?

nothing.
*.usm file is Scaleform Video file.
only *.avi convert *.usm.
don't convert *.usm to *.avi.
[video_encoder.jpg](https://xentaxbackup.github.io/file/4268_video_encoder.jpg)
## Post #93
- Username: Arxel
- Rank: n00b
- Number of posts: 18
- Joined date: Thu May 26, 2011 6:32 am
- Post datetime: 2011-05-27T22:32:01+00:00
- Post Title: Re: The Witcher 2

Just to be sure - in items/ we have some .xml files.. Do You guys have all items names in english or maybe in your foreign language? I'm not sure if all inside .xml names are in english and the translation is somewhere in .w2strings or maybe I did something wrong while installing game
## Post #94
- Username: inforsir
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 24, 2011 3:45 am
- Post datetime: 2011-05-27T23:25:00+00:00
- Post Title: Re: The Witcher 2

anyone know how to open .w2comm files because i want to a take a peek into the quest files.to change the quest exp/orens rewarded from the said quest
## Post #95
- Username: chalon
- Rank: n00b
- Number of posts: 16
- Joined date: Sun May 22, 2011 3:20 am
- Post datetime: 2011-05-27T23:26:20+00:00
- Post Title: Re: The Witcher 2

> Reply from Arxel
>
> Just to be sure - in items/ we have some .xml files.. Do You guys have all items names in english or maybe in your foreign language? I'm not sure if all inside .xml names are in english and the translation is somewhere in .w2strings or maybe I did something wrong while installing game

The item names in the xml files are basically in english, but they are not the item names displayed. It uses the name in the xml file as a key in the .w2strings file to get the actual localized name that it displays.

I'm trying to figure out the w2strings format. I've got it to read all the key strings in the first part of the file, which was pretty easy, but the second part of the file is compressed, encoded, or encrypted somehow.

The basics of the format I've figured out is the file starts out with a magic number first four bytes (c9 00 00 00).

Then there are 4 bytes, followed by 1 byte of the key string size, followed by the key string itself. This repeats until you get through all the key strings, except for one key in the middle that seems to be slightly malformed.

The most significant bit of the string size tells you whether the key string is UTF-8 or UTF-16. Set to 1 means UTF-8, set to 0 means UTF-16. Then the rest of the bits tell you the actual size of the string.

I haven't really figured out what the 4 bytes before the string size byte mean, though. If I load it up as a little endian int32, the two most significant bytes are almost always 0x7933, then the next two bytes vary quite a bit.

Anyway, just writing a real simple program that grabs the 4 bytes as an int32, reads the string, and outputs both, I get a lot of output like this:

```
0x79338317: temple
0x7933842e: temple cemetery
0x7933a633: tentadrake armor
0x79336b6c: tentadrake armor enhancement
0x79336ab5: tentadrake eyes
```
## Post #96
- Username: Arxel
- Rank: n00b
- Number of posts: 18
- Joined date: Thu May 26, 2011 6:32 am
- Post datetime: 2011-05-27T23:50:11+00:00
- Post Title: Re: The Witcher 2

Good work! I only want stuff names etc. 

oh, .w2comm would also be great..!
## Post #97
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2011-05-28T01:07:41+00:00
- Post Title: Re: The Witcher 2

but the downside is, those xml files will be referring to complete w2 files, not the individual names from inside.

am i wrong in assuming this?
## Post #98
- Username: chalon
- Rank: n00b
- Number of posts: 16
- Joined date: Sun May 22, 2011 3:20 am
- Post datetime: 2011-05-28T01:15:16+00:00
- Post Title: Re: The Witcher 2

The w2strings file, when decoded, is going to be a lot of key,value pairs that are essentially along the lines of:
Key=tentadrake armor,Value=Kayran Armor

The XML files refer to those Keys. So if you want the correct item names you just have to match the key with the actual values.

The localization process would probably involve just localizing all those values and then encoding the new w2strings file.

But the w2strings file has to be figured out first. Right now I have the "keys", but none of the "values."
## Post #99
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2011-05-28T01:35:52+00:00
- Post Title: Re: The Witcher 2

alright, thanks.
## Post #100
- Username: inforsir
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 24, 2011 3:45 am
- Post datetime: 2011-05-28T05:33:23+00:00
- Post Title: Re: The Witcher 2

anybody have any info on how to change the sell amount on a item? so u can sell it for a lot. or change how much orens is drop off a body?
## Post #101
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-05-28T07:56:51+00:00
- Post Title: Re: The Witcher 2

For w2strings:
[http://svn.gib.me/public/red/trunk/Gibb ... ngsFile.cs](http://svn.gib.me/public/red/trunk/Gibbed.RED.FileFormats/StringsFile.cs)
[http://svn.gib.me/public/red/trunk/Gibbed.RED.Strings/](http://svn.gib.me/public/red/trunk/Gibbed.RED.Strings/)
## Post #102
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2011-05-28T08:11:35+00:00
- Post Title: Re: The Witcher 2

hi, i compiled that with microsoft network 4. what does it do? i try inputting w2 files but it just shuts down.
## Post #103
- Username: chalon
- Rank: n00b
- Number of posts: 16
- Joined date: Sun May 22, 2011 3:20 am
- Post datetime: 2011-05-28T09:14:45+00:00
- Post Title: Re: The Witcher 2

> Reply from Rick
>
> For w2strings:
http://svn.gib.me/public/red/trunk/Gibb ... ngsFile.cs
http://svn.gib.me/public/red/trunk/Gibbed.RED.Strings/

Thanks a lot. I was basically getting nowhere trying to look at it in IDA, now I can get all this localization stuff in my item DB!
## Post #104
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2011-05-28T16:48:06+00:00
- Post Title: Re: The Witcher 2

oveja,

Thanks for the info.
## Post #105
- Username: Arxel
- Rank: n00b
- Number of posts: 18
- Joined date: Thu May 26, 2011 6:32 am
- Post datetime: 2011-05-28T17:01:54+00:00
- Post Title: Re: The Witcher 2

Quick question - Does anyone know where to look for a script that disable HUD?
When we save the game, images are without hud.. In preview version [H] key allow to switch on/off hud in-game..

I don't have any files from preview version so can't look for some files that references to controls..
## Post #106
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-05-28T17:04:14+00:00
- Post Title: Re: The Witcher 2

latest compiled version [here](http://dl.dropbox.com/u/9919707/blogs/xentax.com/the-witcher-2-pc/witcher2-gibbed-tools/witcher2-gibbed-tools-11-05-29.zip)
## Post #107
- Username: Arxel
- Rank: n00b
- Number of posts: 18
- Joined date: Thu May 26, 2011 6:32 am
- Post datetime: 2011-05-28T17:23:11+00:00
- Post Title: Re: The Witcher 2

Thank you! Works great, have all items names! Hell yeah!

In Opera I have problem with "invalid character reference" [http://www.w3.org/TR/REC-xml/#NT-CharRef](http://www.w3.org/TR/REC-xml/#NT-CharRef)
Think 'cos of polish language
## Post #108
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2011-05-28T19:37:31+00:00
- Post Title: Re: The Witcher 2

i'm ask Rick in PM, but he is not aviable ;)

to unpack a ru0.w2strings (Russian) must be added one line in the file \Gibbed.RED.FileFormats\StringsFile.cs:

```
        {
            switch (fileKey)
            {
                // ------------------------------- skipped
                case 0x63481486: return 0x42386347; //RU ver 1.1
                case 0x77932179: return 0x54932186; //RU ver 1.0-1.0.0.3
            }
            return 0;
        }
```
## Post #109
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-05-28T20:15:06+00:00
- Post Title: Re: The Witcher 2

Interesting since my Steam copy of the game doesn't have those values. Thanks.
## Post #110
- Username: Arxel
- Rank: n00b
- Number of posts: 18
- Joined date: Thu May 26, 2011 6:32 am
- Post datetime: 2011-05-28T20:19:38+00:00
- Post Title: Re: The Witcher 2

As far as I know, steam versions is a little different that retail versions
## Post #111
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2011-05-28T20:41:38+00:00
- Post Title: Re: The Witcher 2

just in the Steam are not the Russian version, but on 17 June she will appear.

p.s.
update message with a old keypair for initial russian version (before the path 1.1)
## Post #112
- Username: Arxel
- Rank: n00b
- Number of posts: 18
- Joined date: Thu May 26, 2011 6:32 am
- Post datetime: 2011-05-29T09:20:35+00:00
- Post Title: Re: The Witcher 2

Which exactly files does Gibbed.RED.ResourceEdit can unpack?
Anyone know where I can find locations of items? Some coordinates or something? I know that some of them we can find in shops, but I would like to make for example a maps with all herbs on them
## Post #113
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-05-29T11:09:12+00:00
- Post Title: Re: The Witcher 2

ResourceEdit is still very early in development and can't actually edit anything yet, and its support for resources is very minimal at this point.
## Post #114
- Username: Dimmell
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat May 28, 2011 12:25 am
- Post datetime: 2011-05-29T18:14:27+00:00
- Post Title: Re: The Witcher 2

> Reply from hhrhhr
>
> i'm ask Rick in PM, but he is not aviable 

to unpack a ru0.w2strings (Russian) must be added one line in the file \Gibbed.RED.FileFormats\StringsFile.cs:
Code: Select all        private static uint GetRealKey(uint fileKey)
        {
            switch (fileKey)
            {
                // ------------------------------- skipped
                case 0x63481486: return 0x42386347; //RU ver 1.1
                case 0x77932179: return 0x54932186; //RU ver 1.0-1.0.0.3
            }
            return 0;
        }

Is it possible to add these changes to witcher2-gibbed-tools?
## Post #115
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-05-29T19:17:04+00:00
- Post Title: Re: The Witcher 2

new version is [here](http://dl.dropbox.com/u/9919707/blogs/xentax.com/the-witcher-2-pc/witcher2-gibbed-tools/witcher2-gibbed-tools-11-05-30.zip), Gibbed.RED.ResourceEdit not included.
## Post #116
- Username: Dimmell
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat May 28, 2011 12:25 am
- Post datetime: 2011-05-29T21:24:04+00:00
- Post Title: Re: The Witcher 2

> Reply from Tosyk
>
> new version is here, Gibbed.RED.ResourceEdit not included.
Thank you! Excellent work - decodes ru0.w2strings and encodes without problems.  

 Thanks Rick!
## Post #117
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-05-29T21:27:28+00:00
- Post Title: Re: The Witcher 2

> Reply from Dimmell
>
> Tosyk wrote:new version is here, Gibbed.RED.ResourceEdit not included.
Thank you! Excellent work - decodes ru0.w2strings and encodes without problems.
all thanks to Rick, please
## Post #118
- Username: chalon
- Rank: n00b
- Number of posts: 16
- Joined date: Sun May 22, 2011 3:20 am
- Post datetime: 2011-05-30T10:11:18+00:00
- Post Title: Re: The Witcher 2

> Reply from Arxel
>
> Anyone know where I can find locations of items? Some coordinates or something? I know that some of them we can find in shops, but I would like to make for example a maps with all herbs on them

You won't be able to do something like this with the current available tools.

The locations of the herbs are most likely in all the herbs.w2l files that are in various directories under levels. But those files are binary data, so it will be a while before it's figured out.
## Post #119
- Username: dubh
- Rank: n00b
- Number of posts: 13
- Joined date: Mon May 23, 2011 4:34 pm
- Post datetime: 2011-06-01T03:54:44+00:00
- Post Title: Re: The Witcher 2

FYI: I'm maintaining the [project page for Rick's tools](http://www.witchernexus.com/downloads/file.php?id=52) at Witcher Nexus. There's a setup file for easy/familiar installation, and a readme on the project page that has basic usage instructions and answers to frequently asked questions. (ResourceEdit is currently not included per Rick's request.) Feel free to send anyone who needs only the binaries there. Oh, and if you're registered on Nexus, please endorse the file to show Rick some love.
## Post #120
- Username: JPulowski
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 29, 2010 5:39 am
- Post datetime: 2011-06-04T01:55:18+00:00
- Post Title: Re: The Witcher 2

For the .USM files, it seems the game using ui_video.swf in global folder for playing them. I don't know much about coding stuff, but I've found this actionscript inside the .swf file. Maybe it helps somebody, who knows?

```

// [Action in Frame 1]
stop ();

function PlayVideo(vName, vLoop)
{
    video.attachVideo(ns);
    ns.loop = vLoop;
    ns.setOpenTimeout(0);
    if (_global.gfxVersion != undefined)
    {
        vName = vName + ".usm";
    }
    else
    {
        vName = vName + ".flv";
    } // end else if
    ns.play(vName);
    subLine.subtitleTxt.text = "";
    SetStatusText("Play: " + vName + "\n");
    blackscreen.gotoAndPlay(2);
} // End of the function
function StopVideo()
{
    movieInfo = undefined;
    ns.close();
    flash.external.ExternalInterface.call("MovieStopped");
} // End of the function
function PauseVideo(vLoop)
{
    ns.pause(vLoop);
} // End of the function
function GetSubtitleLanguage()
{
    return (subtitleLanguage);
} // End of the function
function GetAudioLanguage()
{
    return (audioLanguage);
} // End of the function
function SetAudioLanguage(vLang)
{
    audioLanguage = vLang;
    setupLanguage();
} // End of the function
function SetSubtitleLanguage(vLang)
{
    subtitleLanguage = vLang;
    setupLanguage();
} // End of the function
function GetDuration()
{
    if (movieInfo == undefined)
    {
        return (0);
    } // end if
    return (movieInfo.duration);
} // End of the function
function GetMovieInfo()
{
    return (movieInfo);
} // End of the function
function setupLanguage()
{
    if (movieInfo == undefined || movieInfo.audioTracks == undefined)
    {
        return;
    }
    else
    {
        ns.audioTrack = 0;
        ns.subAudioTrack = audioLanguage;
        ns.subtitleTrack = subtitleLanguage;
    } // end else if
} // End of the function
function ShowStatus(enable)
{
    if (enable)
    {
        statusTxt._visible = true;
        statusTxt.text = "";
        statusTxt.scroll = statusTxt.maxscroll;
    }
    else
    {
        statusTxt._visible = false;
    } // end else if
} // End of the function
function onKeyDown()
{
    if (Key.getCode() == 3)
    {
        StopVideo();
    } // end if
} // End of the function
_global.gfxExtensions = 1;
Stage.scaleMode = "Scale";
ShowStatus(false);
var nc = new NetConnection();
nc.connect(null);
var ns = new NetStream(nc);
var movieInfo;
var audioLanguage = 0;
var subtitleLanguage = 0;
Key.addListener(this);
SetStatusText = function (msg)
{
    if (statusTxt._visible)
    {
        statusTxt.text = statusTxt.text + (msg + "\n");
        statusTxt.scroll = statusTxt.maxscroll;
    } // end if
};
ns.onMetaData = function (infoObject)
{
    movieInfo = infoObject;
    for (var _loc1 in movieInfo)
    {
        SetStatusText(_loc1 + ":" + movieInfo[_loc1]);
    } // end of for...in
    if (movieInfo.audioTracks != undefined)
    {
        SetStatusText("Audio tracks:" + movieInfo.audioTracks.length);
    }
    else
    {
        SetStatusText("No audio tracks!");
    } // end else if
    if (movieInfo.audioTracks != undefined)
    {
        SetStatusText("Subtitles tracks:" + movieInfo.subtitleTracksNumber);
    }
    else
    {
        SetStatusText("No subtitles tracks!");
    } // end else if
    setupLanguage();
};
ns.onCuePoint = function (infoObject)
{
    flash.external.ExternalInterface.call("CuePoint", infoObject.name);
};
ns.onSubtitle = function (line)
{
    subLine.subtitleTxt.text = line;
    gotoAndPlay("playSubtitle");
};
ns.onStatus = function (infoObject)
{
    SetStatusText("STATUS: " + infoObject.code);
    switch (infoObject.code)
    {
        case "NetStream.Play.Start":
        {
            flash.external.ExternalInterface.call("MovieStarted");
            break;
        } 
        case "NetStream.Play.Stop":
        {
            flash.external.ExternalInterface.call("MovieStopped");
            break;
        } 
    } // End of switch
    gotoAndPlay(playSubtitle);
};
if (_global.gfxVersion == undefined)
{
    PlayVideo("movie", false);
    gotoAndPlay("playSubtitle");
    ShowStatus(true);
} // end if

// [Action in Frame 2]
trace ("go");

// [Action in Frame 134]
trace ("stop");
stop ();

```
## Post #121
- Username: chalon
- Rank: n00b
- Number of posts: 16
- Joined date: Sun May 22, 2011 3:20 am
- Post datetime: 2011-06-04T21:11:40+00:00
- Post Title: Re: The Witcher 2

> Reply from JPulowski
>
> For the .USM files, it seems the game using ui_video.swf in global folder for playing them. I don't know much about coding stuff, but I've found this actionscript inside the .swf file. Maybe it helps somebody, who knows?

The action script just tells the Scaleform middleware that the game uses to play back the video. Right now, the only way you're going to be able to play back the USM files is if you have Scaleform installed on your machine.
## Post #122
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2011-06-05T07:14:29+00:00
- Post Title: Re: The Witcher 2

I'm almost positive that Scaleform GFX comes bundled with UDK

I don't have the UDK downloaded and installed ATM, but I was wondering if this will allow playback of the .usm video

Anyone Know?
## Post #123
- Username: chalon
- Rank: n00b
- Number of posts: 16
- Joined date: Sun May 22, 2011 3:20 am
- Post datetime: 2011-06-05T10:31:48+00:00
- Post Title: Re: The Witcher 2

> This is the full version of the Scaleform GFx SDK, but does not include Scaleform Video, is not included in the UE3/UDK bundle

From here: [http://forums.epicgames.com/showthread.php?t=724791](http://forums.epicgames.com/showthread.php?t=724791)

The usm files require Scaleform Video, I'm pretty sure.
## Post #124
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2011-06-05T15:18:06+00:00
- Post Title: Re: The Witcher 2

In the Latest Build UDK-2011-05 under C:\UDK\UDK-2011-05\Binaries\GFx  (FxMediaPlayer.exe)
is a Scaleform gFX player however after opening it says audio/video disabled.

Bummer
## Post #125
- Username: JPulowski
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 29, 2010 5:39 am
- Post datetime: 2011-06-05T19:21:20+00:00
- Post Title: Re: The Witcher 2

Hmm... What's the difference between .usm and .bik? I think .usm file is very similar to a .mkv file. But the .usm file is encrypted. Someone said it has CRID encryption. Like I said I do not know much about coding stuff. Why a .usm file cannot be unpacked properly? What does CRID mean in layman's terms? Just curiosity.
## Post #126
- Username: chalon
- Rank: n00b
- Number of posts: 16
- Joined date: Sun May 22, 2011 3:20 am
- Post datetime: 2011-06-05T20:57:01+00:00
- Post Title: Re: The Witcher 2

Scaleform video uses CRI, which is just another middleware company. They have their own video format that's a competitor to Bink. [http://en.wikipedia.org/wiki/CRI_Middleware](http://en.wikipedia.org/wiki/CRI_Middleware)
## Post #127
- Username: Ckpaa
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 07, 2011 5:47 am
- Post datetime: 2011-06-06T22:03:14+00:00
- Post Title: Re: The Witcher 2

Anyone can answer on my question:
Where TW2 store items icon? In which files?
I need it for wikia.
I only find textures of items but no icons for inventory.
## Post #128
- Username: chalon
- Rank: n00b
- Number of posts: 16
- Joined date: Sun May 22, 2011 3:20 am
- Post datetime: 2011-06-06T22:39:19+00:00
- Post Title: Re: The Witcher 2

> Reply from Ckpaa
>
> Anyone can answer on my question:
Where TW2 store items icon? In which files?
I need it for wikia.
I only find textures of items but no icons for inventory.

They're in globals/gui/icons/items. They're all dds files, you can batch convert them and maintain alpha using Compressonator.
## Post #129
- Username: JPulowski
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 29, 2010 5:39 am
- Post datetime: 2011-06-07T19:02:18+00:00
- Post Title: Re: The Witcher 2

Well, tried to demuxing the content of .usm file with VGMToolbox but only got corrupted .m2v file, not surprised. 
[00128.jpg](https://xentaxbackup.github.io/file/4303_00128.jpg)
## Post #130
- Username: Arxel
- Rank: n00b
- Number of posts: 18
- Joined date: Thu May 26, 2011 6:32 am
- Post datetime: 2011-06-08T12:39:51+00:00
- Post Title: Re: The Witcher 2

OK, so there is no way right now to play .usm videos?
## Post #131
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2011-06-08T13:53:48+00:00
- Post Title: Re: The Witcher 2

> Reply from Arxel
>
> OK, so there is no way right now to play .usm videos?
create file \CookedPC\globals\video_start.csv (right choose your distributive)

```
cdpr;cdpr;cdpr;cdpr;cdpr;cdpr;cdpr;cdpr;cdpr;cdpr;cdrp;cdpr
;;;;;dream_01_letho;;;;;;
;;;;;dream_01_letho;;;;;;
;;;;;dream_02_baltimore;;;;;;
;;;;;dream_03_peasant;;;;;;
;;;;;dream_04_dragon;;;;;;
;;;;;dream_05_iorweth;;;;;;
.......
```


and use any screen capture program where all videos will be played after the game start :)
## Post #132
- Username: JPulowski
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 29, 2010 5:39 am
- Post datetime: 2011-06-08T14:00:01+00:00
- Post Title: Re: The Witcher 2

> Reply from hhrhhr
>
> Arxel wrote:OK, so there is no way right now to play .usm videos?
create file \CookedPC\globals\video_start.csv (right choose your distributive)
Code: Select allEFIGS;GOG;ATARI;ROW;PL;RU;CZ;HU;JA;TW;DD;ATARI_DD
cdpr;cdpr;cdpr;cdpr;cdpr;cdpr;cdpr;cdpr;cdpr;cdpr;cdrp;cdpr
;;;;;dream_01_letho;;;;;;
;;;;;dream_01_letho;;;;;;
;;;;;dream_02_baltimore;;;;;;
;;;;;dream_03_peasant;;;;;;
;;;;;dream_04_dragon;;;;;;
;;;;;dream_05_iorweth;;;;;;
.......

and use any screen capture program where all videos will be played after the game startYeah, already know that. But voice files must be added later. You will only hear 1st channel. Which is generally background music, sfx etc. No subtitles, no voice.
## Post #133
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2011-07-17T06:44:46+00:00
- Post Title: Re: The Witcher 2

any updates?
## Post #134
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2011-08-05T06:42:15+00:00
- Post Title: Re: The Witcher 2


## Post #135
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2011-10-08T06:11:42+00:00
- Post Title: Re: The Witcher 2

my theory: they hired him to work on mod tools and he has signed a nda
## Post #136
- Username: ner0
- Rank: advanced
- Number of posts: 50
- Joined date: Sun Aug 28, 2011 11:47 pm
- Post datetime: 2011-11-06T23:23:25+00:00
- Post Title: Re: The Witcher 2

> Reply from JPulowski
>
> Well, tried to demuxing the content of .usm file with VGMToolbox but only got corrupted .m2v file, not surprised.
Same for me.
...
## Post #137
- Username: bugmenotty
- Rank: Banned
- Number of posts: 10
- Joined date: Wed Mar 16, 2011 6:26 pm
- Post datetime: 2012-01-21T13:48:38+00:00
- Post Title: Re: The Witcher 2

Those files aren't corrupted. Use a proper player with a proper codec. Potplayer plays these files without a hitch.
## Post #138
- Username: ner0
- Rank: advanced
- Number of posts: 50
- Joined date: Sun Aug 28, 2011 11:47 pm
- Post datetime: 2012-01-21T16:43:34+00:00
- Post Title: Re: The Witcher 2

> Reply from bugmenotty
>
> Those files aren't corrupted. Use a proper player with a proper codec. Potplayer plays these files without a hitch.
You're absolutely right. I just tried it with Potplayer and it works flawlessly. Does Potplayer have any specific codecs for those files, I mean if I want to convert them which codecs will decode correctly? Thanks.
## Post #139
- Username: bugmenotty
- Rank: Banned
- Number of posts: 10
- Joined date: Wed Mar 16, 2011 6:26 pm
- Post datetime: 2012-01-21T19:35:09+00:00
- Post Title: Re: The Witcher 2

Well, those that I'm meddling with (Deus ex 3 ones) were created with TMPEnc, so your best bet would be to use this encoder. Last time I checked it supported loading a plethora of formats. Since the files in question use merely the MPEg1-format, chances are that you won't need any other decoders. That's just an educated guess though. In a worse case scenario you could try to load Potplayer's decoder in an avisynth script and frameserve the file to the encoder of your choice.
## Post #140
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2012-02-21T10:05:44+00:00
- Post Title: Re: The Witcher 2

[https://github.com/yole/Gibbed.RED](https://github.com/yole/Gibbed.RED)

someone has further worked on the tools, but i forgot how to compile the csproj. could someone do it for me or remind me?

thanks
## Post #141
- Username: Aiser
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Feb 25, 2012 1:06 am
- Post datetime: 2012-04-06T17:17:08+00:00
- Post Title: Re: The Witcher 2

en0.w2strings Xbox 360 The Witcher 2
http://dl.dropbox.com/u/64750833/Xbox36 ... .w2strings

```

Unhandled Exception: System.FormatException: hash for strings does not match
   at Gibbed.RED.FileFormats.StringsFile.Deserialize(Stream input)
   at Gibbed.RED.Strings.Program.Main(String[] args)
```

Gibbed's RED Tools r21. Not working.
## Post #142
- Username: aslanale
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Mar 13, 2012 3:08 am
- Post datetime: 2012-04-07T15:06:02+00:00
- Post Title: Re: The Witcher 2

Yes,it doesn't work.I hope someone will make new tools.
## Post #143
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2012-04-09T02:14:57+00:00
- Post Title: Re: The Witcher 2

that's probably because it's the xbox version. how did you get it 9 days before it's out btw?
## Post #144
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2012-04-17T01:24:02+00:00
- Post Title: Re: The Witcher 2

pc version just got ee update, rick are you gonna start working on this game again? i notice you have w2resource reader, but it doesn't work with most of the crucial files.
## Post #145
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-04-17T05:37:25+00:00
- Post Title: Re: The Witcher 2

Currently have no interest in doing further work on Witcher 2.
## Post #146
- Username: aslanale
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Mar 13, 2012 3:08 am
- Post datetime: 2012-04-17T19:30:09+00:00
- Post Title: Re: The Witcher 2

PC The Witcher 2 :EE en0.w2strings:

*distributing files is no longer acceptable as of the new rules*
## Post #147
- Username: aslanale
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Mar 13, 2012 3:08 am
- Post datetime: 2012-04-18T11:52:56+00:00
- Post Title: Re: The Witcher 2

Red Tools doesn't work with tr0.w2strings.

Tool gives this error:



Why it gives this error?
## Post #148
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-04-18T15:37:01+00:00
- Post Title: Re: The Witcher 2

What is tr0.w2strings from? I don't have that file.
## Post #149
- Username: aslanale
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Mar 13, 2012 3:08 am
- Post datetime: 2012-04-18T16:32:36+00:00
- Post Title: Re: The Witcher 2

> Reply from Rick
>
> What is tr0.w2strings from? I don't have that file.

It is from Enhanced Edition,Gibbed tool decode every string file(English-Hungary-Czech-Russian-Japanese) except Turkish string file.I pm file to you.
## Post #150
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-04-18T17:06:28+00:00
- Post Title: Re: The Witcher 2

Guess it's not included in the Steam EE.
## Post #151
- Username: aslanale
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Mar 13, 2012 3:08 am
- Post datetime: 2012-04-18T18:11:06+00:00
- Post Title: Re: The Witcher 2

No,

it is official and Steam EE has this file.
## Post #152
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-04-18T19:19:36+00:00
- Post Title: Re: The Witcher 2

You're right, looks like my install wasn't updating properly, validated game files and now it's redownloading.
## Post #153
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-04-19T04:46:16+00:00
- Post Title: Re: The Witcher 2

> red: rick * r25 /trunk/ (3 files in 2 dirs): 
>
> red: - Support non-Unicode strings in StringsFile.
>
> red: - Minor changes to StringsFile so it doesn't blow up if strings hash isn't correct.
>
> red: - Corrected StringsFile serialization when encryption key is zero (ie, no encryption).
>
> red: - New option for Strings, --force, which will force decode if strings hash isn't correct.
## Post #154
- Username: aslanale
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Mar 13, 2012 3:08 am
- Post datetime: 2012-04-19T08:48:13+00:00
- Post Title: Re: The Witcher 2

Where can i download or update tool's new version?
## Post #155
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-04-20T16:15:03+00:00
- Post Title: Re: The Witcher 2

i i'm not sure is there something new [here](http://dl.dropbox.com/u/9919707/cg.forexperts.ru/forum/tools/special/svn/TheWitcher2GibbedTools/the-witcher-2-gibbed-tools-12-04-21.7z)
compilled tools
## Post #156
- Username: aslanale
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Mar 13, 2012 3:08 am
- Post datetime: 2012-04-20T16:57:09+00:00
- Post Title: Re: The Witcher 2

> Reply from Tosyk
>
> i i'm not sure is there something new here
compilled tools

Thanks but there is no Strings.
## Post #157
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-04-20T17:50:43+00:00
- Post Title: Re: The Witcher 2

> Reply from aslanale
>
> Thanks but there is no Strings.try to download again
## Post #158
- Username: aslanale
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Mar 13, 2012 3:08 am
- Post datetime: 2012-04-20T18:18:38+00:00
- Post Title: Re: The Witcher 2

Thanks again Tosyk.

@Rick

New version doesn't work with  tr0.w2strings too.

It gives this error:



And will be xbox string support?
## Post #159
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-04-21T03:58:53+00:00
- Post Title: Re: The Witcher 2

> Reply from aslanale
>
> Thanks again Tosyk.

@Rick

New version doesn't work with  tr0.w2strings too.

It gives this error:



And will be xbox string support?You could try reading the help of the Strings tool, it clearly specifies how to get around that error.

As for xbox support, I have no idea. It doesn't directly support big-endian if the strings files are stored that way on Xbox 360.
## Post #160
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-04-21T05:32:43+00:00
- Post Title: Re: The Witcher 2

> Reply from Rick
>
> aslanale wrote:Thanks again Tosyk.

@Rick

New version doesn't work with  tr0.w2strings too.

It gives this error:



And will be xbox string support?You could try reading the help of the Strings tool, it clearly specifies how to get around that error.

As for xbox support, I have no idea. It doesn't directly support big-endian if the strings files are stored that way on Xbox 360.

Hi Rick,

Yes files are only different on the endianness level
## Post #161
- Username: aslanale
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Mar 13, 2012 3:08 am
- Post datetime: 2012-04-21T09:13:42+00:00
- Post Title: Re: The Witcher 2

@Rick


I tried "force" decode but it didn't work.Every time help screen comes.
## Post #162
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2012-05-18T01:33:49+00:00
- Post Title: Re: The Witcher 2

why do you want to decode strings? they're not useful at all.
## Post #163
- Username: leoaires
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Aug 06, 2012 9:06 am
- Post datetime: 2012-09-19T15:50:14+00:00
- Post Title: Re: The Witcher 2

Does not work on the Xbox version ..
But the PC version works perfect ..

I need to extract this "en0.w2strings" to translate this game into Portuguese language.
Anyone know a solution to extract the. xml file from the xbox version ?
## Post #164
- Username: leoaires
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Aug 06, 2012 9:06 am
- Post datetime: 2012-11-27T12:13:26+00:00
- Post Title: Re: The Witcher 2

up
Anyone know extract this file "en0.w2strings" on xbox?
## Post #165
- Username: soulslayerzx
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Aug 14, 2012 9:46 am
- Post datetime: 2012-12-22T21:02:54+00:00
- Post Title: Re: The Witcher 2

So does this work still?
## Post #166
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2012-12-24T22:09:10+00:00
- Post Title: Re: The Witcher 2

> Reply from soulslayerzx
>
> So does this work still?

Perfectly fine.
## Post #167
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-01-02T17:56:54+00:00
- Post Title: Re: The Witcher 2

and it's possible to extract w2speech ?
nova find 36 files mp2 only and look bug in 2 big psd file
## Post #168
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-01-14T22:46:26+00:00
- Post Title: Re: The Witcher 2

i have system expection on unpack
[wisp1.jpg](https://xentaxbackup.github.io/file/6131_wisp1.jpg)
## Post #169
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-01-14T22:49:18+00:00
- Post Title: Re: The Witcher 2

ok this me this tool works for dzip file

some tool for ? .w2speech
## Post #170
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-01-15T18:58:10+00:00
- Post Title: Re: The Witcher 2

VGMtool basic riff say warning: For string found at: 0x1081F38D, total file end will go past the end of the file (56C83CDF)
  Extracted [fr0_00000000.wav] begining at 0x1081F38D, for string found at: 0x1081F38D, with size 0x4646495A
## Post #171
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-01-15T19:13:47+00:00
- Post Title: Re: The Witcher 2

i finish my extracted on readable wav but this 17h sound file with scratch between all dialogue 
some one know one good tool for auto cutting ? please or better way for config vgmtool for exporte
## Post #172
- Username: tomatofarmer
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu May 17, 2012 7:54 pm
- Post datetime: 2013-01-25T10:54:27+00:00
- Post Title: Re: The Witcher 2

> Reply from kilik
>
> i finish my extracted on readable wav but this 17h sound file with scratch between all dialogue 
some one know one good tool for auto cutting ? please or better way for config vgmtool for exporte

Audacity, perhaps?:
[http://audacity.sourceforge.net/](http://audacity.sourceforge.net/)

But yeah, that has to be a better way to do that than slicing it manually.
