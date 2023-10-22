## Post #1
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2019-03-01T21:41:36+00:00
- Post Title: How to generate tile faces based on vertices?

I have a terrain/map file that only contains vertices data, no faces. I guess the game generates the faces when loading the map.

Considering it is a map all vertices are in square tiles. For example:



As you can see a terrain is visible through all this vertex points. But how do I create the faces based on the vertices?

Here is my idea: (feel free to correct me)

```
    height = struct.unpack("<I", bin.read(4))[0]

    for x in range(width*height):
        texture_index = struct.unpack("<H", bin.read(2))[0]

        output = output + "g tile_%d\n" % (x) 
        output = output + "usemtl mat_%d\n" % (texture_index)
        
        for y1 in range(8):
            x1 = (x*9)+1
            x2 = (x*9)+y1+2
            x3 = (x*9)+y1+3
            
            if y1 == 7:
                x3 = (x*9)+0+2
            
            output = output + "f %d/%d/%d %d/%d/%d %d/%d/%d\n" % (x1,x1,x1,x2,x2,x2,x3,x3,x3)   

```
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-03-02T00:57:44+00:00
- Post Title: How to generate tile faces based on vertices?

> Reply from majidemo ↑Sat Mar 02, 2019 5:41 am at Sat Mar 02, 2019 5:41 am
>
> 
Here is my idea: (feel free to correct me)
Why not just run your code and see if it works? 

> Reply from majidemo ↑Sat Mar 02, 2019 5:41 am at Sat Mar 02, 2019 5:41 am
>
> 
Code: Select all        for y1 in range(8):
            x1 = (x*9)+1
            x2 = (x*9)+y1+2
            x3 = (x*9)+y1+3
            
            if y1 == 7:
                x3 = (x*9)+0+2
            
            output = output + "f %d/%d/%d %d/%d/%d %d/%d/%d\n" % (x1,x1,x1,x2,x2,x2,x3,x3,x3)
I'm sure it'd be much simpler and more appropriate to generate two triangles at a time. You can refer to the method in this post:
[viewtopic.php?p=141503#p141503](https://forum.xentax.com/viewtopic.php?p=141503#p141503)
You may break the quad to triangles if required.
## Post #3
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2019-03-02T04:12:37+00:00
- Post Title: How to generate tile faces based on vertices?

I just tried my code and it made Noesis freeze for about a minute but ultimately loaded a map with faces. Altough the freeze is annoying me. The game I’m working with only works with tris. No quads. I’ll check your link.
