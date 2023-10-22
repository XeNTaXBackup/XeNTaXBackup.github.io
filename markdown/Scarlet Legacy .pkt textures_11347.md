## Post #1
- Username: lumis
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Dec 01, 2013 4:32 am
- Post datetime: 2014-03-22T17:22:36+00:00
- Post Title: Scarlet Legacy .pkt textures

previous topic about this game
[viewtopic.php?f=21&t=7170](http://forum.xentax.com/viewtopic.php?f=21&t=7170)

Can anyone make a bms script or any unpack tool for .pkt files from this game? these are encoded textures probably cuz most of them models are non textured in noesis and i can't find any textures in the client.

samples
[https://www.dropbox.com/s/umg4qc6nw2wlp18/W07506.7z](https://www.dropbox.com/s/umg4qc6nw2wlp18/W07506.7z)

Thanks in advance.

Edit: Thanks to Luigi now we've got a script to decode .pkt but even after that textures are somehow coded oO

```
goto 0x40
get ZSIZE long
goto -4
get SIZE long
get NAME basename
string NAME += "."
clog NAME 0x44 ZSIZE SIZE
###
```


Any1 up to solve this?:d Noesis script is kinda useless without having textures 

Edit2: Shitty edited script to unpack .pkt by me, i don't know anything about quickbms, i just mixed 2 scripts and added extension, at least it works, if anyone wants to fix it, go ahead

```
string name += ".dds"
goto -4
get size long
goto 0x40
get zsize long
clog MEMORY_FILE 0x44 zsize size
get size asize MEMORY_FILE
math size - 4
log name 4 size MEMORY_FILE

```
## Post #2
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-03-23T08:47:24+00:00
- Post Title: Scarlet Legacy .pkt textures

pkt is just zlibd blocks

then once decompresed

its a werid DDS header thing idk why they did this but yeah simple shiz
## Post #3
- Username: lumis
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Dec 01, 2013 4:32 am
- Post datetime: 2014-03-24T15:12:55+00:00
- Post Title: Scarlet Legacy .pkt textures

Noesis script doesnt seem to load textures on models properly so it's kinda pointless to mess around with this game files, just an info if any1 cares.
