## Post #1
- Username: amorilia
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Apr 28, 2009 2:00 am
- Post datetime: 2009-04-27T21:33:54+00:00
- Post Title: hello + some questions

Hi everyone, I'm new here on the forum and thought I'd introduce myself. But first, I send some thanks to chrrox who (albeit indirectly) made me aware of the existence of this nice community!!

Seeing the kind of stuff you guys are doing is right at the center of my interest field: I'm author of an open source python lib (see first link in my sig for the site) for interfacing arbitrary file formats - well, there's some restrictions but so far it has worked for complex formats such as nif and cgf. With interfacing I mean: reading, writing, and changing every piece of data in them in an straightforward way, as I'm in particular interested making it easy to produce custom content (3d models, animations) for existing games. So I guess this library could be another tool in your toolbox. I must warn it is not very fast, but it codes very easy (almost no boilerplate, just a format description in xml + a class definition), and it is usually fast enough in practice except for some very specialized and resource consuming tasks.

I'm always eager to learn more, and one of the things I'm wondering right now is what kind of tools for interfacing formats are commonly used here? I've seen MultiEx commander, and I must say that I really would like to learn more about it, for instance to find out how to use its format descriptions in pyffi, or vice versa. Although mexcom seems more like a tool for working with archives, and pyffi has a slightly different focus, it feels similar in some ways to what pyffi tries to do.

