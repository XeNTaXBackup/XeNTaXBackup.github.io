## Post #1
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-10-06T05:01:42+00:00
- Post Title: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2009-10-07T08:49:08+00:00
- Post Title: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

It is just filesystem  You can merge all files to 1. All files inside are compressed with LZSS. here is no problem. Problem is file win_000.nfs. I think it is AES encrypted file with information about files inside. I am able to decompress files from win_000.??? files, but I was unable to decrypt that "index" file to get info about offsets, sizes etc.
## Post #3
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2009-10-07T10:04:33+00:00
- Post Title: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

try using "AC2211234495ACA27E805986108BEEDD4D01D3970B9D4CA93D7BE1BBEDDA8458" as key
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-10-07T11:14:06+00:00
- Post Title: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

i am using the tool DeLZSS but have no idea how to use the command to input the key.
## Post #5
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2009-10-07T11:59:48+00:00
- Post Title: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

> Reply from OrangeC
>
> i am using the tool DeLZSS but have no idea how to use the command to input the key.
It is not standard LZSS, but custom one
## Post #6
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2009-10-07T13:26:23+00:00
- Post Title: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

> Reply from Vash
>
> try using "AC2211234495ACA27E805986108BEEDD4D01D3970B9D4CA93D7BE1BBEDDA8458" as key

Well, key is ok, file decrypted  How did you get it? I found only something like "BF238E52208261B11FB50901E78E45AC4660153565F09295305484E1F05166EC"
## Post #7
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2009-10-07T15:16:34+00:00
- Post Title: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

i did some asm researches
## Post #8
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-10-07T15:40:34+00:00
- Post Title: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

Nice! So I decrypt the .000, combine all the files into one archive, and how would I go about to decompress it?
## Post #9
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2009-10-07T15:46:43+00:00
- Post Title: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

Wow, you guys are fast. Good work.

> Reply from Vash
>
> i did some asm researches

Is there a guide or something else that explains how to do "asm researches" to find such keys?
## Post #10
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-10-07T16:07:34+00:00
- Post Title: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

