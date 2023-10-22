## Post #1
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-01-28T18:12:07+00:00
- Post Title: DMC Devi May Cry

hi all 

extract audio easy with umodel 
but revorb crash 
someone get solution 
if can be nice
thank's
## Post #2
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-01-28T20:30:25+00:00
- Post Title: DMC Devi May Cry

> Reply from kilik
>
> hi all 

extract audio easy with umodel 
but revorb crash 
someone get solution 
if can be nice
thank's

normally that means you used the wrong codebooks file.
## Post #3
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-01-29T10:07:03+00:00
- Post Title: DMC Devi May Cry

Yes it's look is that so i have retry with full setup and more but i have no find the way at this time 
he exist another codecs ?
## Post #4
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-01-31T14:08:46+00:00
- Post Title: DMC Devi May Cry

hmm, maybe there's a new third set of codebooks used we don't have yet?
## Post #5
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-02-02T12:57:59+00:00
- Post Title: DMC Devi May Cry

it's one possibility driver san fransico do the same thinks
## Post #6
- Username: !!!!!
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 22, 2009 8:55 am
- Post datetime: 2013-02-04T17:09:20+00:00
- Post Title: DMC Devi May Cry

Which version of the game are you extracting from?
## Post #7
- Username: !!!!!
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 22, 2009 8:55 am
- Post datetime: 2013-02-04T19:41:08+00:00
- Post Title: DMC Devi May Cry

