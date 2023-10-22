## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-04-21T04:19:01+00:00
- Post Title: Sine Mora (XBLA) *.bin

Hello everyone! I just stumbled upon a large number of *.bin files from the above game. I can't file any offsets/sizes/names anywhere to extract the contents. Can anyone please take a look at these? Any help is highly appreciated!
Here are samples: [http://www.sendspace.com/file/8onoj7](http://www.sendspace.com/file/8onoj7)
Thanks!
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2012-11-11T13:14:51+00:00
- Post Title: Sine Mora (XBLA) *.bin

The game is now out for PC. Maybe someone could please take a look and try to make a decrypter/unpacker for the game using the executable
## Post #3
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2012-11-11T16:17:56+00:00
- Post Title: Sine Mora (XBLA) *.bin

.bin file format:

```
  int hash1;
  int hash2;        // hash1..hash2 - filename
  int hash3;        // hash3 - dirname
  int size;         // unpacked size
  int zsize;        // packed size
  char data[zsize];
}

// repeat while EOF
```

data starts with one of the following bytes: - 63, 64, 80, 92, 95, 98, 113, 148, 161, 192, 208, 211, 226, 227, 240, 241, 242, 243, 244, 245, 246, 247, 248, 249, 251, 252, 253, 254, 255.

i think this is a LZ*-like compression.
## Post #4
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2012-11-11T16:39:08+00:00
- Post Title: Sine Mora (XBLA) *.bin

Don't know if xbox version has the same compression, but PC version uses LZ4.
## Post #5
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2012-11-11T16:42:49+00:00
- Post Title: Sine Mora (XBLA) *.bin

> Reply from merlinsvk
>
> PC version uses LZ4.
confirm that.

p.s.
i think what quickbms 0.5.15b have a error in LZ4 part, files are unpacked with "compressed" sizes:
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-11-11T19:37:09+00:00
- Post Title: Sine Mora (XBLA) *.bin

Well here script for unpack.

```
# 
# Written by Ekey (h4x0r) 0.1
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

comtype LZ4

for
    get FILENAMEHASH long
    get HASH2 long
    get FILEEXTHASH long
    get SIZE long
    get ZSIZE long
    savepos OFFSET
    string NAME p= "%08X" FILENAMEHASH
	
    if ZSIZE == SIZE
        log NAME OFFSET SIZE
        math OFFSET += SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
        math OFFSET += ZSIZE
    endif

    goto OFFSET
next
```


And tool for generate hash.

Edited: Hash3 its hashed file extension.

Example for prologue.bin

```
FE5F29A1 - Unknown
4DB55A5E (5E5AB54D) - dds
```

[SMHasher_0.1.rar](https://xentaxbackup.github.io/file/5979_SMHasher_0.1.rar)
## Post #7
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2012-11-11T20:26:47+00:00
- Post Title: Sine Mora (XBLA) *.bin

Xbox 360 .BIN files unpack the same as the PC version. I get an Error: Incomplete input file number 0, can't read 4 bytes for both platforms though but I'm assuming it's working properly.

The game has an FMOD .DLL file so I'm guessing it's using FSB containers but I can't seem to find any FSB headers yet.

EDIT: Game uses MP3 for it's audio
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-11-11T20:30:09+00:00
- Post Title: Sine Mora (XBLA) *.bin

> Reply from brendan19
>
> Xbox 360 .BIN files unpack the same as the PC version. I get an Error: Incomplete input file number 0, can't read 4 bytes for both platforms though but I'm assuming it's working properly.
This error for PC too because count files is unknown. Anyway script extract all files.

> Reply from brendan19
>
> The game has an FMOD .DLL file so I'm guessing it's using FSB containers but I can't seem to find any FSB headers yet.
That does not nothing mean. In archives sounds and music in OGG and MP3 format.

Edited: some files for render.bin (extension psc)

```
render/cache/564442de_d77e5f14_6e95a18a_1_windows
render/cache/564442de_d77e5f14_6e95a18a_2_windows
render/cache/5142abd8_d77e5f14_ab8e9822_0_windows
render/cache/5142abd8_d77e5f14_ab8e9822_1_windows
render/cache/5142abd8_d77e5f14_ab8e9822_2_windows
render/cache/5142abd8_d77e5f14_ab8e9822_3_windows
render/cache/5142abd8_d77e5f14_ab8e9822_4_windows
render/cache/5142abd8_d77e5f14_ab8e9822_5_windows
render/cache/5142abd8_d77e5f14_ab8e9822_6_windows
render/cache/5142abd8_d77e5f14_ab8e9822_7_windows
render/cache/5142abd8_d77e5f14_ab8e9822_8_windows
render/cache/5142abd8_d77e5f14_ab8e9822_9_windows
render/cache/5142abd8_d77e5f14_ab8e9822_a_windows
render/cache/5142abd8_d77e5f14_ab8e9822_b_windows
render/cache/5142abd8_d77e5f14_ab8e9822_c_windows
render/cache/5142abd8_d77e5f14_ab8e9822_d_windows
render/cache/5142abd8_d77e5f14_ab8e9822_e_windows
render/cache/5142abd8_d77e5f14_ab8e9822_f_windows
render/cache/5142abd8_d77e5f14_ab8e9822_10_windows
render/cache/5142abd8_d77e5f14_ab8e9822_11_windows
render/cache/5142abd8_d77e5f14_ab8e9822_12_windows
render/cache/564442de_f9bb33d_6e95a18a_0_windows
render/cache/564442de_f9bb33d_6e95a18a_1_windows
render/cache/5142abd8_f9bb33d_69940a84_0_windows
render/cache/5142abd8_f9bb33d_69940a84_1_windows
render/cache/564442de_db14f000_6e95a18a_0_windows
render/cache/564442de_db14f000_6e95a18a_1_windows
render/cache/5142abd8_db14f000_69940a84_0_windows
render/cache/5142abd8_db14f000_69940a84_1_windows
render/cache/564442de_d5d51d0e_6e95a18a_0_windows
render/cache/564442de_d5d51d0e_6e95a18a_1_windows
render/cache/5142abd8_d5d51d0e_69940a84_0_windows
render/cache/5142abd8_d5d51d0e_69940a84_1_windows
render/cache/564442de_aaa5863a_6e95a18a_0_windows
render/cache/564442de_aaa5863a_6e95a18a_1_windows
render/cache/5142abd8_aaa5863a_69940a84_0_windows
render/cache/5142abd8_aaa5863a_69940a84_1_windows
render/cache/564442de_90ec1d9d_6e95a18a_0_windows
render/cache/564442de_90ec1d9d_6e95a18a_1_windows
render/cache/5142abd8_90ec1d9d_69940a84_0_windows
render/cache/5142abd8_90ec1d9d_69940a84_1_windows
render/cache/564442de_c7c8dbec_6e95a18a_0_windows
render/cache/564442de_c7c8dbec_6e95a18a_1_windows
render/cache/5142abd8_c7c8dbec_69940a84_0_windows
render/cache/5142abd8_c7c8dbec_69940a84_1_windows
render/cache/564442de_bb061e49_6e95a18a_0_windows
render/cache/564442de_bb061e49_6e95a18a_1_windows
render/cache/5142abd8_bb061e49_69940a84_0_windows
render/cache/5142abd8_bb061e49_69940a84_1_windows
render/cache/564442de_3d18079f_6e95a18a_0_windows
render/cache/564442de_3d18079f_6e95a18a_1_windows
render/cache/5142abd8_3d18079f_69940a84_0_windows
render/cache/5142abd8_3d18079f_69940a84_1_windows
render/cache/564442de_84add148_6e95a18a_0_windows
render/cache/564442de_84add148_6e95a18a_1_windows
render/cache/5142abd8_84add148_69940a84_0_windows
render/cache/5142abd8_84add148_69940a84_1_windows
render/cache/564442de_7dd158e9_6e95a18a_0_windows
render/cache/564442de_7dd158e9_6e95a18a_1_windows
render/cache/5142abd8_7dd158e9_69940a84_0_windows
render/cache/5142abd8_7dd158e9_69940a84_1_windows
render/cache/564442de_4ed6b5f6_6e95a18a_0_windows
render/cache/564442de_4ed6b5f6_6e95a18a_1_windows
render/cache/5142abd8_4ed6b5f6_69940a84_0_windows
render/cache/5142abd8_4ed6b5f6_69940a84_1_windows
render/cache/564442de_1ae85e6e_6e95a18a_0_windows
render/cache/564442de_1ae85e6e_6e95a18a_1_windows
render/cache/5142abd8_1ae85e6e_69940a84_0_windows
render/cache/5142abd8_1ae85e6e_69940a84_1_windows
render/cache/5142abd8_1ae85e6e_69940a84_2_windows
render/cache/5142abd8_1ae85e6e_69940a84_3_windows
render/cache/5142abd8_1ae85e6e_69940a84_4_windows
render/cache/5142abd8_1ae85e6e_69940a84_5_windows
render/cache/564442de_88c585c5_6e95a18a_0_windows
render/cache/564442de_88c585c5_6e95a18a_1_windows
render/cache/5142abd8_88c585c5_69940a84_0_windows
render/cache/5142abd8_88c585c5_69940a84_1_windows
render/cache/564442de_346d7bcc_6e95a18a_0_windows
render/cache/564442de_346d7bcc_6e95a18a_1_windows
render/cache/5142abd8_346d7bcc_69940a84_0_windows
render/cache/5142abd8_346d7bcc_69940a84_1_windows
render/cache/564442de_64291c52_6e95a18a_0_windows
render/cache/564442de_64291c52_6e95a18a_1_windows
render/cache/5142abd8_64291c52_69940a84_0_windows
render/cache/5142abd8_64291c52_69940a84_1_windows
render/cache/564442de_64291c52_2f0459b6_0_windows
render/cache/564442de_64291c52_2f0459b6_1_windows
render/cache/5142abd8_64291c52_197843dc_0_windows
render/cache/5142abd8_64291c52_197843dc_1_windows
render/cache/564442de_e1b051d9_6e95a18a_0_windows
render/cache/564442de_e1b051d9_6e95a18a_1_windows
render/cache/5142abd8_e1b051d9_69940a84_0_windows
render/cache/5142abd8_e1b051d9_69940a84_1_windows
render/cache/564442de_f9e6da_6e95a18a_0_windows
render/cache/564442de_f9e6da_6e95a18a_1_windows
render/cache/5142abd8_f9e6da_69940a84_0_windows
render/cache/5142abd8_f9e6da_69940a84_1_windows
render/cache/564442de_f190e29_6e95a18a_0_windows
render/cache/564442de_f190e29_6e95a18a_1_windows
render/cache/5142abd8_f190e29_69940a84_0_windows
render/cache/5142abd8_f190e29_69940a84_1_windows
render/cache/5142abd8_d77e5f14_69940a84_0_windows
```
## Post #9
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-11-12T01:00:31+00:00
- Post Title: Sine Mora (XBLA) *.bin

Thanks for the script!
## Post #10
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-11-12T02:00:17+00:00
- Post Title: Sine Mora (XBLA) *.bin

Here's my enhanced script with correct termination, type detection and some other minor changes. =)

```
#
# Base script by Ekey (h4x0r) 0.1
# http://www.progamercity.net
#
# Enhancements by AlphaTwentyThree
#
# script for QuickBMS http://quickbms.aluigi.org


include "func_getTYPE.bms"
comtype LZ4
get FSIZE asize
for
	get HASH1 long
	get HASH2 long
	get UNK long
	get SIZE long
	get ZSIZE long
	savepos OFFSET
	if ZSIZE == SIZE
		log MEMORY_FILE OFFSET ZSIZE
	else
		clog MEMORY_FILE OFFSET ZSIZE SIZE
	endif
	get NAME basename
	string NAME += "/"
	string HASH1 p= "%08x" HASH1
	string HASH2 p= "%08x" HASH2
	string NAME += HASH1
	string NAME += "_"
	string NAME += HASH2
	callfunction getTYPE 1
	string NAME += EXT
	get SIZE asize MEMORY_FILE
	log NAME 0 SIZE MEMORY_FILE
	math OFFSET += ZSIZE
	if OFFSET < FSIZE
		goto OFFSET
	else
		cleanexit
	endif
next
```

You can find my func_getTYPE.bms here: [viewtopic.php?f=13&p=69577#p69577](http://forum.xentax.com/viewtopic.php?f=13&p=69577#p69577) (needed revision: 2012-11-12 and up).
## Post #11
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2012-11-12T02:04:29+00:00
- Post Title: Sine Mora (XBLA) *.bin

can anybody make screenshot of any unpacked texture?
## Post #12
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-11-12T15:39:17+00:00
- Post Title: Sine Mora (XBLA) *.bin

Some textures after decompress are cut off
## Post #13
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2012-11-12T15:43:15+00:00
- Post Title: Sine Mora (XBLA) *.bin

> Reply from Ekey
>
> Some textures...
some = all, textures = files, because 
> quickbms 0.5.15b have a error in LZ4 part, files are unpacked with "compressed" sizes ;)

who know how to contact aluigy?
## Post #14
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-11-12T18:19:27+00:00
- Post Title: Sine Mora (XBLA) *.bin

dunno text files decompressed good. 

```
web:    aluigi.org
```
## Post #15
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2012-11-13T16:21:02+00:00
- Post Title: Sine Mora (XBLA) *.bin

There are segments of the music missing I've found as well.
## Post #16
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-11-19T19:27:03+00:00
- Post Title: Re: Sine Mora (XBLA) *.bin

Currently work on unpacker 
[smbin.PNG](https://xentaxbackup.github.io/file/6010_smbin.PNG)
## Post #17
- Username: CONSTANT EGO
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon May 28, 2012 3:19 am
- Post datetime: 2012-11-20T05:46:14+00:00
- Post Title: Re: Sine Mora (XBLA) *.bin

> Reply from Ekey
>
> Currently work on unpacker

Can you upload this tool? Please.
## Post #18
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-11-20T15:39:57+00:00
- Post Title: Re: Sine Mora (XBLA) *.bin

Not finished yet
## Post #19
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-11-21T18:45:33+00:00
- Post Title: Re: Sine Mora (XBLA) *.bin

Well here unpacker [here](http://forum.xentax.com/viewtopic.php?p=81182#p81182)
## Post #20
- Username: GARID
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Apr 06, 2011 8:29 pm
- Post datetime: 2012-11-22T08:32:43+00:00
- Post Title: Re: Sine Mora (XBLA) *.bin

> Reply from Ekey
>
> Well here unpacker.

Unpacker and Video with explain

Да мужик, ты крут    и спасибо за унпакер
## Post #21
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-11-22T16:05:48+00:00
- Post Title: Re: Sine Mora (XBLA) *.bin

Download: [see below](http://forum.xentax.com/viewtopic.php?p=92155#p92155)
## Post #22
- Username: DrMefistO
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Feb 03, 2014 8:59 pm
- Post datetime: 2014-02-04T09:06:08+00:00
- Post Title: Re: Sine Mora (XBLA) *.bin

```
1E1EA7D5 = sph
06C0B650 = mp3
5CE18709 = dat
93FF62E0 = psc
17B1DCCE = scb
1E22F830 = bson
D7EBE1E0 = loc
208EF3E0 = sub
5ED5C411 = dep
71F3BA83 = hlsl
F10C041F = rsb
1F92D4DE = ssb
08F2025B = mtl
```

This is full extensions list for PC-version. Don't know, where did you found .json ext.
## Post #23
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-02-04T09:25:52+00:00
- Post Title: Re: Sine Mora (XBLA) *.bin

> Reply from DrMefistO
>
> Don't know, where did you found .json ext.
In main executable.
## Post #24
- Username: DrMefistO
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Feb 03, 2014 8:59 pm
- Post datetime: 2014-02-04T09:33:20+00:00
- Post Title: Re: Sine Mora (XBLA) *.bin

But I have checked every bin-archive and have not found any .json.
I know that my list is full, because, I wrote a parser, which finds extension by its checksum, and parses every bin-file. So...
## Post #25
- Username: DrMefistO
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Feb 03, 2014 8:59 pm
- Post datetime: 2014-02-04T13:23:43+00:00
- Post Title: Re: Sine Mora (XBLA) *.bin

```
35B99DDD = cpp
```

One another extension from XBOX-version.
## Post #26
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-02-08T14:03:18+00:00
- Post Title: Re: Sine Mora (XBLA) *.bin

> Reply from DrMefistO
>
> Code: Select all35B99DDD = cpp
One another extension from XBOX-version.
Thanks. Here updated version.

```
* Fixed crashes while unpacking memfile
* Updated lz4 library (r112) - thanks to Yann Collet
```

[BINUnpacker_0.2.0.rar](https://xentaxbackup.github.io/file/7002_BINUnpacker_0.2.0.rar)
## Post #27
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-02-08T17:58:40+00:00
- Post Title: Re: Sine Mora (XBLA) *.bin

File name list updated. Added ~3500 names (PC/PS3/XBOX)
[SM_Projects_4281.rar](https://xentaxbackup.github.io/file/7003_SM_Projects_4281.rar)
## Post #28
- Username: DrMefistO
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Feb 03, 2014 8:59 pm
- Post datetime: 2014-02-09T18:12:57+00:00
- Post Title: Re: Sine Mora (XBLA) *.bin

Is every path applicable to PC/XBOX/PS3 versions?
Some ones are not applicable to PC, some - to XBOX, and... I have not checked PS3 version yet.
## Post #29
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-02-09T19:57:51+00:00
- Post Title: Re: Sine Mora (XBLA) *.bin

> Reply from DrMefistO
>
> Is every path applicable to PC/XBOX/PS3 versions?
Some ones are not applicable to PC, some - to XBOX, and... I have not checked PS3 version yet.
I checked all platforms. In PS3 all *.bin archives encrypted in EDAT 4.0.0.w
## Post #30
- Username: DrMefistO
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Feb 03, 2014 8:59 pm
- Post datetime: 2014-02-10T17:29:18+00:00
- Post Title: Re: Sine Mora (XBLA) *.bin

My current progress of paths identifying (includes only valid Ekey's paths and plus my valid paths):
[filenames.zip](https://xentaxbackup.github.io/file/7004_filenames.zip)
## Post #31
- Username: DrMefistO
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Feb 03, 2014 8:59 pm
- Post datetime: 2014-02-11T05:33:13+00:00
- Post Title: Re: Sine Mora (XBLA) *.bin

Sometimes decompression process goes wrong, sometimes - good. And I don't know why.
I mean, that sometimes result, returned by decompression function is negative, that means - something goes wrong.
## Post #32
- Username: DrMefistO
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Feb 03, 2014 8:59 pm
- Post datetime: 2014-02-24T19:30:58+00:00
- Post Title: Re: Sine Mora (XBLA) *.bin

Good news:
 - I have found good decompressor/compressor(!) code;
 - I know what means second dword;

Updates will be soon.
## Post #33
- Username: DrMefistO
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Feb 03, 2014 8:59 pm
- Post datetime: 2014-02-27T19:17:17+00:00
- Post Title: Re: Sine Mora (XBLA) *.bin

Great update! (Includes allmost finished filelist for PC - only 51 files still missed).
[filenames.zip](https://xentaxbackup.github.io/file/7049_filenames.zip)
## Post #34
- Username: DrMefistO
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Feb 03, 2014 8:59 pm
- Post datetime: 2014-03-03T15:20:00+00:00
- Post Title: Re: Sine Mora (XBLA) *.bin

+7 files recognized. I can't publish compression tool without full list (at least for PC). So... Help me to find'em'all!
[filenames.zip](https://xentaxbackup.github.io/file/7063_filenames.zip)
## Post #35
- Username: DrMefistO
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Feb 03, 2014 8:59 pm
- Post datetime: 2014-03-17T10:43:17+00:00
- Post Title: Re: Sine Mora (XBLA) *.bin

So... Last paths are most hard to find. Only bruteforce, or manual name-finding.

This is list of unknown hashes with two known names before and after.

```
BC6B36A9
textures/cubemap1

sounds/bokumono/boss/boss_egybe_stereo
E7890CC7
E78F0E41
E7800A90
30605F88
07F44146
0AE89E4C
sounds/bokumono/boss/boss_rotate

sounds/bokumono/underwater_explosion_loop2d
60B2DA44
sounds/bokumono/boss/st1_head_move_and_beam_up

sounds/cardinal_canyon/player_entrance_high_altitude
2930831D
29368497
292780E6
54060ADE
A6806070
A974BD76
sounds/cardinal_canyon/warship_high_altitude

textures/gui/frontend/intrologo_microsoft
F3936782
textures/gui/frontend/intrologo_dr

objects/enemies/boss_spider/egg
FC517337
objects/levels/robot_factory/small_spider

sounds/last_enkie_city/stage_5_entrance
784C3B28
78523CA2
784338F1
66306D69
D65DAB25
D952082B
sounds/last_enkie_city/leonard_entrance

sounds/moneta_point/sub-boss/st1_electrical_discharge1_loop
C3DE870F
9A097590
sounds/moneta_point/sub-boss/boss_explosion

sounds/underwater_explosion_large
352FF321
B569544F
B56A548E
B56B54CD
7605AAC9
9A10A7AF
F44B2BA8
230D2F10
4AB496B5
EF960B60
DB03BEBC
A76791F9
4F200CE1
sounds/target_icon

sounds/tira/stage_6_part_1/teki_propella
CB45439C
textures/gui/boss_acridoidea

render/stateblocks/default
620CB43B
render/stateblocks/depth_only

render/stateblocks/water_blend
B2A40AE9
render/stateblocks/clamp_bilinear
```


And last paths in attachment.
[paths.zip](https://xentaxbackup.github.io/file/7102_paths.zip)
## Post #36
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-03-17T10:57:43+00:00
- Post Title: Re: Sine Mora (XBLA) *.bin

Unknown files may be not used in the game.
## Post #37
- Username: DrMefistO
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Feb 03, 2014 8:59 pm
- Post datetime: 2014-03-17T11:01:24+00:00
- Post Title: Re: Sine Mora (XBLA) *.bin

No. This hashes are from the game. They are still unknown. And they are used.
## Post #38
- Username: DrMefistO
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Feb 03, 2014 8:59 pm
- Post datetime: 2014-03-19T10:52:40+00:00
- Post Title: Re: Sine Mora (XBLA) *.bin

Important info for those guys, who want to help: some paths can contain spaces. So, use it in your searches.
## Post #39
- Username: DrMefistO
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Feb 03, 2014 8:59 pm
- Post datetime: 2014-03-27T07:18:25+00:00
- Post Title: Re: Sine Mora (XBLA) *.bin

Almost last super update!
[https://www.dropbox.com/s/4y9aerrfcnivsmc/paths.txt](https://www.dropbox.com/s/4y9aerrfcnivsmc/paths.txt)

Only 39 file still missed (for PC/XBOX/PS3)!
## Post #40
- Username: Adrot
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Dec 03, 2017 9:00 am
- Post datetime: 2018-12-05T23:22:14+00:00
- Post Title: Re: Sine Mora (XBLA) *.bin

Sorry for necroposting, but due to the release of Sine Mora EX, I thought that attention regarding this game has sparked again. In addition to that, the Dropbox link isn't working. What can be done now?
