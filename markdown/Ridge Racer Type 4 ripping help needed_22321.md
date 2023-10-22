## Post #1
- Username: GuillermoTell
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jun 25, 2020 9:42 pm
- Post datetime: 2020-06-25T17:12:41+00:00
- Post Title: Ridge Racer Type 4 ripping help needed

Hi guys,
I'm new here and in game modding in general. I've been trying to rip Ridge Racer Type 4 resources but I feel a bit lost.   If this thread belongs to another forum, please, tell me so I can move it.

First, I was able to get the main game files from the USA version, they are:
-FILE.DAT: PSX boot?
-R4.BIN: resources?
-R4.STR: video files?
-SLUS_007.97: PSX title id?
-SYSTEM.CNF: PSX boot config?

From what I've figured out, the two last ones are needed by the PSX to run the game, R4.STR looks like a video file, and the interesting resources are located at R4.BIN.

In R4.BIN I've found the standard TIM textures used by the game, thanks to PSXPrev, and some car name references.

From my ignorance, it looks like there's no filesystem, just all the files attached together. I've made a simple Python script and the car names matched the following number of times:
ANTILOPE : 9
AVERSE : 8
BATAILLE : 25
DIRIGEANT : 24
ECUREUIL : 6
ESPION : 9
LICORNE : 8
MEGERE : 24
PROPHETIE : 33
SORCIERE : 8
SUPERNOVA : 8
AQUILA : 9
BISONTE : 24
CAVALIERE : 8
ESTASI : 8
FATALITA : 24
INFINITO : 8
PROMESSA : 34
REGALO : 25
RONDINE : 9
SQUALO : 8
VULCANO : 5
BONFIRE : 32
CATARACT : 8
COLLEAGUE : 8
COMRADE : 8
DETECTOR : 24
IGNITION : 8
NIGHTMARE : 6
OFFICER : 24
RECKLESS : 8
TAMER : 8
WISDOM : 24
AMBITIOUS : 32
CAPITAL : 8
COWBOY : 8
DECISION : 8
DESTROYER : 8
RUMOR : 24
STARLIGHT : 8
TERRIFIC : 8
TROOP : 24
UTOPIA : 6
WILDBOAR : 24

So, it looks like there's no compression. No track matches. I'm not sure about attaching the file, it may be against the forum rules.
Thanks.
## Post #2
- Username: GuillermoTell
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jun 25, 2020 9:42 pm
- Post datetime: 2020-06-28T00:43:59+00:00
- Post Title: Ridge Racer Type 4 ripping help needed

Update!
I noticed the sector info was still inside the data.  
I wrote a simple Python script and now everything is properly clean.
All the textures are nice and sharp.  
Now, I'm having a look at the car models, do you think the one in the picture may be the Ecureuil?   
Thanks.
Note: I tried to attach the file, but the website says is too large (6MB)   I'll try to upload it somewhere else.
[R4_cleaned.BIN_Sun_Jun_28_03-38-47_2020.png](https://xentaxbackup.github.io/file/18386_R4_cleaned.BIN_Sun_Jun_28_03-38-47_2020.png)
## Post #3
- Username: GuillermoTell
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jun 25, 2020 9:42 pm
- Post datetime: 2020-06-28T13:21:40+00:00
- Post Title: Ridge Racer Type 4 ripping help needed

For those who want to have a look, you can find attached a sample of a chunk that contains car code, in this case, Promessa. As an interesting thing, all of them are 0xB800 in size. I'm sure at least the vertices are inside it.

More info:
-Vertices:
--Count: 290? (measured by trial and error)
--Start: 0x236c
--Padding: 2
-Name:
--Name: PROMESSA
--Start: 0x20d

Looks like the data following the vertices are normals, but I'm not sure about it.

Thanks.
[Promessa.7z](https://xentaxbackup.github.io/file/18393_Promessa.7z)
