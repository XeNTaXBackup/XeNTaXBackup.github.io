## Post #1
- Username: ofthriceandmen
- Rank: n00b
- Number of posts: 18
- Joined date: Sat Dec 01, 2018 1:08 am
- Post datetime: 2021-10-31T00:25:46+00:00
- Post Title: Marvel Ultimate Alliance 1 Xbox Prototype Audio Extraction Issues

Since asking for help here with 1 problem worked, I figured I'd try my luck again.

These are then audio files from the Marvel Ultimate Alliance 1 Xbox Prototype. The main file we're worried about it "x_voice," but I've included them because of the strangeness of it and thinking maybe having them all will make it easier to figure out.

[https://drive.google.com/file/d/1WcXJgt ... sp=sharing](https://drive.google.com/file/d/1WcXJgtqSOQDLU8vyiEcqbfctMWxzjVIm/view?usp=sharing)


The audio in all the files can be extracted with foobar and can also be listened to and edited with this program, which says they're all XBADPCM files:

[https://www.mediafire.com/file/tbqzfjob ... r.zip/file](https://www.mediafire.com/file/tbqzfjob972cfz4/Uploaded_2013-09-10_ZSMsoundeditor.zip/file)

But not all of the audio plays. But all of the audio, even the ones that don't play, are all different file sizes and play lengths. And it seems random as to which play and which won't. The files with "_v" are voiceover lines and "x_voice" also has voiceover lines in it as well. These are the most important for us to want to hear, but they also tend to be the ones that won't play. "x_voice" has some that will play, but many that won't and based on the filenames in that file, some of the ones that won't play were cut out of the final game and so of course we'd like to hear them.

Does anyone have any idea what's going on?

The audio, most especially the x_voice audio, would be very useful to us in the Marvel Mods community, and I thought I'd ask here and see.

Thanks for reading this.
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-10-31T02:08:33+00:00
- Post Title: Marvel Ultimate Alliance 1 Xbox Prototype Audio Extraction Issues

All of the ZSS/ZSM files load ok in Foobar.

When you say they don't play, do you mean they're silent?  The reason they're silent is because those files are completely blank, so there is nothing to hear.  For example, all of the files in x_voice beginning with "an_" or "break_" have no audio data so you just get half a second of silence for each one.

Similarly, with a lot of the other "_v" files, the filename is shown as "blank.xbadpcm", indicating that it's just a placeholder with no actual audio.
## Post #3
- Username: ofthriceandmen
- Rank: n00b
- Number of posts: 18
- Joined date: Sat Dec 01, 2018 1:08 am
- Post datetime: 2021-10-31T02:31:51+00:00
- Post Title: Marvel Ultimate Alliance 1 Xbox Prototype Audio Extraction Issues

No, I don't mean the ones that are called "blank."
Take x_voice for instance. None of the files there are blank and yet some play and some don't.
The ones starting with "an_" and the ones starting with "break_" are different sizes and lengths and don't play.
That's what I mean. They seem to be different files and not just the same blank over and over.
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-10-31T11:19:28+00:00
- Post Title: Marvel Ultimate Alliance 1 Xbox Prototype Audio Extraction Issues

Yeah, as I mentioned, those in x_voice are also blank - the audio data for those are just zeroes according to the file table, so they're silent.  In x_voice, the file table starts at 0x1754 (0x54 bytes per entry).  The first 2 values are data offset and data size.  If you check those for the "an" and "break" files, you'll see there's no audio data there at all for those.
