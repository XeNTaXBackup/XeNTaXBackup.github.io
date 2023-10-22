## Post #1
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-09T08:30:45+00:00
- Post Title: Mashed PIZ

Help extract Mashed PIZ archives
example attached   
thx
[LED.zip](https://xentaxbackup.github.io/file/428_LED.zip)
## Post #2
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-09T22:07:35+00:00
- Post Title: Mashed PIZ

Nobody can help me?  
Watto , Mr.Mouse
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-09-09T23:00:09+00:00
- Post Title: Mashed PIZ

Of course I will try to help my Russian friend
## Post #4
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-09T23:05:56+00:00
- Post Title: Mashed PIZ

> Reply from Mr.Mouse
>
> Of course I will try to help my Russian friend
I shall wait for a script or a plug-in
## Post #5
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-09-11T14:08:23+00:00
- Post Title: Mashed PIZ

This is the specs - will have a plugin or something in a few days.

```
| Mashed *.piz |
+--------------+

4 - Header ("PIZ" + null)
4 - Version (3)
4 - Number Of Files
2036 - null

// for each file
  116 - Filename (null)
  4 - File Offset
  4 - File Length
  4 - File ID?
  
X - null Padding to a multiple of 2048 bytes

// for each file
  X - File Data
  X - null Padding to a multiple of 2048 bytes)
```


WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #6
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-09-20T05:56:21+00:00
- Post Title: Mashed PIZ

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
[Plugin_PIZ_PIZ.zip](https://xentaxbackup.github.io/file/440_Plugin_PIZ_PIZ.zip)
## Post #7
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-20T08:03:56+00:00
- Post Title: Mashed PIZ

thx Watooo
## Post #8
- Username: kam15
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 10, 2016 6:53 am
- Post datetime: 2016-11-10T00:12:13+00:00
- Post Title: Mashed PIZ

hi guys, i am playing with my friends mashed(non fully loaded), and i ve a question.
is possible to move tracks, power ups and vehicles from fully loaded to previous version ? 
cheers & thanks for reply
