## Post #1
- Username: Taurine
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Sep 01, 2023 11:41 am
- Post datetime: 2023-09-19T10:03:27+00:00
- Post Title: The interleave of PS2 game Rozen Maiden: Gebetgarten

Hello!
I was trying to rip the audio files from this game: [https://ps.romsfast.com/PS2-REDUMP-ASIA ... (Japan).7z](https://ps.romsfast.com/PS2-REDUMP-ASIA/Rozen%20Maiden%20-%20Gebetgarten%20%28Japan%29.7z)
using cube media player 2.
And I did scan them out, but have no idea about how to set the interleave(and frequency),thus making the converted files be in really poor quality.

Could anyone inform me a method to find the correct interleave please?
## Post #2
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2023-09-19T11:46:01+00:00
- Post Title: The interleave of PS2 game Rozen Maiden: Gebetgarten

To find a stereo PS ADPCM interleave values all you have to do to find a 16-bytes zero pattern to indicate the start of left/right channel audio data.

For this example, I'll use a VB files from GTAIII

Here you can see the 16-bytes of zeroes of the left channel audio data



Use those 16-bytes as a find pattern to look for the start of the right channel audio data



Then just subtract the right channel data offset with the left ones and that's your interleave value (Since CMP is using decimal numbers so you might want to convert the offset hex numbers to decimal first). 

This works with most games but there are some games that didn't have zero-byte patterns though.
As for sample rates, it was mostly trial and error. Just keep playing around with it until you can find the correct ones.

 ̶O̶r̶ ̶y̶o̶u̶ ̶c̶a̶n̶ ̶m̶a̶k̶e̶ ̶t̶h̶i̶s̶ ̶e̶a̶s̶i̶e̶r̶ ̶b̶y̶ ̶s̶e̶n̶d̶i̶n̶g̶ ̶o̶u̶t̶ ̶a̶ ̶s̶a̶m̶p̶l̶e̶ ̶f̶i̶l̶e̶ ̶h̶e̶r̶e̶.̶
Wait, wasn't this game is the one of those that hide most of it's datas and only thing that's visible is the game's executable and a video file and some IRX modules?
In that case, looks like you have to use CMP indeed.
## Post #3
- Username: Taurine
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Sep 01, 2023 11:41 am
- Post datetime: 2023-09-19T21:10:25+00:00
- Post Title: The interleave of PS2 game Rozen Maiden: Gebetgarten

Yeah, it's highly ..like protected? I'll leave it for now and hope someday come across a proper method.
Thank you anyway.
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2023-09-20T19:27:45+00:00
- Post Title: The interleave of PS2 game Rozen Maiden: Gebetgarten

> Reply from Taurine ↑Wed Sep 20, 2023 5:10 am at Wed Sep 20, 2023 5:10 am
>
> 
Yeah, it's highly ..like protected? I'll leave it for now and hope someday come across a proper method.
Thank you anyway.

There are rips out there of the music, but I haven't checked how complete they are.  You can use my attached QuickBMS script to extract the music and dialogue as playable .ss2 files.


 rozen_audio.zip
(817 Bytes) Downloaded 14 times
