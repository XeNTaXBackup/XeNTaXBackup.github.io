## Post #1
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2016-12-03T05:27:20+00:00
- Post Title: watch dogs 2 .dat .fat archive?

any progress?
Can't wait to mod wd2
## Post #2
- Username: disastorm
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Sep 20, 2014 5:20 pm
- Post datetime: 2016-12-03T09:08:43+00:00
- Post Title: watch dogs 2 .dat .fat archive?

I don't know anything about how to do this, but I'll post my thoughts on the fat file, maybe people who know stuff will see it and automatically know the answer.

It looks like the fat file may be best viewed at 20 bytes per line.

The first 8 bytes are always the same, probably the name and version or something like that. 35544146 0B000000

The next 4 bytes seem to have 2 variants: either 01064600  or 00004600

files with 01064600 :
common.fat
videos.fat
installpackage.fat
san_francisco_english.fat
san_francisco_hires.fat
san_francisco_preload.fat
san_francisco_cache.fat
san_francisco_cache_patch.fat
installpackage_english.fat
patch.fat
shadersobj.fat
san_francisco.fat

files with 00004600:
sound_english.fat
sound.fat
san_francisco_sound.fat
san_francisco_sound_english.fat


The 8 bytes after that are always all Fs in the initial header: FFFFFFFF FFFFFFFF
And the 4 bytes after that initial header thing is always 00000000.


Here are some fat images in case anyone has any ideas:
The fourth column in all of them seems to be constantly increasing I believe, but it doesnt start at zero and they seem too high to be offsets.

common.fat ( the second column seems to have some repeated values) :


