## Post #1
- Username: happypommes
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jun 26, 2018 7:41 pm
- Post datetime: 2018-06-26T12:46:28+00:00
- Post Title: FTL Advanced Edition Packer/Unpacker HELP!!!!!

Hi,
i'm new here and i really hope someone can help me!?

In 2013 i started with modding of the game FTL - Faster Than Light. Because i was busy with work i never could finish this. After the release of FTL Advanced Edition i bought it again on GOG. Now i would like to finish my mods of the game.

In 2013 i used the FTL_UnPacker to unpack and pack the needed .dat files. You can find it here [https://subsetgames.com/forum/viewtopic.php?t=2788](https://subsetgames.com/forum/viewtopic.php?t=2788).
Still i can use it to unpack the gamedata from the ftl.dat but the FTL_UnPacker was written for the first FTL Edition and not for the Advanced Edition so i can't pack it again. It's because in the 1st Edition there were 2 .dat files named "data.dat"[included "data" folder] and "resource.dat" [included "audio", "fonts" and"img" folders].
In GOG's Advanced Edition there's only one .dat file named "ftl.dat". Now the ftl.dat includes all gamedata folders named "audio", "data", "fonts" and "img". Before it was seperated in the 2 .dat files. Oh and i searched the whole www and couldn't find any up to date Un/Packer for FTL Advanced.

Here's a screenshot from the FTLUnPacker's message when i try to pack all folders. 

The FTL_UnPacker.jar was written in Java. There's no source code available. I tried to contact the programmer Didero but last time he was seen in the forum was in December 2012.

I'm not a programmer so i have problems to change the code. First i tried with Visual Studio but the program always told me there are bugs in the code. Then i decompiled the .class files within the .jar file with the Bytecode Viewer but there are several problems with compiling again. I tried several compilers. For me JD-GUI seems to be work best but i always get this error message:


Error compiling class: ftl/unpacker/FTLEditor
Keep in mind most decompilers cannot produce compilable classes
java.lang.Exception: 
Error:
Note: C:\Users\xxxxxxxxxxx\.Bytecode-Viewer\bcv_temp\tempXUxHFmIJukuX\ftl\unpacker\FTLEditor.java uses unchecked or unsafe operations.
Note: Recompile with -Xlint:unchecked for details.
1 error

Exit Value is 1
at the.bytecode.club.bytecodeviewer.compilers.JavaCompiler.compile(JavaCompiler.java:113)
at the.bytecode.club.bytecodeviewer.BytecodeViewer.compile(BytecodeViewer.java:792)
at the.bytecode.club.bytecodeviewer.gui.MainViewerGUI$14$1.run(MainViewerGUI.java:868)


I know i had to uncheck the Xlint option to solve this problem but within the Bytecode Viewer i cannot set any compiler options and i don't know how or if it's possible to set this anywhere in the Java folders.

I'm really going crazy with this and i hope someone can help me in any way!!!!! Maybe someone knows how to code Java and can do this for me?? For every help i'm thankful!

Regards happy
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2018-06-26T14:25:39+00:00
- Post Title: FTL Advanced Edition Packer/Unpacker HELP!!!!!

Use [Slipstream Mod Manager 1.9.1](https://subsetgames.com/forum/viewtopic.php?t=17102)
## Post #3
- Username: happypommes
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jun 26, 2018 7:41 pm
- Post datetime: 2018-06-26T15:23:42+00:00
- Post Title: FTL Advanced Edition Packer/Unpacker HELP!!!!!

I know and tried Slipstream's Mod Manager but how can i pack all needed folders into the ftl.dat with it??
## Post #4
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2018-06-28T14:25:05+00:00
- Post Title: FTL Advanced Edition Packer/Unpacker HELP!!!!!

Make a mod. And use Slipstream Manager to patch ftl.dat file with.

Read "usage" [here](https://subsetgames.com/forum/viewtopic.php?f=12&t=17102).
## Post #5
- Username: happypommes
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jun 26, 2018 7:41 pm
- Post datetime: 2018-06-28T17:24:28+00:00
- Post Title: FTL Advanced Edition Packer/Unpacker HELP!!!!!

I solved the problem with the java code and i tried SlipstreamModManager again and it's working now!   

Thx for your help!!!!!
