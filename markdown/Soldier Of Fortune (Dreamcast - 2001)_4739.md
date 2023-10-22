## Post #1
- Username: TuxTheWise
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jun 26, 2010 8:27 am
- Post datetime: 2010-07-11T17:53:10+00:00
- Post Title: Soldier Of Fortune (Dreamcast - 2001)

I was taking a look again at Dreamcast version of Soldier of Fortune. Most game files (basically everything not read on-the-fly) are inside a huge file called FILES.PAK. I need to be able to unpack and pack it back, so I can work on this game. The most important part is unpacking it, because after understanding the format packing should be much easier.

This PAK is not a ZIP file (like in ID games), and also it's not the same format used in the PC version of Soldier Of Fortune. No general game formats extractor I tried (probably every one that you can think on) can work with this format. Also, XeNTaX forums and wiki don't have anything related to this format (as far as I searched for it), probably because it's been assumed that the formats of DC and PC version would be the same.

The good news is that there is a start point. First one: WinRAR can open the file, identify and extract some files but it says the header is corrupted. Analysing the PAK in a hex editor, you can't find a ZIP header, meaning that the WinRAR have recognized the structure of the PAK itself, not of a file inside of the PAK. The conclusion is that the format has something to do with ZIP format. Note that I'm assuming WinRAR identified it as a ZIP, I'm not sure of that and it needs further investigation. Additionally, WinRAR shows the files as compressed, so it means that the PAK uses compression. That's probably the reason of the big loading times of this game.

There is another thing that can be used to figure out this format. There are two "pirate" releases I know: Echelon (split 2 discs) and Isozone (single disc). Since every disc have a different PAK file, it means that you have a total of 4 valid PAK files that can be used for comparison. The most interesting is Isozone's, because it's slighty different, probably ignoring not used header fields. Additionally, WinRAR cannot open it at all.

The first 3mb of each pack file is uploaded together here:

```
http://www.sendspace.com/file/few8c0
```

Note that the WinRAR behaviour I mentioned can be seen even with the short versions of the files.

I need help unpacking/understanding this format, and this place seemed like the best one to ask for it. Thanks.
