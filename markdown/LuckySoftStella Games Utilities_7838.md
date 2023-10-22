## Post #1
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2011-12-10T23:13:56+00:00
- Post Title: LuckySoft/Stella Games Utilities

I've finally gotten around to updating these programs and linking them with the latest games. Here's me restoring the tools after the purge. The tools are linked against Secrets of Power: Alexander the Great, engine build 1240. Note that for these programs to work you will have to supply the game engine core files, as those are copyrighted and not included in the distribution files. All command line apps will display usage text if you run them without arguments. Use those to help you figure out what to do, and if you still have questions ask here.

Stella Games LzmaPack Decryptor and Unpacker
This tool allows you to extract files from Data.pack. You can extract all files, one file, files that match a certain glob, and encrypt/decrypt the pack for whatever reason. Encryption key is not included, so you'll have to extract it out of the game launcher. Save the key text inside a Unicode text file, or else the key won't work. Here's the typical usage scenario:

```
LuckySoftUnpack.exe /in=path\to\Data.pack /extract /keyfile=path\to\key.txt
```

This will extract all files in the LzmaPack to a directory named Data_decrypted.pack that is in the same directory as the input file.

Download: [blog/?p=646](http://forum.xentax.com/blog/?p=646)

Stella Games Assembly Deobfuscator
This tool decrypts the assemblies from the 'bin' folder inside the game folder and attempts to restore their original names. The resulting files can then be referenced by .NET programs for use. You will need to point the tool to Startup.bin, which is the initial assembly deobfuscator. Startup.bin must be from a game later than Elementals: The Magic Key (i.e. Mystery of Mortlake Mansion and Secrets of Power: Alexander the Great), because the version in Elementals is obfuscated in itself. After that, pick the bin directory, and click on "Deobfuscate". You'll see the log window scroll, and when it's done you may see files that need "rectifying". Pick one, click on "Rectify", and swap the letters from the bottom box until it successfully deobfuscates. Note that you do not need to deobfuscate 1h0iv6hs00twjvh8wr.bin and z03zw30tp0nn0sjixs.bin, as they are merely flags and their contents are in one of the other files.

Download: [blog/?p=649](http://forum.xentax.com/blog/?p=649)

Stella Games UData Binary/Udl Transcoder
Once you've unpacked the game files, you've probably noticed that most of the .resource files are in some sort of binary format. This tool will allow you to convert the file between binary, compact, and formatted formats. Double click on a .resource or .metadata file to convert it to text and view it, and right click on it to convert to one of the three formats. It doesn't get any simpler.

Download: [blog/?p=653](http://forum.xentax.com/blog/?p=653)

Stella Games Image Decompositor (Noveau)
This is a rewrite of the previous image decompositor, and does not use the game engine to do the decompositing. This program takes all the image resources that have been composited, and separates those images back out. This makes it easy to find the images and edit them if you wish. Just supply the repository root path (must be extracted) to the tool, and it'll separate out all the files that are in composites. The output format is PNG, and the input can be DDS, PNG (as of Alexander the Great), and Targa (very recently). As usual, do not steal other people's art assets and use it in your own projects.

The reason the program was rewritten is because the engine needs to be wrangled to not alpha blend, and in Alexander the Great transparency is very screwed up. Therefore I used a proven library (FreeImage and System.Drawing) to read and write images, putting problematic code out of the way. It works much faster than the game engine, and doesn't run out of memory or crash like the game engine does.

Download: [blog/?p=990](http://forum.xentax.com/blog/?p=990)

Updated June 6, 2013
v.2.1:
- Rewritten decomposing process to decompose images by composites, resulting in no duplicate loading of composites.

Startup.bin and these programs
If you can't get a copy of Engine.dll, you can still run these programs. Just obfuscate them with Startup.bin and run them under Startup.bin.
To obfuscate:

```
Startup.bin --obf path\to\program.exe
```

If not in it already, move the obfuscated file to the bin folder.
To run:

```
Startup.bin ProgramName arg1 arg2 arg...
```

LzmaPack BMS script
I haven't managed to get it working, but I'll say it's theoretically correct. I think QuickBMS expects every compressed section to have its own decoder bytes, but in the LzmaPack it's defined once at the beginning.


 LzmaPack.zip
LzmaPack BMS script (not working) (447 Bytes) Downloaded 44 times


GRAF Format Wiki Page
[http://wiki.xentax.com/index.php/GRAF:S ... s_LzmaPack](http://wiki.xentax.com/index.php/GRAF:Stella_Games_LzmaPack)

If you have any problems, please leave a reply. If you need to have the programs linked against an older game (Alexander the Great refactored all of their code so the namespaces are different), reply with the version.txt file and game name and I'll try recompiling it for you.
## Post #2
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2012-02-18T22:03:29+00:00
- Post Title: LuckySoft/Stella Games Utilities

New tool has been posted. It separates game images from the composites into individual files. Useful for making art out of game assets.
## Post #3
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2012-12-04T09:39:06+00:00
- Post Title: LuckySoft/Stella Games Utilities

Tools have been relisted on this page, but not yet uploaded. I'll have it on the tools blog soon.

Update: Tools uploaded and linked.
## Post #4
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2013-06-06T16:29:51+00:00
- Post Title: LuckySoft/Stella Games Utilities

Stella Games Image Decompositor (Noveau) has been updated.
## Post #5
- Username: AntonZab
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 20, 2015 2:38 am
- Post datetime: 2015-09-23T19:31:06+00:00
- Post Title: LuckySoft/Stella Games Utilities

Hi GMMan. I downloaded all these applications.I did deobfuscation. Found Engine.dll. Posted in Bat script file. and gave me a sign

The input file is C:\ -------- \ Data.pack
The output file / directory is Data_decrypted.pack
Error: Can not open GammaXoringStream as a LzmaPack. Please make sure your key is valid.

Tell me where to get the key. Where and how to unpack it?...
