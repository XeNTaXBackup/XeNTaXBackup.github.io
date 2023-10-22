## Post #1
- Username: MEH AI
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jul 09, 2022 8:26 pm
- Post datetime: 2022-07-09T12:47:33+00:00
- Post Title: Dream League Soccer, xbnk, bnk,comentary.bnk

Hi!! I need some help please!
I did an extraction for my [commentary.bnk](https://www.mediafire.com/file/qasv6333toduim0/commentary.bnk/file) using this script: [score_hero_bnk.bms (0.2.3a)](http://aluigi.altervista.org/bms/score_hero_bnk.bms). and I get a lot of oggs files, I edited some of them but the probleme is that I can't repack them into the original xbnk. I tried with reimport.bat using the same script above but no luck.
that's what I got...
[Screenshot 2022-07-05 150711.png](https://xentaxbackup.github.io/file/22464_Screenshot 2022-07-05 150711.png)
## Post #2
- Username: MEH AI
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-07-10T10:40:06+00:00
- Post Title: Dream League Soccer, xbnk, bnk,comentary.bnk

Are you sure you're using reimport mode correctly?
You need to use the script on BNK file, not on OGG file.

Here's more info [http://aluigi.zenhax.com/papers/quickbms.txt](http://aluigi.zenhax.com/papers/quickbms.txt)

It should be something like this:

```
quickbms.exe -w -r score_hero_bnk.bms commentary.bnk output_folder
```
## Post #3
- Username: MEH AI
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jul 09, 2022 8:26 pm
- Post datetime: 2022-07-17T19:05:53+00:00
- Post Title: Dream League Soccer, xbnk, bnk,comentary.bnk

It works perfectly, thank uou sm.
## Post #4
- Username: MEH AI
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jul 09, 2022 8:26 pm
- Post datetime: 2022-07-17T19:24:13+00:00
- Post Title: Dream League Soccer, xbnk, bnk,comentary.bnk

I faced another problem with the same game, I want to export/view a database file .DAT with 78 9C EC as a header.
this is the file [teams.dat](https://www.mediafire.com/file/0tpda7giwd8tpyn/teams.dat/file)
please help!
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-07-17T23:05:47+00:00
- Post Title: Dream League Soccer, xbnk, bnk,comentary.bnk

> I want to export/view a database file .DAT with 78 9C EC as a header

This file is compressed with ZLIB.
You can use offzip to decompress this [http://aluigi.altervista.org/mytoolz/offzip.zip](http://aluigi.altervista.org/mytoolz/offzip.zip)

```
offzip.exe -a teams.dat
```
## Post #6
- Username: MEH AI
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jul 09, 2022 8:26 pm
- Post datetime: 2022-07-20T12:04:19+00:00
- Post Title: Dream League Soccer, xbnk, bnk,comentary.bnk

with Zlib I get another file 000000.dat but still cannot read
## Post #7
- Username: fun21turkiye
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu May 25, 2023 2:11 am
- Post datetime: 2023-05-24T18:21:06+00:00
- Post Title: Dream League Soccer, xbnk, bnk,comentary.bnk

> Reply from ikskoks ↑Sun Jul 10, 2022 6:40 pm at Sun Jul 10, 2022 6:40 pm
>
> 
Are you sure you're using reimport mode correctly?
You need to use the script on BNK file, not on OGG file.

Here's more info http://aluigi.zenhax.com/papers/quickbms.txt

It should be something like this:
Code: Select allquickbms.exe -w -r score_hero_bnk.bms commentary.bnk output_folder 
hi, i did the same thing but it didn't work, can you help me in more detail?
