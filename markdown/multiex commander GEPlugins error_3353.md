## Post #1
- Username: RENIKRILL
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Feb 11, 2009 7:54 pm
- Post datetime: 2009-02-12T15:14:41+00:00
- Post Title: multiex commander GEPlugins error

im on the verge of bashing my skull repeatedly through my screen. can somebody please explain to me why, everytime I open up multiEX commander it comes up with "GEPlugins error - Unable to find game extractor's JAR file."

For the love of god.

Thanks in advance for any help, and please excuse my frustration-inspired lewd manner about which I am asking for help in my desperate, anxious state.
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-02-13T23:55:25+00:00
- Post Title: multiex commander GEPlugins error

That error happens when it can't find Game Extractor (MexCom can use it's supported formats as well). As to the message, I know, I should remove it. I will do that with the next release.
## Post #3
- Username: RENIKRILL
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Feb 11, 2009 7:54 pm
- Post datetime: 2009-02-14T00:43:38+00:00
- Post Title: multiex commander GEPlugins error

so its not an actual 'error'? 
and is it able to use GA's file formats if it 'cant find' GA?

Thanks for tha help
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-02-14T09:29:56+00:00
- Post Title: multiex commander GEPlugins error

To use GE's formats, MexCom needs to find Game Extractor's .jar file in the standard installation directory of GE.
A future release will make it possible to point to the file, or even have the file in the MexCom dir.
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2009-02-17T18:30:10+00:00
- Post Title: multiex commander GEPlugins error

I think it should also just log silently if it can't find the jar file, instead of displaying an error (or at the most, display some sort of status message in the main program window or something).
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-02-17T18:57:57+00:00
- Post Title: multiex commander GEPlugins error

Yeah, I know, I know.
## Post #7
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2009-02-18T00:02:35+00:00
- Post Title: multiex commander GEPlugins error

When I made the plugin, I didn't actually think it would be 'enabled' by default. So if you don't want to see the error message you could just delete the plugin from the directory.
## Post #8
- Username: TanatOS
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat May 03, 2008 10:18 am
- Post datetime: 2009-10-13T23:07:38+00:00
- Post Title: multiex commander GEPlugins error

When start MultiEx I see that message:



GEPlugins Error GEPlugin Errors.png (3.92 KiB) Viewed 814 times


How I can fix it?

WinXP SP3
Game Explorer 2.0.1
Jre Version 6 Update 16
## Post #9
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-10-14T06:05:16+00:00
- Post Title: multiex commander GEPlugins error

Usually by installing the latest Java.
## Post #10
- Username: TanatOS
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat May 03, 2008 10:18 am
- Post datetime: 2009-10-14T19:28:39+00:00
- Post Title: multiex commander GEPlugins error

> Reply from Mr.Mouse
>
> Usually by installing the latest Java.You have a newer version?  
Info from [Java.com](http://java.com/en/download/manual.jsp)
"Recommended Version 6 Update 16"...
## Post #11
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-10-14T19:31:26+00:00
- Post Title: multiex commander GEPlugins error

Interesting. Well, I did not write the plugin, though. We should see where this comes from.
## Post #12
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2009-10-30T05:04:31+00:00
- Post Title: multiex commander GEPlugins error

> Reply from Mr.Mouse
>
> Interesting. Well, I did not write the plugin, though. We should see where this comes from.Oops... sorry it took so long for me to notice this  

When I wrote the code I made some assumptions based on my installation of Java, and I could be wrong. I don't think I have the time to investigate it right now.

Well, here's a quick fix: go to the registry key HKCU\Software\MexComGEPlugins and make a new string (if it isn't there already) called JreBinary and set it to the path and filename of jvm.dll. For example, mine would be C:\Program Files\Java\jre6\bin\client\jvm.dll.
## Post #13
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-10-30T08:07:24+00:00
- Post Title: multiex commander GEPlugins error

I recreated the issue on another machine. Simply installing the latest java (the machine had no java before) fixed the problem. So, it's weird that it did not work with you.
## Post #14
- Username: piratesephiroth
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Nov 08, 2009 6:05 pm
- Post datetime: 2009-12-21T08:03:32+00:00
- Post Title: multiex commander GEPlugins error

Yeah I had to create that JreBinary registry value manually too.
