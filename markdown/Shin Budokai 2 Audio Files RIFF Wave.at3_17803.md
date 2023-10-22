## Post #1
- Username: iPocalypSe
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 03, 2018 2:08 am
- Post datetime: 2018-03-10T14:43:09+00:00
- Post Title: Shin Budokai 2 Audio Files RIFF Wave/.at3

Regards   

I found some files using the extension .at3 and in hex editor it says RIFF but i cant hear it, maybe the audio is compressed? 
If somebody can help me please i will thank you very much   


These are the files

Link: [http://www.mediafire.com/file/scwkitr5r ... _Files.rar](http://www.mediafire.com/file/scwkitr5rizncj7/Audio_Files.rar)


Thanks
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2018-03-10T22:55:16+00:00
- Post Title: Shin Budokai 2 Audio Files RIFF Wave/.at3

These audio files are encoded in Sony's proprietary codec ATRAC-3.

Get [vgmstream](https://github.com/bnnm/vgmstream-builds/blob/master/bin/vgmstream-latest-test-u.zip) and you can use the plugin to play it back natively using Winamp or you can use the test.exe to convert it into PCM WAV with the following batch script by saving it into notepad and giving it the extension .bat

```
pause
```

-l = number of loops
-f = fade out over number of seconds
-o = output filename
## Post #3
- Username: iPocalypSe
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 03, 2018 2:08 am
- Post datetime: 2018-03-11T18:27:45+00:00
- Post Title: Shin Budokai 2 Audio Files RIFF Wave/.at3

> Reply from brendan19
>
> These audio files are encoded in Sony's proprietary codec ATRAC-3.

Get vgmstream and you can use the plugin to play it back natively using Winamp or you can use the test.exe to convert it into PCM WAV with the following batch script by saving it into notepad and giving it the extension .bat
Code: Select allFOR %%a IN (*.at3) DO test -l 2 -f 10 -o "%%a.wav" "%%a"
pause
-l = number of loops
-f = fade out over number of seconds
-o = output filename

Thank you very much  it works perfectly in the most audios of game but i have another audios that it doesn't says nothing in hex editor, it not says RIFF or Wave, doesn't says nothing, i can see that are similars to the others audios but the difference is that not says nothing at the start 

Is possible add the first offsets (RIFF WAVE fmt) to the audio that not have nothing at the start?

here is one example of the strange audio

Link: [http://www.mediafire.com/file/ct4ti82gy ... o+test.rar](http://www.mediafire.com/file/ct4ti82gy8tmnhc/Audio+test.rar)

Thanks
