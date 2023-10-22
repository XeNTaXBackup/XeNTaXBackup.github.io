## Post #1
- Username: skytoast
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jan 31, 2010 6:12 pm
- Post datetime: 2010-02-14T11:23:42+00:00
- Post Title: Soul Calibur IV voice tracks

I was wondering if anyone can help extract voices from Soul Calibur IV (360).  I am able to get to the music but having difficulty with voices.   The files are packaged as AFS files but once extracted are either ADX or somethng similar .ad.   The BGM music adx files in bgm.afs playback fine.  However when I try to extract some of the adx files in voice.afs  I can hear the voice track but its garbled with noise.

Sample file: [http://www.sendspace.com/file/hmi10h](http://www.sendspace.com/file/hmi10h)

There is also a folder called "Voice" which also contain some encrypted dtx files but I havent been able to get anything useful out of these.  any ideas?
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-02-14T16:17:29+00:00
- Post Title: Soul Calibur IV voice tracks

It's encrypted ADX.  For future reference you can tell this by the 08 at offset 0x13, in unencrypted ADX that's 00.  I run it through guessadx and got the key:
-s 59ed -m 4679 -a 46c9

I've added support for it to [vgmstream](http://hcs64.com/vgmstream.html) r741, so it will now play this file (and probably the others) directly.  Or you can decrypt the files permanently with degod by giving that key on the command line.
## Post #3
- Username: skytoast
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jan 31, 2010 6:12 pm
- Post datetime: 2010-02-14T23:53:52+00:00
- Post Title: Soul Calibur IV voice tracks

Thank you so much for taking the time to look into this.  Works great!
## Post #4
- Username: andthen619
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 18, 2010 7:43 pm
- Post datetime: 2010-07-03T13:14:24+00:00
- Post Title: Soul Calibur IV voice tracks

any luck with replacing the voice files with your own voices.  can't seem to get it to work.  they are either silent or the game glitches.
