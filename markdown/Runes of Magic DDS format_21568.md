## Post #1
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2020-01-04T12:34:55+00:00
- Post Title: Runes of Magic DDS format?

I've got some progress on Runes of Magic thanks to DKDave on the Discord, but it brought up a new problem:

When I try to open a texture file (they are saved in .dds format), GIMP throws me a double error that reads: "Invalid DDS file." as well as "Invalid DDS Header!" This happens with ANY texture file, so I've got no idea where I could find the cause for this problem... Can I?

The texture files are packed in a 7z file that can be found [here](https://drive.google.com/open?id=10hDqgt6Bo1eaITDo3B_cD6fLEpejUh75). (It is a rather big file as I need certain textures for both genders on humans and elves...)

Any help is greatly appreciated!
## Post #2
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2020-01-06T12:50:47+00:00
- Post Title: Runes of Magic DDS format?

It's pretty clear they have intentionally scrambled the files to prevent you having access.
The first layer is zlib compression but what the 2nd layer is supposed to be would need more figuring out whether its another compression layer or cipher.
Can't help further, maybe someone else has the time/expertise/interest to try various means to reverse engineer them.
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-01-06T20:02:58+00:00
- Post Title: Runes of Magic DDS format?

they are lzma compressed, here is bms script to decompress to viewable dds files.   

edit
*updated script to support zlib compressed files also* 


 RunesOfMagic_dds.zip
(616 Bytes) Downloaded 22 times
## Post #4
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2020-01-30T08:13:25+00:00
- Post Title: Runes of Magic DDS format?

> Reply from Acewell ↑Tue Jan 07, 2020 4:02 am at Tue Jan 07, 2020 4:02 am
>
> 
they are lzma compressed, here is bms script to decompress to viewable dds files.  
Code: Select all# script for QuickBMS http://aluigi.altervista.org/quickbms.htm

comtype lzma_dynamic
get NAME basename
get EXT extension
string NAME + _decmp.
string NAME + EXT
goto 0x46
get SIZE long
get ZSIZE long
savepos OFFSET
clog NAME OFFSET ZSIZE SIZE

I keep running into a memory allocation problem or I get this error:

```
12 clog NAME OFFSET ZSIZE SIZE
```


I think I found the problem:
Some of the texture files I extracted exceed the size of 1MB - and that script can't handle this size (it doesn't matter if I use the regular or the 4gb_files executable)... Skip them or fix the script?
Take for example the file hm_male_foot_02_leather100-001.dds and try decompressing it.
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-01-30T14:19:45+00:00
- Post Title: Runes of Magic DDS format?

that file is zlib compressed instead of lzma, and it is headerless rgba32 when decompressed,
i will try to modify the script later to accomodate these best i can.  
i might just put this into a Noesis python script later for fun.   

edit: script updated in previous post
