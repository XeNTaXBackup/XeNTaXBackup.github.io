## Post #1
- Username: jenny1367
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Aug 19, 2021 3:10 am
- Post datetime: 2022-11-27T19:03:46+00:00
- Post Title: 忘川风华录 encryption

Someone did it here [https://tieba.baidu.com/p/7274917616](https://tieba.baidu.com/p/7274917616), however they don't want to share the tool. they said there are multiple packs in each bundle and they made a tool after splitting the files. here is a sample [https://drive.google.com/file/d/1LNhNVa ... sp=sharing](https://drive.google.com/file/d/1LNhNVaC_Au7EY4M0R-xN87KcHyTUJW42/view?usp=sharing), thanks in advance for any help!
## Post #2
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-11-29T11:23:25+00:00
- Post Title: 忘川风华录 encryption

It is not particularly difficult. The header is set to UnityFS as usual:

remove one byte of 0x00 that exists after 0x43, which is the marker for lz4 information, so that it becomes 0x43 0x1E.
Rewrite the file size information is correct, and change the size up to the lz4 information to the correct size as well.
Now it is ready to load in AS.

I also found information on the tool by looking it up in PM03FS. I haven't actually tried it, so I don't know if this tool will decrypt...
## Post #3
- Username: jenny1367
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Aug 19, 2021 3:10 am
- Post datetime: 2022-11-29T22:24:44+00:00
- Post Title: 忘川风华录 encryption

> Reply from einherjar007 ↑Tue Nov 29, 2022 7:23 pm at Tue Nov 29, 2022 7:23 pm
>
> 
It is not particularly difficult. The header is set to UnityFS as usual:

remove one byte of 0x00 that exists after 0x43, which is the marker for lz4 information, so that it becomes 0x43 0x1E.
Rewrite the file size information is correct, and change the size up to the lz4 information to the correct size as well.
Now it is ready to load in AS.

I also found information on the tool by looking it up in PM03FS. I haven't actually tried it, so I don't know if this tool will decrypt...

Thanks a lot! Managed to find another tool for it, I only searched the game's name but not the unique header before.. thanks again ><
