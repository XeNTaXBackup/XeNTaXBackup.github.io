## Post #1
- Username: Zetta
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Mar 17, 2016 11:50 pm
- Post datetime: 2016-03-17T16:36:32+00:00
- Post Title: Assassin's Creed II and Revelations

Hello, could someone help me please?

I tried to extract sounds_sfx.pck and then convert into .ogg but after running .ogg file in the (VLC players, Media Player Classic HC or foobar2000) I can only hear creaking.

Assassin's Creed Revelations
There are 5 files from the sounds_sfx.pck

```
http://www.filedropper.com/02_9
```


Thank you very much for your help!
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-17T18:20:40+00:00
- Post Title: Assassin's Creed II and Revelations

I think you don't understand how wwise banks work.

From these 5 files, 4 files are proper 6-ch music files, all converted ok with OLD codebooks.

And the first file is probably the result of your attempt to extract the prefetch data from the sound bank. This contains about 300 prefetch blocks, combined in one file. Some of them are playable, because the sound is short, and was fully prefetched. Some are just the beginning of the big file that must be somewhere else.
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-17T18:34:25+00:00
- Post Title: Assassin's Creed II and Revelations

In short: you extracted these files wrong.
## Post #4
- Username: Zetta
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Mar 17, 2016 11:50 pm
- Post datetime: 2016-03-17T18:35:30+00:00
- Post Title: Assassin's Creed II and Revelations

I can upload the whole file sounds_sfx.pck because I have no clue what to do.

or 

if you would be so kind and wrote me what to do, step by step.

These 5 files are just a part of 19 971 files. What I extracted.

Thanks!
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-17T18:41:01+00:00
- Post Title: Assassin's Creed II and Revelations

What did you use to extract them?
## Post #6
- Username: Zetta
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Mar 17, 2016 11:50 pm
- Post datetime: 2016-03-17T18:45:51+00:00
- Post Title: Assassin's Creed II and Revelations

I have there 3 extractor, but I think I used this:

Wwise-Unpacker-1.0

```
http://www.filedropper.com/wwise-unpacker-10
```
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-17T19:17:19+00:00
- Post Title: Assassin's Creed II and Revelations

Just use another one of those 3.
## Post #8
- Username: Zetta
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Mar 17, 2016 11:50 pm
- Post datetime: 2016-03-17T19:30:50+00:00
- Post Title: Assassin's Creed II and Revelations

Assassin's_Creed_Rogue_Voice_unpacker_V1.00
Wwise_PCK_Decoding
Wwise-Unpacker-1.0
Wwise-Unpacker-master
Nova software extractor

There are all of the extractors

```
http://www.filedropper.com/extractor
```
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-17T20:26:02+00:00
- Post Title: Assassin's Creed II and Revelations

I have a feeling that none of these will be able to decode all sounds. You can have most of 17000 files working with Wwise_PCK_Decoding, but still will be missing some 1000's of them.

What's the total size of sounds_sfx.pck ?
## Post #10
- Username: Zetta
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Mar 17, 2016 11:50 pm
- Post datetime: 2016-03-17T20:44:34+00:00
- Post Title: Assassin's Creed II and Revelations

sounds_sfx.pck --> 1 111 710 231 k

After extraction have all files .wav --> 1 088 876 628 k

in sounds_sfx.pck there are also .txt files
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-18T17:18:21+00:00
- Post Title: Assassin's Creed II and Revelations

As I expected, the file has BNK files inside in addition to usual WAV files. And that's why all extractors fail with it.

I can't download the file to the end yet, it's slow and always fails in the middle.
## Post #12
- Username: Zetta
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Mar 17, 2016 11:50 pm
- Post datetime: 2016-03-18T17:44:51+00:00
- Post Title: Assassin's Creed II and Revelations

Should I the file upload somewhere else ? But I do not know where.
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-18T19:40:34+00:00
- Post Title: Assassin's Creed II and Revelations

