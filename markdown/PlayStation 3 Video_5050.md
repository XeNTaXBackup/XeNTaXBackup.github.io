## Post #1
- Username: zerohp
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Sep 17, 2010 8:52 am
- Post datetime: 2010-09-17T02:13:32+00:00
- Post Title: PlayStation 3 Video

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-09-17T02:25:28+00:00
- Post Title: PlayStation 3 Video

The audio is headerless atrac3 and there is no working header that decodes these yet, it would be great if someone can write a working header.
## Post #3
- Username: zerohp
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Sep 17, 2010 8:52 am
- Post datetime: 2010-09-17T04:55:55+00:00
- Post Title: PlayStation 3 Video

If you have it, can you post the raw audio data?
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-09-17T16:09:44+00:00
- Post Title: PlayStation 3 Video

have what?
## Post #5
- Username: zerohp
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Sep 17, 2010 8:52 am
- Post datetime: 2010-09-17T17:16:27+00:00
- Post Title: PlayStation 3 Video

The raw audio file on its own, like I did with the video.
## Post #6
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-09-17T17:21:11+00:00
- Post Title: PlayStation 3 Video

yes i got what you just posted.

EDIT: the raw audio data you posted is headerless atrac3. i have never decoded it because there is no working header
## Post #7
- Username: zerohp
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Sep 17, 2010 8:52 am
- Post datetime: 2010-09-18T11:55:16+00:00
- Post Title: PlayStation 3 Video

I didn't post any raw audio data. I posted a fully muxed file containing audio data that shouldn't be over 1MB.
## Post #8
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-09-21T07:36:08+00:00
- Post Title: PlayStation 3 Video

You haven't demuxed any video stream. The original file should stay like this. The video stream starts at 0x800 btw. 
This seems like a PMF variant (Playstation Media File). PMF videos are used in PSP games and start with "PMF0041" (in hex), so this could be something like "Playstation Advanced Media File". The video is just an MPG stream, the audio seems to be ATRAC3+.
I'll take a look at how the pmf demuxer gets the audio out of the file and try to simulate this behaviour. I've worked with PSP games quite a bit, but still haven't figured out multichannel PMF, so it's not guaranteed that I'll succeed. Problem with AT3+ is that there's no player except KMPlayer that supports the format. You can only decode AT3+ files with Sony SoundForge (if they have an OMA/AA3 header) or Sonic Stage with HiMDRenderer (if they have a RIFF header).
Will post here if anything interesting happens...
## Post #9
- Username: Skyknight
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 23, 2010 1:26 am
- Post datetime: 2010-09-22T17:31:23+00:00
- Post Title: PlayStation 3 Video

The raw file in your zip can be viewed as a normal 264 stream file, I'll extract myself from your pam file directly to see what I get from it; also sound is undoubtly at3 but it can be even aac lc profile, ac3 pro or dts.

I'm doing my own research with this kind of pmf since I'm trying to extract MGS4, Heavenly Sword and Eternal Sonata, FF13 is pretty easy to extract so the challenge is with those namce and konami games since they use their own codec sometimes.

I'll post again in a while.

EDIT:  I extracted your pamf file myself into a celestial being codec file and muxed it into a normal mkv for playback, I did the same with yours anyway.

