## Post #1
- Username: AaronVB
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 23, 2021 4:37 am
- Post datetime: 2021-04-22T21:05:18+00:00
- Post Title: Crossout's .grp files

Hi everyone,

Recently i've been trying to extract textures from the game Crossout.

I found out that when you open their .grp files in a hex viewer, you can find the names of files in that archive and the header "GRP2".
For every .grp file there is also a .index file which has a header "TGP2" and sometimes also contains file names.

For Models they appaear to be using .mdl and .mdf and for Textures .tfh.

Since War Thunder and Crossout use the same engine, the "dagor engine", I searched for War Thunder texture extractors since War Thunder has been around for a lot longer and found this thread -> [viewtopic.php?t=11349](https://forum.xentax.com/viewtopic.php?t=11349).
However, War Thunder apparently used to/still uses .bin files for Textures and only uses .grp for Models, while Crossout has both Textures and Models in .grp Files. War Thunder has a Modding-Toolkit, however that doesn't seem to be able to open .grp files.

I found a bunch of QuickBMS scripts that are supposed to be ably to open these Files but it seems Crossout uses a modified Format since none worked for me. I also found a shell script on GitHub that looked useful but it only prints out junk.
[https://github.com/darealshinji/scripts ... aster/grp2](https://github.com/darealshinji/scripts/blob/master/grp2)


And now i'm here, looking for help.
## Post #2
- Username: TheInfinityUser
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Mar 17, 2021 2:45 pm
- Post datetime: 2021-05-02T18:53:47+00:00
- Post Title: Crossout's .grp files

With help, I was able to unpack the grp file. But I dunno about the tgp file tho.

The grp file further contains even more files.
It contains five more files - MDL, MDF, MDP, TFH and TFD.
Here's the unpacked grp file along with the script [https://drive.google.com/file/d/1CmMSbx ... p=drivesdk](https://drive.google.com/file/d/1CmMSbxtt7kCOYoTFRG33c0R5gYdYjU3s/view?usp=drivesdk)
## Post #3
- Username: knifers
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jan 09, 2018 1:05 am
- Post datetime: 2021-05-04T16:34:04+00:00
- Post Title: Crossout's .grp files

Good job, how you figure it out?
## Post #4
- Username: TheInfinityUser
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Mar 17, 2021 2:45 pm
- Post datetime: 2021-05-04T16:41:46+00:00
- Post Title: Crossout's .grp files

Someone on discord did, I didn't.
He says that he looked at the bytes, did some analysis and created a script for it.
I don't think there is currently any way to decode any of those files.
But I viewed the files in hex viewer and the MDL appears to be for the model, the MDP appears to be for physics and the mdf appears to be for materials. And as you said earlier tfh and tfd are for the textures.
## Post #5
- Username: Zhung Me
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 13, 2022 6:12 am
- Post datetime: 2022-07-12T22:14:48+00:00
- Post Title: Crossout's .grp files

SHEESH, link is no more... 
somebody can pm me a new one?
## Post #6
- Username: Persival
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Oct 06, 2018 10:14 am
- Post datetime: 2022-07-20T17:38:05+00:00
- Post Title: Crossout's .grp files

- Has anyone that script to reupload? Hope it not missed forever.
## Post #7
- Username: FriedrichAlterFritz
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Dec 29, 2019 4:24 am
- Post datetime: 2022-08-13T22:46:12+00:00
- Post Title: Crossout's .grp files

Here is my version of the .grp unpacker. 
Usage: unpacker.py -i "folder with archives" -o "output folder"

However, I still couldn't fix some issues:
 1. The script can unpack only first 131072 bytes of original file
 2. .pk2 files cannot be extracted

I also researched the .mdl file and found that this is also an archive, but I could not figure out how files are stored in it.
[unpacker + some mdl files.zip](https://xentaxbackup.github.io/file/22642_unpacker + some mdl files.zip)
## Post #8
- Username: Butterized
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 29, 2023 6:41 am
- Post datetime: 2023-03-31T01:55:15+00:00
- Post Title: Crossout's .grp files

does anyone know how to use the script? i cant seem to figure it out.
## Post #9
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2023-04-19T09:22:03+00:00
- Post Title: Crossout's .grp files

> Reply from TheInfinityUser ↑Wed May 05, 2021 12:41 am at Wed May 05, 2021 12:41 am
>
> 
Someone on discord did, I didn't.
He says that he looked at the bytes, did some analysis and created a script for it.
I don't think there is currently any way to decode any of those files.
But I viewed the files in hex viewer and the MDL appears to be for the model, the MDP appears to be for physics and the mdf appears to be for materials. And as you said earlier tfh and tfd are for the textures.

I released the Targem Engine (Crossout) *.mdl/mdf loader module.

How to get the 3D Object Converter:
Download the 3D Object Converter from [ http://3doc.i3dconverter.com](http://3doc.i3dconverter.com) and install it or download and use the portable version (if you don’t have it yet).

After it just use the Help/Check for updates... function to get the latest program version.
## Post #10
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-05-03T22:31:19+00:00
- Post Title: Crossout's .grp files

i made plugin for Noesis [*.mdl]



Без имени-1.png (32.58 KiB) Viewed 197 times


[fmt_Crossout_mdl.py](https://github.com/Durik256/Noesis-Plugins/blob/master/fmt_Crossout_mdl.py)


> Reply from Butterized ↑Fri Mar 31, 2023 9:55 am at Fri Mar 31, 2023 9:55 am
>
> 
does anyone know how to use the script? i cant seem to figure it out.
send .grp file
## Post #11
- Username: maksum022
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat May 27, 2023 12:43 am
- Post datetime: 2023-05-26T17:18:45+00:00
- Post Title: Crossout's .grp files

for some reason things not work for me, models just not open or show corrupted geometry
## Post #12
- Username: FriedrichAlterFritz
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Dec 29, 2019 4:24 am
- Post datetime: 2023-10-01T20:46:40+00:00
- Post Title: Crossout's .grp files

It seems that I understand - the .index file contains three blocks, two of which are compressed using ZSTD - these are file names and a table with the sizes and offsets of these files. The third block is the sizes of ZSTD frames, the game resource data itself is compressed in frames of 128 kb of the original data.
## Post #13
- Username: FriedrichAlterFritz
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Dec 29, 2019 4:24 am
- Post datetime: 2023-10-09T02:08:13+00:00
- Post Title: Crossout's .grp files

How to decode TFH header (first 8 bytes)? I need to know what the bits in pixel_format mean (when the image uses DXT1, DXT5 or raw encoding) and how to find the width and height of the image.
Here is its approximate structure:
struct tfh_header {
  unsigned char width_height[4];

  unsigned char a1; // always 1

  unsigned char has_alpha_channel:1;
  unsigned char mips_count:4;
  unsigned char zeros:3; // = 0 

  unsigned char pixel_format; // = this is what i need to know

  unsigned char zero; // = 0
};
struct tfh_mip {
  unsigned long offset;
  unsigned long sized;
  unsigned long decoded_width;
  unsigned long size2; // = size
};

Some files: [https://ufile.io/8a2yar0l](https://ufile.io/8a2yar0l)
## Post #14
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-10-09T17:44:53+00:00
- Post Title: Crossout's .grp files

> I need to know what the bits in pixel_format mean (when the image uses DXT1, DXT5 or raw encoding) and how to find the width and height of the image.
Try one of these to find correct pixel format and height/width  [viewtopic.php?t=15540](https://forum.xentax.com/viewtopic.php?t=15540)
