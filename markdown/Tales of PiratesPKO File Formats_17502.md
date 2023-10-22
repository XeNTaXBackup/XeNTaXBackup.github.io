## Post #1
- Username: ofkings
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Jan 01, 2018 7:16 am
- Post datetime: 2018-01-06T03:01:43+00:00
- Post Title: Tales of Pirates/PKO File Formats

i saw some posts about pko files (.lgo .par .eff) here and want some tool to work with it.

i got this tool made by Wolfen, i can convert, but i cant make new shape glow, new wings, pet, etcs.

how i open edit it and save back or convert

and about this PKO SDK, someone can give me link of it?


maybe this help:
[https://github.com/IGamemaker/PKO-file- ... /PKOMdlLib](https://github.com/IGamemaker/PKO-file-viewer/tree/master/PKOMdlLib)

there is wing, pet and sword model  attached
[Models.rar](https://xentaxbackup.github.io/file/13760_Models.rar)
## Post #2
- Username: ofkings
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Jan 01, 2018 7:16 am
- Post datetime: 2018-01-08T16:53:14+00:00
- Post Title: Tales of Pirates/PKO File Formats

BUMP
## Post #3
- Username: ofkings
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Jan 01, 2018 7:16 am
- Post datetime: 2018-01-14T17:21:24+00:00
- Post Title: Tales of Pirates/PKO File Formats

BUMP!
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-04-28T19:28:23+00:00
- Post Title: Tales of Pirates/PKO File Formats

nice PKO viewer (for a successful compile I had to delete the project "MindpowerModelsNet", because MindpowerModelsNet\MindpowerModelsNet.vcxproj was missing):



PKOModelviewer.jpg (114.3 KiB) Viewed 145 times
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-09-25T07:17:29+00:00
- Post Title: Tales of Pirates/PKO File Formats

Five and a half years later I still see desperate guys crying for source codes (which they probably aren't able to use  ).

Anyways, all I can suggest is to use the C# project from here:
[https://github.com/WeaponOwl/PKO-file-viewer](https://github.com/WeaponOwl/PKO-file-viewer)

It imports .lgo files and has a "Save as Lgo" option now (you'll need to provide an .obj file then, of course):
.



PKOModelViewer.png (77.94 KiB) Viewed 61 times



In the Importform you "Select" an .obj file, then press "Import" -> .lgo being created.
Didn't manage to (re) load that .lgo , though. (It's smaller than the original .lgo.)

btw: you may catch an exception on loading lgo files if your missing a subfolder scripts in the model folder, btw.

(And again I didn't care for MindpowerModelsNet.vcxproj)