Ok, I got 20961 files from this, and NO .txt files. Just wait while I'll sort this all out
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-18T20:00:24+00:00
- Post Title: Assassin's Creed II and Revelations

Drop the pck file into this tool, and it will extract all BNK & WAV files from it.

Then use BNKEXTR (you have it) on BNK files.

Then use ww2ogg and revorb on all WAV files you get after that. (You should have batch files for this somewhere inside your other extractors)

Then delete all WAV files, and you must have 20961 playable ogg files left.
[Assassin_creed2_pck.rar](https://xentaxbackup.github.io/file/10604_Assassin_creed2_pck.rar)
## Post #15
- Username: Zetta
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Mar 17, 2016 11:50 pm
- Post datetime: 2016-03-18T20:02:16+00:00
- Post Title: Assassin's Creed II and Revelations

There are .txt files and some other formats in sounds_sfx.pck
## Post #16
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-18T20:03:54+00:00
- Post Title: Re: Assassin's Creed II and Revelations

[quote="Zetta"]There are .txt files and some other formats in sounds_sfx.pck

No, this tool on your picture can't understand what's inside of the PCK, so these are all wrong
## Post #17
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-18T20:13:54+00:00
- Post Title: Re: Assassin's Creed II and Revelations

And of course all these files have names, but I'll need the full game to find them, and it will take much more time, so I'm not gonna do it.
## Post #18
- Username: Zetta
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Mar 17, 2016 11:50 pm
- Post datetime: 2016-03-18T20:19:42+00:00
- Post Title: Re: Assassin's Creed II and Revelations

I created a new folder and there i copy the: 
Assassin_creed2_pck.exe
sounds_sfx.pck

and then launched: Assassin_creed2_pck.exe and nothing.
## Post #19
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-18T20:22:48+00:00
- Post Title: Re: Assassin's Creed II and Revelations

Don't launch it, just drag and drop the PCK file on it
## Post #20
- Username: Zetta
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Mar 17, 2016 11:50 pm
- Post datetime: 2016-03-18T20:36:58+00:00
- Post Title: Re: Assassin's Creed II and Revelations

Hmm now ? I think i need more specific instruction please. 

It extracted 9258 files of .bnk and .wav 


Then use BNKEXTR (you have it) on BNK files. ????

Then use ww2ogg and revorb on all WAV files you get after that. (You should have batch files for this somewhere inside your other extractors)

Then delete all WAV files, and you must have 20961 playable ogg files left.
## Post #21
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-18T20:49:01+00:00
- Post Title: Re: Assassin's Creed II and Revelations

ok this is a batch file for you

```
for %%a in (*.wav) do ww2ogg "%%a"
for %%a in (*.ogg) do revorb "%%a"

```


must have ww2ogg, revorb, bnkextr, packed_codebooks.bin - in that folder where you have all the files

this will take a LOT OF TIME
## Post #22
- Username: Zetta
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Mar 17, 2016 11:50 pm
- Post datetime: 2016-03-18T21:14:49+00:00
- Post Title: Re: Assassin's Creed II and Revelations

You have my admiration, respect and many thanks!
## Post #23
- Username: oden666
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Sep 10, 2016 10:58 am
- Post datetime: 2016-09-10T03:23:21+00:00
- Post Title: Re: Assassin's Creed II and Revelations

> Reply from daemon1
>
> ok this is a batch file for you
Code: Select allfor %%a in (*.bnk) do bnkextr "%%a"
for %%a in (*.wav) do ww2ogg "%%a"
for %%a in (*.ogg) do revorb "%%a"


must have ww2ogg, revorb, bnkextr, packed_codebooks.bin - in that folder where you have all the files

this will take a LOT OF TIME

daemon1, you are my favorite person of all time.
## Post #24
- Username: TorpeJG52
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 13, 2017 5:56 pm
- Post datetime: 2017-09-13T10:06:39+00:00
- Post Title: Re: Assassin's Creed II and Revelations

> Reply from daemon1
>
> ok this is a batch file for you
Code: Select allfor %%a in (*.bnk) do bnkextr "%%a"
for %%a in (*.wav) do ww2ogg "%%a"
for %%a in (*.ogg) do revorb "%%a"


must have ww2ogg, revorb, bnkextr, packed_codebooks.bin - in that folder where you have all the files

this will take a LOT OF TIME

Thank you very much!!!!!
## Post #25
- Username: ZuluViking
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jul 09, 2018 2:31 pm
- Post datetime: 2018-07-09T12:06:36+00:00
- Post Title: Re: Assassin's Creed II and Revelations

> Reply from daemon1
>
> ok this is a batch file for you
Code: Select allfor %%a in (*.bnk) do bnkextr "%%a"
for %%a in (*.wav) do ww2ogg "%%a"
for %%a in (*.ogg) do revorb "%%a"


must have ww2ogg, revorb, bnkextr, packed_codebooks.bin - in that folder where you have all the files

this will take a LOT OF TIME

Ok, very new reply to a pretty old post, so I'm just hoping you see this. Something obviously worked here for a lot of people, but I have no idea what that was/is. I have the exact same problem as OP was having where I'm trying to extract the voice files from ACII and AC: Brotherhood and I can't find anything that works. I downloaded your tool and all the other necessary files and put them all in the same folder together with the pck-file I'm trying to unpack. Then I dragged the pck-file onto your tool, but the command prompt that pops up stays black and nothing happens before it eventually disappears. So what am I doing wrong, and what is the batch file for? I'm assuming I have to make a text file, copy & paste the code you wrote there, and save the text file to .bat? Even if that's correct, what then? I tried double clicking it and yet again nothing happens. I'm a complete noob when it comes to this, so I'm hoping someone can explain it to me like I'm 10 years old.
## Post #26
- Username: MrZorro
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 01, 2019 8:27 pm
- Post datetime: 2019-07-01T12:28:34+00:00
- Post Title: Re: Assassin's Creed II and Revelations

i Have the same problem, which tool do i have tu use xd ?
## Post #27
- Username: The7thOne
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 20, 2020 11:46 pm
- Post datetime: 2020-04-20T16:13:46+00:00
- Post Title: Re: Assassin's Creed II and Revelations

> Reply from ZuluViking ↑Mon Jul 09, 2018 8:06 pm at Mon Jul 09, 2018 8:06 pm
>
> 

Ok, very new reply to a pretty old post, so I'm just hoping you see this. Something obviously worked here for a lot of people, but I have no idea what that was/is. I have the exact same problem as OP was having where I'm trying to extract the voice files from ACII and AC: Brotherhood and I can't find anything that works. I downloaded your tool and all the other necessary files and put them all in the same folder together with the pck-file I'm trying to unpack. Then I dragged the pck-file onto your tool, but the command prompt that pops up stays black and nothing happens before it eventually disappears. So what am I doing wrong, and what is the batch file for? I'm assuming I have to make a text file, copy & paste the code you wrote there, and save the text file to .bat? Even if that's correct, what then? I tried double clicking it and yet again nothing happens. I'm a complete noob when it comes to this, so I'm hoping someone can explain it to me like I'm 10 years old.

I know this is an old reply to an even older thread, but I just wanted to explain this more clearly in case anyone reading this thread in the future is having problems.

You need to copy the code as text, paste into Notepad, and then save that text file as a batch file. You need to change the "Save As..." from "Text file" to "All files". Make sure the filename ends in ".bat". Ensure all of the WAV files, ww2ogg, and the batch file itself are all in the same folder. Then simply double-click (run) the batch file. It should automatically output the files for you. The terminal window will just be black; this is normal. Don't exit out of it, it will do so automatically once it's done converting everything. Once it's done, just delete the .WAVs, and you'll be left with playable .OGG tracks. I then added them to a foobar2000 playlist, and they're completely playable. This is the exact method I've just used for AC2's audio files, and it worked perfectly. So something must be wrong on your end.
