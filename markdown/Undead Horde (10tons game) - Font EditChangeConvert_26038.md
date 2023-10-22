## Post #1
- Username: UtkuGARIP
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Feb 28, 2017 8:53 am
- Post datetime: 2022-11-27T13:44:30+00:00
- Post Title: Undead Horde (10tons game) - Font Edit/Change/Convert

Hello

I want to translate for Undead Horde game and I found the language files in "data-localizations.pak" archive.



data-localizations.png (13.15 KiB) Viewed 100 times



When I opened the "languages.xml" file, I saw the font name and extension used. "data -> fonts -> necro.mft" I searched the file "necro.mft" and found out that it is MetaFont. I wonder how do I edit this file or can "ttf to mft" actually be done?

[necro.mft.zip - Google Drive](https://drive.google.com/file/d/1Wwd3xTU4psT7DjF0Z-S8gtICD_x-sVxm/view?usp=share_link)
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-11-28T20:16:36+00:00
- Post Title: Undead Horde (10tons game) - Font Edit/Change/Convert

MFT is a custom font file format made by 10tons for their games
[http://wiki.xentax.com/index.php/10tons_MFT](http://wiki.xentax.com/index.php/10tons_MFT)

Currently there are no tools for this format.
## Post #3
- Username: UtkuGARIP
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Feb 28, 2017 8:53 am
- Post datetime: 2022-11-28T20:59:39+00:00
- Post Title: Undead Horde (10tons game) - Font Edit/Change/Convert

> Reply from ikskoks ↑Tue Nov 29, 2022 4:16 am at Tue Nov 29, 2022 4:16 am
>
> 
MFT is a custom font file format made by 10tons for their games
http://wiki.xentax.com/index.php/10tons_MFT

Currently there are no tools for this format.

Thank you for the information, if I find a tool one day I will share it here.
## Post #4
- Username: UtkuGARIP
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Feb 28, 2017 8:53 am
- Post datetime: 2022-11-29T00:50:25+00:00
- Post Title: Undead Horde (10tons game) - Font Edit/Change/Convert

I found it here, does it work?

[https://github.com/metaflop/metaflop-www](https://github.com/metaflop/metaflop-www)
## Post #5
- Username: UtkuGARIP
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-11-29T16:55:37+00:00
- Post Title: Undead Horde (10tons game) - Font Edit/Change/Convert

I've searched whole source code for "mft", "MEG" or "10tons" keywords, but I didn't find anything useful.
I would say that metafont format and 10tons format are completely different from each other.
## Post #6
- Username: JamesNorman
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 17, 2022 6:04 pm
- Post datetime: 2022-12-19T12:06:13+00:00
- Post Title: Undead Horde (10tons game) - Font Edit/Change/Convert

Have you found out the solution?
## Post #7
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-12-19T12:41:20+00:00
- Post Title: Undead Horde (10tons game) - Font Edit/Change/Convert

> Reply from JamesNorman ↑Mon Dec 19, 2022 8:06 pm at Mon Dec 19, 2022 8:06 pm
>
> 
Have you found out the solution?

That depends what you mean by "solution". File format is known already (at least for version 6).
You can check it here [http://wiki.xentax.com/index.php/10tons_MFT](http://wiki.xentax.com/index.php/10tons_MFT)

So you can hex edit values (e.g. by some binary template).

You can also create a quickbms script to unpack and repack image data using info from the wiki.

Btw, version 7 used in "Undead Horde" may be a little different than the one from "Neon Chrome" that was researched by me.
