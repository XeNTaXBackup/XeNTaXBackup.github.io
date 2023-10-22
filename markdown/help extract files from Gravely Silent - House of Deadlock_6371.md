## Post #1
- Username: tmgley
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Mar 04, 2011 8:07 am
- Post datetime: 2011-04-07T07:34:29+00:00
- Post Title: help extract files from Gravely Silent - House of Deadlock

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-15T10:15:29+00:00
- Post Title: help extract files from Gravely Silent - House of Deadlock

script for quickbms:
[http://aluigi.org/papers/bms/vogat.bms](http://aluigi.org/papers/bms/vogat.bms)
## Post #3
- Username: gambit37
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Nov 05, 2010 11:27 am
- Post datetime: 2011-04-15T20:35:01+00:00
- Post Title: help extract files from Gravely Silent - House of Deadlock

Nice script, it works perfectly 

I noticed in the script comments it should also work on some other games. I tried it on Shades of Death: Royal Blood and also Elixir of Immortality, but I it stops immediately with this error without extracting anything:

```
       anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted
```
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-15T21:20:37+00:00
- Post Title: help extract files from Gravely Silent - House of Deadlock

I thought they used the same file format.

no problem, I have just updated the script so refresh the link and you will see the new one :)
## Post #5
- Username: gambit37
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Nov 05, 2010 11:27 am
- Post datetime: 2011-04-15T21:56:09+00:00
- Post Title: help extract files from Gravely Silent - House of Deadlock

Wow, you're a superfast machine!  There's a problem though, the script doesn't execute:

```
Error: the variable index is invalid, there is an error in this tool
```
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-15T22:28:24+00:00
- Post Title: help extract files from Gravely Silent - House of Deadlock

I guess you have an old version of quickbms because that error is visualized when a specified "comtype" algorithm is not available.
the latest version is available here:
[http://aluigi.org/papers.htm#quickbms](http://aluigi.org/papers.htm#quickbms)
## Post #7
- Username: gambit37
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Nov 05, 2010 11:27 am
- Post datetime: 2011-04-15T22:39:13+00:00
- Post Title: help extract files from Gravely Silent - House of Deadlock

Ah right, I didn't think to check the version. Thanks, it's working on those two games now (there's some nice music in these games that I enjoy listening to). Thanks for all your work on this!
## Post #8
- Username: tmgley
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Mar 04, 2011 8:07 am
- Post datetime: 2011-04-16T03:47:17+00:00
- Post Title: help extract files from Gravely Silent - House of Deadlock

Hello, 

I served much the script.

thank you very much everyone, alugi'm your fan # 1.   

One more question guys, how to compress it again?

Thanks for such good work and this great forum that does a great job.
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-16T06:06:36+00:00
- Post Title: help extract files from Gravely Silent - House of Deadlock

it's not guarantee to work but you can try the following which is the same step-by-step for any game supported by quickbms because the tool allows to reimport the modified files:

in the folder where you have extracted the files delete those that you have not modified, for example if you have modified the file my_folder\settings\settings.xml then delete all the others and leave only this one (don't touch its path)
create a backup copy of the bin file you will modify
create a link to quickbms.exe and add -r -w in the "Target:" field in the properties of the link, for example the result should be like: "c:\folder\quickbms.exe" -r -w
click on the link you have just created
quickbms will guide you step-by-step, so select the bms script
select the original archive in which you want to reimport the files you have modified
select the folder where the files reside, exactly the same folder you selected for the extraction
at the end of the process quickbms will tell you how many files have been reimported, so verify that they are exactly those you expected
