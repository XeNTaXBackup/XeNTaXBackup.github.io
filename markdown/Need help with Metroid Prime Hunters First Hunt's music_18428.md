## Post #1
- Username: GordenF
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Jul 16, 2016 6:14 am
- Post datetime: 2018-07-12T08:29:28+00:00
- Post Title: Need help with Metroid Prime Hunters: First Hunt's music

Hello everyone!

I'm trying to decode this game's music format, but it seems I've hit a roadblock.
Have some files first:

The raw audio file: https://i.peterwunder.de/BGMDATA_0005D4AB.raw
Its header: https://i.peterwunder.de/HEADER_0005D4AB.bin
What I managed to salvage with sox: https://i.peterwunder.de/BGMDATA_0005D4AB.wav (warning, loud)
And the sox command: Code: Select allsox -t vox -e signed-integer -b 4 -r 11025 -c 1 BGMDATA_0005D4AB.raw -r 44100 -b 16 BGMDATA_0005D4AB.wav

I know I'm close, but what I have right now is a far (and bitcrushed to all hell) cry from what the file is supposed to sound like: [https://www.youtube.com/watch?v=ZpeBEgH53Qs](https://www.youtube.com/watch?v=ZpeBEgH53Qs)
There has to be a way to get it to sound good, this is the only file in the game's filesystem that even contains music. The person who made the Youtube video has to have gotten the music from somewhere.  

I don't even know if that sox command was correct, I just know it outputs something that's identifiable as music.
I know it's probably some form of ADPCM, NDS devs love ADPCM.  I looked up how ADPCM is usually decoded and it seems there are some state variables that can optionally be set using data from the file's header, but I can't find anything useful in there.

Here's all I know about the file header:

uint: file length
4 null bytes
ushort: sample rate (11025)
2 null bytes
always 00 04 01 00 00 00, possibly ADPCM-related
uint: file length, but shifted 2 bytes to the right for some reason and also sometimes off by one

Can anyone help me properly decode this?
