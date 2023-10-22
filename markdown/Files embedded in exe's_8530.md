## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-12T04:22:01+00:00
- Post Title: Files embedded in exe's?

Is there some standard way of packing files inside an executable?
Or can people do whatever they want with an exe, as long as it's a valid PE file?

Like I extract the files and all I see is the exe for the game and nothing else, though the exe itself is massive.
I go through it and see a file table, but then the data is compressed/encrypted or something.
## Post #2
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2012-03-12T04:40:36+00:00
- Post Title: Files embedded in exe's?

> Reply from finale00
>
> Is there some standard way of packing files inside an executable?
Or can people do whatever they want with an exe, as long as it's a valid PE file?

Like I extract the files and all I see is the exe for the game and nothing else, though the exe itself is massive.
I go through it and see a file table, but then the data is compressed/encrypted or something.
There isn't really a standard for this.  Are you asking because you have one in particular that you want to extract things from?  Or are you asking in general?  Or do you want a method to do it yourself?

I can answer right away, if you want to do it yourself, if it's a .NET based executable, Xenocode/Spoon is a great system to embed a virtual file-system into your exe file.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-12T05:58:22+00:00
- Post Title: Files embedded in exe's?

lol these kinds of things are worth $2000?

I'm guessing a lot of exe files (the ones with MZ heading anyways) have similar structure?
## Post #4
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2012-03-12T06:34:19+00:00
- Post Title: Files embedded in exe's?

> Reply from finale00
>
> lol these kinds of things are worth $2000?

I'm guessing a lot of exe files (the ones with MZ heading anyways) have similar structure?
Did you pay full price for Photoshop or 3DS Max?  I'll just leave it at that, and you can read between the lines ... 

But, it all depends on the system the exe file is using on how easy it is to get the files or not.  A system like Xenocode/Spoon is more difficult to reverse than some system that isn't trying to hide everything.
## Post #5
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-03-12T06:40:02+00:00
- Post Title: Files embedded in exe's?

If I recall right in Windows you can embed files within EXEs as resources. It's called [RCDATA](http://msdn.microsoft.com/en-us/library/windows/desktop/aa381039%28v=vs.85%29.aspx). They can be loaded in code via the [LoadResource](http://msdn.microsoft.com/en-us/library/windows/desktop/ms648046%28v=vs.85%29.aspx) function. It's not just limited to accelerators, menus, icons and bitmaps. You can store arbitrary binary and text data in there as well. Resource sections in EXEs are oftentimes hacked as there are many programs that can open up EXEs and read/write to the resource data section of an EXE file (the old Borland C++ comes to mind).
## Post #6
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2012-03-12T06:47:35+00:00
- Post Title: Files embedded in exe's?

> Reply from howfie
>
> If I recall right in Windows you can embed files within EXEs as resources. They can be loaded in code via the LoadResource function. It's not just limited to accelerators, menus, icons and bitmaps. You can store arbitrary binary and text data in there as well. Resource sections in EXEs are oftentimes hacked as there are many programs that can open up EXEs and read/write to the resource data section of an EXE file (the old Borland C++ comes to mind).
Yes, that's true, but if he's trying to reverse something, they almost always use some form of obfuscation and system that does the obfuscation.  Rarely will you find like a game exe that is using standard methods, and if you are making something, and don't want it reversed, you shouldn't use the standard way.  That's why I was asking exactly what he was trying to do.
## Post #7
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-03-12T06:50:28+00:00
- Post Title: Files embedded in exe's?

> Reply from finale00
>
> 
Did you pay full price for Photoshop or 3DS Max?  I'll just leave it at that, and you can read between the lines ...

lol my photoshop is legal. $500 for Master Collection at journeyed. you can get photoshop alone I think sometimes for $99 when they have a student sale. my 3ds max too (student edition, so only good for 3 years). if you know someone with a .edu address, hit them up to get you free software LOL! doesn't matter who... if you know a criminal justice major or some shit, have them get you the software lol! they'll never use it ha ha ha!
## Post #8
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-03-12T07:14:02+00:00
- Post Title: Files embedded in exe's?

> Reply from brienj
>
> Yes, that's true, but if he's trying to reverse something, they almost always use some form of obfuscation and system that does the obfuscation.  Rarely will you find like a game exe that is using standard methods, and if you are making something, and don't want it reversed, you shouldn't use the standard way.  That's why I was asking exactly what he was trying to do.

Oh ok, yeah, looks like he just wants to extract files from some game with a large EXE. One way to find out if it uses RCDATA is to load the EXE in visual studio. If it's RCDATA, you will see a boatload of crap listed in VS. If it's not, you won't see much... just some icons and maybe some dialog crap. And yeah, if it's encrypted RCDATA or some other non-standard method I would just move on since there's plenty of other easier games to work on. Ha ha ha there's a bunch of guys here who would love you forever if you would help them extract their gundams lol. What game is it finale00?
## Post #9
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-03-12T07:37:32+00:00
- Post Title: Files embedded in exe's?

I know that some packers/extractors allow you to create EXEs with embedded files (almost always as self-extracting archives) or extract files from EXEs in some cases. For games, this would be terribly hit-and-miss (and, probably, mostly miss), but it's there as one possibility.

File rippers (such as Jaeder Naub) should be able to find and rip certain types of files from the vast majority of EXEs with embedded files, unless the files are compressed or encrypted (and maybe sometimes even then, I'm not really sure).
## Post #10
- Username: mono24
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-14T00:04:14+00:00
- Post Title: Files embedded in exe's?

Personally, I like to define a custom section for the linker to generate and stick some stub info there, then I'll have another tool that takes my PE, finds that custom linker section by string name (by going through the PE sections til it finds it), and overwrites the custom struct with filesystem info and location. Then I just stick that filesystem itself on the end of the file. That's my process for making self-installers.

But, if you're looking for standard methods, yeah, there really aren't any because there are so many options for shoving crap in an exe. Embedded resources are a feature of PE's as well (as outlined by the spec, it's pretty straightforward to get at resource binary), but it's relatively rare to find proprietary binary or entire filesystems buried in that section. One thing that can definitely help with finding/sorting crap out, though, is understanding the PE structure and parsing it out yourself. You can find out rather quickly if any part of the binary is unreferenced as a PE section or if any data in the data sections points to large chunks of the binary which are likely to contain interesting data. The Windows PE spec is all over the internet, so writing a parser for them is pretty easy. 64-bit PE's are nearly identical by spec as well, making my existing 32-bit PE loader handle 64-bit was a lot easier than I was expecting it'd be the first time I did it.
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-22T21:39:36+00:00
- Post Title: Files embedded in exe's?

Where's the specs for these exe files? I saw one but it was like MS-DOS PE or something. Is that what I'm looking for?
## Post #12
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-04-22T23:17:56+00:00
- Post Title: Files embedded in exe's?

[http://lmgtfy.com/?q=portable+executable+specification](http://lmgtfy.com/?q=portable+executable+specification)
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-10T19:02:16+00:00
- Post Title: Files embedded in exe's?

I've written a PE reader after reading an article or two.
It just grabs the PE offset in the DOS header and heads over to the PE header. Then I  grab the section count, skip the optional header, and start reading in the sections.

But then I realized that the exe I'm working with stores the rest of the data after the last section.

And then there's another exe file there, and it has a whole file table stored after its sections.

But is true that all of the data stored after those .text, .rdata, .reloc etc sections is just "other stuff"? Or is there an offset somewhere that says "this is where the other good stuff is"

Ok I sort of just glanced over all of the technical explanations and just needed to know how to get around the file so I might have missed that piece of info lol
