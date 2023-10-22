## Post #1
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2010-02-01T14:45:10+00:00
- Post Title: Question: What to upload and how?

Hey to all,

Sorry about the post being in the wrong section (if it is, please do move it as seen fit).

Anyhow, I have a few archives which I would like to upload but the problem is they're large. I recall being told to upload the first and last 10MB of the archives. Was wondering if anyone could help as to how to do it properly.

Thanks in advance.
## Post #2
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2010-02-01T18:58:51+00:00
- Post Title: Question: What to upload and how?

you can split them with winrar into 10s parts and upload each of them separately ...
## Post #3
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2010-02-01T19:27:01+00:00
- Post Title: Question: What to upload and how?

Download Watto's Filecutter from here:

[http://www.watto.org/program/vb.html](http://www.watto.org/program/vb.html)

In the line where it says "Archive To Analyze" click "Select" and choose the file you want to be analyzed.

In the next line it says "Output archive name", here you can rename the name of the output file or change the path where it gets saved. Best thing is to leave the standard path which is chosen automatically.

In the third line it says "Amount of data to copy", click on the arrow to open the drop down menu and choose "2MBs".

Now you only have to click on "Create Analysis Archive".

After the program finished cutting the important parts of the file, close the programm and upload the archive the program created to sendpace.com
## Post #4
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2010-02-02T08:36:34+00:00
- Post Title: Question: What to upload and how?

The file cutter is working fine, however all the options you just said don't exist for me. The only thing I have is "Start Byte", "End Byte" and "Outputname".

Also, I'm unable to get the last 10MB of the file for some reason. I type in the last value of the file and subtract 10MB from it hoping it would generate the file, but nothing. It doesn't generate anything.

The first 10MB is fine.

Any advice?
## Post #5
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-02-02T10:07:26+00:00
- Post Title: Question: What to upload and how?

well there should be filecutters that do all you say. What I have done is basically go in to a hex editor and just copy ALOT of bytes and paste into a new document, then I copy ALOT of bytes from end and paste into new document, this is back to basics and not optimal but works
## Post #6
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2010-02-02T10:56:11+00:00
- Post Title: Question: What to upload and how?

> Reply from AceAngel
>
> The file cutter is working fine, however all the options you just said don't exist for me. The only thing I have is "Start Byte", "End Byte" and "Outputname".

Also, I'm unable to get the last 10MB of the file for some reason. I type in the last value of the file and subtract 10MB from it hoping it would generate the file, but nothing. It doesn't generate anything.

The first 10MB is fine.

Any advice?

Maybe we use a different version or so. Here's the one I use, maybe it works now.
And I think that 2MB should be enough, I always cut out 2MB and so far everyone was able to help me.
[Wattos File Cutter.rar](https://xentaxbackup.github.io/file/2762_Wattos File Cutter.rar)
## Post #7
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2010-02-02T11:16:31+00:00
- Post Title: Question: What to upload and how?

Ah, thanks. This one is working fine. Thank you very much my good Sir.
## Post #8
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2010-02-02T12:17:42+00:00
- Post Title: Question: What to upload and how?

> Reply from AceAngel
>
> Ah, thanks. This one is working fine. Thank you very much my good Sir.

No problem. That's why we all are here on Xentax, isn't it?
## Post #9
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2010-02-03T11:00:41+00:00
- Post Title: Question: What to upload and how?

> Reply from AceAngel
>
> Hey to all,

Sorry about the post being in the wrong section (if it is, please do move it as seen fit).

Anyhow, I have a few archives which I would like to upload but the problem is they're large. I recall being told to upload the first and last 10MB of the archives. Was wondering if anyone could help as to how to do it properly.

Thanks in advance.

oooh sorry ! i couldn't understand your question properly !
now i know what you want !
you can do this work with quickbms so easy in an alternative way ...

```
# author Fereydoon Shekofte
# powered by QuickBMS
# http://aluigi.org/papers.htm#quickbms

get size ASIZE
log head 0 10000000
math size - 10000000
log tail size 10000000
```


even you can use it for batch process ..
