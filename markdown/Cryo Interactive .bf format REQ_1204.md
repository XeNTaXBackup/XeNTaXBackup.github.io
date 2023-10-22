## Post #1
- Username: liz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 25, 2005 4:25 am
- Post datetime: 2005-04-24T20:45:32+00:00
- Post Title: Cryo Interactive .bf format REQ

Hi,

Fantastic site for exploring game content!  

I really enjoy the music found on "Return to Mystery Island" and would like to put it on my iPod for workouts.  I looked at the data, and it seems to be a special format used by Cryo Interactive.  The contents are .ogg files.  I just don't know how to extract them.

I posted one of the smaller files (15mb!) for you to take a look if you're curious.

[http://www.planet.io/_archive/file_format/](http://www.planet.io/_archive/file_format/)

TIA!
Liz
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-25T11:51:07+00:00
- Post Title: Cryo Interactive .bf format REQ

Thanks for the archive - we are downloading it now and will take a look at it soon.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-25T14:01:06+00:00
- Post Title: Cryo Interactive .bf format REQ

I have figured out the format. It's not too difficult to write a plugin for. My DAMN mexscript would be able to do it, but it's bugged, or so I noticed.   

```
0000 - 0005    IDString    "CryoBF"
0024 - 0027    32-bit        Tail pointer (TP)
0028 - 0031    32-bit        Data start

TP - nnnn        32-bit       Number of directories

(entries) 

nnnn - nnn3    32-bit        Size of filename string
nnn4 - nnn4+  string        Filename (or directory name)
nnn etc.          32-bit        Type (1= dir, 2 = file)

If Type = 1 then the next 32-bit is the Number of Files in the directory
followed by File entries. 

If Type = 2 then it's a File entry and continues like:

nnn etc.           32-bit      File size
nnn etc.           32-bit      Unknown (0)
nnn etc.           32-bit      Relative File offset (from Data start) 


```


That's it.
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-25T22:39:40+00:00
- Post Title: Cryo Interactive .bf format REQ

I have also created a script for it, but it will require a new version of MultiEx.dll and this will also mean a new version of mc32.exe (to link to the new DLL). The script works though, and I heard the oggs. No tunes though. 
Just speech.
## Post #5
- Username: liz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 25, 2005 4:25 am
- Post datetime: 2005-04-26T07:35:40+00:00
- Post Title: Cryo Interactive .bf format REQ

Wow!

That looks great Mr.M!  It's nice to see somethings in life aren't always difficult 

I only uploaded the smallest file.  There's a 400mb that probably has the music in it.

I spent half-an-hour trying to ramp myself up on trying to extract these myself (great tutorial!).  Would it be easiest for me to wait until you do another release, though?

TIA!
