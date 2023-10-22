## Post #1
- Username: railroads
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jan 30, 2018 6:39 am
- Post datetime: 2018-02-04T20:43:14+00:00
- Post Title: Need help opening .texture file with heightmaps inside

Hello! Need some help opening up a .texture file. From what I have read on this and other forums, the .texture extension can be another file, like .dds etc.

I know what's inside. Its a heightmap. The problem is, I dont know how to extract it. I have used the textureFinder 2.1 and with 16x4=48+16 width 2049 I get a clear image of what's inside. and with the help of that tool, i manage to see the heightmap, but dont know how to convert and extract the map inside. 


I'll upload two such heightmaps (.textures) files and, and hope someone can help me out. The 7zip file is 6MB so I cant upload here, I throw in a link: 

[http://s000.tinyupload.com/index.php?fi ... 3767716452](http://s000.tinyupload.com/index.php?file_id=52939561533767716452)
## Post #2
- Username: railroads
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jan 30, 2018 6:39 am
- Post datetime: 2018-02-06T01:42:26+00:00
- Post Title: Need help opening .texture file with heightmaps inside

I have tried reading the file and looked at the header, but I cant get anything usefull out of it. Maybe the file is encrypted or obfuscated. I dont know, but it's strange I can view it using textureFinder. Would love to get a comment on this
## Post #3
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-02-06T03:57:01+00:00
- Post Title: Need help opening .texture file with heightmaps inside

it's a 2049 x 2049 x 16 bit greyscale.

edit: stupid mistake i made. 

i tried and failed to export it to full precision dds. and i got no viewer that supports whether dx10 or 16 bit per channel. microshit (visual studio) doesn't even wanna open their own f*cking format.  16-bit grey is hard to display anyway.

scripts are for basic rgb dds that i got open in gimp. it shows up just as 8-bit grey tho. lost precision. the dx10 seems a useless export since i can't seem to open it, but it's inclu. it should give you more precision in case you can some make use of it.
[halfbaked.rar](https://xentaxbackup.github.io/file/13886_halfbaked.rar)
## Post #4
- Username: railroads
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jan 30, 2018 6:39 am
- Post datetime: 2018-02-06T22:46:32+00:00
- Post Title: Need help opening .texture file with heightmaps inside

Thank you for the reply. Very nice to see someone trying to help 

Realy hate this kind of files.

The exact picture that is inside the file is not so important, because I know how it look like. I even got the .png formate of the files.

My goal is finding a way i can "pack" other images so they will get the same formate, and then can be loaded by the game. This files is used to draw the map for the game Railway Empire. It's more then just this file, but i thought it would be enough starting with this heightmaps.

So the engine for the game makes the game world everytime i runs, based on the image inside the files. All other aspects of the map/game world is added later, and I know how to handle that. So this is just the last step. I need to figure out what fileformate this is so i can convert my own heightmaps into the game.

When i cant treat it like a normal jpeg, bit or png, Im kinda stuck with my noob skills. 
I'm using 1-2 hours every day trying to get this to work. If i cant make it, its not the end of the world. But would be awesome to get it to work some how. 

If you have anymore usefull info to share, I would be very happy
## Post #5
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-02-07T00:21:14+00:00
- Post Title: Need help opening .texture file with heightmaps inside

okay. a rail world? you wanna reimport things? i'm not able todo that tho. i can't do guessed headers. i could code a 8 to 16 bit 'extender' shift, but i have no clue how the engine would scale that height. so...

nah. sorry. end of the line.
## Post #6
- Username: railroads
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jan 30, 2018 6:39 am
- Post datetime: 2018-02-07T18:00:14+00:00
- Post Title: Need help opening .texture file with heightmaps inside

> Reply from episoder
>
> okay. a rail world? you wanna reimport things? i'm not able todo that tho. i can't do guessed headers. i could code a 8 to 16 bit 'extender' shift, but i have no clue how the engine would scale that height. so...

nah. sorry. end of the line.

Yes, the main objective is to make new maps/game worlds for the game. The engine use this files to generate the world. But since I dont know what file extension/formate the file is, Im stuck.
But again, thx for trying to help. I really appreciate it
