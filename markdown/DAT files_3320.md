## Post #1
- Username: peshkohacka
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jan 22, 2009 6:20 am
- Post datetime: 2009-01-23T21:11:34+00:00
- Post Title: DAT files

Hi, as a new here i don't know would this be against the rules, but here's a few files that i can get to understand them at all - some are encrypted (i guess), some not. However they all start with VBDFILE, so if you have any idea for the format please help:

```
http://www.rapidspread.com/file.jsp?id=zqocu4exd2
```


The archive contains a few samples (this are full-size files) and a program that i think is using it.
## Post #2
- Username: asmxtx
- Rank: veteran
- Number of posts: 127
- Joined date: Mon Jun 09, 2008 5:32 am
- Post datetime: 2009-01-25T20:48:04+00:00
- Post Title: DAT files

I don't know this program but it seems to be commercial malware:

[http://www.file.net/process/ctxfispi.exe.html](http://www.file.net/process/ctxfispi.exe.html)

For me it seems these data-files contain some registry data converted in a special way. Besides it appears to be some kind of copy-protection. Maybe the programmers decided to not to burden the Windows-registry-database with these values because they are never changed and used for read-only purposes only. Maybe the programmers utilize an internal self-made library or a bypass not to touch the registry.

I think this program runs as a such called "service".
If you want to remove it, you should use invoke the commandline program "SC.EXE", which is located in the SYSTEM32-folder. This program can handle all available services in WinXP (be careful).
For example, if you want to remove the unnecessary NVIDIA graphic card service, enter:

```
sc delete nvsvc
```


Then this bloody thing will never run again.

Or to list all services into a text file, enter:

```
sc query >xyz.txt
```
## Post #3
- Username: peshkohacka
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jan 22, 2009 6:20 am
- Post datetime: 2009-01-26T10:22:52+00:00
- Post Title: DAT files

Its too bad, but its not malware, its the main back of the creative's drivers, and this .dat's if i i'm right contain info about features of the soundcard itself
