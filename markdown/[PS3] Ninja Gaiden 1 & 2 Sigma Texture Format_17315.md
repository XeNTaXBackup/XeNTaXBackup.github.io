## Post #1
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2017-11-22T02:17:10+00:00
- Post Title: [PS3] Ninja Gaiden 1 & 2 Sigma Texture Format

I figured out a method to extract GXT textures from the Vita version of Ninja Gaiden Sigma 2.  Since they are low resolution I'm looking to employ similar tricks to the PS3 format.  I know where the image data is, I just don't know the format.  In previous cases I needed the image header, either gxt or dds.  For these files, I don't see any header information, so I'm guessing I need to find the headers or need to know what header data to put in front of the data.  Could someone please help me identify the format of the images or identify what I'm looking for in terms of header data?

Thanks!

Sample Files: [http://www.mediafire.com/file/2b4gfetq7 ... lNinja.zip](http://www.mediafire.com/file/2b4gfetq755gkbm/NGS2_PS3_TacticalNinja.zip)



The gmd contains the local offset inside the ttgl. The gmd also includes the length of the image data.  The ttgl contains the image data.
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-11-22T09:06:23+00:00
- Post Title: [PS3] Ninja Gaiden 1 & 2 Sigma Texture Format

the ttg in gmd has 3 sections of info, the first contains the offsets, the second contains the datasize and the last contains format
and width and height and strings. The first byte of that 32 byte stride last section is the format, 0x88 == dxt5 and 0x86 == dxt1.  

edit
the image data actually starts at 0x100 in the ttgl, so the offsets are not absolute it seems, add 0x80 to each

edit2
here is Noesis python script that will open the textures from your sample  
*script updated December 19, 2017*


 tex_NinjaGaiden2Sigma_PS3_ttgl.zip
(1.35 KiB) Downloaded 94 times


supports DXT1, DXT3, DXT5 and ARGB32 swizzled formats
you must have the gmd and ttgl pair in same folder, then open the gmd file.
## Post #3
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2017-11-22T13:38:33+00:00
- Post Title: [PS3] Ninja Gaiden 1 & 2 Sigma Texture Format

Holy Cow! Wow, Thanks, AceWell! You went the extra mile, in creating the plugin too! Glad I was more specific in my questions than usual, lol.

So since the third TTD block just had basic info & dxt1/dxt5 flags, I still would have had craft the DDS header myself?  I looked at your plugin. I'm not that skilled with Noesis stuff, but it looks like it's leveraging Noesis' code to generate the textures?  Just trying to expand my knowledge to better understand this stuff. 

Thanks again, exceeded expectations and saved me a bit of time on restructuring on of my own scripts.  

Edit: 
Shoot, it would figure the one sample wasn't a good baseline...   All the other files I'm trying are crashing.  Here's what I've found by tinkering with the plugin. 

Most other files have this happen:



Since it's a print line, if I comment it out, I get this.



I noticed that some files do have 0x85 for a file type.  Might that be DXT3 or alternate DXT with/without alpha channel?

I'm going to attempt to identify the issue, but I'm rather slow at this since I haven't worked with Noesis plugins before? Can I get the print lines to show in a console somehow?  Only recourse I have at the moment is to Save > Reload Plugins> 'Hope for the best'

Here are some other file samples: [https://www.mediafire.com/file/s7dacdlf ... amples.zip](https://www.mediafire.com/file/s7dacdlfi83c4jo/NGS2_PS3_Samples.zip)

Edit 2: 
In the case of r_rei_a.gmd it looks like the image data is split between the gmd/ttgl.  The Vita files did this, so unfortunately not surprising, but in that case all images were in one file or the other, not divided...  need to figure out if there's a flag to determine which file holds each image because offsets appear to be mixed.  :-/
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-11-23T00:16:40+00:00
- Post Title: [PS3] Ninja Gaiden 1 & 2 Sigma Texture Format

yeah one sample rarely is ever enough to reverse correctly   
uncomment line 7 in the script and reload to bring up the console to see print.
i will investigate this format 0x85
## Post #5
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2017-11-23T01:06:51+00:00
- Post Title: [PS3] Ninja Gaiden 1 & 2 Sigma Texture Format

> Reply from AceWell
>
> i will investigate this format 0x85

i don't endian so well, but looks like ATI2 format
## Post #6
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2017-11-23T03:06:59+00:00
- Post Title: [PS3] Ninja Gaiden 1 & 2 Sigma Texture Format

Thanks, guys!

I did more tinkering and I've managed to gut the data of one sample manually and combine with proper DXT1/DXT5 headers, so it'll be quicker for me to write a dump routine since I don't know the noesis library as well.  I'm getting close, and if I'm on the right track the only thing that'd be missing is whatever that 0x85 format is.  If is is indeed ATI2 would it have a different file header format?

I did find that byte 0xE in each of the header strides identifies the file that contains the data.  if its 0x00 then the data is in the ttgl.  If its 0x01 then it's in the gmd.
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-11-23T03:10:33+00:00
- Post Title: [PS3] Ninja Gaiden 1 & 2 Sigma Texture Format

i couldn't get anything decent with ATI2, but morton swizzled raw looks good  

```
            untwid = bytearray()
            for x in range(0, imgWidth):
                for y in range(0, imgHeight):
                    idx = noesis.morton2D(x, y)
                    untwid += data[idx*4:idx*4+4]
            data = rapi.imageDecodeRaw(untwid, imgWidth, imgHeight, "a8 r8 g8 b8")
            texFmt = noesis.NOESISTEX_RGBA32


```
## Post #8
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2017-11-23T04:45:16+00:00
- Post Title: [PS3] Ninja Gaiden 1 & 2 Sigma Texture Format

Oiy, I'm so close.  Glad you found the proper format.  Ok, so down to the last thing... what does the header look like for that format?  At least with a working container I could see the DXT1/5 headers as a reference, but since the plugin doesn't yet like having images divided, I can't get Noesis to export me one of that type.  I'll have to dig for a pair of files that has them all in the ttgl and include at least one 0x85.

Here's what I have so far.  It's working on both standard & mixed types.  After opening both files it'll dump all textures, but of course the 0x85's aren't correct.  My code isn't very sophisticated, so I have some things hard coded since I'm still learning how to dissect all this stuff.  

[https://www.mediafire.com/file/wrnj7rba ... r_V0.9.zip](https://www.mediafire.com/file/wrnj7rba47r4ap9/NGS2_DDS_Ripper_V0.9.zip)
## Post #9
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2017-11-27T18:38:55+00:00
- Post Title: [PS3] Ninja Gaiden 1 & 2 Sigma Texture Format

Ok, I guess this constitutes an official release.  I've been able extract everything to suit my needs, so I'm not pouring a ton of time into a Noesis plugin, but what I came up with is a bit of a clunky multi step process.  All textures that aren't ripped as DDS will output as '.ngs'.  I managed to cobble together a watered down version of the Noesis plugin that will read just the '.ngs' format and use the provided samples to make them viewable in Noesis, and by that, extractable.  I've only found a couple characters so far that even have the RGBA32 textures, and of those it's a small percentage of the overall textures.  In most cases they are normal maps.  

Ninja Gaiden Sigma 2 PS3 DDS Ripper & Custom Noesis plugin: [https://www.mediafire.com/file/m7myca7e ... r_V1.0.zip](https://www.mediafire.com/file/m7myca7eq3a1ayb/NGS2_DDS_Ripper_V1.0.zip)

Thank you so much for the assist, AceWell! I never would have made sense of the header or stumble across the swizzle algorithm without the samples to follow.
## Post #10
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2017-12-09T14:56:16+00:00
- Post Title: [PS3] Ninja Gaiden 1 & 2 Sigma Texture Format

I got some motivation to work on Ninja Gaiden Sigma 1.  Thankfully much of the data is the same, so I only had to adjust some things for my script.  One snag though is another image format.  This one contains mostly 86/88 DXT1/5   stuff, but now there is a 0x87 image type.  

AceWell, or anyone knowledgeable, any chance you could help parse that one like with the 0x85?  Please  

I have included two sample file sets that have 0x87's in them.  Like before, the TMC has the header data, the TTX has the image data.  The file is not actually a TTX extension, I just had to call it something since there was no extension in the header of the original file when unpacked.   I have also included my script in its current state which will dump all dds.  0x87's will dump to .ngs like with my previous script with just the header data & image data in case this any way a time saver to get right to the guts needed to parse the format.  

[https://www.mediafire.com/file/gef47cp9 ... amples.zip](https://www.mediafire.com/file/gef47cp932ec8dm/NGS_Samples.zip)
## Post #11
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-12-09T21:45:32+00:00
- Post Title: [PS3] Ninja Gaiden 1 & 2 Sigma Texture Format

the 0x87 types look like dxt3 to me
## Post #12
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2017-12-09T22:05:24+00:00
- Post Title: [PS3] Ninja Gaiden 1 & 2 Sigma Texture Format

Terrific!! Looks like that worked.  Thank you so much.  

btw, Ace, I saw that I couldn't send you a PM.  Any way I can throw something your way for your time.  I really appreciate the help.
## Post #13
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-12-20T02:36:04+00:00
- Post Title: [PS3] Ninja Gaiden 1 & 2 Sigma Texture Format

just knowing that it works is good enough for me   

and since i don't like leaving incomplete scripts posted i have updated my previous Noesis python script here with your findings   
[viewtopic.php?p=135533#p135533](http://forum.xentax.com/viewtopic.php?p=135533#p135533)
## Post #14
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2017-12-21T15:01:33+00:00
- Post Title: [PS3] Ninja Gaiden 1 & 2 Sigma Texture Format

Thank you! You are a true community team player.  I'm glad to having some working utils for a game I wasn't sure that extraction would happen for.  

Awesome stuff, I'm sure the Noesis route will be helpful for any more keen on that over my roundabout methods.  

Alternate topic, do you work with mesh extraction as well or just stick to graphic formats?  I have one last game on my to do list which has been challenging due to the age & irregular format (ie Original Xbox/MGF format).  My success at enlisting help in the past has been a challenge.
## Post #15
- Username: ryu haybusa
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon May 10, 2021 12:09 am
- Post datetime: 2021-06-06T14:30:37+00:00
- Post Title: [PS3] Ninja Gaiden 1 & 2 Sigma Texture Format

Hey All,

I've been reading about TTGL and GMD file formats for a while now and attempted a model swap for Ninja Gaiden 3: Razors Edge on RPCS3

What I found and am struggling with:

I.E: Ryu into Ayane

Ryu GMD & TTGL filesize is less than Ayane's
Ryu is 5mb for example and Ayane's is 6mb

I copy GMD & TTGL data of Ryu into Ayane's -> Model doesn't load
I add padding to the GMD/TTGL of Ayane's to bring the file size back to 6mb -> Model swap works

The problem im having is, I can't do swap of characters if the TTGL/GMD data im putting into is a greater size as I can't "depad" the data to match the original size. Am I missing a step here? Any help would be great 

I noticed if I copy over the image data in TTGL from Ryu to Ayane but not the full image data. I.E from 0x100 to say 0x1EFC90 without adding padding - it'll render Ayane but the colour for her costume/body is missing (I.E they're random colours of green, black etc..) but the head will render correctly...so if I copy more of the TTGL (the rest of the file) that's when the model fails to load
## Post #16
- Username: HUnterARG
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Mar 22, 2022 4:54 pm
- Post datetime: 2022-03-22T13:57:00+00:00
- Post Title: Re: [PS3] Ninja Gaiden 1 & 2 Sigma Texture Format

Hello, I need help extracting Ninja Gaiden Sigma textures from PS3. I have extracted the ".afs" files with AFSPacker and then the textures with "NGS DDS Ripper". But I can't extract the textures that are inside the files extracted from the "spr" file. Is it in another image format? Try looking with the Text Editor and found that it says "texture_image" Is there a way to extract them?

Here an example of the file i want to extract: [https://www.mediafire.com/file/e3jxgjfx ... e.zip/file](https://www.mediafire.com/file/e3jxgjfxqswd493/file.zip/file)
## Post #17
- Username: SpeedVash
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat May 15, 2021 9:14 am
- Post datetime: 2022-04-23T18:57:17+00:00
- Post Title: Re: [PS3] Ninja Gaiden 1 & 2 Sigma Texture Format

Dude I'm also trying to extract something similar. These are the ninja gaiden 3 re files. There are two files, the LTF and SPR, which I have not yet been able to extract.
