## Post #1
- Username: Dante00001
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Mar 26, 2017 5:36 am
- Post datetime: 2019-09-08T11:01:58+00:00
- Post Title: Control (extract videos) [SOLVED]

Hi there!

I've managed to extract stuff from Remedy Control's *.rmdp files but it seems that the video files are implemented as 'textures'. I can see a lot of files like  'cine_1_09_800_fakecredits.tex' and 'cine_1_10_600.tex'.

Is there any way to get actual videos out of these?

Thank you!
## Post #2
- Username: Dante00001
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Mar 26, 2017 5:36 am
- Post datetime: 2019-09-08T12:23:25+00:00
- Post Title: Control (extract videos) [SOLVED]

Nevermind, solved it. In case anyone interested I've opened the loadingscreen.ui file with HEX editor and found the reference to a video file called "hiss_menuloop.bk2". *.bk2 is actually a Bink video file which can be opened with RAD Video Tools. So I found the video file with the mentioned name and even though the extracted video file had an extension .tex the RAD Video Tools opened it without a problem (since it's actually a bink video file). 

And finally, the RAD Video Tools can export it to the actual video file (*.avi or whatever)

Cheers!
## Post #3
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2019-09-19T12:47:41+00:00
- Post Title: Control (extract videos) [SOLVED]

nice find!
## Post #4
- Username: hl24a3
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Sep 14, 2020 9:45 pm
- Post datetime: 2020-09-14T13:47:14+00:00
- Post Title: Control (extract videos) [SOLVED]

ok so in HxD I see the path like this textures/videos/hiss_inserts/hiss_menuloop.bk2 how do I actually find the file or extract it?
