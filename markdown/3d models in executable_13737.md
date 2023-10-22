## Post #1
- Username: theclub654
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Oct 14, 2015 8:57 am
- Post datetime: 2015-12-29T06:24:33+00:00
- Post Title: 3d models in executable

hello today i am here to tell you i am a programmer with little experience one of my biggest dreams is to mod a console games 3d model as i cant do that right now because i have little experience so im here today because i wanna look into a games code and see how they load a 3d model file and check the format so i can use that and reverse engineer it and use it to make a importer and exporter for a game i like can anyone give me tips and pointer on what i should be looking for in the games code because i've been dreaming this for years now and i would really love to do this i now what vertices and faces and uvs and stuff like that are but i wanna know how to find it in a games executable and i already know how to load executables and stuff like that you know basics i just need to know what i need to be looking for in the executable
## Post #2
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-12-30T00:59:21+00:00
- Post Title: 3d models in executable

Start off by using periods in your sentences.
## Post #3
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2016-01-11T21:03:05+00:00
- Post Title: 3d models in executable

> Reply from theclub654
>
> hello today i am here to tell you i am a programmer with little experience one of my biggest dreams is to mod a console games 3d model as i cant do that right now because i have little experience so im here today because i wanna look into a games code and see how they load a 3d model file and check the format so i can use that and reverse engineer it and use it to make a importer and exporter for a game i like can anyone give me tips and pointer on what i should be looking for in the games code because i've been dreaming this for years now and i would really love to do this i now what vertices and faces and uvs and stuff like that are but i wanna know how to find it in a games executable and i already know how to load executables and stuff like that you know basics i just need to know what i need to be looking for in the executable
Punctuate.

Find a file you know is going to be loaded ahead of time, and break when it's accessed. Then trace through each instruction until you either see it being loaded, or see a DLL call that has some name like 'model read' or something. It'll likely be the former, since usually external calls aren't easily spotted and just get compiled into the basic functionality.

Assuming you do actually know the basics of loading an EXE, then it shouldn't be much trouble to do that. There is no magic word that will tell you "the exe is loading a model now."

Generally there are two forms of model loading.
The first form is where the programmer already knows the structure of the model and writes the code to read it into memory line by line.
Because programmers are generally so far removed from file auditors and authors that you could fit the great wall of china between them lengthwise, this is probably not how the code will work.

The second form of model loading is when the creator of the model format writes the import and export code into a self contained module and provides that to whomever has licensed the model format for use (this is generally a 3rd party company that has no direct affiliation with the game's producer or developer)
This module then gets loaded and told to handle everything without the programmer really having to do any work outside of knowing how to integrate a module.
Occasionally the developers will modify the module in order to support an extra layer of compression or to read in a specific order or read a new type of data. Depending on the size and budget of the company using the module, they may simply ask the company licensing the module to modify the code for them as part of the contract.

In the end all this really means is that instead of decompiling and/or inspecting the contents of the exe, you should be decompiling or inspecting a random DLL somewhere.

If you've never done any sort of assemby inspection before, I recommend you learn how to hack native binaries before trying to hack how they load models.
Its a lot easier to make a character immortal or be able to fly around with impunity from gravity, than to hook the model load process.

If you don't have a debugger like cheatengine or such that can show you both the RAM and instruction set of the program you're working with while it runs, you should probably rethink your strategy for loading models.
