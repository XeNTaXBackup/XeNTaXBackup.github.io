## Post #1
- Username: DBzera
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 10, 2022 8:44 pm
- Post datetime: 2022-04-11T17:39:23+00:00
- Post Title: Reverse engineering on Bully: Scholarship Edition .XWB files

According to [this previous topic](https://forum.xentax.com/viewtopic.php?f=17&t=21633&p=159327&hilit=bully#p159327), I need to find out whats the XACT version and file format version that was used originally to create these .xwb files. 

How can I know that information? I've succeeded changing musics to other existent musics in game (ex. I've changed the menu theme to kart race theme and stuff) just duplicating and replacing the files that I want for the original ones (just worked after I done that to both .xwb and .xsb files) now I'm on my way to replace some musics in game to my custom tracks.

Thanks in advance.
## Post #2
- Username: DBzera
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-04-11T22:20:55+00:00
- Post Title: Reverse engineering on Bully: Scholarship Edition .XWB files

I did a little research and it seems that Bully SE v1.2 for PC uses tool_version=44 and format_version=42
which is exact match for XACT from DirectX SDK 2008 August (available on web archive).

Check also this article [http://wiki.xentax.com/index.php/XACT_XWB_XSB_XGS_Audio](http://wiki.xentax.com/index.php/XACT_XWB_XSB_XGS_Audio) for more info.
I have made a lot of changes there, because it was very outdated.
(More updates will appear soon)
## Post #3
- Username: DBzera
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 10, 2022 8:44 pm
- Post datetime: 2022-04-13T02:27:05+00:00
- Post Title: Reverse engineering on Bully: Scholarship Edition .XWB files

Thanks ikskoks for your answer, it helped me a lot! But there are some things that I can't understand... Can you help me get these information that are listed in the article from the original files (like soundbank name, cues and stuff)? I've readed it and tried to find the information inside file's hex and... I didn't get anywhere. 

I've also looked for some tutorials to help me understand better but got a little confused. Maybe you could indicate some article or help me find these important informations inside the files? I'll attach both of them if you want to take a look at it.

[https://drive.google.com/file/d/1lhrCuo ... sp=sharing](https://drive.google.com/file/d/1lhrCuoCbOrR2bkpHrW1AEIYan2aUxtct/view?usp=sharing)

Thanks in advance!
## Post #4
- Username: DBzera
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-04-13T21:09:25+00:00
- Post Title: Reverse engineering on Bully: Scholarship Edition .XWB files

Well, file format on the wiki is still a little outdated.   (It was originally based on version 3, now the newest one I could find is version 46/44)
This article was created in 2005 and was not properly maintained since then.
A lot of has changed, like - it is no longer only for XBOX. Since 2006 it is shared with DirectX SDK,
so file format is used in some PC games as well.

I'll try my best to update this info in the upcoming days, 
but in the meantime you can just use a XWBTool source code for reference:
[https://github.com/microsoft/DirectXTK/ ... in/XWBTool](https://github.com/microsoft/DirectXTK/tree/main/XWBTool)
[https://github.com/microsoft/DirectXTK/ ... Reader.cpp](https://github.com/microsoft/DirectXTK/blob/main/Audio/WaveBankReader.cpp)

and just debug the app in Visual Studio to get proper values in real-time.


By the way, why do you need to parse data manually?
If you'll get correct SDK version (XACT version), you will be able to create Wave Banks and Sound Banks with XACT
and probably replace them in game without issues. 


Also, if you need more tutorials to learn RE, you can check this topic [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)
## Post #5
- Username: DBzera
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 10, 2022 8:44 pm
- Post datetime: 2022-04-14T00:08:40+00:00
- Post Title: Reverse engineering on Bully: Scholarship Edition .XWB files

I think the problem now is really the .xsb file, since I’ve created a new wavebank and soundbank from XACT august 2008 like you said previously, and it didn’t worked.

When I replaced the menu song .xwb with another original .xwb from the game, it only worked when I replaced both .xwb and .xsb.

So I presume that, since i’ve done creating the two files from August 2008 DX SDK’ XACT and it didn’t work, the real problem now is really the way that .xwb is referenced inside .xsb.

I’m testing in many ways I can, but unfortunately by now, couldn’t succeeded
## Post #6
- Username: DBzera
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 10, 2022 8:44 pm
- Post datetime: 2022-04-15T04:36:36+00:00
- Post Title: Reverse engineering on Bully: Scholarship Edition .XWB files

Hello, I came back here because after a few months trying, I don't know what else to do.

Creating the two files directly from XACT August 2008 did not work. I tried comparing the hex values ​​of the two files (original and the one created by me) and I didn't get any useful information either.

About the DirectXTK reference links, I downloaded and tried to compile both tools using a C++ IDE but also to no avail.

I'm starting to disbelieve that modifying Bully's audio is really possible, even though I managed to get further than most who tried.

I'm begging you, please help me. If you who are reading this know of anything that can help us, we would be very grateful. So far, apparently, no one has been able to modify Bully's audios and those who have tried claim it's impossible (and I don't want to believe that).

In fact, maybe I didn't mention it, but these attempts to modify the songs are nothing more than tests for the real objective: to dub the entire game into another language.

If we can customize a song at all, we'll be able to modify the characters' lines and make that possible. If you are interested and know how to help us, please contact us through this topic.

Thanks in advance.
## Post #7
- Username: DBzera
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-04-15T22:18:13+00:00
- Post Title: Reverse engineering on Bully: Scholarship Edition .XWB files

> I'm begging you, please help me.
I'll try to help, but I can't promise that it will be successful...

> About the DirectXTK reference links, I downloaded and tried to compile both tools using a C++ IDE but also to no avail.
Which IDE did you use? It should work with Visual Studio 2022.
Edit: I've just checked it and XWBTool compiles just fine for me.

> Creating the two files directly from XACT August 2008 did not work.

What about creating new XWB file and leaving original XSB file untouched. Did you try that?

> When I replaced the menu song .xwb with another original .xwb from the game
What file exactly did you test? Can you tell me what is the name of this file and it's location?


Also, what version of the game do you have and on what platform (PC, Xbox etc.)?
## Post #8
- Username: DBzera
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Apr 10, 2022 8:44 pm
- Post datetime: 2022-04-15T22:55:17+00:00
- Post Title: Reverse engineering on Bully: Scholarship Edition .XWB files

> Which IDE did you use? It should work with Visual Studio 2022.
>
> Edit: I've just checked it and XWBTool compiles just fine for me.
I tried first with visual studio community 2022, but the IDE returns me a .lib other than a .exe for DirectXTK Audio. XWBTool works fine but, it just creates a wavebank, I want to read the original ones information.

> What about creating new XWB file and leaving original XSB file untouched. Did you try that?
Yes, and it didn't work either

> What file exactly did you test? Can you tell me what is the name of this file and it's location?
I tested it with two songs, and it worked with both.

The menu theme (MS_Gobble) and the walking theme (MS_RunningLow). I needed to replace the XWB and XSB files, replacing just the XWB didn't work. They are inside "steamapps\common\Bully Scholarship Edition\audio\PLAYLIST\Music.bin". I tested it several times, with several different files. As long as the XWB file is smaller or equal in byte size to the file you want to replace, it will work.

> Also, what version of the game do you have and on what platform (PC, Xbox etc.)?
I'm running Bully Scholarship Edition (PC steam version, patch v1.200).

If you want, we can talk somewhere else to make it easier, my twitter is @dbzera if you want to contact me

Thanks!
## Post #9
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-04-20T21:23:20+00:00
- Post Title: Reverse engineering on Bully: Scholarship Edition .XWB files

Try this:

# AUDIO EXTRACT STEPS #
1. Download quickbms [http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)
2. Download this script [viewtopic.php?p=41076#p41076](https://forum.xentax.com/viewtopic.php?p=41076#p41076)
and save it as "Bully_SE_BIN_LST_script.bms".
3. Use the script with quickbms to unpack data from Music.bin file from \Bully Scholarship Edition\audio\PLAYLIST directory.
4. Find file "MS_Gobble.xwb" in the output directory.
5. Download towav [https://web.archive.org/web/20220411181 ... /towav.zip](https://web.archive.org/web/20220411181454/http://namgorf.com/towav.zip)
6. Put "MS_Gobble.xwb" file in towav's directory and run towav to get original WAV file


# AUDIO IMPORT STEPS #
1. Check your extracted "MS_Gobble.xwb" file in hex editor for tool version and format version.
For Bully SE (PC) v1.2 it will be tool_version=44 and format_version=42
2. Go to the SDK compatibility table on the wiki [http://wiki.xentax.com/index.php/XACT_X ... lity_Table](http://wiki.xentax.com/index.php/XACT_XWB_XSB_XGS_Audio#SDK_Compatibility_Table)
3. Check your SDK version. For Bully it will be DirectX SDK 2008 August.
4. Download proper SDK version (all versions are available on webarchive).
5. Go to C:\Program Files (x86)\Microsoft DirectX SDK (August 2008)\Utilities\bin\x86\Xact3.exe and run XACT.
6. In XACT click File > New Project
7. Click on WaveBanks, then "New Wave Banks".
8. Rename your wave bank to "MS_Gobble".
9. Add new wave to wave bank. "Insert Wave Files" or CTRL+W. In my example I've used this song [https://www2.cs.uic.edu/~i101/SoundFile ... Band60.wav](https://www2.cs.uic.edu/~i101/SoundFiles/CantinaBand60.wav)
10. Rename your wave file to "MS_Gobble".
11. Change wave type to "Streaming".
12. Check "Friendly Names" checkbox.
13. Click File > Save project.
14. Click File > Build.
15. Go to "Win" directory in your project directory. Here you should have "MS_Gobble.xwb" file with your new music.
16. Copy your NEW file to quickbms output directory.
17. Use "reimport.bat" script from quickbms to reimport your new file to Music.bin archive. (REIMPORT ONLY NEW XWB FILE!!! LEAVE ORIGINAL XSB FILE AS IT IS)
18. Replace Music.bin file in \Bully Scholarship Edition\audio\PLAYLIST directory.
19. Test your changes in game. Music should be now replaced with your custom WAV file. 


This method works fine for me, new music plays in the main menu. I've included also steps for extraction as it may be useful for other people reading this topic.
I'm sharing also my project files in case you need them for comparsion:
[https://drive.google.com/file/d/1PJekl- ... sp=sharing](https://drive.google.com/file/d/1PJekl-FvCtqzCXJA1VJtPLZPPBlVoF42/view?usp=sharing)


I may include shorter version of this tutorial to the wiki.
