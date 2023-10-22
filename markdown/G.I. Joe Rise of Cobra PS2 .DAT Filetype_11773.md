## Post #1
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2014-08-11T19:59:07+00:00
- Post Title: G.I. Joe Rise of Cobra PS2 .DAT Filetype

Using the QuickBMS script for this game I was able to extract all the files from the DFU file I had, now I'm left with . DAT, .18A, and .EVE files. I figure the .DAT files being the largest might be the ones containing the 3D model. They don't have any specific file names so no idea what the model is until you open the DAT file. And Noesis doesn't work with it. Although it might if a script is modified. 
Here's a sample if someone can take a crack at it. 
[https://www.sendspace.com/file/ne78gv](https://www.sendspace.com/file/ne78gv)

If you can convert the files and want to use any of these for game mod (GMod, etc.) purposes have at it. Here's everything in one big Zip folder. 
[https://www.sendspace.com/file/xnb175](https://www.sendspace.com/file/xnb175)
## Post #2
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2014-08-12T20:03:29+00:00
- Post Title: G.I. Joe Rise of Cobra PS2 .DAT Filetype

Well nothing I've tried has worked, I give up for now. The best info I've found is that the DAT is in hex, while what I am trying to open and convert it to in OBJ which is Ascii. And I don't understand how to use the Hex2OBJ program that's on here.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-08-13T20:32:27+00:00
- Post Title: G.I. Joe Rise of Cobra PS2 .DAT Filetype

most of the data in 0000003a.dat seems to be textures. It's a rather big file so you have to separate the textures from the model data (using TextureFinder or a similar tool.)
You need to invest some time to get results. This looks as if it were some kind of map:



mapE478F0.JPG (114.55 KiB) Viewed 128 times



btw: "separate" means just to define the start/stop addresses of the textures. May turn into wild guessing.
## Post #4
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2014-08-14T23:15:42+00:00
- Post Title: G.I. Joe Rise of Cobra PS2 .DAT Filetype

Yeah that's probably a map, trying to find the Accelerator Suit in the game files. But like I mentioned before I hate trying to use that Hex2OBJ program. Maybe that program needs a new version where it automatically finds the values for you.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-08-15T10:52:58+00:00
- Post Title: G.I. Joe Rise of Cobra PS2 .DAT Filetype

Nope, Hex2obj was written to help noobs to analyze simple models and for my understanding it fullfills these needs
(maybe not perfectly)
If it comes to more complex files such as these PS2 .DAT files "you need to invest some time to get results".
If you hate this, well, then you'll need to find someone who is willing to do this nasty analysing part for you. Good luck.
## Post #6
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2014-08-16T00:51:26+00:00
- Post Title: G.I. Joe Rise of Cobra PS2 .DAT Filetype

What I'm wondering is that if the files are DAT, how hard would it be to alter a script in Noesis because there are 1 or 2 game formats that are for DAT files, but they won't open these. I've seen someone before where he altered a script and was able to view and extract the model.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-08-16T16:01:39+00:00
- Post Title: G.I. Joe Rise of Cobra PS2 .DAT Filetype

If the games are using the same game engine it may work; mostly it doesn't.

BTW: Accelerator Suit, most likely it's not to be found in mega bytes sized .dat files.
It's just a guess but there might be seperate model files.
## Post #8
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2014-08-21T17:15:11+00:00
- Post Title: G.I. Joe Rise of Cobra PS2 .DAT Filetype

The extension of a file is just a given name it does not determine what the file is. You could rename the file from .dat to .txt and open it in a notepad but its not going to show right :/

Same in this case, no idea whats inside the extension doesnt really mean anything to us

And hex2obj might further confuse newcomers, they would have 0 technical understanding and just expect to open a file and go... Which will never be the case
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-08-21T18:12:17+00:00
- Post Title: G.I. Joe Rise of Cobra PS2 .DAT Filetype

> Reply from mariokart64n
>
> And hex2obj might further confuse newcomers, they would have 0 technical understanding and just expect to open a file and go... Which will never be the casewell, it's made for noobs.
But it is not made for noobs, who don't read the tutorial.  

(I will place this phrase in the next version's intro -if I don't forget to remember...)

edit: well, the intro says: "Use the short tutorial to get a clue on how to proceed."
I'm not sorry for guys who don't follow the rules...
