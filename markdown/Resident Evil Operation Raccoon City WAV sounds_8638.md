## Post #1
- Username: Nemesiscv
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Mar 19, 2012 4:16 pm
- Post datetime: 2012-03-26T04:15:49+00:00
- Post Title: Resident Evil Operation Raccoon City WAV sounds

Hi !

So I'm still with REORC (If some of you saw my thread in the Game Archives forum) and now with the sound.
There is one huge .pck file, called "streamed.pck". I extract the files in it with Ravioli, and I have many WAV that won't play.
I know you're thinking "Convert them to OGG with ww2ogg". But I tried, and it convert it into a OGG file... And it's doesn't work neither.
I tried Audacity, open the WAV, the OGG, impart them as RAW but I just have some noise.

So I've uploaded a sound file and I hope you guys might help me ! 

```
http://www.mediafire.com/?v81058tk1l1f995
```


Best,

Nemesiscv
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2012-03-26T09:24:21+00:00
- Post Title: Resident Evil Operation Raccoon City WAV sounds

Man I am going to get tired of saying this.

> You need to use the new codebooks, instead of
>
> Code: Select allww2ogg.exe streamed_00008431.wav
>
> do
>
> Code: Select allww2ogg.exe --pcb packed_codebooks_aoTuV_603.bin streamed_00008431.wav
>
> 
>
> This is mentioned in the readme, fwiw.
## Post #3
- Username: Nemesiscv
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Mar 19, 2012 4:16 pm
- Post datetime: 2012-03-26T13:27:36+00:00
- Post Title: Resident Evil Operation Raccoon City WAV sounds

Hi ! Thanks for you answer ! I've been searching for a long time and I'm so sorry I did saw your message.

But since I'm a total noob, I don't understand what I have to do... :/
## Post #4
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2012-03-26T22:38:29+00:00
- Post Title: Resident Evil Operation Raccoon City WAV sounds

How did you run ww2ogg? Since you didn't recognize the command line, I'll assume you just dragged and dropped the file onto it.  You can make a .bat that runs the .exe with any files you drop onto it.

Create a text file with Notepad with the following text:
```
:getfile
if "%~1"=="" goto end
ww2ogg.exe --pcb packed_codebooks_aoTuV_603.bin "%~1"
shift
goto getfile
:end
```
Save it as ww2ogg.bat in the same folder as ww2ogg.exe, you can then drop files (but not folders) onto the .bat and it should convert them correctly.

I haven't tested this but it's based on other things I've slapped together, if it doesn't work let me know.
## Post #5
- Username: Nemesiscv
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Mar 19, 2012 4:16 pm
- Post datetime: 2012-03-27T13:42:55+00:00
- Post Title: Resident Evil Operation Raccoon City WAV sounds

It does work perfectly ! Thank you so much !!! 

Thank you and sorry for asking it again !

I think someone should make a sticky topic about that !
## Post #6
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-03-28T06:02:52+00:00
- Post Title: Resident Evil Operation Raccoon City WAV sounds

Just to confirm - RavioliGameTools didn't give you the actual file names, did it?
If not, than I guess as of right now there's no known way to extract streamed.pck the "right way".
Sorry for offtop.
## Post #7
- Username: Nemesiscv
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Mar 19, 2012 4:16 pm
- Post datetime: 2012-03-28T08:25:07+00:00
- Post Title: Resident Evil Operation Raccoon City WAV sounds

Ravioli did gave me the right name. I fully extract nearly 50 000 sounds from the archives and found all the sounds from the Spec Ops DLC coming soon haha
## Post #8
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-03-28T09:10:05+00:00
- Post Title: Resident Evil Operation Raccoon City WAV sounds

That's good news. Can you specify what are the steps to get the file names?
I ran the RExtractor.exe and it didn't recognize pck format, so I did RExplorer.exe and it found a gazillion of WAVs.
## Post #9
- Username: Nemesiscv
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Mar 19, 2012 4:16 pm
- Post datetime: 2012-03-28T09:53:43+00:00
- Post Title: Resident Evil Operation Raccoon City WAV sounds

