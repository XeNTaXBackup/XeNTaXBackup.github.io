## Post #1
- Username: kimkalisto
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Apr 16, 2007 7:26 am
- Post datetime: 2007-08-03T00:00:20+00:00
- Post Title: Simpsons Hit And Run RSD Files

Can someone help me convert the music files from simpsons Hit And Run.

here is the header

```
00000010:c0 5d 00 00 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a    À]..************
00000020:2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a    ****************
00000030:2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a    ****************
00000040:2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a    ****************
00000050:2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a    ****************
00000060:2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a    ****************
00000070:2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a 2a       *************** 


```


Im guessing its some type of PCM not ogg like in scarface which is made by the same company.

Here is also a file attatchment.
[banjo_end_neg_b4.rar](https://xentaxbackup.github.io/file/1300_banjo_end_neg_b4.rar)
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-08-09T23:20:16+00:00
- Post Title: Simpsons Hit And Run RSD Files

I think it's a raw pcm, i remember the same data in the game Hulk, you can encode with ogg vorbis using raw format, ex:

oggenc --raw name.rsd
## Post #3
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2008-08-03T20:56:58+00:00
- Post Title: Simpsons Hit And Run RSD Files

Have you tried MFAudio ive sucessfully extracted some stuff from that game nothing really worth saving but i did like this machine sound the pin maker 5000 machine outside barney's bowl a rama, if you have the .RSD files from the archive youll need to open one up using MFAudio and you shouldnt need to mess with any settings like the interleave and offset settings now hit play and hopefully you will hear audio or music if you hear static then play around with the settings but some of those cannot be converted like short sounds, to get those you might want to just record them from your line in
