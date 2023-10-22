## Post #1
- Username: Teryal5532
- Rank: beginner
- Number of posts: 27
- Joined date: Wed May 11, 2011 7:10 am
- Post datetime: 2011-10-18T18:50:40+00:00
- Post Title: Wolfenstein: Enemy Territory  FONT Files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2011-10-19T09:58:58+00:00
- Post Title: Wolfenstein: Enemy Territory  FONT Files

W:ET is opensource. Take a look at the sourcecode to find out how the characters from the tga's are read by the game.

[http://www.splashdamage.com/index.php?q ... pen-source](http://www.splashdamage.com/index.php?q=content/wolfenstein-enemy-territory-goes-open-source)
## Post #3
- Username: Teryal5532
- Rank: beginner
- Number of posts: 27
- Joined date: Wed May 11, 2011 7:10 am
- Post datetime: 2011-10-19T14:24:39+00:00
- Post Title: Wolfenstein: Enemy Territory  FONT Files

Thanks but where should i look to see how the game read the chars from the font files?

I checked the files from the source code but i don't understand where should i look

Can you tell me?

Sorry but i'm "noob" at this   

----------

Maybe i must look at the the "ui" files (..src\ui) but where exactly
## Post #4
- Username: Sartr0n
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Nov 14, 2011 8:13 pm
- Post datetime: 2012-02-28T14:45:33+00:00
- Post Title: Wolfenstein: Enemy Territory  FONT Files

*bump*

That would be good if there is someone who can say how to open those files but i see that no one posted here for months.

I have a server with my clan and i have played the game from when it's released (many years) and i have tried to translate the game before around 5 months (i think), but the problem were are the font/s/. I have looked at the game's source code but i don't understand nothing from coding/scripting.   

So, is there anyone who can help with that files or no one is viewing this thread anymore?

hmm, the links doesn't work. I can upload the same files but i'll post links later when i upload them.
## Post #5
- Username: Radegast
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 02, 2012 11:54 pm
- Post datetime: 2012-04-02T16:51:45+00:00
- Post Title: Wolfenstein: Enemy Territory  FONT Files

> Reply from Teryal5532
>
> If there is someone who can tell me with what i can open the .dat files and how i can draw the letters in the font files so the game can read them properly, please, write here or PM me.
Short answer: anything is possible to do with enough willpower to do it.
Shorter answer: you can't.

But really, you don't want to edit those *.tga and *.dat files by hand. What you want to do is to re-create them from a TrueType font. I am working on an improved version of Wolfenstein: Enemy Territory called [ET: Legacy Project](http://etlegacy.com) and I wrote a short guide on how to do it: [http://etlegacy.com/projects/etlegacy/w ... e_Freetype](http://etlegacy.com/projects/etlegacy/wiki/How_to_use_Freetype). As you can see from the screenshot on that page it is not ideal atm, but as I said I am working on it and UTF-8 support is on the way.

The relevant source file is [src/renderer/tr_font.c](http://etlegacy.com/projects/etlegacy/repository/revisions/master/entry/src/renderer/tr_font.c) (but the slightly improved one is located inside ioquake3-import branch)

EDIT: well, ok, if you really want to you can make small edits to those .tga files in Gimp or Photoshop or pretty much in any other image editor. But adding new letters or stuff like that won't work.
