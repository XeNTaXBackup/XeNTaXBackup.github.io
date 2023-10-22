## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-03-24T21:12:05+00:00
- Post Title: Ridge Racer Unbounded Compressed files.

Seems the new ridge racer game uses an ultra compression technique that when you remove the 360 padding the actual game size is 1gb. They must of used some sort of compression scheme because i cannot even recognize anything in the bigfiles.

sample
* snip *
## Post #2
- Username: marlborox
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Apr 09, 2011 10:03 am
- Post datetime: 2012-03-28T18:51:20+00:00
- Post Title: Ridge Racer Unbounded Compressed files.

could be zlib compression as offzip ([http://aluigi.altervista.org/mytoolz/offzip.zip](http://aluigi.altervista.org/mytoolz/offzip.zip)) seemed to find something
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-03-28T21:20:45+00:00
- Post Title: Ridge Racer Unbounded Compressed files.

Doiesn't look like zlib.

I gues we will have to wait for the pc/ps3 version to find out if its the same compression. Man why does namco do that?
## Post #4
- Username: RVR72GV
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 08, 2011 5:16 pm
- Post datetime: 2012-03-30T09:14:36+00:00
- Post Title: Ridge Racer Unbounded Compressed files.

Could be zlib compression since the track editor crashes with zlib error (incorrect header check) in the PC version.
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-03-30T17:29:00+00:00
- Post Title: Ridge Racer Unbounded Compressed files.

PC Version is using Zlib. Is the window bits value different?
## Post #6
- Username: Gruselgurke
- Rank: advanced
- Number of posts: 72
- Joined date: Sat Mar 31, 2012 1:15 am
- Post datetime: 2012-03-30T17:36:06+00:00
- Post Title: Ridge Racer Unbounded Compressed files.

I tried to open it using zlib but had no success. Could you extract it C00L12345?
## Post #7
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-03-30T18:50:35+00:00
- Post Title: Ridge Racer Unbounded Compressed files.

Algo 006CEE40

```

arg_0		= dword	ptr  8
arg_4		= dword	ptr  0Ch
anonymous_0	= dword	ptr  10h

		push	ebp
		mov	ebp, esp
		mov	ecx, [ebp+arg_0]
		push	esi
		mov	esi, [ebp+anonymous_0]
		dec	esi
		xor	eax, eax
		push	edi
		test	esi, esi
		jle	short sz_End
		push	ebx

sz_Loop:
		mov	edx, [ecx+eax*4+4]
		mov	edi, edx
		mov	ebx, edx
		shr	edi, 5
		shl	ebx, 4
		xor	edi, ebx
		mov	ebx, [ebp+arg_4]
		add	edi, edx
		mov	edx, eax
		xor	edx, 0FFFFFFFEh
		and	edx, 3
		mov	edx, [ebx+edx*4]
		sub	edx, 61C88647h
		xor	edi, edx
		sub	[ecx+eax*4], edi
		inc	eax
		cmp	eax, esi
		jl	short sz_Loop
		pop	ebx

sz_End:
		mov	eax, [ecx]
		mov	edx, eax
		mov	edi, eax
		shr	edx, 5
		shl	edi, 4
		xor	edx, edi
		mov	edi, [ebp+arg_4]
		add	edx, eax
		mov	eax, esi
		xor	eax, 0FFFFFFFEh
		and	eax, 3
		mov	eax, [edi+eax*4]
		sub	eax, 61C88647h
		xor	edx, eax
		sub	[ecx+esi*4], edx
		pop	edi
		pop	esi
		pop	ebp
		retn
sub_6CEE40	endp
```


PseudoCode

```
{
  int v3; // esi@1
  int i; // eax@1
  int result; // eax@3

  v3 = a3 - 1;
  for ( i = 0; i < v3; ++i )
    *(_DWORD *)(a1 + 4 * i) -= (*(_DWORD *)(a2 + 4 * (((unsigned __int8)i ^ 0xFE) & 3)) - 1640531527) ^ (*(_DWORD *)(a1 + 4 * i + 4) + (16 * *(_DWORD *)(a1 + 4 * i + 4) ^ (*(_DWORD *)(a1 + 4 * i + 4) >> 5)));
  result = *(_DWORD *)(a2 + 4 * (((unsigned __int8)v3 ^ 0xFE) & 3)) - 1640531527;
  *(_DWORD *)(a1 + 4 * v3) -= result ^ (*(_DWORD *)a1 + (16 * *(_DWORD *)a1 ^ (*(_DWORD *)a1 >> 5)));
  return result;
}
```


Example on 01___unbounded___ archive

[Loaded Header](http://img12.imageshack.us/img12/996/rru1j.png)

[after 006CEE40 Header](http://img62.imageshack.us/img62/6314/rru2.png)

BFS1 - seems archives used in FlatOut 2 ? 

Anyway binaries and example archives [here](http://www.mediafire.com/?l4ey6fola60iucn)
## Post #8
- Username: Gruselgurke
- Rank: advanced
- Number of posts: 72
- Joined date: Sat Mar 31, 2012 1:15 am
- Post datetime: 2012-03-30T19:14:08+00:00
- Post Title: Ridge Racer Unbounded Compressed files.

Yes that should be the archive type from Flatout: [viewtopic.php?p=9533#p9533](http://forum.xentax.com/viewtopic.php?p=9533#p9533)

So were you able to unpack it? Sorry for that noobish question, I really have a very limited knowledge about this stuff  
I wouldn't know what to do with the stuff you posted :s
## Post #9
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-03-30T19:14:19+00:00
- Post Title: Ridge Racer Unbounded Compressed files.

I hope someone cracks this!
## Post #10
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-03-31T23:43:04+00:00
- Post Title: Ridge Racer Unbounded Compressed files.

How can we use that code?
## Post #11
- Username: 360AMC
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Apr 20, 2011 10:26 am
- Post datetime: 2012-03-31T23:51:48+00:00
- Post Title: Ridge Racer Unbounded Compressed files.

Gonna be great when the PC files get cracked. Want to make it so every street has traffic.
## Post #12
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2012-04-01T20:12:22+00:00
- Post Title: Ridge Racer Unbounded Compressed files.

Well i was able to build a 1/2 module for Unpakke for that game.

So far i can successfully unpack "00__ridge_racer__" (full of XML's) and "02____update_____" (where the localization files are). The last "01___unbounded___" archive has something strange in the structure that i didn't figure yet but... stay tuned i guess...?   

The "BFS1" format is key encrypted (custom encryption as much as i am familiar with cryptography...).
The structure is key encrypted also, with algo similar to the file one, but this time it's executed in 6 rounds.
The file names and file path of every entry is obfuscated a little and... hash table encrypted. 

Finally, the file entries are simply ZIP-ed.

Those guys really don't want no one to pick with the game res...

Here's the file structure of "02____update_____" (just to prove my words):

```
    ГДДДart
    і   АДДДbase
    і       ГДДДarea
    і       і   ГДДДboroughs
    і       і   і   ГДДДarea
    і       і   і   і   ГДДДhighway
    і       і   і   і   і   АДДДblock
    і       і   і   і   і           collateral1.dpdc
    і       і   і   і   і           driving1.dpdc
    і       і   і   і   і           driving3.dpdc
    і       і   і   і   і           driving4.dpdc
    і       і   і   і   і           driving5.dpdc
    і       і   і   і   і           driving6.dpdc
    і       і   і   і   і           driving7.dpdc
    і       і   і   і   і           driving8.dpdc
    і       і   і   і   і           transition2.dpdc
    і       і   і   і   і           transition3.dpdc
    і       і   і   і   і           transition4.dpdc
    і       і   і   і   і           transition4b.dpdc
    і       і   і   і   і           transition5.dpdc
    і       і   і   і   і           
    і       і   і   і   ГДДДport
    і       і   і   і   і   АДДДblock
    і       і   і   і   і           driving1b.dpdc
    і       і   і   і   і           driving1c.dpdc
    і       і   і   і   і           empty3.dpdc
    і       і   і   і   і           target1.dpdc
    і       і   і   і   і           target2.dpdc
    і       і   і   і   і           target3.dpdc
    і       і   і   і   і           target4.dpdc
    і       і   і   і   і           tmp_car_driving7.dpdc
    і       і   і   і   і           
    і       і   і   і   АДДДwarehouses
    і       і   і   і       АДДДblock
    і       і   і   і               collateral1.dpdc
    і       і   і   і               collateral2.dpdc
    і       і   і   і               driving1b.dpdc
    і       і   і   і               shortcut1.dpdc
    і       і   і   і               shortcut2.dpdc
    і       і   і   і               shortcut3.dpdc
    і       і   і   і               shortcut4.dpdc
    і       і   і   і               shortcut5.dpdc
    і       і   і   і               shortcut6.dpdc
    і       і   і   і               
    і       і   і   АДДДblock
    і       і   і           advanced_objects_block.dpdc
    і       і   і           collateral1.dpdc
    і       і   і           collateral2.dpdc
    і       і   і           empty2.dpdc
    і       і   і           offgrid2.dpdc
    і       і   і           offgrid3.dpdc
    і       і   і           shortcut4.dpdc
    і       і   і           shortcut6.dpdc
    і       і   і           shortcut7.dpdc
    і       і   і           shortcut8.dpdc
    і       і   і           
    і       і   АДДДdowntown
    і       і       ГДДДarea
    і       і       і   ГДДДcommercial
    і       і       і   і   АДДДblock
    і       і       і   і           driving1.dpdc
    і       і       і   і           driving1b.dpdc
    і       і       і   і           driving2.dpdc
    і       і       і   і           driving3.dpdc
    і       і       і   і           driving3b.dpdc
    і       і       і   і           driving3c.dpdc
    і       і       і   і           driving4.dpdc
    і       і       і   і           driving5.dpdc
    і       і       і   і           driving6.dpdc
    і       і       і   і           shortcut1.dpdc
    і       і       і   і           shortcut2.dpdc
    і       і       і   і           shortcut3.dpdc
    і       і       і   і           shortcut4.dpdc
    і       і       і   і           shortcut5.dpdc
    і       і       і   і           
    і       і       і   ГДДДconstruction
    і       і       і   і   АДДДblock
    і       і       і   і           driving1.dpdc
    і       і       і   і           driving1b.dpdc
    і       і       і   і           driving2.dpdc
    і       і       і   і           driving3.dpdc
    і       і       і   і           driving4.dpdc
    і       і       і   і           
    і       і       і   АДДДunderground
    і       і       і       АДДДblock
    і       і       і               driving1.dpdc
    і       і       і               driving1b.dpdc
    і       і       і               driving2.dpdc
    і       і       і               driving2b.dpdc
    і       і       і               driving3.dpdc
    і       і       і               driving4.dpdc
    і       і       і               
    і       і       АДДДblock
    і       і               collateral1b.dpdc
    і       і               driving1.dpdc
    і       і               driving10.dpdc
    і       і               driving11.dpdc
    і       і               driving11b.dpdc
    і       і               driving1b.dpdc
    і       і               driving2.dpdc
    і       і               driving3.dpdc
    і       і               driving4.dpdc
    і       і               driving5.dpdc
    і       і               driving6.dpdc
    і       і               driving7.dpdc
    і       і               driving8.dpdc
    і       і               driving9.dpdc
    і       і               empty1.dpdc
    і       і               offgrid1b.dpdc
    і       і               offgrid1c.dpdc
    і       і               offgrid3.dpdc
    і       і               shortcut1.dpdc
    і       і               shortcut2.dpdc
    і       і               shortcut3.dpdc
    і       і               shortcut4.dpdc
    і       і               shortcut5.dpdc
    і       і               shortcut6.dpdc
    і       і               tmp_car_driving11b.dpdc
    і       і               tmp_car_shortcut2.dpdc
    і       і               
    і       АДДДblock
    і               filler_boroughs1.dpdc
    і               filler_boroughs2.dpdc
    і               filler_downtown1.dpdc
    і               filler_downtown2.dpdc
    і               filler_downtown3.dpdc
    і               filler_port1.dpdc
    і               filler_warehouses1.dpdc
    і               
    ГДДДeditor
    і   АДДДshatterbay
    і       АДДДdistrict13
    і               d13_level2.bin
    і               
    ГДДДgameflow
    і       gameflow.bsm
    і       
    ГДДДlocalization
    і       language0.dat
    і       language100.dat
    і       language3.dat
    і       language5.dat
    і       language8.dat
    і       
    АДДДmenu
        ГДДДhud_as3
        і       hud_base_i16.dds
        і       hud_base_i3.dds
        і       
        ГДДДingame
        і       advancedmodeoptions_i1.dds
        і       ingameoptions_i1.dds
        і       pause_i1.dds
        і       
        ГДДДoverlay
        і       menuoverlay_i29.dds
        і       menuoverlay_i2e.dds
        і       menuoverlay_i5f.dds
        і       profileoverlay_i1.dds
        і       profileoverlay_i13.dds
        і       
        АДДДtextures
            АДДДmain
                АДДДlegal
                        disclaimer0_pc.bmap
                        disclaimer2_pc.bmap
                        disclaimer4_pc.bmap
                        disclaimer7_pc.bmap
```

(Sorry for the "АДДД" crap, but that how Windows tree.exe dump the table  )
## Post #13
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-04-01T20:27:15+00:00
- Post Title: Ridge Racer Unbounded Compressed files.

Interesting!

hope to see more progress!
## Post #14
- Username: Gruselgurke
- Rank: advanced
- Number of posts: 72
- Joined date: Sat Mar 31, 2012 1:15 am
- Post datetime: 2012-04-02T00:08:45+00:00
- Post Title: Ridge Racer Unbounded Compressed files.

Awesome 
Well I looked into the .exe with Ollydgb and it seems like the game includes a hell lot of source code (according to the filenames). Maybe thats why they don't want that file to openend so easily.
## Post #15
- Username: 360AMC
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Apr 20, 2011 10:26 am
- Post datetime: 2012-04-02T01:29:56+00:00
- Post Title: Ridge Racer Unbounded Compressed files.

Something tells me this game runs on the same engine as Flatout 2 and Flatout Ultimate Carnage. Most likely a tweaked version of UC's engine.
## Post #16
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2012-04-02T09:20:27+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

I've released a module for Unpakke supporting the format. However, it's a beta version, which means you can only "unpack" the resources.
I'll try to add the "pack" procedure soon (or never...).

The module is available for download from [http://nullsecurity.org/unpakke](http://nullsecurity.org/unpakke)

Have fun!
## Post #17
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-02T10:51:36+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

Good job
## Post #18
- Username: matt55
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Apr 19, 2010 8:13 pm
- Post datetime: 2012-04-02T11:56:58+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

This game was created with Bugbear help so that's why it looks simillar to FO. Anyway, I think that BFS unpacker will be good source to work with. I guess that there aren't any big changes in code.
## Post #19
- Username: 360AMC
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Apr 20, 2011 10:26 am
- Post datetime: 2012-04-02T13:57:03+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

> Reply from matt55
>
> This game was created with Bugbear help so that's why it looks simillar to FO. Anyway, I think that BFS unpacker will be good source to work with. I guess that there aren't any big changes in code.
I am completely aware of that, and I totally agree about the BFS unpacker.
## Post #20
- Username: Gruselgurke
- Rank: advanced
- Number of posts: 72
- Joined date: Sat Mar 31, 2012 1:15 am
- Post datetime: 2012-04-02T14:02:01+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

Awesome XpoZed!
The game works just fine without the archives. So the need for a packer is not thaat high 
Being able to unpack it is awesome.
## Post #21
- Username: matt55
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Apr 19, 2010 8:13 pm
- Post datetime: 2012-04-02T14:10:14+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

Too bad that Flatout Joint is down or maybe it is alive(??) Well I remember the discussion about modding that game.
For me Ridge racer looks similar to Burnout but with mods it will be even more better
## Post #22
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2012-04-02T16:17:04+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

> Reply from Gruselgurke
>
> Awesome XpoZed!
The game works just fine without the archives. So the need for a packer is not thaat high 
Being able to unpack it is awesome.
Well if the game runs well unpacked i think i will leave the module as is. There is a 0x1F28 bytes long hash table that is used to group the files in some weird way that i don't think will be able to reverse engineer. Also, I'm lazy so... (  )
## Post #23
- Username: Gruselgurke
- Rank: advanced
- Number of posts: 72
- Joined date: Sat Mar 31, 2012 1:15 am
- Post datetime: 2012-04-02T17:07:15+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

Haha, fair enough! 

Note for other users. You have to unpack all of the three archives in order to make it work. First the main archive and then the others and overwrite every file that is already existing from the main archive, those files got patched with the 02__update__ archive.
## Post #24
- Username: 360AMC
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Apr 20, 2011 10:26 am
- Post datetime: 2012-04-05T00:09:25+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

Is there a way to extract the archives without using CMD?
## Post #25
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2012-04-05T09:04:27+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

> Reply from 360AMC
>
> Is there a way to extract the archives without using CMD?
Why what's the problem with CMD? Did you read the Unpakke's user manual from nullsecurity.org?
## Post #26
- Username: 360AMC
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Apr 20, 2011 10:26 am
- Post datetime: 2012-04-07T02:53:34+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

See attached file. That's why. Just because I forgot .exe at the end of unpakke at the start and misidentified how many _ are in the filename and didn't understand the shitty directions, I gotta type all that shit again? Bullshit!
[FUCK.JPG](https://xentaxbackup.github.io/file/5273_FUCK.JPG)
## Post #27
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2012-04-07T07:54:41+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

> Reply from 360AMC
>
> See attached file. That's why. Just because I forgot .exe at the end of unpakke at the start and misidentified how many _ are in the filename and didn't understand the shitty directions, I gotta type all that shit again? Bullshit!
As much as i can see, Unpakke is working nice. However, it will be nice if you spend some time in learning the basics in using the Windows console, instead of calling my tool "bullshit".

1. When your input or output directory path contains [spaces] (like in "My documents"), you should put the whole path in double quotes.
2. If you are lazy to type 20 chars, use TAB to complete the directory names. I think thats a little effort from your side, compared to the 500+ lines of assembler code i write for this module.

So once again, the problem is not in Unpakke. The problem is in the device in front of your keyboard.
## Post #28
- Username: 360AMC
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Apr 20, 2011 10:26 am
- Post datetime: 2012-04-08T00:27:52+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

Everything done correctly. Nothing. Yep-this is bullshit, and i'm sorry, but that path is far beyond 20 chars. And there's no manual in sight. And if I have to read a frigging MANUAL just to extract a couple lousy files, something is wrong.
[No. Just. No..JPG](https://xentaxbackup.github.io/file/5276_No. Just. No..JPG)
## Post #29
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-08T01:02:55+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

Make BAT file and insert next text:

```
unpakke upkk_bfs1_beta.dll unpack "C:\Program Files\Steam\steamapps\common\ridge racer unbounded\01___unbounded___" "C:\Program Files\Steam\steamapps\common\ridge racer unbounded\01_unbounded"
```
## Post #30
- Username: terminator
- Rank: advanced
- Number of posts: 53
- Joined date: Mon Mar 29, 2010 3:16 pm
- Post datetime: 2012-04-08T08:34:12+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

Could you make a packer algorythm? It would be help so much in localization.
## Post #31
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-04-08T09:40:51+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

> Reply from 360AMC
>
> Everything done correctly. Nothing. Yep-this is bullshit, and i'm sorry, but that path is far beyond 20 chars. And there's no manual in sight. And if I have to read a frigging MANUAL just to extract a couple lousy files, something is wrong.

You are on the brink of being banned. Violation of rule 12: [viewtopic.php?f=28&t=1270](http://forum.xentax.com/viewtopic.php?f=28&t=1270)
## Post #32
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2012-04-08T10:01:48+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

> Reply from terminator
>
> Could you make a packer algorythm? It would be help so much in localization.
It's in my TODO list.
## Post #33
- Username: burnabycomputer
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 09, 2012 12:20 am
- Post datetime: 2012-04-08T20:23:19+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

Thanks a lot for your tool as Im decompressing now... can I rip car models out of this game? 
Earlier I tried DX ripper (OBJ. too) but it only saves the wheels and 3DVIA Printscreen crashes the game on startup.... but Ive yet to try that gameassassin ripper.
## Post #34
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2012-04-08T21:11:04+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

> Reply from burnabycomputer
>
> Thanks a lot for your tool as Im decompressing now... can I rip car models out of this game? 
Earlier I tried DX ripper (OBJ. too) but it only saves the wheels and 3DVIA Printscreen crashes the game on startup.... but Ive yet to try that gameassassin ripper.
No idea here. Maybe you should ask in the "3D/2D models" subforums.
## Post #35
- Username: Purple44
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 09, 2012 10:29 am
- Post datetime: 2012-04-09T02:45:22+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

> Reply from matt55
>
> Too bad that Flatout Joint is down or maybe it is alive(??) Well I remember the discussion about modding that game.
For me Ridge racer looks similar to Burnout but with mods it will be even more better

We are still kicking at [Flatout Joint](http://flatoutjoint.com), at least for the time being. Came close to closing doors back in 2010.

I had high hopes for RRU, especially the advance track editor. But RRU being a console port, no wheel support, no remapping, no text chat online, online having major issues, I'm afraid RRU may have a short life like Blur. 

Been a disappointing year so far. Flatout 3 release as a beta and publisher Strategy First screwing over Team6 and the Flatout community. Bugbear releasing Ridge Racer Unbounded as a console port and Dirt Showdown only having 8 players online, when you really need 10-12 players to have a good, rip roaring derby figure 8 race, like we use to have with GRID.

Good luck modding RRU and maybe some the modders from FOJ may stop by. But right now, most of us at FOJ have taken a pass on RRU for now.
## Post #36
- Username: terminator
- Rank: advanced
- Number of posts: 53
- Joined date: Mon Mar 29, 2010 3:16 pm
- Post datetime: 2012-04-16T16:03:28+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

> Reply from XpoZed
>
> terminator wrote:Could you make a packer algorythm? It would be help so much in localization.
It's in my TODO list.

Is there any progress in packer coding, or surrended it?
## Post #37
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2012-04-16T18:29:58+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

> Reply from terminator
>
> XpoZed wrote:terminator wrote:Could you make a packer algorythm? It would be help so much in localization.
It's in my TODO list. 

Is there any progress in packer coding, or surrended it?
Sorry, I'm quite busy lately and don't have much free time for Unpakke.
## Post #38
- Username: RVR72GV
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 08, 2011 5:16 pm
- Post datetime: 2012-04-17T04:42:00+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

Fun fact: Running the game uncompressed seems to make the track editor able to load your tracks again.

...or is it just me.

And pretty much every scripts are in .xml format, which means it should be modifiable (the cars should be moddable as well, but the car body mesh is in .vhcl format, and the texture is in .bmap).
## Post #39
- Username: terminator
- Rank: advanced
- Number of posts: 53
- Joined date: Mon Mar 29, 2010 3:16 pm
- Post datetime: 2012-04-17T08:25:20+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

"Sorry, I'm quite busy lately and don't have much free time for Unpakke."

I'm feeling sad to read that - I was hope you could make some handy script to packer algorythm to help us in localization.
Ridge Racer Unbound doesnt read any localized string from unpakked sources ...   
I hope someone gonna help us.

Best wishes!
## Post #40
- Username: GulBroz
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 02, 2012 8:06 pm
- Post datetime: 2012-05-02T12:22:19+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

Hi all

@XpoZed: congratulations for your work on unpacking RRU, that's really great stuff.

As you said you do not have time to work on the packer part, maybe you can PM me your findings on RRU (especially the cypher part), and I'll upgrade BFSpack tool (I already enhanced it for FlatOut2 since Karok released the 1st version, and added support for FlaOut:UltimateCarnage).

I'm not asking this just to have the code, I'll do something of it (of course I could disassemble RRU binary and redo what you've done, but I do not have enough free time for this - and I'm not very comfortable with x86 assembler too , so it will take me a lot of time).

More over, I think that cypher algo is maybe the key to something we all dream of at flatoutjoint.com: the way to fully decode FlatOut2 files and be able to have a fully working track editor, with the ability to create tracks from scratch. (but that is secondary/bonus objective, the 1st one is to add support for RRU in BFSpack).

Hope you'll hear me.

GulBroz.
## Post #41
- Username: terminator
- Rank: advanced
- Number of posts: 53
- Joined date: Mon Mar 29, 2010 3:16 pm
- Post datetime: 2012-05-03T07:59:32+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

> (but that is secondary/bonus objective, the 1st one is to add support for RRU in BFSpack).

It would be soooo great thing!
## Post #42
- Username: 360AMC
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Apr 20, 2011 10:26 am
- Post datetime: 2012-05-04T23:23:10+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

> Reply from RVR72GV
>
> Fun fact: Running the game uncompressed seems to make the track editor able to load your tracks again.

...or is it just me.

And pretty much every scripts are in .xml format, which means it should be modifiable (the cars should be moddable as well, but the car body mesh is in .vhcl format, and the texture is in .bmap).
I tried to make traffic spawn on city streets, but sadly, no luck.(created all the correct folders and .xmls, added.xmls to database.cfg or w/e it's called, got nothing.)
I did only change how fast the traffic would go, otherwise the data is the same as the .xml for the highway traffic...probably something else that needs to be changed.
## Post #43
- Username: headrushmayor
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Nov 29, 2010 12:03 pm
- Post datetime: 2012-05-08T10:53:25+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

> Reply from 360AMC
>
> RVR72GV wrote:Fun fact: Running the game uncompressed seems to make the track editor able to load your tracks again.

...or is it just me.

And pretty much every scripts are in .xml format, which means it should be modifiable (the cars should be moddable as well, but the car body mesh is in .vhcl format, and the texture is in .bmap).
I tried to make traffic spawn on city streets, but sadly, no luck.(created all the correct folders and .xmls, added.xmls to database.cfg or w/e it's called, got nothing.)
I did only change how fast the traffic would go, otherwise the data is the same as the .xml for the highway traffic...probably something else that needs to be changed.

Hi i don't if this will help you with the traffic but i look in sum files after i unpack it come with file 00__ridge_racer__data_database_data_career in there a file called 
database this got everthing do with the game, look down about half way u find it called <Property name="TrafficDensityScale"  i set it too <Value>2.000000</Value>.
I have change laps from 5 to 15 <Property name="Laps" type="PROPERTY_INT">
			<Value>5</Value>
get more fun out of the game and trying set AI bit harder. i played around with sound so far and find the names of all the songs as well.
Here list of song in game.
<Property name="PlayList" type="PROPERTY_POOLSTRING" array="true">
			<Value>Yu Miyake - Tsui Tsui (RR5)</Value>
			<Value>Hiroshi Okubo - Explorers (RR6)</Value>
			<Value>Rio Hamamoto - Road Mauler (RR6)</Value>
			<Value>Rio Hamamoto - Beat Assassinator (RR7)</Value>
			<Value>Akitaka Tohyama - Freak Out (RR7)</Value>
			<Value>Hiroshi  Okubo - Orbital Rock (RR7)</Value>
			<Value>AJURIKA - Drifting Spiders</Value>
			<Value>sampling masters MEGA - Mushrooms</Value>
			<Value>sampling masters MEGA -  Wrong way</Value>
			<Value>sampling masters AYA - 1 Halen</Value>
			<Value>sampling masters AYA - Lederhosen Samurai</Value>
			<Value>sanodg - Down & Under</Value>
			<Value>Rio Hamamoto - The Finger</Value>
			<Value>Hiroshi Okubo - Take a ride</Value>
			<Value>Overseer - Crash & Burn</Value>
			<Value>The Crystal Method - Double Down Under</Value>
			<Value>Skrillex - Kill Everybody </Value>
			<Value>Noisia & The Upbeats - Blindfold</Value>
			<Value>Ever Never - Persecution</Value>
			<Value>RuN RiOT -  Survive The Drop</Value>
			<Value>Skrillex - Scary Monsters And Nice Sprites</Value>
			<Value>Scratch Perverts - Stand By (Krafty Kuts Remix)</Value>
## Post #44
- Username: 360AMC
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Apr 20, 2011 10:26 am
- Post datetime: 2012-05-16T19:40:13+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

Whoa whoa whoa...did traffic spawn on streets when you did that?
## Post #45
- Username: headrushmayor
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Nov 29, 2010 12:03 pm
- Post datetime: 2012-06-25T07:33:53+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

> Reply from 360AMC
>
> Whoa whoa whoa...did traffic spawn on streets when you did that?
i got lot more cars from that only set to 2.000000 try set to higher number and see what happens, i have not played much with it as i am doing dirt showdown, i doing sound file for game and other 
effect as well, i have look again tonight do video if works out ok give link to it.
## Post #46
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2016-01-28T08:52:32+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

> Reply from Ekey
>
> Make BAT file and insert next text:
Code: Select allunpakke upkk_bfs1_beta.dll unpack "C:\Program Files\Steam\steamapps\common\ridge racer unbounded\01___unbounded___" "C:\Program Files\Steam\steamapps\common\ridge racer unbounded\01_unbounded"

I am getting this error:

> Cannot load module: upkk_bfs1_beta.dll
unpakke 1.0 (1005)
modules\upkk_bfs1_beta.dll is 4608 bytes
Any clues?

Thank you!
## Post #47
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2016-01-28T18:55:41+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

> Reply from Csimbi
>
> Ekey wrote:Make BAT file and insert next text:
Code: Select allunpakke upkk_bfs1_beta.dll unpack "C:\Program Files\Steam\steamapps\common\ridge racer unbounded\01___unbounded___" "C:\Program Files\Steam\steamapps\common\ridge racer unbounded\01_unbounded"

I am getting this error:
Cannot load module: upkk_bfs1_beta.dll
unpakke 1.0 (1005)
modules\upkk_bfs1_beta.dll is 4608 bytes
Any clues?

Thank you!
First, you'll need the old Unpakke version (0.4b). The new version of Unpakke (1.0) doesnt support the old modules.
Then, you just need to move the upkk_bfs1_beta.dll in your Unpakke folder and execute the line you already got.

Good luck.
## Post #48
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2016-01-29T08:02:52+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

> Reply from XpoZed
>
> First, you'll need the old Unpakke version (0.4b). The new version of Unpakke (1.0) doesnt support the old modules.
Then, you just need to move the upkk_bfs1_beta.dll in your Unpakke folder and execute the line you already got.

Good luck.

I thought the newest version would support it.
Worked like a charm, thanks!
## Post #49
- Username: Cmdbest
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 01, 2023 8:37 am
- Post datetime: 2023-01-01T00:55:12+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

Hey there, I have a tiny issue with this unpacker.

Whenever I try to use it (I am using Unpakke 0.4b and I have the "zlib.dll" library and the "upkk_bfs1_beta" module with the .bat file with both the input and output directories, all in the same folder where Unpakke is located) I get an error, and then cmd closes. Is there something I can do to prevent this from happening? I tried running your tool in both Windows 7 and 10 (both 64-bits). In windows 10, cmd just closes right away and doesnt even let me see what the issue was.

PD: I had to copy your tool into a flash drive and then copy it into my old laptop, which runs windows 7.

This is the error in Windows 7:

> Bad archive header.
## Post #50
- Username: BH founder
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 25, 2023 4:29 am
- Post datetime: 2023-05-24T20:34:41+00:00
- Post Title: Re: Ridge Racer Unbounded Compressed files.

I have the same issue, when i run the exe it instantly closes just when cmd is about to open, how to fix this?
