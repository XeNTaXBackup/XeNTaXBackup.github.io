## Post #1
- Username: PopSndExt
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jul 13, 2021 5:04 am
- Post datetime: 2021-07-12T21:11:29+00:00
- Post Title: How do I extract Prince of Persia Warrior Within audio files?

Hi!

I remember that when I was still child I had some kind of program that extracted music files and audio files from Prince Of Persia Warrior Within. I cant find it anywhere anymore. Is there still such program available somewhere or is POP WW so old game that  this tool is permanently gone now? Or any suggestions what keywords to google for? I have tried everything that has came to my mind.

PS I know that music tracks are already available on youtube. I am not looking for these.


Thanks in advance.
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-12T21:57:40+00:00
- Post Title: How do I extract Prince of Persia Warrior Within audio files?

Check those links:

[https://web.archive.org/web/20100502061 ... rfster.be/](https://web.archive.org/web/20100502061619/http://prince.turfster.be/)
[viewtopic.php?t=1618](https://forum.xentax.com/viewtopic.php?t=1618)
[viewtopic.php?t=1620](https://forum.xentax.com/viewtopic.php?t=1620)
[http://wiki.xentax.com/index.php?search ... arch&go=Go](http://wiki.xentax.com/index.php?search=sb0&title=Special%3ASearch&go=Go)
[viewtopic.php?f=17&t=3156](https://forum.xentax.com/viewtopic.php?f=17&t=3156)
## Post #3
- Username: PopSndExt
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jul 13, 2021 5:04 am
- Post datetime: 2021-07-12T23:51:28+00:00
- Post Title: How do I extract Prince of Persia Warrior Within audio files?

This first tool gives me couple of  sb0 files which I dont know how to open and then one ss0 file which I dont know how to open.

Linked tool: [viewtopic.php?t=1618](https://forum.xentax.com/viewtopic.php?t=1618) but it does not seem to work.

```

PoPSoT FAT dumper v0.1 25-may-2k4 ■ by VAG, ARR. ■ vagsoft@mail.ru
....................................................................................................................................................
PoP:T2T Sound Decoder v0.7b 21-dec-2k5 ■ by VAG, ARR. ■ vagsoft@mail.ru
--- !poptemp\000.sb0 -
Something is really wrong. Check the files and try again.


Seems like we are done. Check the "!audio" folder for the results.
Note: To get the credits song, use RAD Video Tools.
Press any key to continue . . .

```


This [viewtopic.php?f=17&t=3156](https://forum.xentax.com/viewtopic.php?f=17&t=3156) seems to be working with ss0 file but it looks like some sounds are still missing. I think those are sb0 files? Any hints on them?

One example is (had to zip it to be able to upload):


 menu1.zip
(188.45 KiB) Downloaded 14 times



Update: When I try to use sb0dump2.exe manually I get:

```
PoP:WW Sound Decoder v0.5b 7-dec-2k4 ■ by VAG, ARR. ■ vagsoft@mail.ru
--- C:\projektid\Sound\sound\english\pirate3.sb0 - Bad sb0 file
```
## Post #4
- Username: PopSndExt
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jul 13, 2021 5:04 am
- Post datetime: 2021-07-13T10:32:00+00:00
- Post Title: How do I extract Prince of Persia Warrior Within audio files?

I tried with game console ISO image. I got sb1 files from there instead of sb0 files. Any idea what these might be?
## Post #5
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-07-13T11:24:50+00:00
- Post Title: How do I extract Prince of Persia Warrior Within audio files?

> Reply from PopSndExt ↑Tue Jul 13, 2021 7:51 am at Tue Jul 13, 2021 7:51 am
>
> 
One example is (had to zip it to be able to upload):
menu1.zip

Your menu1 example plays fine in Foobar with the vgmstream plugin, so give that a go.  It's much easier than using command line tools.
## Post #6
- Username: PopSndExt
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jul 13, 2021 5:04 am
- Post datetime: 2021-07-13T13:15:36+00:00
- Post Title: How do I extract Prince of Persia Warrior Within audio files?

I made discovery that his post that is for POP 3D still works for POP SOT and WW. T2T is not tested but I suspect it might work:

[https://forum.princed.org/viewtopic.php?p=18578#p18578](https://forum.princed.org/viewtopic.php?p=18578#p18578)

Just copy paste in case other site ever happens to shut down or something:

> Reply from David From forum.princed.org
>
> You can also use Audacity's File -> Import -> Raw Data.
Use these settings:
Code: Select allEncoding: Signed 16 bit PCM
Byte order: Little-endian
Channels: 1 Channel (Mono) (or sometimes Stereo)
Start offset: 32 bytes for *.sfx files, 0 bytes for *.data files
Amount to import: 100%
Sample rate: 22050 Hz

Now I just have to figure out how to do these steps in ffmpeg to bulk convert them to wav files

Update:  for bulk conversion you can save this code as bat file in directory of your sb0 files and then run it from cmd:

```
FOR %%a IN (*.sb0) DO ffmpeg -f s16le -ar 22050 -ac 1 -i %%a %%a.wav
```


If anyone knows how ow to use ffmpeg alone to iterate files would be even better.

Update2: Made fun discovery that one audio file contains multiple sound effects, separated by silence.

Update 3: I discovered that someone had already done this all and uploaded to internet:
[https://www.sounds-resource.com/pc_comp ... ndsoftime/](https://www.sounds-resource.com/pc_computer/princeofpersiathesandsoftime/)
