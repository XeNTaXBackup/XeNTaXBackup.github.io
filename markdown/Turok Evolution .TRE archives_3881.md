## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-11-18T23:04:25+00:00
- Post Title: Turok Evolution .TRE archives

Hello to all of you!

This is my first post and, well, simultaneously a call for help. Why I haven't posted earlier? Well, there was some problem with my registration and I never investigated the causes.  Luckily some admin activated my account - Thanks to whoever did that!  
I'm quite active in the VGM ripping scene and recently got a request for Turok: Evolution. All files but the videos are inside a TRE archive (at least in the XBox and GameCube version). I've never seen a similar HEX structure (file and folder tables among the single files) and so far I couldn't find any extractor. I've tried DragonUnpacker, Multi EX commander, GameExtractor - all without luck.
Does anyone know a program that is capable to extract the files?
Thanks a lot guys! 

Regards, Timo
## Post #2
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2009-11-18T23:19:36+00:00
- Post Title: Turok Evolution .TRE archives

I don't know of an extractor, but maybe you could post an archive and someone could write a BMS script.
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-11-19T08:24:42+00:00
- Post Title: Turok Evolution .TRE archives

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-11-19T17:07:38+00:00
- Post Title: Turok Evolution .TRE archives

```
Get NUM_FILES long
Get UNK long

# Calculate data offset
Set OFF_FILE_DATA long NUM_FILES
Math OFF_FILE_DATA *= 16
Math OFF_FILE_DATA += 4

For I = 0 < NUM_FILES
	# File info
	Get SIZE long
	Get UNK long
	Get UNK long
	Get UNK long

	# Extract file
	Log I OFF_FILE_DATA SIZE
	Math OFF_FILE_DATA += SIZE
Next I

Get FILE_SIZE asize
Print "OK. Final OFF_FILE_DATA = %OFF_FILE_DATA%, expected %FILE_SIZE%"

```
## Post #5
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-11-22T10:14:13+00:00
- Post Title: Turok Evolution .TRE archives

Thank you kindly for this script. However if I extract another TRE archive, it splits right in the middle of plain text lists. So maybe this TRE file is different than the others.
I've searched them a bit via HEX and found a kind of script in plain text inside the archive that seems to be used to extract its contents. At least is has a list with files, sizes and offsets, but the latter don't match to the container itself. When I get to it, I'll upload one of these other containers tomrrow earliest. Maybe the script it's imortable in MultiEx commander or GameExtractor.
Thanks!
## Post #6
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-11-25T11:12:19+00:00
- Post Title: Turok Evolution .TRE archives

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-11-27T19:38:18+00:00
- Post Title: Turok Evolution .TRE archives

The contents of this post was deleted because of possible forum rules violation.
## Post #8
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-11-27T23:06:16+00:00
- Post Title: Turok Evolution .TRE archives

Fixed:

```
Get NUM_FILES long

For I = 0 < NUM_FILES
   # File info
   Get OFFSET long
   Get SIZE long
   Get UNK long
   Get UNK long

   # Extract file
   Log I OFFSET SIZE
Next I

```


By the way, many of the extracted files are also like TRE files, so you can extract them with the same script!

There are also some WAVs.
## Post #9
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-11-29T18:07:50+00:00
- Post Title: Turok Evolution .TRE archives

Hm, still not quite right: Extract the supertree0.tre and look at the first few files - they are still split in the middle.
Sorry to bother you...
## Post #10
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-12-04T18:55:45+00:00
- Post Title: Turok Evolution .TRE archives

The contents of this post was deleted because of possible forum rules violation.
## Post #11
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-12-04T19:39:46+00:00
- Post Title: Turok Evolution .TRE archives

> Reply from AlphaTwentyThree
>
> Hm, still not quite right: Extract the supertree0.tre and look at the first few files - they are still split in the middle.
Sorry to bother you...

I don't see any splitted file. Check if you're using the latest version of the script, and if it doesn't work, tell me the exact container & file no of the splitted file.
And what's wrong with the GC version?
## Post #12
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-12-05T00:56:37+00:00
- Post Title: Turok Evolution .TRE archives

> Reply from GameZelda
>
> AlphaTwentyThree wrote:Hm, still not quite right: Extract the supertree0.tre and look at the first few files - they are still split in the middle.
Sorry to bother you...

I don't see any splitted file. Check if you're using the latest version of the script, and if it doesn't work, tell me the exact container & file no of the splitted file.
And what's wrong with the GC version?
Oh I'm so sorry!    I looked at the files once again and I saw that the files are not split but are single command files. I thought I saw some file list cut in the middle, but that's apparently not that case.
However, the GameCue version gives back the message "0 files found". Could be a slightly different header - maybe you can post another script for the GameCube version? Thanks!
## Post #13
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-12-07T04:29:29+00:00
- Post Title: Turok Evolution .TRE archives

