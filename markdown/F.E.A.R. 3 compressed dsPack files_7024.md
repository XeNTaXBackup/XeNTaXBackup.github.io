## Post #1
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-07-20T12:42:45+00:00
- Post Title: F.E.A.R. 3 compressed dsPack files

hi,
this file from original release of the game. there is 2 different header for files.
resources\Localized\Audio\English.dsPack file: 
```
2066676D5A5A0108 :  fgmZZ..
```

other files in resources\ has 
```
6D67662008015A5A : mgf ..ZZ
```
 . there is I think there is only little endian and big endian difference.
and example file:
[DOWNLOAD sample preload.dsPack file](http://www.mediafire.com/?hdpz3bbht1h8tfl)
## Post #2
- Username: bugmenotty
- Rank: Banned
- Number of posts: 10
- Joined date: Wed Mar 16, 2011 6:26 pm
- Post datetime: 2012-01-16T21:09:51+00:00
- Post Title: F.E.A.R. 3 compressed dsPack files

I can't believe no one has managed to create an extractor for the game. I checked out english.dspack and found the file listing at offset 0x2506D6. The archive contains over 2000 uncompressed mp3-files with wave headers (160kbps, mono, 48khz). The same goes for audio.dspack. I extracted one file manually with a hex editor and it plays fine. 

I checked out resource.dspack and that one seems to be compressed. The end of the file seems to contain the dictionary, at least the many word fragments I found give me the impression. I'm not knowledgeable enough to identify the compression algorithm, but may be someone can take it from here and finally decipher these files.
## Post #3
- Username: bugmenotty
- Rank: Banned
- Number of posts: 10
- Joined date: Wed Mar 16, 2011 6:26 pm
- Post datetime: 2012-01-22T10:14:31+00:00
- Post Title: F.E.A.R. 3 compressed dsPack files

Funny that no one seems to be able to extract the uncompressed archives. Well, I wrote my own extractor in the meantime so never mind.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-22T11:41:40+00:00
- Post Title: F.E.A.R. 3 compressed dsPack files

some time ago I wrote a work-in-progress script for extracting the uncompressed files from F3AR so I have just replaced the clog command with a log one (after all if I don't know the algorithm I can do nothing so extract them compressed) for allowing it to work:
[http://aluigi.org/papers/bms/f3ar_prebuild.bms](http://aluigi.org/papers/bms/f3ar_prebuild.bms)
## Post #5
- Username: bugmenotty
- Rank: Banned
- Number of posts: 10
- Joined date: Wed Mar 16, 2011 6:26 pm
- Post datetime: 2012-01-22T12:28:35+00:00
- Post Title: F.E.A.R. 3 compressed dsPack files

I tried both of your Fear 3 scripts on the retail version and not a single one extracts. On audio.dspack the extraction of crc.map errors out with the following message:

"Error: the specific offset can't be reached"

Since the audio-archives are not compressed, there's not much to figure out. I already have the files extracted with generic filenames. Now all I need to do is to read the names and directory structure from the archive.
## Post #6
- Username: prudislav
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 13, 2010 6:48 am
- Post datetime: 2012-02-16T16:50:16+00:00
- Post Title: F.E.A.R. 3 compressed dsPack files

still nothing?
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-16T17:42:01+00:00
- Post Title: F.E.A.R. 3 compressed dsPack files

Maybe bugmenotty would like to share his source since it works?
## Post #8
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2012-02-21T03:15:00+00:00
- Post Title: F.E.A.R. 3 compressed dsPack files

If you read, he extracted the audio files. (uncompressed ones) any wave/mp3 scanner does that just fine.
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-21T03:25:35+00:00
- Post Title: F.E.A.R. 3 compressed dsPack files

Didn't read his second post. thought he meant it was easy and was surprised that no one has figured it out.
## Post #10
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-03-04T21:09:12+00:00
- Post Title: F.E.A.R. 3 compressed dsPack files

I have seen no threads related to this argument on encode.ru.
anyway I have doubts about someone there who would like to spend time on this algorithm without even having a precompiled code to check (game + exact location of the algorithm)

about the nickname banning I don't know the policy here but I understand the frustration of being obligated to register anywhere (forums and bug trackers) only to say one thing.
## Post #11
- Username: Akramma
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Nov 12, 2018 3:43 am
- Post datetime: 2020-05-15T18:56:57+00:00
- Post Title: F.E.A.R. 3 compressed dsPack files

Did you guys extract all the sounds from the Audio file? I would like to get the multiplayer voicelines
## Post #12
- Username: ZachFett
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Mar 17, 2020 5:18 pm
- Post datetime: 2020-09-26T01:34:07+00:00
- Post Title: F.E.A.R. 3 compressed dsPack files

> Reply from Akramma ↑Sat May 16, 2020 2:56 am at Sat May 16, 2020 2:56 am
>
> 
Did you guys extract all the sounds from the Audio file? I would like to get the multiplayer voicelines

Do you still need these? I successfully extracted them with a program I found called "Game Extractor".
