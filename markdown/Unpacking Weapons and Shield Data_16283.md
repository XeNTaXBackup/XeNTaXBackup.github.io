## Post #1
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2017-05-15T10:55:59+00:00
- Post Title: Unpacking Weapons and Shield Data

Hello,

It's been more than 6 months since I last asked about unpacking weapons but I still have the exact same problem. I still wasn't able to unpack the files because my technique always included looking for the face indices and these files doesn't have any, it seems like everything is a float.

I have extracted a segment of the files which I expect to contain a dagger that looks like this:


I have also written an analyzer that perfectly maps all data in the file to a structure, I just don't have any idea what the structure means.

This is a portion of the analyzer for a weapon. This includes comments on the functions used to read the data when I put the game under a debugger:

```
        # sub_65CC40((void *)(v16 - 4), 1u, 4u, v5);
        # sub_65CC40((void *)v16, 1u, 4u, v5);
        # sub_65CC40((void *)(v16 + 4), 1u, 4u, v5);
        # sub_65CC40((void *)(v16 + 8), 1u, 4u, v5);
        # sub_65CC40((void *)(v16 + 12), 1u, 4u, v5);
        # sub_65CC40((void *)(v16 + 16), 1u, 4u, v5);
        # sub_65CC40((void *)(v16 + 20), 1u, 4u, v5);
        # sub_65CC40((void *)(v16 + 24), 1u, 4u, v5);
        # sub_65CC40((void *)(v16 + 28), 1u, 4u, v5);
        # sub_65CC40((void *)(v16 + 32), 1u, 4u, v5);
        # sub_65CC40((void *)(v16 + 36), 1u, 4u, v5);
        # sub_65CC40((void *)(v16 + 40), 1u, 4u, v5);
        # sub_65CC40((void *)(v16 + 44), 1u, 4u, v5);
        # sub_65CC40((void *)(v16 + 48), 1u, 4u, v5);
        # sub_65CC40((void *)(v16 + 52), 1u, 4u, v5);
        unk0 = unpack("<fffffffffffffff", bin.read(60))

        for n in range(head[0]): # head[0] is 1
            # sub_65CC40((void *)(v37 + *(_DWORD *)(v16 + 56)), 1u, 4u, v5);
            # sub_65CC40((void *)(v18 + 4), 1u, 0x40u, v5);
            # sub_65CC40((void *)(v18 + 76), 4u, 2u, v5);
            unk1 = unpack("<i", bin.read(4))
            unk2 = unpack("<ffffffffffffffff", bin.read(64))
            textureIds = unpack("<hhhh", bin.read(8))

            v19 = head[1] # head[1] is 194
            v20 = 3 * v19
            if (3 * v19) > 0:
                # sub_65CC40(*(void **)(v18 + 88), 3 * v19, 4u, v5);
                # sub_65CC40(*(void **)(v18 + 92), v20, 4u, v5);
                # sub_65CC40(*(void **)(v18 + 96), v20, 4u, v5);
                # sub_65CC40(*(void **)(v18 + 100), v20, 4u, v5);
                # sub_65CC40(*(void **)(v18 + 104), v20, 4u, v5);
                # sub_65CC40(*(void **)(v18 + 108), v20, 4u, v5);
                bin.read(3*v19*4)
                bin.read(v20*4)
                bin.read(v20*4)
                bin.read(v20*4)
                bin.read(v20*4)
                bin.read(v20*4)

            v21 = head[2] # head[2] is 194
            v22 = 3 * v21
            if (3 * v21) > 0:
                # sub_65CC40(*(void **)(v18 + 112), 3 * v21, 4u, v5);
                # sub_65CC40(*(void **)(v18 + 116), v22, 4u, v5);
                unk4r = "f"*(3*v21)
                unk4 = unpack("<%s" % (unk4r), bin.read(3*v21*4))
                unk5r = "f"*(v22)
                unk5 = unpack("<%s" % (unk5r), bin.read(v22*4))

```


The code above reads one weapon. But it's weird as there are no face indices and there seems to be too much floats for simple 3D weapons.



Any idea on what this could mean? Why aren't there any face indices?

Here is the binary file for the weapon in question: DOWNLOAD.

The binary doesn't include the header data which is: (1, 194, 194)
I have no idea what 194 could mean, it could be number of faces or number of vertices... 
1 can be ignored as its the same for all headers.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-05-15T12:54:56+00:00
- Post Title: Unpacking Weapons and Shield Data

funny format. I wouldn't care for the face indices for now, as a first step I'd look for a decent point cloud.

funny enough: I changed the FVFsize in steps of 4 from 12 up to 52 (count decreased to 262 then)
and there's that square mesh part remaining in the midst:



262_dagger.jpg (62.01 KiB) Viewed 138 times


getting the proper FVF size would be important, I'd guess for 16, but not sure.

Maybe a less complex object like a book, a box or a cup could give more insights?

Approaching the above mentioned object (as a point cloud) I've tried this H2O file :
0x0 500
Vb1
12 99
0x2FC8 150
020000
0x0 255
## Post #3
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2017-05-15T13:32:23+00:00
- Post Title: Unpacking Weapons and Shield Data