Actually the WAV does not have real names... Just numbers.
## Post #10
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-03-28T16:03:34+00:00
- Post Title: Resident Evil Operation Raccoon City WAV sounds

:facepalm:
## Post #11
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-03-28T16:57:17+00:00
- Post Title: Resident Evil Operation Raccoon City WAV sounds

How are people getting the .wav files because when i try drop my wav files in .bat it's not working.
## Post #12
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-03-28T17:50:47+00:00
- Post Title: Resident Evil Operation Raccoon City WAV sounds

> Reply from C00L12345
>
> How are people getting the .wav files because when i try drop my wav files in .bat it's not working.
1) Run Ravioli (RExplorer.exe) on streamed.pck, scan and extract WAV files. 
2) Put that .bat in the same folder with ww2ogg.exe, now drag-and-drop WAVs onto .bat will convert them to .Ogg,
Playable in foobar2000.

Worth a note, that ww2ogg.exe could not convert more than 20 (or something like that) WAVs at a time, at least for me.
## Post #13
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-03-28T19:53:32+00:00
- Post Title: Resident Evil Operation Raccoon City WAV sounds

> Reply from MiLØ
>
> C00L12345 wrote:How are people getting the .wav files because when i try drop my wav files in .bat it's not working.
1) Run Ravioli (RExplorer.exe) on streamed.pck, scan and extract WAV files. 
2) Put that .bat in the same folder with ww2ogg.exe, now drag-and-drop WAVs onto .bat will convert them to .Ogg,
Playable in foobar2000.

Worth a note, that ww2ogg.exe could not convert more than 20 (or something like that) WAVs at a time, at least for me.
Then what about those BNK containers? i used a quickbms to give me wav files but i can't get anything off them
## Post #14
- Username: Nemesiscv
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Mar 19, 2012 4:16 pm
- Post datetime: 2012-03-28T20:31:05+00:00
- Post Title: Resident Evil Operation Raccoon City WAV sounds

Ravioli will help you to extract the sounds from the PCK file.

If anyone want, I uploaded the music on my website :

```
http://downloads.ultimate-re.com/ost/Best%20of%20Resident%20Evil%20Operation%20Raccoon%20City%20Soundtrack%20Rip.rar
```
## Post #15
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2012-03-29T00:04:09+00:00
- Post Title: Resident Evil Operation Raccoon City WAV sounds

That's cool, but why are they all mono while the original data was stereo?

I'd suggest just using the original converted oggs to avoid introducing any more loss into the data.  If you do that, you should run revorb on the oggs, which you can find here: [http://www.hydrogenaudio.org/forums/lof ... 64328.html](http://www.hydrogenaudio.org/forums/lofiversion/index.php/t64328.html)
That way it will run in as many players as possible.
## Post #16
- Username: Nemesiscv
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Mar 19, 2012 4:16 pm
- Post datetime: 2012-03-29T09:32:13+00:00
- Post Title: Re: Resident Evil Operation Raccoon City WAV sounds

Oh I used Revorb. Then I work on the files on audacity to give them proper ends (Since some of them are loop) and that's when I noticed some of the files were in mono while some others are in stereo...

It took me a long time to extract the files and due to their size I had to remove them... I don't have the strengh to do it again !
## Post #17
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-03-29T11:45:57+00:00
- Post Title: Re: Resident Evil Operation Raccoon City WAV sounds

Edit. Nvm
## Post #18
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-04-07T00:04:34+00:00
- Post Title: Re: Resident Evil Operation Raccoon City WAV sounds

