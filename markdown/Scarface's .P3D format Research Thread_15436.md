## Post #1
- Username: Wakka387
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 02, 2015 2:06 pm
- Post datetime: 2016-11-01T14:29:11+00:00
- Post Title: Scarface's .P3D format Research Thread

While I know that .P3D files are containers for Texture/Model/ETC and have been used in games such as Scarface, Hulk Ultimate Destruction, and Prototype. 

I was hoping that this thread could serve as a means to co-ordinate and properly research into the format.

here are an assortment of random P3D's straight from the PS2 version for reference. 

[Albatross.P3D](https://dl.dropboxusercontent.com/u/18575411/Random/Scarface/albatross.p3d)
[MCP_Assassin.P3D](https://dl.dropboxusercontent.com/u/18575411/Random/Scarface/MCP_Assassin.p3d)
[Shark.P3D](https://dl.dropboxusercontent.com/u/18575411/Random/Scarface/shark.p3d)
[Shark_collision.P3D](https://dl.dropboxusercontent.com/u/18575411/Random/Scarface/shark_collision.p3d)
[Skybox_miami_01.P3D](https://dl.dropboxusercontent.com/u/18575411/Random/Scarface/skybox_miami_01.p3d)
[Zone_miami.P3D](https://dl.dropboxusercontent.com/u/18575411/Random/Scarface/zone_miami.p3d)
## Post #2
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2016-11-05T03:47:01+00:00
- Post Title: Scarface's .P3D format Research Thread

Format looks to be a fairly simple container format, however there's some unknown data that controls how the data is stored.

Here's a pseudo-C struct (meaning it's just for research) that describes a P3D file. This only barely scratches the surface, and much more research will be required if any tools are to be made.

```
    /* 
        NOTE:
        
        All offsets/sizes are relative to the beginning of
        their respective structure unless otherwise specified.
   */
    
    const int magic = 0xFF443350; // 'P3Dÿ'
    int version; // version 12?
    int fileSize; // size of file + header (0xC)
    
    /*
        read entries until EOF
        if fileSize == 0xC, file is "empty"
    */
    
    struct P3DEntry {
        byte unk_00; // type?
        byte unk_01; // flags? part of type?
        
        /* these bytes appear to control the size of strLen? */
        
        byte unk_02; // GUESS: is strLen a byte?
        byte unk_03; // GUESS: is strLen a int?
        
        /*
            following are relative to beginning of P3DEntry
            
            if childOffset == chunkSize, it contains no children.
        */
        
        int childOffset; // offset to next child
        int chunkSize; // size of chunk/container, next entry will start immediately afterwards
        
        /*
            unfortunately this is where things get confusing,
            the unknown bytes at the beginning control what
            data will be put here.
            
            sometimes there's extra fields with unknown purposes.
            do not assume the filename will follow directly after!
        */
        
        if (unk_02 == 1) {
            byte strLen;
        }
        else if (unk_03 == 1) {
            int strLen;
        }
        else {
            /* error? */
        }
        
        char name[strLen + 1]; // strLen does not include null-terminator
        
        /*
            data starts here? unknown if there's anything else besides the name
            do not assume the child will follow directly after, usually there's
            data that needs to be stored in a buffer.
        */
        
        /* @ childOffset */
        P3DEntry child; // assuming childOffset != chunkSize
    } entries[]; // til EOF
}
```

Update:
My original research was close, but I was wrong on "unk_02" and "unk_03".

I've attached some logs of the P3D files you've provided. I've only read the headers in hopes someone with a hex editor and some street smarts can figure out what's going on.

Update 2:
As I originally suspected (but didn't note in the spec), the data is stored as a simple linked-list.

Once again, I've attached some dumps to help decode what the beginning bytes may mean.
[P3D_dumps_20161104-0220.zip](https://xentaxbackup.github.io/file/11878_P3D_dumps_20161104-0220.zip)
## Post #3
- Username: Wakka387
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 02, 2015 2:06 pm
- Post datetime: 2017-01-11T01:26:00+00:00
- Post Title: Scarface's .P3D format Research Thread

good progress
## Post #4
- Username: KeysREC
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Mar 01, 2019 6:47 am
- Post datetime: 2019-02-28T23:15:21+00:00
- Post Title: Scarface's .P3D format Research Thread

I managed to open P3D with the help of the program: Lucas Pure3D Editor 4.1
pic:
[https://ibb.co/1KNBBnc](https://ibb.co/1KNBBnc)
