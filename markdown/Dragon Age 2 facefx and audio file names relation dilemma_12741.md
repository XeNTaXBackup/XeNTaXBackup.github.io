## Post #1
- Username: 123185321f
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Apr 28, 2012 8:53 am
- Post datetime: 2015-04-04T05:30:29+00:00
- Post Title: Dragon Age 2 facefx and audio file names relation dilemma

hi all, in the past few days I worked on finding a way to generate faceFX for Dragon Age 2, and I've been pretty successful so far, at least so it seems to me at the moment .

anyways, I can't seem to figure out the pattern between face FX naming convention, which follows the same one used in Dragon Age Origins, i.e. 6114295_m.fxe, which unexpectedly requires 1003006487.ogg sound file, for the male voice. I figured out this specific example manually, that is I listened to the sound file first, then searched for its equivalent text in the talk table, found the string ID, and looked for the stringID_gender.FXE .

I looked for 1003006487 as text, as hexadecimal and as hash, and I couldn't find anything to connect 1003006487.ogg with 6114295_m.fxe. I looked into all the files, exported or not exported, original ERF or .cnv/.cl/etc.

I don't know how exactly the game knows which ogg sound files to play based on the stringID of the text in the talk table

Maybe I missed something and I can use an extra pair of eyes, it's pretty late here in Bay Area

Thanks!

