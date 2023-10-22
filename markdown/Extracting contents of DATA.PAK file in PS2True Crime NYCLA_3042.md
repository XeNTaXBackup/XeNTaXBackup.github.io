## Post #1
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2008-05-21T07:12:34+00:00
- Post Title: Extracting contents of DATA.PAK file in PS2True Crime NYC/LA

Does anyone know of a way to extract the contents of the DATA.PAK file in the games True Crime New York City,  and Streets Of LA (2 games) ive tried everything a bunch of pak file editor programs and both cube media player (too slow) and game extractor (too difficult to use and creates a file with an empty footer that hangs MFAudio) is there some other tool or program that I can use I do have the free version of the multiex commander program but i dont have the right update or something or my game isnt supported it is the DATA.PAK file from the PS2 versions of the games true crime NYC and streets of LA. this file i believe contains everything in the game like the music which im after and all the sound effects graphics and other stuff like cut scenes i am after all these things inside this file is there any way i can extract the contents of this file and save what im after i could either post this file somewhere but its like 2 GB or you can see this file on a copy of true crime NY or LA (doesnt matter which game) put the game into your pc and look at the files on the disc the DATA.PAK file is the one im talking about. does anyone know how to extract the contents of this file? thanks for your help.
## Post #2
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2008-06-23T17:46:12+00:00
- Post Title: Extracting contents of DATA.PAK file in PS2True Crime NYC/LA

I got this from another forum I posted to Mr mouse i hope this helps any
Re: extract audio data from PS2 game
Question for all, does anyone know how to extract the music tracks from the true crime series of games like true crime streets of LA and New York city, here is what i see when i put the disc in my pc

SLUS_211.06  <-- some sort of Game ID but i dunno

TC2.elf  <-- Dunno what this is, TC2 thats true crime 2, possibly equivalent to a PC .EXE file

2 file folders:
modules 
slogan   <-- VAGs are in this folder  

(ive found alot of .VAG audio files in the slogan folder that play when you load the game after the luxoflux logo it plays a different one each time, Ive tried them all no music )

DATA.PAK  .PAK file (i think the music files are inside this file along with the game data, sounds, and MUSIC) <-- need to open this file and view/extract its contents

.pss Movie file (the spinning activision logo video, I already have this)

and this file called system but it shows up in windows as a speed dial shortcut
## Post #3
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2008-06-24T01:00:38+00:00
- Post Title: Extracting contents of DATA.PAK file in PS2True Crime NYC/LA

This may help anyone trying to also do this

Ive sucessfully opened the DATA.PAK file in true crime LA. youll need to head over to alucard.cc and then go to downloads and youll need to register(Free) and after you log in go to downloads then ps2 ripkits and scroll down till you see true crime streets of LA ripkits PAL/UK, download and run this file and then copy the DATA.PAK file to the folder where you have the program in and then run the little true crime streets of LA icon and it will give you 2 options extract, and rebuild hit extract and then i think tell it where your data.pak file is and if its already doing this let it do its thing and do something else and when its done extracting go to the folder where you have the program in and look for a folder named Ext look thru there and the music is in the sounds folder, use the vice city radio decoder to extract the songs, this is a command line prog so copy the .VB files into a folder on your c drive like c:\decode and then put in the following: decode -r 44100 xxx.VB (where xxx is the name of the .vb  file you are decoding. repeat this for the other files and its a bit of extra work, a batch file would help with this but im terrible at programming so feel free to experiment with that and write to this forum if you have any luck

I hope this post is in the right place but it seems like i've solved my own problem, well time to rip the true crime NY music now

EDIT: The software mentioned in this post no longer works for some reason it says Class not registered and it closes so it's back to square one. and Game extractor cannot open this archive it just spits out 3-4 files with no extension. ADPCM Player can detect the audio files inside the DATA.PAK but the 2 audio channels are offset from each other so one channel is behind the other.
## Post #4
- Username: Paw Inc
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 29, 2019 10:00 pm
- Post datetime: 2019-06-29T14:32:25+00:00
- Post Title: Extracting contents of DATA.PAK file in PS2True Crime NYC/LA

I would recommend Game Extractor. When I extracted the game. But it wasn't the game you are talking about but maybe it will work. It extracted everything. So I recommend it. have fun extracting PS2True Crime NYC/LA! I'm sure it will extract DATA.PAK
