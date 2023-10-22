## Post #1
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-10-14T09:19:09+00:00
- Post Title: MK vs DC Audio Files - xbox 360

Hi. I've been trying to view the audio files from this game. 

I've managed to extract the files from the "xxx" containers but I have no idea how to open them. The file extensions are "FmodDesignerProject" , "FmodEventParameter" , "FmodEvent" and "Package". The naming of the "FmodEvent" files lead me to believe that these are the sound files. 

I've downloaded an application called fmod designer but it cant seem to open any of these files. The application is looking for  fdp files but the game doesnt seem to contain this file. 

Anybody have any ideas???

Thanks in advance.
## Post #2
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-10-14T15:44:23+00:00
- Post Title: MK vs DC Audio Files - xbox 360

No need for FMOD Designer.

Load one of the XXX's into a hex editor. Scan for FSB4 strings. Extract all the fsb's in the xxx. Then, download a tool called ToWav by xplorer. I cannot link you to the tool itself, at the author's wishes. When you have it downloaded, place all the fsb's you extracted in the same folder as ToWav and run ConvAll.bat. After it is done converting, you should have a folder full of both the fsb's and the wav's. Should be pretty self explanatory from there on.
## Post #3
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-10-15T09:18:26+00:00
- Post Title: MK vs DC Audio Files - xbox 360

Awesome. Thanks a lot for your help, the program worked like a charm
