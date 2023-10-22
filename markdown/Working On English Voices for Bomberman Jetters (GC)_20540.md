## Post #1
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2019-05-24T03:46:14+00:00
- Post Title: Working On English Voices for Bomberman Jetters (GC)

Hello again everyone, I'm at it again! I just had a brief question this time. I extracted the files from the iso with Dolphin and there's a folder called Voice. It appears to have everything I'm looking for, all in .DSP files. I opened these with a DSP friendly version of Audacity and the voices are audible but some appear scrambled. 

For example, the file e004lr has Shout speaking and mid way through the sentence, she repeats herself, cutting herself off before finishing her statement. I've noticed this is the case with many of the samples. Even voices that complete their sentences still repeat themselves such as with file h072lr. 

Should I use a different program or is it somehow loading these wrong?
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-05-24T16:34:52+00:00
- Post Title: Working On English Voices for Bomberman Jetters (GC)

I've just had a look at these.  They are stereo DSP files, although vgmstream doesn't seem to detect them correctly, so you get some that don't sound right when played.  I suspect Audacity is also opening them incorrectly.

It should be simple enough to do something with these - I'll have a think 

Maybe Pingu will have some info too!
## Post #3
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-05-24T16:39:25+00:00
- Post Title: Working On English Voices for Bomberman Jetters (GC)

It was easier than I thought!

If you rename all of the files so that there's an underscore before the "lr" in the filename, they should all play correctly in Foobar with vgmstream.
## Post #4
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2019-05-25T02:10:52+00:00
- Post Title: Working On English Voices for Bomberman Jetters (GC)

Yes, this is true. Sometimes you have to rename certain extensions as the vanilla version of foobar takes priority in reading sound files first before vgmstream. Renaming then allows vgmstream to be prioritized as foobar doesn’t know what to do with the extension.
## Post #5
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2019-05-25T12:40:51+00:00
- Post Title: Working On English Voices for Bomberman Jetters (GC)

Ah very good, that trick worked. However it seems not all the voices are here. Some characters like Bomberman and Max are still floating around out there.

I showed this to a friend and he noticed there are some voices in the jetters.samp file. Is there a way to get to them from here?
## Post #6
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-05-25T13:01:33+00:00
- Post Title: Working On English Voices for Bomberman Jetters (GC)

I think I can get those from the .samp file for you.  Working on it
## Post #7
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-05-25T14:12:05+00:00
- Post Title: Working On English Voices for Bomberman Jetters (GC)

Ok, here's my program that should do the trick.  Unzip the attached files into the same folder as jetters.samp.  Open a command prompt and run bj_samp.exe - as usual, it should be self-explanatory.


Dave
[bj_samp.zip](https://xentaxbackup.github.io/file/16282_bj_samp.zip)
## Post #8
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2019-05-26T13:13:22+00:00
- Post Title: Working On English Voices for Bomberman Jetters (GC)

I'm having trouble again DKDave. Whenever I go to open the file bj_samp.exe the window appears then vanishes just as quick. I tried opening Command Prompt itself and running bj_samp.exe but it did nothing. I'm not the most tech savvy so I apologize for the inconvenience.
## Post #9
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-05-26T14:09:21+00:00
- Post Title: Working On English Voices for Bomberman Jetters (GC)

No problem, SteamyJ - just put the attached .bat file in the same folder as bj_samp.exe, file_table and jetters.samp - and then double-click the bj.bat file.
[bj.zip](https://xentaxbackup.github.io/file/16291_bj.zip)
## Post #10
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2019-05-28T03:19:35+00:00
- Post Title: Working On English Voices for Bomberman Jetters (GC)

Thanks for the file DKDave. I put it in and it extracted over 800 files for me.

My next thing is, roughly half of these files will not play in Foobar while the others will. Here's what it looks like.

[https://i.imgur.com/aGFFa7z.png](https://i.imgur.com/aGFFa7z.png)
## Post #11
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-05-28T10:47:01+00:00
- Post Title: Working On English Voices for Bomberman Jetters (GC)

I'm not sure what the problem is there.  All 854 files play fine for me, although I do know Foobar is sometimes a bit temperamental.

I'm not an expert on Foobar, but maybe vgmstream is detecting the files incorrectly.  If you go into your Foobar preferences, under Playback > Decoding, you can drag vgmstream higher up the list so it gets priority.

It would be interesting to know if these files play ok for anyone else.

If you want an alternative solution, which might work better, you can rename all the files to have the extension .vgmstream, and then paste the following into a text file called .vgmstream.txth in the same folder as the audio files:

codec = DSP
codec_mode = 0
interleave = 0
channels = 1
sample_rate = @0x0A:BE$2
num_samples = @0x00:BE$4
start_offset = 0x0060
coef_offset = 0x001c
coef_spacing = 0x0020
coef_endianness = BE
## Post #12
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2019-05-28T22:10:58+00:00
- Post Title: Working On English Voices for Bomberman Jetters (GC)

I tried both ways you suggested but neither seemed to work. Is there a particular component I need to add to foobar for them to work?
## Post #13
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-05-29T00:55:46+00:00
- Post Title: Working On English Voices for Bomberman Jetters (GC)

If you haven't got it, I think you might also need the ADPCM decoders for Foobar.

vgmstream will support the TXTH format, but it doesn't seem to recognise DSP, properly, which looks like the problem you're having.

If you install the ADPCM decoders 1.13 from the Foobar2000 site, that should work (fingers crossed!).
## Post #14
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2019-05-29T10:15:25+00:00
- Post Title: Working On English Voices for Bomberman Jetters (GC)

Good news. All I needed was the ADPCM decoder and the DSP files work now. Turns out I just needed that all along lol. Everything seems to play correctly now. I'll let you know if anything else comes up but thanks as usual DKDave!
## Post #15
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2019-06-01T13:37:12+00:00
- Post Title: Working On English Voices for Bomberman Jetters (GC)

Hey again. I finally had a chance to sit down and go through all of the files from .samp file. It seems that after all that there are still just a few more voices in hiding. These in particular are in the animated cutscenes. There's roughly 8 of them in the game: when you start a new file, 5 different bosses, a bad ending and a cutscene in place of the bad ending leading to the final world.
## Post #16
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-06-01T17:06:33+00:00
- Post Title: Re: Working On English Voices for Bomberman Jetters (GC)

The cutscenes are all in the H4M folder as 18 video files.  I can't find anything to play the video properly, but Foobar will play the audio with vgmstream, so you can use it to convert them to a separate audio file.
## Post #17
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2019-06-02T13:42:41+00:00
- Post Title: Re: Working On English Voices for Bomberman Jetters (GC)

The audio for these scenes has music in the background so some of the voices are a bit muddled. Do you know of any way to explore these files further?
## Post #18
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-06-02T18:51:02+00:00
- Post Title: Re: Working On English Voices for Bomberman Jetters (GC)

The music and voices in the cutscenes are all one audio stream, so unfortunately there's no way to separate them to get just the voices.  So that's probably the best you'll get for those ones.
## Post #19
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2020-11-06T15:31:20+00:00
- Post Title: Re: Working On English Voices for Bomberman Jetters (GC)

I recently went back and decided to extract the voices from the Japanese version. However they sound terrible for some reason. Here's an example.

[https://mega.nz/file/g14iVZAb#Ip3RtABDO ... OkrtHAa-jc](https://mega.nz/file/g14iVZAb#Ip3RtABDO01rfAI1MFyHpZT3Ux_HR66zHOkrtHAa-jc)
