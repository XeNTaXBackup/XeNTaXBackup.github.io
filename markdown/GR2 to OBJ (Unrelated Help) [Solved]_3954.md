## Post #1
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-12-18T20:47:33+00:00
- Post Title: GR2 to OBJ (Unrelated Help) [Solved]

The contents of this post was deleted because of possible forum rules violation.
[GR2ToOBJ.7z](https://xentaxbackup.github.io/file/2629_GR2ToOBJ.7z)
## Post #2
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2010-02-21T08:32:49+00:00
- Post Title: GR2 to OBJ (Unrelated Help) [Solved]

After reading the readme file it looks like the program REQUIRES you to name the output file manually.  I think that's your hangup.  Sorry I don't know much about batching other than the basics, if you can find a way to grab the name of the current source file and automatically create the name of the output file with the .obj extension it'll work.

Edit: Just tried the tool after downloading and it seems to convert with several issues.  Most output files are incomplete and the program crashes (I am running on windows 7 x64 though) and the only file it succesffuly converted I imported with Milkshape 3d and it was just individual vertices or points not connected.  No mush just point cloud it looked like.
## Post #3
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2010-02-21T10:17:28+00:00
- Post Title: GR2 to OBJ (Unrelated Help) [Solved]

thanks so much AceAngel for sharing evegr2toobj
## Post #4
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2010-02-21T18:27:44+00:00
- Post Title: GR2 to OBJ (Unrelated Help) [Solved]

if i am right about your question ! 
this bath file convert all gr2 files in the current directory :

```
for %%f in (*.gr2) do evegr2toobj %%f %%f_.obj
```

you can modify it in any form easily :
[http://technet.microsoft.com/en-us/libr ... 90909.aspx](http://technet.microsoft.com/en-us/library/bb490909.aspx)

 converter.rar
(118 Bytes) Downloaded 88 times
