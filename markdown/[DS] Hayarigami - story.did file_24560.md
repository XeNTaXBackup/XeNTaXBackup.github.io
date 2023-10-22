## Post #1
- Username: ytuD fo llaC
- Rank: beginner
- Number of posts: 23
- Joined date: Mon May 24, 2021 10:32 am
- Post datetime: 2021-10-02T17:15:39+00:00
- Post Title: [DS] Hayarigami - story.did file

Can someone help me find out what this file contains or does that would be much appreciated   

Sample file
[https://disk.yandex.com/d/WvLAJ8F2CS3CsQ](https://disk.yandex.com/d/WvLAJ8F2CS3CsQ)
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-10-03T18:10:14+00:00
- Post Title: [DS] Hayarigami - story.did file

This file is compressed with NitroSDK compression exactly the same as other files from this game.
So you can use script from this post to decompress data [viewtopic.php?p=177118#p177118](https://forum.xentax.com/viewtopic.php?p=177118#p177118)

After decompressing you'll get a file with big array of values, 
but I don't know what are they used for.

According to the file name it should be something related to game's story logic.

File structure looks like this:

```

num_of_entries *
{
   8 bytes - entry data
}
```
## Post #3
- Username: ytuD fo llaC
- Rank: beginner
- Number of posts: 23
- Joined date: Mon May 24, 2021 10:32 am
- Post datetime: 2021-10-03T19:16:49+00:00
- Post Title: [DS] Hayarigami - story.did file

Ok, thank you. I will remember this
