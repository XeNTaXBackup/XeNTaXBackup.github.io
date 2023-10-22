## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-08-18T01:51:14+00:00
- Post Title: Saints row IV ps3_vpp.

Has anyone taken a look at this?

PM me for sample.
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-08-18T13:04:47+00:00
- Post Title: Saints row IV ps3_vpp.

Can i have a see?
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-08-18T13:17:34+00:00
- Post Title: Saints row IV ps3_vpp.

PM sent.
## Post #4
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-08-18T14:59:52+00:00
- Post Title: Saints row IV ps3_vpp.

Here you go then, it seems to work fine although some of the extracted files may be compressed. I'm not sure what compression is used in this game!

```
# Script v1.1
# By Gh0stblade!
# Thanks Chrrox for you know what (:

endian big

IDSTRING "\x51\x89\x0A\xCE"

get VERSION long		#0xA
get HASH long			#Possible checksum? i hope not!
get VPP_SIZE long		#Size of the full archive
get NULL00 long			#Always 00 00 00 00
get FILES long			#The file count!
get PTR_NAMES long		#0x28 + this is the offset to the names table
get PTR_DATA long 		#0x28 + PTR_NAMES + this is the offset to the data start
get DSIZE long			#Size of the data section
get PADDING long		#Padding always 0xFFFFFFFF

#Each file table entry is 0x18 in length!
for i = 0 < FILES

	get NAME_OFF long	#This is the relative name offset relative to base offset PTR_NAMES + 0x28
	get NULL01 long		#Always 00 00 00 00
	get OFFSET long		#This is the relative data offset relative to base offset 0x28 + PTR_NAMES + PTR_DATA
	get SIZE long		#The size of the file!
	get PADDING long	#Padding always 0xFFFFFFFF
	get UNK00 long		#Always 00 00 00 01

	#Get the correct offset and read the name string!
	math NAME_OFF += 0x28
	math NAME_OFF += PTR_NAMES
	savepos TEMP
	goto NAME_OFF
	get NAME string
	goto TEMP

	#Get the correct offset for the data!
	math OFFSET += 0x28
	math OFFSET += PTR_NAMES
	math OFFSET += PTR_DATA

	log NAME OFFSET SIZE
next i

```
## Post #5
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2013-08-18T15:10:39+00:00
- Post Title: Saints row IV ps3_vpp.

Seems it's used deflate compression, i'm not sure. Aluigi's offzip can decompress some data but not all
## Post #6
- Username: CRACKbomber
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Nov 10, 2011 8:13 am
- Post datetime: 2013-08-21T19:17:45+00:00
- Post Title: Saints row IV ps3_vpp.

> Reply from Gh0stBlade
>
> Here you go then, it seems to work fine although some of the extracted files may be compressed. I'm not sure what compression is used in this game!
Code: Select all# [PS3] Saints Row IV Unpacker [.VPP]
# Script v1.1
# By Gh0stblade!
# Thanks Chrrox for you know what (:
# Fixed by CRACKbomber
endian big
    get IDENT long                  #File ident - 0x00
    get VERSION long                #10 for SRIV - 0x04
    get HASH long                   #Checksum - 0x08 calculated here http://pastebin.com/Parpjz8W
    get VPP_SIZE long               #File size - 0x0C
    get FLAGS long                  #Flags - 0x10
    get FILES long                  #Number of files 0x014
    get DIR_SIZE long               #Directory size 0x18
    get FILENAME_SIZE long          #Filename size 0x1C
    get DSIZE long                  #Size of the data section 0x20
    get COMPSIZE long               #Size of the compressed data section 0x24

    #Each file table entry is 0x18 in length!
    for i = 0 < FILES

        get NAME_OFF long       #This is the relative name offset relative to base offset PTR_NAMES + 0x28
        get PADDING long        #PADDING
        get OFFSET long         #This is the relative data offset relative to base offset 0x28 + PTR_NAMES + PTR_DATA
        get SIZE long           #The size of the file!
        get COMPSIZE long       #Compressed data size
        get FLAGS short         #Flags of the file
        get ALIGNMENT short     #Alignment of the file either 1 or 16
        
        #Get the correct offset and read the name string!
        math NAME_OFF += 0x28
        math NAME_OFF += DIR_SIZE
        savepos TEMP
        goto NAME_OFF
        get NAME string
        goto TEMP

        #Get the correct offset for the data!
        math OFFSET += 0x28
        math OFFSET += DIR_SIZE
        math OFFSET += FILENAME_SIZE

        log NAME OFFSET SIZE
        next i

