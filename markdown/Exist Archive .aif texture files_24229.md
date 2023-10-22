## Post #1
- Username: Diablomarv
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jul 11, 2021 8:54 am
- Post datetime: 2021-07-13T04:23:06+00:00
- Post Title: Exist Archive *.aif texture files

Hi, I'm trying to get access to the Exist Archive [Vita] models and texture files, it's a long process.
I managed to unpack the cpks and found the image/texture files as .AIF files, I tried using the SOA and TOC aif viewers to no avail.
I tried the Texture Cooker tool and none of the options on there worked, there were 2 options that sort of worked on the PVRTexTool ... but they look like this... Pretty sure it's still the wrong way to view the files.
The options that worked were 512x512 compressed PVRTC 2bpp RGB and 2bpp RGBA.

A link to the file if you wanna mess with it is:
[https://www.mediafire.com/file/hucos5ro ... e.aif/file](https://www.mediafire.com/file/hucos5roggkq2jq/cp001_unitface.aif/file)

I can provide more .aif files if that'd help.
Thanks in advance!
It would be nice to be able to eventually mess with the aif files themselves and repack them into the game, but at least viewing them is a start.
[cp001_test1.png](https://xentaxbackup.github.io/file/20453_cp001_test1.png)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-07-20T14:20:58+00:00
- Post Title: Exist Archive *.aif texture files

Apparently it's RGBA32 if you take a look at the data. 


Here's the test noesis script for the file:
[tex_ExistArchive_aif.zip](https://xentaxbackup.github.io/file/20474_tex_ExistArchive_aif.zip)
