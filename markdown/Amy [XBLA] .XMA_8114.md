## Post #1
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-01-24T09:40:33+00:00
- Post Title: Amy [XBLA] .XMA

Hello, I'm having a little trouble converting Amy's XMA to a standard WAV format. 

All XMAs are stored inside FSB containers so using fsbext pulls them out of there with no problem. Than I tried using some tools and scripts, but nothing really produced a proper playable WAV. 

Towav, Alpha23's wav scanner script, RIFF header adder script - all didn't work. I have a feeling the answer is somewhere near, I'm simply not using the right tool for the job. 

Here is Common_Stream.fsb and Music_Maintheme.xma (one of the files extracted from it). 

Please have a look.

[http://www.mediafire.com/?x48pbg6c48e38je](http://www.mediafire.com/?x48pbg6c48e38je)

[http://www.mediafire.com/?erwrtifnrvlwsee](http://www.mediafire.com/?erwrtifnrvlwsee)
## Post #2
- Username: RENIKRILL
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Feb 11, 2009 7:54 pm
- Post datetime: 2012-02-08T00:24:31+00:00
- Post Title: Amy [XBLA] .XMA

You're taking more steps than are necessary to decode the streams, which is actually why you are having no luck decoding them ;-P
All you need to do is place Towav alongside your desired fsb file, then run Towav's batch-file and watch it do the work for you.
Towav natively supports [properly structured] xma, as well as just-about any FMOD sound-bank (fsb) file you might present to it (with the exception of some of the new-gen architectures, i.e. interleaved mpeg streams.)

Hopefully this clears up any probs you were having
## Post #3
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-02-08T03:09:23+00:00
- Post Title: Amy [XBLA] .XMA

Oh crappity crap, indeed this is a much shorter way and the output WAVs play just fine.
Once again RENIKRILL saves the day, thanks a lot man!
## Post #4
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-02-10T01:15:35+00:00
- Post Title: Amy [XBLA] .XMA

Hehe, I'm always after the source files, that's why there are all those scripts.
