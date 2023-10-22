## Post #1
- Username: Tom_planeswalker
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jun 11, 2006 3:05 pm
- Post datetime: 2006-06-11T08:03:35+00:00
- Post Title: Realms Of The Haunting

Hello people,

I'm trying to access the speech/audio files from above mentioned game from Gremlin Interactive

[http://www.the-underdogs.info/game.php?id=889](http://www.the-underdogs.info/game.php?id=889)
(I'm using the official cd-version)

These files are packed in .DAT files, I've tried almost every program available to export them but to no avail

- Game Extractor Full
- Multi-Ex Share
- Dragon Unpacker
- Jaeder Nauber
etc...

I've managed to access these files using XWE Wad and I can listen and export them as wav but the files are very static and clearly wrongly exported (the voices are so static you can't even make out the words)
This is the program that's been the closest to me being able to access the files. Has anyone here ripped this game or know of a way to access the uncompressed content of these dat files? I would very much like to access these sound files without horrible static complety messing them up.

Regards
Tom
## Post #2
- Username: Tom_planeswalker
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jun 11, 2006 3:05 pm
- Post datetime: 2006-06-12T14:09:12+00:00
- Post Title: Realms Of The Haunting

Here's a sample made with watto's archive cutter
[DBASE500.DAT1.zip](https://xentaxbackup.github.io/file/761_DBASE500.DAT1.zip)
## Post #3
- Username: Tom_planeswalker
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jun 11, 2006 3:05 pm
- Post datetime: 2006-06-12T14:21:15+00:00
- Post Title: Realms Of The Haunting

Here's a sample of the uncompressed .wav format I can't find the right decoder for
[0001.zip](https://xentaxbackup.github.io/file/762_0001.zip)
## Post #4
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-06-13T16:52:41+00:00
- Post Title: Realms Of The Haunting

Just curious..the header "RIFF" it's reversed "FFIR"   but looks a .wav "modified"
## Post #5
- Username: Tom_planeswalker
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jun 11, 2006 3:05 pm
- Post datetime: 2006-06-13T20:26:53+00:00
- Post Title: Realms Of The Haunting

Probably has something to do with the encryption by Gremlin (?), maybe with the right adjustments you could make it riff again .  Could you play the file without static making it almost unhearable?
## Post #6
- Username: Tom_planeswalker
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jun 11, 2006 3:05 pm
- Post datetime: 2006-06-15T06:06:17+00:00
- Post Title: Realms Of The Haunting

This is what the developer of XWE found out

--

At this moment I don't know what format the ROTH sound files are. They are in a WAV container, but they use compression 42 (0x2A), for which I can't find documentation anywhere. The data is not even compressed. Previously XWE just displayed the sound data "as is", and even then the speech could be heard. If it were compressed, it would be a garbled mess.

What we need to figure out is what those bytes mean. It's trial and error. I tried several things, but haven't figured it out. The bytes are weird in the sense that they don't go "up and down" like usual wave data bytes do, but rather "stay on one side". One thing that did improve a bit was when I used the lowest bit to the most significant position. Grab the beta, that's how I left it. It's still very noisy, but you can hear the speech much better. That's where I'm stuck, unless someone knows what those bytes mean, I think it's hopeless.

--

In the attachment is the new wav, which is indeed somewhat improved.
[Another One.zip](https://xentaxbackup.github.io/file/764_Another One.zip)
## Post #7
- Username: Russell
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jun 21, 2006 5:39 pm
- Post datetime: 2006-06-21T09:44:22+00:00
- Post Title: Realms Of The Haunting

It would be nice to see some support for this game, it has some great textures and sounds in it, aswell as gfx.

I had a look at the fxscript.sfx file last night (I own the whole game myself, 4 cds of fun), I couldn't figure out the file format of it though
