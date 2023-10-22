## Post #1
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-18T16:53:07+00:00
- Post Title: psp riff wav

hey guys im having a problem converting theses files to normal wav files WRS helped me extract them from the .bin
iv tried  ww2ogg that didn't work and towav didn't ether i got the .vag files to work but for some reason .wav's  are harder if anyone knows how to fix this that would be nice

here are some wav files from that .bin file
[http://www.sendspace.com/file/sh9jsc](http://www.sendspace.com/file/sh9jsc)
## Post #2
- Username: snakemeat
- Rank: advanced
- Number of posts: 45
- Joined date: Wed Jan 28, 2009 12:00 am
- Post datetime: 2012-08-18T17:09:51+00:00
- Post Title: psp riff wav

They are either ATRAC3 or ATRAC3plus.  If ATRAC3, you need the ATRAC3 codec.  If ATRAC3plus, you need to install SonicStage and HiMDRenderer.  Although they have the same header as WAV files, they are actually .at3 files.

There are probably walkthroughs on both of those tasks on the web.  Good luck!
## Post #3
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-18T19:07:29+00:00
- Post Title: psp riff wav

> Reply from snakemeat
>
> They are either ATRAC3 or ATRAC3plus.  If ATRAC3, you need the ATRAC3 codec.  If ATRAC3plus, you need to install SonicStage and HiMDRenderer.  Although they have the same header as WAV files, they are actually .at3 files.

There are probably walkthroughs on both of those tasks on the web.  Good luck!

tryed all that and it didnt work i found guides and still nothing all coverters give errors
## Post #4
- Username: mauzerX
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jul 01, 2010 8:48 pm
- Post datetime: 2012-08-21T20:09:22+00:00
- Post Title: psp riff wav

U can use QuickBMS with [AT3 to AA3 converter script](http://forum.xentax.com/viewtopic.php?f=13&p=42443#p42443) to add valid header, than convert with Sound Forge 10.
## Post #5
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-21T22:17:45+00:00
- Post Title: psp riff wav

> Reply from mauzerX
>
> U can use QuickBMS with AT3 to AA3 converter script to add valid header, than convert with Sound Forge 10.

thank you soo much mauzerX now this is going to take long lol i have 7000 of them to go
## Post #6
- Username: mauzerX
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jul 01, 2010 8:48 pm
- Post datetime: 2012-08-22T20:24:28+00:00
- Post Title: psp riff wav

I don't see any problem  , just use batch:
for quickbms

```
for %%i in (*.wav) DO quickbms.exe -o AT3toAA3.bms "%%i" "%CD%"
```

for Sound Forge
GoTo tools --> batch converter
## Post #7
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-23T12:37:10+00:00
- Post Title: psp riff wav

> Reply from mauzerX
>
> I don't see any problem  , just use batch:
for quickbms
Code: Select allfor %%i in (*.wav) DO quickbms.exe -o AT3toAA3.bms "%%i" "%CD%"
for Sound Forge
GoTo tools --> batch converterthank you soo much that will make this 1000 times easier
now im going to look on here how to make the new waves into xma back to xwb's
