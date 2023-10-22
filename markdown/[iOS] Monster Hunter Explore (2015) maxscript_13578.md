## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-11-26T20:02:52+00:00
- Post Title: [iOS] Monster Hunter Explore (2015) maxscript

Hi guys! Here's maxscript to import Monster Hunter Explore (2015) iOS models with bones+weights (3ds max 2009-2014). 
Game isn't a AAA project with awesome HQ models, but if anyone will find it useful - good:)
Wiki page [http://monsterhunter.wikia.com/wiki/Mon ... er_Explore](http://monsterhunter.wikia.com/wiki/Monster_Hunter_Explore)
Use Sectus's ArcTool too extract models/textures


[Monster_Hunter_Explore.7z](https://xentaxbackup.github.io/file/10079_Monster_Hunter_Explore.7z)
## Post #2
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2019-07-02T19:04:57+00:00
- Post Title: [iOS] Monster Hunter Explore (2015) maxscript

What version or command did you use with Arctool to extract the .ARC?

I keep getting:
RE6 tex format selected.
Single-file mode.
Could not determine compatible file type.
## Post #3
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-10-23T04:02:48+00:00
- Post Title: [iOS] Monster Hunter Explore (2015) maxscript

sorry necro post, but recent result.

I was interested in this game and tried to load it. Since python script was no longer functioning due to the abolition of the old library, I was fixed and decompressed arcc.

And script read mod. There was no problem with the mesh, but the weight was broken. Also, textures will probably not be converted correctly now.
I've tried various tools and options, but tex produces clearly corrupted results.

4 years have passed since the script was provided, so the format specification may have changed significantly.
I wanted to try importing lmt using MT FrameWork script, but I can't import it because the format is different from other lmt files.
The same applies to mod.
## Post #4
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-11-21T13:50:32+00:00
- Post Title: [iOS] Monster Hunter Explore (2015) maxscript

finally, I was able to create my own bms script. Decrypt the arc file. I couldn't extract it with Arctool, but it can be extract with Kuriimu!
This is my second reverse experience. It's cheap code, but it certainly works. If you get an error in Append, enter a.

```
get SIZE asize

get name basename
set decname string "dec\\"
set ext string ".arc"

string decname + name
string decname + ext
Log "decname" 0 0x08

encryption blowfish "kaseoa nkaeka;eawf3"
math SIZE - 0x08

Append
Log "decname" 0x08 SIZE
Append
```


However, the script created by zaramot can load the mesh, but the weights will be damaged.
The result is the same for both iOS and Android. But it's great to get the mesh!
sadly, This game is about to end. Thanks to CAPCOM and this game for providing a great game...
