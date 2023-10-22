## Post #1
- Username: montcer9012
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Jul 14, 2012 2:14 pm
- Post datetime: 2013-11-05T07:00:23+00:00
- Post Title: QBMS script for BatmanAA .SoundNodeWav and .upk?

Hi.

I am trying to unpack/repack localization UPK files from Batman Arkham Asylum to replace the subtitles, but i have 2 problems:
1. I have only found a working unpacker, not a reckpaker of UPK files.
2. Subtitles are embedded to sound files, which are .SoundNodeWav. Need to unpack those audio files to get the subtitles files, make the mods and then repack it.

To unpack the UPK files, i am using Gildor's Unreal Engine extractor. The tool i am using to repack the UPK [can be found here](http://www.gildor.org/smf/index.php/topic,267.msg13432.html#msg13432). The problem is that after repack the UPK, the game crash; maybe the tool need to be updated for Batman; i am trying to contact who created the tool hoping he have a work around to repack Batman's UPK files.

On the mean while, need to detach the subtitles from .SoundNodeWav files, so i was wondering if a QBMS script can be worked for those .SoundNodeWav and .UPK files.

Here are 3 example files of first chapter. Run the "extract_all.cmd" to get the files extracted (Notice that after the extraction, .upk files will be renamed like .bak): [http://www.mediafire.com/?bwyabsw6u2cv7zp](http://www.mediafire.com/?bwyabsw6u2cv7zp)

Please, someone can help me out here?
## Post #2
- Username: GimmyBreaker
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Jul 06, 2012 12:24 am
- Post datetime: 2013-11-13T12:45:02+00:00
- Post Title: QBMS script for BatmanAA .SoundNodeWav and .upk?

QBMS script?
You can easily write Python script for SoundNodeWave.

Example export script in attachment, correct tabs in Python GUI if script will not work.
Should work.

There are other tools to extract/repack upk files.
[bataa.rar](https://xentaxbackup.github.io/file/6771_bataa.rar)
## Post #3
- Username: montcer9012
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Jul 14, 2012 2:14 pm
- Post datetime: 2013-11-13T13:03:33+00:00
- Post Title: QBMS script for BatmanAA .SoundNodeWav and .upk?

Thanks man.

Sadly, I am not coder so I don't know how to make a script. I will appreciatte if you get online later to seek my test result with the file you attachment.

I can't check it now, but surely will do later.
## Post #4
- Username: GimmyBreaker
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Jul 06, 2012 12:24 am
- Post datetime: 2013-11-13T13:15:58+00:00
- Post Title: QBMS script for BatmanAA .SoundNodeWav and .upk?

Sure, let me know.

Ah, and other thing, before I forget. Check which string game is reading.
And do some research, if all strings begin from 368 offset.
You can use HxD for this.
## Post #5
- Username: montcer9012
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Jul 14, 2012 2:14 pm
- Post datetime: 2013-11-13T23:49:16+00:00
- Post Title: QBMS script for BatmanAA .SoundNodeWav and .upk?

Ok, i get very lost here hahahaha.

First, i don't know how to get the script to work. It keeps saying:

```
  File "C:\Users\CAMG\Downloads\bataa\bataa.py", line 14
    print "Working on:Max_A1_CH1_BM_G2_02.SoundNodeWave", i
                                                       ^
SyntaxError: invalid syntax

C:\Users\CAMG\Downloads\bataa>

```


Those are the modifications i made to the script; for sure i am doing something wrong:

```
nazwa = []
txt = [] 
point = [] 

for i in files:
    with open(i, "rb") as in_file: #odczyt plików SoundNodeWave
        print "Working on:Max_A1_CH1_BM_G2_02.SoundNodeWave", i
```


About the thing you ask me... The game is reading the X language string that is set, so... i don't get the question. I guess you want me to give you a hex number or something, not sure... But i do notice on the that the script work with some 3XX numbers; i assume those numbers are the offsets on the file where the strings start, right?

Also, have to google for what is "offset". Now i know what it is, still can't answer because offsets change if i change the vies on the hex editor, but it seems that no, strings does not always start at that "off set". That's how looks like BAA .soundnode files:

[](http://www.subirimagenes.com/otros-captura-8695832.html)
## Post #6
- Username: GimmyBreaker
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Jul 06, 2012 12:24 am
- Post datetime: 2013-11-14T02:23:31+00:00
- Post Title: QBMS script for BatmanAA .SoundNodeWav and .upk?

Yes, script work on offset 3xx. It's always depends on game.
You have Python 3.x, delete all line with print or change to print("Working on: ",i).
I'm working on 2.7.x

Nevermind, I will do this for you only because I didn't have enough time to finish my importer and exporter for Grimm.
Script will be public.
But It's first and last time, I'm only do such things for free for Polish fan translations community.
You are lucky
## Post #7
- Username: montcer9012
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Jul 14, 2012 2:14 pm
- Post datetime: 2013-11-14T02:47:19+00:00
- Post Title: QBMS script for BatmanAA .SoundNodeWav and .upk?

Not for free??? Mmm well at least could you point me on the right direction? I live on a communism country (Venezuela), were foreign currencies are banned, so i can't pay to you... No with a working currency. If you accept VEF then let me know hahahaha.

The game already have the translation i want (Spanish), but i want to force it to play english voices with spanish subs (Can't be done normally, because voices and subtitles are embedded together). That's why i want to unpack .soundnodewav file: to rewrite the English subs with the spanish ones, then repack the .soundnodewav, and finally repack the .upk.

By the way, Python looks kinda a batch file; at least i could understand it a little bit. I do erase the line, and now it sais this:

```
  File "C:\Users\CAMG\Downloads\bataa\bataa.py", line 7
    files = sorted(glob("C:\Users\CAMG\Downloads\bataa"))
                       ^
SyntaxError: (unicode error) 'unicodeescape' codec can't decode bytes in positio
n 2-3: truncated \UXXXXXXXX escape

```
## Post #8
- Username: GimmyBreaker
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Jul 06, 2012 12:24 am
- Post datetime: 2013-11-14T10:40:24+00:00
- Post Title: QBMS script for BatmanAA .SoundNodeWav and .upk?

No, I said, that I will do this for you, for free only this time and script will be public. Wait few days.
Unreal Engine is my cup of tea.
I don't do research and tools for free for other countries only because I takes a lot of time   
I hate Python 3.x version, they've change so much...

UPK Unpack/Repack in Attachment.
[UPK.rar](https://xentaxbackup.github.io/file/6773_UPK.rar)
## Post #9
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-11-14T10:59:51+00:00
- Post Title: QBMS script for BatmanAA .SoundNodeWav and .upk?

> Reply from GimmyBreaker
>
> No, I said, that I will do this for you, for free only this time and script will be public. Wait few days.
Unreal Engine is my cup of tea.
I don't do research and tools for free for other countries only because I takes a lot of time   
I hate Python 3.x version, they've change so much...

UPK Packer/Repacker in Attachment.

I was just curious and grabb this and test it, what this exactly does mate ?? It does not do anything just create folder and put some non usable log files in it.... Confused... Really?? Your Tools does not work correctly.... What is the compression use for PC ? On X360 is LZX of course??
## Post #10
- Username: GimmyBreaker
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Jul 06, 2012 12:24 am
- Post datetime: 2013-11-14T11:13:24+00:00
- Post Title: QBMS script for BatmanAA .SoundNodeWav and .upk?

> Reply from michalss
>
> 
I was just curious and grabb this and test it, what this exactly does mate ?? It does not do anything just create folder and put some non usable log files in it.... Confused... Really?? Your Tools does not work correctly.... What is the compression use for PC ? On X360 is LZX of course??

It's unpacker and reapacker for .upk files for montcer9012, because when he repack .upk game crashes, he wanted QBMS script for upk files, I said there are other tools to do this, now in my attachment. It's only because Gildor Unpacker and 0dd14lab Unpacker are different.
There are not my tools, there are from 0dd14lab, no longer available from their website. Only Decompressor from gildor can be useful to decompress .upk package.

We are talking with montcer9012 about importer and exporter for SoundNodeWave files.
## Post #11
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-11-14T12:39:28+00:00
- Post Title: QBMS script for BatmanAA .SoundNodeWav and .upk?

> Reply from GimmyBreaker
>
> michalss wrote:
I was just curious and grabb this and test it, what this exactly does mate ?? It does not do anything just create folder and put some non usable log files in it.... Confused... Really?? Your Tools does not work correctly.... What is the compression use for PC ? On X360 is LZX of course??

It's unpacker and reapacker for .upk files for montcer9012, because when he repack .upk game crashes, he wanted QBMS script for upk files, I said there are other tools to do this, now in my attachment. It's only because Glidor Unpacker and 0dd14lab Unpacker are different.
There are not my tools, there are from 0dd14lab, no longer available from their website. Only Decompressor from glidor can be useful to decompress .upk package.

We are talking with montcer9012 about importer and exporter for SoundNodeWave files.

Well both are useless for localization i'm afraid . And that one you posted does not work at all
## Post #12
- Username: montcer9012
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Jul 14, 2012 2:14 pm
- Post datetime: 2013-11-14T13:39:52+00:00
- Post Title: QBMS script for BatmanAA .SoundNodeWav and .upk?

Cool man! Repacked UPK files does work now! Many tanks for the files.

At this point, i only need the .soundNodeWav unpacker/repacker to replace the subtitles. So, i have to ask, the tool you are developing will be avaible soon, and is intended to unpack/repack .soundNodeWav files? I am working with BAA for now, later will start with BAO but i hope same tools work for both games.

Remember i upload 3 files from the first chapter, in case you want to try your tool with BAA files. Download link:
[http://www.mediafire.com/download/bwyab ... 01_BAA.zip](http://www.mediafire.com/download/bwyabsw6u2cv7zp/Chapter_01_BAA.zip)

> Reply from michalss
>
> 
Well both are useless for localization i'm afraid . And that one you posted does not work at all
What do you mean with "both"? If you mean unpacker/repacker for upk, it does work for BAA. 

If i do remember well, you finished your translation of BAO, and i ask the tools you used but you haven't answer to me.

EDIT: The tools does not work for BAO. Even if i extract .UPK files with Gildor's tool, then i can't repack it because Gildor tool does not create .UPKpkginfo file. But for now, i want to work first with BAA, then look forward for BAO.
## Post #13
- Username: GimmyBreaker
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Jul 06, 2012 12:24 am
- Post datetime: 2013-11-14T14:52:37+00:00
- Post Title: QBMS script for BatmanAA .SoundNodeWav and .upk?

Gildor unpacker doesn't work with UPK Repacker, because, It was created only to unpack, not for repack. 
I will look around BO files. But as I said before, If UPK Unpack can't decompress .upk files, then you must use Gildor Decompressor and use UPK Unpack on that decompressed file 

The problem is, that there is no universal tool for Unreal Engine and never be. There are so many games running on that engine, and It everyone always end in Hex Editor, to chceck differences.

Yes, my tool for exporting and importing strings for SoundeNodeWave files will be avalibe soon, as open code, Python script, will work with Batman AA.
I have this game from HumbleBundle, so I don't need files from you.

> Reply from michalss
>
> Well both are useless for localization i'm afraid . And that one you posted does not work at all

Maybe you don't know how to use them?
## Post #14
- Username: montcer9012
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Jul 14, 2012 2:14 pm
- Post datetime: 2013-11-14T15:02:19+00:00
- Post Title: QBMS script for BatmanAA .SoundNodeWav and .upk?

You have both Batman A Asylum and B A Origins? Let me know if you need anything. Is the most i can do since i can't pay for your work.
## Post #15
- Username: GimmyBreaker
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Jul 06, 2012 12:24 am
- Post datetime: 2013-11-14T15:05:44+00:00
- Post Title: QBMS script for BatmanAA .SoundNodeWav and .upk?

Yes, I have all new Batmans.
As I said for Batman Origins, use Gildor Decompressor and then use UPK Unpack from me, should work If they don't change lot in those files.
If not, well, we will see
## Post #16
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-11-14T15:05:55+00:00
- Post Title: Re: QBMS script for BatmanAA .SoundNodeWav and .upk?

> Reply from GimmyBreaker
>
> 

Maybe you don't know how to use them?

Or might that tool is crap?? My point is why to waste time on something what does not work ? This is not rude just pointing the fact mate...
## Post #17
- Username: GimmyBreaker
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Jul 06, 2012 12:24 am
- Post datetime: 2013-11-14T15:11:51+00:00
- Post Title: Re: QBMS script for BatmanAA .SoundNodeWav and .upk?

I don't even care about that, my dear friend @michalss.

I've worked on Mass Effect Pinnacle Station and and working on Antichamber translation.
I've prepared translated .upk files for Borderlands DLC translation, so, I know what I'm talking.
I've even created exporter and importer for The Wolf Among Us, before Brazilian team.

I can only tell, don't be rude if you want to learn something.
I've learned a lot from my friends from Polish community.
## Post #18
- Username: montcer9012
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Jul 14, 2012 2:14 pm
- Post datetime: 2013-11-14T15:25:44+00:00
- Post Title: Re: QBMS script for BatmanAA .SoundNodeWav and .upk?

Yeah, i try that with no luck.

It seems that those upk are a new way packed. Remember that Gildor updated his tools recently because it does not work with BAO. Latest version of decompressor/unpacker are from october, if i remember well.

Anyway, i have unpacked sveral files from BAO and haven't found a single .soundnodewav file... It seems they change the whole system on that game. Also, strings are contained in a single file that contains ALL strings, without the sound that belongs to that string. Maybe i am wrong, because i still doesn't found first chapter files, but well, that's all i know for now. I guess BAO will be much difficult to change voices/subtitles...

EDIT: michalls you are becoming annoying. If you are not going to help, don't see the point to keep making comments.
## Post #19
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-11-14T17:01:31+00:00
- Post Title: Re: QBMS script for BatmanAA .SoundNodeWav and .upk?

Well what are you actually trying to archive here ? Replace audio string or what? if you want to have EN voice and other lang subtitles, it is simple to do, you have to repack texts only it means extract texts from UPK change them as you like and import back, no need to messup with sounds!
## Post #20
- Username: montcer9012
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Jul 14, 2012 2:14 pm
- Post datetime: 2013-11-14T22:44:57+00:00
- Post Title: Re: QBMS script for BatmanAA .SoundNodeWav and .upk?

> Reply from michalss
>
> ... if you want to have EN voice and other lang subtitles, it is simple to do, you have to repack texts only it means extract texts from UPK change them as you like and import back, no need to messup with sounds!

Exactly, that's what i am trying to do! But how do you repack the upk file? The one that the GimmyBreaker attached works like a charm for BAA, sadly, not for BAO. I only have found another UPK repacker but intended to Alice Madness, so it obviously won't work to BAO UPK files.

Also, i haven't research so much BAO files, so i don't know which files are the ones that contains the strings. In BAA for example, are those that ends like "LOC_INT.upk".

I have think it twice, and are convinced that is better to modify the game engine to always use english voices. I guess it can be done just with an Hex Editor, but i don't know either which file is the source of the engine, neither what should i modify. A guy do that with latest Mortal Kombat and i compare the original file with the modificated one, and the whole file is diferent, and the size is even bigger! So i am more lost. I post about that here:
[http://www.gildor.org/smf/index.php/topic,2017.0.html](http://www.gildor.org/smf/index.php/topic,2017.0.html)
## Post #21
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-11-15T06:59:24+00:00
- Post Title: Re: QBMS script for BatmanAA .SoundNodeWav and .upk?

> Reply from montcer9012
>
> michalss wrote:... if you want to have EN voice and other lang subtitles, it is simple to do, you have to repack texts only it means extract texts from UPK change them as you like and import back, no need to messup with sounds!

Exactly, that's what i am trying to do! But how do you repack the upk file? The one that the GimmyBreaker attached works like a charm for BAA, sadly, not for BAO. I only have found another UPK repacker but intended to Alice Madness, so it obviously won't work to BAO UPK files.

Also, i haven't research so much BAO files, so i don't know which files are the ones that contains the strings. In BAA for example, are those that ends like "LOC_INT.upk".

I have think it twice, and are convinced that is better to modify the game engine to always use english voices. I guess it can be done just with an Hex Editor, but i don't know either which file is the source of the engine, neither what should i modify. A guy do that with latest Mortal Kombat and i compare the original file with the modificated one, and the whole file is diferent, and the size is even bigger! So i am more lost. I post about that here:
http://www.gildor.org/smf/index.php/topic,2017.0.html

I dont know how to archive that EN fwould be default no matter what...  I can only repack texts, but this would be very complicated for you, coz they are mixed ASCII, Unicode together and each language is not same level all the time in every file, this game was nightmare to do, so i dont know how to really help you. Even if i would give you text repacker, it would be same amount of work as normal localization, coz you would need to reposition all texts...
## Post #22
- Username: GimmyBreaker
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Jul 06, 2012 12:24 am
- Post datetime: 2013-11-15T11:26:19+00:00
- Post Title: Re: QBMS script for BatmanAA .SoundNodeWav and .upk?

What? Reposition all text? First, .SoundNodeWave files in Batman AA contains strings only in one language, second, SoundNodeWave contains sound.

And why the hell montcer9012 will need to reposite all text? He will export strings in language he want, then import them to SoundNodeWave files he want. Where is reposition?
## Post #23
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-11-15T11:57:42+00:00
- Post Title: Re: QBMS script for BatmanAA .SoundNodeWav and .upk?

> Reply from GimmyBreaker
>
> What? Reposition all text? First, .SoundNodeWave files in Batman AA contains strings only in one language, second, SoundNodeWave contains sound.

And why the hell montcer9012 will need to reposite all text? He will export strings in language he want, then import them to SoundNodeWave files he want. Where is reposition?

First i think you dont know anything about it, so again, since in this is kind of new UPK files from UE3, there is not really id of the text, at least i did not found it.. Here is example of file i have exported from UPK. Also warning not every UPK contains the text. File Types SF does not contains any text, at least i did not found any. UE3 engine for string using some kind magic number to found out text string in UPK.

```
https://dl.dropboxusercontent.com/u/38234344/Prison_C1_Ch1.upk.txt
```


If you look at the file there is 13 strings for each section, where first 2 are Sound String and Name of the block/character talking - again not always the same. So you would need to switch text between each other to make this work for every single file and every single text block. It is possible but it will take a huge amount of time.. Previous versions of Batman had a different way to store text and also there was possible to identify id of the language, but this time i could not determinate it  SO i had to export all texts from UPK. I made importer where you dont care if string is Unicode or ASCII importer take care of it on the base of the mark [/U]  By this method im capable of do anything about the texts.


All this problems and differences in Engine is cause by custom modification each Game Studio and also version of Engine itself!

1 more thing, for example Video files is different as well, string are store in UTF8 and there you can found ID of the language, which is great...
## Post #24
- Username: montcer9012
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Jul 14, 2012 2:14 pm
- Post datetime: 2013-11-15T13:01:15+00:00
- Post Title: Re: QBMS script for BatmanAA .SoundNodeWav and .upk?

> Reply from GimmyBreaker
>
> What? Reposition all text? First, .SoundNodeWave files in Batman AA contains strings only in one language, second, SoundNodeWave contains sound.
No, we were talking about BAO, not BAA.

I agree that will be a nightmare keep only english  voices on BAO because of the new file system, and that's why i told up that will be better to mod the game engine to force the game to always use english voices, if possible.
## Post #25
- Username: montcer9012
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Jul 14, 2012 2:14 pm
- Post datetime: 2013-11-16T20:17:25+00:00
- Post Title: Re: QBMS script for BatmanAA .SoundNodeWav and .upk?

> Reply from michalss
>
> 
All this problems and differences in Engine is cause by custom modification each Game Studio and also version of Engine itself!
michalss, what do you recommend me to keep english voices with spanish subtitles on BAO?

For BAA i only need to unpack the .SoundNodeWav files, replace the subtitles and then repack it.
## Post #26
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-11-16T20:54:22+00:00
- Post Title: Re: QBMS script for BatmanAA .SoundNodeWav and .upk?

> Reply from montcer9012
>
> michalss wrote:
All this problems and differences in Engine is cause by custom modification each Game Studio and also version of Engine itself!

michalss, what do you recommend me to keep english voices with spanish subtitles on BAO?

For BAA i only need to unpack the .SoundNodeWav files, replace the subtitles and then repack it.

Only Way i know is to swich langs and pack back
## Post #27
- Username: montcer9012
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Jul 14, 2012 2:14 pm
- Post datetime: 2013-11-16T23:26:55+00:00
- Post Title: Re: QBMS script for BatmanAA .SoundNodeWav and .upk?

> Reply from michalss
>
> 
Only Way i know is to swich langs and pack back

How to do that?
## Post #28
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2013-12-08T18:12:22+00:00
- Post Title: Re: QBMS script for BatmanAA .SoundNodeWav and .upk?

Anyone know where are the strings in Batman: Arkham Origins?
## Post #29
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2015-01-09T08:30:24+00:00
- Post Title: Re: QBMS script for BatmanAA .SoundNodeWav and .upk?

Hi all!Could you help me how to generate .UPKpkginfo? I created a new font with new size (smaller original file), when I repack UPK without generate .UPKpkginfo, game crash and have a warning: 

Sorry! I mean is how to repack with new font!

Original file have size: 198101
New file have size: 181857

Example file: Startup_INT.rar
Origin UPK file: [https://www.dropbox.com/s/axr2cci5iafwx ... T.upk?dl=0](https://www.dropbox.com/s/axr2cci5iafwx8b/Startup_INT.upk?dl=0)

Thanks!
