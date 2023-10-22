## Post #1
- Username: lumis
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Dec 01, 2013 4:32 am
- Post datetime: 2014-07-03T11:32:36+00:00
- Post Title: Invincible/Bulpae online

Seems like the dds textures of this game are somehow "packed" even after using script from this topic [viewtopic.php?p=77616#p77616](http://forum.xentax.com/viewtopic.php?p=77616#p77616) , meshes, bones, anims are working fine after import, just textures won't.

Here's how it looks in hex


and here are the file samples
[http://go4up.com/dl/1XKnLFlvIt0](http://go4up.com/dl/1XKnLFlvIt0)

Any chance that someone could make a quickbms script to "unpack" these textures? thanks in advance.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2014-07-05T17:24:22+00:00
- Post Title: Invincible/Bulpae online

that's the script to decode the DDS header:

```
encryption xor KEY
log MEMORY_FILE 0 0x3f
encryption "" ""
append
get SIZE asize
math SIZE -= 0x3f
log MEMORY_FILE 0x3f SIZE
append
get SIZE asize MEMORY_FILE
get NAME filename
log NAME 0 SIZE MEMORY_FILE
```

note to people who write script with quickbms: if you have a variable with a fixed content that includes a '[' or ']' character, you need to specify it as "binary" otherwise quickbms will interpret it as a multi dimensional array (like "variable")
