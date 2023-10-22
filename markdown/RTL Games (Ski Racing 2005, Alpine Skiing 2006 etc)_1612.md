## Post #1
- Username: nikita
- Rank: VIP member
- Number of posts: 28
- Joined date: Sun Dec 11, 2005 7:34 pm
- Post datetime: 2005-12-11T11:37:53+00:00
- Post Title: RTL Games (Ski Racing 2005, Alpine Skiing 2006 etc)

would be nice with support for this...
The format looks abit like the genereal "PACK" header type archive, however must be slightly different, since it wont open correct.

This sample is from RTL Alpine Skiing 2006
should contain some txt files! and folder layout.
[balance.zip](https://xentaxbackup.github.io/file/487_balance.zip)
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-11T16:12:58+00:00
- Post Title: RTL Games (Ski Racing 2005, Alpine Skiing 2006 etc)

Okay,I've written a script for it.

Unfortunately, it will extract the files in compressed state. I have not figured out what type of compression they used, might be an altered zip method. 

Here's what MultiEx Com gives as specifications: 

```
// THIS IS AN AUTOMATED SPECIFICATION
// READ WITH CARE
// ----------------------------
// LEGEND
// ----------------------------
// ==> (Jump to offset)
// #DECLARE (Set variable to value)
// $$ CALCULATE (Calculate a new value)
// ** (Section that repeats itself on condition)
// // (Comment)
// uint32{4} (Unsigned 32-bit value, 4 bytes)
// uint16{2} (Unsigned 16-bit value, 2 bytes)
// ubyte{1} (Unsigned 8-bit value, 1 byte)
// char{n} (String value, n bytes in length
// ----------------------------


// Format Specification


FileID   		'PACK'
uint32{4}		Version
uint32{4}		FileNum
uint32{4}		TableEnd


** Start Repeated entry (T) {FileNum}
#DECLARE CSO = CURRENT OFFSET
uint32{4}		CompressedSize
#DECLARE UCO = CURRENT OFFSET
uint32{4}		UncompressedSize
#DECLARE FOO = CURRENT OFFSET
uint32{4}		Offset
uint32{4}		FilenameOffset
uint32{4}		CRC
uint32{4}		Method
#DECLARE NextEntry = CURRENT OFFSET


==>FilenameOffset
char{}   		Filename


// Resources have a name (Filename), are located at Offset and have a size of CompressedSize


==>NextEntry
** End Repeated entry (T)
// ----------------------------
// MexCom - Recreation complete 

```
 

The BMS script: 

```
IDString 0 PACK ;
Get Version Long 0 ;
Get FileNum Long 0 ;
Get TableEnd Long 0 ;
For T = 1 To FileNum ;
SavePos CSO 0 ;
Get CompressedSize Long 0 ;
SavePos UCO 0 ;
Get UncompressedSize Long 0 ;
SavePos FOO 0 ;
Get Offset Long 0 ;
Get FilenameOffset Long 0 ;
Get CRC Long 0 ;
Get Method Long 0 ;
SavePos NextEntry 0 ;
GoTo FilenameOffset 0 ;
Get Filename String 0 ;
Log Filename Offset CompressedSize FOO CSO ;
GoTo NextEntry 0 ;
Next T ;

```


And get the BMS file from the attachment. Use it to open the PAK files with MultiEx Commander.
[pak.zip](https://xentaxbackup.github.io/file/488_pak.zip)
## Post #3
- Username: nikita
- Rank: VIP member
- Number of posts: 28
- Joined date: Sun Dec 11, 2005 7:34 pm
- Post datetime: 2005-12-11T21:16:19+00:00
- Post Title: RTL Games (Ski Racing 2005, Alpine Skiing 2006 etc)

Could it be it uses the old PACK compression? if this is just a new version that is.
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-11T21:20:12+00:00
- Post Title: RTL Games (Ski Racing 2005, Alpine Skiing 2006 etc)

I don't know the old compression, I haven't dealt with these RTL game files before. Do your know the compression of the old RTL games PACK format?
## Post #5
- Username: nikita
- Rank: VIP member
- Number of posts: 28
- Joined date: Sun Dec 11, 2005 7:34 pm
- Post datetime: 2005-12-11T21:30:31+00:00
- Post Title: RTL Games (Ski Racing 2005, Alpine Skiing 2006 etc)

not really.. I know Gameextractor almost is able to open them.. But not identifiable by plugins since GE has so many .pak plugins..

Btw donated! Great job on MXC

btw this dll is in gamedir, and ive seen it before! maybe it has something to do with the packfiles?

Attached..
shfolder_x.dll
[shfolder_x.zip](https://xentaxbackup.github.io/file/489_shfolder_x.zip)
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-11T21:34:36+00:00
- Post Title: RTL Games (Ski Racing 2005, Alpine Skiing 2006 etc)

Thanks! Never mind the last sentence in the mail I sent you, I already know your nick
## Post #7
- Username: nikita
- Rank: VIP member
- Number of posts: 28
- Joined date: Sun Dec 11, 2005 7:34 pm
- Post datetime: 2005-12-11T21:35:30+00:00
- Post Title: RTL Games (Ski Racing 2005, Alpine Skiing 2006 etc)

Look at my edited post. hope this helps
## Post #8
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-11T21:39:51+00:00
- Post Title: RTL Games (Ski Racing 2005, Alpine Skiing 2006 etc)

Hmm, no, I don't think that's the one. I only found some two novel functions in there:

SHGetFolderPathA
SHGetFolderPathW

They don't look like having anything to do with compression.
## Post #9
- Username: nikita
- Rank: VIP member
- Number of posts: 28
- Joined date: Sun Dec 11, 2005 7:34 pm
- Post datetime: 2005-12-11T21:41:25+00:00
- Post Title: RTL Games (Ski Racing 2005, Alpine Skiing 2006 etc)

if just game extractor could identify which plugin it uses!

Right got a memcard.raw. so seems to be a console conversion..

[http://wiki.xentax.com/index.php/Skispr ... r_Cup_2005](http://wiki.xentax.com/index.php/Skisprung_Winter_Cup_2005)

RTL Pack format.
However seems to be older format
## Post #10
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-11T21:52:02+00:00
- Post Title: RTL Games (Ski Racing 2005, Alpine Skiing 2006 etc)

That's actually the id Software PACK format. See how all those games that use the Quake 2 engine are in there? It comes as a surprise to me now that the Skisprung game is also in the list. If true, then the Skisprung game used the id Software .PAK format. These are NOT compressed.
## Post #11
- Username: nikita
- Rank: VIP member
- Number of posts: 28
- Joined date: Sun Dec 11, 2005 7:34 pm
- Post datetime: 2005-12-11T21:54:20+00:00
- Post Title: RTL Games (Ski Racing 2005, Alpine Skiing 2006 etc)

:/
## Post #12
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-12T00:07:19+00:00
- Post Title: RTL Games (Ski Racing 2005, Alpine Skiing 2006 etc)

Hi mate,

I will take a look at the file for you - chances are that Game Extractor doesn't decompress the files either.

In regards to finding out the plugin in Game Extractor...
1. If you have the full version, and the archive is savable, then click on the save button and the plugin will be selected on the right.
2. I think you can also select a file on the left, and click the File Information button and it tells you the plugin - I can't remember if this happens or not though
3. If you export the file list, the plugin should be written somewhere near the top of the exported file
4. Not sure what else can be done... 

Maybe I will look into adding this in somewhere - I have a lot of things I need to do to Game Extractor but its just a matter of getting time.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #13
- Username: nikita
- Rank: VIP member
- Number of posts: 28
- Joined date: Sun Dec 11, 2005 7:34 pm
- Post datetime: 2005-12-12T08:39:22+00:00
- Post Title: RTL Games (Ski Racing 2005, Alpine Skiing 2006 etc)

Hey i got the full version yeah.... If u are watto, i sended u a sample frmo a game called Onimusha 3. Maybe u remember me
## Post #14
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2005-12-12T11:24:55+00:00
- Post Title: RTL Games (Ski Racing 2005, Alpine Skiing 2006 etc)

I have created the unpacker for all the packages used in the games developed by 49Games: [http://www.49games.de](http://www.49games.de)

[http://aluigi.altervista.org/papers.htm#u49gext](http://aluigi.altervista.org/papers.htm#u49gext)

Instead Ski Racing 2005 uses total different formats, the FSB files contain header-less wave files (have not checked if they use strange codecs) while the main .BND file is a Gamebryo format which I don't know what type of data contain..
## Post #15
- Username: nikita
- Rank: VIP member
- Number of posts: 28
- Joined date: Sun Dec 11, 2005 7:34 pm
- Post datetime: 2005-12-12T16:22:16+00:00
- Post Title: RTL Games (Ski Racing 2005, Alpine Skiing 2006 etc)

Great Ur a GOD 
/kisses Bugtest

However is there a way to reverse the process *create pak* files.
Since the game wont accept unpacked files, the whole modding process is kinda killed.
## Post #16
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2005-12-12T17:10:33+00:00
- Post Title: 

> Reply from nikita
>
> 
However is there a way to reverse the process *create pak* files.

Unfortunately not, that's why I have no source code for the decompression algorithm and have used just the ripped function from the game executable.
At the moment I don't have enough knowledge about compression algorithms (except zlib), sorry.
## Post #17
- Username: nikita
- Rank: VIP member
- Number of posts: 28
- Joined date: Sun Dec 11, 2005 7:34 pm
- Post datetime: 2005-12-12T18:28:20+00:00
- Post Title: 

Would there be a way to make the game.exe use unpacked files instead then? Or is this a dead end to.
## Post #18
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2005-12-12T18:39:37+00:00
- Post Title: 

> Reply from nikita
>
> Would there be a way to make the game.exe use unpacked files instead then? Or is this a dead end to.

I think this is not possible because the game looks for the .pak files, so there is no easy way for modify it.
Anyway I have in mind to write (have just started it now) a program for testing many compression algorithms which will be very useful for finding what compression is used on any file, work in progress...
## Post #19
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2005-12-13T17:40:02+00:00
- Post Title: 

No good news, unfortunately.
I have just finished that experimental program (about 23 compression algorithms supported at the moment) and have found nothing about the compression used by the game.
## Post #20
- Username: davenjohn
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jan 28, 2011 1:34 pm
- Post datetime: 2011-01-28T05:38:15+00:00
- Post Title: 

So I grew up a skier but have snowboarded for over 17 years, I constantly find myself going back and forth between the 2, I love both. I finally have come up with a backcountry solution so you can enjoy both sports.
