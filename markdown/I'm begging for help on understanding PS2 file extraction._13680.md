## Post #1
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2015-12-15T05:44:17+00:00
- Post Title: I'm begging for help on understanding PS2 file extraction.

I'm literally at my wits end here. I've have been trying since July to rap my head around PS2 model ripping after learning it was possible for the sake of my personal hobby, making paper models, and for months I've found only whispers and poorly documented successful attempts buried under Noesis and 3D Ripper tutorials. I've tried asking in just about every other forum and for whatever reason, I'm rarely lucky enough get a single reply, never mind and actual answer. In short, I'm literally begging that someone,anyone, would be able to give me something, anything, at this point that adds some clarity to the process of getting files out of a archive and getting model data out of the files barring information on quickbms since it's actually pretty well documented. I need to know what model data and TIM 2 textures looks like in hex, I need a better understanding of file headers and what they look like when displayed solely in hex rather than a three letter code at he beginning of a file, I need information. If you are reading this and have anything to contribute, please post it. I'm extremely willing to learn this difficult process but I can't make any progress with all of these dead ends.
## Post #2
- Username: XNTX=26
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Dec 09, 2015 8:33 pm
- Post datetime: 2015-12-15T06:47:31+00:00
- Post Title: I'm begging for help on understanding PS2 file extraction.

