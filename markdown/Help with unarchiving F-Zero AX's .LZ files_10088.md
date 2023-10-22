## Post #1
- Username: StarkNebula
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jan 24, 2013 12:06 pm
- Post datetime: 2013-01-26T23:56:20+00:00
- Post Title: Help with unarchiving F-Zero AX's .LZ files

GameZelda made a great .ARC and .LZ unarchiver for the files found in F-Zero GX (called GXPAND). After exploring GX, it was only natural for me to go check out F-Zero AX (the Triforce arcade version of GX). GXPAND is able to unarchive AX's .ARC files, but returns an error for the .LZ files. When I try to unarchive it I get this:  

C:\Users\…\gxpand unpack input output
UnLZ output\st87.gma.lz
std.stream.ReadException@std\stream.d<46>: not enough data in stream
----------------
47EA54
47E8CB
----------------

C:\Users\…\gxpand>save
'save' is not recognized as an internal or external command, operable program or batch file.

C:\Users\…\gxpand>close
'close' is not recognized as an internal or external command, operable program or batch file.

While going through what I could of AX, I saw that there are 19 new stages within AX's 'stg' folder that were not present in GX's ROM. Stages numbered 77-110, missing a bunch in between. These could either be test stages or beta stages. It would be crazy if anyone could extract that content. 

I'm particularly interested in this because I want to see everything in AX and document my, and anybody else's, findings on TCRF.net. The only thing I could do so far was deduce from file names and view .ARC or uncompressed files. Still cool, but more than half of the files in AX's ROM are .LZ archives.
