## Post #1
- Username: PlanB0902
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 14, 2010 4:40 am
- Post datetime: 2010-11-19T18:48:58+00:00
- Post Title: Dead Rising 2 .adw & .xwma

When you try to replace music in Dead Rising 2 PC, all the bgm is deactivated. I have found that the .adw files are .WAVEs in ADPCM codec. Not sure about xWMAs, any knowledge?
## Post #2
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2010-11-19T22:12:12+00:00
- Post Title: Dead Rising 2 .adw & .xwma

audio is adpcm ur rigth dunno if it was now ms or ima but i think ms,, game have 2 kinds of wav, these adpcm and xma, u can covert the xma with the ms sdk xWMAEncode.exe is what u need, ive tryt it but for me game dont work anymore, maby u have more luck
## Post #3
- Username: RENIKRILL
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Feb 11, 2009 7:54 pm
- Post datetime: 2010-11-20T04:13:42+00:00
- Post Title: Dead Rising 2 .adw & .xwma

the .adw files are MS-ADPCM, with all of the necessary file-information included in the RIFF header. simply change the extensions to .wav, and they'll play in any half-decent player.
the .xwma files aren't xma, they're xwma (yes, there's a difference  ). specifications for this [godforsaken] format, along with a command-line encoder/decoder, can be found here: "[http://msdn.microsoft.com/en-us/library ... S.85).aspx](http://msdn.microsoft.com/en-us/library/ee415832%28VS.85%29.aspx)"
## Post #4
- Username: Schemer
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jun 11, 2010 10:59 pm
- Post datetime: 2011-01-25T04:04:47+00:00
- Post Title: Dead Rising 2 .adw & .xwma

please read my post [here](http://deadrising2mods.proboards.com/index.cgi?action=gotopost&board=dr2tools&thread=186&post=2380) about Gibbed.DeadRising2.Tools & .xwma
