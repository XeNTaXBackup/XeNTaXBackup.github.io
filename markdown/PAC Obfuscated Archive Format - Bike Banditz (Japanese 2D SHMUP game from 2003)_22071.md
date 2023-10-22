## Post #1
- Username: Habanero
- Rank: n00b
- Number of posts: 19
- Joined date: Thu May 02, 2019 2:36 am
- Post datetime: 2020-04-27T01:35:34+00:00
- Post Title: PAC Obfuscated Archive Format - Bike Banditz (Japanese 2D SHMUP game from 2003)

Hello. I would like to extract the two PAC files present in this MEGA folder (mainly to get the audio). I've included the filecutter results as well. I don't recognize any headers in HxD (looks like gibberish). Just for the hell of it, I tried the scripts on the QuickBMS page that have "pac" in them (none worked, of course).

[https://mega.nz/folder/I9QBkKrQ#W3rQGAyJ05_5cL7rVq4yDg](https://mega.nz/folder/I9QBkKrQ#W3rQGAyJ05_5cL7rVq4yDg)

I originally asked on Zenhax, and aluigi replied:

> Reply from aluigi
>
> There is some obfuscation in place.

32bit equal to one, followed by 0x40 bytes xored with 0x40 (example of GameData.pac):
Code: Select allba b1 8a 56 42 45 53 45 30 30 2e 49 4d 47 00 00   ...VBESE00.IMG..
7e e9 d1 77 00 00 40 00 60 90 39 01 f6 0c 10 00   ~..w..@.`.9.....
90 e9 d1 77 60 90 39 01 00 00 40 00 10 1f 54 00   ...w`.9...@...T.
00 00 40 00 00 00 00 00 c0 ff 12 00 43 b2 82 56   ..@.........C..V
Followed by a 32bit offset field but not sure what's the content from 0x48 to that offset, it's for sure xored with the same 0xac since there are some readable strings there.
I suppose it's compressed with some lzss algorithm and this reminds me of some game that used that algorithm with the data of the copy opcode xored with some constant that (if I remember correctly) was just 0xac.

Unfortunately I don't remember what was the game or maybe I'm confusing it with the lzss used in Allegro which uses xor on the flag and repeated characters.

So I wanted to crosspost here for more exposure. The game is really fun, and there are only a few menu images that need to be translated, so I want to try and get that out to give this game more exposure. In the meantime I'll just write a chart with quick instructions. Thank you for any assistance.
## Post #2
- Username: Habanero
- Rank: n00b
- Number of posts: 19
- Joined date: Thu May 02, 2019 2:36 am
- Post datetime: 2020-05-25T03:04:55+00:00
- Post Title: PAC Obfuscated Archive Format - Bike Banditz (Japanese 2D SHMUP game from 2003)

To update this, in case anyone was wondering: the audio is just a bunch of RIFF headers, easily extracted with VGM Toolbox. No luck on the texture/sprite extraction though.
