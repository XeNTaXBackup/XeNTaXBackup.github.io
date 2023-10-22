## Post #1
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-07-10T21:34:25+00:00
- Post Title: wave file codec detection

I have a wave file with a strange format. Even vlc can't play it.
[http://uploaded.to/?id=t97sw1](http://uploaded.to/?id=t97sw1) (.wav)

The only program that plays it, is MPC:
[http://uploaded.to/?id=xuzl8k](http://uploaded.to/?id=xuzl8k) (.wav + MPC)

Is someone able to identify the used codec?
Is this somehow convertible to a more common format?
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-07-12T22:03:04+00:00
- Post Title: wave file codec detection

Oups

Edited: i tried and the codec it's IAC2
You can play/reconvert it with mplayer if you dont' use linux search celtic druids win32 bin compilations or compile yourself

Have a look/download here:
[http://tirnanog.fate.jp/mirror/mplayer/](http://tirnanog.fate.jp/mirror/mplayer/)

If you use linux you know..  [http://www.mplayerhq.org](http://www.mplayerhq.org)
## Post #3
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-07-12T22:17:14+00:00
- Post Title: wave file codec detection

With MPC I mean Media Player Classic ( not the standard windows one  )
## Post #4
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-07-12T22:21:03+00:00
- Post Title: wave file codec detection

Look the post of above  

> AUDIO: 22050 Hz, 2 ch, s16le, 88.2 kbit/12.50% (ratio: 11025->88200)
>
> Selected audio codec: [iac25] afm: acm (Indeo audio)
## Post #5
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-07-12T22:29:13+00:00
- Post Title: wave file codec detection

can't find celtic druid stuff via Google
## Post #6
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-07-12T22:56:56+00:00
- Post Title: wave file codec detection

You tried the link of above?
[http://tirnanog.fate.jp/mirror/mplayer/](http://tirnanog.fate.jp/mirror/mplayer/)
## Post #7
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-07-13T06:41:26+00:00
- Post Title: wave file codec detection

mencoder tells me that video stream is mandatory. Doesn't convert it.
## Post #8
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-07-13T14:05:37+00:00
- Post Title: wave file codec detection

Get this
[ftp://ftp.sac.sk/pub/sac/sound/acmst210.zip](ftp://ftp.sac.sk/pub/sac/sound/acmst210.zip)
This program uses the acm's audio installed in your system, install it and grab the wav, and sure you can convert to any other audio
## Post #9
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-07-13T14:51:05+00:00
- Post Title: wave file codec detection

Converted mp3 only plays for a second or so and then is silence.
## Post #10
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-07-13T15:12:27+00:00
- Post Title: wave file codec detection

Okay no problem   
Get mplayer and use this

```

```


In this case the reconversion it's a PCM wav 

Example from your attachment:

```

```


I hope now you can play this
## Post #11
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-07-13T15:51:30+00:00
- Post Title: wave file codec detection

Yeah this works. Thanks!
