## Post #1
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-12-20T17:17:57+00:00
- Post Title: Audio formats

Well, we've got a thread for working on encrypted and compressed formats, so I figured, why not audio (and video and binary, in a minute)? Not that I know how to decipher these formats - I know even less than Mr.Mouse and friendsofwatto...
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2005-12-20T17:47:20+00:00
- Post Title: Audio formats

Excellent idea.
I admit that I have started to watch more deeply the audio formats (algorithms) only in the last days so I'm still a newbie in this field.
Let's start with some links.

Xbox ADPCM:
Used for some of the audio data contained in the XWB archives available mainly on the Xbox console for games like Unreal Championship, Psychonauts and Conan
Code:
C: [http://aluigi.altervista.org/papers.htm#others-file](http://aluigi.altervista.org/papers.htm#others-file)
Delphi: uXboxAdpcmDecoder.pas in Psychonauts Explorer
[http://quick.mixnmojo.com/software.php#source](http://quick.mixnmojo.com/software.php#source)
(I don't know what is the latest official homepage of the code), 
Windows codec:[download.php?id=205](http://forum.xentax.com/download.php?id=205)
(no source code and unknown author)
## Post #3
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2006-01-04T12:58:37+00:00
- Post Title: Audio formats

hello

need software for play or convert this files 

wav files included in fsb archive in games coldfear,american chopper 2(ps2) and evil dead regeneration
[uk_computer_warning_15.zip](https://xentaxbackup.github.io/file/556_uk_computer_warning_15.zip)
## Post #4
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-04T13:13:53+00:00
- Post Title: Audio formats

These files will not play because they are compressed. (all FSB3 archives compress the files) . I do not know the compression algorithm, so these files are currently unusable. I would imagine that it would be a common compression format though, as FSB3 archives are in a variety of different games, and also different consoles.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #5
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2006-01-04T14:38:05+00:00
- Post Title: Audio formats

thanks mr watto for comment 

but opened above games with fsb plugins game extractor and script multiex
## Post #6
- Username: Sly
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Aug 04, 2004 6:19 am
- Post datetime: 2006-01-04T14:38:32+00:00
- Post Title: Audio formats

2sajad
If you want I can write decoder for you
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-04T17:03:23+00:00
- Post Title: Audio formats

> Reply from Sly
>
> 2sajad
If you want I can write decoder for you

Why don't you just tell all of us first what the method for encoding is, and THEN write a decoder for him? I have seen you lurk at this forum for a long time (you may be invisible to others, but not to me) and you refuse to help people here. Tread lightly, friend.
## Post #8
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2006-01-04T19:53:20+00:00
- Post Title: Audio formats

to sly

ok, if you can write decoder

not problem
## Post #9
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-04T20:10:15+00:00
- Post Title: Audio formats

> Reply from sajad
>
> to sly

ok, if you can write decoder

not problem

Indeed, no problem. But we would kindly urge Sly to include a description of the encoding method, as that is what we do here.
## Post #10
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-04T21:45:27+00:00
- Post Title: Audio formats

Sajad: GE and MexCom can unpack the files, but they are still compressed. That is why they don't work.

Sly: Yes, we welcome your assistance on this matter, and hope that you will share your knowledge with us.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2006-01-05T20:52:20+00:00
- Post Title: Audio formats

> Reply from Mr.Mouse
>
> 
Why don't you just tell all of us first what the method for encoding is, and THEN write a decoder for him? I have seen you lurk at this forum for a long time (you may be invisible to others, but not to me) and you refuse to help people here. Tread lightly, friend.

Agree with you.
Personally I hate everything is closed source, and sharing the knowledge is the best thing we have.
Nobody likes to do the same job 2 or more times so I don't understand what evil mind could prefer that other people redo the same things again while he has already made it... that's totally senseless moreover in a community!
## Post #12
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2006-01-06T18:29:07+00:00
- Post Title: Audio formats

anybody know how can mib sound ps2 files convert or play
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2006-01-07T18:43:01+00:00
- Post Title: Audio formats

The ffmpeg project has support to various ADPCM formats, XA included:

[http://ffmpeg.sourceforge.net/index.php](http://ffmpeg.sourceforge.net/index.php)

if this audio uses the XA codec (possible) it will work.

Actually I'm not aware of programs which implement this library in a raw mode, I'm too lazy at the moment for doing this thing since the ffmpeg library is not super-mega-simple to use.
## Post #14
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-02-20T14:32:00+00:00
- Post Title: Audio formats

Hi somebody knows where i can found a audio conversor created by fmod?
I know it pack. but i don't know how to reconvert to pcm.

Any idea?
## Post #15
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-02-20T22:21:05+00:00
- Post Title: Audio formats

I tried the web [http://www.fmod.org](http://www.fmod.org), the creators of the file systeme fsb and packers audio.

Somebody can download the api (freeware) and create a plugin for winamp or similar.

The plugin info it's in: examples/plugin_dev/

Thanks!
## Post #16
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-02-24T11:25:18+00:00
- Post Title: 

No body know how to, or can do?
