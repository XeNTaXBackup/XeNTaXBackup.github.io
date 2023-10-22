## Post #1
- Username: Tartarus
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jul 08, 2013 5:19 pm
- Post datetime: 2014-12-21T06:25:17+00:00
- Post Title: Really need help!

Does anyone know how to extract audio (like the dialogue) from The Evil Within? I've looking for a while now and haven't found a way to do so. I've extracted files that have MSADPCM extensions which seem to be audio but I can't play them no matter what program I use.

If anyone could help that would be much appreciated!
## Post #2
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2014-12-25T15:07:44+00:00
- Post Title: Really need help!

Already answered:

[viewtopic.php?f=17&t=12138](http://forum.xentax.com/viewtopic.php?f=17&t=12138)
## Post #3
- Username: Tartarus
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jul 08, 2013 5:19 pm
- Post datetime: 2015-01-01T22:45:59+00:00
- Post Title: Really need help!

> Reply from Vosvoy
>
> Already answered:

viewtopic.php?f=17&t=12138

Which answer was the solution? How do you do it?
## Post #4
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2015-01-02T19:08:10+00:00
- Post Title: Really need help!

This line:

> Reply from Vosvoy
>
> Okay. Back to Xbox360 version for me then. I suggest you guys do the same 'cause you can have filenames as PC version (thanks to Aluigi) and .xma files are not lossy after conversion.
Plus, no weird compression in the .xma files of the console version. I tested it with regular tools (xma_parse11 + ToWav) and it worked like a charm (+5Gb of music and sound w/o the voice lines).
(You have to own a NTSC Xbox360 copy of the game)

Now, if you don't know anything 'bout extraction of .xma sounds at all, just tell me.

Late advice: Next time you want help from us with something, be more accurate about your problem in the title (type of file/game/script...) and not only "Really need help!" because we don't really like that type of title on this forum. I, personally, don't care for this time. I will try to help you. 
Thanks in advance.
## Post #5
- Username: Tartarus
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jul 08, 2013 5:19 pm
- Post datetime: 2015-01-05T00:28:13+00:00
- Post Title: Really need help!

> Reply from Vosvoy
>
> This line:
Vosvoy wrote:Okay. Back to Xbox360 version for me then. I suggest you guys do the same 'cause you can have filenames as PC version (thanks to Aluigi) and .xma files are not lossy after conversion.
Plus, no weird compression in the .xma files of the console version. I tested it with regular tools (xma_parse11 + ToWav) and it worked like a charm (+5Gb of music and sound w/o the voice lines). 
(You have to own a NTSC Xbox360 copy of the game)

Now, if you don't know anything 'bout extraction of .xma sounds at all, just tell me.

Late advice: Next time you want help from us with something, be more accurate about your problem in the title (type of file/game/script...) and not only "Really need help!" because we don't really like that type of title on this forum. I, personally, don't care for this time. I will try to help you. 
Thanks in advance.
Thanks for the response.

I can get a hold of an xbox version and try it out. If I run into some trouble I'll hit you up if you're still down to help me out. +1 Thanks.
## Post #6
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2015-01-07T12:20:18+00:00
- Post Title: Really need help!

> Reply from Tartarus
>
> 

I can get a hold of an xbox version and try it out. If I run into some trouble I'll hit you up if you're still down to help me out. +1 Thanks.

Sure. Post me your questions in this thread if you have any problem during the extraction process.
## Post #7
- Username: Tartarus
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jul 08, 2013 5:19 pm
- Post datetime: 2015-01-30T08:09:36+00:00
- Post Title: Really need help!

> Sure. Post me your questions in this post if you have any problem during the extraction process.

I finally got a chance to pick up the 360 version of  The Evil Within. I got the .xma files but not sure how to use the tools to convert them. If you could help me out that would be much appreciated.
## Post #8
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2015-01-30T19:35:54+00:00
- Post Title: Really need help!

Alright. I'm gonna try to teach you the technique I use. Maybe there's a better one but my way is pretty simple and efficient (at least for me). Excuse my poor english in advance.

First, make sure you have the right tools:

_[QuickBMS](http://aluigi.altervista.org/papers/quickbms.zip)
_[ToWav](http://www.ctpax-x.org/index.php?goto=files&show=24&lang=en) (for this one, just scroll down the page and click on the download text)
_[xma_parse011](http://www.hcs64.com/files/xma_parse011.zip)
_[Notepad++](http://notepad-plus-plus.org/) (optional) This could be useful if you want to create/edit a .txt or a .bat file because it highlights some commands with color and stuff.

Extract all the main archives in a same folder (that's gonna be your archive folder) and create separately an extraction folder (where all your tools have to be and where you're gonna convert the sounds).

Then, you'll have to create two QuickBMS script files:

- addheader_mono.bms (copy/paste the following code in a empty .txt file with the notepad and save it as "addheader_mono.bms" in your extraction folder)
Info: This script add a mono header to the raw file(s) to be converted to proper .wav file(s).

```

get NAME basename
get SIZE asize
string NAME += ".xma"

append
log MEMORY_FILE 0 SIZE
append
math SIZE += 60
log NAME 0 SIZE MEMORY_FILE
```

- addheader_stereo.bms (copy/paste the following code in a empty .txt file with the notepad and save it as "addheader_stereo.bms" in your extraction folder)
Info: This script add a stereo header to the raw file(s) to be converted to proper .wav file(s).

```

get NAME basename
get SIZE asize
string NAME += ".xma"

append
log MEMORY_FILE 0 SIZE
append
math SIZE += 60
log NAME 0 SIZE MEMORY_FILE
```

Next, You'll have to create three batch command files:

- RUN - XMAMono (copy/paste the following code in a empty .txt file with the notepad and save it as "RUN - XMAMono.bat" in your extraction folder)
Info: I chose to rename every processed .xma files into .res files to avoid any mistakes. That's my way to do it.

```
for %%i in (*.res) do "%CD%\xma_test.exe" %%i -2 -o 0x00 -B -r %%~ni.xm
for %%i in (*.xm) DO "%CD%\quickbms.exe" -o "%CD%\addheader_mono.bms" %%i "%CD%"
del *.xm
@towav.exe *.xma
del *.xma
```

- RUN - XMAStereo (copy/paste the following code in a empty .txt file with the notepad and save it as "RUN - XMAStereo.bat" in your extraction folder)
Info: I chose to rename every processed .xma files into .res files to avoid any mistakes. That's my way to do it.

```
for %%i in (*.res) do "%CD%\xma_test.exe" %%i -2 -o 0x00 -B -r %%~ni.xm
for %%i in (*.xm) DO "%CD%\quickbms.exe" -o "%CD%\addheader_stereo.bms" %%i "%CD%"
del *.xm
@towav.exe *.xma
del *.xma
```

- RES_ERASER (copy/paste the following code in a empty .txt file with the notepad and save it as "RES_ERASER.bat" in your extraction folder)
Info: This batch command delete every .res file in the folder (files created by the "RUN" batch commands. Could save a lot of time).

```
del *.res
```

Okay, you should be good to go now. It could be a little confusing for someone who's not familiar with all that but, once you've got all your tools ready to go, it's fairly easy.

Now, for the extraction process:

Advice: If you're a "sound hunter" like me and want to pick every sound of a game, then go folder by folder because it's easy to lose yourself and that could save you a lot of time

First, copy/paste the .xma files you want to convert in your extraction folder from your archive folder (I advise you to never directly convert the original files that you previously extracted from the game archives because it's a bit risky. You may mistakenly delete extracted files and that's not cool).
Next, launch the RUN - XMAStereo if you have stereo .xma files (like musics, background ambience, cutscenes sfx, ...) in your folder or RUN - XMAMono if you have mono .xma files (like foley and voice sounds) in your folder. After a little while, you should see the converted .xma files as .wav files. Play them before anything else! It's important!
Why? Because if the sounds are completly messed up, that means you tried to convert a mono .xma file into a stereo .wav file (and vice versa). That's not good, be aware of that.

[Note: You can easily detect screwed up converted sounds by their size (generally from 1 to 4 kb)]

Then, you have two solutions for this problem:

First, you can blindly select your file as you're sure they are mono or stereo .xma files and restart the process if you made a mistake.

Or you can use a hex editor program like [HxD](http://mh-nexus.de/en/hxd/) to determine if your files are stereo or mono.

If you want to use HxD then install it and, when it's done, launch it and drag-and-drop your files in it (not too many files at once because it could crash the program). 
Next, go in search/find (or Ctrl-F) and, in the "search for" box, write FC 01 C0 01 for stereo flag or FC 03 80 00 for mono flag. Before anything else, be sure to change the "datatype" scroll box into "Hex-values" ("Text-string" by default). If "Can't find FC 01 C0 01" appears, that means that the file is not a stereo .xma file (and vice versa).

Both ways have their pros and cons. Do as you want.

[Note: Keep in mind that you can reuse this technique for other games but you'll probably need some other tools. Most of the situations are trickier but that's a good start.]

Voilà. I think that's all for me. Tell me if there's any problem still.

PS: Don't forget to use the RES_ERASER batch command if you want to quickly delete all .res files in your extraction folder. At least when you're sure you're done with the process. 
Oh, one last thing, it's very important to have a basic knowledge of [windows prompt commands](http://en.wikipedia.org/wiki/List_of_DOS_commands) because it's very useful with batch files.

Cordialy.
## Post #9
- Username: Tartarus
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jul 08, 2013 5:19 pm
- Post datetime: 2015-01-31T10:46:22+00:00
- Post Title: Really need help!

Wow man thanks for the in-depth reply. I'll definitely give it a shot
## Post #10
- Username: Tartarus
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jul 08, 2013 5:19 pm
- Post datetime: 2015-02-02T10:42:33+00:00
- Post Title: Really need help!

> Reply from Vosvoy
>
> Alright. I'm gonna try teach you the technique I use. Maybe there's a better one but my way is pretty simple and efficient (at least for me). Excuse my poor english in advance.

First make sure you have the right tools:

_quickbms
_ToWav (for this one, just scroll down the page and click on the download text)
_xma_parse011

Extract all the archives in a same folder (that's gonna be your extraction folder).

Then, you'll have to create two QuickBMS script files:

- addheader_mono.bms (copy/paste the following code in a empty .txt file with the notepad and save it as "addheader_mono.bms" in your extraction folder)
Info: This script add a mono header to the raw file(s) to be converted to proper .wav file(s).
Code: Select allset MEMORY_FILE binary "\x52\x49\x46\x46\xb8\x59\xa7\x00\x57\x41\x56\x45\x66\x6d\x74\x20\x20\x00\x00\x00\x65\x01\x10\x00\xd6\x10\x00\x00\x01\x00\x00\x03\xe3\x9a\x00\x00\x80\xbb\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x02\x00\x64\x61\x74\x61\xff\xff\xff\x70"

get NAME basename
get SIZE asize
string NAME += ".xma"

append
log MEMORY_FILE 0 SIZE
append
math SIZE += 60
log NAME 0 SIZE MEMORY_FILE
- addheader_stereo.bms (copy/paste the following code in a empty .txt file with the notepad and save it as "addheader_stereo.bms" in your extraction folder)
Info: This script add a stereo header to the raw file(s) to be converted to proper .wav file(s).
Code: Select allset MEMORY_FILE binary "\x52\x49\x46\x46\xb8\x59\xa7\x00\x57\x41\x56\x45\x66\x6d\x74\x20\x20\x00\x00\x00\x65\x01\x10\x00\xd6\x10\x00\x00\x01\x00\x00\x03\xe3\x9a\x00\x00\x80\xbb\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x02\x02\x00\x64\x61\x74\x61\xff\xff\xff\x70"

get NAME basename
get SIZE asize
string NAME += ".xma"

append
log MEMORY_FILE 0 SIZE
append
math SIZE += 60
log NAME 0 SIZE MEMORY_FILE
Next, You'll have to create three batch command files:

- RUN - XMAMono (copy/paste the following code in a empty .txt file with the notepad and save it as "RUN - XMAMono.bat" in your extraction folder)
Info: I chose to rename every processed .xma files into .res files to avoid any mistakes. That's my way to do it.
Code: Select allren *.xma *.res
for %%i in (*.res) do "%CD%\xma_test.exe" %%i -2 -o 0x00 -B -r %%~ni.xm
for %%i in (*.xm) DO "%CD%\quickbms.exe" -o "%CD%\addheader_mono.bms" %%i "%CD%"
del *.xm
@towav.exe *.xma
del *.xma
- RUN - XMAStereo (copy/paste the following code in a empty .txt file with the notepad and save it as "RUN - XMAStereo.bat" in your extraction folder)
Info: I chose to rename every processed .xma files into .res files to avoid any mistakes. That's my way to do it.
Code: Select allren *.xma *.res
for %%i in (*.res) do "%CD%\xma_test.exe" %%i -2 -o 0x00 -B -r %%~ni.xm
for %%i in (*.xm) DO "%CD%\quickbms.exe" -o "%CD%\addheader_stereo.bms" %%i "%CD%"
del *.xm
@towav.exe *.xma
del *.xma
- RES_ERASER (copy/paste the following code in a empty .txt file with the notepad and save it as "RES_ERASER.bat" in your extraction folder)
Info: This batch command delete every .res file in the folder (files created by the "RUN" batch commands. Could save a lot of time).
Code: Select alldel *.res
Okay, you should be good to go now. It could be a little confusing for someone who's not familiar with all that but, once you've got all your tools ready to go, it's fairly easy.

Now, for the extraction process:

Advice: If you're a "sound hunter" like me and want to pick every sound of a game, then go folder by folder because it's easy to lose yourself and that could save you a lot of time

First, copy/paste the .xma files you want to convert in your extraction folder (I advise you to never directly convert the original files that you previously extracted from the game archives because it's a bit risky. You may mistakenly delete extracted files and that's not cool).
Next, launch the RUN - XMAStereo if you have stereo .xma files (like musics, background ambience, cutscenes sfx, ...) in your folder or RUN - XMAMono if you have mono .xma files (like foley and voice sounds) in your folder. After a little while, you should see the converted .xma files as .wav files. Play them before anything else! It's important!
Why? Because if the sounds are completly messed up, that means you tried to convert a mono .xma file into a stereo .wav file (and vice versa). That's not good, be aware of that.

[Note: You can easily detect screwed up converted sounds by their size (generally from 1 to 4 kb)]

Then, you have two solutions for this problem:

First, you can blindly select your file as you're sure they are mono or stereo .xma files and restart the process if you made a mistake.

Or you can use a hex editor program like HxD to determine if your files are stereo or mono.

If you want to use HxD then install it and, when it's done, launch it and drag-and-drop your files in it (not too many files at once because it could crash the program). 
Next, go in search/find (or Ctrl-F) and, in the "search for" box, write FC 01 C0 01 for stereo flag or FC 03 80 00 for mono flag. Before anything else, be sure to change the "datatype" scroll box into "Hex-values" ("Text-string" by default). If "Can't find FC 01 C0 01" appears, that means that the file is not a stereo .xma file (and vice versa).

Both ways have their pros and cons. Do as you want.

[Note: Keep in mind that you can reuse this technique for other games but you'll probably need some other tools. Most of the situations are trickier but that's a good start]

Voilà. I think that's all for me. Tell me if there's any problem still.

PS: Don't forget to use the RES_ERASER batch command if you want to quickly delete all .res files in your extraction folder. At least when you're sure you're done with the process.

Cordialy.

I tried your method and it works great, finally got the audio for all the characters! One issue though is that the audio seems slightly higher pitched than it's supposed to be. Is there any fix for that or is it unavoidable?
## Post #11
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2015-02-02T12:44:19+00:00
- Post Title: Really need help!

> Reply from Tartarus
>
> I tried your method and it works great, finally got the audio for all the characters! One issue though is that the audio seems slightly higher pitched than it's supposed to be. Is there any fix for that or is it unavoidable?

Yeah, I think that's because some sounds have a lower sampling rate (44100Hz? 32000Hz? I can't tell) while the tool convert those as 48000Hz by default. You can simply switch the sampling rate via Audacity.

If you want to directly convert those sounds with a 44100Hz sampling rate, just change the addheader_mono.bms to:

```

get NAME basename
get SIZE asize
string NAME += ".xma"

append
log MEMORY_FILE 0 SIZE
append
math SIZE += 60
log NAME 0 SIZE MEMORY_FILE
```

Just use this modified script for those (voice?) sounds because the majority of the sounds of The Evil Within have a 48000Hz sampling rate.
## Post #12
- Username: Tartarus
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jul 08, 2013 5:19 pm
- Post datetime: 2015-02-04T03:41:33+00:00
- Post Title: Really need help!

> Reply from Vosvoy
>
> Tartarus wrote:I tried your method and it works great, finally got the audio for all the characters! One issue though is that the audio seems slightly higher pitched than it's supposed to be. Is there any fix for that or is it unavoidable?

Yeah, I think that's because some sounds have a lower sampling rate (44100Hz? 32000Hz? I can't tell) while the tool convert those as 48000Hz by default. You can simply switch the sampling rate via Audacity.

If you want to directly convert those sounds with a 44100Hz sampling rate, just change the addheader_mono.bms to:
Code: Select allset MEMORY_FILE binary "\x52\x49\x46\x46\xb8\x59\xa7\x00\x57\x41\x56\x45\x66\x6d\x74\x20\x20\x00\x00\x00\x65\x01\x10\x00\xd6\x10\x00\x00\x01\x00\x00\x03\xe3\x9a\x00\x00\x44\xac\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x02\x00\x64\x61\x74\x61\x00\x58\xa7\x00"

get NAME basename
get SIZE asize
string NAME += ".xma"

append
log MEMORY_FILE 0 SIZE
append
math SIZE += 60
log NAME 0 SIZE MEMORY_FILE
Just use this modified script for those (voice?) sounds because the majority of the sounds of The Evil Within have a 48000Hz sampling rate.
Thanks man, works like a charm
