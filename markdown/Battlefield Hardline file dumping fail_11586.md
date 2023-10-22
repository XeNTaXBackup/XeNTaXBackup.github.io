## Post #1
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2014-06-11T16:10:48+00:00
- Post Title: Battlefield Hardline file dumping fail

i used a dumper method for hardline and i get these errors

[http://www.bfeditor.org/forums/index.ph ... opic=15731](http://www.bfeditor.org/forums/index.php?showtopic=15731)
BF3-MOHWF dumper:

```
layout.toc
CommonChunks0.toc

Traceback (most recent call last):
  File "C:\Python27\dumper.py", line 417, in <module>
    main()
  File "C:\Python27\dumper.py", line 414, in main
    dump(fname,outputfolder)
  File "C:\Python27\dumper.py", line 201, in dump
    toc=sbtoc.Superbundle(tocName)
  File "C:\Python27\sbtoc.py", line 177, in __init__
    self.entry=Entry(toc)
  File "C:\Python27\sbtoc.py", line 90, in __init__
    raise Exception("Entry does not start with \x82 or (rare) \x87 byte. Position: "+str(toc.tell()))
Exception: Entry does not start with ‚ or (rare) ‡ byte. Position: 1
>>>
```

[http://www.bfeditor.org/forums/index.ph ... opic=15844](http://www.bfeditor.org/forums/index.php?showtopic=15844)
with the BF4 Dumper:

```
  File "C:\Python27\bf4dumper.py", line 258, in <module>
    if "tocRoot2" in locals(): dumpRoot(tocRoot2)
  File "C:\Python27\bf4dumper.py", line 248, in dumpRoot
    dump(fname,targetDirectory)
  File "C:\Python27\bf4dumper.py", line 196, in dump
    catEntry=cat[entry.sha1]
KeyError: '\x0b\x8e\xcb\x85V\xd5\xd1\x9c\xe05d\x16K\xcd\x97U[g#\x0b'
>>> 
```


anyone have any ideas?
## Post #2
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-06-13T20:48:05+00:00
- Post Title: Battlefield Hardline file dumping fail

> Reply from Rin
>
> i used a dumper method for hardline and i get these errors

http://www.bfeditor.org/forums/index.ph ... opic=15731
BF3-MOHWF dumper:
Code: Select all>>> 
layout.toc
CommonChunks0.toc

Traceback (most recent call last):
  File "C:\Python27\dumper.py", line 417, in <module>
    main()
  File "C:\Python27\dumper.py", line 414, in main
    dump(fname,outputfolder)
  File "C:\Python27\dumper.py", line 201, in dump
    toc=sbtoc.Superbundle(tocName)
  File "C:\Python27\sbtoc.py", line 177, in __init__
    self.entry=Entry(toc)
  File "C:\Python27\sbtoc.py", line 90, in __init__
    raise Exception("Entry does not start with \x82 or (rare) \x87 byte. Position: "+str(toc.tell()))
Exception: Entry does not start with ‚ or (rare) ‡ byte. Position: 1
>>>
http://www.bfeditor.org/forums/index.ph ... opic=15844
with the BF4 Dumper:
Code: Select allTraceback (most recent call last):
  File "C:\Python27\bf4dumper.py", line 258, in <module>
    if "tocRoot2" in locals(): dumpRoot(tocRoot2)
  File "C:\Python27\bf4dumper.py", line 248, in dumpRoot
    dump(fname,targetDirectory)
  File "C:\Python27\bf4dumper.py", line 196, in dump
    catEntry=cat[entry.sha1]
KeyError: '\x0b\x8e\xcb\x85V\xd5\xd1\x9c\xe05d\x16K\xcd\x97U[g#\x0b'
>>> 

anyone have any ideas?

I had a hell of a time with the python dumpers trying to get them to work at all.
I don't know what I did to fix it for myself, but I was getting those errors before with bf4 beta and moh:wf.
all I can say is that BF:Hardline beta extracts fine for me. make sure you have the latest scripts and dll from dropbox, overwrite every bit of the older scripts? I don't think it's been updated in a few months, but I made many small mistakes trying to get my setup working. first I used 64bit python, then I used 3.x, before realizing I needed 2.7.6+ then I updated the scripts but I only overwrote some of them and not all. 

It does work, it's just a pain sometimes to get there.
