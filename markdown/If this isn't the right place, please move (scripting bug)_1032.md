## Post #1
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-12-31T19:54:29+00:00
- Post Title: If this isn't the right place, please move (scripting bug?)

I'm trying to write a BMS file for a filetype I know a bit about (Berkeley Systems Script Resource File - or .SRF for short)

Here's the script I have

```
FindLoc DUMMYL String snd 0 ;
Get FILECNTL Long 0 ;
Get FILESTART Long 0 ;
Do ;
GoTo FILESTART 0 ;
Get FILENAME Long 0 ;
Get FILEOFF Long 0 ;
Get FILESIZE Long 0 ;
SavePos FILESTART 0 ;
Log FILENAME FILEOFF FILESIZE 0 0 ;
Math EXTRCNT += 1 ;
While EXTRCNT <> FILECNTL ;

```


It seems to crash Multiex when I try to use it - what am I doing wrong?

To explain it, so that people can see any errors I may have made, it should first check that the first long is 'srf1', and then skip to a header long 'snd ' (note the space at the end), the next long is the number of files, the next the filename (two numbers, two spaces), the one after the offset and finally the size in bytes.

I can't see why this script doesn't work, it passes all the tests bar the actual extraction (a sample file is at [http://www.mametesters.org/elcondor/ABH.srf](http://www.mametesters.org/elcondor/ABH.srf) )

Please help.
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-01T11:47:23+00:00
- Post Title: If this isn't the right place, please move (scripting bug?)

First of all, all the variables (longs) are not Little Endian, but Big Endian, so you'll have to do a "ReverseLong" statement before you can work with them after you "loaded" them. 

Example:

Get FILECNTL Long 0 ;
ReverseLong FILECNTL ;

Second of all, you must actually jump to the location of DUMMYL. FindLoc will only load up the DUMMYL variable with the location (offset) of the string you were looking for. So, do a Math DUMMYL += 4 (4 characters in "snd ") and then a GoTo DUMMYL 0 ;. 

Third of all, there are no actual filenames in there I believe, or you may be able to use the strings as filenames (see header STR and where the offsets point to). To not use filenames, simply use the log statement like 

Log "" OFFSET SIZE 0 0 ;

Hope this helps you getting the script right.
Note that you can find a mex3.log in the windows system32 dir that can help you track the script and where it goes wrong.
## Post #3
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-01-01T19:43:24+00:00
- Post Title: If this isn't the right place, please move (scripting bug?)

Oops, didn't notice the endianness (I forgot this was actually a MAC OS format).

I'll try retooling the script - I suppose I could use the filenames in the STR, but that's probably too difficult for me to get my head round, so I'll stick to the file ID numbers, because these don't vary between file revisions (the STR stuff does, the engine's more sophisticated than I can script, and can pick up on particular characteristics from another file to configure itself.
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-03T08:47:08+00:00
- Post Title: If this isn't the right place, please move (scripting bug?)

Also note that the script varibles you used come from old MultiEx 16-bit (FILECNLT, DUMMYL etc). You can use any variable name you want in  Mex3Scriptor (the latest scripting program).
## Post #5
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-01-03T19:53:24+00:00
- Post Title: If this isn't the right place, please move (scripting bug?)

Sorry about the delay, I've been a little busy...

I've taken your advice, and now I have a script which decodes all that type of file, unfortunately, the audio format used is a little bizarre.

I know that you can use any variable you like, but I prefer the originals, they make enough sense, and the veterans can understand them better
## Post #6
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-01-04T00:05:35+00:00
- Post Title: If this isn't the right place, please move (scripting bug?)

Is there anywhere I can go to find a tutorial on how to use these scripts, and if not, could someone show me?
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-04T07:25:53+00:00
- Post Title: If this isn't the right place, please move (scripting bug?)

You should create the script using MexBinderPlus (start the scriptor) and then import it into mc.mrf (in the data/config dir of MultiEx Commander) using the binder (open mc.mrf, add single format, give it a name and resave the mc.mrf, overwrite the old mc.mrf in the config dir). 

The Use Custom BMS option is screwed in the latest MultiEx Commander release (extract/preview failes I believe) but I have fixed that for the upcoming release.

As for the script itself, you can read a little about it in MexBinder or the Scriptor (see help).
## Post #8
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-01-04T15:49:30+00:00
- Post Title: If this isn't the right place, please move (scripting bug?)

Well, I've downloaded MexBinderPlus and read the Help file, but I don't have any experience with scripting beyond HTML and some CSS  . So if anyone could take some time out of their busy schedule and show me how to do just some really basic scripting, I would much appreciate it.
## Post #9
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-01-04T20:08:57+00:00
- Post Title: If this isn't the right place, please move (scripting bug?)

Once I've got the script I'm on done, I'll get signed up properly here, and try to take you through it, if that helps.
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-04T23:23:11+00:00
- Post Title: If this isn't the right place, please move (scripting bug?)

Nice of you to help him out, also please post the script here a well then, so I can implement it into the next release!
## Post #11
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-01-05T17:27:22+00:00
- Post Title: If this isn't the right place, please move (scripting bug?)

Okay, thanks! 


Should I start a new topic in Code Talk for it?
## Post #12
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-05T18:06:05+00:00
- Post Title: If this isn't the right place, please move (scripting bug?)

That's a good idea!
## Post #13
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-01-06T15:40:37+00:00
- Post Title: If this isn't the right place, please move (scripting bug?)

Ooh, I had a good idea!  

What should I title it? Perhaps "scripting help"...
## Post #14
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-06T15:43:46+00:00
- Post Title: If this isn't the right place, please move (scripting bug?)

Yeah, or Mex Scripting Help 

Hey, "Guest", will you also share that script you created with us?
## Post #15
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-01-07T20:51:59+00:00
- Post Title: If this isn't the right place, please move (scripting bug?)

> Reply from Mr.Mouse
>
> Yeah, or Mex Scripting Help

Okay, I'll go make it.
