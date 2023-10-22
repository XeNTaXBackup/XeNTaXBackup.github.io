## Post #1
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-03-19T11:34:09+00:00
- Post Title: Shade

Hello

Please see .res from shade game

thx
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-03-21T11:02:12+00:00
- Post Title: Shade

Ok, this is the format...

```
  4 - File Type ("PK" + (byte)3,4 or "IPF1")
  2 - Unknown (20)
  2 - Unknown (2)
  2 - Unknown (File=8, Dir=0)
  4 - Directory/File Identifier? (Dir=823760679, File=823701178)
  // Note: If it is a Directory - the next 3 fields are null
  4 - Timestamp???
  4 - File Size
  4 - Decompressed File Size?
  4 - Filename Length
  X - Filename
  X - File Data
```


I havn't had time to code it into a plugin or a script yet though, so there could be some errors in it.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-03-22T12:11:00+00:00
- Post Title: Shade

Hi again,

I have confirmed that this format is correct, but havn't made a script for this format yet - mostly because I am not too sure how to write a script for a format without knowing how many files are in the archive. I guess I would prefer Mr Mouse to write a script for this one, so I can see how it is structured for the future.

Sorry about that.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-03-22T12:38:00+00:00
- Post Title: Shade

Okido. Will see what I can do. I am having trouble making free time to work on the new release and/or scripts, but will give it a shot nevertheless.
## Post #5
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-03-22T12:39:07+00:00
- Post Title: Shade

Actually, I took a look at some of the scripts from other games, and hopefully this will do the job...

```
Goto EOF 0 ;
SavePos EndPos 0 ;
Goto 18 0 ;
Do ;
Get FS Long 0 ;
Get DummyL Long 0 ;
Get FNLen Long 0 ;
GetDString FN FNLen 0 ;
SavePos FO 0 ;
Log FN FO FS 0 0 ;
Math FO += FS ;
Goto FO 0 ;
While CurPos <> EndPos ;

```


Also see the attached compiled script, that can be put straight into the main script archive.

Good Luck

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-03-22T12:51:52+00:00
- Post Title: Shade

Even better !
## Post #7
- Username: baccello
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Sep 23, 2004 1:44 am
- Post datetime: 2005-03-24T10:44:57+00:00
- Post Title: Shade

Hello, you can extract this pack with WinRAR when encurring in error archive you must repair it whit repair function of WinRAR, make a copy of original file. The new file is a simple zip file.
You can edit files but you can't put them into archive. If you want that game accept your edit file you only put them in game folder, when you start game your file in game folder will read from game.

Sorry my poor little english, I'm italia
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-03-24T11:26:18+00:00
- Post Title: Shade

Thank you, I was wondering that same thing, when I noticed that Watto wrote "PK" as header. Didn't have time to check such a file myself though.
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-03-27T11:35:37+00:00
- Post Title: Shade

Hmm, the script doesn't work.
## Post #10
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-03-27T12:51:27+00:00
- Post Title: Shade

Yeah, I guess thats posible - I didn't test it on the actual archive - I just made sure it compiled properly. The format specs should be correct though because I used them fo my own plugin. I wasn't really sure about a few things too, such as reading the filename, etc.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
