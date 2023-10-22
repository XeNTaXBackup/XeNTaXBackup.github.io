## Post #1
- Username: Dragosh
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Apr 23, 2019 8:11 pm
- Post datetime: 2019-04-23T12:15:49+00:00
- Post Title: The Ward 2000 / Music rip

So there is a game by the name "The Ward" , kinda old game from 2000, i am trying to extract the music from it but i have not managed to do so with public available tools.

The data is stored in .RES files (at least i think so), i do have the copy of the game on CD, i dont know if sharing the files is allowed, if someone could try to extract them themselves ?
## Post #2
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2019-04-25T04:15:32+00:00
- Post Title: The Ward 2000 / Music rip

Sharing files is allowed... please upload some samples so we may help you
## Post #3
- Username: Dragosh
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Apr 23, 2019 8:11 pm
- Post datetime: 2019-04-25T06:58:13+00:00
- Post Title: The Ward 2000 / Music rip

Here i have uploaded the 4 files that are zipped

[https://multiup.org/download/168f8f476f ... 7Z-001.zip](https://multiup.org/download/168f8f476fd9f159205e77bc8ba1d600/drive-download-20190425T065027Z-001.zip)
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-05-10T19:03:07+00:00
- Post Title: The Ward 2000 / Music rip

The music files are all in WARD101.RES and WARD102.RES

The file RESDIR.DAT on CD 1 contains an index to all 4 .RES files.  From what I can tell, the music is 16-bit PCM (little endian), stereo, 22050 Hz.  These files don't have recognisable headers, but do have a few bytes indicating the audio rate and number of channels at the start of each file, so it's possible to construct a RIFF/WAVE header to play them normally in something like foobar.

I could possibly conjure up a small program to extract these and add a WAVE header ...
## Post #5
- Username: Dragosh
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Apr 23, 2019 8:11 pm
- Post datetime: 2019-05-15T12:31:35+00:00
- Post Title: The Ward 2000 / Music rip

I could upload all the files from the game if you need any more ?
## Post #6
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-05-15T16:56:47+00:00
- Post Title: The Ward 2000 / Music rip

I have all of the files 

Attached is my simple command line program to extract all of the audio and add a WAVE header.  It's fairly simple, but let me know if it works, or if you have any problems.


Dave
[wardex.zip](https://xentaxbackup.github.io/file/16247_wardex.zip)
## Post #7
- Username: Dragosh
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Apr 23, 2019 8:11 pm
- Post datetime: 2019-05-15T22:28:47+00:00
- Post Title: The Ward 2000 / Music rip

Files got extracted and i ended up with 683 separate wav files all going in sequence, 

seeing and listening to how the music is playing it leaves me to believe that the game picks which tracks to play from a "table" and loop from track number x to track number x

So for starters i can say that the extractor did his utmost excellence with the wav extraction, i recognise music and other sound effects files, and ill have to go through all the 683 files .
## Post #8
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-05-16T15:58:25+00:00
- Post Title: The Ward 2000 / Music rip

Thanks.  Glad to be of assistance.  Enjoy the audio!


Dave
