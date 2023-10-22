## Post #1
- Username: Sn0wCrack
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 22, 2016 8:17 pm
- Post datetime: 2016-12-22T14:35:39+00:00
- Post Title: Genkai Tokki Seven Pirates .PAC files

These .PAC archives seem to be different compared to the other .PAC archives included in other IdeaFactory games.

All I can really comment on what little I can figure out is the first 7 bytes are some kind of header (an enum or something), it seems to start with 0x01 and end with 0x10 and has another 0x10 at 0x03 (usually)

I also believe there are at least 2 different types of the .PAC file, ones that contain models, textures, motion data, and ones that contain other forms of data (text and other things)

The other thing is it could just be some kind of compression format as well, as the header looks similar to the header on event script files (also included in the samples)

No clue where to go from here, any help on these would be greatly appreciated.

UPDATE:

It seems like all the text is stored in plain utf-8 at the end of the .bin event files


Samples: 
[https://mega.nz/#!NUJX0JQQ!K36b2YsZFzD0 ... RZysPbokHI](https://mega.nz/#!NUJX0JQQ!K36b2YsZFzD0xqLwB1zGDC-HlQZiHZOEkRZysPbokHI)
