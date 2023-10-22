## Post #1
- Username: darksoul
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Apr 20, 2011 11:49 pm
- Post datetime: 2011-08-09T20:59:44+00:00
- Post Title: succesfull modded MK9 textures help creating QUICKBMS SCRIPT

okay the things i posted earlier i deleted 

so heres what im going try to do now

i want to make a bms script for the texture2d files and convert them to .dds dxt5 files 
texture2d files from CHAR files can be obtained useing the tools from gildor ,Unreal Package Extractor
when you extract a CHAR file you will get a map with the same name as the CHAR file you extracted
in there is a map called textures this is where the .texture2d files are located

looking at the texture2d files i figured how the are put together and what pixel format it uses namely .dds dxt5 with mipmaps
i already edited succesfully the textures and replaced them back into the texture2d but all useing a hex editor,so i want to make this absolete by making a script for quickbms and i know that with the latest version you can also use the same script as a reimporter.

now im going to tell here how the texture2d are put together and how i was able to edit them in photoshop
first there are 4 major textures for characters which are _diff.texture2d _normalHQA.textur2d _spec.texture2d and _pmsk.texture2d and characters also have damage textures which are called  DMG_diff.texture2d DMG_normalHQA.textur2d DMG_spec.texture2d and DMG_pmsk.texture2d plus more textures like for hair or weapons stuff like that,but i edited the _diff.texture2d in photoshop so i could change the colors like for skarlet and made her blue in stead of red






so im going to use the _diff.texture2d as an example (the other texture2d files are put togheter in the same way so)

first 100 bytes of a _diff.texture2d file 


```
00 00 06 18 00 00 00 00 00 00 04 13 00 00 00 00 00 00 00 04 00 00 00 00 00 00 04 00 00 00 06 19 00 00 00 00 00 00 04 13 00 00 00 00 00 00 00 04 00 00 00 00 00 00 04 00 00 00 02 F4 00 00 00 00 00 00 00 FB 00 00 00 00 00 00 00 01 00 00 00 00 07 00 00 04 D2 00 00 00 00 00 00 04 13 00 00 00 00 00 00 00 04 00 00 00 00 00 00 00 FF 00 00 05 05 00 00 00 00 00 00 00 CD 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 01 00 00 04 67 00 00 00 00 00 00 00 FB 00 00 00 00 00 00 00 01 00 00 00 00 02 00 00 05 09 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 D3 FB 60 00 00 00 00 00 00 00 00 00 00 00 00 00 D3 FB 70 00 00 00 0B 00 00 00 00 00 10 00 00 00 10 00 00 00 D3 FB 84 00 00 00 00 00 00 00 00 49 4A C7 39 BF BF 1D 3D 00 00 00 00 00 00 00 00 10 84 24 21 5E 5E 5E 5E 00 00
```


everything is in endian big and everything is 4 bytes long


so when we go to 0xCA in a hex editor you will the number of textureblocks  00 00 00 0B 

then you will get a NULL 00 00 00 00

then you will get  00 10 00 00 2 times which is the size of the first texture block 

after that you get  00 D3 FB 84 which is an offset specific for the CHAR_file but not relevant if i want to just convert the texture2d to a dds dxt5

after the offset begins the textureblock which is  00 10 00 00 long in hex 

so jumping 00 10 00 00 further with the hex editor you will get 

```
00 00 04 00 00 00 04 00 00 00 00 00 00 04 00 00 00 04 00 00 00 E3 FB 9C
```


first 4 bytes after the first textureblock is 00 00 04 00=1024 which is the height of the texture 
2nd 4bytes is also  00 00 04 00=1024 which is the width of the texture 
then you will get a NULL 00 00 00 00
and then you will get filesize for the 2nd textureblock within the texture2d 2 times again 00 04 00 00
and then again an offset before the 2nd textureblock begins  00 E3 FB 9C which is again specific for the CHAR file

so this will go on 11 times 00 00 00 0B

what i did is i took out all the the textureblocks and placed them togehter in the same order put a dds dxt5 header above it.

the dds header and texture for the texture2d can easily be obtainted for the correct width and height.

