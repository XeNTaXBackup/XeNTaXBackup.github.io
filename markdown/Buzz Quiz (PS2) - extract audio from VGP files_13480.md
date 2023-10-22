## Post #1
- Username: luisnrkl
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 29, 2015 9:00 am
- Post datetime: 2015-10-30T20:15:16+00:00
- Post Title: Buzz Quiz (PS2) - extract audio from VGP files

Hi guys,

I'm trying to extract the audio from the Buzz games. 

The audio for the questions are in *.vgp format, for which i can't find any information.

Does anyone know how to decode these files?

Thanks,
## Post #2
- Username: AnonMouseTrap
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 06, 2022 2:59 am
- Post datetime: 2022-10-05T19:01:34+00:00
- Post Title: Buzz Quiz (PS2) - extract audio from VGP files

Did you ever work this out? 

Currently looking to mod this game updating the questions etc.
## Post #3
- Username: SpaceCoyote
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 10, 2022 4:12 am
- Post datetime: 2022-10-09T20:16:50+00:00
- Post Title: Buzz Quiz (PS2) - extract audio from VGP files

I am also looking into the game, from what I've worked out

 - It's running on Renderware
 - PAK files are easy enough as you can open them in any WinRAR
 - The game scripts are LUA based I think
 - Most of the text strings are in plain text
 - Videos are PSS which I think has a tool out there to open or convert


Kind struggling to make any good progress though in terms of changing content
## Post #4
- Username: SpaceCoyote
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 10, 2022 4:12 am
- Post datetime: 2022-10-31T21:59:40+00:00
- Post Title: Buzz Quiz (PS2) - extract audio from VGP files

Update on this:

Game Scripts- .CLU - Compiled LUA 5 and 5.1 from the mega quiz onwards - Slim chance they can be decompiled, there are decompilers out there but they don't get very far with these
3D Models & Animations - .RP2 - Output using tool included with the RenderWare SDK, most likely made originally in either maya or 3DSMax,  according to the documentation, it should be possible to re-import them using one of the tools.
Contestant Sounds, Music clips & background music - .VGP - No idea on these
Buzzer sounds, other sound effects - .VAG - Can be converted using a couple different tools
Textures - .TEX .UVS - No idea on these
Intro/Outro Videos - .PSS - There are a few utilities around for viewing and ripping PSS files
In-game Stage Screen Videos - .RSV - No Idea here
Game menu text - .str - Plain text


This applies to the majority of the games, if not all. Except for the Junior games which have vastly different structure and formats.

For some reason, only the music quiz has a list of hundreds of questions and possible answers in a file, in plain text. Can't remember which one, but I did find a script for a debug menu.
## Post #5
- Username: zeetu
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 24, 2022 6:03 pm
- Post datetime: 2022-12-24T13:35:22+00:00
- Post Title: Buzz Quiz (PS2) - extract audio from VGP files

Any new findings here?
