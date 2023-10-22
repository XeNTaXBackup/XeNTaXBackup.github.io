## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-11-28T16:47:55+00:00
- Post Title: Headhunter (Dreamcast) - ADPCM stream

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: mauzerX
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jul 01, 2010 8:48 pm
- Post datetime: 2010-11-28T19:59:56+00:00
- Post Title: Headhunter (Dreamcast) - ADPCM stream

try Genh for Yamaha AICA 4bit ADPCM with this settings
Header skip:0x10
frequency: 44100
interleave:0x1
Channels:2
No loops
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-11-28T23:48:49+00:00
- Post Title: Headhunter (Dreamcast) - ADPCM stream

> Reply from mauzerX
>
> try Genh for Yamaha AICA 4bit ADPCM with this settings
Header skip:0x10
frequency: 44100
interleave:0x1
Channels:2
No loops
Cool, thanks!  Haven't had this codec yet... Do you know how the header should look like in order for vgmstream to play the files? I don't like those generic headers.
## Post #4
- Username: mauzerX
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jul 01, 2010 8:48 pm
- Post datetime: 2010-11-29T07:53:55+00:00
- Post Title: Headhunter (Dreamcast) - ADPCM stream

> Reply from AlphaTwentyThree
>
> Do you know how the header should look like in order for vgmstream to play the files?
It must be [*.STR](http://www.sendspace.com/file/bbm8eh) type by Sega Stream Asset Builder...M.b. [Dream SDK](http://www.emuparadise.org/sdk/Sega/Sega%20Dreamcast.7z) will help U
## Post #5
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-11-29T13:56:37+00:00
- Post Title: Headhunter (Dreamcast) - ADPCM stream

> Reply from mauzerX
>
> It must be *.STR type by Sega Stream Asset Builder...M.b. Dream SDK will help U
Thanks for the examples. Do you have a link to specifications or can you explain the few variables in the header? Couldn't make a lot of it to be honest and just by playing around I couldn't get the files to play. I'd like to write a little QuickBMS script that automatically converts those RIFF header files to playable STR files. I want to centralize my tools to as less as possible. Thanks!
## Post #6
- Username: mauzerX
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jul 01, 2010 8:48 pm
- Post datetime: 2010-11-30T08:51:39+00:00
- Post Title: Headhunter (Dreamcast) - ADPCM stream

> Reply from AlphaTwentyThree
>
> 
Do you have a link to specifications or can you explain the few variables in the header?
Ask hc's or manakoAT in the [console_stream chat](http://wbe01.mibbit.com/?server=irc.foreverchat.net&channel=%23console_stream).
