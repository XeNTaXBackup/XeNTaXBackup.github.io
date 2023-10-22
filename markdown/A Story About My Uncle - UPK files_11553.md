## Post #1
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2014-05-31T10:24:48+00:00
- Post Title: A Story About My Uncle - UPK files

Hello there.
I've been trying to get the text files of ASAMU for few days now, but so far it's no good.
At first I found some files in ASAMU\Localization\INT folder. I've translated the first two sections of [Workshop_Narrator.INT](https://dl.dropboxusercontent.com/u/20577703/TranslationProjects/ASAMU/Workshop_Narrator.int) file, only to find out that nothing changes in the game. Though when I changed a string in [ASAMU.INT](https://dl.dropboxusercontent.com/u/20577703/TranslationProjects/ASAMU/ASAMU.int), it worked fine...
So I started trying other things. I found out decompress.exe by Gildor, and [UPKInOut](http://forum.xentax.com/viewtopic.php?f=35&t=9575&p=78609#p78609) 1.5 by Jenner thanks to H3rdell. I decompressed the [AG-Workshop_LOC_INT.upk](https://dl.dropboxusercontent.com/u/20577703/TranslationProjects/ASAMU/AG-Workshop_LOC_INT.upk) file, and dropped it on the UPKInOut but it says that there isn't any strings in the file though there is...
Then I found some [tools](http://forum.xentax.com/viewtopic.php?f=35&t=10964&p=92873#p92873) thanks to swuforce. UPKUnpack and UPKRepack worked fine, but loc_int_export and loc_int_import didn't work. So I used HxD to edit the SoundNodeWave files and repacked it, and it worked fine in the game. But I'd rather not to use hex programs to translate, since it's way harder and it has character limit.

So, can anyone take a look at the upk file?
Thanks in advance.
## Post #2
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-06-01T06:15:55+00:00
- Post Title: A Story About My Uncle - UPK files

Hi, did you ever know? What is font file?
## Post #3
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2014-06-01T08:51:52+00:00
- Post Title: A Story About My Uncle - UPK files

I don't know the name, but I think it's located under Startup_LOC_INT.upk. You can view it with umodel.
## Post #4
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-06-01T12:47:20+00:00
- Post Title: A Story About My Uncle - UPK files

> Reply from qabRieL
>
> I don't know the name, but I think it's located under Startup_LOC_INT.upk. You can view it with umodel.
Thank you.
## Post #5
- Username: Starnova
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Feb 10, 2014 10:19 am
- Post datetime: 2014-06-02T12:58:54+00:00
- Post Title: A Story About My Uncle - UPK files

Im trying to figure out how to make the external localization works, but so far I couldnt do anything. I was thinking probably in create other localization folder, for example, ESN (for spanish localization) and rename all the .int files to .ESN. After that i modified DefaultEngine.ini to configure the language but when i start the game, shows me an executable error. Well, i have to keep trying haha. Regards.
## Post #6
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2014-06-02T15:18:09+00:00
- Post Title: A Story About My Uncle - UPK files

> Reply from Starnova
>
> Im trying to figure out how to make the external localization works, but so far I couldnt do anything. I was thinking probably in create other localization folder, for example, ESN (for spanish localization) and rename all the .int files to .ESN. After that i modified DefaultEngine.ini to configure the language but when i start the game, shows me an executable error. Well, i have to keep trying haha. Regards.
Good to see an other fellow working on this. Good luck!
## Post #7
- Username: Starnova
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Feb 10, 2014 10:19 am
- Post datetime: 2014-06-04T20:44:40+00:00
- Post Title: A Story About My Uncle - UPK files

> Reply from qabRieL
>
> Starnova wrote:Im trying to figure out how to make the external localization works, but so far I couldnt do anything. I was thinking probably in create other localization folder, for example, ESN (for spanish localization) and rename all the .int files to .ESN. After that i modified DefaultEngine.ini to configure the language but when i start the game, shows me an executable error. Well, i have to keep trying haha. Regards.
Good to see an other fellow working on this. Good luck!

Seems that no one want to help, so the only choice is to translate with the HexEditor. There are not too much subtitles, but there must be a way to use the external localization.
## Post #8
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2014-06-05T07:59:50+00:00
- Post Title: A Story About My Uncle - UPK files

Use the same japanese tool for the upk.
And use this for export import text: [http://www.sendspace.com/file/0mbinv](http://www.sendspace.com/file/0mbinv)
## Post #9
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2014-06-05T08:33:21+00:00
- Post Title: A Story About My Uncle - UPK files

> Reply from swuforce
>
> Use the same japanese tool for the upk.
And use this for export import text: http://www.sendspace.com/file/0mbinv
Thanks for the effort and the tool pal, great job. I really appreciate it.
A question though: I was able to export the  text file, but I couldn't import it back. It kept saying "There are no .SoundNodeWave files in Workshop_Narrator folder, or the folder not exists" even though text file is located in with 7 .SoundNodeWave files. What am I doing wrong?
## Post #10
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2014-06-09T17:10:00+00:00
- Post Title: A Story About My Uncle - UPK files

They are already translating it to a couple of languages here:
[https://crowdin.net/project/a-story-about-my-uncle](https://crowdin.net/project/a-story-about-my-uncle)
