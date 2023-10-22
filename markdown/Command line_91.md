## Post #1
- Username: Mabus
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jan 17, 2003 9:35 pm
- Post datetime: 2003-01-17T13:39:54+00:00
- Post Title: Command line

Greetings !

First, Id like to say congratulations on such a great program !

However, there is one feature I am missing.. command line support.

IE, I would like to do:
multiex.exe -create=pak <SOURCEDIR> <TARGET>
Where <sourcedir> would be something like "c:\mypak", and <target> would be mypak.pak. This command would then create a Quake 1 PAK archive containing all the files in <SOURCEDIR> and recursive (perhaps a '-r' switch or something, for recursive mode).

Thank you,
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-01-18T17:25:45+00:00
- Post Title: Command line

AH yes, that would be very great indeed. Exactly my idea too for future releases of MultiEx Commander. However, this would require a new MultiEx engine, as the one (MultiEx3) that is in there now handles scripted files depicting the file format in such as way that it cannot actualy create new archives from scratch. 
The MultiEx3 script is a much enhanced version of the 16-bit MultiEx2 script and enables file importation into an existing archive. It does NOT unfortunately KNOW a format, it just knows how to process the script to open a specific format. I have started work some time ago on a new MultiEx4, that handles this formatting in a different way, so users could select files and create different archives from them, if they wanted a PAK file, it would do it, if they wanted a GRP BAR file, it would also do it. 
The major problem is that a lot of archives have much more information in the files than just the position and length of a specific resource that's saved in the archive. These are most of the time variables that the game needs to know, such as when to use the resource, if it is a sound file or other file, which character in the game is linked to this specific resource and when to use it. All of this can be found out, but it would require substantial knowledge of the game, and the archive format, and then , yes, a new MultiEx4. AND this would require a lot of time. This program is freeware, because it is coded in freetime. That means that it will be a lot of work for me, and would require a lot of freetime to lift the code to the next-generation of Massive Multiple Archive Format Handling, MAFFH, and still be able to add new formats on the fly by some kind of scripted process or standard format-code. I hope this makes sense. 
But you are absolutely right, the feature you ask for is very high on my to-do list, but still requires time.
