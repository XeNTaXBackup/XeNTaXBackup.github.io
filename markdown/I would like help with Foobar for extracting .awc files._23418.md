## Post #1
- Username: TheOnlyRobert
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Feb 08, 2021 7:01 pm
- Post datetime: 2021-02-08T11:13:54+00:00
- Post Title: I would like help with Foobar for extracting .awc files.

Hello guys.

I really like Red Dead Redemption 1's soundtrack, and I would like to extract the audio files the same way you can in OpenIV for other Rockstar titles. The problem is, OpenIV doesn't support RDR1.

From there, I found a video that contained all of John Marston's lines. I looked through the comments for a potential explanation, and I found that he used Foobar2000 and the help of you guys to make it possible.

I downloaded the program and installed the vgm plugin that lets me convert the .awc file into a .wav file. The problem is, the awc contains multiple layers of audio that through this conversion method, it puts together, which I would not like. I would like it to be separated. I looked through the forums here, and found this command written by "bnmm" that, by my understanding, could do what I want it to do:

```
set MAX=%2

for /L %%A in (1,1,%MAX%) do (
  test.exe -s %%A -o %FILE%_%%A.wav %FILE%
)
```


And right now I'm stuck, because I do not know and I could not find a way to put commands into Foobar, or the plugin, or wherever it needs to be put.

I think I would be content for a while if anyone could help me with this. Thank you in advance.
## Post #2
- Username: QuasiDetective
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 06, 2019 11:01 am
- Post datetime: 2021-02-08T18:24:35+00:00
- Post Title: I would like help with Foobar for extracting .awc files.

