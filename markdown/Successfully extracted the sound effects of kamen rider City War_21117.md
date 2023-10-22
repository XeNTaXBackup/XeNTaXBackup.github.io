## Post #1
- Username: bymutou
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Nov 08, 2018 9:57 am
- Post datetime: 2019-09-14T05:35:03+00:00
- Post Title: Successfully extracted the sound effects of kamen rider City War

I know how to extract the sound effects of kamen rider City War, but I don't know how to make batches.
Request help to make a batch of bms files
## Post #2
- Username: bymutou
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Nov 08, 2018 9:57 am
- Post datetime: 2019-09-14T05:36:59+00:00
- Post Title: Successfully extracted the sound effects of kamen rider City War

Just delete the characters in front of oggs and modify the suffix to .ogg to play, but there are too many files, I don't know how to make batches.
[1.png](https://xentaxbackup.github.io/file/16740_1.png)
## Post #3
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-09-14T10:02:33+00:00
- Post Title: Successfully extracted the sound effects of kamen rider City War

If all of the files have the same length header to remove, you can use the Simple Cutter feature in VGMToolbox.  This can also add an extension to the output files automatically.
## Post #4
- Username: bymutou
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Nov 08, 2018 9:57 am
- Post datetime: 2019-09-14T10:38:11+00:00
- Post Title: Successfully extracted the sound effects of kamen rider City War

Thank you very much, my friend, helped me a lot! !
## Post #5
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2019-09-14T19:36:39+00:00
- Post Title: Successfully extracted the sound effects of kamen rider City War

Just to post, if you were looking for a BMS adaptation, it would work like so:

```
set OFFSET long 0x55
get ARKSIZE asize
xmath SIZE "ARKSIZE - 0x55"
set NAME string ""
string NAME p "%s.ogg" BASENAME
log NAME OFFSET SIZE

```


That should hopefully work.. just went off that screenshot above .
## Post #6
- Username: wjj162446
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jul 10, 2019 7:01 pm
- Post datetime: 2023-10-19T09:18:35+00:00
- Post Title: Successfully extracted the sound effects of kamen rider City War

Is there anybody know how to extract Kamen Rider Gotchard File game?
