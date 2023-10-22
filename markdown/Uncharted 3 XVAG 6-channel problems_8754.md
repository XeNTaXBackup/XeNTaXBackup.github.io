## Post #1
- Username: fadi002
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 12, 2012 1:10 pm
- Post datetime: 2012-04-12T05:34:45+00:00
- Post Title: Uncharted 3 XVAG 6-channel problems

Ok, so Uncharted 3 uses XVAG files for audio, and I can only playback the mono or stereo files normally. Files that have more channels get messed up, and make the music annoying. 
<link removed due forum rules violation>

789_sandlantis_doorwalkthrough.xvag has more than 2 channels and is messed up for me, (What it's supposed to sound like: [http://www.youtube.com/watch?v=-08HFkAewRw&t=11s](http://www.youtube.com/watch?v=-08HFkAewRw&t=11s))
6-channel-test.xvag is a file I found, and it sounds normal. I'm assuming this is because there is only 1 channel with audio at any given time,
and powerplay-temp-60-sec.xvag works normally.

I use VLC media player or Import them into audacity (with FFmpeg) when VLC fails to listen to them.

Is there any way to listen to these sound files normally?
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-04-12T17:34:50+00:00
- Post Title: Uncharted 3 XVAG 6-channel problems

Ive done some tests on this and the only way to get them to play is to split the channels because the mpeg stream is interleaved. Now in order to deinterleave the tracks is to use alphatwentythree's deinterleave bms script, problem is finding the right interleave for the files. You can do this by looking at the mpeg frames in hex code. However its time consuming and difficult to determine a proper interleave as they can vary.
## Post #3
- Username: fadi002
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 12, 2012 1:10 pm
- Post datetime: 2012-04-12T23:46:21+00:00
- Post Title: Uncharted 3 XVAG 6-channel problems

> Reply from OrangeC
>
> Ive done some tests on this and the only way to get them to play is to split the channels because the mpeg stream is interleaved. Now in order to deinterleave the tracks is to use alphatwentythree's deinterleave bms script, problem is finding the right interleave for the files. You can do this by looking at the mpeg frames in hex code. However its time consuming and difficult to determine a proper interleave as they can vary.
Thanks for that, but I need to know how to do these things:
-How do I run the script, and how do I use it with the files I was talking about?
-How do I find the mpeg frame I need to find the right interleave?
-How do I determine the right interleave from the frame and use it in the code?

I hope this isn't too much for you, and thanks for helping me .
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-04-13T00:56:43+00:00
- Post Title: Uncharted 3 XVAG 6-channel problems

To run scripts you need to use Quickbms, Click on exe file then script then output folder.

As for how to find the interleave if you don't know atleast how to look for stuff in hex editor then there's not much i can do toe xplain.
## Post #5
- Username: fadi002
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 12, 2012 1:10 pm
- Post datetime: 2012-04-13T01:23:12+00:00
- Post Title: Uncharted 3 XVAG 6-channel problems

> Reply from OrangeC
>
> To run scripts you need to use Quickbms, Click on exe file then script then output folder.

As for how to find the interleave if you don't know atleast how to look for stuff in hex editor then there's not much i can do toe xplain.
I can use a Hex editor, I just need to know what to look for and how to put it in the script. If you're not gonna tell me how to do that, can you at least give me a link to somewhere that explains the mpeg layers and interleaving?

And this is the script you were talking about, right? [viewtopic.php?f=13&p=39344#p39344](http://forum.xentax.com/viewtopic.php?f=13&p=39344#p39344)
## Post #6
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-04-13T18:26:21+00:00
- Post Title: Uncharted 3 XVAG 6-channel problems

Yes.

In hex you have to find out the interleaving via the individual frames. Now each frame start with FFFB. Each frame holds a specific offset. So i woul suggest trying each offset and nput it into your script like so.

Interleave: 0x1000 for example

Layer: 3 for example depending on the channel count.

Run quickbms exe then open script then file then output folder, and it should output the deinterleaved files.
## Post #7
- Username: fadi002
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 12, 2012 1:10 pm
- Post datetime: 2012-04-15T04:06:21+00:00
- Post Title: Uncharted 3 XVAG 6-channel problems

Thanks! The interleave was 0x3000, and the layer was 2 for most of the quad-channel+ sound files in the game. Turns out the 789_sandlantis_doorwalkthrough.xvag file was a bit different, with a 0x2A00 interleave. Anyways, I've gotten them to work properly thanks to you .
## Post #8
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-04-15T05:09:26+00:00
- Post Title: Uncharted 3 XVAG 6-channel problems

The 0x2a00 one you mentioned still has some skips. So that can't be the right interleave unless if you have done something different.
## Post #9
- Username: fadi002
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 12, 2012 1:10 pm
- Post datetime: 2012-04-17T15:12:38+00:00
- Post Title: Uncharted 3 XVAG 6-channel problems

> Reply from OrangeC
>
> The 0x2a00 one you mentioned still has some skips. So that can't be the right interleave unless if you have done something different.
I made the header 0x133. It worked. Here it is in wav format: [http://min.us/mbe2J3NHYV](http://min.us/mbe2J3NHYV)
## Post #10
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-04-17T16:52:22+00:00
- Post Title: Uncharted 3 XVAG 6-channel problems

Ahh great!!

Maybe i can then start my uncharted 3 rip.
## Post #11
- Username: FunnyML
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 04, 2007 1:45 am
- Post datetime: 2012-04-28T15:01:53+00:00
- Post Title: Uncharted 3 XVAG 6-channel problems

Just a small correction, the header seems to be 0x134. Doesn't really matter, as the files can be played perfectly anyway, but you know...  Good luck with your rip Orange