Could you post a sample AWC file and a link to the forum thread you found that command on? It looks to me like a batch script, which calls for "test.exe", which may have been a program made explicitly for this purpose -- the command will do you no good without that program (unless I'm completely wrong on what it is).
## Post #3
- Username: TheOnlyRobert
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Feb 08, 2021 7:01 pm
- Post datetime: 2021-02-08T19:10:28+00:00
- Post Title: I would like help with Foobar for extracting .awc files.

> Reply from QuasiDetective ↑Tue Feb 09, 2021 2:24 am at Tue Feb 09, 2021 2:24 am
>
> 
Could you post a sample AWC file and a link to the forum thread you found that command on? It looks to me like a batch script, which calls for "test.exe", which may have been a program made explicitly for this purpose -- the command will do you no good without that program (unless I'm completely wrong on what it is).

I'm happy that you answered, I think I'll thank you for that. 

I'll upload the .awc file on Mega.
[https://mega.nz/file/3QFw2Jia#oUO3ujyUb ... UoJ8NVoM_8](https://mega.nz/file/3QFw2Jia#oUO3ujyUb0TFwfv974kNq9SjAzXEuTJmXUoJ8NVoM_8)

This is the link for the forum thread I found the code on:
[viewtopic.php?f=17&t=19670&p=149977&hilit=awc#p149977](https://forum.xentax.com/viewtopic.php?f=17&t=19670&p=149977&hilit=awc#p149977)
## Post #4
- Username: QuasiDetective
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 06, 2019 11:01 am
- Post datetime: 2021-02-08T22:11:25+00:00
- Post Title: I would like help with Foobar for extracting .awc files.

Okay, I think I've come up with a solution that appears to work, though it's a bit clunky.

First of all, you're going on want to download the vgmstream build linked in that thread. Download the one that includes command-line tools here: [https://vgmstream.org/downloads](https://vgmstream.org/downloads)
This includes "test.exe".

It appears that these files do not need the full "all channel" thing used in the batch script to work, as test.exe appears to generate a WAV file with every subsong on its own channel. This means that the output files are seemingly very big. (The file you gave me alone comes out to 261mb, with 16 channels.) So, please keep that in mind before using this tool in bulk.

I have created a very lightly modified version of bnnm's batch script that appears to work, more or less. You can drag and drop an AWC file onto it, and it will generate the full multi-channel WAV file in the same folder.
Where you see...

```
[path to test.exe]
```

... put the full path to where you put vgmstream's files and test.exe (without the brackets, and with quotations). For example:

```
"C:\Users\Your Username Here\Desktop\Programs\vgmstream\test.exe"
```


Here is the modified batch file. Copy this text and save it wherever you like on your PC (remember to replace "[path to test.exe]"), but make sure it saves as a .bat file. Then, as said, you can simply drag and drop an AWC file onto it, and then it should extract a multi-channeled WAV file that you should be able to open in Audacity.

```
set MAX=1

for /L %%A in (1,1,%MAX%) do (
  [path to test.exe] -s %%A -o %FILE%_%%A.wav %FILE%
)

pause
```


I'm not very familiar with vgmstream's test.exe, so I'm unsure if there's a way to make the process easier by making the separate channels export as individual WAV files. It seems like that's what it's supposed to do, but it doesn't for some reason... I had to set the max number of subtracks it exports to 1 because it was just outputting the same 261mb/16 channel file over and over again.
But each separate channel in the "single subtrack" 261mb output still seems to load fine into Audacity (albeit with a bit of lag); with it, you can then remove all the channels you don't want and re-save the lone remaining subtrack channel as a separate file. Though, you'd have to do this for every channel manually...
(Though, keep in mind that some of them appear to be stereo. There are "Left", "Right", and "Mono" channels inside, so the "Left" and "Right" ones should no doubt be exported together into single stereo WAV files/whatever format you decide to export them into if you use this method. )

Perhaps someone else can come along and find a way to automate the whole "separating each channel into its own file" thing, but I hope this helps in the meantime.
## Post #5
- Username: TheOnlyRobert
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Feb 08, 2021 7:01 pm
- Post datetime: 2021-02-09T14:18:52+00:00
- Post Title: I would like help with Foobar for extracting .awc files.

Through following your steps, I got it to work, thank you for your that. I extracted the .wav file and opened it in Audacity, and it seems to have given me what I would like.

Though, I'm afraid I might seem ungrateful by asking for this, but I'd like to know more about this program, so I can potentially find a solution to my next problem.

I noticed this weird kind of lag that is present in the tracks that are exported. On the thread I linked previously, it seems to me that they mention this interaction between vgmstream and specifically Xbox 360 audio, that in this interaction the exported audio can have lag in it. Therefore, I fear that I can't do anything about that, but I think I could be wrong. Do you know if there's anything I can do about that?

Also, could you explain to me what the code in the .bat file actually does, line to line? I'm interested as to how it works.
## Post #6
- Username: QuasiDetective
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 06, 2019 11:01 am
- Post datetime: 2021-02-09T15:56:48+00:00
- Post Title: I would like help with Foobar for extracting .awc files.

Are you talking about how it lags Audacity/Foobar and takes forever to actually start playing? Because, if so, I'm having that issue too. However, I believe I have solved it and also came up with a way to separate each subchannel! Be warned that this program has a weird quirk that really bugs me, though, so it's not very pretty.

First of all, make a new batch file. This one here scans the file for its metadata so you can see the number of channels it has, then prints instructions to the console window.

```

[path to test.exe] -m %FILE%

echo "Find value 'channels:' above and set MAX in the main batch file to (number of channels - 1). Ex. If there are 16 channels, set MAX = 15. Otherwise, the program will simply start over when it reaches the end of the channels!"
pause
```


Unfortunately, you have to set the maximum value of channels the program exports manually, otherwise it simply restarts. For example, with the track you gave me, I set total channels to 18 to see if it would stop (keep in mind there are 16 channels, so it should've stopped at 15 (16 - 1, because channel 1 is at position 0 -- kind of confusing, I know)), but sure enough, it went all the way to 18. 16 was a copy of 0. FML.   

Here is the modified batch script that exports each subchannel. These resulting wav files seem to playback just fine in Audacity, with no lag. You can replace the old one with this.

```
set /p MAX="Number of channels?: "

[path to test.exe] -2 0 -o %FILE%_0.wav %FILE%

for /L %%A in (1,1,%MAX%) do (
  [path to test.exe] -2 %%A -o %FILE%_%%A.wav %FILE%
)
pause
```


... And here's an explanation of what (I believe) it does, line by line.   

```
set FILE=%1
```

Sets "FILE" to the full path to the file drag-and-dropped onto the batch script.

```
set /p MAX="Number of channels?: "
```

Sets the maximum number of channels to export to a number. Must be an integer. This is requested to be input by the user in the console window as it's running. For the example AWC file given (nrt_song_06), input 15 (because the file has 16 channels).

```
[path to test.exe] -2 0 -o %FILE%_0.wav %FILE%
```

Runs test.exe with flag -2 (get channel number (for stereo channel; it looks like they're all actually stereo tracks, not mono!), in this case we're getting channel 0), and flag -o to output [original filepath]_0.wav, reading from [original file path]. This has to be done to get channel 0, because I can't find a reliable method to make the following for loop do it without getting caught in an infinite loop.

```
for /L %%A in (1,1,%MAX%) do (
```

Runs the following command on each channel until we reach the maximum number of channels, input earlier.

```
[path to test.exe] -2 %%A -o %FILE%_%%A.wav %FILE%
```

Same as before, but this time we set the channel number to the number we're currently on, until we reach the end of this for loop (until we run out of channels).

```
)
```

Marks the end of the for loop's actions, which began with "do (". Kind of self-explanatory, lol

```
pause
```

Brings up the "Press any key to continue..."; simply stops the program from instantly exiting. You can remove this if you don't want to have to press a key every time it finishes just to close it.

I hope this helps! Sorry there isn't an easier way to do it without having to manually input how many channels there are, but I suppose having to do that is infinitely less time consuming than having to manually export every individual channel with Audacity, especially when apparently some of these files can get up to, like, 200 channels or something.  

EDIT: Okay, actually, I listened to the track output on channel 3 (or 2 in this case) and I think I get what you mean now. The left channel for this one is like... stuttering at the start and lagging behind? (The right channel does it later on in the song, too...)
I have no idea what's causing that. (I believe it might have something to do with how test.exe is processing the file, as it seems to stutter differently each time it gets exported...) I'm afraid I don't know how to help other than by suggesting you split the two channels into mono, try to manually edit the laggy bits back to normal, and correct them manually.   
I hope this modified batch script helps at least in some way. I'll see if I can figure out a way to get it to stop stuttering, but I don't think there's anything that can be done about that, unfortunately...
