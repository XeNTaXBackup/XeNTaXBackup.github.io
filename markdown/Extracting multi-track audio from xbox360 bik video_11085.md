## Post #1
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2013-12-26T22:04:09+00:00
- Post Title: Extracting multi-track audio from xbox360 bik video

hi, i tried to convert bik video from FFXIII:lightning Returns,the audio from the music and backsound video very clear,but when lightning or other character talk,i cant hear their voice because the sound is so little (is it because the vocal voice is on other track,that RAD tools cant manage???) any suggestion for this,so i can extract the character speech??? all help are appreciate
## Post #2
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2013-12-26T22:33:47+00:00
- Post Title: Extracting multi-track audio from xbox360 bik video

You'll need to extract all audio tracks separately and then mix them all together. 
Here's what I do: 
1) VGMToolbox > Misc Tools > Stream Tools > Video Demultiplexer > select BIK format, check box "Split Audio Tracks".
2) RAD Video Tools > select all split audio files from previous step > Convert a file > Yes > Output type WAV > Batch > Start
3) Now open the first resulted WAV file in Sony SoundForge, just open it, then open the next one, double click on second to highlight it, right mouse click > Copy. Then close second WAV track, press Mix icon from the top (Ctrl+M) > hit OK. There, now the audio files are merged. If there are more then 2 files, just copy and mix each file with the first one. 
And then when you done save the resulted WAV and mix it with video stream from original BIK file (step 4). 
4) RAD Video Tools > select video.bik file > Mix in sound > select the merged WAV file from step 3 > Mix.

Hope this helps. Also if you don't have SoundForge try some other similar [free] program like Audacity. The point is you need to merge tracks so any program that can do it, will do.
## Post #3
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2013-12-27T09:51:45+00:00
- Post Title: Extracting multi-track audio from xbox360 bik video

Thanks for your reply,i will try it asap   sorry out of topic,is it possible to convert real time cutscene in lightning returns to video?
## Post #4
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2013-12-27T14:33:49+00:00
- Post Title: Extracting multi-track audio from xbox360 bik video

Ok,I've tried your methods a minute ago,and its works like a charm   thanks again, Milo
## Post #5
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2013-12-27T18:24:48+00:00
- Post Title: Extracting multi-track audio from xbox360 bik video

Glad it worked. As for cutscenes that run on game's engine in real time, the only way to convert them to video would be to record with a capture card. That's something I've never done so can't really give any advice there. 

Also just in case you're after better quality pre-rendered cutscenes, keep i mind that PS3 version has them in sharper quality compared to Xbox360. PAM video on PS3 while 360 uses BIK.
## Post #6
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2013-12-29T05:56:46+00:00
- Post Title: Extracting multi-track audio from xbox360 bik video

Yes,i notice the different video quality between ps3 and xbox 360 version,but since i only have an xbox,i guess im quite satisfied with bik format  beside, the tools for converting bik video is available.is there any pam video converter just like bik with rad game tools?
## Post #7
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2013-12-29T07:06:27+00:00
- Post Title: Extracting multi-track audio from xbox360 bik video

The same video demultiplexer from VGMToolbox will split PAM file into video and audio streams. It will result in m2v video and aa3 audio streams. aa3 is converted to wav with Sony SoundForge, while m2v is already good to go. Then MKVmerge (which is part of MKVtoolnix package) will stitch m2v and wav together.
## Post #8
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2013-12-30T18:21:48+00:00
- Post Title: Extracting multi-track audio from xbox360 bik video

Great,now i have plenty of choice   thanks again for your help Milo
