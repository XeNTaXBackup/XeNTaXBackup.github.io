## Post #1
- Username: Irastris
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Sep 21, 2015 12:28 pm
- Post datetime: 2016-10-10T08:12:55+00:00
- Post Title: Resident Evil 5 (.mod) - Noesis improperly loading model

Hello, XeNTaX. I'm hoping someone can help me out with this issue.

I'm trying to import a RE5 mod into Noesis, but for some reason several of the vertices end up misplaced in the preview, and persist if I export to a different format.


Here's the mod in question: [http://residentevilmodding.boards.net/t ... or-costume](http://residentevilmodding.boards.net/thread/2066/re5-rachael-foley-aviator-costume)
And here's a direct download to the .mod and the .dds textures: [http://www21.zippyshare.com/v/0ABoVVCA/file.html](http://www21.zippyshare.com/v/0ABoVVCA/file.html)

Thanks in advance to anyone that can provide some help and/or a solution.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-10-10T11:03:15+00:00
- Post Title: Resident Evil 5 (.mod) - Noesis improperly loading model

Since DMC4/RE5 is a built-in format there's no direct solution.
You might export as obj, then import to blender separated as groups.
Then it's possible to select proper mesh parts (delete remaining odds in face or edge select mode):



pl1200-groups.jpg (155.13 KiB) Viewed 253 times
## Post #3
- Username: Irastris
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Sep 21, 2015 12:28 pm
- Post datetime: 2016-10-11T01:24:41+00:00
- Post Title: Resident Evil 5 (.mod) - Noesis improperly loading model

> Reply from shakotay2
>
> 
Since DMC4/RE5 is a built-in format there's no direct solution.
You might export as obj, then import to blender separated as groups.
Then it's possible to select proper mesh parts (delete remaining odds in face or edge select mode):
]

Thank you for the help!
## Post #4
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2016-10-11T03:00:50+00:00
- Post Title: Resident Evil 5 (.mod) - Noesis improperly loading model

I imagine that model is from the remaster or Re5 in PC because Noesis works wery well on every model of the first RE5.
## Post #5
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-11-01T22:00:53+00:00
- Post Title: Resident Evil 5 (.mod) - Noesis improperly loading model

I'd been meaning to look into this, and finally did recently. This looks to be a user-made model that someone has butchered mercilessly. RE5 stores multiple LOD's for each model, and Noesis loads all of them. Typically a LOD index of -1 means "draw in all LOD settings". This model relies on putting the only legitimate surfaces in LOD -1, and has piled a bunch of broken garbage geometry that no longer correctly matches up to the vertex buffers in LOD 0. The game is only showing you LOD -1 surfaces, but Noesis shows you the horror underneath.

Figuring there's more busted data like this floating around in the user community due to whatever unholy tool produced this abomination, future versions of Noesis will have a "-capmodln1" command, which will ignore all geometry that doesn't have a LOD assignment of -1, which causes this broken model to load like this instead.
