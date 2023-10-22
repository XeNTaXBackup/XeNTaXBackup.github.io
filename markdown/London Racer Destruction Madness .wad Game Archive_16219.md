## Post #1
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2017-04-29T19:11:47+00:00
- Post Title: London Racer: Destruction Madness *.wad Game Archive

Hi,im really want to extract files from this game.


Here is а game archive: 

[https://mega.nz/#!koU3lYbI!ORBEgvBCXZzP ... dZ2jH6O5ZE](https://mega.nz/#!koU3lYbI!ORBEgvBCXZzPnIxz4eePrZpOzbYFqBYSodZ2jH6O5ZE)

Screenshot of hex



I hope someone can help me.
## Post #2
- Username: devmode
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Jun 07, 2016 2:51 am
- Post datetime: 2017-04-30T19:26:27+00:00
- Post Title: London Racer: Destruction Madness *.wad Game Archive

Test unpack script for QuickBMS. Files extracting without original names, because i can't get any info from file, which can be pointing to filename strings. Strange format.

```
get dummy long
get namesSz long

goto namesSz 0 SEEK_CUR 

get unk1 long
get unk2 long
get offsetsCnt long

print "Reading offsets.."
for I = 1 to offsetsCnt
    get curOffset long
    putArray 0 I curOffset
next I
print "Sorting array. Please wait.."
sortArray 0

getArray fOffset 0 1

for j = 2 to offsetsCnt    
    getArray nextOffset 0 j
    xmath fSize "nextOffset - fOffset"
    log "" fOffset fSize
    math fOffset = nextOffset
next j

```


Format specification, how I presume:

```
int32 {4}  Unknown (dummy)
int32 {4}  File Names Block size (0x48EB0)

//File Names Block:
  // null delimited strings of filenames, folders, etc.

//Offsets Block:
  int32 {4} Unknown (0x00486D)
  int32 {4} Unknown (0x000912)
  int32 {4} Offsets\Files count (0x0000621C)
        //For each:
          uint32 {4} File Offset
#Size of Offsets block: 0x1887C

//Info Block
  # 16 bytes buffer for each file?
   bytes {4} Unknown #Offset to filename string? Almost all not exact point to start of string.
   bytes {4} Unknown
   bytes {4} Unknown
   bytes {4} Unknown (dummy)
#Size of Info Block 0x517F0

```


I don't have more ideas. Maybe somebody can complement.
## Post #3
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2017-05-01T00:03:20+00:00
- Post Title: London Racer: Destruction Madness *.wad Game Archive

> Reply from devmode
>
> Test unpack script for QuickBMS. Files extracting without original names, because i can't get any info from file, which can be pointing to filename strings. Strange format.
Code: Select allget unk long
get dummy long
get namesSz long

goto namesSz 0 SEEK_CUR 

get unk1 long
get unk2 long
get offsetsCnt long

print "Reading offsets.."
for I = 1 to offsetsCnt
    get curOffset long
    putArray 0 I curOffset
next I
print "Sorting array. Please wait.."
sortArray 0

getArray fOffset 0 1

for j = 2 to offsetsCnt    
    getArray nextOffset 0 j
    xmath fSize "nextOffset - fOffset"
    log "" fOffset fSize
    math fOffset = nextOffset
next j


Format specification, how I presume:
Code: Select allchar  {4}  Header (x34\x12\x00\x02)
int32 {4}  Unknown (dummy)
int32 {4}  File Names Block size (0x48EB0)

//File Names Block:
  // null delimited strings of filenames, folders, etc.

//Offsets Block:
  int32 {4} Unknown (0x00486D)
  int32 {4} Unknown (0x000912)
  int32 {4} Offsets\Files count (0x0000621C)
        //For each:
          uint32 {4} File Offset
#Size of Offsets block: 0x1887C

//Info Block
  # 16 bytes buffer for each file?
   bytes {4} Unknown #Offset to filename string? Almost all not exact point to start of string.
   bytes {4} Unknown
   bytes {4} Unknown
   bytes {4} Unknown (dummy)
#Size of Info Block 0x517F0


I don't have more ideas. Maybe somebody can complement.
Thanks man,its big progress. Ninja ripper doesnt work with that game,only extract some textures.
## Post #4
- Username: devmode
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Jun 07, 2016 2:51 am
- Post datetime: 2017-05-02T05:50:25+00:00
- Post Title: London Racer: Destruction Madness *.wad Game Archive

Aluigi on Zenhax.com already researched format: [http://zenhax.com/viewtopic.php?f=9&t=4157](http://zenhax.com/viewtopic.php?f=9&t=4157)
