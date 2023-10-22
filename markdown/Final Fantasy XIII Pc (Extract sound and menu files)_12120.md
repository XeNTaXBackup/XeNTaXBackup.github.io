## Post #1
- Username: akafa123
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Oct 16, 2014 12:19 am
- Post datetime: 2014-10-15T16:21:17+00:00
- Post Title: Final Fantasy XIII Pc (Extract sound and menu files)

I guess they are stored in sys folder, but files don't have headers at all, is there anyway to extract sound files and menu elements? I tried ps3 script, but no luck!
## Post #2
- Username: akafa123
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Oct 16, 2014 12:19 am
- Post datetime: 2014-10-16T09:31:45+00:00
- Post Title: Final Fantasy XIII Pc (Extract sound and menu files)

I managed to extract all files
And I know how to convert scd audio files to wav, but I can do it only for 1 file not multiple ones. Is there any way to convert all audio files just using one script?
## Post #3
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2014-10-17T10:48:54+00:00
- Post Title: Final Fantasy XIII Pc (Extract sound and menu files)

what are you using to convert them into WAV?
## Post #4
- Username: akafa123
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Oct 16, 2014 12:19 am
- Post datetime: 2014-10-17T13:52:53+00:00
- Post Title: Final Fantasy XIII Pc (Extract sound and menu files)

> Reply from brendan19
>
> what are you using to convert them into WAV?
Oh I found a way to play them throught foobar2000, just download it and download this component 
[http://www.foobar2000.org/components/vi ... _vgmstream](http://www.foobar2000.org/components/view/foo_input_vgmstream) (double click, apply)
Then just play all files from sound/pack in foobar

But I sitll don't know where all menu stuff is, I found fonts and background animations when you click Status in game, but there must be anything else...
## Post #5
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2014-10-17T16:02:50+00:00
- Post Title: Final Fantasy XIII Pc (Extract sound and menu files)

1. Download vgmstream and its external DLL libraries from HCS here.
[vgmstream](http://hcs64.com/files/vgmstream/)
[vgmstream external dll](http://hcs64.com/files/vgmstream_external_dlls.zip)

2. Extract them both into the same folder.

3. Save the following into notepad with the extension .bat in the same folder with the test.exe

```
FOR %%a IN (*.scd) DO test -l 2 -f 10 -o "%%a.wav" "%%a"
```


4. Run the batch file and it will convert them for you
## Post #6
- Username: akafa123
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Oct 16, 2014 12:19 am
- Post datetime: 2014-10-18T08:21:58+00:00
- Post Title: Final Fantasy XIII Pc (Extract sound and menu files)

> Reply from brendan19
>
> 1. Download vgmstream and its external DLL libraries from HCS here.
vgmstream
vgmstream external dll

2. Extract them both into the same folder.

3. Save the following into notepad with the extension .bat in the same folder with the test.exe
Code: Select allFOR %%a IN (*.scd) DO test -l 2 -f 10 -o "%%a.wav" "%%a"

4. Run the batch file and it will convert them for you

Wow! Thanks a lot! You are the best!
## Post #7
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2018-08-04T16:14:59+00:00
- Post Title: Final Fantasy XIII Pc (Extract sound and menu files)

For some reason, very few of these are able to be played in Foobar, even with the vgmstream codec. Hardly any of them work from what I got. I plan to rip the SFX and English voices, but anyway, here's an example: [https://drive.google.com/open?id=1Vs8f0a...gg2uINLDeU](https://drive.google.com/open?id=1Vs8f0a...gg2uINLDeU)

So, can you help me?
