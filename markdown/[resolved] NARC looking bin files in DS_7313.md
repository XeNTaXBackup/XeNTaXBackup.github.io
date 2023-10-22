## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-09-07T18:43:40+00:00
- Post Title: [resolved] NARC looking bin files in DS

I have some .bin files from a DS game (code geass...something).

I went around looking for more information about DS files and got some tools to work with it

-dslazy, dumps nds rom
-ninunpack, command-line narc file unpacker
-DSDecmp, command-line decompresses ncgc files to ncgr
-glycerin map viewer, views images using ncer, ncgr, nclr files

But then there are two additional file types that I couldn't find any tools for:

1: ncbc files. Looks like a variation of ncgc.
2: NARC-looking bin files. Viewed it in hex, looks like a narc file (with the NARC idstring and chunk ID's afterwards) but then there's extra information.

Anyone know how to deal with these?

I'm interested in getting some sprites, but so far I haven't had any luck finding them so I thought maybe they'd be in these files.

Some people have [put together spritesheets](http://spritedatabase.net/game.php?game=10) from the game, and I'm assuming it was obtained through the data itself, though there was only a limited amount of sprites (one character) and nothing else so I decided to get them myself.
[dsFiles.7z](https://xentaxbackup.github.io/file/4695_dsFiles.7z)
## Post #2
- Username: admirzuza
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Dec 03, 2010 12:38 am
- Post datetime: 2011-09-07T21:24:49+00:00
- Post Title: [resolved] NARC looking bin files in DS

I have looked at files, and all I gotta say.....Man, if U wanna do NDS hacks all U need is Crystal Tile.....and no problems......so just get it, and U will be able to decompress (LZ77 compressed) and extract all Files.....hope this was helpful
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-09-07T21:30:53+00:00
- Post Title: [resolved] NARC looking bin files in DS

I found a copy of crystal tiles in the archive of tools I downloaded, but didn't really know how to use it.

Perhaps you can take the samples I put up and pick something out to confirm that crystal tiles is a good start? Then I'll start looking around for details on how to properly use it.

For one, as I'm unfamiliar with DS files, I wouldn't know what I'm looking at is actually supposed to be an image or not (and from using the glycerin viewer it looks like I need multiple files just to view an image), but it can sort of view the ncbc files so I can assume that is an image.

EDIT: upon closer inspection, it would seem that those bin and those ncbc files have one thing in common: They look very similar to narc and ncgc files, except they have extra bytes before the idstring and different data throughout.

Hopefully this is not a unique file type. Perhaps that is where the compression comes in and they use these extra bytes at the beginning to denote that the file is compressed.

EDIT2: came across this document: [http://www.romhacking.net/documents/469/](http://www.romhacking.net/documents/469/)
Hopefully I can convert the files into something the existing tools recognize.

EDIT3: If I'm reading the documentation correctly, the ncbc and ncgc are just compressed ncgr images using two different compressions. Guess I'll see if I can get crystal tile to just decompress it.

EDIT4: solution: dsdecmp can handle everything.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-07T23:21:22+00:00
- Post Title: [resolved] NARC looking bin files in DS

i got some of the files decompressed with the comtype lz77wii
the files look different from the wii games tho for instance FF FE is FE FF in the ds game.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-09-08T00:08:09+00:00
- Post Title: [resolved] NARC looking bin files in DS

I finally got to the sprite sheets, only to realize that although it is stored very similar, they use some sort of PAL file for the palette rather than an nclr file  

The three n* files are documented, but there doesn't seem to be anything about the PAL file.

This would probably be more appropriate in the graphics forum.
[mpc003.7z](https://xentaxbackup.github.io/file/4696_mpc003.7z)
