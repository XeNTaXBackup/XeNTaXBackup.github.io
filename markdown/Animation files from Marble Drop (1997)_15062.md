## Post #1
- Username: milek7
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 18, 2016 3:58 am
- Post datetime: 2016-09-17T21:22:59+00:00
- Post Title: Animation files from Marble Drop (1997)

I have problem with figuring out animation format in puzzle game Marble Drop by Maxis South.


 1.1.tar
sample animation file (group 194 in level01c.dat, lifter wheel) (10 KiB) Downloaded 20 times


Currently I know that:
1 byte - 00
2 bytes - width
2 bytes - height
9 bytes - possibly rest of header?
I suspect that indexed animation is compressed with primitive compression algorithm (75% entropy, I can find single pixels that appear in game, but not series of them).

Game can be downloaded from [https://archive.org/details/marble-drop](https://archive.org/details/marble-drop) or demo [https://archive.org/details/MDDEMO](https://archive.org/details/MDDEMO)
quickbms script for unpacking .DAT archives:

```
getdstring name 50
getdstring desc 100
print "App name: %name%\nFile description: %desc%"
get size long
get groups short
get unknown1 short
get unknown2 long
for g = 0 < groups
    get entries byte
    for e = 0 < entries
        get type byte
        if type == 0
            set len 2
        else
            get len long
        endif

        set fn g
        string fn + "/"
        string fn + e
        string fn + "."
        string fn + type

        savepos offset
        log fn offset len
        goto len 0 SEEK_CUR
    next e
next g

```

Every resource with type 1 (saved with extension ".1" by script) is animation data, except first image which contain table background compressed with Greenleaf compression algorithm.