For the PC Version, use [AlphaTwentyThree's wavscanner.bms script](http://forum.xentax.com/viewtopic.php?f=13&p=74664#p74664) to extract .wavs from the PC_Xenon.apk. Then use [ww2ogg](http://hcs64.com/files/ww2ogg019.zip) using the "packed_codebooks_aoTuV_603.bin" method on the .wavs to extract the .oggs. Finally [revorb](http://www.hydrogenaudio.org/forums/lofiversion/index.php/t64328.html) to render the .oggs playable. 

For the 360 Version, use [AlphaTwentyThree's wavscanner.bms script](http://forum.xentax.com/viewtopic.php?f=13&p=74664#p74664) to extract .wavs from the Main_Xenon.apk to extract .wavs. And then use [AlphaTwentyThree's XMA Transform .bms script](http://forum.xentax.com/viewtopic.php?f=17&t=9023) to extract the .xmas from the wavs. Towav should do the rest.

Give this post a thanks if you found it useful if you would be so kind.
## Post #8
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-02-05T22:25:37+00:00
- Post Title: DMC Devi May Cry

Very nice work's !! it's make me happy thank's !!
## Post #9
- Username: kangmin
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Jun 17, 2012 4:38 pm
- Post datetime: 2013-02-17T08:35:24+00:00
- Post Title: DMC Devi May Cry

Kilik how did you do it? can u give me a step by step? managed to extarct the wav but it doesnt play anithing at all

For the PC Version, use AlphaTwentyThree's wavscanner.bms script to extract .wavs from the PC_Xenon.apk. Then use ww2ogg using the "packed_codebooks_aoTuV_603.bin" method on the .wavs to extract the .oggs. Finally revorb to render the .oggs playable. 


pls explain more specifically .. i'm really confused  DmC 5
## Post #10
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2013-02-23T09:54:35+00:00
- Post Title: DMC Devi May Cry

I actually have some problems as well. I was able to extract the .ogg file from the .wav, but when I drag it on revorb nothing happens. If I try to open the .ogg file again, on Win Vista I just got an impossible to play file, on Win 7 Media Player crushes. Am I doing something wrong?

What's the meaning of "Then use ww2ogg using the "packed_codebooks_aoTuV_603.bin" method"?

EDIT: My mistake, I had to do everything from the prompt command, now it worked! But I have a question: is there a way to batch every file? It's quite painful doing it for every single file...
## Post #11
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-02-23T12:21:30+00:00
- Post Title: DMC Devi May Cry

how you extract file 

for %%i In (*.ogg) do revorb.exe %%i
## Post #12
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2013-02-23T13:46:11+00:00
- Post Title: DMC Devi May Cry

> Reply from kilik
>
> how you extract file 

for %%i In (*.ogg) do revorb.exe %%i

I open prompt command and write ww2ogg --pcb packed_codebooks_aoTuV_603.bin filename.wav, then write revorb filename.ogg and perfectly works for me. Of course you have to specify the directory.

Anyway, looking forward for a batch system that will allow me to directly extract all the files without doing it manually for 200000 objects.
## Post #13
- Username: !!!!!
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 22, 2009 8:55 am
- Post datetime: 2013-02-26T16:09:20+00:00
- Post Title: DMC Devi May Cry

> Reply from RunaWhite
>
> kilik wrote:how you extract file 

for %%i In (*.ogg) do revorb.exe %%i

I open prompt command and write ww2ogg --pcb packed_codebooks_aoTuV_603.bin filename.wav, then write revorb filename.ogg and perfectly works for me. Of course you have to specify the directory.

Anyway, looking forward for a batch system that will allow me to directly extract all the files without doing it manually for 200000 objects.

Open notepad, paste (for %%a in (*.WAV) do ww2ogg.exe "%%a") without the parentheses, save as ww2ogg.bat in the same folder with ww2ogg and you should be good.
## Post #14
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2013-02-27T15:02:17+00:00
- Post Title: DMC Devi May Cry

> Reply from !!!!!
>
> RunaWhite wrote:kilik wrote:how you extract file 

for %%i In (*.ogg) do revorb.exe %%i

I open prompt command and write ww2ogg --pcb packed_codebooks_aoTuV_603.bin filename.wav, then write revorb filename.ogg and perfectly works for me. Of course you have to specify the directory.

Anyway, looking forward for a batch system that will allow me to directly extract all the files without doing it manually for 200000 objects.

Open notepad, paste (for %%a in (*.OGG) do ww2ogg.exe "%%a") without the parentheses, save as ww2ogg.bat in the same folder with ww2ogg and you should be good.

Thanks, just one thing... what should I write then in the prompt command? Also... do this work for .wav to .ogg files only? This means that I would need to use revorb for any single file anyway...
## Post #15
- Username: !!!!!
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 22, 2009 8:55 am
- Post datetime: 2013-03-06T13:21:28+00:00
- Post Title: DMC Devi May Cry

> Reply from RunaWhite
>
> !!!!! wrote:I open prompt command and write ww2ogg --pcb packed_codebooks_aoTuV_603.bin filename.wav, then write revorb filename.ogg and perfectly works for me. Of course you have to specify the directory.

Anyway, looking forward for a batch system that will allow me to directly extract all the files without doing it manually for 200000 objects.

Open notepad, paste (for %%a in (*.OGG) do ww2ogg.exe "%%a") without the parentheses, save as ww2ogg.bat in the same folder with ww2ogg and you should be good.

Thanks, just one thing... what should I write then in the prompt command? Also... do this work for .wav to .ogg files only? This means that I would need to use revorb for any single file anyway...[/quote]

I screwed up, here's the correction > (for %%a in (*.WAV) do ww2ogg.exe "%%a") Just click the .bat and it should batch convert all of the .wavs in the same folder as it and the application. If you want to use it on any other file format to extract any possible oggs from within, just open the bat in notepad and change .WAV to whatever extension you are trying to convert.
## Post #16
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2013-04-24T11:59:27+00:00
- Post Title: Re: DMC Devi May Cry

Sorry for the late reply and thanks! The batch works for the .WAV files, but I have to convert the obtained .ogg files with revorb since they don't work properly. What kind of format should I write? If I change .WAV in .OGG nothing happens. If I use this ( for %%i In (*.ogg) do revorb.exe %%i ) it crashes...

EDIT: Noticed that if I convert both .wav and .ogg manually in the prompt command everything works fine. The .bat file creates corrupted files...
## Post #17
- Username: !!!!!
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 22, 2009 8:55 am
- Post datetime: 2013-04-24T14:53:40+00:00
- Post Title: Re: DMC Devi May Cry

> Reply from RunaWhite
>
> Sorry for the late reply and thanks! The batch works for the .WAV files, but I have to convert the obtained .ogg files with revorb since they don't work properly. What kind of format should I write? If I change .WAV in .OGG nothing happens. If I use this ( for %%a in (*.OGG) do revorb.exe %%a ) it crashes...

EDIT: Noticed that if I convert both .wav and .ogg manually in the prompt command everything works fine. The .bat file creates corrupted files...

Edit the .bat, and replace that command with this: (no parenthesis)

```
for %%a in (*.OGG) do revorb.exe "%%a"
```
## Post #18
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2013-04-24T17:19:16+00:00
- Post Title: Re: DMC Devi May Cry

Actually I removed the parenthesis already... :\ but the problem is the .wav batch I think. It just converts very wrong .ogg files that make the prompt crash when I try to decompress them with revorb.
## Post #19
- Username: !!!!!
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 22, 2009 8:55 am
- Post datetime: 2013-04-24T20:56:04+00:00
- Post Title: Re: DMC Devi May Cry

> Reply from RunaWhite
>
> Actually I removed the parenthesis already... :\ but the problem is the .wav batch I think. It just converts very wrong .ogg files that make the prompt crash when I try to decompress them with revorb.

The correct command has quotes in it. Different from the one you posted.
## Post #20
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2013-04-26T00:14:27+00:00
- Post Title: Re: DMC Devi May Cry

Even this new one crashes. Normal command line crashes as well, means the .ogg created with the .wav batch are corrupted.
## Post #21
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2013-04-26T05:11:13+00:00
- Post Title: Re: DMC Devi May Cry

> Reply from RunaWhite
>
> Even this new one crashes. Normal command line crashes as well, means the .ogg created with the .wav batch are corrupted.

Use this :

```
SET outputOGGfolder=C:\Users\xxx\Desktop\Game Edit\DMC Devil May Cry\sound
SET ww2oggFolder=C:\Users\xxx\Desktop\Game Edit\DMC Devil May Cry\sound
SET packedCodebook=C:\Users\xxx\Desktop\Game Edit\DMC Devil May Cry\sound\packed_codebooks_aoTuV_603.bin
SET revorbFolder=C:\Users\xxx\Desktop\Game Edit\DMC Devil May Cry\sound

for %%a in ("%inputWAVfolder%\*.wav") do "%ww2oggFolder%\ww2ogg" "%%a" --pcb "%packedCodebook%"
for %%a in ("%inputOGGfolder%\*.ogg") do move "%%a" "%outputOGGfolder%"
for %%G in ("%outputOGGfolder%\*.ogg") do "%revorbFolder%\revorb" "%%G"
```


remember to set your own path and use the new codebook.
## Post #22
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2013-04-26T08:36:35+00:00
- Post Title: Re: DMC Devi May Cry

Thanks, I'll try. But what do you mean with "use the new codebook"?

EDIT: Nevermind, it seems to work. Now the revorb .bat doesn't crash the command line anymore, thank you so much!