PS: attached are the original FXA human male from Dragon Age 2,along with the custom mapping I re-created (FXS) and a facefx script, in case you want to play with it as well. The original Dragon Age 2 FXE/FXA files are created with the same facefx studio 1.7.1 which can be found in the Dragon Age Origins toolset, although the RoboBrad used in DA2 is much more complex (~125 presets) compared to DA:O(~25 presets)
[da2_facefx.ZIP](https://xentaxbackup.github.io/file/8938_da2_facefx.ZIP)
## Post #2
- Username: 123185321f
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Apr 28, 2012 8:53 am
- Post datetime: 2015-05-19T18:38:34+00:00
- Post Title: Dragon Age 2 facefx and audio file names relation dilemma

meanwhile I continued working on a Dragon Age 2 Toolset, I have an alpha version functional with one major feature: conversation viewer



Uses Rick's libraries, Mephales' ErfExtractor, Hikami dialog converter, WayneBaby MVVM Sidekick framework
backend is SQL 2014, with C# Linq to SQL in between



Due to the fact that I happen to be physically and visually challenged, progress is very slow course, so if you live in Bay Area and you want to participate, perhaps we can meet up somewhere, there is a very long to do list that needs to be taken care of 

As for the original dilemma, still no progress, I really need to get a hold of WWise with the schema version 30, the earliest I found so far has schema version 44, 2010.3, so if you happen to have it, please do let me know

Thanks!
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-19T18:54:01+00:00
- Post Title: Dragon Age 2 facefx and audio file names relation dilemma

In case you can't find the relation anywhere else, it must be in wwise audio banks.

As for wwise, try this one:

[http://hcs64.com/files/Wwise_v2009.3_Windows.zip](http://hcs64.com/files/Wwise_v2009.3_Windows.zip)
## Post #4
- Username: 123185321f
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Apr 28, 2012 8:53 am
- Post datetime: 2015-05-19T19:20:24+00:00
- Post Title: Dragon Age 2 facefx and audio file names relation dilemma

> Reply from daemon1
>
> In case you can't find the relation anywhere else, it must be in wwise audio banks.
Yes, I plan to eventually try and take apart init.bnk for clues 

> Reply from daemon1
>
> 
As for wwise, try this one:

http://hcs64.com/files/Wwise_v2009.3_Windows.zip
thank you very  very much!! This file is schema version 36, close enough I hope, I'll give it a try and let you know how it goes. The reason I think I need schema version 30, is because converting WAV files to WEM with schema version 44, Dragon age 2 didn't play any sound, and that may be because the Wwise Vorbis converter in the schema version 44 is incompatible with what Dragon age 2 expects. But I may be wrong, I'll see what happens with schema version 36 when converting sound files

Again, thank you very much!
## Post #5
- Username: 123185321f
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Apr 28, 2012 8:53 am
- Post datetime: 2015-05-19T23:57:55+00:00
- Post Title: Dragon Age 2 facefx and audio file names relation dilemma

> Reply from daemon1
>
> http://hcs64.com/files/Wwise_v2009.3_Windows.zip

Thank you!!! compressing wave files with Vorbis from Wwise 2009.3, schema version 36, made them playable in Dragon Age 2. The original Dragon Age 2 audio files uses schema version 30, but the codec seems to be friendly to files compressed with schema version 36. In my previous tests are used schema version 44 and up, to no avail, so your file saved the day. my previous tests consisted of extracting all audio files from the original ERF, convert them to OGG, convert them to WAV, convert them to WEM, ERF pack them back into a new ERF, rename the original ERF as _old, rename the new ERF with the original name,move it to the original location, start a new game from the beginning with the first cut scene, and wait for Varrick to say: "I had gentler invitations". Up until today I never heard his voice when testing as mentioned above with schema version 44 and up. But today with schema version 36 his voice sounded just fine!

As of now there is only one unknown that stands in between us and a complete cut scene editor for Dragon age 2, as of now we have: 
a way to compress new audio files and we now know that the built-in codec plays them,
generating new FaceFX
a dialogue Creator it's on its way, my current toolset is a read-only viewer for now, but should be doable to turn it into an editor
still the missing ingredient is how to connect the dialogue line ID for the audio file, I'll poke around in the init.BNK when I can

Thank you very much for your help with Wwise 2009.3 which added one more piece to the picture
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-20T18:03:35+00:00
- Post Title: Dragon Age 2 facefx and audio file names relation dilemma

This wwise version was saved for us by HCS, the man who made ww2ogg tool 

If you like, send me (PM) some files that may contain that names relation data. I have some experience finding those.
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-22T15:31:58+00:00
- Post Title: Dragon Age 2 facefx and audio file names relation dilemma

The relation is found. It is done through hash of audio event name in wwise audio bank. I will test it a little more and then publish the results.
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-22T17:50:37+00:00
- Post Title: Dragon Age 2 facefx and audio file names relation dilemma

Let's make an example of Varrick: "I've had gentler invitations."

There's probably a lot of ways to know the bank where it belongs to. One of them is .cl file:

pro000_opening6207373.cl

The name of this file consist of "pro000_opening" - this is the bank name and "6207373" - this is TalkID.

Now the audio event in the game is build like this:

play_6207373_m  (use "_f" if it was female version)

Wwise always calculates its audio event IDs through 32-bit FNV hash.

hash("play_6207373_m") = 0DE209EE - this is event ID for this phrase

Now let's open pro000_opening.bnk and analyze it's HIRC segment contents using the guide provided on xentax here: [http://wiki.xentax.com/index.php?title= ... 28*.bnk%29](http://wiki.xentax.com/index.php?title=Wwise_SoundBank_%28*.bnk%29)

It is a little different for wwise version used in DA2, but we still can find that:

1. Audio event (ID = 0DE209EE) contains one audio action (ID = 096B7F25)
2. Audio action (ID = 096B7F25) contains one voice (ID = 27796C6F)
3. Voice (ID = 27796C6F) use sound file (ID = 31FE666C) 

So now we only need to convert this to decimal 31FE666C = 838755948

And we know the sound file to play is 838755948.ogg
## Post #9
- Username: 123185321f
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Apr 28, 2012 8:53 am
- Post datetime: 2015-05-22T21:33:14+00:00
- Post Title: Dragon Age 2 facefx and audio file names relation dilemma

and that, my friends, is how an efficient brain works! 

It makes perfect sense, I have no idea how I missed this in my previous tests, I'm pretty sure I looked for hexadecimal value, big or little endian… No matter, I'm very grateful for the explanation and help! 

it's clear now that the bank files are needed as an index for the actual sound files to be streamed as needed/when needed.

Well, I'll see if I can turn my DA2 conversation explorer into a conversation editor, and integrate it with Wwise and FaceFX to add new content, but keep in mind the current state of my health, 0% arms usability (voice-recognition FTW!) and 15-30% eyes usability, so it may take a while 

Thank you again very much!
## Post #10
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-23T06:11:33+00:00
- Post Title: Dragon Age 2 facefx and audio file names relation dilemma

> Reply from 123185321f
>
> I'm pretty sure I looked for hexadecimal value, big or little endian…

The thin part here was in how they name their audio events. It could be anything, but in this case they used this "play_" prefix. I've seen this once in another game.
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-23T15:13:50+00:00
- Post Title: Dragon Age 2 facefx and audio file names relation dilemma

That's how it was researched:

I first started with 1003006487.ogg file. "I need some sort of justification for wasting my time". I've found this phrase in the talktable, and checked that there's nothing else in there except the talkID.

Audio filenames are numbers from 0 to 2^30, so this must be wwise audio IDs. I searched for this number in hex in all banks, and found it in gen00fl_aveline.bnk - rather large one. I already know wwise bank structure, so I quickly went through the chain from sound ID to voice, action and found event ID = 5dac701e. Unfortunately, it was nowhere to be found in any game files.

I thought maybe I'm missing something, because this character was present in many game levels, so I wanted to find a character with a small number of phrases. I took "commoner1", who seem to have only one phrase.

Strange enough, its bank has only one file, but 2 audio events. I supposed this file is played with different options/fx, and so we have 2 events. They have IDs A4682F51 & A4682F5A - only last number is different. Anyway, trying to search for these numbers again lead to nothing. This must mean that IDs are not stored anywhere in game files, but calculated on runtime from the event name.

Well, wwise use FNV hash, and it's good for us, because it has "last byte" problem - when names only differ by last char, their hashes will be also different in one last byte. So I can assume that was something like "commoner1_1" and "commoner1_2". But hash differs by 9, so this is not it. What can it be then? Suddenly I understood that names must be ending with "f" and "m", thus the difference in hash.

First I tried "6114295_m", but it was wrong. Then I remember in Dishonored audio events were named like "Play_83EA668809F861BB052D160D76F02EF5", so I decide to try "play_6114295_m" and it worked! End of story.
## Post #12
- Username: 123185321f
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Apr 28, 2012 8:53 am
- Post datetime: 2015-05-23T18:10:48+00:00
- Post Title: Dragon Age 2 facefx and audio file names relation dilemma

> Reply from daemon1
>
> Suddenly I understood that names must be ending with "f" and "m", thus the difference in hash.

First I tried "6114295_m", but it was wrong. Then I remember in Dishonored audio events were named like "Play_83EA668809F861BB052D160D76F02EF5", so I decide to try "play_6114295_m" and it worked! End of story.

Amazing! thank you very much! in my tests it never occurred to me to try with the "play" prefix, so I was banging my head against the wall when the hash of "talkID_gender" didn't match with anything. Good catch! now that you figured it out it's obvious that wwise events ( such as play, stop, etc.) are being used as part of the arguments between the engine and wwise

Thanks again!
## Post #13
- Username: planesofduality
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 10, 2020 9:20 am
- Post datetime: 2020-12-10T01:25:14+00:00
- Post Title: Dragon Age 2 facefx and audio file names relation dilemma

Shot in the dark, but how can I search the bnk files' HIRC section to follow the process to find the audio file number outlined above? Tbh following the link to how the bnk files are composed made sense in theory, but in practice, I don't know where to start.
## Post #14
- Username: 123185321f
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Apr 28, 2012 8:53 am
- Post datetime: 2020-12-25T07:07:36+00:00
- Post Title: Dragon Age 2 facefx and audio file names relation dilemma

here [https://1drv.ms/u/s!AtUshxK9rYxAjTPABae ... x?e=KdDTAV](https://1drv.ms/u/s!AtUshxK9rYxAjTPABae6PU9IfAox?e=KdDTAV) you can find all the dialogue line ID and sound ID sets.

The CSV file contains the following columns
dialogue ID, gender, sound ID, Bank file parent ID

In the BNK binary file you can find the sound ID hexadecimal little endian equivalent. 
e.g.: 6000680, m, 267111449, dae000_flemeth.bnk
in dae000_flemeth.bnk there should be 267111449 = 0xFEBCC19 which is little endian 19 CC BC FE

I think, it's been a while
## Post #15
- Username: mvs15
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Feb 16, 2023 1:42 pm
- Post datetime: 2023-05-14T14:02:39+00:00
- Post Title: Dragon Age 2 facefx and audio file names relation dilemma

Hello. Please tell me how to find out the original file names in the bnk (int files) of the game Dishonored, for example Play_6B84E3670819E4BBB4229C1D103311A2? For a very long time I studied the bnk(int) file through the hex editor, but I could not understand how this name is created. I really hope for your help. Thanks

I'm sorry, I don't know English well. Because of this, I used a translator.
## Post #16
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-05-17T07:00:12+00:00
- Post Title: Re: Dragon Age 2 facefx and audio file names relation dilemma

> Reply from mvs15 ↑Sun May 14, 2023 10:02 pm at Sun May 14, 2023 10:02 pm
>
> 
Hello. Please tell me how to find out the original file names in the bnk (int files) of the game Dishonored, for example Play_6B84E3670819E4BBB4229C1D103311A2? For a very long time I studied the bnk(int) file through the hex editor, but I could not understand how this name is created. I really hope for your help. Thanks
I dont remember how it worked, it was too long ago.
