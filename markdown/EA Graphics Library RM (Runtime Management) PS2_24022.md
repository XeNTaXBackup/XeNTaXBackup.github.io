## Post #1
- Username: lusji2011
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Dec 06, 2016 6:52 pm
- Post datetime: 2021-06-10T17:51:11+00:00
- Post Title: EA Graphics Library RM (Runtime Management) PS2

Inside FIFA 14 iso, I found this file called EAGLRM.elf,maybe inside this file we can get information about SSH texture files,maybe some programmer can take a look


 eaglrm.rar
(19.88 KiB) Downloaded 24 times
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-06-10T21:11:24+00:00
- Post Title: EA Graphics Library RM (Runtime Management) PS2

There is already an article about SSH images on the wiki
[http://wiki.xentax.com/index.php/EA_SSH_FSH_Image](http://wiki.xentax.com/index.php/EA_SSH_FSH_Image)

Information provided there allows for basic image conversion.
Also some tools are listed there.
## Post #3
- Username: lusji2011
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Dec 06, 2016 6:52 pm
- Post datetime: 2021-06-10T23:07:40+00:00
- Post Title: EA Graphics Library RM (Runtime Management) PS2

yeah, but we need know wich tipe o texture RAW format are used in the images,because .raw can be open on photoshop, but the image format is unknow see the results.
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-06-11T07:11:00+00:00
- Post Title: EA Graphics Library RM (Runtime Management) PS2

You can determine image type by reading "record ID" value from the image header



screenshot000626.png (19.15 KiB) Viewed 95 times



I was able to recognize some types in my tool for NHL (lines 166-235)
[https://github.com/bartlomiejduda/Tools ... S2_Tool.py](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/NHL%202002%20PS2/NHL_2002_PS2_Tool.py)
But for now it is only PoC tool and support for other types is limited.
