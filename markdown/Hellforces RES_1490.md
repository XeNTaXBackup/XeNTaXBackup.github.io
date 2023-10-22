## Post #1
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-09T08:29:21+00:00
- Post Title: Hellforces RES

Help extract   
example attached
thx
[pshaders.zip](https://xentaxbackup.github.io/file/427_pshaders.zip)
## Post #2
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-09T22:08:18+00:00
- Post Title: Hellforces RES

Nobody can help me?  
Watto , Mr.Mouse
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-09-09T23:01:55+00:00
- Post Title: Hellforces RES

patience, my friend
## Post #4
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-09T23:04:22+00:00
- Post Title: Hellforces RES

I suffer
## Post #5
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-09-11T14:07:23+00:00
- Post Title: Hellforces RES

Hi mate,

Sorry for the delay - we do look at all the files that people give us, we just need some time - we have other things to do as well so it might take a few days.

These are the specs for this format - I will probably have a plugin or script for this format in a few days because I am busy with university.

```
| Hellforces *.res |
+------------------+

// ZLib Compression is used

4 - Number Of Files

// for each file (136 bytes for each entry)
  128 - Filename (null-terminated, filled with junk)
  4 - File Offset
  4 - Compressed File Length

// for each file
  4 - Decompressed File Length
  X - Compressed File Data
```


WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #6
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-09-20T05:55:30+00:00
- Post Title: Hellforces RES

OK, I have attached a Game Extractor plugin for this archive - I'm still pretty busy though so I don't have a MexCom script, and I havn't put this plugin into a Game Extractor update yet.

The plugin should work if you unzip it into your "GameExtractor/Plugins" directory, or the "GameExtractor/" directory. If not, you can do the following...

1. Unzip the attachment
2. Open GameExtractor.jar in a zip program like WinZip
3. Put the new plugin into the zip
4. Save it (as GameExtractor.jar , NOT GameExtractor.zip)
5. Run Game Extractor.

Good luck - when I get some more time I will try to get some scripts done and a new Game Extractor update.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[Plugin_RES_9.zip](https://xentaxbackup.github.io/file/439_Plugin_RES_9.zip)
## Post #7
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-20T08:04:29+00:00
- Post Title: Hellforces RES

thx Watooo
