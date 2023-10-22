## Post #1
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-01-24T14:45:39+00:00
- Post Title: RaiderZ filesystem

The second closed beta test of RaiderZ revealed a new filesystem. I wanted to take a quick look at what's new!

Note: This isn't a request or a solution, but definitely falls under the 'compression methods' category!


Previously
Previously, the MRS format was used to store files.

This same format (and version) was used in another game by this developer (MAIET) - GunZ - and uses a modified ZIP format to compress the headers. See: [viewtopic.php?f=21&t=4871](http://forum.xentax.com/viewtopic.php?f=21&t=4871)

MRS files were loaded from hard-coded names in the RaiderZ executable.. not anymore!

A File List!
In the installation directory is the new filesystem's file list - meet fileindex.msf!

This MSF file is the very first file read as it contains everything about the filesystem that's needed to load all the right files, and, naturally, there is some protection..

I should first say that 'fileindex.msf' is slightly different from other MSF files in that the uncompressed size is added to the MSF data like so:

```
uint8 Data[ .. ]

```


When reading the file list, RaiderZ first reads the data into it's own file so uSize doesn't interfere with the MSF reading (see below).

MSF files
Each MSF has a corresponding uncompressed size value from the file list (or, with the case of filelist.msf, the value preceeding the data - see above).

The MSF data is fed through an XOR table function (pseudo-code):

```

EAX = FileSize -1;

while(EAX)
{
  CL = data[EAX -1]
  CL >>= 1;
  EBX = EAX & 0xFFFF;
  CL ^= table[EBX]
  data[EAX] ^= CL
  EAX--;
}

AL = data[FileSize -1]
AL >>= 1;
AL ^= table[0]
AL ^= data[0] // AL is now 0x00
data[0] = AL

```


The XOR table is 64 KB, which I've dumped for reference purposes. It could be dynamically calculated at runtime, but I've not followed this up!

See attachment

The next step is the decompression. Now I'm not interested in following all that as it's sure to change before release! For the purposes of exploring the file list, I just dumped the result.

A File List! Decrypted!
Now decrypted, the file list takes the following format:

```
{
  uint32 uSize
  uint32 Pos // relative to the MRF file
  uint32 PackedSize
  uint16 MRFNameLen
  uint16 FileNameLen
  uint32 UNKNOWN
  char MRFName[ MRFNameLen ]
  char FileName[ FileNameLen ]
}

```


Files can now be read from the filesystem using this table structure - the Pos and PackedSize values point to the size and position within the MRF file (see MRF file notes below).

MRF files
MRS files are literally just MSF files which have been joined together  The MSF files can be read off using the decrypted file list!

Once the MSF is read off the MRF package, it's processed like I've already described! That's everything!

Edits Formatting!
[lookup_table.zip](https://xentaxbackup.github.io/file/3839_lookup_table.zip)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-07-03T19:07:46+00:00
- Post Title: RaiderZ filesystem

Updates!

In response to a request, aluigi has added the msf compression algorithm to [quickbms](http://aluigi.org/quickbms.htm) (from 0.5.2)!

So here is how I've made use of it:

I wrote up the xor table (which i dumped above) into bms - i'm now generating it as the clients are
I wrote up the fileindex parsing into bms (i described this format above)
The final script dumps the entire file system

So the script works for both existing RealSpace3 games - GunZ 2 and RaiderZ.

It does take a while to run - and it uses a few memory_file (including the ~400kb fileindex)

5617 files in 489 seconds (8 minutes)

Again, thanks to aluigi - for his dedication to updating quickbms
[rs3_msf.zip](https://xentaxbackup.github.io/file/4430_rs3_msf.zip)
## Post #3
- Username: elmon
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jul 27, 2011 2:46 am
- Post datetime: 2011-07-26T18:51:28+00:00
- Post Title: RaiderZ filesystem

well, i guess this script is useless without client   
So... Please, could you upload last cbt korean client? As i've understood you have it:)
P.s. Good uploader (for such a big files): [http://filedropper.com](http://filedropper.com) 
P.p.s Biiig thanks for a quickbms script:)
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-27T05:01:04+00:00
- Post Title: RaiderZ filesystem

Google it. It's circulating since people have set up private servers already.
## Post #5
- Username: elmon
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jul 27, 2011 2:46 am
- Post datetime: 2011-07-27T07:02:08+00:00
- Post Title: RaiderZ filesystem

I found it after posting, but that is a client from E3 expo, bause some maps,models,animation etc are missing, and there are some specific maps like SomeLocation(E3)
Im trying to get into korean beta, but i don't have an account on pmang.com, because of lack of kssn's
## Post #6
- Username: Cain142
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jul 27, 2011 5:06 pm
- Post datetime: 2011-07-27T09:20:52+00:00
- Post Title: RaiderZ filesystem

Client can be found here

[http://www.cultureandchaosmmo.com/downl ... taller.exe](http://www.cultureandchaosmmo.com/download/RaiderZ/Raiderz%20Installer.exe)

And what i can see there is no date set for CBT3 korean version yet.
I been browsing their site every day now to get the new client once they release it ill upload it to a host.
## Post #7
- Username: elmon
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jul 27, 2011 2:46 am
- Post datetime: 2011-07-27T14:01:36+00:00
- Post Title: RaiderZ filesystem

wow) guess we got too offtopic 
Ive got a question on fs structure:
Mrf is a all files packed and merged into one big file?

off:@cain142 do you have login at pmang.com?
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-29T02:02:27+00:00
- Post Title: RaiderZ filesystem

Yes. WRS has also written a bms script for the MRF archives. Search the forums for it
## Post #9
- Username: elmon
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jul 27, 2011 2:46 am
- Post datetime: 2011-07-29T07:38:17+00:00
- Post Title: RaiderZ filesystem

It is in this topic >.> (it opens all files mrs and mrf)
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-29T13:52:10+00:00
- Post Title: RaiderZ filesystem

Didn't notice
## Post #11
- Username: elmon
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jul 27, 2011 2:46 am
- Post datetime: 2011-07-29T15:31:01+00:00
- Post Title: RaiderZ filesystem

nice) now all we need - is to create a packer:)

p.s. whats with korean client? our build date is 31.05, thats good, but not enough for us i guess)
## Post #12
- Username: Cain142
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jul 27, 2011 5:06 pm
- Post datetime: 2011-08-03T10:10:10+00:00
- Post Title: RaiderZ filesystem

> Reply from elmon
>
> wow) guess we got too offtopic 
Ive got a question on fs structure:
Mrf is a all files packed and merged into one big file?