Ok, figured it out after a while: The GameCube version just has a big endian header (n00by, I know...). So just add 
```
Endian big
```
 to the above script and it works. 
But can anyone tell me why the sequence 

```
If NUM_FILES > 65536
   ReverseLong NUM_FILES
   Endian big
EndIf
```

doesn't work when added to the above script? Thanks
## Post #14
- Username: evilpie
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Nov 30, 2009 5:13 am
- Post datetime: 2009-12-07T21:49:38+00:00
- Post Title: Turok Evolution .TRE archives

What doesnt work?
Why you want to do this, when you already changed it to big endians?
Post whole code..
## Post #15
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-12-08T08:44:21+00:00
- Post Title: Turok Evolution .TRE archives

I wanted to make it work for both archive formats. That' the code I tried:

```
If NUM_FILES > 65536
   ReverseLong NUM_FILES
   Endian big
EndIf

For I = 0 < NUM_FILES
   # File info
   Get OFFSET long
   Get SIZE long
   Get UNK long
   Get UNK long

   # Extract file
   Log I OFFSET SIZE
Next I
```

Message is always: 0 files found
## Post #16
- Username: evilpie
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Nov 30, 2009 5:13 am
- Post datetime: 2009-12-08T14:00:42+00:00
- Post Title: Re: Turok Evolution .TRE archives

I did some test, and its seems like the NUM_FILES is Little Endian and everything else is Big Endian?

```
{
    uint NumFiles;
    struct FILES
    {  
        BigEndian ();
        uint Offset;
        if (Offset < FileSize())
        {
            Printf ("Valid Of: %d\n", Offset);
        }
        
        uint Size;
        uint unk;
        uint unk2;
    } files[NumFiles] <optimize=false>;
} test <optimize=false>;
```


```

print "%NUM_FILES%"
Endian Big
For I = 0 < NUM_FILES
   # File info
   Get OFFSET long
   #Get SIZE long
   GET S1 BYTE
   GET S2 BYTE
   GET S3 BYTE
   GET S4 BYTE
   #Get Size Long
   
   print "%S1% %S2% %S3% %S4%"
   
   Set Size = S1
   Math S2 <<= 8
   Math S3 <<= 16
   Math S4 <<= 24
   Math Size += S3
   Math Size += S2
   Math Size += S1
   
   Get UNK long
   Get UNK long
   print "%OFFSET% %Size%" 
	
   # Extract file
   Log I OFFSET Size
Next I
```
## Post #17
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2010-12-28T01:27:27+00:00
- Post Title: Re: Turok Evolution .TRE archives

I am also interested in opening the .TRE archives in this game for the purposes of ripping the soundtrack and the sound effects. does anyone know of any programs that can open the .TRE archive on the PS2 version? how do you use the scripts that are posted on here what programs are they used for Please help, Thanks.
## Post #18
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-12-28T14:45:01+00:00
- Post Title: Re: Turok Evolution .TRE archives

