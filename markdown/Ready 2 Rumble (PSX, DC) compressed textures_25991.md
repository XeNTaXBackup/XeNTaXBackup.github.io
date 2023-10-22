## Post #1
- Username: IlDucci
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 20, 2014 10:01 pm
- Post datetime: 2022-11-14T21:15:50+00:00
- Post Title: Ready 2 Rumble (PSX, DC) compressed textures

Greetings. I've been trying to identify the hidden compression found on the textures of Ready 2 Rumble 1 for the PSX (though I suspect it is also used on both the sequel and their versions for Dreamcast). This file in particular contains the first screen with some legal credits.

I have tried to put a uncompressed texture for modding, but the game expects it compressed.

Here's the specs I could get from the header format, which will include info from the uncompressed TIM equivalents:

```

--------------------
ELEMENT HEADER
--------------------

0x04 bytes = Element's Magic word
0x04 bytes = File size
0x04 bytes = Possible file format flag:
 - 0x00 = models, anims
 - 0x01 = compressed TIM
 - 0x02 = uncompressed TIM
0x04 bytes = Possible file content flag
 - 0x01 = anims
 - 0x02 = TIM (both compressed and uncompressed)
 - 0x0D = models

0x04 bytes = File size
0x0C bytes = File name (Windows 3.1 method)

TIMs may have a sequence of pointers that contain a list of subTIMs within a TIM.
 - 0x04 bytes = amount of pointers
 - 0x04 bytes = size of this mini block
If the first value is higher than 1, will mean that there is more than one TIM and that the pointer list will extend, 0x04 bytes per pointer, all of them relative to the beginning of the file.
```


The other thing I know is that the first thing that appears in the TIM area is the uncompressed size of the file. After that, I am lost.
[legal.tim.midway.zip](https://xentaxbackup.github.io/file/23030_legal.tim.midway.zip)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-11-20T00:17:23+00:00
- Post Title: Ready 2 Rumble (PSX, DC) compressed textures

I am not able to help you with the compression - in my opinion it may be custom.
But I can help you at least with the file format and automatization of your research   

Here is the file format -->  [http://wiki.xentax.com/index.php/Ready_ ... Boxing_BIN](http://wiki.xentax.com/index.php/Ready_2_Rumble_Boxing_BIN)
And here is the script to extract\import data --> [https://github.com/bartlomiejduda/Tools ... script.bms](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/Ready%202%20Rumble%20Boxing/Ready_2_rumble_BIN_script.bms)

Script is capable of dumping valid TIM/VAG files. All TIM files can be easily opened in Noesis and all VAG files can be opened in foobar2000 with vgmstream plugin.

BIN archives from this game are tricky and I had some issues with figuring out proper way for parsing data.
For example, I wasn't able to match files with the directory - game must have some internal logic for this.

I've found a few interesting samples.
For example RINGS\GYM03.BIN file stores VAG, TIM and PHM entries
and AAERO.BIN stores TIM, MODL and MLST entries.

Also compressed TIM image from LEGAL.BIN archive seem to be very similar to TWD files from "SELECT" directory.
## Post #3
- Username: IlDucci
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 20, 2014 10:01 pm
- Post datetime: 2022-11-20T12:51:05+00:00
- Post Title: Ready 2 Rumble (PSX, DC) compressed textures

> Reply from ikskoks ↑Sun Nov 20, 2022 8:17 am at Sun Nov 20, 2022 8:17 am
>
> 
I am not able to help you with the compression - in my opinion it may be custom.
But I can help you at least with the file format and automatization of your research
Thank you for helping out with the formats. My main target, besides that legal file, is the shell files, as they contain the fonts of the game, needed for a proper translation.

I have not taken too much of a look on DC, but I did take a look on the Nintendo 64 version as well, even though the formats seem to differ, but the N64 seems to use the standard zlib compression for its files (thanks to Zoinkity for its Midwaydec compressor/decompressor). Strange that this game uses standard zlib when Midway does have four LZ/LZSS variants listed in the Midwaydec tool and other games by Point of View seem to use some sort of derivative of RLE.
