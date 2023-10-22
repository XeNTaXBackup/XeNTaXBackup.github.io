## Post #1
- Username: WhiskeyTangoFoxtrot
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 03, 2020 4:47 pm
- Post datetime: 2020-01-03T09:08:42+00:00
- Post Title: [Star Citizen] .bnk extraction issues

Hey folks,

Recently I decided to dive into SC to do some analysis on the sound design. Extracting files from the available Wwise sound banks used to be easy with a lot of tools you can find on git. After early 2017 they switched to packing all assets in p4k format. After some time a p4k extractor was created. However, it now seems like the Wwise sound banks themselves are no longer extractable. Possibly due to them using a newer version of Wwise? Difficult for me to say, as I am not a programmer so my expertise on the matter ends here.

I've tried extracting the bnk files with every extractor I could find on git and none seem to be able to do the trick. I am at a loss and am wondering if anyone is able to figure out why this is the case.

I have a sample file that I know 100% contains audio data, as the same file contained audio in the older bnk version. If anyone needs more samples however, please let me know.

[https://drive.google.com/file/d/1L-qhwJ ... sp=sharing](https://drive.google.com/file/d/1L-qhwJVZ0Ids7wIXEHLKt0GGjxQUT0EU/view?usp=sharing)
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-01-03T16:01:14+00:00
- Post Title: [Star Citizen] .bnk extraction issues

Just from looking at that file, it doesn't seem to contain any audio data.  It contains a "HIRC" section which is just information about the sounds.  More files are probably needed to analyse (I don't have the game).
## Post #3
- Username: WhiskeyTangoFoxtrot
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 03, 2020 4:47 pm
- Post datetime: 2020-01-03T17:26:40+00:00
- Post Title: [Star Citizen] .bnk extraction issues

Thanks for the help.

I've uploaded some more samples, this time with some files that are bigger in size, hopefully there will be some hits in here. I also included some wem files I was able to dig up.

[https://drive.google.com/open?id=1Y45Fs ... xGHxHSovxX](https://drive.google.com/open?id=1Y45FsH7iqIHLfL6xfqkHlaxGHxHSovxX)

Going to keep sniffing around the data file to see if I can find anywhere else these assets are could be stored.
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-01-03T22:27:38+00:00
- Post Title: [Star Citizen] .bnk extraction issues

The "VERB_INT_Caves_Large_Cavern_Bright" file looks like it has audio, as does "CIG_Distortion".  The audio data itself is headerless, so I'm not sure what format it's in.  Usually, if the file has a DIDX and DATA section, then it'll be audio.

If anyone knows how the audio format is indicated in the header, it should then be possible to extract it in a playable format.  Ripping the actual raw data is easy, just not sure what to do with it.
## Post #5
- Username: WhiskeyTangoFoxtrot
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 03, 2020 4:47 pm
- Post datetime: 2020-01-04T23:32:46+00:00
- Post Title: [Star Citizen] .bnk extraction issues

I tried using ww2ogg to convert the wem files I was able to extract into ogg. But it gives a 'missing RIFF' error. The samples I provided look to be Impulse Responses for use within wwise's convolution reverb plugin. They should technically be wav files as usually lossless formats are used for IRs. But for some reason these extractors can't parse the data.
