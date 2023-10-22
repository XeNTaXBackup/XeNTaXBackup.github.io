## Post #1
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-03-07T19:37:23+00:00
- Post Title: [Request] Guild Wars 2 DAT

I wanted to enlist some help on getting the DAT file for the GW2 client figured out. It shares similarities to GW1 from what I see, but its different, and I couldn't quite figure it out.

I can provide the 16mb patcher that you download, it downloads the rest of the game. I can also provide cuts of the archive file (what file cutter do you recommend?).

Just tell me which is the preferred route and how to get it to you guys.
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-03-07T20:19:23+00:00
- Post Title: [Request] Guild Wars 2 DAT

> Reply from aluigi
>
> and where are the samples?

> Reply from aluigi
>
> If files big use filecutter or other solutions:
http://www.xentax.com/downloads/tools/filecutter.zip

PS: Or just link for download client.
## Post #3
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-03-07T20:40:24+00:00
- Post Title: [Request] Guild Wars 2 DAT

* snip *

That is the link to the client patcher. 5 mb (rar file), 16mb extracted, it will download the rest of the client.

It downloads in place, so put it into a convenient folder.

The full size of the DAT after downloading the full client is 16gb
## Post #4
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-03-07T21:00:25+00:00
- Post Title: [Request] Guild Wars 2 DAT

I did do a bit of work already from the limited knowledge I know.

I also think there is a master file numbered 13525, it seems to have just a massive list in it. Not sure how its coded. URLs to their CDN are in the EXE if you run it through OllyDBG or monitor traffic with Wireshark. All files are downloaded compressed, but if you remove the compressed tag from the URLs, you will get the Uncompressed versions added to the .DAT file. If you get the cookie information, you can download them directly.

Other than that, I thought the list of files would be somewhere in memory, but I could not figure out where yet. So not sure how much this helps.
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-03-08T12:25:24+00:00
- Post Title: [Request] Guild Wars 2 DAT

