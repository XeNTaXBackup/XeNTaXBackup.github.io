## Post #1
- Username: fudgonaut
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jun 05, 2022 7:01 pm
- Post datetime: 2022-10-11T15:37:36+00:00
- Post Title: Alien Vs Predator (2010) texture extraction

I tried using Terry Butler's Asura Engine Extractor to unpack AvP 2010 game textures.

The results are .tga files that are unreadable by Photoshop. PS displays a file-format module error. I tried a couple image converters which were also unable to read the .tga files

I tried this extractor here 

> Reply from delutto ↑Wed May 02, 2012 10:00 am at Wed May 02, 2012 10:00 am
>
> 
Unpack and Repacker:
http://www.mediafire.com/?2d5fkbaq7ax4vc6

The extractor's log said

```
Done   C:\Games\Aliens vs. Predator\Envs\Colony\M01_Colony.pc
File size 442251795 bytes
Decompressing Asura file.....
Done   
Exploring files...
Done      
```


but didn't actually output or list any files.

Has anyone run into these issues, or know of another program (Gimp, etc) that can read this type of .tga?

Or an alternate method of extracting textures from Asura engine .pc files?
## Post #2
- Username: Kelthic
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 27, 2023 6:32 pm
- Post datetime: 2023-07-27T12:10:29+00:00
- Post Title: Alien Vs Predator (2010) texture extraction

Is that not .tga file. Rename filename.tga to filename.dds and you got working file.
I dont know why Extractor do that, but his do.
