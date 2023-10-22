## Post #1
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2006-05-02T11:22:44+00:00
- Post Title: Rayman 3 ADPCM audio

Hello,

I would like some help with this.
I managed to extract some .wav files from Rayman 3: Hoodlum Havoc - Pc version. ( the data.hst file )
I released a codec finder program on it, and it said it was ADPCM.
I can't play ADPCM audio! I need a converter or something like that!
I attached one of the files with this post.
Can anybody try to find out how they can be played?
[ADPCM.zip](https://xentaxbackup.github.io/file/735_ADPCM.zip)
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-01-18T13:36:58+00:00
- Post Title: Rayman 3 ADPCM audio

Looks like the audio of king kong, the decoders identify the data like Ms-adpcm but can't convert

At the moment i have no idea how to reconvert it
## Post #3
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2007-06-27T14:57:58+00:00
- Post Title: Rayman 3 ADPCM audio

*Big Bump - Sorry!*

Does anybody have any idea?
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-06-28T11:49:47+00:00
- Post Title: Rayman 3 ADPCM audio

Even VLC can't play it. So this file must be really corrupt.
## Post #5
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-06-28T18:42:30+00:00
- Post Title: Rayman 3 ADPCM audio

I do not believe the file to be (fully) corrupt. When visualized, the data shows distinct patterns (see attachment). There is no sign of a compression I am familiar with, but it is quite definitely not the IMA variant of ADPCM -- at least not directly. On the other hand, I have not seen enough samples of MS ADPCM to be able to identify this method.

Also note the regular distances between areas with minimum and maximum values -- possibly chunk borders?
[Data 05063.gif](https://xentaxbackup.github.io/file/1237_Data 05063.gif)