Cutted [http://www.mediafire.com/?hsowrca6g562gzc](http://www.mediafire.com/?hsowrca6g562gzc)

```
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org
  optimized search function from Andrew http://www.team5150.com/~andrew/
  disassembler engine from Oleh Yuschuk

- open file "d:\GW2\Gw2Dev.exe"
- 22800384 bytes allocated
- load signatures
- open file d:\!Project\Game Tools\Aluigi\signsrch.sig
- 1774060 bytes allocated for the signatures
- 2278 signatures in the database
- WARNING:
  the file loaded in memory is very big so the scanning could take many time
- start signatures scanning:

  offset   num  description [bits.endian.size]
  --------------------------------------------
  0109fda0 31   Adler CRC32 (0x191b3141) [32.le.1024]
  010a0da0 32   Adler CRC32 (0x191b3141) [32.be.1024]
  010a01a0 33   Adler CRC32 (0x01c26a37) [32.le.1024]
  010a11a0 34   Adler CRC32 (0x01c26a37) [32.be.1024]
  010a05a0 35   Adler CRC32 (0xb8bc6765) [32.le.1024]
  010a15a0 36   Adler CRC32 (0xb8bc6765) [32.be.1024]
  00f66cf0 115  ADPCM index table (step variation) [32.le.64]
  00f66d30 117  ima_adpcm step table [16.le.178]
  01044940 135  libavutil ff_log2_tab [..256]
  0109e3e8 142  ACSS reverse sbox [..256]
  01022e48 145  SHA256 Hash constant words K (0x428a2f98) [32.le.256]
  008027e7 147  SHA256 Initial hash value H (0x6a09e667UL) [32.le.32&]
  010adfa0 167  Rijndael Te0 (0xc66363a5U) [32.le.1024]
  010ae3a0 169  Rijndael Te1 (0xa5c66363U) [32.le.1024]
  010ae7a0 171  Rijndael Te2 (0x63a5c663U) [32.le.1024]
  010aeba0 173  Rijndael Te3 (0x6363a5c6U) [32.le.1024]
  010aefa0 175  Rijndael Te4 (0x63636363U) [32.le.1024]
  010af3a0 176  Rijndael Td0 (0x51f4a750U) [32.le.1024]
  010af7a0 178  Rijndael Td1 (0x5051f4a7U) [32.le.1024]
  010afba0 180  Rijndael Td2 (0xa75051f4U) [32.le.1024]
  010affa0 182  Rijndael Td3 (0xf4a75051U) [32.le.1024]
  010b03a0 184  Rijndael Td4 (0x52525252U) [32.le.1024]
  010b07a0 185  Rijndael rcon [32.le.40]
  00801ee2 307  SHA1 / SHA0 / RIPEMD-160 initialization [32.le.20&]
  010a21c0 357  Zlib dist_code [..512]
  00f48ac0 358  Zlib length_code [..256]
  010a24c0 360  Zlib base_length [32.le.116]
  010a2538 362  Zlib base_dist [32.le.120]
  0118c4cc 373  possible mask reset used in arithmetic compression [..9]
  0109c650 384  Jpeg dct 14 bit aanscales [16.le.128]
  0109c610 388  Jpeg dct AA&N scale factor [double.le.64]
  0114e29a 550  Windows CryptAcquireContext [..21]
  0049d86b 568  classical random incrementer 0x343FD 0x269EC3 [32.le.8&]
  00e3d940 815  libavcodec ff_zigzag_direct [..64]
  00f632b0 851  libavcodec ASF asf_header [..16]
  00f67d48 855  Generic bitmask table [32.le.128]
  00f63cb0 973  asf_content_desc_guid [..16]
  011974b0 1014 mp3lib huffman tab1 [16.le.14]
  01196a6c 1016 mp3lib huffman tab2 [16.le.34]
  011974c0 1018 mp3lib huffman tab3 [16.le.34]
  011974e4 1020 mp3lib huffman tab5 [16.le.62]
  01197524 1022 mp3lib huffman tab6 [16.le.62]
  01197568 1024 mp3lib huffman tab7 [16.le.142]
  011975f8 1026 mp3lib huffman tab8 [16.le.142]
  01197688 1028 mp3lib huffman tab9 [16.le.142]
  01197718 1030 mp3lib huffman tab10 [16.le.254]
  01197818 1032 mp3lib huffman tab11 [16.le.254]
  01197918 1034 mp3lib huffman tab12 [16.le.254]
  01197a18 1036 mp3lib huffman tab13 [16.le.1022]
  01197e18 1038 mp3lib huffman tab15 [16.le.1022]
  01198218 1040 mp3lib huffman tab16 [16.le.1022]
  01198618 1042 mp3lib huffman tab24 [16.le.1022]
  01198a18 1044 mp3lib huffman tab_c0 [16.le.62]
  01198a58 1046 mp3lib huffman tab_c1 [16.le.62]
  01196a90 1048 mp3lib bandInfo [..2592]
  01194970 1049 mp3lib intwinbase [32.le.1028]
  00f67f68 1176 Vorbis FLOOR1_fromdB_LOOKUP [float.le.1024]
  0109e3e8 1198 FFT and FHT routines rv_tbl [..128]
  00f4b788 1228 rfc3548 Base 64 Encoding with URL and Filename Safe Alphabet [..
62]
  00f61648 1237 B64EncodeTable [..64]
  010a1b78 1525 zinflate_lengthExtraBits [32.le.116]
  010a1c00 1529 zinflate_distanceExtraBits [32.le.120]
  0114cc02 1767 anti-debug: IsDebuggerPresent [..17]
  00f67d4c 1810 bitmask [32.le.128]
  015be7b4 2253 PADDINGXXPADDING [..16]
  00f48bc0 2254 unlzx table_one [..32]
  00f67d48 2259 unlzx table_three [32.le.64]
  00de0bd0 2269 DMC compression [32.le.16&]
  0104d163 2271 compression algorithm seen in the game DreamKiller [32.le.12&]
  01046217 2272 compression algorithm seen in the game DreamKiller [32.be.12&]

- 70 signatures found in the file
```
## Post #6
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-03-09T04:03:17+00:00
- Post Title: [Request] Guild Wars 2 DAT

So this is what I have found so far that could help:

/latest/102 : has the latest build # (ex. returns: 13525 2312313 12313123) the first number is the build number.
/manifest/program/102/{build#} : manifest file for build number (ex. 13525, 13603)
/program/102/0/0/{fileNumber}/ : the actual data file uncompressed (ex. 844474 - MP3 File of a Roar)
/program/102/0/0/{fileNumber}/compressed : the actual data file compressed (have not investigated the compression used)

The Manifest File:

It is a list of UInt32 in Little Endian order. once converted to decimals, they are the fileNumber used in the above links. They do not have filenames, the number is the filename.
The Cookie information, and the CDN address is in the GW2Dev.exe file, should not be hard to find for those that are working on it.

Also, randomly (well seems random to me) there are numbers in the Manifest files that are not Files. They are the size in bytes of the previous file downloaded.

Example:
1814180 - 345208 bytes
2519389 - 345036 bytes
345036
2054826 - 72964 bytes
2948595 - 104384 bytes
104384

There are a lot of files unknown to me. AMATGMRT, MAPCPARM, PIMGPG, AMSPAMSP, MODLMODL, CINPC, and hvkChavK. A lot of files seem to have messed up or modified headers. like a good portion of the DXT files. They have a ATEXDXT# in the header, instead of some of the ones that work that start with DDS|. I have no clue how to repair the header, if its even possible. But I did some reading, it sounds similar to the GW1 ATEXDXT files. Messed up header, seems the size of the image is there somewhere after the header. Missing Texels? Thats all I read.
## Post #7
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-03-13T23:11:16+00:00
- Post Title: [Request] Guild Wars 2 DAT

Anyone have any success or progress on this? Just curious.
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-03-14T00:14:51+00:00
- Post Title: [Request] Guild Wars 2 DAT

i got a script to look at the uncompressed files but it downloaded 50 gigs of files not sure how that's possible.
## Post #9
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-03-14T00:24:39+00:00
- Post Title: [Request] Guild Wars 2 DAT

> Reply from chrrox
>
> i got a script to look at the uncompressed files but it downloaded 50 gigs of files not sure how that's possible.

Well, I dunno what compression they use, or if they have secondary manifests somewhere, but that is correct. Uncompressed size of the download is 50 gigs of files. But compressed it is 16 gigs inside the DAT file. It compresses each file individually and then inserts it into the dat.

If you modify the GW2Dev.exe file and remove the /compressed from the URLs that are coded into the EXE, it will download 50 gigs directly into the DAT file. At least it did the last time I checked.

You can try it yourself and see. Backup your 16 gig file, and download the 50 gig version. you can then use it to compare for finding how files are stored in the DAT file? and then you can compared the uncompressed to the compressed to see how ti was compressed.

Not sure what to tell you.
## Post #10
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-03-14T00:45:46+00:00
- Post Title: [Request] Guild Wars 2 DAT

now that would be very usefull especially if it downloads them in order.
ill give that a try.
## Post #11
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-03-14T00:57:00+00:00
- Post Title: [Request] Guild Wars 2 DAT

> Reply from chrrox
>
> now that would be very usefull especially if it downloads them in order.
ill give that a try.

You can also try with small samples. Let it download 20-30 files uncompressed, then 20-30 comrpessed into seperate dat files. So you dont have to wait.

You can then also check if they are in order.

Also you can download the individual files with my script, or a modified version of my script, and find the data in the archives. I dont have the tools to do it, but maybe some how search for the contents of Uncompressed File 1 in Uncompressed DAT, and then search Compressed File 1 in Uncompressed DAT file. and it could help you figure out how the DAT is split up and so on.

I think from there you know more than I do.

I also believe it downloads them in the order of the manifest.
## Post #12
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-03-18T19:29:22+00:00
- Post Title: [Request] Guild Wars 2 DAT

Any luck?
## Post #13
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-03-18T20:55:15+00:00
- Post Title: [Request] Guild Wars 2 DAT

i never got the uncompressed data as one big file
## Post #14
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-03-19T00:48:09+00:00
- Post Title: [Request] Guild Wars 2 DAT

> Reply from chrrox
>
> i never got the uncompressed data as one big file

Even after modifying the patcher?

At address 00F5F454 of the latest exe (Build 13703), there is a line that says /compressed (2F 63 6F 6D 70 72 65 73 73 65 64), if you 0 that out, it should download everything uncompressed into the data file. I just did it yesterday to test. I have a 34 gig DAT file atm. Still downloading.

[Edit] Just did it. First ~1000 files. Compressed file is 135MB, uncompressed file is 239MB. I am uploading them both atm to dropbox and will link them to you in a bit.
## Post #15
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-03-19T01:58:01+00:00
- Post Title: [Request] Guild Wars 2 DAT

Compressed DAT Part (132MB) :Gw2DevStream-Compressed.dat ( just the first ~1000 files downloaded)
Uncompressed DAT Part (233MB): Gw2DevStream-Uncompressed.dat ( hopefully the same ~1000 files )

The way i cut it off, i started the patcher with no Data file (backed up my old one) and launched it, when it reached 157000 remaining files, I shut off the patcher. and I believe it started at 158000ish. Then I 00'd out the /compressed in the EXE, and did the same with a new data file.

[Edit] I took down the links, so they aren't linked to my dropbox account, and I believe anyone that would need them, has them.
## Post #16
- Username: BobSaget
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 23, 2012 8:17 am
- Post datetime: 2012-03-23T00:21:14+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Any progress on this? and also has anyone managed to download a single file from [http://assetcdn.101.arenanetworks.com/](http://assetcdn.101.arenanetworks.com/) ?
## Post #17
- Username: BobSaget
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 23, 2012 8:17 am
- Post datetime: 2012-03-23T15:25:59+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

You can edit existing tools for GW1 to extract files from the uncompressed gw2stream.dat, but only the uncompressed one atm.

Header size has gone from 32 -> 40;

// Header of the Gw2Stream.dat
struct Header {
unsigned char ID[4];
int HeaderSize;
unsigned char Unk0[4]; // Difference GW1 -> GW2
int SectorSize;
int CRC;
__int64 MFTOffset;
int MFTSize;
int Flags;
};
## Post #18
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-03-24T03:47:22+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from BobSaget
>
> You can edit existing tools for GW1 to extract files from the uncompressed gw2stream.dat, but only the uncompressed one atm.

Header size has gone from 32 -> 40;

// Header of the Gw2Stream.dat
struct Header {
unsigned char ID[4];
int HeaderSize;
unsigned char Unk0[4]; // Difference GW1 -> GW2
int SectorSize;
int CRC;
__int64 MFTOffset;
int MFTSize;
int Flags;
};

Logically, the way that the patcher adds files to the DAT file, it should work with the compressed version. Since the files are compressed individually, not the entire archive.

So maybe I don't know enough about this, but it should work for the compressed version, the difference is that it will extract compressed versions of the files, instead of uncompressed.

But I personally haven't done too much work with reverse engineering things, and I am not familiar with a lot of this stuff, so I am just tyring to help as best I can. Hopefully those more knowledgeable will chip in more. (i mean i understand all this, i just wouldnt know where to begin on how to decipher header information and file structures.)
## Post #19
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-03-24T04:39:47+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from BobSaget
>
> Any progress on this? and also has anyone managed to download a single file from http://assetcdn.101.arenanetworks.com/ ?

Also in response to this. I have. I even wrote some code to read the manifest and download the files in order, uncompressed. You need a cookie that is in the Patcher (in plain text) in order for the link to let you download. ALSO its assetcdn.102 not 101

Aside from the cookie, all the info to download from the CDN is posted in my earlier posts.
## Post #20
- Username: ItsmeJC
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Apr 30, 2009 7:40 am
- Post datetime: 2012-03-24T06:14:20+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Nimba
>
> ALSO its assetcdn.102 not 101

101=Beta Client
102=Dev Client
103=Alternate
104=Alternate

The dat and binary are not compatible between them.
## Post #21
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-03-24T06:18:30+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from ItsmeJC
>
> Nimba wrote:ALSO its assetcdn.102 not 101

101=Beta Client
102=Dev Client
103=Alternate
104=Alternate

The dat and binary are not compatible between them.

Oh wow, this I did not know. I believe the Dev Client is being phased out for the Beta one, as that will most likely have the newer filestructures and other stuff.

Hmm, well then the stuff I said earlier might not apply 100%. I don't have the Beta client to test.
## Post #22
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-03-24T08:41:13+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

For those that want to get the different clients:

assetcdn.{#}.arenanetworks.com
get /latest/{#}

It will be in this format (not sure what the other file is, just has some languages listed):

```

```


with the file info, query for the files.

/program/{#}/0/0/{EXEfileNum}

That should download a file with the size of {EXEFileSize}. Rename it whatever you want, I named mine Gw2Dev.exe or Gw2Beta.exe depending on which one it is.

Thats it, you now have the patchers for whichever you want.

{#} is the type. As stated by ItsmeJC
101 = Beta Client
102 = Dev Client
103 = Alternate
104 = Alternate
## Post #23
- Username: mqltglea
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 25, 2012 7:10 am
- Post datetime: 2012-03-24T23:12:35+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

I've been interested in trying to analyze the GW2 data for a while, but haven't had access to the client. If anyone cares to PM me I'd appreciate it and hopefully be able to contribute.
## Post #24
- Username: BobSaget
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 23, 2012 8:17 am
- Post datetime: 2012-03-24T23:46:55+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Here is the dl link for the current gw2 beta.

[http://www.sendspace.com/file/irw7zc](http://www.sendspace.com/file/irw7zc)
## Post #25
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-03-25T01:30:09+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Actually, I PMed this to mqltglea, but then decided that I will release it public.

This is the Python script I wrote that will query for the LATEST build, and pull the EXE for that build. Meaning you can always get the latest build from whichever branch you want.

Usage:

```

```


the {#} is the codes we posted above, 101, 102, 103, 104. Only 101 and 102 are of any importance atm. Once you get the EXE, run the EXE and it will download the rest of the client.

There is almost 0 error handling, so if you get errors, make sure you are entering the right numbers. If you dont enter the number, it will just error.

This should get people started. It willd ownload things into the current directory of the script in specific folders, if you download them all, this is how the folder will look:

gw2intializer.py
Beta\Gw2Beta.exe
Dev\Gw2Dev.exe
Alternate103\Gw2Branch103.exe
Alternate104\Gw2Branch104.exe

Keep that in mind when running it.

THIS SCRIPT REQUIRES PYTHON 3.x, PREFERABLY PYTHON 3.2!!!!!


 gw2initializer.zip
Gw2 Intializer - Removed Numpy import (988 Bytes) Downloaded 159 times
## Post #26
- Username: BobSaget
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 23, 2012 8:17 am
- Post datetime: 2012-03-25T04:29:03+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

People should already know this but if they want the script to work they will have to download the numpy module. This is especially usefull for those using the 64bit python.

[http://www.lfd.uci.edu/~gohlke/pythonlibs/#numpy](http://www.lfd.uci.edu/~gohlke/pythonlibs/#numpy)
## Post #27
- Username: mqltglea
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 25, 2012 7:10 am
- Post datetime: 2012-03-25T05:11:07+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from BobSaget
>
> People should already know this but if they want the script to work they will have to download the numpy module. This is especially usefull for those using the 64bit python.

http://www.lfd.uci.edu/~gohlke/pythonlibs/#numpy

I just took out the dependency. I didn't see numpy getting used anywhere. I also had to change a backslash to a forward slash, but I'm on a mac atm, so that could have been the cause.
## Post #28
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-03-25T07:59:59+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Oh, my apologies, I copied the script from my fiel downloader script, forgot to remove Numpy. I used numpy to load up the manifest in half a second instead of 1 min.

I will get the script re-uploaded so you don't need to edit the script.

[Edit] Fixed, reuploaded the script so it doesn't have the Numpy import.
## Post #29
- Username: Gornoth
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Mar 25, 2012 10:43 am
- Post datetime: 2012-03-25T18:49:53+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Has anyone modified the gw unpacker to work with gw2stream.dat?
## Post #30
- Username: BobSaget
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 23, 2012 8:17 am
- Post datetime: 2012-03-25T19:32:57+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

I know someone modified the GW Dat Browser on 4chan to extract audio and textures. I have the source files if any one needs them. Should be just a modification of the header information to get the dat browser to work with gw2. (but for the uncompressed gw2stream.dat until someone figures out the compression algorithm.)

Edit: Here is the link anyways for people that want it.
GW Dat Browser
[http://www.raechaer.de/GWDatBrowser.rar](http://www.raechaer.de/GWDatBrowser.rar)

Supposedly if you modify the header struct to match it will read and extract the gw2 dat file. I havent tried anything yet though.
## Post #31
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-03-25T20:11:33+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Gornoth
>
> Has anyone modified the gw unpacker to work with gw2stream.dat?

Yes and no, I did a bit of modifying, but there seems to be more than just modifying the header. The thing hits the first file, and bugs out, then errors out on the 2nd file. It seems that either the MFT Header has gotten more fields, the MFT Entry has more fields, or both. Since for some reason when it reads the first file, it wants to allocate 330 megs of space for the output file....

Here is my source of what I have so far. All I did was update the headers, a few of the checks, and so on, nothing special. I put it into its own folder. I use Visual Studio 2010 and it upgraded the SLN file from the original. The original is still there as sln.orig, so if you want to use that you can.

All the original work, sources, and everything is still present form the GW1 download.

I tried the same thing with GWDatBrowser, and it broke in the exact same place after I modified the headers. Maybe I am doing this wrong. Its the same code. GWDatBrowser pretty much directly uses GWUnpacker in its code. with a bit of modification to non-crucial areas.
[GWUnpacker.zip](https://xentaxbackup.github.io/file/5230_GWUnpacker.zip)
## Post #32
- Username: blinky57
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Mar 27, 2012 5:25 am
- Post datetime: 2012-03-26T21:41:27+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

hello guys,

so i've been reading through this topic and while most of it is going over my head, i was wondering if its possible to extract 3d models from the .dat?
## Post #33
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-03-27T00:28:57+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from blinky57
>
> hello guys,

so i've been reading through this topic and while most of it is going over my head, i was wondering if its possible to extract 3d models from the .dat?

Extracting anything isn't possible yet, unless someone somewhere has made progress on getting the files to extract. But you can download the files directly uncompressed. and I know i haev a lot of MODL files downloaded. So yes, you can get the models.
## Post #34
- Username: blinky57
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Mar 27, 2012 5:25 am
- Post datetime: 2012-03-27T01:51:54+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

ok part two. if you already have the files, any way i could bum the male sareph armor model off you?

thanks
## Post #35
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-03-27T03:51:04+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from blinky57
>
> ok part two. if you already have the files, any way i could bum the male sareph armor model off you?

thanks

Sure, if i knew which file it was, or how to open these. I have no real clue what the file format is, nor are tehy named or soerted in any way to figure out the models. they are all just numbers all lumped together.
## Post #36
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-03-27T10:52:10+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

I am curious if anyone has managed to figure out what the 2nd file in the LATEST query is. it goes build exeNum exeFileSize WEIRDFILE WEIRDFILESIZE

The file has map names, languages and this at the bottom:

```

```
## Post #37
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2012-03-27T16:50:37+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

what file # is that?
## Post #38
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2012-03-27T17:26:36+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

and can you post that file? it looks very similar to file #13, except mine ends with 
buildId.records.....<...............3...............*...........................baseId.fileId.size.PackAssetManifestRecordV0.PackAssetManifestV0................FOOT

and has no plain text map names or anything
## Post #39
- Username: Phi La Ke Terre
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 28, 2012 1:34 am
- Post datetime: 2012-03-27T18:22:57+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

For those who try to re-use the GWunpacker/GWDatBrowser : the decompression function used is different. Can can look at the function at GW2Demo.exe 0x7CD130, I think it is the good one, (but I don't have any clue on how I can use it). I can disassemble it, but since I don't understand assembler, I can't do much.

```
.text:007CD130
.text:007CD130 ; Attributes: bp-based frame
.text:007CD130
.text:007CD130 sub_7CD130      proc near               ; CODE XREF: sub_7CC4C0+148p
.text:007CD130
.text:007CD130 var_1270        = dword ptr -1270h
.text:007CD130 var_94C         = dword ptr -94Ch
.text:007CD130 var_940         = dword ptr -940h
.text:007CD130 var_1C          = dword ptr -1Ch
.text:007CD130 var_18          = dword ptr -18h
.text:007CD130 var_14          = dword ptr -14h
.text:007CD130 var_10          = dword ptr -10h
.text:007CD130 var_C           = dword ptr -0Ch
.text:007CD130 var_8           = dword ptr -8
.text:007CD130 var_4           = dword ptr -4
.text:007CD130 arg_0           = dword ptr  8
.text:007CD130
.text:007CD130                 push    ebp
.text:007CD131                 mov     ebp, esp
.text:007CD133                 mov     eax, 1270h
.text:007CD138                 call    call_1
.text:007CD13D                 push    ebx
.text:007CD13E                 push    esi
.text:007CD13F                 mov     esi, [ebp+arg_0]
.text:007CD142                 mov     eax, [esi+0Ch]
.text:007CD145                 push    edi
.text:007CD146                 mov     [ebp+var_4], edx
.text:007CD149                 mov     edx, [esi+10h]
.text:007CD14C                 mov     ebx, eax
.text:007CD14E                 mov     edi, edx
.text:007CD150                 shl     eax, 4
.text:007CD153                 shr     edi, 1Ch
.text:007CD156                 or      edi, eax
.text:007CD158                 mov     eax, [esi+8]
.text:007CD15B                 shr     ebx, 1Ch
.text:007CD15E                 mov     [ebp+var_8], ecx
.text:007CD161                 mov     [esi+0Ch], edi
.text:007CD164                 cmp     eax, 4
.text:007CD167                 jb      short loc_1
.text:007CD169                 shl     edx, 4
.text:007CD16C                 mov     [esi+10h], edx
.text:007CD16F                 add     eax, 0FFFFFFFCh
.text:007CD172                 jmp     short loc_2
.text:007CD174 ; ---------------------------------------------------------------------------
.text:007CD174
.text:007CD174 loc_1:                             ; CODE XREF: sub_7CD130+37j
.text:007CD174                 mov     edx, [esi]
.text:007CD176                 cmp     edx, [esi+4]
.text:007CD179                 jz      short loc_7CD1A3
.text:007CD17B                 mov     edi, [edx]
.text:007CD17D                 add     edx, 4
.text:007CD180                 lea     ecx, [eax+1Ch]
.text:007CD183                 mov     [esi], edx
.text:007CD185                 mov     edx, edi
.text:007CD187                 shr     edx, cl
.text:007CD189                 mov     [ebp+arg_0], ecx
.text:007CD18C                 mov     ecx, 4
.text:007CD191                 sub     ecx, eax
.text:007CD193                 or      [esi+0Ch], edx
.text:007CD196                 mov     eax, [ebp+arg_0]
.text:007CD199                 shl     edi, cl
.text:007CD19B                 mov     ecx, [ebp+var_8]
.text:007CD19E                 mov     [esi+10h], edi
.text:007CD1A1                 jmp     short loc_2
.text:007CD1A3 ; ---------------------------------------------------------------------------
.text:007CD1A3
.text:007CD1A3 loc_7CD1A3:                             ; CODE XREF: sub_7CD130+49j
.text:007CD1A3                 xor     eax, eax
.text:007CD1A5                 mov     [esi+10h], eax
.text:007CD1A8
.text:007CD1A8 loc_2:                             ; CODE XREF: sub_7CD130+42j
.text:007CD1A8                                         ; sub_7CD130+71j
.text:007CD1A8                 mov     edx, [ebp+var_4]
.text:007CD1AB                 inc     ebx
.text:007CD1AC                 mov     [esi+8], eax
.text:007CD1AF                 lea     eax, [ecx+edx]
.text:007CD1B2                 mov     [ebp+var_10], ebx
.text:007CD1B5                 mov     ebx, ecx
.text:007CD1B7                 mov     [ebp+var_4], eax
.text:007CD1BA                 cmp     ecx, eax
.text:007CD1BC                 jz      loc_7CD2F1
.text:007CD1C2
.text:007CD1C2 loc_7CD1C2:                             ; CODE XREF: sub_7CD130+1BBj
.text:007CD1C2                 push    esi
.text:007CD1C3                 lea     ecx, [ebp+var_1270]
.text:007CD1C9                 call    sub_7D4010
.text:007CD1CE                 push    esi
.text:007CD1CF                 lea     ecx, [ebp+var_940]
.text:007CD1D5                 call    sub_7D4010
.text:007CD1DA                 mov     eax, [esi+0Ch]
.text:007CD1DD                 mov     ecx, [esi+10h]
.text:007CD1E0                 mov     edi, eax
.text:007CD1E2                 mov     edx, ecx
.text:007CD1E4                 shr     edx, 1Ch
.text:007CD1E7                 shl     eax, 4
.text:007CD1EA                 or      edx, eax
.text:007CD1EC                 mov     [esi+0Ch], edx
.text:007CD1EF                 mov     edx, [esi+8]
.text:007CD1F2                 shr     edi, 1Ch
.text:007CD1F5                 mov     [ebp+var_C], edi
.text:007CD1F8                 cmp     edx, 4
.text:007CD1FB                 jb      short loc_7CD20B
.text:007CD1FD                 shl     ecx, 4
.text:007CD200                 add     edx, 0FFFFFFFCh
.text:007CD203                 mov     [esi+10h], ecx
.text:007CD206                 mov     [esi+8], edx
.text:007CD209                 jmp     short loc_7CD242
.text:007CD20B ; ---------------------------------------------------------------------------
.text:007CD20B
.text:007CD20B loc_7CD20B:                             ; CODE XREF: sub_7CD130+CBj
.text:007CD20B                 mov     ecx, [esi]
.text:007CD20D                 cmp     ecx, [esi+4]
.text:007CD210                 jz      short loc_7CD23A
.text:007CD212                 mov     eax, [ecx]
.text:007CD214                 add     ecx, 4
.text:007CD217                 mov     [esi], ecx
.text:007CD219                 lea     ecx, [edx+1Ch]
.text:007CD21C                 mov     edi, eax
.text:007CD21E                 shr     edi, cl
.text:007CD220                 mov     [ebp+arg_0], ecx
.text:007CD223                 mov     ecx, 4
.text:007CD228                 sub     ecx, edx
.text:007CD22A                 or      [esi+0Ch], edi
.text:007CD22D                 mov     edi, [ebp+var_C]
.text:007CD230                 shl     eax, cl
.text:007CD232                 mov     [esi+10h], eax
.text:007CD235                 mov     eax, [ebp+arg_0]
.text:007CD238                 jmp     short loc_7CD23F
.text:007CD23A ; ---------------------------------------------------------------------------
.text:007CD23A
.text:007CD23A loc_7CD23A:                             ; CODE XREF: sub_7CD130+E0j
.text:007CD23A                 xor     eax, eax
.text:007CD23C                 mov     [esi+10h], eax
.text:007CD23F
.text:007CD23F loc_7CD23F:                             ; CODE XREF: sub_7CD130+108j
.text:007CD23F                 mov     [esi+8], eax
.text:007CD242
.text:007CD242 loc_7CD242:                             ; CODE XREF: sub_7CD130+D9j
.text:007CD242                 inc     edi
.text:007CD243                 shl     edi, 0Ch
.text:007CD246                 test    edi, edi
.text:007CD248                 jz      short loc_7CD2C2
.text:007CD24A                 lea     ebx, [ebx+0]
.text:007CD250
.text:007CD250 loc_7CD250:                             ; CODE XREF: sub_7CD130+190j
.text:007CD250                 dec     edi
.text:007CD251                 mov     [ebp+arg_0], edi
.text:007CD254                 cmp     ebx, [ebp+var_4]
.text:007CD257                 jz      short loc_7CD2C2
.text:007CD259                 push    esi
.text:007CD25A                 lea     ecx, [ebp+var_1270]
.text:007CD260                 call    sub_7CCA10
.text:007CD265                 cmp     eax, 100h
.text:007CD26A                 jb      loc_7CD2FF
.text:007CD270                 lea     ecx, [eax-100h]
.text:007CD276                 call    sub_7CCDB0
.text:007CD27B                 mov     edi, eax
.text:007CD27D                 add     edi, [ebp+var_10]
.text:007CD280                 push    esi
.text:007CD281                 lea     ecx, [ebp+var_940]
.text:007CD287                 call    sub_7CCA10
.text:007CD28C                 mov     ecx, eax
.text:007CD28E                 call    sub_7CCC10
.text:007CD293                 lea     ecx, [edi+ebx]
.text:007CD296                 cmp     ecx, [ebp+var_4]
.text:007CD299                 ja      short loc_7CD304
.text:007CD29B                 mov     edx, ebx
.text:007CD29D                 sub     edx, [ebp+var_8]
.text:007CD2A0                 cmp     eax, edx
.text:007CD2A2                 jge     short loc_7CD304
.text:007CD2A4                 mov     ecx, ebx
.text:007CD2A6                 sub     ecx, eax
.text:007CD2A8                 dec     ecx
.text:007CD2A9                 test    edi, edi
.text:007CD2AB                 jz      short loc_7CD2BB
.text:007CD2AD                 lea     ecx, [ecx+0]
.text:007CD2B0
.text:007CD2B0 loc_7CD2B0:                             ; CODE XREF: sub_7CD130+189j
.text:007CD2B0                 mov     al, [ecx]
.text:007CD2B2                 dec     edi
.text:007CD2B3                 mov     [ebx], al
.text:007CD2B5                 inc     ebx
.text:007CD2B6                 inc     ecx
.text:007CD2B7                 test    edi, edi
.text:007CD2B9                 jnz     short loc_7CD2B0
.text:007CD2BB
.text:007CD2BB loc_7CD2BB:                             ; CODE XREF: sub_7CD130+17Bj
.text:007CD2BB                 mov     edi, [ebp+arg_0]
.text:007CD2BE
.text:007CD2BE loc_7CD2BE:                             ; CODE XREF: sub_7CD130+1D2j
.text:007CD2BE                 test    edi, edi
.text:007CD2C0                 jnz     short loc_7CD250
.text:007CD2C2
.text:007CD2C2 loc_7CD2C2:                             ; CODE XREF: sub_7CD130+118j
.text:007CD2C2                                         ; sub_7CD130+127j
.text:007CD2C2                 mov     ecx, [ebp+var_1C]
.text:007CD2C5                 test    ecx, ecx
.text:007CD2C7                 jz      short loc_7CD2CE
.text:007CD2C9                 call    sub_5E4D80
.text:007CD2CE
.text:007CD2CE loc_7CD2CE:                             ; CODE XREF: sub_7CD130+197j
.text:007CD2CE                 mov     ecx, [ebp+var_94C]
.text:007CD2D4                 xor     eax, eax
.text:007CD2D6                 mov     [ebp+var_1C], eax
.text:007CD2D9                 mov     [ebp+var_14], eax
.text:007CD2DC                 mov     [ebp+var_18], eax
.text:007CD2DF                 cmp     ecx, eax
.text:007CD2E1                 jz      short loc_7CD2E8
.text:007CD2E3                 call    sub_5E4D80
.text:007CD2E8
.text:007CD2E8 loc_7CD2E8:                             ; CODE XREF: sub_7CD130+1B1j
.text:007CD2E8                 cmp     ebx, [ebp+var_4]
.text:007CD2EB                 jnz     loc_7CD1C2
.text:007CD2F1
.text:007CD2F1 loc_7CD2F1:                             ; CODE XREF: sub_7CD130+8Cj
.text:007CD2F1                 pop     edi
.text:007CD2F2                 pop     esi
.text:007CD2F3                 mov     eax, 1
.text:007CD2F8                 pop     ebx
.text:007CD2F9                 mov     esp, ebp
.text:007CD2FB                 pop     ebp
.text:007CD2FC                 retn    4
.text:007CD2FF ; ---------------------------------------------------------------------------
.text:007CD2FF
.text:007CD2FF loc_7CD2FF:                             ; CODE XREF: sub_7CD130+13Aj
.text:007CD2FF                 mov     [ebx], al
.text:007CD301                 inc     ebx
.text:007CD302                 jmp     short loc_7CD2BE
.text:007CD304 ; ---------------------------------------------------------------------------
.text:007CD304
.text:007CD304 loc_7CD304:                             ; CODE XREF: sub_7CD130+169j
.text:007CD304                                         ; sub_7CD130+172j
.text:007CD304                 mov     ecx, [ebp+var_1C]
.text:007CD307                 xor     esi, esi
.text:007CD309                 cmp     ecx, esi
.text:007CD30B                 jz      short loc_7CD312
.text:007CD30D                 call    sub_5E4D80
.text:007CD312
.text:007CD312 loc_7CD312:                             ; CODE XREF: sub_7CD130+1DBj
.text:007CD312                 mov     ecx, [ebp+var_94C]
.text:007CD318                 mov     [ebp+var_1C], esi
.text:007CD31B                 mov     [ebp+var_14], esi
.text:007CD31E                 mov     [ebp+var_18], esi
.text:007CD321                 cmp     ecx, esi
.text:007CD323                 jz      short loc_7CD32A
.text:007CD325                 call    sub_5E4D80
.text:007CD32A
.text:007CD32A loc_7CD32A:                             ; CODE XREF: sub_7CD130+1F3j
.text:007CD32A                 pop     edi
.text:007CD32B                 pop     esi
.text:007CD32C                 xor     eax, eax
.text:007CD32E                 pop     ebx
.text:007CD32F                 mov     esp, ebp
.text:007CD331                 pop     ebp
.text:007CD332                 retn    4
.text:007CD332 sub_7CD130      endp


```

Sorry for the big code, but it seems I'm not allowed to attach the file.
## Post #40
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-03-27T19:44:01+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from nicoli_s
>
> and can you post that file? it looks very similar to file #13, except mine ends with 
buildId.records.....<...............3...............*...........................baseId.fileId.size.PackAssetManifestRecordV0.PackAssetManifestV0................FOOT

and has no plain text map names or anything

Its in latest, but I'll pull the most recent ones:

```
102: Build=13793 Patcher=3055547 PatcherFileSize=21993320 NewFile=3055544 NewFileSize=6808

```


I have attached the 2 files in a zip. They are labeled accordingly.
[gw2unknownfile.zip](https://xentaxbackup.github.io/file/5237_gw2unknownfile.zip)
## Post #41
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2012-03-27T20:15:01+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

thx for posting those nimba. ive been working on gw2 since i got a hold of the last beta test client, i basically went the same route as other people suggested, and i downloaded all the files uncompressed, and i have an app that does some categorization and displays them, so i can see textures, strings etc. Seems they changed very little from gw1, as i was able to reuse the ATEXReader posted on this forum, and was able to figure out the string data pretty quickly. One thing that is weird is that im not seeing that file you posted inside the .dat files, unless im missing something. But my format guesser finds others that have a similar header to this file, so either its an error on my part, or that file is only used in the actual patching, and not stored in the dat
## Post #42
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-03-27T20:20:48+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Ya, I was surprised the textures just needed ATEX, figured out it works a  day or 2 ago. We havent gotten around to doing any processing in the text files, but they are pretty easy to read even if you don't process them.

I guess our focus needs to be on analyzing more of the uncompressed files, and figuring out the DAT structure. The assembly that was posted above could lead to something. It is just past my expertise at that point. Not good enough to make use of it.

As for that file, it might be used as a template in memory for the Patcher to properly insert data into the DAT file or preferences for the patcher of some sort.
## Post #43
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2012-03-27T20:29:15+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

also im almost done figuring out the basic structure of that file, so ill post it once im done
## Post #44
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-03-27T23:04:41+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from nicoli_s
>
> also im almost done figuring out the basic structure of that file, so ill post it once im done

Very nice, how similar is it to GW1?
## Post #45
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-03-28T04:32:54+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Just an FYI to everyone. They have invalidated the cookie for the Dev branch, and branch 103 and 104. It now only works for the beta client.

So unless we get a new copy of the dev client to get the new cookie, we can't download 102,103,or104. For now, we are stuck with what we have, and the beta client.
## Post #46
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2012-03-28T14:32:28+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

i havent done any real work on gw1, so im not sure how the ARMFARMF file compares to gw1, if it even existed in gw1. didnt get a chance to finish it last night, but looks to be a header, a count of entries, and then for each entry 20 bytes of data, then null padded unicode strings for each entry
## Post #47
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-03-29T02:25:29+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Here is I think the relevant information from GW1 that could help you:

```
struct MainHeader
{
	unsigned char ID[4];
	int HeaderSize;
	int SectorSize;
	int CRC1;
	__int64 MFTOffset;
	int MFTSize;
	int Flags;
};

struct MFTHeader
{
	unsigned char ID[4];
	int Unk1;
	int Unk2;
	int EntryCount;
	int Unk4;
	int Unk5;
};

struct MFTEntry
{
	__int64 Offset;
	__int32 Size;
	unsigned short a;
	unsigned char b;
	unsigned char c;
	__int32 ID;
	__int32 CRC;
	__int32 type;
	__int32 uncompressedSize;
	__int32 Hash;
};

struct MFTExpansion
{
	int FileNumber;
	int FileOffset;
};

```


And earlier in the post, someone said that there is an extra 8 bits of data between the headersize and Sectorsize, so it turns into this:

```
{
	unsigned char ID[4];
	int HeaderSize;
	unsigned char Unk0[4];
	int SectorSize;
	int CRC1;
	__int64 MFTOffset;
	int MFTSize;
	int Flags;
};

```


I am sure there is more that needs changing, but it seems to read the header correctly at least, not sure.

Here is the xentax wiki page for GW1:
[http://wiki.xentax.com/index.php/Guild_Wars_DAT](http://wiki.xentax.com/index.php/Guild_Wars_DAT)
## Post #48
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2012-03-29T20:53:50+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

oh im not even worrying with the .dat for now, I got all the files extracted and categorized, so i dont even access the .dat in my app for now, i was talking about that one specific file you posted w/ the map names
## Post #49
- Username: Gornoth
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Mar 25, 2012 10:43 am
- Post datetime: 2012-03-29T22:50:09+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Anyone been able to extract files from the .dat yet?
## Post #50
- Username: polarbearsrawr
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Mar 31, 2012 5:01 am
- Post datetime: 2012-04-06T11:07:16+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Gornoth
>
> Anyone been able to extract files from the .dat yet?
using the updated dat extractor provided it'll extract files alright with a few 'error' files which you can skip, but it seems they're not all 100% recognized or contain data errors. For instance there's only a few sound OGG files that appear which are less then a second in length and the only texture files that I can open are the DDS ones since the ATEX converter doesn't seem to work. The DDS files open reasonably well, but after a set X amount of pixels, there is a random color pixel inserted into the data stream, and this repeats through the entire image such that towards the bottom of the file they can be offset by quite a lot.
## Post #51
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-04-07T02:24:59+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from polarbearsrawr
>
> Gornoth wrote:Anyone been able to extract files from the .dat yet?
using the updated dat extractor provided it'll extract files alright with a few 'error' files which you can skip, but it seems they're not all 100% recognized or contain data errors. For instance there's only a few sound OGG files that appear which are less then a second in length and the only texture files that I can open are the DDS ones since the ATEX converter doesn't seem to work. The DDS files open reasonably well, but after a set X amount of pixels, there is a random color pixel inserted into the data stream, and this repeats through the entire image such that towards the bottom of the file they can be offset by quite a lot.

Just an FYI for the ATEX reader (that ocmes with the browser or unpacker, forget which came with it). It actually can read the ATEX files and convert them to PNGs. It handsl DXT1-5 and 2 other specific ones. ATEP and ATEXDCX dont work.
## Post #52
- Username: parlan
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Apr 11, 2012 2:29 am
- Post datetime: 2012-04-10T18:36:14+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Hello,

I cant really extract much files.
After 14 files the program is closing with an error
## Post #53
- Username: polarbearsrawr
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Mar 31, 2012 5:01 am
- Post datetime: 2012-04-11T08:53:00+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from parlan
>
> Hello,

I cant really extract much files.
After 14 files the program is closing with an error

You need to skip those files that error out by increasing the start file parameter in the command line. So instead of typing 
gwunpacker gw2stream.dat x 0 124950
You would move on skipping the file 15 as you can see in the log window at the bottom and type:
gwunpacker gw2stream.dat x 16 124950
if that and any other files also error just go up by one each time continuing where the last error file was.
## Post #54
- Username: parlan
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Apr 11, 2012 2:29 am
- Post datetime: 2012-04-11T16:32:11+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Ahh, okay, horrible, but it seems to work by that now.
thank you
## Post #55
- Username: Lockout
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 11, 2012 7:09 am
- Post datetime: 2012-04-12T18:37:23+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Very cool reading all this. Just a quick question is there any command line arguments found?
## Post #56
- Username: Antodias
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 21, 2012 5:28 am
- Post datetime: 2012-04-12T18:52:16+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

There are some just like in Guild Wars 1: -image, -bmp, -noui
## Post #57
- Username: crazycatz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Apr 13, 2012 4:27 am
- Post datetime: 2012-04-12T20:33:17+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Lockout
>
> Just a quick question is there any command line arguments found?
Here's a list of what I found in the program:
nopatch
pvpdemo
pressdemo
perf
nodemotimer
demo
cinema
authsrv
assetsrv
filesrv
localdat
fps
windowed
userid
update
uninstall
tokenpassword
token
texlod
startmap
shareArchive
repair
portalalias
portal
password
noui
nosound
nopatchui
nomusic
nodelta
multi
mce
image
exit
enablescripting
enabledevice
enablecommerce
email
diag
dat
demounset
demoLang
cuda
copydat
combatlog
defaultcharname
bmp
autologin
audio
## Post #58
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-04-12T21:39:34+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

[viewtopic.php?f=28&t=1270](http://forum.xentax.com/viewtopic.php?f=28&t=1270)
## Post #59
- Username: typ1232
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 04, 2012 12:05 am
- Post datetime: 2012-04-15T14:52:01+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

take a look: [http://www.gamerevision.com/showthread. ... er&p=39401](http://www.gamerevision.com/showthread.php?2340-Guide-How-to-update-GWDatBrowser&p=39401)
## Post #60
- Username: nems
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 21, 2012 10:30 pm
- Post datetime: 2012-04-21T15:28:02+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

found here:
[http://www.reddit.com/r/Guildwars2/comm ... dable_yet/](http://www.reddit.com/r/Guildwars2/comments/sklzf/new_gw2_patcher_for_bwe_not_downloadable_yet/)

Someone can upload the dev client link?
## Post #61
- Username: BobSaget
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 23, 2012 8:17 am
- Post datetime: 2012-04-21T17:06:13+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

I would assume that is Nimba but I think it was somewhat of a guessing game figuring out the exact link to get the exe to download. It might just be a different cookie.
## Post #62
- Username: salamando
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 22, 2012 1:32 am
- Post datetime: 2012-04-21T18:01:07+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

When I try to grab the 101 client with the gw2initializer script, here's what I get:

```
Downloading 'latest' for 101
502
b'<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR
/xhtml1/DTD/xhtml1-strict.dtd">\r\n<html xmlns="http://www.w3.org/1999/xhtml">\r
\n<head>\r\n<meta http-equiv="Content-Type" content="text/html; charset=iso-8859
-1"/>\r\n<title>502 - Web server received an invalid response while acting as a
gateway or proxy server.</title>\r\n<style type="text/css">\r\n<!--\r\nbody{marg
in:0;font-size:.7em;font-family:Verdana, Arial, Helvetica, sans-serif;background
:#EEEEEE;}\r\nfieldset{padding:0 15px 10px 15px;} \r\nh1{font-size:2.4em;margin:
0;color:#FFF;}\r\nh2{font-size:1.7em;margin:0;color:#CC0000;} \r\nh3{font-size:1
.2em;margin:10px 0 0 0;color:#000000;} \r\n#header{width:96%;margin:0 0 0 0;padd
ing:6px 2% 6px 2%;font-family:"trebuchet MS", Verdana, sans-serif;color:#FFF;\r\
nbackground-color:#555555;}\r\n#content{margin:0 0 0 2%;position:relative;}\r\n.
content-container{background:#FFF;width:96%;margin-top:8px;padding:10px;position
:relative;}\r\n-->\r\n</style>\r\n</head>\r\n<body>\r\n<div id="header"><h1>Serv
er Error</h1></div>\r\n<div id="content">\r\n <div class="content-container"><fi
eldset>\r\n  <h2>502 - Web server received an invalid response while acting as a
 gateway or proxy server.</h2>\r\n  <h3>There is a problem with the page you are
 looking for, and it cannot be displayed. When the Web server (while acting as a
 gateway or proxy) contacted the upstream content server, it received an invalid
 response from the content server.</h3>\r\n </fieldset></div>\r\n</div>\r\n</bod
y>\r\n</html>\r\n'
Downloading EXE for branch 101
Traceback (most recent call last):
  File "gw2initializer.py", line 86, in <module>
    main()
  File "gw2initializer.py", line 83, in main
    downloadEXE(branch);
  File "gw2initializer.py", line 32, in downloadEXE
    url = "http://assetcdn."+str(branch)+".arenanetworks.com"+filePath+str(infoL
ist[1])
IndexError: list index out of range

C:\beta>


```


Anyone have any insight?  Thank you!
## Post #63
- Username: BobSaget
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 23, 2012 8:17 am
- Post datetime: 2012-04-21T18:20:48+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

You cannot grab the exe atm the cookie is no longer valid. The script in its current form doesnt work.
## Post #64
- Username: salamando
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 22, 2012 1:32 am
- Post datetime: 2012-04-21T18:34:28+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Damn.  Thanks for the info.
Saw a screenshot of the new launcher so someone has to have the cookie.  You the man, Bob.
## Post #65
- Username: BobSaget
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 23, 2012 8:17 am
- Post datetime: 2012-04-21T18:48:38+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

I think there was a way to retrieve the new cookie when the old one was still active but I im not sure its possible now that the old one is invalid, obviously aside from the person who already has the new cookie. But this isnt my area of expertise so just speculating.
## Post #66
- Username: kthackeray
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Mar 28, 2012 2:36 am
- Post datetime: 2012-04-21T20:22:14+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from salamando
>
> When I try to grab the 101 client with the gw2initializer script, here's what I get:
Code: Select allC:\beta>c:\Python32\python.exe gw2initializer.py 101
Downloading 'latest' for 101

502 - Web server received an invalid response while acting as a
gateway or proxy server.



Anyone have any insight?  Thank you!
Notice the error...

> Reply from BobSaget
>
> the cookie is no longer valid.
You wouldn't be able to see the error if the cookie was not valid. 
They use IIS and Application Request Routing for most of their servers.
They just have to fix the routing error.
## Post #67
- Username: BobSaget
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 23, 2012 8:17 am
- Post datetime: 2012-04-21T20:39:18+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

In his case it might of been a connection issue if he tries again he will probably get a different error, everyone else gets a 403 error, because the authentication/cookie is invalid.
## Post #68
- Username: salamando
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 22, 2012 1:32 am
- Post datetime: 2012-04-21T20:59:41+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

I've traveled from the office back to the hotel a few times today and get the same error message at both places.
## Post #69
- Username: BobSaget
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 23, 2012 8:17 am
- Post datetime: 2012-04-21T21:06:26+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Thats wierd. Well I get the proper 403 error. If I had the right hash code I would be able to download from their servers.
## Post #70
- Username: kthackeray
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Mar 28, 2012 2:36 am
- Post datetime: 2012-04-21T21:12:04+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

You must be authenticating incorrectly then. There is nothing wrong with the cookie.
## Post #71
- Username: BobSaget
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 23, 2012 8:17 am
- Post datetime: 2012-04-21T21:20:13+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

There is a reason the beta client, or the dev client, or the demo or the stage demo clients are no longer able to connect and crash instantly. Because access is denied to the servers. Are you able to launch the client and it updates? I dont think so. The servers are still there just the no access to them, and the only thing that determines access is the cookie.
## Post #72
- Username: bobone123
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Apr 22, 2012 1:43 am
- Post datetime: 2012-04-21T21:22:15+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

How are you suppose to execute the script?
when i double click it (python is installed), it opens a black window then close automaticly.
## Post #73
- Username: kthackeray
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Mar 28, 2012 2:36 am
- Post datetime: 2012-04-21T21:25:31+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from BobSaget
>
> There is a reason the beta client, or the dev client, or the demo or the stage demo clients are no longer able to connect and crash instantly. Because access is denied to the servers. Are you able to launch the client and it updates? I dont think so.

The reason for that being that the server is experiencing a routing issue, not because the client can't auth.
## Post #74
- Username: BobSaget
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 23, 2012 8:17 am
- Post datetime: 2012-04-21T21:29:09+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

No, the new BWE Client connects perfectly fine and updates perfectly. There are no routing issues there is a reason you are going to have to download a new client for the beta weekend event.
## Post #75
- Username: bobone123
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Apr 22, 2012 1:43 am
- Post datetime: 2012-04-21T21:33:38+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

BobSaget, can you explain how you did it then?
I have a very very slow internet connection (by satellite) and won't be able to download in time for the beta event (if I wait for the official release of the client).
## Post #76
- Username: kthackeray
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Mar 28, 2012 2:36 am
- Post datetime: 2012-04-21T21:42:47+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from BobSaget
>
> No, the new BWE Client connects perfectly fine and updates perfectly.

I can only assume any other client you are talking about (including the one pictured on the previous page) is the developer client, which yes, uses a different server and cookie and works fine.

As for the public one, the valid cookie only tells the Akamai mirror to forward the request to the origin server and that is what is happening here. Whether or not the server can supply the content right now is really irrelevant to my argument. The cookie is serving its purpose and the request is being forwarded. If you have another client that differs from these two, by all means, post the info.
## Post #77
- Username: salamando
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 22, 2012 1:32 am
- Post datetime: 2012-04-21T21:43:51+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from bobone123
>
> How are you suppose to execute the script?
when i double click it (python is installed), it opens a black window then close automaticly.

Hi there,
If you check my post out a few up you can see how I executed with the default python install.  Go to a dos prompt, cd into the directory you have the script, and run the command I listed above.  I'd be curious to see if it works for you (since it didn't for me).  Double clicking it doesn't provide the 101 that is needed at the end to tell the script which install to fetch.
## Post #78
- Username: BobSaget
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 23, 2012 8:17 am
- Post datetime: 2012-04-21T21:48:00+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

The Developer client uses the same authentication cookie as the beta client, Therefore the old dev client doesnt work either.

and the developer client doesnt use a different server it uses the same server just a different branch its like ftp but without login/password instead an authentication cookie.
## Post #79
- Username: kthackeray
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Mar 28, 2012 2:36 am
- Post datetime: 2012-04-21T21:51:00+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from BobSaget
>
> The Developer client uses the same authentication cookie as the beta client, Therefore the old dev client doesnt work either.

and the developer client doesnt use a different server it uses the same server just a different branch its like ftp but without login/password but an authentication cookie.

The dev cookie was changed weeks ago. Using the new cookie it works fine.

And okay yes, they all run through Akamai.
## Post #80
- Username: septic
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 22, 2012 5:43 am
- Post datetime: 2012-04-21T21:52:53+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from kthackeray
>
> BobSaget wrote:The Developer client uses the same authentication cookie as the beta client, Therefore the old dev client doesnt work either.

and the developer client doesnt use a different server it uses the same server just a different branch its like ftp but without login/password but an authentication cookie.

The dev cookie was changed weeks ago. Using the new cookie it works fine.

And okay yes, they all run through Akamai.

Any way you could upload the files needed to get started? Worried that my internetspeed wont suffice if they send me the link on Tuesday or later!
## Post #81
- Username: bobone123
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Apr 22, 2012 1:43 am
- Post datetime: 2012-04-21T21:53:36+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

salamando, can you explain in more details (i'm quite new to all of this lol) ?
## Post #82
- Username: timexy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Apr 02, 2012 9:34 am
- Post datetime: 2012-04-21T21:55:35+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from bobone123
>
> salamando, can you explain in more details (i'm quite new to all of this lol) ?

Without the new cookie that script is useless so it really doesn't matter...
## Post #83
- Username: salamando
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 22, 2012 1:32 am
- Post datetime: 2012-04-21T21:58:03+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from timexy
>
> bobone123 wrote:salamando, can you explain in more details (i'm quite new to all of this lol) ?

Without the new cookie that script is useless so it really doesn't matter...

Aye, sorry man, if someone spills the new cookie we can update the script and explain in more detail.  Right now it'd be for nothing.
## Post #84
- Username: bobone123
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Apr 22, 2012 1:43 am
- Post datetime: 2012-04-21T22:00:55+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

I see .... 

 For those who got the cookie... why don't you share it? It would definitly help some of us! D:
## Post #85
- Username: BobSaget
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 23, 2012 8:17 am
- Post datetime: 2012-04-21T22:02:08+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Yes the whole issue is the cookie they dont have routing issues. My speculation is they are going to give the beta client and the dev client their own authentication cookie to prevent people from downloading their dev client. Besides all the people asking for the download its useless for their purposes because it wont work for the BWE since its a developer client. I think they made a mistake when they uploaded the new launcher exe first and then changed the authentication cookie, which gave some people access to the new cookie.
## Post #86
- Username: kthackeray
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Mar 28, 2012 2:36 am
- Post datetime: 2012-04-21T22:07:06+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from BobSaget
>
> Yes the whole issue is the cookie they dont have routing issues. My speculation is they are going to give the beta client and the dev client their own authentication cookie to prevent people from downloading their dev client. Besides all the people asking for the download its useless for their purposes because it wont work for the BWE since its a developer client. I think they made a mistake when they uploaded the new launcher exe first and then changed the authentication cookie, which gave some people access to the new cookie.

Interesting speculation. As I already mentioned and has been mentioned on previous pages of this thread, the dev client received its own cookie weeks ago. You seem to stand firm with it and I've made my argument, but it's not uncommon for their servers to experience such issues.

[https://forum.guildwars.com/forum/forum ... f-HTTP-502](https://forum.guildwars.com/forum/forums/web/The-return-of-HTTP-502)
## Post #87
- Username: timexy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Apr 02, 2012 9:34 am
- Post datetime: 2012-04-21T22:13:13+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from bobone123
>
> I see .... 

 For those who got the cookie... why don't you share it? It would definitly help some of us! D:

Probably because it would be spread all over the internet since this thread has been linked on reddit now, and ArenaNet could do something to prevent us from downloading (unlikely, but yeah).

Also we would have an influx of people that don’t know how to make simple stuff like edit an file on notepad asking things like “how this work?” or “will I have to download it again later?”, and if they have to, they’ll come here angry about that because now it’s our fault, even though they downloaded it from their own volition still knowing it could happen.

Simply put, for the sake of peace, I don’t think anyone will share the new cookie, but if they did, I’d appreciate 

> Reply from kthackeray
>
> ...

Either way, it's 403 now. Maybe they were just preparing it for the BWE. The only way to know for sure is to get your hands on the new cookie and try to downlaod the latest file from branch 101 instead of 102.
## Post #88
- Username: bobone123
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Apr 22, 2012 1:43 am
- Post datetime: 2012-04-21T22:14:07+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Ok, i understand how to run the script now.
I simply hope someone will be kind enough to share the cookie lol

Edit: well, they could share it by pm you know
## Post #89
- Username: BobSaget
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 23, 2012 8:17 am
- Post datetime: 2012-04-21T22:18:43+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from bobone123
>
> Ok, i understand how to run the script now.
I simply hope someone will be kind enough to share the cookie lol

Edit: well, they could share it by pm you know

Why would you even want it its useless. You wouldnt be able to use it for BWE since its the developer client and not the beta client and their dat files are different anyways. Only use for it is for research on unpacking the dat but thats it.
## Post #90
- Username: bobone123
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Apr 22, 2012 1:43 am
- Post datetime: 2012-04-21T22:22:53+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Well, as far as i understand:
It's the same cookies for the beta and the dev client.
So in theory I could download the beta client instead, isn't that right!?
## Post #91
- Username: BobSaget
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 23, 2012 8:17 am
- Post datetime: 2012-04-21T22:27:14+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Nimba explains
## Post #92
- Username: timexy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Apr 02, 2012 9:34 am
- Post datetime: 2012-04-21T22:32:19+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

So they're using the same for all branches again? Not that getting the dev client would make any difference in-game; you'd just download more stuff and there is still the chance of it not working for the Live (Beta) servers. I'd just extract it and get the BGM again to check if there is anything new anyway...
## Post #93
- Username: BobSaget
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 23, 2012 8:17 am
- Post datetime: 2012-04-21T22:36:39+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Well the dev client will 100 percent not work with the Live beta servers. The dev client is what it is, its used by the developers to play and test their content. Though figuring out one of the dev accounts would be interesting but thats another ball game .
Edit: Another strong speculation I have is they they run their own server for the dev client which they test shit on so it would be always online and if you happen to have one of the dev accounts...... anyways.
## Post #94
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-04-21T22:43:10+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Ok, since things are getting a bit out of hand, here is some info.

The new cookies are Branch specific. The new cookie I have is only for branch 102. It will not work on any other branch. They have the branch specific numbers in the cookie and the paths are locked to the branch. SO you can no use the cookie I have for anything other than the 102 branch.

Second, no one needs the new cookie except those that work on reversing the DAT file. 

I repeat. IT IS USELESS FOR BWE, IT WILL NOT WORK ON BWE. they use different login servers. They are always up, and they are used by the DEVs.

I have given it to a select few people that I know are using it for reverse engineering the DAT file. That is its only purpose atm.

Even I will have to download the new BWE client from scratch because this one wont work.

I will not be updating the scripts. The scripts work 100% fine with the new cookie. Those that have the new cookie, just need to update the script with it.

Second, BWE is in a few days. a good 90% of you dont need the Dev Client. I have turned away many people in the last few days because they think they can just get the cookie from me to download. I do not want us hammering their CDN for Dev client stuff.

Anything that is worth releasing publicly has been released. The new GW2DatBrowser works, and once you get the BWE client, you can use it. The Unpacker kinda works, it will get you some stuff. For a majority of you, that will be plenty.
## Post #95
- Username: Loumie
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 12, 2012 3:00 pm
- Post datetime: 2012-04-23T07:56:02+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Hey,

As the patcher does not work for now, I had a question that I can't verify until I have the bwe client. 

I did some digging some time ago to understand how to navigate inside the various files in the DAT, I found that a good entry point was the "RootManifest" that you get from the latest query as it points to all the subsequent submanifests, etc, etc..

Now, after fixing the issue with big files for the new unpacker, it seems that I can't find this "RootManifest" in the dat archive. 
Does anyone know if the client is always making a query to retrieve it at boot ? I could do it myself but, without the client working I can't check the logic of the outgoing http queries.

Thanks !
## Post #96
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-04-23T19:04:55+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Loumie
>
> Hey,

As the patcher does not work for now, I had a question that I can't verify until I have the bwe client. 

I did some digging some time ago to understand how to navigate inside the various files in the DAT, I found that a good entry point was the "RootManifest" that you get from the latest query as it points to all the subsequent submanifests, etc, etc..

Now, after fixing the issue with big files for the new unpacker, it seems that I can't find this "RootManifest" in the dat archive. 
Does anyone know if the client is always making a query to retrieve it at boot ? I could do it myself but, without the client working I can't check the logic of the outgoing http queries.

Thanks !

Well, the patcher seems to download 2 files when it queries for a new build. it queries /latest, which returns 5 numbers.

build exeFile# exeFileSize unknownFile# and unknownFileSize.

The thing is, when i downloaded the unknownFile it looks kinda like a bare manifest, had some info in it, but it wasnt much, and i thoguht it was either some header or something.

There might be a chance that it is that RootManifest you want. Give me a little bit to grab the latest one, and I will post it here for you to look over and see if it is what you are looking for.
## Post #97
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-04-23T23:40:17+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Here is the file. Hopefully it is what you are looking for. Seems to have some kind of Manifest info in it at the bottom. Anyways, GL!
[Gw2DevUnknownfile.zip](https://xentaxbackup.github.io/file/5359_Gw2DevUnknownfile.zip)
## Post #98
- Username: kthackeray
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Mar 28, 2012 2:36 am
- Post datetime: 2012-04-24T05:14:56+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from BobSaget
>
> Yes the whole issue is the cookie they dont have routing issues. etc etc etc

...and now that the gateway issue has been fixed your argument is even more invalid.
## Post #99
- Username: Loumie
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 12, 2012 3:00 pm
- Post datetime: 2012-04-24T06:55:17+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Nimba
>
> Loumie wrote:Hey,

As the patcher does not work for now, I had a question that I can't verify until I have the bwe client. 

I did some digging some time ago to understand how to navigate inside the various files in the DAT, I found that a good entry point was the "RootManifest" that you get from the latest query as it points to all the subsequent submanifests, etc, etc..

Now, after fixing the issue with big files for the new unpacker, it seems that I can't find this "RootManifest" in the dat archive. 
Does anyone know if the client is always making a query to retrieve it at boot ? I could do it myself but, without the client working I can't check the logic of the outgoing http queries.

Thanks !

Well, the patcher seems to download 2 files when it queries for a new build. it queries /latest, which returns 5 numbers.

build exeFile# exeFileSize unknownFile# and unknownFileSize.

The thing is, when i downloaded the unknownFile it looks kinda like a bare manifest, had some info in it, but it wasnt much, and i thoguht it was either some header or something.

There might be a chance that it is that RootManifest you want. Give me a little bit to grab the latest one, and I will post it here for you to look over and see if it is what you are looking for.

Thanks for the file, Nimba!

Yes that's exactly the file I was talking about, it is actually a very important file in term of navigation/categorization in the DAT archive.
I was trying to understand if each time it boots (even if it's up to date) the program retrieves this file or not, as I can't find it in the DAT but only in the latest query.

Finally, for informations, these kinds of files are easy to understand, if you look at the bottom they actually tells you what it is, globally for each "category" (global, maps, languages, etc...) this files points you to the submanifest of these different categories, so it is a really good entry point. (By the way this file is slightly updated compared to the last one I have, maybe because it's DEV version though, the MapEventUnitTests/MapPvpDOTA made me laugh ;D)

So for example here we have:

uint32 buildId = 14049   
uint32 manifests = 123

then 123 records of the second struct.. etc...

But I will wait for the bwe client to verify my though, anyway it should be available really soon 

Cheers!

Edit: By the way, if someone is working on this (I'm more interested in actual game data more than textures/sounds) and wants to team-up, let me know via PM ;D
I'm looking at the txtm file for now, to see how they map the strs files~
## Post #100
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-04-24T10:07:08+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

[http://cloudfront.guildwars2.com/pVRS48 ... 1J/Gw2.zip](http://cloudfront.guildwars2.com/pVRS48PNCNhr0nlwfSIGf2jVkt4AhkjAVCp0IUp3ptvHlENECYbMWlJ49hwCn1J/Gw2.zip)

Beta client. It works again. Run it and it will update itself to the new one that will work for bwe
## Post #101
- Username: BobSaget
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 23, 2012 8:17 am
- Post datetime: 2012-04-24T12:37:29+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from kthackeray
>
> BobSaget wrote:Yes the whole issue is the cookie they dont have routing issues. etc etc etc

...and now that the gateway issue has been fixed your argument is even more invalid.

What routing issues?..... They just enabled the old auth cookie again. There were never any routing issues.
## Post #102
- Username: parlan
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Apr 11, 2012 2:29 am
- Post datetime: 2012-04-24T14:12:34+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

So "old" NDA-Beta client works =)
patience was the key
## Post #103
- Username: kthackeray
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Mar 28, 2012 2:36 am
- Post datetime: 2012-04-24T15:54:13+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from BobSaget
>
> What routing issues?..... They just enabled the old auth cookie again. There were never any routing issues.

> Reply from salamando
>
> When I try to grab the 101 client...
502 - Web server received an invalid response while acting as a
 gateway or proxy server. There is a problem with the page you are
 looking for, and it cannot be displayed. When the Web server (while acting as a
 gateway or proxy) contacted the upstream content server, it received an invalid
 response from the content server.

Keep telling yourself that.

> Reply from Loumie
>
> Does anyone know if the client is always making a query to retrieve it at boot ?

If the build matches the latest query, it just launches the game and doesn't look at either manifest.


> Reply from Loumie
>
> I'm looking at the txtm file for now, to see how they map the strs files~
The strs files themselves are actually pretty interesting. Using the same format as the original game.
## Post #104
- Username: BobSaget
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 23, 2012 8:17 am
- Post datetime: 2012-04-24T17:46:27+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

kthackeray obviously if I recieved that error thats another story. But I never ever had issues connecting to their server at any time, I would know I query the branchs every 30 minutes for any modified exe. I bet most of the people never got a 502. Just because you or someone else was having issues doesnt mean everyone else is. 
Edit: And dont forget you dont directly connect to arenanetworks.com, depending on your location you get bounced to a "patch server" for better speeds.
## Post #105
- Username: kthackeray
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Mar 28, 2012 2:36 am
- Post datetime: 2012-04-24T22:27:45+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from BobSaget
>
> Edit: And dont forget you dont directly connect to arenanetworks.com, depending on your location you get bounced to a "patch server" for better speeds.

> Reply from kthackeray
>
> As for the public one, the valid cookie only tells the Akamai mirror to forward the request to the origin server and that is what is happening here.

Not sure why you bring up things that have already been covered in the thread.

It actually just [happened to them again](http://twitter.com/#!/GuildWars2/status/194903803559026689) though. They could use a few pointers when it comes to load balancing.
## Post #106
- Username: BobSaget
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Mar 23, 2012 8:17 am
- Post datetime: 2012-04-24T22:31:20+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Well now its slightly happening because of load but a few tries will get it working again though.
## Post #107
- Username: Loumie
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 12, 2012 3:00 pm
- Post datetime: 2012-04-25T07:04:44+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from kthackeray
>
> Loumie wrote:
Does anyone know if the client is always making a query to retrieve it at boot ?
If the build matches the latest query, it just launches the game and doesn't look at either manifest.

Yep, just saw that this morning after the update was finished. I'll have to rescan my DAT then ;D

> Reply from kthackeray
>
> Loumie wrote:
I'm looking at the txtm file for now, to see how they map the strs files~
The strs files themselves are actually pretty interesting. Using the same format as the original game.

I didn't spend much time on the strs files, but I didn't have time to look at the ones that seems maybe encrypted of some sort, maybe that's what you're talking about because I didn't see anything special. Just a BOM, a size, a string, and other values that are here when it is not in "clear".

Cheers.
## Post #108
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-04-25T08:22:29+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Loumie, this might help you, but I was looking for where GW2 stored its settings and found a .DAT file in My Documents/Guild Wars 2. Then I noticed the Size, it was 1.2 megs. I deleted it, and for sure, I got my settings reset. But I was curious why it was so big. I backed up my old one before deleting which I think had some data from an older beta.

But anyways. I noticed in the hex editor, it had the same header as the GW2 Dat file. So I made the GW2DatBrowser point to it, and viola. A small DAT file with Manifests. Just manifests. At the very end of one, I saw a loclpref file, which i think had settings, but the new ones GW2 generated, didnt have this file. Which I am assuming is something left over from the old client.

But I do know somewhere in this local.dat it stores settings. There are quite a few files that GW2Dat doesnt even recognize and doesn't let me view them. But this could help you 

Maybe your update GW2DatBrowser you mentioned on GameRevision can get you more data.
## Post #109
- Username: Loumie
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 12, 2012 3:00 pm
- Post datetime: 2012-04-25T12:55:51+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Hey,

In fact, it seems that they are moving things around between betas, before this new beta I spotted the file you are talking about, the loclpref one, actually there are 4 files that seem special (apart from the ones that are 4097 / 4098 /etc..):

- Ids were: 2 / 3 / 12 / 13

There was:
- the loclpref that you talk about
- a file starting with dibw that seems to be like a CD Key or a serial
- the two remaining ones I don't remember

BUT, indeed now, a new file appeared the Local.dat one, I didn't look at it yet, but it seems interesting given what you found 
I'll run my parser on it to check all the files inside.

But, what I discovered is pretty funny, actually by rewritting the pseudo code that rafi did into a more correct one, I'm beginning to think that it is a simple zlib compression, as the description of what the algorithm of zlib does is exactly what the decompression algorithm is doing to extract the files, the only difference could be the initial static data. I'm more focused on this right now, if I find anything I'll let you know.

Edit: So I parsed this Local.dat and it is indeed what I was looking for, the 198828 is the main manifest, then there are 42 other manifests for the 42 sub categories, then there is the gw2.exe(198831) number and the localpref(3)
## Post #110
- Username: JimboJoe
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 27, 2012 9:55 pm
- Post datetime: 2012-04-27T14:04:13+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

I'm willing to pay for a working dat extractor, which at least extracts text-information (most important) and graphics from the game. Feel free to send me a pm.
## Post #111
- Username: Dolkar
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon May 07, 2012 11:13 pm
- Post datetime: 2012-05-07T15:30:27+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

What about sniffing out the location of in-game files and downloading them uncompressed without using the official downloader? That might be much easier than unpacking them from the .dat file.

The first thing that is probably getting downloaded is the list of the files and their locations (possibly even names?). I'll try to sniff that one out when I have some time. Or has anyone already successfully done that?
## Post #112
- Username: Gornoth
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Mar 25, 2012 10:43 am
- Post datetime: 2012-05-07T15:41:20+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Here is a dll that decompresses the guild wars 2 .dat.
It was created by Loumie at gamerevision.

> Hey,
>
> 
>
> So, here is a dll, with the sources, which contain a simple function "inflate" (in gw2Inflate.h) that decompresses a file.
>
> I'm using codeblocks/GCC because the C compiler of VS is not even compliant with C99 (unless I missed something).
>
> 
>
> It successfully decompresses the files of the last version with about 50~ fails out of 187919 files. These fails seems to happen at the end of the decoding, usually the last bytes in the files, I don't have time to look at it right now though.
>
> 
>
> Feel free to point at eventual mistakes, I'm more a C++ programmer than a pure C one ;D.
>
> 
>
> Cheers.
[gw2Inflate.zip](https://xentaxbackup.github.io/file/5402_gw2Inflate.zip)
## Post #113
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-05-07T16:37:43+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Dolkar
>
> What about sniffing out the location of in-game files and downloading them uncompressed without using the official downloader? That might be much easier than unpacking them from the .dat file.

The first thing that is probably getting downloaded is the list of the files and their locations (possibly even names?). I'll try to sniff that one out when I have some time. Or has anyone already successfully done that?

That is kinda what we have been doing all along. THere is no way atm to find the real file-name. At least we haven't found any correlation tables. But if we need specific files, we find their number, and download them.

Another thing is, GW2DatBrowser works, stuff can be extracted with that.


> Reply from Gornoth
>
> Here is a dll that decompresses the guild wars 2 .dat.
It was created by Loumie at gamerevision.
Hey,

So, here is a dll, with the sources, which contain a simple function "inflate" (in gw2Inflate.h) that decompresses a file.
I'm using codeblocks/GCC because the C compiler of VS is not even compliant with C99 (unless I missed something).

It successfully decompresses the files of the last version with about 50~ fails out of 187919 files. These fails seems to happen at the end of the decoding, usually the last bytes in the files, I don't have time to look at it right now though.

Feel free to point at eventual mistakes, I'm more a C++ programmer than a pure C one ;D.

Cheers.

Thank you for reposting this. I was trying to find it for a while after I missed it.
## Post #114
- Username: Neoryudo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Mar 28, 2010 12:32 am
- Post datetime: 2012-05-07T16:53:14+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

been trying to use the GW2datbroswer, but am finding it crashes every time at 78%, anyone else finding this?
## Post #115
- Username: Loumie
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 12, 2012 3:00 pm
- Post datetime: 2012-05-07T17:11:31+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Yeah, I edited out the link on gamerevision when I got fed up to only receive PMs from people wanting a full extractor program.
Anyway, I would have given it to you if you had asked me Nimba, you've shared plenty enough ;D

Cheers.
## Post #116
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-05-08T01:13:59+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Loumie
>
> Yeah, I edited out the link on gamerevision when I got fed up to only receive PMs from people wanting a full extractor program.
Anyway, I would have given it to you if you had asked me Nimba, you've shared plenty enough ;D

Cheers.

I got it from someone else that got it, but I did message you on GameRevision for the DLL (I am Daegalus there) but its cool  No harm and I understand the reason. But the DLL works great.
## Post #117
- Username: xtridence
- Rank: n00b
- Number of posts: 11
- Joined date: Tue May 08, 2012 3:58 pm
- Post datetime: 2012-05-08T08:10:22+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Thanks Loumie for providing the decompression algorithm. It works well with GWUnpacker (with few minor adjustments to make it C++ compatible). 

Changelog:
v0: Nimba's [modified GWUnpacker](http://forum.xentax.com/viewtopic.php?p=69984#p69984)
v1: Ported Loumie's decompression algorithm to GWUnpacker
v2: Implemented ral's suggestions with regards to sorting certain files types.
v3: Some minor bugfixes related to ATEP files
v4: Added support for "newer" versions of dat files
[GW2Unpackerv4.zip](https://xentaxbackup.github.io/file/5426_GW2Unpackerv4.zip)
## Post #118
- Username: ral
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 24, 2012 12:26 am
- Post datetime: 2012-05-08T10:09:29+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Thank you 

And to sort the files a bit more and to have some less .raw files just add the following switch/case in the GWUnpacker.cpp from xtridence.
Hope the PF one is not a mess from programming style but I'm not a c++ developer and it works like that so I didn't care about it. 

Add this one to case 'XETA':

```
	CreateDirectory("GWDat/ATEX/3DCX",NULL);
	printf(" 3DCX");
	sprintf(newname,"GWDat/ATEX/3DCX/%s.atex\0",Name);
	break;

```


And the rest in the switch (i):

```
	CreateDirectory("GWDat/ATEU",NULL);
	printf(" ATEU");
	switch (k)
	{
	case '1TXD':
		CreateDirectory("GWDat/ATEU/DXT1",NULL);
		printf(" DXT1");
		sprintf(newname,"GWDat/ATEU/DXT1/%s.ateu\0",Name);
		break;
	case '2TXD':
		CreateDirectory("GWDat/ATEU/DXT2",NULL);
		printf(" DXT2");
		sprintf(newname,"GWDat/ATEU/DXT2/%s.ateu\0",Name);
		break;
	case '3TXD':
		CreateDirectory("GWDat/ATEU/DXT3",NULL);
		printf(" DXT3");
		sprintf(newname,"GWDat/ATEU/DXT3/%s.ateu\0",Name);
		break;
	break;
	case '5TXD':
		CreateDirectory("GWDat/ATEU/DXT5",NULL);
		printf(" DXT5");
		sprintf(newname,"GWDat/ATEU/DXT5/%s.ateu\0",Name);
		break;
	break;
	case 'LTXD':
		CreateDirectory("GWDat/ATEU/DXTL",NULL);
		printf(" DXTL");
		sprintf(newname,"GWDat/ATEU/DXTL/%s.ateu\0",Name);
		break;
	}
	break;
case 'PETA':
	CreateDirectory("GWDat/ATEP",NULL);
	printf(" ATEP");
	switch (k)
	{
	case '1TXD':
		CreateDirectory("GWDat/ATEP/DXT1",NULL);
		printf(" DXT1");
		sprintf(newname,"GWDat/ATEP/DXT1/%s.atep\0",Name);
		break;
	case '5TXD':
		CreateDirectory("GWDat/ATEP/DXT5",NULL);
		printf(" DXT5");
		sprintf(newname,"GWDat/ATEP/DXT5/%s.atep\0",Name);
		break;
	}
	break;
case 'ffba':
	CreateDirectory("GWDat/abff",NULL);
	printf(" abff");
	sprintf(newname,"GWDat/abff/%s.abff\0",Name);
	break;
	// FP
case 83536:
	CreateDirectory("GWDat/PF",NULL);
	char type[9];
	for (int z=8; z<16;z++)
		type[z-8] = Output[z];
	type[8] = '\0';
	printf(" PF %s", type);
	char dirname[18];
	sprintf(dirname, "GWDat/PF/%s\0", type);
	if (strcmp("ABNKBKCK", type) == 0)
	{
		CreateDirectory(dirname, NULL);
		sprintf(newname,"GWDat/PF/%s/%s.mp3\0",type, Name);
	}
	else
	{
		CreateDirectory(dirname, NULL);
		sprintf(newname,"GWDat/PF/%s/%s.pf\0",type, Name);
	}
	break;
case 'dnsa':
	CreateDirectory("GWDat/asnd",NULL);
	printf(" asnd");
	sprintf(newname,"GWDat/asnd/%s.asnd\0",Name);
	break;
case 'srts':
	CreateDirectory("GWDat/strs",NULL);
	printf(" strs");
	sprintf(newname,"GWDat/strs/%s.strs\0",Name);
	break;

```


Hope I didn't miss any files. And I didn't know any of the files (except the audio because of the Xing Header) so I just gave them the names I saw in the header.

EDIT:// Edit was because I forgot making ATEP and ATEU dir :/ Sorry
## Post #119
- Username: xtridence
- Rank: n00b
- Number of posts: 11
- Joined date: Tue May 08, 2012 3:58 pm
- Post datetime: 2012-05-08T12:44:43+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

I've updated the unpacker to sort certain file types. Thank you ral for the suggestion.
## Post #120
- Username: ral
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 24, 2012 12:26 am
- Post datetime: 2012-05-08T13:44:15+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Thanks for adding.
Oh and the PF - ASNDASND has 2 different kind of audio files I just noticed.
Some with Xing Header and some with Ogg header.
This should work to identify the different filetypes:

```
{
	char oggOrNot[5];
	for (int z=92; z<96;z++)
		oggOrNot[z-92] = Output[z];
	oggOrNot[4] = '\0';
	CreateDirectory(dirname, NULL);
	if (strcmp(oggOrNot, "OggS") == 0)
		sprintf(newname,"GWDat/PF/%s/%s.ogg\0",type, Name);
	else
		sprintf(newname,"GWDat/PF/%s/%s.mp3\0",type, Name);
}

```


And I'm sorry, in my code above I forgot the CreateDirectory for ATEP and ATEU so you won't get the files if the dir doesn't exist :/
## Post #121
- Username: polarbearsrawr
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Mar 31, 2012 5:01 am
- Post datetime: 2012-05-08T15:32:40+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

I don't suppose you remember the parameters for the atexreader for converting the atex files to be open-able in say photoshop or xnview, currently does nothing when I try feeding it the any of the following:
atexreader *.atex *
atexreader * *
atexreader *.atex *.png
atexreader *.atex *.tga
atexreader [filenumber].atex *

Tested on the DXT1,DXT5, and 3DCX directories.
## Post #122
- Username: ral
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 24, 2012 12:26 am
- Post datetime: 2012-05-08T15:50:22+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

On page 3 you find a dl by Nimba of the GWUnpacker. That one containts the ATEXReader.exe.
I don't have the time to test it all at the moment. I know it doesn't always work and I can't tell you why but when you have the atexreader in the same dir as the .atex files and you open cmd and go to the dir. Then it should work when you type:
atexreader 00000116.atex

atexreader *.atex works too to get all files

When you are let's say in cmd at c:\ and use a command like
c:\gw2\atexreader\atexreader c:\gw2\GWDat\ATEX\DXT1\00000116.atex
then it doesn't work.´

// 
And .abff and .asnd are audio files too
## Post #123
- Username: Dolkar
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon May 07, 2012 11:13 pm
- Post datetime: 2012-05-08T17:55:13+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

I'm just wondering where does the game get IDs of files it needs to download. The only file it downloads prior to the actual game files contains these 5 numbers:

```
14120 200012 21623832 199991 2428
```

However, the first file downloaded is 13361. I could only identify the largest number, which seems to be the size of the executable in bytes.
Those IDs are not hard-coded to the executable, either. It might be a hash, but generated from what? Any ideas?
## Post #124
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-05-08T18:03:13+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Dolkar
>
> I'm just wondering where does the game get IDs of files it needs to download. The only file it downloads prior to the actual game files contains these 5 numbers:
Code: Select all14120 200012 21623832 199991 2428
However, the first file downloaded is 13361. I could only identify the largest number, which seems to be the size of the executable in bytes.
Those IDs are not hard-coded to the executable, either. It might be a hash, but generated from what? Any ideas?

well thats build, exe, exesize, someManifest, manifestSize

then it takes teh build number and uses it against

/manifest/program/102/build# to get the file manifest for that build.

This was all on the 6th or 7th post in this thread.


> Reply from Nimba
>
> So this is what I have found so far that could help:

/latest/102 : has the latest build # (ex. returns: 13525 2312313 12313123 ...) the first number is the build number.
/manifest/program/102/{build#} : manifest file for build number (ex. 13525, 13603)
/program/102/0/0/{fileNumber}/ : the actual data file uncompressed (ex. 844474 - MP3 File of a Roar)
/program/102/0/0/{fileNumber}/compressed : the actual data file compressed (have not investigated the compression used)

The Manifest File:

It is a list of UInt32 in Little Endian order. once converted to decimals, they are the fileNumber used in the above links. They do not have filenames, the number is the filename.
The Cookie information, and the CDN address is in the GW2Dev.exe file, should not be hard to find for those that are working on it.

Also, randomly (well seems random to me) there are numbers in the Manifest files that are not Files. They are the size in bytes of the previous file downloaded.

Example:
1814180 - 345208 bytes
2519389 - 345036 bytes
345036
2054826 - 72964 bytes
2948595 - 104384 bytes
104384
## Post #125
- Username: Dolkar
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon May 07, 2012 11:13 pm
- Post datetime: 2012-05-08T18:14:10+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Oh, thanks! I must have missed that one...

It just bugs me why I couldn't see the manifest file being downloaded...

EDIT: The format of /manifest/program/101/14120 file seems to be different though:

unknown 4 bytes, probably CRC
after that, every 12 bytes: fileID (4 bytes), fileID (4 bytes), size(4 bytes)
## Post #126
- Username: Loumie
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 12, 2012 3:00 pm
- Post datetime: 2012-05-08T19:32:38+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Hey,

Soooo.. I thought that having a wiki to share the different file structures / encryptions / etc... would be a good idea, because it seems that a lot of people are just working on their own and everybody could benefit from shared experience. (The goal would be to centralize all infos on the DAT file, game data/sounds/textures/maps/etc...)
But with new Xentax "rules of conducts" and some encryption/file formats that are sensitive to release publicly w.r.t. ArenaNet, I think that a private wiki would be more appropriate than the Xentax one, unless Xentax could create a private one ? (It is ok for general files, but going into details on game data/disassembly is I think sensitive). I know that there is a private section on GameRevision, but they are a botting site, it's not really related to DAT RE.

So I created one where I started to fill out infos of what I currently know (this is on-going), so, everyone that thinks can contribute in any way and actually wants to share some infos with others can ask me for the URL/rights details!

Lastly, I'm sorry but people who can't program or can't come up with an idea to contribute I don't see the point of giving them access. But don't worry, with this kind of stuff I'm pretty sure that tools will be available a lot faster for you to play with ;D

Anyways,
Cheers !
## Post #127
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2012-05-09T05:17:39+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

mind pming me the info? ill def help out where i can
## Post #128
- Username: xtridence
- Rank: n00b
- Number of posts: 11
- Joined date: Tue May 08, 2012 3:58 pm
- Post datetime: 2012-05-10T01:31:41+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Updated [unpacker](http://forum.xentax.com/viewtopic.php?p=72880#p72880) so that it might be able to work with certain dat files.

Modified ATEXreader so that it can work with ATEP and ATEU files. Apparently they are the same as ATEX.

Note: ATEXreader does not support DXTA (yet).

Changelog:
v1: Support for ATEP files
v2: Support for ATEU files
v3: Support for 3DCX format
[ATEXreader_v3.zip](https://xentaxbackup.github.io/file/5429_ATEXreader_v3.zip)
## Post #129
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-05-10T17:44:29+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

[https://bitbucket.org/Daegalus/gw2re/overview](https://bitbucket.org/Daegalus/gw2re/overview)

I have setup a bitbucket for all the devs working on RE to share their source through that. We are releasing open source packages as it is. It would be nice to have everything in one place so that we can increase the speed to better tools.

So xtridence, if you wish, submit your code to the repo. If you want, just the ATEX reader. I can add you directly as a contributer so you can commit directly, or you can do the pull request method. If you wish, you can add your changes to existing products.

If you don't want to interfere with anyone, make a copy of their project, and make changes to it under a modified folder name.

As for others, this is for developers and its only source code, you won't be able to download binaries.
## Post #130
- Username: Gornoth
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Mar 25, 2012 10:43 am
- Post datetime: 2012-05-11T05:00:59+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Nimba
>
> https://bitbucket.org/Daegalus/gw2re/overview

I have setup a bitbucket for all the devs working on RE to share their source through that. We are releasing open source packages as it is. It would be nice to have everything in one place so that we can increase the speed to better tools.

So xtridence, if you wish, submit your code to the repo. If you want, just the ATEX reader. I can add you directly as a contributer so you can commit directly, or you can do the pull request method. If you wish, you can add your changes to existing products.

If you don't want to interfere with anyone, make a copy of their project, and make changes to it under a modified folder name.

As for others, this is for developers and its only source code, you won't be able to download binaries.

Thank you for your work on this. The Gw2DatUnpacker works great!
## Post #131
- Username: Cruelbob
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed May 16, 2012 10:27 am
- Post datetime: 2012-05-16T04:41:02+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Knows anyone what is format that used for string files?
## Post #132
- Username: Rhoot
- Rank: beginner
- Number of posts: 26
- Joined date: Sat May 05, 2012 6:01 am
- Post datetime: 2012-05-16T05:41:37+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Gornoth
>
> Thank you for your work on this. The Gw2DatUnpacker works great!
Glad you like it! 

Edit: I updated it yesterday btw, so if it crashed for you before, it should no longer do that. Instead it should just skip the files it could not read.
## Post #133
- Username: Rhoot
- Rank: beginner
- Number of posts: 26
- Joined date: Sat May 05, 2012 6:01 am
- Post datetime: 2012-05-16T05:58:18+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from xtridence
>
> Modified ATEXreader so that it can work with ATEP and ATEU files. Apparently they are the same as ATEX.
In the exe, it checks for a couple more FourCC codes for textures. They're don't seem to be in use yet, but they're likely to be at some point. For instance, they changed most of the UI textures from ATEX to ATEU, between the build before the BWE and the BWE build.

In the current build they're in the function located at 0x701900. All of them are: ATEX, ATTX, ATEC, ATEP, ATEU, ATET.

Edit: Are you sure the channels in the 3DC files are correct and don't need to be moved around/inverted? It's *very* rare for [0,0.5,0.5] to be used for flat surfaces. Usually it's [0.5,0.5,1] or rarely [0.5,1,0.5].

Edit 2: I would guess the swapping of red/blue that happens after the switch should not happen for 3DC textures, and that their neutral state is [0.5,0.5,0]. It would make a whole lot more sense than [0,0.5,0.5] (unless they use the X-axis as the vertical axis and negative X means up). Personally, to get them usable to me, I changed it to not swap red and blue, and instead I swap red and green, and invert red and blue (after the swap). This makes it work like it should in the engine I'm currently trying out things in. For some textures I seem to have to invert green as well so it might be that all of them are inverted. I'll have to check with more textures to see which one is more usual.

Edit 3: You definitely need to add 'free(img)' in the if-case for FourCC and the if-case for compression format, before the returns. And also in the default case in the switch (together with free(output)). Doing ATexReader *.atex in a folder with 19k files made me run out of memory quite fast due to the DXTA files.
## Post #134
- Username: xtridence
- Rank: n00b
- Number of posts: 11
- Joined date: Tue May 08, 2012 3:58 pm
- Post datetime: 2012-05-16T15:35:29+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Thanks for spotting those bugs. I was wondering why the 3DC colors seems a little off (it's because the RGBA struct seemed to have swapped the red and blue for some reason). 

I've implemented all of your suggestions (except for the part on compression because there was no buffer to free before the return statement).

(I've put this build in a separate post just in case I broke the tool when I did some adjustments.)

Changelog
v4: 3DC bugfix, plugged a few memory leaks
v5: Bugfixes
[ATEXreader_v5.zip](https://xentaxbackup.github.io/file/5441_ATEXreader_v5.zip)
## Post #135
- Username: Rhoot
- Rank: beginner
- Number of posts: 26
- Joined date: Sat May 05, 2012 6:01 am
- Post datetime: 2012-05-16T17:17:42+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

You now have another bug on your hands instead. You cannot do 'delete[]' on a variable that was allocated with 'malloc'. Malloc'ed chunks of memory need to be freed using free(). I'm looking at the 'delete[] img' you added.
## Post #136
- Username: xtridence
- Rank: n00b
- Number of posts: 11
- Joined date: Tue May 08, 2012 3:58 pm
- Post datetime: 2012-05-17T02:03:38+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Rhoot
>
> You now have another bug on your hands instead. You cannot do 'delete[]' on a variable that was allocated with 'malloc'. Malloc'ed chunks of memory need to be freed using free(). I'm looking at the 'delete[] img' you added.

Fixed. 
Used new instead of malloc.
## Post #137
- Username: Nimba
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Mar 08, 2012 3:32 am
- Post datetime: 2012-05-18T04:21:34+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

xtridence: Is it ok with you if I commit your atexreader sources to the Bitbucket repo? I'll keep it up-to-date for you if you want whenever you release a new version.
## Post #138
- Username: jeckerson
- Rank: n00b
- Number of posts: 10
- Joined date: Sat May 19, 2012 12:00 am
- Post datetime: 2012-05-18T17:32:06+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Any one know in what format .strs files are: xml, txt or some DB type? And if there are some strs parser that convert to another viewable formats?
## Post #139
- Username: stalja
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Sep 12, 2009 6:33 pm
- Post datetime: 2012-05-18T17:48:50+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Everyone is asking about strs files. I did some research of my own on the subject. The format seems to very similar, if not the same, to Guild Wars 1 strs files format. For now I have determined that plain text strings have a 6 byte header that tell the length and the type of the string. But there are some strange parts of the strs files that I was not able to decipher. In an old thread here on xentax it is suggested that these strings are encoded/compressed, but I cano not determine the compression method used. It does not look like zlib but I might be wrong because my RE skills are very novice. I did try poking around the exe to find the function that opens strs files and manipulates them and from what I was able to gather that there is one point in the exe file where this is done (00A767E5) but this is as far as my RE skills go right now.

Still, even if we decipher all of this (which I am sure is a piece of cake for some experienced RE) it remains to be determined how are these strings connected to items, icons, rewards and all that other good stuff that makes up a MMO game.
## Post #140
- Username: jeckerson
- Rank: n00b
- Number of posts: 10
- Joined date: Sat May 19, 2012 12:00 am
- Post datetime: 2012-05-18T18:01:05+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

It seems that in strs only INT data is encoded, or maybe some link variables to another files, because I can easily read names and descriptions of items/skills.

> It does not look like zlib but I might be wrong because my RE skills are very novice.

And how about Huffman coding?
## Post #141
- Username: kthackeray
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Mar 28, 2012 2:36 am
- Post datetime: 2012-05-18T20:40:06+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

They use the same format as GW1 with the addition of the header. Strings are referenced in structs and packet via an ID number. Each string has a 6 byte header including the size and enc info. Non UTF strings in GW1 are RC4 encrypted (with every string having a unique key) so I assume they are using the same here.
## Post #142
- Username: lordsavyj
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 16, 2012 12:25 pm
- Post datetime: 2012-05-19T00:23:37+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Yeah, what they said...it's almost identical to gw.dat format ([http://www.guildwiki.org/User:Dr_ishmael/Gw.dat](http://www.guildwiki.org/User:Dr_ishmael/Gw.dat)).

I built a proof of concept in PHP ([http://dev.kantanker.us/lab/](http://dev.kantanker.us/lab/)) and you can see my code at ([http://dev.kantanker.us/lab/code.php](http://dev.kantanker.us/lab/code.php)).

Update: Code updated to better display strings
## Post #143
- Username: xtridence
- Rank: n00b
- Number of posts: 11
- Joined date: Tue May 08, 2012 3:58 pm
- Post datetime: 2012-05-19T09:58:08+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Here's a STRS reader (I did not release it earlier as the format is not fully understood yet). The format for encrypted strings is unknown.

The dump button is to combine all STRS files (in a directory) and output into a single file so that strings can be searched easily.

@Nimba: You can commit the stuff to a repository if you want. Please include the compiled files in the repository.
[STRSViewer.zip](https://xentaxbackup.github.io/file/5444_STRSViewer.zip)
## Post #144
- Username: Cruelbob
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed May 16, 2012 10:27 am
- Post datetime: 2012-05-19T10:26:24+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

I have scanned Gw2.exe for cryptographic primitives.
[gw2.png](https://xentaxbackup.github.io/file/5446_gw2.png)
## Post #145
- Username: jeckerson
- Rank: n00b
- Number of posts: 10
- Joined date: Sat May 19, 2012 12:00 am
- Post datetime: 2012-05-19T11:40:35+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from xtridence
>
> Here's a STRS reader (I did not release it earlier as the format is not fully understood yet). The format for encrypted strings is unknown.

The dump button is to combine all STRS files (in a directory) and output into a single file so that strings can be searched easily.

@Nimba: You can commit the stuff to a repository if you want. Please include the compiled files in the repository.

Could you explain me please meaning of Ichar and type fields?
## Post #146
- Username: ral
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 24, 2012 12:26 am
- Post datetime: 2012-05-19T14:31:52+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Thank you guys.

I don't know if anyone looked closer at the files in PF/ABNKBKCK already (which currently are .mp3 files). I just started looking at them.
They always start with 496 bytes (PF ABNKBKCK).
After that there are more Headers in the file. So far i only saw PF ASNDASND (mp3 files with Xing header) and PF MODLMODL (If there are more i'll edit it in later once my unpacker is done with everything).
If you want all files just cut the .mp3 files at every new PF Header (start with 50 46 01 00 00 00 0C 00).

The ASNDASND Header is 92 bytes.
After that one there is a MPEG Audio Header + XING Header. 
I don't know much about audio files but I think there's nothing more than the audio after the headers.

Last but not least the update for those who want to update their unpacker to seperate the .strs files into german, english, french and korean Directories: (If 2nd last byte really == the language. There seem to be a lot of stuff that isn't translated if it's true)

```
	textcount++;
	CreateDirectory("GWDat/strs",NULL);
	// looking for the language
	switch (Output[OutSize-2])
	{
	case 0:
		printf("english strs");
		CreateDirectory("GWDat/strs/english",NULL);
		sprintf(newname,"GWDat/strs/english/%s.strs\0",Name);
		break;
	case 1:
		printf("korean strs");
		CreateDirectory("GWDat/strs/korean",NULL);
		sprintf(newname,"GWDat/strs/korean/%s.strs\0",Name);
		break;
	case 2:
		printf("french strs");
		CreateDirectory("GWDat/strs/french",NULL);
		sprintf(newname,"GWDat/strs/french/%s.strs\0",Name);
		break;
	case 3:
		printf("german strs");
		CreateDirectory("GWDat/strs/german",NULL);
		sprintf(newname,"GWDat/strs/german/%s.strs\0",Name);
		break;
	default:
		// other language
		printf("strs");
		sprintf(newname,"GWDat/strs/%s.strs\0",Name);
	}

```
## Post #147
- Username: xtridence
- Rank: n00b
- Number of posts: 11
- Joined date: Tue May 08, 2012 3:58 pm
- Post datetime: 2012-05-19T14:46:21+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

PF reader for those who want to delve into PF files. Note that the structure of the PF file is not completely understood yet (so the tool is not exactly that useful), however I hope that this tool might speed up some progress towards that.

@jeckerson: "lchar" refers to the character with the smallest ASCII value (assuming it followings GW specification). "type" = 16 means the text is UTF-16 (it is currently not known how to read the strings for other values).
[PFviewer.zip](https://xentaxbackup.github.io/file/5449_PFviewer.zip)
## Post #148
- Username: kthackeray
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Mar 28, 2012 2:36 am
- Post datetime: 2012-05-19T15:34:57+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from xtridence
>
> Here's a STRS reader (I did not release it earlier as the format is not fully understood yet). The format for encrypted strings is unknown.

> Reply from xtridence
>
> "type" = 16 means the text is UTF-16 (it is currently not known how to read the strings for other values).

> Reply from kthackeray
>
> Non UTF strings in GW1 are RC4 encrypted (with every string having a unique key) so I assume they are using the same here.

In order to read them you need the key from the server...
## Post #149
- Username: jeckerson
- Rank: n00b
- Number of posts: 10
- Joined date: Sat May 19, 2012 12:00 am
- Post datetime: 2012-05-19T15:37:32+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from kthackeray
>
> In order to read them you need the key from the server...
If there are some way to brute-force that keys or read packets while playing?
## Post #150
- Username: kthackeray
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Mar 28, 2012 2:36 am
- Post datetime: 2012-05-19T15:55:11+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from jeckerson
>
> If there are some way to brute-force that keys or read packets while playing?

You have to get them from analyzing server packets, yes. The GW1 algorithm has already been cracked and so far there is no evidence to show that they are using something different here. I'm not sure why you would want to waste the time to brute force them just for some text. Imagine how long it would take to do so for ~198,000 strings each with a unique key.
## Post #151
- Username: jeckerson
- Rank: n00b
- Number of posts: 10
- Joined date: Sat May 19, 2012 12:00 am
- Post datetime: 2012-05-19T16:05:53+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from kthackeray
>
> jeckerson wrote:If there are some way to brute-force that keys or read packets while playing?

You have to get them from analyzing server packets, yes. The GW1 algorithm has already been cracked and so far there is no evidence to show that they are using something different here. I'm not sure why you would want to waste the time to brute force them just for some text. Imagine how long it would take to do so for ~198,000 strings each with a unique key.

Thank you for answer. I just need to know all info in strs files, which have information about items, skills, quests as I think so. But damn, what kind of structure data they have there which read and show in da game...
## Post #152
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-05-19T16:09:48+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Cruelbob
>
> I have scanned Gw2.exe for cryptographic primitives.
Very old and not actually scanner  here better [Signsrch 0.1.7](http://aluigi.altervista.org/mytoolz/signsrch.zip)
## Post #153
- Username: Cruelbob
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed May 16, 2012 10:27 am
- Post datetime: 2012-05-19T16:24:48+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

I think that i have found SendPacket function:


```
Address   Hex dump          Command                                          Comments
009FDDA0  /$  55            PUSH EBP                                         ; Gw2.009FDDA0(guessed Arg1)
009FDDA1  |.  8BEC          MOV EBP,ESP
009FDDA3  |.  83EC 28       SUB ESP,28
009FDDA6  |.  53            PUSH EBX
009FDDA7  |.  56            PUSH ESI
009FDDA8  |.  57            PUSH EDI
009FDDA9  |.  8BF9          MOV EDI,ECX
009FDDAB  |.  8BF2          MOV ESI,EDX
009FDDAD  |.  8975 F8       MOV DWORD PTR SS:[LOCAL.2],ESI
009FDDB0  |.  85FF          TEST EDI,EDI
009FDDB2  |.  75 14         JNE SHORT 009FDDC8
009FDDB4  |.  68 6F0E0000   PUSH 0E6F                                        ; /Arg1 = 0E6F
009FDDB9  |.  BA D4D32F01   MOV EDX,OFFSET 012FD3D4                          ; |ASCII "..\..\..\Services\Msg\MsgConn.cpp"
009FDDBE  |.  B9 64D92F01   MOV ECX,OFFSET 012FD964                          ; |ASCII "mc"
009FDDC3  |.  E8 1842C1FF   CALL 00611FE0                                    ; \Gw2.00611FE0
009FDDC8  |>  8B5D 08       MOV EBX,DWORD PTR SS:[ARG.1]
009FDDCB  |.  85DB          TEST EBX,EBX
009FDDCD  |.  75 14         JNE SHORT 009FDDE3
009FDDCF  |.  68 700E0000   PUSH 0E70                                        ; /Arg1 = 0E70
009FDDD4  |.  BA D4D32F01   MOV EDX,OFFSET 012FD3D4                          ; |ASCII "..\..\..\Services\Msg\MsgConn.cpp"
009FDDD9  |.  B9 083D2D01   MOV ECX,OFFSET 012D3D08                          ; |ASCII "rawData"
009FDDDE  |.  E8 FD41C1FF   CALL 00611FE0                                    ; \Gw2.00611FE0
009FDDE3  |>  83FE 02       CMP ESI,2
009FDDE6  |.  73 14         JNB SHORT 009FDDFC
009FDDE8  |.  68 710E0000   PUSH 0E71                                        ; /Arg1 = 0E71
009FDDED  |.  BA D4D32F01   MOV EDX,OFFSET 012FD3D4                          ; |ASCII "..\..\..\Services\Msg\MsgConn.cpp"
009FDDF2  |.  B9 D0D92F01   MOV ECX,OFFSET 012FD9D0                          ; |ASCII "rawDataBytes >= sizeof(word)"
009FDDF7  |.  E8 E441C1FF   CALL 00611FE0                                    ; \Gw2.00611FE0
009FDDFC  |>  83BF A8000000 CMP DWORD PTR DS:[EDI+0A8],2
009FDE03  |.  0F85 4A010000 JNE 009FDF53
009FDE09  |.  837F 7C 00    CMP DWORD PTR DS:[EDI+7C],0
009FDE0D  |.  0F84 40010000 JE 009FDF53
009FDE13  |.  0FB713        MOVZX EDX,WORD PTR DS:[EBX]
009FDE16  |.  8B4F 0C       MOV ECX,DWORD PTR DS:[EDI+0C]
009FDE19  |.  8955 F0       MOV DWORD PTR SS:[LOCAL.4],EDX
009FDE1C  |.  E8 3F0F0000   CALL 009FED60
009FDE21  |.  8BF0          MOV ESI,EAX
009FDE23  |.  85F6          TEST ESI,ESI
009FDE25  |.  75 14         JNE SHORT 009FDE3B
009FDE27  |.  68 7F0E0000   PUSH 0E7F                                        ; /Arg1 = 0E7F
009FDE2C  |.  BA D4D32F01   MOV EDX,OFFSET 012FD3D4                          ; |ASCII "..\..\..\Services\Msg\MsgConn.cpp"
009FDE31  |.  B9 C8D92F01   MOV ECX,OFFSET 012FD9C8                          ; |ASCII "sendMsg"
009FDE36  |.  E8 A541C1FF   CALL 00611FE0                                    ; \Gw2.00611FE0
009FDE3B  |>  8B06          MOV EAX,DWORD PTR DS:[ESI]
009FDE3D  |.  8378 10 00    CMP DWORD PTR DS:[EAX+10],0
009FDE41  |.  75 14         JNE SHORT 009FDE57
009FDE43  |.  68 800E0000   PUSH 0E80                                        ; /Arg1 = 0E80
009FDE48  |.  BA D4D32F01   MOV EDX,OFFSET 012FD3D4                          ; |ASCII "..\..\..\Services\Msg\MsgConn.cpp"
009FDE4D  |.  B9 A8D92F01   MOV ECX,OFFSET 012FD9A8                          ; |ASCII "sendMsg->defArray[0].defSize"
009FDE52  |.  E8 8941C1FF   CALL 00611FE0                                    ; \Gw2.00611FE0
009FDE57  |>  8B0E          MOV ECX,DWORD PTR DS:[ESI]
009FDE59  |.  8B55 F8       MOV EDX,DWORD PTR SS:[LOCAL.2]
009FDE5C  |.  3B51 10       CMP EDX,DWORD PTR DS:[ECX+10]
009FDE5F  |.  74 14         JE SHORT 009FDE75
009FDE61  |.  68 840E0000   PUSH 0E84                                        ; /Arg1 = 0E84
009FDE66  |.  BA D4D32F01   MOV EDX,OFFSET 012FD3D4                          ; |ASCII "..\..\..\Services\Msg\MsgConn.cpp"
009FDE6B  |.  B9 78D92F01   MOV ECX,OFFSET 012FD978                          ; |ASCII "rawDataBytes == sendMsg->defArray[0].defSize"
009FDE70  |.  E8 6B41C1FF   CALL 00611FE0                                    ; \Gw2.00611FE0
009FDE75  |>  8D4D 08       LEA ECX,[ARG.1]
009FDE78  |.  51            PUSH ECX                                         ; /Arg6 => OFFSET ARG.1
009FDE79  |.  8B4D F8       MOV ECX,DWORD PTR SS:[LOCAL.2]                   ; |
009FDE7C  |.  8D55 FC       LEA EDX,[LOCAL.1]                                ; |
009FDE7F  |.  52            PUSH EDX                                         ; |Arg5 => OFFSET LOCAL.1
009FDE80  |.  03CB          ADD ECX,EBX                                      ; |
009FDE82  |.  51            PUSH ECX                                         ; |Arg4
009FDE83  |.  8D55 F4       LEA EDX,[LOCAL.3]                                ; |
009FDE86  |.  52            PUSH EDX                                         ; |Arg3 => OFFSET LOCAL.3
009FDE87  |.  33C0          XOR EAX,EAX                                      ; |
009FDE89  |.  50            PUSH EAX                                         ; |Arg2 => 0
009FDE8A  |.  8945 FC       MOV DWORD PTR SS:[LOCAL.1],EAX                   ; |
009FDE8D  |.  8B16          MOV EDX,DWORD PTR DS:[ESI]                       ; |
009FDE8F  |.  57            PUSH EDI                                         ; |Arg1
009FDE90  |.  8D4D D8       LEA ECX,[LOCAL.10]                               ; |
009FDE93  |.  895D F4       MOV DWORD PTR SS:[LOCAL.3],EBX                   ; |
009FDE96  |.  C745 08 FFFFF MOV DWORD PTR SS:[ARG.1],-1                      ; |
009FDE9D  |.  E8 0EE7FFFF   CALL 009FC5B0                                    ; \Gw2.009FC5B0
009FDEA2  |.  837D EC 00    CMP DWORD PTR SS:[LOCAL.5],0
009FDEA6  |.  75 14         JNE SHORT 009FDEBC
009FDEA8  |.  68 920E0000   PUSH 0E92                                        ; /Arg1 = 0E92
009FDEAD  |.  BA D4D32F01   MOV EDX,OFFSET 012FD3D4                          ; |ASCII "..\..\..\Services\Msg\MsgConn.cpp"
009FDEB2  |.  B9 68D92F01   MOV ECX,OFFSET 012FD968                          ; |ASCII "err.IsSuccess()"
009FDEB7  |.  E8 2441C1FF   CALL 00611FE0                                    ; \Gw2.00611FE0
009FDEBC  |>  8B5D F0       MOV EBX,DWORD PTR SS:[LOCAL.4]
009FDEBF  |.  8B55 FC       MOV EDX,DWORD PTR SS:[LOCAL.1]
009FDEC2  |.  8BCB          MOV ECX,EBX
009FDEC4  |.  E8 E71F0000   CALL 009FFEB0
009FDEC9  |.  8B77 18       MOV ESI,DWORD PTR DS:[EDI+18]
009FDECC  |.  85F6          TEST ESI,ESI
009FDECE  |.  74 55         JE SHORT 009FDF25
009FDED0  |.  813E DDDDDDDD CMP DWORD PTR DS:[ESI],DDDDDDDD
009FDED6  |.  75 14         JNE SHORT 009FDEEC
009FDED8  |.  68 73010000   PUSH 173                                         ; /Arg1 = 173
009FDEDD  |.  BA 982D1001   MOV EDX,OFFSET 01102D98                          ; |ASCII "p:\code\arena\core\Collections/List.h"
009FDEE2  |.  B9 F02E1001   MOV ECX,OFFSET 01102EF0                          ; |ASCII "m_linkOffset != static_cast<int>(LINK_OFFSET_UNINIT)"
009FDEE7  |.  E8 F440C1FF   CALL 00611FE0                                    ; \Gw2.00611FE0
009FDEEC  |>  8B06          MOV EAX,DWORD PTR DS:[ESI]
009FDEEE  |.  8B4C38 04     MOV ECX,DWORD PTR DS:[EDI+EAX+4]
009FDEF2  |.  8B1438        MOV EDX,DWORD PTR DS:[EDI+EAX]
009FDEF5  |.  8B52 04       MOV EDX,DWORD PTR DS:[EDX+4]
009FDEF8  |.  03C7          ADD EAX,EDI
009FDEFA  |.  83E2 FE       AND EDX,FFFFFFFE
009FDEFD  |.  83E1 FE       AND ECX,FFFFFFFE
009FDF00  |.  2BCA          SUB ECX,EDX
009FDF02  |.  8B10          MOV EDX,DWORD PTR DS:[EAX]
009FDF04  |.  891401        MOV DWORD PTR DS:[EAX+ECX],EDX
009FDF07  |.  8B48 04       MOV ECX,DWORD PTR DS:[EAX+4]
009FDF0A  |.  8B10          MOV EDX,DWORD PTR DS:[EAX]
009FDF0C  |.  894A 04       MOV DWORD PTR DS:[EDX+4],ECX
009FDF0F  |.  8B4E 04       MOV ECX,DWORD PTR DS:[ESI+4]
009FDF12  |.  8908          MOV DWORD PTR DS:[EAX],ECX
009FDF14  |.  8B10          MOV EDX,DWORD PTR DS:[EAX]
009FDF16  |.  8B4A 04       MOV ECX,DWORD PTR DS:[EDX+4]
009FDF19  |.  8948 04       MOV DWORD PTR DS:[EAX+4],ECX
009FDF1C  |.  8B56 04       MOV EDX,DWORD PTR DS:[ESI+4]
009FDF1F  |.  897A 04       MOV DWORD PTR DS:[EDX+4],EDI
009FDF22  |.  8946 04       MOV DWORD PTR DS:[ESI+4],EAX
009FDF25  |>  833D BC4D6501 CMP DWORD PTR DS:[1654DBC],0
009FDF2C  |.  74 10         JE SHORT 009FDF3E
009FDF2E  |.  8D87 D4020000 LEA EAX,[EDI+2D4]
009FDF34  |.  3947 78       CMP DWORD PTR DS:[EDI+78],EAX
009FDF37  |.  74 05         JE SHORT 009FDF3E
009FDF39  |.  E8 52D2FFFF   CALL 009FB190                                    ; [Gw2.009FB190
009FDF3E  |>  8B4D 08       MOV ECX,DWORD PTR SS:[ARG.1]
009FDF41  |.  8B55 FC       MOV EDX,DWORD PTR SS:[LOCAL.1]
009FDF44  |.  8B47 08       MOV EAX,DWORD PTR DS:[EDI+8]
009FDF47  |.  51            PUSH ECX                                         ; /Arg4 => [ARG.1]
009FDF48  |.  52            PUSH EDX                                         ; |Arg3 => [LOCAL.1]
009FDF49  |.  53            PUSH EBX                                         ; |Arg2
009FDF4A  |.  50            PUSH EAX                                         ; |Arg1
009FDF4B  |.  E8 00BFC0FF   CALL 00609E50                                    ; \Gw2.00609E50
009FDF50  |.  83C4 10       ADD ESP,10
009FDF53  |>  5F            POP EDI
009FDF54  |.  5E            POP ESI
009FDF55  |.  5B            POP EBX
009FDF56  |.  8BE5          MOV ESP,EBP
009FDF58  |.  5D            POP EBP
009FDF59  \.  C2 0400       RETN 4


```
## Post #154
- Username: Loumie
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 12, 2012 3:00 pm
- Post datetime: 2012-05-19T20:29:45+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Multiple things here:

  - strs files: I can confirm that in GW2 they still use some kind of RC4 encryption on the encoded strings. What you call lchar is actually an offset used when outputting the string, (if value < 32 then tableLookup else offset+value-32) so by construction it is the lowest char. Finally the last value 0x10 in UTF-16 strings is the number of significant bits, it means than at each pass it reads X bits to decode a value. (I don't know about the value received from the server as I didn't look further)

  - Unpacker: Please take a look at the unpacker of Rhoot, it is quite good and will most likely suit your needs: [https://bitbucket.org/Daegalus/gw2re/src](https://bitbucket.org/Daegalus/gw2re/src)

  - crypt: On page 1 post 5 Ekey displayed the output of signsrch

Cheers,
Loumie
## Post #155
- Username: ral
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 24, 2012 12:26 am
- Post datetime: 2012-05-19T21:53:07+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

So here is what I know about PF/ABNKBKCK files:

```
16 bytes File Header (PF ABNKBKCK):
50 46 01 00  00 00 0C 00  41 42 4E 4B  42 4B 43 4B

40 bytes ABNKBKCK Header:
4 bytes (number of bytes in file - 20)
4 bytes (02 00 10 00)
4 bytes (number of bytes in file - 80)
16 bytes (always 0x00)
4 bytes (always 0A 00 00 00)
4 bytes (always 08 00 00 00)
4 bytes (always 0x00)

10 Entries with 44 bytes each entry (entries can be full 0x00) (440 bytes in total):
4 bytes (always counting up +1 in a file but I don't know how to find out what the start number is. Empty entry still counts the counter up)
4 bytes (always 01 00 00 00 or 00 00 00 00 but I don't know what it means)
16 bytes (always 0x00)
4 bytes (unknown)
4 bytes (unknown)
4 bytes (always 0x00)
4 bytes (bytes for the file. Always a ASNDASND (can include a MODLMODL after the ASNDASND I think))
4 bytes (unknown)

```

Rest of the file are the single ASNDASND and MODLMODL files.
## Post #156
- Username: xtridence
- Rank: n00b
- Number of posts: 11
- Joined date: Tue May 08, 2012 3:58 pm
- Post datetime: 2012-05-20T02:05:25+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

GW2Unpacker CLI is no longer actively developed. Please use the repository version (see rhoot's post following this post). 

Some general tips to compiling repository version:
* Install and compile wxwidgets 2.9.3+. Their recommendation is to compile using the VC9 solution file in the build directory via VS2008. You can use VS2010 to compile this as well.
* For an easier life, set the option for Runtime library to "Multi-threaded Debug" (Configuration properties, C/C++, Code Generation) for all Wxwidgets projects and the bitbucket project.
* Follow the instructions on the [wxWidgets wiki](http://wiki.wxwidgets.org/Microsoft_Visual_C%2B%2B_Guide) for editing several project properties if needed (don't forget to set environment variables for your computer and link the libraries to the project)
* If using VS2010 to compile the repository version (and VS2008 to compile wxwidgets), set platform toolset to use v90 instead of v100. If using VS2010 for both, ignore this step (both should be set to v100).
* Tweak where needed (May need to use stdint.h instead of cstdint, which can be obtained online. Replace nullptr with NULL if having problems with nullptr.)

As for PF files, they consist of a 12 byte header, followed by several blocks of data.

Each block/chunk has a format like this:

```
* 4 byte name
* 4 byte offset to next chunk
* 2 byte something
* 2 byte block header size
* 4 byte offset to a table (no table if this value is 0)

Data: Contains offsets to actual data, as well as the data itself
Table: Usually occurs after data.
* First 4 bytes is the number of entries in the table
* Each entry is an offset starting from the end of the header. It points to another offset that starts from that point.
```


ABNK can contain more than one PF file (usually ASND).
ASND can contain MP3 (which usually start with something like FF FB) or Ogg, as well as MODL PF file (it's a file within a file within a file within a file)
(The PFviewer can be used to extract these.)
## Post #157
- Username: Rhoot
- Rank: beginner
- Number of posts: 26
- Joined date: Sat May 05, 2012 6:01 am
- Post datetime: 2012-05-20T17:27:03+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

The bitbucket repository has moved, actually. The reason being that so far only me and Loumie have put anything in it, and of us two only I had a preference of DVCS client. Individual projects will (from now on) be pushed to it as submodules, so it's more of a listing of projects. It can still be cloned as one big repository if wanted though, but you'll have to do a recursive clone.

On top of this, I uploaded the browser I've been working on for a couple of weeks now. It acts as an extension of the unpacker. Scanning a .dat takes roughly 10 minutes but once that is done, every subsequent start the indexer should load the contents in about 5-10 seconds. Files can be exported if wanted, by right clicking on them in the tree. So far it only supports viewing power-of-two textures and binary data as hex. The reason it does not do non-power-of-two textures is cause they seem to have a different compression algorithm. Even with the ATexReader they turn out as garbage blocks.

Anyway, the new repository is located on github, at: [https://github.com/Daegalus/gw2re](https://github.com/Daegalus/gw2re)
The browser is located at: [https://github.com/rhoot/Gw2Browser](https://github.com/rhoot/Gw2Browser)

If you prefer binaries over source, there are binaries of the browser at [http://skold.cc/gw2browser/](http://skold.cc/gw2browser/)

Edit: 

> Reply from xtridence
>
> Some general tips to compiling bitbucket version (in the event you run into problems):
* Install and compile wxwidgets 2.9.3+. Best to compile using the VC9 solution file in the build directory via VS2008.
* For an easier life, set the option for Runtime library to "Multi-threaded Debug" (Configuration properties, C/C++, Code Generation) for all Wxwidgets projects and the bitbucket project.
* Follow the instructions on the wxWidgets wiki for editing several project properties (don't forget to set environment variables for your computer and link the libraries to the project)
* If using VS2010 to compile the BitBucket version (and VS2008 to compile wxwidgets), set platform toolset to use v90 instead of v100.
* Tweak where needed (May need to use stdint.h instead of cstdint, which can be obtained online. Replace nullptr with NULL if not compiling using /clr option. Read the readme file.)

The unpacker was actually written in VS2010. It was linked against a version of wxWidgets built in 2010 while developing as well, so there shouldn't be any need to go to 2008 unless you don't have 2010. Also, nullptr is actually [valid C++ starting with C++11](https://en.wikipedia.org/wiki/C%2B%2B11#Null_pointer_constant), and is supported by MSVC [starting with 2010](http://wiki.apache.org/stdcxx/C++0xCompilerSupport). That said, the unpacker doesn't use it anywhere, so I'm assuming this line applies to wxWidgets.

Edit 2: Fixed a bug in the browser that made it unable to save the index on computers where it had not saved an index before (a directory didn't exist for it). The binary linked to above has been replaced, so if you're having troubles, get a new one.
## Post #158
- Username: xtridence
- Rank: n00b
- Number of posts: 11
- Joined date: Tue May 08, 2012 3:58 pm
- Post datetime: 2012-05-21T00:40:39+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

My guide is intended for those who were having issues compiling the code, so I propose an alternative workaround. The best solution of course, is to simply use VS2010.

nullptr is supported in VS2010 (but there are caveats for VS2008 and lower).
## Post #159
- Username: Rhoot
- Rank: beginner
- Number of posts: 26
- Joined date: Sat May 05, 2012 6:01 am
- Post datetime: 2012-05-21T22:52:46+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

I just figured out the DXTA format, thanks to some data obtained by Loumie. It's really simple. Each block contains no color, but only an alpha channel, so 64 bits per block. The alpha is calculated in the exact same way it is for DXT5.

In order to get the decompression to work, it needs the image format 0x0A1. You can get that in the ATexReader by feeding 0x14 to the AtexDecompress function (though in GW2 it's really format 0x1a, since the format table was updated).

That's really all there is to it.
## Post #160
- Username: xtridence
- Rank: n00b
- Number of posts: 11
- Joined date: Tue May 08, 2012 3:58 pm
- Post datetime: 2012-05-22T00:52:02+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

So DXTA is similar to the BC4 format? I guess that could be arranged. 

Update: Here's the ATEX reader.
[ATEXreader_v6.zip](https://xentaxbackup.github.io/file/5456_ATEXreader_v6.zip)
## Post #161
- Username: Grax
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 23, 2012 8:32 pm
- Post datetime: 2012-05-23T18:30:27+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Can someone tell me, what those "Bank files" are?
Looks like mp3, but i couldn't figure out how to get a real .mp3 file out of it.

EDIT:
Ooh, got it
## Post #162
- Username: lordsavyj
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 16, 2012 12:25 pm
- Post datetime: 2012-05-24T16:32:26+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Has anyone, who is willing to share, discovered where to look for item details in the gw2.dat?  I'm specifically looking for recipe info.  I've been parsing the data...slowly...but with so many files a pointer would be much appreciated.
## Post #163
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2012-05-24T16:58:46+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

I'll say this, you arent just going to stumble upon the item/recipe/skill data. Anet did a good job making it very hard to access
## Post #164
- Username: stalja
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Sep 12, 2009 6:33 pm
- Post datetime: 2012-05-24T18:56:22+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

From what I gathered from old Guild Wars 1 Dat they found out that items are basically files with flags that determine that item;s name, stats and special characteristics. They are not ASCII, but binary files with a special structure holding IDs of stats and such. Which file of the ones extracted so far I do not now. Again, person with RE skills has probably figured it through reversing the .exe
## Post #165
- Username: kthackeray
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Mar 28, 2012 2:36 am
- Post datetime: 2012-05-24T21:09:10+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from stalja
>
> From what I gathered from old Guild Wars 1 Dat they found out that items are basically files with flags that determine that item;s name, stats and special characteristics. They are not ASCII, but binary files with a special structure holding IDs of stats and such. Which file of the ones extracted so far I do not now. Again, person with RE skills has probably figured it through reversing the .exe

Not sure what file you're talking about here, but in GW1 all item characteristics are sent by the server via an item packet. The dat doesn't contain anymore info than the name of the item and its icon. I assume GW2 is using a similar system, but time will tell.
## Post #166
- Username: lordsavyj
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 16, 2012 12:25 pm
- Post datetime: 2012-05-25T00:38:56+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

I'm parsing the binary files...not an easy thing...pretty sure I had a series of micro strokes the other night trying to pickup on this stuff.

So, here's what I know...all the item data is either in the gw2.dat or it's possible to force the server to send information for items you don't have.  This is known because our friend from gw2db.com has done it.  He's contractually obliged to keep their IP confidential but I see him lurking here ... seeing if anyone else is smart enough to figure it out.
## Post #167
- Username: blumb2is
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 31, 2012 7:37 pm
- Post datetime: 2012-06-01T09:49:40+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Did they closed download of uncompressed files? 

Also anyone wanna start to create emulator for this game?
## Post #168
- Username: Cruelbob
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed May 16, 2012 10:27 am
- Post datetime: 2012-06-02T15:40:53+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from blumb2is
>
> Also anyone wanna start to create emulator for this game?

I can't see much sense in it.
## Post #169
- Username: kthackeray
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Mar 28, 2012 2:36 am
- Post datetime: 2012-06-02T22:59:35+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Cruelbob
>
> I can't see much sense in it.

Cause it's fun, and gives you the chance to see content otherwise inaccessible on live. The server project for the first game has always been about messing around and having fun more than it is about replicating game play, and so will this one, eventually.
## Post #170
- Username: ral
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 24, 2012 12:26 am
- Post datetime: 2012-06-03T08:25:47+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Did anyone take a closer look at models already? It's my first time working with models so I just tried something out and probably still do mistakes.
I still have some problems getting the models done. Here's an example:
Vertices Only

With Face


I can't really find my mistakes. But for those who wanna look more into it here's what I did. I only used the GEOM part in the MODL files and ignored the rest for now.
Not all MODL contain GEOM with all the data I write now:

```
GEOM
byte[4] = header (47 45 4D 4D) (GEOM)
byte[4] = length in bytes of GEOM
byte[length] = data

// closer look at data
// part1
byte[4] = 01 00 10 00
byte[4] = unknown
byte[4] = amount of repeats for part2
byte[(amount of repeats + 1)*4] = unknown
byte[28] = 0x00

// part2 starts now 
// always 88 bytes and for amount of repeats look part 1
byte[88] = all unknown to me // less to write like this

// part3 starts now
// Here can be 2 different now

// part3 possibility 1
// Vertices floats
// amount of repeats unknown to me but it either ends with part 3 possibility 2 or part4
byte[4] = float x
byte[4] = float y
byte[4] = float z
byte[unknown] = probably normals and other stuff // I don't really know where you can find the size

// part3 possibility 2
byte[10] = Header (AmatShader) - 41 6D 61 74  53 68 61 64  65 72
byte[2] = unknown
byte[4] = 0x00
byte[unknown] = unknown // I don't really know where you can find the size

// part4
// facelist
// repeats unknown to me but it doesn't go till the end
byte[2] = 1
byte[2] = 2
byte[2] = 3

```

I didn't really find yet where most sizes are so I cut them out by hand because it's not that hard to see where the end is.
Part 3 and 4 can repeat more often because the models are split up.

Can anyone with more experience correct errors in the part I wrote up or say what the to me unknown bytes are?
## Post #171
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-06-03T10:46:52+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

post the first 0x40 bytes in hex of the facelist section in a code block. that should tell you whether they use triangle lists, triangle strips, or triangle strips with strip cut indices. the pic looks like it might use triangle strips and you are loading a triangle list.
## Post #172
- Username: ral
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 24, 2012 12:26 am
- Post datetime: 2012-06-03T11:10:04+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Here are .obj, .face, .geom and the full .modl file of the model I posted. The .face and .geom are the second last model in the .modl file. But the cutted parts should be enough already to find my mistake.

// link removed

Facelist starts like this:

```
00 00 01 00  02 00 03 00  04 00 05 00  06 00 07 00  08 00 09 00  0A 00 0B 00  0C 00 0D 00  0E 00 0F 00  10 00 11 00  12 00 13 00
```
## Post #173
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-06-03T16:43:55+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Your generated OBJ file is almost fine. Simple triangle lists yes they are. The only problem is OBJ face indices are 1-based. You use zero.

BTW, I'd delete the sample from your post; new rules are no samples out in the open.
## Post #174
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-06-03T22:57:50+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Btw what modeler are you using to preview? Noesis? Lol any program should have caught your obj bug by either crashing or displaying an error. Are there any hot females in game lol? If the models are good don't forget to post your extractor here when done .
## Post #175
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-06-03T23:05:54+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

he is using deep exploration
[http://www.youtube.com/watch?v=48AIa_ipEX0](http://www.youtube.com/watch?v=48AIa_ipEX0)
## Post #176
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-06-03T23:15:23+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Oh wow cool models do look nice. Model format looked really easy. Hopefully new guy will have something soon!
## Post #177
- Username: ral
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 24, 2012 12:26 am
- Post datetime: 2012-06-04T05:02:20+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Thanks for the help 
The only important part that is missing now are the information about how many bytes the data with vertices and other stuff is, where the information for stuff like AmatShader, Clothing, Skin etc. between some vertices is and the start and end of the facelist. With that data it'd be no problem to write a first extractor but I couldn't find it yet and I don't have that much time to work on it at the moment, that's why I posted everything I knew about the GEOM data in the modl files up there in hope someone else can help
## Post #178
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-06-04T15:02:29+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Don't worry, take your time; I normally take a full month to work on something, an hour here, an hour there. I had found the number of vertices, size of vertex buffer, number of indices, and size of index buffer in the data you provided. The size of vertex data is that 0x87000100 number I think but I didn't test it. If 87 I think it vertex bytes was 0x1C, if 80 it was 0x24, but not sure.

Ha ha ha anyways, I see the game isn't even technically out yet and at $79 bucks preorder all I can say is I'm used to PC gaming being cheaper than console gaming  so I'll wait a little while. Same thing with Tekken Tag 2, the model data is there in the last two bin files of the demo but I ain't going to work on it till the actual game comes out since they might change stuff around.
## Post #179
- Username: Rhoot
- Rank: beginner
- Number of posts: 26
- Joined date: Sat May 05, 2012 6:01 am
- Post datetime: 2012-06-04T17:51:49+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

I have the majority of the geometry data figured out actually (and have had for a month or so). LODs and everything. I recently also found out how to couple models with their textures. I'm working on implementing this in the browser but I've had too much to do the last two weeks. It can extract them as obj files at the moment, but doesn't render them yet. Hopefully I'll be able to get it done this weekend, at which point you can see the structure in the source files.
## Post #180
- Username: ral
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 24, 2012 12:26 am
- Post datetime: 2012-06-04T17:58:17+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Nice. Then I don't need to look more into it. At least I learned a bit since I'm still new to all this stuff
## Post #181
- Username: Rhoot
- Rank: beginner
- Number of posts: 26
- Joined date: Sat May 05, 2012 6:01 am
- Post datetime: 2012-06-06T08:39:25+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Fresh new [binary](http://skold.cc/gw2browser/) (and [source](https://github.com/rhoot/Gw2Browser)) up now, which also handles models. It's both experimental and ugly to say the least, but it should work for most models.

One major exception is equipment. Most of those models will have the wrong texture since they don't seem to contain any texture references.

Edit: Also note some model files contain no geometry, only animation data. For these models you will see "Meshes: 0".
## Post #182
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-06-06T10:58:00+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Cool. It is always nice to see new people on here ripping games. When done create your own thread in the 2d/3d secction with a screen cap. It will get more attention there. I'm tempted to buy the game now hehehe. How do the female models look?
## Post #183
- Username: Rhoot
- Rank: beginner
- Number of posts: 26
- Joined date: Sat May 05, 2012 6:01 am
- Post datetime: 2012-06-06T19:55:15+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from howfie
>
> How do the female models look?
chrrox linked you a video before: [http://www.youtube.com/watch?v=48AIa_ipEX0](http://www.youtube.com/watch?v=48AIa_ipEX0)
## Post #184
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-06-06T21:17:12+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

That's in game though... it's always interesting to see what they look like with only their diffuse map applied.
## Post #185
- Username: Rhoot
- Rank: beginner
- Number of posts: 26
- Joined date: Sat May 05, 2012 6:01 am
- Post datetime: 2012-06-06T23:02:15+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from howfie
>
> That's in game though... it's always interesting to see what they look like with only their diffuse map applied.

That's hard with player characters though, since they are generally built up from several models. One for the chest piece, one for legs, one for the scalp, one for the face, etc. During the stress test however I stashed away a list of all files that were loaded when I logged in, so I'll see if I can make a patch work of one of my characters. If not, I'll look for an NPC model.
## Post #186
- Username: Rhoot
- Rank: beginner
- Number of posts: 26
- Joined date: Sat May 05, 2012 6:01 am
- Post datetime: 2012-06-07T02:11:31+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

So here's my patchworked necromancer. She's got the wrong colors since the textures are for the default colors. She's also got the ugliest hat in existence since the character selection shows it regardless of whether or not it's hidden in-game. Also, yes. The boots looked that messed up in-game as well.

Edit: Note that this is without any sort of textures other than diffuse (and alpha for the boot laces and eyelashes).

[](http://i.imgur.com/YlBh7.png)

Edit 2: Or there's this if you'd prefer.

[](http://i.imgur.com/8xzge.png)
## Post #187
- Username: stalja
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Sep 12, 2009 6:33 pm
- Post datetime: 2012-06-07T07:17:56+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

That second chick is HOT!
## Post #188
- Username: psychopigeon
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Mar 08, 2012 4:24 pm
- Post datetime: 2012-06-07T15:17:23+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

O.M.G I need soundtrack now!
## Post #189
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-06-07T15:23:42+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Oh wow lol, ha ha ha that's some funny shit Rhoot. What's up with the second pic?
## Post #190
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2012-06-07T15:34:34+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

think you could post the base ids for the meshes making up that necro? interested in cross referencing them, see if we can find where those are defined at
## Post #191
- Username: Rhoot
- Rank: beginner
- Number of posts: 26
- Joined date: Sat May 05, 2012 6:01 am
- Post datetime: 2012-06-07T19:39:53+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from howfie
>
> Oh wow lol, ha ha ha that's some funny shit Rhoot. What's up with the second pic?

There's that and like 5 more models next to it that are broken. It looks to me like they're using a triangle strip instead of triangle list but I can't find a flag for whether or not it is one. Seeing as it only affects those few models however I haven't really bothered. (It's funny though, that chick was the first model I managed to render when I was figuring out the model structure. I thought my algorithms were off until I looked at other models.)

Edit: Also, if it was just a triangle strip that wouldn't explain why the eyes are popping out of the head like that. I still think they're just broken.

> Reply from nicoli_s
>
> think you could post the base ids for the meshes making up that necro? interested in cross referencing them, see if we can find where those are defined at

34698 = helm
34747 = legs / skirt
34758 = bottom part of boots
34759 = rest of the boots
34769 = gloves
34772 = shoulders (more like a mantle though)
34775 = chest piece / upper body
35406 = face
## Post #192
- Username: spitfiresson
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 11, 2012 7:01 pm
- Post datetime: 2012-06-11T11:04:35+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Thought I'd reply and give thanks to Rhoot for this. It's quite awesome, if a crude and in progress viewer. Very nice job.

Slowly working on getting models/textures working in max. Not too easy but possible.
## Post #193
- Username: Benny2202
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 18, 2012 2:31 am
- Post datetime: 2012-06-17T20:52:22+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Does someone have the cookie or the exe of the Dev version and could send it to me via pm ? Thanks
## Post #194
- Username: Jeston
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat May 16, 2009 12:16 pm
- Post datetime: 2012-06-19T04:26:55+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Could gw2browser be given the ability to also export all the textures without transparency instead of just a png
## Post #195
- Username: Rhoot
- Rank: beginner
- Number of posts: 26
- Joined date: Sat May 05, 2012 6:01 am
- Post datetime: 2012-06-19T09:47:17+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Jeston
>
> Could gw2browser be given the ability to also export all the textures without transparency instead of just a png
It's on the TODO list, but it requires some work beforehand and I'm in the middle of a move so I don't really have that much time for a couple of weeks. Until then your best bet is to open them in Photoshop with [SuperPNG](http://www.fnordware.com/superpng/) installed, while holding shift. This will allow you to handle the alpha channel separately, meaning no transparency. Instead the alpha channel will pop up as a channel.
## Post #196
- Username: evilwind
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 06, 2012 6:01 pm
- Post datetime: 2012-06-20T02:50:42+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

also when exporting models, i think the textures should follow with also
## Post #197
- Username: Rhoot
- Rank: beginner
- Number of posts: 26
- Joined date: Sat May 05, 2012 6:01 am
- Post datetime: 2012-06-20T10:40:53+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from evilwind
>
> also when exporting models, i think the textures should follow with also
[It's been on the TODO list for a while.](https://github.com/rhoot/Gw2Browser/blob/master/TODO.md) Second to last item.
## Post #198
- Username: mtew
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 26, 2012 10:39 pm
- Post datetime: 2012-06-27T03:55:50+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Nimba
>
> Here is the file. Hopefully it is what you are looking for. Seems to have some kind of Manifest info in it at the bottom. Anyways, GL!

Thanks for the effort on GW2Unpacker. I am running a Fedora system and it runs well under wine. Since I do not have a windows system, I can not rebuild the executable, so I will not (at least for now) try making corrections myself, but I have some notes on what might be added.

I tried it on the Local.dat file and found some interesting information:

Executable files (.dll,.exe,.ctx and so on) start with the two letters 'MZ'.

The master file table (MFT) can also have the tag 'Mft'.

There are 'PF' sub-types 'ARMFARMF' and 'ARMFMFST'.
## Post #199
- Username: Rhoot
- Rank: beginner
- Number of posts: 26
- Joined date: Sat May 05, 2012 6:01 am
- Post datetime: 2012-06-27T16:02:21+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from mtew
>
> Executable files (.dll,.exe,.ctx and so on) start with the two letters 'MZ'.
Aye, and they are identified as such by the browser.

> Reply from mtew
>
> The master file table (MFT) can also have the tag 'Mft'.
"Also?" The MFT always has the magic id 'Mft'.

> Reply from mtew
>
> There are 'PF' sub-types 'ARMFARMF' and 'ARMFMFST'.
There are far more subtypes than that. For those specific ones however, only 'ARMF' describes the file type. The second 'ARMF, as well as 'MFST' are the ids for the first chunk within those files.

EDIT: It seems you've only used the unpacker. I haven't changed anything at all in it since I created it (yes I, not Nimba ), so it's very outdated. I would suggest checking out the browser instead. [Binaries](http://skold.cc/gw2browser/), [Source](https://github.com/rhoot/Gw2Browser). (Granted that is getting severely outdated as well.)
## Post #200
- Username: jeckerson
- Rank: n00b
- Number of posts: 10
- Joined date: Sat May 19, 2012 12:00 am
- Post datetime: 2012-07-01T23:13:44+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Could you explain please, what type of data is located in "Maps" folder, with PF header?
## Post #201
- Username: Rhoot
- Rank: beginner
- Number of posts: 26
- Joined date: Sat May 05, 2012 6:01 am
- Post datetime: 2012-07-02T09:34:40+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from jeckerson
>
> Could you explain please, what type of data is located in "Maps" folder, with PF header?
Those files are just what they sound like. They contain the in-game maps, most of it anyway. Some of the maps data are in other files (such as the prlt files) but terrains, lights, etc are in the files in the Maps "folder". I just haven't written a renderer for them yet. Not sure if I will either, I'm losing interest in both the gw2 files and the browser now that there's not much left undiscovered. :/
## Post #202
- Username: jeckerson
- Rank: n00b
- Number of posts: 10
- Joined date: Sat May 19, 2012 12:00 am
- Post datetime: 2012-07-02T10:46:23+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Are you sure? There are much undiscovered data left, like for example: map layers, links for items data, npc stats etc...
## Post #203
- Username: Loumie
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 12, 2012 3:00 pm
- Post datetime: 2012-07-02T12:26:39+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Everything has been figured out, at least everything has been unpacked in structure format or XML, it just hasn't been released yet publicly. The only things left are unrelevant stuff like fonts/etc...

@developers: I will soon do a last update on [https://github.com/ahom/gw2DatTools](https://github.com/ahom/gw2DatTools), to clean up some stuff then leave it like this. Feel free to fork on it if you wish to add other stuff, but the basics on dat/texture decompressions are all here, plus some hidden goodies for those knowing what is IDA and what are idc scripts ;D
## Post #204
- Username: ral
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 24, 2012 12:26 am
- Post datetime: 2012-07-02T15:22:57+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Too bad you guys want to stop working on it but I still want to thank you a lot. Your code really helped me to learn and understand a lot of stuff.
I'll take a look at stuff you released and soon I have more time again. Maybe if I have the time and the knowledge I make some Tools for stuff I'm interested in or improve stuff.
Thanks again for everything
## Post #205
- Username: Loumie
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 12, 2012 3:00 pm
- Post datetime: 2012-07-02T15:45:13+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Actually there was a heavy hint on IDA and idc scripts in my repo, if you dig it you'll find lot's of stuff, the other part though, I can't say more as I'm not the one who found it and it's meant to be kept private for now.
## Post #206
- Username: ral
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 24, 2012 12:26 am
- Post datetime: 2012-07-02T15:48:52+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

I just saw it (that's why i edited my post incase you saw the old one). That's really a lot of info. Great job
## Post #207
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-04T13:59:27+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from howfie
>
> Model format looked really easy.

Well I hope it is, the GW1 format was my worst nightmare, it was asif they had 3k formats in one. They had certain flags that I had to check each time and add to a list of possible parsingmethods.

I haven't looked through the entire thread, but if anyone can give me a global idea of the format I'll see if I can cook anything up for Noesis in the future.
## Post #208
- Username: ral
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 24, 2012 12:26 am
- Post datetime: 2012-07-04T20:19:32+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Demonsangel
>
> 
I haven't looked through the entire thread, but if anyone can give me a global idea of the format I'll see if I can cook anything up for Noesis in the future.
Just take a look at the ModelReader.cpp of the Gw2Browser. That should give you all info to get started.
[https://github.com/rhoot/Gw2Browser/blo ... Reader.cpp](https://github.com/rhoot/Gw2Browser/blob/master/src/Readers/ModelReader.cpp)
## Post #209
- Username: jeckerson
- Rank: n00b
- Number of posts: 10
- Joined date: Sat May 19, 2012 12:00 am
- Post datetime: 2012-07-04T20:42:00+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Loumie
>
> Everything has been figured out, at least everything has been unpacked in structure format or XML

Which type of data is unpacked in XML format?

Btw, there are some problem with some DDS map files rendering.



WTF?? 184851.png (187.72 KiB) Viewed 100 times
## Post #210
- Username: Loumie
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 12, 2012 3:00 pm
- Post datetime: 2012-07-05T08:40:09+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from jeckerson
>
> Loumie wrote:Everything has been figured out, at least everything has been unpacked in structure format or XML

Which type of data is unpacked in XML format?

I'm not able to answer this. You will have to figure it out yourselves or the author will himself talk about it.

Anyway, I'm working on a small python project that will dump content of the PF files in XML format, that seems interesting ;D. I hope that with this available, peoples will be able to do their own specific viewer tools, as the format will be really straight forward.

Maybe peoples could even help Rhoot with: [https://github.com/rhoot/Gw2Browser](https://github.com/rhoot/Gw2Browser), I'm sure he will be happy to have help to implement new stuff.
## Post #211
- Username: ral
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 24, 2012 12:26 am
- Post datetime: 2012-07-07T19:40:42+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Loumie
>
> 
Anyway, I'm working on a small python project that will dump content of the PF files in XML format, that seems interesting ;D. I hope that with this available, peoples will be able to do their own specific viewer tools, as the format will be really straight forward.
That would be really nice to have.

Can anyone give some info about the structure of the map files?
From looking into them it looks like there are many models (full map + everything on it?) inside (vectors with x,y,z + facelists) and some other stuff I don't know (Just started looking into them some minutes ago).
Here I just extracted some vertices of 1 part of a file (189364.pf)


I'm interested in making these maps to .obj files and some help with the structure would be really nice (since some people seem to know everything already).
## Post #212
- Username: Rhoot
- Rank: beginner
- Number of posts: 26
- Joined date: Sat May 05, 2012 6:01 am
- Post datetime: 2012-07-07T20:42:58+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from jeckerson
>
> Btw, there are some problem with some DDS map files rendering.
That is not a problem, the files actually look like that. It seems they contain 4 masks, one in each channel.

> Reply from Loumie
>
> Maybe peoples could even help Rhoot with: https://github.com/rhoot/Gw2Browser, I'm sure he will be happy to have help to implement new stuff.
I've decided to discontinue the browser due to lack of time and interest, but I'll still accept pull requests if they appear and contain useful stuff.

> Reply from ral
>
> I'm interested in making these maps to .obj files and some help with the structure would be really nice (since some people seem to know everything already).
Either have a look at Loumie's IDA script, or check out my git repository that'll appear in a couple of days.
## Post #213
- Username: ral
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 24, 2012 12:26 am
- Post datetime: 2012-07-08T10:51:17+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Rhoot
>
> 
Either have a look at Loumie's IDA script, or check out my git repository that'll appear in a couple of days.
Guess I'll wait a bit then because the next days I probably still will be busy. And thanks for all the effort.
## Post #214
- Username: Loumie
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 12, 2012 3:00 pm
- Post datetime: 2012-07-08T13:35:11+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from ral
>
> Rhoot wrote:
Either have a look at Loumie's IDA script, or check out my git repository that'll appear in a couple of days.
Guess I'll wait a bit then because the next days I probably still will be busy. And thanks for all the effort.

This should help you: [http://pastebin.com/0agaEtTW](http://pastebin.com/0agaEtTW)
## Post #215
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-08T17:53:07+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Current Noesis script: [https://www.dropbox.com/sh/qbct1tjyv7al ... yCEbiL/GW2](https://www.dropbox.com/sh/qbct1tjyv7alpoi/8uppyCEbiL/GW2)
edit: updated 9/7/2012 v0.0.5
edit: updated 10/7/2012 v0.0.6
now loads ATEX files instead of png

It's based off Rhoot's code, so thanks for making my life easier.
I've only had 1 model to play with so some models could fail to load.
Current script loads textures as png files, I'm still working on ATEX support.



Edit: added lightmap support
## Post #216
- Username: ral
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 24, 2012 12:26 am
- Post datetime: 2012-07-09T12:19:08+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Looks nice Demonsangel.

> Reply from Loumie
>
> 
This should help you: http://pastebin.com/0agaEtTW

Started working on it with that data:
Chunk: area


Chunk: havk (collision only atm) (different map than the one above for area) (positioning still is wrong of all objects)


Edit:// 10th July 2012
XML Export in the works (Still gotta rename some stuff and write all Data into it)
Obj Export in the works
Facelist can be increased with every Model. So like Obj 1 facelist starts at 1 3 2 and Obj 2 starts at 433 445 444. Depends on the way how you render/or just view it,  it may be useful.

Implemented Chunks (doesn't include the exports to file):
- parm
- area
- havk

But today I don't have time to continue the work.

Edit:// 11th July 2012
- Full XML Output for chunks: parm, area, havk, msn, shex, cube

Edit:// 13th July 2012
- Now support for chunks: parm, trn, area, msn, havk, shex, cube, audi
XML-Example:
## Post #217
- Username: Loumie
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 12, 2012 3:00 pm
- Post datetime: 2012-07-09T16:38:52+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Nice work keep it up
## Post #218
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-09T19:04:14+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

About the ATEX files, the DXT5 and DXT1 formats, are they actual DXT5 info or does the raw image data need to be decrypted/decompressed or something like this.

I tried loading the raw image data and using Noesis' DXT5 converter but the image didn't load up correctly.
If I have to use all the steps in Rhoot's code the image conversion will take some time in python.
## Post #219
- Username: Loumie
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 12, 2012 3:00 pm
- Post datetime: 2012-07-09T20:37:30+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

That's what this repo [https://github.com/ahom/gw2DatTools](https://github.com/ahom/gw2DatTools) is for, decompression of files in general in the Dat and also decompression of ATEX files, before they can be used properly
## Post #220
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-09T20:51:33+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

More c++ to drive me crazy.
## Post #221
- Username: xtridence
- Rank: n00b
- Number of posts: 11
- Joined date: Tue May 08, 2012 3:58 pm
- Post datetime: 2012-07-10T06:55:47+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Demonsangel
>
> About the ATEX files, the DXT5 and DXT1 formats, are they actual DXT5 info or does the raw image data need to be decrypted/decompressed or something like this.

I tried loading the raw image data and using Noesis' DXT5 converter but the image didn't load up correctly.
If I have to use all the steps in Rhoot's code the image conversion will take some time in python.

The ATEX format has 2 sets of compressions, one of them is a proprietary one, and the other being one of the regular DXT formats (which has readily available algorithms).

Here's a [tool along with source](http://forum.xentax.com/viewtopic.php?p=73376#p73376) from a while back that specifically decompresses the ATEX format. A little bit of tweaking could get you the format you desire, and the script itself is fairly minimal and independent.
## Post #222
- Username: Rhoot
- Rank: beginner
- Number of posts: 26
- Joined date: Sat May 05, 2012 6:01 am
- Post datetime: 2012-07-10T12:00:59+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

I just pushed the library I've been working on (also in C++) that can read just about all the files encountered in the .dat. It assumes you know what you're after rather than just 'exploring'. If you do know what you're after however, it should definitely come in handy.

[https://github.com/rhoot/gw2formats](https://github.com/rhoot/gw2formats)

Edit:

> Reply from xtridence
>
> Here's a tool along with source from a while back that specifically decompresses the ATEX format. A little bit of tweaking could get you the format you desire, and the script itself is fairly minimal and independent.

Loumie has actually reversed that proprietary compression and put it in his library on github (see [inflateTextureFileBuffer.cpp](https://github.com/ahom/gw2DatTools/blob/master/src/gw2DatTools/compression/inflateTextureFileBuffer.cpp)). It is a lot easier to read than the asm in AtexReader.
## Post #223
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-10T13:16:07+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Updated the dropbox with ateximage.dll so the script now loads ATEX files instead of png.

I gave up trying to convert the c++ code to python when I saw the ASM so I had Necrolis turn it into a Noesis dll plugin based on your source codes (copy paste mostly).
Read the readme, I'll continue to fill it with more detailed changelogs and instructions.

Thanks for the help guys
## Post #224
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-11T11:31:38+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Fun part starts again, does anyone know the exact order of calculations for the armature?
## Post #225
- Username: Rhoot
- Rank: beginner
- Number of posts: 26
- Joined date: Sat May 05, 2012 6:01 am
- Post datetime: 2012-07-13T23:20:55+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

I wrote a DLL for use with node.js that wraps the decompression in Loumie's gw2DatTools, if someone's interested. The binary is for windows with both 32-bit and 64-bit versions, with a wrapper script selecting the right one. Usage is very briefly documented in the js-file.

Binary: [http://skold.cc/gw2/gw2dattools.node.zip](http://skold.cc/gw2/gw2dattools.node.zip)
Source: [https://gist.github.com/3107143](https://gist.github.com/3107143)
## Post #226
- Username: Demonsangel
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-07-13T23:46:15+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Demonsangel
>
> 
Fun part starts again, does anyone know the exact order of calculations for the armature?

did you try switch from left to right handed matrix.
if it is using quats you just invert the w.
## Post #227
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-14T13:35:25+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from chrrox
>
> 

did you try switch from left to right handed matrix.
if it is using quats you just invert the w.

Genious, it worked.

Good to know this for other formats.
## Post #228
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-14T17:07:31+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Has anyone encountered a bonemap?
I just used an (i++) loop to connect the bones to eachother which works fine, but the the boneID's in the vertex data for the weights don't match the actual boneID's
## Post #229
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-07-14T17:50:17+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

yeah i have worked with bone maps if you want pm me the model your trying and the script and what info you have and i can help with the bone map.
## Post #230
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-14T20:50:43+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

We found the bonemaps so moving on to the next part: animations

When following the file reference for the animations I got F2 B4 44 58 01 00 (13854.pf)
but it ends on 0100 which according to the algorythm you guys reversed gives an assertion.

Is there another algorythm or did I stumble upon the wrong reference? And if any of you do find the correct one, could you send the file over to me since I don't have the archive.
## Post #231
- Username: ral
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 24, 2012 12:26 am
- Post datetime: 2012-07-14T21:29:07+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

I'll send you a pm in some mins containing some data + files if I can do it fast  Just gotta do it by hand with hex editor fast to get filenumbers.

EDIT:// Mhh weird .. Sorry but I'm getting wrong info too .. I'll look more into it now but it can take a bit more time than i expected :/

EDIT2:// Ahh got it now  I was counting wrong .. do you have all chunk structs btw?

EDIT3:// You got a pm with some info
## Post #232
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-14T22:18:13+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

I don't know anything about the ANIM struct, I was basically trying a lot of combinations to try and get the file reference.
## Post #233
- Username: ral
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 24, 2012 12:26 am
- Post datetime: 2012-07-14T22:26:08+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

I sent you all structures from the ida script that is on Loumie's git repo. Now you should know everything about the structures, at least where the data is for everything 

Good luck getting stuff done now
## Post #234
- Username: Rhoot
- Rank: beginner
- Number of posts: 26
- Joined date: Sat May 05, 2012 6:01 am
- Post datetime: 2012-07-15T03:36:29+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Demonsangel
>
> When following the file reference for the animations I got F2 B4 44 58 01 00 (13854.pf)
but it ends on 0100 which according to the algorythm you guys reversed gives an assertion.

Is there another algorythm or did I stumble upon the wrong reference? And if any of you do find the correct one, could you send the file over to me since I don't have the archive.

That should be the only file reference algorithm, aside from files that just use the plain fileId as an uint32. The bytes you gave are definitely not a file reference. They are easy to spot:

- They're three 16-bit integers long (totalling 6 bytes).
- The first integer is always >= 0x100
- The second integer is always >= 0x100, but still very low. It's usually 0x100 or 0x101.
- The third integer must always be 0 since it's used as a utf-16 string terminator.

About those structs you got from ral (from Loumie's IDA script); if you want to know what the TSTRUCT_ARRAY_PTR_START and friends are, they're defined in [TypesDef.bt](https://github.com/ahom/gw2DatTools/blob/master/misc/templates/TypesDef.bt) in Loumie's repository. How the defines work is not entirely obvious just from glancing at them (especially if you're unfamiliar with 010 templates), but those defines basically deal with offsets in files.
## Post #235
- Username: Loumie
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 12, 2012 3:00 pm
- Post datetime: 2012-07-15T07:46:29+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

For those who are too lazy to run the script or don't want to download IDA Pro Free, here is the output of the current build 14762.
It contains structures classified by ChunkName and VersionNumber, it also prints the address it was taken from in the exe if you think something is weird.

[ANStructs.txt](https://raw.github.com/ahom/gw2DatTools/master/misc/templates/ANStructs.txt)
[TypesDef.bt](https://github.com/ahom/gw2DatTools/blob/master/misc/templates/TypesDef.bt)
[PackFile.bt](https://github.com/ahom/gw2DatTools/blob/master/misc/templates/PackFile.bt)

It looks like this:

```
 Chunk: eula (chunkname), versions: 1 (number of versions for this chunk), strucTab: 0x1527F78
==================================================
=> Version: 0 (version 0)
typedef struct 
{
    byte Language;
    wchar_ptr Text;
} PackEulaLanguageV0<optimize=false>;

typedef struct 
{
    TSTRUCT_ARRAY_PTR_START PackEulaLanguageV0 Language TSTRUCT_ARRAY_PTR_END;
    byte Version;
} PackEulaV0<optimize=false>; (last struct in version is the starting struct)

```


They are meant to be usable templates for 010 editor, in conjunction with Types.bt and PackFile.bt you don't have really anything to do just some glue code like this:

```
#include <PackFile.bt>

<insert the structures you want from the script here...>

PackFile MODLPackFile(0, FileSize()); // Declare and parse the PackFile at offset 0 and of size FileSize()

local uint32 lLoopIndex = 0;
local string lMagic;
while (exists(MODLPackFile.chunk[lLoopIndex])) // Loop on all the chunks
{
    FSeek(startof(MODLPackFile.chunk[lLoopIndex].data)); // Put the cursor at the start of the chunk
    
    lMagic = MODLPackFile.chunk[lLoopIndex].header.magic;

    if (lMagic == "MODL") // If chunk is MODL apply the right struct
    {
        ModelFileDataV65 MODLChunk;
    }
    if (lMagic == "SKEL")
    {
        ModelFileSkeletonV1 SKELChunk;
    }

    <blabla...>

    lLoopIndex = lLoopIndex + 1;
}

```


Keep in mind that one type is not handled by the script, the 0x1C one, the definition of this type is known but it is pain to implement inside 010 templates and as we didn't need it, I didn't bother writing the code for it.
As Rhoot explained the strange defines in TypesDef.bt are here to handle various offsets, it is quite hard to handle them properly in 010 template as they don't allow MACROS with variables nor C++ templates definitions. If anyone as a more elegant and easy to use solution please share. ;D

Please also note that there are some other struct definitions in the EXE, but they are not tied to any chunk and as such they are not parsed.

Cheers,
Loumie
## Post #236
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-15T11:49:23+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Ok so

when i have 
```
for
typedef struct 
{
    TSTRUCT_PTR_ARRAY_PTR_START ModelAnimationDataV32 animations TSTRUCT_PTR_ARRAY_PTR_END;
    TSTRUCT_ARRAY_PTR_START ModelCompoundAnimationDataV24 compoundAnimations TSTRUCT_ARRAY_PTR_END;
    TSTRUCT_ARRAY_PTR_START qword fallbacks TSTRUCT_ARRAY_PTR_END;
    TSTRUCT_ARRAY_PTR_START ModelAnimationImportDataV32 imports TSTRUCT_ARRAY_PTR_END;
} ModelFileAnimationBankV24<optimize=false>;
```

The last 3 don't get parsed because offset and count == 0, so it doesn't parse a filereference. Does it mean the animation data is in the pf file itself?
I did notice a lot of bytes being put into ModelAnimationDataV32, but 3 animations does seem too few for such a model.

And this is just nitpicking but in

```
{
    filename filename;
    TSTRUCT_ARRAY_PTR_START ModelAnimationImportSequenceV24 sequences TSTRUCT_ARRAY_PTR_END;
} ModelAnimationImportDataV32<optimize=false>;
```


010 editor doesn't like twice the same name, so filename Filename;
## Post #237
- Username: Rhoot
- Rank: beginner
- Number of posts: 26
- Joined date: Sat May 05, 2012 6:01 am
- Post datetime: 2012-07-15T12:44:15+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Demonsangel
>
> The last 3 don't get parsed because offset and count == 0, so it doesn't parse a filereference. Does it mean the animation data is in the pf file itself?
I did notice a lot of bytes being put into ModelAnimationDataV32, but 3 animations does seem too few for such a model.
Judging by the bytes you posted, you should be having 10 animations, not 3. The first uint32 is the count for the animations array.

> Reply from Demonsangel
>
> 
And this is just nitpicking but in
Code: Select alltypedef struct 
{
    filename filename;
    TSTRUCT_ARRAY_PTR_START ModelAnimationImportSequenceV24 sequences TSTRUCT_ARRAY_PTR_END;
} ModelAnimationImportDataV32<optimize=false>;

010 editor doesn't like twice the same name, so filename Filename;
Those structs are auto-generated from the exe, so they sometimes require some changes. Another example is in the exe fields can have periods in their names.
## Post #238
- Username: ral
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 24, 2012 12:26 am
- Post datetime: 2012-07-15T12:56:07+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Example on 13854.pf (which you got)

```
41 4E 49 4D  BC C6 01 00  18 00 10 00  CC C5 01 00

typedef struct 
{
    TPTR_START ModelFileAnimationBankV24 bank TPTR_END;
    PackGrannyAnimationType anim;
} ModelFileAnimationV24<optimize=false>;
-> in that file: 0C 00 00 00  00 00 00 00  00 00 00 00

ModelFileAnimationBankV24
Offset: 0C 00 00 00

PackGrannyAnimationType:
typedef struct 
{
    TSTRUCT_ARRAY_PTR_START byte animation TSTRUCT_ARRAY_PTR_END;
} PackGrannyAnimationType<optimize=false>;
animation:
Count:00 00 00 00
Offset: 00 00 00 00
(so no animation data)


ModelFileAnimationBankV24 has an offset so let's go on with that one:

typedef struct 
{
    TSTRUCT_PTR_ARRAY_PTR_START ModelAnimationDataV32 animations TSTRUCT_PTR_ARRAY_PTR_END;
    TSTRUCT_ARRAY_PTR_START ModelCompoundAnimationDataV24 compoundAnimations TSTRUCT_ARRAY_PTR_END;
    TSTRUCT_ARRAY_PTR_START qword fallbacks TSTRUCT_ARRAY_PTR_END;
    TSTRUCT_ARRAY_PTR_START ModelAnimationImportDataV32 imports TSTRUCT_ARRAY_PTR_END;
} ModelFileAnimationBankV24<optimize=false>;

You know the offset was 0C 00 00 00 (so 12 bytes) and that was at byte 27,952 so now let's go on at byte 27,964:

03 00 00 00  1C 00 00 00
00 00 00 00  00 00 00 00
00 00 00 00  00 00 00 00
00 00 00 00  00 00 00 00

So that means for
ModelAnimationDataV32: 
count: 03 00 00 00
offset: 1C 00 00 00
ModelCompoundAnimationDataV24
count: 00 00 00 00
offset: 00 00 00 00
(no Data for that)
etc.

Now at that offset the struct ModelAnimationDataV32 starts which is big again etc.
So you have 3 times that ModelAnimationDataV32 struct with a lot of data. And it goes on and on like that till you're done with all structs
```


Hope that helped a bit how it works. There's a lot of data in the ANIM chunk so I think everything for the animation of 1 model can be in 1 MODL file.

(P.S I never had TSTRUCT_PTR_ARRAY_PTR_START so far for the stuff I did so if it's wrong that it's 8 bytes too please correct me)
## Post #239
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-15T13:28:24+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

lol, I was thinking about 13854.pf but had the bytes from 216211.pf on my clipboard.
216211 does indeed have 10 entries.

Ral posted the right bytes, but as you can see it only has 3 entries, which surely can't be enough for the model in the picture I posted at the top of the page.
(zeropose,walk,idle)
unless ofcourse I managed to get a useless npc model at my disposal.
## Post #240
- Username: ral
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 24, 2012 12:26 am
- Post datetime: 2012-07-15T14:05:54+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Demonsangel
>
> 
unless ofcourse I managed to get a useless npc model at my disposal.
That indeed is possible.

I sent you a pm with some stuff. Now you can get more models, textures and whatever else you want
## Post #241
- Username: Loumie
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 12, 2012 3:00 pm
- Post datetime: 2012-07-15T17:57:49+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> (P.S I never had TSTRUCT_PTR_ARRAY_PTR_START so far for the stuff I did so if it's wrong that it's 8 bytes too please correct me)

Yes that's also 8 bytes. The meaning of this name is:

TSTRUCT_PTR_ARRAY_PTR => array<struct*>* , it means that you read uint32(numberOfRecords) uint32(offsetToRecords) and that those records are themselves just an offset to a struct.

And about name conflicts, either you just parse the structs with a modified script that appends '_' to variable names and replaces '.' by '_' (like me xD) or you do it manually when 010 complains. But it is still not so frequent so doing it by hand is not a big issue. But you can blame ArenaNet for naming them like this
## Post #242
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-15T18:22:46+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Before I try to manually reverse the animation data, is there a struct for them?
I had a look at all the animation chunks but none of them seem to resemble the data I have at hand.

As far as I could tell from a quick glance the data starts with a pointer to the animation name with then 2 dwords where the second seems to always be 89 88 88 3C (for the few files I had a look at) and the first AB AA AA 3E with the last byte 3F in some datachunks and the first 3 CE CC 4C
## Post #243
- Username: Loumie
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 12, 2012 3:00 pm
- Post datetime: 2012-07-15T18:40:07+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

I don't know what files you have but from what I have, in MODL files, the ANIM chunk is exactly the struct the scripts outputs => ModelFileAnimationV24

```
41 4E 49 4D 54 38 00 00 18 00 10 00
```


18 00 => V24

```
typedef struct 
{
    TSTRUCT_ARRAY_PTR_START byte animation TSTRUCT_ARRAY_PTR_END;
} PackGrannyAnimationType<optimize=false>;

typedef struct 
{
    PackGrannyAnimationType data;
    filename fileFull;
} ModelAnimationLodV24<optimize=false>;

typedef struct 
{
    qword boneToken;
    TSTRUCT_ARRAY_PTR_START float keys TSTRUCT_ARRAY_PTR_END;
} ModelVisTrackDataV32<optimize=false>;

typedef struct 
{
    byte type;
    dword trackGroupIndex;
    dword vectorTrackIndex;
    float4 initialValue;
} ModelTrackTypeDataV24<optimize=false>;

typedef struct 
{
    dword uvAnimId;
    TSTRUCT_ARRAY_PTR_START ModelTrackTypeDataV24 uvTransformData TSTRUCT_ARRAY_PTR_END;
} ModelUVAnimationV24<optimize=false>;

typedef struct 
{
    qword bone;
    TSTRUCT_ARRAY_PTR_START ModelTrackTypeDataV24 cloudTrackData TSTRUCT_ARRAY_PTR_END;
} ModelCloudAnimV24<optimize=false>;

typedef struct 
{
    dword materialId;
    dword constToken;
    dword trackGroupIndex;
    dword vectorTrackIndex;
    float4 initialValue;
} ModelMatConstAnimV24<optimize=false>;

typedef struct 
{
    qword bone;
    TSTRUCT_ARRAY_PTR_START ModelTrackTypeDataV24 lightTrackData TSTRUCT_ARRAY_PTR_END;
} ModelLightAnimationV24<optimize=false>;

typedef struct 
{
    qword id;
    dword type;
    float time;
    qword val;
    filename strVal;
} ModelAnimPropertyDataV24<optimize=false>;

typedef struct 
{
    qword linkToken;
    dword trackGroupIndex;
    dword vectorTrackIndex;
    float4 initialValue;
} ModelTokenMapAnimV24<optimize=false>;

typedef struct 
{
    qword bone;
    TSTRUCT_ARRAY_PTR_START ModelTrackTypeDataV24 bcTrackData TSTRUCT_ARRAY_PTR_END;
} ModelBoneConstraintAnimV24<optimize=false>;

typedef struct 
{
    qword bone;
    TSTRUCT_ARRAY_PTR_START ModelTrackTypeDataV24 anchorTrackData TSTRUCT_ARRAY_PTR_END;
} ModelAnchorAnimV24<optimize=false>;

typedef struct 
{
    qword bone;
    TSTRUCT_ARRAY_PTR_START ModelAnchorAnimV24 anchorAnim TSTRUCT_ARRAY_PTR_END;
} ModelStreakAnimV24<optimize=false>;

typedef struct 
{
    qword bone;
    TSTRUCT_ARRAY_PTR_START ModelTrackTypeDataV24 lightningTrackData TSTRUCT_ARRAY_PTR_END;
} ModelLightningAnimV24<optimize=false>;

typedef struct 
{
    qword bone;
    TSTRUCT_ARRAY_PTR_START ModelTrackTypeDataV24 windTrackData TSTRUCT_ARRAY_PTR_END;
} ModelWindAnimationV24<optimize=false>;

typedef struct 
{
    qword token;
    PackGrannyAnimationType data;
    TPTR_START ModelAnimationLodV24 animLod TPTR_END;
    float moveSpeed;
    TSTRUCT_ARRAY_PTR_START ModelVisTrackDataV32 visTrackData TSTRUCT_ARRAY_PTR_END;
    TSTRUCT_ARRAY_PTR_START ModelUVAnimationV24 uvAnimData TSTRUCT_ARRAY_PTR_END;
    TSTRUCT_ARRAY_PTR_START ModelCloudAnimV24 cloudAnim TSTRUCT_ARRAY_PTR_END;
    TSTRUCT_ARRAY_PTR_START ModelMatConstAnimV24 matConstAnim TSTRUCT_ARRAY_PTR_END;
    TSTRUCT_ARRAY_PTR_START word morphTrackGroups TSTRUCT_ARRAY_PTR_END;
    TSTRUCT_ARRAY_PTR_START float triggerTimes TSTRUCT_ARRAY_PTR_END;
    TSTRUCT_ARRAY_PTR_START qword triggerTokens TSTRUCT_ARRAY_PTR_END;
    TSTRUCT_ARRAY_PTR_START ModelLightAnimationV24 lightAnimData TSTRUCT_ARRAY_PTR_END;
    dword isAdditive;
    dword variantCount;
    dword variantIndices[3];
    TSTRUCT_ARRAY_PTR_START ModelAnimPropertyDataV24 properties TSTRUCT_ARRAY_PTR_END;
    float3 center;
    float radius;
    TSTRUCT_ARRAY_PTR_START ModelTokenMapAnimV24 tokenMapAnims TSTRUCT_ARRAY_PTR_END;
    TSTRUCT_ARRAY_PTR_START ModelBoneConstraintAnimV24 bcAnim TSTRUCT_ARRAY_PTR_END;
    TSTRUCT_ARRAY_PTR_START ModelStreakAnimV24 streakAnim TSTRUCT_ARRAY_PTR_END;
    TSTRUCT_ARRAY_PTR_START ModelLightningAnimV24 lightningAnim TSTRUCT_ARRAY_PTR_END;
    TSTRUCT_ARRAY_PTR_START ModelWindAnimationV24 windAnimData TSTRUCT_ARRAY_PTR_END;
} ModelAnimationDataV32<optimize=false>;

typedef struct 
{
    qword token;
    qword start;
    qword loop;
    qword end;
} ModelCompoundAnimationDataV24<optimize=false>;

typedef struct 
{
    qword name;
    float duration;
} ModelAnimationImportSequenceV24<optimize=false>;

typedef struct 
{
    filename filename;
    TSTRUCT_ARRAY_PTR_START ModelAnimationImportSequenceV24 sequences TSTRUCT_ARRAY_PTR_END;
} ModelAnimationImportDataV32<optimize=false>;

typedef struct 
{
    TSTRUCT_PTR_ARRAY_PTR_START ModelAnimationDataV32 animations TSTRUCT_PTR_ARRAY_PTR_END;
    TSTRUCT_ARRAY_PTR_START ModelCompoundAnimationDataV24 compoundAnimations TSTRUCT_ARRAY_PTR_END;
    TSTRUCT_ARRAY_PTR_START qword fallbacks TSTRUCT_ARRAY_PTR_END;
    TSTRUCT_ARRAY_PTR_START ModelAnimationImportDataV32 imports TSTRUCT_ARRAY_PTR_END;
} ModelFileAnimationBankV24<optimize=false>;

typedef struct 
{
    TPTR_START ModelFileAnimationBankV24 bank TPTR_END;
    PackGrannyAnimationType anim;
} ModelFileAnimationV24<optimize=false>;

```
## Post #244
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-15T18:53:05+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

I'm talking about 

```
typedef struct 
{
    TSTRUCT_ARRAY_PTR_START byte animation TSTRUCT_ARRAY_PTR_END; <---------data in here
} PackGrannyAnimationType<optimize=false>;

```
## Post #245
- Username: Loumie
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 12, 2012 3:00 pm
- Post datetime: 2012-07-15T19:18:48+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

No idea but as the name suggest it may be public => [http://www.radgametools.com/granny.html](http://www.radgametools.com/granny.html)

Most likely ANet just throws this info to Granny API.
## Post #246
- Username: STIGMATED
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jul 16, 2012 2:05 am
- Post datetime: 2012-07-15T21:14:11+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Does anybody know in what file kepps IP for connection with server?
## Post #247
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-16T22:23:59+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

There are (really) minor similarities to the format they desrcibed, mostly the header
for the raw code
all pointers are absolute with the first byte of the raw data being 0
I'll apologize up front if I misused the term "pointer" since my c++ isn't great

```
float Duration;
float TimeStep;
float Oversampling;
int count?? <so far only seen 1 or 2>
int ?? <only encountered "28">
int/float Table[24]

```


Then with the following 010 template I was able to get some position/rotation/9x9 matrix info
but still a lot of unknowns

```
int count;
int table[count-2];
typedef struct
{
    local int type = ReadUShort(FTell());
    if(type == 4){FSkip(4);float x;float y;float z;}
    else if (type == 5){FSkip(4);float x;float y;float z;float w;}
    else if(type == 2){FSkip(2);ushort flag;}
    else if (type== 3){FSkip(4);int count;int posMat9x9;}
    else if (type == 513){
        local quad current = FTell();
        FSkip(4);
        int count1<hidden=true>;
        int pos1<hidden=true>;
        int count2<hidden=true>;
        int pos2<hidden=true>;
        FSeek(pos1);
        float data1[count1]<bgcolor=cPurple>;
        FSeek(pos2);
        float data2[count2]<bgcolor=cAqua>;
        FSeek(current);
    }
    else if (type == 520){
        local quad current = FTell();
        FSkip(8);
        int count<hidden = true>;
        int pos<hidden = true>;
        FSeek(pos);
        float data[count/2]<bgcolor=cSilver>;
        FSeek(current);
    }
}data<optimize=false>;
typedef struct
{
    local quad current=FTell();
    int count;//?
    FSeek(ReadInt(FTell()));
    string CurveDataHeader<bgcolor=cRed>;
    
}CurveData;
typedef struct{
    local quad current;
    current = FTell();
    FSeek(ReadInt(FTell()));
    string Name<bgcolor=cYellow>;
    FSeek(current+4);

    int zero;
    
    current = FTell();
    FSeek(ReadInt(FTell()));
    CurveData Header;
    FSeek(current+4);

    current = FTell();
    FSeek(ReadInt(FTell()));
    data Data2;
    FSeek(current+4);

    int a;

    current = FTell();
    FSeek(ReadInt(FTell()));
    data Data;
    FSeek(current+4);

    int c;

    current = FTell();
    FSeek(ReadInt(FTell()));
    data Data3;
    FSeek(current+4);
    
}float8<optimize=false>;

float8 floats[table[8]];

```
## Post #248
- Username: hazballs
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Dec 03, 2011 9:05 pm
- Post datetime: 2012-07-19T01:47:14+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Hi all, quite excited to see so much work being done for GW2 - I was wondering if anybody knows how the game stores text based data. Arenanet has said there are literally thousands of dynamic events, it would be nice to find the names/objectives etc. in the game files somehow. I'd also love to be able to browse the skills, elite skills in particular, and maybe update the official wiki if their info is out of date after the coming BWE. Can this stuff be viewed using the GW2 dat browser?
## Post #249
- Username: Dr Ishmael
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jan 31, 2010 10:59 am
- Post datetime: 2012-07-19T03:12:49+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Yes, the individual text strings can be viewed in the STRS files, but there is no known structure that ties them together.  For example, a skill is composed of at least 2 strings: the name, the description, and then all the individual effects.  There is nothing inside the dat file that says "skill 123 uses string 123456 as the name and string 123457 as the description" (unless this has indeed been found and I just missed it).  This information has to be retrieved from the game server.

Another complication is that a lot of strings are encrypted, and the server has to supply the encryption key for the game to decrypt and display it.  In GW1, nearly all the text for quests and NPC dialogue was encrypted, so it's a safe assumption that this applies to dynamic events in GW2.

Oh, and as for skill info on the wiki, don't worry about it - I've already got a framework of spreadsheets and other stuff in place to capture all the data and easily post it to the wiki.
## Post #250
- Username: Rhoot
- Rank: beginner
- Number of posts: 26
- Joined date: Sat May 05, 2012 6:01 am
- Post datetime: 2012-07-19T04:40:40+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Dr Ishmael
>
> Yes, the individual text strings can be viewed in the STRS files, but there is no known structure that ties them together.
There is, but it's only know by a few select people.

> Reply from Dr Ishmael
>
> There is nothing inside the dat file that says "skill 123 uses string 123456 as the name and string 123457 as the description" (unless this has indeed been found and I just missed it).
Yup, there is. But again it's only known by a few select people (3 that I know of [including me], 2 that I'm unsure of). It's the same data gw2db is using. The first person to stumble upon it didn't want it made public, so that's why it isn't. It's also partly why I'm not working on the browser any more, since everything is already discovered (that and the architecture is quite crap).

I *might* write a separate model viewer at some point, that uses the correct shaders, but definitely no promises.

> Reply from Dr Ishmael
>
> Oh, and as for skill info on the wiki, don't worry about it - I've already got a framework of spreadsheets and other stuff in place to capture all the data and easily post it to the wiki.
Which means I don't have to bother with skill info on the wiki, good to know!
## Post #251
- Username: ral
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 24, 2012 12:26 am
- Post datetime: 2012-07-19T14:20:15+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Rhoot
>
> 
Dr Ishmael wrote:There is nothing inside the dat file that says "skill 123 uses string 123456 as the name and string 123457 as the description" (unless this has indeed been found and I just missed it).
Yup, there is. But again it's only known by a few select people (3 that I know of [including me], 2 that I'm unsure of). It's the same data gw2db is using. The first person to stumble upon it didn't want it made public, so that's why it isn't. It's also partly why I'm not working on the browser any more, since everything is already discovered (that and the architecture is quite crap).
Interesting. I didn't find the data for that yet but I also didn't really try to find it :/ But now you made me curious so I'll try to find it (I hope it's not too hidden or in a file where I don't have the structure of).

With my Tool I only have XML output of mapc (except 3 chunks), txtm, ARMF, PIMG, strs and DEPS files at the moment.
I also have other output but that's not really done and was just as a test (like for PIMG files).
## Post #252
- Username: Gordon21
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun May 06, 2012 3:18 am
- Post datetime: 2012-07-19T19:08:30+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

First post right here, but i'm following for a while now. Good joob everyone.

> Reply from Rhoot
>
> Dr Ishmael wrote:Yes, the individual text strings can be viewed in the STRS files, but there is no known structure that ties them together. 
There is, but it's only know by a few select people.
You mean txtm? Or something else?

> Reply from Rhoot
>
> 
Dr Ishmael wrote:There is nothing inside the dat file that says "skill 123 uses string 123456 as the name and string 123457 as the description" (unless this has indeed been found and I just missed it).
Yup, there is. But again it's only known by a few select people (3 that I know of [including me], 2 that I'm unsure of). It's the same data gw2db is using. The first person to stumble upon it didn't want it made public, so that's why it isn't.
Could you give us a clue?
## Post #253
- Username: Rhoot
- Rank: beginner
- Number of posts: 26
- Joined date: Sat May 05, 2012 6:01 am
- Post datetime: 2012-07-19T21:08:13+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Gordon21
>
> You mean txtm? Or something else?
Nope. The txtm just contains a list of strs files in order, for each language. It also contains the amount of strings that are available in each strs file (which is 1024, but if it changes, the txtm file will contain the change). The first file listed in the txtm file contains strings 0-1023, the second contains 1024-2047, etc.

> Reply from Gordon21
>
> Could you give us a clue?
Nope sorry. Unless the original finder pops in to drop the bomb, or someone entirely unrelated, it won't appear here.
## Post #254
- Username: Gordon21
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun May 06, 2012 3:18 am
- Post datetime: 2012-07-19T21:27:18+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Ok np but is it in the DAT?

Also, did anyone worked on networking? Listening to chats, txtp, achievements tracking...
## Post #255
- Username: Rhoot
- Rank: beginner
- Number of posts: 26
- Joined date: Sat May 05, 2012 6:01 am
- Post datetime: 2012-07-19T21:39:30+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Gordon21
>
> Ok np but is it in the DAT?
Yes.
## Post #256
- Username: ral
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 24, 2012 12:26 am
- Post datetime: 2012-07-19T23:21:42+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Reference between ABNK and strs files:
I used some old files to test it and I didn't test it with too many files because I'm too tired right now so if you find mistakes, correct me 


Top left XML = strs file
Lower left XML = ABNK file
Right top = txtm file
Hex Editor = txtv

So in txtv files you have the reference between textId and voiceId. (See IcyExplorer in Screenshot. 4 bytes textId, 4 bytes voiceId)
All ABNK files contain voiceIds; for every "audio part" 1 ID.
For textIds I just quote Rhoot:

> Reply from Rhoot
>
> The txtm just contains a list of strs files in order, for each language. It also contains the amount of strings that are available in each strs file (which is 1024, but if it changes, the txtm file will contain the change). The first file listed in the txtm file contains strings 0-1023, the second contains 1024-2047, etc.

Then you just gotta calculate where it is.
## Post #257
- Username: Gordon21
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun May 06, 2012 3:18 am
- Post datetime: 2012-07-22T16:09:44+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Thank you for these infos.

Did someone find what means flag 1 in an image (PIMG file). It always gives the same negative fileId.
Example : (file=96106)

```
	<x>24</x>
	<y>50</y>
	<flags>1</flags>
	<layer>0</layer>
	<file>-16711935</file>
	<solidColor>0/0/0/0</solidColor>
</image>

```


Also, many of you are talking about "DEPS" files but i can't find any with the browser, where did you find them? Can someone send me one?
## Post #258
- Username: STIGMATED
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jul 16, 2012 2:05 am
- Post datetime: 2012-07-22T19:03:47+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Does anybody want to take part in the development of emulator of Guild Wars 2? Write me on ICQ 154137.
## Post #259
- Username: Rhoot
- Rank: beginner
- Number of posts: 26
- Joined date: Sat May 05, 2012 6:01 am
- Post datetime: 2012-07-26T21:29:08+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Gordon21
>
> Also, many of you are talking about "DEPS" files but i can't find any with the browser, where did you find them? Can someone send me one?
It got removed quite early, BWE1 I believe.
## Post #260
- Username: Gordon21
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun May 06, 2012 3:18 am
- Post datetime: 2012-07-26T21:39:09+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

So the only files left are "unknown" ones (mostly garbage from deleted files?), bxm2 files (I can't find any) and cntc "data" byte arrays, right?

Do you know why strings in cntc files dont represent actual strings?
## Post #261
- Username: Loumie
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 12, 2012 3:00 pm
- Post datetime: 2012-07-27T10:16:02+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Did someone find what means flag 1 in an image (PIMG file). It always gives the same negative fileId.

Don't take my words for granted but, to me, it seems obvious, looking at fileId and solidColor, that the flag should tell you if this "page" is a solidColor or a standalone texture found in fileId X.

And just a quick guess, with a fileReference of 0x0000 / 0x0000 / 0x0000 the file Id computed would be:
0xFF00 * (-0x100) + (-0x100) + 1 pretty sure this is what you see.

> So the only files left are "unknown" ones (mostly garbage from deleted files?), bxm2 files (I can't find any) and cntc "data" byte arrays, right?

Last I checked, some of the "unknown" ones (maybe all, didn't check) were referred in the AFNT file, so most likely Fonts.
## Post #262
- Username: Gordon21
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun May 06, 2012 3:18 am
- Post datetime: 2012-07-27T11:35:24+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Loumie
>
> Don't take my words for granted but, to me, it seems obvious, looking at fileId and solidColor, that the flag should tell you if this "page" is a solidColor or a standalone texture found in fileId X.
I did some test and it seems it indicates "deleted page, just step over".

> Reply from Loumie
>
> And just a quick guess, with a fileReference of 0x0000 / 0x0000 / 0x0000 the file Id computed would be:
0xFF00 * (-0x100) + (-0x100) + 1 pretty sure this is what you see.
You're right I did the calculation it's just fileref 0.

> Reply from Loumie
>
> Last I checked, some of the "unknown" ones (maybe all, didn't check) were referred in the AFNT file, so most likely Fonts.
I'll sort the files then.
## Post #263
- Username: Rhoot
- Rank: beginner
- Number of posts: 26
- Joined date: Sat May 05, 2012 6:01 am
- Post datetime: 2012-07-28T13:41:43+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Gordon21
>
> Do you know why strings in cntc files dont represent actual strings?
They're hashed and encrypted.
## Post #264
- Username: gott
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 28, 2012 8:25 pm
- Post datetime: 2012-07-28T13:51:32+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Being late to the party, does the gw2.dat consist of calculations pertaining to in-game mechanics?  ie, weapon/spell damage?
## Post #265
- Username: Gordon21
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun May 06, 2012 3:18 am
- Post datetime: 2012-07-28T19:34:30+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Rhoot
>
> Gordon21 wrote:Do you know why strings in cntc files dont represent actual strings?
They're hashed and encrypted.

I'm a bit new to this so I can't understand how it is possible. You can't reverse hashing right?

According to the exe, they're using :

Aes
Cbc
Hmac
Rc4
Sha
Sha256

So RC4 then something else I didn't have time to find today will look a bit more tomorrow.
## Post #266
- Username: gott
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 28, 2012 8:25 pm
- Post datetime: 2012-07-28T20:56:37+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Gordon21
>
> Rhoot wrote:Gordon21 wrote:Do you know why strings in cntc files dont represent actual strings?
They're hashed and encrypted.

I'm a bit new to this so I can't understand how it is possible. You can't reverse hashing right?

According to the exe, they're using :

Aes
Cbc
Hmac
Rc4
Sha
Sha256

So RC4 then something else I didn't have time to find today will look a bit more tomorrow.You can decrypt the strings if you have the crypto key and the encryption method used.
## Post #267
- Username: Rhoot
- Rank: beginner
- Number of posts: 26
- Joined date: Sat May 05, 2012 6:01 am
- Post datetime: 2012-07-29T13:48:20+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Gordon21
>
> I'm a bit new to this so I can't understand how it is possible. You can't reverse hashing right?
That's correct, but you don't really have to as the occurrence of the string is hashed in all places already. Thus the exe never has to do the hashing.

Edit: That is, the strings you're mentioning are only used for lookup. Any strings used in the game are in the strs files.

> Reply from gott
>
> You can decrypt the strings if you have the crypto key and the encryption method used.
If you do, you're left with a hashed string. It's a bit easier to handle, but still unreadable.
## Post #268
- Username: cyrakuse
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 27, 2012 12:19 am
- Post datetime: 2012-07-31T08:48:08+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

How is it possible to get the list of items from gw2.dat ?
## Post #269
- Username: b00mb0
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 02, 2012 12:46 am
- Post datetime: 2012-08-01T16:53:40+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

First post here 

I really don't know if this is ok to post this here. If not, please ignore 
I'm currently looking for a way to automate the construction of the ingame map (as to create a png file out of every map tiles). Right now, i'm using gw2Browser to extract map tiles, to after stich them manually in photoshop .... i know..
I was wondering if a kind soul can help with with this request.

Thanks to everyone and again, pls accept my appologies if this is not the right place to post something like this.
## Post #270
- Username: polarbearsrawr
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Mar 31, 2012 5:01 am
- Post datetime: 2012-08-03T06:03:48+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from b00mb0
>
> First post here 

I'm currently looking for a way to automate the construction of the ingame map (as to create a png file out of every map tiles). Right now, i'm using gw2Browser to extract map tiles, to after stich them manually in photoshop .... i know..

I've been working on this exact thing,(mostly by hand) and I'll just warn that it requires several hundred GB of swap space for Photoshop for the highest resolution map  The final BMP type save file should be just under 2GB or so, with dimensions currently at 27648 x 25600.
## Post #271
- Username: ral
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 24, 2012 12:26 am
- Post datetime: 2012-08-03T09:59:32+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

For those people who put the Map Textures by hand together in Photoshop I can give the hint to look at PIMG files 
[This git repo](https://github.com/ahom/gw2DatTools) and the knowledge that you need PIMG files should be enough to write a Tool fast. Shouldn't even take a day and you have all your maps put together 

Currently I'm busy with other stuff and I'm getting a bit bored of the GW2 files because knowing all the structs of all files made it a bit boring for me
## Post #272
- Username: Gordon21
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun May 06, 2012 3:18 am
- Post datetime: 2012-08-03T10:57:59+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from polarbearsrawr
>
> b00mb0 wrote:First post here 

I'm currently looking for a way to automate the construction of the ingame map (as to create a png file out of every map tiles). Right now, i'm using gw2Browser to extract map tiles, to after stich them manually in photoshop .... i know..


I've been working on this exact thing,(mostly by hand) and I'll just warn that it requires several hundred GB of swap space for Photoshop for the highest resolution map  The final BMP type save file should be just under 2GB or so, with dimensions currently at 27648 x 25600.

Actually only 40 GB
## Post #273
- Username: Loumie
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 12, 2012 3:00 pm
- Post datetime: 2012-08-03T11:51:35+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

If you're programming in C++ you can also use rhoot gw2Format util which gives an easy to use interface for manipulating PF files Chunks:
[https://github.com/rhoot/gw2formats](https://github.com/rhoot/gw2formats)

In conjunction with [https://github.com/ahom/gw2DatTools](https://github.com/ahom/gw2DatTools) you should actually be able to build pretty cool tools and very quickly.
## Post #274
- Username: hazballs
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Dec 03, 2011 9:05 pm
- Post datetime: 2012-08-13T11:34:49+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Can anybody tell me how icons are linked to strings and how to match them up? There are a lot of items (particularly weapons and armor) that are not currently on the wiki that are on GW2, I'd like to get stuck in updating it.
## Post #275
- Username: neuroquila
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Aug 04, 2012 4:08 am
- Post datetime: 2012-08-17T08:11:09+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

So someone managed to extract the ATEP files just as they should be. He says he did that with the help from "ATEXreader" with "small changes to it". He's opened this page here: [https://sites.google.com/site/jumptovictory](https://sites.google.com/site/jumptovictory) ... really impressive.
I wasn't able at all to extract the ATEP files from the dat using atexreader because something goes terribly wrong with the channels and what you get is not what's visible in-game and I'm not able to correct this. My C knowledge isn't sufficient to make any improvements.
So please could someone (maybe the author of this page above) please help me in extracting those files? I don't want to rely on someones work if I plan to use that for an application!
## Post #276
- Username: ral
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 24, 2012 12:26 am
- Post datetime: 2012-08-17T08:43:50+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from neuroquila
>
> So someone managed to extract the ATEP files just as they should be. He says he did that with the help from "ATEXreader" with "small changes to it". He's opened this page here: https://sites.google.com/site/jumptovictory ... really impressive.
I wasn't able at all to extract the ATEP files from the dat using atexreader because something goes terribly wrong with the channels and what you get is not what's visible in-game and I'm not able to correct this. My C knowledge isn't sufficient to make any improvements.
So please could someone (maybe the author of this page above) please help me in extracting those files? I don't want to rely on someones work if I plan to use that for an application!
In the ATEXreader V6 just go to the following function

```
RGBA *ProcessDXT5(unsigned char *data,int xr, int yr) { }
```

and comment-out the line 

```
image[x*4+a+(y*4+b)*xr].a=atbl[k&7];
```

If i remember correctly that was all that is needed.
## Post #277
- Username: neuroquila
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Aug 04, 2012 4:08 am
- Post datetime: 2012-08-17T10:59:37+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

thanks for your help!
I successfully changed and compiled it but that didn't changed anything on the output...
Edit: ok, right..that change targets DXT5 and yes it did something to those files but ... have a look for yourself
## Post #278
- Username: ral
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 24, 2012 12:26 am
- Post datetime: 2012-08-17T11:58:17+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Yes, there are files like that but if you look through all files you'll also find the ones you probably want  Just ignore these kind of images except you'll find out what they're good for
## Post #279
- Username: neuroquila
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Aug 04, 2012 4:08 am
- Post datetime: 2012-08-17T14:07:27+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

oh...indeed. I only picked a handful of files to test it and so I couldn't see it's working.

I think those others image files have something to do with AI, environment or stuff like that since these consist only of points and circles and 4 different colors: black, blue, red, green; just like heat maps!
## Post #280
- Username: ShadowWalker
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 30, 2012 9:34 pm
- Post datetime: 2012-08-30T17:39:41+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

I have a question, is it possible to extract ALL skill images + descriptions (effects, time to recharge etc)?

I'm planning to some applications but for that I need all those things :/. One of the applications will allow you make your own builds on your computer without logging in on GW2 or on the internet.
## Post #281
- Username: Xdta
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 23, 2012 10:47 pm
- Post datetime: 2012-08-31T10:03:00+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from ShadowWalker
>
> I have a question, is it possible to extract ALL skill images + descriptions (effects, time to recharge etc)?

I'm planning to some applications but for that I need all those things :/. One of the applications will allow you make your own builds on your computer without logging in on GW2 or on the internet.

Yes, but the method on how to do it isn't public and ArenaNet changed the format of the content files about a week ago.
## Post #282
- Username: ShadowWalker
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 30, 2012 9:34 pm
- Post datetime: 2012-09-01T11:35:36+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

So all the things that have been discovered in this thread (and the not-public methods) are unusable? :/
## Post #283
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2013-04-01T18:28:38+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

IIRC there was a switch for GW2.EXE to download the DAT file as uncompressed. I cannot find it anymore. Is it still in the .EXE nowadays? If so, does anyone know what switch it was?

thanks
-Darkstar
## Post #284
- Username: brandon02852
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 17, 2012 8:56 pm
- Post datetime: 2013-05-24T19:44:11+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

Can somebody please write a tutorial on how to use the GW2Inflate DLL?  The author just slapped it up here without giving anybody any idea on how to use it.
## Post #285
- Username: Pesmontis
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Jun 21, 2010 12:10 am
- Post datetime: 2014-11-30T04:52:06+00:00
- Post Title: Re: [Request] Guild Wars 2 DAT

> Reply from Rhoot
>
> So here's my patchworked necromancer. She's got the wrong colors since the textures are for the default colors. She's also got the ugliest hat in existence since the character selection shows it regardless of whether or not it's hidden in-game. Also, yes. The boots looked that messed up in-game as well.

Edit: Note that this is without any sort of textures other than diffuse (and alpha for the boot laces and eyelashes).



Edit 2: Or there's this if you'd prefer.

In the second image, I think the mesh data isn't wrong, it's just that the mesh hasn't got bones & skin applied.
This kind of mesh deformation was also found with Sacred 2 models (gr2 models).
In the latter case, the facial bones have scale factors in their 4x4 transform matrices.
