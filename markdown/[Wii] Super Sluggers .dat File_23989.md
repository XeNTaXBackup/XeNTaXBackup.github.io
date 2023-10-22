## Post #1
- Username: Flame1029
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jun 02, 2021 11:51 pm
- Post datetime: 2021-06-02T15:59:48+00:00
- Post Title: [Wii] Super Sluggers .dat File

Hey everyone, first post on this site. I'm not new to modding wii games and programming in general, but I AM new to reverse engineering. The issue here is I have extracted the contents of the game I want to mod, Mario Super Sluggers. The assets (cutscenes, sounds, etc) are fine and located in their own folders. The rest of the game is pretty much stored in one big .dat file. I'm aware that for Wii games, they usually just turn everything into .dat files to prevent them from being easily editable. I opened it up in a hex editor and I'm pretty sure it's a proprietary archive format, but I can't seem to figure out how to get the files out of it. Assuming the header wasn't stripped (if you can even do that without breaking the file?) it seems to be a .DB file in actuality. Is there any way I can go about writing an extractor for this file? I'm totally fine with doing all of the work, just need a point in the right direction.

Any help is much appreciated, thanks
[snip.png](https://xentaxbackup.github.io/file/20245_snip.png)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-06-02T17:53:17+00:00
- Post Title: [Wii] Super Sluggers .dat File

Hi, you can get some RE skills from those tutorials
[viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)
It is a good place to start learning.

If the file format is easy, you could write some quickbms script for example.
## Post #3
- Username: Flame1029
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jun 02, 2021 11:51 pm
- Post datetime: 2021-06-02T18:20:59+00:00
- Post Title: [Wii] Super Sluggers .dat File

> Reply from ikskoks ↑Thu Jun 03, 2021 1:53 am at Thu Jun 03, 2021 1:53 am
>
> 
Hi, you can get some RE skills from those tutorials
viewtopic.php?f=29&t=22266
It is a good place to start learning.

If the file format is easy, you could write some quickbms script for example.

Thanks so much! Will take a look at this now.
## Post #4
- Username: Flame1029
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jun 02, 2021 11:51 pm
- Post datetime: 2021-06-02T19:23:40+00:00
- Post Title: [Wii] Super Sluggers .dat File

Still having a good deal of issue with this. Not sure how the archive is even formatted as it's hard to tell. I'm not sure if the header was removed or not, as I assume this file was not a .DB like the magic number would lead me to believe. Here is a picture showing I know there is AT LEAST model data in here: 


snap2.png (12.77 KiB) Viewed 88 times



I know that there are TPL and GPL files in here at least, as I can see some file names. I don't seem to have any luck finding a file directory list near the start or end of the file. Can anyone help me with this?

UPDATE:

I found the offsets of several "db" files:

```
4AA61400
4AA63E00
27D705E0
27D70880
2A9EBB40
2A9EBC00
```


Still unsure how to actually get the files out of this archive
