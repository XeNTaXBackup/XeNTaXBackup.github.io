## Post #1
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2011-09-08T13:56:43+00:00
- Post Title: Dead Island RIFF Wavs

I recently tried getting some of the audio out of Dead Island from the .xwb files using unxwb. Only problem seems to be is that they will not play in anything but vlc. Opening the .wav's extracted in a hex editor show that it is a Riff wave and running them through other tools to try and convert does not seem to work. I do not know enough to identify the problem. 
Is there some sort of cmd line option I should be using in unxwb to get a proper header or something? Would greatly appreciate any info. Thanks.
Below is a xwb file.

* snip *
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-09-08T16:19:00+00:00
- Post Title: Dead Island RIFF Wavs

You can load it into audacity with the ffmpeg plugin library installed.
## Post #3
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2011-09-08T21:58:29+00:00
- Post Title: Dead Island RIFF Wavs

its something weird with how unxwb produces headers for adpcm data, i've tried using batch commands to make vlc convert each file, but vlc isnt very cmd friendly, and i always have to close each vlc window by hand for the next one to pop up and convert the next file. it's a big pain, yes. i've considered contacting the tool's author, but i've always just went with clicking a thousand times instead for some reason...
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-09-08T23:08:06+00:00
- Post Title: Dead Island RIFF Wavs

Umm did you not read my post?
## Post #5
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2011-09-09T00:13:17+00:00
- Post Title: Dead Island RIFF Wavs

> Reply from OrangeC
>
> Umm did you not read my post?

I did. doesn't change the fact that its standard adpcm with a bad header and those options arent good for batch converting thousands of them at once. hell, my method is only slightly better, but is still tedious. who is the author of unxwb? is it aluigi or whoever? since the dead island xwb files also lack xsb pairs, but store the file names inside in the xwb in a way that isnt xsb standard. some kind of new xwb probably. I've dealt with this on many games, everything from magicka to dead island and others. the header isnt rebuilt correctly, so only very leniant audio codecs/apps can decode it. ffmpeg and vlc are two of them. Wait. does ffmpeg have a cmd runnable version? if so, I'm very sorry for being rude and i will love you forever. if not, still sorry for being rude.

IT DOES. Thanks!
## Post #6
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-09-09T02:11:42+00:00
- Post Title: Dead Island RIFF Wavs

It should but why would you need to fiddle around with it if you can just install audacity with the ffmpeg libraires and just drag and drop the ms adpcm files into audacity and batch export to wav?
## Post #7
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2011-09-09T02:22:22+00:00
- Post Title: Dead Island RIFF Wavs

I had came across the idea and even downloaded the ffmpeg as a back up plan. But if this works then thanks for saving me the time and super hassle as I would of eventually done the same as Pepper had done in vlc and manually converted each file.
## Post #8
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2011-09-09T22:30:10+00:00
- Post Title: Dead Island RIFF Wavs

> Reply from OrangeC
>
> It should but why would you need to fiddle around with it if you can just install audacity with the ffmpeg libraires and just drag and drop the ms adpcm files into audacity and batch export to wav?

well, in certain games there can be thousands of audio files. using a .bat script helps, but vlc isnt very friendly with it. ffmpeg is. again, its more of not liking have to click thousands of times for each file.
## Post #9
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2011-09-19T18:25:28+00:00
- Post Title: Dead Island RIFF Wavs

The contents of this post was deleted because of possible forum rules violation.
## Post #10
- Username: Suigintou
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Sep 13, 2011 11:16 pm
- Post datetime: 2011-09-25T10:48:41+00:00
- Post Title: Dead Island RIFF Wavs

I tried to extract .xwb archive and I got many wav files 14.9 kb each. Obvious, i cant open them. What i do wrong? Also, i have Audacity with FFmpeg and I can't open those files too.
## Post #11
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2011-09-25T12:34:32+00:00
- Post Title: Dead Island RIFF Wavs

The .zip file attached contains a .bat file that will convert the .wav files using VLC nice and quickly.

You might have to change the directory of where your VLC.exe is located in the batch file if needed.

Put that .bat file where the .wav files are and run the script.

Your converted files will have a ".wav.wav" extension 
[VLC Batch Conversion.zip](https://xentaxbackup.github.io/file/4738_VLC Batch Conversion.zip)
## Post #12
- Username: Suigintou
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Sep 13, 2011 11:16 pm
- Post datetime: 2011-09-25T14:32:09+00:00
- Post Title: Dead Island RIFF Wavs

Works fine, thx!
## Post #13
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2011-09-25T20:25:05+00:00
- Post Title: Dead Island RIFF Wavs

Yes, it works, thanks.
Still, I'd like to have a script that converts this header to the SFC header above so I can play the files in Winamp or any other player! Thanks for your help!
## Post #14
- Username: passburger
- Rank: n00b
- Number of posts: 15
- Joined date: Mon May 21, 2012 6:42 am
- Post datetime: 2012-05-21T17:02:23+00:00
- Post Title: Dead Island RIFF Wavs

> Reply from geevious
>
> I recently tried getting some of the audio out of Dead Island from the .xwb files using unxwb. Only problem seems to be is that they will not play in anything but vlc. Opening the .wav's extracted in a hex editor show that it is a Riff wave and running them through other tools to try and convert does not seem to work. I do not know enough to identify the problem. 
Is there some sort of cmd line option I should be using in unxwb to get a proper header or something? Would greatly appreciate any info. Thanks.
Below is a xwb file.

http://www5.zippyshare.com/v/60540907/file.html

Hi,
Sorry for bumping!
The file has expired, could you please give me the name of that xwb file so I don't unpack the wrong file? I'm unpacking one of the files, but its taking ages to unpack, 16gb later and the file is still unpacking.
