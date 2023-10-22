## Post #1
- Username: Raik
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Jul 17, 2015 7:51 am
- Post datetime: 2015-09-22T23:58:35+00:00
- Post Title: Missing on Lost Island (ADPCM Variant)

Hello

I need help to get this kind of ADPCM tracks working. I have tried different headers but i was not successful. I have thought it would be the MS ADPCM Codec but am still not sure. I have added two .dat files and the exe to this archive Pack.zip (52.99MB): [https://www.sendspace.com/file/31srxd](https://www.sendspace.com/file/31srxd)

It looks like the stream starts offset E8, sampling rate 22050 offset D4, stereo for the music.dat file. If this codec is well know then i need only working headers.

Thanks
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-09-23T16:21:58+00:00
- Post Title: Missing on Lost Island (ADPCM Variant)

Looking at those 0200 0800 0000DEAF chunks, I must suppose its IMA ADPCM. Also I see IMA table inside of the EXE.
## Post #3
- Username: Raik
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Jul 17, 2015 7:51 am
- Post datetime: 2015-09-23T19:15:24+00:00
- Post Title: Missing on Lost Island (ADPCM Variant)

thx do you think that we have here the classic IMA ADPCM codec? I have tried some headers but without luck or is it another special codec?
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-09-23T19:20:45+00:00
- Post Title: Missing on Lost Island (ADPCM Variant)

Found it here: 

[http://sourceforge.net/p/freecnc/git/ci ... format.txt](http://sourceforge.net/p/freecnc/git/ci/444bf40d9c8391ecb2f8d56a3e0c4b54b30ef4ea/tree/doc/tech/aud_format.txt)

maybe its westwood custom codec, but it must be very close to classic
## Post #5
- Username: Raik
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Jul 17, 2015 7:51 am
- Post datetime: 2015-11-06T12:39:06+00:00
- Post Title: Missing on Lost Island (ADPCM Variant)

Finally i had some time to look again into these tracks. You are completely right. It is westwoods IMA Codec. Its very simple to get these tracks playable because the header is valid. You nee only to delete all date before the sampling rate 22050 offset D4 and save this file as AUD like the old C&C Audiofiles. Finally you can use Foobar to play this track. Thx for your hint daemon1

bye
