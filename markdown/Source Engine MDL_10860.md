## Post #1
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2013-10-10T21:34:48+00:00
- Post Title: Source Engine MDL

I've been asked to post this here. In case anyone is interested. Also I guess I can provide flat compiles of quick and simple models I can potentially build myself
Static cube
Static cube with bone
multiple cube objects with multiple cube materials on a skeleton system

or something similar.

[QUOTE=Gmod4ever;42446004]Okay, so this is like the fifth time I've done this now - we really need a "generic modeling questions" thread.

This isn't directly related to porting, though has some relevance in that it involves potential ports and Source Filmmaker files.

Long story short, though, I need some help parsing HL2 MDL files.

The reason I am posting this here is because I have been recommended to pose my question to the Xentax forum. However, it appears they require you to pay to register, and you have to register to post, so that's not happening.

I was wondering if someone here, who has posting access at Xentax, could pose the question for me?

Here is all the relevant information:

- Half-Life 2 .mdl file format by Valve Software. 
- I need both the local material paths, and the material names.
- According to public source files provided by Valve, the header of the .mdl file contains (among other things) addresses to where the material paths and material names can be found, as well as how many of each there are. However, I can't figure out how to make them accurate.
- Need parsing information for .mdl formats "IDST," "IDST0" and "IDST1", if they differ.
- An example .mdl file, unusable without its associated files, can be found here: [https://dl.dropboxusercontent.com/u/841 ... plemdl.rar](https://dl.dropboxusercontent.com/u/8416055/Semipermanent/samplemdl.rar)
- Relevant information for the .mdl header for Source 2007 engine can be found here: [https://dl.dropboxusercontent.com/u/841 ... _notes.rar](https://dl.dropboxusercontent.com/u/8416055/Semipermanent/parse_notes.rar)
- A small infographic, using the above sample .mdl and above header information, showing the problem: [https://dl.dropboxusercontent.com/u/841 ... renMDL.jpg](https://dl.dropboxusercontent.com/u/8416055/Semipermanent/VarrenMDL.jpg)
- Relevant information for the .mdl header for some other version of the format can be found here: [https://developer.valvesoftware.com/wiki/MDL](https://developer.valvesoftware.com/wiki/MDL)
- It appears that the .mdl source files are straight C.

Again, I hate to post this here, but this is the closest we have to a "general modeling question" thread, and I don't know anyone who has posting privileges to xentax. I know there are some people who frequent this area who do, though. I am hoping one of those kind people would be willing to help me.

This is for a packager program that would make Source Filmmaker DMX files self-contained, to allow for easy cooperation between team partners, by the way.[/QUOTE]
## Post #2
- Username: Bigpet
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Sep 25, 2013 10:08 pm
- Post datetime: 2013-10-11T20:00:05+00:00
- Post Title: Source Engine MDL

I'd say that your best bet is to look at the various SDK releases for details.

The most relevant seem to be:

[sp/src/public/studio_generic_io.cpp](https://github.com/ValveSoftware/source-sdk-2013/blob/b2215f2dbc553b2c2ddcbc2a43092c077b7f8965/sp/src/public/studio_generic_io.cpp)

[sp/src/public/studio.h](https://github.com/ValveSoftware/source-sdk-2013/blob/b2215f2dbc553b2c2ddcbc2a43092c077b7f8965/sp/src/public/studio.h) look at struct studiohdr_t (the datadesc is the datamap_t)

and 

[sp/src/public/datamap.h](https://github.com/ValveSoftware/source-sdk-2013/blob/b2215f2dbc553b2c2ddcbc2a43092c077b7f8965/sp/src/public/datamap.h) look at struct datamap_t



edit: Looks like that won't really help. It seems like the actual files are loaded through datacache.dll and the structures are returned from engine.dll. But it would still be interesting to load the *.mdl in question into the SDK and set breakpoint at the point where the studiohdr_t is passed from the engine.dll. Then he could see what value the *.dll spits out and if they correspond 1 to 1 to the binary file, or if the IVModelInfo implementation in question changed anything.
