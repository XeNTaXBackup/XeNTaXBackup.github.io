## Post #1
- Username: 1jn14r
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jun 27, 2013 6:42 am
- Post datetime: 2015-06-12T22:53:01+00:00
- Post Title: Spyro WAD format

Now using  Kly_Men_COmpany aka aleksuskilm's SpyroWorld Viewer we can unpack the WAD files. Now when we unpack (using WAD extractor) we get a load of unknown files but using the appropriate script we can rip the 3d models and texture from some of these unkown files. Now here are some intersting things I've learnt by inspecting some of these files with a hex editor. This example below is using Spyro 1 NTSC

1,23
8,9,
10,12,14,16,18,20,22,24,26,28,30,32,34,36,38,40,42,44,46,48,50,52,54,56,58,60,62,64,66,68,70,72,74,76,78
82

40 unknown
62 known(3d models + texture)

All the numbered files above are the number of the files which are unknown the rest get unpacked into textures.

Now you see line 3 of the unknown files has a distinct pattern. Now from what I can tell these files are logic code for levels. How do I know this? When you extract the 3d objects and their textures you see they will start at 11 and go up in two's i.e. 11,13,15... My findings indicate that the logic file is before the objects file i.e. 10 is the logic for 11 and 12 is the logic for 13 etc. Now if you look at file 10 for example you will see it contains "baloonist" and stuff like "hop on spyro!". Then look at file 11 in the viewer. It's a homeworld, this also appears on all the files 1 before a homeworld. Also if you look at the file one before a speedway level, you will see it contains stuff like "course record" and "continue". All the other Spyro's also seem to support this theory that the logic is just before the model.

Now some of these what I think are logic files, are quite small. Some are like 40kb which isn't much. Maybe the files with textures in contain some logic as well. I may be wrong, my findings may be wrong.

Also file 3 contains SCUS info and some other unknown stuff.

[EDIT]
2 is start menu textures
would assume that 1 would handle the start screen loading games etc.
[/EDIT]

We are left with files 1,3,8,9,82. I think that maybe there is where all the game text is and maybe there is where the actual Spyro model is. Also it could contain all the other character models. If anyone could verify/or disprove my claims they will be welcome.

Also if possible could someone put me in contact with Kly_Men_COmpany aka aleksuskilm?

Thank you
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-06-13T14:19:42+00:00
- Post Title: Spyro WAD format

I'm slowly working on an Engine Clone for Spyro the Dragon in my free time that I get. I haven't yet fully looked into the files but those files you call "logic files" will just be mips assembly code which is pretty much useless for PCs.
## Post #3
- Username: 1jn14r
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jun 27, 2013 6:42 am
- Post datetime: 2015-06-13T18:50:06+00:00
- Post Title: Spyro WAD format

So we have to disassemble to see what's going on in these files? Hmmmm I'm not really interested in making the engine tbh, I'm just looking for 3d objects, strings and textures so I can mod the game    . But if someone is able disassemble and have a good look at the files it will help create an engine (for PC) which will be very similar to the original one (PS1). Also we will know how the games work and this will allow us to create awesome mods!!!  

(30 mins later) OK using Munch 1.0 and disassembling some of the files I now realise that disassembling is probably not the way to go, the best way would be to try and run the game using a debugger and seeing what files and resources it accesses. Trying to make sense out of assembly is too advanced for me. (well when it comes to game engines). I still think that being able to break down the psx engine will still help us even on the pc engine.
## Post #4
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-06-13T21:21:32+00:00
- Post Title: Spyro WAD format

> Reply from 1jn14r
>
> So we have to disassemble to see what's going on in these files? Hmmmm I'm not really interested in making the engine tbh, I'm just looking for 3d objects, strings and textures so I can mod the game    . But if someone is able disassemble and have a good look at the files it will help create an engine (for PC) which will be very similar to the original one (PS1). Also we will know how the games work and this will allow us to create awesome mods!!!  

(30 mins later) OK using Munch 1.0 and disassembling some of the files I now realise that disassembling is probably not the way to go, the best way would be to try and run the game using a debugger and seeing what files and resources it accesses. Trying to make sense out of assembly is too advanced for me. (well when it comes to game engines). I still think that being able to break down the psx engine will still help us even on the pc engine.

Fortunately, you won't need to touch those files to bring out the game assets. It's most likely gameplay/ai related code. Tomb Raider 3+ on the PS1 did something similar but only with AI.
## Post #5
- Username: 1jn14r
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jun 27, 2013 6:42 am
- Post datetime: 2015-06-14T15:33:42+00:00
- Post Title: Spyro WAD format

Yeah all the AI will be handled in those files, but it still leaves a lot of mysteries about where the hell everything is stored in that game and what formats it uses. So far we can only rip the 3d worlds and textures. I'm certain that Spyro's model and other character models exist in those files, except I don't think anyone has been able to rip a character model from any of the PS1 Spyro games? The only place it could be is in those WAD files, that's why I'm trying to decrypt them. I'm sure that Spyro's animations and stuff have to be stored somewhere in there.

Also if we were able to extract all of the "useful" stuff (animations textures etc) and be left with the assembly code which dictates the engine and logic etc, we would be able to have a good guess and maybe even work out how the engine is implemented to the T. It's just that if we're going to make an engine I want it to be as close to the original as we can get it. If it turns out that it's impossible then I don't mind either!

(EDIT)

well it seems Spyro doesn't use normal 3d models for it's characters. They are just part of the huge WAD file, also I read that spyro uses vertexes with a weird format. It's not going to be easy to rip models from Spyro
