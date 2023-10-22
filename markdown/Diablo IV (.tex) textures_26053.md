## Post #1
- Username: IstiGI
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Nov 16, 2015 11:10 pm
- Post datetime: 2022-12-02T19:56:47+00:00
- Post Title: Diablo IV (.tex) textures

Hi guys!

So I was lucky to be invited in D4 closed beta and managed to unpack some texture files from the game. Years ago there was .tex to .dds converter for Diablo 3, but it doesn't work with D4 obviously. 

Any help?   
[https://drive.google.com/file/d/1Ddei7P ... share_link](https://drive.google.com/file/d/1Ddei7Pof6qH3hZbmi7GqLISDG7r5l89Q/view?usp=share_link)
[https://drive.google.com/file/d/1s5NL7A ... share_link](https://drive.google.com/file/d/1s5NL7AJXGYfAzYL6wa8xu60HqJdxh9H7/view?usp=share_link)
[https://drive.google.com/file/d/1dyAgLn ... share_link](https://drive.google.com/file/d/1dyAgLnQJzuVjhcwXkisbFRtTB_KHE0pt/view?usp=share_link)
## Post #2
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2022-12-04T01:52:22+00:00
- Post Title: Diablo IV (.tex) textures

Diablo 4 is new to me.  Can we see some model data?

Are all texture files this large? 28MB?  It seems unusually large for a single texture.
## Post #3
- Username: IstiGI
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Nov 16, 2015 11:10 pm
- Post datetime: 2022-12-04T08:35:32+00:00
- Post Title: Diablo IV (.tex) textures

Not all of them this large. I thought it would be more convenient to add the largest ones as an example 

And those are 2D interface textures

EDIT. Did some research and it seems that there are separate texture files and meta data for it
[https://drive.google.com/file/d/1cw7E5q ... share_link](https://drive.google.com/file/d/1cw7E5qiy4aIVC-q3Hw_rJy32su1v6DR2/view?usp=share_link) - meta data
[https://drive.google.com/file/d/1vMIC_V ... share_link](https://drive.google.com/file/d/1vMIC_Voz6Nv7wEUBzSZCNnuozcaiVT_U/view?usp=share_link) - texture
## Post #4
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2022-12-05T00:35:01+00:00
- Post Title: Diablo IV (.tex) textures

> Reply from IstiGI ↑Sun Dec 04, 2022 4:35 pm at Sun Dec 04, 2022 4:35 pm
>
> 
Not all of them this large. I thought it would be more convenient to add the largest ones as an example

Not really, the smallest files are best. The less data to look at, the better.  And not just one file, we need several, for comparisons.
## Post #5
- Username: IstiGI
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Nov 16, 2015 11:10 pm
- Post datetime: 2022-12-06T12:15:05+00:00
- Post Title: Diablo IV (.tex) textures

Ok. Here are few more examples with smaller size
[https://drive.google.com/file/d/1K9sPs1 ... share_link](https://drive.google.com/file/d/1K9sPs1hbbBKTS9jsvi6AxcPmjvQFsMjl/view?usp=share_link)
## Post #6
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2023-01-06T13:58:57+00:00
- Post Title: Diablo IV (.tex) textures

Payload texture:
Looks like pure texture data, most likely in some compressed format.

Meta data:
0x18 (DWORD), possibly texture format.
0x28 (DWORDs), width, height of texture.  Not always powers of 2, but always a multiple of 4.

Rest of meta data probably meaningless until someone figures out what texture format(s) are being used.
## Post #7
- Username: rman1234
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 03, 2021 2:51 am
- Post datetime: 2023-01-11T23:34:35+00:00
- Post Title: Diablo IV (.tex) textures

I'm also trying to see if I figure out how to extract the subfiles on each of these textures. I could find the metadata to get the format (usually BC1 or BC3) and the width/height, but some metadata also points to the texture rectangles to extract/crop specific subtextures. 

Example of an extracted texture + the corresponding tex meta file:
[https://anonymfile.com/VpmOx/skills1-2.png](https://anonymfile.com/VpmOx/skills1-2.png)
[https://anonymfile.com/6NQD0/skills1.tex](https://anonymfile.com/6NQD0/skills1.tex)
[https://anonymfile.com/AWEAP/colours1.png](https://anonymfile.com/AWEAP/colours1.png)
[https://anonymfile.com/Lap6a/colours1.tex](https://anonymfile.com/Lap6a/colours1.tex)

I can't figure out what coordinates to crop to get the subtextures, they have names on the .tex and some values there, but I can't find how they are supposed to be cropped (left, right, sizes...). Any idea on how to assemble the coordinates for cropping from the meta .tex files?
## Post #8
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-01-12T01:05:49+00:00
- Post Title: Diablo IV (.tex) textures

@rman1234: Metadata is divided into 100 bytes per block for a sub-texture, where last 32 bytes are normalized float coordinates for two points of rectangle, which probably works like UVs for texture (x+y pairs from top left). Though I'm not sure about why there are two sets there, for rectangle textures they are identical or close to that, which looks rather like designer fault.
## Post #9
- Username: rman1234
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 03, 2021 2:51 am
- Post datetime: 2023-01-12T02:07:48+00:00
- Post Title: Diablo IV (.tex) textures

That is what I was missing! The normalized texture coordinates, thanks so much @Spiritovod
## Post #10
- Username: Rushster
- Rank: n00b
- Number of posts: 10
- Joined date: Sat May 08, 2021 9:55 pm
- Post datetime: 2023-02-09T15:13:22+00:00
- Post Title: Diablo IV (.tex) textures

Did you manage to figure this out? I am trying to get a look at these now but not sure where to start and what to use to get these working.
## Post #11
- Username: Thidnen
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Feb 10, 2023 11:00 pm
- Post datetime: 2023-02-10T15:02:03+00:00
- Post Title: Diablo IV (.tex) textures

> Reply from IstiGI ↑Tue Dec 06, 2022 8:15 pm at Tue Dec 06, 2022 8:15 pm
>
> 
Ok. Here are few more examples with smaller size
https://drive.google.com/file/d/1K9sPs1 ... share_linkpapa's pizzeria

Thanks for these example
## Post #12
- Username: Rushster
- Rank: n00b
- Number of posts: 10
- Joined date: Sat May 08, 2021 9:55 pm
- Post datetime: 2023-02-11T13:52:41+00:00
- Post Title: Diablo IV (.tex) textures

So I have tried using Rawtex to get the .tex files to show but so far all coming out looking like garbage. Tried numerous settings on both the larger and smaller files but so far no cigar.

Has anyone had success getting these files converted and out to PNG?
## Post #13
- Username: Rushster
- Rank: n00b
- Number of posts: 10
- Joined date: Sat May 08, 2021 9:55 pm
- Post datetime: 2023-03-02T13:17:35+00:00
- Post Title: Diablo IV (.tex) textures

Still looking to get these texture files out to at least DDS. Has anyone got any help or pointers? I have tried numerous tools but to no avail so far
## Post #14
- Username: nic77
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 13, 2021 8:22 am
- Post datetime: 2023-03-21T14:24:39+00:00
- Post Title: Diablo IV (.tex) textures

Has anyone been able to convert them to .dds? Im tryting to do it with the beta files but as the previous user said even after using many tools I haven't been able to
## Post #15
- Username: BoyC
- Rank: beginner
- Number of posts: 36
- Joined date: Thu Jul 06, 2006 4:24 am
- Post datetime: 2023-03-22T14:59:49+00:00
- Post Title: Diablo IV (.tex) textures

> Reply from nic77 ↑Tue Mar 21, 2023 10:24 pm at Tue Mar 21, 2023 10:24 pm
>
> 
Has anyone been able to convert them to .dds? Im tryting to do it with the beta files but as the previous user said even after using many tools I haven't been able to

The raw texture data seems to be in bog standard DXGI_FORMAT_BC3_UNORM_SRGB: [https://imgur.com/a/m0YLwHg](https://imgur.com/a/m0YLwHg)
## Post #16
- Username: alexchaos
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Mar 23, 2023 3:05 am
- Post datetime: 2023-03-22T19:07:28+00:00
- Post Title: Re: Diablo IV (.tex) textures

> Reply from BoyC ↑Wed Mar 22, 2023 10:59 pm at Wed Mar 22, 2023 10:59 pm
>
> 
nic77 wrote: ↑Tue Mar 21, 2023 10:24 pm
Has anyone been able to convert them to .dds? Im tryting to do it with the beta files but as the previous user said even after using many tools I haven't been able to


The raw texture data seems to be in bog standard DXGI_FORMAT_BC3_UNORM_SRGB: https://imgur.com/a/m0YLwHg

What exactly are the steps your took? I've been trying a few different things with that format and can't seem to get any result.Thanks!
## Post #17
- Username: strpetrichor
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 10, 2020 10:19 am
- Post datetime: 2023-03-23T23:46:44+00:00
- Post Title: Re: Diablo IV (.tex) textures

The .tex files are indeed BC3_Unorm_SRGB

[https://imgur.com/a/uYWwDXk](https://imgur.com/a/uYWwDXk)

The resolution of the images can be a bit of a pain to find, some of them are massive.
## Post #18
- Username: BoyC
- Rank: beginner
- Number of posts: 36
- Joined date: Thu Jul 06, 2006 4:24 am
- Post datetime: 2023-03-24T00:01:51+00:00
- Post Title: Re: Diablo IV (.tex) textures

Yeah I've been looking at the metadata and on the particular image i've been looking at (the gems texture) what seems to be the width in the metadata (520) doesn't match up with the width at which the image lines up properly (576) - however the height does line up properly. No idea why, I haven't seen such a mismatch before.
## Post #19
- Username: alexchaos
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Mar 23, 2023 3:05 am
- Post datetime: 2023-03-24T01:56:15+00:00
- Post Title: Re: Diablo IV (.tex) textures

> Reply from BoyC ↑Fri Mar 24, 2023 8:01 am at Fri Mar 24, 2023 8:01 am
>
> 
Yeah I've been looking at the metadata and on the particular image i've been looking at (the gems texture) what seems to be the width in the metadata (520) doesn't match up with the width at which the image lines up properly (576) - however the height does line up properly. No idea why, I haven't seen such a mismatch before.

Same thing here, some width are good but most seems to not line up.
## Post #20
- Username: Ivenend
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Dec 16, 2018 10:58 am
- Post datetime: 2023-03-25T13:28:52+00:00
- Post Title: Re: Diablo IV (.tex) textures

> Reply from strpetrichor ↑Fri Mar 24, 2023 7:46 am at Fri Mar 24, 2023 7:46 am
>
> 
The .tex files are indeed BC3_Unorm_SRGB

https://imgur.com/a/uYWwDXk

The resolution of the images can be a bit of a pain to find, some of them are massive.

Just curious, do you have more d4 weapon icon images?

Also what offset in Rawtex do you use?
## Post #21
- Username: strpetrichor
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 10, 2020 10:19 am
- Post datetime: 2023-03-25T18:12:15+00:00
- Post Title: Re: Diablo IV (.tex) textures

> Reply from Ivenend ↑Sat Mar 25, 2023 9:28 pm at Sat Mar 25, 2023 9:28 pm
>
> 
strpetrichor wrote: ↑Fri Mar 24, 2023 7:46 am
The .tex files are indeed BC3_Unorm_SRGB

https://imgur.com/a/uYWwDXk

The resolution of the images can be a bit of a pain to find, some of them are massive.


Just curious, do you have more d4 weapon icon images?

Also what offset in Rawtex do you use?

i'm not using rawtex for this, i'm using a python script to pull the resolution from the meta file and then convert the .tex file in the payload folder with a matching name to a png with that resolution
i can try and grab some more of the armor/weapon icons in a bit - i posted some of my findings on the diablo subreddit, i'll probably do a deeper dive once the beta ends.
## Post #22
- Username: IstiGI
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Nov 16, 2015 11:10 pm
- Post datetime: 2023-03-29T06:32:25+00:00
- Post Title: Re: Diablo IV (.tex) textures

> Reply from strpetrichor ↑Sun Mar 26, 2023 2:12 am at Sun Mar 26, 2023 2:12 am
>
> 
i'm not using rawtex for this, i'm using a python script to pull the resolution from the meta file

Any chance that you can share it with us?
## Post #23
- Username: whfill
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue May 23, 2023 7:39 pm
- Post datetime: 2023-05-23T11:41:35+00:00
- Post Title: Re: Diablo IV (.tex) textures

> Reply from strpetrichor ↑Sun Mar 26, 2023 2:12 am at Sun Mar 26, 2023 2:12 am
>
> 
Ivenend wrote: ↑Sat Mar 25, 2023 9:28 pm
strpetrichor wrote: ↑Fri Mar 24, 2023 7:46 am
The .tex files are indeed BC3_Unorm_SRGB

https://imgur.com/a/uYWwDXk

The resolution of the images can be a bit of a pain to find, some of them are massive.


Just curious, do you have more d4 weapon icon images?

Also what offset in Rawtex do you use?


i'm not using rawtex for this, i'm using a python script to pull the resolution from the meta file and then convert the .tex file in the payload folder with a matching name to a png with that resolution
i can try and grab some more of the armor/weapon icons in a bit - i posted some of my findings on the diablo subreddit, i'll probably do a deeper dive once the beta ends.

Could you please share the script, or host it on github, thank you so much.
## Post #24
- Username: lla
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat May 20, 2023 8:13 am
- Post datetime: 2023-05-23T17:54:09+00:00
- Post Title: Re: Diablo IV (.tex) textures

Hey,

Has anyone been able to open/convert D4 tex-files to dds or png?
Can anyone help or walk me through cause I have not been successful so far.
I would much appriciate it!
Many thanks in advance!
## Post #25
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2023-05-28T18:32:50+00:00
- Post Title: Re: Diablo IV (.tex) textures

coredevel at zenhax created a tool that works well.  Unfortunately zenhax appears to be broken so I have not been able to ask him if it's ok to distribute the tool.  Does anyone know if he is active here?
## Post #26
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2023-06-09T00:01:27+00:00
- Post Title: Re: Diablo IV (.tex) textures

I have been unable to reach coredevel and zenhax appears to have shut down. As such, in order that it not be lost, <link removed by moderator - apparently this program was a virus (as reported by one of the users)> is the tool that can convert Diablo 4 Textures. Apologies to coredevel; if you would like me to remove the link I will do so immediately.

To use the tool, make sure that your meta and payload texture folders are arranged the same as they are in the game archives, including a meta and payload folder with the associated files.  Then, select the input texture directory that contains the meta files, and an output directory. Then, hit "Go".

If you did it right, the textures will be converted to .pngs.  I could only do a few hundred at a time, not sure why.  Eventually I was able to convert all of them.

Some of the textures have a strange alpha channel.  Not sure what should be there, but in most cases I just deleted it and all of necessary texture data was there.

Cheers
## Post #27
- Username: MisterT
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 12, 2023 4:06 pm
- Post datetime: 2023-06-12T08:20:40+00:00
- Post Title: Re: Diablo IV (.tex) textures

I am not managing to get the tool to work.
If anyone could help me out, that would be awesome! Could really use the help.

Anyone who got it to work and is willing to help, feel free to PM me!
## Post #28
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2023-06-12T17:21:30+00:00
- Post Title: Re: Diablo IV (.tex) textures

> Reply from MisterT ↑Mon Jun 12, 2023 4:20 pm at Mon Jun 12, 2023 4:20 pm
>
> 
I am not managing to get the tool to work.
If anyone could help me out, that would be awesome! Could really use the help.

Anyone who got it to work and is willing to help, feel free to PM me!

Here are some better instructions:

You need to extract the meta and payload textures that you want into a meta and payload folder on your system using [CASC Explorer](https://forum.xentax.com/viewtopic.php?t=26832).

For example:

I have extracted meta files to:

"C:\DIABLO4EX\base\meta\Texture"

and the payload files to:

"C:\DIABLO4EX\base\payload\Texture"

Then run the tool and select "C:\DIABLO4EX\base\meta\Texture" as your Input Texture Directory. Make sure you choose the meta directory, not payload! Now choose any folder you want as your Output Texture Directory. Then hit "Go".  

This is will create a 'png' for any 'meta' tex file that has a corresponding 'payload' tex file.  Some of them cause the tool to crash, although it still converts them.  You will need to remove the offending texture from the meta folder and try again after its converted.

Hope that helps,

Cheers
## Post #29
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2023-06-12T22:06:31+00:00
- Post Title: Re: Diablo IV (.tex) textures

> Reply from zardalu ↑Fri Jun 09, 2023 8:01 am at Fri Jun 09, 2023 8:01 am
>
> 
<link removed by moderator - apparently this program was a virus (as reported by one of the users)>

Edit - confirmed to be false positive. Check new version [here](https://forum.xentax.com/viewtopic.php?p=192477#p192477). Thanks roswell
## Post #30
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2023-06-12T22:48:31+00:00
- Post Title: Re: Diablo IV (.tex) textures

No, it's not a virus. And if someone reports it as one, then prove it.  Be specific, not generic.  VirusTotal always returns a small number of bogus hits, it's how these companies make money.  E.g. If program not signed, then give a false warning.

This seems to explain it. Some non-commerical AV engines are rigged with bogus settings:
"May differ from commercial off-the-shelf product.  The company decides the particular settings with which the engine should run in VirusTotal."

Some AVs may just rely on a database of hashes, so if hash not found, then give a false warning.
## Post #31
- Username: si3g
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Apr 15, 2016 9:50 am
- Post datetime: 2023-06-13T05:56:56+00:00
- Post Title: Re: Diablo IV (.tex) textures

The textures i tried to extract, eg the sanctuary map, seem to result in garbage output.

I don't know if the original author would like to share this on github so we can contribute.
## Post #32
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2023-06-13T10:22:31+00:00
- Post Title: Re: Diablo IV (.tex) textures

It was only given out to one person because it was never fully tested, so there may be a few unknown formats. But, I think it can handle most of them.  Any bad formats it can't handle need to be collected and uploaded somewhere for further inspection. Both meta and payload files required.
## Post #33
- Username: MisterT
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 12, 2023 4:06 pm
- Post datetime: 2023-06-13T10:34:00+00:00
- Post Title: Re: Diablo IV (.tex) textures

Chrome is currently refusing to redownload it, because of known trojan.
When I bypass it, windows defender blocks it, because known trojan.
When bypassing that as well and running it, Malwarebyte (Premium) goes haywire, because of known trojan.
As a certainty, I scanned my computer with SpyHunter, which also quarantined it as known trojan.

I guess I will not get the files I hope to obtain
## Post #34
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2023-06-13T10:48:20+00:00
- Post Title: Re: Diablo IV (.tex) textures

Let me try to nip this virus nonsense right here and now.

The original program is 100% clean and safe.  Downloading files from a single trusted source would be best, so if people distribute it elsewhere, that guarantee is lost. Malicious folks may try to hijack it.

This is the original hash from virustotal.com:

SHA-256: d2dceb984eaf160731d3e309048dfc66457a51161d386d71fe32dc1a159ffc53
File size 527.00 KB (539648 bytes)

So, trust this one.

btw, even Windows has a hash tool built into its operating system:

> certutil -hashfile d4_texture_converter.exe SHA256

SHA256 hash of file d4_texture_converter.exe:
d2 dc eb 98 4e af 16 07 31 d3 e3 09 04 8d fc 66 45 7a 51 16 1d 38 6d 71 fe 32 dc 1a 15 9f fc 53
CertUtil: -hashfile command completed successfully.
## Post #35
- Username: si3g
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Apr 15, 2016 9:50 am
- Post datetime: 2023-06-13T22:11:04+00:00
- Post Title: Re: Diablo IV (.tex) textures

> Reply from roswell ↑Tue Jun 13, 2023 6:22 pm at Tue Jun 13, 2023 6:22 pm
>
> 
It was only given out to one person because it was never fully tested, so there may be a few unknown formats. But, I think it can handle most of them.  Any bad formats it can't handle need to be collected and uploaded somewhere for further inspection. Both meta and payload files required.

Here's the huge sanctuary map tex file, the output image from the tool gives something that indicates it's not handling properly something about the dimensions or something.

[https://easyupload.io/ski68u](https://easyupload.io/ski68u)

Here's how the output image looks like:
## Post #36
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2023-06-13T23:49:15+00:00
- Post Title: Re: Diablo IV (.tex) textures

I believe 6208x6208 is the correct texture dimensions.  I assume it's a picture of a world map, according to its filename.
I'm not aware if the texture format stores any kind of scanline padding.  But, it does look like the pixels are shifted.  
I tried some things, but I couldn't unshift the pixels into something recognizable.

Subrect coords are always stored at the end of the file, but these are usually (0,0) to (1,1), so I see nothing there that would cause the pixels to shift.

Are there other "_Continent_map.tex" files with similar dimensions that convert correctly?
## Post #37
- Username: si3g
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Apr 15, 2016 9:50 am
- Post datetime: 2023-06-14T03:12:16+00:00
- Post Title: Re: Diablo IV (.tex) textures

There are 4 map files that seem big:

Frac_Underworld_map.tex
Kehj_Hell_map.tex
Quest_Template_World_map.tex
Sanctuary_Eastern_Continent_map.tex

They all result with the same kind of output.
## Post #38
- Username: IstiGI
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Nov 16, 2015 11:10 pm
- Post datetime: 2023-06-14T06:21:30+00:00
- Post Title: Re: Diablo IV (.tex) textures

Dimensions in meta are correct but the output textures contains blank alpha channel space. For example the world map texture file is actually 6272x6208 where 6208x6208 is a visible part of the texture. It would be very nice to get the updated version of the converter

Till then I can share a pretty ineffective way to get D4 textures
1) Install Noesis
2) Install TextureFinder plugin by Durik256
3) Choose .tex file in the plugin, select texture size and format (you can take it info from meta)
4) Now you can export a picture from Noesis preview
## Post #39
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2023-06-14T10:35:31+00:00
- Post Title: Re: Diablo IV (.tex) textures

Ok, the correct dimensions are 6272 x 6208. The decoder is simply being sent the wrong dimensions.

But, the converter uses the meta header to determine the dimensions for all textures, and
these say 6208 x 6208.  The header doesn't contain the value of 6272.  Difference is 64 (6272-6208),
and I don't see that value either.  So, I don't know where they're getting 6272.
## Post #40
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2023-06-15T14:55:35+00:00
- Post Title: Re: Diablo IV (.tex) textures

Texture dimensions for this particular .tex file is stored in the meta header at:
0x20	width  (WORD)
0x22	height (WORD)

I don't know how often this happens, if there's only a few textures that show this problem, then I could just add a simple hack until it breaks:
if (w == 6208) w = 6272;

btw, this program should never hangup or crash, so if any particular texture crashes it, let me know.

It saves out .png files at default (best) compression, so there's always a small delay when dealing with large textures.
## Post #41
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2023-06-15T23:13:50+00:00
- Post Title: Re: Diablo IV (.tex) textures

Ok, I updated the converter:

- added map dimensions fix
- compiled as 64-bit
- compiled as unicode
- added readme.txt

Download link, Updated (v105)
[https://app.box.com/s/iwcael2wbqbuor4eq7f5coqaexpz2cpt](https://app.box.com/s/iwcael2wbqbuor4eq7f5coqaexpz2cpt)

SHA-256 33fd1dbb14e85595c73243a53f7beeb73e753c65176dda21185017217e33e50b 
File size 619.50 KB (634368 bytes)

Uploaded to VirusTotal, 100% clean.
## Post #42
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2023-06-16T05:13:43+00:00
- Post Title: Re: Diablo IV (.tex) textures

This is a question that has nothing to do with textures, but does the plug-in for extracting diablo 4 models still not exist? I looked up some plugins, but couldn't find anything that could extract bones and weight together. I think we need a plug-in that can completely convert the model and extract it rather than the texture. Does anyone know about these plugins or tools?
## Post #43
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2023-06-16T11:57:04+00:00
- Post Title: Re: Diablo IV (.tex) textures

D4 model extraction thread here:
[viewtopic.php?t=26587](https://forum.xentax.com/viewtopic.php?t=26587)

But I think stand-alone tools are going to have a harder time importing D4 models, since they separated the data, and hashed all the filenames.  You can't look up resources like materials or textures without having some kind of database telling you which file to use.

The only way to do it cleanly is for someone to build model extraction directly into CASExporer, or something like that.
## Post #44
- Username: UuPhan
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Apr 21, 2021 2:31 pm
- Post datetime: 2023-06-16T13:56:23+00:00
- Post Title: Re: Diablo IV (.tex) textures

Does anyone have a problem with AO, Normal, Metal, Roughness? I couldn't find a right format with these type of textures. Some example:
[001_GoatManRanged_Body_AO.tex](https://anonymfile.com/PNmpr/001-goatmanrangedbodyao.tex)
[001_GoatManRanged_Body_Metal.tex](https://anonymfile.com/ZRxme/001-goatmanrangedbodymetal.tex)
[001_GoatManRanged_Body_Normal.tex](https://anonymfile.com/YPDkY/001-goatmanrangedbodynormal.tex)
[001_GoatManRanged_Body_Rough.tex](https://anonymfile.com/lLPd9/001-goatmanrangedbodyrough.tex)
## Post #45
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2023-06-16T14:17:21+00:00
- Post Title: Re: Diablo IV (.tex) textures

The pixel format is found in the meta header, and you only posted the payload data.  Need to see both files.
## Post #46
- Username: UuPhan
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Apr 21, 2021 2:31 pm
- Post datetime: 2023-06-16T14:24:55+00:00
- Post Title: Re: Diablo IV (.tex) textures

> Reply from roswell ↑Fri Jun 16, 2023 10:17 pm at Fri Jun 16, 2023 10:17 pm
>
> 
The pixel format is found in the meta header, and you only posted the payload data.  Need to see both files.

Ah, sorry. Here are meta header: 
[001_GoatManRanged_Body_Metal.tex](https://anonymfile.com/59Zpj/001-goatmanrangedbodymetal.tex)
[001_GoatManRanged_Body_Normal.tex](https://anonymfile.com/yKPNo/001-goatmanrangedbodynormal.tex)
[001_GoatManRanged_Body_Rough.tex](https://anonymfile.com/pdZQx/001-goatmanrangedbodyrough.tex)
[001_GoatManRanged_Body_AO.tex](https://anonymfile.com/drPx3/001-goatmanrangedbodyao.tex)
## Post #47
- Username: UuPhan
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Apr 21, 2021 2:31 pm
- Post datetime: 2023-06-16T14:46:01+00:00
- Post Title: Re: Diablo IV (.tex) textures

Got some information for those files:

```
 "__fileName__": "data/base/meta/Texture/001_GoatManRanged_Body_AO.tex",
 "__snoID__": 128032,
 "__type__": "TextureDefinition",
 "__typeHash__": 3631735738,
 "eTexFormat": 41,
 "dwVolumeXSlices": 1,
 "dwVolumeYSlices": 1,
 "dwWidth": 256,
 "dwHeight": 256,
 "dwDepth": 1,
 "dwFaceCount": 1,
 "dwMipMapLevelMin": 3,
 "dwMipMapLevelMax": 9,
 "dwImportFlags": 513,
 "unk_d27620": 0,
 "unk_dc7d39c": {
  "r": 0.8222674131393433,
  "g": 0.8222674131393433,
  "b": 0.8222674131393433,
  "a": 1
 },
 "pHotspot": {
  "x": 0,
  "y": 0
 },
 "serTex": [
  {
   "__type__": "SerializeData",
   "__typeHash__": 2632036962,
   "dwOffset": 0,
   "dwSizeAndFlags": 32768
  },
  {
   "__type__": "SerializeData",
   "__typeHash__": 2632036962,
   "dwOffset": 0,
   "dwSizeAndFlags": 8192
  },
  {
   "__type__": "SerializeData",
   "__typeHash__": 2632036962,
   "dwOffset": 8192,
   "dwSizeAndFlags": 4096
  },
  {
   "__type__": "SerializeData",
   "__typeHash__": 2632036962,
   "dwOffset": 12288,
   "dwSizeAndFlags": 2048
  },
  {
   "__type__": "SerializeData",
   "__typeHash__": 2632036962,
   "dwOffset": 14336,
   "dwSizeAndFlags": 1024
  },
  {
   "__type__": "SerializeData",
   "__typeHash__": 2632036962,
   "dwOffset": 15360,
   "dwSizeAndFlags": 512
  },
  {
   "__type__": "SerializeData",
   "__typeHash__": 2632036962,
   "dwOffset": 15872,
   "dwSizeAndFlags": 256
  }
 ],
 "ptFrame": [
  {
   "__type__": "TexFrame",
   "__typeHash__": 24231676,
   "hImageHandle": 0,
   "flU0": 0,
   "flV0": 0,
   "flU1": 1,
   "flV1": 1,
   "unk_8081ff3": 0,
   "unk_8082014": 0,
   "unk_8081ff4": 1,
   "unk_8082015": 1
  }
 ],
 "unk_20823c1": [],
 "ptPostprocessed": "0"
}
```


```
 "__fileName__": "data/base/meta/Texture/001_GoatManRanged_Body_Normal.tex",
 "__snoID__": 128031,
 "__type__": "TextureDefinition",
 "__typeHash__": 3631735738,
 "eTexFormat": 42,
 "dwVolumeXSlices": 1,
 "dwVolumeYSlices": 1,
 "dwWidth": 1024,
 "dwHeight": 1024,
 "dwDepth": 1,
 "dwFaceCount": 1,
 "dwMipMapLevelMin": 1,
 "dwMipMapLevelMax": 9,
 "dwImportFlags": 513,
 "unk_d27620": 0,
 "unk_dc7d39c": {
  "r": 0.5007882118225098,
  "g": 0.5052597522735596,
  "b": 0.9580270051956177,
  "a": 1
 },
 "pHotspot": {
  "x": 0,
  "y": 0
 },
 "serTex": [
  {
   "__type__": "SerializeData",
   "__typeHash__": 2632036962,
   "dwOffset": 0,
   "dwSizeAndFlags": 1048576
  },
  {
   "__type__": "SerializeData",
   "__typeHash__": 2632036962,
   "dwOffset": 0,
   "dwSizeAndFlags": 262144
  },
  {
   "__type__": "SerializeData",
   "__typeHash__": 2632036962,
   "dwOffset": 262144,
   "dwSizeAndFlags": 65536
  },
  {
   "__type__": "SerializeData",
   "__typeHash__": 2632036962,
   "dwOffset": 327680,
   "dwSizeAndFlags": 16384
  },
  {
   "__type__": "SerializeData",
   "__typeHash__": 2632036962,
   "dwOffset": 344064,
   "dwSizeAndFlags": 4096
  },
  {
   "__type__": "SerializeData",
   "__typeHash__": 2632036962,
   "dwOffset": 348160,
   "dwSizeAndFlags": 2048
  },
  {
   "__type__": "SerializeData",
   "__typeHash__": 2632036962,
   "dwOffset": 350208,
   "dwSizeAndFlags": 1024
  },
  {
   "__type__": "SerializeData",
   "__typeHash__": 2632036962,
   "dwOffset": 351232,
   "dwSizeAndFlags": 512
  },
  {
   "__type__": "SerializeData",
   "__typeHash__": 2632036962,
   "dwOffset": 351744,
   "dwSizeAndFlags": 256
  }
 ],
 "ptFrame": [
  {
   "__type__": "TexFrame",
   "__typeHash__": 24231676,
   "hImageHandle": 0,
   "flU0": 0,
   "flV0": 0,
   "flU1": 1,
   "flV1": 1,
   "unk_8081ff3": 0,
   "unk_8082014": 0,
   "unk_8081ff4": 1,
   "unk_8082015": 1
  }
 ],
 "unk_20823c1": [],
 "ptPostprocessed": "0"
}
```


Wonder what "eTexFormat" number stand for. Normal have 42, the rest AO, Metal, Roughness (kind of grayscale) is 41. And color texture is 49.
## Post #48
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2023-06-16T18:04:28+00:00
- Post Title: Re: Diablo IV (.tex) textures

Ok, I see the problem.

001_GoatManRanged_Body_AO.tex:
Payload file size is 16,384 bytes, but the texture dimensions of 256x256 needs twice that amount (32,768 bytes).
So, that's what causing the converter to crash.  Another case of misleading meta data in the header. Loading it as 128x128 should fix it.

I can add a fix for pixel formats 41 and 42, so it converts correctly and doesn't crash.
See previous post for updated download link.
## Post #49
- Username: lla
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat May 20, 2023 8:13 am
- Post datetime: 2023-06-16T18:06:38+00:00
- Post Title: Re: Diablo IV (.tex) textures

Result is the same as before the converter update for me.

e.g:
[2DUI_ProgressBars.tex](https://anonymfile.com/yKP4P/2dui-progressbars.tex)
[2DUI_NameplateBoss.tex](https://anonymfile.com/59ZbL/2dui-nameplateboss.tex)
[2DUI_ActionBar.tex](https://anonymfile.com/eRPDX/2dui-actionbar.tex)
[2DUI_ProgressBars.tex](https://anonymfile.com/WYzLL/2dui-progressbars.tex)
[2DUI_ActionBar.tex](https://anonymfile.com/Qp4yd/2dui-actionbar.tex)
[2DUI_NameplateBoss.tex](https://anonymfile.com/j0PWd/2dui-nameplateboss.tex)

Result:

[2DUI_ProgressBars.PNG](https://anonymfile.com/JOAbl/2dui-progressbars.png)
## Post #50
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2023-06-16T19:37:40+00:00
- Post Title: Re: Diablo IV (.tex) textures

Shifted pixels usually means the meta header has misleading texture dimensions.

meta header:
2DUI_ActionBar       (w,h:  992, 3568)
2DUI_NameplateBoss   (w,h: 1696,  376)
2DUI_ProgressBars    (w,h:  920,  656)

actual size:
2DUI_ActionBar       (w,h: 1024, 3568)
2DUI_NameplateBoss   (w,h: 1728,  376)
2DUI_ProgressBars    (w,h:  960,  656)

Texture dimensions can only be in multiples of 4, so it might be faster to determine the correct dimensions if you used the TextureFinder Noesis plugin and just keep adding 4 to the width until it looks correct.

This seems to happen often with GUI textures, but I'm not still not sure where they are getting these "adjusted" values if the meta header says otherwise.  I can update the program later with these fixes. If there's hundreds of these files, then I probably won't update the program until a real solution is found.

Updated:
2DUI_ProgressBars.PNG
## Post #51
- Username: UuPhan
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Apr 21, 2021 2:31 pm
- Post datetime: 2023-06-16T22:20:36+00:00
- Post Title: Re: Diablo IV (.tex) textures

I just wrote a script and plugin for Noesis and upload to Github. Scripts may not optimized and unable to read every files yet. So if you good at scripting then you can help to improve it or just report a issues on this git: [https://github.com/UuPhan/d4Tex](https://github.com/UuPhan/d4Tex)

[](https://postimg.cc/bGj1V14j)

[](https://postimg.cc/Jt75Wc0r) [](https://postimg.cc/w7ZXJCVM) [](https://postimg.cc/BjFxCmYg)

[](https://postimg.cc/py0YVh5D)
## Post #52
- Username: UuPhan
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Apr 21, 2021 2:31 pm
- Post datetime: 2023-06-17T06:28:50+00:00
- Post Title: Re: Diablo IV (.tex) textures

[ Updated Script - [https://github.com/UuPhan/d4Tex](https://github.com/UuPhan/d4Tex) ]  - Support more types, able to read mostly texture files but except these format code: 0, 7, 12, 25, 43, 44, 45, 50 and 51. That would be great if someone could tell me format of those type is.

> Reply from roswell ↑Sat Jun 17, 2023 3:37 am at Sat Jun 17, 2023 3:37 am
>
> 
Updated: 2DUI_ProgressBars.PNG

I think it should look transparent like this:
## Post #53
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2023-06-17T12:17:37+00:00
- Post Title: Re: Diablo IV (.tex) textures

That's just a thumbnail for display, not the real texture.  The converter will write .png files with an alpha channel, so yes, transparency is included if it has it.
## Post #54
- Username: dxp
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 23, 2023 4:16 pm
- Post datetime: 2023-06-23T08:21:51+00:00
- Post Title: Re: Diablo IV (.tex) textures

> Reply from roswell ↑Thu Jun 15, 2023 10:55 pm at Thu Jun 15, 2023 10:55 pm
>
> 
btw, this program should never hangup or crash, so if any particular texture crashes it, let me know.

minimap_mask.tex is crashing the app and leaves an 0b png

All Files with "minimap" in name create bad output.
2DUIMinimap.tex for example
## Post #55
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2023-06-24T15:40:29+00:00
- Post Title: Re: Diablo IV (.tex) textures

Please upload files (meta+payload, zipped in single attachment) for fixing. Thanks.
## Post #56
- Username: vuphanenjoyer
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 25, 2023 9:20 am
- Post datetime: 2023-06-25T01:27:17+00:00
- Post Title: Re: Diablo IV (.tex) textures

Here are some of the requested minimap files that are decoded incorrectly.
[bug.zip](https://xentaxbackup.github.io/file/23972_bug.zip)
## Post #57
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2023-06-25T19:20:31+00:00
- Post Title: Re: Diablo IV (.tex) textures

Ok, I made some changes. Added new pixel format 23, and I'm now re-calculating the texture dimensions for misleading headers, so that should fix them, once and for all. Updated download link.
## Post #58
- Username: vuphanenjoyer
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 25, 2023 9:20 am
- Post datetime: 2023-06-25T20:12:12+00:00
- Post Title: Re: Diablo IV (.tex) textures

Wow, thanks for the quick fix, it's working perfectly for the textures I needed them for ^^.

On a complete side note, I'm afraid there remain some vile textures which don't want to be decoded. I personally don't need these, but wanted to post them anyway.




[bug.zip](https://xentaxbackup.github.io/file/23973_bug.zip)
## Post #59
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2023-06-26T04:52:00+00:00
- Post Title: Re: Diablo IV (.tex) textures

I was able to fix MinimapBackground, but the other one doesn't seem to decode correctly.

2DUI_MinimapBackground.tex:
converts ok after fix.

2DUI_Minimap_DGN_Hatches.tex:
header dimensions: 512x512

Something unusual about this one.  Tried various dimensions, but can't get rid of the lines.
The lines straighten out if decoded as 128x128, but doesn't look correct.  It should decode as BC1.
## Post #60
- Username: IstiGI
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Nov 16, 2015 11:10 pm
- Post datetime: 2023-07-19T15:42:42+00:00
- Post Title: Re: Diablo IV (.tex) textures

> Reply from roswell ↑Mon Jun 26, 2023 3:20 am at Mon Jun 26, 2023 3:20 am
>
> 
Ok, I made some changes. Added new pixel format 23, and I'm now re-calculating the texture dimensions for misleading headers, so that should fix them, once and for all. Updated download link.

Thanks for you tool man. Too bad it crushes almost instantly. Any ideas why this is happening?
## Post #61
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2023-07-20T14:35:00+00:00
- Post Title: Re: Diablo IV (.tex) textures

Crashes after doing what?  startup? conversion?  It runs ok here.  If conversion, I would need to see the last file that causes it.
## Post #62
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2023-07-29T11:32:54+00:00
- Post Title: Re: Diablo IV (.tex) textures

Same for me, it crashes after 32 items. If I look at the list of images it has converted, it looks like it is unable to convert a file named : "2DInventory_Bundle_Accessory_glo_stor001"

Although everything else looks krisp, so well done.

Could you just implement a error log/ try catch statement that is just logs what files went wrong and continue?

Thanks !!
T.
## Post #63
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2023-07-29T12:20:36+00:00
- Post Title: Re: Diablo IV (.tex) textures

Things going wrong/crashes:

Incorrect:
2DUI_BrightnessScreen_Highs
2DUI_BrightnessScreen_Mids
2DUIBreathMeter

Crashes:
2DUITiled_SelectionHighlightExpertise

BTW, could you share some info on the meta files, it may help me out for the 3D models, since I'm struggleing with those :/

T.
## Post #64
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2023-07-30T00:37:52+00:00
- Post Title: Re: Diablo IV (.tex) textures

I don't have the full installation, so please upload (meta+payload) for any files that won't load.

UuPhan posted a JSON output of the meta file on page 4, which has very descriptive field names:
[viewtopic.php?t=26053&start=45](https://forum.xentax.com/viewtopic.php?t=26053&start=45)

Maybe you should ask him what program he used to dump D4 meta files to JSON output, because I don't have it.
