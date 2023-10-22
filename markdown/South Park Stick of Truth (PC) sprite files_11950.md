## Post #1
- Username: Mystie
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Aug 11, 2014 1:38 am
- Post datetime: 2014-09-13T20:51:41+00:00
- Post Title: South Park: Stick of Truth (PC) sprite files

So, I've done some research on the file formats that South Park: Stick of Truth uses for its sprites, and you have to rename the header of each file in a hex editor, rename the extension to .swf, then open the file with an SWF decompiler. I've done all of this, but every time I open one of the files, all of the parts (minus the eyes and mouths) have the wrong color.

Apparently, from what I've been told, you need to edit the 1000/1008/1009 codes in order to make the colors display correctly, but I cannot find them anywhere in the files. I've looked in both JPEXS and a hex editor, and looked through everything, and I could not find these codes anywhere at all.

Can anyone please help me? Thanks in advance.
## Post #2
- Username: Mystie
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Aug 11, 2014 1:38 am
- Post datetime: 2014-09-29T20:31:12+00:00
- Post Title: South Park: Stick of Truth (PC) sprite files

Sorry for bumping, but I really need to know how to do this.
## Post #3
- Username: rubinho146
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Jun 14, 2016 10:13 pm
- Post datetime: 2016-09-24T23:15:29+00:00
- Post Title: South Park: Stick of Truth (PC) sprite files

Gfx are the files that contains graphical content such as characters, backgrounds, etc.

You need to open the gfx file with an hex editor and then change CFX to CWS. After that change the extension to swf.

Get a program that can compile all that swf to fla (Shotink SWF Decompiler) so you can open with Adobe Flash (CS4 or higher).


The problem next is that some color textures are missing because of the dds files that works as textures.

  In that one I still can't figure out the problem.

Edit: I think here it kinda explains about the dds but I'm not sure: [http://forums.na.leagueoflegends.com/bo ... p?t=515500](http://forums.na.leagueoflegends.com/board/showthread.php?t=515500)
