## Post #1
- Username: survivalizeed
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jul 18, 2023 4:29 am
- Post datetime: 2023-08-17T23:22:29+00:00
- Post Title: Shadow of War .anix files

Since im currently the only active person modding the game and i already converted zaramots 3dsmax script to C++ and made it .obj compatible I now really want to do/try the file analysis myself with the .anix files the game uses. 
So far I found out a few things that i want to share here and maybe there is someone able to help or extend this here.

Offset 0xC-4bytes: file size
Offset 0x34-4bytes: bones count
Offset 0x38-12bytes: idk what that is but it seems like it some sort of identifier if the object is two legged.

Maybe someone here is able to give some valuable advice on what is going on in the file...

Here is the link [https://drive.google.com/file/d/1vYMto- ... sp=sharing](https://drive.google.com/file/d/1vYMto-OYb3dFsUH3j05RtaIpJVvFsYpE/view?usp=sharing)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-08-18T12:29:05+00:00
- Post Title: Shadow of War .anix files

There's a floats block with 82 entries, but they don't show up as  a skeleton:
.



player_body-anix.png (8.68 KiB) Viewed 94 times
## Post #3
- Username: survivalizeed
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jul 18, 2023 4:29 am
- Post datetime: 2023-08-19T16:26:34+00:00
- Post Title: Shadow of War .anix files

Hmm yes I don't think they would need to show up as a skeleton since it's an animation file not a bones file.
What I surely know is:
.mesh: The actual vertices, faces, boneweight...
.skel: The bones, parent-child relation, position of the bones...
.anix: The animation which moves the bones from the .skel file which then influences the vertices in the .mesh file.

Could you tell me which offset the float block has?
## Post #4
- Username: survivalizeed
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jul 18, 2023 4:29 am
- Post datetime: 2023-08-19T16:32:43+00:00
- Post Title: Shadow of War .anix files

+ afaik the game also tends to sometimes use half floats e.g .mesh files.
## Post #5
- Username: survivalizeed
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jul 18, 2023 4:29 am
- Post datetime: 2023-08-22T12:35:14+00:00
- Post Title: Shadow of War .anix files

Okay i did some RE and want to share my current progress to encourage people here to help me out with a good starting point + maybe in the future someone finds this resource useful 

1. The entire file is 4 bytes layouted (LE). There is no such thing as single byte flags etc. 
2. The Header starts at 0x0 and is exacly 48 bytes long

Header: 
-> (4 bytes) magic word p1
-> (4 bytes) magic word p2
-> (4 bytes) unknown static 
-> (4 bytes) file size
-> (4 bytes) a counter in a for loop. I don't exactly know what this is for
-> (4 bytes) unknown static
-> (4 bytes) unknown
-> (4 bytes) first section size (I think that those are the actual encoded keyframes)
-> (4 bytes) unknown
-> (4 bytes) second section size (idk what this is for)
-> (4 bytes) unknown static
-> (4 bytes) unknown static

This is the entire header. Now to the loading code I got so far (in c++):

```
    fseek(f, 0x10, SEEK_SET);
    auto count = readlong(f);
    fseek(f, 0x8, SEEK_CUR);
    auto sec1Size = readlong(f);
    readlong(f);
    auto sec2Size = readlong(f);
    fseek(f, 0x30, SEEK_SET); //end of header
    int inc = 0;
    for (int i = 0; i < count; i += inc) {
        auto b1 = readlong(f);
        auto bonescount = readlong(f);
        inc = bonescount;
        for (int j = 0; j < bonescount; inc = bonescount) {
            auto b3 = readlong(f);
            j++;
            values.push_back({ b3, b1 });
        }
    }

```

Current code is for the bones only i guess. 
The real data is located at the file ptr after executing the current code. This is where the first section starts with size of 
```
sec1Size
```


The real data is also stored in 4 byte unsigned ints but they get shifted to floats in a very complex way later in the routine.
