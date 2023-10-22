## Post #1
- Username: JPulowski
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 29, 2010 5:39 am
- Post datetime: 2012-06-07T03:53:59+00:00
- Post Title: Max Payne 3 .awc audio files

So the latest version of [OpenIV](http://www.openiv.com/) just released. I've succesfully extracted audio files. The extension is .awc. I've tried some simple ways to decode the file such as importing it as raw data on Audacity. But no luck. My purpose is archiving the audio files especially the main theme variations. I'm posting a sample, if anyone is able to decode it I'd appreciate it. 

[http://lh.rs/NJF4xRKWilBX](http://lh.rs/NJF4xRKWilBX) (theme_loop.awc)
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-06-07T07:29:51+00:00
- Post Title: Max Payne 3 .awc audio files

the audio is ima adpcm as far as I know but headerless.
## Post #3
- Username: kangmin
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Jun 17, 2012 4:38 pm
- Post datetime: 2012-06-17T08:43:27+00:00
- Post Title: Max Payne 3 .awc audio files

bumping this thread :/ I too need help on decoding the .awc files... it really annoys me .. taking too much time to configure this out!
## Post #4
- Username: Bob7k
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Sep 14, 2010 5:06 pm
- Post datetime: 2012-06-17T09:02:52+00:00
- Post Title: Max Payne 3 .awc audio files

Ive gotten some really crackly results by opening it under RAW as "VOX ADPCM", and inputting the rate at 22050hz, but its so crackly and poppy. Wonder if anyone can use this information to clean up the sounds a little.
## Post #5
- Username: kangmin
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Jun 17, 2012 4:38 pm
- Post datetime: 2012-06-17T10:06:33+00:00
- Post Title: Max Payne 3 .awc audio files

^ have the same problem .. badly wanted the bullet time sfx!!
## Post #6
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-06-17T23:09:41+00:00
- Post Title: Max Payne 3 .awc audio files

I'm working on it...
## Post #7
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2012-06-17T23:40:15+00:00
- Post Title: Max Payne 3 .awc audio files

> Reply from kangmin
>
> ^ have the same problem .. badly wanted the bullet time sfx!!
weapon sounds are just raw 44khz pcm data. they arent compressed to adpcm like the music.
## Post #8
- Username: Bob7k
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Sep 14, 2010 5:06 pm
- Post datetime: 2012-06-17T23:54:48+00:00
- Post Title: Max Payne 3 .awc audio files

Has anyone worked out a converter yet?
## Post #9
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-06-18T01:13:06+00:00
- Post Title: Max Payne 3 .awc audio files

> Reply from AlphaTwentyThree
>
> I'm working on it...

Thanks alpha!
## Post #10
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-06-18T14:20:03+00:00
- Post Title: Max Payne 3 .awc audio files

> Reply from Pepper
>
> kangmin wrote:^ have the same problem .. badly wanted the bullet time sfx!!
weapon sounds are just raw 44khz pcm data. they arent compressed to adpcm like the music.
Yes, but of course the header is different and the files can't be played right away. Working on that, too.
## Post #11
- Username: Bob7k
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Sep 14, 2010 5:06 pm
- Post datetime: 2012-06-22T12:42:42+00:00
- Post Title: Max Payne 3 .awc audio files

Any progress on some sort of converter or cleanup tool?
## Post #12
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-06-22T13:43:28+00:00
- Post Title: Max Payne 3 .awc audio files

Tried all kinds of codecs, but somehow I didn't come up with anything. Anyone got an idea about the interleave? Maybe it changes all the time (maybe that's what the table each 512kB is for?).
Any help on this is appreciated.
## Post #13
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-06-22T15:06:27+00:00
- Post Title: Max Payne 3 .awc audio files

Alpha you might want to contact this guy.

[http://openiv.com/](http://openiv.com/)

He might have an idea of this format.
## Post #14
- Username: GooD
- Rank: beginner
- Number of posts: 29
- Joined date: Sat May 03, 2008 5:07 pm
- Post datetime: 2012-07-28T21:37:00+00:00
- Post Title: Max Payne 3 .awc audio files

New OpenIV 1.1 is released - [http://openiv.com/?p=677](http://openiv.com/?p=677)
Now it is able to play and export audio (*.awc) to WAVe files.
## Post #15
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-07-28T22:38:48+00:00
- Post Title: Max Payne 3 .awc audio files

SWEEEEET!!

Will try it out


Thanks!!
## Post #16
- Username: nitoiviorel
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Oct 07, 2011 6:37 pm
- Post datetime: 2012-07-29T18:25:22+00:00
- Post Title: Re: Max Payne 3 .awc audio files

It works but OpenIV decode in bad quality.I heard many scratches and pops .i think because have only 32.000 hz. I try recode to 48 000 but heard the same noises.
## Post #17
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-07-29T22:13:45+00:00
- Post Title: Re: Max Payne 3 .awc audio files

Thats because the original sample rate is 32hz. Its even in the files header.
## Post #18
- Username: nitoiviorel
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Oct 07, 2011 6:37 pm
- Post datetime: 2012-07-31T06:14:30+00:00
- Post Title: Re: Max Payne 3 .awc audio files

Now i have another question:
How can i extract music from Max payne 2?
Extension is .ras file
I search on google for ras extractor but nowhere found.

Hey come on,nobody reply me?
