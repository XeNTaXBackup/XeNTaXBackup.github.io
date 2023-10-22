## Post #1
- Username: brownyfifa
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 16, 2020 11:58 am
- Post datetime: 2020-03-13T04:24:43+00:00
- Post Title: Multiple LuaQ files help

Hi all,

Looking to get some help to extract the linked file below , could it be done in quickbms?

The file header is LuaQ , which is a compiled version of a lua file.

However there are multiple LuaQ file headers throughout the file, so I believe this is why I cannot decompile these using LuaDec or unluac .

Would anyone be able to write a bms file that would extract this bin archive in to the multiple LuaQ files ? I am a novice to unpacking scripts so it would be much appreciated. Hoping it's a straight forward file as it has file names in clear text.

That should allow me to decompile the individual luac files

[https://filebin.net/2ufaby8a5r7rcpnq](https://filebin.net/2ufaby8a5r7rcpnq)
## Post #2
- Username: brownyfifa
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 16, 2020 11:58 am
- Post datetime: 2020-03-13T23:03:25+00:00
- Post Title: Multiple LuaQ files help

So I have gotten further with this. 

It appears like the file starts with a 12 byte header
then 3 null bytes in a row
then a name size 


however with my limited bms knowledge now I need to know the filesize and offset. From doing some research, it seems that these are stored in a seperate file (attached)

How the hell do I find the filesize and offsets for these files in that file ? It looks completely random. Also is it possible to reference them in quickbms or would I just manually input all the filesize and offsets per file (tedious but ill do whatever required)

Would appreciate any help available

My current script goes like this (first time)

get FILES Long
for i=0 < FILES
get HEADER1 long
get HEADER2 long
get null short
get null byte
get NSIZE byte
getdstring NAME NSIZE

##find filesize and offset from other .bin file##
[0001_SCRC_[Script Package Lookup].zip](https://xentaxbackup.github.io/file/17709_0001_SCRC_[Script Package Lookup].zip)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-14T08:39:08+00:00
- Post Title: Multiple LuaQ files help

print out your files count (print "number of files %FILES%")
surprise!  

Anyways I have a  deja vue of a (general) bms filesplitter, but can't find it.

So I made one in 'C', which splits before "LuaQ", here's the first 4 resulting files.
You may check them. In case it works I could send you the tool.
.


 LuaQ.zip
(5.1 KiB) Downloaded 20 times



btw: used simple file numbering ("1","2","3") because of the weird pathnames.
r:\resources\luascripts\common\\achievementtable.lua for example.
(It's so annoying. Else I use one or two slashes but not mixed, never.  )

You could, of course, read the path 'till the first double slash, create that directory, read the rest of the path (lua filename) and log that file then.
Don't have the time for such...
## Post #4
- Username: brownyfifa
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 16, 2020 11:58 am
- Post datetime: 2020-03-14T23:36:01+00:00
- Post Title: Multiple LuaQ files help

Hey mate, 

That is legendary thanks. Really appreciate the help. 

Are you able to run that program on the whole archive (im not stressed about the file names) so I can test it properly?
## Post #5
- Username: brownyfifa
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 16, 2020 11:58 am
- Post datetime: 2020-03-14T23:51:38+00:00
- Post Title: Multiple LuaQ files help

Hey Shatokay2,

I might not need to reinvent the wheel here. I found a program on the net that uses C# to perform this process, however it does it from the .fchunk archive. 

Ran into a problem with it though, it supports big endian archive decompiling (using --big) however it doesn't support big endian recompiling. 

I've attached the software and an example of an fchunk. 

Just based on your knowledge, how long would it take me to learn C# enough to understand this program and add big endian recompiling support? I work in IT but have little programming knowledge outside what I did at college. I had a look at it in VB2019 and it does look relatively complicated. I'm wondering if I just go through and try to understand only the commands in this program, or actually try to learn C# ground up.
## Post #6
- Username: brownyfifa
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 16, 2020 11:58 am
- Post datetime: 2020-03-14T23:54:31+00:00
- Post Title: Multiple LuaQ files help

Files are below

[https://filebin.net/f663mxp0s3r2dgca](https://filebin.net/f663mxp0s3r2dgca)
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-15T08:31:21+00:00
- Post Title: Multiple LuaQ files help

> Reply from brownyfifa ↑Sun Mar 15, 2020 7:36 am at Sun Mar 15, 2020 7:36 am
>
> Are you able to run that program on the whole archive (im not stressed about the file names) so I can test it properly?Hey brownyfifa,
having 496 .lua files in one folder? (You will hate it!  ) (I could replace the drive letter "r:" in the path at the beginning of the files by "c:" in case it helps)
.
[LuaQ-split.zip](http://www.uploadmb.com/dw.php?id=1584259195)


> Reply from brownyfifa ↑Sun Mar 15, 2020 7:51 am at Sun Mar 15, 2020 7:51 am
>
> I'm wondering if I just go through and try to understand only the commands in this programInteresting  thought.  (Could work in case you know 'C' for example.)

> Just based on your knowledge, how long would it take me to learn C# enough to understand this program and add big endian recompiling support? I work in IT but have little programming knowledge outside what I did at college. I had a look at it in VB2019 and it does look relatively complicated.Depends on what you learned at college so far. Did you ever compile a (Visual)Basic, a C#, a 'C' or 'C++' program?
If 'no', then you have a long road to go. Not a matter of 3 weeks, I guess. 

Anyways, you might have a look here: [https://stackify.com/learn-c-sharp-tutorials/](https://stackify.com/learn-c-sharp-tutorials/)

Or here (no ads!):
C# Tutorial - Full Course for Beginners
[https://www.youtube.com/watch?v=GhQdlIFylQ8](https://www.youtube.com/watch?v=GhQdlIFylQ8)

This is some very valuable comment, imho:
Richard James Andersen
"After browsing other videos for beginners, I should note that a few important things were left out that should have been included:
[...]
7) Where do go after this video? I would highly recommend C# Tutorial for beginners by ProgrammingKnowledge (the video is 5h 37min long)."

Guess, he means this one (with ads):
[https://www.youtube.com/watch?v=KVr8NTZ ... dex=6&t=0s](https://www.youtube.com/watch?v=KVr8NTZ-vG4&list=PLS1QulWo1RIYEMepIBinxplXsx9v0zCSf&index=6&t=0s)
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-16T21:03:46+00:00
- Post Title: Multiple LuaQ files help

> Reply from brownyfifa ↑Sun Mar 15, 2020 7:54 am at Sun Mar 15, 2020 7:54 am
>
> 
Files are belowWhere is the DSCript project?

Couldn't find it in the web, only DScript ([https://github.com/bizzehdee/DScript](https://github.com/bizzehdee/DScript)), which doesn't seem to be the required one.
## Post #9
- Username: brownyfifa
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 16, 2020 11:58 am
- Post datetime: 2020-03-17T02:04:17+00:00
- Post Title: Multiple LuaQ files help

Hi Shakotay, 

Thanks very much for your help. Looks like I won't need to learn C, I was able to modify the values I needed to by hex editing the f chunk file itself, without even needing to decompile. 

Much appreciated.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-17T07:34:43+00:00
- Post Title: Multiple LuaQ files help

Hi brownyfifa,

great!  

But where do I get the DSCript project?
It's not a package only - the LuaSF solution requires a DSCript.csproj.
Project("{FAE04EC0-301F-11D3-BF4B-00C04F79EFBC}") = "DSCript", "..\DSCript\DSCript.csproj", "{09C8AA4A-AFB8-4BDB-866B-B8C88D48D9EB}"

(It's not in the zip you've uploaded - there's only libDSC.dll.)

edit: got it compiled by adding libDSC.dll as a reference. But the exe crashes when dropping ps3split.fchunk onto it.
Where did you get the LuaSF from? (author is CarLuver69 as it seems)
## Post #11
- Username: brownyfifa
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 16, 2020 11:58 am
- Post datetime: 2020-03-18T13:10:33+00:00
- Post Title: Multiple LuaQ files help

[https://filebin.net/cs9k030b8iu9jh03](https://filebin.net/cs9k030b8iu9jh03)

above is the DCScript project

will need to use the --big argument on the fchunk otherwise it won't work.
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-18T18:58:17+00:00
- Post Title: Multiple LuaQ files help

Thanks! finally I got the LuaSF project compiled and working with ps3split.fchunk - but I had to use libDSC.dll from 2016 ).
## Post #13
- Username: brownyfifa
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 16, 2020 11:58 am
- Post datetime: 2020-03-18T22:15:13+00:00
- Post Title: Multiple LuaQ files help

haha awesome! Unfortunately it doesn't support big endian compiling  Would make modding a lot more flexible.
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-19T07:51:04+00:00
- Post Title: Multiple LuaQ files help

The problem with little endian/bigendian files is as this (from my experience):
you need a FULL format analysis, because you can't just "swap bytes".

Say, you've a little endian file (14 bytes) like 3412 99EFCDAB 0600 58454E544158. (last 6 bytes in ASCII: "XENTAX")
Could be word, DWORD, strlen word, string (6 bytes).

In big endian it's 1234 ABCDEF99 0006 58454E544158.

But what if the little endian file is meant to be DWORD, word,  strlen word, string (6 bytes)?
And you need to know where the string(s) to start.
So the analysis part of code which can handle the little endian file has to be rewritten on the base of the analysis to handle big endian.
