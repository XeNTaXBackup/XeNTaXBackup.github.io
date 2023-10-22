## Post #1
- Username: bizzybody
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Jan 02, 2008 4:54 pm
- Post datetime: 2009-01-07T03:35:22+00:00
- Post Title: Source engine .mdl decompiler that doesn't require Steam?

I want to decompile a couple of .mdl files from Portal but the only app I've found that can requires Steam to be installed.

It will need to specifically support "Orange Box" Half Life 2 and Portal .MDL files. From what I read on the Valve developer Wiki, they updated the .MDL (and .VTF and other files) just for these games, though a few were still compiled with older versions of the formats.

There are plugins to import the 3D data into some version of 3D Studio and Blender *after* it's been extracted from the .mdl file.
## Post #2
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2009-01-10T20:14:31+00:00
- Post Title: Source engine .mdl decompiler that doesn't require Steam?

The decompiler that I use says in the readme that steam is required to be installed, but it's not really necessary. The decompiler just looks for a couple of files associated with steam. If those files are in the same directory as the decompiler, they will work even without steam installed. I will see if I can remember which files are needed by looking on my other system when I have it available. I have not yet seen a decompiler that works with the newer .mdl files used in portal and HL2 episode 2.  The one I have only works with HL2, Episode One, SIN Episodes, Dark Messiah of Might and Magic, and to a limited extent on Vampire: Bloodlines (no animations for that one).
## Post #3
- Username: bizzybody
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Jan 02, 2008 4:54 pm
- Post datetime: 2009-01-11T00:15:10+00:00
- Post Title: Source engine .mdl decompiler that doesn't require Steam?

I found an older copy of the vstdlib.dll that mdldecompiler.exe (the supposedly bugfixed version of the one by CannonFodder) complained about. With that and tier0.dll in the same folder, it works.

Valve updated vstdlib.dll (among other things) and that broke the decompiler, which nobody has bothered to update to work with the new dll.
## Post #4
- Username: bizzybody
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Jan 02, 2008 4:54 pm
- Post datetime: 2009-01-11T00:30:29+00:00
- Post Title: Source engine .mdl decompiler that doesn't require Steam?

Here's the vstdlib.dll that actually works with [Erik's fixed version](http://developer.valvesoftware.com/wiki/Mdldecompiler) of CannonFodder's decompiler.

Here's where I found this version of the dll. [http://forums.facepunchstudios.com/show ... p?t=592985](http://forums.facepunchstudios.com/showthread.php?t=592985)

[http://www.afreedll.com/dll/download/2546/vstdlib.dll](http://www.afreedll.com/dll/download/2546/vstdlib.dll)
[vstdlib.zip](https://xentaxbackup.github.io/file/1804_vstdlib.zip)
