## Post #1
- Username: Venushja
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 19, 2010 11:13 pm
- Post datetime: 2012-12-03T21:45:14+00:00
- Post Title: Far Cry 3 .FAT decryption

Hi,
Anybody can decryption .FAT files in Far Cry 3? Thansk.
## Post #2
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-12-04T00:15:28+00:00
- Post Title: Far Cry 3 .FAT decryption

It's not encrypted.
## Post #3
- Username: Venushja
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 19, 2010 11:13 pm
- Post datetime: 2012-12-04T08:51:16+00:00
- Post Title: Far Cry 3 .FAT decryption

> Reply from Rick
>
> It's not encrypted.

Then algorithm for unpack files? I need unpack this file because, need change language, replace english language for czech language.
## Post #4
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2012-12-04T12:15:05+00:00
- Post Title: Far Cry 3 .FAT decryption

[http://svn.gib.me/builds/dunia2/](http://svn.gib.me/builds/dunia2/)
Unpacker and Packer 

Thanks Rick! Works perfectly!
## Post #5
- Username: Venushja
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 19, 2010 11:13 pm
- Post datetime: 2012-12-04T15:54:44+00:00
- Post Title: Far Cry 3 .FAT decryption

I have a PS3 and here is decryption meybe ... This unpack tools not working
## Post #6
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2012-12-04T16:57:40+00:00
- Post Title: Far Cry 3 .FAT decryption

> Reply from Venushja
>
> I have a PS3 and here is decryption meybe ... This unpack tools not working

Different compression scheme, you'll have to work out what then implement it in ricks code or write your own.
## Post #7
- Username: Venushja
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 19, 2010 11:13 pm
- Post datetime: 2012-12-04T17:21:17+00:00
- Post Title: Far Cry 3 .FAT decryption

> Reply from twisted
>
> Venushja wrote:I have a PS3 and here is decryption meybe ... This unpack tools not working 

Different compression scheme, you'll have to work out what then implement it in ricks code or write your own.

If I would how compresion scheme than I write own program but I don't no
## Post #8
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2012-12-04T21:43:55+00:00
- Post Title: Far Cry 3 .FAT decryption

Might not be the best place to ask but...anyone doing research about game models?
## Post #9
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-12-04T22:38:59+00:00
- Post Title: Far Cry 3 .FAT decryption

> Reply from CMihai
>
> Might not be the best place to ask but...anyone doing research about game models?On my todo list, my Dunia repository has some work on Far Cry 2's model format, of which Far Cry 3 has a newer version of.

[http://svn.gib.me/public/dunia/trunk/Gi ... rceFile.cs](http://svn.gib.me/public/dunia/trunk/Gibbed.Dunia.FileFormats/GeometryResourceFile.cs)
[http://svn.gib.me/public/dunia/trunk/Gi ... /Geometry/](http://svn.gib.me/public/dunia/trunk/Gibbed.Dunia.FileFormats/Geometry/)
## Post #10
- Username: Venushja
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 19, 2010 11:13 pm
- Post datetime: 2012-12-04T23:06:33+00:00
- Post Title: Far Cry 3 .FAT decryption

To Rick : Here is a file from PS3 version 

```
removed
```

You can do anything that in order to extract the files? And pack into back?
Thanks for you answer.
## Post #11
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-12-05T20:30:33+00:00
- Post Title: Far Cry 3 .FAT decryption

In the PC version, the file, containing the texts of the game is in the oasisstrings.xml file, in the common.dat/.fat archive, however the game doesn't read from there, but a compressed oasisstrings_compressed.bin file is there too with the texts of the game.
So my guess is, we have to compress the .xml file to .bin, to make the game use it.
## Post #12
- Username: tpcrew
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Jan 08, 2012 7:36 pm
- Post datetime: 2012-12-07T11:46:15+00:00
- Post Title: Far Cry 3 .FAT decryption

Hi! this is for decode *.sbao sound files of FC3

[http://neb.frikafrax.com/2010/06-2475-j ... rsion.html](http://neb.frikafrax.com/2010/06-2475-james-camerons-avatar-game-sound-conversion.html)
## Post #13
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-12-07T17:22:06+00:00
- Post Title: Far Cry 3 .FAT decryption

Any news on how to make the modified texts work ingame?
## Post #14
- Username: vitoci
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Nov 11, 2011 2:24 am
- Post datetime: 2012-12-08T07:05:54+00:00
- Post Title: Far Cry 3 .FAT decryption

> Reply from Rick
>
> CMihai wrote:Might not be the best place to ask but...anyone doing research about game models?On my todo list, my Dunia repository has some work on Far Cry 2's model format, of which Far Cry 3 has a newer version of.

http://svn.gib.me/public/dunia/trunk/Gi ... rceFile.cs
http://svn.gib.me/public/dunia/trunk/Gi ... /Geometry/

Hi Rick, Greetings.
There is a way to create an injector extracted files to the original tablets, as well as the reimport of quicbms.
to PC system
Thanks
## Post #15
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2012-12-08T08:37:02+00:00
- Post Title: Far Cry 3 .FAT decryption

there is an extracted folder named _UNKNOWN, so will game run with the repacked dat/fat archive
## Post #16
- Username: Luriam
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Jun 25, 2012 3:44 pm
- Post datetime: 2012-12-08T08:53:36+00:00
- Post Title: Far Cry 3 Sound Extract

Hi everyone, if anyone needs to extract sounds from the archives, you may use [OggExtract](http://www.mediafire.com/?4o0ip9qnm8uerkq) to do that. Have Fun!
## Post #17
- Username: Venushja
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 19, 2010 11:13 pm
- Post datetime: 2012-12-08T14:18:13+00:00
- Post Title: Far Cry 3 Sound Extract

this unpacker i work, but me show error on common.FAT file. Please help me?
[http://img203.imageshack.us/img203/3862/commonfat.png](http://img203.imageshack.us/img203/3862/commonfat.png)
Edit : I have a game on PS3.
## Post #18
- Username: abdullayev007
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Aug 02, 2012 7:02 am
- Post datetime: 2012-12-08T14:40:17+00:00
- Post Title: Far Cry 3 Sound Extract

> Reply from Venushja
>
> this unpacker i work, but me show error on common.FAT file. Please help me?
http://img203.imageshack.us/img203/3862/commonfat.png

I Think This tool isn't work on XBOX or PS3 file format. Only for PC.
## Post #19
- Username: Venushja
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 19, 2010 11:13 pm
- Post datetime: 2012-12-08T14:45:48+00:00
- Post Title: Far Cry 3 Sound Extract

> Reply from abdullayev007
>
> Venushja wrote:this unpacker i work, but me show error on common.FAT file. Please help me?
http://img203.imageshack.us/img203/3862/commonfat.png

I Think This tool isn't work on XBOX file format. Only for PC.
Sh*t ... I think so Xbox and Playstation3 use Big Endian and this tools use Little Endian. 
Anybody rewrite this tools?
## Post #20
- Username: abdullayev007
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Aug 02, 2012 7:02 am
- Post datetime: 2012-12-08T14:55:59+00:00
- Post Title: Far Cry 3 Sound Extract

> Reply from Venushja
>
> abdullayev007 wrote:Venushja wrote:this unpacker i work, but me show error on common.FAT file. Please help me?
http://img203.imageshack.us/img203/3862/commonfat.png

I Think This tool isn't work on XBOX file format. Only for PC.
Sh*t ... I think so Xbox and Playstation3 use Big Endian and this tools use Little Endian. 
Anybody rewrite this tools?

in the future may be tool will support ps3 or xbox formats.
## Post #21
- Username: Venushja
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 19, 2010 11:13 pm
- Post datetime: 2012-12-08T15:00:59+00:00
- Post Title: Far Cry 3 Sound Extract

> Reply from abdullayev007
>
> 
in the future may be tool will support ps3 or xbox formats.
I will need this rewrite tools on suppert ps3 and xbox as soon as possible.
## Post #22
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2012-12-08T18:05:05+00:00
- Post Title: Far Cry 3 Sound Extract

As I've said previously the console files use different compression methods.
## Post #23
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2012-12-11T18:44:37+00:00
- Post Title: Far Cry 3 Sound Extract

Many thank's to Rick for his tool.
## Post #24
- Username: tpcrew
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Jan 08, 2012 7:36 pm
- Post datetime: 2012-12-12T12:51:04+00:00
- Post Title: Far Cry 3 Sound Extract

as I can see or convert. xbg files?

Thx
## Post #25
- Username: Venushja
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 19, 2010 11:13 pm
- Post datetime: 2012-12-14T14:35:59+00:00
- Post Title: Far Cry 3 Sound Extract

Anybody can write algorithm for PS3?
## Post #26
- Username: abdullayev007
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Aug 02, 2012 7:02 am
- Post datetime: 2012-12-15T09:58:24+00:00
- Post Title: Far Cry 3 Sound Extract

Any news about XML >> BIN convertor?
## Post #27
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2012-12-20T15:43:16+00:00
- Post Title: Far Cry 3 Sound Extract

Is it any way to know what's the name of the SBAO and SPK sounds? Because I managed to convert those files to wav or ogg but still have their binary name ( 0003158bg54, 5184dehbd022, etc... ) and I didn't found any list of them in the main archive. That's took me 3 hours for only 60Mo of sounds because I tried to figure out something important: " what sound is what for? "

So, any help will be appreciated.

Cordialy

Vosvoy
## Post #28
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2012-12-25T22:36:58+00:00
- Post Title: Far Cry 3 Sound Extract

Anything new regarding Geometry Rick?
## Post #29
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-12-27T03:18:09+00:00
- Post Title: Far Cry 3 Sound Extract

> Reply from CMihai
>
> Anything new regarding Geometry Rick?Nearly the same as FC2. I don't know enough about modelling to make import/export tools, someone will have to take my work and do something with it.
## Post #30
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2012-12-27T07:12:53+00:00
- Post Title: Far Cry 3 Sound Extract

So on what you have so far, an importer can be done?
## Post #31
- Username: abdullayev007
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Aug 02, 2012 7:02 am
- Post datetime: 2012-12-27T09:38:41+00:00
- Post Title: Re: Far Cry 3 .FAT decryption

> Reply from Rick
>
> CMihai wrote:Anything new regarding Geometry Rick?  Nearly the same as FC2. I don't know enough about modelling to make import/export tools, someone will have to take my work and do something with it.

Will you create a Tool for compressing XML strings to BIN?
## Post #32
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-01-04T19:50:44+00:00
- Post Title: Re: Far Cry 3 .FAT decryption

Edit: Nevermind, the models have already been dumped on the Interwebs.
## Post #33
- Username: Rocky5
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Jun 21, 2007 6:30 am
- Post datetime: 2013-01-10T17:15:00+00:00
- Post Title: Re: Far Cry 3 .FAT decryption

Any chance you could have a look at the Xbox xml format, some xmls are plain txt & others seem to be garbled, I thought they maybe zlib compressed but no 

We can use some of the PC files so not all is lost  the file in the attached files the PC version works on the Xbox, I removed the Memory limits from items.

Batch I put together to extract Common.fat just drag the folder containing the Comman.fat/dat onto the batch or double click it. (searches through folders for the files, keeps my work space clean)

```

:: Set File & Folder names
:: Checks through the folders for the files.
for /f "delims=" %%A in ('dir /b /S "common.fat"') do Set "Input=%%A"
if "%Input%"=="%Input:~0,-11%\common.fat" Set "Filename=common"
Set "Output=%homedrive%\Unpacked"

:: Echo output information
Echo:
Echo   Unpacking = %Filename%
Echo   Temp Location = %Output%
Echo   Final Directory = "Common Unpacked"
Echo:
Ping -n 3 127.0.0.1 >Nul

:: Do the work :-D

for /f "delims=" %%B in ('dir /b /S "Gibbed.Dunia2.Unpack.exe"') do "%%B" -v -o "%Input%" "%Output%"

Move "%Output%" "%CD%\"
Ren "Unpacked" "Common Unpacked"

CLS
Echo:
Echo  Done...
Echo:
Ping -n 3 127.0.0.1 >Nul
Explorer "%CD%\Common Unpacked"
Exit

```

[object_inventory.zip](https://xentaxbackup.github.io/file/6126_object_inventory.zip)
## Post #34
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2013-02-26T20:40:41+00:00
- Post Title: Re: Far Cry 3 .FAT decryption

Is it possible to both view and edit the text files on PC yet?
## Post #35
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-02-27T23:28:46+00:00
- Post Title: Re: Far Cry 3 .FAT decryption

> Reply from qabRieL
>
> Is it possible to both view and edit the text files on PC yet?
The text file was always editable (18.000 lines of pure joy in 1 .xml file), the only problem is, that the game doesn't use it, since it (probably) has to be repacked to a .bin file.
## Post #36
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2013-03-02T19:28:10+00:00
- Post Title: Re: Far Cry 3 .FAT decryption

Here the 010Editor template that parses oasisstrings_compressed.bin file. Run this template on the oasisstrings_compressed.bin file.
LZO compression is used in the cmpData places in the file.(lzo1x)
THIS TEMPLATE DOES NOT DECOMPRESS ANYTHING!
It is just for to show structure of file.


```
struct stringTable{    
    int unknown;
    int sectorCount;
    struct section{
        int sectorHash;//crc32 of sector name
        int stringCount;
        struct{
            int id;    //line id
            int sec;   //same as sectorHash
            int _enum; //crc32 hash of enum attribute in string
            int pack; //crc32 Hash of 'Main'    
        }lines[stringCount]<optimize=false>;
        int cmpPartCount; //Number of lzo compressed parts
        struct{
            int unknown;
            int cs;//compressed size of data
            int ds; //decompressed size of data
            ubyte cmpData[cs]; //These bytes are lzo compressed (lzo1x)
       }parts[cmpPartCount]<optimize=false>;   
    }sectors[sectorCount]<optimize=false>;
}all[stringTableCount]<optimize=false>;

```

Here the compressed and decompressed ones for first sector:

[](http://imgur.com/SxWnWSO)

Here is the tool from  General_Problem ([ubisoft far cry 3 forums](http://forums.ubi.com/showthread.php/734046-Mods-for-Far-Cry-3?p=8971009&viewfull=1#post8971009))


> Reply from General_Problem
>
> 
JGR.Dunia2.ConvertXML version 1.0

I have completed my first version of my tool to de-compress and re-compress the oasisstrings_compressed.bin file.  This tool also has the ability to use oasisstrings.xml as a lookup dictionary for de-compressing the section and enum names into human-readable text rather than hexadecimal when that file is in the same folder as the oassistrings_compressed.bin file you are decompressing.

I have also trimmed down the source code to only those sections of the Dunia2 source which were necessary to support the tool as a standalone application.

Get the executable here

Get the source code here

The tool was written based on Rick's original Gibbed.Dunia2.ConvertXML application, but I added options in order to handle this special file as well as a new FileFormats class, OasisStringsCompressedFile, to handle the conversion to and from XML (as well as the de-/compression).

Here is a brief overview of the steps to follow in order to modify game text and put your changes into the game utilizing this tool:

1) Put the files for this tool in a new tools folder (or you can put them in your existing Dunia2 folder, but it will overwrite 
	some files, so MAKE A BACKUP if you do this).
2) Use the JGR.Dunia2.ConvertToXML.exe tool to convert your oasisstrings_compressed.bin to xml.  (Note that the output will have
	the text "_converted" appended the same way the original Dunia2 tools do).
3) Edit your desired text in the xml file output from step 2
4) Use JGR.Dunia2.ConvertToXML.exe again to convert your xml file back to oasisstrings_compressed.bin. (Note that the output will
	now also have "_compressed_converted" appended to the name).
5) Rename your final output file back to "oasisstrings_compressed.bin" 
6) Don't forget to put the new "oasisstrings_compressed.bin" file into your patch under the .\languages\*your local language*\
	folder, then re-pack your patch to try it in the game.
7) Remember that unless you translate your modified text and perform these tasks for all supported language files, your mod will
	likely only function properly when executed from versions that support your own language. You could potentially replace all
	of the oasisstrings_compressed.bin files with your newly modified file in your patch to force all users to see your language.

Please read the README.txt file in the downloads for more information.

Cheers!

Acknowledgements: 
- Rick for creating the original tools that were completely essential
- Special thanks to "tom.solo", "sfaunl", and "celikeins" for your assistance, input, and dedictaion to the virtual islands.
## Post #37
- Username: sergeron
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 16, 2013 8:25 pm
- Post datetime: 2013-05-01T18:53:29+00:00
- Post Title: Re: Far Cry 3 .FAT decryption

Dunia2 don't work on Far Cry 3: Blood Dragon.
## Post #38
- Username: soulslayerzx
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Aug 14, 2012 9:46 am
- Post datetime: 2013-07-12T18:32:00+00:00
- Post Title: Re: Far Cry 3 .FAT decryption

So far, I believe this dunia thing can extract textures, sounds,

I was wondering if there was a way to extract the models without ripping them unrigged. I hate rigging.
## Post #39
- Username: wana7262
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Dec 13, 2014 4:51 pm
- Post datetime: 2015-04-15T10:06:23+00:00
- Post Title: Re: Far Cry 3 .FAT decryption

How to extract .dat file?
