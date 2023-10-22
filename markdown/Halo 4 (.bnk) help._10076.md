## Post #1
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-01-24T03:41:37+00:00
- Post Title: Halo 4 (.bnk) help.

Hello folks, first I'm still to new to this, but I've had a lot of success so far. After extracting the contents of soundbank.pck I've been able to convert a majority of xma .bnk files by adding a stereo header to it and then convert it using ToWav. However some files do not convert properly and I can't figure out why. 

Halo 4 uses four formats XMA, Wwise OGG, xWMA and xWMA Pro. Below are two samples I cannot get to properly convert.

[http://www.fileden.com/files/2007/3/7/861170/Hsamp.zip](http://www.fileden.com/files/2007/3/7/861170/Hsamp.zip) 

Both samples does not contain any xma values, but it does have the header RIFX Wavefmt. Ravioli scanner says it's a .wav file but I'm assuming it is wrong and that it is actually a wwise ogg, but I cannot get it to convert with ww2ogg. I also tried xWMAEncode without any success (The file is not PCM or xWMA). 

I'm quite certain it can be converted, I'm just not doing it right, can anyone help me with this problem and tell me how to correctly convert these bnk files?

Thank you for your time.
## Post #2
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-02-07T02:36:05+00:00
- Post Title: Halo 4 (.bnk) help.

A lot of views but no replies. Nobody has anything?
## Post #3
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2013-02-07T17:50:42+00:00
- Post Title: Halo 4 (.bnk) help.

0x4f6b8297 doesn't work because it has multiple audio files in it. Some of the files are truncated though. Split them at the RIFX header and then run them through ww2ogg.

The 2nd file is a mono XMA file identified by the flag "FC038000". The audio data starts at 0x1000 which is 6 bytes before the flag. Trim that off, put on the proper mono XMA header and convert it with ToWAV.
## Post #4
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-02-07T21:50:11+00:00
- Post Title: Halo 4 (.bnk) help.

Thank you so much, I was able to convert the files with no problem. 

I now have one other problem, I cannot unpack the contents of soundstream.pck. Do you know of any script that will unpack it? 

I was able to unpack soundbank.pck using the ADPK script Alpha23 posted, however it doesn't work on larger .pck files. I know it's off topic but I appreciate any info. 

Thank you again.
## Post #5
- Username: LordNazo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 02, 2016 6:08 am
- Post datetime: 2016-01-02T01:01:59+00:00
- Post Title: Halo 4 (.bnk) help.

I already extracted (virtually) all of the audio from Halo 4 (from both discs).