i used umodel (also from gildor) for the char_...xxx files and when useing (for ps3) the commands -nomesh -noanim -ps3 -export you will also get a map called texture2d in there are the textures only in .tga just convert the .tga to .dds dxt5 and then we already have the dds header in the correct size(witdh and height)

it opens in photoshop (dds plugin) loaded it without mipmaps,edited it saved it again as a dds dxt5 with generate mipmaps and put it back again with hex
editor

the sizes of the textureblocks will be the same as the mipmaps ,1st was 00 10 00 00 so selected first 00 10 00 00 hex (1048576 bytes) (-.dds header))of the dds and swapped it in the texture2d then the next 00 04 00 00 and so on



the .texture2d is actually the same as a .dds dxt5 format with mipmaps only the texture2d puts the mipmaps seperatly in with width,height and size2x (and a offset specific for within the char...xxx file)


so now that i explained how its put together,i want to make a bms script for making the texture2d into a dds and edit it,and then use the reimport option of quickbms to reimport 

ive been trying to make scripts but with no luck,i find it hard to understand,i know it can be made i saw the topic of chroxx and uncharted2 that he made a script for making a file of uncharted2 into a .dds file.

[viewtopic.php?f=18&t=6901&p=56077&hilit=quickbms#p56077](http://forum.xentax.com/viewtopic.php?f=18&t=6901&p=56077&hilit=quickbms#p56077)

so any help here is much appreciated 



here are the textures and the diff texture i used in the example

[http://www.megaupload.com/?d=7FU4XFL6](http://www.megaupload.com/?d=7FU4XFL6)
## Post #2
- Username: darksoul
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Apr 20, 2011 11:49 pm
- Post datetime: 2011-08-14T10:41:10+00:00
- Post Title: succesfull modded MK9 textures help creating QUICKBMS SCRIPT

so here is a script i made thus far 

```

endian big 

get files long

for i = 0 < FILES

get null02 long

get unk03 long

get size long

get NAME long

savepos OFFSET

getDstring OFFSET size

get WIDTH long 

get HEIGHT long

Log NAME OFFSET SIZE

next i
```


which gives me

```
------------------------------
  00000000 1048576    11593977
  00000000 262144     12642577
  00000000 65536      12904745
  00000000 16384      12970305
  00000000 4096       12986713
  00000000 1024       12990833
  00000000 256        12991881
  00000000 64         12992161
  00000000 16         12992249
  00000000 16         12992289
  00000000 16         12992329

- 11 files found in 0 seconds
```


so what am i doing wrong here ?,i got files and filesizes right,but every file starts at offset 00000000

how can i change that to get the right offset for the right file,tried several things but keep getting same error
## Post #3
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2011-08-14T20:13:53+00:00
- Post Title: succesfull modded MK9 textures help creating QUICKBMS SCRIPT

Sorry i can't help with this but awesome work so far. Nice that you kept trying 

Hopefully chrox or some other hexwizard will come to help
## Post #4
- Username: darksoul
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Apr 20, 2011 11:49 pm
- Post datetime: 2011-08-14T21:31:44+00:00
- Post Title: succesfull modded MK9 textures help creating QUICKBMS SCRIPT

> Reply from Itze
>
> Sorry i can't help with this but awesome work so far. Nice that you kept trying 

Hopefully chrox or some other hexwizard will come to help

thnx itze 

i initially first posted a new topic just for help

but when no one helps you out with knowledge of scripts and quickbms   ,with exception of a few people,you have to find things out for your self,its also the best way to learn new stuff

anyways got a little bit progress on the script

```

endian big 

get files long

for i = 0 < FILES

get null long

get unk long

get size long

get unk1 long

savepos block

savepos OFFSET

getdstring block unk

get WIDTH long

get HEIGHT long

log "" OFFSET SIZE 

next i
```


which gives me 

```
------------------------------
  000000de 1048576    00000000.dat
  001000f6 262144     00000001.dat
  0014010e 65536      00000002.dat
  00150126 16384      00000003.dat
  0015413e 4096       00000004.dat
  00155156 1024       00000005.dat
  0015556e 256        00000006.dat
  00155686 64         00000007.dat
  001556de 16         00000008.dat
  00155706 16         00000009.dat
  0015572e 16         0000000a.dat

- 11 files found in 0 seconds

```


which means i now have extracted the mipmaps/textures correctly,but all seperatly,so i must now let it extract as 1 file togehter and with a .dds header above it.
so now looking further into quickbms.
## Post #5
- Username: darksoul
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Apr 20, 2011 11:49 pm
- Post datetime: 2011-08-21T10:49:46+00:00
- Post Title: succesfull modded MK9 textures help creating QUICKBMS SCRIPT

oke made a bit progress on the script

```
string NAME + ".dds"
goto 0xCA
endian big 
get MIPS long
get null long
get SIZE1 long
get SIZE2 long
get unk1 long
savepos OFFSET
savepos texblock
getDstring texblock SIZE1
set OFFSET2 OFFSET
math OFFSET2 + SIZE2
goto OFFSET2
get WIDTH long
get HEIGHT long
callfunction addDDSheader
math SIZE1 + 0x80
log NAME 0 SIZE1 MEMORY_FILE
For i = 0 < FILES
get null long
get SIZE3 long
get SIZE4 long
get unk1 long
savepos OFFSET3
savepos texblock2
getDstring texblock2 SIZE4
get MMWITDH long
get MMHEIGHT long
append
log NAME OFFSET3 SIZE3
append
next i

startfunction addDDSheader
endian little
set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A

\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00

\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00

\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00

\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
putVarChr MEMORY_FILE 0x10 WIDTH long
putVarChr MEMORY_FILE 0xC HEIGHT long
putVarChr MEMORY_FILE 0x1C MIPS long
endian big
   append
   log MEMORY_FILE OFFSET SIZE1
   append
endfunction
```


now the texture2d extracts as a .dds   ,but it will not work on all the texture2d files e.g normhqa and more(different offsets)
## Post #6
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2011-08-26T11:18:46+00:00
- Post Title: succesfull modded MK9 textures help creating QUICKBMS SCRIPT

Thanks to the info provided by darksoul, I've managed to add support in X-Packer for MK9 files. Download the latest version from my site.
## Post #7
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2011-08-27T19:24:45+00:00
- Post Title: succesfull modded MK9 textures help creating QUICKBMS SCRIPT

as charly sheen would say: WINNING!   

thanks to you guys we can basically texture mod every unreal engine game now without texmod
## Post #8
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2011-08-27T20:18:59+00:00
- Post Title: succesfull modded MK9 textures help creating QUICKBMS SCRIPT

guess i spoke a bit too soon...   

this is how the xpacker converted diff texture looks if used from a 360 package (i've used the alternative costume of sonya):

[http://i.imgur.com/SuB1R.jpg](http://i.imgur.com/SuB1R.jpg)

here is the already decompressed character file:

[http://www63.zippyshare.com/v/61495353/file.html](http://www63.zippyshare.com/v/61495353/file.html)

would be nice if you could xpacker to work with the 360 version too
## Post #9
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2011-08-28T08:02:47+00:00
- Post Title: succesfull modded MK9 textures help creating QUICKBMS SCRIPT

The contents of this post was deleted because of possible forum rules violation.
## Post #10
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2011-08-29T13:11:44+00:00
- Post Title: succesfull modded MK9 textures help creating QUICKBMS SCRIPT

The contents of this post was deleted because of possible forum rules violation.
## Post #11
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2011-09-28T11:20:18+00:00
- Post Title: succesfull modded MK9 textures help creating QUICKBMS SCRIPT

the desizzling problem has been solved and a new version of my app has been released which supports the xbox version.
## Post #12
- Username: interloko
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Oct 27, 2009 12:53 am
- Post datetime: 2012-02-07T19:32:09+00:00
- Post Title: succesfull modded MK9 textures help creating QUICKBMS SCRIPT

i'm not sure if this helps you but new version of umodel can export textures in dds format
## Post #13
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2012-02-27T07:23:02+00:00
- Post Title: succesfull modded MK9 textures help creating QUICKBMS SCRIPT

> Reply from interloko
>
> i'm not sure if this helps you but new version of umodel can export textures in dds format

Thanks, but I've already solved the issue.
