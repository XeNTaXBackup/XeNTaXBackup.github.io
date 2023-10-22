## Post #1
- Username: oux
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jan 28, 2017 3:45 am
- Post datetime: 2017-02-12T09:46:51+00:00
- Post Title: How to convert .raw audio files?

Hello, I just extracted music from the game Stronghold, but all music files have .raw file extension. Any ideas how to convert them into regular audio file formats?
Here is the example: [http://rgho.st/6pfkHsf2j](http://rgho.st/6pfkHsf2j)
## Post #2
- Username: peter2005
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Mar 25, 2016 3:26 pm
- Post datetime: 2017-02-12T11:43:41+00:00
- Post Title: How to convert .raw audio files?

it's seems to be 16bit PCM, Stereo ,44KHz  raw audio, any audio editor like Audacity can convert it to wav or other more convenient format
## Post #3
- Username: oux
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jan 28, 2017 3:45 am
- Post datetime: 2017-02-12T13:14:35+00:00
- Post Title: How to convert .raw audio files?

> Reply from peter2005
>
> it's seems to be 16bit PCM, Stereo ,44KHz  raw audio, any audio editor like Audacity can convert it to wav or other more convenient format
What is the best audio format for these files? .wav?
I am not sure if .mp3 cut some quality.
## Post #4
- Username: peter2005
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Mar 25, 2016 3:26 pm
- Post datetime: 2017-02-12T17:10:00+00:00
- Post Title: How to convert .raw audio files?

If you want exact quality as in a game and don't mind file having 10mb just save it as wave, otherwise if the size matters and/or you want to listen to it from a mp3 stick, pick mp3.

use google for more info
## Post #5
- Username: oux
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jan 28, 2017 3:45 am
- Post datetime: 2017-02-12T18:15:19+00:00
- Post Title: How to convert .raw audio files?

I don'y dare to bother you more, you helped me enough... 
But, if I import .raw files to Audacity with this settings: 16-bit PCM, Little-endian, 2 channels, 44100 Hz - the music plays like two time faster than expected, why is that?
## Post #6
- Username: peter2005
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Mar 25, 2016 3:26 pm
- Post datetime: 2017-02-12T18:40:48+00:00
- Post Title: How to convert .raw audio files?

> Reply from oux
>
> I don'y dare to bother you more, you helped me enough... 
But, if I import .raw files to Audacity with this settings: 16-bit PCM, Little-endian, 2 channels, 44100 Hz - the music plays like two time faster than expected, why is that?

I do not know how original sounds, try to change sample rate to 22050, but to me it sounds too slow..but who knows
## Post #7
- Username: oux
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jan 28, 2017 3:45 am
- Post datetime: 2017-02-12T19:22:16+00:00
- Post Title: How to convert .raw audio files?

> Reply from peter2005
>
> oux wrote:I don'y dare to bother you more, you helped me enough... 
But, if I import .raw files to Audacity with this settings: 16-bit PCM, Little-endian, 2 channels, 44100 Hz - the music plays like two time faster than expected, why is that?

I do not know how original sounds, try to change sample rate to 22050, but to me it sounds too slow..but who knows
Thank you, it works...
But, how to determine the true frequency of the music? 22050 sounds good, but I am not sure if it is true frequency of this music.
## Post #8
- Username: peter2005
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Mar 25, 2016 3:26 pm
- Post datetime: 2017-02-12T19:54:35+00:00
- Post Title: How to convert .raw audio files?

> Reply from oux
>
> peter2005 wrote:oux wrote:I don'y dare to bother you more, you helped me enough... 
But, if I import .raw files to Audacity with this settings: 16-bit PCM, Little-endian, 2 channels, 44100 Hz - the music plays like two time faster than expected, why is that?

I do not know how original sounds, try to change sample rate to 22050, but to me it sounds too slow..but who knows
Thank you, it works...
But, how to determine the true frequency of the music? 22050 sounds good, but I am not sure if it is true frequency of this music.

Problem is that the .raw file is headerless wav file .i.e there are no information how it should be played. Both 44100 and 22050 are standard most likely used bitrates(you can try also 32000). 

You would have to reverse engineer the game to determine the true frequency for sure, or try to find already extracted tracks from the game somewhere on the internet.
## Post #9
- Username: Pepper26
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Feb 14, 2017 11:06 pm
- Post datetime: 2017-02-14T15:19:38+00:00
- Post Title: How to convert .raw audio files?

keep in mind source files might not be stereo, so importing it to stereo tracks would make it play twice as fast but the same or similar pitches to the ones you hear in game.  if it sounds off in both speed and pitch, you have the wrong sample rate.

commonly used ones include:
48000hz 44100hz 41000hz 36000hz 32000hz 28000hz 22050hz 18000hz 16000hz 11025hz 8000hz 6000hz.

though I have encountered files at strange rates like 40095hz adpcm in a file in rage, or 14000hz in turok 2 on n64.
