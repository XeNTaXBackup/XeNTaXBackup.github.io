## Post #1
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2019-03-08T16:05:11+00:00
- Post Title: EASTL hash for file names in .big file

Hi, I have been looking a way to calculate hash value for file names from this kind of EA's .big archive ([http://aluigi.org/papers/bms/fightnight.bms](http://aluigi.org/papers/bms/fightnight.bms)). I think it's some kind of EASTL hash but I'm not sure. Same hash is used also in .bh (big header file) files from FIFA series but I haven't found a tool which can calculate the hash. I can rebuild big files in files which already is in the big file, but I can't add new files because I don't know the hash.

I found visceral tools ([https://github.com/gibbed/Gibbed.Visceral](https://github.com/gibbed/Gibbed.Visceral)) which can rebuild .big files from Dead Space and calculate hash for file names. Im not sure if is it the same type of algorithm but I need to calculate hash for whole path for example:
attribdb/renddb.bin (hash: 3C12BC16)
attribdb/renddb.opt	(hash: 3C12F450)
attribdb/renddb.vlt	(hash:3C131193)
rendering/board/board_shadow_0.rx2 (hash: 81EA84CF)
rendering/board/board_shadow_1.rx2 (hash: 81FC9D50)

Here is link for EA's gpl source for Skate 3 which contains this type of .big archives. The hash code can be possibly found there, but I don't know how to use it. [https://gpl.ea.com/skate3.html](https://gpl.ea.com/skate3.html)

I'm grateful if someone can help me to solve this.
