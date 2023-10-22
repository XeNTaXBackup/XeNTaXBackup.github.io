## Post #1
- Username: ColbyDash
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Nov 09, 2021 5:17 pm
- Post datetime: 2023-05-09T06:09:34+00:00
- Post Title: [X360/PS3] Eurocom's Rio Video Game (.edb)

Hello! I apologize ahead of time if I have happened to have posted this in the wrong topic but it was best as I'll go on to explain.

I'm looking to extract assets from the Rio video game, specifically the character models above all, and after FINALLY figuring out how to extract the file structure of the game through this [thread](https://forum.xentax.com/viewtopic.php?f=10&t=8026), I ran into another roadblock with these .edb files for as far as I know in my research, there's only one script known in existence for extracting an older version of that format from one of the Spyro games according to someone else on here who've asked about the same format before but for a different Eurocom game. If anyone knows anything about this format or would like to help in any way, it would very well be much appreciated as I would to use the character models from the game as I've mentioned, using the meshes found directly from within the game files opposed to using the meshes I've ripped using NinjaRipper 2 and it's perspective based rips. I don't even care if I get a static mesh, all that matters to me is that I do get a model I can use for [the second update in my Rio models pack over on DA](https://www.deviantart.com/colbydash/art/Birds-Luiz-and-Marmosets-Rio-The-Video-Game-942086469) and I hope that through this I'll finally be satisfied enough with the quality of the models to finally share them on the Models Resource. 

[If it helps, here are the .edb files from both of my extracted copies of the 360 port and the PS3 port.](https://drive.google.com/file/d/1zhB3DAZQB7-uK_DRp5qt3iCvy23-64FW/view?usp=sharing)

Many thanks ahead of time for the help should anyone choose to help and hopefully be able to contribute greatly to overcoming this roadblock in my quest!
## Post #2
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-05-09T19:58:29+00:00
- Post Title: [X360/PS3] Eurocom's Rio Video Game (.edb)

> Reply from Korubii ↑Tue May 09, 2023 2:09 pm at Tue May 09, 2023 2:09 pm
>
> 
Hello! I apologize ahead of time if I have happened to have posted this in the wrong topic but it was best as I'll go on to explain.

I'm looking to extract assets from the Rio video game, specifically the character models...

Hi, just upload a few model samples, not all files. I think models are "rigres_xxname.edb". So upload a few from PS3 and XBOX360.
## Post #3
- Username: ColbyDash
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Nov 09, 2021 5:17 pm
- Post datetime: 2023-05-09T23:12:02+00:00
- Post Title: [X360/PS3] Eurocom's Rio Video Game (.edb)

> Reply from roocker666 ↑Wed May 10, 2023 3:58 am at Wed May 10, 2023 3:58 am
>
> 
Korubii wrote: ↑Tue May 09, 2023 2:09 pm
Hello! I apologize ahead of time if I have happened to have posted this in the wrong topic but it was best as I'll go on to explain.

I'm looking to extract assets from the Rio video game, specifically the character models...


Hi, just upload a few model samples, not all files. I think models are "rigres_xxname.edb". So upload a few from PS3 and XBOX360.

Okie dokey, I'll leave the og up in case if anyone wants to look through the rest of the .edb files and not just the rigres files (which I assume to contain the models as well): [https://drive.google.com/file/d/1H-Gtf8 ... sp=sharing](https://drive.google.com/file/d/1H-Gtf8fLspWDzomSQQl1iITAW8rWvg5R/view?usp=sharing)
## Post #4
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-05-10T00:14:34+00:00
- Post Title: [X360/PS3] Eurocom's Rio Video Game (.edb)

> Reply from ColbyDash ↑Wed May 10, 2023 7:12 am at Wed May 10, 2023 7:12 am
>
> 
Okie dokey, I'll leave the og up in case if anyone wants to look through the rest of the .edb files and not just the rigres files (which I assume to contain the models as well): https://drive.google.com/file/d/1H-Gtf8 ... sp=sharing

Ok, thanks. It seems like all files use some kind of compression method so you need to decompress files first but I don't know hot to do that..
## Post #5
- Username: ColbyDash
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Nov 09, 2021 5:17 pm
- Post datetime: 2023-05-10T00:40:32+00:00
- Post Title: [X360/PS3] Eurocom's Rio Video Game (.edb)

> Reply from roocker666 ↑Wed May 10, 2023 8:14 am at Wed May 10, 2023 8:14 am
>
> 
ColbyDash wrote: ↑Wed May 10, 2023 7:12 am
Okie dokey, I'll leave the og up in case if anyone wants to look through the rest of the .edb files and not just the rigres files (which I assume to contain the models as well): https://drive.google.com/file/d/1H-Gtf8 ... sp=sharing


Ok, thanks. It seems like all files use some kind of compression method so you need to decompress files first but I don't know hot to do that..

Np! Idk how I might go about that either but I was thinking if we could find that [Spyro .edb script](https://forum.xentax.com/viewtopic.php?p=135542&hilit=edb#p135542) I had mentioned in my inital post, it could be re-engineered into working with version 12 Eurocom .edb files as such I believe the Rio video game does use from what I've gathered around here.
## Post #6
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-05-10T01:32:15+00:00
- Post Title: [X360/PS3] Eurocom's Rio Video Game (.edb)

> Reply from ColbyDash ↑Wed May 10, 2023 8:40 am at Wed May 10, 2023 8:40 am
>
> 
 if we could find that Spyro .edb script I had mentioned in my inital post, it could be re-engineered into working with version 12 Eurocom .edb files as such I believe the Rio video game does use from what I've gathered around here.

Spyro a hero's tail .edb files(PS2) are not compressed so you can extract the model with no problem. But here is the script if you want to analyze it:
[https://web.archive.org/web/20170812173 ... ero's+Tail](https://web.archive.org/web/20170812173541/http://ps23dformat.wikispaces.com/Spyro+A+Hero%27s+Tail)
## Post #7
- Username: ColbyDash
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Nov 09, 2021 5:17 pm
- Post datetime: 2023-05-10T09:05:51+00:00
- Post Title: [X360/PS3] Eurocom's Rio Video Game (.edb)

> Reply from roocker666 ↑Wed May 10, 2023 9:32 am at Wed May 10, 2023 9:32 am
>
> 
ColbyDash wrote: ↑Wed May 10, 2023 8:40 am
 if we could find that Spyro .edb script I had mentioned in my inital post, it could be re-engineered into working with version 12 Eurocom .edb files as such I believe the Rio video game does use from what I've gathered around here.


Spyro a hero's tail .edb files(PS2) are not compressed so you can extract the model with no problem. But here is the script if you want to analyze it:
https://web.archive.org/web/20170812173 ... ero's+Tail

Sweet! Thanks for that grab and all the support so far as well! I'll keep that in mind as I go on into this. Also, one of my friends did a deeper search into Eurocom games and found this [tool](https://github.com/eurotools/eurochef) made for Spyro and the rest but not for Rio (or at least not of just yet).
