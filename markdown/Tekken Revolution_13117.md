## Post #1
- Username: kubaork
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jul 26, 2015 6:25 pm
- Post datetime: 2015-07-26T10:34:40+00:00
- Post Title: Tekken Revolution

Hey! I saw some TR models ripped from game but I can't find tutorial on how to extract game files.
I have heard that TR models are the same as TTT2 models (format).
I got pkg file of 1.00 version of game (Japan version, ID: NPJB00404) and in usrdir i have *.psarc files.
I downloaded plugin for Total Commander and in every *.psarc file there are many *.dat files and one idmap.txt file.
I don't know what can i make with *.dat files. Anybody know what can I do?
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2015-07-26T20:40:45+00:00
- Post Title: Tekken Revolution

Steven's Gas Machine

google it
## Post #3
- Username: kubaork
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jul 26, 2015 6:25 pm
- Post datetime: 2015-07-27T21:10:57+00:00
- Post Title: Tekken Revolution

Ohh thanks!   
But i realized that ripping model is SOO HARD :/
Maybe I am doing something wrong, but ".smc" files doesn't load textures when I am loading it to blender.
I tried to read this (*.smc) file and i noticed some ".dds". I tried to add them manually to mesh in blender but... wow. It looks like tekken normal maps are green and red    I can't find blue channel. Maybe it's different normal mapping method. 

I think that ripping models isn't for me  .
## Post #4
- Username: kubaork
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jul 26, 2015 6:25 pm
- Post datetime: 2015-07-28T09:52:55+00:00
- Post Title: Tekken Revolution

For those, who want's to know how tekken normal maps works... 
In noesis there are texture images and green texture images. Green texture images contains Green and Alpha channel.
Green channel is a normal map green channel, but alpha channel is normal map red channel. There isn't blue channel, so you can fill layer with 100% blue color and SUM all R, G, B layers and yeah... you have normal map
