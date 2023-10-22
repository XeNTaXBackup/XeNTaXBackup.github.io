## Post #1
- Username: rubinho146
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Jun 14, 2016 10:13 pm
- Post datetime: 2016-06-26T18:10:27+00:00
- Post Title: South Park Rally RBH file/archive sound format

All the characters sound/voices seems to be in .rbh format, it seems like an archive for me with all the samples in there, I don't know if it's .wav or .aiff or anything similar.


I don't know if someone can help me with these.

I would like to edit those sounds and such.



Here I give one of the files, thank you.
[https://drive.google.com/file/d/0By_Xs8 ... RnVVU/view](https://drive.google.com/file/d/0By_Xs884e-hxd0NiQzBETlRnVVU/view)
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-07-09T16:35:03+00:00
- Post Title: South Park Rally RBH file/archive sound format

This is what I figured out so far:

```
uint32		fileSize
char[4]		"RBHF"

char[4]		"RBHH"
uint32		chunkSize
uint32		0
uint32		size of first BODY
uint16		2
uint16		4
uint32		0
uint32		size of second BODY
uint16		0
uint16		4

char[4]		"BODY"
uint32		chunkSize
for (numSounds) { // numSounds = chunkSize / 0x28
uint16		bitsPerSample (8 | 16)
uint16		0xFF | 0xE0
uint32		dataSize
uint32		sampleRate (4000 | 8000 | 11025 | 22050)
int32		-1	
uint32		1
uint32		1
uint32		dataOffset
uint32		0
uint32		0
uint16		0
byte		0xC8 | 0xFF
byte		0 | 1
}

char[4]		"BODY"
uint32		chunkSize
uint32		0
uint16		1
uint16		1
for (numSounds) {
// PCM, mono
byte[dataSize * bitsPerSample / 8] data // @dataOffset
byte[?]		padding (only if filesize % 4 != 0)
}

char[4]		"GLOB"
uint32		chunkSize
uint32		numSounds
uint32		unknown (mostly 1)
for (numSounds) {
uint32		unknown
uint32		offset to header chunk (first BODY)
}
```


You can extract and repack the sound files with this tool:
[viewtopic.php?f=32&t=14623](http://forum.xentax.com/viewtopic.php?f=32&t=14623)
## Post #3
- Username: SubDrag
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 23, 2015 8:49 pm
- Post datetime: 2022-02-11T16:07:15+00:00
- Post Title: South Park Rally RBH file/archive sound format

Heads up for anyone finding this thread.  This game uses Impulse Tracker for the music.  They actually just store the samples once, in sound\music\SP-SAMP.IT.  The music are Impulse Tracker as well, but don't bundle the samples (are at 0), called SPX-PATT.it.  You can open these right in OpenMPT, then import the samples.  You could also surely import it too and play with new music!

The N64 has the same exact format and method, though it is compressed, and samples are stored in a separate but simple compressed format (don't think same as PC).
## Post #4
- Username: HaajPaaj
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 12, 2022 9:50 pm
- Post datetime: 2022-07-12T13:59:19+00:00
- Post Title: South Park Rally RBH file/archive sound format

I just found this post, but have had confusion with loading the samples. In OpenMPT, do I have to export the samples as individual files and then load them? If so, how do I do this, and how does each song know what samples to use? I tried loading SP-SAMP.IT into the samples, and SP1-PATT.it into general but it doesn't work. I'm sure this is a dumb question, but I have not been able to figure this out. Your initial post seemed vague to me, I guess.
## Post #5
- Username: SubDrag
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 23, 2015 8:49 pm
- Post datetime: 2022-07-30T00:16:39+00:00
- Post Title: South Park Rally RBH file/archive sound format

The samples are all in SP-SAMP.IT.  The songs they didn't copy them to each one, so you have to take them from the sample file, and just import them into the songs.  The songs use indexes into samples, so if they're all there, it will pick the right one.
