## Post #1
- Username: tigershop
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Nov 25, 2009 9:03 pm
- Post datetime: 2010-05-25T04:38:21+00:00
- Post Title: Need A Tool To Repack....., *.xwb files

Hi there!!!

I need a toll to repack some files into a *.xwb binary.
I used "unxwb.exe" from "Luigi Auriemma"  to extract the audiofiles from the game Powerdrome.

Now I changed the music and I want to put the music back into the music.xwb



Is there any tool to do this?
## Post #2
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2010-08-03T13:15:01+00:00
- Post Title: Need A Tool To Repack....., *.xwb files

> Reply from tigershop
>
> Hi there!!!

I need a toll to repack some files into a *.xwb binary.
I used "unxwb.exe" from "Luigi Auriemma"  to extract the audiofiles from the game Powerdrome.

Now I changed the music and I want to put the music back into the music.xwb
I don't know if there is a tool that puts back waves into an existing wavebank. But you can create a new wavebank (this has to have the same name, of course) using XACT. XACT is part of the DirectX SDK and you can download it from Microsoft - it's THE tool that is used by game designers in order to create the .xsb/.xwb files. But you have to be aware of two things:
1) you have to know, which tool version and file format version your .xwb file was created with. I think, unxwb tells you this information. If not, just use a hex editor: the .xwb files start with the string "WBND", followed by the tool version (4 Bytes in LittleEndian Order), followed by the file format version (again 4 Bytes in LittleEndian).
Then you have to download the particular DirectX SDK version, that creates the .xwbs with your tool & file format version (i.e. the DirectX SDK version, Powerdrome was made with). The only hint I can give you is:
XACT from [DirectX SDK, March 2009](http://www.microsoft.com/downloads/details.aspx?FamilyID=24a541d6-0486-4453-8641-1eee9e21b282&displaylang=en) creates .xwbs with tool version=45 and file format version=43 (I guess, you'll need an earlier version of DirectX SDK).
2) When you create your wavebank with XACT: 
-don't try to create a sound bank, just create a new project and 'your' wavebank (right-click on Wavebanks->New Wavebank)
-when you insert your waves (just use drag and drop) into your wavebank, they have to be inserted in the same order as in the original .xwb (otherwise the related .xsb won't find them). This of course means, you have to insert ALL waves that were in the original .xwb, not just the ones you changed.

Good luck  

PS: Sorry for my English
