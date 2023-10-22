## Post #1
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2018-02-05T06:22:58+00:00
- Post Title: UFC 2 big archives - PS4

Hi guys. I am trying to extract the files from the EA Sports UFC game from the ps4. Has anyone successfully extracted these or deciphered the format as yet?

If anyone has any information on how this archive format, I can code something to extract the files. I have attached two sample files where I've taken what looks like the header info, filenames and a bit of data. If anyone needs an entire big file for analysis, let me know and I'll upload it. 

Any assistance would be greatly appreciated.
[big samples.rar](https://xentaxbackup.github.io/file/13875_big samples.rar)
## Post #2
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2018-02-05T11:41:55+00:00
- Post Title: UFC 2 big archives - PS4

Made some progress. This is what I''ve figured out so far of the headers (see picture attached). I still can't figure out how the offsets and filesize are listed in the section highlighted in red. 

The archive also seems to consists of a number of compressed files with the header of "chunkzip." After some searching, I found a bms script which can decompress this archive. Decompressing some the of the files with quickbms has yielded files with an extension of "GNF" which looks like some sort of texture file upon inspection in a hex editor. The number of chunkzip files also do not correspond to the filenames listed in the filename listing. 

I can't seem to find a viewer for the file at present. The bytes kind of looks like a dds file. 

I think the bms script is also not extract all the files in the chunkzip file correctly as I'm only getting one decompressed file. I can post sample files if anyone wants to assist.
[ufc big format.jpg](https://xentaxbackup.github.io/file/13877_ufc big format.jpg)
## Post #3
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2018-02-05T23:39:26+00:00
- Post Title: UFC 2 big archives - PS4

Hi, it seems similar big-archive than EA's NHL games. I found Big-File-Extractor from Experiment5x here: [https://github.com/Experiment5X/BIG-Fil ... or?files=1](https://github.com/Experiment5X/BIG-File-Extractor?files=1)

In each file row first four bytes is file offset /0x10, next 4 bytes is compressed file size (Im not sure why this block is empty in most of files but so is it also in most of xbox 360 NHL Legacy files which are chunklzx format). Next four bytes is uncompressed file size (in this case size of chunkzip/chunklzx files) last 4 bytes in the row is file crc hash.
## Post #4
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2018-02-05T23:58:26+00:00
- Post Title: UFC 2 big archives - PS4

Bms script for nhl 13 .big archive founds here:
[viewtopic.php?f=13&p=79708#p79708](http://forum.xentax.com/viewtopic.php?f=13&p=79708#p79708)

Change comtype to deflate and "chunklzx" to "chunkzip" so it might be works in your file
## Post #5
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2018-02-06T06:24:11+00:00
- Post Title: UFC 2 big archives - PS4

Thank you, the bms script worked perfectly. The big file extractor didn't work at all, but I have extracted the files with the script. 

Now onto the model and texture format. I suppose I'll have to create a thread in the relevant sections. Here's the files for reference:

GNF Texture: [http://www19.zippyshare.com/v/Eb6icRWi/file.html](http://www19.zippyshare.com/v/Eb6icRWi/file.html)

MCD model: [http://www74.zippyshare.com/v/f2E614jW/file.html](http://www74.zippyshare.com/v/f2E614jW/file.html)
## Post #6
- Username: plodtrew
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-02-06T23:42:24+00:00
- Post Title: UFC 2 big archives - PS4

gnf texture is supported b noesis.
## Post #7
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2018-02-07T10:57:57+00:00
- Post Title: UFC 2 big archives - PS4

> Reply from chrrox
>
> gnf texture is supported b noesis.

Thank you. The diffuse and spec maps are supported, however the normal maps don't display correctly.
## Post #8
- Username: MarkGPlays
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 31, 2018 12:14 am
- Post datetime: 2021-03-26T13:13:16+00:00
- Post Title: UFC 2 big archives - PS4

Hey plodtrew and Beedy,

I know this is kinda reviving a old thread. But I tried to run the BMS script with a UFC 4 .big File and it seems like they f**ked with the offsets.



Is there any way you guys can point me into a direction to fix the offsets ?
## Post #9
- Username: 1476435277
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Mar 06, 2023 1:02 am
- Post datetime: 2023-03-05T17:08:36+00:00
- Post Title: UFC 2 big archives - PS4

bro，The UFC 2 texture link has expired.Can you share it again? Thank you!
## Post #10
- Username: goatmeatrice
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 15, 2022 7:57 pm
- Post datetime: 2023-05-08T00:32:22+00:00
- Post Title: UFC 2 big archives - PS4

> Reply from MarkGPlays ↑Fri Mar 26, 2021 9:13 pm at Fri Mar 26, 2021 9:13 pm
>
> 
Hey plodtrew and Beedy,

I know this is kinda reviving a old thread. But I tried to run the BMS script with a UFC 4 .big File and it seems like they f**ked with the offsets.



Is there any way you guys can point me into a direction to fix the offsets ?

Hey MarkGplays, I just figured out a way to extract textures from UFC 4. I've attached the 2 bms scripts needed and an example texture I extracted (Volkanovski). Open big files with the fightnight script. This will extract everything but the files will have a chunzstd idstring, meaning they still need to be decompressed further. So then you just run the rx3decompressor script on the extracted files. And that's it. Enjoy.

[https://drive.google.com/drive/folders/ ... lMUoSbbjg0](https://drive.google.com/drive/folders/17lpETZrn4WeAY7ALzhnJE0lMUoSbbjg0)
