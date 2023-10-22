## Post #1
- Username: djneo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jul 03, 2017 9:57 pm
- Post datetime: 2022-07-09T10:23:45+00:00
- Post Title: NHL 2K3 (Gamecube) - PVR, CMN, NHM etc.

Hi guys,
to save your precious time, I'll go straight to my question...

Luckily extracting these NHL 2K3 files was pretty easy (even for a noob like me), well unfortunately the names of the files are still  not in standard formats that I could edit and revert back to the game (textures, models, audio file)

Please take a look at the screens below:



I was wondering if anyone here could point me to what to do next?
It would really help me out! 

Thanks in advance, I appreciate that...
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-07-10T13:38:55+00:00
- Post Title: NHL 2K3 (Gamecube) - PVR, CMN, NHM etc.

Please upload a few samples of each type you want to check
(e.g. few PVR files, few CMN files etc.)
## Post #3
- Username: djneo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jul 03, 2017 9:57 pm
- Post datetime: 2022-07-10T14:26:52+00:00
- Post Title: NHL 2K3 (Gamecube) - PVR, CMN, NHM etc.

Hello!

Thank you for your quick response and letting me know, how to do it right.
I'll upload everything as soon as I get back home to computer from work, which will be tomorrow morning.

Greetings from rainy Prague
## Post #4
- Username: djneo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jul 03, 2017 9:57 pm
- Post datetime: 2022-07-10T22:45:19+00:00
- Post Title: NHL 2K3 (Gamecube) - PVR, CMN, NHM etc.

I managed to get home sooner, so here are the promised samples, in their own folders.

Let me know if anything else is needed, thanks again! 

[https://www.mediafire.com/file/l22lz57q ... be.7z/file](https://www.mediafire.com/file/l22lz57qrlnsca1/NHL2K3_files_samples_Gamecube.7z/file)
## Post #5
- Username: djneo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jul 03, 2017 9:57 pm
- Post datetime: 2022-07-11T18:21:44+00:00
- Post Title: NHL 2K3 (Gamecube) - PVR, CMN, NHM etc.

Not sure if its any important, but it's a game from 2002 developed by Treyarch.
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-07-12T19:40:30+00:00
- Post Title: NHL 2K3 (Gamecube) - PVR, CMN, NHM etc.

So I have checked your files and here are the results:


CMN - it is an archive format. It is used to store models and GCT textures (GCNT signature)
File format is here [http://wiki.xentax.com/index.php/NHL_2K3_CMN](http://wiki.xentax.com/index.php/NHL_2K3_CMN)
And you can unpack data from them using this script [https://github.com/bartlomiejduda/Tools ... script.bms](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/NHL%202K3/NHL_2K3_CMN_script.bms)


More info on GCT files here [http://wiki.xentax.com/index.php/GCT_Image](http://wiki.xentax.com/index.php/GCT_Image)
If you'll change extension from BIN to GCT and remove first 8 bytes in file,
you will be able to convert textures using tools listed on the wiki.


DAT - I have no idea what those files are, sorry.

DB - Seems to be some custom database format for storing players info (?)

NHM - I have no idea what those files are, sorry, but they seems to be
somehow corelated with CMN archives. They also seems to always start with 00 00 04 80 value.

PVR - Those seems to be GCT textures as well, but for some reason
I couldn't convert them with existing tools...

STR - I have no idea what those files are, sorry.
## Post #7
- Username: djneo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jul 03, 2017 9:57 pm
- Post datetime: 2022-07-12T22:47:32+00:00
- Post Title: NHL 2K3 (Gamecube) - PVR, CMN, NHM etc.

1st thanks a lot for your time and script!
I'm doing some tests, but I get this error, not sure what I'm doing wrong?

[](%5Bimg%5Dhttps%3A//i.imgur.com/Q2FRmHC.jpg%5B/img%5D)

Do you think if these CMN folders contain models, will it be possible to edit them and re-import them?
That would be awesome.
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-07-13T20:43:35+00:00
- Post Title: NHL 2K3 (Gamecube) - PVR, CMN, NHM etc.

> not sure what I'm doing wrong?
I'm not sure either. My script has only 24 lines of code and you have an error on line 184.   
Try to type "y" and then press enter. Or try to reformat the script (check new lines, indent etc.).

> Do you think if these CMN folders contain models, will it be possible to edit them and re-import them?
Maybe. I don't know anything about models. You can ask on "3D/2D models" section on this forum. There are some model experts there.
## Post #9
- Username: djneo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jul 03, 2017 9:57 pm
- Post datetime: 2022-07-13T21:30:01+00:00
- Post Title: NHL 2K3 (Gamecube) - PVR, CMN, NHM etc.

Hah, that's weird 

I'll test again...
## Post #10
- Username: djneo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jul 03, 2017 9:57 pm
- Post datetime: 2022-07-15T11:00:15+00:00
- Post Title: NHL 2K3 (Gamecube) - PVR, CMN, NHM etc.

so I think I just saving the script the wrong way.
I was saving it by right clicking- "save link as" which indeed saves a file much longer than 24 lines.

Sorry for this stupid question, but how should I save this script correctly, I don't see any save option there, and I'm not obviously very familiar with the GitHub site
## Post #11
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-07-15T16:40:41+00:00
- Post Title: NHL 2K3 (Gamecube) - PVR, CMN, NHM etc.

> Sorry for this stupid question, but how should I save this script correctly, I don't see any save option there, and I'm not obviously very familiar with the GitHub site

So there are two methods:

Method 1:
1. Go to script file on Github
2. Select everything and press CTRL+C
3. Open new windoow in Notepad++ (download Notepad++ first if you don't have it)
4. Paste everything in Notepad++ and save new file as "script.bms"


Method 2:
1. Go to Main repository site [https://github.com/bartlomiejduda/Tools](https://github.com/bartlomiejduda/Tools)
2. Click on green button "Code" and select "Download ZIP"
as on this screenshot [https://imgur.com/a/em1ttRO](https://imgur.com/a/em1ttRO)
(but this will download other scripts as well)
