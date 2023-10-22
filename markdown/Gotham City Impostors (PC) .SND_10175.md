## Post #1
- Username: hoodlum47
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jan 30, 2011 6:01 am
- Post datetime: 2013-02-25T21:22:44+00:00
- Post Title: Gotham City Impostors (PC) .SND

Hello I have successfully extracted the .Arch01 archives from this game using one of Alpha23's qbms scripts (since its architecture is very similar to F.E.A.R. 2) and it resulted in numerous .snd files which are supposed to contain .wavs as they did in FEAR 2. So I tried using the SNDExtractor from the FEAR2 Tools package, but it isn't working correctly.

If anyone is interested in helping me I will PM them the link to a sample file.
## Post #2
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-02-27T01:34:04+00:00
- Post Title: Gotham City Impostors (PC) .SND

try using a generic riff/wave header scanner script. it's not quite the same as fear 2, but the wav files are still in there uncompressed. filenames might be in the raw data somewhere too.
## Post #3
- Username: hoodlum47
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jan 30, 2011 6:01 am
- Post datetime: 2013-02-27T05:51:21+00:00
- Post Title: Gotham City Impostors (PC) .SND

I already tried that using Alpha's scanner script, Hyperipper, and Ravioli scanner and none of them found a single thing.
## Post #4
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-03-01T14:15:55+00:00
- Post Title: Gotham City Impostors (PC) .SND

> Reply from hoodlum47
>
> I already tried that using Alpha's scanner script, Hyperipper, and Ravioli scanner and none of them found a single thing.

huh weird, since going f2p they seem to have removed the wave headers. it's just raw little endian stream data now in there.
## Post #5
- Username: hoodlum47
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jan 30, 2011 6:01 am
- Post datetime: 2013-03-01T14:22:02+00:00
- Post Title: Gotham City Impostors (PC) .SND

Well that would explain why the tools/scripts aren't working. But that also means extraction will be all the more difficult doesn't it?
## Post #6
- Username: hoodlum47
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jan 30, 2011 6:01 am
- Post datetime: 2013-06-29T20:25:00+00:00
- Post Title: Gotham City Impostors (PC) .SND

Ok i'm still getting nowhere with these on the pc version so I switched to the ps3 version, they are still .snd archives but their filesizes are considerably smaller (most likely because the contained audio is in a compressed codec for the PS3) I will upload a sample if anyone can help me.
## Post #7
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-06-29T22:19:20+00:00
- Post Title: Gotham City Impostors (PC) .SND

Sorry i took this long to reply, but just import the raw pc .snd into audacity using little endian stereo / mono format.
## Post #8
- Username: ojo987
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Sep 12, 2014 9:59 pm
- Post datetime: 2014-09-12T14:05:03+00:00
- Post Title: Gotham City Impostors (PC) .SND

Hi folks, new member here, and sorry to resurrect an old thread. I've been a diehard fan of GCI since it came out on Xbox, and have just downloaded it for PC/Steam. I've love to be able to extract some of the graphics (particularly card backgrounds) and maybe sounds and videos. I'm curious as to how I can unpack/extract the ".arch01" files, as mentioned in this thread. I see references to a qbms script but can't find them, and not sure how to proceed. Sorry for the newbie question, but wondering if anyone could let me know where to begin? Thanks for any help!
## Post #9
- Username: ojo987
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Sep 12, 2014 9:59 pm
- Post datetime: 2014-09-12T15:25:16+00:00
- Post Title: Gotham City Impostors (PC) .SND

> Reply from ojo987
>
> Hi folks, new member here, and sorry to resurrect an old thread. I've been a diehard fan of GCI since it came out on Xbox, and have just downloaded it for PC/Steam. I've love to be able to extract some of the graphics (particularly card backgrounds) and maybe sounds and videos. I'm curious as to how I can unpack/extract the ".arch01" files, as mentioned in this thread. I see references to a qbms script but can't find them, and not sure how to proceed. Sorry for the newbie question, but wondering if anyone could let me know where to begin? Thanks for any help!

Quick update - I found the qbms script! Successfully extracted the .arch01 files. It looks like the things I want to play with are the .tex files and .snd files. I've so far found about half a dozen tools that supposedly convert .tex to .jpg, but thus far no luck at all. I'm not a programmer so I'm not sure how to mess with the files to make them viewable. Any suggestions??
## Post #10
- Username: ojo987
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Sep 12, 2014 9:59 pm
- Post datetime: 2014-09-14T20:43:08+00:00
- Post Title: Gotham City Impostors (PC) .SND

> Reply from Pepper
>
> Sorry i took this long to reply, but just import the raw pc .snd into audacity using little endian stereo / mono format.

For what it's worth, I tried this (using the PC/steam version) and had no luck. There are .snd files and .wav files, but no combination of importing raw with signed/unsigned, 8/16/24 bit, little/big/no endian, etc in Audacity resulted in anything but static. Any suggestions?
## Post #11
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-09-17T13:35:26+00:00
- Post Title: Gotham City Impostors (PC) .SND

> Reply from ojo987
>
> Pepper wrote:Sorry i took this long to reply, but just import the raw pc .snd into audacity using little endian stereo / mono format.

For what it's worth, I tried this (using the PC/steam version) and had no luck. There are .snd files and .wav files, but no combination of importing raw with signed/unsigned, 8/16/24 bit, little/big/no endian, etc in Audacity resulted in anything but static. Any suggestions?
 make sure you use the fear 2 tools downloadable in the game specific tools forum. little end 44khz 16bit in audacity works fine for me with .snd files.
## Post #12
- Username: ojo987
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Sep 12, 2014 9:59 pm
- Post datetime: 2014-09-17T15:30:56+00:00
- Post Title: Gotham City Impostors (PC) .SND

> Reply from Pepper
>
>  make sure you use the fear 2 tools downloadable in the game specific tools forum. little end 44khz 16bit in audacity works fine for me with .snd files.

Sorry, I should have been more specific, it's the .wav files that are not working for me. The file extension is .wav, but they do not appear to be actual WAV files. I've tried every combination of import in Audacity, and Soundforge (which I am much more familiar with) can't open them either. 

I will try to attach below some screenshots of the hex of the first part of several of these .wav files. I know almost nothing about hex but I don't see any obviously repeated patterns so I'm not sure if that means there's no header etc? Anyhoo, open to suggestions on anything that might open/convert these .wav files.

BTW - your advice on the .snd files worked PERFECTLY - thanks for that!!
[soundfile1hex.jpg](https://xentaxbackup.github.io/file/7832_soundfile1hex.jpg)
## Post #13
- Username: ojo987
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Sep 12, 2014 9:59 pm
- Post datetime: 2014-09-17T15:33:19+00:00
- Post Title: Gotham City Impostors (PC) .SND

screenshot of the hex of another .wav file
[soundfile2hex.jpg](https://xentaxbackup.github.io/file/7833_soundfile2hex.jpg)
## Post #14
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-09-17T16:41:36+00:00
- Post Title: Gotham City Impostors (PC) .SND

> Reply from ojo987
>
> screenshot of the hex of another .wav file

Sorry, I don't have a clue. It's probably some kind of compression of the audio, but I'm no expert.
