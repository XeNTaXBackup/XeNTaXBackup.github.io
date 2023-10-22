## Post #1
- Username: Mike Oxmaul
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Dec 05, 2014 9:54 pm
- Post datetime: 2015-04-04T14:57:02+00:00
- Post Title: Need for Speed World Car Models (.BIN)

Hi all. I need help with the importing models from NFS World. I'd tried to open the geometry.bin or textures.bin file with all tools compatible with another NFS with this game engine, but I see only "APPCRASH" or "Error while opening" etc.
I compared the geometry file from NFS World and a from NFS Undercover, and found that their structure is very similar. Almost the same general structure, written in almost identical principle headers, same compression algorithms... But... ZModeler2 was crashed while I try to import the model. I'd tried the ZModeler 2.1.0, and the model was partly imported. Materials list, meshes list - these was imported. But each mesh have a polycount equals 0. Next. I'd tried to open the textures.bin file with latest version of NFS-TexEd (0.9.1). This tool have successfully readed a total number of textures and texture archive size, but after a few seconds the program provided a critical error and closes.
Some time later, I found a tools (and their source codes) that are designed to decompress the game archives. But this tools works incorrectly with this game.
Some information about compression algorithms, founded by me or a from the web:
All game archives contains the data blocks, which are compressed with algorithms HUFF or JDLZ. Each file (model, texture, or many other files) contains a lot of same blocks. I have the source code for tools named unhuff (simple decompressor for huff algorithm, written on assembler), unjdlz (simple decompressor for jdlz algorithm, written on c++), and jdlzpack (this tool will compress the files with jdlz algorithm, written on c++). The author of these tools - Arushan and EA Games (same codes taken from game exe), the man who wrote a lot of tools (NFS-TexEd, NFS *** ModTools etc.).
But, given that I'm not a programmer and don't know the programming language, I'm not able to compile these programs, I ask you professionals help. I don't found any tool who works fine with NFS World as this moment.

The source codes, some tools and some game files you can download here: [https://drive.google.com/folderview?id= ... sp=sharing](https://drive.google.com/folderview?id=0B41fB90jbip1fnB1bGlYdUJLM0pyRlE4QWZ3dTBWY0xjcEFHQkQ2U1BaWDdFSWdjbk9WYTA&usp=sharing)
Maybe anybody write a maxscript, script for quickbms or tool for extract models, textures, and any data from game archives.

P.S.: Sorry for mistakes in the text, my English aren't ideal, I'll still learning it.
## Post #2
- Username: JONATHANTKB
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 24, 2014 12:24 pm
- Post datetime: 2015-04-22T00:33:30+00:00
- Post Title: Need for Speed World Car Models (.BIN)

lol need use 3d ripper 

S.S.T™®
## Post #3
- Username: Mike Oxmaul
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Dec 05, 2014 9:54 pm
- Post datetime: 2015-04-25T18:05:21+00:00
- Post Title: Need for Speed World Car Models (.BIN)

3D ripper? Lol. After Ninja Ripper I can't successfully import the scene into 3dsmax. I don't know right values of UV.
## Post #4
- Username: JONATHANTKB
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 24, 2014 12:24 pm
- Post datetime: 2015-04-28T17:12:45+00:00
- Post Title: Need for Speed World Car Models (.BIN)

only now can rip in 3d ripper dx but need only 32bits system and stat 3d ripper in global monitoring
