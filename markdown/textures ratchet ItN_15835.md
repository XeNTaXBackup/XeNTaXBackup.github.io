## Post #1
- Username: theismarius
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jan 14, 2017 8:11 am
- Post datetime: 2017-02-05T17:05:38+00:00
- Post Title: textures ratchet ItN

Hi, early before have extracted models from ratchet and clank games, the only thing left is the textures, have been trying to get them for weeks without any results, someone who knows how to extract them gave me this instructions

"The textures are not in the irb, only the hash is.

To find the textures
you need to get the hashes from the irb find them in shaders.dat and get the id, find the id in assetlookup.dat and get the size and start of the texture, then manually extract them.

After you manually extract them you will then need to find out what type the texture is (PVRTC, DXT1,DXT5) and manually add a header to it.

Finally you would need to manually fix the textures if they are PVRTC by swaping the the Blue with Alpha ans Red with Green."

Ive tried so many things, but dont know how to start.

Could anyone help?

Thx theismarius
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-02-05T17:28:08+00:00
- Post Title: textures ratchet ItN

well , then let's give that a try.
As I've told you I never extracted those textures so let's follow the receipe step by step:
1) in irb: hash of texture
2) find hash in shaders.dat, get the id
3) find id in assetlookup.dat -> get size and start of texture

I don't know about the hashes and the ids, I hope you do, else you've to ask the creator of the receipe for more infos.

So, do you have a hash of a texture from irb file?
If so, use a hex editor to find that hash in the shaders.dat and post a picture of the block
containing the hash, minus x0100 bytes before and +0x100 bytes after (0x200= 512 bytes)
## Post #3
- Username: theismarius
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jan 14, 2017 8:11 am
- Post datetime: 2017-02-05T19:37:02+00:00
- Post Title: textures ratchet ItN

Well, i have a problem, im spanish, and when it says hash, not of the translations found relates with this, so could you tell me what is hesh?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-02-05T19:59:43+00:00
- Post Title: textures ratchet ItN

"hash" is some kind of unique number bound to objects or strings.
The wiki description is: a hash is used to "map data of arbitrary size to data of fixed size".
What does that mean? Hashes have constant length (4, 8, 16 whatever) while the strings (for example) bound to them have not.

I don't know which size the hashes in the irbs have. I had a look at a small irb file but I don't have a clue where the hash should be.

In wpn_bat_projectile.entity.irb it might be C3ECE7286B061502, but that's a wild guess only.
(built/tuids/c3e/ c3ece7286b061502)
## Post #5
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-02-06T15:52:40+00:00
- Post Title: textures ratchet ItN

Incomniac engine uses DXT1, DXT5 and swizzled RGBA8 texture types (they are usually used on detail or HD textures like character faces). 
There are cached and uncached archives, uncached have highest mip detail.
## Post #6
- Username: theismarius
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jan 14, 2017 8:11 am
- Post datetime: 2017-09-01T15:49:46+00:00
- Post Title: textures ratchet ItN

Hi, has pases 6 months since been trying to get textures from this game with texture finder, but couldnt manage it. They told me that the Best way was with hdx hex editor. But dont know how it work. Could someone help please?

[http://imgur.com/a/Xoq6J](http://imgur.com/a/Xoq6J) that is an image of hwat ive got

Thanks for all
## Post #7
- Username: OverLord115
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Oct 26, 2017 12:52 am
- Post datetime: 2017-11-08T00:08:28+00:00
- Post Title: textures ratchet ItN

[quote="theismarius"]Hi, has pases 6 months since been trying to get textures from this game with texture finder, but couldnt manage it. They told me that the Best way was with hdx hex editor. But dont know how it work. Could someone help please?

Its very simple with the texture finder, (I did not know if the ratchet and clank games have similar files, but since I'm dealing with Resistance 2, which was created by the same company, I guess it will have the same or similar ones) in the program you need to load any texture.dat file, then use the DTX1, DTX3 or DTX5 options and you will see the textures (i'm not sure if each and every one of the textures will be seen as it is in my case).
