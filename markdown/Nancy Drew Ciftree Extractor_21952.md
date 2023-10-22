## Post #1
- Username: HuwMiller
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Mar 21, 2020 4:42 am
- Post datetime: 2020-04-01T01:02:51+00:00
- Post Title: Nancy Drew Ciftree Extractor

Hello!

I've been trying to find a program that I could use to extract the files from the Ciftree.DAT files found in the Nancy Drew PC games. I managed to find some programs to extract the files from games 18-32 in the series, but nothing that I've found can properly extract the Ciftree.DAT files for games 1-17. Someone created some source code ( [https://gitlab.com/ShimmerFairy/oldhertools](https://gitlab.com/ShimmerFairy/oldhertools) ) to create a program which can extract the files from Ciftree.DAT, but I don't have much knowledge about coding. If anyone could help me out with trying to extract the files or make a program which does that, I would be super grateful. I know another user made GOBREAD, but when I used that to extract the files, it wouldn't work for some games, and the games it did work on had all the files come out as .file file format.

If need be, here's a link to download the Ciftree.DAT for the first game: [https://www.dropbox.com/s/yu7f8idmw9bz8 ... e.dat?dl=0](https://www.dropbox.com/s/yu7f8idmw9bz837/CifTree.dat?dl=0)

Cheers to anyone who can help!
## Post #2
- Username: nancydrew
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 25, 2020 12:01 am
- Post datetime: 2020-05-24T20:00:56+00:00
- Post Title: Nancy Drew Ciftree Extractor

Let me give you an explanation of the various components and perhaps this will help you find what you are looking to find. Before I get into it though, which game were you able to get GOBREAD to extract individual .FILE files? When I run it against any of the old games I get a "file format unrecognized" error. 

Anyway, onto the explanation.

Overview

Depending on what you are trying to extract from the old Nancy Drew games determines where you need to look. There are seven main categories of data stored in the Nancy Drew games: Sound (all the sound effects and music score), Backgrounds (all of the room environments), Animations (cutscenes), Puzzle Overlays (any movable pieces in a puzzle are called 'overlays' in the game code), Character Dialogue Videos (the characters speaking), Interfaces (cursors, inventory items, etc), and Game Logic (the actual code for the game). 

Sound

Inside the CDSound folder you will typically find .HIS files (stands for Her Interactive Sound, I believe). These files are basically headless WAV audio files. You can use the Audacity program to play them. Simply use the Import > Raw File menu function. When imported they may need to be sped up or slowed down. In my experience, setting the speed to around 50% restores the correct speed.   

Backgrounds & Animations

Inside the CDVideo folder you will typically find .AVF files in the older games, which was a proprietary file format created by Wayne Sikes (programmer for Her Interactive in the early 2000s). To open these files (and export them) you can use AVFExt by puggsoy ([https://github.com/puggsoy/AVFExt/releases](https://github.com/puggsoy/AVFExt/releases)).    It works in most cases, although a few animated .AVF files would not export properly. If you want to read more about the file format check this out ([https://shimmerfairy.neocities.org/nd/ff_avf.html](https://shimmerfairy.neocities.org/nd/ff_avf.html))

Her Interactive switched to .BIK video files at some point and you can use Bink Video Player by RAD Games Tools ([http://www.radgametools.com/bnkdown.htm](http://www.radgametools.com/bnkdown.htm)) to view them. I imagine there are converters out there for this file type if you need them in another format. 

Puzzle Overlays, Character Dialogue, Interface, & Game Logic 

Now we get the what you asked, the CIFTree.DAT. This file contains puzzle overlay images (basically any movable object in a puzzle), character dialog animation videos, interface images, and the game logic.

Here's the problem: the format for the CIFTree.DAT changed with almost every game until around game #17 (I think). This means you need to analyze each game and write a separate algorithm for each one to decompile the CIFTree.DAT properly.   (You can read more about this here [https://shimmerfairy.neocities.org/nd/ff_ciftree.html](https://shimmerfairy.neocities.org/nd/ff_ciftree.html).) If you look at the source code to oldhertools ([https://gitlab.com/ShimmerFairy/oldhertools](https://gitlab.com/ShimmerFairy/oldhertools)) you can actually see the programmer wrote algorithms for game #1, #2, and #3. Since they didn't compile the program into a release it is up to the individual to handle that if they want to extract data from those games. Sadly, it does not appear algorithms have been distributed for the other older games.   

Since you mention you don't know how to code I assume you are looking for the puzzle overlays or character dialogue (the main image files not stored in the CDVideo folder). If that is the case, you can simply take a screenshot or video capture of the game and save it yourself.    I know that sounds terrible, but with these games "what you see is what you get". The original image files saved in the CIFTree.DAT have no more data or pixels than what is displayed to you on screen. 

I hope this was somewhat helpful even though it doesn't offer a solution to the CIFTree.DAT issue.

Also, in case anyone is wondering, I was never associated with Her Interactive and never worked on any of the projects. I just researched this enough to comment intelligently on the subject.
