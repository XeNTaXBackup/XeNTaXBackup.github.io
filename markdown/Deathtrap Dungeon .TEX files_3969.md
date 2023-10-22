## Post #1
- Username: StarQuake
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 03, 2009 8:22 pm
- Post datetime: 2009-12-22T00:05:09+00:00
- Post Title: Deathtrap Dungeon .TEX files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-22T07:21:34+00:00
- Post Title: Deathtrap Dungeon .TEX files

Do not use megaupload again. Check the rules.

Yes it is possible to do this. 



14124.png (33.77 KiB) Viewed 209 times



That is the texture you added. Raw bitmap data of 256x256. The palette I took from the pal1.pal file (it was at the beginning of this file , 256 x RGB values (768 bytes total). You can load up the .tex file in Photoshop as a raw file. Then set mode to indexed and load the 768 bytes as palette.
## Post #3
- Username: StarQuake
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 03, 2009 8:22 pm
- Post datetime: 2009-12-22T07:51:30+00:00
- Post Title: Deathtrap Dungeon .TEX files

Many Thanks, and sorry about the megaupload thing
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-22T08:08:13+00:00
- Post Title: Deathtrap Dungeon .TEX files

Oh and the pal1.pal shows of the palette with different tones:



imagedatafrompal1.png (70.15 KiB) Viewed 205 times
## Post #5
- Username: StarQuake
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 03, 2009 8:22 pm
- Post datetime: 2009-12-22T08:38:47+00:00
- Post Title: Deathtrap Dungeon .TEX files

Just a quick question, how do I load the bytes as the palette?
## Post #6
- Username: StarQuake
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-22T08:39:55+00:00
- Post Title: Deathtrap Dungeon .TEX files

Use a hex editor to cut out the first 768 bytes of the pal1.pal file and save it as "palette.act". Photoshop can then load that colour table.
## Post #7
- Username: willward
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jan 26, 2010 6:00 am
- Post datetime: 2010-01-26T18:28:32+00:00
- Post Title: Deathtrap Dungeon .TEX files

you could try slimtex its a tool for geoff crammonds grand prix 4 nfor pc that opens tex files

heres a link to it [http://gp4db.com/index.php?category=misc&section=Tools](http://gp4db.com/index.php?category=misc&section=Tools)
its under zaz tools
