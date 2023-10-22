## Post #1
- Username: sakis720
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jul 05, 2022 6:51 pm
- Post datetime: 2023-07-07T11:02:46+00:00
- Post Title: Ghostbusters The Video Game Multiplayer Map Levels

Hi i want to ask if it is possible to make the multiplayers maps .bst files to a .fbx or .obj file or something compatable 

Sample:
[https://www.mediafire.com/file/2vdi4jt1 ... m.bst/file](https://www.mediafire.com/file/2vdi4jt1nifk29l/mp_a1_readingroom.bst/file)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-07-07T18:25:52+00:00
- Post Title: Ghostbusters The Video Game Multiplayer Map Levels

Looks doable - using hex2obj (view link in my sig):
.



mp_a1-bst.png (19.93 KiB) Viewed 168 times

(checked one sub mesh only)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-07-13T20:23:44+00:00
- Post Title: Ghostbusters The Video Game Multiplayer Map Levels

This format seemed to be easy but in fact it's a little bit annoying. (Calculating FVFsizes drives me crazy; need to find the magic tables, if any.)
.



Ghostbuster_readingroom.png (70.82 KiB) Viewed 122 times
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-07-14T09:59:22+00:00
- Post Title: Ghostbusters The Video Game Multiplayer Map Levels

Here's some H2O files (not all but 193) for mp_a1_readingroom.bst:
.


 mp_a1_readingroom.bst_0.zip
(35.03 KiB) Downloaded 17 times



Load said bst file into hex2obj, then File\SaveAs Mmesh.

59 obj files are spoiled, thus renamed to .objx.
If you want to repair them open in notepad and find the responsible H2O file in the first line, for example mp_a1_readingroom.bst_10.h2o

Load the H2O file into hex2obj and correct wrong parameters. (You'll need some experience for this.  It's required to check the bst in a hex editor for such.)
Maybe try out:
reduce FI count at step 1 (press go1, check bottom of left lower listbox)
or step 3: subtract 4 from startaddr

Sometimes the FIs' startaddress is bogus due to the automatic detection failure. 

The other 134 obj files should load without a problem. See picture in previous post.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-07-14T10:26:09+00:00
- Post Title: Ghostbusters The Video Game Multiplayer Map Levels

With 527 meshes it looks like so:
.



reading_room_527_meshes.png (119.46 KiB) Viewed 113 times
