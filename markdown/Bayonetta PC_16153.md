## Post #1
- Username: wardialer6000
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jun 09, 2016 2:05 am
- Post datetime: 2017-04-16T18:09:21+00:00
- Post Title: Bayonetta PC

i extracted all the CPK files in noesis which created a lot of DAT files in 'data??files' folders.  however, i can't seem to open any DAT files in noesis.  i keep getting a 'file could not be previewed' error.

are these files encrypted, or am i clicking on the wrong ones?
## Post #2
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-04-16T18:46:09+00:00
- Post Title: Bayonetta PC

You need to provide samples, I'm almost sure it's endianness difference console/pc + different texture format (.xpr xbox-360 and most likely .dds for pc)
## Post #3
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2017-04-17T00:10:46+00:00
- Post Title: Bayonetta PC

Can someone confirm if Bayonetta 2's Bayonetta model has the same or similar skeleton? I can move her over to Bayonetta PC if I get time.

Cheers.
## Post #4
- Username: MisterNatal
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Sep 02, 2014 9:53 am
- Post datetime: 2017-05-02T05:52:17+00:00
- Post Title: Bayonetta PC

Can someone please link me to the wmb importer script for 3ds max? and the noesis script please!
## Post #5
- Username: Kerilk
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Aug 27, 2017 9:08 pm
- Post datetime: 2017-08-27T19:10:59+00:00
- Post Title: Bayonetta PC

I have updated the Noesis plugin for Bayonetta PC (with permission from MrAdults). You can find it here:
[https://github.com/Kerilk/noesis_bayonetta_pc](https://github.com/Kerilk/noesis_bayonetta_pc)
in the release section.

Some normal maps and textures have an offset/scale that I cannot reliably fix right now but most of the models can be viewed.

I am trying to figure the animation format. I made some progress (I can read the files) bur I can't figure out the interpolation method used.
## Post #6
- Username: Kerilk
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Aug 27, 2017 9:08 pm
- Post datetime: 2017-10-01T22:33:14+00:00
- Post Title: Bayonetta PC

Just a little update to report that I have added some support for animations to the plugin.
## Post #7
- Username: MisterNatal
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Sep 02, 2014 9:53 am
- Post datetime: 2017-12-07T05:19:53+00:00
- Post Title: Bayonetta PC

> Reply from Kerilk
>
> Just a little update to report that I have added some support for animations to the plugin.Could you explain on what type of animations you have seen work? like her movelist? walking? taunts? cutscenes?
## Post #8
- Username: Kerilk
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Aug 27, 2017 9:08 pm
- Post datetime: 2017-12-07T11:20:25+00:00
- Post Title: Bayonetta PC

> Reply from MisterNatal
>
> Kerilk wrote:Just a little update to report that I have added some support for animations to the plugin.Could you explain on what type of animations you have seen work? like her movelist? walking? taunts? cutscenes?

All of them. They are often located in different files. Example: pl0000.dat and pl000f.dat. pl000f.dat contains all movements. Boss specific movements are contained in the boss file: example em0400.dat contains surf related animations. I think weapon specific animations are located with the weapons. Note that noesis will only play animations for pl0000.dat as it contains pl0010.wmb and all player related animations have format pl0010_xxx.mot.

Animations for cutscene are contained in the cutscene files themselves. I have tried it with bayo 2, never with bayo 1 but it should be the same. The extension is not .dat so the filter will not display it and you will need to write the filename in the box.
## Post #9
- Username: MisterNatal
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Sep 02, 2014 9:53 am
- Post datetime: 2019-02-12T08:03:18+00:00
- Post Title: Bayonetta PC

> Reply from Kerilk
>
> MisterNatal wrote:Kerilk wrote:Just a little update to report that I have added some support for animations to the plugin.Could you explain on what type of animations you have seen work? like her movelist? walking? taunts? cutscenes?

All of them. They are often located in different files. Example: pl0000.dat and pl000f.dat. pl000f.dat contains all movements. Boss specific movements are contained in the boss file: example em0400.dat contains surf related animations. I think weapon specific animations are located with the weapons. Note that noesis will only play animations for pl0000.dat as it contains pl0010.wmb and all player related animations have format pl0010_xxx.mot.

Animations for cutscene are contained in the cutscene files themselves. I have tried it with bayo 2, never with bayo 1 but it should be the same. The extension is not .dat so the filter will not display it and you will need to write the filename in the box.
Hey! Was wondering if you or anyone really would mind helping me with Bayo 2 animations? I downloaded your plugin and believe I installed it to the right location but i'm still unable to view them
## Post #10
- Username: Kerilk
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Aug 27, 2017 9:08 pm
- Post datetime: 2019-02-28T23:35:03+00:00
- Post Title: Bayonetta PC

You need to delete the original bayonetta.dll in the plugins folder for the bayonetta_pc.dll to work. If noesis asks you to open a file for animations then it is my plugin loading the model.

For whatever reason I was not notified of your post. The github bugtracker of the plugin is also a good place to reach me for issues with the plugin.
## Post #11
- Username: MrJonathan16
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 05, 2023 7:32 am
- Post datetime: 2023-07-04T23:33:45+00:00
- Post Title: Bayonetta PC

Where can i find Animations for cutscenes for Bayonetta 1, 2 and 3 more easily
