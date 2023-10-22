## Post #1
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-18T12:24:12+00:00
- Post Title: Learn To Speak application archive

This is particularly directed to Mr Mouse, but anyone else who might be able to help is welcome.

Someone I know sent me an archive from a program called Learn To Speak French that he wanted me to figure out. I am having some real problems though because the files and the directory seem to be interwoven, and furthermore the file data seems to be in a different order to the directory.

This is what I have got so far...

```
| Learn To Speak French *.trl |
+-----------------------------+

// Directories have FileLength=0

8 - Hash?
16 - null
4 - Unknown
4 - Unknown
4 - Unknown (6)
8 - null
4 - Padding Size? (256)
4 - Unknown (1)
4 - null
4 - Padding Multiple (4096)
4 - Number of Files? (200)
4 - Unknown (37)
4 - Unknown
4 - Unknown (2)

// for each file
  4 - Group ID
  
// for (256)
  4 - File IDs? (kinda incremental from 1, some are all 255's)

// for each file (128-bytes per entry)
  64 - Filename (null-terminated) (unicode text)
  2 - Unknown
  1 - Entry Type (5=Root Directory, 1=Directory, 2=File)
  1 - Unknown (0/1)
  52 - Unknown Data
  4 - Group ID?
  4 - File Length
  4 - null
  
// for each file in this directory
  if (file){
    X - File Data
    X - null Padding to a multiple of 4096 bytes
    }
  else if (folder){
    // for (2)
      128 - File Entry (as above - ie repeat from // for each file)
    }
```


So the way I was assuming it to be read is that you would first read the directory, and then following that would be all the file data and sub-directory entries for those files. This would explain the interwoven file data. An example, if the main directory has the following entries...

File Entry
Sub-Directory Entry
File Entry

Then I would expect that following those entries would be the file data for file 1, the 128-byte entry for the Sub-Directory, and the file data for file 2.

This is kinda how it works, however the files in the directory seem to be out of order. For example, even though the example above goes File,Dir,File - the following data could actually be File,File,Dir or Dir,File,File , etc. Also, I cannot seem to determine how many files are in a sub directory, so I don't know when to stop.

This is really confusing and frustrating. I am kinda hoping that someone can shed some light onto where I am going wrong - its got me totally baffled.

You can grab the sample snippets at [http://www.watto.org/xzistenz/ltsf.zip](http://www.watto.org/xzistenz/ltsf.zip) . Thanks to all that help.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #2
- Username: Sly
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Aug 04, 2004 6:19 am
- Post datetime: 2005-12-18T12:39:47+00:00
- Post Title: Learn To Speak application archive

It's a standart Microsoft Compound Document aka OLE2 Storage files.
There are some libs in the i-net for reading/writing this files.
## Post #3
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-19T10:39:34+00:00
- Post Title: Learn To Speak application archive

Wow, excellent - thanks for your help! I will have a look at it a bit more now - but it looks great so far.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
