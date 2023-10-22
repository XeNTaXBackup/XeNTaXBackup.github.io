## Post #1
- Username: tigrou
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Feb 22, 2017 6:35 pm
- Post datetime: 2020-11-07T15:08:02+00:00
- Post Title: Quarantine map format

I recently took a look at Quarantine map format.  Here is what I found so far : 
Each level has usually 3 files : MAP, BLK and BSP (eg: KCITY.MAP, KCITY.BLK and KCITY.BSP)

MAP : levels are made of big square blocks (eg: a crossroad, a T section, a building, ...). 
That file is simply a 2D array containing blocks indexes .

```
+02 map height (2 bytes)
+04 block indexes (2 bytes * map width * map height)
```


The block index seems to be made of two parts : first byte is a value between 0-127 that reference an entry in BLK file block table header.
Second byte value is either a flag or some sort of sub-index inside a given block entry. It's often 0.

If I dump all blocks indexes to a color for the first level, here is what I got : 


Here is a quick hack where I replaced all blocks by 0x3502 ("Weapon King" block) :


BLK : it probably means block.

```
+04 block table header with 128 entries, each entry is 8 bytes. it probably contains an offset to the block data.
+404 block data, format is unknown
```


Block data seems to be compressed. It's read once during load, and the way it is loaded in memory is slightly different than content of the BLK file itself. 

BSP : that file is created when level is loaded. If you delete it, the game will recreate it automatically.
What is weird is that this file seems to be never read by the game, even during gameplay. It's just written once during load.
I don't know what BSP stand for. It might be "binary space partition" or "block sprite".