So, first silly question, is this the source [http://mexcom.cvs.sourceforge.net/mexcom/](http://mexcom.cvs.sourceforge.net/mexcom/) and where should I start to learn about how it works?

Second question: any other tools worth checking out for me?

Yours,
Amorilia
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-04-28T06:25:15+00:00
- Post Title: hello + some questions

Hi and welcome! 

Well, that's indeed the source (old) of MultiEx Commander. I tried in the past to open source it let others work on it (that old hag Time prevented me to work on it myself for 100%). However, work never took off there, and I continued on my own again, cleaning the lousy code myself hehe. 

As for the scripting that MultiEx Commander does, you may want to check out the BMS guide at [http://wiki.xentax.com/index.php/BMS](http://wiki.xentax.com/index.php/BMS) That should explain the basics. There are some guys here at the Forum that know their way around BMS as well, like bugtest, Rahly, Craptain and others. 

As for tools, there are many of interest, and hopefully we will soon have our tool site. Meanwhile we have a tools page at the Game File Format Central. [http://wiki.xentax.com/index.php/Extraction_tools](http://wiki.xentax.com/index.php/Extraction_tools) and 
[http://wiki.xentax.com/index.php/Game_Tools](http://wiki.xentax.com/index.php/Game_Tools)

By the way, using XML to address formats really interests me. We have a workgroup that expresses thoughts on MeXML, an XML based way to describe file formats. I guess you are already ahead of this, but perhaps it will be worthwhile to discuss this further!

Cheers! 

Mike
## Post #3
- Username: amorilia
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Apr 28, 2009 2:00 am
- Post datetime: 2009-04-28T15:10:28+00:00
- Post Title: hello + some questions

Hi Mike,

Thanks for the warm welcome, and for the pointers to get me started in the right direction. I'm sorry to say that I can't do much yet with the code, I tried compiling with mono's vb compiler (linux is my main platform) but I have no clue where to start - the last time I used basic must have been gwbasic back in the DOS days.

If you are interested in xml for format descriptions, here is a simple example of what pyffi uses:

[http://github.com/amorilia/pyffi/blob/0 ... GA/tga.xml](http://github.com/amorilia/pyffi/blob/0632076e98c10a1787632a8f452bd11ae8eeae19/PyFFI/Formats/TGA/tga.xml)

and here's a really complex example:

[http://github.com/amorilia/pyffi/blob/0 ... IF/nif.xml](http://github.com/amorilia/pyffi/blob/0632076e98c10a1787632a8f452bd11ae8eeae19/PyFFI/Formats/NIF/nif.xml)

To be honest, I've been considering for a while to move away from xml because it's not convenient for very complex formats like the nif format (in particular version checks get pretty long and are as efficient), and to go towards a custom file format description language. Here's an example:

[http://niftools.sourceforge.net/forum/v ... 155#p15155](http://niftools.sourceforge.net/forum/viewtopic.php?f=10&t=1980&p=15155#p15155)

But I suffer from that old hag Time as well. Maybe I get somewhere with this in five years or so. 

I'll certainly post back here when I make some progress using BMS - it's different because it is really a scripting language and not just a structure description (like my xml examples above). One obvious question that comes to my mind is whether you can also create and write new archives just using a BMS? As far as I understand from a quick reading of the documentation, is that possibly partial writing of some records in existing archives could be supported with these scripts. Or is it just reading and extracting particular blobs?
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2009-04-28T16:43:20+00:00
- Post Title: hello + some questions

Hello amarilia! That's some interesting stuff you've done with XML (though I don't have much experience in the area of programming for file formats, so I can't give an opinion on its efficiency or anything).

Yep, MexScript (BMS stands for Binary MexScript and refers to the compiled script, so I try not to use it when talking about the actual script[ing language]  ) is a scripting language. IIRC, Mr.Mouse actually explicitly wrote it with scripting in mind, as opposed to C-style structure description, so that he could keep it really simple (and I'd say he succeeded on that front, when you look at some of the formats MexScript can actually handle versus the script that handles them). MexScript itself merely describes how to handle the format in question; it passes the gathered data on to whatever program is using it, and the program then decides what it can do with it. And actually, MultiEx Commander does support the creation of archives in several formats from scratch. Of course, once again, I don't have a really deep understanding of it myself, so someone else may want to jump in behind me and clarify my explanation here.
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-04-28T19:33:07+00:00
- Post Title: hello + some questions

Well, Dinoguy gives some good info on the subject. I would add that MexScript allows to save particular variable positions. For instance, you can save the filepointers for a resource's offset and size variable. When you know the offset of these pointers you can update them when you start replacing resources in an archive. Basically, this is what my old multiex.exe (DOS) did and what MultiEx Commander now does. It tells the interpreter (MultiEx.dll) to cough up a list of files, with their names, offsets and sizes, and pointers to these offsets and sizes. This will then make possible the replacement of certain files in an archive, by updating all other pointers when needed (if you replace file 2 with a larger one, you need to update these pointers for all files starting from file 2 if they are saved after the file 2. Obviously, file 1 (if before file 2) needs no updated pointers in the archive. 
This method can be applied to many formats, but when things get too complex it it tricky. If a game saves more information in its resource files, you can only hope that changing the length of archives and replacing content will be tolerated by the game code.

The archives that MultiEx Commander can create from scratch are those that are supported by plugins, not written in MexScript. Rahly wrote a plugin manager for MexCom that allows specific non-activeX DLLs, and I had created my own plugin (activeX) format previously.
## Post #6
- Username: amorilia
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Apr 28, 2009 2:00 am
- Post datetime: 2009-04-28T21:09:23+00:00
- Post Title: hello + some questions

Many thanks for the clear answers, Mr.Mouse and Dinoguy. At this point, to get the ball rolling, I'm considering to add a MexScript (yes, I'll be careful with terminology!) parser to PyFFI. That will bring the number of supported formats in pyffi, at least those that can be read, from 4 to 1004 so to say (although I like 1003 better, because of Don Giovanni's adventures in Spain).

For modifying content in existing archives, as you say the least it should attempt is to keep the data between the files intact (and then cross our fingers!). A next step could be a tool that generates xml from the scripts, so all data can be accessed in the files, and thereby at least in theory, enabling creation of new archives for anything that has a MexScript (of course there will be corner cases... I wonder if those plugins could be turned into xml - any source code examples?).

Hah, and I just found this: [http://openmex.cvs.sourceforge.net/view ... x/OpenMex/](http://openmex.cvs.sourceforge.net/viewvc/openmex/OpenMex/) Excellent! (Thank you craptain!)

Back to coding now... Might take a few days or even weeks but I'll post back in the appropriate sections of the forum if I'm making progress.
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-04-29T06:02:22+00:00
- Post Title: hello + some questions

Good luck!
