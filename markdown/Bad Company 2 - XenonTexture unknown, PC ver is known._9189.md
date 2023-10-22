## Post #1
- Username: norm
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jan 12, 2010 3:54 am
- Post datetime: 2012-07-01T21:36:10+00:00
- Post Title: Bad Company 2 - XenonTexture unknown, PC ver is known.

p01.itexture ([http://www.mediafire.com/?3upgk1kuje19ei1](http://www.mediafire.com/?3upgk1kuje19ei1)) (PC)
p01.xenontexture ([http://www.mediafire.com/?1a9sdm64m5mct3t](http://www.mediafire.com/?1a9sdm64m5mct3t)) (Xbox 360)

If you write a DXT5 header over the custom header on p01.itexture you get a readable .dds file. ([http://www.mediafire.com/?ouxhie5sajzdzmf](http://www.mediafire.com/?ouxhie5sajzdzmf))

Any ideas what compression p01.xenontexture is using?

Some extra info. 

[](http://imgur.com/y0Lo8)
[compare.rar](https://xentaxbackup.github.io/file/5528_compare.rar)
## Post #2
- Username: norm
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jan 12, 2010 3:54 am
- Post datetime: 2012-07-01T22:18:22+00:00
- Post Title: Bad Company 2 - XenonTexture unknown, PC ver is known.

Xenos (name for Xbox 360 GPU) supports uncompressed, DXT1/DXT3/DXT5 (and maybe also DXT2/4 but not sure). But there's also these:

 • DXT3A - "4 bit scalar replicated into four channels in shader"

 • DXT3A as 1111 - "1 bit per channel pixel"

 • DXT5A "3bit selection between 2 8bit endpoints"

 • DXN "3Dc normal compression" and "2-channel version of DXT5A"

 • CTX1 "bit selection between 2 8.8bit endpoints"
## Post #3
- Username: norm
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-07-02T00:12:59+00:00
- Post Title: Bad Company 2 - XenonTexture unknown, PC ver is known.

They look like big endian DDS files but i used a script to swap the endian and it's just distorted. Anyway this should add your .DDS header.

```
# Xbox 360 Only
# MrNightmareTM

get NAME basename
getdstring NAME2 0x10
goto 0x50
get UNK1 long
reverselong UNK1
get UNK2 long
reverselong UNK2
set MEMORY_FILE2 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
putVarChr MEMORY_FILE2 0xC UNK1 long
putVarChr MEMORY_FILE2 0x10 UNK2 long
append
get SIZE asize MEMORY_FILE2
log MEMORY_FILE 0 SIZE MEMORY_FILE2
get SIZE asize     
math SIZE -= 0x9C             
log MEMORY_FILE 0x9C SIZE             
append
get SIZE asize MEMORY_FILE
string NAME += ".dds"
log NAME 0 SIZE MEMORY_FILE

```


They look like big endian dds files as i previously said

Before:



After Conversion:



Original PC file:



You can see they look very similar but still distorted but it's progress, the file looks like it needs unswizzling.

Anyway here is that other script made ages ago:

```
# May not have full support
# MrNightmareTM
# Special thanks, Chrrox for the method!
# v0.1a

get SIZE asize
log MEMORY_FILE 0 SIZE

get SIZE2 asize
math SIZE2 -= 0x80
math SIZE2 /= 4
goto 0x80

for i = 0 < SIZE2


savepos CURRENTOFFSET
get UNK1 short
reverseshort UNK1
putVarChr MEMORY_FILE CURRENTOFFSET UNK1 short

savepos CURRENTOFFSET
get UNK1 short
reverseshort UNK1
putVarChr MEMORY_FILE CURRENTOFFSET UNK1 short

next i 

get NAME basename
string NAME += "_reversed.dds"

log NAME 0 SIZE MEMORY_FILE


```


Seems weird how the file is all swizzled, is it swizzled or is it something else?
## Post #4
- Username: norm
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jan 12, 2010 3:54 am
- Post datetime: 2012-07-02T00:35:43+00:00
- Post Title: Bad Company 2 - XenonTexture unknown, PC ver is known.

I'm 100% sure P01.Itexture + P01.XenonTexture are identical. They come from the exact same place in the file tree.

I've attached another pair of textures to compare. Thanks.
[compare2.rar](https://xentaxbackup.github.io/file/5529_compare2.rar)
## Post #5
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-07-02T09:54:11+00:00
- Post Title: Bad Company 2 - XenonTexture unknown, PC ver is known.

> Reply from norm
>
> I'm 100% sure P01.Itexture + P01.XenonTexture are identical. They come from the exact same place in the file tree.

I've attached another pair of textures to compare. Thanks.

Actually they're not the exact same they are swizzled around which is why they cannot be read with a standard .dds header + conversion. Why do you need Xbox textures anyway?
## Post #6
- Username: norm
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jan 12, 2010 3:54 am
- Post datetime: 2012-07-02T11:59:37+00:00
- Post Title: Bad Company 2 - XenonTexture unknown, PC ver is known.

I wanted to get at the Xenon BC1 textures, which I figure use the same compression technique as BC2.

BC1 wasn't released on PC btw.

PS. When I said the files are identical, I meant in terms of what the game displays, it's the same image.
[bc1_example.rar](https://xentaxbackup.github.io/file/5531_bc1_example.rar)
## Post #7
- Username: norm
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jan 12, 2010 3:54 am
- Post datetime: 2012-07-02T12:42:33+00:00
- Post Title: Bad Company 2 - XenonTexture unknown, PC ver is known.

I think the BC1 textures may have different compression, because when processed to .dds & reversed they look very blocky.

As for unswizzling, I googled about and found this talking about Dead Rising 2.

> The textures are encoded or swizzled with a predicted tiling algorithm to increase the efficiency of the 360's GPU speed. to solve just run the textures through the 360 sdk to untile... then they can be repacked using any BIG packer 

[http://deadrising2mods.proboards.com/in ... age=1#7816](http://deadrising2mods.proboards.com/index.cgi?action=display&board=dr2otctools&thread=1035&page=1#7816)
## Post #8
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-07-02T14:47:11+00:00
- Post Title: Bad Company 2 - XenonTexture unknown, PC ver is known.

> Reply from norm
>
> I think the BC1 textures may have different compression, because when processed to .dds & reversed they look very blocky.

As for unswizzling, I googled about and found this talking about Dead Rising 2.
The textures are encoded or swizzled with a predicted tiling algorithm to increase the efficiency of the 360's GPU speed. to solve just run the textures through the 360 sdk to untile... then they can be repacked using any BIG packer 

http://deadrising2mods.proboards.com/in ... age=1#7816
That's for dead rising though i tried noesis untile yesterday and nothing showed it was no different, the closest i ever got was using the endian swap script unless it's a custom swizzle algo.
## Post #9
- Username: norm
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jan 12, 2010 3:54 am
- Post datetime: 2012-07-02T16:37:07+00:00
- Post Title: Bad Company 2 - XenonTexture unknown, PC ver is known.

Ok so I managed to unswizzle the Xenon Textures from the BC2 release using the 360 SDK tools.

I used Bundler.exe to create an XPR file (you need to specify an RDF with it).

```
<RDF Version="XPR2">
<Texture
   Name   = "i20"
   Source = "i20.png"
   Format = "D3DFMT_DXT5"
   Width  = "512"
   Height = "512"
   Levels = "1"
/>
</RDF>

```


I then took the header from the resulting .xpr file and applied it to p01.xenontexture (saved it as p01.xpr).

Ran p01.xpr through Unbundler.exe and it outputs the texture as .tga (unswizzled).

I just need to figure out what compression BC1 textures are using now because they don't work with the same method.
[xpr_dxt5_header.rar](https://xentaxbackup.github.io/file/5532_xpr_dxt5_header.rar)
## Post #10
- Username: norm
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jan 12, 2010 3:54 am
- Post datetime: 2012-07-03T20:39:39+00:00
- Post Title: Bad Company 2 - XenonTexture unknown, PC ver is known.

Ok so after making various files using bundler.exe and reading about the texture formarts in the 360 XDK help file.

The BC1 textures I attached above are 256x256 using D3DFMT_A8R8G8B8. 

Strangely though, they included larger versions in another place which are 512x512 which use DXT5. Both are swizzled (tiled) so need to be decompressed with Unbundler.exe
[xpr_header_256_A8R8G8B8.rar](https://xentaxbackup.github.io/file/5537_xpr_header_256_A8R8G8B8.rar)
## Post #11
- Username: KENNITHH
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Dec 27, 2013 2:50 am
- Post datetime: 2014-11-23T00:40:03+00:00
- Post Title: Bad Company 2 - XenonTexture unknown, PC ver is known.

have you guys been able to get it?
## Post #12
- Username: mirh
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-11-23T07:45:44+00:00
- Post Title: Bad Company 2 - XenonTexture unknown, PC ver is known.

it is very easy format this is from X360 :
## Post #13
- Username: KENNITHH
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Dec 27, 2013 2:50 am
- Post datetime: 2014-11-23T11:56:38+00:00
- Post Title: Bad Company 2 - XenonTexture unknown, PC ver is known.

Awesome, if anyone of you would like to have more "test subjects", here are 5 more xenontextures:

Includes diffuse/normal/?colormap?

[http://www.mediafire.com/download/hppdg ... 1-x360.zip](http://www.mediafire.com/download/hppdgu375j98t89/bfbc1-x360.zip)
## Post #14
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-11-23T14:12:14+00:00
- Post Title: Bad Company 2 - XenonTexture unknown, PC ver is known.

well easy enought
## Post #15
- Username: KENNITHH
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Dec 27, 2013 2:50 am
- Post datetime: 2014-11-23T16:03:04+00:00
- Post Title: Bad Company 2 - XenonTexture unknown, PC ver is known.

Awesome that it all works, thanks again michalss. But I didn't expect it to look like that, I hoped the _D. one would actually be colored, but well I guess I'll just have to wait some days to know it all for sure
## Post #16
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-11-23T16:52:30+00:00
- Post Title: Re: Bad Company 2 - XenonTexture unknown, PC ver is known.

> Reply from KENNITHH
>
> Awesome that it all works, thanks again michalss. But I didn't expect it to look like that, I hoped the _D. one would actually be colored, but well I guess I'll just have to wait some days to know it all for sure

This is what is it in files, _D is always colored!
## Post #17
- Username: KENNITHH
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Dec 27, 2013 2:50 am
- Post datetime: 2014-11-23T16:54:35+00:00
- Post Title: Re: Bad Company 2 - XenonTexture unknown, PC ver is known.

> Reply from michalss
>
> 
This is what is it in files, _D is always colored!

But the HK416 (_D) you're showing there is black&white?
## Post #18
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-11-23T18:49:02+00:00
- Post Title: Re: Bad Company 2 - XenonTexture unknown, PC ver is known.

> Reply from KENNITHH
>
> michalss wrote:
This is what is it in files, _D is always colored!

But the HK416 (_D) you're showing there is black&white?

It look like gun and it is collored.
## Post #19
- Username: KENNITHH
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Dec 27, 2013 2:50 am
- Post datetime: 2014-11-24T16:43:31+00:00
- Post Title: Re: Bad Company 2 - XenonTexture unknown, PC ver is known.

> Reply from michalss
>
> KENNITHH wrote:michalss wrote:
This is what is it in files, _D is always colored!

But the HK416 (_D) you're showing there is black&white?

It look like gun and it is collored.

I mean look, i sent you 

UL_rif_HK416_C(olormap?)
UL_rif_HK416_D(iffuse?)
UL_rif_HK416_N(ormal)

This one: [http://puu.sh/d3KBK/9749fa75be.jpg](http://puu.sh/d3KBK/9749fa75be.jpg) is it Diffuse? cause it looks black & white, thats what I mean
## Post #20
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-12-05T18:36:04+00:00
- Post Title: Re: Bad Company 2 - XenonTexture unknown, PC ver is known.

here is Noesis python script to open all xenontexture samples in this thread  


 tex_BattlefieldBadCompany_X360_xenontexture.zip
(946 Bytes) Downloaded 47 times



supports dxt1, dxt5 and argb32
i think this thread has a mix of BC1 and BC2 samples, not sure which is which so the script should open both.
## Post #21
- Username: Heico
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 01, 2020 6:04 pm
- Post datetime: 2020-06-17T20:38:44+00:00
- Post Title: Re: Bad Company 2 - XenonTexture unknown, PC ver is known.

> Reply from Acewell ↑Wed Dec 06, 2017 2:36 am at Wed Dec 06, 2017 2:36 am
>
> 
here is Noesis python script to open all xenontexture samples in this thread  
tex_BattlefieldBadCompany_X360_xenontexture.zip

supports dxt1, dxt5 and argb32
i think this thread has a mix of BC1 and BC2 samples, not sure which is which so the script should open both.

Hi Acewell, I'm actively modding and researching about the Frostbite 1 engine for over a year now.
I would like to ask you for permission to share an edited version of your Python plugin for Noesis on GitHub Gist.
This way it would be much more easy for me to maintain and share the script with my community. 
I will make sure to give proper credits to you, of course!

If you have any questions or if you need more info about me, feel free to contact me via PM.

I would be glad about a response from you. 

Greetings, Heico!
## Post #22
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-06-18T05:01:35+00:00
- Post Title: Re: Bad Company 2 - XenonTexture unknown, PC ver is known.

no permission is needed, do what you like, i don't own any of this stuff.
## Post #23
- Username: Heico
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 01, 2020 6:04 pm
- Post datetime: 2020-06-18T18:34:31+00:00
- Post Title: Re: Bad Company 2 - XenonTexture unknown, PC ver is known.

> Reply from Acewell ↑Thu Jun 18, 2020 1:01 pm at Thu Jun 18, 2020 1:01 pm
>
> 
no permission is needed, do what you like, i don't own any of this stuff.

Ok, good to know, thanks a lot! 

Edit: Oh and in case anyone is interested in the updated version: [https://gist.github.com/HeicoDev/cb5210 ... 83edd279d6](https://gist.github.com/HeicoDev/cb521072ffacef94b7bed883edd279d6)
For now I only added support for ATI1 textures, but I plan to extend the script as soon as I find out more.