Fixed your script with more accurate names. Also the compression is zlib.
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-08-21T19:22:38+00:00
- Post Title: Saints row IV ps3_vpp.

its the same as a psarc file. they just modified it slightly.
## Post #8
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-08-21T19:24:16+00:00
- Post Title: Saints row IV ps3_vpp.

does it work for X360 as well ?
## Post #9
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-08-21T20:07:42+00:00
- Post Title: Saints row IV ps3_vpp.

Yes i would like to know if 360 would be supported as well.
## Post #10
- Username: CRACKbomber
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Nov 10, 2011 8:13 am
- Post datetime: 2013-08-22T04:35:49+00:00
- Post Title: Saints row IV ps3_vpp.

Yes, the PS3 and XBOX files are identical, just different endings.
## Post #11
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-08-22T20:53:33+00:00
- Post Title: Saints row IV ps3_vpp.

Well a few days ago i worked along side with chrrox to try get the decompression working. We did update the script however, I don't know why it's not decompressing some files so I'll just post up what we got so far.

It's extremely messy though but I'll leave it just in case someone else can fix it!

Edit: Maybe it's due to the byte alignment which was stated in the script edit by the other guy? Someone could investigate maybe, just a thought!

```
# Script v1.2
# By Gh0stblade!
# Thanks Chrrox for you know what (:

endian big
comtype unzip_dynamic

IDSTRING "\x51\x89\x0A\xCE"

get VERSION long        #0xA
get HASH long           #Possible checksum? i hope not!
get VPP_SIZE long       #Size of the full archive
get ATYPE long          #Archive type 00 00 00 00 = Uncompressed; 00 00 50 03 = Compressed
get FILES long          #The file count!
get PTR_NAMES long      #0x28 + this is the offset to the names table
get PTR_DATA long       #0x28 + PTR_NAMES + this is the offset to the data start
get DSIZE long          #Size of the data section
get DZSIZE long         #Size of the compressed data section if compressed or -1 if uncompressed!

#Each file table entry is 0x18 in length!
set OFFSET2 0

for i = 0 < FILES
   	get NAME_OFF long    #This is the relative name offset relative to base offset PTR_NAMES + 0x28
   	get NULL01 long      #Always 00 00 00 00
   	get OFFSET long      #This is the relative data offset relative to base offset 0x28 + PTR_NAMES + PTR_DATA
   	get SIZE long        #The size of the file!
   	get ZSIZE long       #The compressed size of the file if compressed or -1 if uncompressed!
   	get UNK00 long       #Always 00 00 00 01

   	#Get the correct offset and read the name string!
	savepos TEMP
   	math NAME_OFF += 0x28
   	math NAME_OFF += PTR_NAMES
   	goto NAME_OFF
   	get NAME string
   	goto TEMP
	
	#if it's not the uncompressed archive
	if ATYPE != 0x00000000
		set OFFSET OFFSET2
		math OFFSET += 0x28
   		math OFFSET += PTR_NAMES
   		math OFFSET += PTR_DATA
		math OFFSET += 0x8
		math OFFSET2 += ZSIZE
		math ZSIZE -= 0x8
   		clog NAME OFFSET ZSIZE SIZE
	else
   		#Get the correct offset for the data!
   		math OFFSET += 0x28
   		math OFFSET += PTR_NAMES
   		math OFFSET += PTR_DATA
		log NAME OFFSET SIZE
	endif
next i
```
## Post #12
- Username: CRACKbomber
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Nov 10, 2011 8:13 am
- Post datetime: 2013-08-22T21:28:17+00:00
- Post Title: Saints row IV ps3_vpp.