videos.fat ( you'll notice the second column is mostly zeroes ):


sound.fat ( second column is also mostly zeroes, also note this is one of the files with 00004600 for bytes 9-12 ):



Here are some fats for 0 byte dat files:
## Post #3
- Username: iambosh
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Oct 04, 2014 12:22 pm
- Post datetime: 2016-12-03T21:47:53+00:00
- Post Title: watch dogs 2 .dat .fat archive?

i suppose we could modify the quick bms script for fat files? i really wise we knew how to modify gibbs tools
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-06T09:26:18+00:00
- Post Title: watch dogs 2 .dat .fat archive?

i know how to modify gibbed tools, but i doubt it will help. Do you think the format is similar to Watch dogs 1?
## Post #5
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2016-12-06T15:36:18+00:00
- Post Title: watch dogs 2 .dat .fat archive?

i have found rick/gibbed 's twitter,maybe someone can ask him about the disrupt tool
[https://twitter.com/gibbed/with_replies](https://twitter.com/gibbed/with_replies)
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-12-06T15:40:35+00:00
- Post Title: watch dogs 2 .dat .fat archive?

Header:

```
    dwVersion: uint32_t; //11
    dwUnknown1: uint32_t;
    dwUnknown2: uint32_t; //-1
    dwUnknown3: uint32_t; //-1
    dwUnknown4: uint32_t; //0
    dwTotalFiles: uint32_t;
```


Entry:

```
    dwSize: uint32_t;
    dwOffset: uint32_t;
    dwZSize: uint32_t;
```


for gibbed source's

```
           var b = TFileStream.ReadInt32();
           var c = TFileStream.ReadInt32();
           var d = TFileStream.ReadInt32();
           var e = TFileStream.ReadInt32();

           NameHash = a;
           NameHash |= ((ulong)b) << 32;
           Offset = (long)d << 2;
           Offset |= ((c & 0xC0000000u) >> 30);
           UncompressedSize = (uint)(e & 0xFFFFFFFC) >> 2;
           CompressedSize = (uint)((c & 0x3FFFFFFF) >> 0);
```


Compression seems is LZ series
## Post #7
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2016-12-06T22:44:48+00:00
- Post Title: watch dogs 2 .dat .fat archive?

Yeah, it uses LZMA and modified version of LZ4.
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-12-06T22:46:44+00:00
- Post Title: watch dogs 2 .dat .fat archive?

Interesting.. there are 2 types of compression? Or One > LZMA + LZ4 ?
## Post #9
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2016-12-06T23:35:29+00:00
- Post Title: watch dogs 2 .dat .fat archive?

Two types.

```
struct SFatFileEntry{
	/*uint32_t	field_0;
	uint32_t	field_4;
	uint32_t	field_8;
	uint32_t	field_c;
	uint32_t	field_10;*/
	uint64_t	Hash;
	uint64_t	CompressedSize : 30;
	uint64_t	Offset : 34;
	uint32_t	CompressionMethod : 2;
	uint32_t	UncompressedSize : 30;
};
#pragma pack(pop)
```

Type 2 is the modified LZ4, 0 is LZMA.
## Post #10
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-12-06T23:59:03+00:00
- Post Title: watch dogs 2 .dat .fat archive?

Hash is Fnv1a x64

```
{
    ulong fnv64Prime = 0x00000100000001B3ul;
    ulong hash = 0xCBF29CE484222325ul;

    for (var i = 0; i < value.Length; i++)
    {
        hash *= fnv64Prime;
        hash = hash ^ value[i];
    }

    return hash & 0x1FFFFFFFFFFFFFFFul | 0xA000000000000000ul;
}
```
## Post #11
- Username: disastorm
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Sep 20, 2014 5:20 pm
- Post datetime: 2016-12-07T11:37:56+00:00
- Post Title: watch dogs 2 .dat .fat archive?

Wow didn't expect people to continue this. I wish I could help more but not really sure what to do. It seems you guys figured out offset and file size? Is the last thing to just get the compression correct?
## Post #12
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-12-07T12:54:37+00:00
- Post Title: watch dogs 2 .dat .fat archive?

> Reply from disastorm
>
> Is the last thing to just get the compression correct?
Yup. Currently i have not found a piece code of compression in library. Maybe Sir Kane can give a some hint's
## Post #13
- Username: disastorm
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Sep 20, 2014 5:20 pm
- Post datetime: 2016-12-07T13:55:51+00:00
- Post Title: watch dogs 2 .dat .fat archive?

If I'm not mistaken, even after getting the compression, would we still need to figure out what the various values in the xmls are? didn't gibbed need to make some kind of binary class mapping files for the watch dogs 1 gibbed?
## Post #14
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-12-07T17:16:53+00:00
- Post Title: watch dogs 2 .dat .fat archive?

about the compression, this is the same problem Aluigi came across when unpacking another Ubisoft title, Far Cry: Primal.  It also uses LZMA and an unknown LZ4.  So that's something to keep in mind, perhaps some clues can be found in one game to benefit the other...

[http://www.zenhax.com/viewtopic.php?f=9&t=378#p11725](http://www.zenhax.com/viewtopic.php?f=9&t=378#p11725)
## Post #15
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2016-12-07T23:10:32+00:00
- Post Title: watch dogs 2 .dat .fat archive?

0xE6C is good constant to look for to find the LZMA code (which turns out to be slightly modified, too).
## Post #16
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-12-08T18:40:47+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Well, i found LZ4. Seems there changed only dec32_table :

Original

```
const int dec64table[] = {0, 0, 0, -1, 0, 1, 2, 3};
```

UBI

//32 - {0, 3, 2, 3, 0, 0, 0, 0};

```
  v47 = 3i64;
  v48 = 2i64;
  v49 = 3i64;
  v50 = 0i64;
  v51 = 0i64;
  v52 = 0i64;
  v53 = 0i64;
```


and

//64 - {0, 0, 0, -1, 0, 1, 2, 3};

```
  v55 = 0i64;
  v56 = 0i64;
  v57 = -1i64;
  v58 = 0i64;
  v59 = 1i64;
  v60 = 2i64;
  v61 = 3i64;
```
## Post #17
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2016-12-08T18:47:41+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

I already reverse engineered the LZ4 one, just need to get LZMA working.
## Post #18
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-08T19:46:12+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

I don't see a single file in the whole 22GBs using lzma. I checked this specifically right now. How can you get it working when there's no files compressed with it?
## Post #19
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2016-12-08T19:51:38+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

It's certainly being used.
## Post #20
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-08T19:55:34+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from Ekey
>
> Well, i found LZ4. Seems there changed only dec32_table :

//32 - {0, 3, 2, 3, 0, 0, 0, 0};
//64 - {0, 0, 0, -1, 0, 1, 2, 3};

This game only runs on 64 bit. Both these tables are for 64-bit LZ4:

```
        readonly sbyte[] m_Dec2table = new sbyte[8] { 0, 0, 0, -1, 0, 1, 2, 3 };

```
## Post #21
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-08T19:57:24+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from Sir Kane
>
> It's certainly being used.

Maybe, but NOT on the fat/dat files. Maybe on some savegame data? Anyway, its not needed for unpacking game files.
## Post #22
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2016-12-08T20:04:55+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Some of the data in the .dat files is compressed with the modified LZMA, and the rest is compressed with the modified LZ4.
## Post #23
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-08T20:10:56+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from Sir Kane
>
> Some of the data in the .dat files is compressed with the modified LZMA, and the rest is compressed with the modified LZ4.

ok if you say so, tell me at least one filename/offset compressed with lzma.

p.s. i'm talking about watch dogs 2, maybe you're looking into far cry?
## Post #24
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-12-08T20:22:00+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Here one decompressed XML file. One strange thing: in the end of file can be some trash bytes. 
[credits.rar](https://xentaxbackup.github.io/file/11997_credits.rar)
## Post #25
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-08T21:37:04+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

ok considering this all, it looks like we either have different versions of the game, or game protection makes some different obfuscation in different regions, or even every copy of the game. So it will be technically impossible to make a tool for this.
## Post #26
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-08T21:53:24+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

if Sir Kane wants to prove its not true, I'm still waiting for a .dat file offset where lzma is used.
## Post #27
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-08T22:07:21+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

nothing?
## Post #28
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2016-12-09T03:11:14+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

[http://sktest.aruarose.com/WD2Extract.7z](http://sktest.aruarose.com/WD2Extract.7z)
## Post #29
- Username: mlleemiles
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Sep 08, 2014 6:20 pm
- Post datetime: 2016-12-09T03:25:33+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from Sir Kane
>
> http://sktest.aruarose.com/WD2Extract.7z

Sir Kane, may I ask how did you extract the file names from the data?
## Post #30
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2016-12-09T04:05:04+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

There's a function pointer the game calls with the string to hash if it's non-null, so I just set the function pointer to a function that dumps the passed in string into a file.
## Post #31
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-09T07:09:33+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

can you now confirm that the game is NOT using lzma?
## Post #32
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2016-12-09T07:32:34+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

There's undoubtedly support for archives with LZMA compression, it just may not be used in the PC version. I haven't looked too hard for whatever enables it.
## Post #33
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-09T07:35:54+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from Sir Kane
>
> There's undoubtedly support for archives with LZMA compression, it just may not be used in the PC version.

Yes, that may very well be the case.
## Post #34
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2016-12-09T09:13:51+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

WOW,thanks for the good work!
the extractor works really great!
but the only thing that bother me is that the items.lib seems can't be converted to .xml with the Gibbed.Disrupt.ConvertBinaryObject.exe
yet graphickit_models.lib can be converted to .xml with that...

strange...
## Post #35
- Username: disastorm
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Sep 20, 2014 5:20 pm
- Post datetime: 2016-12-09T10:54:18+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Wow you guys got a working extractor? Can it also repack or not yet?
## Post #36
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-12-09T11:33:53+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

combined with my list (156874) > [http://www78.zippyshare.com/v/okVZiF2W/file.html](http://www78.zippyshare.com/v/okVZiF2W/file.html)
## Post #37
- Username: disastorm
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Sep 20, 2014 5:20 pm
- Post datetime: 2016-12-10T11:02:33+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from redcomet
>
> WOW,thanks for the good work!
the extractor works really great!
but the only thing that bother me is that the items.lib seems can't be converted to .xml with the Gibbed.Disrupt.ConvertBinaryObject.exe
yet graphickit_models.lib can be converted to .xml with that...

strange...
Actually you can extract items and graphickit parts and other libraries.You have just to remove the Watch Dog 1 class definitions from your project folder. The only downside is that without the definitions, none of the fields will have names, you will have to figure out all the xml fields yourself.


Have you guys made a repacker yet?
## Post #38
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2016-12-11T09:17:52+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from disastorm
>
> redcomet wrote:WOW,thanks for the good work!
the extractor works really great!
but the only thing that bother me is that the items.lib seems can't be converted to .xml with the Gibbed.Disrupt.ConvertBinaryObject.exe
yet graphickit_models.lib can be converted to .xml with that...

strange...
Actually you can extract items and graphickit parts and other libraries.You have just to remove the Watch Dog 1 class definitions from your project folder. The only downside is that without the definitions, none of the fields will have names, you will have to figure out all the xml fields yourself.


Have you guys made a repacker yet?
Thanks for the advice,but it doesn't work for me,no matter i removed any file from 'project' or removed the entire folder,it didn't help
there is still only one .xml file in the 'items_converted' folder,'Clothing_ULC.WD1_Clothing_ULC.ChicagoClub'

so i wonder why only this one can be converted but the others can't.
## Post #39
- Username: maury121
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Sep 05, 2016 9:06 pm
- Post datetime: 2016-12-12T00:13:43+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Hi guys i'm new to the mod world, i was looking to extract and view models and textures from WD2, is there any working extractor already? BTW i'm pretty sure that WD2 use the same engine of The Division because both game has the same problem on my computer (EVGA Precision delay every keyboard input).
## Post #40
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-12-12T02:09:48+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from maury121
>
> is there any working extractor already?
Did you read topic? [viewtopic.php?p=124883#p124883](http://forum.xentax.com/viewtopic.php?p=124883#p124883)
## Post #41
- Username: neburas
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Aug 06, 2012 6:01 pm
- Post datetime: 2016-12-12T03:29:18+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Extracter is fine, but how to repack to dat/fat? Rick's gibbed pack tool causes error.
## Post #42
- Username: maury121
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Sep 05, 2016 9:06 pm
- Post datetime: 2016-12-12T03:50:19+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from Ekey
>
> maury121 wrote:is there any working extractor already?
Did you read topic? viewtopic.php?p=124883#p124883
 Yes sir i read the topic and i've already download the .exe file, there is no instructions inside so i don't know where to use it, or how to.

EDIT: solved.
## Post #43
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-12-12T11:33:22+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from neburas
>
> Extracter is fine, but how to repack to dat/fat? Rick's gibbed pack tool causes error.
Currently you can't pack files back.
## Post #44
- Username: neburas
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Aug 06, 2012 6:01 pm
- Post datetime: 2016-12-12T12:55:29+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from Ekey
>
> neburas wrote:Extracter is fine, but how to repack to dat/fat? Rick's gibbed pack tool causes error.
Currently you can't pack files back.
It's a shame to hear that. I wish if Rick working on upgrade disrupt tools.
## Post #45
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-12T13:34:37+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from neburas
>
> Extracter is fine, but how to repack to dat/fat?

It would be easy to just pack files back, without compressing them. Also this lz4 version has no big difference from standard, considering if you skip the varint in the beginning (which is not needed by compression anyway), most of the files can be unpacked even with standard LZ4. Also the new possibilities to have big offsets and to leave big blocks uncompressed is NOT needed for compression again. So even a new LZ4 packer is not a big problem if someone have time to write it.
## Post #46
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-12-12T14:36:06+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Updated list, added ~51083 > (207957) > [http://www4.zippyshare.com/v/iGDypDyX/file.html](http://www4.zippyshare.com/v/iGDypDyX/file.html)
## Post #47
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-12-12T19:07:43+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

One more, added ~34757> (242714) > [http://www6.zippyshare.com/v/H8To8RZy/file.html](http://www6.zippyshare.com/v/H8To8RZy/file.html)
## Post #48
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2016-12-12T19:16:15+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

The uncompressed chunk at the end of the compressed data is actually required, since the compressed data is loaded into the end of the output buffer and decompression keeps going while src pointer < dest pointer.
## Post #49
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-12T19:26:06+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from Sir Kane
>
> The uncompressed chunk at the end of the compressed data is actually required

Not really. And for most files its actually not present. In most cases, last compressed data (after decompression) will end exactly at the end of the buffer.
## Post #50
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2016-12-12T20:43:13+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Added a tool to repack (doesn't compress) and merged my filelist with Ekey's.

[http://sktest.aruarose.com/WD2FatTools_v002.7z](http://sktest.aruarose.com/WD2FatTools_v002.7z)
## Post #51
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-12-12T21:50:36+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Texture converter (XBT to DDS) > [http://cra0kalo.com/public/xbt2dds.zip](http://cra0kalo.com/public/xbt2dds.zip)
## Post #52
- Username: disastorm
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Sep 20, 2014 5:20 pm
- Post datetime: 2016-12-13T00:34:48+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Does the game read them if they are packed uncompressed ?
## Post #53
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2016-12-13T01:27:25+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Yes, files can be either compressed or uncompressed, with the latter mostly being used for really small files.
## Post #54
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2016-12-13T10:44:45+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from Sir Kane
>
> Yes, files can be either compressed or uncompressed, with the latter mostly being used for really small files.
pardon me,may i ask how to pack it,i dragged both the folder and fat and dat files to wd2pack.exe,but nothing happen
## Post #55
- Username: disastorm
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Sep 20, 2014 5:20 pm
- Post datetime: 2016-12-13T11:51:49+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

So do you think we'd be able to extract common.fat/dat , convert it to xml, modify, convert it back to binary, and then pack it back and have it run, or are some of those steps still imperfect?

*edit just did a simple extract, repack with no changes, and start the game and that worked.
Does anyone know which files affect the player model? I know in Watch Dogs 1 there was the aiden outfit items, but in this one I guess the main character has various parts of items he can equip.
## Post #56
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2016-12-13T12:11:41+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from disastorm
>
> So do you think we'd be able to extract common.fat/dat , convert it to xml, modify, convert it back to binary, and then pack it back and have it run, or are some of those steps still imperfect?

*edit just did a simple extract, repack with no changes, and start the game and that worked.
Does anyone know which files affect the player model? I know in Watch Dogs 1 there was the aiden outfit items, but in this one I guess the main character has various parts of items he can equip.

graphickit_models handles the npc model
items handles the clothing model

that's what i know
## Post #57
- Username: disastorm
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Sep 20, 2014 5:20 pm
- Post datetime: 2016-12-13T12:24:08+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Yea, the very last section in the xml for graphickit characters ( hash 0FEF3467 ) are their graphickit_part ids. Not sure how to link it with the clothes though.
## Post #58
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2016-12-13T12:42:20+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from disastorm
>
> Yea, the very last section in the xml for graphickit characters ( hash 0FEF3467 ) are their graphickit_part ids. Not sure how to link it with the clothes though.
I have done some experiments on the clothing model,trying to replace a biker jacket to a police shirt.
unfortunately,the game just automatically closed after loading into the game.

FYI [http://forums.guru3d.com/showthread.php?t=402960](http://forums.guru3d.com/showthread.php?t=402960)

although that post is outdated since the clothing system is totally changed in wd2,some of the contents are still worth reading.
## Post #59
- Username: disastorm
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Sep 20, 2014 5:20 pm
- Post datetime: 2016-12-13T13:13:40+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from redcomet
>
> disastorm wrote:Yea, the very last section in the xml for graphickit characters ( hash 0FEF3467 ) are their graphickit_part ids. Not sure how to link it with the clothes though.
I have done some experiments on the clothing model,trying to replace a biker jacket to a police shirt.
unfortunately,the game just automatically closed after loading into the game.

FYI http://forums.guru3d.com/showthread.php?t=402960

although that post is outdated since the clothing system is totally changed in wd2,some of the contents are still worth reading.

Hm I was able to find references to the graphickit_part ids in the Clothing item xmls, but when I changed them to something else, it didn't change in the game. It really is quite puzzling to me that changing all references to the graphickit_part didn't change it in the game, unless its not using the xml file I changed. Here is what I did to see if anyone has any ideas:

At the bottom of the items/Clothing_Rewards.ClothesBox.Torso.CyberDriver_Torso01.xml

```
      <field hash="6816806D" type="BinHex">05</field>
      <field hash="71C8840A" type="BinHex">C35E7D8F04000080</field>
      <field hash="D935FAD9" type="BinHex">28088AE703000080</field>
      <field hash="14088DCA" type="BinHex">FF</field>
      <field hash="1DF0076D" type="BinHex">FFFFFFFFFFFFFFFF</field>
      <field hash="730D0113" type="BinHex">FFFFFFFFFFFFFFFF</field>
      <field hash="7E23AAAE" type="BinHex">67726170686963735C6D6F64656C735C3078383030303030303365373861303832392E6D6F64656C00</field>
      <field hash="A849532C" type="BinHex">F0C2D5B6F2C645BA</field>
      <object hash="37CF95BD">
        <field hash="2BE15935" type="BinHex">FFFFFFFF</field>
        <field hash="5177A0C7" type="BinHex">000000000000000000000000</field>
        <field hash="99298BDA" type="BinHex">000000000000000000000000</field>
        <field hash="FC176C73" type="BinHex">0000803F0000803F0000803F</field>
      </object>

```


Here are 2 values found in graphickit_parts:
$ grep "F0C2D5B6F2C645BA" ./*
./W2CH_PAR_avat_ma_tor.fill_ma_tor_jacket01_opentshirt_REWARD_JimmySiska.xml:                                                                     <field hash="E4556387" type="BinHex">F0C2D5B6F2C645BA</field>


$ grep "28088AE703000080" ./*
./W2CH_PAR_avat_ma_tor.fill_ma_tor_jacket01_opentshirt_REWARD_JimmySiska.xml:  <                                                               field hash="1FE8D41C" type="BinHex">28088AE703000080</field>
./W2CH_PAR_avat_ma_tor.fill_ma_tor_jacket01_opentshirt_REWARD_JimmySiska.xml:  <                                                               field hash="389F6DA7" type="BinHex">28088AE703000080</field>

I replaced these in the original items/Clothing_Rewards.ClothesBox.Torso.CyberDriver_Torso01.xml with values from a different torso graphickit_part,
but in the game the item still looks exactly the same. I did verify that it was indeed reading my new common.dat/fat.
There doesn't seem to be any other graphickit_part references in that file, so the only thing I can think of is that the game doesn't actually use this file the way I was thinking it did.

*edit, I even changed the actual graphickit_part xml file , copy pasted over almost the whole thing and it still didn't seem to do anything... its really bizzare.

*edit oh i think its because i'm changing common, i should try changing the patch file.
## Post #60
- Username: disastorm
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Sep 20, 2014 5:20 pm
- Post datetime: 2016-12-13T13:54:38+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

check it out, wasn't really what i was hoping for, but its a start. At least we can see the game can be modded without crashing:
## Post #61
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-12-13T14:13:02+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Combined with Sir Kane list and added ~9110 > (263423) > [http://www111.zippyshare.com/v/S8DPCVHT/file.html](http://www111.zippyshare.com/v/S8DPCVHT/file.html)
## Post #62
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-12-13T14:26:39+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

rml2xml and xml2rml converter.

usage example:

to XML -> result - [http://pastebin.com/gEj11FnH](http://pastebin.com/gEj11FnH)

```
Gibbed.Disrupt.ConvertXml -xml music.rml music.xml
```


to RML

```
Gibbed.Disrupt.ConvertXml -rml music.xml music.rml
```


Edited: Re-attached
[Gibbed.Disrupt.ConvertXml.rar](https://xentaxbackup.github.io/file/12039_Gibbed.Disrupt.ConvertXml.rar)
## Post #63
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2016-12-13T15:07:58+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from disastorm
>
> check it out, wasn't really what i was hoping for, but its a start. At least we can see the game can be modded without crashing:

http://i.imgur.com/iAeWcvl.jpg

may i ask how to use the repacker,because i found out that my game crashed wasn't because the file i edited(i repacked the folder that i didn't edit to dat fat file and the game still crash)
## Post #64
- Username: disastorm
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Sep 20, 2014 5:20 pm
- Post datetime: 2016-12-13T16:16:37+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from redcomet
>
> disastorm wrote:check it out, wasn't really what i was hoping for, but its a start. At least we can see the game can be modded without crashing:

http://i.imgur.com/iAeWcvl.jpg

may i ask how to use the repacker,because i found out that my game crashed wasn't because the file i edited(i repacked the folder that i didn't edit to dat fat file and the game still crash)
If you run it without parameters it tells you how to use it.
Its just the command <folder> <output fat>

The full process for modding is as follows:
extract patch.fat/dat
convert whatever file you want to modify into xml using the Gibbed tools.
Modify the xml.
Convert it back to .lib or whatever it was before.
Put it back in the folder where the patch.fat/dat was extracted.
Repack the patch.fat/dat from the folder using the Repack exe tool.
Put the patch.fat/dat in your watchdogs data64 directory or whatever its called.
Run the game.

Btw got modelswap working, I'll post a guide tommorow for what files to change if people are interested.
## Post #65
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2016-12-13T16:39:15+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from disastorm
>
> redcomet wrote:disastorm wrote:check it out, wasn't really what i was hoping for, but its a start. At least we can see the game can be modded without crashing:

http://i.imgur.com/iAeWcvl.jpg

may i ask how to use the repacker,because i found out that my game crashed wasn't because the file i edited(i repacked the folder that i didn't edit to dat fat file and the game still crash)
If you run it without parameters it tells you how to use it.
Its just the command <folder> <output fat>

The full process for modding is as follows:
extract patch.fat/dat
convert whatever file you want to modify into xml using the Gibbed tools.
Modify the xml.
Convert it back to .lib or whatever it was before.
Put it back in the folder where the patch.fat/dat was extracted.
Repack the patch.fat/dat from the folder using the Repack exe tool.
Put the patch.fat/dat in your watchdogs data64 directory or whatever its called.
Run the game.

Btw got modelswap working, I'll post a guide tommorow for what files to change if people are interested.
http://i.imgur.com/TBj8ARp.jpg
Glad to see you are making progress! Looking forward for the tutorial.
But for the repacking tool,what do I need to drag or open to the repack.exe to repack to dat fat?
For me the program seemed not working right,i dragged the folder/the original dat fat file to the repack.exe,nothing happened at all. Double click the repack exe doesn't work as well.
## Post #66
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-12-13T17:51:08+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from redcomet
>
> 
Glad to see you are making progress! Looking forward for the tutorial.
But for the repacking tool,what do I need to drag or open to the repack.exe to repack to dat fat?
For me the program seemed not working right,i dragged the folder/the original dat fat file to the repack.exe,nothing happened at all. Double click the repack exe doesn't work as well.

It's batch usage

```
wd2pack.exe <source folder> <output fat file>
```


Example:

Unpack:

```
WD2Extract "e:\Games\Steam\SteamApps\common\Watch_Dogs2\data_win64\patch.fat" "D:\MyPath"
```


Unpacked files will be in path > D:\MyPath

Pack:

```
WD2Pack "D:\MyPath" "D:\Patch.fat"
```


This just example, use your path's.
## Post #67
- Username: disastorm
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Sep 20, 2014 5:20 pm
- Post datetime: 2016-12-14T00:34:46+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

You have to use command line to use the tool.

start->run->cmd will open the command line.
if on windows 10 you have to right click start.
## Post #68
- Username: iambosh
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Oct 04, 2014 12:22 pm
- Post datetime: 2016-12-14T03:50:34+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

anyone write a batch to extract everything?
## Post #69
- Username: neburas
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Aug 06, 2012 6:01 pm
- Post datetime: 2016-12-14T11:18:52+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Anyone succeeded to extract items.lib?
ConvertBinaryObject.exe can't handle this now...
## Post #70
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-12-14T12:26:57+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Small update. Added ~2591 > (266014) > [http://www25.zippyshare.com/v/oTTiV6rd/file.html](http://www25.zippyshare.com/v/oTTiV6rd/file.html)
## Post #71
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2016-12-14T12:38:43+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from neburas
>
> Anyone succeeded to extract items.lib?
ConvertBinaryObject.exe can't handle this now...
just remove 'binary objects' folder in 'disrupt tool path\project\watch dogs'
and you are good to go
## Post #72
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2016-12-14T12:41:25+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from Ekey
>
> redcomet wrote:
Glad to see you are making progress! Looking forward for the tutorial.
But for the repacking tool,what do I need to drag or open to the repack.exe to repack to dat fat?
For me the program seemed not working right,i dragged the folder/the original dat fat file to the repack.exe,nothing happened at all. Double click the repack exe doesn't work as well.

It's batch usage
Code: Select allwd2pack.exe <source folder> <output fat file>

Example:

Unpack:
Code: Select allWD2Extract "e:\Games\Steam\SteamApps\common\Watch_Dogs2\data_win64\patch.fat" "D:\MyPath"

Unpacked files will be in path > D:\MyPath

Pack:
Code: Select allWD2Pack "D:\MyPath" "D:\Patch.fat"

This just example, use your path's.

thanks!i can pack it back now!
## Post #73
- Username: disastorm
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Sep 20, 2014 5:20 pm
- Post datetime: 2016-12-14T12:42:59+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Ok guys, so for anyone having issues using the gibbed tools on libs, you need to remove the class definition from the projects/Watch Dogs/binary objects/files/ gibbed directory.

Here is a picture of mine ( I've removed stuff like Items.binaryobjectfile.xml, GraphicKit_parts.binaryobjectfile.xml, etc )



Additionally, the file being modded should be patch.dat/fat.

Here is how to do model swaps using the clothing in the game:


The file on the left is the items.lib file for one of the DedSec hats.
The file on the right is the graphickit_models.lib file for Aiden from the jail mission.
You simply copy paste the section shown.
The highlighted field, with hash "D935FAD9" is the reference to the graphickit_parts.lib file.

Here is how you can find out what the various sections in the graphickit_models files are:

The below example shows checking the 3 sections on the Aiden file shown in the image above.
Inside the extracted graphickit_parts directory:

$ grep "8A84909104000080" ./*
./W2CH_PAR_pois_mul.pers18_AidenHead.xml:  <field hash="1FE8D41C" type="BinHex">8A84909104000080</field>
./W2CH_PAR_pois_mul.pers18_AidenHead.xml:  <field hash="389F6DA7" type="BinHex">8A84909104000080</field>


$ grep "E4F1550C02000080" ./*
./W2CH_PAR_body_m.body_m_full.xml:  <field hash="1FE8D41C" type="BinHex">E4F1550C02000080</field>
./W2CH_PAR_body_m.body_m_full.xml:  <field hash="389F6DA7" type="BinHex">E4F1550C02000080</field>


$ grep "758E3CF002000080" ./*
./W2CH_PAR_avat_ma_tor.avat_ma_tor_coataiden01_REWARD_brownleather.xml:  <field hash="1FE8D41C" type="BinHex">758E3CF002000080</field>
./W2CH_PAR_avat_ma_tor.avat_ma_tor_coataiden01_REWARD_brownleather.xml:  <field hash="389F6DA7" type="BinHex">758E3CF002000080</field>

This shows us that these 3 sections are Aiden's Head, the generic male body, and his coat.


Important Notes:
-After modifying the Item files, these items will no longer show up in your locker ( until you revert the changes ). You must first equip the items before adding the modded patch.fat/dat, and then upon logging in, you will see the modded graphickit parts on your character.
-I don't know 100% but it appears that when equipping various parts, it will remove the default Marcus parts. For example if you equip an item that you set to a male or female body, it will replace Marcus's body as opposed to showing both at the same time. However, in some cases i did seem to see the glasses + the additional graphickit_part so maybe I did something wrong, or there are some cases where this doesn't apply.
-I also believe the parts don't matter whether or not they are Head, torso, etc, they can be set to any piece of clothing.
-However, I did try to make one item set to multiple parts by duplicating the section at the bottom of the file on the left, but it appears to only use the first definition of that object, so it appears one item per graphickit part.


The full modding flow should be as below:
extract patch.fat/dat
convert whatever file you want to modify into xml using the Gibbed tools.
Modify the xml.
Convert it back to .lib or whatever it was before.
Put it back in the folder where the patch.fat/dat was extracted.
Repack the patch.fat/dat from the folder using the Repack exe tool.
Put the patch.fat/dat in your watchdogs data64 directory or whatever its called.
Run the game with the cheat thingy disabled.
## Post #74
- Username: neburas
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Aug 06, 2012 6:01 pm
- Post datetime: 2016-12-14T13:44:30+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from redcomet
>
> neburas wrote:Anyone succeeded to extract items.lib?
ConvertBinaryObject.exe can't handle this now...
just remove 'binary objects' folder in 'disrupt tool path\project\watch dogs'
and you are good to go

Thanks. It worked.
## Post #75
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-12-14T13:47:32+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

One more update. Added ~94851 > (360865) > [http://www55.zippyshare.com/v/s5siOMNi/file.html](http://www55.zippyshare.com/v/s5siOMNi/file.html)
## Post #76
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2016-12-14T14:14:16+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from disastorm
>
> Ok guys, so for anyone having issues using the gibbed tools on libs, you need to remove the class definition from the projects/Watch Dogs/binary objects/files/ gibbed directory.

Here is a picture of mine ( I've removed stuff like Items.binaryobjectfile.xml, GraphicKit_parts.binaryobjectfile.xml, etc )



Additionally, the file being modded should be patch.dat/fat.

Here is how to do model swaps using the clothing in the game:


The file on the left is the items.lib file for one of the DedSec hats.
The file on the right is the graphickit_models.lib file for Aiden from the jail mission.
You simply copy paste the section shown.
The highlighted field, with hash "D935FAD9" is the reference to the graphickit_parts.lib file.

Here is how you can find out what the various sections in the graphickit_models files are:

The below example shows checking the 3 sections on the Aiden file shown in the image above.
Inside the extracted graphickit_parts directory:

$ grep "8A84909104000080" ./*
./W2CH_PAR_pois_mul.pers18_AidenHead.xml:  <field hash="1FE8D41C" type="BinHex">8A84909104000080</field>
./W2CH_PAR_pois_mul.pers18_AidenHead.xml:  <field hash="389F6DA7" type="BinHex">8A84909104000080</field>


$ grep "E4F1550C02000080" ./*
./W2CH_PAR_body_m.body_m_full.xml:  <field hash="1FE8D41C" type="BinHex">E4F1550C02000080</field>
./W2CH_PAR_body_m.body_m_full.xml:  <field hash="389F6DA7" type="BinHex">E4F1550C02000080</field>


$ grep "758E3CF002000080" ./*
./W2CH_PAR_avat_ma_tor.avat_ma_tor_coataiden01_REWARD_brownleather.xml:  <field hash="1FE8D41C" type="BinHex">758E3CF002000080</field>
./W2CH_PAR_avat_ma_tor.avat_ma_tor_coataiden01_REWARD_brownleather.xml:  <field hash="389F6DA7" type="BinHex">758E3CF002000080</field>

This shows us that these 3 sections are Aiden's Head, the generic male body, and his coat.


Important Notes:
-After modifying the Item files, these items will no longer show up in your locker ( until you revert the changes ). You must first equip the items before adding the modded patch.fat/dat, and then upon logging in, you will see the modded graphickit parts on your character.
-I don't know 100% but it appears that when equipping various parts, it will remove the default Marcus parts. For example if you equip an item that you set to a male or female body, it will replace Marcus's body as opposed to showing both at the same time. However, in some cases i did seem to see the glasses + the additional graphickit_part so maybe I did something wrong, or there are some cases where this doesn't apply.
-I also believe the parts don't matter whether or not they are Head, torso, etc, they can be set to any piece of clothing.
-However, I did try to make one item set to multiple parts by duplicating the section at the bottom of the file on the left, but it appears to only use the first definition of that object, so it appears one item per graphickit part.


The full modding flow should be as below:
extract patch.fat/dat
convert whatever file you want to modify into xml using the Gibbed tools.
Modify the xml.
Convert it back to .lib or whatever it was before.
Put it back in the folder where the patch.fat/dat was extracted.
Repack the patch.fat/dat from the folder using the Repack exe tool.
Put the patch.fat/dat in your watchdogs data64 directory or whatever its called.
Run the game with the cheat thingy disabled.

Nice work sir!
i have tried it by myself,and it works!
but the problem is that there is no facial movements in chatting with the swapped face,
moreover,seems like the glasses are not possible to get rid of.

anyway,i think you can creat a new thread on guru3d to discuss model swapping in wd2,it may helps in gathering people to brainstorm.
## Post #77
- Username: judgereinhold2
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 14, 2016 10:49 am
- Post datetime: 2016-12-14T14:51:32+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

I'm having a bit of an issue: I found where the in-game licensed music is kept (san_francisco_sound.dat/fat). I extracted the fat files, converted the audio binary files to ogg, everything is fine. I edited the ogg audio files to what I wanted, then I converted them back to "wen" format (using this tutorial [http://forum.worldofwarships.eu/index.p ... 2/#topmost](http://forum.worldofwarships.eu/index.php?/topic/39798-sound-mod-creation-guide-052/#topmost)), and placed them back in (kept the same filenames but with the .wen extension) and rebuilt the dat/fat archives.

Some of the ones I modified work fine in the game when I use the in-game player, but the others don't play anything now... What am I missing here? Do they need to match in length exactly, or something else? This is the first time I've worked on modifying Watch Dogs stuff.
## Post #78
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-12-14T20:12:57+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Updated for latest patch. Added ~2431 > (363296) > [http://www61.zippyshare.com/v/pqS1mV5a/file.html](http://www61.zippyshare.com/v/pqS1mV5a/file.html)
## Post #79
- Username: iambosh
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Oct 04, 2014 12:22 pm
- Post datetime: 2016-12-14T20:39:47+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

so the gibbed tools work now? any way someone can post the updated version?
## Post #80
- Username: BadBoy
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Apr 24, 2016 10:17 pm
- Post datetime: 2016-12-14T21:22:01+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

How to open language files with .loc extension?

```

```
## Post #81
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2016-12-15T11:15:07+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

i managed to swap the police outfit from police gunman m1 on marcus,but the material of the shirt didn't appear...
and the pants's material became different texture.(turn from blue to brown)
except shirt and pants,the police hat,shoes and police logo with gun holster works great to me(no missing textures)

i wonder why...


*plz be noted that the logos on the shirt doesn't belong to the shirt itself,those logos are come up with the gun holster
## Post #82
- Username: neburas
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Aug 06, 2012 6:01 pm
- Post datetime: 2016-12-15T11:18:20+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

I'm working on adding some vehicles to car on demand app just like WD1 mod. Adding new vehicle is fine by create "CarHackingRewards.Generic.Budjet.XXXX.xml" in "items.lib"(same as WD1), but it locked and can't buy it at car dealer. I wish if anyone found hash value of "default unlocked" status of car on demand app.
## Post #83
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2016-12-15T11:20:21+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from iambosh
>
> so the gibbed tools work now? any way someone can post the updated version?
there are working extractor on page 2 and repacker on page 4 in this thread
and Gibbed.Disrupt.ConvertBinaryObject is used to convert .lib to .xml(to convert items.lib you need to remove binary objects folder in project\watch dogs)
## Post #84
- Username: disastorm
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Sep 20, 2014 5:20 pm
- Post datetime: 2016-12-15T16:26:12+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Yea there seems to be some texture issue. It seems to use only some kind of generic texture for the various parts, I havn't been able to figure out how to get it to be anything else.
## Post #85
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-12-15T21:28:48+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

More update. Added ~16855 > (377720) > [http://www6.zippyshare.com/v/ZqmJ5xsA/file.html](http://www6.zippyshare.com/v/ZqmJ5xsA/file.html)
## Post #86
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-12-15T21:59:23+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Last update from me. Added ~67823 > (445543) > [http://www65.zippyshare.com/v/G71EpEo9/file.html](http://www65.zippyshare.com/v/G71EpEo9/file.html)

Overall info:

```
common.fat -> Resolved: 5779 / Unknown: 256
dlc_ultra_textures.fat -> Resolved: 9316 / Unknown: 8
installpackage.fat -> Resolved: 8174 / Unknown: 876
installpackage_XXXXX.fat -> Resolved: 2616 / Unknown: 77
patch.fat -> Resolved: 51394 / Unknown: 4901
san_francisco.fat -> Resolved: 152515 / Unknown: 48495
san_francisco_cache.fat -> Resolved: 14989 / Unknown: 1013
san_francisco_hires.fat -> Resolved: 14710 / Unknown: 3454
san_francisco_preload.fat -> Resolved: 44247 / Unknown: 42466
san_francisco_XXXXX.fat -> Resolved: 14334 / Unknown: 7543
san_francisco_sound.fat -> Resolved: 4955 / Unknown: 526
san_francisco_sound_XXXXX.fat -> Resolved: 76514 / Unknown: 0
shadersobj.fat -> Resolved: 47357 / Unknown: 2977
sound.fat -> Resolved: 50 / Unknown: 0
videos.fat -> Resolved: 129 / Unknown: 1
```


Good luck
## Post #87
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2016-12-16T09:27:10+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from Ekey
>
> Last update from me. Added ~67823 > (445543) > http://www65.zippyshare.com/v/G71EpEo9/file.html

Overall info:
Code: Select allXXXXX -> All Languages
common.fat -> Resolved: 5779 / Unknown: 256
dlc_ultra_textures.fat -> Resolved: 9316 / Unknown: 8
installpackage.fat -> Resolved: 8174 / Unknown: 876
installpackage_XXXXX.fat -> Resolved: 2616 / Unknown: 77
patch.fat -> Resolved: 51394 / Unknown: 4901
san_francisco.fat -> Resolved: 152515 / Unknown: 48495
san_francisco_cache.fat -> Resolved: 14989 / Unknown: 1013
san_francisco_hires.fat -> Resolved: 14710 / Unknown: 3454
san_francisco_preload.fat -> Resolved: 44247 / Unknown: 42466
san_francisco_XXXXX.fat -> Resolved: 14334 / Unknown: 7543
san_francisco_sound.fat -> Resolved: 4955 / Unknown: 526
san_francisco_sound_XXXXX.fat -> Resolved: 76514 / Unknown: 0
shadersobj.fat -> Resolved: 47357 / Unknown: 2977
sound.fat -> Resolved: 50 / Unknown: 0
videos.fat -> Resolved: 129 / Unknown: 1

Good luck

thank you for all the updates!
appreciate it!
## Post #88
- Username: disastorm
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Sep 20, 2014 5:20 pm
- Post datetime: 2016-12-16T13:54:24+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Does anyone know which file has most of the animations?
## Post #89
- Username: Marsbar
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Nov 01, 2014 7:04 am
- Post datetime: 2016-12-16T18:13:16+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Has anyone noticed code or anything indicating how to remove the small circle in the middle of the screen? It appears to be a style of reticle and it's always present except in camera mode and maybe a few other circumstances. Hope I'm not out of place asking about this.

I realize there are a lot of other symbols and text, mostly onscreen popup text bubbles, that you can't get rid of (yet) during gameplay just like in WD1. And they get in the way of immersion when in exploration mode imo. But with the popups you can sometimes position your character so they are gone from view. But not so with the small circle.
## Post #90
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2016-12-17T08:16:05+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Did anyone notice that there are Clara's model files in items.lib?
## Post #91
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-12-17T14:06:40+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Some research. feu files - it's normal flash file > just change header UEF to FWS
## Post #92
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2016-12-17T14:36:08+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Can someone please remove the startup sequence (Ubisoft and Nvidia logos)?
Or is it possible to do this with a command-line?
## Post #93
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-12-17T14:55:34+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Here some commands, but not all works

```
-animtracker
-automation
-bfname
-d3ddebug
-demo
-disabledrive
-disablemetadataservice
-dtnopopup
-editorpc
-enablehigh
-enableRequestTrace
-enablevedit
-exec
-eac_launcher
-fireadvanceifinvisible
-forcedrive
-forcemarketingpad2
-forcemarketingpad3
-forcemarketingpad4
-gkiterrormode
-ingameMapOverrideMap
-launcher_restarted
-localizationdisplayid
-localizationhideerror
-logFile
-login
-marketing
-nobf
-nocompile
-noexmouse
-noIntroVideo
-nologfile
-nomouse
-noonlinedebuglistener
-nopad
-nophysicstepworkerthread
-norender
-norumble
-nosave
-noshaderreports
-nosndocc
-nosndremote
-nosound
-nosplash
-nospuheightfield
-pad
-password
-phystimers
-profileLoading
-profileOperationsOnly
-roadnetworkHighResLoading
-runscriptindebug
-skiploggertool
-spawnpos
-splitscreen
-splitscreen4
-tf
-txtlang
-unittest
-vehiclecolordebug
```
## Post #94
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2016-12-17T15:18:43+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from disastorm
>
> Yea there seems to be some texture issue. It seems to use only some kind of generic texture for the various parts, I havn't been able to figure out how to get it to be anything else.
is there any way i can get the correct texture for the various parts?
it seems that there are many textures share one model parts.
## Post #95
- Username: guest12345
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Dec 18, 2016 1:25 am
- Post datetime: 2016-12-17T17:27:20+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

can anybody make a modification which allows for the player to be swapped with the co op characters? there's so many facial models available there, that would most likely work over marcus' rig.
## Post #96
- Username: bigodon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 18, 2016 2:24 am
- Post datetime: 2016-12-17T18:29:55+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

hi guys, interesting progress you are making here

let me ask, there is any file or mod to make this fog:


happens more often? this is pretty much happens, i must have over 20h of gaming and never saw this
i'm afraid i will finish the game without see this running here, maybe changing some weather settings?
## Post #97
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2016-12-18T09:53:53+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from redcomet
>
> disastorm wrote:Yea there seems to be some texture issue. It seems to use only some kind of generic texture for the various parts, I havn't been able to figure out how to get it to be anything else.
is there any way i can get the correct texture for the various parts?
it seems that there are many textures share one model parts.
my discovery

<object hash="C0EDBAE7">
    <field hash="0F43A933" type="BinHex">FFFFFFFFFFFFFFFF</field>
    <field hash="54D14F92" type="BinHex">FFFFFFFFFFFFFFFF</field>
    <field hash="4CAAD60F" type="BinHex">FFFFFFFFFFFFFFFF</field>
    <field hash="1DE90D38" type="BinHex" />
    <field hash="B8F64BF2" type="BinHex">FFFFFFFFFFFFFFFF</field>
    <field hash="24436F9E" type="BinHex">95020B4005000080</field>

field hash="24436F9E" handles the texture of the clothing item
the code is refer to the xml files in texturedb.lib

but some npc clothing's textures seem are not include in the texturedb.lib (eg:police,paramedic etc)
## Post #98
- Username: neburas
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Aug 06, 2012 6:01 pm
- Post datetime: 2016-12-18T10:03:37+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Adding new vehicles to car on demand successfully.



By the way anyone found how to increase traffic density?
WD2 has a much smaller traffic density than WD1, anywhere roads are empty.
## Post #99
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2016-12-18T10:48:21+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from neburas
>
> Adding new vehicles to car on demand successfully.



By the way anyone found how to increase traffic density?
WD2 has a much smaller traffic density than WD1, anywhere roads are empty.

couldn't agree more!
when i first saw the gameplay,i thought this problem was because it is on ps4 with fixed specs.
but turns out the retail version on all platform has the same small peds traffic density.
What a disappointment,i hope they will let us to customize the density of peds and traffic,otherwise it is nothing like SF.

btw,i see you are work great in making some custom vehicles on cars on demand,may i ask when will it come out?
(fun facts:driving police car in front of the police will get you arrest,i wonder will we get wanted if we driving the police car from cars on demand?)
## Post #100
- Username: neburas
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Aug 06, 2012 6:01 pm
- Post datetime: 2016-12-18T13:30:28+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from redcomet
>
> 
btw,i see you are work great in making some custom vehicles on cars on demand,may i ask when will it come out?
(fun facts:driving police car in front of the police will get you arrest,i wonder will we get wanted if we driving the police car from cars on demand?)

Unfortunately I can't take time on weekdays because I'm busy with my work during December.
But I'm working on it to release by the end of the month.  

All vehicles calling by cars on demand treated as "player owned" vehicles.
So you can ride police vehicle in front of police with no wanted or shoot.
I wish this game has more traffic density just like GTA5...
## Post #101
- Username: Freaky
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Dec 16, 2016 3:19 am
- Post datetime: 2016-12-18T14:38:00+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Has anyone figured out how "archetypes" are hashed?
Or how to figure out which archetype is which vehicle/entity?

Example Archetypes:
{9f28c077-03d3-46b6-8f6d-5dcb8b3f9095}
{13ea3ea6-99dc-4b8a-9cf0-367c13e14780}
{970dd1c2-3983-4cf9-a195-f251b22fbdb1}

The first of the above is this Lamborghini:


The other two are sports cars aswell.
## Post #102
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2016-12-18T15:34:39+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

@Neburas: May I ask how adding vehicles to the app works? Yesterday I tried it but I couldn't figure it out.
You could try to add the scissor lift to the app.
## Post #103
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-12-20T16:38:26+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Small update. Added ~13214 > (458757) > [http://www47.zippyshare.com/v/D8zEgUUf/file.html](http://www47.zippyshare.com/v/D8zEgUUf/file.html)

Overall info:

```
common.fat -> Resolved: 5870 / Unknown: 165
dlc_ultra_textures.fat -> Resolved: 9312 / Unknown: 7
installpackage.fat -> Resolved: 8946 / Unknown: 104
installpackage_XXXXX.fat -> Resolved: 2620 / Unknown: 73
patch.fat -> Resolved: 51706 / Unknown: 4589
san_francisco.fat -> Resolved: 155642 / Unknown: 45368
san_francisco_cache.fat -> Resolved: 15690 / Unknown: 312
san_francisco_hires.fat -> Resolved: 17896 / Unknown: 268
san_francisco_preload.fat -> Resolved: 49269 / Unknown: 37444
san_francisco_XXXXX.fat -> Resolved: 14710 / Unknown: 7167
san_francisco_sound.fat -> Resolved: 4994 / Unknown: 487
san_francisco_sound_XXXXX.fat -> Resolved: 76514 / Unknown: 0
shadersobj.fat -> Resolved: 47358 / Unknown: 2976
sound.fat -> Resolved: 50 / Unknown: 0
videos.fat -> Resolved: 129 / Unknown: 1
```
## Post #104
- Username: disastorm
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Sep 20, 2014 5:20 pm
- Post datetime: 2016-12-21T11:46:57+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from redcomet
>
> redcomet wrote:disastorm wrote:Yea there seems to be some texture issue. It seems to use only some kind of generic texture for the various parts, I havn't been able to figure out how to get it to be anything else.
is there any way i can get the correct texture for the various parts?
it seems that there are many textures share one model parts.
my discovery

<object hash="C0EDBAE7">
    <field hash="0F43A933" type="BinHex">FFFFFFFFFFFFFFFF</field>
    <field hash="54D14F92" type="BinHex">FFFFFFFFFFFFFFFF</field>
    <field hash="4CAAD60F" type="BinHex">FFFFFFFFFFFFFFFF</field>
    <field hash="1DE90D38" type="BinHex" />
    <field hash="B8F64BF2" type="BinHex">FFFFFFFFFFFFFFFF</field>
    <field hash="24436F9E" type="BinHex">95020B4005000080</field>

field hash="24436F9E" handles the texture of the clothing item
the code is refer to the xml files in texturedb.lib

but some npc clothing's textures seem are not include in the texturedb.lib (eg:police,paramedic etc)

Interesting, were you able to get other npc clothing to appear with textures?

I just found out how to get the clothes to show up in shops/inventory (replacing existing items), so you can convert a bunch of clothing and switch them around in-game.

In addition to setting an items.xml entry for a specific graphickit_part, you have to goto the graphickit_part xml entry for that item and you will see something that looks like the following:

```
        <field hash="CF68E402" type="BinHex">4354616743617465676F727953696E676C6553656C656374696F6E5769746856697369626C6554616743617465676F727900</field>
        <field hash="25368426" type="BinHex">909F9001</field>
        <field hash="BDB3B8D5" type="BinHex">4354616743617465676F727953696E676C6553656C656374696F6E5769746856697369626C6554616743617465676F727900</field>
        <field hash="401A8276" type="BinHex">909F9001</field>
        <field hash="F5391DFF" type="BinHex">C71D21C801000080</field>
        <field hash="8D9F3562" type="BinHex">C71D21C801000080</field>
        <field hash="E7575742" type="BinHex">FFFFFFFFFFFFFFFF</field>
      </object>

```

Specifically you will see the "C71D21C801000080" twice there.
The value at the bottom with all the "FFFFFFFFFFFFFFFF" is something like a "category". You replace it with an actual value, and it will show up in that category in your inventory.
Here are some example values I got from other items:
"DDD0721E02000080" # NORMCORE
"DED0721E02000080" # BIKER
"DFD0721E02000080" # URBAN
"E0D0721E02000080" # HIPPIE
"C61D21C801000080" # HIPSTER
"DBD0721E02000080" # SUITS
"DCD0721E02000080" # HIP-HOP
## Post #105
- Username: hqqttjiang
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Apr 19, 2012 10:27 am
- Post datetime: 2016-12-21T15:16:21+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

great works
## Post #106
- Username: Freaky
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Dec 16, 2016 3:19 am
- Post datetime: 2016-12-21T23:51:25+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

In case you are wondering what some of the CRC32 hashes mean, here is a table:
[https://gist.githubusercontent.com/anon ... 2_dump.txt](https://gist.githubusercontent.com/anonymous/58205a5fc0ee2f52ac169a31e5e3cb35/raw/6f841e99d1553e34887c0238cea69b8b2b7ab07a/wd2_crc32_dump.txt)
Sorry for the weird formatting and double entries

This should help with unknown fields.
Hopefully some kind soul has the time to put this information together and create the necessary files to make ConvertBinaryObject generate proper files. Otherwise I'll write a script for it sometime next week.
## Post #107
- Username: mlleemiles
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Sep 08, 2014 6:20 pm
- Post datetime: 2016-12-22T04:15:11+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from Freaky
>
> In case you are wondering what some of the CRC32 hashes mean, here is a table:
https://gist.githubusercontent.com/anon ... 2_dump.txt
Sorry for the weird formatting and double entries

This should help with unknown fields.
Hopefully some kind soul has the time to put this information together and create the necessary files to make ConvertBinaryObject generate proper files. Otherwise I'll write a script for it sometime next week.

Can you explain how do you get this dump? Would be very useful for WD1 modding as well!
## Post #108
- Username: Freaky
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Dec 16, 2016 3:19 am
- Post datetime: 2016-12-22T11:32:34+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from mlleemiles
>
> Can you explain how do you get this dump? Would be very useful for WD1 modding as well!

Those are all strings from the Disrupt_64.dll. I used IDA Pro to analyze the dll and exported all strings.
I then ran them through a script I wrote. I also added some strings that I found in the Gibbed project files.
## Post #109
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2016-12-22T14:34:26+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

after a week of investigation,i finally figured out something good.

from Clothing_Shops.Normcore.Shoes.Clogs01_Slingback_Black.xml in items.lib
    <object hash="73642E5E">
      <field hash="6816806D" type="BinHex">05</field>
      <field hash="71C8840A" type="BinHex">37A8D22403000080</field>
      <field hash="D935FAD9" type="BinHex">626CCA9302000080</field>
      <field hash="14088DCA" type="BinHex">FF</field>
      <field hash="1DF0076D" type="BinHex">FFFFFFFFFFFFFFFF</field>
      <field hash="730D0113" type="BinHex">FFFFFFFFFFFFFFFF</field>
      <field hash="7E23AAAE" type="BinHex">67726170686963735C6D6F64656C735C3078383030303030303239336361366336652E6D6F64656C00</field>
<field hash="A849532C" type="BinHex">95FF0D643C6E07B2</field>
      <object hash="37CF95BD">
        <field hash="2BE15935" type="BinHex">FFFFFFFF</field>
        <field hash="5177A0C7" type="BinHex">000000000000000000000000</field>
        <field hash="99298BDA" type="BinHex">000000000000000000000000</field>
        <field hash="FC176C73" type="BinHex">0000803F0000803F0000803F</field>
      </object>

from W2CH_PAR_avat_ma_fee.fill_ma_fee_clogs01_slingback_NORMCORE_black.xml in graphickit_models.lib
  <object hash="61205A45">
    <object hash="1A0E5F5C">
      <field hash="E735EB72" type="BinHex">67726170686963735C6D6F64656C735C3078383030303030303239336361366336652E6D6F64656C00</field>
<field hash="E4556387" type="BinHex">95FF0D643C6E07B2</field>


the field hash="A849532C" turns out is the one that handles the material of model part,
the problem why the material of police shirt and pants didn't show up probably is because their xml in graphickit_parts.lib doesn't include the texture that required,if you add it by yourself you can get back the texture.



in addition,if you replace marcus head by editing W2CH_MOD_nar_ava.avatar.xml in graphickit model.lib,you can get a swapped face with animation!
## Post #110
- Username: guest12345
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Dec 18, 2016 1:25 am
- Post datetime: 2016-12-22T16:48:55+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

in addition,if you replace marcus head by editing W2CH_MOD_nar_ava.avatar.xml in graphickit model.lib,you can get a swapped face with animation!


[/quote]

Cool!!! is there any way you can upload the aiden swap so some of us can play around with it? (not really good at this stuff)
## Post #111
- Username: disastorm
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Sep 20, 2014 5:20 pm
- Post datetime: 2016-12-22T17:10:43+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from redcomet
>
> after a week of investigation,i finally figured out something good.

from Clothing_Shops.Normcore.Shoes.Clogs01_Slingback_Black.xml in items.lib
    <object hash="73642E5E">
      <field hash="6816806D" type="BinHex">05</field>
      <field hash="71C8840A" type="BinHex">37A8D22403000080</field>
      <field hash="D935FAD9" type="BinHex">626CCA9302000080</field>
      <field hash="14088DCA" type="BinHex">FF</field>
      <field hash="1DF0076D" type="BinHex">FFFFFFFFFFFFFFFF</field>
      <field hash="730D0113" type="BinHex">FFFFFFFFFFFFFFFF</field>
      <field hash="7E23AAAE" type="BinHex">67726170686963735C6D6F64656C735C3078383030303030303239336361366336652E6D6F64656C00</field>
<field hash="A849532C" type="BinHex">95FF0D643C6E07B2</field>
      <object hash="37CF95BD">
        <field hash="2BE15935" type="BinHex">FFFFFFFF</field>
        <field hash="5177A0C7" type="BinHex">000000000000000000000000</field>
        <field hash="99298BDA" type="BinHex">000000000000000000000000</field>
        <field hash="FC176C73" type="BinHex">0000803F0000803F0000803F</field>
      </object>

from W2CH_PAR_avat_ma_fee.fill_ma_fee_clogs01_slingback_NORMCORE_black.xml in graphickit_models.lib
  <object hash="61205A45">
    <object hash="1A0E5F5C">
      <field hash="E735EB72" type="BinHex">67726170686963735C6D6F64656C735C3078383030303030303239336361366336652E6D6F64656C00</field>
<field hash="E4556387" type="BinHex">95FF0D643C6E07B2</field>


the field hash="A849532C" turns out is the one that handles the material of model part,
the problem why the material of police shirt and pants didn't show up probably is because their xml in graphickit_parts.lib doesn't include the texture that required,if you add it by yourself you can get back the texture.
Great job man, however actually I knew about A849532C from the beginning, and its reference from items.lib, but I couldn't get the texture working so didn't post it here, sorry about that.
But I  Never thought about adding it to graphickit_parts.lib. How did you add it to the part in graphickit_parts.lib, can you show an example? Did you just add another entry to the second section?

Also, for replacing the head, did you also have to unequip any items that give you the head, which one takes priority ?
## Post #112
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2016-12-23T06:18:03+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from guest12345
>
> Cool!!! is there any way you can upload the aiden swap so some of us can play around with it? (not really good at this stuff)
[https://drive.google.com/file/d/0B-TeCx ... sp=sharing](https://drive.google.com/file/d/0B-TeCxD9rGVMaWZpc0s2c0ZIYzQ/view?usp=sharing) 
edit:fixed version

note:before replacing the original patch.dat/fat,you need to load into the game with original patch.dat/fat
and change all your clothes to private eye's 
for the glasses,you need to wear the one that you can buy in biker shop.(there is only one glasses for sale in biker shop)

after changing the outfit,you can exit the game and replace the original files with the files that i provide


private eye outfit


biker glasses
## Post #113
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2016-12-23T07:05:42+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from disastorm
>
> redcomet wrote:after a week of investigation,i finally figured out something good.

from Clothing_Shops.Normcore.Shoes.Clogs01_Slingback_Black.xml in items.lib
    <object hash="73642E5E">
      <field hash="6816806D" type="BinHex">05</field>
      <field hash="71C8840A" type="BinHex">37A8D22403000080</field>
      <field hash="D935FAD9" type="BinHex">626CCA9302000080</field>
      <field hash="14088DCA" type="BinHex">FF</field>
      <field hash="1DF0076D" type="BinHex">FFFFFFFFFFFFFFFF</field>
      <field hash="730D0113" type="BinHex">FFFFFFFFFFFFFFFF</field>
      <field hash="7E23AAAE" type="BinHex">67726170686963735C6D6F64656C735C3078383030303030303239336361366336652E6D6F64656C00</field>
<field hash="A849532C" type="BinHex">95FF0D643C6E07B2</field>
      <object hash="37CF95BD">
        <field hash="2BE15935" type="BinHex">FFFFFFFF</field>
        <field hash="5177A0C7" type="BinHex">000000000000000000000000</field>
        <field hash="99298BDA" type="BinHex">000000000000000000000000</field>
        <field hash="FC176C73" type="BinHex">0000803F0000803F0000803F</field>
      </object>

from W2CH_PAR_avat_ma_fee.fill_ma_fee_clogs01_slingback_NORMCORE_black.xml in graphickit_models.lib
  <object hash="61205A45">
    <object hash="1A0E5F5C">
      <field hash="E735EB72" type="BinHex">67726170686963735C6D6F64656C735C3078383030303030303239336361366336652E6D6F64656C00</field>
<field hash="E4556387" type="BinHex">95FF0D643C6E07B2</field>


the field hash="A849532C" turns out is the one that handles the material of model part,
the problem why the material of police shirt and pants didn't show up probably is because their xml in graphickit_parts.lib doesn't include the texture that required,if you add it by yourself you can get back the texture.

Great job man, however actually I knew about A849532C from the beginning, and its reference from items.lib, but I couldn't get the texture working so didn't post it here, sorry about that.
But I  Never thought about adding it to graphickit_parts.lib. How did you add it to the part in graphickit_parts.lib, can you show an example? Did you just add another entry to the second section?

Also, for replacing the head, did you also have to unequip any items that give you the head, which one takes priority ?

i am not good at explaining,but i will do my best to deliver the clearest message

let's use the police short sleeves for example

from this,you can see the material value of the shirt is 'A1AA8A1500EA7CAB'


and yet there is no such thing in it's graphickit part xml


you can just add it back by following other's order,then it should do it.
## Post #114
- Username: disastorm
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Sep 20, 2014 5:20 pm
- Post datetime: 2016-12-23T12:30:54+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

thanks, i'm going to try that out.
## Post #115
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2016-12-23T12:55:47+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from disastorm
>
> thanks, i'm going to try that out.
glad that i help
## Post #116
- Username: disastorm
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Sep 20, 2014 5:20 pm
- Post datetime: 2016-12-23T14:32:40+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Thanks, the materials worked, great job.

I couldn't get the face to work though. I had it set in the models but when i dequipped my face item, it showed marcus' face again.
*edit nevermind i got it to show the other face. havn't tested the cutscenes yet, though.
## Post #117
- Username: Freaky
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Dec 16, 2016 3:19 am
- Post datetime: 2016-12-23T15:42:07+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Changing clothes on the fly
## Post #118
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2016-12-23T15:57:15+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from Freaky
>
> 

Changing clothes on the fly

oh,you were talking about this gif,i though it was supposed in the chatroom
## Post #119
- Username: judgereinhold2
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 14, 2016 10:49 am
- Post datetime: 2016-12-23T17:13:08+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Not gonna lie, the stuff you guys are posting and displaying is way over my head. I'm trying to learn it but yeesh. Too much for me!

Is there a way to make Marcus's head into a toilet?
## Post #120
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2016-12-23T23:31:35+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

So this is kind of related, I was playing an OLD UBISOFT game from my child hood and I really wanted to know if it's possible to extract the .DAT files, it's an old game so they are small files, it's for a game called Totally Spies Totally party. I know I know, but I'm serious UBISOFT made this game o.0.

Here are the Samples if anyone wants to take a crack at it any help would be much appreciated. 
Sorry about the drop box link, I think it might be a bit to big for the attachment side. 

[https://www.dropbox.com/s/j1npf3v36y6gv ... 1.DAT?dl=0](https://www.dropbox.com/s/j1npf3v36y6gvh4/BIGFILE1.DAT?dl=0)
## Post #121
- Username: guest12345
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Dec 18, 2016 1:25 am
- Post datetime: 2016-12-23T23:40:08+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from redcomet
>
> guest12345 wrote:Cool!!! is there any way you can upload the aiden swap so some of us can play around with it? (not really good at this stuff)
[https://drive.google.com/file/d/0B-TeCx ... sp=sharing](https://drive.google.com/file/d/0B-TeCxD9rGVMYjZNZXdjTTJLdGc/view?usp=sharing)

note:before replacing the original patch.dat/fat,you need to load into the game with original patch.dat/fat
and change all your clothes to private eye's 
for the glasses,you need to wear the one that you can buy in biker shop.(there is only one glasses for sale in biker shop)

after changing the outfit,you can exit the game and replace the original files with the files that i provide


hello, it doesn't seem that the game (steam version) is working with the patch.dat/.fat files that you sent, as the game starts up, goes to a black screen, and then quits out. *i have anti cheat disabled, have tried with enabled too*
if you can help, thank you!!!
## Post #122
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2016-12-24T03:45:57+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

sorry for the previous file i uploaded,that was a broken version because i messed up something.

here is the fixed version,plz download it,i will update the new link for my previous reply as well.

[https://drive.google.com/file/d/0B-TeCx ... sp=sharing](https://drive.google.com/file/d/0B-TeCxD9rGVMaWZpc0s2c0ZIYzQ/view?usp=sharing)
## Post #123
- Username: guest12345
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Dec 18, 2016 1:25 am
- Post datetime: 2016-12-24T05:04:33+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from redcomet
>
> sorry for the previous file i uploaded,that was a broken version because i messed up something.

here is the fixed version,plz download it,i will update the new link for my previous reply as well.

https://drive.google.com/file/d/0B-TeCx ... sp=sharing

thank u so much!!!
do you think this could work with the coop model faces? there's so many of them and i'm wondering if they're accessable and useable like this
## Post #124
- Username: neburas
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Aug 06, 2012 6:01 pm
- Post datetime: 2016-12-24T05:11:33+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Finally I did it. Added all available vehicles to app with thumbnails.(whopping 93 variations!)
Making 93 thumbnails was a soooooo painful work.



I'm working on final testing but can't figure out how to unlock adding vehicles yet. Gamesave with all main missions completed works fine.
But start new game, complete first mission, buy car on demand app, not work
## Post #125
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2016-12-24T05:23:26+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from guest12345
>
> redcomet wrote:sorry for the previous file i uploaded,that was a broken version because i messed up something.

here is the fixed version,plz download it,i will update the new link for my previous reply as well.

https://drive.google.com/file/d/0B-TeCx ... sp=sharing

thank u so much!!!
do you think this could work with the coop model faces? there's so many of them and i'm wondering if they're accessable and useable like this

yes,every in-game model can be work like this.
## Post #126
- Username: guest12345
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Dec 18, 2016 1:25 am
- Post datetime: 2016-12-24T05:25:43+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

[/quote]yes,every in-game model can be work like this.[/quote]

do you think you could point me in the direciton of how to put the co op faces onto marcus? (like u did with aiden)?
## Post #127
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2016-12-24T05:26:17+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from neburas
>
> Finally I did it. Added all available vehicles to app with thumbnails.(whopping 93 variations!)
Making 93 thumbnails was a soooooo painful work.



I'm working on final testing but can't figure out how to unlock adding vehicles yet. Gamesave with all main missions completed works fine.
But start new game, complete first mission, buy car on demand app, not work

maybe it is because the story was not yet introduced the app so you can't use it.
## Post #128
- Username: guest12345
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Dec 18, 2016 1:25 am
- Post datetime: 2016-12-24T05:31:41+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from redcomet
>
> guest12345 wrote:redcomet wrote:sorry for the previous file i uploaded,that was a broken version because i messed up something.

here is the fixed version,plz download it,i will update the new link for my previous reply as well.

https://drive.google.com/file/d/0B-TeCx ... sp=sharing

thank u so much!!!
do you think this could work with the coop model faces? there's so many of them and i'm wondering if they're accessable and useable like this

yes,every in-game model can be work like this.

do you know how to replace aiden's face in this swap with the face of co op avatar 03?
## Post #129
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2016-12-24T05:49:26+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from guest12345
>
> do you know how to replace aiden's face in this swap with the face of co op avatar 03?

first thing first,you need to locate the coop avatar 03's xml file from graphickit model converted folder,and then search for the head model by searching the values of the models from the xml in graphickit parts converted folder.
once you know which model value is head,copy that definition and replace the head definition in default avatar xml.

i know it is difficult to understand with my expression,it will be more easier to understand with image though.
you can read the tutorial from disastorm at page 3 in this thread.
## Post #130
- Username: guest12345
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Dec 18, 2016 1:25 am
- Post datetime: 2016-12-24T05:56:51+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from redcomet
>
> guest12345 wrote:do you know how to replace aiden's face in this swap with the face of co op avatar 03?

first thing first,you need to locate the coop avatar 03's xml file from graphickit model converted folder,and then search for the head model by searching the values of the models from the xml in graphickit parts converted folder.
once you know which model value is head,copy that definition and replace the head definition in default avatar xml.

i know it is difficult to understand with my expression,it will be more easier to understand with image though.
you can read the tutorial from disastorm at page 3 in this thread.

ok, i am not v good at this stuff but i will attempt to try it, thanks for the information
## Post #131
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2016-12-24T06:05:12+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from guest12345
>
> redcomet wrote:guest12345 wrote:do you know how to replace aiden's face in this swap with the face of co op avatar 03?

first thing first,you need to locate the coop avatar 03's xml file from graphickit model converted folder,and then search for the head model by searching the values of the models from the xml in graphickit parts converted folder.
once you know which model value is head,copy that definition and replace the head definition in default avatar xml.

i know it is difficult to understand with my expression,it will be more easier to understand with image though.
you can read the tutorial from disastorm at page 3 in this thread.

ok, i am not v good at this stuff but i will attempt to try it, thanks for the information
sry,not page 3 but page 5
## Post #132
- Username: guest12345
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Dec 18, 2016 1:25 am
- Post datetime: 2016-12-24T15:09:21+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from redcomet
>
> 

ok, i am not v good at this stuff but i will attempt to try it, thanks for the information
sry,not page 3 but page 5[/quote][/quote]



no luck, this stuff is 2 hard for me. ah well. thanks for your aiden swap man
## Post #133
- Username: paulscottttt
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Jan 25, 2016 8:34 am
- Post datetime: 2016-12-24T23:12:08+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from redcomet
>
> sorry for the previous file i uploaded,that was a broken version because i messed up something.

here is the fixed version,plz download it,i will update the new link for my previous reply as well.

https://drive.google.com/file/d/0B-TeCx ... sp=sharing

any way of just replacing the clothes but not face or hands?
## Post #134
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2016-12-25T00:29:42+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from paulscottttt
>
> redcomet wrote:sorry for the previous file i uploaded,that was a broken version because i messed up something.

here is the fixed version,plz download it,i will update the new link for my previous reply as well.

https://drive.google.com/file/d/0B-TeCx ... sp=sharing

any way of just replacing the clothes but not face or hands?
You can get the coat by completing Aidan's side mission
## Post #135
- Username: Xecutioner
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Oct 12, 2016 6:51 pm
- Post datetime: 2016-12-26T12:32:14+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Possible to increase traffic cars density ?? and parked too ?
## Post #136
- Username: paulscottttt
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Jan 25, 2016 8:34 am
- Post datetime: 2016-12-26T15:36:45+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

can anyone remove the sunglasses and the bag?
i did try but have no idea how to repack the.lib
## Post #137
- Username: guest12345
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Dec 18, 2016 1:25 am
- Post datetime: 2016-12-27T05:22:16+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

can anybody replace marcus with co op character 3? i've been trying to get it to work and i've had no luck, anybody willing to take a crack at it? (and if you end up doing it successfully, put the patch.dat/.fat up for download?)
## Post #138
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2017-01-02T16:59:46+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Does anyone know where the textures for the characters are located in WD2?
## Post #139
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2017-01-04T13:44:14+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

I managed to modify the AK47 weapon. I made a video too but it's not up-to-date. It now has 200 bullets per clip, infinite ammo, near to zero recoil, it destroys cars in one shot and can shoot through walls. It also sounds like the NewBoySerge sniper rifle.

[Link to the video](https://www.youtube.com/watch?v=gk4waKGz_WQ)
## Post #140
- Username: 089fe972
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jan 11, 2017 1:55 am
- Post datetime: 2017-01-10T18:00:55+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

bit of a strange question, I really enjoy the art in this game and wanted to watch the videos again, wd2extract on videos.dat/fat resulted in 130 files named 0xA to 0xB, but I have no idea what they are, do they need to be converted to be played or viewed? according to the file lists posted in here they should be bik files but they don't appear to be mp4 format or bik or whatever, I'm guessing theres another step? tia.
## Post #141
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2017-01-11T06:37:57+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

i wonder if we can edit the file to make our character get in any faction(fbi or sfpd .etc)

does anyone know which file refer to the spider tank?
just wanted to see if we can spawn a spider tank in free roma.(maybe using cars on demand?)
## Post #142
- Username: Xecutioner
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Oct 12, 2016 6:51 pm
- Post datetime: 2017-01-11T16:01:22+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

So forum is dead ? why nobody work for release a extractor for this game ?
## Post #143
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-11T16:10:42+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

because extractor was done long time ago
## Post #144
- Username: Xecutioner
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Oct 12, 2016 6:51 pm
- Post datetime: 2017-01-11T16:41:00+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from daemon1
>
> because extractor was done long time ago

done ? finish for people user or death ? 

we juste want to modify some texture and other stuff like wd 1
## Post #145
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-11T17:05:27+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

extractor was released here, read the thread
## Post #146
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-01-13T10:45:48+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from volfin
>
> about the compression, this is the same problem Aluigi came across when unpacking another Ubisoft title, Far Cry: Primal.  It also uses LZMA and an unknown LZ4.  So that's something to keep in mind, perhaps some clues can be found in one game to benefit the other... http://www.zenhax.com/viewtopic.php?f=9&t=378#p11725
Probably a long shot, but I'm posting here to ask whether it would be possible to update Gibbed's Dunia2 tools to support the Far Cry: Primal compression? After reading [Janne252's post on Far Cry Primal Modding](https://www.janne252.com/blog/view/id/3/title/first-look-at-far-cry-primal-and-its-mod-ability/), I have a hunch the game isn't all that different from Far Cry 4, aside from the incompatible compression scheme. So I thought: perhaps it's similar to the one used in Watch Dogs 2? I attached a sample dat/fat:

 FarCryPrimal_multicommon_debug_dat.zip
Smallest Far Cry Primal dat/fat I could find. (122.33 KiB) Downloaded 80 times

I wouldn't know where to start trying to unpack the data, let alone update the Dunia tools. Seeing the great work that has been done here, perhaps someone (daemon1, Sir Kane?) could have a look and see if they can crack the compression?

Perhaps related, there are certain binary files Far Cry 4 uses, which can't be unpacked by Dunia either. Examples are the oasisstrings.bin (info [here, on XeNTaX](http://forum.xentax.com/viewtopic.php?p=83467#p83467)) and depload.dat (example [here](http://steve.farcry.eu/files/FarCry4_deploads.zip), along with what appears to be a sourcefile for them, somehow stored alongside in the main and dlc dat file). Perhaps the compression is the same in all cases?
## Post #147
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-13T15:21:22+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from bouvrie
>
> perhaps it's similar to the one used in Watch Dogs 2

Yes, I checked that before, and compression is the same. I will not update Dunia2 tools. I can make my own tool.
## Post #148
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-01-13T23:22:39+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from daemon1
>
> Yes, I checked that before, and compression is the same. I will not update Dunia2 tools. I can make my own tool.
Wow, that would be really cool! Though I'd imagine it being quite some more work to support all features of the Dunia2 toolchain (Unpack, ConvertBinaryObject: decompiling binary files to XML for editing & dealing with casting BinHex to other types, then compiling them again, Pack, ConvertXML/RML), an Unpack+Pack would suffice provided Dunia2's ConvertBinaryObject is still compatible with the FC:Primal binary objects.

Are you by any chance referring to the Far Cry 4 depload files' compression as well? I think being able to edit that file could potentially unlock adding extra objects to the game, which would be a nice boost for moddability.
## Post #149
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-14T05:35:49+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from bouvrie
>
> ConvertBinaryObject
I didn't know about that feature. What it does? What files are those binary files?

Also, how can you say its "not different from Far Cry 4", when no single file was decompressed? It can be very different. And it usually is.

> Reply from bouvrie
>
> Are you by any chance referring to the Far Cry 4 depload files' compression as well?
From what is said in the link you gave, LZO1x is used in them, its not the same type as in data files, but its known and can be easily decompressed, even the example is given there.
## Post #150
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-01-14T12:19:45+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

// Excuse me, this topic is going beyond Watch Dogs 2 a bit. Didn't want to hijack the thread. -bouvrie

> Reply from daemon1
>
> Also, how can you say its "not different from Far Cry 4", when no single file was decompressed? It can be very different. And it usually is.
Sorry, I'm looking at this from a game modder's perspective. From that view, it is known that Far Cry games released over the years have been re-using the engine framework, filenames, techniques. I.e. having filenames and strings stored and referred to by CRC(32b/64 ISO polynomial) hashes, filenames (i.e. "nomadobjecttemplates.fcb" game defining parameters being present in both FC3 and FC4) and game concepts. In case of Far Cry 4, they even still included remnants of Far Cry 3 code and assets, only some of which seem to be unused by the game. Since the controversy about the [Far Cry Primal gameplay map reusing Far Cry 4's heightmaps](http://kotaku.com/turns-out-ubisoft-used-far-cry-4s-map-to-make-far-cry-p-1762497550), along with using the same filenames as FC4, I bet modding the game would turn out similar to Far Cry 4. 

> Reply from daemon1
>
> bouvrie wrote:Are you by any chance referring to the Far Cry 4 depload files' compression as well?
From what is said in the link you gave, LZO1x is used in them, its not the same type as in data files, but its known and can be easily decompressed, even the example is given there.
As for the oasisstrings file, the modding tool available there was intended for Far Cry 3 format. And for a while the FC4 oasisstrings could be (de-)compressed, but Ubi changed the compression in an update to the game. If you care, I upped the tool along with examples of the FC3 bin format and new FC4 compressed file [here](http://steve.farcry.eu/files/JGR.Dunia2.ConvertXml_with_FC3FC4_oasisstring_examples.zip). The tool doesn't work on the depload file out of the box, I don't know if that's because of different compression or unexpected filetype (the tool wasn't designed for it).

> Reply from daemon1
>
> bouvrie wrote:ConvertBinaryObjectI didn't know about that feature. What it does? What files are those binary files?
Short version (longer version [here](http://farcrymods.freeforums.net/post/3050/thread) goes into more, including the Gibbed.Dunia2.ConvertXml.exe tool): Far Cry *.dat/fat pairs unpack to smaller files. Some of those binary files (usually *.FCB or *.BIN) can be converted to *.XML and detail the core mechanics of the game. ConvertBinaryObject allows to convert between binary <--> XML. 
Also, the XML references data using hashes and BinHex values, i.e.: 
FC4 file patch_hd.dat\entityarchetypeslibrary\7592896315570.ark.fcb, converted to raw XML:
```
<object hash="256A1FF9">
  <field hash="8EDB0295" type="BinHex">B240E3DBE7060000</field>
  <field hash="B435B769" type="BinHex">656E74697479617263686574797065736C6962726172795C373539323839363331353537302E61726B2E66636200</field>
  <field hash="2D90D933" type="BinHex">F1DC4190CB75E2EC</field>
  <field hash="FE11D138" type="BinHex">4643332F504B4D2E4D756C746900</field>
  <field hash="6EA390DB" type="BinHex">776561706F6E733A6663332F706B6D2E6D756C746900</field>
  <object hash="0984415E">
    <field hash="B9295CC7" type="BinHex">776561706F6E733A4643332F504B4D2E4D756C746900</field>
    <field hash="D2B3429E" type="BinHex">43456E7469747900</field>
    <field hash="1875AE89" type="BinHex">6750C950</field>
    <field hash="ADC3BD93" type="BinHex">22000000</field>
    <field hash="B554978A" type="BinHex">00</field>
    <field hash="B435B769" type="BinHex">656E74697479617263686574797065736C6962726172795C373539323839363331353537302E61726B2E66636200</field>
    <field hash="2D90D933" type="BinHex">F1DC4190CB75E2EC</field>
    <object hash="A115F62D">
      <object hash="049C7D70">
        <field hash="FEE21F0D" type="BinHex">00</field>
        <field hash="2A7BCA49" type="BinHex">67726170686963735C5F636F6D6D6F6E5C776561706F6E735C706B6D5C706B6D2E786D6C00</field>
        <field hash="9C39465B" type="BinHex">E3B40BC6959DA01C</field>
      </object>
  </object>
</object>
```

ConvertBinaryObject allows to further translate those BinHex values if you specify the type they should translate to, in a separate XML file used for decoding. The above file would then translate to:
FC4 file patch_hd.dat\entityarchetypeslibrary\7592896315570.ark.fcb, converted to named and typecasted XML:
```
  <field name="disLibItemId" type="Id64">7592896315570</field>
  <field hash="B435B769" type="String">entityarchetypeslibrary\7592896315570.ark.fcb</field>
  <field hash="2D90D933" type="UInt64">17427876748161573612</field>
  <field name="Name" type="StringId">FC3/PKM.Multi</field>
  <field hash="6EA390DB" type="String">weapons:fc3/pkm.multi</field>
  <object name="Entity">
    <field name="hidName" type="StringId">weapons:FC3/PKM.Multi</field>
    <field name="text_hidEntityClass" type="String">CEntity</field>
    <field name="hidEntityClass" type="Hash32">6750C950</field>
    <field name="hidResourceCount" type="Int32">34</field>
    <field name="hidConstEntity" type="Boolean">False</field>
    <field hash="B435B769" type="String">entityarchetypeslibrary\7592896315570.ark.fcb</field>
    <field hash="2D90D933" type="UInt64">17427876748161573612</field>
    <object name="Components">
      <object name="CFileDescriptorComponent">
        <field name="hidHasAliasName" type="Boolean">False</field>
        <field name="text_fileName" type="String">graphics\_common\weapons\pkm\pkm.xml</field>
        <field name="fileName" type="BinHex">E3B40BC6959DA01C</field>
      </object>
  </object>
</object>

```

By the way, that XML is a snippet of the Far Cry 4 file "patch_hd.dat\entityarchetypeslibrary\7592896315570.ark.fcb", added in a later game patch to FC4. See how it blatantly reuses "weapons:fc3/pkm.multi" from Far Cry 3 in Far Cry 4? That's why I believe Far Cry Primal would perhaps feature different compression, but the concepts for further modding should be the same. 

One thing I noticed with Sir Kane's Watch Dogs 2 extractor, is that [it manages to translate the filepath/name hashes from the dat/fat into the actual filenames](http://forum.xentax.com/viewtopic.php?p=124884#p124884). The Dunia2 toolset used for Far Cry modding doesn't, and instead uses filelists for modders to dictionary attack them. With no match, the CRC64 hash is used as a filename. It would be very cool if that trick can be reproduced with Far Cry 4 (and/or Primal), because at this time, the [Far Cry 4 modders' dictionary](http://janne252.com/downloads/fc4/gibbed_fc4project.zip) understands about 102469/357260 (28%) of Far Cry 4's filelist.
## Post #151
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-14T14:29:58+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from bouvrie
>
> // Excuse me, this topic is going beyond Watch Dogs 2 a bit. Didn't want to hijack the thread. -bouvrie

ok lets go here, I have some progress already: [viewtopic.php?f=16&t=15735](http://forum.xentax.com/viewtopic.php?f=16&t=15735)
## Post #152
- Username: RoguishRonin
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 19, 2017 2:07 am
- Post datetime: 2017-01-18T18:47:50+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

How would I go about extracting the audio clips and have convert them to WAV, MP3, or OGG?
## Post #153
- Username: Xecutioner
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Oct 12, 2016 6:51 pm
- Post datetime: 2017-01-19T11:30:53+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from daemon1
>
> extractor was released here, read the thread

Oh yes ok thanks! 

Anyway to find location of texture sign billboards ?? i don't find it after i extract all files
## Post #154
- Username: Haytham
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Oct 27, 2014 7:06 am
- Post datetime: 2017-01-20T06:08:17+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Please! Created Watch Dogs 2 blender xbg-xbt import/export script!
## Post #155
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2017-01-21T09:49:57+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Where is the link in the items.lib vehicle files to the vehicle files in vehicle.lib?
I just can't figure it out!
## Post #156
- Username: TigraPolosatiy
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jan 23, 2017 7:12 pm
- Post datetime: 2017-01-23T11:27:08+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Hi everyone.
I converted some textures from .xbt to .dds and edited it.
Tell me please how to correctly convert textures back into .xbt?
The game doesn't perceive them after compiling into patch.dat/fat 
It's just blank...  

Modified textures:
\graphics\characters\wd2\avatar\torso\avat_ma_tor_coataiden01\avat_ma_tor_coataiden01_coatbrown_c.xbt
\graphics\characters\wd2\avatar\torso\avat_ma_tor_coataiden01\avat_ma_tor_coataiden01_coatbrown_c_high.xbt
\graphics\characters\wd2\avatar\torso\avat_ma_tor_coataiden01\avat_ma_tor_coataiden01_coatbrown_c_med.xbt
## Post #157
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-23T17:03:50+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from TigraPolosatiy
>
> Hi everyone.
I converted some textures from .xbt to .dds and edited it.
Tell me please how to correctly convert textures back into .xbt?
The game doesn't perceive them after compiling into patch.dat/fat 
It's just blank...  

Modified textures:
\graphics\characters\wd2\avatar\torso\avat_ma_tor_coataiden01\avat_ma_tor_coataiden01_coatbrown_c.xbt
\graphics\characters\wd2\avatar\torso\avat_ma_tor_coataiden01\avat_ma_tor_coataiden01_coatbrown_c_high.xbt
\graphics\characters\wd2\avatar\torso\avat_ma_tor_coataiden01\avat_ma_tor_coataiden01_coatbrown_c_med.xbt

if you look at the xbt and the DDS side by side, you can see xbt is just a DDS with a header laid on top. so just cut the header off the old xbt, and attach to your new dds, and now it's an xbt.  I'd make sure the resolution was the same as the original for maximum compatibility.
## Post #158
- Username: TigraPolosatiy
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jan 23, 2017 7:12 pm
- Post datetime: 2017-01-23T17:26:12+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from volfin
>
> 
if you look at the xbt and the DDS side by side, you can see xbt is just a DDS with a header laid on top. so just cut the header off the old xbt, and attach to your new dds, and now it's an xbt.  I'd make sure the resolution was the same as the original for maximum compatibility.

Oh. I didn't notice it. Now I will try to repack ...
## Post #159
- Username: TigraPolosatiy
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jan 23, 2017 7:12 pm
- Post datetime: 2017-01-23T19:11:08+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Yes!  
Thanks volfin!!!
## Post #160
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2017-01-23T20:31:53+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Very important!

Does someone know which file to modify if I want to edit the camera of specific vehicles? Especially 3rd person driving camera. Is it in cameracontext.lib? And where's the link between the vehicle files and the camera files?
## Post #161
- Username: griffin02
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jan 24, 2017 9:28 am
- Post datetime: 2017-01-24T01:33:36+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Well I got this idea from @Freaky who was asking about archtypes. I took the time to gather what I could

This is just a small example


Here's the list, it's a double vector, so vector element contains the name and hash, however some of the names are mangled and I didn't bother to fix them but it's still pretty straight forward
Excuse the formatting(And I didn't see a spoiler tag to hide this)

```

```
## Post #162
- Username: guest12345
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Dec 18, 2016 1:25 am
- Post datetime: 2017-01-24T03:04:39+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from guest12345
>
> can anybody replace marcus with co op character 3? i've been trying to get it to work and i've had no luck, anybody willing to take a crack at it? (and if you end up doing it successfully, put the patch.dat/.fat up for download?)

still have no luck with this, anybody made any progress on co op character model swapping?
## Post #163
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2017-01-24T11:42:57+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Find attached 2 bik files, which will skip the 1st 2 intro_movies. If anyone happens to know the 3rd one, let me know...!
Checked all bik/bink files/locations, but not part of the current list. Also checked headers (first 3 bytes) of hex_files in [common - installpackage - installpackage_english - videos]: no trace either...  (I made a little batchfile for that purpose, in combo with SFK; if anyone is interested)

To enable (btw: process takes some time ~5-10min):
- extract patch.fat
- extract attached rar in root 'patch' folder
- patch patch.fat (make backup of original one first!)

p
[WD2_NoIntro.rar](https://xentaxbackup.github.io/file/12279_WD2_NoIntro.rar)
## Post #164
- Username: doncarlone
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 18, 2014 5:24 pm
- Post datetime: 2017-01-24T11:59:54+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

How to open language files with .loc extension?
## Post #165
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2017-01-24T18:37:11+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from Ekey
>
> Some research. feu files - it's normal flash file > just change header UEF to FWSWhat else needs to be changed (besides header/extension change) in order to get them played via (pc) mediaplayer (like VLC)? I'm thinking that the last/3rd intro movie might be a flash (instead of bink) file?!
## Post #166
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2017-01-25T12:20:02+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Here is how to change the body of the character:
Open the file for Marcus in graphickit_models.lib (something with avatar). The D935FAD9 field is the file ID of the graphickit_parts.lib files. Copy the value and search for that in the graphickit_parts XMLs. The result's file name shows what part it is (head, arms, torso, ...). Now open the coop character file in graphickit_models.lib with which you want to replace Marcus' body with, search the values again and copy the head and body and replace the original ones with them.
Et voila, now you only have to repack it and have some fun.

Btw you can also delete the entries of the earbuds, glasses and backpack in the models files if you want to.
## Post #167
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2017-01-25T13:15:53+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Attached 2 little batchfiles to do the job (using SFK ~ Swiss File Knife).
p

ps: while SFK has a very small footprint, could not add it to rar. So google and download SFK from their site. I was using sfk181 (latest 183), so you'll need to edit batchfiles accordingly...
ps2: batchfiles are "quick & dirty": feel free to change/adapt; and even take ownership if you like. if you need help, just pm
ps3: can easily be adapted to work for other extensions.
[WD2_Tools.rar](https://xentaxbackup.github.io/file/12287_WD2_Tools.rar)
## Post #168
- Username: JimmyJ
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Dec 21, 2011 8:54 am
- Post datetime: 2017-01-25T19:33:09+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Is it available to import xbg files in 3d tools?
## Post #169
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-25T20:59:13+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from JimmyJ
>
> Is it available to import xbg files in 3d tools?

I released an importer for WD2 for blender here: [viewtopic.php?p=126171#p126171](http://forum.xentax.com/viewtopic.php?p=126171#p126171)

It's first draft, so if you find any issues let me know, i'll try to resolve them.
## Post #170
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2017-01-25T21:42:17+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Finally some fresh wind here 
Does someone know how to change the camera of specific vehicles? Where are the files that manage this? And where is the link to the vehicle files?
## Post #171
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2017-01-26T02:24:43+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

I have managed to spawn a helicopter on ground by editing the vehiclespawninfo.lib in common.dat
you can enter the vehicle,but once u enter it,your camera will suddenly go to the other place.... and you won't know if you are controlling it...
strange....
## Post #172
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2017-01-26T07:37:50+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Man this is the reason I ask for help on the camera! We could work together on this!
Maybe we then could archieve a working mod one day...
## Post #173
- Username: TigraPolosatiy
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jan 23, 2017 7:12 pm
- Post datetime: 2017-01-26T15:31:19+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

One more question:
Where the Paint jobs textures, for "Car on Demand" are located?
I would like to replace one of this colorings.
## Post #174
- Username: danielkarloskar1
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Aug 13, 2016 6:10 am
- Post datetime: 2017-01-26T18:26:23+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Great to see a thread about this game =)  I read on reddit that the tools was updated, can i find these unpack and pack tools in this thread?
Thanks for your work!
## Post #175
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2017-01-26T19:00:56+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Page 2 and 4 of this thread.
## Post #176
- Username: TigraPolosatiy
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jan 23, 2017 7:12 pm
- Post datetime: 2017-01-26T21:10:50+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

I had troubles with Paul44's batchfiles (resolved already  ). So there is his quote

> - extract the complete rar in a 'working' folder
>
> - create an [XBT] subfolder, and dump the files you'd like to edit/convert in here
>
> - run [WD2_1_XBT_Convert.bat]: which looks in said subfolder, and processes them
>
> a) creates a T_Header subfolder and places 'header' files in there
>
> b) creates a T_DDS subfolder and places 'DDS' files in there
>
> 
>
> - once you've edited the DDS files (keep their original filenames !), run [WD2_2_DDS_Convert.bat]
>
> - which processes all files in T_DDS subfolder: adds the corresponding header to each DDS file
>
> - and dumps the resulting file in XBT_UPD subfolder
Good luck
## Post #177
- Username: TigraPolosatiy
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jan 23, 2017 7:12 pm
- Post datetime: 2017-01-26T22:41:34+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

BTW about Paint jobs for "Car on Demand".
I found all the textures    and something interesting  

Among the usual paintjobs I found one belonging to the development team 

Take a look at this:


And paintjob called "ubisoft_employee"
## Post #178
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2017-01-27T12:15:07+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Does the game read lua files that were decrypted with unluac?
## Post #179
- Username: ultima
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Dec 08, 2009 12:37 pm
- Post datetime: 2017-01-28T18:14:35+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Hello, could anyone explain to me in detail how to rebuild graphickit_models.lib please?

My file made more than 88 mo, and once patched, the game lag enormously.

thank you in advance.

(Sorry for my bad english)
## Post #180
- Username: TigraPolosatiy
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jan 23, 2017 7:12 pm
- Post datetime: 2017-01-30T09:40:13+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Important question!
How to convert ZOLA dds files ot DXT1? nVidia plugin can't read this images.   





Please help.
## Post #181
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-30T19:14:05+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Must be something wrong with your setup, or your file is corrupted somehow. because  A) DTX1 is one of the earliest and most standard formats, literally every app that supports DDS can open it.  
And B): I tried it with every app I have, and all had no problem:

Photoshop with Nvida Plugin:


Photoshop with Intel texturworks plugin:


XnView:


IrfanView/Visual studio/ and so on and so on. nothing had any problem with it.
## Post #182
- Username: TigraPolosatiy
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jan 23, 2017 7:12 pm
- Post datetime: 2017-01-31T08:30:33+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from volfin
>
> Must be something wrong with your setup, or your file is corrupted somehow. because  A) DTX1 is one of the earliest and most standard formats, literally every app that supports DDS can open it.  
And B): I tried it with every app I have, and all had no problem:
***
IrfanView/Visual studio/ and so on and so on. nothing had any problem with it.

Look closely.
The problem not in
"fill_m_tor_jacketgoose01_iraq_c_high(med).xbt" but in
"fill_m_tor_jacketgoose01_iraq_mhd_high(med).xbt" textures group 
Try to convert and open them.
## Post #183
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-31T18:09:41+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

these ZOLA files are not DTX1, in fact I'd say they are not any graphics format. I scanned the source code to Nvidia's Texture Tools, and there's no ZOLA FOUR_CC code anywhere in their code. 

The name ZOLA however brings up interesting pages.
[http://dl.acm.org/citation.cfm?id=28146 ... N=56218111](http://dl.acm.org/citation.cfm?id=2814684&CFID=722993500&CFTOKEN=56218111)

Jaroslaw Zola co-wrote a paper on Dimensionality reduction using GPUs. 

So one can theorize a few things:
A) it's some format Nvida hasn't release publically. 
B) it's a format Ubisoft developed internally.

and
A) it's probably something used for CUDA Compute to do who knows what. 

But it's likely not image data.
## Post #184
- Username: TigraPolosatiy
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jan 23, 2017 7:12 pm
- Post datetime: 2017-02-01T01:47:50+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from volfin
>
> these ZOLA files are not DTX1, in fact I'd say they are not any graphics format. I scanned the source code to Nvidia's Texture Tools, and there's no ZOLA FOUR_CC code anywhere in their code. 

The name ZOLA however brings up interesting pages.
http://dl.acm.org/citation.cfm?id=28146 ... N=56218111

Jaroslaw Zola co-wrote a paper on Dimensionality reduction using GPUs. 

So one can theorize a few things:
A) it's some format Nvida hasn't release publically. 
B) it's a format Ubisoft developed internally.

and
A) it's probably something used for CUDA Compute to do who knows what. 

But it's likely not image data.
Hmm. But it has to be. Because the group has the the prefixes "c" (color), "high" (1024x1024), "med" (512x512) like other textures.
## Post #185
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-02-01T04:08:48+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

If they are using them as source data for a GPU computation, then of course they have multiple sizes to match texture resolution. Doesn't mean it is a texture. If you have diffuse/normal/and specular, then this texture is unnecessary.

I mean what exactly is missing from this shirt that you dont' see on the texture I posted above? nothing. that's all there is to it.



Anyway you're welcome to spend the rest of your life looking for the Loch Ness monster in the files. No skin off my nose.
## Post #186
- Username: TigraPolosatiy
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jan 23, 2017 7:12 pm
- Post datetime: 2017-02-01T06:32:37+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from volfin
>
> If they are using them as source data for a GPU computation, then of course they have multiple sizes to match texture resolution. Doesn't mean it is a texture. If you have diffuse/normal/and specular, then this texture is unnecessary.

I mean what exactly is missing from this shirt that you dont' see on the texture I posted above? nothing. that's all there is to it.



Anyway you're welcome to spend the rest of your life looking for the Loch Ness monster in the files. No skin off my nose.
Hahahah 
How about orange waistcoat itself? There should be texture for this part
## Post #187
- Username: TigraPolosatiy
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jan 23, 2017 7:12 pm
- Post datetime: 2017-02-04T19:20:31+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Now i happy  
[https://youtu.be/hqmzeiPEcrE](https://youtu.be/hqmzeiPEcrE)
## Post #188
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2017-02-04T19:50:32+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Does someone want to help me with making the spider drone available in free roam?
It's possible to order the spider drone via Car on Demand but it's completely broken.
Atm I don't know if the game handles it as a vehicle or as a character...
Maybe the solution is to make the game load the spider's model instead of Marcus - or maybe we have to change the object properties (the files that define if a vehicle is enterable or hackable, etc.) cause in the mission it's a hackable object, but I don't know where this is located or maybe it's hardcoded?

This would be the biggest mod if we manage to figure it out!

Maybe the mission scripts help us with this, if someone here has lua coding knowledge cause they're lua files (decompilable with unluac). The first game could read decompiled lua scripts without compiling again (which is impossible).
## Post #189
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2017-02-05T05:40:35+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from CobraGamer
>
> Does someone want to help me with making the spider drone available in free roam?
It's possible to order the spider drone via Car on Demand but it's completely broken.
Atm I don't know if the game handles it as a vehicle or as a character...
Maybe the solution is to make the game load the spider's model instead of Marcus - or maybe we have to change the object properties (the files that define if a vehicle is enterable or hackable, etc.) cause in the mission it's a hackable object, but I don't know where this is located or maybe it's hardcoded?

This would be the biggest mod if we manage to figure it out!

Maybe the mission scripts help us with this, if someone here has lua coding knowledge cause they're lua files (decompilable with unluac). The first game could read decompiled lua scripts without compiling again (which is impossible).


you can change wrench's robot to mini spider drone without any problem,but if you change any vehicle to it,it will be broken.
## Post #190
- Username: dracconus
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Feb 02, 2017 11:59 am
- Post datetime: 2017-02-05T08:24:41+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

So since the WD2 game already has Patch.dat/fat what would I do if I wanted to change things that were in the engine settings of the common.dat/fat files without recompressing the entire thing into an "on the fly patch?"
## Post #191
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2017-02-05T13:15:00+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

@redcomet: Thanks for the tip! Maybe through editing of the mission xml in missionlist.lib we can change the spawn point - that's what I'm after now.

But it's important that we find the settings of the archetypes, they got to be somewhere!
## Post #192
- Username: del721rx
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Feb 04, 2017 6:33 am
- Post datetime: 2017-02-06T22:36:08+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Hi    I unpacked patch.fat, and there are many files, what to do with these files? Sorry, I'm a noob, just need Wrench model files

(Sorry for my bad english)
## Post #193
- Username: Lizzierawr
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 11, 2017 6:32 am
- Post datetime: 2017-02-10T22:35:44+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Is it possible to add clothes in the game to a store or directly to the wardrobe ? Missed out on some leaderboard rewards and would love to add them to the wardrobe in the game.
## Post #194
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2017-02-11T21:14:34+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Yes, it's possible to unlock the dlc outfits. You just have to edit the availability rules in the clothing xml in items.lib (set 0F43A933 54D14F92 and 4CAAD60F values to FFFFFFFFFFFFFFFF)

Is there any progress on the spider tank or the archetype settings?
## Post #195
- Username: machine4578
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 26, 2017 1:02 am
- Post datetime: 2017-02-13T07:52:45+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from CobraGamer
>
> Yes, it's possible to unlock the dlc outfits. You just have to edit the availability rules in the clothing xml in items.lib (set 0F43A933 54D14F92 and 4CAAD60F values to FFFFFFFFFFFFFFFF)

Is there any progress on the spider tank or the archetype settings?
thanks for the info, but in the Clothing_Bundles.Leaderboard.Leaderboard_Bundle.xml, those 3 rules you mentioned are already set to all F's. am i missing something else here?

these are the default values already in xml
<field hash="0F43A933" type="BinHex">FFFFFFFFFFFFFFFF</field>
<field hash="54D14F92" type="BinHex">FFFFFFFFFFFFFFFF</field>
<field hash="4CAAD60F" type="BinHex">FFFFFFFFFFFFFFFF</field>

thanks to all who made this possible to unpack the files! and further help unlocks these outfits is appreciated!

-edit-

nevermind, thanks to a friend i found the correct files and all 12 leaderboard unlocks work
## Post #196
- Username: Police
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Feb 14, 2017 4:26 am
- Post datetime: 2017-02-13T20:30:01+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Hello. I downloaded the file change that changes the private eye to police outfit and the main menu just freezes. Can someone help?

EDIT: By freeze, I mean the cinematic shows and everything, I just can't click on continue or any thing on the menu (i.e. the "continue" button).
## Post #197
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2017-02-14T22:10:58+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

A gamer asked me recently about how to edit the 'items.lib' (see prev page). So I wrote him a little instruction set. I post it here as well as I can imagine that it could be helpful to others.

------------------------------------------------------------------------
Watch Dogs 2 ~ modding

Prenotes: 
- preferably perform all actions in a (temporary) working folder
- ALWAYS make backups of the files you plan to overwrite !
- all actions are performed within a DOS box/window

* Un/pack fat/dat files: exe's found in this topic (pg 2 & 4)
-> find latest [filelist.txt] in this topic pg 7 ~ update 9)
* Un/pack lib files (and others): [ svn.gib.me/builds/disrupt/?C=M;O=D ]
-> Remove 'GraphicKit_parts.binaryobjectfile.xml' & 'Items.binaryobjectfile.xml' from the [..\bin\projects\Watch Dogs\binary objects\files] subfolder (see this topic pg 6) !


A. extracting/editing/repacking 'items.lib'

1. extract [Patch.fat] (located in your game folder) using [WD2Extract.exe]
	=> WD2Extract.exe "D:\Games\Watch Dogs 2\data_win64\patch.fat" Patch
	(creates a 'Patch' subfolder within your working folder)
	(this process can take some time 2-4 mins)

2. find [items.lib] in [.\Patch\generated\databases\generic]
-> copy this file in another working subfolder
	(find location of 'items.lib' in [filelist.txt] ~ see above)

3. extract [items.lib] using the Gibbed Tools for Watch Dogs
	=> .\WD2_Tools\Gibbed_Unpacker\bin\Gibbed.Disrupt.ConvertBinaryObject" items.lib
	(creates a 'items_converted' subfolder within your working folder)
	(creates a 'items_converted.xml' file within your working folder)
	(ps: you should get an error stating 'items' file definition missing ~ ignore: see above)

4. edit any XML file as you see fit: eg 'Clothing' category

5. repack [items.lib]:
	=>  .\WD2_Tools\Gibbed_Unpacker\bin\Gibbed.Disrupt.ConvertBinaryObject" items_converted.xml
	(creates a 'items_converted_converted.fcb' file within your working folder)
	=> ren items_converted_converted.fcb items.lib

6. copy [items.lib] to [.\Patch\generated\databases\generic]
	(see pt 2 ~ overwriting existing file)

7. Repack [Patch.fat]:
	=> WD2Pack.exe Patch Patch.fat
	(this creates 2 files: patch.fat & patch.dat)
	(embedded files are not recompressed, so resulting dat_file will have become much bigger in size)
	(this process can take some time 5-10 mins)

8. copy both [patch.*] files to your game folder
	(make a backup first !)
------------------------------------------------------------------------

That said:
I was not really aware about its contents; so I figured that perhaps I could 'unlock' the complete music set this way (not really cheating as these are "available" after all; one just need to have some luck to come across new songs).
Anways: if one checks [musiclibrary.lib], you'll find all the Music Player songs (and more) in there, categorized as follows:
RADIO_FINAL_DedSec_Pirate_Radio	=>	Elec
RADIO_FINAL_Rock_The_Bridge		=>	Punk
RADIO_FINAL_Rock_The_Bridge		=>	Rock
RADIO_FINAL_KCE_Centuries		=>	Clas
RADIO_FINAL_Bay_City_Pop		=>	Pop
RADIO_FINAL_Radio_Bay_Nation		=>	Rap
RADIO_FINAL_Las_Ondas_De_La_Ria	=>	World

I did a comparison between a 'start' save (when first activating the media player, you'll get some "free" songs out of the box), and further down in game progress. Compairing these xml files, give some differences. But no matter what I changed, I was not able to add any 'new' songs to the list...

Any suggestions/tips would be appreciated to get them activated automatically.

ps: it goes without saying; all credits to authors/contributors of aforementioned tools/posts.

*******************
-EDIT- some more info:
Common.fat => musicgenres.lib:
Punk Rock.xml =>   <field hash="1FE8D41C" type="BinHex">2787B63B02000080</field>  (which is the genre_ID you'll find back in the songs_xml file)
	* RADIO_FINAL_Rock_The_Bridge.Jawbreaker.xml =>   <field hash="4DB16FE4" type="BinHex">2787B63B02000080</field>

Common.fat => musicplaylists.lib  (contains full radio_list of songs, referring to their song_ID)
RADIO_STATIONS_FINAL.Las_Ondas_De_La_Ria.xml => <field hash="6F61FB50" type="BinHex">83C2C71F04000080</field>
	* RADIO_FINAL_Las_Ondas_De_La_Ria.10cc.xml => <field hash="1FE8D41C" type="BinHex">83C2C71F04000080</field>  (which is  their song_ID)

      * initial [musicplaylists.lib] list
      <field hash="6F61FB50" type="BinHex">14891AC103000080</field> RADIO_FINAL_Las_Ondas_De_La_Ria.Anthony B.xml>
      <field hash="6F61FB50" type="BinHex">16891AC103000080</field> RADIO_FINAL_Las_Ondas_De_La_Ria.Daniela Mercury.xml
      <field hash="6F61FB50" type="BinHex">13891AC103000080</field> RADIO_FINAL_Las_Ondas_De_La_Ria.Jungle Fire.xml
      <field hash="6F61FB50" type="BinHex">15891AC103000080</field> RADIO_FINAL_Las_Ondas_De_La_Ria.Tony Rebel.xml
      <field hash="6F61FB50" type="BinHex">83C2C71F04000080</field> RADIO_FINAL_Las_Ondas_De_La_Ria.10cc.xml

Example: inital playlist PunkRock:
* The Lookouts		RADIO_FINAL_Rock_The_Bridge.The_Lookouts.xml	  <field hash="1FE8D41C" type="BinHex">73D19D4207000080</field>
* Jawbreaker		RADIO_FINAL_Rock_The_Bridge.Jawbreaker.xml	  <field hash="1FE8D41C" type="BinHex">77D19D4207000080</field>
* NOFX			RADIO_FINAL_Rock_The_Bridge.NOFX.xml		  <field hash="1FE8D41C" type="BinHex">74D19D4207000080</field>
* Dead Kennedys		RADIO_FINAL_Rock_The_Bridge.Dead Kennedys.xml	  <field hash="1FE8D41C" type="BinHex">21891AC103000080</field>
However: not all songs are present in a particular playlist (eg: Jawbreaker)

btw: the initial list gives one 42 songs. Another thing I did not know: select/play a radiostation, and it will "activate" any new songs detected (ie one still needs to 'tab' - open SneakSong - to get them registered)

ps: created some batchfiles to generate appropriate info (see attached). Better check what they do before running them...

Q: #CobraGamer mentioned earlier on that one can use [unluac] to decompile lua scripts. Anyone knows of a Win_exe that can do the job as well? (unluac needs java; which is not - will not be - installed on my pc). Tried all the ones I could find, but these returned errors...

-UPDATE-:
Finished my research on the music part (got all of them now). Checkout [_MusicList_Cat_Sorted.txt] in the attached file for more info/detail.
ps: I did the test 'removing most ads & flashnews' for Bay Nation; had no probs with it. To make things more practical, I've added a [musiclibrary_converted_sorted.xml]...
[WD2_Mod Items_Music.rar](https://xentaxbackup.github.io/file/12478_WD2_Mod Items_Music.rar)
## Post #198
- Username: Police
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Feb 14, 2017 4:26 am
- Post datetime: 2017-02-15T02:54:35+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

The thing is, I suck at that and I will undoubtedly mess it up. Why can't someone just post the repacked patch.dat and .fat?
## Post #199
- Username: Police
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Feb 14, 2017 4:26 am
- Post datetime: 2017-02-15T02:56:21+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

And also, when I downloaded it, it was a patch.dat and a patch.fat which was bigger than the original.
## Post #200
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-02-18T13:33:44+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from Sir Kane
>
> http://sktest.aruarose.com/WD2Extract.7z

watch dogs 2 I can open the .xbg file
## Post #201
- Username: machine4578
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 26, 2017 1:02 am
- Post datetime: 2017-02-18T14:24:45+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

thanks alot for sharing Paul44!!
## Post #202
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-02-18T14:37:16+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Watch dogs how can i open .xbg file

 Please Please Please Please
## Post #203
- Username: DigitalZky
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Feb 18, 2017 9:26 am
- Post datetime: 2017-02-18T20:30:50+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from TSelman61X
>
> Watch dogs how can i open .xbg file

 Please Please Please Please

You can with a Blender plugin, check this thread [viewtopic.php?p=127569#p127569](http://forum.xentax.com/viewtopic.php?p=127569#p127569)
## Post #204
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-02-20T08:50:11+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

You can with a Blender plugin, check this thread [viewtopic.php?p=127569#p127569](http://forum.xentax.com/viewtopic.php?p=127569#p127569)[/quote]

Thx bro    
But there's no skeleton on it
## Post #205
- Username: DigitalZky
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Feb 18, 2017 9:26 am
- Post datetime: 2017-02-20T19:17:33+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Nope, just the model... but the skeleton should be in the files somewhere

Edit: So I had a problem with the extractor but I think it's all good now. Although I don't know if it's normal to get a million files with random numbers after extracting a .fat file. Can anyone tell me in which unextracted file the main characters models are located? I tried common.fat and there's no xbg/xbt files, just what I mentioned earlier.
## Post #206
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2017-02-21T11:38:08+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

@DigitalZky :-> find latest [filelist.txt] in this topic pg 7 ~ update 9). dump it in same subfolder of wd2extract.
## Post #207
- Username: DigitalZky
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Feb 18, 2017 9:26 am
- Post datetime: 2017-02-21T21:53:37+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from Paul44
>
> @DigitalZky :-> find latest [filelist.txt] in this topic pg 7 ~ update 9). dump it in same subfolder of wd2extract.

OMG, thank you so much! Such a small detail makes the whole difference haha

Question, though: Can the filelist be normally edited? There are some missing textures on some persons_of_interest folders, especially ultra res on pers03, pers07 and a few others. And even though I added the locations for xbt files they still weren't extracted :/
## Post #208
- Username: JimmyJ
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Dec 21, 2011 8:54 am
- Post datetime: 2017-02-22T11:25:41+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

can someone tell how to use WD2Extract??? I did all things with cmd but it still not work...

When I wrote:
WD2Extract "D:\Games\Watch Dogs 2\data_win64\patch.fat" "D:\Programs\WD2Extract\1"
results:
is no internal or external
command, operable program or batch file.

When I wrote:
"D:\Programs\WD2Extract\WD2Extract.exe" "D:\Games\Watch Dogs 2\data_win64\patch.fat" "D:\Programs\WD2Extract\1"
results:
C:\Users\Admin>
nothing in cmd, and no files in a folder:(

My system is Windows 10.
Help me please...
## Post #209
- Username: Xecutioner
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Oct 12, 2016 6:51 pm
- Post datetime: 2017-02-22T13:23:50+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Hi Can somebody tel me where i can find Billboards texture ? 

and how increase traffic cars ?
## Post #210
- Username: JimmyJ
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Dec 21, 2011 8:54 am
- Post datetime: 2017-02-22T17:23:42+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

I fix my problem.

Someone knows in which fat file placed pers5.xbg? In patch.fat?
## Post #211
- Username: Xecutioner
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Oct 12, 2016 6:51 pm
- Post datetime: 2017-02-23T16:28:57+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Please help us
## Post #212
- Username: DigitalZky
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Feb 18, 2017 9:26 am
- Post datetime: 2017-02-24T03:48:05+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

@Xecutioner @JimmyJ You can find both billboards textures and pers05.xbg on sanfrancisco.fat
## Post #213
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2017-02-24T11:55:09+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

As promised, find hereby my tool to collect filenames (as found/residing within particular filetypes). This (batch)tool makes use of 'Swiss File Knife', which is not included in the attachment. (you'll need to download the latest vs, and edit the batchfile accordingly)

Since filesize_limit is ridiculously low for this forum, one can download it here: (feel free to upload it to other filehost services)
- scan tool: [ [https://www.4shared.com/archive/0aPfpgw ... n_v28.html](https://www.4shared.com/archive/0aPfpgwLba/WD2_Scan_v28.html) ] ~ 1.5 MB
- updated filelist: [ [https://www.4shared.com/archive/R8PLycU ... elist.html](https://www.4shared.com/archive/R8PLycUNba/WD2_filelist.html) ] ~ 1.6 MB

Some remarks:
1. this tool is based on my experience with MGS5 (and has been posted as such on nexus). a few references can be found in it, but functionality remains the same.
2. the readme includes instructions on how to use it but - as said - it primarily explains how to use it for a mgs5 environment.
that said: you only need to concentrate on [Preparation: step 1. ] (since I've done most preparation work already)
also, the current scans should get you going as well...
3. the scans - i've done - are primarily performed on the '0x*' files; as I noticed that quite a few of them contained filename references. but the tool can scan any file (data, exe, memdump, etc)...
4. embedded files which are (have been) compiled, compressed, encrypted, etc will hardly return any results. if you know how to "undo" such action, obviously do so first...
5. I had no plans to actually scan this game; but thought it would be nice to make someone aware of it (based on some earlier posts). Iow I leave it for others to perform any 'full' scans. But you can always pm me if you need info/assistance.
## Post #214
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2017-02-24T14:52:51+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

After some research, I found out that the 3rd intro 'movie' is actually a flash file: [patch\ui\fire\bin\wd2bootsequence.feu]. At least, you'll find references to 'epilepsy' in there (but it probably grabs its full text from the appropriate language file).

@Ekey (or anyone with active flash dev experience): could you look into this, and shorten the delay to 1-2 secs ?
thx in advance,

UPDATE: I was able to pull the script info from that flash file (see attached). anyone with active Flash action script?
p

ps: to convert the file, check #Ekey's post on pg 7
[WD2_wd2bootsequence.rar](https://xentaxbackup.github.io/file/12548_WD2_wd2bootsequence.rar)
## Post #215
- Username: Xecutioner
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Oct 12, 2016 6:51 pm
- Post datetime: 2017-02-24T15:13:41+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from DigitalZky
>
> @Xecutioner @JimmyJ You can find both billboards textures and pers05.xbg on sanfrancisco.fat

Hi thanks for your response but i look all folder and i can't find any billboards,  this is no like watch dogs 1 where billboards was located in "signs" folder
## Post #216
- Username: DigitalZky
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Feb 18, 2017 9:26 am
- Post datetime: 2017-02-25T23:28:20+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from Xecutioner
>
> DigitalZky wrote:@Xecutioner @JimmyJ You can find both billboards textures and pers05.xbg on sanfrancisco.fat

Hi thanks for your response but i look all folder and i can't find any billboards,  this is no like watch dogs 1 where billboards was located in "signs" folder

Hmm, I've seen some files named billboard in that folder, but I'd recommend just searching for 'billboard' in the graphics folder and you'll get all the matching results
## Post #217
- Username: Xecutioner
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Oct 12, 2016 6:51 pm
- Post datetime: 2017-02-26T19:12:20+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from DigitalZky
>
> Xecutioner wrote:DigitalZky wrote:@Xecutioner @JimmyJ You can find both billboards textures and pers05.xbg on sanfrancisco.fat

Hi thanks for your response but i look all folder and i can't find any billboards,  this is no like watch dogs 1 where billboards was located in "signs" folder

Hmm, I've seen some files named billboard in that folder, but I'd recommend just searching for 'billboard' in the graphics folder and you'll get all the matching results

Hi Thanks you! i finally found all things i wanted to find
## Post #218
- Username: PatrickJr
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Feb 28, 2017 11:11 am
- Post datetime: 2017-02-28T03:28:26+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Man, the talent here. Amazing.
I can't wait to see more cool stuff!

Edit: How would I add clothing for Marcus, for shits and giggles I'd love to have the police uniform, how would I go about doing this?
## Post #219
- Username: Xecutioner
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Oct 12, 2016 6:51 pm
- Post datetime: 2017-02-28T11:43:05+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Please after 1 week i still dnt understand how to use WD2Pack.exe, nothing happens when i dragg the file into it and when i try to pack with "Gibbed.Disrupt.Pack" after i launch the game in the menu the game won't starte!

My game located in my "D" drive and all modification i do is on my deskpot.
## Post #220
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2017-02-28T15:45:05+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

@Xecutioner: you can NOT pack/unpack from the windows desktop (at least, I did not try it). You'll need to open a 'windows command prompt' (google!), and type the commands there.  (see instruction steps here: [ [viewtopic.php?p=127631#p127631](http://forum.xentax.com/viewtopic.php?p=127631#p127631) ]).

ps: glad you found 'everything'. care to updates us on what you've found where? (not for myself, but i'm sure others will appreciate your feedback)

-EDIT- 3x
This is "basic" stuff, but anyways: [ [https://www.howtogeek.com/235101/10-way ... indows-10/](https://www.howtogeek.com/235101/10-ways-to-open-the-command-prompt-in-windows-10/) ] (most of this applies to Win 7 as well, which I'm using). I always use the [Shift + Right click] trick from within Windows explorer. And yes: you must (should?) un/pack within a temporary/working folder (and no: it is not a good idea to do that within your game folder ~ create one somewhere else, and when finished copy/paste modded files back to your game folder ~ and don't forget to backup...).
The 'commands' are "highlighted" by '=>' (ie pack/unpack & use Win explorer to do the necessary copy/pasting)

- as far as the textures is concerned: can't help there. check some billboards, see what is written on it, and try to search for that in the filelist (I remember finding a billboard in WD1 as it referred to a motel)
UPDATE: you should find all 'signs' under [graphics\_geometries\building_dressing\signs]. eg I saw a 'Brewed Delight' sign in a shopping mall; searched for 'brewed' and bingo... I expected xbt_file, and got one (if you do not know how to convert xbt to dds and back, read this topic)
- traffic density: I recall somebody else already asking for it (or you bumping the question). no idea: just keep googling, and it might pop up one day 
UPDATE: check out "Variety Pack" for WD1 on Nexus. It contains - among others - a traffic density mod. The file you're looking for is [generated\databases\generic\trafficpatternselector.lib]. You can obviously NOT use this one. You'll need to figure out the difference between the original one (also comes with the pack) and the modded one (see attached). Once you know what needs to be edited, try that on the WD2 vs...
+attached: I made a xdelta comparaison between the original vs modded: you only need to change 4 xml files apparently. You will find the traffic_file in [common.dat] !
(I also added a comparaison of the 'highdensity' xml files - do the same for the other 3 xml files)
[WD2_TrafficDensity.rar](https://xentaxbackup.github.io/file/12543_WD2_TrafficDensity.rar)
## Post #221
- Username: Xecutioner
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Oct 12, 2016 6:51 pm
- Post datetime: 2017-02-28T16:35:59+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from Paul44
>
> @Xecutioner: you can NOT pack/unpack from the windows desktop (at least, I did not try it). You'll need to open a 'windows command prompt' (google!), and type the commands there.  (see instruction steps here: [ viewtopic.php?p=127631#p127631 ]).

ps: glad you found 'everything'. care to updates us on what you've found where? (not for myself, but i'm sure others will appreciate your feedback)

Hi thanks to reply me but what du you say about "type the commands" ? can you give me a exemple ? (im big nooby)  
(BTW, usually, i extract all files in my desktop and its working fin. Its just to repack is not clear for me)

So i need to make a folder into my game installation, and working in this folder ? unpack/repack ?

And about what i found, i found many textures in the _geometries, "building_dressing" folder located into graphics folder. but its no exactly the textures i wanted to find, because me i'm looking billboards accross the city, freeway etc and some shop signs but nothing at all   

P.S What about increase cars density ?
## Post #222
- Username: zlksmlnu
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Aug 10, 2016 6:27 am
- Post datetime: 2017-03-01T19:23:58+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Hello guys! Does anybody know where the radio songs is stored? I've found an album arts only. I want to add my own songs.

```
Common.fat\ui\fire\sources\textures\ingame\apps\mediaplayer\albumart
```

Thanks in advance and good luck with modding mates!
## Post #223
- Username: zlksmlnu
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Aug 10, 2016 6:27 am
- Post datetime: 2017-03-01T21:22:48+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Hello
Can somebody suggest how to extract gif(or videos) used as mission background in mission manager (like [https://hydra-media.cursecdn.com/watchd ... e_Game.jpg](https://hydra-media.cursecdn.com/watchdogs.gamepedia.com/f/f3/The_Name_Game.jpg) but animated) ? Or maybe usual filetype for such data.
## Post #224
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-03-01T23:28:26+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

they are in video.fat/dat.  They are in Bink video format. [http://www.radgametools.com/bnkmain.htm](http://www.radgametools.com/bnkmain.htm)
You can play them with the free bink player, but as far as converting to a GIF, I've never seen that anyone has made a Bink to [different format] converter. (hopefully someone will prove me wrong)
## Post #225
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2017-03-02T08:29:45+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

The Radvideo tools come with a 'convert a file' option which allows you to convert the bink (vs 1 & 2) file to several formats (among others gif). In a worst scenario, one can convert it to avi; and proceed from there...
## Post #226
- Username: hjadr
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 02, 2017 7:08 pm
- Post datetime: 2017-03-02T12:58:05+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

So there are quite a lot of ubi employe items. I tried editing in the items.lib only partial succes (unfortunately). But maybe there is a easier way to "become employe" may be true the WD2_GamerProfile.xml. Do any of you have a brilliant idea?
## Post #227
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2017-03-05T10:30:40+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

I've spent some time this week, trying to figure out the 'Density' mod by #TXGT 'Variety Pack for Watch_Dogs' (on nexus). Anyone actually tried this out with WD1?

I could figure out where the numbers coming from (binhex to float, and back). But after some experimenting, I was not able to obtain a substantial difference (more parked cars or pedestrians ~ based on said mod).
If someone can make sense out of that; I got 2 questions: a) how DO the numbers work ? b) what's with the "01~05" and "10~50" ?

-UPDATE-
I got some feedback from #TXGT (see below). In fact, this makes sense...
In a nutshell: all xml settings are behaving in the same way, and are allocated to "specific" areas on the map (either blocks or perhaps even per (part of) street). Iow: if you want the same density everywhere, just edit ALL xml settings to the same 'density' you'd prefer.

Bottomline: I've entered/changed to 'VeryHighDensity' in all respective xml files; for Pedestrians/ParkedCars and Trafficpattern respectively. (still not impressed with the pedestrian density though - there might also be max threshold settings)

Attached: update xls sheet + batchifle convert Binhex~Float + modded lib_files.
(this runs fine on my pc, but could be a performance hit with low(er) GPUs)

ps: also expect more traffic jams/accidents...  

------------------------------------------
Feedback from #TXGT (for WD1 Mod):
"In my understanding the lower the value the more cars will be on the roads. So that means it's a time values. They mean how often the new cars will be spawning. But I don't know if it's a seconds or milliseconds or the game engine converts those values somehow.

Another thing I know for sure is that the settings from those xmls (LowDensity, HighDensity etc.) are placed across the city. For example LowDensity is always on one road near the Theater and HighDensity is always on Highways."
[WD2_Density.7z](https://xentaxbackup.github.io/file/12564_WD2_Density.7z)
## Post #228
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2017-03-05T13:28:37+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

New version that supports listing all file names contained within an archive and extracting specific files.

Name list has also been updated with some new names.

[http://sktest.aruarose.com/WD2FatTools_v003.7z](http://sktest.aruarose.com/WD2FatTools_v003.7z)
## Post #229
- Username: Lizzierawr
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 11, 2017 6:32 am
- Post datetime: 2017-03-06T06:44:16+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Is there a way to unlock all clothes from the start of the game ?
## Post #230
- Username: Xecutioner
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Oct 12, 2016 6:51 pm
- Post datetime: 2017-03-07T14:00:53+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from Paul44
>
> I've spent some time this week, trying to figure out the 'Density' mod by #TXGT 'Variety Pack for Watch_Dogs' (on nexus). Anyone actually tried this out with WD1?

I could figure out where the numbers coming from (binhex to float, and back). But after some experimenting, I was not able to obtain a substantial difference (more parked cars or pedestrians ~ based on said mod).
If someone can make sense out of that; I got 2 questions: a) how DO the numbers work ? b) what's with the "01~05" and "10~50" ?

-UPDATE-
I got some feedback from #TXGT (see below). In fact, this makes sense...
In a nutshell: all xml settings are behaving in the same way, and are allocated to "specific" areas on the map (either blocks or perhaps even per (part of) street). Iow: if you want the same density everywhere, just edit ALL xml settings to the same 'density' you'd prefer.

Bottomline: I've entered/changed to 'VeryHighDensity' in all respective xml files; for Pedestrians/ParkedCars and Trafficpattern respectively. (still not impressed with the pedestrian density though - there might also be max threshold settings)

Attached: update xls sheet + batchifle convert Binhex~Float + modded lib_files.
(this runs fine on my pc, but could be a performance hit with low(er) GPUs)

ps: also expect more traffic jams/accidents...  

------------------------------------------
Feedback from #TXGT (for WD1 Mod):
"In my understanding the lower the value the more cars will be on the roads. So that means it's a time values. They mean how often the new cars will be spawning. But I don't know if it's a seconds or milliseconds or the game engine converts those values somehow.

Another thing I know for sure is that the settings from those xmls (LowDensity, HighDensity etc.) are placed across the city. For example LowDensity is always on one road near the Theater and HighDensity is always on Highways."

Hi thanks for this! but can you make a .fat version of this ? i dnt know how repack file in WD2
## Post #231
- Username: Paul44
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Sep 18, 2014 1:06 am
- Post datetime: 2017-03-07T18:17:18+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

^No. Read my previous post in full: [ [https://forum.xentax.com/viewtopic.php?p=128116#p128116](https://forum.xentax.com/viewtopic.php?p=128116#p128116) ]; all you need to know is referenced there...
## Post #232
- Username: Xecutioner
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Oct 12, 2016 6:51 pm
- Post datetime: 2017-03-07T21:43:06+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from Paul44
>
> ^No. Read my previous post in full: [ https://forum.xentax.com/viewtopic.php?p=128116#p128116 ]; all you need to know is referenced there...

Thanks you for your help bro
## Post #233
- Username: Xecutioner
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Oct 12, 2016 6:51 pm
- Post datetime: 2017-03-11T22:01:17+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

This game need real darker night and reshade and sweetfx can't do this. I really hope somebody work on it in the future like WD 1 graphic mod
## Post #234
- Username: MediaWindowsIntel
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri May 11, 2012 8:41 pm
- Post datetime: 2017-03-19T10:25:13+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Original en Français. Bonjour je voudrais savoir comment modifié l'armenents et leurs nombres de munitition maximum dans Watch Dogs 2! Quel fichiers doivent toucher pour les armes et les eei?

> translated by Google. Hello I would like to know how modified the armenents and their maximum munitition numbers in Watch Dogs 2! Which files should touch for weapons and eei?
## Post #235
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2017-04-01T16:33:31+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Nothing new here, I have been experimenting with clothing customization...

Has anyone found a way to modify clothing without making its item disappear in the shop?
## Post #236
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2017-04-08T19:18:29+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

I wrote a small tutorial on how to add new clothing items to the shop. I won't explain how to use the WD2 tools to extract the game's files as there already are tutorials on this thread.

Useful online converters:
- [Hex to Decimal](http://www.rapidtables.com/convert/number/hex-to-decimal.htm)

Files necessary to edit:
- items.lib - for creating the new item itself. The file includes a link to the modelpart in graphickit_parts.lib
- itemsshopproperties.lib - for defining shop category and price, including link to item file in items.lib
- shopcomponentsettings.lib - for defining availability of the new item in a specific shop and making it show up
- graphickit_models.lib - contains the specific parts of a model. I recommend deleting every part except for his head and body (read below for further information on how to do this)

Finding specific clothing parts:
- if you open "W2CH_MOD_nar.ava.avatar.xml" (which is the file of Marcus) or any other file you want, you see the specific parts of his outfit, such as jacket, hat, pants, shoes and glasses. Each part begins with field "E93DDFF8", where "D935FAD9" is the link to the specific outfit part in graphickit_parts.lib. Copy this field's value and search for it in all files of the graphickit_parts folder (I recommend using Sublime Text Editor).

1) items.lib
	1. copy an existing clothes file (e.g. Clothing_VendingMachines.DedSec.Torso.BomberSweater01_BlueShiny.xml, which would be Marcus' blue bomber jacket) and rename it.
	2. change the ID of the file in field "389F6DA7" to a new, unique one (important: ID'S only contain letters from A to F).
	3. the fields "389F6DA7", "54D14F92" and "4CAAD60F" define the requirement to make the item appear in the shop. These fields must be set to "FFFFFFFFFFFFFFFF".
	4. the part below "73642E5E" contains the link to the graphickit_part file. The value of the field "D935FAD9" is the ID of the modelpart file in graphickit_parts.lib.

2) itemshopproperties.lib
	1. copy an existing file from this folder and rename it. Once again, change the new file's ID to a new, unique one.
	2. field "73280CDE" is the link to the new item file in items.lib you created, so change this value to the unique ID you created earlier.
	3. field "92AF09E1" defines the shop category you want your new item to appear in. Look at other files in this folder that are in the category you want and copy their value.
	4. field "33E4CFD7" defines the price of the new item. Use the hex to decimal converter I linked in the first part of this tutorial.

3) shopcomponentsettings.lib
	1. edit the file you want your new item to appear in (e.g. ShopComponentSettings.VendingMachines.Hackerspace.xml if you want your item to appear in the vending machine in the hackerspace)

If you read this tutorial carefully, everything should work as it should. If not, please write your problem or do some research on your own, as I didn't completely figure this out yet.
## Post #237
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2017-04-11T11:11:57+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Come on, Paul44 and griffin02, we're one step further on the archetypes, have a look at this:
[https://www.dropbox.com/s/dyvjpv3c02px0 ... D.xml?dl=0](https://www.dropbox.com/s/dyvjpv3c02px0vh/%7B06ed9791-7382-440d-92ae-a400c44fefc0%7D.xml?dl=0)

It's an archetype file! I think it's a leftover of a car that wasn't going to be converted to WD2 and the devs forgot to delete it. I found it in the unpacked san_francisco.fat archive.
There are more archetype files in there, mostly furnitures and other things.

How the fuck do these archetypes work? Where do we start?
## Post #238
- Username: Xecutioner
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Oct 12, 2016 6:51 pm
- Post datetime: 2017-04-11T16:44:39+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

I really hope WD2 Modding don't die ! Please !
## Post #239
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2017-04-13T22:29:57+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from griffin02
>
> Here's the list, it's a double vector, so vector element contains the name and hash, however some of the names are mangled and I didn't bother to fix them but it's still pretty straight forward
Excuse the formatting(And I didn't see a spoiler tag to hide this)

This is like chinese to me. Could you (or someone else) explain how to get the archetype's name out of {5ec60cec-c076-4fcd-86d7-a853faf5851f}?
## Post #240
- Username: Xecutioner
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Oct 12, 2016 6:51 pm
- Post datetime: 2017-04-15T15:22:31+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Please i need help to convert dds to xbt properly because in the game i get blanked texture wtf ?

i fixed it!
## Post #241
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2017-04-16T10:11:04+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from Xecutioner
>
> Please i need help to convert dds to xbt properly because in the game i get blanked texture wtf ?

i fixed it!
[There](http://forum.xentax.com/viewtopic.php?p=126615#p126615) you go.
## Post #242
- Username: Xecutioner
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Oct 12, 2016 6:51 pm
- Post datetime: 2017-04-16T16:32:31+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from CobraGamer
>
> Xecutioner wrote:Please i need help to convert dds to xbt properly because in the game i get blanked texture wtf ?

i fixed it!
There you go.

Yep thanks but is strange,

My first texture working perfectly but others i try to make, i got blanked texture, and off course i do the same thing i do firstly 
[There](http://forum.xentax.com/viewtopic.php?p=126615#p126615) you go.[/quote]

Very strange
## Post #243
- Username: Xecutioner
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Oct 12, 2016 6:51 pm
- Post datetime: 2017-04-16T22:21:49+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Ok I noticed all major signs around the city are .hkx files so is impossible to edit them

so bad
## Post #244
- Username: Lizzierawr
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 11, 2017 6:32 am
- Post datetime: 2017-04-18T23:17:28+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Does the PC version of the game have textures for the CtOS and Bitflip outfits (PS4 Exclusive so far) ?
## Post #245
- Username: griffin02
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jan 24, 2017 9:28 am
- Post datetime: 2017-04-19T01:49:10+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from CobraGamer
>
> griffin02 wrote:Here's the list, it's a double vector, so vector element contains the name and hash, however some of the names are mangled and I didn't bother to fix them but it's still pretty straight forward
Excuse the formatting(And I didn't see a spoiler tag to hide this)

This is like chinese to me. Could you (or someone else) explain how to get the archetype's name out of {5ec60cec-c076-4fcd-86d7-a853faf5851f}?

Saw your visitor thread on UC... I haven't released my work yet, kinda got side-tracked... 
That being said I never actually figured out how to they calculated the archtypes.

If you dump the game files you'll find a file "generated\databases\generic\vehiclespawninfo.lib".. If you open it in a hex editor, it has the vehicle names and their archtypes.. I just made a program to read the file and pull the data in a certain format.

ex
## Post #246
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2017-04-19T10:21:30+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Thanks for the answer! I thought there was a connection between the archetype IDs and the name (if you extract the vehiclespawninfo.lib and open a vehicle's file, you get the ID as well as the archetype's name).
## Post #247
- Username: maury121
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Sep 05, 2016 9:06 pm
- Post datetime: 2017-04-25T13:58:39+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Hi guys, i want to extract some bik videos, textures and models from the dlc2 folder, is there an updated file list for that folder?
## Post #248
- Username: Xecutioner
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Oct 12, 2016 6:51 pm
- Post datetime: 2017-04-25T22:14:00+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Update: Finally i found all i need to found! 

But i have a problem, i dnt know how Ubisoft make this game but is no like Watch dogs 1.

I edited this billboards "billboard_plainstock_01_c_high"  "billboard_plainstock_01_c_med"  and i converted with HxD editor etc. Good! 

But Now in game i still get vanilla plainstock billboard with strange blurring effect, no mine i edited

Why ? i'm confused with modding of this game !!
## Post #249
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2017-04-26T15:47:37+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

okay,the latest dlc included 3 special outfits,which comes with 3 new emotions respectively.eg:police outfit can stop people,paramedic can wake ppl up .etc

so i wonder could i use those new emotions even though i don't own the dlc
i checked the items.lib,those 3 new emotion files are exsiting even i don't have the dlc.
i added the item value of the 3 new emotions from items.lib into the Emotes.PlayerEmotes.xml at iteminventorylists.lib,but it doesn't do anything,the emo list remain the same. 
i replaced the exsiting emo to the new emo at the list,still nothing has changed.

for your information if you interested in the new emo.
## Post #250
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2017-05-01T08:24:28+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Txt files can be reached with this?
## Post #251
- Username: BrownRecluse
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 05, 2017 12:41 am
- Post datetime: 2017-05-04T17:20:36+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from CobraGamer
>
> Here is how to change the body of the character:
Open the file for Marcus in graphickit_models.lib (something with avatar). The D935FAD9 field is the file ID of the graphickit_parts.lib files. Copy the value and search for that in the graphickit_parts XMLs. The result's file name shows what part it is (head, arms, torso, ...). Now open the coop character file in graphickit_models.lib with which you want to replace Marcus' body with, search the values again and copy the head and body and replace the original ones with them.
Et voila, now you only have to repack it and have some fun.

Btw you can also delete the entries of the earbuds, glasses and backpack in the models files if you want to.

I tried this and nothing changed in my game. I replaced Marcus' head with Wrench's unmasked head(W2CH_PAR_pois_mul.pers01-thewrenchHeadnomask.xml  ID: C3A7C99302000080) on lines 32 and 415 in W2CH_MOD_nar.ava.avatar.xml. After editing the xml I converted it to fcb using
the Gibbed tools and renamed it to .lib and copied it into the extracted patch and then repacked the patch using WD2Pack and copied both patch files into my game directory. Did I do anything wrong? Did I edit the wrong xml file?
## Post #252
- Username: crossedfayt
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 15, 2017 12:16 am
- Post datetime: 2017-05-17T21:11:45+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from BrownRecluse
>
> CobraGamer wrote:Here is how to change the body of the character:
Open the file for Marcus in graphickit_models.lib (something with avatar). The D935FAD9 field is the file ID of the graphickit_parts.lib files. Copy the value and search for that in the graphickit_parts XMLs. The result's file name shows what part it is (head, arms, torso, ...). Now open the coop character file in graphickit_models.lib with which you want to replace Marcus' body with, search the values again and copy the head and body and replace the original ones with them.
Et voila, now you only have to repack it and have some fun.

Btw you can also delete the entries of the earbuds, glasses and backpack in the models files if you want to.

I tried this and nothing changed in my game. I replaced Marcus' head with Wrench's unmasked head(W2CH_PAR_pois_mul.pers01-thewrenchHeadnomask.xml  ID: C3A7C99302000080) on lines 32 and 415 in W2CH_MOD_nar.ava.avatar.xml. After editing the xml I converted it to fcb using
the Gibbed tools and renamed it to .lib and copied it into the extracted patch and then repacked the patch using WD2Pack and copied both patch files into my game directory. Did I do anything wrong? Did I edit the wrong xml file?
Have you had any luck making it work? I tried but failed. Also I cannot install that Aiden mod. It loads up fine till main menu. I can move my mouse and the video is working in the background but I am unable to do anything.
## Post #253
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2017-05-28T07:31:39+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

That's because the patch files of the mod are from a older game version.
## Post #254
- Username: paulscottttt
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Jan 25, 2016 8:34 am
- Post datetime: 2017-05-28T08:30:06+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

how do you remove the backpack and sunglasses?
## Post #255
- Username: defult06
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon May 29, 2017 12:58 pm
- Post datetime: 2017-05-29T05:16:20+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Is there any tutorial video available to this? really ı want to open language file but ı still dont understand that stuff. I unpack path file and a lot of files have been created(like 0xBAFB0E1AED0F0B3E-0xBAFBD08BD77E6A7A) I don't know what ı need to do now ? Please ı want to video.
## Post #256
- Username: guest12345
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Dec 18, 2016 1:25 am
- Post datetime: 2017-05-30T20:14:24+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

has anybody been able to figure out how to model swap marcus with the multiplayer character models yet
## Post #257
- Username: MrWasdennnoch
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue May 30, 2017 11:44 pm
- Post datetime: 2017-06-04T14:22:34+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Since it looks like the tool to automatically parse the hex dump and create class definitions for the lib files hasn't been released yet (if it even exists) I decided to try my luck. So far I can generate definitions for a single file, merging multiple files to create a full definition for a library shouldn't be hard to implement as well. The only thing I'm stuck on right now is how to detect duplicate patterns and merge them into one single object Nevermind, it's actually pretty straight-forward. For example, the ShopComponentSettings roughly look like this:

Removed example because irrelevent now

And the gibbed tools automatically detect if that repeats. Now I have to find a way to detect that as well Done.


I also manually created definitions for the libraries I found interesting or worked with so far, namely BoudarySettingsDB, Helicopter, ItemCategory, ItemInventoryLists, Items, ItemShopProperties, ShopComponentSettings, TextureDB, UIColorPaletteSetting, UIMenuPageDB (hell that was annoying), VehicleSpawnInfo, Weapon and WeatherPreset. I attached them below (the whole gibbed project folder since it also for some reason directly reads some WD files so I fixed the paths for WD2).


 projects.zip
(17.26 KiB) Downloaded 134 times



Someone already made a Car On Demand mod in December, was that ever released? I haven't seen that yet. I also added the helicopter to COD (as someone else already did as well) and will also add the 2 other heli types and maybe some other interesting new stuff. There have been questions about where the vehicle archetype info is stored, I think it's in the entitylibrary_rt.fcb (including camera references) but unfortunately there is no tool to decompile that one yet (Gibbed tools fail). I also found something that could be a list of default unlocked items (iteminventorylists.lib, Player.StartupKit.xml) but I'm not sure about that.


EDIT: So the program is pretty much done now and it can generate definitions for all libraries; there is a little problem though: Most of them don't automatically work. In many libraries a value in a file has a different value type than it should have which lets Gibbed tools crash so I have to manually adjust individual types to fix the crashes. That'll be a fun time. I'm half-tempted to make another program for that.

EDIT2: Does anyone know where the vehicle pain job textures get referenced in the libraries? The TextureDB contains the shop icons but not the actual vehicle textures and I couldn't find anything with Notepad++ file search over all libs.
## Post #258
- Username: mostafa0017
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jun 12, 2017 3:33 am
- Post datetime: 2017-06-11T19:41:06+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Hey does anyone know where can I find the xml file responsible for sound files located in san_francisco_sound\soundbinary they are numbered like this "246233514" but each number is supposed to be paired with a real name in a file somewhere but I can't find that file I am trying to change all of the music files including thier names and possibly there thumbnails too in game media player but recognizing music by their length have been very tedious so can anyone direct me to this file If it exists ?
## Post #259
- Username: MrWasdennnoch
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue May 30, 2017 11:44 pm
- Post datetime: 2017-06-12T20:08:27+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from mostafa0017
>
> Hey does anyone know where can I find the xml file responsible for sound files located in san_francisco_sound\soundbinary they are numbered like this "246233514" but each number is supposed to be paired with a real name in a file somewhere but I can't find that file I am trying to change all of the music files including thier names and possibly there thumbnails too in game media player but recognizing music by their length have been very tedious so can anyone direct me to this file If it exists ?
Seems like the musiclibrary.lib has the things you are looking for, it contains items with the path to the soundbinary, album art, genre, radio station and song name/artist/album.
## Post #260
- Username: mostafa0017
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jun 12, 2017 3:33 am
- Post datetime: 2017-06-13T16:04:32+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from MrWasdennnoch
>
> mostafa0017 wrote:Hey does anyone know where can I find the xml file responsible for sound files located in san_francisco_sound\soundbinary they are numbered like this "246233514" but each number is supposed to be paired with a real name in a file somewhere but I can't find that file I am trying to change all of the music files including thier names and possibly there thumbnails too in game media player but recognizing music by their length have been very tedious so can anyone direct me to this file If it exists ?
Seems like the musiclibrary.lib has the things you are looking for, it contains items with the path to the soundbinary, album art, genre, radio station and song name/artist/album.

Hey man sorry to bug you again but do you know how to get any of the values located in these xml files to be the same as (refer to) the corresponding .wem file ??
for example the file RADIO_FINAL_Bay_City_Pop.Major_Lazer.xml located in musiclibrary.lib it's corresponding .wem files are 133118895.wem and 325889386.wem one for 1 channel-124 kb/s and the other is 2 channels-230 kb/s but I can't get the relation between any of the values located in that xml file to the 2 .wem files i.e. how can I convert the values in the xml file to be more like the wem names or am I looking in the wrong place here ?? the xml contains hashes which could be translated nicely here [https://gist.githubusercontent.com/anon ... 2_dump.txt](https://gist.githubusercontent.com/anonymous/58205a5fc0ee2f52ac169a31e5e3cb35/raw/6f841e99d1553e34887c0238cea69b8b2b7ab07a/wd2_crc32_dump.txt) and BinHexs which is supposed to refer to the wem files but I can't for the life of me figure out who do they refer, sorry I am a big noob in this area  
in this post [viewtopic.php?f=10&t=15567&p=126135&hil ... ex#p126135](http://forum.xentax.com/viewtopic.php?f=10&t=15567&p=126135&hilit=BinHex#p126135) the binhexs are converted using ConvertBinaryObject but I can't understand what to do to get them converted into readable letters instead of the BinHexs

after further reading here [http://farcrymods.freeforums.net/thread ... ollTo=3050](http://farcrymods.freeforums.net/thread/431/trying-documentation-where-start-modding?page=1&scrollTo=3050) I understood that I need to specify an object definition in this line "Gibbed.Disrupt.ConvertBinaryObject.exe -b=".ark.fcb" <inputfilename>.FCB <inputfilename>.XML" but I don't know which definition to use ?
## Post #261
- Username: MrWasdennnoch
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue May 30, 2017 11:44 pm
- Post datetime: 2017-06-14T13:34:09+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from mostafa0017
>
> Hey man sorry to bug you again but do you know how to get any of the values located in these xml files to be the same as (refer to) the corresponding .wem file ??
for example the file RADIO_FINAL_Bay_City_Pop.Major_Lazer.xml located in musiclibrary.lib it's corresponding .wem files are 133118895.wem and 325889386.wem one for 1 channel-124 kb/s and the other is 2 channels-230 kb/s but I can't get the relation between any of the values located in that xml file to the 2 .wem files i.e. how can I convert the values in the xml file to be more like the wem names or am I looking in the wrong place here ?? the xml contains hashes which could be translated nicely here https://gist.githubusercontent.com/anon ... 2_dump.txt and BinHexs which is supposed to refer to the wem files but I can't for the life of me figure out who do they refer, sorry I am a big noob in this area  
in this post viewtopic.php?f=10&t=15567&p=126135&hil ... ex#p126135 the binhexs are converted using ConvertBinaryObject but I can't understand what to do to get them converted into readable letters instead of the BinHexs

after further reading here http://farcrymods.freeforums.net/thread ... ollTo=3050 I understood that I need to specify an object definition in this line "Gibbed.Disrupt.ConvertBinaryObject.exe -b=".ark.fcb" <inputfilename>.FCB <inputfilename>.XML" but I don't know which definition to use ?
You have to add the file definitions in the projects/Watch Dogs/binary objects/ folder, you don't have to do anything in the command line. I just created them for you 


 MusicLibraryDefinition.zip
(1.4 KiB) Downloaded 47 times


You can now easily see which sound files the item links to (although I haven't found any channel difference entries that you mentioned).
The BinHex fields are all basically IDs that mostly point to other libraries, for example the album art field links to an item in the TextureDB.lib (I attached definitions for that in my previous post). If you find an entry still in BinHex: If the hex is rather long it's a string and you can convert it online (for example with [http://www.rapidtables.com/convert/numb ... -ascii.htm](http://www.rapidtables.com/convert/number/hex-to-ascii.htm)). If the values are only 00 and 01 it's a Boolean. You can also see many types in the field name; if it's "bLegacy" it's a boolean, "fAccelleration" is a Float, "colorSomething" and "vec3something" are Vector3. If you have a look at the definitions you can easily see how they work.
## Post #262
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2017-06-14T13:35:08+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from MrWasdennnoch
>
> Since it looks like the tool to automatically parse the hex dump and create class definitions for the lib files hasn't been released yet (if it even exists) I decided to try my luck. So far I can generate definitions for a single file, merging multiple files to create a full definition for a library shouldn't be hard to implement as well. The only thing I'm stuck on right now is how to detect duplicate patterns and merge them into one single object Nevermind, it's actually pretty straight-forward. For example, the ShopComponentSettings roughly look like this:

Removed example because irrelevent now

And the gibbed tools automatically detect if that repeats. Now I have to find a way to detect that as well Done.


I also manually created definitions for the libraries I found interesting or worked with so far, namely BoudarySettingsDB, Helicopter, ItemCategory, ItemInventoryLists, Items, ItemShopProperties, ShopComponentSettings, TextureDB, UIColorPaletteSetting, UIMenuPageDB (hell that was annoying), VehicleSpawnInfo, Weapon and WeatherPreset. I attached them below (the whole gibbed project folder since it also for some reason directly reads some WD files so I fixed the paths for WD2).
projects.zip

Someone already made a Car On Demand mod in December, was that ever released? I haven't seen that yet. I also added the helicopter to COD (as someone else already did as well) and will also add the 2 other heli types and maybe some other interesting new stuff. There have been questions about where the vehicle archetype info is stored, I think it's in the entitylibrary_rt.fcb (including camera references) but unfortunately there is no tool to decompile that one yet (Gibbed tools fail). I also found something that could be a list of default unlocked items (iteminventorylists.lib, Player.StartupKit.xml) but I'm not sure about that.


EDIT: So the program is pretty much done now and it can generate definitions for all libraries; there is a little problem though: Most of them don't automatically work. In many libraries a value in a file has a different value type than it should have which lets Gibbed tools crash so I have to manually adjust individual types to fix the crashes. That'll be a fun time. I'm half-tempted to make another program for that.

EDIT2: Does anyone know where the vehicle pain job textures get referenced in the libraries? The TextureDB contains the shop icons but not the actual vehicle textures and I couldn't find anything with Notepad++ file search over all libs.

so far as i know,the car on demand mod hasn't been released yet,
## Post #263
- Username: mostafa0017
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jun 12, 2017 3:33 am
- Post datetime: 2017-06-15T18:52:38+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Thank you so much for the definitions I use razor's data conversion utility to convert long BinHexs to strings and after using your definitions most of the hashs and the BinHexs got converted except for a few but when I tried to convert on of them using razor's tool I got gibberish for example this line "<field name="texturedbobjectAlbumArtTexture" type="BinHex">9DD19D4207000080</field>" located in "RADIO_FINAL_Bay_City_Pop.Major_Lazer.xml" before using your definitions the field name was in a hash form but now it's converted however If I tried to convert the "9DD19D4207000080" I get "�ѝB" as a string any guidance ?
## Post #264
- Username: MrWasdennnoch
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue May 30, 2017 11:44 pm
- Post datetime: 2017-06-15T19:29:28+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from mostafa0017
>
> Thank you so much for the definitions I use razor's data conversion utility to convert long BinHexs to strings and after using your definitions most of the hashs and the BinHexs got converted except for a few but when I tried to convert on of them using razor's tool I got gibberish for example this line "<field name="texturedbobjectAlbumArtTexture" type="BinHex">9DD19D4207000080</field>" located in "RADIO_FINAL_Bay_City_Pop.Major_Lazer.xml" before using your definitions the field name was in a hash form but now it's converted however If I tried to convert the "9DD19D4207000080" I get "�ѝB" as a string any guidance ?
That's because it's not a String; fields like this with 8 bytes are (I think) of the type UInt32. They're just IDs pointing to another lib file.
## Post #265
- Username: mostafa0017
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jun 12, 2017 3:33 am
- Post datetime: 2017-06-16T10:55:58+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

But they are too long to be UInt32 but maybe they are UInt64 ?? but still though "9DD19D4207000080" converts to "9223372068037185949" in UInt64
## Post #266
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2017-06-16T14:20:21+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

So entitylibrary.fcb is very interesting as every mission script in the game refers to the entities which I guess are stored in entitylibrary.fcb. Being able to extract that file would definitely help us in terms of making the spider drone available in free roam without editing the mission scripts.
## Post #267
- Username: MrWasdennnoch
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue May 30, 2017 11:44 pm
- Post datetime: 2017-06-16T14:58:51+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from mostafa0017
>
> But they are too long to be UInt32 but maybe they are UInt64 ?? but still though "9DD19D4207000080" converts to "9223372068037185949" in UInt64
Ah yes, UInt64 then. 9223372068037185949 seems about right.
## Post #268
- Username: Bluebolt
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 30, 2017 9:19 pm
- Post datetime: 2017-07-03T13:02:20+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

How can find the models?
## Post #269
- Username: MrWasdennnoch
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue May 30, 2017 11:44 pm
- Post datetime: 2017-07-04T17:45:42+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Bad news. Update 1.16 renders the helicopter on demand mod useless. You can't enter a helicopter anymore. Not through hijacking one, not through ordering one via car on demand. This is a sad day. Let's hope the entitylibrary has a flag for it, assuming we get a tool to decompile it soon.
## Post #270
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2017-07-05T11:27:22+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

The lack of response shows that there is no interest in modding this game anymore. We won't get any tool.
## Post #271
- Username: redcomet
- Rank: advanced
- Number of posts: 40
- Joined date: Sat Dec 03, 2016 11:35 am
- Post datetime: 2017-07-05T14:06:57+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from CobraGamer
>
> The lack of response shows that there is no interest in modding this game anymore. We won't get any tool.
give it some time,the dev is still updating the game
## Post #272
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2017-07-06T08:28:47+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

It's not about the devs, it's about modders who actually are able to create such a tool. We're like 10 persons still modding this game and none of us has the abilities - I may have been wrong!
## Post #273
- Username: MrWasdennnoch
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue May 30, 2017 11:44 pm
- Post datetime: 2017-08-03T14:19:43+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Aaaand it's over. EAC detects all mods now. Awesome. Even such a simple fix like the escape button mod. GG ubi.
## Post #274
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2017-08-03T15:23:14+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Can't disable EAC anymore?
## Post #275
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2017-08-03T19:31:09+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

You still can disable EAC manually, but what's the point in getting locked out of multiplayer for just using graphics mods?
## Post #276
- Username: mlleemiles
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Sep 08, 2014 6:20 pm
- Post datetime: 2017-08-07T20:41:11+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Is it possible to convert entitylibrary.fcb? Gibbed tool doesn't seem to make sense of this file. I've already removed the extra header.
## Post #277
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2017-08-11T19:13:19+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

The entity library converter is out now on Guru3D

[http://forums.guru3d.com/showthread.php?t=416238](http://forums.guru3d.com/showthread.php?t=416238)
## Post #278
- Username: MrWasdennnoch
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue May 30, 2017 11:44 pm
- Post datetime: 2017-08-11T22:53:29+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Btw guys, we created a Discord server dedicated to WD modding. This has advantages such as live chat (as opposed to the traditional reload-to-see-reply forum), simple file sharing and, most importantly, it's one place for everything combined so you don't have to switch between different threads or even websites just to see stuff for WD1 or 2. If anyone is interested, the link to the server is Mod Edit: Link removed 

User edit: Well, you can find the link over at Guru3D as well lol Mod Edit: Link removed 
(I guess that link is allowed? ^^)
## Post #279
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2017-08-28T22:19:17+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from MrWasdennnoch
>
> Btw guys, we created a Discord server dedicated to WD modding. This has advantages such as live chat (as opposed to the traditional reload-to-see-reply forum), simple file sharing and, most importantly, it's one place for everything combined so you don't have to switch between different threads or even websites just to see stuff for WD1 or 2. If anyone is interested, the link to the server is Mod Edit: Link removed 

User edit: Well, you can find the link over at Guru3D as well lol Mod Edit: Link removed 
(I guess that link is allowed? ^^)

Hi there,

Though I understand your reasoning for posting a link to that Discord server. After careful reviewing, I decided that it's not appropriate to be posted here. If users wish to discuss content about the Watch Dogs 2 .dat/.fat file format or modding they can do so here. We're not prepared to deal withpotential problems which could occur off-site or be held liable for it.

Please respect my decision to remove the link from your post. Since you thought it was appropriate to add a link to a forum which links to that Discord server and gloat about it. I've decided to apply a suspension to your account. Please respect staff and the decisions they make.

Cheers.
## Post #280
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2018-06-06T05:29:21+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from Ekey
>
> One more, added ~34757> (242714) > http://www6.zippyshare.com/v/H8To8RZy/file.html

All the zippyshare links are dead.
Can anybody please give the link to download the tool to extract .dat .fat archive.
I have read the whole thread and didn't found a working link.
Please give the download link.
## Post #281
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2018-06-13T16:01:33+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from Ekey
>
> Small update. Added ~13214 > (458757) > http://www47.zippyshare.com/v/D8zEgUUf/file.html

Overall info:
Code: Select allXXXXX -> All Languages
common.fat -> Resolved: 5870 / Unknown: 165
dlc_ultra_textures.fat -> Resolved: 9312 / Unknown: 7
installpackage.fat -> Resolved: 8946 / Unknown: 104
installpackage_XXXXX.fat -> Resolved: 2620 / Unknown: 73
patch.fat -> Resolved: 51706 / Unknown: 4589
san_francisco.fat -> Resolved: 155642 / Unknown: 45368
san_francisco_cache.fat -> Resolved: 15690 / Unknown: 312
san_francisco_hires.fat -> Resolved: 17896 / Unknown: 268
san_francisco_preload.fat -> Resolved: 49269 / Unknown: 37444
san_francisco_XXXXX.fat -> Resolved: 14710 / Unknown: 7167
san_francisco_sound.fat -> Resolved: 4994 / Unknown: 487
san_francisco_sound_XXXXX.fat -> Resolved: 76514 / Unknown: 0
shadersobj.fat -> Resolved: 47358 / Unknown: 2976
sound.fat -> Resolved: 50 / Unknown: 0
videos.fat -> Resolved: 129 / Unknown: 1

Link is dead.
Can any body please give the link to download, please.
## Post #282
- Username: jhyxe
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 02, 2018 11:06 pm
- Post datetime: 2018-07-02T15:09:12+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from blackfoxeye
>
> Ekey wrote:Small update. Added ~13214 > (458757) > http://www47.zippyshare.com/v/D8zEgUUf/file.html

Overall info:
Code: Select allXXXXX -> All Languages
common.fat -> Resolved: 5870 / Unknown: 165
dlc_ultra_textures.fat -> Resolved: 9312 / Unknown: 7
installpackage.fat -> Resolved: 8946 / Unknown: 104
installpackage_XXXXX.fat -> Resolved: 2620 / Unknown: 73
patch.fat -> Resolved: 51706 / Unknown: 4589
san_francisco.fat -> Resolved: 155642 / Unknown: 45368
san_francisco_cache.fat -> Resolved: 15690 / Unknown: 312
san_francisco_hires.fat -> Resolved: 17896 / Unknown: 268
san_francisco_preload.fat -> Resolved: 49269 / Unknown: 37444
san_francisco_XXXXX.fat -> Resolved: 14710 / Unknown: 7167
san_francisco_sound.fat -> Resolved: 4994 / Unknown: 487
san_francisco_sound_XXXXX.fat -> Resolved: 76514 / Unknown: 0
shadersobj.fat -> Resolved: 47358 / Unknown: 2976
sound.fat -> Resolved: 50 / Unknown: 0
videos.fat -> Resolved: 129 / Unknown: 1

Link is dead.
Can any body please give the link to download, please.

Found a link for the patcher, but this one is wayyy older.

[https://www88.zippyshare.com/v/HZ4T8htq/file.html](https://www88.zippyshare.com/v/HZ4T8htq/file.html)

1.07 old. Still works but the filelist is Out of Date.
## Post #283
- Username: Omris
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Feb 01, 2018 11:04 pm
- Post datetime: 2018-07-25T06:01:53+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Anyone can help me ? this extractor is awesome but i need extract main english.loc
Anyone can give me a tool ?
## Post #284
- Username: PaulPhoenix31139
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Oct 09, 2018 4:38 pm
- Post datetime: 2019-01-19T09:09:03+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

Can someone please reload Latest update Ekey. Added ~13214 > (458757)
link broken

XXXXX -> All Languages
common.fat -> Resolved: 5870 / Unknown: 165
dlc_ultra_textures.fat -> Resolved: 9312 / Unknown: 7
installpackage.fat -> Resolved: 8946 / Unknown: 104
installpackage_XXXXX.fat -> Resolved: 2620 / Unknown: 73
patch.fat -> Resolved: 51706 / Unknown: 4589
san_francisco.fat -> Resolved: 155642 / Unknown: 45368
san_francisco_cache.fat -> Resolved: 15690 / Unknown: 312
san_francisco_hires.fat -> Resolved: 17896 / Unknown: 268
san_francisco_preload.fat -> Resolved: 49269 / Unknown: 37444
san_francisco_XXXXX.fat -> Resolved: 14710 / Unknown: 7167
san_francisco_sound.fat -> Resolved: 4994 / Unknown: 487
san_francisco_sound_XXXXX.fat -> Resolved: 76514 / Unknown: 0
shadersobj.fat -> Resolved: 47358 / Unknown: 2976
sound.fat -> Resolved: 50 / Unknown: 0
videos.fat -> Resolved: 129 / Unknown: 1
## Post #285
- Username: IlayArye
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 04, 2019 1:10 am
- Post datetime: 2019-07-03T17:12:17+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

is 3d model files extraction possible?
## Post #286
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2019-07-11T22:12:35+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from Sir Kane ↑Fri Dec 09, 2016 3:32 pm at Fri Dec 09, 2016 3:32 pm
>
> 
There's undoubtedly support for archives with LZMA compression, it just may not be used in the PC version. I haven't looked too hard for whatever enables it.

Hi Sir Kane,
I found the following files from the PS4 version of the Watch Dogs. They might be using LZMA compression there?
[viewtopic.php?f=21&t=20790](https://forum.xentax.com/viewtopic.php?f=21&t=20790)
## Post #287
- Username: Naden
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jun 20, 2017 10:09 pm
- Post datetime: 2019-11-10T13:50:55+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

When using the extractor, I get a lot of .hkx files but very few .xbg files even though they are in the filelist. Can anyone help me out?

Extracting this: Watch Dogs 2\data_win64\worlds\san_francisco\san_francisco.fat
## Post #288
- Username: iDu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Feb 15, 2021 1:53 am
- Post datetime: 2022-07-24T04:30:18+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

> Reply from Sir Kane ↑Sun Mar 05, 2017 9:28 pm at Sun Mar 05, 2017 9:28 pm
>
> 
New version that supports listing all file names contained within an archive and extracting specific files.

Name list has also been updated with some new names.

http://sktest.aruarose.com/WD2FatTools_v003.7z

Anymore updates? a version 4 or 5 with a filelist that resolves all names for musics files in san_francisco_sound.fat?
## Post #289
- Username: joaobrasil65
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Nov 22, 2022 6:22 am
- Post datetime: 2022-11-21T22:41:58+00:00
- Post Title: Re: watch dogs 2 .dat .fat archive?

I really want to get the City models used for San Francisco mostly.... anyway to easily do this?
