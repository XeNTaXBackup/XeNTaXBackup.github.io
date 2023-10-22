## Post #1
- Username: Abyssinian
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Aug 19, 2013 9:10 am
- Post datetime: 2013-11-20T15:33:43+00:00
- Post Title: Lego Marvel textures

Hey everyone,

I was just messing around with getting textures from the new Lego Marvel game (PC version). Using QuickBMS and the TT games DAT file extractor script I managed to extract all game files. However, there were no textures. No .tga or .dds files whatsoever. Would anyone have any idea as to where or how I can get a hold of those?

Thanks in advance!
## Post #2
- Username: RickyOs
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Nov 30, 2010 12:54 am
- Post datetime: 2013-11-21T14:20:46+00:00
- Post Title: Lego Marvel textures

Look for .tex files and rename them to .dds files. You can use the following recursive (/R) command in the root dir of your extraction:

```
for /R %x in (*.tex) do ren "%x" *.dds
```

There are also little archives that contain more dds textures: .nxg_textures files.
## Post #3
- Username: Abyssinian
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Aug 19, 2013 9:10 am
- Post datetime: 2013-11-22T00:52:55+00:00
- Post Title: Lego Marvel textures

I'm sorry I have to ask, but how do I apply the command? I get the code, just have no idea how to use it.

Also, do you know how (or with what) I can extract the textures from the .nxg_textures files?
## Post #4
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2013-11-22T04:58:27+00:00
- Post Title: Lego Marvel textures

There's also a freeware program that I use that can do batch renaming, by the name of (simply enough) [ReNamer](http://www.den4b.com/?x=products&product=renamer). Just drag all the files into the program and do a batch replace from .tex to .dds (you'll have to uncheck "Skip extension" first, of course).
## Post #5
- Username: Abyssinian
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Aug 19, 2013 9:10 am
- Post datetime: 2013-11-22T09:25:19+00:00
- Post Title: Lego Marvel textures

Ah, okay. Thanks!

And how do I extract the files from the .nxg_textures archives?
