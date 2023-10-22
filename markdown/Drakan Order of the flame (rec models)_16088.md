## Post #1
- Username: olli9000
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Dec 02, 2015 12:04 am
- Post datetime: 2017-04-03T22:20:44+00:00
- Post Title: Drakan Order of the flame (rec models)

Hey everyone,
iam trying to extract or ripping 3d models of drakan order of the flame, but there are some problems to solve it.
Drakan has 2 different filetypes like static objects (.reo) and character models (.rec). There is an official level editor, who can export the .reo models without problems.
But the .rec files not. The menu items in the program is grey and deactivate for rec models.
So, i have tried to rip the models, cause in level editor there is a 3d view to preview the model. I used 3d Ripper DX for that, cause its for directX 6, too. Yes, the game is from 1999   
I tried also with ninja ripper and 3dvia tools, but the results are terrible.

3d Ripper dx can rip it with textures from the level editor, but without backfaces. So the mesh looks like very terrible and its hard to rip from more perspektives to get the full model.
I think the game engine (Riot engine) have backface culling on, whats the reason for that (you can see it in 3d view of the level editor).
So i dont need the full animation with bones of the models, just only the mesh with textures. So i think, there must be a way to solve this, but how?

1. Is there a way, to disable backface culling in the engine.exe file to rip the models with backfaces or

2. Is there a way with an external tool to disable the backface culling in the engine to rip the models with backfaces or

3. Extract the rec models from database files or extract them from the 3dview in the editor? I tried many things. For example: I tried to save the process of engine.exe if i viewing a model in 3dview to a dump file, to look this in hxd editor, but i dont know how can i extract it from there.

I have uploaded the game with editor at my webspace: [http://www.olliruesweg.de/downloads/games/drakan.zip](http://www.olliruesweg.de/downloads/games/drakan.zip)
To see a model in editor, start the Psygnosis\Drakan\Editor\Level Editor.exe and open a level (for example : Psygnosis\Drakan\Mountain World\Ruined Village\Ruined Village.lvl)
If the level is loaded, goto window -> databases to open the db window. Click on models and choose NPCs. So here are all .rec models, you can view it via doubleclick in 3dview.

I hope it helps and i really hope, someone can help me here to extract the rec models. They are low poly and not too complicated.
Please help me   

Best regards,
olli
## Post #2
- Username: olli9000
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Dec 02, 2015 12:04 am
- Post datetime: 2017-04-05T02:19:54+00:00
- Post Title: Drakan Order of the flame (rec models)

I asked some c++ developers and they said, thats not too hard with a debugger to change the culling mode.
I would like ripping the models, if there is really no chance to extract them, but i must disable the backface culling.

Please help me
