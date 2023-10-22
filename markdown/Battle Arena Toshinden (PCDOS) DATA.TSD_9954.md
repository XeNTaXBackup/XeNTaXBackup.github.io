## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2012-12-15T11:43:09+00:00
- Post Title: Battle Arena Toshinden (PC/DOS) DATA.TSD

Practically all game data is stored in DATA.TSD, including music in HMI format, models in ASC, textures in PCX and BMP, audio in RAW, and so forth. The only problem is that all data is compressed. Header starts with 4D 46 49 4c "MFIL" then followed by that is the file index, thus how I know the contents. Compression method unknown but suspecting LZW or derivative.

Due to the new rules I can't submit the archive here so it will have to be elsewhere or you can get the game itself pretty easily, it isn't big.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-12-21T23:11:05+00:00
- Post Title: Battle Arena Toshinden (PC/DOS) DATA.TSD

I got stuck on debugging this   

The file count (3250) is read in (at least referenced) in segment 0160 at address 001C456F

```

0160:001C456F  mov  edi,[esp+0008]             ss:[0030A874]=00000CB2 EAX:00000004 EBX:00000004 ECX:00000000 EDX:00000000 ESI:0023E4AA EDI:0024E5C0 EBP:0024B9F4 ESP:0030A86C DS:0168 ES:0168 FS:0000 GS:0168 SS:0168 CF:0 ZF:1 SF:0 OF:0 AF:0 PF:1 IF:1
```
## Post #3
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2012-12-30T02:24:09+00:00
- Post Title: Battle Arena Toshinden (PC/DOS) DATA.TSD

Hm... perhaps I underestimated the form of compression, it may be some oddball proprietary compression for all I know. But at least there's the file count so it adds to what is known. Thanks for the effort, at least!  I'm mostly interested in the music since it seems to be a direct conversion of the arcade soundtrack.
## Post #4
- Username: blugodzia
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 05, 2011 11:23 pm
- Post datetime: 2013-08-19T19:35:47+00:00
- Post Title: Battle Arena Toshinden (PC/DOS) DATA.TSD

Hello.

I was sniffing through this datafile (DATA.TSD) a couple years ago and i've found one uncompressed file.
It is bitmap file: EIJI1R\05_HIP.UMP at offset: 2 409 835, filesize: 17 462.
Compressed version of this file is: EIJI1R\05_HIP.BMP at offset 2 475 951, compressed filesize is: 5 695.
I was trying to figure out what kind of LZ compression it is, but i failed and gave up. 
Maybe you have more skills to figure it out by looking into those two files.
Probably these files in DATA.TSD are also encrypted.

Good luck.
## Post #5
- Username: blugodzia
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 05, 2011 11:23 pm
- Post datetime: 2013-08-19T19:42:35+00:00
- Post Title: Battle Arena Toshinden (PC/DOS) DATA.TSD

Ugh, i forgot.

More information on DATA.TSD, maybe this will help.

Header
Magic : char[4] = MFIL
ItemCount : longint

Item
Filename : char[64] (with path)
Offset : longint
Size : longint
UnpackedSize : longint

--------------------------
Added 02/01/2017

Maybe someone has already figured it out, but finally...   
With a little help from QuickBMS tool I managed to figure it out. 
Compression scheme: TITUS_LZW. No encryption.

Below QuickBMS script, which is working on both: DEMO and Retail versions.

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "MFIL"
get FILES long

for i = 0 < FILES

	getdstring NAME 0x40
	get OFFSET long
	get ZSIZE long
	get SIZE long

	savepos INFO
	goto OFFSET

	if SIZE == ZSIZE
		comtype copy
		log NAME OFFSET SIZE
	else
		comtype TITUS_LZW
		clog NAME OFFSET ZSIZE SIZE
	endif

	goto INFO

next i
```

Happy looking into content files and Happy 2017.
