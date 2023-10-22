## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-12-03T00:54:26+00:00
- Post Title: Gray Matter .xwb/.xsb

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2010-12-04T20:00:09+00:00
- Post Title: Gray Matter .xwb/.xsb

> Reply from AlphaTwentyThree
>
> Hi there! The Gray Matter Demo has xsb/xwb pairs which are extractable with unxbw. But the extracted files are headerless and look suspiciously like WMA or MP3. 
Thanks in advance!
Hi AlphaTwentyThree,

yes, those files are xWMA. And you're correct: unxwb (which is apart from that the best .xwb extractor in my opinion) doesn't create a header for those, but my tool (xactxtract) does: it extracts .xwma files from .xwb Wavebanks. If you place Microsofts xWMAEncode.exe in the same directory, then my tool also converts the .xwma files into .wav. Just put xactxtract, xWMAEncode.exe and your MusicBank.xwb into the same directory and start xactxtract from the command line with:
xactxtract -x2 MusicBank.xwb

More info about xactxtract (including download links for xWMAEncode) [here](http://forum.xentax.com/viewtopic.php?f=17&t=4391&start=15). But don't use the xactxtract download links from there, because I just noticed, there's a problem currently:

Virus scanners report they found the "Worm/Autorun bqef SIGNATURE" on newer versions of xactxtract (v0.96, v0.97). I think/I'm quite sure it's a false alert, because I scanned my whole system and the only "infected" files were these two xactxtract executables. Therefor I think that compiling my Perl script (xactxtract is actually a Perl script) with PAR::Packer accidently produces the above signature. But if you want to be sure, better don't use versions 0.96 & 0.97 and use this old version (0.95) instead. I scanned this version (0.95) today (2010-dec-04) with several up-to-date scanners (including AntiVir, AVG, NOD32 and Kapersky) and they all found nothing:

==>[Use this link to get xactxtract v0.95](http://www.file-upload.net/download-3023539/xactxtract-v0.95.zip.html)
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-12-05T00:47:02+00:00
- Post Title: Gray Matter .xwb/.xsb

Hey, thanks for this. =) 
Just a little improvement suggestion: automatically get the names from the *.xsb (offset of the file names is at 0x2a).
## Post #4
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2010-12-05T16:59:48+00:00
- Post Title: Gray Matter .xwb/.xsb

> Reply from AlphaTwentyThree
>
> Hey, thanks for this. =) 
Just a little improvement suggestion: automatically get the names from the *.xsb (offset of the file names is at 0x2a).

Unfortunately, it's not that easy   The offset at 0x2a points to the so called CUE NAMES at the end of the .xsb. These are not the file names. The file names are not stored in the xsb files. Naming the (wav) files according to the cues does not work, because usually, the amount of cues differs from the amount of (wave) files.
For example in your MusicBank.xsb, there are 37 (cue) names, but in the MusicBank.xwb are only 35 files.
## Post #5
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-12-06T00:10:36+00:00
- Post Title: Gray Matter .xwb/.xsb

Huh, valid argument...  What are these names good for then? *wonders*
## Post #6
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2010-12-06T20:35:37+00:00
- Post Title: Gray Matter .xwb/.xsb

> Reply from AlphaTwentyThree
>
> Huh, valid argument...  What are these names good for then? *wonders*
Very good question   
The cue names are the "interface" to the game. The game developers don't have to worry much about how the sound is played. The game just passes the cue name (i.e. "main theme") to the XACT sub system. The XACT sub systems looks for "main theme" in the .xsb files (actually it's a little bit more complicated: .xsb files use hash tables) and gets the cue entry. The cue entry points to one or more "sound entries" and each sound can have one or more tracks. The tracks finally contain events (e.g. "play") and a reference to one of the files in the according .xwb file... an example for a track might be "play file with index 5 in MusicBank.xwb"). So basically, the .xsb files contain cue names, cues, sounds and tracks. A cue can be seen as a sort of play list, sounds contain things like volume and category. Unfortunately, the file format changes a little bit with each version, and there are further obstacles in the .xsb files like checksum (xactxtract has an option to recalculate the checksum, so it's possible to modify the values in a xsb file), several optional extra segments and so on   

As the xsb format is completely undocumented, it took me almost a month to figure all this out... and I still know just a part of it. I wrote xactxtract, because my aim is/was to insert new wav/wma files into the XSB/XWBs of Drakensang (a very good RPG). I gave up xsb a while ago, because I can't figure out the hash function. If I find the time (sometime next year), then I'll implement an option to replace files in XWBs (an improvement suggested by the Modders from Saints Row 2). But that's probably much more than you want to know   (sorry)
## Post #7
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-12-07T13:43:02+00:00
- Post Title: Gray Matter .xwb/.xsb

Cool, thanks for the clarification!  Nope, not too much info, I'm interested in this kind of information to understand certain facts about archives better. So this is indeed a pretty ugly case with the xsb containers - too bad. 
I thought about the hash values. If there are less names than tracks, that would mean that some tracks belong together ore merely go under the same name. Doesn't that mean that severyl hash values appear multiple times in this case? Isn't it possible to connect the hash values to the name offset so you could at least tell which files have the same name? Just wondering... I'm not that deep into this stuff so excuse me for sounding naive.
## Post #8
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2010-12-08T21:12:30+00:00
- Post Title: Gray Matter .xwb/.xsb

> Reply from AlphaTwentyThree
>
>  Isn't it possible to connect the hash values to the name offset so you could at least tell which files have the same name? Just wondering... I'm not that deep into this stuff so excuse me for sounding naive.
You don't sound naive at all - quite the contrary: you're asking exactly the right questions (not a big surprise, because looking at the number of your postings in this forum, you definitely have a lot of experience   ). And you're right: in your Gray Matter MusicBank, there have to be some tracks that go under the same cue name.

> Reply from AlphaTwentyThree
>
>  Doesn't that mean that severyl hash values appear multiple times in this case?
Well, there are as many hash table entries (37) as there are cue names and cue entries...but in fact, several hash values appear multiple times, because the hash function isn't very smart and maps cue names very often to the same hash value...there's an extra section for these hash entry collisions. 
But the hash values are not the problem - they only prevent me from inserting new cue/sound/track entries into the XSB, because I can't calculate the value for a given cue name (=the name I want to insert). But reading works - xactxtract knows, which cuename belongs to which hash entry and to which cue entry. So, to be precise, the "link chain" is (Game)->cue name->hash value/table->cue entry->sound entry (surprisingly, tracks don't have there own section, but are included in the sound entries)-> WaveBank name+index. The problem with the Gray Matter xwb are the cue entries. For "Standard" Cues (=cues, that contain exactly ONE sound) and "Standard" Sounds (=sounds, that contain exactly ONE track), my tool will give you for each cue an information line like this:

