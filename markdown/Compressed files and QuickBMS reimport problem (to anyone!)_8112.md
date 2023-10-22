## Post #1
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-23T22:04:29+00:00
- Post Title: Compressed files and QuickBMS reimport problem (to anyone!)

I post this thread here because often some people reported problems in reimporting compressed files via quickbms -r -w even if the original size of the modified file is the same (for example you modified one or no bytes).

as already explained the problem is not caused by quickbms but it's just a limitation of the various zlib/deflate open source libraries that are not much optimized for the compression ratio.
for example zlib has almost no optimization (worst results) while the one used in 7zip (advancecomp, default in quickbms) is better but still not enough.

note that I talk about the files compressed with zlib/deflate and NOT the other files, so I refer just to the modified files that have the same size of the original ones. ok?

as far as I know kzip [http://advsys.net/ken/utils.htm](http://advsys.net/ken/utils.htm) is one of the best and slowest tools for the deflate compression so from QuickBMS 0.5.5 (released just now) it's used automatically if the compressed file is too big.

so instead of giving you the usual error message about the file size now QuickBMS will automatically try to compress it with kzip.

everything is completely transparent to you except for a message that notifies the usage of this alternative method (because it's a work-around that consumes many resources and so it must be visible when used).

if you have had this problem in the past and you want to try it feel free to report your results and what you think.
this is the last chance because there are no other solutions except writing an extreme deflate compression algorithm by myself... and no I have no intention and capabilities for doing it :)

QuickBMS:
[http://quickbms.aluigi.org](http://quickbms.aluigi.org)
## Post #2
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-01-27T11:42:51+00:00
- Post Title: Compressed files and QuickBMS reimport problem (to anyone!)

I have a script:

```
comtype kzip_deflate_compress
get SIZE asize
get NAME filename
string NAME += ".zip"
clog NAME 0 SIZE 1000000
```


This works fine with deflate_compress or lzo1_compress, except with kzip_deflate_compress. I use QuickBMS 0.5.5.
The error:

```

Error: there is an error with the decompression
       the returned output size is negative (-1)
```


I just want to compress a simple file. How can I make this kzip compression work?
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-27T15:48:18+00:00
- Post Title: Compressed files and QuickBMS reimport problem (to anyone!)

solved in 0.5.6a, in short I wanted to force quickbms to use it only in reimport mode.
I forgot that instead it can be very useful also for stand-alone compressions.
## Post #4
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-01-27T16:08:30+00:00
- Post Title: Compressed files and QuickBMS reimport problem (to anyone!)

Now it try to compress the file, but crash in the meantime.
No error message, just an appcrash messagebox. I tried to use the earlier posted script.
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-27T17:35:29+00:00
- Post Title: Compressed files and QuickBMS reimport problem (to anyone!)

oh yeah sorry, it's the C compiler that breaks all the compatibility with the patch I apply to kzip.exe so I have opted for a precompiled patch.
try version 0.5.6c and sorry again for the troubles, I tried to solve the problem as fast as possible
## Post #6
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-01-27T17:38:31+00:00
- Post Title: Compressed files and QuickBMS reimport problem (to anyone!)

No problem. Thanks.
## Post #7
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2012-10-13T14:56:17+00:00
- Post Title: Compressed files and QuickBMS reimport problem (to anyone!)

I have few problems with this. I have game Rosemary running on Wintermute engine and i extracted all files from data.dcp archive. I did some modifications in items.items file and now this file is smaller than original, but quick bms shows me the informations that this file is bigger than original and it can't be reimported again, even with kzip method. Where did i do a mistake? I can't understand it 

I used this script [http://aluigi.altervista.org/papers/bms/wintermute.bms](http://aluigi.altervista.org/papers/bms/wintermute.bms)

Here are screens with original/modified file size and information that quick bms showed me when i tried reimported items.items file:
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-10-13T21:15:04+00:00
- Post Title: Compressed files and QuickBMS reimport problem (to anyone!)

that's normal, in short the original file was bigger but had less "entropy" than your current one.
in short the sequence of bytes in your new files is more complex and so it's not possible to compress it till a final size equal or minor than the compressed one of the original file.
## Post #9
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2012-10-14T10:52:32+00:00
- Post Title: Compressed files and QuickBMS reimport problem (to anyone!)

Is there any way to get through this? 

Even if i change few values in hex editor, i can't reimport files.
## Post #10
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-10-14T18:50:59+00:00
- Post Title: Compressed files and QuickBMS reimport problem (to anyone!)

QuickBMS already uses the best solution for the deflate compression so there is nothing else I can do.
## Post #11
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2012-10-14T19:33:52+00:00
- Post Title: Compressed files and QuickBMS reimport problem (to anyone!)

ok, i understand it.
Thank you for help. Maybe i'll find another solution. 


btw aluigi, i'm big fan of your scripts ;p
## Post #12
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-04-06T18:50:26+00:00
- Post Title: Compressed files and QuickBMS reimport problem (to anyone!)

In QuickBMS 0.5.18 I have implemented a better compression method that uses kzip combined with 2 other tools.
Additionally now I use kzip with the /b128 option that seems to give better results so if you had problems reimporting the XML files now they will work perfectly.

Enjoy :)
