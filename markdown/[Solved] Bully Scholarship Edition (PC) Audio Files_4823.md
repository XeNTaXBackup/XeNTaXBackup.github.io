## Post #1
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2010-07-29T00:22:31+00:00
- Post Title: [Solved] Bully Scholarship Edition (PC) Audio Files

Bully Scholarship Edition (PC) has Bin files for all the audio, each Bin has a Lst file that when opened in notepad reads... 

```
EX_XmasTreeEmitter04.rsm
MS_CarnivalFunhouseAmbient.rsm
MS_Somower.rsm
MS_RomanceHigh.rsm
MS_MusicClass_Turkey.rsm
etc 
```


I was wondering if these rsm files can be extracted and converted to wav/mp3 etc?

EDIT: Solved, RENIKRILL's QuickBMS Scripts (To Extract the .Bin/.Sea) + ToWav (To convert the XSB + XWB into .wav)
[COWBELL_01.zip](https://xentaxbackup.github.io/file/4639_COWBELL_01.zip)
## Post #2
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2010-08-01T11:29:11+00:00
- Post Title: [Solved] Bully Scholarship Edition (PC) Audio Files

Why do you want to extract the sound?
Both, the retail version and the Steam version of the game come with the soundtrack on CD/320kbit MP3.
## Post #3
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2010-08-01T11:36:06+00:00
- Post Title: [Solved] Bully Scholarship Edition (PC) Audio Files

I have the UK Retail version of Bully SE that didnt include a soundtrack, I didnt realise the steam version had the soundtrack too.

but I would like to be able to extract speech and sound effects also.
## Post #4
- Username: RENIKRILL
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Feb 11, 2009 7:54 pm
- Post datetime: 2010-08-03T15:07:27+00:00
- Post Title: [Solved] Bully Scholarship Edition (PC) Audio Files

ReeceMix, just for future reference, it's prudent to provide an uploaded example of at least one, or part of the file((type(s)) of which you are making particular reference to within your forum-post, so that others can download & examine them for your benefit. This is explicitly due to the reality that not every member here is psychic.
However, in this particular case, I've looked into these files myself already.

This [appropriately-modified] quickbms script willl output seperated .xsb and .xwb files for each audiofile referenced within any given sound-archive, respectively:

```
open FDDE lst 1

idstring Hash
get FILES long

for i = 0 < FILES
	get FILEHASH long
	get OFFSET long
	get SIZE long
	getct NAME string 0x0D 1
	get TXT byte 1
	
	set XSBN string NAME
	string XSBN -= 4
	string XSBN += .xsb
	set XWBN string NAME
	string XWBN -= 4
	string XWBN += .xwb
	set XWBOFF long OFFSET
	math XWBOFF += 0x800
	set XWBSIZE long SIZE
	math XWBSIZE -= 0x800
	
	log XSBN OFFSET 0x800
	log XWBN XWBOFF XWBSIZE
next i

```

FYI: the "rsm" files are simply xbox-soundbanks (xwb) followed by the corresponding wavebank (xwb). And by the looks of what follows, the encoding is microsoft-adpcm.
The quickest way of decoding these files to wave is to use towav, which automates the procedure greatly. If you don't happen to have this app lying about your computer already, it's freely available from ctpax-x.ru

So once you've extracted the individual files from any of the given game audio-archives, just put towav.exe and its .bat into the folder along with your extracted .xwb files and use the batchfile to produce some familiar wave files.
Hope this helps you out mate.  

> Reply from Faqew
>
> Why do you want to extract the sound?
Both, the retail version and the Steam version of the game come with the soundtrack on CD/320kbit MP3.
Simply put: there's hours worth of original music within the game, which ultimately didn't get given a place within the soundtrack, so i guess any desire for more is understandable.
## Post #5
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2010-08-03T18:07:33+00:00
- Post Title: [Solved] Bully Scholarship Edition (PC) Audio Files

Thanks so much this is exactly what I was looking for 
x
## Post #6
- Username: RENIKRILL
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Feb 11, 2009 7:54 pm
- Post datetime: 2010-08-03T18:58:33+00:00
- Post Title: [Solved] Bully Scholarship Edition (PC) Audio Files

you're welcome m8
## Post #7
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2010-08-15T15:45:15+00:00
- Post Title: [Solved] Bully Scholarship Edition (PC) Audio Files

> Reply from RENIKRILL
>
> 
Faqew wrote:Why do you want to extract the sound?
Both, the retail version and the Steam version of the game come with the soundtrack on CD/320kbit MP3.
Simply put: there's hours worth of original music within the game, which ultimately didn't get given a place within the soundtrack, so i guess any desire for more is understandable.

Sorry, didn't know that. I thought every "big" track found its way onto the soundtrack CD.
## Post #8
- Username: nkttis
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Aug 14, 2010 4:34 pm
- Post datetime: 2010-08-16T13:37:17+00:00
- Post Title: [Solved] Bully Scholarship Edition (PC) Audio Files

> Reply from RENIKRILL
>
> ReeceMix, just for future reference, it's prudent to provide an uploaded example of at least one, or part of the file((type(s)) of which you are making particular reference to within your forum-post, so that others can download & examine them for your benefit. This is explicitly due to the reality that not every member here is psychic.
However, in this particular case, I've looked into these files myself already.

This [appropriately-modified] quickbms script willl output seperated .xsb and .xwb files for each audiofile referenced within any given sound-archive, respectively:
Code: Select allopen FDDE bin 0
open FDDE lst 1

idstring Hash
get FILES long

for i = 0 < FILES
	get FILEHASH long
	get OFFSET long
	get SIZE long
	getct NAME string 0x0D 1
	get TXT byte 1
	
	set XSBN string NAME
	string XSBN -= 4
	string XSBN += .xsb
	set XWBN string NAME
	string XWBN -= 4
	string XWBN += .xwb
	set XWBOFF long OFFSET
	math XWBOFF += 0x800
	set XWBSIZE long SIZE
	math XWBSIZE -= 0x800
	
	log XSBN OFFSET 0x800
	log XWBN XWBOFF XWBSIZE
next i

FYI: the "rsm" files are simply xbox-soundbanks (xwb) followed by the corresponding wavebank (xwb). And by the looks of what follows, the encoding is microsoft-adpcm.
The quickest way of decoding these files to wave is to use towav, which automates the procedure greatly. If you don't happen to have this app lying about your computer already, it's freely available from ctpax-x.ru

So once you've extracted the individual files from any of the given game audio-archives, just put towav.exe and its .bat into the folder along with your extracted .xwb files and use the batchfile to produce some familiar wave files.
Hope this helps you out mate.

I had the same dilema as ReeceMix, except with the Ps2 version of Bully. I used RENIKRILL's QuickBMS script on the SPEECH.bin file under the AUDIO folder ripped from the DVD and it worked like a charm. So I had thousands of .xsb and .xwb files now from the  .bin. I downloaded ToWav from the exact site given by RENIKRILL, put the .exe and .bat files in the same folder as all my xsb and xwb files and ran the program through the batch file. A black command prompt window opened. And nothing happened. I gave it more time and a window popped up reading "Exception EAccessViolation in module towav.exe at 00029ed8. Access violation at adress 00429ED8 in module 'towav.exe'. Read of adress 0000000A". I tried running towav through command prompt, checking the batch file, downloading towav through different sites, trying out all the different .xsb converters and extractors I could find but to no avail. What am I doing wrong? What should I do? Help would be GREATLY appreciated. And i've attached a zip of some of the files for reference. Thanks in advance.
[vag.zip](https://xentaxbackup.github.io/file/3333_vag.zip)
## Post #9
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2010-08-16T15:29:31+00:00
- Post Title: [Solved] Bully Scholarship Edition (PC) Audio Files

The XWB files contains VAG data without a proper VAG header. i slapped a VAG header ontop of them and the program converted them to WAV just fine.
the XSB files however doesnt really contain any data at all.
[hi.zip](https://xentaxbackup.github.io/file/3336_hi.zip)
## Post #10
- Username: nkttis
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Aug 14, 2010 4:34 pm
- Post datetime: 2010-08-17T09:00:22+00:00
- Post Title: [Solved] Bully Scholarship Edition (PC) Audio Files

> Reply from Strobe
>
> The XWB files contains VAG data without a proper VAG header. i slapped a VAG header ontop of them and the program converted them to WAV just fine.
the XSB files however doesnt really contain any data at all.

Thanks! But how do I go about creating .vag headers for the .xwb files?
## Post #11
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-08-17T12:08:11+00:00
- Post Title: [Solved] Bully Scholarship Edition (PC) Audio Files

Use GENH from HCS: [http://hcs64.com/mboard/forum.php?showthread=10460](http://hcs64.com/mboard/forum.php?showthread=10460) and play them with the vgmstream plugin for Winamp ([http://hcs64.com/vgmstream.html](http://hcs64.com/vgmstream.html))
Careful: All variables have to be entered as DECIMAL, so a hex interleave of 0x800 has to be entered as 2048!
For a faster processing you may want to open the headerless files with MFAudio (from Zophar's Domain) and play around with the interleave first. I expect all tracks to have the same interleave. For the sample rate: search for any clue about that - it's variable.
## Post #12
- Username: RENIKRILL
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Feb 11, 2009 7:54 pm
- Post datetime: 2010-08-17T12:13:36+00:00
- Post Title: [Solved] Bully Scholarship Edition (PC) Audio Files

Hey dude that script was slightly modified from it's original state and is only applicable to the archives used in the PC scholarship edition.
The PS2 audio-archives are identical, but they don't contain the xsb/xwb audio stuff, so you're gonna need the unmodified bms to get the untouched files.

```

open FDDE bin 0
open FDDE lst 1

idstring Hash
get FILES long

for i = 0 < FILES
	get FILEHASH long
	get OFFSET long
	get SIZE long
	getct NAME string 0x0D 1
	get TXT byte 1	# '\x0D'
	
	log NAME OFFSET SIZE
next i

```

Once extracted, you should have any number of *.rsm files instead of the xsb/xwb stuff.
IIRC vgmstream supports the headers in these files, so no additional work needs to be done.
Grab the latest build from here: [http://hcs64.com/files/vgmstream/](http://hcs64.com/files/vgmstream/)

Hope this helps.
## Post #13
- Username: nkttis
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Aug 14, 2010 4:34 pm
- Post datetime: 2010-08-18T09:09:15+00:00
- Post Title: [Solved] Bully Scholarship Edition (PC) Audio Files

AlphhaTwentyThree, the GENH file was not found when I tried the link to it... I didn't manage to find any other links.
RENIKRILL once again, your script worked perfectly and I ended up with a bunch of rsm files. So I went on to getting the latest vgmstream for winamp. Followed intructions in readme, put in_vgmstream into plugins under winamp, the other 3 required dll files together in the winamp.exe directory, but Winamp just could not play the files. The readme didn't list any support for rsm. rstm, yes but not rsm. Are they the same thing though? Running the test.exe that came with in_vegstream didn't recognise the rsm files either. And i'm stuck again.
## Post #14
- Username: RENIKRILL
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Feb 11, 2009 7:54 pm
- Post datetime: 2010-08-18T10:24:02+00:00
- Post Title: [Solved] Bully Scholarship Edition (PC) Audio Files

> Reply from nkttis
>
> AlphhaTwentyThree, the GENH file was not found when I tried the link to it... I didn't manage to find any other links.
RENIKRILL once again, your script worked perfectly and I ended up with a bunch of rsm files. So I went on to getting the latest vgmstream for winamp. Followed intructions in readme, put in_vgmstream into plugins under winamp, the other 3 required dll files together in the winamp.exe directory, but Winamp just could not play the files. The readme didn't list any support for rsm. rstm, yes but not rsm. Are they the same thing though? Running the test.exe that came with in_vegstream didn't recognise the rsm files either. And i'm stuck again.
I just went and found my copy of the ps2 game and tried to try out these files in vgmstream and, as you observed, the appropriate extension is rstm. So you'll have to rename all of your *.rsm files to *.rstm for them to be processed properly. Below is an alternative to the former script, which will give the appropriate extension to the output files:

```

open FDDE bin 0
open FDDE lst 1

idstring Hash
get FILES long

for i = 0 < FILES
   get FILEHASH long
   get OFFSET long
   get SIZE long
   getct NAME string 0x0D 1
   get TXT byte 1   # '\x0D'
   string NAME -= 4
   string NAME += .rstm
   
   log NAME OFFSET SIZE
next i
```
I'm quite sure all should work fine for you now
## Post #15
- Username: nkttis
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Aug 14, 2010 4:34 pm
- Post datetime: 2010-08-19T06:19:42+00:00
- Post Title: [Solved] Bully Scholarship Edition (PC) Audio Files

Yes, RENIKRILL it worked. Thanks so much once again for your help  I was able to play the rstm files on Winamp, though the sample rate was too high. So I converted the rstms with the test.exe that came with the vgmstream plugin and the tracks managed to play perfectly. (FINALLY!) Many thanks to ALphaTwentyThree and Strobe too for their input. All i've got to do now is to figure out how to convert all my rstm files at one go. I've got thousands here! Does anyone here know how I could do that?
[tests.zip](https://xentaxbackup.github.io/file/3351_tests.zip)
## Post #16
- Username: RENIKRILL
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Feb 11, 2009 7:54 pm
- Post datetime: 2010-08-19T09:19:01+00:00
- Post Title: Re: Bully Scholarship Edition (PC) RSM audio?

create a windows batch (.bat) file and within it, paste the following:

```
for %%i in (*.rstm) do test -o "%%i.wav" "%%i"
```
place this into the same folder as the rstm files, as well as the test.exe, then run the batch file
## Post #17
- Username: nkttis
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Aug 14, 2010 4:34 pm
- Post datetime: 2010-08-20T06:40:12+00:00
- Post Title: Re: Bully Scholarship Edition (PC) RSM audio?

Man, you seem to have the solution for everything i'm having trouble with  Anyway, I created the batch file and it works as it should, but by default, test.exe converts files with loops and a 10 second fade time. I could change these settings through command prompt with "-l 1.0" and "-f 0.0" but how do I incorporate that into the batch file? I tried multiple times and sadly failed
## Post #18
- Username: RENIKRILL
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Feb 11, 2009 7:54 pm
- Post datetime: 2010-08-20T09:00:08+00:00
- Post Title: Re: Bully Scholarship Edition (PC) RSM audio?

```
for %%i in (*.rstm) do test -o "%%i.wav" -l 1.0 -f 0.0 "%%i"
```
## Post #19
- Username: nkttis
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Aug 14, 2010 4:34 pm
- Post datetime: 2010-08-20T11:03:35+00:00
- Post Title: Re: Bully Scholarship Edition (PC) RSM audio?

> Reply from RENIKRILL
>
> Code: Select allfor %%i in (*.rstm) do test -o "%%i.wav" -l 1.0 -f 0.0 "%%i"
The funny thing is, I actually used that exact same command in the batch file that I tried creating myself. It didn't work. When I copied and pasted yours, it worked. Strange. All in all, you've been a great help
## Post #20
- Username: prysm
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jun 15, 2009 6:38 am
- Post datetime: 2010-10-27T21:11:56+00:00
- Post Title: Re: Bully Scholarship Edition (PC) RSM audio?

RENIKRILL, thanks a lot for both scripts!
## Post #21
- Username: RENIKRILL
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Feb 11, 2009 7:54 pm
- Post datetime: 2010-11-05T08:33:31+00:00
- Post Title: Re: Bully Scholarship Edition (PC) RSM audio?

> Reply from prysm
>
> RENIKRILL, thanks a lot for both scripts!
you're welcome buddy. keep it real ^^
## Post #22
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2011-08-16T18:27:32+00:00
- Post Title: Re: Bully Scholarship Edition (PC) RSM audio?

I've converted all the music audio but in the Xact folder there are bunch of .SEA files.

I thought that .sea was a pretty standard video game audio format but trying to google 'sea audio' is a nightmare anyone know of a converter?
## Post #23
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2011-08-18T13:47:27+00:00
- Post Title: Re: Bully Scholarship Edition (PC) RSM audio?

Attached COWBELL_01.SEA to the first post for analysis
## Post #24
- Username: RENIKRILL
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Feb 11, 2009 7:54 pm
- Post datetime: 2011-08-19T03:11:42+00:00
- Post Title: Re: Bully Scholarship Edition (PC) RSM audio?

> Reply from ReeceMix
>
> I've converted all the music audio but in the Xact folder there are bunch of .SEA files.

I thought that .sea was a pretty standard video game audio format but trying to google 'sea audio' is a nightmare anyone know of a converter?

Ok i had a short look at this file for you (thanks for the attachment, I don't currently have my copy of the game anywhere handy).
The file-extension is pretty much meaningless in most cases with game resource files, as the devs usually just give it something fitting, but not necessarily 'common'.
As is the case with these ".SEA" files, I'm very much certain they are specific to this game. My guess is that they literally stand for something along the lines of "scholarship edition audio", or similar.

To the business:
There's a lot of unessesary garbage at the beginning of these SEA sound-bank files. I've written a short & sweet quickbms script which works fine with the file you attached (and hopefully the rest of them, too). It will extract the corresponding 'xsb' & 'xwb' soundbanks/wavebanks (just like before). Also as before, simply run towav alongside the outputted files and it will produce the desired [playable] wave files.

```

get XSBOFF long
get XSBLEN long	# XWBOFF
get XWBLEN long	# EOF
get INITREFS long	

get XSBN basename
string XSBN += .xsb
get XWBN basename
string XWBN += .xwb

log XSBN XSBOFF XSBLEN
math XSBLEN += XSBOFF
log XWBN XSBLEN XWBLEN
```


I haven't spent practically any time on these forums (or others) lately as i've been bogged down with both uni & life in general, but in any case, let me know how things work out for you with these files and hopefully I can help you out further should any subsequent dramas arise.

 peace
## Post #25
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2011-08-19T18:06:28+00:00
- Post Title: Re: Bully Scholarship Edition (PC) RSM audio?

Worked perfectly for all of them 322.seas became 3652.wavs

Many thanks you are a King amongst Peasants   


(NOTE: alot of the audio files (EG: 4 BikeShopAmbREV_8va22k.wav) are named '8va' or '2eq8va' these sounds are speeded up , looks like they use the bully sound engine itself to slow them down and equalise them ingame)
