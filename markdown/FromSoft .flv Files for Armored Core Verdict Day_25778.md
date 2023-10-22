## Post #1
- Username: manus
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed May 18, 2022 2:36 pm
- Post datetime: 2022-09-06T22:55:22+00:00
- Post Title: FromSoft .flv Files for Armored Core: Verdict Day

Hi, I was able to extract the .flv files from Armored Core: Verdict Day, but I'm stuck on converting them into a usable format? 

There was an older post by finale00 on a script for DS1 [viewtopic.php?f=16&t=7876#p66961](viewtopic.php?f=16&t=7876#p66961), but the dropbox link has gone defunct so I can't test whether it would've worked here. Does anyone still have a copy of this by chance?  

I've also tried using the DS1 Noesis .flv/.flver plugin, but it returns an error("File could not be previewed") when importing. finale00 mentions that AC has a different .flv format from DS1 so that's probably why. 

I've uploaded some sample files below. 

Thanks!
[AC .flv.zip](https://xentaxbackup.github.io/file/22768_AC .flv.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-07T09:52:20+00:00
- Post Title: FromSoft .flv Files for Armored Core: Verdict Day

Those .flv files look compressed to me.
## Post #3
- Username: manus
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed May 18, 2022 2:36 pm
- Post datetime: 2022-09-07T17:23:28+00:00
- Post Title: FromSoft .flv Files for Armored Core: Verdict Day

Huh, I wasn't expecting that. aluigi's Demon's Souls script worked with other FS titles so I assumed it would be the same here. 

I'll seek help from the game archive section first. Thank you for taking a look!
## Post #4
- Username: manus
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed May 18, 2022 2:36 pm
- Post datetime: 2022-09-07T18:18:38+00:00
- Post Title: FromSoft .flv Files for Armored Core: Verdict Day

Forgive me for the double post    - I've been an idiot and didn't take care to notice that those were .dcx files which were named to an flv. 

Here are the new sample files [https://www.mediafire.com/file/2b8qbes3 ... 2.zip/file](https://www.mediafire.com/file/2b8qbes3u0ichr8/1992.zip/file), which returns "Tried to read off end of data array" when opened in Noesis.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-07T20:37:34+00:00
- Post Title: FromSoft .flv Files for Armored Core: Verdict Day

There's a pretty point cloud at least:  
.



m0010_l2-flv.jpg (86.28 KiB) Viewed 90 times


For the face indices: I have no idea - maybe contained in this block?

```
 1204  1199 52669 12544 65535 65535 
 1187  1225 52669 12544 65535 65535 
 1196  1299 52669 12544 65535 65535 
 1217  1310 60607 32512 65535 65535 
 1719   418 60607 32512 65535 65535 
 1807   418 60607 32512 65535 65535 
 1807  1229 60607 32512 65535 65535 
 1719  1229 60607 32512 65535 65535 
 1807  1229 60607 32512 65535 65535 
 1807   418  5314 32512 65535 65535 
 1719   418  5314 32512 65535 65535 
 1807   418  5314 32512 65535 65535 
 1807  1229  5314 32512 65535 65535 
 1719  1229  5314 32512 65535 65535 
 1807  1229  5314 32512 65535 65535 
 1807   418  4670 32512 65535 65535 

```
## Post #6
- Username: manus
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed May 18, 2022 2:36 pm
- Post datetime: 2022-09-09T00:00:20+00:00
- Post Title: FromSoft .flv Files for Armored Core: Verdict Day

Thank you!  This is great! I'll spend some time combing through by trial and error(probably the only way given the mess) and try to come up with something workable.
