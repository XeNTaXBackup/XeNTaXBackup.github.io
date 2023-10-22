## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-12-04T12:35:07+00:00
- Post Title: Star Wars: The Clone Wars - Repulic Heroes *.rkv

Hello there! Here's a quite easy task: [http://www.sendspace.com/file/3kt8dy](http://www.sendspace.com/file/3kt8dy). I took the smallest one of the containers. This is from the PSP version.

At the end of the file you'll find a file list, an offset table and a folder allocation (I'd only take the last folder as a subfolder to create as the full structure is as well unknown and unimportant). I guess it's quite easy to write a little BMS script. I'm currently learning BMS and I'm still having trouble writing my own scripts. 

Thanks to the voluntary!
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-04T13:58:52+00:00
- Post Title: Star Wars: The Clone Wars - Repulic Heroes *.rkv

*edit* updated script

```

idstring "RKV2"
get FILES long
get NAME_SIZE long
get FULLNAME_FILES long
get DUMMY long
get INFO_OFF long               # 0x2ac9a00
get DUMMY long

math NAME_OFF = FILES
math NAME_OFF *= 20
math NAME_OFF += INFO_OFF       # 0x2adb2dd

math INFO2_OFF = NAME_OFF
math INFO2_OFF += NAME_SIZE     # 0x2af0394

math FULLNAME_OFF = FILES
math FULLNAME_OFF *= 16
math FULLNAME_OFF += INFO2_OFf  # 0x2AFE444

for i = 0 < FILES
    goto INFO_OFF
    get NAMEOFF long
    get DUMMY long
    get SIZE long
    get OFFSET long
    get CRC long
    savepos INFO_OFF

    math NAMEOFF += NAME_OFF    # use FULLNAME_OFF if you like
    goto NAMEOFF
    get NAME string

    log NAME OFFSET SIZE
next i
```
*updated* script
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-12-04T14:36:02+00:00
- Post Title: Star Wars: The Clone Wars - Repulic Heroes *.rkv

You'll have to double-check the code with this archive: [http://www.sendspace.com/file/4u7v0i](http://www.sendspace.com/file/4u7v0i) 

Thanks! 

P.S.: And again, 7zip rules with a compression down to 23%!
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-04T15:11:47+00:00
- Post Title: Star Wars: The Clone Wars - Repulic Heroes *.rkv

ih ih ih exactly as I guessed :)
that ZSIZE field meant something else, I have edited the previous script
## Post #5
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-12-04T15:32:12+00:00
- Post Title: Star Wars: The Clone Wars - Repulic Heroes *.rkv

Thanks, works perfectly. However I have a little additional request: partly restore the folder structure. 
The folders at the end of each rkv file start with "D:\projects\cw09-lg\branches\PSPTrunk\Data\RKVs\..\[sometimes some other folder]\..\". With 'partly' I mean the folder structure directly after the last of the "\..\". 
If it's not too much to ask for, could you update the script one last time?  
Hopefully I'll learn BMS quickly so you won't have to bother with so many requests anymore. 
As always, huge thanks!
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-04T15:48:33+00:00
- Post Title: Star Wars: The Clone Wars - Repulic Heroes *.rkv

the problem is that in the second archive those filenames are less than the available files and so they can't be used.
## Post #7
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2009-12-04T20:08:44+00:00
- Post Title: Star Wars: The Clone Wars - Repulic Heroes *.rkv

AlphaTwentyThree: You can try this site for conlose requests: [http://www.alucard.cc/](http://www.alucard.cc/)
eg rkv plugin for  Xpert is already exist.
## Post #8
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-12-05T01:07:37+00:00
- Post Title: Star Wars: The Clone Wars - Repulic Heroes *.rkv

> Reply from aluigi
>
> the problem is that in the second archive those filenames are less than the available files and so they can't be used.
Ah ok, in this case it's indeed not possible. 
Thanks. =)
## Post #9
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2009-12-16T23:45:44+00:00
- Post Title: Star Wars: The Clone Wars - Repulic Heroes *.rkv

My attempts to use this bms script to unpack the 3.21GB common_d9.rkv archive for the PC version of this game have been unsuccessful.
Even though 3dRipperDX 1.6rc3 can rip the models and textures from this game it would be great if aluigi or anyone with the knowledge could analyze this FileCutter sample and find a solution to unpack it: 

*attachment removed*

