## Post #1
- Username: lllsondowlll
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 22, 2017 7:40 am
- Post datetime: 2017-10-21T23:42:34+00:00
- Post Title: Lub decompilation

About 10 years ago, a friend and I discovered how to decompile the attached lub files. Since then I had a hard drive crash and lost my backups in the move on how to perform this. I've been trying based on memory to hex edit the lub files into a format luadec could read but I keep getting stuck on how we were generating the stripped table. 

From what I can remember, we were converting this luac 5.0 header to a luac 5.1 that luacdec 51 could read by changing the header, and cutting some of the data (namely the size code) near " C63E" (which can be found in every lub) and pasting it under the 51 header. There were some other steps needed such as generating a checksum which my memory is hazy on, and the data at the footer of the luac51 file which I simply cannot find out how to generate. 

Luckily, I am in possession of SOME of the unpacked lubs which I've been trying to use as a comparison. I simply just need to modify this file back to a format where a decompiler can read. This is why I am reaching out as this has been taking up a LOT of my time and figured someone here could point me in the right direction. I've attached two sample files with four formats: Lub, Lua, Luac50, and Luac51. 

Please, if anyone could shed some light on to this so I can get decompilers to read the original, I would be extremely grateful
[LUB.zip](https://xentaxbackup.github.io/file/13481_LUB.zip)
## Post #2
- Username: lllsondowlll
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 22, 2017 7:40 am
- Post datetime: 2017-10-22T05:33:54+00:00
- Post Title: Lub decompilation

Nevermind, I got it figured out