> Reply from gamehead
>
> how do you use the scripts that are posted on here what programs are they used for Please help, Thanks.
[http://aluigi.altervista.org/papers.htm#quickbms](http://aluigi.altervista.org/papers.htm#quickbms)
## Post #19
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2010-12-28T21:29:32+00:00
- Post Title: Re: Turok Evolution .TRE archives

[quote="AlphaTwentyThree"][quote="gamehead"]how do you use the scripts that are posted on here what programs are they used for Please help, Thanks.

Link Removed

Let's check the safety ratings on sites before you post them shall we. The linked site is flagged red by mcafee b/c it contains bad stuff. 

[http://www.siteadvisor.com/sites/aluigi.altervista.org](http://www.siteadvisor.com/sites/aluigi.altervista.org)

Any other sites that may have these programs?
## Post #20
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2011-01-04T16:27:06+00:00
- Post Title: Re: Turok Evolution .TRE archives

OK I now have QuickBMS up and running, Found it on the Xentax blog page now is there a script for the .TRE archives of the PS2 version of Turok Evolution? I tried the ones here and it extracted the files but now they all have filenames from 0 to 7579 and with no extension. they crash MFAudio.  what am I doing wrong? do I have the wrong script? Please help. Thanks.

Next I will be trying Driver 3 with this program and a few other games with archives that I can't open. But that will be down the road.
## Post #21
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2011-01-05T01:07:58+00:00
- Post Title: Re: Turok Evolution .TRE archives

> Reply from gamehead
>
> AlphaTwentyThree wrote:gamehead wrote:how do you use the scripts that are posted on here what programs are they used for Please help, Thanks.

Link Removed

Let's check the safety ratings on sites before you post them shall we. The linked site is flagged red by mcafee b/c it contains bad stuff. 

http://www.siteadvisor.com/sites/aluigi.altervista.org

Any other sites that may have these programs?
That site is owned by the creator of QuickBMS, and all of the other programs there (aluigi).
## Post #22
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2011-01-05T01:54:51+00:00
- Post Title: Re: Turok Evolution .TRE archives

Caboose wrote:

> That site is owned by the creator of QuickBMS, and all of the other programs there (aluigi).

Well I just didnt want anyone getting a virus or anything bad b/c I got a nasty one a few months ago and I had to reformat my PC. not fun, for maybe an hour or 2 I officially had a brick. BTW I do have QuickBMS now and I'm trying to fiigure out how to use it, I need a script for Turok Evolution on the PS2. I tried the other scripts on this thread and then after that I tried Game extractor and both programs extracted the files but the files were still useless to me. maybe I used the wrong script. Please Help. Thanks.
## Post #23
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-10-01T22:53:04+00:00
- Post Title: Re: Turok Evolution .TRE archives

I know this was a REALLY long time ago and I normally don't do this, but I just found a way to get the original folder structure for these files!!!  Seems like the array sorting function isn't so useless after all.  So here's the final script:

```
# note: CORRECT NAMES!!!
# (c) 2012-10-02 by AlphaTwentyThree of XeNTaX

get FILES long
for i = 0 < FILES
	get OFFSET long
	get SIZE long
	get DATA_CRC long
	get NAME_CRC long
	putArray 0 i OFFSET
	putArray 1 i SIZE
next i
print "sorting array"
sortarray 0 1
getArray NAMEOFF 0 2
goto NAMEOFF
for i = 0 < FILES
	getCT NAME string 0x0d
	get DUMMY byte
	getArray OFFSET 0 i
	getArray SIZE 1 i
	log NAME OFFSET SIZE
next i
```
## Post #24
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2012-10-03T05:59:12+00:00
- Post Title: Re: Turok Evolution .TRE archives

> Reply from AlphaTwentyThree
>
> I know this was a REALLY long time ago and I normally don't do this, but I just found a way to get the original folder structure for these files!!!  Seems like the array sorting function isn't so useless after all.  So here's the final script:
Code: Select all# extracts the contents of the TRE archives from Turok: Evolution (PS2)
# note: CORRECT NAMES!!!
# (c) 2012-10-02 by AlphaTwentyThree of XeNTaX

get FILES long
for i = 0 < FILES
	get OFFSET long
	get SIZE long
	get DATA_CRC long
	get NAME_CRC long
	putArray 0 i OFFSET
	putArray 1 i SIZE
next i
print "sorting array"
sortarray 0 1
getArray NAMEOFF 0 2
goto NAMEOFF
for i = 0 < FILES
	getCT NAME string 0x0d
	get DUMMY byte
	getArray OFFSET 0 i
	getArray SIZE 1 i
	log NAME OFFSET SIZE
next i

Hi I tried this script using QuickBMS and I get this error when trying to open the STREE0.TRE archive from the PS2 version of Turok Evolution. The first error is the edited version and the second is the original from here.

ERROR: Invalid command "sortarray" or arguments 2 at line 11

ERROR: Invalid command "sortarray" or arguments 2 at line 15


Press RETURN to quit.

::Program Closes when Return is pressed::

Any ideas why this is happening? I tried 2 different versions of the script. I removed the stuff on top like where it says Xentax on one and the other is completely original. Both failed to extract files. What am I doing wrong Please help. I've been trying to open this archive for a long time. It doesn't seem to like that sortarray line. I even made the script file with a .BMS extension and I got the same error. Please help, Thanks.
## Post #25
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-10-03T12:31:22+00:00
- Post Title: Re: Turok Evolution .TRE archives

You're using an old QuickBMS version. Get the newest one @ [http://aluigi.org/quickbms.htm](http://aluigi.org/quickbms.htm)
## Post #26
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-10-03T12:33:05+00:00
- Post Title: Re: Turok Evolution .TRE archives

Here's also the version for all other *.tre archives (inside the big tre):

```
# note: for the main STREE.TRE use my other script!
# (c) 2012-10-02 by AlphaTwentyThree of XeNTaX

include "func_getTYPE.bms"
get FILES long
for i = 0 < FILES
	get OFFSET long
	get SIZE long
	get DATA_CRC long
	get NAME_CRC long
	putArray 0 i OFFSET
	putArray 1 i SIZE
	putarray 2 i NAME_CRC
next i
print "sorting array"
sortarray 0 1
get BNAME basename
string BNAME += "_"
for i = 0 < FILES
	getArray OFFSET 0 i
	getArray SIZE 1 i
	getArray CRC 2 i
	putVarChr MEMORY_FILE SIZE 0
	log MEMORY_FILE 0 0
	append
	log MEMORY_FILE OFFSET SIZE
	append
	string CRC p= "_0x%08x" CRC
	set NAME BNAME
	string NAME += i
	string NAME += CRC
	callfunction getTYPE 1
	if EXT != ""
		string NAME += EXT
	endif
	log NAME 0 SIZE MEMORY_FILE
next i
```
## Post #27
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2012-10-03T21:41:14+00:00
- Post Title: Re: Turok Evolution .TRE archives

> Reply from AlphaTwentyThree
>
> Here's also the version for all other *.tre archives (inside the big tre):
Code: Select all# extracts *.TRE archives from Turok: Evolution (PS2)
# note: for the main STREE.TRE use my other script!
# (c) 2012-10-02 by AlphaTwentyThree of XeNTaX

include "func_getTYPE.bms"
get FILES long
for i = 0 < FILES
	get OFFSET long
	get SIZE long
	get DATA_CRC long
	get NAME_CRC long
	putArray 0 i OFFSET
	putArray 1 i SIZE
	putarray 2 i NAME_CRC
next i
print "sorting array"
sortarray 0 1
get BNAME basename
string BNAME += "_"
for i = 0 < FILES
	getArray OFFSET 0 i
	getArray SIZE 1 i
	getArray CRC 2 i
	putVarChr MEMORY_FILE SIZE 0
	log MEMORY_FILE 0 0
	append
	log MEMORY_FILE OFFSET SIZE
	append
	string CRC p= "_0x%08x" CRC
	set NAME BNAME
	string NAME += i
	string NAME += CRC
	callfunction getTYPE 1
	if EXT != ""
		string NAME += EXT
	endif
	log NAME 0 SIZE MEMORY_FILE
next i

Alright that seems to have worked, I downloaded the version you linked me to and that opened the big .tre file and it's showing me all the stuff inside. I tried the new script you posted to extract everything from the small .tre files and I now get this error:

requested script  "func_getTYPE.bms" not found

Press RETURN to quit

I'm getting closer but is there something i'm missing from my program or no? Thanks again.
## Post #28
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-10-06T01:17:24+00:00
- Post Title: Re: Turok Evolution .TRE archives

The func_getTYPE.bms is located here: [viewtopic.php?f=13&p=69577#p69577](http://forum.xentax.com/viewtopic.php?f=13&p=69577#p69577)
## Post #29
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2012-10-07T01:19:44+00:00
- Post Title: Re: Turok Evolution .TRE archives

> Reply from AlphaTwentyThree
>
> The func_getTYPE.bms is located here: viewtopic.php?f=13&p=69577#p69577

Thanks for the script, it did work. I'm after the SFX and music. They are stored in either .VAG files or .AAA files inside a sound.tre archive. I need to get the right interleave of the files. I'm using a program called ADPCM player which is just like MFAudio but better. ADPCM player can't see the raw .tre archives but could see the sound.tre archive some of the files could be played but the audio is garbled and the settings cannot be changed. When trying an extracted audio file from sound.tre  the settings can be changed and I just need to find the right interleave setting and it's still a bit garbled. Can you suggest a program to convert these files to WAV/mp3 so I can put them on my iPod. I'm not sure where I can upload one of the files as it's too big for the forum and I'm not sure what's a good file hosting site.
## Post #30
- Username: Shichi1337
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 09, 2022 5:01 pm
- Post datetime: 2022-12-09T10:06:19+00:00
- Post Title: Re: Turok Evolution .TRE archives

Hello, i've messed around a while with the .bms script in the old thread here: [viewtopic.php?t=3881](https://forum.xentax.com/viewtopic.php?t=3881)
But nothing seems to work properly, do I miss something or what else?

Every time I tried, it gives me this error:

```
- select input archives/files, type * for the whole folder and subfolders
- select output folder where extracting files
- filter string: "*"
- filter   1: *
- start the scanning of the input folder: C:\Stuff\Apps\quickbms\in
- open input file C:\Stuff\Apps\quickbms\in\supertree0.tre
- open script C:\Stuff\Apps\quickbms\turok_evolution.bms
- set output folder C:\Stuff\Apps\quickbms\out

  offset           filesize   filename
--------------------------------------

- error in src\extra\xalloc.c line 703: xdbg_realloc()

Error: memory allocation problem
       Access denied


press ENTER to quit
```

I don't know if specific regional changes were made in this Turok Evolution .TRE file, because I ripped my game, basically a german version of the game, but as you see...

Any help would be appreciated.
