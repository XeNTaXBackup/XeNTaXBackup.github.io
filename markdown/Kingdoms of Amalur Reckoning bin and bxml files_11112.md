## Post #1
- Username: Phnx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Apr 17, 2010 11:31 pm
- Post datetime: 2014-01-06T00:41:00+00:00
- Post Title: Kingdoms of Amalur Reckoning bin and bxml files

Now that we have an archive explorer

[http://raptor.cestiny.cz/download/kingd ... actor.html](http://raptor.cestiny.cz/download/kingdoms-of-amalur-reckoning-big-files-extractor.html)

we have access to all the files inside. There are a lot of bin and bxml files. 

[http://en.wikipedia.org/wiki/Binary_XML](http://en.wikipedia.org/wiki/Binary_XML) ???

[http://bin.fileextensionguide.com](http://bin.fileextensionguide.com) ???

I guess they control how the game functions. I'd really love to edit them but they are encrypted and I have no idea where to start. I would really appreciate help with this! 

Here are two example files from the BigFile_0000.big archive.

[http://www.mediafire.com/download/9z3oj ... 2.lua_bxml](http://www.mediafire.com/download/9z3ojpx1k5utud9/12842.lua_bxml)

[http://www.mediafire.com/download/8d545 ... t_init.bin](http://www.mediafire.com/download/8d545r061a33aj7/luascript_init.bin)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-01-06T15:54:48+00:00
- Post Title: Kingdoms of Amalur Reckoning bin and bxml files

> Reply from Phnx
>
> I guess they control how the game functions. I'd really love to edit them but they are encrypted and I have no idea where to start. I would really appreciate help with this!The bxml looks like a binary xml file.
You'll need to code a bxml to xml converter and vice versa (means decoder/encoder) if you want to mod the game.

From my experience on another game, ArcaniA, it doesn't work just to edit/repack the binary xml.

(I was a supporter of the ArcaniA Unpacker some years ago and it was a hard task to get it working.

I could give you the link to the unpacker's repository. From the code you could get a clue on how to start
if you are an experienced coder.)
## Post #3
- Username: Phnx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Apr 17, 2010 11:31 pm
- Post datetime: 2014-01-08T23:55:15+00:00
- Post Title: Kingdoms of Amalur Reckoning bin and bxml files

Unfortunately I'm no coder. I thought maybe with a little luck a bxml to xml converter/bin editor already exists but I guess it should have been specific to the game anyway.

Also, I found strings like "cheat_add_item" in the exe. Is there any chance to re-activate the dev-mode/console?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-01-09T09:10:35+00:00
- Post Title: Kingdoms of Amalur Reckoning bin and bxml files

> Reply from Phnx
>
> Also, I found strings like "cheat_add_item" in the exe. Is there any chance to re-activate the dev-mode/console?Again you'll need advanced skills. For the PC version of the game you could search with ollydbg for example for the "entry point" of a dev console. But the existence of such a console is not confirmed nor could anyone use a cheat afaik.

edit: are there other command strings in the exe like exit, quit, give, gold, teleport, debug info, god?
## Post #5
- Username: Phnx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Apr 17, 2010 11:31 pm
- Post datetime: 2014-01-09T21:08:58+00:00
- Post Title: Kingdoms of Amalur Reckoning bin and bxml files

I found some interesting files with a lot of commands and key combinations in the archives.

[http://www.mediafire.com/download/jlk5s ... enums.bxml](http://www.mediafire.com/download/jlk5st34i3swh5i/compiled_enums.bxml)

[http://www.mediafire.com/download/j0xpb ... rated.bxml](http://www.mediafire.com/download/j0xpbxs7bao0a6x/concommands_generated.bxml)

[http://www.mediafire.com/download/zcdoz ... eymap.bxml](http://www.mediafire.com/download/zcdoz9s0671r0it/tools_keymap.bxml)
## Post #6
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2021-12-15T12:28:55+00:00
- Post Title: Kingdoms of Amalur Reckoning bin and bxml files

any idea about *.ksdf file than'ks
