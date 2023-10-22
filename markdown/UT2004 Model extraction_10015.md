## Post #1
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2013-01-06T15:32:20+00:00
- Post Title: UT2004 Model extraction?

Hey,
This is really silly considering how old the game is, but I can't seem to find any way to import UT2004 character models into 3ds max. I have noesis mode viewer, which should be able to view the models, but I can't get past the .ukx compressed files the models are stored in. I heard tell you could get the whole selection of character models in max format, rigged and everything, from the developers, but all the links to those files are long dead. Can someone help me out with this? I have tried a variety of extractors, such as GFE and Wotgreal, but they make no sense, and don't seem to be able to open these files... they also don't like the install location of UT2004, considering I got it for steam. Any ideas? 
Thanks!
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2013-01-06T17:19:15+00:00
- Post Title: UT2004 Model extraction?

Gildor is the master of all things Unreal, you need not look further than his [UE Viewer](http://www.gildor.org/en/projects/umodel) which happens to support UT2004.
## Post #3
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2013-01-06T17:44:05+00:00
- Post Title: UT2004 Model extraction?

Thanks for the help, dude... I used Gildor's tool to extract the meshes and textures I wanted (after sifting through a bunch of files, of course... UT2004 has a messy file structure), and used his Actor X importer to import the mesh (with rigging) into 3ds max. I then realized that the importer imports meshes as a single mesh, which was a problem because the textures are split into 2 parts: head, and body. By experimenting, I found that by detaching the head mesh in the editmesh options, I could apply the head texture, as the head mesh retained its UV Mapping. So, all in all, it worked just fine. Thanks for the help guys, it turned out great.
