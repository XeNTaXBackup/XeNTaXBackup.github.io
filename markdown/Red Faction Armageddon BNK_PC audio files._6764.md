## Post #1
- Username: srredfire
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jan 19, 2011 2:22 pm
- Post datetime: 2011-06-11T04:41:35+00:00
- Post Title: Red Faction Armageddon BNK_PC audio files.

Never seen this extension before, nor is there anything on Google about it. Trying to extract some music from the game with no success. I unpacked the sounds.vpp_pc file, which gave me a bunch of these BNK_PC files.

Any help would be much appreciated!

Here's some sample files:

[http://dl.dropbox.com/u/7075762/RFAsamples.zip](http://dl.dropbox.com/u/7075762/RFAsamples.zip)

Thanks.
## Post #2
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2011-06-15T04:45:11+00:00
- Post Title: Red Faction Armageddon BNK_PC audio files.

ah ever usual BKHD header so wwise audio engine, files are too small to contain any music however, not sure on the HIRC sub type, could be just audio related data. Look for larger files, good bet to find riff vorbis audio within.
## Post #3
- Username: Schemer
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jun 11, 2010 10:59 pm
- Post datetime: 2011-06-16T20:56:53+00:00
- Post Title: Red Faction Armageddon BNK_PC audio files.

In sounds.vpp_pc exist two audio files type:
*filename*.bnk_pc – with “BKHD” header
And
*filename*_media.bnk_pc – with “VWSBPC  “ header

Sample files: [http://flashget3.ru/download/rfa_audio_samples.zip](http://flashget3.ru/download/rfa_audio_samples.zip)
## Post #4
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2011-06-19T06:04:50+00:00
- Post Title: Red Faction Armageddon BNK_PC audio files.

“VWSBPC “ header ones seem to contain as expected riff vorbis audio with even comment field on some of those files i had not seen before (may be problematic for ww2ogg due to data marker twice). There is notable zero byte areas between every file held in for one way to split out or use a plain wav scanner.
## Post #5
- Username: srredfire
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jan 19, 2011 2:22 pm
- Post datetime: 2011-06-22T16:59:23+00:00
- Post Title: Red Faction Armageddon BNK_PC audio files.

So any hope?
## Post #6
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2011-07-03T12:13:42+00:00
- Post Title: Red Faction Armageddon BNK_PC audio files.

Use Dragon Unpacker's Hyper Ripper that's how I got the audio, however you won't be able to play it yet.
Next, download the file I've attached to my post and extract it in the folder which you've extracted your .WAV files of the game.
Run the .bat file and it shall begin to convert the .WAV's to streamable .OGG files and you're good to go.
[redfactionarm-files.rar](https://xentaxbackup.github.io/file/4426_redfactionarm-files.rar)
## Post #7
- Username: Schemer
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jun 11, 2010 10:59 pm
- Post datetime: 2011-07-05T00:54:06+00:00
- Post Title: Red Faction Armageddon BNK_PC audio files.

2 FinalBlast, thank you!

it's realy work!!

p.s. ssory for my bad english
## Post #8
- Username: Gertax
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 25, 2017 1:04 pm
- Post datetime: 2017-04-25T05:32:09+00:00
- Post Title: Red Faction Armageddon BNK_PC audio files.

> Reply from FinalBlast
>
> Use Dragon Unpacker's Hyper Ripper that's how I got the audio, however you won't be able to play it yet.
Next, download the file I've attached to my post and extract it in the folder which you've extracted your .WAV files of the game.
Run the .bat file and it shall begin to convert the .WAV's to streamable .OGG files and you're good to go.

I tried that, but it's throwing me an error
