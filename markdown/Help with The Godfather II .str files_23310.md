## Post #1
- Username: venixuc
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 13, 2019 10:00 am
- Post datetime: 2021-01-15T00:45:52+00:00
- Post Title: Help with The Godfather II .str files

The "dac49de4.str" file contains text displayed in this game. I was able to extract its content with QuickBMS (using dead_space_3.bms). However, the text I would like to edit is compressed inside NAM_1.dat. When extracting .str content with Game Extractor, NAM_1 file is exported as kapR file and the text is decompressed, it's possible to edit it with hex editor as long as the original file size is preserved.
But, in order to reimport the modified file into .str, it has to be compressed.
So, the question is: How to convert kapR file to NAM_1.dat?
I've attached the .rar archive which contains:
- dac49de4.str - the original archive
- NAM_1.dat, NAM_2.bal, NAM_3 dat, NAME - files extracted with QuickBMS
- kapR - the decompressed NAM_1.dat.
The files of interest for this are NAM_1.dat and kapR. Also, is there any other way to edit kapR other than using hex editor that would allow changing its size (something like .gxt editor for GTA games)? The Game Extractor exports it without extension.
Any help is appreciated.
[dac49de4.rar](https://xentaxbackup.github.io/file/19306_dac49de4.rar)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-15T13:45:00+00:00
- Post Title: Help with The Godfather II .str files

> So, the question is: How to convert kapR file to NAM_1.dat?
This NAM_1 file is compressed with Refpack algorithm.
To pack this, you would need to compress it again with Refpack
Here is some info [https://www.google.com/search?client=fi ... compressor](https://www.google.com/search?client=firefox-b-d&q=refpack+compressor)

But maybe it will be better to just use quickbms to parse the file,
here is file format for STR [http://www.watto.org/specs.html?specs=Archive_STR_3SLO](http://www.watto.org/specs.html?specs=Archive_STR_3SLO)


> Also, is there any other way to edit kapR other than using hex editor that would allow changing its size (something like .gxt editor for GTA games)?
It is possible only by reverse engineering whole file format and creating working custom editor manually. That's a lot of work.
## Post #3
- Username: venixuc
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 13, 2019 10:00 am
- Post datetime: 2021-01-16T00:15:05+00:00
- Post Title: Help with The Godfather II .str files

Thanks for your reply, ikskoks.
I inspected the kapR file further and found out that it can be opened with notepad. It's even possible to view and edit the text I need (I'm not trying to translate the game, I want to edit npc names - more precisely mobster names). But, when I compare the non-edited and edited files in HxD, I see this:
[https://ibb.co/VgZd0Gw](https://ibb.co/VgZd0Gw) (non-edited)
[https://ibb.co/NnzPQL1](https://ibb.co/NnzPQL1) (edited)
Several "00" values are changed to "20". Can this corrupt the file? 
If the file doesn't get corrupted while doing this, it would be easy to change its size. But then a new problem emerges; QuickBMS refuses to reimport the larger file into .str.
Also, the npc names are grouped - here you can see a fragment of Corleone mobster names:
[https://ibb.co/NpGJrnW](https://ibb.co/NpGJrnW)
The same thing goes with the mobster names from another families. If I wanted to keep the file size intact and use HxD for editing, would I need to keep the original name length or just the sequence length of the name group?
For example, mobster name "Big Greenie" Grinberg has 23 characters, including the spacing and quotation marks. The next name in the sequence is Micheal Galli, with 14 characters (spacing included). And let's say that the entire sequence of Corleone mobster names has e.g. 600 characters.
Would it be possible to give Big Greenie a new, 20-characters long name and 17-characters long name to Galli? Something like this:
[https://ibb.co/KyNHv9K](https://ibb.co/KyNHv9K)
This wouldn't "shift" the rest of the file or change its size, but would the new names show up correctly in game?

And one more thing:
I compiled the refpack-brute-force.c but it doesn't open the file; when I type refpack-brute-force INFILE kapR or refpack-brute-force INFILE NAM_1.dat, it says that no such file/directory exists.
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-16T10:03:11+00:00
- Post Title: Help with The Godfather II .str files

> and found out that it can be opened with notepad.

> Several "00" values are changed to "20". Can this corrupt the file?
Ok, so never use notepad for editing binary files. It can corrupt file for many ways. 
It's always better to use hex editor or custom tool.

> QuickBMS refuses to reimport the larger file into .str.
That's the case I was talking earlier. It's easier to use quickbms because of it's
reimport function. But of course edited file must be the same size as original to make it work.
Only way to change this is to write a custom tool and as I said - it can be a lot of 
reverse engineering and programming work.

> Also, the npc names are grouped

> would I need to keep the original name length or just the sequence length of the name group?

> but would the new names show up correctly in game?

There is a way to change this. When games use text blocks like this one, they can have pointer tables
before these blocks. And here you fortunately have such pointer table starting at offset 36308.

Here is the structure:

```
{
  2 bytes (uint16) - string pointer
  2 bytes (uint16) - ID  // e.g. "1"
}
```


Here you can see how it looks for the first strings [https://i.imgur.com/poy87uD.png](https://i.imgur.com/poy87uD.png)
And here how these pointers looks in the hex editor [https://i.imgur.com/5glpvrs.png](https://i.imgur.com/5glpvrs.png)

So basically you need to edit those pointers to make some strings larger and some smaller.


> I compiled the refpack-brute-force.c but it doesn't open the file; when I type refpack-brute-force INFILE kapR or refpack-brute-force INFILE NAM_1.dat, it says that no such file/directory exists.
Maybe you forgot to put paths in quotes or something like that?
## Post #5
- Username: venixuc
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 13, 2019 10:00 am
- Post datetime: 2021-01-17T01:26:32+00:00
- Post Title: Help with The Godfather II .str files

> There is a way to change this.
If you mean "change the fact that the names are grouped", I'm not trying to change that; I don't think it would be possible at all due to the game mechanic - there are approx. 100 npc model variations and 200 names for crime families, so one model can have one of 2 possible names (e.g. a specific Corleone mobster can be Nick Williams or Ray Sforza - this is random). This means that these names are also paired in some way, but that's not really important for what I'm trying to do; if I was to edit the file (I'm not doing it yet because I can't get the refpack program working), I would do it block by block - this would require keeping the string length of the entire block and the number of names intact.

But I'd like to know more about string lengths within one block. I mean, if I changed the names "Big Greenie" Grinberg and Michael Galli to Alessandro Esposito and Virgilio Zingaro would the new string lengths be correctly registered by the game (I definitely wouldn't like to launch the game and see that the new names are shown as Alessandro EspositoVir or Alessandro Esposito Vi or Virgilio Zing because old lengths are kept instead). Does editing string lengths within one block (without changing number of strings) require editing pointers as well?

As for the refpack, I really don't know what I'm doing wrong. No matter what I type in - file name or path to it, it always "fails to open input file for reading - no such file or directory". The file is in the same directory as the .exe and the cmd is opened inside that folder. I'm starting to wonder if it's functional at all.
Here is a fragment of the refpack-brute-force.c code describing its usage and the error I'm getting:

```
		printf("Usage: refpack_brute_force INFILE OUTFILE\n");
		return EXIT_SUCCESS;
	}

	fd = fopen(argv[1], "rb");
	if (!fd) {
		fprintf(stderr, "Error: failed to open input file for reading"
			" (%s)\n", strerror(errno));
		return EXIT_FAILURE;
	}
```
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-17T12:33:53+00:00
- Post Title: Help with The Godfather II .str files

> If you mean "change the fact that the names are grouped"
I meant only string editing. Change of grouping would require changing game source code.

> Does editing string lengths within one block (without changing number of strings) require editing pointers as well?
Yes, exactly. You need to change pointers to manipulate lengths. 


> As for the refpack, I really don't know what I'm doing wrong.
Maybe just use other compressor. First link in google isn't always the best one xd

This one is working fine for me [https://cncguild.net/item-133](https://cncguild.net/item-133)
[https://i.imgur.com/cdcjdGG.png](https://i.imgur.com/cdcjdGG.png)
## Post #7
- Username: venixuc
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 13, 2019 10:00 am
- Post datetime: 2021-01-18T00:11:30+00:00
- Post Title: Help with The Godfather II .str files

> This one is working fine for me https://cncguild.net/item-133
Actually that tool is the first one I tried and it works for me too. But after the compression, the file size is 150 kb while it has to be 127 kb. And again, QuickBMS doesn't want to deal with it due to its size. I haven't modified the file before compressing it; I just compressed the kapR file extracted with Game Extractor. 
I also tried decompressing NAM_1.dat extracted with QuickBMS, but it says that it isn't compressed (???!!!):
[https://ibb.co/TqDy3x7](https://ibb.co/TqDy3x7)

I also tried the one from Niotso Wiki:

> The original RefPack.cpp written by Frank Barchard was released by WCNews: http://download.wcnews.com/files/docume ... efPack.cpp
However this one won't compile at all. Even if it did, I don't think it would work; the page describes that the refpack variation of the file is the one from The Sims Online (2002). Considering the fact that even The Godfather: The Game (2006) tools aren't compatible with The Godfather II (for example, there is a Zenhax topic about editing .str files from the first game - the strtool they used there doesn't recognize .str files from the second game, it says that "the input file is not a .str file"), I can say that this tool is pretty much useless.

Anyways, I got the RefPack Brute Force working. Or so I thought - the compressed file is completely empty.

The Game Extractor was the only tool capable of making NAM_1.dat content readable - not by opening it directly, but by extracting from the .str (it exports the file as kapR). And when it comes to .str files, GE can only export their content - importing anything back corrupts the .str and the game doesn't load.

Another option would be the Gibbed tools:
[https://github.com/gibbed?tab=repositories](https://github.com/gibbed?tab=repositories)
There is a RefPack tool there too. But yet again, I'm having problems with compiling it:

```
error CS5001: Compression.exe does not contain a static `Main' method suitable for an entry point
```

I used csc.exe from .NET Framework.
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-18T08:53:11+00:00
- Post Title: Help with The Godfather II .str files

Maybe try my refpack script
[https://github.com/bartlomiejduda/Tools ... script.bms](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/PGA%20Tour%2097/refpack_script.bms)

Only change extension on line 13 to the one you want to have after decompressing.

First decompress DAT file with this script, make some changes in the file and then use reimport mode.
Let me know if it worked.
## Post #9
- Username: venixuc
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 13, 2019 10:00 am
- Post datetime: 2021-01-19T01:43:54+00:00
- Post Title: Help with The Godfather II .str files

> Maybe try my refpack script
>
> https://github.com/bartlomiejduda/Tools ... script.bms
This happens when I try to decompress NAM_1.dat:
[https://ibb.co/C0S8FSc](https://ibb.co/C0S8FSc)
While the script can't decompress NAM_1.dat, it successfully compresses kapR file and the size after compression is 127 kb which makes it possible to import it back into .str with QuickBMS. But then the game crashes. The cause is obvious: when the compressed file is opened with hex editor, its content looks quite different than the original. Again, I haven't modified the kapR before the compression.

The refpack algorithm variation is probably different. I can't be 100% sure, but it appears that GE decompresses the file properly. However, standalone NAM_1.dat cannot be opened with GE; it decompresses it when .str archive is opened.

That's why I decided to try the Gibbed RefPack. Its algorithm is the one used in Dead Space 2, and there is a good chance that this one would work, just like dead_space_3.bms script for QuickBMS. But I'm still unable to compile it.

I've attached two NAM_1.dat files; original (extracted with QuickBMS) and modified (compressed kapR).
[NAM_1.dat.rar](https://xentaxbackup.github.io/file/19325_NAM_1.dat.rar)
## Post #10
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-19T09:18:50+00:00
- Post Title: Help with The Godfather II .str files

Oh boy, this case is more complicated than I thought, haha.

As for decompression method from Game Extractor, you can refer to the source code
[https://sourceforge.net/projects/gameex ... p/download](https://sourceforge.net/projects/gameextractor/files/Game%20Extractor%203.0x/3.11/source_311.zip/download)
The files you should look in are "Plugin_STR_3SLO.java" and of course "Exporter_REFPACK.java"

> there is a good chance that this one would work, just like dead_space_3.bms script for QuickBMS
I have googled this script and it seems that it also uses "dk2" as a comtype parameter

```
        comtype dk2
```

so I have no idea what's wrong here...


> But I'm still unable to compile it.
I was able to compile it without issues in Visual Studio 2019,
but it seems it is only a DLL file, not a working program.
To make it usable you probably need write some wrapper or at least main function.
I'm not a C# programmer, so I can't help you with that. xd


Edit: Here is compiled DLL in case you need it


 Gibbed_Refpack_dll.zip
(13.42 KiB) Downloaded 28 times
## Post #11
- Username: venixuc
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 13, 2019 10:00 am
- Post datetime: 2021-01-20T03:18:41+00:00
- Post Title: Help with The Godfather II .str files

> I was able to compile it without issues in Visual Studio 2019,
>
> but it seems it is only a DLL file, not a working program.
I compiled it to .dll too with csc.exe (using -target:library command). But the .dll file itself isn't very useful. All of the Gibbed tools are available only as the source code, and if this refpack code isn't meant to be a standalone .exe, it would be extremely difficult to determine which one uses it as an extension.

I haven't found any plugins in GE source code. The "3SLO" (ols3) signature is defined inside dead_space_3.bms for extracting .str file content. When I try decompressing NAM_1.dat using this script, this happens:
[https://ibb.co/bH3XCsV](https://ibb.co/bH3XCsV)
It doesn't recognize the signature.

Now, both QuickBMS and GE break down the .str srchive in several chunks. The QuickBMS extracts 4 chunks: NAM_1.dat, NAM_2.bal, NAM_3.dat and NAME (these files are attached in my first post), while GE extracts 3 chunks - kapR, Unnamed File 000002 and Unnamed File 000003. The 'unnamed files' are equivalent to NAM_2.bal and NAM_3.dat respectively, and GE doesn't decompress them (just like QuickBMS). Also, GE doesn't extract anything equivalent to NAME (this file only contains a header fragment from the .str).

The interesting file here is NAM_1.dat; while QuickBMS extracts it just how it looks like inside the .str archive, GE decompresses it. Its directory also contains a number of bms scripts inside .rar file. But I couldn't find any scripts or plugins responsible for the decompression; they could be hardcoded or inside .dll.

Not everything inside .str archive is compressed; only chunks with "kapR" identificator. The only file with this identificator inside dac49de4.str is NAM_1.dat. That's why GE decompresses it and extracts it as kapR. Finding out how GE decompresses these chunks would be helpful for compressing the extracted data.

I found a bms script which covers 99% of NAM_1.dat when i try decompressing it - skate3.bms. However, it says that it can't read 4 bytes at offset 0001FFBC and it doesn't complete the process. The same message shows up if I change idstring 6F 6C 73 33 (ols3) to B8 FF 01 00 with hex editor inside dead_space_3.bms. I wonder if skate3.bms could be modified to successfully decompress NAM_1.dat.

The last script line before the error is: 
```
30 get crc long
```

It looks like this
[https://ibb.co/D1JVZYt](https://ibb.co/D1JVZYt)

This time, I've attached the complete GE .str extraction results and the skate3.bms script.
[GE_extract+script.rar](https://xentaxbackup.github.io/file/19340_GE_extract+script.rar)
## Post #12
- Username: venixuc
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 13, 2019 10:00 am
- Post datetime: 2021-01-24T01:52:37+00:00
- Post Title: Help with The Godfather II .str files

I've found "Exporter_REFPACK.java" GE plugin. While I can't really tell what's going on with it by looking at its content, one thing got my attention:

> A.K.A. DBPF compression. Refer to http://wiki.niotso.org/RefPack for more info.
It refers to the RefPack.cpp file available there. This means that this file could be useful, if only it could be compiled; there are way too many missing libraries when I try compiling it.

Until the way to compress kapR (or decompress NAM_1.dat) is found, I'm unable to test editing results. This could take ages, and this topic could be long forgotten by that time.

Before that happens, I'd like to ask about string pointers. For example, the very first string in Corleone names block is "Big Greenie" Grinberg. How to find its pointer, and what exactly has to be edited there (value, position or something else)?
## Post #13
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-24T12:07:33+00:00
- Post Title: Help with The Godfather II .str files

> It refers to the RefPack.cpp file available there. This means that this file could be useful, if only it could be compiled; there are way too many missing libraries when I try compiling it.
You don't really need to compile it as it is already used in quickbms.
Check the file \src\libs\shadowforce\RefPack.cpp in quickbms source.
I have compared both files and there is almost 100% match [https://i.imgur.com/rtl1MpZ.png](https://i.imgur.com/rtl1MpZ.png)

Test all refpack types from src\comtype.h in the bms script I have send you earlier.

```
XREFPACK
XREFPACK0
CT_RefPack_COMPRESS
DK2
DK2_COMPRESS

```


Btw this Gibbed dll also can be useful. There are ways 
to use dynamic libraries in C++ projects [https://www.google.com/search?client=fi ... 2B+project](https://www.google.com/search?client=firefox-b-d&q=import+C%23+dll+library+in+c%2B%2B+project)
(or just write a wrapper in C#)



As for pointers, I have explained it with screenshots earlier
[https://i.imgur.com/poy87uD.png](https://i.imgur.com/poy87uD.png)
[https://i.imgur.com/5glpvrs.png](https://i.imgur.com/5glpvrs.png)

You only need to change values. For example you have "Specs" word with pointer 7050.
When you change it to 7052, game will read this as "ecs".
But ot will give you of course 2 extra characters to use in the previous string.
## Post #14
- Username: venixuc
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 13, 2019 10:00 am
- Post datetime: 2021-01-25T01:46:43+00:00
- Post Title: Help with The Godfather II .str files

> Test all refpack types from src\comtype.h in the bms script I have send you earlier.
>
> Code: Select allCT_RefPack
>
> XREFPACK
>
> XREFPACK0
>
> CT_RefPack_COMPRESS
>
> DK2
>
> DK2_COMPRESS

Well, xrefpacks don't work at all. This type gives an error "unsupported compression -1 in reimport mode" with last script line:

```
clog NAME 0 ZSIZE SIZE
```


With ct_refpacks and dk2s it's possible to complete the compression of kapR, but the data inside new NAM_1.dat is compressed too much which creates a huge "gap" from offset 0001b3c0 to 0001ffbc; this causes the game to crash. 

It's also worth mentioning that changing comtype in the script doesn't make decompression of original NAM_1.dat possible - it always says that the input file is incomplete. There is something in the script itself that compresses the data differently.

[https://www.zenhax.com/viewtopic.php?f=4&t=27&start=20](https://www.zenhax.com/viewtopic.php?f=4&t=27&start=20)
In this Zenhax topic "How to recognize the compression algorithms with your eyes", GHFear wrote:

> Just want to add how I spot RefPack/dk2 nowadays.
>
> First off...
>
> 0xXX = random value.
>
> RefPack/dk2 compression mostly looks like this "0xXX\0xFB" (where the 0xFB seems to be the tell tale sign of refpack.) and then right after is the Decompressed Size as a 4byte 32 bit integer / long. (to further confirm that it in fact is refpack/dk2.)
>
> So all in all it looks like this "0xXX\0xFB\0x00\0x1B\0x62\0x1C"
>
> 
>
> Depending on the strength of the compression the strings can still be sorta readable like this: "c:\datatemp\inter\PS2\Neutral\Chapâs\Hogwarts\ZoneãONE_HW_Viaduct_E.nãnce_DD\LefTextur�'àET_BURNâOOK_PAPER.ss€"
>
> 
>
> If you see this pattern, use comtype dk2

So the comtype here is probably dk2. I've tested every dk2 bms script I could find on QuickBMS site; none of them is able to decompress NAM_1.dat. Only GE is able to do this, but it cannot be used to edit .str files. And, GE is unable to open original NAM_1.dat directly. Could this mean that it doesn't decompress the data the right way?
## Post #15
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-25T20:39:11+00:00
- Post Title: Help with The Godfather II .str files

> none of them is able to decompress NAM_1.dat.

Delete 4 bytes from the beginning of NAM_1.dat and you will be able to decompress it.
## Post #16
- Username: venixuc
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 13, 2019 10:00 am
- Post datetime: 2021-01-26T02:21:28+00:00
- Post Title: Re: Help with The Godfather II .str files

> Delete 4 bytes from the beginning of NAM_1.dat and you will be able to decompress it.
You are right. This makes is possible to decompress the file and it looks exactly like kapR. It means that GE only reads the file after those 4 bytes, and nothing else; this finding makes GE obsolete.

This script, written by aluigi, extracts only decompressed NAM_1.dat from .str (the file has the same name as the .str archive - dac49de4 in this case):

```
goto 0x34
get SIZE long
goto 0x44
get ZSIZE long
savepos OFFSET
get NAME basename
clog NAME OFFSET ZSIZE SIZE
```

The decompressed file is the same as kapR, but the script doesn't compress it back.

The decompressed NAM_1 (and/or kapR) starts with 4C 43 48 32 (LCH2). The compressed one extracted from .str has B8 FF 01 00 10 FB 03 65 DF E2 (¸˙...ű.eßâ) before this string, and it cannot be decompressed without removing B8 FF 01 00. 
Using dk2 as comtype parameter in bms script for decompression makes the data fully readable; xrefpack gives an error "the uncompressed data is bigger than the allocated buffer"; and ct_refpack crashes QuickBMS.

The compression results are different. For example, "Skarsvaag" string is compressed as "Skŕvaag" in the original file and as "Sűkŕvaag" in dk2 or ct_refpack comtype script; the strings before LCH2 are also different - BC FF 01 00 E0 10 FB 01 FF 06 05 BC E0 FB 0A 05 BC FB FB E4 B8 FF 01 00 10 FB 03 65 DF E2 (Ľ˙..ŕ.ű.˙..Ľŕű..Ľűűä¸˙...ű.eßâ) for ct_refpack and 10 FB 01 FF BC E4 BC FF 01 00 E0 10 FB 01 FF 06 05 BC E0 FB 0A 05 BC FB FB E4 01 13 B8 FB 10 FB 03 65 DF E2 (.ű.˙ĽäĽ˙..ŕ.ű.˙..Ľŕű..Ľűűä..¸ű.ű.eßâ) for dk2. Using xrefpack for compression gives an error "unsupported compression -1 in reimport mode". The B8 FF 01 00 part is present only in ct_refpack compression.

The data compression for dk2 and ct_refpack is similar, and the "gap" from 0001b3c0 to 0001ffbc is present for both comtypes. The last byte in the original file is at offset 0001ffbb, and it's part of compressed data. 

An important question is: are dk2, ct_refpack and xrefpack the only refpack comtypes?
## Post #17
- Username: venixuc
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-26T11:00:15+00:00
- Post Title: Re: Help with The Godfather II .str files

So it seems that the only problem you may have now with packing is making compressed file smaller or equal original to be able to replace it in archive.
I think that I have solved that issue, explanation below.

I have checked refpack-brute-force once again and it seems that it works fine, but the author didn't attach any progress tracking,
so both of us probably thought that tool is broken. 
I made some minor changes to the source and now progress can be tracked [https://i.imgur.com/tjnFxeO.png](https://i.imgur.com/tjnFxeO.png)
It will take some time (like 5-10 minutes), but it works and it will output file smaller than orginal. [https://i.imgur.com/bRxydAa.png](https://i.imgur.com/bRxydAa.png)

If you need this new file to match original size (131 000), just fill the file with zeroes at the end and that should do the trick.

Updated refpack-brute-force code is in the attachment with compiled executable ready to use.
[refpack-brute-force.zip](https://xentaxbackup.github.io/file/19398_refpack-brute-force.zip)
## Post #18
- Username: venixuc
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 13, 2019 10:00 am
- Post datetime: 2021-01-27T01:12:32+00:00
- Post Title: Re: Help with The Godfather II .str files

> Updated refpack-brute-force code is in the attachment with compiled executable ready to use.

This one works! But it takes some extra steps to avoid game crashing. 

The only way to reimport modified kapR into the .str is by using dead_space_3.bms script. This script, however, reads the NAM_1.dat inside the archive from B8 FF 01 00; the file compressed with refpack-brute-force doesn't have this. 

Inside the .str, the content from 00000040 to 0000004F is 6B 61 70 52 B8 FF 01 00 10 FB 03 65 DF E2 4C 43 (kapR¸˙...ű.eßâLC). After using dead_space_3.bms to reimport the kapR compressed with refpack-brute-force, the "B8 FF 01 00" is overwritten, and 4 extra zerobytes are added at the end, before "COHSÔ...TADSbal Borbon" string at the beginning of NAM_2.bal. 

This crashes the game. But the workaround is simple. It's necessary to add those 4 bytes manually between 6B 61 70 52 and 10 FB 03 65, and remove 4 zerobytes at the end. Then it fully works, the game doesn't crash and the text in game is displayed properly.

This wraps up the compression; now, it's possible to edit text and test the results.

Just one thing remains. How to find the string pointer inside decompressed kapR? The first text string is "1", followed by "Specs", then "Choose a hand accessory style", and so on. The first pointers are 88 1B, 8A 1B and 90 1B. 

But, the names are located relatively far from those first strings. The Specs string starts at 00011B8A, while "Big Greenie" Grinberg starts at 00018363 (viewed with HxD).

So, how to find a pointer of "Big Greenie" Grinberg string?
## Post #19
- Username: venixuc
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-27T15:29:20+00:00
- Post Title: Re: Help with The Godfather II .str files

> This wraps up the compression; now, it's possible to edit text and test the results.
Great!


> So, how to find a pointer of "Big Greenie" Grinberg string?
I have created a text exporter that will make it easier for you.
It outputs data in four columns - ID, pointer offset, text offset and text.
[https://github.com/bartlomiejduda/Tools ... xt_Tool.py](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/The%20Godfather/TheGodfather_text_Tool.py)

So for example pointer for text "Big Greenie" Grinberg is at offset 41196.
[https://i.imgur.com/S92tDGd.png](https://i.imgur.com/S92tDGd.png)
## Post #20
- Username: venixuc
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 13, 2019 10:00 am
- Post datetime: 2021-01-28T01:38:53+00:00
- Post Title: Re: Help with The Godfather II .str files

> I have created a text exporter that will make it easier for you.
>
> It outputs data in four columns - ID, pointer offset, text offset and text.
>
> https://github.com/bartlomiejduda/Tools ... xt_Tool.py

This one is great. It's basically vital for finding pointers.

Now, in one of your earlier posts, you wrote:

> As for pointers, I have explained it with screenshots earlier
>
> https://i.imgur.com/poy87uD.png
>
> https://i.imgur.com/5glpvrs.png
>
> 
>
> You only need to change values. For example you have "Specs" word with pointer 7050.
>
> When you change it to 7052, game will read this as "ecs".
>
> But ot will give you of course 2 extra characters to use in the previous string.

Here are screenshots of "Big Greenie" Grinberg pointer, at offset 0000A0EC (value 63 83):

[https://ibb.co/z6dHmMp](https://ibb.co/z6dHmMp) (Little endian)

[https://ibb.co/GWxSFY4](https://ibb.co/GWxSFY4) (Big endian)

Since increasing pointer value makes the string shorter, then decreasing it should make it longer (by reading fragments of previous string). Does this mean that pointers mark beginning of the string, while null terminators mark its end?

I don't know if you played the game; it has a "Don's View", where various things can be viewed - including "Family Tree" and businesses (with owners). The very first string I changed was "Your Family" (string length 12) at offset 00012F44; I changed it to "Corleone" (string length 9) without editing pointers, I just filled the remaining bytes with zeroes - and the text was properly shown in game.
So the player family name now was Corleone instead of Your Family; the business ownership text was also changed, since it also reads from the same offset - for example, instead of reading Appliance King - Controlled by Your Family it reads Appliance King - Controlled by Corleone.

But it worked this way because I didn't edit previous or next string. 
Again, i'll take the first 2 Corleone names for example; changing "Big Greenie" Grinberg to Alessandro Esposito (length 23 to 20) and Michael Galli to Virgilio Zingaro (length 14 to 17). The pointer value for the first name is 63 83 (25475 for int16/uint16) and 7A 83 (31363 for int16/uint16) for the next one. 

Michael Galli (Virgilio Zingaro) after pointer editing in game:

[https://ibb.co/bXcqbKZ](https://ibb.co/bXcqbKZ) (original)

[https://ibb.co/NYjSCx9](https://ibb.co/NYjSCx9) (edited)

Alessandro Esposito string works just well without pointer editing, since its beginning isn't moved. The screenshots for this one are missing because I forgot to take a screenshot in game, he was spawned first and I was focused on finding Zingaro.

The obvious limits for editing the decompressed file are file size and total number of strings. Are these the only limits?
## Post #21
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-28T11:49:31+00:00
- Post Title: Re: Help with The Godfather II .str files

> Does this mean that pointers mark beginning of the string, while null terminators mark its end?
Yes, exactly.

> The obvious limits for editing the decompressed file are file size and total number of strings. Are these the only limits?

Yes.
## Post #22
- Username: venixuc
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 13, 2019 10:00 am
- Post datetime: 2021-01-29T00:56:43+00:00
- Post Title: Re: Help with The Godfather II .str files

Well, the game was released in April 2009 - if we exclude the trainers and graphic enhancement (which is also an "external" mod like Silent's Patch), it took nearly 12 years to be able to mod it. Was it because it never became as popular as several other games of its genre, or because the file formats weren't easy to reverse, or both, I don't know. 

I started playing it in 2015; by that time, the online mode was already history - not that I would've played it anyways, since I'm not into online gaming. But, I've stumbled upon numerous sites where people discussed translating the game into other languages - to this day, no one succeded. This means that there are still people who care about this game (offline, single player mode). 

Since the English localization is everything I need, I definitely won't be translating it; I'm only interested in editing names. However, I believe that this topic, with all the information, screenshots and attachments, is a great place to start for anyone who may be interested in translating the game into their language.

ikskoks, thanks for your patience and time you invested in this topic.
## Post #23
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-29T09:08:56+00:00
- Post Title: Re: Help with The Godfather II .str files

> ikskoks, thanks for your patience and time you invested in this topic.

Sure, no problem.
## Post #24
- Username: venixuc
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 13, 2019 10:00 am
- Post datetime: 2021-01-31T01:29:41+00:00
- Post Title: Re: Help with The Godfather II .str files

One last thing. When refpack-brute-force is used for compression, the file size is 125 kb as opposed to 127 kb. There is no problem in reimporting the smaller file into .str.

But, it compresses it in a way that after compressed data, there are exactly 2901 zerobytes added during reimporting to match the original size - this is relatively large waste of space; these extra bytes could be used for replacing shorter strings with longer ones.

I decided to test that out, knowing what could happen - I replaced the 12-characters long string with another one (19 characters long) by overwriting it in hex editor,  and removed 7 zerobytes. When I launched the game, it didn't crash; but as I expected, the text stored after that string was displayed incorrectly due to the strings being shifted without pointer editing (every pointer after that string has to have its value increased by 7).

The last pointer value inside decompressed file is at offset 00011B84, so doing this manually would take ages. Is there a faster way to update the pointer values after inserting a longer string?
## Post #25
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-31T10:11:41+00:00
- Post Title: Re: Help with The Godfather II .str files

> Is there a faster way to update the pointer values after inserting a longer string?

Yeah, you could write text importer which automates this task and it changes pointers during program execution.
## Post #26
- Username: venixuc
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 13, 2019 10:00 am
- Post datetime: 2021-02-01T00:53:09+00:00
- Post Title: Re: Help with The Godfather II .str files

> Yeah, you could write text importer which automates this task and it changes pointers during program execution.

That would be the best solution - basically a custom tool. However, it would require not only understanding the pointers and text strings, but also the data above them. According to [https://www.metadata2go.com/](https://www.metadata2go.com/), the decompressed file header looks like this:
[https://ibb.co/7n8ZhvQ](https://ibb.co/7n8ZhvQ)
I don't know what the data between the header and the pointers block represents. 

When I edit a string and move its beginning, I only edit the uint16 pointer value - the other values update automatically. While the last pointer is at offset 00011B84, the last important pointer is at offset 0000F0A0 (it belongs to last text string stored inside NAM_1.dat - Cristo); other pointers belong to text strings located in NAM_2.bal.

Considering the fact that editing kapR and compressing it to NAM_1.dat mustn't move the NAM_2.bal content (it would mean that the .str size is changed), the pointers from 0000F0A4 to 00011B84 don't require value editing.

I never considered a custom text importer for kapR. If I replaced, for example, the string Steve Szakal (12 characters) at offset 00018CB1 (pointer at 0000A364) with 19-characters long string, all pointers from 0000A368 to 0000F0A4 would require having their values increased by 7.

I thought of something like this: replacing the string with hex editor, then running some kind of external script which would increase (or decrease) the pointer values at required offsets. It would be necessary to repeat this for every longer string, but still  easier than reversing the kapR and writing a custom tool (in my opinion).

I'm not quite sure what to do; but if everything else fails, I'll go back to manual pointer editing.
------------------------------------------------------------------------------------------------------------------------------------------------

The Granados mobster names are located inside NAM_2.bal file. That file is just the plain text; the pointers are inside NAM_1.dat. How to find corresponding NAM_2.bal pointers inside kapR?
## Post #27
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-02-01T17:30:02+00:00
- Post Title: Re: Help with The Godfather II .str files

> I thought of something like this: replacing the string with hex editor, then running some kind of external script which would increase (or decrease) the pointer values at required offsets. It would be necessary to repeat this for every longer string, but still easier than reversing the kapR and writing a custom tool (in my opinion).

That could work, but why bother, when you lose all benefits of the text importer.

I would do it like that:

#Export# (that's basically similar logic to the one from my tool in Python)
1. Read unknown data block from kapr and save it as "temp.bin"
2. Read pointer table
3. Read all texts using pointer table
4. Save text in file "out.txt"

#Import
1. Read data from "temp.bin"
2. Read "out.txt"
3. Calculate new pointers from string lengths
4. Save data from temp.bin, then new pointer table and then new texts as a new "kapr" file.
5. (optionally) do some checks on file size etc.
6. (optionally) automate it even more by executing brute-force refpack at the end.

> The Granados mobster names are located inside NAM_2.bal file. That file is just the plain text; the pointers are inside NAM_1.dat. How to find corresponding NAM_2.bal pointers inside kapR?

Why do you think pointers are in NAM_1.dat? I don't see any pointers at the beginning of this unknown data block.
Besides, BAL file uses completely different format (string + NULL), so I think that pointers are somewhere in the game executable.
## Post #28
- Username: venixuc
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 13, 2019 10:00 am
- Post datetime: 2021-02-02T00:54:45+00:00
- Post Title: Re: Help with The Godfather II .str files

> Why do you think pointers are in NAM_1.dat? I don't see any pointers at the beginning of this unknown data block.

I don't think that the NAM_2.bal pointers are within the unknown data block inside NAM_1.dat; that wouldn't make sense, since that block is located above pointers block. I think that NAM_2.bal pointers are inside NAM_1.dat's pointer block.

When I used your Python script to get string pointers from NAM_1.dat, the last one listed was at offset 0000F0A0 (or 00061600):
[https://ibb.co/mX7sdKH](https://ibb.co/mX7sdKH)

However, that pointer isn't the last one inside NAM_1.dat; there are plenty more pointers from 0000F0A4 to 00011B84:

The next one:
[https://ibb.co/g6Djmgw](https://ibb.co/g6Djmgw)

The last one, before first text strings:
[https://ibb.co/LPfmLV3](https://ibb.co/LPfmLV3)

Roughly 2/3 of the text is inside NAM_1.dat, the remaining third is inside NAM_2.bal. I strongly suspect that NAM_2 is actually .dat file, the .bal extension could be derived from first 4 bytes (bal ):
[https://ibb.co/GFwjmJZ](https://ibb.co/GFwjmJZ)

And, the last string inside NAM_1.dat is Cristo, but that isn't a standalone string; the full string is Cristobal Borbon - bal Borbon fragment is inside NAM_2. There is no null terminator after Cristo string inside NAM_1.dat, nor before bal Borbon inside NAM_2 - this probably means that pointer at 0000F0A0 covers the whole string.

If that's the case, then pointer at 0000F0A4 should belong to Cody Flowers string - the first standalone string inside NAM_2.

Also, this part of your Python script caught my attention:

```
    num_of_entries = 6324       # for decompressed NAM_1.DAT from The Godfather
```


So I decided to merge kapR with NAM_2.bal:
[https://ibb.co/dMcVD1D](https://ibb.co/dMcVD1D)
This could be useful for connecting the remaining pointers with their strings - but num_of_entries value has to be changed.

I've attached kapR merged with NAM_2. What would be the new value for num_of_entries?


> That could work, but why bother, when you lose all benefits of the text importer.

My programming skills aren't the best - if I decided to write something as complex as that, it would probably take more time than editing every single pointer manually. And I obviously can't ask you to do it, because I'm not the only one on this forum who needs help.
But if you get some time, the pointer value-changing script would be enough. Don't take this as a request, neither.
[kapR - merged with NAM_2.rar](https://xentaxbackup.github.io/file/19445_kapR - merged with NAM_2.rar)
## Post #29
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-02-02T09:11:24+00:00
- Post Title: Re: Help with The Godfather II .str files

> I don't think that the NAM_2.bal pointers are within the unknown data block inside NAM_1.dat; that wouldn't make sense, since that block is located above pointers block. I think that NAM_2.bal pointers are inside NAM_1.dat's pointer block.

> However, that pointer isn't the last one inside NAM_1.dat; there are plenty more pointers from 0000F0A4 to 00011B84:

Yes, of course, now I see it.  You are right. Good catch with this one. To be honest, I haven't noticed it earlier.

> I've attached kapR merged with NAM_2. What would be the new value for num_of_entries?

New value should be 9069. That will cover merged files.

> But if you get some time, the pointer value-changing script would be enough. Don't take this as a request, neither.
I'll see what I can do. No promises, but I will check it.
## Post #30
- Username: venixuc
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 13, 2019 10:00 am
- Post datetime: 2021-02-03T02:40:53+00:00
- Post Title: Re: Help with The Godfather II .str files

Ok.
Now, excluding the header, the .str file is divided in 3 chunks: NAM_1.dat, NAM_2.bal and NAM_3.dat. Their sizes are 127 KB (131,004 bytes), 67.1 KB (68,808 bytes) and 60.7 KB (62,240 bytes) respectively. 

It appears that not only the .str archive size matters, but also the sizes of these individual files. The kapR (decompressed NAM_1.dat) size is 217 KB (222,687 bytes); refpack-brute-force's higher compression ratio creates 2901 spare zerobytes at the end of compressed file, giving an opportunity to make several strings longer than original which then requires updating pointer values for NAM_1.dat strings. 

With NAM_2.bal, the case is different. The text inside it isn't compressed, and the file itself doesn't have spare zerobytes at its end. It can be compressed and reimported into .str, but then the text inside it appears as compressed garbage in game.

The NAM_3.dat file consists only of zerobytes; it has "LLIF" identificator at the beginning (FILL) which means that this file's purpose is keeping the .str size in check.

I tried to use NAM_3.dat's zerobytes as spare ones by making one string inside NAM_2.bal 2 bytes longer,and removing 2 zerobytes at NAM_3.dat's end. When I launched the game, it didn't load and it didn't crash; instead, it froze. No keyboard combination worked when I tried exiting to desktop, the only way out was to use the reset button. 

So, when .str size is preserved but with altering size of its chunks, the game locks up - it obviously doesn't have an error statement for this type of situation and gets stuck after unsuccessfull loading and unsuccessfull crashing.

Is it possible that unknown data block inside NAM_1.dat contains size checks for these 3 chunks? If it does, then it would (theoretically) be possible to edit size checks for NAM_2.bal and NAM_3.dat in order to make the former larger and latter smaller.
## Post #31
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-02-03T08:50:16+00:00
- Post Title: Re: Help with The Godfather II .str files

> Is it possible that unknown data block inside NAM_1.dat contains size checks for these 3 chunks?
It is possible, but you don't know it for sure until you reverse engineer the whole file format.
## Post #32
- Username: venixuc
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 13, 2019 10:00 am
- Post datetime: 2021-02-04T01:26:15+00:00
- Post Title: Re: Help with The Godfather II .str files

> you don't know it for sure until you reverse engineer the whole file format.
Alright. I'll see which option is better - doing this or simply keeping an eye on number of characters in Granados names block.
The latter is definitely going to be different than editing other 5 names blocks (located in NAM_1.dat) because I don't have spare zerobytes in NAM_2.bal; with NAM_1.dat's blocks and almost 3000 spare zerobytes created during compression, editing can be done (almost) without a care in this world (I have around 250 additional characters per block, so no worries here).

Unless I find a way to make the game read compressed NAM_2.bal content properly. This would've created 34130 extra zerobytes, but only if it can be done at all.
## Post #33
- Username: venixuc
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 13, 2019 10:00 am
- Post datetime: 2021-02-25T01:17:44+00:00
- Post Title: Re: Help with The Godfather II .str files

So, I couldn't figure out what's going on with the unknown data block inside decompressed NAM_1.dat - the only thing I found out was the fact that it contains font characters.

But I managed to create new Granados mobster names and keep the total number of characters (2787) intact. I'll have to do the same thing with Roth Syndicate mobsters, since their names are located in NAM_2.bal as well.

As for the NAM_1.dat blocks, I created new names for Corleones (generic mobsters and recruits), Rosatos (Carmine and Tony) and Manganos; only the Almeidas remain.

After that, I'll import these names into NAM_1.dat (for compressed strings) and .str archive (for NAM_2.bal strings), and adjust the pointer values; so everything about editing this text .str archive is pretty much clear.
______________________________________________________________________________________________________
In the meantime, I wanted to try something else. While changing character clothes (player or made men) there is an option for changing the clothes color. I'd like to edit that color palette by replacing several colors with shades of gray and red, and I'd also like to add the black color.

Here are some screenshots:

[https://ibb.co/FBZBmWn](https://ibb.co/FBZBmWn)

[https://ibb.co/YtkJyKv](https://ibb.co/YtkJyKv)

The problem is, I don't know the rgb values for those colors. I've been searching the ram with keywords such as "color", "rgb", "hsv" and  "hsl" and looking up the neighboring values (using hex editor) but I couldn't find anything useful. I suspect that these values are stored in allcharacters.str or globals_global.str, but I don't know which values I should be looking for so I decided to find them in the active memory first.

The options in the clothes editor are highlighted; in the first screenshot, the color option is highlighted and the color is lighter, and in another one I highlighted the last option which made the color dimmer. This highlighter affects the displayed color, so I'm unable to simply take a screenshot and use the color picker to get the rgb value.

So, I'm trying to find something in the ram without knowing its value, or even the address. Could Cheat Engine be useful for this?
## Post #34
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-02-25T10:36:43+00:00
- Post Title: Re: Help with The Godfather II .str files

> Could Cheat Engine be useful for this?
Yeah, probably. You can scan for the unknown value first, then change the color, then scan again and repeat that until you find correct value.
## Post #35
- Username: Jack Sparrow
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Sep 03, 2020 8:13 pm
- Post datetime: 2021-02-25T18:53:08+00:00
- Post Title: Re: Help with The Godfather II .str files

Send me language files I have a special tool
## Post #36
- Username: venixuc
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 13, 2019 10:00 am
- Post datetime: 2021-02-25T23:39:26+00:00
- Post Title: Re: Help with The Godfather II .str files

> You can scan for the unknown value first, then change the color, then scan again and repeat that until you find correct value.

The problem is, I'm unsure what data type I should scan for (binary, 4 bytes, 8 bytes, grouped etc.). When I scan the memory, the values aren't really helpful - I change the color and repeat the scan but I can't see anything that looks like rgb value. I'm definitely confused; also I can't find the way to run this game in windowed mode.


> Send me language files I have a special tool

You mean the .str archive? It's attached in my first post on this topic, along with its chunks extracted with QuickBMS (using dead_space_3.bms). I'm not trying to translate the game, I just want to change mobster names. Something like this:

[https://ibb.co/bXcqbKZ](https://ibb.co/bXcqbKZ) (original)

[https://ibb.co/NYjSCx9](https://ibb.co/NYjSCx9) (edited)

And please, just post in this topic, no need for private messages - any valuable information should be publically available, in case anyone else needs help with this.  

Anyways, if the attached files are somehow damaged or unavailable, let me know and I'll upload them again. Thanks for joining the discussion.
## Post #37
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-02-26T08:00:51+00:00
- Post Title: Re: Help with The Godfather II .str files

> I'm unsure what data type I should scan for (binary, 4 bytes, 8 bytes, grouped etc.)
That's never clear on the beginning. You need to guess it.
I would start with 4 bytes int, then 2 bytes int, then float, then double, then any other.

> also I can't find the way to run this game in windowed mode.
Did you try to use DXWnd?
## Post #38
- Username: venixuc
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 13, 2019 10:00 am
- Post datetime: 2021-02-27T00:19:46+00:00
- Post Title: Re: Help with The Godfather II .str files

> That's never clear on the beginning. You need to guess it.
>
> I would start with 4 bytes int, then 2 bytes int, then float, then double, then any other.

Ok, but when one of the following value types - "binary", "string", "grouped" or "array of byte" is selected, there is no option for "unknown initial value" scan. Obviously, the "string" type isn't the right one for this, but what about the other three? I checked the ram with hex editor, and rgb value isn't stored as rgb (r,g,b) (like carcols in gta games); I think it could be like this: B2 40 38 (just an example). Hypothetically, if the correct value type is "byte" or "2 bytes", and the rgb value is split, then this could be impossible to detect.

> Did you try to use DXWnd?

Yes, but it crashes very often with this game. I tested some other games (gta sa/vc, manhunt/manhunt2) and they run fine. BTW, is it necessary to use windowed mode? So far I've been minimizing the game in order to use Cheat Engine - can this affect the scan results?
## Post #39
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-02-27T10:40:44+00:00
- Post Title: Re: Help with The Godfather II .str files

To be honest I'm not cheat engine expert, I did only few simple cheats in ASM :p
There is a forum about cheat engine when you could get better help than from me [https://forum.cheatengine.org/](https://forum.cheatengine.org/)


But I think that you could keep guessing with all types as I said or you could search for 1 byte and use "Value between" option to narrow your results.
For example if you will search for "R" byte from your RGB value and you choose red color or pink color in game's color picker, you will know that "R" byte will be high, so you can choose value between 170 and 255.


As for DXWnd, I had also lot of problems with it when I was using it with older games.
I can only tell you that there are many configuration options for DXWnd, you can see many hooks, hacks and fixes there, so maybe it's worth to try change some options.

And I think that you don't have to minimize the game, you can just use ALT+TAB (but it sometimes depends on the game).
## Post #40
- Username: venixuc
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 13, 2019 10:00 am
- Post datetime: 2021-02-28T01:00:01+00:00
- Post Title: Re: Help with The Godfather II .str files

I was wondering if rgb values are stored similarly in GTA SA and GF2, so I checked GTA SA's ram (with hex editor) during mod garages visit to see how carcols.dat is written in memory there. For example, color no. 86 rgb value is 46,91,32; so I searched for 34 36 2C 39 31 2C 33 32 (surmising that character has its own hex value, decoded view 46,91,32) and 2E 2C 5B 2C 20 (surmising that entire numbers are stored as hex, decoded view .,[, ).

I couldn't find the color value with this type of search. So, if the rgb value isn't stored in ram like this, then how could it be stored? Before I try to find the unknown rgb value, I have to make sure that I can find the known one.
## Post #41
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-02-28T11:03:09+00:00
- Post Title: Re: Help with The Godfather II .str files

> So, if the rgb value isn't stored in ram like this, then how could it be stored?
As I said, I don't have enough knowledge about this topic to help you.

Better check those topics
[https://www.cheatengine.org/forum/viewt ... 15b5cc4bd3](https://www.cheatengine.org/forum/viewtopic.php?p=5690978&sid=a7dc5d6815e376ba4a334c15b5cc4bd3)
[https://reverseengineering.stackexchang ... s-beginner](https://reverseengineering.stackexchange.com/questions/13311/how-would-i-find-a-colors-memory-address-beginner)

or create a new one on cheat engine forum.
## Post #42
- Username: venixuc
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 13, 2019 10:00 am
- Post datetime: 2021-02-28T23:58:41+00:00
- Post Title: Re: Help with The Godfather II .str files

> I don't have enough knowledge about this topic to help you.

Ok. If I somehow get this done, i'll return to post the rgb values and (maybe) to analyze the .str archive that contains them.

Thanks for helping so far.
_____________________________________________________________________________________________________
And here's a small tip about NAM_2.bal text.
While it's not possible to make this chunk larger, it's still possible to make some strings longer, by "hijacking" bytes from text strings reserved for multiplayer mode (since it's dead anyways).
## Post #43
- Username: venixuc
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 13, 2019 10:00 am
- Post datetime: 2022-02-10T14:19:13+00:00
- Post Title: Re: Help with The Godfather II .str files

I have a small update regarding the colors in the apparel editor menu. As it turned out, the colors in RAM are stored as single 4-byte floats. And the colors have to be highlighted in the menu before taking a screenshot to get the right RGB value with color picker.

For example, one shade of pink (203,147,141 or #cb938d) is stored as 00 00 4b 43 00 00 13 43 00 00 0d 43. This one:
[https://ibb.co/R2SBys2](https://ibb.co/R2SBys2)
Other types of scans produce no interesting results, or no results at all. I used the HxD since I find it more user-friendly than Cheat Engine.

After I replaced 00 00 4b 43 00 00 13 43 00 00 0d 43 with 00 00 00 00 00 00 00 00 00 00 00 00, I partially got the result I wanted - the pink color in the box was changed to black. But not the clothes color - it stayed pink, even after reloading the menu.

I've been doing this with an assumption that clothes textures are white in the game files and that they rely on some kind of color .dat files. This discovery makes me question that; could it be that in fact the textures are colored, and the colors menu is used merely for reference?

I should also mention the fact that I wasn't able to fully extract the globals_global.str or allcharacters.str files with dead_space_3.bms - it always ends up with an error. These files are 40 MB large, and even when their contents are partially extracted, there are around 5000 files (mostly .dat, likely packed with refpack).