For the Xbox 360 version, use this script (func_getTYPE is here: [viewtopic.php?f=13&p=69577#p69577](http://forum.xentax.com/viewtopic.php?f=13&p=69577#p69577), save it in the same folder):

```
# Resident Evil: Operation Raccoon City (Xbox 360)
#
# (c) 2012-04-07 by AlphaTwentyThree of XeNTaX

include "func_getTYPE.bms"
idstring "AKPK"
endian big
set FOLDEROFF 0x58
goto 0x18
for i = 0 <= 7
	get DUMMY long
	get INDEX long
	savepos MYOFF
	goto FOLDEROFF
	for k = 0 < INDEX
		get FOLDERNAME string
	next k
	putArray 0 INDEX FOLDERNAME
	goto MYOFF
next i

goto 0xa4
get FILES long
for i = 1 <= FILES
	get NAME_CRC long
	string NAME_CRC p= "%08x" NAME_CRC
	get MULTIPLIER long
	get SIZE long
	get OFFSET long
	math OFFSET *= MULTIPLIER
	get TYPE long # folder number
	get FNAME basename
	string FNAME += "_0x"
	string FNAME += NAME_CRC
	getArray WNAME 0 TYPE
	string WNAME += "/"
	string WNAME += FNAME
	log MEMORY_FILE OFFSET SIZE
	callfunction getTYPE 1
	endian big
	string WNAME += EXT
	log WNAME 0 SIZE MEMORY_FILE
next i
```

It automatically distinguished between voice and sfx, as given in the archive. 

And for the wav2ogg conversion you can also use something like

```
for %%i in (*.ogg) do revorb "%%i"
```

Note that there are also XMA files in the Xbox 360 version.
## Post #19
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-04-07T13:11:36+00:00
- Post Title: Re: Resident Evil Operation Raccoon City WAV sounds

Thanks a lot for sharing the script, AlphaTwentyThree. But quickbms gives me an Error: 
```
invalid command "include" or arguments 1 at line 6
```

I did use it on X360 version of streamed.pck

Any advice on how to fix this would be appreciated.
## Post #20
- Username: Nemesiscv
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Mar 19, 2012 4:16 pm
- Post datetime: 2012-04-07T13:14:15+00:00
- Post Title: Re: Resident Evil Operation Raccoon City WAV sounds

Same here ^^
## Post #21
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-04-07T14:28:59+00:00
- Post Title: Re: Resident Evil Operation Raccoon City WAV sounds

You need my file identification script here: [viewtopic.php?f=13&p=69577#p69577](http://forum.xentax.com/viewtopic.php?f=13&p=69577#p69577) 
And the newest QuickBMS version - the command is fairly new.
## Post #22
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-04-07T15:42:25+00:00
- Post Title: Re: Resident Evil Operation Raccoon City WAV sounds

Ok this is great but I'm a little lost and apparently not doing something right. 

First of all - the newest version of QuickBMS is 0.5.10, correct? [http://aluigi.org/quickbms.htm](http://aluigi.org/quickbms.htm)

Next - is this the right scrip for func_getTYPE.bms? : 

```
...
log MEMORY_FILE OFFSET SIZE
callfunction getTYPE 1
if ZNAME != ""
   set NAME ZNAME
else
   get NAME basename
   string NAME += "_"
   string NAME += i
endif
string NAME += EXT
log NAME 0 SIZE MEMORY_FILE
...
```


So I attempted to run it with quickbms on streamed.pck and it says:

```
- requested script "func_getTYPE.bms" not found
```

That's where I'm stuck pretty much. Sorry for trouble, just trying to get this to work.
## Post #23
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-04-07T15:58:53+00:00
- Post Title: Re: Resident Evil Operation Raccoon City WAV sounds

have the get_type script in the same directory as the resident evil script and just run the resident evil script on the file like usual. it should detect the function script automatically.
## Post #24
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-04-07T16:28:05+00:00
- Post Title: Re: Resident Evil Operation Raccoon City WAV sounds

I ran ORC script on .pck file while both scripts are in quickbms folder, and it still says func_getTYPE.bms not found.
## Post #25
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-04-07T19:37:34+00:00
- Post Title: Re: Resident Evil Operation Raccoon City WAV sounds

Do you have the func_getTYPE.bms named as exactly as it is and have the latest quickbms?
## Post #26
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-04-08T00:17:25+00:00
- Post Title: Re: Resident Evil Operation Raccoon City WAV sounds

Here are the steps that I took, feel free to point out if something was done incorrectly.

1) QuickBMS (latest ver. from [here](http://aluigi.org/quickbms.htm)).

2) Save that ORC script by AlphaTwentyThree as ORC.txt and put it into quickbms folder.

3) Save func_getTYPE script as func_getTYPE.bms and put into quickbms folder.

4) Put streamed.pck (Xbox360 version) into quickbms folder.

5) Launch quickbms.exe > ORC.txt > streamed.pck > quickbms main folder.

And at the bottom of command line it says:

```
- requested script "func_getTYPE.bms" not found
```

I double checked if the scripts were copy/pasted correctly and yes everything matches.
## Post #27
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-04-08T02:45:26+00:00
- Post Title: Re: Resident Evil Operation Raccoon City WAV sounds

Okay change the extension to the orc from txt to bms,
## Post #28
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2012-05-04T22:47:02+00:00
- Post Title: Re: Resident Evil Operation Raccoon City WAV sounds

I have the same error:

> QuickBMS generic files extractor and reimporter 0.5.12
>
> by Luigi Auriemma
>
> e-mail: aluigi@autistici.org
>
> web:    aluigi.org
>
> 
>
> - GUI mode activated, remember that the tool works also from command-line
>
>   where are available various options like folder scanning, filters and so on
>
> 
>
> - select the BMS script or plugin to use
>
> - select the input archives/files to extract, type "" for whole folder and subfo
>
> lders
>
> - select the output folder where extracting the files
>
> - open input file D:\test\Streamed.pck
>
> - open script D:\test\orc.bms
>
> - requested script "func_getTYPE.bms" not found
>
> 
>
> Press RETURN to quit

This is the scripts i used:
orc.bms 

```
# Resident Evil: Operation Raccoon City (Xbox 360)
#
# (c) 2012-04-07 by AlphaTwentyThree of XeNTaX

include "func_getTYPE.bms"
idstring "AKPK"
endian big
set FOLDEROFF 0x58
goto 0x18
for i = 0 <= 7
   get DUMMY long
   get INDEX long
   savepos MYOFF
   goto FOLDEROFF
   for k = 0 < INDEX
      get FOLDERNAME string
   next k
   putArray 0 INDEX FOLDERNAME
   goto MYOFF
next i

goto 0xa4
get FILES long
for i = 1 <= FILES
   get NAME_CRC long
   string NAME_CRC p= "%08x" NAME_CRC
   get MULTIPLIER long
   get SIZE long
   get OFFSET long
   math OFFSET *= MULTIPLIER
   get TYPE long # folder number
   get FNAME basename
   string FNAME += "_0x"
   string FNAME += NAME_CRC
   getArray WNAME 0 TYPE
   string WNAME += "/"
   string WNAME += FNAME
   log MEMORY_FILE OFFSET SIZE
   callfunction getTYPE 1
   endian big
   string WNAME += EXT
   log WNAME 0 SIZE MEMORY_FILE
next i

```

func_getTYPE.bms 

```
...
log MEMORY_FILE OFFSET SIZE
callfunction getTYPE 1
if ZNAME != ""
   set NAME ZNAME
else
   get NAME basename
   string NAME += "_"
   string NAME += i
endif
string NAME += EXT
log NAME 0 SIZE MEMORY_FILE
...

```

Thanks!
## Post #29
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2012-05-11T02:26:23+00:00
- Post Title: Re: Resident Evil Operation Raccoon City WAV sounds

@MiLØ & Savage
In the func_getTYPE.bms script remove the first line and the dotted lines so it looks like this and try again.

```
callfunction getTYPE 1
if ZNAME != ""
   set NAME ZNAME
else
   get NAME basename
   string NAME += "_"
   string NAME += i
endif
string NAME += EXT
log NAME 0 SIZE MEMORY_FILE
```


I think the first line put QuickBMS into a loop which generated the error.
## Post #30
- Username: iceydamo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 08, 2012 12:37 am
- Post datetime: 2012-06-07T16:42:21+00:00
- Post Title: Re: Resident Evil Operation Raccoon City WAV sounds

i need help for the pc version of the game i managed to extract the wav files but the sript for ww2ogg didnt work for me i might of got the wrong files for ww2ogg could some one help me this is the script:
"cd "%~dp0"
:getfile
if "%~1"=="" goto end
ww2ogg.exe --pcb packed_codebooks_aoTuV_603.bin "%~1"
shift
goto getfile
:end"