What game is you want to get models from? This guide might be useful [http://www.vg-resource.com/thread-20541.html](http://www.vg-resource.com/thread-20541.html)
## Post #3
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2015-12-15T09:48:34+00:00
- Post Title: I'm begging for help on understanding PS2 file extraction.

Front Mission 4, 5, and Online. All share the same archive method of a single unencrpyted .DAT file and a .POS file that breaks down the individual files. I didn't know what to do with either at first so I contacted the guy who runs PS3Dformat wiki to take a look, he wrote a script to open FM4's .DAT that generated over three thousand files. He said just send him a bunch at a time, which I did, but it's not entire feasible for one person to  shift through hundreds of files for a complete stranger. I asked to explain his methods so I may eventually search through them on my own time and eventually move onto 5 and Online- fifteen days ago. I wanted to make once last plea for guidance to see if I could get even a sliver of new information after all this time and effort. When it comes to ripping from PCSX2, it's not viable for my particular circumstances. While it would allow me to at least get textures without any effort I would have to play both FM4 and FM5 to the specific points where I face the boss mechs I wish to extract and the parts necessary to build the playable units I want to extract, then there is the fact that the boss units have to be grabbed "in the wild" without the aid of a character viewer to get proper angles, and Online is a long defunct MMO so I have to go inside it directly anyhow.
## Post #4
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-12-15T10:52:12+00:00
- Post Title: I'm begging for help on understanding PS2 file extraction.

There aren't any particular secrets when it comes to Noesis. If it's a supported format, just open it up and export. If it's not a supported format, well, Noesis won't help you. Noesis works by interpreting the source data, rather than working with projected geometry and data that no longer exists at the rendering API implementation level like the methods outlined in the link above. The haphazard "it'll have to be scaled on the y axis, who knows how much" bit is pretty terrible, and is because you've also lost the data you need to correctly unproject the geo at that stage, you have to just eyeball it and live with the usually-subtle loss in precision and other data elements.

Presumably I'm not telling you anything you don't already understand, so you're looking for someone to tell you how to reverse engineer things. Expect to spend some months or years of your life delving into a new world if that's the case. There aren't any well-kept secrets or anything there, it's all out in the open, but it's also a huge body of esoteric knowledge just in the fundamentals, and typically when you get into PS2 games you need a bundle of esoteric PS2 bullshit on top of that huge body of esoteric knowledge to recognize what you're looking at. I haven't looked at the Front Mission formats, but starting with a PS2 format probably isn't the best idea in general if you haven't dug through formats before. And honestly, I'm not even going to recommend you try going down this road when your end goal is papercrafting and not all of this bullshit. Unfortunately, that means you're at the mercy of someone who wants to donate hours, days, or weeks (depending on how much of a pain in the ass the format is) to helping you. So, this is the reality, that things take knowledge, and that knowledge takes time to accumulate even when it's freely available to all, and even with the knowledge things still take time to do, and getting people to give you a lot of their time is usually a bitch unless you can hit their ego the right way or give them money or something.

There's also the possibility of modifying PCSX2 and making some hooks to dump geometry at key points. This would work for lots of games, but would still require some small per-game handling. I haven't looked at the PCSX2 codebase other than to try to resurrect its debugger some years ago, but I'd bet you could hook into the VIF emulation there and probably just expose a simple API or something so people can monitor unpacks and pull model data out of VU memory as needed in their per-game handlers. This would be a more blind runtime way of dumping fully-intact data, but of course you'd still have to be emulating the VIFcode you wanted to dump, meaning you'd probably need the model(s) onscreen and you would need to filter through a lot of data and VIF states, being careful to interpret particular data in the right way as many different types of data may be getting unpacked and you'd want to associate your handling with the active microcode. It also doesn't help you if the geometry you're pulling out isn't transformed in a way that's friendly, because then in most cases you'd have to start running through the actual VU microcode and at that point it's probably more difficult to deal with than if you'd just started with the source data. This entire paragraph is completely useless because no one will ever do any of this, and anyone that knows enough to do it probably doesn't need me to give them the idea. Oh well, already typed it.
## Post #5
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2015-12-15T18:53:38+00:00
- Post Title: I'm begging for help on understanding PS2 file extraction.

I've also looked into ram dumping through PCSX2, a vagrant box, and an actual PS2 but haven't found enough information or practical successes to determine if it's actually viable or only really useful for cheats. When It comes to reverse engineering, I'm not asking to have my hand held, in case anyone is holding back because they don't want to get involved. I just want to be pointed in the right direction at least so I can make my own assessment of what I'm willing to do for my end goal. Being told I shouldn't even bother doesn't give me the closure of at least trying and failing. Personally, I don't know how anyone can make a value judgement around the amount of effort involved in my desires but if you put in the same amount of effort into porting stuff to Source because that's what you want to do, you get a ticker tape parade. Coding isn't even out of my wheelhouse anyhow since it's my Major, while learning this would naturally be in wildly impractical it would a be another way of expanding my knowledge base. Since this stuff is so out in the open can you guide me to anything I can read? Maybe I've just been incredibly dense and not googling properly.
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-15T20:41:54+00:00
- Post Title: I'm begging for help on understanding PS2 file extraction.

> Reply from Greg
>
> I need to know what model data and TIM 2 textures looks like in hex, I need a better understanding of file headers and what they look like

The short answer to this is they can look like anything and that is the problem of reversing. In each particular case you just have to guess it all. The only thing you can be sure of, is that model data must hold an array of coordinates, but how they will be presented - this is only a matter of chance and your experience.

If you've seen the [http://wiki.xentax.com/index.php?title=DGTEFF](http://wiki.xentax.com/index.php?title=DGTEFF) and Mr.Mouse's videos, you must understand the basics.
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-15T20:48:50+00:00
- Post Title: I'm begging for help on understanding PS2 file extraction.

> Reply from MrAdults
>
> This entire paragraph is completely useless

This world is full of useless things and situations when you realize how complex and cool was the thing you did, but nobody will ever understand it.
## Post #8
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2015-12-15T20:55:50+00:00
- Post Title: I'm begging for help on understanding PS2 file extraction.

> Reply from daemon1
>
> Greg wrote:I need to know what model data and TIM 2 textures looks like in hex, I need a better understanding of file headers and what they look like

The short answer to this is they can look like anything and that is the problem of reversing. In each particular case you just have to guess it all. The only thing you can be sure of, is that model data must hold an array of coordinates, but how they will be presented - this is only a matter of chance and your experience.

If you've seen the http://wiki.xentax.com/index.php?title=DGTEFF and Mr.Mouse's videos, you must understand the basics.

This is good, TIM 2s don't have a set pattern and vertice data also lacks an obvious tell. Learnin' stuff already.
## Post #9
- Username: XNTX=26
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Dec 09, 2015 8:33 pm
- Post datetime: 2015-12-15T22:00:30+00:00
- Post Title: I'm begging for help on understanding PS2 file extraction.

I decided to download front mission 4, did some looking around, found this tool
[http://www.romhacking.net/utilities/659](http://www.romhacking.net/utilities/659) 

Author Vash
Textures Extractor/Reinserter is a simple command-line program that is able to scan any file for TIM2, TIM3, and GIM images then extract them. It can also reinsert them back into the game after you are done editing them with other programs.

TextER.exe -e dvdimage.dat -tm 

for %%X in (*.*) do texter -e "%%X" -tm.bat

Looking for TIM2 and TIM3 file(s):

Found 8089 TIM2 and 0 TIM3 in dvdimage.dat
## Post #10
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-12-15T22:13:56+00:00
- Post Title: I'm begging for help on understanding PS2 file extraction.

There's not much in particular I can guide you to. It's like saying you want to safely amputate your arm so you'd like some pointers on cutting through bone and you'll totally take it from there.

The best course of natural knowledge accumulation for you would be to write software for your target platform, and become familiar with using platform constructs that will help you spot the data you're looking for. But then maybe the game in question doesn't even use any platform standard you're expecting, so in some cases unless you really take the time to trace through disassembly and painstakingly chart out pages upon pages of binary in potentially multiple processor languages, you may never understand the data fully. Again, being able to do this comes naturally with debugging and tackling hard optimization problems for a platform, but it's not like MIPS assembly is a secret language either.

TIM2/3 is a pretty common format and is identifiable by signature. It's also already supported by a bunch of tools, so, no mysteries there. PCSX2 is also open source if you don't want to have to understand the  texture tiling often favored by the PS2, but again developing for the platform and seeing when/why these things are important is how you would naturally acquire the knowledge.
## Post #11
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2015-12-15T22:56:52+00:00
- Post Title: I'm begging for help on understanding PS2 file extraction.

Great work, Xntx! That vastly simplifies finding textures. "MIPS assembly is a secret language either" I did download ida66 to dissemble the game but wasn't entirely sure if it was a requirement or simply an alternative route. I look into it and PS2DEV. See, you pointed me in the right direction. I never saw anyone make overt references to MIPS or other PS2 programming when I looked.
## Post #12
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2016-01-11T23:46:47+00:00
- Post Title: I'm begging for help on understanding PS2 file extraction.

Anyone one else has anything to share?
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-01-12T15:12:17+00:00
- Post Title: I'm begging for help on understanding PS2 file extraction.

> Reply from Greg
>
> Anyone one else has anything to share?

Tell us about your experiences. What were you able to do so far?
## Post #14
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2016-01-13T06:45:51+00:00
- Post Title: I'm begging for help on understanding PS2 file extraction.

As of right now- I've learned Cheat Engine can be used to find vertex data thanks to the guy who's working on those files for me, answering one of the major "hows?" I had, I'm currently looking over the failed Dirge of Cerberus rip attempt given it's one of the few well documented PS2 attempts for practical examples, and am reading the file format guide. Also, I'm looking to PCS2X save states as a possible route for future extraction given most game won't share Front Mission's simple structure.  I'm firmly in the "learning" stage right now and probably won't be "doing" for weeks if not months, I can pop one of the unpacked files into Cheat Engine but am still figuring out what I'm looking at. I guess I could stumble my way through with the information I have now but I'd still welcome more pertinent information.
## Post #15
- Username: RVR72GV
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 08, 2011 5:16 pm
- Post datetime: 2016-02-07T09:07:10+00:00
- Post Title: I'm begging for help on understanding PS2 file extraction.

I have PC version of Front Mission Online; maybe I can help by posting one of the .dat file for analysis. I'll upload it if anyone interested.

Completely not relevant, but 3D Ripper DX used to work with Front Mission Online's benchmark program, so it could've been worked with the actual game itself....only if they didn't kill the server for real that is.

Here's the benchmark program I'm talking about
[https://mega.nz/#!nxkEnLZa!ngtpI4mE1qPe ... rVj1cL45F8](https://mega.nz/#!nxkEnLZa!ngtpI4mE1qPefy0JAI_ddZiw977bSMAmIrVj1cL45F8)
