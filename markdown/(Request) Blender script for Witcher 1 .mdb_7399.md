## Post #1
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2011-09-22T23:25:42+00:00
- Post Title: (Request) Blender script for Witcher 1 .mdb

Can someone make a blender script to import .mdb character models from The Witcher 1?

I know that Witcher 2 script already exists, but there are some really good characters in Witcher 1 that would be nice to get into blender.

Also, there does exist an importer for 3ds max 9 but I have not this program so I would really need the script for blender. Please!

Here is a link for Adda character .mdb with textures if someone wants to give it a look.

[http://www.filesonic.com/file/2111041904/Adda.rar](http://www.filesonic.com/file/2111041904/Adda.rar)
## Post #2
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-09-27T19:06:04+00:00
- Post Title: (Request) Blender script for Witcher 1 .mdb

The contents of this post was deleted because of possible forum rules violation.

Updated 2015-11-05:
This is blend importer for Blender old version 249 and Python 266.
After unpacking zip move all files to folder where is blender.exe and double click Blender249.blend.
Use for files with original location after unpacking from bif archives:
-mdb-model file
-mda-animation container, use for unpack action files
-action-my animation file (not used by game)-select from *.mda+_animfiles
[Blender249[TheWitcher][mdb][2015-11-05].zip](https://xentaxbackup.github.io/file/9971_Blender249[TheWitcher][mdb][2015-11-05].zip)
## Post #3
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2011-09-28T13:35:45+00:00
- Post Title: (Request) Blender script for Witcher 1 .mdb

Thank You  Szkaradek123,

I always look forward to your posts and I'll certainly be looking forward to this update also.

Thanks again for the script:)
## Post #4
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2011-09-28T17:03:19+00:00
- Post Title: (Request) Blender script for Witcher 1 .mdb

Doesn't the witcher 1 use the engine used for NWN2?
I think if you can find tools for that, you ought to be able to import the models.
## Post #5
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2011-09-29T03:20:45+00:00
- Post Title: (Request) Blender script for Witcher 1 .mdb

> Reply from junk angel
>
> Doesn't the witcher 1 use the engine used for NWN2?
I think if you can find tools for that, you ought to be able to import the models.

From wikipedia:
"The Witcher is powered by a heavily modified version of the Aurora Engine by BioWare"

Being it's heavily modified, I wouldn't think NWN2 tools would work although I haven't tried it.
## Post #6
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2013-04-03T15:40:35+00:00
- Post Title: (Request) Blender script for Witcher 1 .mdb

Anyone still have the import script for this? Szkaradek123 post is empty now...
## Post #7
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-04-03T20:53:54+00:00
- Post Title: (Request) Blender script for Witcher 1 .mdb

Here, I've got this one.
[WITCHER.rar](https://xentaxbackup.github.io/file/6311_WITCHER.rar)
## Post #8
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2013-04-03T21:04:01+00:00
- Post Title: (Request) Blender script for Witcher 1 .mdb

Thanks! (Exactly the model I'm looking for doesn't work, Shani, works for you?)

Edit: On more checks, I can't seem to load anything  Getting "struct.error: unpack requires a string argument of lenght 4"
## Post #9
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-04-03T21:15:53+00:00
- Post Title: (Request) Blender script for Witcher 1 .mdb

It's for Blender 2.49 (with Python 2.6/7) maybe you're using newer version?
## Post #10
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2013-04-03T22:17:08+00:00
- Post Title: (Request) Blender script for Witcher 1 .mdb

I'm on the right version (have like 5 more import scripts from Szkaradek123 working) so dunno what could be...
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-04-04T17:50:04+00:00
- Post Title: (Request) Blender script for Witcher 1 .mdb

> Reply from CMihai
>
> Thanks! (Exactly the model I'm looking for doesn't work, Shani, works for you?)

Edit: On more checks, I can't seem to load anything  Getting "struct.error: unpack requires a string argument of lenght 4"Got the same prob. I checked parser() fct. for what is going wrong.

But it was easier for me to code my own obj converter. It needs manual offs correction (as always) so don't know whether I'll waste more time on this.



shani-obj.jpg (25.99 KiB) Viewed 120 times



edit: finally I made it. But use it on your own risk!
[WitchExtract.zip](http://www.uploadmb.com/dw.php?id=1365430464)
Mesh and UV to be extracted. Tried some level mesh (gl18.mdb). Seemed to work, too.
