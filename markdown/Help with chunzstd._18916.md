## Post #1
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2018-10-10T21:50:57+00:00
- Post Title: Help with chunzstd.

Friends, I've extracted FIFA 19 Nintendo switch and got chunzstd. compressed files. Is there anybody who can help me with this?

[https://www.mediafire.com/file/tw37qiwq ... s.rx3/file](https://www.mediafire.com/file/tw37qiwqx8l35rh/ball_0_textures.rx3/file)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-11T04:05:02+00:00
- Post Title: Help with chunzstd.

Here's a BMS decompressor for the zstd-compressed rx3 image container.


 RX3Decompressor.zip
v0.1.2 (520 Bytes) Downloaded 52 times


The pixel formats look weird so I didn't add the unpacking code.
## Post #3
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2018-10-11T15:20:36+00:00
- Post Title: Help with chunzstd.

> Reply from Bigchillghost
>
> Here's a BMS decompressor for the zstd-compressed rx3 image container.
RX3Decompressor.zip
The pixel formats look weird so I didn't add the unpacking code.

Works fine, but there is some difference. Can you take a look at this files
[https://www.mediafire.com/file/8is7iqa2](https://www.mediafire.com/file/8is7iqa2) ... s.rar/file
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-12T12:04:13+00:00
- Post Title: Help with chunzstd.

Always remember to format your URL with the corresponding BBCode tag.
## Post #5
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2019-03-06T21:57:43+00:00
- Post Title: Help with chunzstd.

Can you take a look buddy this file. I can decompress it with the rx3 decompressor. 
[https://www.mediafire.com/file/l23a41d2 ... s.rx3/file](https://www.mediafire.com/file/l23a41d28z1urzc/shoe_15_0_textures.rx3/file)
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-03-07T11:43:46+00:00
- Post Title: Help with chunzstd.

Well there's indeed a small issue in the code where the script trys to read past the end of the file. But QuickBMS didn't consider it an error? Might just be lucky. It's fixed now in [v0.1.2 script](https://forum.xentax.com/viewtopic.php?p=144910#p144910). 

> Reply from mita996 ↑Thu Mar 07, 2019 5:57 am at Thu Mar 07, 2019 5:57 am
>
> I can decompress it with the rx3 decompressor.
So what's the problem?
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-03-07T16:45:28+00:00
- Post Title: Help with chunzstd.

> Reply from mita996 ↑Thu Mar 07, 2019 5:57 am at Thu Mar 07, 2019 5:57 am
>
> 
Can you take a look buddy this file. I can decompress it with the rx3 decompressor. 
https://www.mediafire.com/file/l23a41d2 ... s.rx3/file
here is Noesis python script to open the decompressed rx3 file.  


 tex_FIFA19_Switch_rx3.zip
(918 Bytes) Downloaded 28 times


supports dxt1, dxt5 and ati2, top level mip only.
## Post #8
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2019-03-07T19:15:12+00:00
- Post Title: Help with chunzstd.

> Reply from Acewell ↑Fri Mar 08, 2019 12:45 am at Fri Mar 08, 2019 12:45 am
>
> 
mita996 wrote: ↑Thu Mar 07, 2019 5:57 am
Can you take a look buddy this file. I can decompress it with the rx3 decompressor. 
https://www.mediafire.com/file/l23a41d2 ... s.rx3/file

here is Noesis python script to open the decompressed rx3 file.   
tex_FIFA19_Switch_rx3.zip
supports dxt1, dxt5 and ati2, top level mip only.

Buddy, there is a strange thing, I've decompressed other fifa's like fo4, and the files are perfect (512 kb) for hair for example and the textures are bright. These files are 684, and they are shiny.
for example, the second image is the correct one, ignore resolution of the image: [https://i.postimg.cc/7Zmpd2tB/image.png](https://i.postimg.cc/7Zmpd2tB/image.png)
## Post #9
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2019-03-07T19:18:22+00:00
- Post Title: Help with chunzstd.

> Reply from Bigchillghost ↑Thu Mar 07, 2019 7:43 pm at Thu Mar 07, 2019 7:43 pm
>
> 
Well there's indeed a small issue in the code where the script trys to read past the end of the file. But QuickBMS didn't consider it an error? Might just be lucky. It's fixed now in v0.1.2 script. 
mita996 wrote: ↑Thu Mar 07, 2019 5:57 amI can decompress it with the rx3 decompressor.

So what's the problem?

Accidentaly, I made a mistake in tipping, I can't decompress, even with the updated script: 
- 0 files found in 0 seconds
  coverage file 0     0%   8          146611     . offset 00000008

Press ENTER or close the window to quit
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-03-07T23:09:58+00:00
- Post Title: Help with chunzstd.

> Reply from mita996 ↑Fri Mar 08, 2019 3:15 am at Fri Mar 08, 2019 3:15 am
>
> Buddy, there is a strange thing, I've decompressed other fifa's like fo4, and the files are perfect (512 kb) for hair for example and the textures are bright. These files are 684, and they are shiny.
for example, the second image is the correct one, ignore resolution of the image: https://i.postimg.cc/7Zmpd2tB/image.png
the one on the left is dxt5 likely with alpha layer and the one on right is dxt1 no alpha likely.
the dxt5 image is probably being displayed with the alpha layer overlay which dulls the look.   

also, the original rx3decompressor bms script decompressed both your samples in this thread fine,
make sure you using latest version of QuickBMS always.
## Post #11
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2019-03-08T08:18:45+00:00
- Post Title: Help with chunzstd.

> Reply from Acewell ↑Fri Mar 08, 2019 7:09 am at Fri Mar 08, 2019 7:09 am
>
> 
mita996 wrote: ↑Fri Mar 08, 2019 3:15 amBuddy, there is a strange thing, I've decompressed other fifa's like fo4, and the files are perfect (512 kb) for hair for example and the textures are bright. These files are 684, and they are shiny.
for example, the second image is the correct one, ignore resolution of the image: https://i.postimg.cc/7Zmpd2tB/image.png

the one on the left is dxt5 likely with alpha layer and the one on right is dxt no alpha likely.
the dxt5 image is probably being displayed with the alpha layer overlay which dulls the look.   

also, the original rx3decompressor bms script decompressed both your samples in this thread fine,
make sure you using latest version of QuickBMS always.
Thank you guys  . I was using old quickbms, that's why I got error. Is there a way how can I fix those alpha layers, so they look perfect and not dull?
## Post #12
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-03-08T11:34:35+00:00
- Post Title: Help with chunzstd.

> Reply from Acewell ↑Fri Mar 08, 2019 12:45 am at Fri Mar 08, 2019 12:45 am
>
> 
here is Noesis python script to open the decompressed rx3 file.
Nice work Ace!  

Alright this is made just for fun — or if anyone feels it helpful — an rx3 unpacker/convertor to pvr format preserving all mipmaps:


 RX3Unpacker.zip
(958 Bytes) Downloaded 27 times



Since BC5 encoded pvr images won't load by my PVRTexTool I'll save also the raw data as an rx3l file.
## Post #13
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2019-03-09T13:11:55+00:00
- Post Title: Help with chunzstd.

> Reply from Bigchillghost ↑Fri Mar 08, 2019 7:34 pm at Fri Mar 08, 2019 7:34 pm
>
> 
Acewell wrote: ↑Fri Mar 08, 2019 12:45 am
here is Noesis python script to open the decompressed rx3 file.

Nice work Ace!  

Alright this is made just for fun — or if anyone feels it helpful — an rx3 unpacker/convertor to pvr format preserving all mipmaps:
RX3Unpacker.zip


Since BC5 encoded pvr images won't load by my PVRTexTool I'll save also the raw data as an rx3l file.

Superb, does it means that can fix the dull textures, actully convert dxt5 to dxt1?
## Post #14
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-03-09T13:33:38+00:00
- Post Title: Help with chunzstd.

> Reply from mita996 ↑Sat Mar 09, 2019 9:11 pm at Sat Mar 09, 2019 9:11 pm
>
> Superb, does it means that can fix the dull textures
I don't have the texture file you're talking about. But the results of the two in this thread look fine to me.

> Reply from mita996 ↑Sat Mar 09, 2019 9:11 pm at Sat Mar 09, 2019 9:11 pm
>
> actully convert dxt5 to dxt1?
No, there's no actual convertion between different pixel formats. All data is taken from the file directly, but a pvr header is added.
## Post #15
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-03-09T16:58:11+00:00
- Post Title: Help with chunzstd.

and just because, here a rx3 to dds bms script.   
*script updated August 5, 2019*


 FIFA19_FIFAOnline4_rx3todds.zip
(1.04 KiB) Downloaded 44 times


the normal map (ATI2) dds files can be open in "[Compressonator](https://github.com/GPUOpen-Tools/Compressonator)" or "Noesis".  
supports chunzstd, chunkzip and chunlzma types


> Reply from mita996 ↑Sat Mar 09, 2019 9:11 pm at Sat Mar 09, 2019 9:11 pm
>
> does it means that can fix the dull textures, actully convert dxt5 to dxt1?
you can convert dxt5 to dxt1 easily with Photoshop and Nvidia's texture tools.
## Post #16
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2019-03-09T17:51:49+00:00
- Post Title: Re: Help with chunzstd.

You guys rocks. All the best!!!
## Post #17
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2019-07-02T20:27:42+00:00
- Post Title: Re: Help with chunzstd.

> Reply from Acewell ↑Sun Mar 10, 2019 12:58 am at Sun Mar 10, 2019 12:58 am
>
> 
and just because, here a rx3 to dds bms script.   
FIFA19_rx32dds.zip
the normal map (ATI2) dds files can be open in "Compressonator" or "Noesis".  

mita996 wrote: ↑Sat Mar 09, 2019 9:11 pmdoes it means that can fix the dull textures, actully convert dxt5 to dxt1?
you can convert dxt5 to dxt1 easily with Photoshop and Nvidia's texture tools.

I fixed first part of texture with ps, but the second part is a bit hard for me, even they are both dxt5, there are difference in brihtness, that makes hair a bit lighter. Here is a pic. The second part should be like on the first part of picture, what should I do. 
[http://oi67.tinypic.com/2ahacld.jpg](http://oi67.tinypic.com/2ahacld.jpg)
## Post #18
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2019-07-03T08:13:22+00:00
- Post Title: Re: Help with chunzstd.

Also @Acewell can you modify your fifa19 dds script, it works awesome with fifa19, but for fifa online 4 the compression is different, they used chunkzip
## Post #19
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-07-08T04:38:37+00:00
- Post Title: Re: Help with chunzstd.

> Reply from mita996 ↑Wed Jul 03, 2019 4:27 am at Wed Jul 03, 2019 4:27 am
>
> what should I do.
i don't know, modding is not my area, just keep trying.   

> Reply from mita996 ↑Wed Jul 03, 2019 4:13 pm at Wed Jul 03, 2019 4:13 pm
>
> 
Also @Acewell can you modify your fifa19 dds script, it works awesome with fifa19, but for fifa online 4 the compression is different, they used chunkzip
i need samples to examine.
## Post #20
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2019-07-08T14:53:22+00:00
- Post Title: Re: Help with chunzstd.

> Reply from Acewell ↑Mon Jul 08, 2019 12:38 pm at Mon Jul 08, 2019 12:38 pm
>
> 
mita996 wrote: ↑Wed Jul 03, 2019 4:27 amwhat should I do.
i don't know, modding is not my area, just keep trying.   
mita996 wrote: ↑Wed Jul 03, 2019 4:13 pm
Also @Acewell can you modify your fifa19 dds script, it works awesome with fifa19, but for fifa online 4 the compression is different, they used chunkzip
i need samples to examine.

The first one is face texture, the second are hair textures, for me it was unable to decompress hair_238380_0_textures, because: Can't read 2 bytes from offset 0003c54b..
[https://www.mediafire.com/file/3cx2ctn7 ... d.rar/file](https://www.mediafire.com/file/3cx2ctn76kqc289/Compressed.rar/file)
## Post #21
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-07-09T02:55:41+00:00
- Post Title: Re: Help with chunzstd.

> Reply from mita996 ↑Mon Jul 08, 2019 10:53 pm at Mon Jul 08, 2019 10:53 pm
>
> for me it was unable to decompress hair_238380_0_textures, because: Can't read 2 bytes from offset 0003c54b..
RX3Unpacker for FIFA Online 4.


 RX3Unpacker_FIFAO4.zip
(1.08 KiB) Downloaded 34 times



Here's your hair.
## Post #22
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2019-07-09T19:39:56+00:00
- Post Title: Re: Help with chunzstd.

> Reply from Bigchillghost ↑Tue Jul 09, 2019 10:55 am at Tue Jul 09, 2019 10:55 am
>
> 
mita996 wrote: ↑Mon Jul 08, 2019 10:53 pmfor me it was unable to decompress hair_238380_0_textures, because: Can't read 2 bytes from offset 0003c54b..

RX3Unpacker for FIFA Online 4.
RX3Unpacker_FIFAO4.zip


Here's your hair.
Thanks mate. I've realized that decomprossed file wasn't complete, because some offsets were missing, I added them with Hxd and it works fine now. Thank you for help!!!
## Post #23
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-07-10T08:00:23+00:00
- Post Title: Re: Help with chunzstd.

i updated the rx3 to dds bms script here for chunkzip support.  
[viewtopic.php?f=10&t=18916&p=149279#p149279](https://forum.xentax.com/viewtopic.php?f=10&t=18916&p=149279#p149279)

your hair_238380_0_textures.rx3 sample must be corrupt because is missing 2 bytes 
at the end and does not work with the given size stored in the file.
## Post #24
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2019-07-21T08:50:44+00:00
- Post Title: Re: Help with chunzstd.

> Reply from Acewell ↑Wed Jul 10, 2019 4:00 pm at Wed Jul 10, 2019 4:00 pm
>
> 
i updated the rx3 to dds bms script here for chunkzip support.  
viewtopic.php?f=10&t=18916&p=149279#p149279

your hair_238380_0_textures.rx3 sample must be corrupt because is missing 2 bytes 
at the end and does not work with the given size stored in the file.

Thaaaanks!!!
## Post #25
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2019-08-05T09:19:14+00:00
- Post Title: Re: Help with chunzstd.

> Reply from Acewell ↑Sun Mar 10, 2019 12:58 am at Sun Mar 10, 2019 12:58 am
>
> 
and just because, here a rx3 to dds bms script.   
*script updated July 10, 2019*
FIFA19_FIFAOnline4_rx3todds.zip
the normal map (ATI2) dds files can be open in "Compressonator" or "Noesis".  

mita996 wrote: ↑Sat Mar 09, 2019 9:11 pmdoes it means that can fix the dull textures, actully convert dxt5 to dxt1?
you can convert dxt5 to dxt1 easily with Photoshop and Nvidia's texture tools.

I ran into kit files, while exporting fifa online 4, and they are having different compression, chunlzma, can you make fo4 chunlzma dds script for kits, I think that chunlzma is last compression fo4 fifa online 4. Thanks in advance   
[https://www.mediafire.com/file/hnawz2sa ... 0.chu/file](https://www.mediafire.com/file/hnawz2saf6t55u9/00000000.chu/file)
## Post #26
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-08-06T00:19:06+00:00
- Post Title: Re: Help with chunzstd.

okay updated the rx3 to dds bms script here for chunlzma support.  
[viewtopic.php?f=10&t=18916&p=149279#p149279](https://forum.xentax.com/viewtopic.php?f=10&t=18916&p=149279#p149279)
## Post #27
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2019-08-06T09:30:54+00:00
- Post Title: Re: Help with chunzstd.

> Reply from Acewell ↑Tue Aug 06, 2019 8:19 am at Tue Aug 06, 2019 8:19 am
>
> 
okay updated the rx3 to dds bms script here for chunlzma support.  
viewtopic.php?f=10&t=18916&p=149279#p149279

Thanks master, but some of them can't be exported, it gives an error:  incomplete input file -1:
       Can't read 1438513646 bytes from offset 008e08e2.
       Anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted.
       Please check the following coverage information to know if it's ok.

  coverage file -1  100%   9316347    9308386    . offset 008e08e2

Last script line before the error or that produced the error:
  114 log NAME OFFSET SIZE -1
here is the sample of the file, that can be fully exported 
[https://www.mediafire.com/file/8tjj7ipd ... e.chu/file](https://www.mediafire.com/file/8tjj7ipdlzjzj4e/000000de.chu/file)
I've decompressed the file, maybe it will be easier for you to make script according to decompressed files, here is the sample:
[https://www.mediafire.com/file/aa3yfyj7 ... a.rx3/file](https://www.mediafire.com/file/aa3yfyj7p8jhorq/0000000a.rx3/file)
## Post #28
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-08-11T08:08:13+00:00
- Post Title: Re: Help with chunzstd.

for some reason there is an extra 2 bytes in the decompressed rx3,   
i don't know why, all i can say is upload more non working samples and a 
solution might be found at some point down the road.
## Post #29
- Username: mita996
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Oct 11, 2018 5:45 am
- Post datetime: 2019-08-13T04:27:25+00:00
- Post Title: Re: Help with chunzstd.

> Reply from Acewell ↑Sun Aug 11, 2019 4:08 pm at Sun Aug 11, 2019 4:08 pm
>
> 
for some reason there is an extra 2 bytes in the decompressed rx3,   
i don't know why, all i can say is upload more non working samples and a 
solution might be found at some point down the road.

It do the job. I have to do manually some files, but I'm satisfied. Thanks master
