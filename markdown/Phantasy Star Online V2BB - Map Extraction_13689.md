## Post #1
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2015-12-17T09:34:11+00:00
- Post Title: Phantasy Star Online V2/BB - Map Extraction

[](http://www.hostingpics.net/viewer.php?id=779932psobb2014081513412634psobb2014081513415240cc3b3pia.png)

Hello all !

Does anyone can help us to extract map content from both PSOV2 (PC) and PSOBB ?


[](http://www.hostingpics.net/viewer.php?id=194579psobbpano1.png)
## Post #2
- Username: PsowKion
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Aug 13, 2014 8:10 pm
- Post datetime: 2015-12-17T13:17:55+00:00
- Post Title: Phantasy Star Online V2/BB - Map Extraction

Hey guys Kion here. I've been working on extracting Pso maps specifically and trying to make all of my documentation and source along the way available as well. For the most part I can parse the binary files in Pso and extract them to json format. Such as this json representation of the psychowand from psobb: [link](https://github.com/seiche/Pso_File_Formats/blob/master/njtl/12/sample/pwand.json). I don't have a lot of experience with 3d, so right now the main thing I'm having trouble with is applying UV, 3d matrix math, vertex color and things like that. If anyone has any experience with the .nj filetype or similar Ninja0Lbrary models, then the stage files from PSO is just a file containing a list of inner-nj files. 

nj
Right now i'm working on nj files using the Katana SDK documentation and Kryslin's ExMldNet source to read nj files. Parsing the information isn't too hard, it's how to apply the rotation and translation matrixes from parent to child and applying the uv is what i'm having trouble with now. I'm hoping that a decent understanding of nj will help me approach the other file formats.

n.rel
In Pso Version 2 to for the PC (and PSO for the dreamcast as well, i think) use a format called n.rel for stage model files. The pointer to the header of the file is at EOF - 16. The header is four dwords long: 

```
    num_sections : dword,
    iff_str : dword,
    section_addr : dword,
    texture_addr : dword
  };
```

First it has the number of sections. Next it has some kind of IFF string which seems to be "  HD" in most cases. The section address is the header to the start of the section list and the texture address a pointer to the list of texture names for the model. The list of texture names follows the exact same format at the NJTL structure.

As for the section list, each entry seems to have the structure of:

```
   id : dword,
   pos : {
     dx : single,
     dy : single,
     dz : single
   },
   rot : {
     x : int,
     y : int,
     z : int,
   },
   radius : single(),
   //pointers
   model_addr_a : dword,
   unknown : dword,
   model_addr_b : dword,
   //number of
   num_model_a : dword,
   num_unknown : dword,
   num_model_b : dword,
   end : dword
}
...]
```


This is not an exact science, but the best guess i have based on the information. The first number seems to be a sequential number for the section number. Followed by the translation for each section. The rotation only seems to be across the y-axis for any given section. Following that there are two groups of model pointers, a and b. I'll get to those in a second. As for the unknown entry i'm not entirely sure since it seems to point to a list of 0x1000 values. As for the end value, i'm not entirely sure if it's a 

Model list A and model list B are both a list of pointers to .nj models inside the n.rel file. The first entry is a dword to the start of the nj model. Following that, the model A list struct seems to have a length of 0x2c bytes which is most often filled with zero's. The model B list has a struct length of 0x38 bytes following the first struct. I'm not sure what the difference is, but my best guess is that the model A list is static content while the model B list might have extra pointers to animation key frames.

Basically each section seems to be a scene inside the map. Such as a shop, a room, or a segment of a stage which is first rendered at the origin. It is then rotated around the y-axis in the left or right direction and then translated to where it needs to be relative to the rest of the stage. I wrote a small script to export each section of an n.rel map to it's own model which can be viewed in noesis, but I'd like to be able to export the whole stage file directly if possible.

xj
The xj file format seems to be a derivative of the nj file format or at least similar. Rather than use ninja-chunks it uses polygons which seem to be a pointer to a list of shorts describing the indices. I've done what I can to document the xj file format here: [link](https://github.com/seiche/Ninja-Lib/blob/master/documentation/XJ_Format.md). For the most part I can read and render the models, but I'm still missing out on some information which I'm hoping to fill in with a better understanding on nj.

n.rel (again)
PSOBB uses n.rel models, but with internal xj models as opposed to inner-nj models. Some of the struct sizes are different. I ported Schthack's model viewer to nodejs, then I went back to try and parse xj models, then I went back to maps again. The result of what I was able to analyze is in this folder: [here](https://github.com/seiche/Pso_File_Formats/tree/master/stage/07). For the most part I'm able to parse and render vertices, still missing some texture information and y-translation, but everything else seems to more or less work okay.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-26T14:53:20+00:00
- Post Title: Phantasy Star Online V2/BB - Map Extraction

> Reply from PsowKion
>
> The result of what I was able to analyze is in this folder: here.Looks great in Noesis with textures! (Though the meshes are not that detailed.)

Finally I managed to get that nasty beast compiled using my old Delphi2005 PE:



mapviewer-old.jpg (129.48 KiB) Viewed 254 times


Is there any newer source version of the mapviewer?
## Post #4
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2015-12-26T18:58:42+00:00
- Post Title: Phantasy Star Online V2/BB - Map Extraction

> Reply from shakotay2
>
> PsowKion wrote:The result of what I was able to analyze is in this folder: here.Looks great in Noesis with textures! (Though the meshes are not that detailed.)

Finally I managed to get that nasty beast compiled using my old Delphi2005 PE:

Nice !!


> Reply from shakotay2
>
> 
Is there any newer source version of the mapviewer?

I don't think, but I will let PsowKion answer this, he know better than me about this subject.
## Post #5
- Username: PsowKion
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Aug 13, 2014 8:10 pm
- Post datetime: 2015-12-27T08:37:31+00:00
- Post Title: Phantasy Star Online V2/BB - Map Extraction

As far as I can tell Schthack's map viewer source is incomplete. For the most part it's able to display maps and get the textures, but it's missing some details like rotation. If you look at the dates of the .pas files in the archive it looks like the map viewer was made in 2008. I think he then went back to the drawing board and fixed his mistakes with the model viewer which he released in 2009, which seems to display everything, but he never released the source code for that.

If you want a slimmed down port, I was able to port Schthack's map viewer to Nodejs and modified it to export .obj files. The source is over  [on github](https://github.com/seiche/Pso_File_Formats/blob/master/mapview/edit08.js). After that I wasn't sure how to follow up, so I decided to scale down and focus on .xj model types, which the source for is in the [same repository](https://github.com/seiche/Pso_File_Formats/tree/master/njtl/12).

The problem that I faced for a while was parsing the information wasn't too hard, but I don't have a lot of experience with 3d, so exporting the models turned out harder than expected. I turned to Kryslin's ExMLDNet and started working on .nj models to see if there were any hits that could help me fill in the holes I had for PSOBB maps and .xj models. The good news is while still pretty primitive, I was able to parse NJ files and export the model structure correctly. The source for that is over in [his repo](https://github.com/seiche/Pso_Toolset/blob/master/nj_export/alpha/njcm.jst).

Taking that a step further, I tried applying that information to PSO version 2 stages, and I finally got somewhere. My most recent attempt, which can be found [on github here](https://github.com/seiche/Pso_Toolset/tree/master/rel_export/alpha). Is finally able to export stage files from the game pretty accurately, admittedly while lacking textures at the moment. There's still more information I need to test, document, and fill in, I've just been catching up on some much needed sleep for the last couple of days.  

Preview:
[](http://i.imgur.com/KQpYG4t.png)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-27T10:02:04+00:00
- Post Title: Phantasy Star Online V2/BB - Map Extraction

Keep up your nice work!  
I myself don't know about .xj and .nj model formats. Is this really needed?
Why not use some more popular format? SMD, FBX, DAE whatever.

> Reply from PsowKion
>
> I turned to Kryslin's ExMLDNet and started working on .nj models to see if there were any hits that could help me fill in the holes I had for PSOBB maps and .xj models.The holes which are fixed by Noesis using face culling?

ExMLDNet uses Visual Basic? Really? Well, ok, just another transformation hurdle to transform it to javascript.  

Anyway, one of my next aims is to get familiar with Node.js.
This one seems to be a good start:
[http://www.tutorialspoint.com/nodejs/](http://www.tutorialspoint.com/nodejs/)
which was my lucky first random hit on inet search.

(Know a better one, maybe?)
## Post #7
- Username: PsowKion
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Aug 13, 2014 8:10 pm
- Post datetime: 2015-12-27T12:00:41+00:00
- Post Title: Phantasy Star Online V2/BB - Map Extraction

> Reply from shakotay2
>
> I myself don't know about .xj and .nj model formats. Is this really needed? Why not use some more popular format? SMD, FBX, DAE whatever.

For testing I've been exporting to .obj and would like to try writing a noesis plugin down the line once I get a better handle on the file formats and 3d in general. As for .nj, it's a "Ninja-Chunk Model" file format that Sega developed and used for Phantasy Star Online in the Dreamcast, and for a lot of other games. And .xj is a variation of that format which Sega used for Phantasy Star Online Blue Burst on the PC several years later. The stage files use these model formats internally to build scenes which make up parts of the stage.

> ExMLDNet uses Visual Basic? Really? Well, ok, just another transformation hurdle to transform it to javascript
I skipped over most of the details for textures, but I was able to port the important parts for how to parse the triangle strip, and the matrix functions needed to render the model correctly. Here's the code I ported for how to parse .nj models: [njcm.js](https://github.com/seiche/Pso_Toolset/blob/master/nj_export/alpha/njcm.js), and here's the code I ported for the matrix functions: [MatrixUtil.js](https://github.com/seiche/Pso_Toolset/blob/master/nj_export/alpha/MatrixUtil.js).

> The holes which are fixed by Noesis using face culling?
In this case I meant it figuratively. I can pretty much parse out all of the vertexes, normals, and triangle strips from the file format. Often they are intended to be double sided and fixed with culling. The "holes" that I meant were lapses in understanding like flags, or vertex alpha and other parts of the file which I'm able to read, don't completely understand what they do from the file definition. Mainly small things for flags on when to flip the UV or things like that.

> Anyway, one of my next aims is to get familiar with Node.js.
To be honest I just starting using Nodejs on a whim one day for this kind of thing and it ended out working pretty well. If you're looking at Nodejs tutorials, I think a lot of them are going to be server oriented. Here's a quick video I made for the how/why I use Nodejs: [Youtube Link](https://youtu.be/B4jZZeQxZtc). Personally I'm just using it for file I/O stuff in this case, so there's nothing too special about it beyond personal preference.
