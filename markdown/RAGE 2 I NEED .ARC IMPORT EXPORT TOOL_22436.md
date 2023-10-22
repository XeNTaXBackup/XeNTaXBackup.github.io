## Post #1
- Username: Mastertarnslator
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 15, 2020 2:22 am
- Post datetime: 2020-07-22T16:13:42+00:00
- Post Title: RAGE 2 I NEED .ARC IMPORT EXPORT TOOL

137/5000
My friends, I already have language files removed and I want to embed this language file in the game again, can you help?
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-07-22T21:28:37+00:00
- Post Title: RAGE 2 I NEED .ARC IMPORT EXPORT TOOL

This rage2_import script looks promising.   
Did you try to use it? And how did you get those scripts?
## Post #3
- Username: Mastertarnslator
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 15, 2020 2:22 am
- Post datetime: 2020-07-23T11:57:58+00:00
- Post Title: RAGE 2 I NEED .ARC IMPORT EXPORT TOOL

A member of these language files had given me. But I can't reach him right now. By the way, I did not extract the language files. I need an import tool right now.
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-07-23T15:28:06+00:00
- Post Title: RAGE 2 I NEED .ARC IMPORT EXPORT TOOL

So maybe attach those scripts and sample files.
Btw how did you manage to get text and not use export tool to achieve this?
And why do you need import tool when you already have one?
## Post #5
- Username: Mastertarnslator
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 15, 2020 2:22 am
- Post datetime: 2020-07-23T20:16:37+00:00
- Post Title: RAGE 2 I NEED .ARC IMPORT EXPORT TOOL

> Reply from ikskoks ↑Thu Jul 23, 2020 11:28 pm at Thu Jul 23, 2020 11:28 pm
>
> 
So maybe attach those scripts and sample files.
Btw how did you manage to get text and not use export tool to achieve this?
And why do you need import tool when you already have one?

My brother didn't even know I had an import tool. So how do I use this import tool? I have no idea how the file system works. Can you help me with this?
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-07-23T21:12:22+00:00
- Post Title: RAGE 2 I NEED .ARC IMPORT EXPORT TOOL

