## Post #1
- Username: Motormouth1212
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 21, 2021 7:40 pm
- Post datetime: 2022-05-13T10:10:41+00:00
- Post Title: Gotham City Impostors .mdl files

Hello, I'm wanting to get the .mdl model files from this game into Blender
To begin with, this game's files were all in .Arch01 files, and I was able to find an extractor to extract them, which gave me the .mdl files
Unfortunately it seems like this is quite a common filetype and doesn't seem to have a 'universal' structure.
I've tried a few of the most common ones, like for Source .mdl files, but they give me errors with these ones
Can anyone take a look and see how to get these into a format or a tool where I could get them into Blender please?
Here are some example files:
[https://www.mediafire.com/file/nb0j5qnp ... l.rar/file](https://www.mediafire.com/file/nb0j5qnpsud81o6/tutorial.rar/file)
These came from a folder called tutorial in the char section, and judging by the filenames they should be the characters from the tutorial cutscene:
[https://www.youtube.com/watch?v=ByHdojeK1BE](https://www.youtube.com/watch?v=ByHdojeK1BE)
So I imagine if someone is able to get them working, they should end up looking like those guys.
## Post #2
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-05-13T17:55:03+00:00
- Post Title: Gotham City Impostors .mdl files

> Reply from Motormouth1212 ↑Fri May 13, 2022 6:10 pm at Fri May 13, 2022 6:10 pm
>
> 
.mdl model
look at *.mesh
one submesh using MeshFinder (Android) or Hex2Obj



melvin.mesh.png (19.79 KiB) Viewed 83 times
## Post #3
- Username: Motormouth1212
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 21, 2021 7:40 pm
- Post datetime: 2022-05-14T02:00:04+00:00
- Post Title: Gotham City Impostors .mdl files

most objects in the game files don't have related .mesh files, it seems that the example models i provided have them for some reason but almost everything else doesnt, i.e. the player models, the weapon models, animations etc.
so in order for me to look at most of the game's content i'd still need a way to do something with the .mdl files, it seems
as an example, here is the 'average' bodytype models:
[https://www.mediafire.com/file/2szunrdm ... e.rar/file](https://www.mediafire.com/file/2szunrdmijgnk3c/average.rar/file)
they only contain .mdl and .tex files, no .mesh ones unfortunately
## Post #4
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-05-14T12:42:53+00:00
- Post Title: Gotham City Impostors .mdl files

> Reply from Motormouth1212 ↑Sat May 14, 2022 10:00 am at Sat May 14, 2022 10:00 am
>
> 
they only contain .mdl and .tex files
*.tex this DDS (remove first 8 bytes and rename extension on .dss)
*mdl - does not contain a mesh. at the end they all link to a *.mesh file. I don't know why you don't have them. 



ninja.png (55.28 KiB) Viewed 57 times
## Post #5
- Username: Motormouth1212
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 21, 2021 7:40 pm
- Post datetime: 2022-05-15T09:10:20+00:00
- Post Title: Gotham City Impostors .mdl files

yes, it's very weird. i've tried extracting the game content again just to make sure, but nothing turns up as .mesh files that fit the names of the .mdl ones. i'm not sure why it is, but if it's the case that the .mdl files don't contain the objects, then there's nothing much more I can do. thanks for the answers anyway
