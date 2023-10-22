## Post #1
- Username: Josepsh
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Apr 15, 2012 2:02 am
- Post datetime: 2012-04-14T18:08:10+00:00
- Post Title: Metal Gear Solid 3 Snake Eater Audio.

Trying To Rip Metal Gear Solid 3 Snake Eater Audio,Trying To Get The Version Of Snake Eater That Plays When You Have 3 More Left To Kill The Boss.
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2012-04-14T19:34:30+00:00
- Post Title: Metal Gear Solid 3 Snake Eater Audio.

I haven't played the game so I'm not sure what track that is, but it's probably one of the ones in BGM.DAT.  Use demux_dat ([http://hcs64.com/files/demux_dat_02.zip](http://hcs64.com/files/demux_dat_02.zip)) to extract the .mtaf files from BGM.DAT, run:
```
demux_dat BGM.DAT
```
VOX.DAT and MOVIE.DAT also have some audio, so you can check those too if you don't find it in BGM.  You can then use vgmstream ([http://hcs64.com/vgmstream.html](http://hcs64.com/vgmstream.html)) to decode those to .wav (with test.exe) or play them directly in Winamp.  The MGS3 mtaf files tend to have more than 2 channels, each pair of two being a particular variation, so you may want to decode to .wav and then open the file with an audio editor like audacity to find what channels you want.
## Post #3
- Username: Josepsh
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Apr 15, 2012 2:02 am
- Post datetime: 2012-04-16T02:30:13+00:00
- Post Title: Metal Gear Solid 3 Snake Eater Audio.

How Do I Decode To Wav?
## Post #4
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2012-04-16T04:02:34+00:00
- Post Title: Metal Gear Solid 3 Snake Eater Audio.

Did you get as far as extracting the .mtaf files?

If not, I think you should be able to just drop a .DAT file onto demux_dat.exe (after you extract it from the .zip).

If you have the .mtaf files:

1. Get vgmstream: [http://hcs64.com/files/vgmstream/vgmstr ... 5-test.zip](http://hcs64.com/files/vgmstream/vgmstream-r975-test.zip)
2. Unzip the test.exe into some directory
3. Get the external dlls: [http://hcs64.com/files/vgmstream_external_dlls.zip](http://hcs64.com/files/vgmstream_external_dlls.zip)
4. Unzip the .dll files into the same directory as test.exe
5. Create a file text file in Notepad (not Wordpad or Word unless you save as plain text) with the following:

```
:getfile
if "%~1"=="" goto end
test.exe "%~1" -o "%~dp1\%~n1.wav"
shift
goto getfile
:end
```

Save it as test.bat
6. Drag 'n drop .mtaf files onto test.bat and it should decode to .wav.

If you're having trouble, remember to explain clearly what you've tried to do already.  I've written way too much on this already but I happened to be in the right mood.
