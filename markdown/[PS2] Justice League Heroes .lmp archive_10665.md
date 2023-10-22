## Post #1
- Username: SoulReaver
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 15, 2009 11:47 pm
- Post datetime: 2013-08-07T08:37:23+00:00
- Post Title: [PS2] Justice League Heroes .lmp archive

Hello all!

can you please help me in unpacking the data for the *.lmp container files?
I've already tried  QuickBMS because it has compatibility with baldur's gate *lmp and *Gob, but unfortunately it didn't work.
I tried to get the models from the container but im still having a hard time understanding their file format.

[https://www.dropbox.com/s/0ubcipkdm6nar ... RBOT.LMP?m](https://www.dropbox.com/s/0ubcipkdm6narg8/SUPERBOT.LMP?m)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-08-07T13:09:07+00:00
- Post Title: [PS2] Justice League Heroes .lmp archive

```
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

get FILES long

for i = 0 < FILES
    get NOFFSET long
    savepos TEMP
    goto NOFFSET
    get NAME string
    goto TEMP
    get OFFSET long
    get SIZE long
    log NAME OFFSET SIZE
next i
```
## Post #3
- Username: SoulReaver
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 15, 2009 11:47 pm
- Post datetime: 2013-08-07T16:02:43+00:00
- Post Title: [PS2] Justice League Heroes .lmp archive

thank you it helped alot. Now I no longer get the error to rename the files, thank you
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-08-07T17:13:11+00:00
- Post Title: [PS2] Justice League Heroes .lmp archive

You also can explore your LMP archive using this:

[](http://www.pic-upload.de/view-20329891/bgda-explorer.jpg.html)

- F4, settings: engine version Champions: Return to Arms

Texture is correctly displayed but vif model not recognized.


Description of the vif format, see posts of ibrown in this thread
[viewtopic.php?f=16&t=4881](http://forum.xentax.com/viewtopic.php?f=16&t=4881)

(Link to CS Source code of explorer also to be found there.)
## Post #5
- Username: SoulReaver
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 15, 2009 11:47 pm
- Post datetime: 2013-08-07T19:07:36+00:00
- Post Title: [PS2] Justice League Heroes .lmp archive

thank you for this , but i dont know how to copile in visual studio to much. But managed to convert vtf model to 3ds now i only need to figure out how to fix these models.
## Post #6
- Username: SoulReaver
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 15, 2009 11:47 pm
- Post datetime: 2013-08-10T12:38:51+00:00
- Post Title: [PS2] Justice League Heroes .lmp archive

allright managed to extract the textures using the converter, all that is left is to find out why some face are missing and some vertexes are to close together. Im guesing the .vtf script is incomplete?
## Post #7
- Username: Curtain
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Apr 18, 2017 2:13 am
- Post datetime: 2019-05-11T02:34:46+00:00
- Post Title: [PS2] Justice League Heroes .lmp archive

[](https://www.youtube.com/watch?v=dHsXNdaBHvo)
Sorry for the bump.
SoulReaver, are there still issues with extracting models from the game? 
If not, I would like to take a shot at this with QuickBMS or Ninja Ripper.
