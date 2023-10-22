## Post #1
- Username: Plombo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 18, 2010 11:27 am
- Post datetime: 2013-07-23T19:25:54+00:00
- Post Title: [PC] Sega Genesis & Mega Drive Classics game format

Sega has a "Genesis & Mega Drive Classics" application that is used to play Genesis/Mega Drive games bought on Steam and/or the Amazon digital games store on Windows.  Each game is stored as a file with extension ".pak" and stored in the "data" subfolder of the Sega Classics folder.

From what I can tell, each of these files starts with the 10 bytes "50 53 43 44 71 89 53 12 00 00".  They seem to be compressed with something, as their sizes are smaller than regular Genesis ROMs, and they might be encrypted as well.  Scanning the .pak files with aluigi's signsrch tool shows nothing; scanning the executable SegaGenesisClassics.exe shows the following:

```
  --------------------------------------------
  000308e6 2639 LZSS (N 4096, F 18, T 2) [32.le.16&]
  00039dc8 1299 classical random incrementer 0x343FD 0x269EC3 [32.le.8&]
  0006c264 2545 anti-debug: IsDebuggerPresent [..17]
  0013d050 3032 PADDINGXXPADDING [..16]
  00146476 917  SSH RSA id-sha1 OBJ.ID. oiw(14) secsig(3) algorithms(2) 26 [..15]

```


Any help in determining the format would be appreciated.  If you're interested but don't have any of the Sega Classics games, they are available from Steam, Amazon, and Green Man Gaming for as little as $3 each, or in bundles that average $1 per game.
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-07-24T20:39:04+00:00
- Post Title: [PC] Sega Genesis & Mega Drive Classics game format

They encrypted with custom algo.
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-07-25T20:53:18+00:00
- Post Title: [PC] Sega Genesis & Mega Drive Classics game format

[http://aluigi.org/papers/bms/others/sega_classics.bms](http://aluigi.org/papers/bms/others/sega_classics.bms)
