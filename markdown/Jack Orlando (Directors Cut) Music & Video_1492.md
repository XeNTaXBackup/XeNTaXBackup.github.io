## Post #1
- Username: blbltheworm
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jun 13, 2005 9:01 pm
- Post datetime: 2005-09-09T11:08:52+00:00
- Post Title: Jack Orlando (Directors Cut) Music & Video

Jack Orlando has a great Jazz-Soundtrack and I want to listen it without playing the game.
The music is stored in *.pms-files but I didn't find a converter/extractor yet.
Can you help me?? Do anybody know a tool to extract the music??

Additionally it would be nice to extract the videos   .
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2005-12-10T21:15:08+00:00
- Post Title: Jack Orlando (Directors Cut) Music & Video

The format used for the game files (.PAK, .PHK, .PH2 and so on) is very simple and have added an entry in the wiki so hopefully someone will create a script for them:

[http://wiki.xentax.com/index.php/Jack_Orlando](http://wiki.xentax.com/index.php/Jack_Orlando)

The demo of the game (very small fortunately) is available here:
[http://www.jowood.com/gamers/?lang=en&s ... do&pfid=PC](http://www.jowood.com/gamers/?lang=en&site=2&ScreenID=4537&GameID=jackorlando&pfid=PC)

A bigger problem instead are the PMS files, in fact I have no experience with audio files and had no luck with the debugger.
I have opened these files as raw audio with all the possible combinations of frequency/channels/bits and format (intel/motorola/a-mu) and is possible to hear something but is very noisy.

The same thing happens also with the ADP files of the Nomad Soul game which is probably more interesting since many people want the music files of this game.

Has someone ideas or more experience with audio files?

Now I will try to look to GSM610 and IMAADPCM formats, let's learn!
## Post #3
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-11T01:37:45+00:00
- Post Title: Jack Orlando (Directors Cut) Music & Video

Hehe it seems as though you have done everything I would have done  . The only other thing I can suggest is to try the Game Audio Player program (google for it) - it is old but it does a lot of games.

Yeah I don't know anything about audio files at all - I intend to learn eventually but its at the bottom of my list...

Archives --> Images --> 3D Models --> Audio --> Video

I can't really help any further with this request, but I will try to make a plugin for the archive format soon. It would be nice if we could somehow come up with a collection of "audio files for dummies"-type materials - maybe there is something out there that will help. I know the Game Audio Player website has some specs for the different formats it reads, so thats a start.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-11T08:42:40+00:00
- Post Title: Jack Orlando (Directors Cut) Music & Video

I have tried and failed to get to grips with the Nomad Soul audio format too in the past. It's a shame.
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2005-12-11T19:09:07+00:00
- Post Title: Jack Orlando (Directors Cut) Music & Video

> Reply from Mr.Mouse
>
> I have tried and failed to get to grips with the Nomad Soul audio format too in the past. It's a shame.

I have spent all my morning trying to find a program or a way to read these files and I have only found that if you use the VOX codec/format you are able to hear the music with a small or minimal distorsion (this is the same for both Jack and Nomad Soul).
If you want to test it try with the programs SOX or Audacity, both on Sourceforge.net.

ADP means "ADPCM sound file" but seems that ADPCM is not very easy to read for unknown reasons... is it possible that doesn't exist a program for reading this stuff in a raw way???

Fortunately the music can be ever recorded without problems so a player or a converter is cool but also recording is an elegant solution eh eh eh.
## Post #6
- Username: john_doe
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-12-13T18:25:18+00:00
- Post Title: Jack Orlando (Directors Cut) Music & Video

I've made a little tool some time ago than can convert the Pms files to standard Wave files.

You can download it from [http://gamefileformats.the-underdogs.or ... stowav.zip](http://gamefileformats.the-underdogs.org/files/pmstowav.zip)

As already mentioned, it's the standard ADPCM algorithm, nothing fancy.

Almost forgot: It's in German but so little text I think everyone should know how to use it. Also, it's a command-line tool.
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2005-12-13T21:22:40+00:00
- Post Title: Jack Orlando (Directors Cut) Music & Video

> Reply from john_doe
>
> 
As already mentioned, it's the standard ADPCM algorithm, nothing fancy.

As far as I know exist tons of ADPCM algorithms, about what you refer?
## Post #8
- Username: dimi
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Apr 29, 2005 8:09 am
- Post datetime: 2005-12-16T22:47:07+00:00
- Post Title: Jack Orlando (Directors Cut) Music & Video

Thank you for this tool,john_doe!
## Post #9
- Username: john_doe
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-12-18T16:27:14+00:00
- Post Title: Jack Orlando (Directors Cut) Music & Video

> Reply from Bugtest
>
> john_doe wrote:
As already mentioned, it's the standard ADPCM algorithm, nothing fancy.


As far as I know exist tons of ADPCM algorithms, about what you refer?

Forgot to add, the IMA ADPCM, the 4-bit version with standard tables.
## Post #10
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-19T10:42:33+00:00
- Post Title: Jack Orlando (Directors Cut) Music & Video

> Reply from Bugtest
>
> The format used for the game files (.PAK, .PHK, .PH2 and so on) is very simple and have added an entry in the wiki so hopefully someone will create a script for them

Hi again mate,

Yeah I have made a plugin for this game and it is included in the latest Game Extractor, including the Basic Version - thanks for helping out with the specs, and everything else in general.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #11
- Username: gaboraa
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 08, 2011 4:07 am
- Post datetime: 2011-06-07T20:15:48+00:00
- Post Title: Jack Orlando (Directors Cut) Music & Video

> Reply from john_doe
>
> I've made a little tool some time ago than can convert the Pms files to standard Wave files.

You can download it from http://gamefileformats.the-underdogs.or ... stowav.zip

As already mentioned, it's the standard ADPCM algorithm, nothing fancy.

Almost forgot: It's in German but so little text I think everyone should know how to use it. Also, it's a command-line tool.

Unfortunately link to the extractor file is broken and it would be great if anyone could post a working link for this is much appreciated. I love this game's music and I registered here just for it:)

I tried extracting using Game Extractor but AFAIK it cannot open its .PMS files.

And I am sorry for my grammar mistakes if there are any.
## Post #12
- Username: gaboraa
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 08, 2011 4:07 am
- Post datetime: 2011-06-07T20:47:00+00:00
- Post Title: Jack Orlando (Directors Cut) Music & Video

Ah I have found it in here: [http://wiki.xentax.com/index.php/Jack_Orlando_Toolset](http://wiki.xentax.com/index.php/Jack_Orlando_Toolset). I should have looked more carefully!
