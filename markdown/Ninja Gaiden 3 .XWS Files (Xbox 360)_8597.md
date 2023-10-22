## Post #1
- Username: !!!!!
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 22, 2009 8:55 am
- Post datetime: 2012-03-20T05:47:23+00:00
- Post Title: Ninja Gaiden 3 .XWS Files (Xbox 360)

I can't figure out how to extract these XWS files. Here's the file that contains the BGM.

stream_bgm.xws
[http://www.mediafire.com/download.php?m2tpvm4a4ka3222](http://www.mediafire.com/download.php?m2tpvm4a4ka3222)
[http://www.mediafire.com/download.php?vcv462j90gwp7e2](http://www.mediafire.com/download.php?vcv462j90gwp7e2)
## Post #2
- Username: Layer
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Feb 19, 2011 5:53 am
- Post datetime: 2012-03-20T16:36:39+00:00
- Post Title: Ninja Gaiden 3 .XWS Files (Xbox 360)

It seems to be an atrac stream without a RiFF header.

Without an header for each BGM contained, it's a bit difficult to extract them.
## Post #3
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2012-03-20T22:18:31+00:00
- Post Title: Ninja Gaiden 3 .XWS Files (Xbox 360)

Xbox 360 primarily uses XMA for its audio.

And this game is no exception. It's headerless XMA at 44.1Hz

There are 96 filenames within the archive but there are only 90 XMA files.

And 4 of those XMAs are 10 seconds of silence.
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-03-21T01:56:22+00:00
- Post Title: Ninja Gaiden 3 .XWS Files (Xbox 360)

The audio is actually in an XWB container, You can find the magic DWORD DNBW under the additional JUNK data. Just delete the additional data, change ext to xwb and extract with unxwb.
## Post #5
- Username: MoriyaMug
- Rank: Banned
- Number of posts: 7
- Joined date: Sat Sep 11, 2010 12:03 am
- Post datetime: 2012-04-05T21:15:53+00:00
- Post Title: Ninja Gaiden 3 .XWS Files (Xbox 360)

I'm trying to convert these files to a format that I can work with, in order to compile a fan soundtrack, but I'm having no luck. I've used unxwb to extract the individual files, but I'm having no luck beyond there. ToWav isn't working on them. When I run the batch to convert everything in the folder, I get "ToWav (C) Xplorer 2k6-2k9" string, then nothing. It just stops and returns to the command prompt (or closes the window, if I just clicked on the batch). Can someone provide some advice, please?
## Post #6
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-04-05T22:00:44+00:00
- Post Title: Ninja Gaiden 3 .XWS Files (Xbox 360)

Use XMA_encode.exe witht his batch "for %%i in (*.xma) DO xmaencode /X  %%i.wav "%%i"
## Post #7
- Username: MoriyaMug
- Rank: Banned
- Number of posts: 7
- Joined date: Sat Sep 11, 2010 12:03 am
- Post datetime: 2012-04-06T01:36:06+00:00
- Post Title: Ninja Gaiden 3 .XWS Files (Xbox 360)

As always, OC, you are the man. Many thanks.
