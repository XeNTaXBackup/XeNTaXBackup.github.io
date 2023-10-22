## Post #1
- Username: LaughingOtter
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 08, 2010 2:46 am
- Post datetime: 2010-10-07T20:06:19+00:00
- Post Title: 7th Level Audio Formats

Hi!
Dunno if this has been covered before. I couldn't find anything like this in the Forum.
I've been hit with a real poser of a problem. A friend of mine and I both have the 7th Level "Meaning Of Life" game CDs and we would both like to extract sound clips from the game for use in Flash projects.
Using Watto's Game Extractor I was able to find out that the internal format file extension for the sound files was .12. The sound files are encoded at about 8KB, and here is where things get nasty...
I have no idea what was used to encode the audio files or how to decode them. I note the game uses DirectX6 (this was 1997), but none of the DirectX utilities were any help. Audacity was the only program willing to work with the raw files as audio clips at all, and it was this way I confirmed these as being audio files.
Could anyone point me in the right direction to decode audio files? I'm certain this will not be the last time I'll be doing this.
Thanks very muchly!
## Post #2
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2010-10-10T07:20:16+00:00
- Post Title: 7th Level Audio Formats

You need to supply example file(s) as most don't likely have the game in question even then, it can be tricky given many audio formats in that era.
## Post #3
- Username: LaughingOtter
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 08, 2010 2:46 am
- Post datetime: 2010-11-12T19:31:16+00:00
- Post Title: 7th Level Audio Formats

D'OH!
Of course that would help. Sorry about that.
Here are three such files.

[http://www.laughingotter.com/music/File_001254.12](http://www.laughingotter.com/music/File_001254.12)
[http://www.laughingotter.com/music/File_003490.12](http://www.laughingotter.com/music/File_003490.12)
[http://www.laughingotter.com/music/File_010460.12](http://www.laughingotter.com/music/File_010460.12)

I haven't been able to get anywhere with these in the last month with any audio extraction tool I've seen out there.
I'd also like to extract stuff from National Lampoon's Chess Maniac 5 Billion And One, but I've not had any luck with that one at all.
## Post #4
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2010-11-14T09:32:36+00:00
- Post Title: 7th Level Audio Formats

Ok, had a look and they are 22khz mono ima adpcm audio, despite the header values implying pcm. can decode/playback with GENH/vgmstream, just use 0x09 ima to make genh header.
## Post #5
- Username: LaughingOtter
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 08, 2010 2:46 am
- Post datetime: 2010-11-16T23:34:40+00:00
- Post Title: 7th Level Audio Formats

You're a genius, Apollo!
The latest Audacity can import the raw data at those specs with very minimal distortion. These resulting files are pretty damn close to perfect, but there's still a bit of fuzz, no doubt caused by my having to import them as VOX ADPCM instead of IMA ADPCM. I couldn't get vgmstream to output anything.
Anyways, this is better than anything I've been able to come up with! Thank you very much!
## Post #6
- Username: LaughingOtter
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 08, 2010 2:46 am
- Post datetime: 2010-11-17T21:32:12+00:00
- Post Title: 7th Level Audio Formats

The SFX is coming over reasonably good, but the speech is terrible. I don't know whether this was the original sound quality or what.

Now how do you go about changing the header in a hex editor? What hex values need to go in at what hex location?
## Post #7
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2010-11-26T12:06:31+00:00
- Post Title: 7th Level Audio Formats

Damn... been away so sorry for late response... Anyway don't use vox adpcm, it is not proper decode of ima audio, as they are different and quality difference is notable.

use [http://www.hcs64.com/manakoAT/genh_creator.html](http://www.hcs64.com/manakoAT/genh_creator.html) GENH aka Generic Header Creator, and with it select the file, and fill in the entries, just pick 0x09 ima format from list and interleave can be put zero/ignored with mono data and while there is header crap, it didnt seem to matter in playback what i tried so i kept header skip to zero, click use file end and then finally create generic header, just don't select the option of create only header option.

then just either try test.exe command line converting (use the dos console to pass the commands) or vgmstream plugin (winamp for example) to playback the created *.GENH file, if sounds fine, parameters correct, if not... try adjusting.

anyway genh is the easiest route to take even tho, workful if want many files converted. Well, if i had time could try do automated bat to do them all. Also remember have the vgmstream dlls too in same folder as test exe or the player program folder.

If you have problem with certain files, put samples up and ill check.
