## Post #1
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-07-23T14:59:33+00:00
- Post Title: Fairly Odd Parents: Breakin Da Rules (PS2) .str

Hi! I need some help because I can convert the other files but some "episode" files doesn't have the same interleave (0x8000) freq 44100 and channels 2 but I think that the file you will see is a sort of multichannel.

links:
[https://mega.nz/#!2hkw0KLC!HqQMJZvzBxuw ... sPRcbYjTGg](https://mega.nz/#!2hkw0KLC!HqQMJZvzBxuwanUjgiSHiYvPIvIzrymmwsPRcbYjTGg)

There's a .wav attached file also:
[https://mega.nz/#!XoUhnDCZ!9EEBK_8DkrG6 ... VoVX_Tpkws](https://mega.nz/#!XoUhnDCZ!9EEBK_8DkrG6a53J8L-oOIlIBT3j-xDsjVoVX_Tpkws)
## Post #2
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-07-25T14:44:41+00:00
- Post Title: Fairly Odd Parents: Breakin Da Rules (PS2) .str

Pretty difficult?
## Post #3
- Username: AwesomeMarioFan
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Aug 05, 2015 10:56 am
- Post datetime: 2015-08-06T02:46:49+00:00
- Post Title: Fairly Odd Parents: Breakin Da Rules (PS2) .str

You're right we seem to have the exact same problem. If it helps any, I was able to use MFAudio to extract a sound in mono (since interleave is only for stereo). How did you find the interleave of 32768 for your song by the way? (Trial and error?) When I play mine with an interleave which sounds good, the audio in both speakers starts at the same place but seems to skip around/go out of sync, so I'm a bit confused. So then when I bring it down to 512, it sounds in sync but very fast and distorted. VGMStream doesn't seem to help any either, either displays a wrong song length or generates a large ~1GB file. (With the latest test version as well.)

Even more confusing, some of the sounds in the game I was looking at seem to be two interleaved streams interleaved together (With stereo as well). This is since parts of the game change the tune of the song sometimes. Then,  some of the sound effects seem to have different interleaves for every sub-sound. It seems this is a very confusing format.

I was also wondering how you were able to extract the individual .str file from the .ps2 audio files? Did you have to extract it from something or was it just included in the game's files in that format?
## Post #4
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-08-06T07:28:30+00:00
- Post Title: Fairly Odd Parents: Breakin Da Rules (PS2) .str

This is a script "blitz_games.bms" with QuickBMS that can extract blitz games .gcp, .ps2, .xbp format. Because for this game I can't rip for all platforms (except PC whichdoesn't have the same musics as well).

For 32768 it's just 0x8000 for the "tiny files" because the "episode" files like episode1.str, episode6.str (a dog's life) have several songs in them. I think the episode files are sort of archives/multichannel interleaved with offsets I don't know but this is the first time I see this problem. Also the episode files have a size of ~20mo so I think they're not simply stream with interleave, they're several files definetly. Same for Taz Wanted.
## Post #5
- Username: AwesomeMarioFan
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Aug 05, 2015 10:56 am
- Post datetime: 2015-08-07T03:59:04+00:00
- Post Title: Fairly Odd Parents: Breakin Da Rules (PS2) .str

You can try using MFAudio ([http://www.zophar.net/utilities/ps2util ... o-1-1.html](http://www.zophar.net/utilities/ps2util/mfaudio-1-1.html)) and converting the .str as PS2 ADPCM (Compressed), Frequency 41000, Channels 1 for mono which seemed to work for me (Unless it's a multi-interleaved audio file). I was able to get this result: [https://mariocube.com/internal/audio.wav](https://mariocube.com/internal/audio.wav). Someone over here said they used a program to split the multi-interleaved streams, but the link is broken: [viewtopic.php?f=17&t=9244](http://forum.xentax.com/viewtopic.php?f=17&t=9244). Unfortunately I can't find any information on the link or the file name. I can keep looking for another program to do that however, since all we seem to need is a program that can do that and (for my case) finding the interleave.

Regarding finding the interleave of the audio, there are posts saying to use a hex editor and search for the first 0x10 bytes and the second one is the interleave, but I couldn't get it to work - not sure if it would help in your case:
[viewtopic.php?f=17&t=8460](http://forum.xentax.com/viewtopic.php?f=17&t=8460)
[viewtopic.php?f=17&t=8460](http://forum.xentax.com/viewtopic.php?f=17&t=8460)

By the way when you say that 0x8000 would be the interleave in your case because there are several songs in some files - did you use a hex editor to get that value or was it trial and error?
This person seems to have the same problem as us as well, he is using a THQ game as well from around the same year: [viewtopic.php?f=17&t=10850](http://forum.xentax.com/viewtopic.php?f=17&t=10850).
## Post #6
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-08-07T12:39:51+00:00
- Post Title: Fairly Odd Parents: Breakin Da Rules (PS2) .str

This is not the same problem than Spongebob. Go to zenhax and see my links, you will can download the files and you'll see the problem
## Post #7
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-08-08T20:41:52+00:00
- Post Title: Fairly Odd Parents: Breakin Da Rules (PS2) .str

@Mr.Mouse any help please?
## Post #8
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-08-09T12:03:08+00:00
- Post Title: Fairly Odd Parents: Breakin Da Rules (PS2) .str

I found the correct interleave. The file is multichannel 3 channels with almost 0x8000 for interleave but it's not 0x8000, I need to find the proper interleave.
## Post #9
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2015-08-09T12:10:43+00:00
- Post Title: Fairly Odd Parents: Breakin Da Rules (PS2) .str

It's fixed now
