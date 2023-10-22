## Post #1
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2004-01-12T08:46:05+00:00
- Post Title: Re: Rabota open max

> Reply from zzz
>
> These program does not work on win98 - it does not found unicows.dll and crashes
So you should add that dll to install packacge


  And when y tryied to open file it shows message
////Could not read file.
Error reading "D:\Arx Fatalis\data.pak: exeptions. Type error ord() expected a character, but string of length 0 found' traceback: File "ArchiveManager.pyc", line 308, in OpenArchive


File "C:\UTIL\OPENMEX\handlers\legacy2\ArxFatalispak.py", line 66, in readStructure

name = bf0.safeReadNullTerminatedString()////

     

And show incorect names in Blood rff files

Many incorect names in Heroes 3 lod files
Thanks for the bugreport. OpenMex is still in Alpha phase, so some things simply do not work yet. I do not have arx fatalis pak files, so could you send me one for testing?

In the meantime, I recommend you use [MultiEx](http://www.xentax.com/html/multiex-main.htm) for your extracting. It should work better for you.
