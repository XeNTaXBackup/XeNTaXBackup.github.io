## Post #1
- Username: mr rocket
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 15, 2015 4:15 am
- Post datetime: 2016-11-23T02:27:40+00:00
- Post Title: Godzilla Unleashed (Wii) *.BDG

Hello! I'm interested in extracting the .BDG file archives from Godzilla Unleashed for modding purposes.

Sample Files: [http://www.mediafire.com/file/18hfssa46 ... +Files.rar](http://www.mediafire.com/file/18hfssa46g5ae1b/GU+Files.rar)

I know that these archives contain .TPL files for textures but they appear headerless in the archives, so it's tough to identify these textures. Poking through the files, these archives also contain .PWK files for models and skeletons. Godzilla_Shapes.BDG should contain the mesh/textures (maybe animations?) while Godzilla.BDG contains the other files needed for the character. Tokyo.BDG should contain all of the files needed for the stage including meshes and textures. All of the .BDG files have a common offset, 0x64-0x66, that contains bytes that point to the offset of the end of the file list. I'm still trying to investigate these files but I'm pretty inexperienced with all of this... lol

So far the Godzilla modding community is fairly small and we're restricted to simple texture mods... I'm hoping to change that. 

Thanks!