Well, learn assembler [http://siyobik.info/index.php?document=x86_32bit_asm](http://siyobik.info/index.php?document=x86_32bit_asm)
Get a disassembler [http://www.hex-rays.com/idapro/idadownfreeware.htm](http://www.hex-rays.com/idapro/idadownfreeware.htm) (or a debugger later on [http://ollydbg.de/](http://ollydbg.de/))
and get yourself lots of experience 

A whole bunch of tutorials can be found here: [http://www.tuts4you.com/download.php?list.19](http://www.tuts4you.com/download.php?list.19)
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-07T16:47:26+00:00
- Post Title: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

@XRaptor:
before the edit I read you had difficulties with the aes decryption, you can test it on the fly using quickbms and a script like the following:

```
encryption aes "\xAC\x22\x11\x23\x44\x95\xAC\xA2\x7E\x80\x59\x86\x10\x8B\xEE\xDD\x4D\x01\xD3\x97\x0B\x9D\x4C\xA9\x3D\x7B\xE1\xBB\xED\xDA\x84\x58"
log "decrypted.dat" 0 SIZE
```
easy :)

then you have written that it's a "custom lzss", can you be more specific?
yesterday I decompressed the first file of the first package perfectly without problems with the classical lzss and its default parameters.

@Polefish:
usually it's more simple than how it looks:
- find the AES signatures (I wrote signsrch just for it)
- set a memory breakpoint in the signature which is used during the setting of the key (aes rcon in this case, unfortunately it's not referenced in the code otherwise was better to bp the code directly)
- obviously you need to know assembler, knowing a bit how to use a debugger and naturally knowing something about how the encryption algorithms are used (from a programmer's point of view, not the algorithm itself) and what mean the signatures found

in this case the disassembler is useless because the key is probably built at runtime
anyway I don't have the game so that's the max I can say/hypothize about this specific case :)
## Post #12
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2009-10-07T17:03:29+00:00
- Post Title: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

> Reply from Bugtest
>
> 
then you have written that it's a "custom lzss", can you be more specific?
yesterday I decompressed the first file of the first package perfectly without problems with the classical lzss and its default parameters.
Well, maybe it is classical lzss, I cant tell what is standard  I just found there is just flag byte then data bytes and no "stop" and "start" byte in files. So some files can longer than data to decompress (maybe some align or my fault). The same is getting offset in buffer and length to copy from info bytes. I found there is xx yz where yxx = offset in buffer and z + MIN_LENGTH is lenght. Sometimes in other games I found that offset must be counted by the other way. But yes, algorithm is standard lzss  So sorry for mix-ups  I'm not perfect
## Post #13
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-10-07T17:15:50+00:00
- Post Title: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

> Reply from XRaptor
>
> Well, maybe it is classical lzss, I cant tell what is standard
Well most implementations are "custom" to be exact.
The original paper only suggested using a flag bit that is saved directly before each data chunk.
Mostly those bits are combined to 1 or 2 bytes today though.
## Post #14
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-07T17:54:32+00:00
- Post Title: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

can you list some of these games/applications which use custom lzss algorithms?
the other time you listed only settlers, do you know others?

because I have ever encountered the classical lzss one like in this game, all the games based on the Cauldron engine, [Zork Nemesis](http://forum.xentax.com/viewtopic.php?f=18&t=3511&p=29933#p29933) and something else that I don't remember in this moment.

I need to know all these exceptions which use different settings of the lzss algorithm for deciding or not to add the manual setting of these fields in quickbms (ok I will do for sure but I would like to have at least a "statistic" for my curiosity).
## Post #15
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-10-07T18:27:36+00:00
- Post Title: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

Well, as I said, I don't know any implementation that uses a single bit cause this involves ugly bitwise operations.
Mostly 8 flag bits are combined, sometimes 16.

More common are variations on the parameters window size and how offset/length are encoded.

I don't know any game though except Settlers 2.
## Post #16
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-07T18:40:10+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

excuse me but there is something I don't understand.
you have said that you know many implementations/variations that use different parameters (N/F/T) and then you say that only settlers2 uses a non-standard lzss... so about what existent implementations you refer?

I'm aware of the [http://oku.edu.mie-u.ac.jp/~okumura/compression/lzss.c](http://oku.edu.mie-u.ac.jp/~okumura/compression/lzss.c) implementation which differs not only at parameters level but also in the code to the common lzss one (I don't know if it's a pre or post version) but I have never found it implemented in a real software.
I'm interested in real implementations.
## Post #17
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-10-07T19:27:23+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

Well, you better interpret it as "I can't remember anything other than Settlers 2"
That library uses the single bit encoding: [http://michael.dipperstein.com/lzss/](http://michael.dipperstein.com/lzss/)
The problem is there's no reference implementation like for the deflate algorithm so there exists a variety of versions.
## Post #18
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-10-09T02:06:55+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

Could I request a QuickBMS script for the extraction of this game please?

Thanks so much in advance!
## Post #19
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-09T13:15:28+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

The contents of this post was deleted because of possible forum rules violation.
## Post #20
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-10-09T14:54:57+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

Terrific, thanks!
## Post #21
- Username: redilS
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Sep 28, 2009 5:07 am
- Post datetime: 2009-10-09T15:52:35+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

I have the german localization sitting on my HDD and while unpacking seems to work fine the extracted files just contain garbage. Could it be, that other localizations use different keys or was it my fault? I tried it three times just to be sure
## Post #22
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-09T16:15:28+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

upload your german win_000.nfs and win_000.000 and I will take a look.
## Post #23
- Username: redilS
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Sep 28, 2009 5:07 am
- Post datetime: 2009-10-09T16:28:29+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

There you go: [http://62.75.220.211/of2/data_win.zip](http://62.75.220.211/of2/data_win.zip)
## Post #24
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-09T16:52:36+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

go in the bms script and substituite 0x2a0000 with 0x2c0000, otherwise refresh my previous thread since I have updated the script to guess this value automatucally :)
## Post #25
- Username: redilS
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Sep 28, 2009 5:07 am
- Post datetime: 2009-10-09T17:48:56+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

Works just fine now. Thank you very much
## Post #26
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-10-09T22:48:41+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

The contents of this post was deleted because of possible forum rules violation.
## Post #27
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-09T22:57:42+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

no I can't help.
this x360 format is even more complex than the PC one
## Post #28
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-10-09T23:21:55+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

Alright then.
## Post #29
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2009-10-10T04:48:19+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

Could you help me?

My Version contains 522 Files, 4.07 GB and I can start unpacking but after some time I get a error...

What do to? Create two big files, and unpack them in sequence??

How to edit the first script for that?
[Unbenannt.PNG](https://xentaxbackup.github.io/file/2432_Unbenannt.PNG)
## Post #30
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-10T07:00:19+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

yeah, that error has been reported also by another user and there is no solution for it at the moment, my script was only a work-around as I stated.
## Post #31
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2009-10-10T09:54:53+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

It's a bit cumbersome but the -f flag should be usable to get specific files in the archive even if extracting the entire thing isn't possible.

Of course knowing all file names and file types will be a bit tricky, tried -f "*.xml" as a test (It's the only file format that's easily editable from what the -l list command gave, FSB music files seems to work as well based on the post a bit up about ripping music and sound.) and that wouldn't work at all so I had to use -f *a*.xml" from a - z and 0 - 9 to get all XML files unpacked.

Unsure how to get the game to actually read the data though but perhaps the \data\ or \data_win\ folder works for uncompressed files, there's a packed \system\ folder which is very similar to the \data\system\ folder though my edits of files like weather effects haven't given any results so perhaps it's not so easy.
(Editing textures, models, scripts and other data would be even harder due to all other file formats used.)

EDIT: Oh right -f *t*.xml tried to unpack a specific xml file that ended up freezing the program, nearly had to turn of the computer as it was about to crash so skip that letter.
(Might be a problem due to the size of the 000.full archive with all those 510 or so archives in the EU multi-language version or the QuickBMS version, did try 3.2 as well released three days ago but had the same problem, rather minor though, probably the first issue with file size.)
## Post #32
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2009-10-10T14:20:18+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

And it's impossible create one big file from 001 to 250, unpack this and then create another big file from 250 to end?
## Post #33
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2009-10-10T15:27:28+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

Interesting idea, might work actually, I accidentally forgot to delete the previous merged file when I ran the utility and it just added all the data onto it so moving half the files away and then merging both of them to separate files and then extracting them individually might be doable.
## Post #34
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2009-10-10T16:20:08+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

How to do it??

First 

for i = 0 < 250

and then i = 250 


?? (First Merge Script)

Edit:

The File is only 1.95 GB but same error on same file ?!

asset_map\2dmap.asset.xml
## Post #35
- Username: Maddog
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Oct 11, 2009 4:59 am
- Post datetime: 2009-10-10T21:14:50+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

Hi everyone, my first post,    
Just to confirm same .xml file hangs on my mashine too.
Around 210 mb of data extracted only, exactly 3895 files in 119 folders.
Is it somehow possible to extract whole thing? Mine win_000.full is 4.269 MB in total.


Regards.
## Post #36
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-10T21:41:51+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

in my opinion it's useless to continue to use the script I posted moreover because I have found other problems with it, for example the file locale\languagedata.xml which is also one of the first files to be extracted is corrupted.
so I highly suggest you to wait for a real extractor by someone else because, as I said, this one was only a blind work-around I wrote to help pietastesgood with his request about the music.
## Post #37
- Username: Maddog
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Oct 11, 2009 4:59 am
- Post datetime: 2009-10-11T12:48:09+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

Anyway thanks for your script at least it gave us a good start for experimenting with extraction. This title will be probably downed by codemaster dev team, unfortunately, but has a lot of potential  for modding. They released mission editor that does extraction of some game data but we need whole thing. I hope someone will come with idea how to do that.
## Post #38
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-11T14:04:08+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

> They released mission editor that does extraction of some game datauhmmm interesting, why not modifying the executable of the mission editor to remove this limitation?
I don't have the game so I don't know if it's technically possible but if the editor has a real full access to all the of2 file system (the win_000 files) limited only by the developers (like a check on the filenames or extensions) then it could be an idea.
## Post #39
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2009-10-12T19:21:47+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

Could you help the exe?
## Post #40
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2009-10-12T19:39:10+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

> Reply from aluigi
>
> don't ask me how I did and don't ask me if and how it will work because the script is really horrible and after all I couldn't do something better because the format is not clear.
so yes, I know that it's horrible but works.

One thing - part of code is wrong

```
    get DUMMY1 long MEMORY_FILE

```


there is no DUMMY1 - OFFSET is 64bit value
## Post #41
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-12T19:45:15+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

yes but the total archive is under 0xffffffff bytes so OFFSET can be considered a 32bit value without problems (also because quickbms doesn't support 64bits)
## Post #42
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2009-10-13T12:21:11+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

> Reply from aluigi
>
> yes but the total archive is under 0xffffffff bytes so OFFSET can be considered a 32bit value without problems (also because quickbms doesn't support 64bits)

Not exactly  Whole data file is 0x1 0490 8000 (4 371 546 112). Offsets are stored as 64b value, so your script is not working correctly.

```
    get OFFSET long MEMORY_FILE  << WRONG
    get DUMMY1 long MEMORY_FILE
    savepos DATAOFF MEMORY_FILE
    ...
    math OFFSET -= OFFSET_SEEK   << WRONG because of wrong OFFSET value
    math ZSIZE = OFFSET   << WRONG because of wrong OFFSET value
    math ZSIZE -= PREV_OFFSET   << WRONG because of wrong OFFSET value
    ...

```


Offsets in index block are not stored as expected (offset1<offset2<offset3...) but there are some "strange" values inside. That is why script hangs up I think.
## Post #43
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-13T12:32:38+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

uhmmm why there is this difference between the size of the packages?
in the first post the reference was to 375 files so: 375*8000*1024 = 0xb71b0000 bytes

then even considering the 64bit problem remains the fact that people reported problems with the files having an offset between 250 and 300 mb.

anyway please no longer consider the script I posted in any case, it was only a test
## Post #44
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2009-10-13T13:10:58+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

> Reply from aluigi
>
> it was only a test
I know it was just test. In full game there are 000-521 files, so it is little huge then data in 1st post.
## Post #45
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-10-13T14:52:18+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

Yeah, for some reason the early leaked Russian version wasn't complete -> only to .375.
## Post #46
- Username: Maddog
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Oct 11, 2009 4:59 am
- Post datetime: 2009-10-16T20:31:43+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

Ok after a bit experimenting with script I'm unable to extract full data. I'm a noob considering this decompression algorithms.
I tried some game modifications with .xml files already extracted but it seems that exe only reads win_*** files and not folders. Folder structures I made are OK, yet no modification to game is applied. I see this in hexedit

```
......
ENGINE  Clean up...
FileSystem.UseVolumeFile
File system common
win_000.nfs file:
```

Is it possible to change filesystem and compression of file/files, that exe will use/read without source code or just simple extracted usable files in folders?
## Post #47
- Username: rqqt
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 25, 2009 12:41 pm
- Post datetime: 2009-10-27T19:26:54+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

The contents of this post was deleted because of possible forum rules violation.
## Post #48
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-27T23:08:04+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

if you refer to the files obtained with the script I posted (as far as I know it was the only public tentative of an extractor) in reality you can't extract just nothing because many of the files extracted with the old versions of quickbms were WRONG, and was enough to open some of them with a text editor to notice their wrong content after some bytes.

so just do NOT exist clean files extracted by that script I posted, it was only a quick experiment based on some informations that were posted initially and were incomplete (I don't have even the game) and in any case was intended for a testing purpose here on xentax, not ready for the wide usage.

please if you know other places where there are discussions related to OF2 and my script write it there: DO NOT USE THAT SCRIPT

ufff posting that script caused more damages than benefits...
## Post #49
- Username: wuixntx
- Rank: beginner
- Number of posts: 28
- Joined date: Sat Nov 14, 2009 10:25 am
- Post datetime: 2010-03-10T22:39:34+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

I think QuickBMS method doesn't operate properly.

Users who are more than 95% experienced unpack-error with extracting a resources.


I guess these files like win_000.nfs, big_one.bms, win_000.full, win_000.nfs must be useless to all the unpacker who extract textures, sounds, texts,voices and maps from Operation Flashpoint Dragon Rising.

I've reinstalled each Windows Xp 32bit and OFP 2 DR many times.
And read many postings and almost all the ones with googling until now.

But there isn't nothing changed.
The same errors always show up.
It was concluded that the using QucikBMS way would be not possible.

Time-Wasting.

*******************************************
***********Do not try to extract it!**************
*******************************************

I hope someone make this solve.
## Post #50
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-03-10T23:16:08+00:00
- Post Title: Re: Operation Flashpoint 2: Dragon Rising .000, .001, .002, etc.

was enough to read the various posts in this thread where the author of the scripts (me) said with huge words that the experimental method posted initially didn't work to avoid to waste time with useless tests and reading the opinions of other people not even involved in the research... oh come on