```
-----------------------------+--------+-------------------
ui_item_plate                 ->Std->     static_ui_53
```

For cases like this, I could (as you suggested) improve my tool so that it automatically renames the static_ui_53.wav (extracted from static_ui.xwb) to ui_item_plate.wav, because the assignment between cue name and wave file is distinct (<-sorry for my English, I hope you can guess what I mean).

Unfortunately, my tool only handles "Standard" cues, but not "extended" cues (=Cues containing more than one sound), because the format of "extended" cues and "extended" sounds is really weird. For example: "Standard" Sounds are 12 Byte long..but I've seen "Extended" Sound Entries with a length of 160 Byte 
(I placed the names in "", because I made up these names on my own - these are not official terms as there is no xsb documentation).

So the two problems with the Gray Matter MusicBank.xsb are
-it doesn't contain "standard" cues at all, all 37 cues are "extended" cues => I don't know which cue points to which sound entry (btw: the sound entries in MusciBank.xsb are all "standard"...so no problem with that)
-the xsb header format was slightly changed and my tool crashes, because it can't find the cue section (but that should be easy to fix)
## Post #9
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-12-11T16:05:52+00:00
- Post Title: Gray Matter .xwb/.xsb

Tried to follow that and had some problems understanding.  But I see that it's currently not possible to link the files to the names. Thanks for working on the format. =)
Grüße aus Weinheim an der Bergstraße
## Post #10
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2011-02-14T09:47:48+00:00
- Post Title: Gray Matter .xwb/.xsb

I tried extracting the MusicBank.xwb from the full game but I got this error

"WARNING: MusicBank.xwb hat Toolversion 771751936 und Formatversion 738197504.
xaXwb.pm unterstuetzt nur die Versionen 45 und 43
FEHLER: WAVEDATA Segment: Offset: 0  ,Laenge: 0 at xaXwb.pm line 208.

EDIT: According to UNXWB, the audio files are now XMA. I managed to convert them using XMAEncode.
## Post #11
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2011-02-14T18:48:52+00:00
- Post Title: Gray Matter .xwb/.xsb

> Reply from brendan19
>
> I tried extracting the MusicBank.xwb from the full game but I got this error

"WARNING: MusicBank.xwb hat Toolversion 771751936 und Formatversion 738197504.
xaXwb.pm unterstuetzt nur die Versionen 45 und 43
FEHLER: WAVEDATA Segment: Offset: 0  ,Laenge: 0 at xaXwb.pm line 208.

EDIT: According to UNXWB, the audio files are now XMA. I managed to convert them using XMAEncode.

Are you sure you're using the MusicBank.xwb from AlphaTwentyThrees posting? I just downloaded the wavebank once more: the files are (x)wma (not xma) and were extracted & converted without problems by xactxtract
## Post #12
- Username: Barnaby
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Dec 15, 2009 12:41 am
- Post datetime: 2011-02-14T20:59:02+00:00
- Post Title: Gray Matter .xwb/.xsb

Xbox 360 version > PC version ?
## Post #13
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2011-02-14T21:57:19+00:00
- Post Title: Gray Matter .xwb/.xsb

The musicbank.xwb Alpha posted was from the demo version. I downloaded the Xbox 360 ISO and ripped all of the XSB/XWB files from that.

Here's a screenshot from the cmd line:



Anyway, here's the first 10MB of the XWB file with the associated XSB file.

[http://www.flameupload.com/files/PPSY7R0P/MusicBank.rar](http://www.flameupload.com/files/PPSY7R0P/MusicBank.rar)
