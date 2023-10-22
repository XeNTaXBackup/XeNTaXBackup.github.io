## Post #1
- Username: JAY
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Dec 13, 2007 10:55 pm
- Post datetime: 2011-11-09T15:36:31+00:00
- Post Title: Driver San Francisco *.fchunk

Most of the files are encrypted. It looks it is similar to Driv3r and Driver Parallel Lines ([viewtopic.php?f=10&t=2877](http://forum.xentax.com/viewtopic.php?f=10&t=2877)). The also used the *.sp file extension. And we have the following:

*.astd
*.dncg
*.fchunk
*.pck

They also have the same header "CHNK". 

I checked out some files in "/media". There we have *.fchunk files which contains lua-scripts. I found many filenames in these files, e.g. in ScriptsLuaScripts.fchunk:

[](http://s7.directupload.net/file/d/2703/fcapm7n4_jpg.htm)

So it should be a lot easier to unpack these files. Can someone have look?

<link removed due forum rules violation>

Thanks.
## Post #2
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-11-10T08:00:53+00:00
- Post Title: Driver San Francisco *.fchunk

Man we are trying to crack this for mont and not success so far. It is very complicated format so good luck with it
## Post #3
- Username: 360AMC
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Apr 20, 2011 10:26 am
- Post datetime: 2011-11-25T22:19:55+00:00
- Post Title: Driver San Francisco *.fchunk

OMFG!
TrafficData.Lua
If we crack this....we could fix the traffic spawning and make all cars spawn in the traffic! Holy shit!
## Post #4
- Username: Dany0
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Dec 25, 2011 12:07 am
- Post datetime: 2011-12-24T17:15:12+00:00
- Post Title: Driver San Francisco *.fchunk

Oh boy oh boy oh boy I'm so excited! I want to mod the hell out of D:SF  The ending didn't give much easter eggs, but I enjoyed it so I'll make some of my own! hehe 

I got to the same point as JAG, will see what can do. So far it seems I can at least change nitro effect.
## Post #5
- Username: Axsis
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Oct 21, 2011 7:55 pm
- Post datetime: 2011-12-29T12:46:38+00:00
- Post Title: Driver San Francisco *.fchunk

these files with CHNK header is some sort of database, with lots of another CHNK files inside.
for example, completely (recursively) unpacked dngvehicles.sp has 150000+ files with generated filenames.  most of them are very small (< 4kb). it's not easy to find something there...
textures in dds format, some sounds in Wwise bnk, car geometry and animation in unknown format in multiple files.
## Post #6
- Username: Dany0
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Dec 25, 2011 12:07 am
- Post datetime: 2012-01-01T11:26:01+00:00
- Post Title: Driver San Francisco *.fchunk

Maybe there are small files that attach to every part on the vehicle that declare damage? It's possible. One could just ignore files smaller then 4kb?
## Post #7
- Username: 360AMC
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Apr 20, 2011 10:26 am
- Post datetime: 2012-01-16T02:27:57+00:00
- Post Title: Driver San Francisco *.fchunk

*bump*
## Post #8
- Username: Axsis
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Oct 21, 2011 7:55 pm
- Post datetime: 2012-01-16T22:27:54+00:00
- Post Title: Driver San Francisco *.fchunk

If you need lua scripts I've got bad news for you - they are in compiled form ("LuaQ" header).
## Post #9
- Username: 360AMC
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Apr 20, 2011 10:26 am
- Post datetime: 2012-01-18T23:57:50+00:00
- Post Title: Driver San Francisco *.fchunk

A guy on Driver Madness named Grover decoded them with LUAdec, and was in the process of making a recomplier....but then DM went down(coincidence? I think not. fucking ubisoft) DM's back up....but Grover hasn't returned.
## Post #10
- Username: Axsis
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Oct 21, 2011 7:55 pm
- Post datetime: 2012-01-19T15:30:25+00:00
- Post Title: Driver San Francisco *.fchunk

Unpacked ScriptsLuaScripts.fchunk file: [http://www.multiupload.com/78RSOXYCVT](http://www.multiupload.com/78RSOXYCVT)
but all scripts still in one file (0002_SCRS_[Script Package Compiled Script].bin) and offsets and sizes in other file (0001_SCRC_[Script Package Lookup].bin)
maybe someone will make a script or tool to unpack them. or maybe I do, but later.
## Post #11
- Username: 360AMC
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Apr 20, 2011 10:26 am
- Post datetime: 2012-01-21T02:08:08+00:00
- Post Title: Driver San Francisco *.fchunk

That would be excellent, please do. That Grover dude was going to....but as I said, DM went down(probably an Ubi inside job) and he lost all his posts due to the forum having to restore to an earlier backup.
## Post #12
- Username: 360AMC
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Apr 20, 2011 10:26 am
- Post datetime: 2012-02-20T04:44:03+00:00
- Post Title: Driver San Francisco *.fchunk

Any luck on decompiling the .LUA script packages?
## Post #13
- Username: 360AMC
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Apr 20, 2011 10:26 am
- Post datetime: 2012-03-25T00:55:22+00:00
- Post Title: Driver San Francisco *.fchunk

Nothing? God damn it, this is such an injustice. Great game like this with a few things needing to be fixed such as traffic spawning, and it'd be easy to make a decomplier/complier, but nope.
## Post #14
- Username: headrushmayor
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Nov 29, 2010 12:03 pm
- Post datetime: 2012-04-16T16:05:17+00:00
- Post Title: Driver San Francisco *.fchunk

> Reply from Axsis
>
> If you need lua scripts I've got bad news for you - they are in compiled form ("LuaQ" header).

Hi all been working on the game i work out edit sounds so far made them louder and alot more bass in car and turn down backfire a bit driving me nuts, i here tell you 
can edit the lua files you will need program called  RavioliGameTools_v2.5 then use the RScanner look at the file it a slow way but you get look in too the files and edit them as well, most file just like this if no what do with them. i have played around with them untill sumone help work them out.
PerformanceAnalysis.SamplePoints[1].X = -3007.607;
PerformanceAnalysis.SamplePoints[1].Y = 145.4927;
PerformanceAnalysis.SamplePoints[1].Z = 4483.603;
PerformanceAnalysis.SamplePoints[1].Angle = 0.6698866;
PerformanceAnalysis.SamplePoints[2].X = -2947.67;
PerformanceAnalysis.SamplePoints[2].Y = 148.6723;
PerformanceAnalysis.SamplePoints[2].Z = 4353.441;
PerformanceAnalysis.SamplePoints[2].Angle = 1.760166;
PerformanceAnalysis.MaxSamplePoints = 2;
## Post #15
- Username: 360AMC
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Apr 20, 2011 10:26 am
- Post datetime: 2012-04-24T23:40:08+00:00
- Post Title: Driver San Francisco *.fchunk

How about an all cars in traffic mod?  
EDIT:Okay, how the hell do you use this thing? I scan, it finds an Unkn0001.dat, it's nothing but hex, wat do.
## Post #16
- Username: Axsis
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Oct 21, 2011 7:55 pm
- Post datetime: 2012-04-26T13:21:12+00:00
- Post Title: Re: Driver San Francisco *.fchunk

[http://multiupload.biz/98kwcjpom046/DSF ... z.rar.html](http://multiupload.biz/98kwcjpom046/DSF_Script_Unpack_MultiUpload.biz.rar.html)
you may try to decompile unpacked lua scripts
## Post #17
- Username: 360AMC
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Apr 20, 2011 10:26 am
- Post datetime: 2012-05-18T21:44:06+00:00
- Post Title: Re: Driver San Francisco *.fchunk

NVM
## Post #18
- Username: 360AMC
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Apr 20, 2011 10:26 am
- Post datetime: 2012-06-09T19:57:04+00:00
- Post Title: Re: Driver San Francisco *.fchunk

>that feel when we'll never get to drive the ASYM Desannes and the Monaco copcar
