## Post #1
- Username: Barnaby
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Dec 15, 2009 12:41 am
- Post datetime: 2010-03-13T12:05:59+00:00
- Post Title: Modern Warfare 2 *.pak

Here is the first and last 10mb of the 1.3gb file. 

[http://www.speedyshare.com/files/214015 ... e1.pak.001](http://www.speedyshare.com/files/21401521/packfile1.pak.001)

[http://www.speedyshare.com/files/214015 ... e1.pak.134](http://www.speedyshare.com/files/21401597/packfile1.pak.134)

Thanks
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-03-13T13:45:33+00:00
- Post Title: Modern Warfare 2 *.pak

uhmm I don't see a table with the informations about the offsets/size of the files.

in the following thread was uploaded the imagefile3.pak file and when I tested it at that time I noticed the same thing:
[viewtopic.php?f=21&t=3820](http://forum.xentax.com/viewtopic.php?f=21&t=3820)

it's like if this is only a raw container and the list of names/offsets/sizes is located somewhere else in another file, indeed we can see the various wav files ("RIFF") but their offsets and/or their names/extensions are not available inside these parts of the archive.

I have found the list of codmw2 files on internet but I don't see one that could be an index file because they are all ff and bik, so I don't have other ideas.
## Post #3
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2010-03-13T14:27:52+00:00
- Post Title: Modern Warfare 2 *.pak

There are four image files, one of which contains the table for the files.
## Post #4
- Username: Barnaby
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Dec 15, 2009 12:41 am
- Post datetime: 2010-03-13T17:21:11+00:00
- Post Title: Modern Warfare 2 *.pak

There were two .xex files where as all the others were bik, ff, and pak.

Here they are:

[http://www.speedyshare.com/files/21407515/default.xex](http://www.speedyshare.com/files/21407515/default.xex)
[http://www.speedyshare.com/files/214075 ... ult_mp.xex](http://www.speedyshare.com/files/21407584/default_mp.xex)
## Post #5
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-04-15T16:17:29+00:00
- Post Title: Modern Warfare 2 *.pak

Here's a simple scanner that extracts the xma files from the sound archive. Nothing elaborate, but at least it calculates the correct file sizes out of the header.  (Thus it can be used for any archive to extract wave files- just change the extension to ".wav")
BTW, I didn't search for "RIFF" because sometimes that string accidentially occurs inside the wave stream. The probability that "WAVEfmt" occurs is pretty much zero.

```
   FindLoc OFFSET STRING "WAVEfmt" 0 ""
   if OFFSET != ""
      math OFFSET -= 8
      goto OFFSET
      FindLoc DATA STRING "data" 0 ""
      math DATA += 4
      goto DATA
      get SSIZE long
      savepos HEADER
      math HEADER -= OFFSET
      set SIZE HEADER
      math SIZE += SSIZE
      get NAME basename
      string NAME += "_"
      string NAME += i
      string NAME += ".wav"
      log NAME OFFSET SIZE
   else
      cleanexit
   endif
next i
```
## Post #6
- Username: Barnaby
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Dec 15, 2009 12:41 am
- Post datetime: 2010-04-15T16:18:50+00:00
- Post Title: Modern Warfare 2 *.pak

Thanks a million mate.
