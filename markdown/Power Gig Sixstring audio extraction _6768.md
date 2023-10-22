## Post #1
- Username: jarredou
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Apr 07, 2011 10:48 am
- Post datetime: 2011-06-11T18:27:04+00:00
- Post Title: Power Gig Sixstring audio extraction ?

Hi there, I'm trying to extract audio from this musical game, a kind of rockband-like.

I got the PS3 version (there also a xbox360 version). So, from original disk, I have extracted 4 big data files (Data.pk0, Data.pk1....pk3). Audio files seems to be in the Data.pk1, some FSB4 are visible, with some little audio files inside. (xxx.crashcymbal.wav...xxx.kick.wav...etc...).

I have succeeded in extracting these files, but it's only "one shot" wavs from Drums part. After the FSB4 section in the data.pk1, there's some various stuff (coordinates, related midi files, cue files), and then a big part (20~50Mb, depends of the song), which is, I think, the real audio data. A kind of multitrack, but I can't find how to read/extract/decrypt this... :S

Here's the beginning of the data.pk1 file (it's just the 2 first songs, I cutted it just after 3rd song first data, I think) :
(the entire file is around 2Gb)
[http://www.multiupload.com/IHSMHEG8GJ](http://www.multiupload.com/IHSMHEG8GJ)

I hope someone can help me ! 


ps : and sorry if my english is a little approximative !
## Post #2
- Username: maxton
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jun 13, 2011 12:29 am
- Post datetime: 2011-06-12T18:04:21+00:00
- Post Title: Power Gig Sixstring audio extraction ?

I'm also interested in getting the music from this game.

I have copied the xbox 360 data files and looked through them with a hex editor.

For the 360, the files are:

```
Data.pk0 (2,082,771 kB)
Data.pk1 (1,778,578 kB)
Data.pk2 (1,346,453 kB)

```

[Data.hdr.e.2](http://www.mediafire.com/?xnqzh2q2qlyopb4) is most likely a type of header file, but it seems to be encrypted.

Data.pk0 contains XBOX achievement information, followed by an xml file for every song ([example for AVH](http://www.mediafire.com/?bj8ysutmjxcxk4c)), and many RIFF header'd files (XMA maybe?) [example](http://www.mediafire.com/?lgd03mbhbbk3b0p).

Data.pk1 contains RIFF files, like those in Data.pk0, but followed by midis for each song. I uploaded from the beginning to what seems to be the end of the first song's (AVH) data [here](http://www.mediafire.com/?tv02x37bkc8brdk).

Data.pk2 contains binaries for the xbox (ex. Bink) followed by bink video files and some other data.

So from this it seems that the XBOX uses XMA files while the PS3 uses FSB files.
## Post #3
- Username: marlborox
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Apr 09, 2011 10:03 am
- Post datetime: 2011-06-15T16:27:15+00:00
- Post Title: Power Gig Sixstring audio extraction ?

both use fsb, but ps3 uses mp3, 360 uses xma, the sound files you found are sfx (with the riff header), the music you are after is encrypted in the same manor as the latest guitar hero game but with a different key & by the looks of it in a slightly different way as the there appears to be an encrypted file associated with each music file but i don't know what this is but the midi files are not encrypted so that other encrypted file must have something to do with the key itself. On the 360 version, there are some tools on the disc too, bink rad tools, etc. I don't know what the other's are, maybe they were clumsy enough to leave the encryption/decryption tools on there too but you'd need to write an extractor to properly pull this one apart but i don't see anyone getting the AES key anytime soon unless they know exactly what they are looking for.
## Post #4
- Username: maxton
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jun 13, 2011 12:29 am
- Post datetime: 2011-06-18T21:06:24+00:00
- Post Title: Power Gig Sixstring audio extraction ?

I have a feeling we won't be able to write an extractor until that header file is decrypted, since it probably has all of the files' name/offset/size information that would be required. However, the header likely uses the same encryption method/key as the encrypted song data, so if we discover the key we'd be killing two birds with one stone.

I'm not very well-versed with XEX executable format, but if the developer did leave the binaries for decryption on the disc, we'd be in luck, because there are many people here who are.
## Post #5
- Username: keystothemaxim
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Oct 21, 2013 6:19 pm
- Post datetime: 2014-12-18T15:29:00+00:00
- Post Title: Power Gig Sixstring audio extraction ?

I read on a rock band customsong forum that the Power GIG files have finally been decrypted? Is it true?
## Post #6
- Username: maxton
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jun 13, 2011 12:29 am
- Post datetime: 2018-08-10T18:26:00+00:00
- Post Title: Power Gig Sixstring audio extraction ?

In case anyone gets to this thread, in the intervening 7 years since my last post here I learned to reverse engineer and you can now open Power Gig archives with my [GameArchives](https://github.com/maxton/GameArchives) library and decrypt the audio files with [this code](https://gist.github.com/maxton/88d65c22b1ef57e877a226b4d2555b2d) (which requires the gamearchives library).
