## Post #1
- Username: darkdragon83
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 26, 2016 5:51 pm
- Post datetime: 2016-04-26T10:29:02+00:00
- Post Title: TellTale The Wolf Among Us

hello,
for the wolf among us 

it is possible to change the _currentDirectory of ttarch file in this string?

"set.gameDataArchives = {
_currentDirectory .. "test.ttarch2" 

I would like to separate ttarch episode files in different episode folders because some files use the same file names for every episode and i can't just put the .landb file into the game directory (they overwrite each other).
For example the ui_episode_english.landb is in every Episode and this leads to problems then (showing the wrong text, doesn't show at all or skipping text).

thanks in advance
## Post #2
- Username: Melkor
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Dec 04, 2015 2:51 am
- Post datetime: 2016-04-29T22:44:09+00:00
- Post Title: TellTale The Wolf Among Us

> Reply from darkdragon83
>
> hello,
for the wolf among us 

it is possible to change the _currentDirectory of ttarch file in this string?

"set.gameDataArchives = {
_currentDirectory .. "test.ttarch2" 

I would like to separate ttarch episode files in different episode folders because some files use the same file names for every episode and i can't just put the .landb file into the game directory (they overwrite each other).
For example the ui_episode_english.landb is in every Episode and this leads to problems then (showing the wrong text, doesn't show at all or skipping text).

thanks in advance

You can repack them in .ttarch2 and put them back in the pack folder. this way your problem will be solved.

Use this:

```
c:\ttarchext.exe -b -V 7 54 c:\0.ttarch2 c:\folder_where_resides_langddb
```


"0.ttarch2" is the repacked ttarch2 - Change its name to whatever the original .ttarch2 was and put it in the pack folder (repalce the old one). the new .ttach2 file size will be bigger than the original so do not worry if you see that!
"folder_where_resides_langddb" is the folder where all the landb's are. put all the file that where in the original .ttarch2 + replace the landb files that you have translated.
