## Post #1
- Username: HeadsetGuy
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Feb 16, 2017 10:51 pm
- Post datetime: 2018-03-24T16:07:21+00:00
- Post Title: Data Design Interactive .WAD Files

Hey guys. I'm very frustrated in my attempts to extract files from Data Design Interactive *.wad files. On the wiki, this would be [London Taxi Rushour](http://wiki.xentax.com/index.php?title=London Taxi Rushour). There seems to be some stuff that's not listed in the article, but which should be. Also, Game Extractor technically "supports" the files, but always extracts corrupted data. The only other program I've found that can extract data from these files was created specifically for one game, LEGO Rock Raiders.
But to my point: I've got another .wad file that I want to get the files from, with proper names and everything. This one is from Tonka Space Station, and is called SpaceStation.wad. As always, feel free to follow along at home. Link: [https://www.dropbox.com/s/b1tlm033ud3id ... n.wad?dl=0](https://www.dropbox.com/s/b1tlm033ud3id57/SpaceStation.wad?dl=0)

```

char {4}     - Header (WADH)
uint32 {4}   - First File Offset
uint32 {4}   - Number Of Files
uint32 {4}   - Filename Directory Length

// UNKNOWN

uint32 {4}   - unknown (all 255's; could also be a signed int, value of -1)
byte {16}    - padding? (all 0's)
uint32 {4}   - unknown (in this case, value is 2538 in decimal)
uint32 {4}   - unknown (all 255's; could also be a signed int, value of -1)
byte {8}      - padding? (all 0's)

// DIRECTORY

   // for each file

   uint32 {4}   - Filename Offset (relative to the start of the filename directory)
   uint32 {4}   - File Offset (relative to the first file offset)
   uint32 {4}   - File Length
   uint32 {4}   - padding? (all 0's)
   uint32 {4}   - Unknown Boolean (0/1)
   uint32 {4}   - Number Of Files In Directory? (all 255's for files)
   uint32 {4}   - Unknown

```


After that, everything else seems to be correct. Sorry if this seems redundant or anything, and also sorry I couldn't figure out what the unknowns were. If anyone knows anything more, please, please, let me know.

-Johnny
