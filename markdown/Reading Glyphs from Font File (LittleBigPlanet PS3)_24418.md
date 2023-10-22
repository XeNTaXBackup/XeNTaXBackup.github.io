## Post #1
- Username: Miles2345
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Sep 08, 2014 5:24 am
- Post datetime: 2021-08-28T01:16:40+00:00
- Post Title: Reading Glyphs from Font File (LittleBigPlanet PS3)

Hi, I've been trying to understand the font file format in LittleBigPlanet on the PS3 for some time, and I was wondering if I could get some help understanding the way it stores glyphs. I'm not sure if they're vector or bitmap but my guess is that they're vector as I'm not able to get much usable data from most graphic viewers. Ultimately, I'd like to eventually be able to import my own fonts to this game.

Similar to the rest of the files in this game, the first 8 bytes represent the magic and the revision number (later games use a later version of the file format), then there seems to be some offset and four dummy bytes. Then there seems to be some sort of table that contains all the characters that exist in the font. Not really sure about the structure of the rest of it. My assumption is the offset (+8) is where the actual graphic data starts.

I'm pretty certain this is a proprietary format. This game uses dds files for textures otherwise.

I'm not particularly familiar with how fonts work in general, so if anybody on this forum has more knowledge than I do, I'd love to learn more about them.

Here are a few samples - [http://puu.sh/I75bh.7z](http://puu.sh/I75bh.7z) 
I would appreciate any and all help - thank you in advance
