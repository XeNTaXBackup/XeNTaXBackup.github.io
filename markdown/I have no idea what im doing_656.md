## Post #1
- Username: supercrazyaustin
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 13, 2004 6:08 am
- Post datetime: 2004-04-12T22:13:13+00:00
- Post Title: I have no idea what im doing

hey yall, i got this swg game and i wanted to know if there was a way to hack myself to be a jedi. I downloaded the tre opener thing but i have no idea what to do with it. Could somebody help me out?
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-04-13T07:15:50+00:00
- Post Title: I have no idea what im doing

Obviously you can OPEN a TRE archive, and EXTRACT it's contents. 

You can IMPORT/CREATE NEW a brand new TRE archive. 

You can VIEW a file inside an open TRE file. 

You can REPLACE an item in the open TRE file with a file of your choice. 

It's simply really. Open a TRE file and RIGHT-CLICK on an item for options. Or use the large buttons. 

Note that this program is AS IS and will not be updated/changed.
## Post #3
- Username: the-lizard-king
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 01, 2006 12:08 pm
- Post datetime: 2006-01-01T04:09:42+00:00
- Post Title: I have no idea what im doing

hey do you know wher i can get the tre opener? WHenever i google it this is the only thing that comes up lol
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-01T07:33:27+00:00
- Post Title: I have no idea what im doing

Two threads down in this News forum and you would have seen it. 

[viewtopic.php?t=520&highlight=tre+archiver](http://forum.xentax.com/viewtopic.php?t=520&highlight=tre+archiver)
[viewtopic.php?t=519&highlight=tre+archiver](http://forum.xentax.com/viewtopic.php?t=519&highlight=tre+archiver)
## Post #5
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-02T13:46:22+00:00
- Post Title: I have no idea what im doing

You can't really do what you want with these programs - things like hacking saved games, and stuff like that, are not really possible using these programs. All that these tools do is read and write archives - archives are not the same as saved games. You will need a save game editor for the game in order to change into a jedi.

Oh, and before you ask, no I do not know if there are any save game editor or anything, you'd just have to google it or something - you could probably find one because the game has been out for a while, hasn't it?

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-01-03T00:46:50+00:00
- Post Title: I have no idea what im doing

The post you're referring to is pretty old, watto (look at the timestamp)... Though your post does stir a new idea within my mind (perhaps some sort of addon to MexCom/GE...?), a saved game editor with its own scripting language for adding support for new games. But surely such a thing would be much harder to create and maintain than an archive opener/editor, as MC and GE are...
## Post #7
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-03T01:37:09+00:00
- Post Title: I have no idea what im doing

Ah ok  - didn't notice that.

In regards to a save game editor - it shouldn't be too hard to do in general, however it would be more complex than MC/GE - archives are pretty basic compared to most other file types.

You would need to adjust the interface slightly so that it dealt with fields that represented a specific thing (such as money or life) rather than individual files. Instead of exporting data, it would be better to have editing built in to the program, which means you would also need to ensure that you had separate text and number fields, that you restricted them to certain lengths, etc. You would probably need to have dropdown fields too, as many saved games would have only a certain number of allowed values.

It is possible to do - it would be similar in some ways to MC/GE, but dealing with different data. Feel free to look into this if anyone wants to - I think there are some programs out there that do this kind of thing already but it could be a bit of fun. Unfortunately I wont be taking this any further - I really don't have the time to work on it, and it would be much more time consuming to work out saved games compared to archvies (usually means you need to save a game, examine it, save the game again when only changing 1 variable (such as dropping money) and then comparing.

Anyway, nice suggestion 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #8
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-01-03T23:04:06+00:00
- Post Title: I have no idea what im doing

Yeah, I was fairly certain it would be more complex... As for save game editors currently out there, I don't know of any that support games past, say, a certain game series or engine, or individual games, which would make my proposed program level with MC/GE. I agree, it would be interesting to pursue this idea, but I lack the programming knowledge (and library of game formats!) to try it myself.

As for determining the formats, that can be a pain. I've recently undertaken the colossal task of figuring out the format for a game that has dynamically built levels (it's a zoo-type game, Jurassic Park Operation Genesis; the fan-based modding forum, when it works, can be found at [http://dynamic.gamespy.com/~modgenesis/](http://dynamic.gamespy.com/~modgenesis/)), currently I haven't moved past figuring out how the terrain heightmaps are stored... Not to mention that after this format (it happens to be stored in a 1008KB file!), I've still got three more filetypes to work through, two of which are dynamically sized...
