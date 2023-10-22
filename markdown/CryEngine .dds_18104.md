## Post #1
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2018-05-17T14:23:30+00:00
- Post Title: CryEngine .dds

I tried following this post below, but I'm getting awful results from the _ddna image type.
To me, it only works for diffuse, displacement, etc.
When I do the same for the normal map, I get results like this:



I know it's close but yet very far away. Can I get some help?
I uploaded random samples here: [https://drive.google.com/open?id=18G5sl ... odI_dfYQRf](https://drive.google.com/open?id=18G5sl-3fqXSJ0nSUSjinaLodI_dfYQRf)


> Reply from o0Crofty0o
>
> Ok what you need:
Noesis (huge thanks here to MrAdults for supporting the normal map format of these properly, even Photoshop doesn't like them much)
Hex Editor
Intel .dds plugin for Photoshop (for the specgloss map thingies)
This .zip with headers:
BC4_Headers.zip
1. Textures are made of these files:

The .dds contains the header info and i think smallest mip level, 1-8 files are increasing mips of the texture. Just take the biggest one (with the highest number, in this case 8, it is the most HD version)

2. Open the .dds and the .8 file in HxD. Switch to the .8 file and select everything with ctrl+a, then copy it with ctrl+c. 

3. Switch to the .dds file and select everyting starting at Offset 94 to the end:

(94 is important, if you do it at for eg 95 your texture will be shifted sidewards and not match the UV)
Then simply paste with ctrl+p and save with ctrl+s.

4. Open texture in Noesis and convert to your format of choice.
You can alternatively open these in Photoshop using the Intel plugins mentioned above. For that open your texture in HxD again and change this small part from whatever it is to 01 (thanks to chrrox for figuring this out): 


5. You may have noticed that _ddn (normal maps) usually don't just have the 1-X files but also files called like 6a,7a,8a. 1-8 belong to normal map, 1a-8a belong to the gloss map.
You have to convert it seperately (as far as i know anyway). I don't know where the game gets this header from, it isn't the .a file. I figured it's BC4 textures however and added a .zip to this post that has headers for the dimensions i came across in the files. The gloss maps here share the dimensions the normal maps have (4k normal map = 4k gloss map). So if it is 4k, open BC4_4k_header.dds and the .8a file in HxD, copy everything from the .8a file again and paste it below the header (offset 80). Save it under a new name you will find easy.
Noesis displays these as plain white, but Photoshop with the linked plugins loads them fine.

6. I noticed that for some reasons the normal map channels seem to be switched (red should be green, green should be red). If you don't do that shading might look quite bad in whatever software you render in.

7. You're finally done and can load them all on your model! Yey!
## Post #2
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-05-17T15:59:46+00:00
- Post Title: CryEngine .dds

This is a format error. You changed something in the header files? Or what tool you use to display those? Noesis displays them correct. I only get this error when i change the format at offset 0x80 from 0x54 to 0x53. signed and unsigned encode. This may be a decoder error in your texture viewer?

Also. I'm not sure howto get unlinked post attachements. Not that i needed those bc4 headers. It's the same file header c/p with just format 0x50. This can be read in the .a files after the CRYF ormat Fourcc. It sure is a weird thing this header is variable in size. I call this 0xbaadc0de.
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-05-17T20:40:47+00:00
- Post Title: CryEngine .dds

link to that original post   
[viewtopic.php?p=130909#p130909](http://forum.xentax.com/viewtopic.php?p=130909#p130909)

> Reply from episoder
>
> I call this 0xbaadc0de.
i see what you did there
