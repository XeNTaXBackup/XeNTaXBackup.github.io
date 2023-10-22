## Post #1
- Username: Taita
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jan 12, 2006 8:00 pm
- Post datetime: 2006-01-12T12:11:32+00:00
- Post Title: Agatha Christie: And then there were none

Hello

I would like to edit the subtitles of the game, but I don't know how to. 

Please help me to unpack *.act files of this game.

Thanks, Taita
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-12T15:21:45+00:00
- Post Title: Agatha Christie: And then there were none

Please read the Game Request rules. We will need example files.
## Post #3
- Username: Taita
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jan 12, 2006 8:00 pm
- Post datetime: 2006-01-12T15:53:21+00:00
- Post Title: Agatha Christie: And then there were none

Sorry, I forgot it.

I packed some files from the game and uploaded here: [http://keptarhely.atw.hu/text.zip](http://keptarhely.atw.hu/text.zip)

I hope you can see it.

And thanks for helping...

Taita
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-12T19:27:57+00:00
- Post Title: Agatha Christie: And then there were none

This is the format:

```


[2] Rows


// For each row

[2] Size of total column bytes (TCB)

[TCB] Row text info (Strings XORed with $30), resulting in Tab-delimited column values and $0a terminated


```


I haven't seen any subtitles though. These files seem like tab-delimited tables converted to a format the game can read. The tables are about items, scripts to run etc.
## Post #5
- Username: Taita
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jan 12, 2006 8:00 pm
- Post datetime: 2006-01-13T08:05:13+00:00
- Post Title: Agatha Christie: And then there were none

Thanks. And don't you know is it possible to edit these files?
## Post #6
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2006-01-14T15:02:53+00:00
- Post Title: Agatha Christie: And then there were none

with this examples i have a question.

despite your knowledges to reverse those hex,how would it be possible to bruteforce a such file to find the xor value?
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-17T22:51:14+00:00
- Post Title: Agatha Christie: And then there were none

> Reply from Taita
>
> Thanks. And don't you know is it possible to edit these files?

Yes, it is possible of couse, I just have to write an extractor/importer. But that costs time, which at the moment, I have run short of. But I will do it nevertheless. Hopefully soon.  

@mambox: Brute force will in all probability not work to satisfaction.
## Post #8
- Username: Taita
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jan 12, 2006 8:00 pm
- Post datetime: 2006-01-19T10:11:47+00:00
- Post Title: Agatha Christie: And then there were none

ok, thanks!
## Post #9
- Username: Taita
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jan 12, 2006 8:00 pm
- Post datetime: 2006-02-07T08:57:06+00:00
- Post Title: Agatha Christie: And then there were none

Can I ask when it will be ready? When can you do it?
