## Post #1
- Username: GianaSistersFan64
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Jul 21, 2020 11:48 pm
- Post datetime: 2022-07-07T19:35:32+00:00
- Post Title: Extracting Giana Sisters 2D Audio tracks

Hello.
I recently discovered Giana Sisters 2D seem to store it musics as tracker, but I'm not certain enough if it's true. I found out these data were stored in a file called "resources.resource", yes it is a Unity game. Unfortunately I couldn't find anything to extract these type of files so why not asking help here.

Here's the file : [https://www.mediafire.com/file/pa7fcc37 ... ource/file](https://www.mediafire.com/file/pa7fcc379e9cr9w/resources.resource/file)

Help would be appreciated
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-07-09T12:30:45+00:00
- Post Title: Extracting Giana Sisters 2D Audio tracks

Hi you can extract XM audio from resource archive using this script:
[https://github.com/bartlomiejduda/Tools ... rchive.bms](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/UNITY_TOOLS/Multiple_XM_files_in_one_RESOURCE_Unity_archive.bms)

You should be able to extract 26 XM files from your sample. 
You can then play them in any audio player, e.g. Winamp.

More info about the format is here [http://wiki.xentax.com/index.php/XM_Audio](http://wiki.xentax.com/index.php/XM_Audio)
## Post #3
- Username: GianaSistersFan64
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Jul 21, 2020 11:48 pm
- Post datetime: 2022-07-09T14:56:37+00:00
- Post Title: Extracting Giana Sisters 2D Audio tracks

Thank you for your help 
XM files can be read with OpenMPT too.
