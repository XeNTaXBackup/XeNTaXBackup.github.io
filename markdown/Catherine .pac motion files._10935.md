## Post #1
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-11-07T23:04:11+00:00
- Post Title: Catherine .pac motion files.

Hi huys, now that noesis supports gamebryo files, I was wondering if it's possible to unpack the .pac files coming with the carachter files:

[http://www.mediafire.com/?525y46d5mroyn1e](http://www.mediafire.com/?525y46d5mroyn1e)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-08T17:48:59+00:00
- Post Title: Catherine .pac motion files.

If you extract the nif  from c03_00_0910.pac (addr 0x1300-0x623F) for example and try to load it with nifskope 1.1.3 it's showing up lots of warnings kinda below and nothing to be seen in the render window:

```
""warning: block 1 (NiConstFloatEvaluator) not inserted!"" 
""device position incorrect after block number 1 (NiConstFloatEvaluator) at 0x1607 ended at 0x1607 (expected 0x1623)"" 
""warning: block 2 (NiFloatEvaluator) not inserted!"" 
...
```
## Post #3
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-11-09T00:30:56+00:00
- Post Title: Catherine .pac motion files.

> Reply from shakotay2
>
> If you extract the nif  from c03_00_0910.pac (addr 0x1300-0x623F) for example and try to load it with nifskope 1.1.3 it's showing up lots of warnings kinda below and nothing to be seen in the render window:
Code: Select all""device position incorrect after block number 0 (NiSequenceData) at 0x1117 ended at 0x1117 (expected 0x1607)"" 
""warning: block 1 (NiConstFloatEvaluator) not inserted!"" 
""device position incorrect after block number 1 (NiConstFloatEvaluator) at 0x1607 ended at 0x1607 (expected 0x1623)"" 
""warning: block 2 (NiFloatEvaluator) not inserted!"" 
...

It's not actually nif files but kf or kfm files. At least you gave me the hint how to exctract the files using a hex editor and tried with noesis without any result. Anyways thanks for the help
## Post #4
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-11-09T15:19:28+00:00
- Post Title: Catherine .pac motion files.

They would work in Noesis, but they all use bspline evaluators, which the Noesis nif script doesn't currently support. I'll get to it eventually.
## Post #5
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-11-09T16:51:59+00:00
- Post Title: Catherine .pac motion files.

Actually, bsplines look like they're mostly used for animating extraneous stuff. These animations play fine in Noesis.

Edit: Well, main characters have most of their major bones animated by bsplines, so you won't so movement on those. Too bad. Here's a Noesis script to extract the pac files: [http://code.google.com/p/noesis-plugins ... ine_pac.py](http://code.google.com/p/noesis-plugins-official/source/browse/trunk/Rich/fmt_catherine_pac.py)
## Post #6
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-11-09T20:17:42+00:00
- Post Title: Catherine .pac motion files.

Too bad but thanks for trying
