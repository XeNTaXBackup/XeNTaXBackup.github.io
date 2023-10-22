## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-10-29T14:57:58+00:00
- Post Title: Star Ocean Anamnesis

here is a sample vertex and face buffer from this game. If someone can figure out how faces are stored I can post a tool to download and decrypt the games files.
[2.7z](https://xentaxbackup.github.io/file/13504_2.7z)
## Post #2
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2017-11-11T13:18:31+00:00
- Post Title: Star Ocean Anamnesis

"Can we STOP this cruel game! And allow the boy to keep ONE shred of dignity!
For God's sake, I can't STAND to see him in all this pain!!
Let him figure out this index data!! Is it so bad to see somebody happy?!
So just help him out!! For the LOVE OF GOD, let the boy  figure this out!!
Good Lord!!"
## Post #3
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-11-12T12:44:46+00:00
- Post Title: Star Ocean Anamnesis

this is taken from ida.
[https://pastebin.com/G32yPxrs](https://pastebin.com/G32yPxrs)
[https://pastebin.com/BmML8Ekj](https://pastebin.com/BmML8Ekj)
## Post #4
- Username: Mrtest
- Rank: advanced
- Number of posts: 43
- Joined date: Wed Aug 24, 2011 3:11 am
- Post datetime: 2017-11-14T13:59:01+00:00
- Post Title: Star Ocean Anamnesis

> Reply from chrrox
>
> If someone can figure out how faces are stored I can post a tool to download and decrypt the games files.
It would be great. The same data is used in Heaven x Inferno. It would be nice extracting models and out of there.
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-11-15T01:22:53+00:00
- Post Title: Star Ocean Anamnesis

These might be more relevant
[https://pastebin.com/cNuTgtfD](https://pastebin.com/cNuTgtfD)

[https://pastebin.com/0KPaBCP8](https://pastebin.com/0KPaBCP8)
## Post #6
- Username: staroceanfan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 06, 2018 3:43 pm
- Post datetime: 2018-04-06T07:46:38+00:00
- Post Title: Star Ocean Anamnesis

Someone has succesfully extract a model from the game

[https://twitter.com/zeroetanaru/status/ ... 8233964544](https://twitter.com/zeroetanaru/status/958716078233964544)
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-04-07T11:34:20+00:00
- Post Title: Star Ocean Anamnesis

I can 'rip' a model from this game using ninja ripper.
does this person share any of the ways they ripped it?
there are 2 - 3 compression that need to be solved to rip them without just dumping raw data from ram.
## Post #8
- Username: Neinthousand
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 16, 2018 7:27 am
- Post datetime: 2018-04-16T10:59:57+00:00
- Post Title: Star Ocean Anamnesis

> Reply from chrrox
>
> I can 'rip' a model from this game using ninja ripper.
does this person share any of the ways they ripped it?
there are 2 - 3 compression that need to be solved to rip them without just dumping raw data from ram.

I ask him about it, he only told me that he used Ninja ripper. It seems he doesn't know about getting that data without that program
## Post #9
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2018-04-27T02:27:29+00:00
- Post Title: Star Ocean Anamnesis

Star Ocean Anamnesis Eoe Event scene, ps3 Eoe has come up.

Is this still impossible to rip or is it possible to use emulator etc.
## Post #10
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-07-26T10:44:15+00:00
- Post Title: Star Ocean Anamnesis

I gave this a try, but no luck. I am fairly convinced that these methods are used (or a variation) : [Article1](https://fgiesen.wordpress.com/2013/12/14/simple-lossless-index-buffer-compression/), [Article2](http://conorstokes.github.io/graphics/2014/09/28/vertex-cache-optimised-index-buffer-compression) . Code samples are available too, but I just couldn't make it work with the indices of this game.

From the files I checked the minimum values in the index lists were like 30, 40. So probably high watermark encoding, on top of compression? I am not sure though.

I ended up getting the indices using NinjaRipper. Requires a bit of manual work, but not that bad. I will be posting some characters time to time on my deviantart, in case anyone is interested. I started out with Evelysse : [Model Download](https://www.deviantart.com/akderebur/art/Star-Ocean-Anamnesis-Evelysse-Original-Rig-756288684)
## Post #11
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2018-07-26T12:25:02+00:00
- Post Title: Star Ocean Anamnesis

> Reply from akderebur
>
> I gave this a try, but no luck. I am fairly convinced that these methods are used (or a variation) : Article1, Article2 . Code samples are available too, but I just couldn't make it work with the indices of this game.

From the files I checked the minimum values in the index lists were like 30, 40. So probably high watermark encoding, on top of compression? I am not sure though.

I ended up getting the indices using NinjaRipper. Requires a bit of manual work, but not that bad. I will be posting some characters time to time on my deviantart, in case anyone is interested. I started out with Evelysse : Model Download

wow finally something from this game! thx man please make more
