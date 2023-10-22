## Post #1
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2012-09-01T13:45:36+00:00
- Post Title: Final Fantasy IV Complete Collection PSP (.BIN)

Hello.

I was wondering if anyone could look into the file format for FF4PSP:

The BIN files are large archives of all the files in the game. There seems to be two types of BIN archives.

In the "USRDIR" folder there is a:
PAC0.BIN (119K) & PAC1.BIN (~300MB)
The PAC0.BIN seems to store the file offsets and filenames for the files contained in the PAC1.BIN

In the "INSDIR" folder there is simply:
PAC1.BIN (~300MB)
This is the only file. It is in a different format than the PAC1.BIN in "USRDIR" and does not have the filenames and file offsets stored in a different file.

Any help would be greatly appreciated.
Thanks,
Andy
## Post #2
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2012-09-03T15:49:47+00:00
- Post Title: Final Fantasy IV Complete Collection PSP (.BIN)

Here is a link to download the files themselves. The original files (with an exception of PAC0.bin which is 119K) I shrank down from ~300MB to about ~10MB for examination purposes if people don't have the game.

```

```
## Post #3
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-09-04T08:30:13+00:00
- Post Title: Final Fantasy IV Complete Collection PSP (.BIN)

here:
[https://www.dropbox.com/s/xul2fd40qk24wt7/FF4_unpac.rar](https://www.dropbox.com/s/xul2fd40qk24wt7/FF4_unpac.rar)
[https://www.dropbox.com/s/1c1tkbz1zwok7hb/FF4_pac.rar](https://www.dropbox.com/s/1c1tkbz1zwok7hb/FF4_pac.rar)
## Post #4
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2012-09-04T15:53:58+00:00
- Post Title: Final Fantasy IV Complete Collection PSP (.BIN)

THAN YOU VERY MUCH FOR FINDING THAT!!! (It doesn't seem to open the PAC1.BIN that stands in its own directory without the PAC0.BIN file - but this seems to be all the files I need, so I'm not sure what that other BIN is for, but it is ~300MB, so I would still be interested).

When that program extracts the files, it outputs many files that are .LZS. I ran some simple programs and none of these files are compressed, just archives. It seems it would be easy to extract the files from there. Here is a sample -- the data seems that it would be VERY simple to write a program to open the LZS. So if anyone can, it would save me the time of extracting each file individually from the archive.

(I have uploaded a sample).

```

```


Thanks again,
Andy
## Post #5
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-09-04T16:33:52+00:00
- Post Title: Final Fantasy IV Complete Collection PSP (.BIN)

I wrote this tools, I know how does it work. The PAC1.BIN is just the same as PAC0.BIN but it's installed (with the original game).
Those files are already decompressed and .lzs is a pretty standard extension in that game...
## Post #6
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2012-09-04T20:42:54+00:00
- Post Title: Final Fantasy IV Complete Collection PSP (.BIN)

Thanks for the answer.

LZS is another type of archive (though the LZS are not compressed). They also contain files. 

For example, the CN_ancient_waterway.lzs that I linked to above is an uncompressed archive, containing TIM2 and other files, which would should not be difficult to make an extractor for that type of archive since it is an uncompressed archive.

Now there are other lzs that seem to be more interesting (which are the ones that are probably the enemy images which I would be the most interested in obtaining):

```
http://www.thezorklibrary.com/history/temp/ms_012.lzs
```


This seems to be either a TIM2 file within an uncompressed LZS OR,
a TIM2 file within a compressed LZTX file within an uncompressed LZS file, OR
a TIM2 file compressed with LZTX file compressed within an uncompressed LZS file.

There are two types of TIM2 files. Some do NOT have the LZTX -- these I am able to view. But others (like the ones in ms_012.lzs) with the LZTX in the archive I am not able to view. So I think the LZTX is some sort of compression. But why some are compressed with LZTX and others not, I have no idea. But both are contained within the LZS archives.

Thanks,
Andy
## Post #7
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-09-05T07:50:01+00:00
- Post Title: Final Fantasy IV Complete Collection PSP (.BIN)

the files are already decompressed during the extraction. The images you can't see are simply swizzled. And I repeat, .SLZ is a common extension for all those files, there is no standard format...
## Post #8
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2012-09-05T13:31:10+00:00
- Post Title: Final Fantasy IV Complete Collection PSP (.BIN)

Did you find a way to be able to view the monster images? (Such as in ms_012.lzs?)
## Post #9
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-09-05T13:36:34+00:00
- Post Title: Final Fantasy IV Complete Collection PSP (.BIN)

Sorry, I wasn't interested in that...there are though some info on the net

[http://forums.ps2dev.org/viewtopic.php? ... 150739f69c](http://forums.ps2dev.org/viewtopic.php?p=22600&sid=be63284c9d66b66b1f86f7150739f69c)
## Post #10
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2012-09-05T14:58:37+00:00
- Post Title: Final Fantasy IV Complete Collection PSP (.BIN)

Thanks. I will look into that.

But what I found was this:

All that is on the disc is pac0.bin & pac1.bin. 
Pac0.bin is the index to determine the offsets and names for the files contained in pac1.bin.
Your program unpacked pac1.bin into thousands of files. 
Within those files are AT3 files and LZS files.
    AT3 files are common PSP audio format taht can easily be played.
    LZS is an archive format that contains many other files -- luckily this archive format does not use compression
    (So we basically have a bunch of archive files within a single archive file -- for example, it would be similar to having a bunch of RAR files within a single ZIP file).

Within each LZS file there are many other files, including TIM2 image files (such as with the first lzs file I posted), which is a standard image format that can easily be viewed with something like Game Graphic Studio. Now Game Graphic Studio is able to search one of these LZS files and find them inside. But all it is able to find is uncompressed (or uncoded) TIM2 files. Unfortunately, there is a combination of both uncompressed TIM2 files, and TIM2 files that seem to be compressed/encoded with some LZTX format (the ms_12.lzs is an example of this, an archive which contains but one TIM2 image, but it is compressed/encoded. I can easily view all the uncompressed TIM2 files by running Game Graphic Studio on each LZS file one by one.

However, it would be better if there was a program that could unpack the LZS archive. Since the LZS does not use any sort of compression method whatever, this should be easy. When you open an LZS in a hex editor, you can easily see each file name and the file's offset. (If I knew how to write code, I would easily write one myself, because this is one of the most simple archive methods I have ever seen with LZS). Then the next step after that, would be to find something that can read the compressed (or encoded) TIM2 files with the LZTX format.

I hope that makes more sense. If you can't help, that is fine. I am just trying to be as detailed about my request as possible. And I definitely thank you for your program, because that at least solved the first step with the original bin file.

Thanks,
Andy
## Post #11
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2012-09-07T14:51:38+00:00
- Post Title: Final Fantasy IV Complete Collection PSP (.BIN)

Hello.

Is there someone who is willing to write a code to extract the LZS archives it would be VERY easy? Here is an example:

```

```


For the above file:

BYTES 0-1 (only in the first file) is the number of files in the archive.

Then, the format for naming and finding the first file is:
BYTES 2~3 (unknown, but usually 0003, not sure what this does, but doesn't seem necessary for file extraction)
BYTES 4~7 offset for first file (00000440)
BYTES 8~B length of first file (00040440)
BYTES C~D file number of first file (0000)
BYTES 10~30 file name of first file (cave1_c_base.tm2)

Then file #2 starts at 40
BYTES 42~43 unknown (0003)
BYTES 44~47 offset for second file (00040880)
BYTES 48~4B length of first file (00040440)
BYTES C~D file number of first file (0001)
BYTES 10~30 file name of first file (cave1_c_var.tm2)

ETC...


Thanks for the time,
And
## Post #12
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-09-07T15:18:39+00:00
- Post Title: Final Fantasy IV Complete Collection PSP (.BIN)

why don't you just use TexER ([http://www.romhacking.net/utilities/659/](http://www.romhacking.net/utilities/659/))?

just do like this:

-Extract the archive
-Make a big rar file with NO COMPRESSION
-Use TextER on the rar with -gim and -tm parameters


Like this you will have 3 folders filled with the raw images extracted...
## Post #13
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2012-09-07T16:03:57+00:00
- Post Title: Final Fantasy IV Complete Collection PSP (.BIN)

> Reply from Vash
>
> why don't you just use TexER (http://www.romhacking.net/utilities/659/)?

just do like this:

-Extract the archive
-Make a big rar file with NO COMPRESSION
-Use TextER on the rar with -gim and -tm parameters


Like this you will have 3 folders filled with the raw images extracted...

Your program works if I want a certain type of TIM2 file (which happen to be in that particular LZS archive: CN_ancient_waterway.lzs -- the map tilesets all use the common TIM2 format). But there are two things: 

#1: That program will only extract Tim2 files, whereas I want ALL of the files extracted, regardless what format they are in.
#2: FF4 uses two types of TIM2 files -- some which common programs can view, and others (especially the monsters and NPCs) which I am unable to find any current program capable of viewing. I will be requesting some help on viewing that format, but it would be much easier to have people try to figure out the file format for the unknown type of TIM2 files if they could all be independently extracted.
#3: Your program does not preserve the original file names, which a simple LZS extractor would be able to do so that I do not have to manually rename each one.

For example, there are 20 TIM2 files in the following LZS archive (CN_agart_village_char.lzs). 19 of them are of unknown type, whereas only ONE is of the regular TIM2 format which can be viewed (or extracted with your program -- your program will NOT extract 19 of the TIM2 files from the following LZS archive - only ONE). And it cannot find the single TIM2 file in the MS_012.lzs:

```
http://www.thezorklibrary.com/history/temp/ms_012.lzs

```


It would be great to be able to get some of these file formats figured out for this game for future mods.
Thanks again,
Andy
## Post #14
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-09-07T16:17:05+00:00
- Post Title: Final Fantasy IV Complete Collection PSP (.BIN)

oh, ok, I thought you just wanted some images for whatever purpose (and I thought that even if the tim2 are swizzled the rest of the format was the same, I was wrong apparently).

Since it's a simple task why don't you take the chance to learn something about programming? You can easily read something about BMS Scripting right here on this forum
## Post #15
- Username: aspire
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Sep 09, 2012 11:28 pm
- Post datetime: 2012-09-09T19:21:16+00:00
- Post Title: Final Fantasy IV Complete Collection PSP (.BIN)

Here is a quick program to unpack all the LZS files. Source included. C#/.NET 4.0

[http://netload.in/dateisGlaHamsdv/FF4_L ... ct.rar.htm](http://netload.in/dateisGlaHamsdv/FF4_LZSExtract.rar.htm)

1. Extract FF4 ISO
2. Use VASH's tool to unpack pac0.bin and pac1.bin
3. Use above tool to dump all files within LZS archive. Place binary in parent directory (USRDIR) and execute

I also found out there are some LZS archives which contain LZS files. The format of these files can be different too. Thus, the tool works great the first time, but it may fail on the second run, since it will pick up the newly extracted LZS files with non-standard format.

Anyone have any info on the LZTX format? Vash how did you figure out pac0.bin and pac1.bin? Can you share source or point me in the right direction?

Aspire
## Post #16
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-09-09T19:27:32+00:00
- Post Title: Re: Final Fantasy IV Complete Collection PSP (.BIN)

it's standard LZSS
## Post #17
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2012-09-11T00:06:29+00:00
- Post Title: Re: Final Fantasy IV Complete Collection PSP (.BIN)

> Reply from aspire
>
> Here is a quick program to unpack all the LZS files. Source included. C#/.NET 4.0

http://netload.in/dateisGlaHamsdv/FF4_L ... ct.rar.htm

1. Extract FF4 ISO
2. Use VASH's tool to unpack pac0.bin and pac1.bin
3. Use above tool to dump all files within LZS archive. Place binary in parent directory (USRDIR) and execute

I also found out there are some LZS archives which contain LZS files. The format of these files can be different too. Thus, the tool works great the first time, but it may fail on the second run, since it will pick up the newly extracted LZS files with non-standard format.

Anyone have any info on the LZTX format? Vash how did you figure out pac0.bin and pac1.bin? Can you share source or point me in the right direction?

Aspire


Thanks for the program! Definitely let me know if you figure out the LZTX compression format for the other TM2 files (seems to primarily be used for the monster and char sprites).
## Post #18
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2012-09-13T22:56:29+00:00
- Post Title: Re: Final Fantasy IV Complete Collection PSP (.BIN)

I found two TM2 files in different directories with the same name -- one is a LZTX compressed version and one is an uncompressed version. I imagine that the compression method could be examined from comparing the two versions of the files.

```

```


~Andy
## Post #19
- Username: aspire
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Sep 09, 2012 11:28 pm
- Post datetime: 2012-09-14T00:43:23+00:00
- Post Title: Re: Final Fantasy IV Complete Collection PSP (.BIN)

Ok I will take a look. Thanks

Also, I noticed a few TM2 (non-LZTX) are not rendering in game graphic studio. It appears this software doesnt like TM2 files higher than 256 color.
The TM2 files that fail to load are easily identifiable. Just goto to offset 0x15 and if the byte is 0C, it wont load. If you change this byte to 04 (256 color), then it loads fine but the colors are missing.. The character portraits in MENU/MENU_COMMON_4 are an example of this...

Aspire
## Post #20
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2012-09-14T02:02:30+00:00
- Post Title: Re: Final Fantasy IV Complete Collection PSP (.BIN)

> Reply from aspire
>
> 
Also, I noticed a few TM2 (non-LZTX) are not rendering in game graphic studio. It appears this software doesnt like TM2 files higher than 256 color.
The TM2 files that fail to load are easily identifiable. Just goto to offset 0x15 and if the byte is 0C, it wont load. If you change this byte to 04 (256 color), then it loads fine but the colors are missing.. The character portraits in MENU/MENU_COMMON_4 are an example of this...

Aspire

That's not the problem. The problem is that those particular TM2 files contain multiple palettes. If you load both the image as both image and palette in TILEDGGD, then you can change the palettes. Any file that did not load properly, I noticed had multiple palettes.


Also, I noticed that the summons were not compressed. And some of the summons are also enemies. I am assuming that the graphics were the same (and checking the data I see the same bytes within). So try to compare the following files for the Mind Flayer summon:

The "ec" is the summon (uncompressed) and the other two are the enemies (the TM2 and lzs are almost exactly the same, but that is how they both extract from different folders (one with a few less header info)

```

```


(I am also surprised at how many files have multiple copies within the data -- they could have saved much more room when removing them and also less programming)

Andy
## Post #21
- Username: aspire
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Sep 09, 2012 11:28 pm
- Post datetime: 2012-09-14T02:40:30+00:00
- Post Title: Re: Final Fantasy IV Complete Collection PSP (.BIN)

Got it! The LZTX format is standard LZSS and decompression starts at offset 0x08. I will update my tool shortly.

Here is what 0_bchara_ta_00.tm2 looks like decompressed...
## Post #22
- Username: aspire
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Sep 09, 2012 11:28 pm
- Post datetime: 2012-09-14T04:34:58+00:00
- Post Title: Re: Final Fantasy IV Complete Collection PSP (.BIN)

And here it is:

[http://netload.in/dateierCXU2KrhE/FF4LZ ... ck.rar.htm](http://netload.in/dateierCXU2KrhE/FF4LZTX_unpack.rar.htm)
## Post #23
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2012-09-14T14:28:12+00:00
- Post Title: Re: Final Fantasy IV Complete Collection PSP (.BIN)

Great that you figured it out!

Problem with the program:

You have to have all the images in the exact same directory as on your original computer in order for it to work (the program tries to read from a different directory). And when I put all the files in there, it still doesn't work an only does the first file for some reason.

Also, it doesn't work on those .LZS monster images -- the ones where the first 4 bytes of the file are not in there (the LZTX header). I could manually edit that, but it would take a long time for each image.

Thanks,
Andy
## Post #24
- Username: aspire
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Sep 09, 2012 11:28 pm
- Post datetime: 2012-09-14T17:04:00+00:00
- Post Title: Re: Final Fantasy IV Complete Collection PSP (.BIN)

ugh sorry... It was late and I forgot to change the hardcoded directory. I have uploaded a new version. 

You should be able to execute this now in any directory and it will traverse down.

[http://netload.in/dateiHp7hYbkYMS/FF4LZ ... ck.rar.htm](http://netload.in/dateiHp7hYbkYMS/FF4LZTX_Unpack.rar.htm)

This program currently only deals with LZTX on TM2 files. I can make it work with others, but I dont have the FF4 ISO extract files in front of me at the moment. Will get to that later.

Aspire
## Post #25
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2012-09-14T22:31:42+00:00
- Post Title: Re: Final Fantasy IV Complete Collection PSP (.BIN)

Thanks for the update.

If you look at the files that I have in the MindFlayer.rar that I put in a previous post -- you can see that most of the LZS monster images are exactly the same as the normal TM2 version (some are even saved as both) but the LZS monster images are really just a TM2 file missing LZTX at the beginning of the file...

Andy
## Post #26
- Username: aspire
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Sep 09, 2012 11:28 pm
- Post datetime: 2012-09-17T03:29:45+00:00
- Post Title: Re: Final Fantasy IV Complete Collection PSP (.BIN)

Here you go:

[http://netload.in/dateiit9Er8vMgS/FF4LZ ... ck.rar.htm](http://netload.in/dateiit9Er8vMgS/FF4LZTX_unpack.rar.htm)

This version will decompress LZTX (LZSS) encoded TM2 and LSZ files. The header is different for both and so is the decompression offset (weird). The LZS files when decompressed are saved as a TM2 file. Run at parent directory.

Aspire
## Post #27
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2012-09-18T06:20:50+00:00
- Post Title: Re: Final Fantasy IV Complete Collection PSP (.BIN)

The compression for the LZS might be slightly different than with the regular files -- because when I load the decompressed LZS monster images, the palettes are slightly off-color. There is no problem with this with the regular decompressed TM2.

~Andy
## Post #28
- Username: aspire
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Sep 09, 2012 11:28 pm
- Post datetime: 2012-09-18T13:44:37+00:00
- Post Title: Re: Final Fantasy IV Complete Collection PSP (.BIN)

I noticed this too. I can't see it being the decompression though.. every file compressed in the FF4 archive appears to use standard LZSS. It would be strange to deviate but possible I guess...  Could it be that these TM2 files are swizzled?

I will play around with it more tonight.
