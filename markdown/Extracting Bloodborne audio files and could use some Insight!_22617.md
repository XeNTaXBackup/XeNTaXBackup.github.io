## Post #1
- Username: Rozekail
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Dec 01, 2017 7:55 am
- Post datetime: 2020-08-29T13:11:30+00:00
- Post Title: Extracting Bloodborne audio files and could use some Insight!

As the title says, I'm currently going through and extracting all of the audio from Bloodborne's Game of the Year disc. However, I've run into two snags. The first of which being that I have a batch file which automates extracting .wav from the .at9 files, and then .mp3 from .wav, if I so choose. However, in order to get to the .at9 files, I have to run each .fsb by dragging it onto getfsb.exe. I'd like to implement getfsb.exe into this batch file so that I can simply run it and take the file all the way from .fsb>.at9>.wav in one sweep. My issue is that I can get it to run getfsb.exe, but it seems to be waiting for some other input, as it doesn't extract anything, just opens the command prompt and lists some info about getfsb.exe, never progressing. Now normally, you can't run getfsb.exe without dragging a .fsb file onto it, so I'm guessing that interaction is somehow neessary, but I have no idea how you'd script that interaction in a batch file. I'll post the script below in case it's an easy fix. The only section I've added is the ":2at9" section, the rest is part of the pre-made convert-all batch file.

```

set /p input=Choice:
echo.
if %input%=="" goto finish
if %input%==1 echo Running option 1... & goto 2wav
if %input%==2 echo Running option 2... & goto 2mp3
if %input%==3 echo Running option 3... & goto 2wav
if %input%==4 echo Running option 4... & goto 2at9

goto finish

:2wav

echo.

for %%a in ("*at9") do (
  echo Converting %%a to wav in current directory...
  at9tool.exe -d "%%a" "%%~na.wav"
  echo.
)

if %input%==1 goto finish

:2mp3

for %%a in ("*.wav") do (
  echo Converting %%a to mp3 in current directory...
  ffmpeg -y -i "%%a" -ab 320k "%%~na.mp3"
  echo.
)

:2at9

echo.

for %%a in ("*fsb") do (
  echo Converting %%a to at9 in current directory...
  getfsb.exe -d "%%a" "%%~na.at9"
  echo.
)

if %input%==4 goto finish

endlocal

:finish

echo Finished.
echo.

pause

exit
```


My second snag is that for some reason, there are a few .fsb files that will still yield .at9 files, but when converted to .wav, they're all unusable 0kb .wav files, and I'm not entirely sure why. If someone else that knows more than I do has any Insight on either of those issues, I'd greatly appreciate it. Just let me know if you need any more info, or the tools themselves. Thanks in advance!
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-08-29T22:58:01+00:00
- Post Title: Extracting Bloodborne audio files and could use some Insight!

I think there's a simpler way to solve your issue.  If you download Foobar2000 and the vgmstream plugin, you should be able to drop all the .fsb files into Foobar and then convert them all in one go, to .wav or .mp3.
## Post #3
- Username: Rozekail
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Dec 01, 2017 7:55 am
- Post datetime: 2020-08-29T23:02:47+00:00
- Post Title: Extracting Bloodborne audio files and could use some Insight!

I'll definitely give it a shot! I appreciate it. I'll let you know how it goes tonight.
## Post #4
- Username: spennser
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Dec 30, 2016 1:12 pm
- Post datetime: 2020-09-07T09:46:49+00:00
- Post Title: Extracting Bloodborne audio files and could use some Insight!

did you have any luck? thanks! 
> Reply from Rozekail ↑Sun Aug 30, 2020 7:02 am at Sun Aug 30, 2020 7:02 am
>
> 
I'll definitely give it a shot! I appreciate it. I'll let you know how it goes tonight.
