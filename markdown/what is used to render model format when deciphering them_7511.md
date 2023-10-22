## Post #1
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2011-10-16T10:40:12+00:00
- Post Title: what is used to render model format when deciphering them?

I am a C++ console programmer who seldom do rendering stuff, and I want to get into cracking model formats

I know a lot of people simply use 3D max scripts to read in the model formats and read the data, but I don't have the hardware or the software to run 3D max right now.

for those of you who use programming language to crack the model formats, what tools do you use to render them? I know C++ supports structures so it should be ideal for this purpose, but I don't know what to use for rendering. What are the choices? OpenGL is the only one I know, but it has several limitations of its own.
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-17T13:38:43+00:00
- Post Title: what is used to render model format when deciphering them?

it is best to use a scripting language like maxscript (max), mel (maya), or lscript (lightwave). writing your own renderer is not a hard thing to do; it just requires a little opengl and windows programming, which are both easy. but it's still easier to use a known modeler rather than screw with window handles and device/render contexts, so that's what i use rather than write my own renderer.

if you are intending on using the forum because you want to be a future game developer (or if a game contains animations that cannot be easily converted to max and you want to see them), write your own renderer. otherwise, don't. use max, maya or lightwave.

for C++:
visual studio 2010 is free for students at dreamspark.com.
mingw is free software and comes with a good C++ compiler.
eclipse is free software and you can hook up gcc and g++ from mingw and have a nice IDE for C and C++.

for modelers:
3ds max is also free for students at autodesk.com.
maya is also free for students at autodesk.com.
lightwave sucks and is not free. i had to pay $199 for that shit. another $199 a few years back for v9 as well.
## Post #3
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2011-10-17T18:20:25+00:00
- Post Title: what is used to render model format when deciphering them?

I have visual c++ installed, I just don't know what I should use to view the model files I have read.
I have some opengl, but it's a pretty raw toolkit.

a lot of coders were able to capture images of their process of cracking the model files, and I have no idea how they do that.
## Post #4
- Username: Satoh
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-10-30T03:39:52+00:00
- Post Title: what is used to render model format when deciphering them?

Noesis is probably actually your best option for reverse engineering with C/C++. It's what I use, that's kind of the reason I created it to begin with. It has a number of ways you can feed geometry into it, including various modes (like points) for debugging/testing. It also handles things like terminated triangle strip lists for you, and contains dozens of functions for dealing with all kinds of common data formats you may come across when reversing console (mainly PS2, 360, and PS3) data that you would otherwise have to figure out on your own if you're off in Max/Maya/etc. land.

Look at the plugin source included in any distribution of Noesis for example plugin code. There's also the option of writing Python scripts for it, though in my opinion debugging in native code makes reversing data much easier. Can't beat the MSVC debugger for casting and testing data at runtime.
## Post #5
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-12-19T05:00:03+00:00
- Post Title: what is used to render model format when deciphering them?

I wasn't even aware noesis had a point renderer... I'll have to figure out how to use it, it should be indispensible to me for finding verts now!
