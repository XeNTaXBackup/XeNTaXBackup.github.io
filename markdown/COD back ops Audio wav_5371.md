## Post #1
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2010-11-10T13:53:28+00:00
- Post Title: COD back ops Audio wav

i have no more ideas, i was thinking about thaht is any kind of wav, but still headers are missing

[http://www.xup.in/dl,42146062/mus_theat ... ore_l.wav/](http://www.xup.in/dl,42146062/mus_theatre_underscore_l.wav/)
## Post #2
- Username: Barnaby
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Dec 15, 2009 12:41 am
- Post datetime: 2010-11-10T17:20:06+00:00
- Post Title: COD back ops Audio wav

This uses headerless adpcm. Could be ms adpcm not decodable yet tho.
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-11-10T17:32:08+00:00
- Post Title: COD back ops Audio wav

Its ms adpcm. genh doesn't work but i think aplha might make a ms adpcm header script
## Post #4
- Username: bxaimc
- Rank: advanced
- Number of posts: 78
- Joined date: Mon May 10, 2010 3:54 am
- Post datetime: 2010-11-12T03:47:20+00:00
- Post Title: COD back ops Audio wav

GENH is a bit of a hastle to work with on MS ADPCM but it can be done. You just need to plug in the right settings. If any small input is wrong, the whole thing doesn't work.
## Post #5
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-11-12T04:17:21+00:00
- Post Title: COD back ops Audio wav

how can one find the interleave value in ms adpcm?
## Post #6
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2010-11-13T13:39:50+00:00
- Post Title: COD back ops Audio wav

any news?
## Post #7
- Username: bxaimc
- Rank: advanced
- Number of posts: 78
- Joined date: Mon May 10, 2010 3:54 am
- Post datetime: 2010-11-13T14:01:31+00:00
- Post Title: COD back ops Audio wav

Wait a min........the file you uploaded clearly has a header.........People please....I've been seeing this for a long time. If you don't see magic bytes in a header such as a word, it doesn't mean it's headerless (or if it doesn't have that blasted RIFF word). You could see that this has a frequency and file size embedded at the beginning.
## Post #8
- Username: bloodshotlol
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 11, 2010 1:12 pm
- Post datetime: 2010-11-21T01:23:48+00:00
- Post Title: COD back ops Audio wav

if anyone can tell me how to decrypt these sounds files successfully i am willing to send you some money through paypal
## Post #9
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-11-21T02:36:28+00:00
- Post Title: COD back ops Audio wav

[http://www.sendspace.com/file/d78oxi](http://www.sendspace.com/file/d78oxi)

Here is a msadpcm header that i took from world at war, a bit unorthodox but works until a script can be made.

just delete everthing before 0x830 and paste before it.

play with any player , your audio editor might give you chunk and internal filesize warnings but ignore that it decodes the file perfectly, not sure about the loop points though
## Post #10
- Username: bloodshotlol
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 11, 2010 1:12 pm
- Post datetime: 2010-11-21T03:50:16+00:00
- Post Title: COD back ops Audio wav

> Reply from OrangeC
>
> http://www.sendspace.com/file/d78oxi

Here is a msadpcm header that i took from world at war, a bit unorthodox but works until a script can be made.

just delete everthing before 0x830 and paste before it.

play with any player , your audio editor might give you chunk and internal filesize warnings but ignore that it decodes the file perfectly, not sure about the loop points though

thanks a lot!

but what audio editor would  you suggest? atm I'm using goldwave and it does not seem to work :/
## Post #11
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-11-21T13:11:42+00:00
- Post Title: COD back ops Audio wav

How does it not work? are you sure your pasting the header right?
## Post #12
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2010-11-21T13:17:21+00:00
- Post Title: COD back ops Audio wav

> Reply from OrangeC
>
> How does it not work? are you sure your pasting the header right?

its works not for all files but for the most


tip "copy /b header.hex file.wav outout.wav"
## Post #13
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-11-21T14:04:52+00:00
- Post Title: COD back ops Audio wav

Elaborate further, i still don't understand what you mean.

Make sure to adjust the channel count if the file is mono.
## Post #14
- Username: bloodshotlol
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 11, 2010 1:12 pm
- Post datetime: 2010-11-21T14:10:01+00:00
- Post Title: COD back ops Audio wav

> Reply from OrangeC
>
> Elaborate further, i still don't understand what you mean.

Make sure to adjust the channel count if the file is mono.

I'm kind of a noob when it comes to this stuff 

[http://img84.imageshack.us/img84/140/erroriv.jpg](http://img84.imageshack.us/img84/140/erroriv.jpg)
## Post #15
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-11-21T14:11:09+00:00
- Post Title: COD back ops Audio wav

do you have the MS adpcm codec installed?
## Post #16
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2010-11-21T14:14:59+00:00
- Post Title: Re: COD back ops Audio wav

he have shista or 7 so its installed normal, i think its better when he upload us one of thes wavs
## Post #17
- Username: bloodshotlol
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 11, 2010 1:12 pm
- Post datetime: 2010-11-21T14:22:51+00:00
- Post Title: Re: COD back ops Audio wav

> Reply from Cryptonia
>
> he have shista or 7 so its installed normal, i think its better when he upload us one of thes wavs

i have Windows 7
## Post #18
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2010-11-21T14:31:13+00:00
- Post Title: Re: COD back ops Audio wav

well try this [http://www.chip.de/downloads/K-Lite-Meg ... 00451.html](http://www.chip.de/downloads/K-Lite-Mega-Codec-Pack_23300451.html)
## Post #19
- Username: bloodshotlol
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 11, 2010 1:12 pm
- Post datetime: 2010-11-22T01:16:35+00:00
- Post Title: Re: COD back ops Audio wav

so what program do you guys suggest i use to do this?
## Post #20
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2010-11-24T02:59:46+00:00
- Post Title: Re: COD back ops Audio wav

are you sure you have the adpcm codec installed correctly?