> Reply from Gh0stBlade
>
> Well a few days ago i worked along side with chrrox to try get the decompression working. We did update the script however, I don't know why it's not decompressing some files so I'll just post up what we got so far.

It's extremely messy though but I'll leave it just in case someone else can fix it!

Edit: Maybe it's due to the byte alignment which was stated in the script edit by the other guy? Someone could investigate maybe, just a thought!
Code: Select all# [PS3] Saints Row IV Unpacker [.VPP]
# Script v1.2
# By Gh0stblade!
# Thanks Chrrox for you know what (:

endian big
comtype unzip_dynamic

IDSTRING "\x51\x89\x0A\xCE"

get VERSION long        #0xA
get HASH long           #Possible checksum? i hope not!
get VPP_SIZE long       #Size of the full archive
get ATYPE long          #Archive type 00 00 00 00 = Uncompressed; 00 00 50 03 = Compressed
get FILES long          #The file count!
get PTR_NAMES long      #0x28 + this is the offset to the names table
get PTR_DATA long       #0x28 + PTR_NAMES + this is the offset to the data start
get DSIZE long          #Size of the data section
get DZSIZE long         #Size of the compressed data section if compressed or -1 if uncompressed!

#Each file table entry is 0x18 in length!
set OFFSET2 0

for i = 0 < FILES
   	get NAME_OFF long    #This is the relative name offset relative to base offset PTR_NAMES + 0x28
   	get NULL01 long      #Always 00 00 00 00
   	get OFFSET long      #This is the relative data offset relative to base offset 0x28 + PTR_NAMES + PTR_DATA
   	get SIZE long        #The size of the file!
   	get ZSIZE long       #The compressed size of the file if compressed or -1 if uncompressed!
   	get UNK00 long       #Always 00 00 00 01

   	#Get the correct offset and read the name string!
	savepos TEMP
   	math NAME_OFF += 0x28
   	math NAME_OFF += PTR_NAMES
   	goto NAME_OFF
   	get NAME string
   	goto TEMP
	
	#if it's not the uncompressed archive
	if ATYPE != 0x00000000
		set OFFSET OFFSET2
		math OFFSET += 0x28
   		math OFFSET += PTR_NAMES
   		math OFFSET += PTR_DATA
		math OFFSET += 0x8
		math OFFSET2 += ZSIZE
		math ZSIZE -= 0x8
   		clog NAME OFFSET ZSIZE SIZE
	else
   		#Get the correct offset for the data!
   		math OFFSET += 0x28
   		math OFFSET += PTR_NAMES
   		math OFFSET += PTR_DATA
		log NAME OFFSET SIZE
	endif
next i
Once again, read my post. It's zlib. and "ATYPE" is just flags. You have to use bit operators the see if a flag is set. (1 == compressed, 2 == condensed)
## Post #13
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-08-22T21:59:17+00:00
- Post Title: Saints row IV ps3_vpp.

> Reply from CRACKbomber
>
> Gh0stBlade wrote:Well a few days ago i worked along side with chrrox to try get the decompression working. We did update the script however, I don't know why it's not decompressing some files so I'll just post up what we got so far.

It's extremely messy though but I'll leave it just in case someone else can fix it!

Edit: Maybe it's due to the byte alignment which was stated in the script edit by the other guy? Someone could investigate maybe, just a thought!
Code: Select all# [PS3] Saints Row IV Unpacker [.VPP]
# Script v1.2
# By Gh0stblade!
# Thanks Chrrox for you know what (:

endian big
comtype unzip_dynamic

IDSTRING "\x51\x89\x0A\xCE"

