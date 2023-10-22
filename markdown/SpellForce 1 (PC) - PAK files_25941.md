## Post #1
- Username: Spiritovod
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-10-27T20:40:53+00:00
- Post Title: SpellForce 1 (PC) - PAK files

My research on PAK archives --> [http://wiki.xentax.com/index.php/SpellForce_PAK](http://wiki.xentax.com/index.php/SpellForce_PAK)

My quickbms script for unpacking/repacking data --> [https://github.com/bartlomiejduda/Tools ... script.bms](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/SpellForce/SpellForce_PAK_script.bms)
## Post #2
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-10-27T22:14:34+00:00
- Post Title: SpellForce 1 (PC) - PAK files

@ikskoks: I'm sorry, but what's the point in creating quickbms script like this, will it work for reimport then? Otherwise it can be significantly simplified:

whole GET_STRING_AND_REVERSE_IT function can be replaced with:

```
string THE_STRING r THE_STRING # reversing string
```


and output path can be set like this:

```
string OUTPUT_FILE_PATH p "%s/%s/%s" ARCHIVE_NAME DIRECTORY_NAME FILE_NAME
```
## Post #3
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-10-28T18:47:12+00:00
- Post Title: SpellForce 1 (PC) - PAK files

To be honest I didn't know those tricks   
I'll try to refactor my code and I will post an update here. Thanks.
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-10-28T19:41:59+00:00
- Post Title: SpellForce 1 (PC) - PAK files

Ok, script has been updated:
[https://github.com/bartlomiejduda/Tools ... script.bms](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/SpellForce/SpellForce_PAK_script.bms)
