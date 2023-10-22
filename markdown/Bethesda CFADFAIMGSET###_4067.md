## Post #1
- Username: Zero Diamond
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Dec 27, 2009 7:10 am
- Post datetime: 2010-01-20T09:23:28+00:00
- Post Title: Bethesda CFA/DFA/IMG/SET/###

I actually already posted a thread about this, but that was before I really knew what the contents of these kinds of files were and thusly it wound up in the wrong forum and was also quite ignored.  However, things have changed and I know exactly what these filetypes are.  IMG is a straight up single image format, CFA and DFA are compressed sets that comprise animations, and SET files contain wall textures.  For some games, these are stored in a BSA game resource, while in the later ones there are several sets of BSA files containing different data types.  All of them utilize COL files for palettes.

I had initially thought that these resources were only the same for Elder Scrolls: Arena and Terminator: Rampage, but it turns out that Bethesda's two later Terminator FPS titles, Future Shock and SKYnet also both utilized some of these file extensions and, much to my surprise, they appear to be the same format as well, though ### files have replaced the SET files as a method of texture storage in those titles.  There's a number of them which have some distorted images displayed in them which may be DFA/CFA animation data.

[Game File Explorer](http://mirrored.xentax.com/gfe/index.html) can open BSA files and view IMG and ### files with their respective COL palettes, as well as being capable of extracting (but not converting) all the other files inside.  [WinArena](http://www.tesnexus.com/downloads/file.php?id=8516) can dump the image files of Elder Scrolls: Arena, but due to an inflexible design revolving around a faux 3D game world renderer as a part of the program, it can't open and dump individual files, nor even operate on anything other than Arena.  HOWEVER, the source code is included and is well commented.  The file [ParseBSA.cpp](http://www.zxdware.net/ParseBSA.txt) (which I link to as a .txt file for reference) has full information on all of these formats (except for ### which was not used in Arena) as well as a handful of others.

Useful information that I've extrapolated at a glance:
COL are the palette files used by the various image types.  They contain 256 entries in 3-byte triplets and apparently stores red in the low byte as opposed to blue.
CFA files are RLE compressed and muxed.  They are animations containing a variable number of multiple frames.
DFA files are only RLE compressed and instead of containing full frames for the whole animation often have only partial animations following the base frame.
IMG files come in three types: one without a header that the app interprets the height and width of, one that is uncompressed, raw image data (but with a header), and one that is compressed with an unknown algorithm (generally used for full screen graphics in Arena and likely not to be that important for other applications).
SET files are just 64x64 blocks of IMG data packed into a file.

I know nothing about ### except that it likely contains IMG format image data as well as occasionally either CFA or DFA animation information--this is only theoretical and stands to be tested.

I'm sure somebody with more knowledge of this stuff could get A LOT more information out of the code that I posted a bit above the list there.  Anyhow, I've got a ZIP file with an assortment of the data files from different games using the formats in order to make sure the compatibility is maximized.  Hopefully somebody will be able to whip up some extraction code using this information, because I really want to have a look at the Future Shock and SKYNet weapon graphics.  Each game has a set of graphics and a palette file included in a folder in the zip.

Download: [Bethesda File Samples](http://www.zxdware.net/BETHESDA_FILES.zip)

Unfortunately all the BSA files are fairly large, but luckily you can download the full version of [Elder Scrolls: Arena](http://www.elderscrolls.com/downloads/downloads_games.htm) free from Bethesda, which includes GLOBAL.BSA, should anyone be so inclined to try and write another extractor for that format.

Anyhow, thanks a lot to anyone who takes a look at this and I can't wait to see what comes of this!