You probably need to install AutoIt 
[https://www.autoitscript.com/site/autoit/downloads/](https://www.autoitscript.com/site/autoit/downloads/)
then google something like "autoit script execution" and you will be able to import files when you learn how to do it.
## Post #7
- Username: Mastertarnslator
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 15, 2020 2:22 am
- Post datetime: 2020-07-24T11:21:40+00:00
- Post Title: RAGE 2 I NEED .ARC IMPORT EXPORT TOOL

> Reply from ikskoks ↑Fri Jul 24, 2020 5:12 am at Fri Jul 24, 2020 5:12 am
>
> 
You probably need to install AutoIt 
https://www.autoitscript.com/site/autoit/downloads/
then google something like "autoit script execution" and you will be able to import files when you learn how to do it.

If I upload your language files, can you show me how to import and export? Yesterday I did a lot of research about Autoit, but I couldn't find anything properly.
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-07-24T15:00:02+00:00
- Post Title: RAGE 2 I NEED .ARC IMPORT EXPORT TOOL

I may try to do it, but I can't promise anything. I'm not an AutoIt expert.
## Post #9
- Username: Mastertarnslator
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 15, 2020 2:22 am
- Post datetime: 2020-07-24T15:17:47+00:00
- Post Title: RAGE 2 I NEED .ARC IMPORT EXPORT TOOL

> Reply from ikskoks ↑Fri Jul 24, 2020 11:00 pm at Fri Jul 24, 2020 11:00 pm
>
> 
I may try to do it, but I can't promise anything. I'm not an AutoIt expert.

Thank you so much brother! Im uploading language files for you now!

Here is link: [https://mega.nz/folder/PwoDUBSa#2Rq4TCbB0C3eYOFkl-sang](https://mega.nz/folder/PwoDUBSa#2Rq4TCbB0C3eYOFkl-sang)
## Post #10
- Username: terminator
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-07-24T20:40:45+00:00
- Post Title: RAGE 2 I NEED .ARC IMPORT EXPORT TOOL

Ok, this import script works, but it is really really slow [https://youtu.be/TgxrDjeE7OE](https://youtu.be/TgxrDjeE7OE)

When using this debugger [http://www.thefoolonthehill.net/drupal/ ... 20Debugger](http://www.thefoolonthehill.net/drupal/AutoIt%20Debugger)
you can see on the right panel which array entry is currently processed.

You have over 63000 lines in your text file, so you need to wait half an hour or more to finish processing
(I really don't know why it is working so slow on my PC, but you probably have the same situation).
When program finish, you will see file with "NEW_" prefix in your directory. This is your imported file. [https://imgur.com/a/xSPrhyI](https://imgur.com/a/xSPrhyI)

I have compiled it for you [https://drive.google.com/file/d/1G8tCeE ... sp=sharing](https://drive.google.com/file/d/1G8tCeEkVtTy4FyokWKfFLpWgnikesuX2/view?usp=sharing)
so it may help you with running, but I recommend to use debugger for progress watching
(just add $NEWdata variable to watcher on the right side).
## Post #11
- Username: Mastertarnslator
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 15, 2020 2:22 am
- Post datetime: 2020-07-24T23:27:21+00:00
- Post Title: RAGE 2 I NEED .ARC IMPORT EXPORT TOOL

> Reply from ikskoks ↑Sat Jul 25, 2020 4:40 am at Sat Jul 25, 2020 4:40 am
>
> 
Ok, this import script works, but it is really really slow https://youtu.be/TgxrDjeE7OE

When using this debugger http://www.thefoolonthehill.net/drupal/ ... 20Debugger
you can see on the right panel which array entry is currently processed.

You have over 63000 lines in your text file, so you need to wait half an hour or more to finish processing
(I really don't know why it is working so slow on my PC, but you probably have the same situation).
When program finish, you will see file with "NEW_" prefix in your directory. This is your imported file. https://imgur.com/a/xSPrhyI

I have compiled it for you https://drive.google.com/file/d/1G8tCeE ... sp=sharing
so it may help you with running, but I recommend to use debugger for progress watching
(just add $NEWdata variable to watcher on the right side).

First of all, thank you for everything. I did what it said and it works really smoothly. Thank you very much. But I have one last problem. These language files are ARC. I have to embed it in TAB and ARC files. Can you help me with this? I have a Just Cause 4 Tool unpack, but it doesn't work.

When I read the Game0.tab file, it gives a screen like this:
-------------------------------------------------- --------------------
Unhandled Exception: System.FormatException: The format of one of the items defined was invalid.
location:
Gibbed.JustCause4.FileFormats.ArchiveTableFile.Deserialize (Stream input) in c: \ projects \ gibbed-jc4 \ projects \ Gibbed.JustCause4.FileFormats \ ArchiveTableFile.cs: line 102
   location: Gibbed.JustCause4.Unpack.Program.Main (String [] args) in c: \ projects \ gibbed-jc4 \ projects \ Gibbed.JustCause4.Unpack \ Program.cs: line 105

The game0.ARC file shows a warning like this:
-------------------------------------------------- -------------------------------------------
Unhandled Exception: System.FormatException: The format of one of the items defined was invalid.
   location: Gibbed.JustCause4.FileFormats.ArchiveTableFile.Deserialize (Stream input) in c: \ projects \ gibbed-jc4 \ projects \ Gibbed.JustCause4.FileFormats \ ArchiveTableFile.cs: line 93
   location: Gibbed.JustCause4.Unpack.Program.Main (String [] args) in c: \ projects \ gibbed-jc4 \ projects \ Gibbed.JustCause4.Unpack \ Program.cs: line 105
## Post #12
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-07-25T09:55:52+00:00
- Post Title: RAGE 2 I NEED .ARC IMPORT EXPORT TOOL

It seems that TAB/ARC archives are covered in different topics:
[viewtopic.php?t=20486](https://forum.xentax.com/viewtopic.php?t=20486)
[viewtopic.php?t=19143](https://forum.xentax.com/viewtopic.php?t=19143)

If mentioned tools don't work, you can ask authors for update. That's all you can do here for now.
## Post #13
- Username: terminator
- Rank: advanced
- Number of posts: 53
- Joined date: Mon Mar 29, 2010 3:16 pm
- Post datetime: 2022-03-13T17:01:40+00:00
- Post Title: RAGE 2 I NEED .ARC IMPORT EXPORT TOOL

> Reply from ikskoks ↑Sat Jul 25, 2020 4:40 am at Sat Jul 25, 2020 4:40 am
>
> 
I have compiled it for you https://drive.google.com/file/d/1G8tCeE ... sp=sharing
Please, can you upload this file ("rage2_tools_compiled.zip") somewhere else, and again? Google says it contains viruses and I can't download it.
It would be a great help for me! Thank You.
## Post #14
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-03-13T19:32:57+00:00
- Post Title: RAGE 2 I NEED .ARC IMPORT EXPORT TOOL

Sure, here's the mirror
[https://mega.nz/file/UuA2kRAb#P5w3iVS2f ... CcT-gBnS_Y](https://mega.nz/file/UuA2kRAb#P5w3iVS2fDPGEV02vw8qanN_BJsDdBitsCcT-gBnS_Y)

It doesn't contain any viruses. It was compiled from the sources, but you can compile it again using AutoIt.
## Post #15
- Username: terminator
- Rank: advanced
- Number of posts: 53
- Joined date: Mon Mar 29, 2010 3:16 pm
- Post datetime: 2022-03-14T10:17:21+00:00
- Post Title: RAGE 2 I NEED .ARC IMPORT EXPORT TOOL

> Reply from ikskoks ↑Mon Mar 14, 2022 3:32 am at Mon Mar 14, 2022 3:32 am
>
> 
It doesn't contain any viruses. It was compiled from the sources, but you can compile it again using AutoIt.
ikskoks, thank you so much! Yeah, I know that Google has some paranoia
## Post #16
- Username: terminator
- Rank: advanced
- Number of posts: 53
- Joined date: Mon Mar 29, 2010 3:16 pm
- Post datetime: 2022-03-15T11:11:32+00:00
- Post Title: Re: RAGE 2 I NEED .ARC IMPORT EXPORT TOOL

Sadly, the game (RAGE 2) crashing after even 1 word modified...
Import tool made a bigger file. Maybe that's the cause.
