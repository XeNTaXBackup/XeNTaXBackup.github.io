## Post #1
- Username: Kosmonautilus
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 27, 2022 8:56 am
- Post datetime: 2022-10-30T03:20:46+00:00
- Post Title: Extracting .bank files from Signalis

Hi!
I've been trying to extract Signalis' FMOD .bank files using QuickBMS and a couple of scripts but have been unsuccessful and results in 0 files found in 0 seconds. Any help would be much appreciated and I've provided a sample below. 

[https://drive.google.com/file/d/1m1STwD ... share_link](https://drive.google.com/file/d/1m1STwDKS5m8VDfcWTBS4rXyyMJj3elYM/view?usp=share_link) <- link to the example .bank file.
*Tried to attach normally but it said it was an invalid extension.

Also excuse me for any bad procedure, this is my first post.
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-10-31T21:06:56+00:00
- Post Title: Extracting .bank files from Signalis

It seems to be encrypted.
## Post #3
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2022-11-12T13:18:51+00:00
- Post Title: Extracting .bank files from Signalis

> Reply from ikskoks ↑Tue Nov 01, 2022 5:06 am at Tue Nov 01, 2022 5:06 am
>
> 
It seems to be encrypted.

What makes you think so? To me it seems to be using come compression method for the chunks, but actual metadata is there, unecnrypted, High entropy for chunks does not necessarily means encryption, the format also newer than any of the current tools support.

It has the key, but I still dont think it is used: 

```
X3EK%Bbga-%Y9HZZ%gkc*C512*$$DhRxWTGgjUG@=rUD
```
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-11-12T17:26:57+00:00
- Post Title: Extracting .bank files from Signalis

I meant data, not header. But you are right - it may be compressed only. I didn't checked it to deeply.
## Post #5
- Username: AutoBio
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Nov 14, 2022 11:59 am
- Post datetime: 2022-11-14T06:38:50+00:00
- Post Title: Extracting .bank files from Signalis

Any progress?
After extensive digging around nothing worked for me - neither conventional quickbms scripts and fsb extractors/dumpers (no fsb "magic" in files), nor fmod bank tools, nor foobar2000 with vgmstream, nor a bunch of other tools and ideas. Tried comtype_scan and encryption_scan with a key mentioned by Kein ([viewtopic.php?f=17&t=25948#p188264](https://forum.xentax.com/viewtopic.php?f=17&t=25948#p188264)), but my potato laptop didn't want to help me with it   

How do you even approach that?
- Create a new project in Unity (Unreal, Godot) or simple console program with FMOD API to play files and then just record audio?

- Try to find possible encryption / compression methods?

- Create new project in FMOD studio, add a variety of audio files, try a variety of .bank creation methods and compare results to your .bank files to find what method might've been used during their creation to help find a solution?

Please, share your wisdom!

Also here are all files (279MB zip) [https://drive.google.com/file/d/15PoAMw ... sp=sharing](https://drive.google.com/file/d/15PoAMwuuho_27O2QdtmEEVN27rlRORGw/view?usp=sharing)
## Post #6
- Username: AutoBio
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Nov 14, 2022 11:59 am
- Post datetime: 2022-11-14T12:51:05+00:00
- Post Title: Extracting .bank files from Signalis

Update: decided to try 3rd route (FMOD Studio). 

No encryption built .banks have FSB5 "magic", fsbext -o -1 works as intended.

Encrypted .banks don't have FSB5 "magic", while still having "RIFF... FEV FMT..." header. 
Will try to compare the file I've got during experiments with one of files I want to extract for more similarities or differences, but for now I hope SIGNALIS devs just used basic build settings.

Does that mean I need to find how to decrypt the file now (if the key provided above is valid)? 
Someone tried  to ask staff on fmod forums what encryption algorithm do they use for banks, but the only answer was "it is a proprietary algorithm".

* Just compared non-encrypted and encrypted file made with the same assets. Difference starts right from the first "FSB5" and to the end of file.
## Post #7
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2022-11-14T13:09:35+00:00
- Post Title: Extracting .bank files from Signalis

If you are willing to put effort and time, some parts of fmod are open-source:
[https://github.com/fmod](https://github.com/fmod)

if these banks are encrypted , the issue is that it is not whole-file encryption but rather in chunks so you first need to inherit the structure and then decrypt chunks. may be some sources have the logic.
## Post #8
- Username: AutoBio
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Nov 14, 2022 11:59 am
- Post datetime: 2022-11-14T13:21:20+00:00
- Post Title: Extracting .bank files from Signalis

> Reply from Kein ↑Mon Nov 14, 2022 9:09 pm at Mon Nov 14, 2022 9:09 pm
>
> 
If you are willing to put effort and time, some parts of fmod are open-source:
https://github.com/fmod

if these banks are encrypted , the issue is that it is not whole-file encryption but rather in chunks so you first need to inherit the structure and then decrypt chunks. may be some sources have the logic.

Wow, thank you! 
Will try and see, what I can do with it.
## Post #9
- Username: AutoBio
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Nov 14, 2022 11:59 am
- Post datetime: 2022-11-14T17:57:05+00:00
- Post Title: Extracting .bank files from Signalis

> Reply from Kein ↑Sat Nov 12, 2022 9:18 pm at Sat Nov 12, 2022 9:18 pm
>
> 
It has the key, but I still dont think it is used: 
Code: Select allX3EK%Bbga-%Y9HZZ%gkc*C512*$$DhRxWTGgjUG@=rUD

Thank you for the key, it worked! How did you get it?

Just needed to remove metadata till encrypted .fsb 
Needed to delete from "RIFF" till combo "MUTE{4 nulls}REFI{4 nulls}PLAT{4 nulls}SND", some more symbols and a lot of nulls. 
The first non-null after that will be the start of encrypted .fsb
Then decrypted .fsb with your key and tools from here [viewtopic.php?t=16059#p132327](https://forum.xentax.com/viewtopic.php?t=16059#p132327)

Now to automate it or at least make the instructions more clear...
## Post #10
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2022-11-14T19:10:11+00:00
- Post Title: Extracting .bank files from Signalis

No problem. Here is the tool that can quickly strip metadata based on SND chunk position. Simply give it either full path (in quotes if spaces) or filename if in the same folder. It also has basic sanity check.
[https://www.dropbox.com/s/43q7zmov01ru2 ... p.exe?dl=1](https://www.dropbox.com/s/43q7zmov01ru2xj/FSBStrip.exe?dl=1)
## Post #11
- Username: KlausSh
- Rank: beginner
- Number of posts: 25
- Joined date: Fri May 06, 2022 12:08 am
- Post datetime: 2022-11-24T18:41:59+00:00
- Post Title: Extracting .bank files from Signalis

I managed to extract some audio but password not working for all files + the files ogg's are unreadable
## Post #12
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2022-11-24T19:33:51+00:00
- Post Title: Extracting .bank files from Signalis

It only works with Steam version and password is compatible with all banks, you are doing something wrong.
## Post #13
- Username: richardphone
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jan 04, 2023 8:31 pm
- Post datetime: 2023-01-04T13:33:26+00:00
- Post Title: Extracting .bank files from Signalis

can someone please help i'm trying to extract the files but all i get is audio without sound ... ??
## Post #14
- Username: richardphone
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jan 04, 2023 8:31 pm
- Post datetime: 2023-01-04T14:42:55+00:00
- Post Title: Extracting .bank files from Signalis

> Reply from Kein ↑Fri Nov 25, 2022 3:33 am at Fri Nov 25, 2022 3:33 am
>
> 
It only works with Steam version and password is compatible with all banks, you are doing something wrong.

using FSBstrip then fsdbext then key it generates audio but it's unreadable
## Post #15
- Username: AfrakaMax
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 12, 2023 10:54 pm
- Post datetime: 2023-10-12T16:21:49+00:00
- Post Title: Extracting .bank files from Signalis

> Reply from Kein ↑Tue Nov 15, 2022 3:10 am at Tue Nov 15, 2022 3:10 am
>
> 
No problem. Here is the tool that can quickly strip metadata based on SND chunk position. Simply give it either full path (in quotes if spaces) or filename if in the same folder. It also has basic sanity check.
https://www.dropbox.com/s/43q7zmov01ru2 ... p.exe?dl=1

I`m trying to unpack a fsb file from another Game(the game is Paint The Town Red) using the tool
I followed the step and get a file named XXX.extracted , how to use it?(I still dont know how to get the password ) ; sorry for the noob question but I know nothing about encryption or data...