off:@cain142 do you have login at pmang.com?

Yes i have a account on pmang

Anyone know why i get error -1 when i try use that BMS unpacker with the unpacking script.
I select script to use "The script posted on this forum" Then file to unpack like system.mrf then folder.
After that i get error and it refuses to unpack anything.
[error.png](https://xentaxbackup.github.io/file/4572_error.png)
## Post #13
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-08-07T16:54:21+00:00
- Post Title: RaiderZ filesystem

> Reply from Cain142
>
> Anyone know why i get error -1 when i try use that BMS unpacker with the unpacking script.
I select script to use "The script posted on this forum" Then file to unpack like system.mrf then folder.
After that i get error and it refuses to unpack anything.

use the script on the fileindex.msf index (because it dumps the entire filesystem)
## Post #14
- Username: rising
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 04, 2011 5:56 am
- Post datetime: 2011-08-14T11:13:16+00:00
- Post Title: RaiderZ filesystem

Hello:
   Nice to meet you,I have seen your topic about RaiderZ filesystem,fllowing your description,I write some code,but it does work fine.
   So execuse me,you meant that fileindex.msf xor lookup_table by your algorithm,right?
   Or lookup_table has a new version?
## Post #15
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-08-14T18:58:51+00:00
- Post Title: RaiderZ filesystem

> Reply from rising
>
> you meant that fileindex.msf xor lookup_table by your algorithm,right?
   Or lookup_table has a new version?

with the fileindex it reads off 4 bytes for the uncompressed size
then a lookup data is made (see my bms script to generate that, or use my dump)
the remaining fileindex data is then run through the function i call the "xor" function (it isn't just an xor though)
then it is decompressed - and the code for that is in quickbms sourcecode (msf.h)

if you're stuck, check the bms version
## Post #16
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-10T16:30:56+00:00
- Post Title: Re: RaiderZ filesystem

This is the same compression used in tales of xillia
## Post #17
- Username: iaw
- Rank: advanced
- Number of posts: 52
- Joined date: Wed Oct 21, 2009 7:52 pm
- Post datetime: 2012-02-15T10:36:16+00:00
- Post Title: Re: RaiderZ filesystem

update!

The new version fileindex.msf ,can't unpack them  


<link removed due forum rules violation>
## Post #18
- Username: kudpro
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 12, 2012 4:40 pm
- Post datetime: 2012-02-15T11:54:21+00:00
- Post Title: Re: RaiderZ filesystem

How to pack back?
## Post #19
- Username: Jesemo
- Rank: Banned
- Number of posts: 3
- Joined date: Fri Apr 13, 2012 2:05 am
- Post datetime: 2012-04-13T18:00:41+00:00
- Post Title: Re: RaiderZ filesystem

Could someone make an mrf unpacker for the Alpha Test NA client? I will provide the fileindex.msf.
## Post #20
- Username: Jesemo
- Rank: Banned
- Number of posts: 3
- Joined date: Fri Apr 13, 2012 2:05 am
- Post datetime: 2012-05-10T05:23:09+00:00
- Post Title: Re: RaiderZ filesystem

Could someone please help?
## Post #21
- Username: Jesemo
- Rank: Banned
- Number of posts: 3
- Joined date: Fri Apr 13, 2012 2:05 am
- Post datetime: 2012-05-10T05:53:07+00:00
- Post Title: Re: RaiderZ filesystem

NO LINKS TO ORIGINAL FILES ALLOWED. Ban. 

These files are from the Alpha Test of RaiderZ PWE.
## Post #22
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-05-29T23:58:17+00:00
- Post Title: Re: RaiderZ filesystem

tiny status update, but I will find time to work on the new clients.

only the initial scrambling has changed (same filelist formats, compression algos)
## Post #23
- Username: Raider
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu May 31, 2012 8:30 pm
- Post datetime: 2012-05-31T12:37:26+00:00
- Post Title: Re: RaiderZ filesystem

This is great! Thanks for working on it WRS.
## Post #24
- Username: Raider
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu May 31, 2012 8:30 pm
- Post datetime: 2012-06-18T21:24:17+00:00
- Post Title: Re: RaiderZ filesystem

WRS, do you have a new status update for us?
## Post #25
- Username: Raider
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu May 31, 2012 8:30 pm
- Post datetime: 2012-06-21T12:05:04+00:00
- Post Title: Re: RaiderZ filesystem

I hope you can help us, like making a guide to let the script unpack the new files.
## Post #26
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-06-23T13:16:21+00:00
- Post Title: Re: RaiderZ filesystem

so after nearly a month of idle progress, i've got something that has dumped the filesystem for me.

i've had to think about to how to package it for XeNTaX, so I'm using aluigi's self-described 'lame patcher' - [http://aluigi.org/mytoolz.htm#lpatch](http://aluigi.org/mytoolz.htm#lpatch) 

you need to read the instructions, and make sure you make a copy of your client's exe before you patch it!

NOTE
if you want to check individual progress, download a debug message viewer like [http://technet.microsoft.com/en-us/sysi ... 96647.aspx](http://technet.microsoft.com/en-us/sysinternals/bb896647.aspx)

edit 4

had the pmang and pwe clients mixed up. hopefully this fixes everything. download: [http://www.sendspace.com/file/ddtsr7](http://www.sendspace.com/file/ddtsr7)


FS Changes

I have defined the fileindex.msf structure (which hasn't changed) as:

```
//	fileindex.msf structure
//	20-bytes
//	
//	NOTE: FILEINDEX_ENTRY records follows a 1-byte compression flag
//
//		3 known types (RaiderZ only uses type 0)
//		
//		0	Compressed		Data should be fed through XorData() before decompressing
//		1	Compressed++	Data needs unscrambling, which converts it to type 0
//		2	Uncompressed	(GUNZ2 FSB) Raw data - BUT the values have been scrambled (TODO)
//
struct FILEINDEX_ENTRY
{
	DWORD size;		// Uncompressed filesize
	DWORD offset;	// MRF file position
	DWORD zsize;	// Size of compressed data
	DWORD xorkey;	// 
	short lenMRFN;	// MRF container name length
	short lenName;	// Filename length
};

```


Files with a compression byte of 0x0:

Are first read into a memory buffer (from their container)
Using the '.xorkey' attribute are xor'd in 32-bit chunks:
Code: Select all	DWORD dBlocks = srcSize >> 2;
	while( dBlocks )
	{
		DWORD tmp;
		tmp = *(DWORD *)srcBuffer; // read 32-bit value
		
		xorkey += tmp;
		tmp ^= xorkey;
		
		*(DWORD *)srcBuffer = tmp; // write 32-bit value
		srcBuffer += 4;
		--dBlocks;
	}


( the remaining bytes are converted to a 32-bit integer then xor'd in the same way )
 The data is then decompressed. I haven't looked any further (http://aluigi.altervista.org/quickbms.htm# comtype scanner) - but some of the xml data is fairly legible after this early step

Files with a compression byte of 0x1 are handled in a similar manner to the fileindex in that the data is sent through a function which does some additional decryption which can alter the expected zsize

The uncompressed files (0x2) in GunZ2 scramble their size values somehow. I've not looked any further into this.


My Z3 module defines 4 functions which are called within the various clients:

GetValues - which returns 2 values that are somehow related to RSA (?)
PartialDec - the function which uses the keys to partial decrypt the data - used by the filelist (any 0x1 comtypes?)
XorData - a very simple xor function (code above) which xors based on the fileindex record
Uncompress - the decompression function

Once the filelist is decrypted (my code does this separately from the client) the 'regular' compressed files (0x0) are xor'ed and decrypted, before saved.
## Post #27
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-07-05T21:25:02+00:00
- Post Title: Re: RaiderZ filesystem

edit Links to the new PMANG open-beta!

[http://file.nowcdn.co.kr/down/NeowizGam ... 070418.exe](http://file.nowcdn.co.kr/down/NeowizGames/RAIDERZ/Full/RaiderZ_full_2012070418.exe)
[http://file.nowcdn.co.kr/down/NeowizGam ... 70418_1.7Z](http://file.nowcdn.co.kr/down/NeowizGames/RAIDERZ/Full/DATA_2012070418_1.7Z)
## Post #28
- Username: skyflox
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 01, 2012 4:55 am
- Post datetime: 2012-08-05T13:44:12+00:00
- Post Title: Re: RaiderZ filesystem

filesystem.msf uses a simple XOR-encrypted key (AD C3 C8 A0 D2 D1 B5 31 ...), which is generated by the program based on the Raiderz.exe arrays, and possibly, the first bytes of filesystem.msf. In the version what I have, the data begin at byte 29h.

Next, the file is decompressed and get a standard structure filesystem.msf described by WRM.

All files are archived as before, are archived. Let us unpack a simple example (rel_const.lua - first file in Script.mrf).

Use XOR = 0x42CFD1B6 (From filesystem.msf) 

Important elements I've highlighted in color.
FE 77 - Encrypted file size control.

```
	int b = 0;
	int len = fileLen;
	while(a<0x20){
	 BYTE bl = data[0];
	 src++;
	 len--;
	 int c = bl & 0x7F;
	 byte cl = a;
	 c = c << cl;
         b = b | c;
	 a +=7;
	 if(bl<0x80) break;
	};

```

As a result, we obtain the value of 3B FF (equal to the value of filesystem.msf), and the Data pointer moves to the top of the archival data.

F0 42 - control code, in this case, "write the 42h byte to uncompressed data."

OD 29 - back to 29h bytes and copy out 7h bytes ("\0x0aCONST_")

64 - write the 1Ah bytes to the uncompressed data

Thus, using the simple instructions step by step we restore the original file.


```
	LPBYTE ldic = dic;
	LPBYTE ldic2 = dic2;
	ldic +=a*2;
	BYTE cl = *(BYTE *)ldic;
	WORD b = *(WORD *)ldic;
	WORD edx = (b >> 11);
	data++;dataLen--;
	DWORD ebp = *(DWORD *)data;
	ldic2 +=edx*4;
	DWORD edi = *(DWORD *)ldic2;
	data+=edx;dataLen-=edx;
	edi &=ebp;
	edx = cl;
	if(a & 3 ){
	 //Insert text from buffer
	}else{
	 //Copy text from archive
	}

```


dic,dic2- dictionary from Raiderz.exe

Extracting the data - easy enough, but here is the creation of the packer can be difficult.
## Post #29
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-08-05T14:08:27+00:00
- Post Title: Re: RaiderZ filesystem

hi skyflox, i appreciate your input!

can you tell me  which version of raiderz is this from? (EU?)

edit
just discovered the 34991 download links..
[http://download.frogster-online.com/FOG ... etup-1.bin](http://download.frogster-online.com/FOG/raiderz/RaiderZ_1_0_0_34991_Setup/RaiderZSetup-1.bin)
[http://download.frogster-online.com/FOG ... etup-2.bin](http://download.frogster-online.com/FOG/raiderz/RaiderZ_1_0_0_34991_Setup/RaiderZSetup-2.bin)
## Post #30
- Username: skyflox
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 01, 2012 4:55 am
- Post datetime: 2012-08-05T14:32:39+00:00
- Post Title: Re: RaiderZ filesystem

I'm not sure, but I think that the EU.

Fileindex from this version (Size = 898328b)
[http://dl.dropbox.com/u/96128597/fileindex.msf](http://dl.dropbox.com/u/96128597/fileindex.msf)

Unpacked 
[http://dl.dropbox.com/u/96128597/fileindex_up.msf](http://dl.dropbox.com/u/96128597/fileindex_up.msf)
## Post #31
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-08-06T20:03:26+00:00
- Post Title: Re: RaiderZ filesystem

i have finally downloaded the client (r34991)!

skyflox has more detail on the extraction here - [viewtopic.php?p=76680#p76680](http://forum.xentax.com/viewtopic.php?p=76680#p76680)
but my dumper uses exactly the same code, so nothing has changed

the xor-ing used by the fileindex is in-use for Z3Ex - [https://gist.github.com/3040921](https://gist.github.com/3040921)

finally,
there is another beta test coming out on the 9th with a different publisher.
[Z3Ex_34991.zip](https://xentaxbackup.github.io/file/5645_Z3Ex_34991.zip)
## Post #32
- Username: archonus
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Mar 29, 2009 5:21 am
- Post datetime: 2012-08-07T21:16:12+00:00
- Post Title: Re: RaiderZ filesystem

is just me or doesnt works on win7 ?
on winxp works fine
## Post #33
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-08-09T21:47:16+00:00
- Post Title: Re: RaiderZ filesystem

> Reply from archonus
>
> is just me or doesnt works on win7 ?
on winxp works fine

my dump tool?

Also, skyflox - can you recognize that decompression method? is it lzx or similar?

edit
sourcecode for my z3ex.dll project: [https://github.com/x1nixmzeng/z3-tools/ ... x/main.cpp](https://github.com/x1nixmzeng/z3-tools/blob/master/Z3Ex/main.cpp)
## Post #34
- Username: archonus
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Mar 29, 2009 5:21 am
- Post datetime: 2012-08-11T20:42:16+00:00
- Post Title: Re: RaiderZ filesystem

Yes, your dump tool

By the way this is for unpack  , can you do a pack tool ?
## Post #35
- Username: archonus
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Mar 29, 2009 5:21 am
- Post datetime: 2012-08-12T23:25:43+00:00
- Post Title: Re: RaiderZ filesystem

this tool doesnt work on last PWE client [http://raiderz.perfectworld.com](http://raiderz.perfectworld.com)
only works on frogster
## Post #36
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-08-20T14:47:35+00:00
- Post Title: Re: RaiderZ filesystem

> Reply from archonus
>
> this tool doesnt work on last PWE client http://raiderz.perfectworld.com
only works on frogster

see [http://forum.ragezone.com/f698/raiderz- ... ost7193706](http://forum.ragezone.com/f698/raiderz-filesystem-extractor-855406/index2.html#post7193706)
## Post #37
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-09-04T20:34:44+00:00
- Post Title: Re: RaiderZ filesystem

Z3Ex.dll is now obsolete.

I am now finishing up a standalone new tool which can extract all existing client releases:

[https://github.com/x1nixmzeng/z3ResEx#download](https://github.com/x1nixmzeng/z3ResEx#download)

if you were curious about the decompression (skyflox outlines it [here](http://forum.xentax.com/viewtopic.php?p=76680#p76680)) - then I have completely reversed the RLE [z3Rle.h](https://github.com/x1nixmzeng/z3ResEx/blob/master/src/z3ResEx/z3Rle.h)
## Post #38
- Username: wimmeke001
- Rank: n00b
- Number of posts: 11
- Joined date: Sun May 13, 2012 2:23 am
- Post datetime: 2012-09-12T22:39:11+00:00
- Post Title: Re: RaiderZ filesystem

if you youse dumptool the compleet client get unpacked in the folder dumpdata 
then you get al model (elu files) and compleet dds and tga textures but it take some time before the client is compleet unpacked here som samples of elu files
[http://www.mediafire.com/?klk311wq5ff7e3s](http://www.mediafire.com/?klk311wq5ff7e3s)
[http://www.mediafire.com/?h7n8nglultsguas](http://www.mediafire.com/?h7n8nglultsguas)
## Post #39
- Username: Arkax
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 15, 2014 2:56 am
- Post datetime: 2014-04-14T19:39:17+00:00
- Post Title: Re: RaiderZ filesystem

Hi guy,

Im trying to use your tool but he dsnt work with the structure of this FileIndex
Its not the PWE client
Can you please add this Key encryption ?


Thx in advance 

Link of File:
[https://dl.dropboxusercontent.com/u/102 ... ildver.mvf](https://dl.dropboxusercontent.com/u/102264163/buildver.mvf)
[https://dl.dropboxusercontent.com/u/102 ... lehash.msf](https://dl.dropboxusercontent.com/u/102264163/filehash.msf)
[https://dl.dropboxusercontent.com/u/102 ... eindex.msf](https://dl.dropboxusercontent.com/u/102264163/fileindex.msf)
