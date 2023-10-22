## Post #1
- Username: Emzi
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Aug 30, 2016 3:42 am
- Post datetime: 2016-09-21T21:23:32+00:00
- Post Title: Star Trek Online MSET Decompiler

Star Trek Online MSET Decompiler

It's been a little over 6 and half a year since Star Trek Online launched, and throughout all that time, nobody managed to crack open the game's model files. Today I present to you, the MSET decompiler.

Download Link

Tool is available here: Box [dead link removed]

Requirements

The tool was developed using .NET Framework 4.5. It is a commandline tool, and as such, the following is required:

Commandline familiarity
Windows: Windows 7 or above (with .NET 4.5 or newer installed)
Linux: Mono 3.2 or newer (I only tested with Mono 4.x though, however Mono 3.2 should support .NET 4.5)
Features

Tool's rather simple. It allows you to decompile any .mset file into either OBJ or PLY (both binary LE and ASCII formats are supported) files which you can import into Blender or 3DS max, and from there import to other games if you wish. If you want to convert into some other format, you can also dump raw mesh data in XML format.

The resulting meshes have the following information:

Vertices
Normals
Faces
Texture Coordinates
Vertex Colors (if present)
Binormals (if present, raw dump only)
Tangents (if present, raw dump only)
If applicable, other data (raw dump only)
Bug reports

MSET file format is not officially documented. I might, in the future, publish a documentation for people who want to work with the format themselves. However, due to the fact that it's been mostly guesswork, there might be files that break it. If possible, try to run a log and send it to me along with a file that caused a problem. Basic information about your environment (OS, version, .NET/Mono/other .NET runtime version) would also help.

While it is possible that this tool will run with .NET runtimes other than Microsoft .NET/Mono, these are the only 2 I officially support.

Future plans

Since I have the format (mostly) documented, I might create a recompiler in the future. Such a tool would convert OBJ or PLY files into MSET files.

Other stuff

Since the tool is obfuscated, Windows or whatever av you use might pick it up as a false positive. I can assure you, the tool contains no malicious code, and, as such, is safe to add to exception list.

Last thing, this tool's been written in my free time, and I'd appreciate any thanks or donations (you can make one [here](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=8UB3CLTBZGURE)).
## Post #2
- Username: Regardie
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 27, 2016 10:01 pm
- Post datetime: 2016-10-27T14:08:26+00:00
- Post Title: Star Trek Online MSET Decompiler

I registered because you posted this.  Does it work?  The box link is dead so I can't test it for myself.

Is your tool capable of compiling mset after working on the decompiled geometries?
