## Post #1
- Username: dijotp
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jun 20, 2009 9:47 pm
- Post datetime: 2009-09-16T17:49:29+00:00
- Post Title: NfS Shift .BFF files

Hi.
Anybody know how to extract these .BFF files?

Samples: [http://66.7.218.134/~usaportu/pub/BFFs.rar](http://66.7.218.134/~usaportu/pub/BFFs.rar)
## Post #2
- Username: demolos
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Mar 12, 2007 10:38 pm
- Post datetime: 2009-09-18T15:30:00+00:00
- Post Title: NfS Shift .BFF files

this game use zlib compression i looking into shift.exe with hexadecimal and i found zlib:

Error decompressing asset (zlib inflate): %s in pakfile %s

also i suppose the bff archives contain xml files 
you can try to use Jaeder Naub to scan and rip the files inside bff archives
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-09-18T18:10:59+00:00
- Post Title: NfS Shift .BFF files

no, it's not zlib.
the most probable hypothesis it's that it uses chunks of 0x800 bytes compressed with a lzx-like algorithm.
this is the max I can say without the game.
## Post #4
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-09-19T08:54:32+00:00
- Post Title: NfS Shift .BFF files

Maybe helps..here more examples:
[http://www.zshare.net/download/65787584f473ba87/](http://www.zshare.net/download/65787584f473ba87/)
And the official demo:
[http://needforspeed.com/web/nfs/downloads](http://needforspeed.com/web/nfs/downloads)

Direct link: [http://cdn.needforspeed.com/data/downlo ... PCDEMO.exe](http://cdn.needforspeed.com/data/downloads/shift/NFSSHIFTPCDEMO.exe) 1.1Gb's
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-09-19T11:16:03+00:00
- Post Title: NfS Shift .BFF files

I have started to work on it this morning.
I have already figured almost all the fields included the rc4 encryption used in some bffs.
the compression algorithm should be called XMemDecompress and I guess it's referred to a cross-platform xbox function.
I will keep you update if there are news
## Post #6
- Username: dijotp
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jun 20, 2009 9:47 pm
- Post datetime: 2009-09-19T11:49:12+00:00
- Post Title: NfS Shift .BFF files

Thank you Bugtest, you rock.
## Post #7
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-09-19T12:25:35+00:00
- Post Title: NfS Shift .BFF files

I found some info about Xmemcompress [http://forums.gtamodding.ru/index.php?showtopic=10](http://forums.gtamodding.ru/index.php?showtopic=10)
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-09-19T13:13:31+00:00
- Post Title: NfS Shift .BFF files

good news, I did it :)
so stay tuned for a new version of QuickBMS and the needed script when all the tests will be finished completely
## Post #9
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-09-19T14:31:08+00:00
- Post Title: NfS Shift .BFF files


## Post #10
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-09-19T20:54:00+00:00
- Post Title: NfS Shift .BFF files

new version of quickbms: [http://aluigi.org/papers.htm#quickbms](http://aluigi.org/papers.htm#quickbms)
and the needed script for Need for Speed Shift: [http://aluigi.org/papers/bms/nfsshift.bms](http://aluigi.org/papers/bms/nfsshift.bms)
## Post #11
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-09-19T21:50:55+00:00
- Post Title: NfS Shift .BFF files

> Reply from Bugtest
>
> new version of quickbms: http://aluigi.org/papers.htm#quickbms
and the needed script for Need for Speed Shift: http://aluigi.org/papers/bms/nfsshift.bms

Wonderful job!

If the string are translated, how do I put the files together again?

Thanks!
## Post #12
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-09-19T22:09:30+00:00
- Post Title: NfS Shift .BFF files

I make only the extractors.

if someone wants to write a quick rebuilder I suggest to use X12d equal to 0 (no encryption) and ever type 0 for each file so that it's not needed to use the compression.
the crc calculated on the files is just the simple classic one:

```
unsigned int crc = 0xffffffff;
for(i = 0; i < len; i++) {
    crc = crctable[(data[i] ^ crc) & 0xff] ^ (crc >> 8);
}
return(crc);
```
## Post #13
- Username: zeeh
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Jul 26, 2009 9:10 am
- Post datetime: 2009-09-19T22:44:55+00:00
- Post Title: NfS Shift .BFF files

Cool  I hope soon we should have compiler working, good job!
## Post #14
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-09-20T03:55:05+00:00
- Post Title: NfS Shift .BFF files

> Reply from zeeh
>
> Cool  I hope soon we should have compiler working, good job!

Are you making one? It would be great!
## Post #15
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2009-09-20T17:39:42+00:00
- Post Title: NfS Shift .BFF files

Don't know if this is against the Rules here but ...

I bet please please create a BFF Rebuilder because Shift don't reads extracted files and I want to start modding
## Post #16
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2009-09-20T18:32:02+00:00
- Post Title: Re: NfS Shift .BFF files

could anyone upload the new quickbms please as the current link doesnt seem to be working and cant find it anywhere else.
Thanks.
## Post #17
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-09-20T20:30:15+00:00
- Post Title: Re: NfS Shift .BFF files

retry again (there was a problem during the upload of a new minor version some hours ago), and if there are other difficulties go on the [mirror](http://aluigi.altervista.org/papers.htm#quickbms)
## Post #18
- Username: zeeh
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Jul 26, 2009 9:10 am
- Post datetime: 2009-09-20T21:34:59+00:00
- Post Title: Re: NfS Shift .BFF files

In fact, I meant we => someone.
## Post #19
- Username: zeeh
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Jul 26, 2009 9:10 am
- Post datetime: 2009-09-21T13:16:46+00:00
- Post Title: Re: NfS Shift .BFF files

> Reply from Bugtest
>
> I make only the extractors.

if someone wants to write a quick rebuilder I suggest to use X12d equal to 0 (no encryption) and ever type 0 for each file so that it's not needed to use the compression.
the crc calculated on the files is just the simple classic one:
Code: Select allunsigned int crtable[...0x77073096 polynomial...];
unsigned int crc = 0xffffffff;
for(i = 0; i < len; i++) {
    crc = crctable[(data[i] ^ crc) & 0xff] ^ (crc >> 8);
}
return(crc);

Bugtest, can you explain more about the two CRC (CRC32 ?) values for each file inside BFF files?
## Post #20
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-09-22T15:23:06+00:00
- Post Title: Re: NfS Shift .BFF files

the first crc (CRC1 in the script) is calculated on the file included in the archive as is.
with "as is" I mean that if it's compressed and encrypted the crc must be calculated over the decrypted but still compressed data.
crc2 instead should be calculated on the final file (the uncompressed one) but I didn't verify it.
## Post #21
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-09-22T15:38:58+00:00
- Post Title: Re: NfS Shift .BFF files

in case someone is interested the following is the explanation of all the fields of the bff archives.
yeah I know that probably was faster for me to just write the repacker but I'm sure that many people will have fun with these info:

```
bytes   description
4       " KAP" ("PAK " in big endian)
4       0x03004010
4       files
4       alignment
4       zero
4       0x800
0x100   name of the archive
4       X118, size of the information table
4       zero
4       X120, size of the name table + 0x308
4       DHSA field offset
4       DHSA field size
1       zero
1       X12d, set it to 0
1       zero
1       zero
X118    information table
4       "TXEP"
4       not verified
0x100   Gecko.xml or GeckoDemo.xml
0x100   C:\DEV\Gecko\ or C:\DEV\GeckoDemo\
0x100   PC
X120    name table
```

```
4       unused (set it as you want, the game works in any case)
4       unused (set it as you want, the game works in any case)
4       absolute offset of the file
4       ever zero
4       size of the file in the archive (for example its compressed size)
4       size of the extracted file
4       zero
4       zero
4       type, set it to 0 (2 is meant for compressed files)
4       zero
4       CRC of the file as is in the archive
4       extension (example: fxo)
```

```
4       absolute offset where is located the name string
4       zero
4       not verified, tell me if there are problems
4       not verified, seems only a date timestamp
```
have phun
## Post #22
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2009-09-22T16:54:36+00:00
- Post Title: Re: NfS Shift .BFF files

Looks really interesting .. but my coding skills to low ...
## Post #23
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-09-22T21:23:25+00:00
- Post Title: Re: NfS Shift .BFF files

I have just updated a small but important detail.
the first 2 fields of the information table are NOT the crc of the file but something else (probably a 64bit timestamp or similar) that can be set to any value.
while the CRC of the file as is stored in the archive is the one immediately before the extension field.
sorry for the mistake.
## Post #24
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-09-23T11:45:38+00:00
- Post Title: Re: NfS Shift .BFF files

> Reply from Bugtest
>
> I have just updated a small but important detail.
the first 2 fields of the information table are NOT the crc of the file but something else (probably a 64bit timestamp or similar) that can be set to any value.
while the CRC of the file as is stored in the archive is the one immediately before the extension field.
sorry for the mistake.

Thanks for the file structure, you're right about the CRC field being immediately before extension field, but the fields you called initially CRC1 and CRC2 cannot be of any value, the game crashes if I try different values than the original ones. Fortunately those fields don't need to be recalculated if the contents are changed.

I've managed to insert the uncompressed file generated by quickbms in the BFF just changing the type field to 0 and recalculating the CRC and zsize/size fields and offsets.

The file I'm working on it's language_English.bff in /UI/Languages folder, there are 2 files inside the BFF, english.bin and english_histogram.bin, the first contains a lot of binary data on top and all game strings starting at 0x010164, but I can't figure out if the string lenghts or offsets are stored on the same file, tried to change some strings but the game menus gone crazy  

The game it's working fine if I don't change the original string length, but it's useless that way
## Post #25
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-09-24T18:25:06+00:00
- Post Title: Re: NfS Shift .BFF files

Hi guys, good news. I did coded the BFF repacker, I'm still testing and will soon give you the code, it lacks a lot of things like error checking etc., but it's pretty functional. I managed to recreate the PHYSICSPERSISTENT.bff file from C:\Program Files (x86)\Electronic Arts\Need for Speed SHIFT\Pakfiles folder, which contains several text and XML files with game physics definitions, like the one bellow (driverhead.txt)

```
// influence vehicle dynamics.  This violates Newton's 3rd law, but
// allows user to configure head physics without "cheating".

HeadMass=6.0                     // Head and helmet
HeadInertia=(0.032,0.028,0.029)  // Head and helmet
MinPos=(-0.03,-0.08,-0.050)       // Minimum extents of position (should be negative)
MaxPos=( 0.03, 0.08, 0.015)       // Maximum extents of position (should be positive)
MinOri=(-7.0,-7.0,-7.0)          // Minimum degrees of pitch, yaw, roll (should be negative)
MaxOri=( 7.0, 7.0, 7.0)          // Maximum degrees of pitch, yaw, roll (should be positive)

// There are three types of springs to control head movement:
//
// Sliding = spring/damper force maintains given direction relative to vehicle
// Normal = spring/damper force in direction between connection points
// FreeDamping = spring is normal, but damper resist velocity in any direction
//
// Parameters for springs are:
//
// SpringDir = direction of spring/damper forces (automatically normalized, not valid for Normal springs)
// SpringHead = connection to driver head (relative to head center)
// SpringBody = connection to vehicle body (relative to head center)
// SpringCollLen = if more than zero, spring doesn't take effect until minimum length has been reached
// SpringParams = spring rate and damper rate

Spring=Sliding
SpringDir=(0.0,1.0,-0.0)      // up/down
SpringHead=(0.0,-0.05,0.01)
SpringBody=(0.0,-0.05,0.01)
SpringParams=(1000.0,225.0)

Spring=Sliding
SpringDir=(0.0,-0.0,-1.0)     // forward/back
SpringHead=(0.0,-0.05,0.01)
SpringBody=(0.0,-0.05,0.01)
SpringParams=(1700.0,382.0)

Spring=Sliding
SpringDir=(1.0,0.0,0.0)       // lateral
SpringHead=(0.0,-0.05,0.01)
SpringBody=(0.0,-0.05,0.01)
SpringParams=(8500.0,351.0)

Spring=FreeDamping            // resists yawing and rolling
SpringHead=(2.0,0.0,0.0)
SpringBody=(2.0,0.0,0.0)
SpringParams=(63.9,1.31)

Spring=FreeDamping            // resists yawing and pitching
SpringHead=(0.0,0.0,2.0)
SpringBody=(0.0,0.0,2.0)
SpringParams=(63.9,1.31)
```


Again, thanks bugtest for the file structure and tips for recreating the archive.
## Post #26
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-09-25T01:32:31+00:00
- Post Title: Re: NfS Shift .BFF files

It's done.

I have attached the utility to this message, you'll need NET Framework 2.0 in order to execute it.

** Only for full version of game. **

Download Links

[http://cid-0459fc515f4928b3.skydrive.li ... _Tools.rar](http://cid-0459fc515f4928b3.skydrive.live.com/self.aspx/Public/BFF%5E_Tools.rar)
[http://forum.racedepartment.com/downloa ... ools-1740/](http://forum.racedepartment.com/downloads/need-for-speed-shift/68/nfs-shift-bff-tools-1740/)

Compiler ([click here](http://forum.xentax.com/viewtopic.php?f=10&t=3717&p=32217#p32217) for more info)


Repacker


Injector


You just need to put all BFF extracted files in a folder (which can have sub-folders) and all files, don't add or delete extracted files before repacking (adding files to the folder will not harm anything and will be simple ignored).

That's it, enjoy  

Edited DDS car livery texture
## Post #27
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-09-25T01:33:55+00:00
- Post Title: Re: NfS Shift .BFF files

bugtest, 

Please, can you take a look at the attached file? I'm looking for string lengths or offsets but I can't figure out what kind of mechanism they used. I would really appreciate if you can give me some hint so I can start translating the game.


 language_English.rar
english.bin and english_histogram.binContains text strings used in game. (100.34 KiB) Downloaded 123 times


Thanks!
## Post #28
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-09-25T13:39:47+00:00
- Post Title: Re: NfS Shift .BFF files

I see no offset or size values in these files
## Post #29
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-09-25T15:05:20+00:00
- Post Title: Re: NfS Shift .BFF files

> Reply from Bugtest
>
> I see no offset or size values in these files

But do you see anything useful? I don't know how the strings are indexed, changing the length of a couple strings on the beginning it's sufficient to mess the entire game.
## Post #30
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2009-09-25T17:50:41+00:00
- Post Title: Re: NfS Shift .BFF files

It's impossible to add a new File in the extracted Folder or change the lenght of any file?
## Post #31
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-09-25T19:07:03+00:00
- Post Title: Re: NfS Shift .BFF files

> Reply from sommergemuese
>
> It's impossible to add a new File in the extracted Folder or change the lenght of any file?

You can't add new files 'cause the game executable will not understand it, unless I'm missing your point.

The extracted files can be changed, no problem with that.
## Post #32
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2009-09-25T23:04:24+00:00
- Post Title: Re: NfS Shift .BFF files

Watched the PakDirInfo.dat File?

Maybe we have to edit this file too?

Edit: Did you mean no completely new BFF-File or no new File inside of BFF-Archive too?
## Post #33
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-09-25T23:19:45+00:00
- Post Title: Re: NfS Shift .BFF files

> Reply from sommergemuese
>
> Watched the PakDirInfo.dat File?

Maybe we have to edit this file too?

I don't think we need to mess with PadDirInfo.dat file.

Can you tell what you're trying to do? 

> Reply from sommergemuese
>
> Edit: Did you mean no completely new BFF-File or no new File inside of BFF-Archive too?

Both are true, you can't create a brand new BFF archive neither add files to a BFF archive, the repacker will only put all files extracted together again, edited/changed or not, in uncompressed form.
## Post #34
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2009-09-26T02:27:45+00:00
- Post Title: Re: NfS Shift .BFF files

Okay 

Thanks

What do you think: Will it possible to create BFF-Files with new Files inside?

Edit: Maybe I'm to silly or your tool isn't working 100%

I tried to extract the RX7.BFF, edited one DDS-File and used your Packer - I got a new BFF File as expected , Size 40.835.741 Bytes but Shift won't load this file and the unpacker isn't working to says this:
[gjhjg.PNG](https://xentaxbackup.github.io/file/2371_gjhjg.PNG)
## Post #35
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-09-26T03:28:24+00:00
- Post Title: Re: NfS Shift .BFF files

Can you upload the edited DDS file?

Edit:
Nevermind, I forgot to save the entire nametable offsets, I'll fix it ASAP.

Sorry.
## Post #36
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-09-26T04:16:57+00:00
- Post Title: Re: NfS Shift .BFF files

Fixed, please download it again from previous page.

Sorry.
## Post #37
- Username: Sqwall
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 26, 2009 4:48 pm
- Post datetime: 2009-09-26T09:20:02+00:00
- Post Title: Re: NfS Shift .BFF files

Still does not work. Done the same thing edited DDS and repacked. Shift comes to loading profile elements and freezes there. Then I unpacked the original BFF file repacked without changing nothing to the files and same thing game freezes when I use repacked version which is more large in size (because of 0 compression).   

Thanks for the efforts and hope that there will be solution for the problem soon. 

Thanks again.
## Post #38
- Username: YodaStar
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Sep 26, 2009 8:01 am
- Post datetime: 2009-09-26T09:51:35+00:00
- Post Title: Re: NfS Shift .BFF files

Sqwall/sommergemuese that is the behavior I get if I add/delete a file in the archives structure.I believe you might have a thumb file in there with the texture that is creating this error.
## Post #39
- Username: Sqwall
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 26, 2009 4:48 pm
- Post datetime: 2009-09-26T09:54:58+00:00
- Post Title: Re: NfS Shift .BFF files

> Reply from YodaStar
>
> Sqwall/sommergemuese that is the behavior I get if I add/delete a file in the archives structure.I believe you might have a thumb file in there with the texture that is creating this error.

Nice point will check.
## Post #40
- Username: Sqwall
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 26, 2009 4:48 pm
- Post datetime: 2009-09-26T10:02:55+00:00
- Post Title: Re: NfS Shift .BFF files

It does not seem that this is the problem because the file count is the same. Quick BMS gives me 1048 files and 9 directories and Repack packs 1048 files. With current Folder options I can see thumbs.db file and there is none in the folders I pack.
## Post #41
- Username: YodaStar
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Sep 26, 2009 8:01 am
- Post datetime: 2009-09-26T10:14:28+00:00
- Post Title: Re: NfS Shift .BFF files

Japamd I seem to be running into a problem with some archives with your repacker.

First the IGPHASEACTIVATE.bff archive cant be repacked throwing me this error code,

```
Destination array was not long enough. Check destIndex and length, and the
array's lower bounds.
at System.Array.Copy(Array sourceArray, Int32 sourceIndex, Array
destinationArray, Int32 destinationIndex, Int32 length, Boolean reliable)
at System.Array.CopyTo(Array array, Int32 index)
at BFF.BFF.Build()
at Repack.Program.Main(String[] args)
```


It also happens with a unpacked unmoddified IGPHASEACTIVATE archive files. I have NET 2 framework with SP2.

Another problem is that bff files from "vehicles" and "tracks" folder gets repacked without problems but the game wont handle the archives when running the game. This stalling the game in infinte loading sequence for x map or modified car.

Btw thank you very much for this tool and Bugtest for unpacker.
## Post #42
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-09-26T12:01:41+00:00
- Post Title: Re: NfS Shift .BFF files

Added files will not be considered because the script will rely on the original BFF nametable and repack only the files contained there, deleted ones will throw an error instead.

Sqwall, I tried repacking the same file and got the same error, the pointed BFF uses a 4 letters extension (bfont) and the program was expecting only 3 letters extensions. Fixed the code and got the files repacked, please download it again.
## Post #43
- Username: Sqwall
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 26, 2009 4:48 pm
- Post datetime: 2009-09-26T12:25:31+00:00
- Post Title: Re: NfS Shift .BFF files

Tested with 0.3 .. still the game freezes on Loading Profile Elements in both ways. Using original files extracted and then packed ... and with edited DDS packed.   

Thanks for fast reply.
## Post #44
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-09-26T13:24:27+00:00
- Post Title: Re: NfS Shift .BFF files

> Reply from Sqwall
>
> Tested with 0.3 .. still the game freezes on Loading Profile Elements in both ways. Using original files extracted and then packed ... and with edited DDS packed.   

Thanks for fast reply.

The error occurs only with the edited DDS file?
## Post #45
- Username: Sqwall
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 26, 2009 4:48 pm
- Post datetime: 2009-09-26T13:35:33+00:00
- Post Title: Re: NfS Shift .BFF files

No.. the problem is there even unpacking original BFF file and repacking the extracted files with the repack program into my_Mazda_MX5.bff. Then copy the newly build file in to the corresponding folder of the game rename the original file to *.old and then rename the new file to the Mazda_MX5.bff (like the original). Then Start the game and it freezes on Loading Profile elements.

I am running Windows 7 x86 if this could help you.
## Post #46
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-09-26T14:31:07+00:00
- Post Title: Re: NfS Shift .BFF files

> Reply from Sqwall
>
> No.. the problem is there even unpacking original BFF file and repacking the extracted files with the repack program into my_Mazda_MX5.bff. Then copy the newly build file in to the corresponding folder of the game rename the original file to *.old and then rename the new file to the Mazda_MX5.bff (like the original). Then Start the game and it freezes on Loading Profile elements.

I am running Windows 7 x86 if this could help you.

I'll try to reproduce the error. Thanks for reporting it.
## Post #47
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-09-26T17:49:56+00:00
- Post Title: Re: NfS Shift .BFF files

Got the same behaviour here, but got it sorted out.

> Reply from Bugtest
>
> Code: Select all4       absolute offset where is located the name string
4       zero
4       not verified, tell me if there are problems
4       not verified, seems only a date timestamphave phun

Looks like the last 8 bytes are needed, I just copied entire nametable from original BFF archive into the newly created and tried to repack the Mazda_MX5.bff contents, now it's working. Please download v0.4 and try again.
## Post #48
- Username: Sqwall
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 26, 2009 4:48 pm
- Post datetime: 2009-09-26T18:50:26+00:00
- Post Title: Re: NfS Shift .BFF files

Nope the game still resists to run with files build by packer. Still freezing to Loading Profile Elements.    I only try BFF files about vehicles. I want to edin DDS textures. I know that the packer is working well on the physics files but I don't know much about physics.  

Everything seems fine .. i tried to unpack BFF files created by me with QuickBMS and it worked but the game refuses to use them.

I really admire you knowledge and I am glad to point the bugs for you. Just hope that this thing is not eating too much of your time.

Thanks again.
## Post #49
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2009-09-26T19:50:41+00:00
- Post Title: Re: NfS Shift .BFF files

I really hope that this will be fixed .. I really want to start modding 

Maybe it sounds interesting, I started a German Shift Modding Tutorial Series only rebuilding is missing so far 

[http://sommergemuese.klee.in](http://sommergemuese.klee.in)
## Post #50
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-09-26T20:57:53+00:00
- Post Title: Re: NfS Shift .BFF files

> Reply from Sqwall
>
> Nope the game still resists to run with files build by packer. Still freezing to Loading Profile Elements.    I only try BFF files about vehicles. I want to edin DDS textures. I know that the packer is working well on the physics files but I don't know much about physics.  

Everything seems fine .. i tried to unpack BFF files created by me with QuickBMS and it worked but the game refuses to use them.

I really admire you knowledge and I am glad to point the bugs for you. Just hope that this thing is not eating too much of your time.

Thanks again.

Hmmm, no problem, it's fun after all. 

But that's weird, I tried repacking the same file as you, Mazda_MX5.bff, replaced the original compressed file with the uncompressed one and the game loaded and played fine.

Maybe the changed texture is causing that, kind a protection against modding or something else, I really don't know.

If you can upload the texture (ie: rapidshare), please let me know so I can try it.
## Post #51
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2009-09-26T21:12:21+00:00
- Post Title: Re: NfS Shift .BFF files

Maybe DXT3 oder DXT5 Error??? Or something like that? I'm not on my PC atm can't test it

ps: can you please try to change a text file just write somewhere in the engine file another coment at the end? look:

then the file is another (crc) and physic tuning is possible, if this works

EngineSpeedHeat=10.875e-004         // bla bla bla



Edit: Damn 0.4 is Crashing Windows 7 X64 ... hmm
## Post #52
- Username: YodaStar
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Sep 26, 2009 8:01 am
- Post datetime: 2009-09-26T23:22:20+00:00
- Post Title: Re: NfS Shift .BFF files

I have the same problem as Sqwall. With london_Circuit and edited vhf files and BMW_135 edited xml file. Game will stall when it is going to load the London track or BMW car. Maybe a dumb question but are you sure the uploaded repacker is the correct one?
## Post #53
- Username: Arachnus
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Sep 27, 2009 2:58 am
- Post datetime: 2009-09-27T00:16:39+00:00
- Post Title: Re: NfS Shift .BFF files

Hi japamd!

I got the loading problem with repacker 0.4 too, the game simply goes to a infinity loading profiles elements!

I uploaded here the modded Livery.DDS i changed and the original one, the file syze is the same, and format i used the same of the original as; DXT1 11bitmaps!

Hope you can figure what is happenning!

And thanks in advance!


 dodge_challenger_livery02.rar
(203.11 KiB) Downloaded 49 times
## Post #54
- Username: Arachnus
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Sep 27, 2009 2:58 am
- Post datetime: 2009-09-27T00:18:10+00:00
- Post Title: Re: NfS Shift .BFF files

and here is the original!

Sorry for double post, but the fórum let´s just one atachment per reply!


 dodge_challenger_livery02ORIGINAL.rar
(198.77 KiB) Downloaded 30 times
## Post #55
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-09-27T00:25:21+00:00
- Post Title: Re: NfS Shift .BFF files

I'm not sure if it's a repacker problem or some kind of protection against file modification, or maybe the game it's just expecting compressed files, albeit file's compression flag set to uncompressed in infotable.

I did successfully repacked the archive using the original/compressed files, maybe I should try to compress the files while repacking them, but that will be possible only if I can figure out what compression algorithm it's been used.
## Post #56
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2009-09-27T11:38:09+00:00
- Post Title: Re: NfS Shift .BFF files

If I try to repack Files like IGPHASEACTIVATE.bff all working fine.

But if I try to Repack any car like RX7 your Repacker is Crashing..

A friend of mine old me, that its impossible to repack Spa too ..

Okay repacking (and extracting) is working fine for me there but Shift freezes on loading the track...
## Post #57
- Username: Shelly
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 27, 2009 12:37 am
- Post datetime: 2009-09-27T15:21:28+00:00
- Post Title: Re: NfS Shift .BFF files

Same here. 

I repacked the BMW_M3_GT2 (changed only a variable in an xml). The original is 17MB, the repacked 36MB. Shift freezes when I tried to load a track or switch to another car (not even the car I modified). Used Version 0.4

Even worse, it seems like my profile was destroyed because of the repacked file. Even after replacing the BMW_M3_GT2 with the original, the freezing was still there. Luckily I made a backup of my profiles. 

BTW, thanks a lot for the hard work!
## Post #58
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-09-27T16:10:00+00:00
- Post Title: Re: NfS Shift .BFF files

Hi guys, good news, I just did (I guess  )

There's a DDS texture changed (where it reads Adrenaline) for the Mazda MX5.

[](http://img25.imageshack.us/img25/7918/shift2009092713061743tn.jpg) [](http://img25.imageshack.us/img25/6876/shift2009092713060594tn.jpg) [](http://img25.imageshack.us/img25/4716/shift2009092713060294tn.jpg)

I'm just finishing testing and will upload the new/working version soon.

Shelly, I don't think a repacked BFF file would mess with game profiles, but thanks for reporting, it's a good idea to backup game profiles and always make a backup of the original files before editing them.
## Post #59
- Username: Arachnus
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Sep 27, 2009 2:58 am
- Post datetime: 2009-09-27T16:31:22+00:00
- Post Title: Re: NfS Shift .BFF files

japamd

You´re the boss!

Anxiously waiting!

Thanks
## Post #60
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2009-09-27T17:45:04+00:00
- Post Title: Re: NfS Shift .BFF files

Yeah really really cool 

Is it possible to repack tracks too?
## Post #61
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-09-27T19:12:36+00:00
- Post Title: Re: NfS Shift .BFF files

Thanks, Arachnus   

sommergemuese, I think it's possible to repack anything now, please try it and let us know.

GUI uploaded, you can download it from [here.](http://forum.xentax.com/viewtopic.php?f=10&t=3717&p=31886#p31886)
## Post #62
- Username: Arachnus
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Sep 27, 2009 2:58 am
- Post datetime: 2009-09-27T19:35:43+00:00
- Post Title: Re: NfS Shift .BFF files

Hi japamd

I tried the GUI, but it´s giving me an .exe error, i´m running in Windows 7 RTM x64, all early versions worked fine, but this update 0.5 crashs do desktop!

The 2 files you´ve just upload are stand alone, or need to be at the same folder of 0.4 repack files?! Anyway i tried the two methods and got .exe error?!

Even running throught DOS, or direct clicking BffRepacker.exe



thanks in advance!
## Post #63
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-09-27T19:59:17+00:00
- Post Title: Re: NfS Shift .BFF files

Ooops, my fault   

Re-uploaded, should work now.

Both files in rar archive (BFF.dll and BffRepacker.exe) must be on same folder.
## Post #64
- Username: Arachnus
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Sep 27, 2009 2:58 am
- Post datetime: 2009-09-27T20:31:14+00:00
- Post Title: Re: NfS Shift .BFF files

thanks Boss! now the BFFRepacker works 100% in win 7 x64!

BUT!!!!!!

Sorry to be so boring brother!

I couldn´t launch the game with my modded livery, still gets infinity loading profile elements!

the question is:?

1=Which file you unpacked to change the livery you got in game?

I´m umpacking this file:

C:\Arquivos de programas (x86)\Eletronic Arts\Need for Speed SHIFT\Pakfiles\Vehicles\DODGE_CHALLENGER_SRT8.bff

So i repack with one altered textures and the game won´t load the car at garage!

2=How do you do it, and how do you saved the .DDS? DXT1(no alpha) Generate mipmaps(11)?

thanks and many thanks!
## Post #65
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-09-27T20:45:34+00:00
- Post Title: Re: NfS Shift .BFF files

> Reply from Arachnus
>
> thanks Boss! now the BFFRepacker works 100% in win 7 x64!

BUT!!!!!!

Sorry to be so boring brother!

I couldn´t launch the game with my modded livery, still gets infinity loading profile elements!

the question is:?

1=Which file you unpacked to change the livery you got in game?

I´m umpacking this file:

C:\Arquivos de programas (x86)\Eletronic Arts\Need for Speed SHIFT\Pakfiles\Vehicles\DODGE_CHALLENGER_SRT8.bff

So i repack with one altered textures and the game won´t load the car at garage!

2=How do you do it, and how do you saved the .DDS? DXT1(no alpha) Generate mipmaps(11)?

thanks and many thanks!

I'm glad it's working now.

1: I've used Nissan_GTR.bff

2: Edited 2 liveries, nissan_gtr_livery01.dds and nissan_gtr_livery02.dds. I'm using [DXTBmp](http://www.btinternet.com/~mnwright/programs/dxtbmp.htm), and saving in the same format as original.
## Post #66
- Username: Arachnus
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Sep 27, 2009 2:58 am
- Post datetime: 2009-09-27T21:03:40+00:00
- Post Title: Re: NfS Shift .BFF files

> 1: I've used Nissan_GTR.bff
>
> 
>
> 2: Edited 2 liveries, nissan_gtr_livery01.dds and nissan_gtr_livery02.dds. I'm using DXTBmp, and saving in the same format as original.

but you´re unpacking the files at the same folder i was unpacking?:

C:\Program Files (x86)\Electronic Arts\Need for Speed SHIFT\Pakfiles\Vehicles\desired vehicle.bff ?

Unpack with QuickBMS.
 Edit textures
  Repack with your BFFRepacker
   Replace original .bff with repaked one
    Fire the game?

Maybe i´m missing something!

I´m using Photoshop CS 4 to edit the textures and [WTV(Windows Textures Viewer)](http://developer.nvidia.com/object/windows_texture_viewer.html) to check the format!
## Post #67
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-09-27T21:33:25+00:00
- Post Title: Re: NfS Shift .BFF files

Any chance for the last version in commandline?
## Post #68
- Username: redilS
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Sep 28, 2009 5:07 am
- Post datetime: 2009-09-27T21:38:55+00:00
- Post Title: Re: NfS Shift .BFF files

Hi guys
If i was you i'd just use '-loose' as cmdline parameter instead of repacking the archives over and over again. Shift will then use the unpacked files instead of the archives 

greetings,
red
## Post #69
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2009-09-27T23:29:49+00:00
- Post Title: Re: NfS Shift .BFF files

did you mean shift.exe -loose  ???

rly?? omg


Shift is crashing with -loose
## Post #70
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-09-28T00:59:12+00:00
- Post Title: Re: NfS Shift .BFF files

> Reply from Savage
>
> Any chance for the last version in commandline?

Just uploaded a new rar containing both GUI and command line.

> Reply from Arachnus
>
> 1: I've used Nissan_GTR.bff

2: Edited 2 liveries, nissan_gtr_livery01.dds and nissan_gtr_livery02.dds. I'm using DXTBmp, and saving in the same format as original.

but you´re unpacking the files at the same folder i was unpacking?:

C:\Program Files (x86)\Electronic Arts\Need for Speed SHIFT\Pakfiles\Vehicles\desired vehicle.bff ?

Unpack with QuickBMS.
 Edit textures
  Repack with your BFFRepacker
   Replace original .bff with repaked one
    Fire the game?

Maybe i´m missing something!

I´m using Photoshop CS 4 to edit the textures and WTV(Windows Textures Viewer) to check the format!

No, I'm unpacking the vehicle BFF into another folder, edit files then repack the entire folder into a new BFF file. 

I recommend you to use DXTBmp and set it to use PS or whatever graphics editor you want. DXTBmp will save the file with the original format.
## Post #71
- Username: Sqwall
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 26, 2009 4:48 pm
- Post datetime: 2009-09-28T05:19:19+00:00
- Post Title: Re: NfS Shift .BFF files

Worked. I edited DDS and repacked using gui and the game worked. Used DXTbmp.

Thanks Japamd really big improvement over small time. You are amazing.  So lets start make skins and edit the textures.

Big thanks to Japamd again.
## Post #72
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2009-09-28T05:47:08+00:00
- Post Title: Re: NfS Shift .BFF files

Thats a lot easier:

[http://sommergemuese.klee.in/2009/09/sh ... er-zocken/](http://sommergemuese.klee.in/2009/09/shift-modden-und-ohne-repacker-zocken/)

I know its German but:

Create the BAT listed there execute and move this content to shift... remove the pakfiles folder and attach the -loose to your nfs shortcut
## Post #73
- Username: redilS
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Sep 28, 2009 5:07 am
- Post datetime: 2009-09-28T07:10:27+00:00
- Post Title: Re: NfS Shift .BFF files

Yes sommergemuese, that's why Shift was crashing. Using "loose" files while not having them in the correct location will make Shift crash. Good to see you figured it out on your own.

Nevertheless, you could've at least mentioned me in your blog. You're the second one that proclaims my findings as his own. Next time, i'll just keep my mouth shut and use such information for my own good...
## Post #74
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2009-09-28T08:11:51+00:00
- Post Title: Re: NfS Shift .BFF files

No swearing pls 

Watch again
## Post #75
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-09-28T12:39:09+00:00
- Post Title: Re: NfS Shift .BFF files

> Reply from Sqwall
>
> Worked. I edited DDS and repacked using gui and the game worked. Used DXTbmp.

Thanks Japamd really big improvement over small time. You are amazing.  So lets start make skins and edit the textures.

Big thanks to Japamd again.

I'm glad it's working for you.

As redilS pointed out, it's a lot easier to use the unpacked files, much better while testing different settings. Thanks, redilS   

I think the repacker will not be required as we can use the unpacked files, so I'm stopping further changes to it.
## Post #76
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2009-09-28T13:52:28+00:00
- Post Title: Re: NfS Shift .BFF files

What about these:

-partpak    -tandemdrift    -solodrift  -timeattack -phantomduel    -phantomderby   -phantomtt  -campaign   -vehicle    -ai -aivehicle  -randomai   -disablehud -skipmenu   -novehicles -track  -password   -login
## Post #77
- Username: venomtrk
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Sep 28, 2009 5:36 am
- Post datetime: 2009-09-28T13:53:05+00:00
- Post Title: Re: NfS Shift .BFF files

Hi there , i need to edit language files for Turkish translation.

I extracted language_english.bff file. There are two files in there. English.bin and English_histogram.bin. How can i edit these files and put them back. Any ideas ?
## Post #78
- Username: redilS
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Sep 28, 2009 5:07 am
- Post datetime: 2009-09-28T14:25:09+00:00
- Post Title: Re: NfS Shift .BFF files

> What about these:
Tried those already...

partpak: maybe, in combination with 'loose', allows the use both packed and unpacked files. though, partpak alone makes shift go awkward
disablehud: easy, disables hud ^^
skipmenu: for me, this skipped the player selection dialogue
novehicles: disables rendering of AI vehicles and track, making your car fall into the void

all others: by now i've found no useful combination. maybe useful for demo purposes, directly booting the game into a race

there's also:
nosoftshadows: shadows are not filtered anymore
noshadows: does nothing apart crashing the game
windowsize
windowpos
plus a few more i don't recall atm
## Post #79
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-09-28T17:00:21+00:00
- Post Title: Re: NfS Shift .BFF files

> Reply from venomtrk
>
> Hi there , i need to edit language files for Turkish translation.

I extracted language_english.bff file. There are two files in there. English.bin and English_histogram.bin. How can i edit these files and put them back. Any ideas ?

I'm trying to translate English.bin, but I didn't discovered how the strings are indexed, you can translate all strings *if you keep the original string size*, change just one string length and the game will get crazy.
## Post #80
- Username: HeliosDoubleSix
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Sep 27, 2009 4:07 pm
- Post datetime: 2009-09-28T20:09:30+00:00
- Post Title: Re: NfS Shift .BFF files

Unpacking all the Data SLOWS your load time due to slow random access speeds on HDD's

Loading a typical race goes from 14 seconds to 23 seconds. (17 seconds if you have an SSD)

--

If people are going to go the unpack everything route, I think it would be wise to test if unpacking has any affect on load times.

Anyone notice any load speed changes after they unpacked everything?

Id imagine you have less cpu use as it no longer needs to uncompress the data, but at the same time you have more data to load in from disk which means if your HD isn't that fast it would probably be slower than when they were compressed, but this is just speculation. Id bet it makes things slightly slower for most people and much slower for laptops or people with slow or fragmented drives.

-EDIT AGAIN-

*sigh* When the game is uncompressed/unpacked it's not much bigger than before so the compression seems minimal.

Cars in the Car Lot/Garage load twice as fast it seems, however loading a race takes a good deal longer, in my test it went from:

14 Seconds to load Elise Invitational

to

23 Seconds.. ouch, that's rather unacceptable so I think I'll be repacking everything!

I can hear my HD crunching away which is a clear sign its doing heavy random access with HD's suck balls at. Packing the files prevents this heavy random access as the files are consolidated.

My bet is if you have a good SSD (solid state storage drive, none moving parts storage, expensivo) it will overcome this slow down entirely and load at the same speed as normal. So I'm going to go test that theory now...

Yah the SSD helps a lot, but it's still slower loading a race in 17.3 instead of 14 when packed.
## Post #81
- Username: redilS
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Sep 28, 2009 5:07 am
- Post datetime: 2009-09-29T09:15:52+00:00
- Post Title: Re: NfS Shift .BFF files

If you're just playing Shift, leave it as it is. Unpacking is ideal for the modders, because the don't have to repack everything only for testing a small change.
## Post #82
- Username: HeliosDoubleSix
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Sep 27, 2009 4:07 pm
- Post datetime: 2009-09-29T10:01:14+00:00
- Post Title: Re: NfS Shift .BFF files

Indeed, though apparently you cannot mod the races/maps as they will not repack. So for so things unpacking everything is the only way... unless someone knows how to use the partial pack argument and it does what it sounds like?

I also cannot get IGPHASEACTIVATE.bff to repack, notsure if thats a bug in the repacker as it used to work now I get some error message about array lengths or something.
## Post #83
- Username: Shelly
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 27, 2009 12:37 am
- Post datetime: 2009-09-29T12:10:37+00:00
- Post Title: Re: NfS Shift .BFF files

I have discovered, that unpacking via *.bat does not work if the Shift Patch 1.01 is installed.

On my machine it works only if I try to unpack an unpatched Shift.

Please make the patched version unpackable too.


Edit:
I think the difference between patched and not patched Shift could be an explanation for why the repacker worked for some and for others not?
## Post #84
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-09-29T13:01:34+00:00
- Post Title: Re: NfS Shift .BFF files

if they are new files not available in the non-patched game it's enough to use the new feature of quickbms 0.3 which scans the input folder:

```
quickbms -F "*.bff" c:\nfsshift.bms "C:\Program Files\Electronic Arts\Need for Speed SHIFT\PakFiles" c:\output_folder
```

instead if it's a new version of a file I need the exact file to analyze to know what is changed
## Post #85
- Username: Shelly
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 27, 2009 12:37 am
- Post datetime: 2009-09-29T13:10:55+00:00
- Post Title: Re: NfS Shift .BFF files

> Reply from Bugtest
>
> if they are new files not available in the non-patched game it's enough to use the new feature of quickbms 0.3 which scans the input folder:
Code: Select allquickbms -F "*.bff" c:\nfsshift.bms "C:\Program Files\Electronic Arts\Need for Speed SHIFT\PakFiles" c:\output_folder
instead if it's a new version of a file I need the exact file to analyze to know what is changed

Ahh, sorry man. I had an old version of quickbms. Now with 0.3 it works fine. Thanks!
## Post #86
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-09-29T13:24:41+00:00
- Post Title: Re: NfS Shift .BFF files

> Reply from HeliosDoubleSix
>
> Indeed, though apparently you cannot mod the races/maps as they will not repack. So for so things unpacking everything is the only way... unless someone knows how to use the partial pack argument and it does what it sounds like?

I also cannot get IGPHASEACTIVATE.bff to repack, notsure if thats a bug in the repacker as it used to work now I get some error message about array lengths or something.

There was a problem with last version uploaded, try downloading it again.
[viewtopic.php?f=10&t=3717&p=31886#p31886](http://forum.xentax.com/viewtopic.php?f=10&t=3717&p=31886#p31886)
## Post #87
- Username: Arachnus
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Sep 27, 2009 2:58 am
- Post datetime: 2009-09-29T18:12:17+00:00
- Post Title: Re: NfS Shift .BFF files

> Reply from Shelly
>
> I have discovered, that unpacking via *.bat does not work if the Shift Patch 1.01 is installed.

On my machine it works only if I try to unpack an unpatched Shift.

Please make the patched version unpackable too.


Edit:
I think the difference between patched and not patched Shift could be an explanation for why the repacker worked for some and for others not?

You might have done something wrong or missed something, cause batch worked 100% here in my Shift patched! But i saw that even unpacking all the files with Batch command, still remais many folders with BFF files inside, so this files i had to use japamd´s BFFRepacker and quickBMS to work around with them, and worked OK too! maybe this is just cause who wrote the full extraction batch, forget to search in game folders for "ALL" the BFF files, and focused only in the "Pakfiles" folder!

I´m so busy and running now even could make good mods, as i have a little time i´ll try to edit the Batch for really all the BFF´s OK!

Thanks and see you
## Post #88
- Username: mesa
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 02, 2009 6:32 am
- Post datetime: 2009-10-02T10:57:58+00:00
- Post Title: Re: NfS Shift .BFF files

Hi! 

(Sry for my poor english)

I have a problem with Repack tool. The repacked file size is larger than the original. 


I unpacked Escort RS file, which is about 16 MByte, then i got 1106 files, and they are using 40 MByte space in unpacked
I did not made any changes, just used repack gui, and the result is 1 new file, ~40 MByte

I copied this new archive into the right place, but in the Shift game's garage no Escort is visble
Just endless spinning circles...

May the problem is that the new file is not compressed ? 
Thx
## Post #89
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-10-02T17:29:19+00:00
- Post Title: Re: NfS Shift .BFF files

The repacked files are not compressed, yet.

I'll take a look on Escort RS file.
## Post #90
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-10-02T19:48:47+00:00
- Post Title: Re: NfS Shift .BFF files

Just tried repacking ford_escort_rs.bff and it went fine.


I'm using Windows 7 Ultimate 64-bit build 7600
## Post #91
- Username: mesa
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 02, 2009 6:32 am
- Post datetime: 2009-10-02T21:11:38+00:00
- Post Title: Re: NfS Shift .BFF files

japamd: thank you for your quick answer!

I did a try:

1. i unpack ford_escort_rs.bff with Quickbms into D:\nfs_mod\unapcked
2. i did not modify anithing - remember it's just a test
3. i repack them with BFF repacker 1.10121 output folder D:\nfs_mod\new_bff

Repacked 1106 files

The result file is 40 Mbyte, and still did not work in NFS Shift game

Here is a link to the files i used for this test
[http://rapidshare.com/files/287898512/nfs_mod.zip.html](http://rapidshare.com/files/287898512/nfs_mod.zip.html)

Could you check it out? Thank you very much

( Windows XP SP3, .NET 2.0, 3.0, 3.5 SP1 all files up to date )

Keep my eyes on suzuka!
## Post #92
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-10-03T03:54:52+00:00
- Post Title: Re: NfS Shift .BFF files

> Reply from mesa
>
> japamd: thank you for your quick answer!

I did a try:

1. i unpack ford_escort_rs.bff with Quickbms into D:\nfs_mod\unapcked
2. i did not modify anithing - remember it's just a test
3. i repack them with BFF repacker 1.10121 output folder D:\nfs_mod\new_bff

Repacked 1106 files

The result file is 40 Mbyte, and still did not work in NFS Shift game

Here is a link to the files i used for this test
http://rapidshare.com/files/287898512/nfs_mod.zip.html

Could you check it out? Thank you very much

( Windows XP SP3, .NET 2.0, 3.0, 3.5 SP1 all files up to date )

Keep my eyes on suzuka!

Hmmm, I see. I didn't tested the repacked file, when I did it later the game could not load the repacked ford_escord_rs.bff file.

But I have good news. I just managed to make the repack recompress the files while repacking, so we should end with a new BFF file with almost the same size as the original. I'm just finishing some testing and will upload the new version soon.

BTW, the repackaged ford_escord_rs.bff is working now  

Edit: file updated. Download it [here](http://forum.xentax.com/viewtopic.php?f=10&t=3717&st=0&sk=t&sd=a&start=25)
## Post #93
- Username: Arachnus
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Sep 27, 2009 2:58 am
- Post datetime: 2009-10-03T05:18:42+00:00
- Post Title: Re: NfS Shift .BFF files

> Reply from japamd
>
> It's done.

I have attached the utility to this message, you'll need NET Framework 2.0 in order to execute it.



Edited DDS car livery texture   




You just need to put all BFF extracted files in a folder (which can have sub-folders) and all files, don't add or delete extracted files before repacking (adding files to the folder will not harm anything and will be simple ignored).

That's it, enjoy

Great japamd, very thanks!

I think the game runs better in compressed format, now i think we can continue modding almost everything, like in uncompressed method! Saving some FPS and loading times!

You´re the boss
## Post #94
- Username: jaketoox
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Sep 27, 2009 9:15 pm
- Post datetime: 2009-10-03T09:02:50+00:00
- Post Title: Re: NfS Shift .BFF files

BFFRepacker has stopped working........

Seems not working here....using Win7_64....

I really would like to have this, was using version 0.6 and now when i'm back from "Moddingland" i see that there is a version with compression....

waiting for a fix..........

edit: and now seems that i don't have 0.6 neither....  

Jake
## Post #95
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-10-03T14:26:11+00:00
- Post Title: Re: NfS Shift .BFF files

Jake,

Wow, that's embarassing, I forgot to update one component in rar. 

Please download it again and let me know if there's any problems yet.
## Post #96
- Username: jaketoox
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Sep 27, 2009 9:15 pm
- Post datetime: 2009-10-03T16:03:35+00:00
- Post Title: Re: NfS Shift .BFF files

Thanks, now it's working....back to Moddingland....

Jake
## Post #97
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-10-03T17:58:16+00:00
- Post Title: Re: NfS Shift .BFF files

> Reply from jaketoox
>
> Thanks, now it's working....back to Moddingland....

Jake

Ok. Where do you publish your mods?
## Post #98
- Username: mesa
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 02, 2009 6:32 am
- Post datetime: 2009-10-03T19:38:15+00:00
- Post Title: Re: NfS Shift .BFF files

japamd: GREAT JOB!
Thank you very much! 

This is my first Cossie skin (first attempt, just for fun):
## Post #99
- Username: ericboyboy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 03, 2009 7:14 pm
- Post datetime: 2009-10-04T10:39:19+00:00
- Post Title: Re: NfS Shift .BFF files

Hi,

I've dled the BFF Repack thingy but it doesnt work on my computer.
It says " BFFRepacker has Stopped Working "

can some1 please help me to repack BMW_M3_GT2.bff and upload it here for me?


Thanks~
## Post #100
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-04T10:43:41+00:00
- Post Title: Re: NfS Shift .BFF files

maybe it's off-topic but the password used for the FSB archives of the game *edit, ONLY the demo* (like nfs_racemusic.fsb) is the following:
kua0@z^y0$Wsh9HkhG6%Ih*gICV$Do8

so use that one when fsbext asks to insert it during the extraction
## Post #101
- Username: Baron Greenback
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 04, 2009 6:13 am
- Post datetime: 2009-10-04T10:52:02+00:00
- Post Title: Re: NfS Shift .BFF files

> Reply from mesa
>
> japamd: GREAT JOB!
Thank you very much! 

This is my first Cossie skin (first attempt, just for fun):

Loving the Repsol livery! That's what I was going to do myself until I found that the repacker (old version) was having problems with the Escort bff.

Big thanks to japamd for the repacker!


> Reply from Bugtest
>
> maybe it's off-topic but the password used for the FSB archives of the game (like nfs_racemusic.fsb) is the following:
kua0@z^y0$Wsh9HkhG6%Ih*gICV$Do8

so use that one when fsbext asks to insert it during the extraction

Sorry to continue the off topic-ness;
I used [MusicPlayerEx](http://jerome.jouvie.free.fr/Fmod/Projects/Project1.php) to extract the FSB sound archives without using a password.
## Post #102
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-04T14:55:58+00:00
- Post Title: Re: NfS Shift .BFF files

ops, I forgot to specify that I was referring to the FSB archives of the demo version so I thought (because I don't have the game) that also those of the retail were encrypted.
## Post #103
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-10-04T15:53:20+00:00
- Post Title: Re: NfS Shift .BFF files

mesa, it's looking good!

> Reply from ericboyboy
>
> Hi,

I've dled the BFF Repack thingy but it doesnt work on my computer.
It says " BFFRepacker has Stopped Working "

can some1 please help me to repack BMW_M3_GT2.bff and upload it here for me?


Thanks~

Demo or full version of game?

The tool has issues with demo version.
## Post #104
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-10-04T23:36:46+00:00
- Post Title: Re: NfS Shift .BFF files

Just added a new tool: BFF Inject to update only modified files.

I think this is handy if you're changing just a few files and just need to update them instead of rebuilding the entire thing.

Download [here](http://forum.xentax.com/viewtopic.php?f=10&t=3717&st=0&sk=t&sd=a&start=15#p31886)

Screenshot


New files can be greater in size than original ones, the tool will reorganize the output BFF archive so offsets will point to the new location inside the archive.

I'm working on a tool to redistribute mods in an automated way and even restore changes made by the tool.

Enjoy
## Post #105
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-10-05T15:20:06+00:00
- Post Title: Re: NfS Shift .BFF files

Finished the compiler, you just need to leave your modded files in a folder (just the edited ones), the compiler will join all your files in compressed form.




Created ZIP contents


The compiler will create a ZIP file with BFF Inject tool and the modded files inside a compressed file. To install the mod just extract all files and fire Injector.exe, it will read Install.bfi script and update required BFF archives in game folder.
## Post #106
- Username: mesa
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 02, 2009 6:32 am
- Post datetime: 2009-10-06T09:39:34+00:00
- Post Title: Re: NfS Shift .BFF files

BFF Inject tool great job also.

But how does it exactly work?  
If i set the source directory of modified files, always rebuild them (1106)
## Post #107
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-10-07T01:29:23+00:00
- Post Title: Re: NfS Shift .BFF files

Inject tool can be used to inject just some files directly into BFF archive. For example, if you're modding textures, you can leave only textures folder and the working dds files, edit them then inject those files into BFF without rebuilding the entire archive.

For modders the Compiler is working great, it's a very straightforward way to publish mods that can be installed on original/compressed form game (without -loose setting), maintaining loading times reasonable (-loose setting slows down races loading times badly).
## Post #108
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2009-10-12T15:49:44+00:00
- Post Title: Re: NfS Shift .BFF files

Hi!

I wrote a German Tutorial great Bff-Tools 

[http://sommergemuese.klee.in/2009/10/nf ... bff-tools/](http://sommergemuese.klee.in/2009/10/nfs-shift-easy-mod-publishing-und-using-mit-den-bff-tools/)
## Post #109
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-10-12T16:50:57+00:00
- Post Title: Re: NfS Shift .BFF files

> Reply from sommergemuese
>
> Hi!

I wrote a German Tutorial great Bff-Tools 

http://sommergemuese.klee.in/2009/10/nf ... bff-tools/

Wow, nice work! Maybe you can make an english version of your tutorial, google translator is not that good translating from german
## Post #110
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2009-10-12T19:23:26+00:00
- Post Title: Re: NfS Shift .BFF files

If you help me .. my English isn't best 

I could Translate it and you correct the sentences, grammar and so on
## Post #111
- Username: japamd
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Sep 20, 2009 5:26 am
- Post datetime: 2009-10-14T02:03:26+00:00
- Post Title: Re: NfS Shift .BFF files

> Reply from sommergemuese
>
> If you help me .. my English isn't best 

I could Translate it and you correct the sentences, grammar and so on

Cool, we can do that, and don't worry, english isn't my mother tongue too, by the way I'm Brazilian
## Post #112
- Username: koler
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 15, 2010 12:33 am
- Post datetime: 2010-07-15T07:24:48+00:00
- Post Title: Re: NfS Shift .BFF files

Hello friends,    i would like to ask all of you,  If somebody can help me with my problem.

i try to translate NFS Shift  all text to my language.  I have translated extracted TXT files  from  DAT files from text files.  I have not completed trabnslation because I can not test already translated sentences and strings.      So my problem is:  

I am looking for tool for compiling extracted TXT file back to the DAT and then  imúport to game. Maybe I am amateur in this area. So If somebody have a skills with extracted langtuage filoes, please for help.  
 Thanks. 
Thanks
Thanks
## Post #113
- Username: paldrive
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 25, 2010 5:44 am
- Post datetime: 2010-07-25T17:12:28+00:00
- Post Title: Re: NfS Shift .BFF files

Hello! I'm trying to mod myself the XBOX360 version of NFS shift, I successfully extracted some pakfiles with quickbms but I cannot repack bffs using BFFTools, which I suppose is working only for PC version of Shift.
Can the makers of BFFtools make an XBOX360 version? As the difference between the bffs of the 2 versions should be big-endian ("pak") for XBOX and little-endian for PC ("kap"), maybe modifying the BFF.dll and the repacker could be easy for those who know how...   
Thanks in advance for your help!
## Post #114
- Username: desperados
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jul 22, 2009 10:33 pm
- Post datetime: 2011-04-29T20:17:32+00:00
- Post Title: Re: NfS Shift .BFF files

Hello
Unpack .BFF data xbox 360 quickbms ok!
No back package tool  PC - japamd  - "BFF Repacker, BFF Inject"  in xbox 360 

Please very please, upgrade tool in  - japamd  - "BFF Repacker, BFF Inject" or xbox 360
PC version  ("kap")  -- Xbox 360  ("pak")  - data xbox in  mirrored

I'm sorry bad of my english

Xbox data BOOTTEXTDB.bff:
[http://www.sendspace.com/file/96b6xy](http://www.sendspace.com/file/96b6xy)
## Post #115
- Username: Alphaziel
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Nov 25, 2011 5:26 am
- Post datetime: 2011-11-24T21:49:02+00:00
- Post Title: Re: NfS Shift .BFF files

Nice to meet you. I find your BFF Tools in nogripracing.com and use it.
Thank you for the exhibition of a very convenient tool   

Do it in the face of us, the issue of one …

I use this BFF Tools in NFS SHIFT 2 UNLEASHED, but BFF Repacker does not function … 
A version using in us is a version with following screenshot, but seems to be older than the version of this topic …



20111125_062919.png (11.47 KiB) Viewed 63 times



I did it and confirmed it, but DL was the same from the downloading link first of the topic that I used it and entered (the second downloading was 404 Not Found.)

Which may you download BFF Repacker 1.0359 from?

Oh, please forgive it for poor English by the machine translation because I am a human being of the Asian area