[http://www.mediafire.com/?amqr0bxwkjtil66](http://www.mediafire.com/?amqr0bxwkjtil66)

I'll work now with the at3 audio stream, all pam files are m2v and at3 originally but my software converts the m2v stream into h264 for playback.  Anyway, it works as I want it to.

Post again when finished with the sound.
## Post #10
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-09-22T20:40:47+00:00
- Post Title: PlayStation 3 Video

Very nice, awaiting on the atrac3.
## Post #11
- Username: zerohp
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Sep 17, 2010 8:52 am
- Post datetime: 2010-09-23T03:54:31+00:00
- Post Title: PlayStation 3 Video

> Reply from AlphaTwentyThree
>
> You haven't demuxed any video stream.
Erm I have, as evidenced by someone who used my raw data. I'll look into the audio info.

> Reply from Skyknight
>
> celestial being
Haha very funny. Leave the antics at rizon.
## Post #12
- Username: DPyro
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jul 12, 2010 3:06 am
- Post datetime: 2010-11-12T21:56:58+00:00
- Post Title: PlayStation 3 Video

Skyknight, can you post the app you used to extract the video. Only program I have right now is one that you can run on the PS3 itself to view the movies.
## Post #13
- Username: Skyknight
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 23, 2010 1:26 am
- Post datetime: 2010-12-06T11:52:36+00:00
- Post Title: PlayStation 3 Video

> Reply from DPyro
>
> Skyknight, can you post the app you used to extract the video. Only program I have right now is one that you can run on the PS3 itself to view the movies.

For the software, I can't release it yet but I can help you extract the video stream with MPlayer.

First you need to dl MPlayer and install it, [http://www.mplayerhq.hu/](http://www.mplayerhq.hu/)

Then you need to create a *.bat file with this commands inside the same directory of MPlayer

mplayer Opening.pam -ni -dumpvideo

Replace Opening.pam for the filename you want to extract.  (It works for both PSP and PS3)

It gives you a stream.dump file, if it's from a psp rename it to stream.264, if it's from a ps3 rename it to stream.mpg

Then mux the stream into mkv, since it's likely that the dumps doesn't have a correct header so mkvmerge fixes that.

-----------------------

And thanks to bigfoot for showing that graphic, it helps.
## Post #14
- Username: bigboot
- Rank: Banned
- Number of posts: 8
- Joined date: Thu Sep 16, 2010 10:10 pm
- Post datetime: 2010-12-12T07:47:03+00:00
- Post Title: PlayStation 3 Video

> Reply from Skyknight
>
> And thanks to bigfoot for showing that graphic, it helps.
...........
## Post #15
- Username: jackkill
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 10, 2010 8:02 am
- Post datetime: 2010-12-22T23:16:46+00:00
- Post Title: PlayStation 3 Video

here is an addition to Skyknight very helpfull post.
rename the ps3 stream file to .m2ts and it will play natively on pc with powerdvd (i use version 10 ultra) 
here is an update :
rename the files extension to .m2t and demux them to .m2ts with tsMuxeR.
this fixes them and make them compatible with encoders.
I used my schools sony vegas to encode them to wmv very high quality (got 19MB for a file that was 60MB with no apparent difference in quality !.
Good luck to everyone
## Post #16
- Username: hyndai
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Jun 04, 2008 4:55 am
- Post datetime: 2010-12-29T22:41:51+00:00
- Post Title: Re: PlayStation 3 Video

I found this doc perhaps usefull for make a tools for extracting audio from *.pam files.
[http://wiki.multimedia.cx/index.php?title=ATRAC3plus](http://wiki.multimedia.cx/index.php?title=ATRAC3plus)

and sample [http://samples.mplayerhq.hu/A-codecs/ATRAC3%2b/](http://samples.mplayerhq.hu/A-codecs/ATRAC3%2B/)
## Post #17
- Username: Animus777
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Dec 11, 2010 12:24 am
- Post datetime: 2011-02-03T20:08:57+00:00
- Post Title: Re: PlayStation 3 Video

Well, I have 30+ Gigs of video in wmp format from Final Fantasy XIII (ps3 version). Video plays with MPC but no sound
## Post #18
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-05T00:46:23+00:00
- Post Title: Re: PlayStation 3 Video

thanks
## Post #19
- Username: sprayer
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Sep 10, 2010 2:09 pm
- Post datetime: 2011-02-10T13:44:16+00:00
- Post Title: Re: PlayStation 3 Video

how to convert back to wmp/pam video? i want to resize video in game
## Post #20
- Username: Skyknight
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 23, 2010 1:26 am
- Post datetime: 2011-02-27T18:06:35+00:00
- Post Title: Re: PlayStation 3 Video

An update with not much success anyway

I'm able to extract or rip some pamf files to both streams now with my software.

[KOF12.at3](http://www.fileserve.com/file/RKgjkmx)
[KOF12.aa3](http://www.fileserve.com/file/CF79kUv)
[KOF12.264](http://www.fileserve.com/file/qaYhUqP)

For KOF12.264 just put it into an mkv or m2ts with MKVmerge or TSMuxer.
The problem is even when the at3 is converted to aa3, all I get in Sound Forge is a blank 6ch audio file.
The at3 file has no conversion so it should be ATRACT3+.

I'm getting problems converting this lpcm, maybe someone can help.
[http://www.fileserve.com/file/t9pRRjh](http://www.fileserve.com/file/t9pRRjh)
It's from ACE R game
## Post #21
- Username: Skyknight
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 23, 2010 1:26 am
- Post datetime: 2011-03-06T21:28:37+00:00
- Post Title: Re: PlayStation 3 Video

> Reply from zerohp
>
> Skyknight wrote:celestial being
Haha very funny. Leave the antics at rizon.

If my software is an antic, sorry.

Anyway, take your antic:

[Video Stream extracted from your PAM file in h264 format at Fileserve](http://www.fileserve.com/file/pEaPs2T)
[Video Stream extracted from your PAM file in h264 format at Mediafire](http://www.mediafire.com/download.php?71fw1rvvoimpo2b)

[JPN Audio track extracted from your PAM file in AT3/AT3+ format at Fileserve](http://www.fileserve.com/file/FcRaegD)
[JPN Audio track extracted from your PAM file in AT3/AT3+ format at Mediafire](http://www.mediafire.com/download.php?apxca9m7yif9vdo)

[ENG Audio track extracted from your PAM file in AT3/AT3+ format at Fileserve](http://www.fileserve.com/file/JCmKnJz)
[ENG Audio track extracted from your PAM file in AT3/AT3+ format at Mediafire](http://www.mediafire.com/download.php?vu4i1uaanw8h6h1)

[JPN Audio track converted from the AT3/AT3+ file to WAV format at Fileserve](http://www.fileserve.com/file/mNnwW6r)
[JPN Audio track converted from the AT3/AT3+ file to WAV format at Mediafire](http://www.mediafire.com/download.php?9hmo8vhvonrkr0h)

[ENG Audio track converted from the AT3/AT3+ file to WAV format at Fileserve](http://www.fileserve.com/file/J2pEKKs)
[ENG Audio track converted from the AT3/AT3+ file to WAV format at Mediafire](http://www.mediafire.com/download.php?ew3it34cijuiev2)

[KOF12.MKV at Fileserve](http://www.fileserve.com/file/mvpJHWM)
[KOF12.MKV at Mediafire](http://www.mediafire.com/download.php?d3hn49xclj4a05h)

I'm sorry for being like that, just I don't like the hate I already receive at rizon to get it here too.

And admin can close the topic since it's fulfilled, although zerohp shold have the last word about it.

Thanks for letting me help you.
