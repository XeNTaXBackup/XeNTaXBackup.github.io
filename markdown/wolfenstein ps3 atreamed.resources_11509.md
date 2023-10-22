## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2014-05-15T20:00:24+00:00
- Post Title: wolfenstein ps3 atreamed.resources

Can anyone look at this file? Uses the same structure as rage but still haven't figured out how to link the info inside gameresources with audio files inside the streamed bank.

Thanks
## Post #2
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-05-21T03:42:42+00:00
- Post Title: wolfenstein ps3 atreamed.resources

pc version are multiple OGGs audio files
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2014-05-21T05:34:14+00:00
- Post Title: wolfenstein ps3 atreamed.resources

just looked at it.

anyway to extract the ogg files with the linked strings from the index chunk files?
## Post #4
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-05-21T06:01:50+00:00
- Post Title: wolfenstein ps3 atreamed.resources

Sample format? Or are the files big
## Post #5
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-05-21T23:15:44+00:00
- Post Title: wolfenstein ps3 atreamed.resources

ambient sounds, effect sounds , music , german voices and others are located in chunkXX.resources files(all compressed), the index files contains names and address of the assets. (wav format for sounds)

header: 03 53 45 52 00 00 00 00 00 00 00 00 00 00 00 00 (.SER..........)



models , animations , skel , etc are in md6  and derivatives formats
textures compressed inside *.pages files with header 04 99 33 77 00 04 00 00 00 00 00 00 0B 00 00 00 55 55 15 00 02 00 00 00

localized language are vorbis ogg files inside *.streamed files (the index files for this streamed files are shared between all index files)

I will try to upload some chunk files
## Post #6
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2014-05-22T00:39:47+00:00
- Post Title: wolfenstein ps3 atreamed.resources

I think most of the music is in the streamed archive in OGG vorbis. did a raw extraction but with no filenames i cant verify if all music is there.
## Post #7
- Username: killerpepo
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Mar 23, 2011 2:22 pm
- Post datetime: 2014-05-22T13:36:09+00:00
- Post Title: wolfenstein ps3 atreamed.resources

Is there any way to extract the textures from the .pages ? What compression algorithm is used ?
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-22T14:01:08+00:00
- Post Title: wolfenstein ps3 atreamed.resources

Share chunk11.index and chunk11.resources
## Post #9
- Username: killerpepo
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Mar 23, 2011 2:22 pm
- Post datetime: 2014-05-22T14:18:09+00:00
- Post Title: wolfenstein ps3 atreamed.resources

> Reply from Ekey
>
> Share chunk11.index and chunk11.resources

Here it is 

[http://www.sendspace.com/file/yl5v1j](http://www.sendspace.com/file/yl5v1j)
## Post #10
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-22T15:54:10+00:00
- Post Title: wolfenstein ps3 atreamed.resources

Game only for x64 right?
## Post #11
- Username: killerpepo
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Mar 23, 2011 2:22 pm
- Post datetime: 2014-05-22T16:23:15+00:00
- Post Title: wolfenstein ps3 atreamed.resources

> Reply from Ekey
>
> Game only for x64 right?

Unfortunately yes    , The game has only one .exe and called "WolfNewOrder_x64.exe"
## Post #12
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-22T16:58:42+00:00
- Post Title: wolfenstein ps3 atreamed.resources

Sad.
## Post #13
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-05-22T22:21:13+00:00
- Post Title: wolfenstein ps3 atreamed.resources

about graphics : game run under openGL
## Post #14
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2014-05-28T05:38:59+00:00
- Post Title: wolfenstein ps3 atreamed.resources

Any progress on this?
## Post #15
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-05-28T15:51:23+00:00
- Post Title: wolfenstein ps3 atreamed.resources

> Reply from OrangeC
>
> Any progress on this?

It was already solved. [viewtopic.php?f=35&t=11529](http://forum.xentax.com/viewtopic.php?f=35&t=11529)
## Post #16
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-07-07T06:39:19+00:00
- Post Title: Re: wolfenstein ps3 atreamed.resources

[out]
