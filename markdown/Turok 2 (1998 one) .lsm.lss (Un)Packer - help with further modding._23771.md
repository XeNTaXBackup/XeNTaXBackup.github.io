## Post #1
- Username: kubpica
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 20, 2021 9:41 pm
- Post datetime: 2021-04-20T14:26:14+00:00
- Post Title: Turok 2 (1998 one) .lsm/.lss (Un)Packer - help with further modding.

Hey, I was analyzing Turok 2's (original one, not remaster) .lsm/.lss files (of the 1998 PC version) a bit and noticed that the file is broken into structures similar to folders and subfolders. I also receieved information from one of the remaster developers how these files are encrypted (actually the byte order is changed probably for better compression) which we called "interleaving".
So I created InterleavingPackerUnpacker available here: [https://github.com/kubpica/InterleavingPackerUnpacker](https://github.com/kubpica/InterleavingPackerUnpacker)

This program finds a hierarchy/structures in .lsm and .lss files and extracts them to files with unknown extension but I am not 100% sure if the decryption of every Turok2 file is done correctly. I don't know much about reverse engineering so we only managed to swap the textures and models among themselves, it can result in fun effects 

I also managed to change position, size, rotation and even models of some parts of levels eg. chairs on the Harbour5 level:



Structure of the Turok2 .lsm files:

```
sb1 -> actor attributes?
sb2 -> actor types?
sb3 -> textures?
sb4 -> particles!
sb5,sb6,sb7 -> levels! (sound shaders? event table?)
sb8 -> warp IDs? / spawn-points!
sb9,sb10 -> ? (empty in .lsm and .lss)
sb11 -> weapon effects (same in every .lsm, smaller in .lss)
sb12 -> ? (same in .lsm, 16bytes longer in .lss)
sb13 -> ? (same in .lsm, 24bytes longer in .lss)
sb14 -> ? (same in .lsm, 8bytes longer in .lss)
sb15 -> ? (same in .lsm, 8bytes longer in .lss)
sb16 -> gui textures! 
sb17 -> defines sth for gui textures (ids? offsets?)
sb18 -> ? (lector sounds/issues? because big in ctf and arena and in .lss, but small in rok?)
sb19 -> ?
sb20 -> ? (empty in .lsm and .lss)
 
rok->5->17 = graveryard
rok->5->17->6 = fog on the floor/ground of graveryard
rok->5->17->3 = positions of pickables and some walls

rok->5->0->3 = picables, gates and bridges, barrels (generally positions of models?)
rok->5->0->1 = ground hitboxes?

rok->5->9 = Harbour5 
rok->5->9->5->9->1 = small ladder
rok->5->9->5->14->1 = House with the rocket launcher (scorpion) on the roof
rok->5->9->5->15->3 = ? maybe this single box near plasma ?
rok->5->9->5->20->3 = ?
rok->5->9->5->21->3 = ?
rok->5->9->5->22->1 = area of second plasma in the small tunnel near boxes
rok->5->9->5->27->1 = left side of the fountain

rok->5->9->5->14->1 // House with the rocket launcher (scorpion) on the roof
	1 segment: the right-down chair (amount of segments and its length is in first 2 words = 8 bytes)
		1 word: ?? (1 word = 4 bytes)
		2,3,4 word: size (float)  
		5 word: x position (float)
		6 word: y position (float)
		7 word: z position (float)
		8 word: ?
		9 word: ?
		10 word: ?
		11 word: first 2 bytes determine displayed model (EA 00 B3 01 = closed book)
		12 word: ?
		13 word: y-axis rotation
	2 segment: right-top chair

```


I noticed that some files are additionally compressed with RNC2 (Rob Northen compression) - those files start with RNC 0x02 (52 4E 43 02). You can use decompressors like [https://github.com/lab313ru/rnc_propack_source](https://github.com/lab313ru/rnc_propack_source) or [https://github.com/temisu/ancient](https://github.com/temisu/ancient) BUT Turok's RNC uses little endian for header values (Uncompressed Size, Compressed Size, Uncompressed CRC, Compressed CRC) and the decompressors use big endian so you have to either swap the bytes of these values in order or edit the source code of these programs to treat these values as little endian.

For example I decompressed this file which I guess is a texture:

into this:

So if it is the bloodblobs texture my intuition says there should be some RGB encoded but I can't see it ;p Can you help?

btw. I also created mod for the multiplayer (original PC version - 1998), I managed to unlock FPS and add some cool features:
[https://www.turokforums.com/index.php?topic=526.0](https://www.turokforums.com/index.php?topic=526.0)

Why to mod the original when we got moddable remaster?
Gameplay of the remaster's multiplayer is very different than the original PC multiplayer, many oldshool T2 mp players were disappointed by the remaster and still play the old multiplayer version. E.g. in the remaster Plasma Rifle is no longer one-shot-killer, it's as if one made Counter-Strike remaster and removed AWP from the game, also some complain about netcode.