Yah, it's a bit weird. Considering the armors were in a very standard structure. While the weapons aren't.

So, the items available here are weapons and shields. Would a shield be considered a simple object? Unfortunately there isn't any item that is a book or resembles a book.

Let me do a quick unpack of items I think looks simple and I'll post some here  Thank you as always!!!
## Post #4
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2017-05-15T13:49:03+00:00
- Post Title: Unpacking Weapons and Shield Data

Hi ... [Here](http://www.mediafire.com/file/kdnr3s1bm54w8p3/xentax_help_weapons%26shields.zip) are the related files.

I think the following items are simple:

======================================

objects/0.bin (broad sword)



======================================

objects/1.bin (long sword)


======================================

I'm trying to do some experiment based on the data you shared... Hopefully can find something...
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-05-15T17:23:25+00:00
- Post Title: Unpacking Weapons and Shield Data

no luck so far. While the outer vertices look symmetrical the inner ones are kinda mess:



0-bin.jpg (74.86 KiB) Viewed 128 times



btw: number of .bins and number of textures doesn't match, can we expect 0.png to belong to 0.bin?
## Post #6
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2017-05-15T18:17:15+00:00
- Post Title: Unpacking Weapons and Shield Data

This one is a bit hard, I've been scratching my head on this format for half a year already. I even considered that this might be encrypted which I highly doubt because of all the float values.

As for texture. Each .bin actually contains which texture it uses. At offset 0x80 its a short but oddly repeated 4 times. Like for texture 5.png it shows, "05 00 05 00 05 00 05 00".

Another thing worth noting is that the armors had 3 LOD steps so each armor actually stored 3 objects. Maybe each of this ".bin" is actually 3 objects... hmmmm
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-05-15T20:14:21+00:00
- Post Title: Unpacking Weapons and Shield Data

checking a simple object like 106.bin doesn't help:



106-bin.jpg (208.76 KiB) Viewed 120 times


(There's many equal values, which might be an issue worth being investigated.)
## Post #8
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2017-05-15T22:43:25+00:00
- Post Title: Unpacking Weapons and Shield Data

So I decided to look at the smallest size bin file. 201.bin is only 1288 bytes.

Texture:


Based on the texture it looks like its a shield, 1 of 4 possible shields. 

Item Icon:


Item Model:


Like how the texture index is weirdly repeated 4 times. I also noticed what you meant, some values are repeated 4 or 3 times.



The remaining bytes on the file right after the last offset (0x88) of the texture index is 0x480 or 1152. I thought of dividing this by 4 which gives me 288. Looking at the header data for 201 which is (1 12 12) gave me the idea to further divide 288 by 12, which gives me 24. 

I still have no idea what this means at this point but it seems to show a bit of a structure. But no luck:
## Post #9
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-05-16T02:47:12+00:00
- Post Title: Unpacking Weapons and Shield Data

i think more info about the game could shed light on some unknowns.
if the developer has other games that have already been researched with findings maybe you could apply some of those to this one.
from what i've read in your other posts, this is a 2001 Korean MMORPG named Khan? 
[viewtopic.php?p=121958#p121958](http://forum.xentax.com/viewtopic.php?p=121958#p121958)
or is this another game? i can find nothing about this title.
does this game go by any other names? i found a game called Kohan from 2001.
who was the developer?
do you have any web links to any kind of info about this game?

edit
[http://www.hardcoregaming101.net/korea/ ... irinae.htm](http://www.hardcoregaming101.net/korea/part1/company-mirinae.htm)
## Post #10
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2017-05-16T03:07:30+00:00
- Post Title: Unpacking Weapons and Shield Data

> Reply from AceWell
>
> i think more info about the game could shed light on some unknowns.
if the developer has other games that have already been researched with findings maybe you could apply some of those to this one.
from what i've read in your other posts, this is a 2001 Korean MMORPG named Khan? 
viewtopic.php?p=121958#p121958
or is this another game? i can find nothing about this title.
does this game go by any other names? i found a game called Kohan from 2001.
who was the developer?
do you have any web links to any kind of info about this game?

Yes, its exactly the same game I was talking about on that post.

The best info I can give is, [this code](https://pastebin.com/4n2vHn5y), it reads the item file that I'm trying to unpack on this topic. The code is generated by a debugger so it's a bit messy. And it's too much for me to reverse engineer.
## Post #11
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2017-05-16T18:44:13+00:00
- Post Title: Unpacking Weapons and Shield Data

I finally figured it out... The format is a bit tricky...

Idea on the format: Take for example a 3 vertex object and the data is 36 bytes. The vertices offset would be like:

```
v float2, float5, float8
v float3, float6, float9

```



Unfortunately there is 128 bytes I cannot guess the structure yet. So I can't create an importer back to the original format for now. Any idea on what the rest of the bytes could be? It's all floats. It's before the texture IDs.

BIG THANK YOU TO shakotay2! AS ALWAYS! 

EDIT: I just tried to 00 out all the 128 unknown bytes and checked the game and saw NOTHING IS WRONG. Weird, whatever they were they didn't seem to affect anything or I just didn't notice.

EDIT EDIT: I finally saw whats wrong when the 128 bytes are zeroed, the particle effects now spawn at origin. Instead of specific positions on the items.
