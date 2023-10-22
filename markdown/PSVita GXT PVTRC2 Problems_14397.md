## Post #1
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2016-05-26T08:49:50+00:00
- Post Title: PSVita GXT PVTRC2 Problems

Hello! I'm trying to convert some textures from PS vita games, in this case Killzone Mercenary. But I can't obtain properly files.
I can see textures with texture finder as DXT1 or DXT5 formats but all files are swizzling



also, I tried to add some PVR headers (PVRTC), the textures look unswizzled but with bad colors and very pixelated.

maybe someone here have experience with this formats. ( maybe this tool can help. I don't have the necessary requirements to compile the tool  [https://github.com/xdanieldzd/GXTConvert](https://github.com/xdanieldzd/GXTConvert)  )

here are some raw samples 

[http://www.mediafire.com/download/f1m4p ... es_kzv.rar](http://www.mediafire.com/download/f1m4pxcun0a66n9/samples_kzv.rar)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-06-05T18:36:15+00:00
- Post Title: PSVita GXT PVTRC2 Problems

I tried to get something out of your samples with an experimental Noesis script i made using the unswizzle part of mikulover39's gxt script posted here
[viewtopic.php?f=16&t=14419&p=119216&hilit=gxt#p119216](http://forum.xentax.com/viewtopic.php?f=16&t=14419&p=119216&hilit=gxt#p119216)

i gave your samples a gxt extension, the text2_n sample looked good


i couldn't get anything decent from text2_d or text2_s

here is the experimental script if you want to mess around with it


 tex_PSVitaX_gxt.zip
(891 Bytes) Downloaded 122 times
## Post #3
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2016-06-06T08:29:17+00:00
- Post Title: PSVita GXT PVTRC2 Problems

Thanks a lot AceWell for the script will be very useful in the future for other GXT formats.

some days ago I discovered how to convert the textures used GXTconvert + adding the following headers to the RAW GXT data


 512x512 UBC1 (similar to BC1 but Swizzled)




 512x512 swizzled UBC3 (alpha) (similar to BC3 but Swizzled)

This is result with a UBC1 header



now I have other problem with some GXT textures. 
Some files use format PVRTC2 4BPP, GXTconvert doesn't support PVRTC2 formats, so I used pvrtextool for convert the file in a DDS UBC3 texture, then I used GXTconvert with the new file for obtain a unswizzled texture but the result is this:



if someone know what happened here it would be very useful the information.

sample images
[http://www.mediafire.com/download/1dost ... amples.rar](http://www.mediafire.com/download/1dost795q87whtp/normal_samples.rar)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-06-06T22:55:07+00:00
- Post Title: PSVita GXT PVTRC2 Problems

> Reply from luxox18
>
> if someone know what happened herewhat's wrong with the texture?
The checker pattern? Maybe it's for marking transparency? (just a wild guess.)
## Post #5
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2016-06-10T08:54:04+00:00
- Post Title: PSVita GXT PVTRC2 Problems

here are others looks of the problem from other texture files




and here is one DDS file for a better analysis of the issue

[http://download1646.mediafire.com/hp9vh ... body_s.dds](http://download1646.mediafire.com/hp9vh4y0n5kg/5eh55gvd5bgopab/kzv_hgh_heavy_trooper_body_s.dds)

and about transparency, the normal texture posted in the previous post have no alpha channel. The dds file above this line have alpha but looks bad too ( I think that when I converted the PVRTC2 texture to DDS-UBC3 and then to normal DDS there are loss of information in the file)
## Post #6
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-06-11T12:14:15+00:00
- Post Title: PSVita GXT PVTRC2 Problems

Looks like either wrong DDS format or an issue with the unswizzling.
## Post #7
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2016-09-23T06:42:44+00:00
- Post Title: PSVita GXT PVTRC2 Problems

Adding a pvr header to the image then using this script to reorder to linear seems to work fine. Just make sure
ENABLE_PVR_REORDERING_TOOL = True
[http://himeworks.com/redirect.php?type= ... =pvrtc_pvr](http://himeworks.com/redirect.php?type=noesis&name=pvrtc_pvr)
## Post #8
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2016-10-02T03:34:24+00:00
- Post Title: PSVita GXT PVTRC2 Problems

Thanks o0DemonBoy0o, this script is very useful
## Post #9
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-02T14:06:18+00:00
- Post Title: PSVita GXT PVTRC2 Problems

> http://himeworks.com/redirect.php?type= ... =pvrtc_pvr
thats the same script that comes with the Noesis installation
## Post #10
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2016-10-03T02:42:23+00:00
- Post Title: PSVita GXT PVTRC2 Problems

> Reply from AceWell
>
> http://himeworks.com/redirect.php?type= ... =pvrtc_pvr
thats the same script that comes with the Noesis installation

haha, many times the solutions are just around the corner, the problem is to know which corner. That's why is important the knowledge
## Post #11
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-17T22:15:59+00:00
- Post Title: PSVita GXT PVTRC2 Problems

this is the pvr script from finale00's old Dropbox repository


 tex_powerVR_pvr.zip
(1.02 KiB) Downloaded 71 times



he must have got them mixed up when he was rebuilding
the repository on his himeworks.com website