I found a tool that unpacks SWRH rkv files ...... but it can't handle files larger than 2GB.  
[http://my.opera.com/JackJ2M/blog/2009/1 ... rs-clone-3](http://my.opera.com/JackJ2M/blog/2009/10/23/extarct-files-from-rkv-file-star-wars-clone-3)
## Post #10
- Username: Zerovisibilite
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jun 13, 2010 9:41 am
- Post datetime: 2010-06-13T11:21:22+00:00
- Post Title: Star Wars: The Clone Wars - Repulic Heroes *.rkv

I have an extractor that I wrote for this. it uses a System file handler so It can do large files up to 4gb(due to the constraints of the unsigned long i'm using in the code which would be easily remedied should the need arise.)Works with both Xbox360 and PC

However, the files form the Xbox and PC seem to be compressed. I admittedly know very little about compression and the look of it inside a file. In the mdl and mdg files I would expect a mass of Floats then a group of shorts progressively increasing to the max vert number. I'm not seeing any of that. If anyone would be interested in taking a look at the files I would love the help with the decompression
## Post #11
- Username: Zerovisibilite
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jun 13, 2010 9:41 am
- Post datetime: 2010-06-14T13:52:46+00:00
- Post Title: Star Wars: The Clone Wars - Repulic Heroes *.rkv

This will work with the large file Common_d9.rkv(PC) and the common_x3.rkv(xbox360) files, And all smaller files as well

Please let me know if it has any dll issues as i'm not making an installer for it, just the exe. The model files i would like to break are in the common file. if anyone can take a look at it and see what you can do, i would appreciate it. I have been staring at hex chr for 4 weeks now and am literally exhausted from it.

Thanks in advance
[CWRHRkvExtractor.rar](https://xentaxbackup.github.io/file/3141_CWRHRkvExtractor.rar)
## Post #12
- Username: psych0fred
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 02, 2010 7:37 am
- Post datetime: 2010-09-02T01:57:30+00:00
- Post Title: Star Wars: The Clone Wars - Repulic Heroes *.rkv

> Reply from Zerovisibilite
>
> This will work with the large file Common_d9.rkv(PC) and the common_x3.rkv(xbox360) files, And all smaller files as well

Please let me know if it has any dll issues as i'm not making an installer for it, just the exe.

COMDLG32.OCX is needed to run the program, so I just copied it to the same folder and it worked.  (I had a copy)
I see the PNG.raw files can be renamed and work, so that's a good sign. Still have not had luck with the PC or the PSP models though.
## Post #13
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2010-09-23T14:10:35+00:00
- Post Title: Star Wars: The Clone Wars - Repulic Heroes *.rkv

> Reply from Zerovisibilite
>
> This will work with the large file Common_d9.rkv(PC) and the common_x3.rkv(xbox360) files, And all smaller files as well

Please let me know if it has any dll issues as i'm not making an installer for it, just the exe. The model files i would like to break are in the common file. if anyone can take a look at it and see what you can do, i would appreciate it. I have been staring at hex chr for 4 weeks now and am literally exhausted from it.

Thanks in advance

The program also works with Blade Kitten.
Anyone knows how to open/convert all the .min.bin , .ast.ads , .mktx.tex files and so on?
## Post #14
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-09-25T18:50:53+00:00
- Post Title: Star Wars: The Clone Wars - Repulic Heroes *.rkv

[http://aluigi.org/papers/bms/rkv.bms](http://aluigi.org/papers/bms/rkv.bms)
supports also the compressed files and files till 4 gigabytes
## Post #15
- Username: Zerovisibilite
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jun 13, 2010 9:41 am
- Post datetime: 2010-09-26T13:36:53+00:00
- Post Title: Star Wars: The Clone Wars - Repulic Heroes *.rkv

Works Great, thank you. I knew the second "size" was the decompressed size but had no clue how to go from there. This is a big load off my back as I have been stewing over it for months now in the back of my mind. THANK YOU
## Post #16
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-09-26T16:40:25+00:00
- Post Title: Re: Star Wars: The Clone Wars - Repulic Heroes *.rkv

would be cool to know also what algorithm is type 1.
in short in the binary x86 code that handles the compressed files (GameRoom was my "subject") there is only support for type 2 (lzf) which means that any other value is considered an error and being the rkv files part of a library (M$ Live stuff) that should be the same for any program/game that uses this container format.

the lack of the handling of type 1 makes me thinking to something non-pc related like, for example, the XMemDecompress algorithm used on X360, so would be cool to find a rkv archive that uses this method 1 compression and confirming or not my guess (other than implementing it obviously eh eh eh).
so let me know if rkv.bms works also with the x360 files.

in case someone is interested/curious I would like to show you how I found that the algorithm was lzf because in my opinion it could be funny and takes only 1 minute.
obviously the first step was the finding of the function that does the compression in the program that I was debugging so the usual "breakpoints-job" that I skip here.

when I found the code I noticed that the first byte (0x02) was non-compression related and the real compression algorithm was very simple so I used the comtype_scan2 way, the same way that obviously I used with the compressed file before debuggin the program but didn't work due to this 0x02 byte.

in short:
comtype_scan2.bat comtype_scan2.bms raw_compressed_file.dat output_folder uncompressed_size

where:
- raw_compressed_file.dat is the compressed file without the first byte
- uncompressed_size is the SIZE field that we find in the informations about the file.

then it's enough to enter in the output_folder and finding all the files that have the same size of the uncompressed_size value.
open them with a hex editor and you will notice that our file is 67.dmp which is lzf (it's enough to look at that number in quickbms.c)

really easy :)

the reference thread about this method and the links to the files is [viewtopic.php?p=37412#p37412](http://forum.xentax.com/viewtopic.php?p=37412#p37412)

hope it helps and moreover will save your time in future.
note that comtype_scan2.bat has a runtime help so it's really a joke to use it and it's not needed to "remember" how to use it.
## Post #17
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2010-10-03T04:24:13+00:00
- Post Title: Re: Star Wars: The Clone Wars - Repulic Heroes *.rkv

> Reply from Zerovisibilite
>
> The model files i would like to break are in the common file. if anyone can take a look at it and see what you can do, i would appreciate it.

> Reply from psych0fred
>
> I see the PNG.raw files can be renamed and work, so that's a good sign. Still have not had luck with the PC or the PSP models though.
chrrox figured out [Blade Kitten's mdg files](http://forum.xentax.com/viewtopic.php?f=16&t=5098) which should be nearly the same as the ones extracted from Republic Heroes. I tried his max script on the RH mdg files but it didn't work or maybe the script doesn't work with 3ds Max 9 i don't know. 

Here's a bit of info on Krome Studio's mdg file structure, it is for another game of theirs but it should still be useful:
[http://ps23dformat.wikispaces.com/Legen ... yro+Series](http://ps23dformat.wikispaces.com/Legend+of+Spyro+Series)

NullARC created a thread about SWRH mdg files also:
[viewtopic.php?f=16&t=5430](http://forum.xentax.com/viewtopic.php?f=16&t=5430)

I uploaded SWRH *.mdg & *.mdl samples for examination here:
*Samples provided upon request*