get VERSION long        #0xA
get HASH long           #Possible checksum? i hope not!
get VPP_SIZE long       #Size of the full archive
get ATYPE long          #Archive type 00 00 00 00 = Uncompressed; 00 00 50 03 = Compressed
get FILES long          #The file count!
get PTR_NAMES long      #0x28 + this is the offset to the names table
get PTR_DATA long       #0x28 + PTR_NAMES + this is the offset to the data start
get DSIZE long          #Size of the data section
get DZSIZE long         #Size of the compressed data section if compressed or -1 if uncompressed!

#Each file table entry is 0x18 in length!
set OFFSET2 0

for i = 0 < FILES
   	get NAME_OFF long    #This is the relative name offset relative to base offset PTR_NAMES + 0x28
   	get NULL01 long      #Always 00 00 00 00
   	get OFFSET long      #This is the relative data offset relative to base offset 0x28 + PTR_NAMES + PTR_DATA
   	get SIZE long        #The size of the file!
   	get ZSIZE long       #The compressed size of the file if compressed or -1 if uncompressed!
   	get UNK00 long       #Always 00 00 00 01

   	#Get the correct offset and read the name string!
	savepos TEMP
   	math NAME_OFF += 0x28
   	math NAME_OFF += PTR_NAMES
   	goto NAME_OFF
   	get NAME string
   	goto TEMP
	
	#if it's not the uncompressed archive
	if ATYPE != 0x00000000
		set OFFSET OFFSET2
		math OFFSET += 0x28
   		math OFFSET += PTR_NAMES
   		math OFFSET += PTR_DATA
		math OFFSET += 0x8
		math OFFSET2 += ZSIZE
		math ZSIZE -= 0x8
   		clog NAME OFFSET ZSIZE SIZE
	else
   		#Get the correct offset for the data!
   		math OFFSET += 0x28
   		math OFFSET += PTR_NAMES
   		math OFFSET += PTR_DATA
		log NAME OFFSET SIZE
	endif
next i
Once again, read my post. It's zlib. and "ATYPE" is just flags. You have to use bit operators the see if a flag is set. (1 == compressed, 2 == condensed)

I know the compression used is Zlib however there's a reason why there are decompression issues. If it's as simple as it just being Zlib then it would decompress fine. I have no need to read your post, i skimmed it because I don't have the time to compare the scripts to see what you changed. 

