## Post #1
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-06-07T17:20:42+00:00
- Post Title: Fable 2 (xbox360)

I upload [.bnk file (140mb)](http://www.sendspace.com/file/ziv8o0) with models from Fable 2. Can any one help in unpacking files from it. I'm very interesting in converting models from this beautiful game. Also i upload [small file](http://www.sendspace.com/file/phzkux).
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-06-07T17:51:15+00:00
- Post Title: Fable 2 (xbox360)

bnk is a video file normally.
## Post #3
- Username: firsak
- Rank: advanced
- Number of posts: 64
- Joined date: Wed Dec 16, 2009 7:32 pm
- Post datetime: 2010-06-07T18:12:13+00:00
- Post Title: Fable 2 (xbox360)

> Reply from chrrox
>
> bnk is a video file normally.
In this case it is not.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-06-07T19:47:40+00:00
- Post Title: Fable 2 (xbox360)

they are nameless zlib files just use 
offzip.exe -a file.bnk c:\extracted 0x0
## Post #5
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-06-07T20:42:42+00:00
- Post Title: Fable 2 (xbox360)

They are not nameless files. The filename tables are at the beginning of the file. (After the 17 bytes long header)
Here they are. (They are already unpacked.)


 name_tables.rar
(98.25 KiB) Downloaded 37 times
## Post #6
- Username: Tosyk
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-06-07T21:13:15+00:00
- Post Title: Fable 2 (xbox360)

ok ill make an extractor if no one beats me to it
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-06-07T21:40:47+00:00
- Post Title: Fable 2 (xbox360)

I can't get quickbms to extract the files i had the same problem with another game and offzip worked but quickbms did not.
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-06-08T07:51:33+00:00
- Post Title: Fable 2 (xbox360)

that can be the following things:
- you left the encryption/filexor/filerot mode activated (if you used it) and so the data was altered
- the data is not correctly compressed and in this case you can know it if offzip returns a warning after the extraction
- the ZSIZE or SIZE value doesn't match

you can bypass the second problem by using comtype "unzip_dynamic" or "zlib_noerror" or "deflate_noerror".
in all the various tests I have done in these monts only one thing is sure: if you receive a zlib error QuickBMS IS RIGHT :)
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-06-08T08:57:49+00:00
- Post Title: Fable 2 (xbox360)

yes i did get the zlib error where do i put the no error command on a new line?
## Post #10
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-06-08T09:06:32+00:00
- Post Title: Fable 2 (xbox360)

comtype zlib_noerror
## Post #11
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-06-08T10:26:29+00:00
- Post Title: Fable 2 (xbox360)

The compressed data files are split to 8000h bytes parts, so we have to ZLIB_decompress all parts!
(For example if the compressed size is 1DB41h, then there are 4 blocks, with block sizes: 8000h,8000h,8000h,5B41h.)
The final results must be combined together, but there is still some trick, because the sum of the unpacked data blocks
is less than the original size, which is stored in the file table.
## Post #12
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-06-09T06:53:40+00:00
- Post Title: Fable 2 (xbox360)

I try to use offzip for archives, but get fail.
## Post #13
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-06-09T08:06:21+00:00
- Post Title: Fable 2 (xbox360)

Here is a simple, work-in-progress version of my .BNK extractor.
There must be some problem with the big files, so please check the log file created in the extraction's target directory.
Most of the extracted files have unknown extension (.mdl, .bgf) so I don't know how to check if they are extracted correctly or not.
[bnk_eXtractor_v0_211.rar](https://xentaxbackup.github.io/file/3139_bnk_eXtractor_v0_211.rar)
## Post #14
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-06-09T15:04:07+00:00
- Post Title: Fable 2 (xbox360)

Big THANKS to bacter! Your tool work just great, at least with 2 archives:

1024mip0_textures.bnk - textures
globals_models.bnk - models

In that archives i find 2 types of files:

TEX - textures
MDL - models

[Here](http://fable2mod.com/forums/forum.php?req=thread&id=20) and [here](http://www.kxcad.net/Softimage_XSI/Softimage_XSI_Documentation/polys_ExtractingPolygons.htm) model description.

And about textures i can't find information anywhere. I try use rename those files in dds/tga, try open with dmc4tex and with megatool noesis, but TEX won't open. Below small samples of each format.

[TEX](http://www.sendspace.com/file/9g50mm) [MDL](http://www.sendspace.com/file/zqsy0t)

Thanks to firsak for help in searching information.

upd:
7zip tell me that TEX files use LZMA (LZMA:192k) compression method.
## Post #15
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-06-15T17:49:05+00:00
- Post Title: Fable 2 (xbox360)

Sorry for double post, but.. any news?
