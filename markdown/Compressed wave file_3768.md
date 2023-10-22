## Post #1
- Username: simple
- Rank: beginner
- Number of posts: 28
- Joined date: Sat Sep 29, 2007 6:52 am
- Post datetime: 2009-10-07T15:48:13+00:00
- Post Title: Compressed wave file?

Hi,

I have had some trouble playing some wave files, I can hear the music but there are also noise and static-ish within the music as well... The file was extracted from an iPhone IPA application... 

Any one have any idea?...I have also upload the sample file if anyone can help me out...

[XAC_ADVANCED_MSTR.wav (976.14 KB)](http://www.slingfile.com/audio/B3kmZwCryF)

If you have trouble with the link above try [this one](http://www.slingfile.com/file/214756-B3kmZwCryF.html) instead...
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2009-10-18T21:44:20+00:00
- Post Title: Compressed wave file?

Pretty weird, everything seems to obey the general form of MS IMA, but the indexes aren't in the normal 0 to 88 range of IMA: the second frame has 0xB3 for the right channel, and the fourth frame has 0xA3 for the left and 0x64 for the right.  So it seems that whatever ADPCM is in use here isn't exactly IMA.  Don't know how to approach it beyond that, I don't think the iPhone has anything but IMA built in, so it's probably in software; if you want I might look at the executable and see if I can spot the decoder.

---
Ah, figured it out. It is normal MS IMA, however *all* bytes in the stream are nibble reversed.

---
Here's a little program to reverse the whole data chunk of a RIFF WAVE:
[http://hcs64.com/files/ipa_reverse_nibbles00.zip](http://hcs64.com/files/ipa_reverse_nibbles00.zip)
makes your file playable.
## Post #3
- Username: simple
- Rank: beginner
- Number of posts: 28
- Joined date: Sat Sep 29, 2007 6:52 am
- Post datetime: 2009-10-19T06:10:22+00:00
- Post Title: Compressed wave file?

Thanks hcs. 

All the waves come out playable after going through the convertor.



EDIT: I just realized this particular file doesn't work after going through the convertor...

Can you help me check again what's wrong?...

[http://www.slingfile.com/file/228190-hiLY5PMQlx.html](http://www.slingfile.com/file/228190-hiLY5PMQlx.html)

Thanks again hcs
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-10-22T18:17:25+00:00
- Post Title: Compressed wave file?

Nice work hcs!
## Post #5
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2009-10-23T02:35:30+00:00
- Post Title: Compressed wave file?

oops, didn't realize that it was posted out here, I already gave simple the little utility for that file (MPEG 1 layer 3 with all but first 4 bytes nibble-swapped) to simple via PM, here it is for anyone else:
[http://hcs64.com/files/mpeg_reverse_nibbles00.zip](http://hcs64.com/files/mpeg_reverse_nibbles00.zip)
Despite the name it doesn't know anything about MPEG, just reverses all but first 4 bytes.