You have updated the script and mine is obviously outdated and lacks the things you may have found. I understand what you mean with the flags, I just think you need to be a little less forceful (if that's the word) with the "it's this, it's this, this this, read". I have simply done what I can with the script and I clearly stated I'm discontinuing it so IF you are interested in fixing the issues then go ahead I don't need to be told what's what because I'm not interested in continuing anymore since I've done what I can with this.

I will clarify that this script has not been touched for a few days and it's just rough stuff I did randomly and clarify further i do not need to be told to read things. I just feel that you're being slightly rude to me so I should let you off this time, just don't ever try to dictate to me or there will be problems.

Regards.
## Post #14
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-08-24T19:11:32+00:00
- Post Title: Saints row IV ps3_vpp.

im almost sure that for x360 it will be xmem_decompress and it will compatible with qbms
## Post #15
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2013-08-29T01:36:03+00:00
- Post Title: Saints row IV ps3_vpp.

Note: I have only tested this on the xbox360 files.

Is everyone sure this is zlib?  I know it does provide the decompressed and compressed sizes in the header sections for each file, but no dll/quickbms is actually decompressing the data.  

The current script does not decompress, only removes the first 8 bytes of the compressed chunks.  Correct me if I'm wrong.

This may be some kind of header-less zlib.  I've tried ICSharpZipLib's SetInput() and Inflate() methods with the Inflater parameter "noZlibHeaderOrFooter" set to true.

Another possibility is a different dictionary.
--I'm not sure, but (aNeedDictionary:.string "need dictionary") in the disassembly doesn't have a xref.  Maybe this means a different dictionary is not used?

Does anyone know of another compression off hand that the decompressed size and compressed size are needed for decompression?
## Post #16
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-08-29T02:57:49+00:00
- Post Title: Re: Saints row IV ps3_vpp.

I might get to it this weekend.
Just look at the psarc format it is 99% identical to it.
its just inflate compression chunks.
## Post #17
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2013-08-29T12:41:16+00:00
- Post Title: Re: Saints row IV ps3_vpp.

Has nothing to do with psarc.
## Post #18
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2013-08-29T18:00:37+00:00
- Post Title: Re: Saints row IV ps3_vpp.

I'm getting some similar results as quickbms using ICSharpCode.SharpZipLib.Zip.Compression; as some of the files the bms script tries seem to start inflating.  
I told the inflater's SetInput() to use from the 8th byte of of the chunk the container is referring to.
I also got a similar result by trying from the 11th byte in another file.  

I get these results after the inflate attempt on patch_compressed.vpp_xbox2 from TU1.  
(The Title Update can be found on xbuc.net if anyone wants to try on the same file.  Just search for its media id 130ABF66.)

jump_sm.xtbl
0x31 0x00 0x00 0x00 0x00 .....
pause_save_game.lua
0x31 0x00 0x31 0x00 0x31 0x00 0x31 0x00 0x31 0x00 0x31 0x32 0x00 0x00 0x00 0x00 .....

Its like the inflater is trying because it doesn't throw an exception when I tell it where the real zlib data starts, but I may not be passing the correct chunk size or not looping correctly.

Anyone get similar results trying to inflate headerless zlib data?
## Post #19
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-08-29T18:44:40+00:00
- Post Title: Re: Saints row IV ps3_vpp.

> Reply from Rick
>
> Has nothing to do with psarc.
are you working on an editor?
If so i wont make a quickbms script.
from what i have seen its just using zlib chunks very simple format.
## Post #20
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-08-29T19:20:16+00:00
- Post Title: Re: Saints row IV ps3_vpp.

Here tools by ThomasJepp for pack/unpack packs and localization.. Source code [here](https://src.tomjepp.co.uk/hg/ThomasJepp.SaintsRow)
[ThomasJepp.SaintsRow_IV_Tools-rev12.7z](https://xentaxbackup.github.io/file/6574_ThomasJepp.SaintsRow_IV_Tools-rev12.7z)
## Post #21
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-08-29T19:24:40+00:00
- Post Title: Re: Saints row IV ps3_vpp.

I thought on Rick's site Volition said they were going to (and have released some minor) extracting tools. The fact that they said they were going to release file format information, extracting tools, and an importer/exporter, I think we should all just wait to save us from wasting a lot of time. Then people can figure out the PS3 and XBox360 formats after the PC tools are released.
## Post #22
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-08-29T20:06:26+00:00
- Post Title: Re: Saints row IV ps3_vpp.

cool tools released here was what i was working on in bms that is not needed. Also i dint put in padding that i think is needed in the format.

```
comtype DEFLATE_NOERROR
IDSTRING "\x51\x89\x0A\xCE\x00\x00\x00\x0A"

get checksum long         
get ARCSIZE long
get UNKSIZE long
get FILES long
get NOFF long
get TOFF long
get TASIZE long
get TAZSIZE long
math NOFF + 0x28
math TOFF += NOFF
savepos TMP
for i = 0 < 2
   goto TMP
   #print "%TMP%"
   get NAME_OFF long   
   get MEM_OFFSET longlong
   get TSIZE long
   get TZSIZE long
   set FSIZE 0
   get COMPTYPE long
   savepos TMP
   math NAME_OFF + NOFF
   goto NAME_OFF
   #print "%NAME_OFF%"
   get NAME STRING
   if TSIZE != TZSIZE
   append
   Do
   goto TOFF
   get ZSIZE short
   math TOFF + ZSIZE
   math TOFF + 8
   get NULL short
   get SIZE long
   savepos OFFSET
   #print "%TOFF%, %OFFSET% , %ZSIZE% , %SIZE%"
   clog MEMORY_FILE OFFSET ZSIZE SIZE
   get FSIZE asize MEMORY_FILE
   #print "%FSIZE%, %TSIZE%"
   while FSIZE < TSIZE
   append
   log NAME 0 TSIZE MEMORY_FILE
   else
   goto TOFF
   savepos OFFSET
   log NAME OFFSET TSIZE
   math TOFF + TSIZE
   endif
next i
```
## Post #23
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-08-29T20:17:50+00:00
- Post Title: Re: Saints row IV ps3_vpp.

Here is Editor for X360

What can this editor do?
As of the current version (0.0.4), it can:
  - Open Archive
  - Extract Files
  - Replace Files
  - Save/Rebuild Archive

Download Binary :

```
http://www.mediafire.com/download/enhqu8jo0ylxqb6/SR4_VPP.exe
```


Download Source

```
http://www.mediafire.com/download/xxcjtdwecl58j9w/SR4_VPP_%5BSource%5D_%5BC%23%5D.zip
```


Autor : XBLToothPik


It does not decompress files, coz he does not know what compression is used. If you know this plsease advice and he will implement it
## Post #24
- Username: XBLToothPik
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Aug 23, 2013 1:44 am
- Post datetime: 2013-08-29T20:39:44+00:00
- Post Title: Re: Saints row IV ps3_vpp.

@Michalss

The editor isn't complete & not everything in the source is right as of now.  Been waiting on more info before I finish it.
## Post #25
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-08-29T21:56:32+00:00
- Post Title: Re: Saints row IV ps3_vpp.

somebody said xbox and ps3 files are identical just different endian, so i'm assuming zlib. post a screenshot of the hex where the compressed data starts. the PC files contain the zlib prefix 78DA so i don't think the xbox one will have the missing prefix. if it's a different compression i would first try one of the LZOs or the xmemcompress as they are fairly common to the xbox.
## Post #26
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2013-08-30T00:39:11+00:00
- Post Title: Re: Saints row IV ps3_vpp.

> Reply from howfie
>
> somebody said xbox and ps3 files are identical just different endian, so i'm assuming zlib. post a screenshot of the hex where the compressed data starts. the PC files contain the zlib prefix 78DA so i don't think the xbox one will have the missing prefix. if it's a different compression i would first try one of the LZOs or the xmemcompress as they are fairly common to the xbox.

The compressed data in the xbox360 file does not contain a regular zlib header.  It may have some kind of truncated zlib header though.
I've yet to try XMemDecompress(), but was thinking about trying it next.

Here are some of the methods I've tried in C#....
Props to all who have been working on this. 

This one attempts to use an ICSharpZipLib Inflater.  I get the same results as Gh0stBlade's v1.2 bms script on some files.

```
{
    Inflater inflater = new Inflater(true);
    using (var inputStream = new MemoryStream(inputData))
    using (var ms = new MemoryStream())
    {
        var inputBuffer = new byte[4096];
        var outputBuffer = new byte[4096];        

        while (inputStream.Position < inputData.Length)
        {
            var read = inputStream.Read(inputBuffer, 0, inputBuffer.Length);

            inflater.SetInput(inputBuffer, 11, (read - 11));

            while (inflater.IsNeedingInput == false)
            {
                var written = inflater.Inflate(outputBuffer, 0, outputBuffer.Length);

                if (written == 0)
                    break;

                ms.Write(outputBuffer, 0, written);
            }

            if (inflater.IsFinished == true)
                break;
        }

        inflater.Reset();

        return ms.ToArray();
    }
}

```


The next one I pulled from Rick's Volition source.  This method was returning an error something like bad header checksum, as I think it attempts to decompress using a normal zlib header.

```
{
    byte[] resBuffer = null;

    MemoryStream mInStream = new MemoryStream(zLibCompressedBuffer);
    MemoryStream mOutStream = new MemoryStream(zLibCompressedBuffer.Length);
    InflaterInputStream infStream = new InflaterInputStream(mInStream);

    mInStream.Position = 0;

    try
    {
        byte[] tmpBuffer = new byte[zLibCompressedBuffer.Length];
        int read = 0;

        do
        {
            read = infStream.Read(tmpBuffer, 0, tmpBuffer.Length);
            if (read > 0)
                mOutStream.Write(tmpBuffer, 0, read);

        } while (read > 0);

        resBuffer = mOutStream.ToArray();
    }
    finally
    {
        infStream.Close();
        mInStream.Close();
        mOutStream.Close();
    }

    return resBuffer;
}

```


The next one I tried is pulled from the SR4 VPP source posted above.  This one returned similar errors (broken uncompressed block, unknown block type).

```
{
    var compressedStream = new MemoryStream(data);
    var zipStream = new DeflateStream(compressedStream, CompressionMode.Decompress);

    var resultStream = new MemoryStream();

    var buffer = new byte[4096];
    int read;

    while ((read = zipStream.Read(buffer, 0, buffer.Length)) > 0)
        resultStream.Write(buffer, 0, read);

    return resultStream.ToArray();
}

```


Another one I tried is based on the ThomasJepp source posted above. This code specifically tests jump_sm.xtbl from TU1 on the xbox.

```
Stream stream = File.OpenRead(this.textBox1.Text);
Stream DataStream;
stream.Read(fileTmp, 0, fileTmp.Length);
FileStream fs = new FileStream(currentPath + "\\" + Path.GetFileNameWithoutExtension(currentFile) + ".test.bin", FileMode.Create, FileAccess.Write);
using (MemoryStream tempStream = new MemoryStream(fileTmp))
{
    using (Stream s = new ZlibStream(tempStream, CompressionMode.Decompress, true))
    {
        byte[] uncompressedData = new byte[64411];
        s.Read(uncompressedData, 0, uncompressedData.Length);
        DataStream = new MemoryStream(uncompressedData);
        DataStream.CopyTo(fs);
    }
}
fs.Close();

```


I also tried some other quick tests using a few different methods.  Again with various errors.

```
FileStream s1 = new FileStream(this.textBox1.Text, FileMode.Open, FileAccess.Read);
FileStream sw1 = new FileStream(this.textBox1.Text + ".test.bin", FileMode.Create, FileAccess.Write);
DeflateStream ds1 = new DeflateStream(s1, CompressionMode.Decompress);
ds1.CopyTo(sw1);
ds1.Dispose();
s1.Close();
sw1.Close();
---------------------------------------------------------------------------------------------------
byte[] dst = new byte[UInt32.Parse(vx2SectionTable[(int)i][2])];
Inflater ifr = new Inflater(true);
ifr.SetInput(fileTmp, 8, (fileTmp.Length - 8));
ifr.Inflate(dst, 0, dst.Length);
File.WriteAllBytes(currentPath + "\\" + Path.GetFileNameWithoutExtension(currentFile) + "_compressed_files\\decompressed\\" + vx2NamesTable[(int)i], dst);
ifr.Reset();
---------------------------------------------------------------------------------------------------
byte[] dst = new byte[UInt32.Parse(vx2SectionTable[(int)i][2])];
[DllImport("zlib1.dll", CallingConvention = CallingConvention.Cdecl)]
static extern int uncompress(byte[] dest, ref uint destLen, byte[] source, uint sourceLen);
uint dstSize = UInt32.Parse(vx2SectionTable[(int)i][2]);
uint srcSize = UInt32.Parse(vx2SectionTable[(int)i][3]);
uncompress(dst, ref dstSize, fileTmp, (uint)srcSize);
File.WriteAllBytes(currentPath + "\\" + Path.GetFileNameWithoutExtension(currentFile) + "_compressed_files\\decompressed\\" + vx2NamesTable[(int)i], dst);
---------------------------------------------------------------------------------------------------

```


I'm not using the alignment or compression flags that look like they are there in the header sections.  Has anyone made any progress on inflating?
Its probably something simple that I'm not doing.
## Post #27
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-08-30T02:02:14+00:00
- Post Title: Re: Saints row IV ps3_vpp.

anyone got an xbox sample?
## Post #28
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2013-08-30T02:04:28+00:00
- Post Title: Re: Saints row IV ps3_vpp.

> Reply from howfie
>
> anyone got an xbox sample?

You can grab one from xbuc.net.  Search for 130ABF66 in the search bar and unpack the downloaded file with wxpirs or another container tool.
Once the container is extracted, you will have 3 files.  The one I'm testing on is patch_compressed.vpp_xbox2.

patch_compressed.vpp_xbox2's contents are as follows..

```
cmp_common.lua
credits_xbox2.xtbl
customization_items.xtbl
jump_sm.xtbl
m17.lua
m22_1.lua
menu_DE.be_strings
menu_ES.be_strings
menu_FR.be_strings
menu_IT.be_strings
menu_US.be_strings
pause_menu_common.lua
pause_save_game.lua
ui_bms_dlc_al.cpeg_xbox2
ui_bms_dlc_al.gpeg_xbox2
ui_bms_dlc_al.xtbl
ui_bms_store_weapon_costumes.xtbl
vdo_hint_bar.lua
weapon_costumes.xtbl

```


I've been trying to decompress jump_sm.xtbl in some tests, because its the first in the loop in the string table.
## Post #29
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-08-30T04:54:51+00:00
- Post Title: Re: Saints row IV ps3_vpp.

> Reply from XBLToothPik
>
> @Michalss

The editor isn't complete & not everything in the source is right as of now.  Been waiting on more info before I finish it.
 Thats why i posted it in here on the first place.
## Post #30
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-08-30T04:56:39+00:00
- Post Title: Re: Saints row IV ps3_vpp.

> Reply from howfie
>
> I thought on Rick's site Volition said they were going to (and have released some minor) extracting tools. The fact that they said they were going to release file format information, extracting tools, and an importer/exporter, I think we should all just wait to save us from wasting a lot of time. Then people can figure out the PS3 and XBox360 formats after the PC tools are released.

sent you samples i hope you gonna figure it out
## Post #31
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2013-08-30T14:53:27+00:00
- Post Title: Re: Saints row IV ps3_vpp.

Xbox version use lzx, or not?
## Post #32
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-08-30T15:38:56+00:00
- Post Title: Re: Saints row IV ps3_vpp.

nope. not lzo, lzx, xbcompress, and not zlib (prefixless or otherwise). tested first file listed in archive of files sent to me. if it was any of those, comtype_scan would have found it. not sure what it is yet. was there an extractor for sr3 xb360?
## Post #33
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-08-30T18:03:37+00:00
- Post Title: Re: Saints row IV ps3_vpp.

same here went through the scanner and did not found anything on X360 version
## Post #34
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-08-30T21:15:56+00:00
- Post Title: Re: Saints row IV ps3_vpp.

Send me a sample 360 file and I'll look
## Post #35
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-08-30T21:53:31+00:00
- Post Title: Re: Saints row IV ps3_vpp.

sent
## Post #36
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2013-09-01T15:56:36+00:00
- Post Title: Re: Saints row IV ps3_vpp.

Any progress chrrox?
## Post #37
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2013-09-22T18:20:26+00:00
- Post Title: Re: Saints row IV ps3_vpp.

Hey anyone made any progress on decrypting or decompressing the data?
## Post #38
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2013-10-15T18:55:24+00:00
- Post Title: Re: Saints row IV ps3_vpp.

It's been nearly a month now and I got the PC version anyone working on that?

T.
## Post #39
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2013-10-15T19:48:07+00:00
- Post Title: Re: Saints row IV ps3_vpp.

I would suggest [Saints Row Mods](http://saintsrowmods.com/) for anything PC-centric.
## Post #40
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2013-11-04T19:07:36+00:00
- Post Title: Re: Saints row IV ps3_vpp.

Friends, have some writing tool for working with files from ps3? Hugs.
