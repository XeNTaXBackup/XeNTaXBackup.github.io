## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-03-21T23:56:14+00:00
- Post Title: Devil May Cry HD Collection FSB IMA ADPCM help

[http://www.sendspace.com/file/q9zl97](http://www.sendspace.com/file/q9zl97)

Need help decoding this particular fsb file. Towav,fsbext,vlc player and other programs will not decode it properly and just produces static. Fsbext tells me it might be Xbox ADPCM audio, but still no luck.
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-03-27T21:24:29+00:00
- Post Title: Devil May Cry HD Collection FSB IMA ADPCM help

Anyone?
## Post #3
- Username: marlborox
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Apr 09, 2011 10:03 am
- Post datetime: 2012-03-28T17:26:32+00:00
- Post Title: Devil May Cry HD Collection FSB IMA ADPCM help

i know the dmc1 & dmc2 fsb files also produce static when converted with towav but if extracted with fsbext, the output files converted with towav play flawlessly, but that doesn't appear to not be the case for this file but i was looking for other dmc3 fsb files to compare but i can't see them on the disc or in the zip files, are they embedded in other files so i can compare... i don't know much but any help is better than nothing right  (i also have the jap version if that makes any difference but i wouldn't have thought so)
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-03-28T18:34:54+00:00
- Post Title: Devil May Cry HD Collection FSB IMA ADPCM help

They ar just mixed around in other fsb banks.
## Post #5
- Username: marlborox
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Apr 09, 2011 10:03 am
- Post datetime: 2012-03-28T18:45:05+00:00
- Post Title: Devil May Cry HD Collection FSB IMA ADPCM help

I'll have a quick lookie, can't think of what the difference would be as fsbext says they are all the same format, so maybe it's just a case of mucking around with replacing a header that towav understands, hopefully anyway as unlike silent hill, i do want the music from this game hehe
## Post #6
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-03-28T21:00:41+00:00
- Post Title: Devil May Cry HD Collection FSB IMA ADPCM help

I found the rest of dmc3 music. Its in a zip archive in the media folder of the disc and instead of fsb files it is OGG.
## Post #7
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-04-01T04:07:51+00:00
- Post Title: Devil May Cry HD Collection FSB IMA ADPCM help

The file you uploaded is an Xbox ADPCM stream but the stream start is wrong. Correct stream start is at 0x1f0. Just delete the header and add a new one. I can't explain why the stream start is wrong.
