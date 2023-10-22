## Post #1
- Username: lolbas
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Nov 18, 2015 11:59 pm
- Post datetime: 2017-11-17T22:54:57+00:00
- Post Title: Order & Chaos 2: Redemption terrains

Recently I've been trying to RE a terrain format from O&C2 game. While there are other file types associated with a single world chunk, the terrain file itself seem to contain such info as:
- heightmap;
- textures list;
- texture mapping;
- water level;
- water type (normal, lava, tar, etc).
For now I've only been able to determine heightmaps.

Format template as what I do know by now can be found [here](https://github.com/lOlbas/Game-Engines-Filetypes-Reverse-Engineering/blob/master/engines/Gameloft/trn/v10/templates/TRN.bt).

So far, terrain is a 64x64 chunk. The format consists of 6 sections:
- header;
- section one (starts at 0x10, consists of 8b marker + 64 structures of 12 values (2 byte each);
- section two - heightmap (starts at 0x618, consists of 65x65 2 byte values);
- section three - possibly water level (starts at 0x271A, consists of 65x65 2 byte values);
- section four (starts at 0x481C, consists of 65x65x3 bytes);
- strings - textures used by chunk.

My main question is: can someone help me determine at least how do textrues are used in this format? I lack general understanding of concept of how do textures applied to terrain.

In the attached archive you can find .obj and .h2o files to view terrain model in hex2obj, original .trn file which to be used by 010 Editor template and screenshot from hex2obj showing terrain.
[0009_-010.zip](https://xentaxbackup.github.io/file/13557_0009_-010.zip)
## Post #2
- Username: lolbas
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Nov 18, 2015 11:59 pm
- Post datetime: 2018-01-17T08:27:44+00:00
- Post Title: Order & Chaos 2: Redemption terrains

A few additions to refresh a post.

Once again, terrain is a 64x64 chunk. The format consists of 6 sections:

1. Header.
2. Section one (starts at 0x10, consists of 8b marker + 64 structures of 12 values (2 byte each).
3. Section two - heightmap (starts at 0x618, consists of 65x65 2 byte values).
4. Section three - possibly water level (starts at 0x271A, consists of 65x65 2 byte values).
5. Section four (starts at 0x481C, consists of 65x65x3 bytes).
6. Strings - textures used by chunk.

A few examples of section one:

```
    0020h 02 00 03 00 04 00 FF FF 0A 40 60 00 14 00 9F 23

```


Splitting section into 2-byte `unsigned short` values we get a sequence (every row is some random sample): 

```
    20:    0 1 0            4 2 -1 5  5 2.019531 96 20 0.01488495
    41:    0 1 0.0008239746 8 2  3 4  9 2.019531 96 20 0.01488495
    63:    0 1 0.0008239746 1 2  3 4 -1 2.019531 96 20 0.01488495

```


So we have only 64 such sequences for any terrain taken. As we see, most of the values are repeating for some reason.

Sections 2 and 3 are not very important: 2 is heightmap, 3 seem to be waterlevel.

Now, section 4 is weird one. It consists of 65x65x3 bytes. So every terrain vertex has 3 bytes of additional info which probably has something to deal with textures. A few samples:

```
     939: F2 7D ED
    1548: F8 7F FE
    4224: 00 7F 00

```


Second value doesn't seem to go lower than 115 for sample file.

I haven't found a maximum number of textures possible, but in the example attached there are 16 textures used. In this particular format all textures can be layered upon terrain chunk and every terrain vertex might have a weight value for each of the textures. However I didn't succeed on finding any patterns on texture indeices or anything similar. I hope someone could give me a couple ideas on where to move on.

Sample file on [mediafire](http://www.mediafire.com/file/cdaj676vbz887p1/0009_-010.trn).
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-01-18T11:26:37+00:00
- Post Title: Order & Chaos 2: Redemption terrains

I'd suggest to check some trn files in irfanview for example (load as raw file):



trn.jpg (72.9 KiB) Viewed 51 times


Thus you might get more insight how this works.

(guess, the texture format uses some compression)
## Post #4
- Username: lolbas
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Nov 18, 2015 11:59 pm
- Post datetime: 2018-01-18T13:09:59+00:00
- Post Title: Order & Chaos 2: Redemption terrains

> Reply from shakotay2
>
> I'd suggest to check some trn files in irfanview for example (load as raw file)I seem to not understand why load terrain file in irfanview since trn does not contain anything that could be viewed as multimedia.

> Reply from shakotay2
>
> (guess, the texture format uses some compression)Texture itself is s PVR image, external file.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-01-18T15:11:02+00:00
- Post Title: Order & Chaos 2: Redemption terrains

> Reply from lolbas
>
> Texture itself is s PVR image, external file.ok, then, I didn't get this - I thought, the textures were included in the trn file.

When you're talking about "sections" it's unclear whether it's related to the texture files or the trn files.

Your question was how the textures are mapped to the terrain, right?

So the usual proceeding (for PC, not consoles) were to give the trn file a structure, find sections, then zero out bytes that might address textures (could result in annoying trial 'n error, yes).

Then save (or repack if required) the changed trn and start the game.
Then some texture should be missing so you'd know the data you zeroed out refers to that missing texture.
