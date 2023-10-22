## Post #1
- Username: BlackFurniture
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Aug 16, 2016 11:53 pm
- Post datetime: 2016-08-16T15:57:46+00:00
- Post Title: Final Fantasy: Crystal Chronicles (GC) BGM/WD/WI decoder

Hi! I've been spending some time reverse-engineering the wavetable (WD), instrument info (WI) and sequence (BGM) files for Final Fantasy: Crystal Chronicles.

The file formats are a similar to the PS2 Squaresoft BGM/WD files, but specifically tailored for the GameCube. For example, the endian is different, looping ADPCMs are used, ADSR is done in software, etc. FFCC also has instrument and sample names stored in .wi files, even though they are not actually used in the game. 

I discovered that VGMTrans is slightly off, and misses or misinterprets some variables in the data, so my discoveries may be useful for that project (if it's still being maintained?). Reverse-engineering was helped by the fact that a debug symbol map was left in the game data, so I was able to restore some function names.

I have written a BGM/WD/WI to Renoise song converter, which I believe is quite accurate. It maps everything, i.e. song loops, notes, ADSR, and track effects/commands.

Renoise .xrns for every BGM: [Download](https://mega.nz/#!0J1BlaBY!paT89SGySWJCAHWoaUw0ohl-Roqjek08r1PSAQVK-Z0)
Converter source: [GitHub](https://github.com/BlackFurniture/ffcc/blob/master/ffcc/audio.py)

The only thing that was difficult to map was the reverb effect parameters, but I think my solution is pretty faithful to the original.

Please let me know if you hear anything odd in the songs. You can listen to them using the free version of Renoise (even though you can't render to files using the demo).

The next step would be to get rid of Renoise and write a custom player in C++/Python/both. I'm not sure if that would be worth my time, but I'd like to know what you think.
## Post #2
- Username: a574045075
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun May 29, 2011 4:25 pm
- Post datetime: 2016-08-23T02:10:08+00:00
- Post Title: Final Fantasy: Crystal Chronicles (GC) BGM/WD/WI decoder

Thank you for sharing, but how to use the audio.py file?
