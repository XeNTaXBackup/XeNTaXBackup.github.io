## Post #1
- Username: robotnick
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Feb 17, 2008 8:52 pm
- Post datetime: 2014-12-08T15:13:59+00:00
- Post Title: Risk of Rain

I'm trying to translate Risk of Rain game but can't find a way to extract data.win content. I've tried with tools like Gamemaker Decompiler and yoyogames script for quickbms but that did'nt work.

Thanks for your help  (sorry for my bad English)

[data.win](http://www.filedropper.com/data_7)
## Post #2
- Username: mertay
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Nov 21, 2014 5:59 am
- Post datetime: 2014-12-08T17:59:47+00:00
- Post Title: Risk of Rain

> Reply from robotnick
>
> I'm trying to translate Risk of Rain game but can't find a way to extract data.win content. I've tried with tools like Gamemaker Decompiler and yoyogames script for quickbms but that did'nt work.

Thanks for your help  (sorry for my bad English)

data.win

It's working. [http://aluigi.altervista.org/papers/bms/yoyogames.bms](http://aluigi.altervista.org/papers/bms/yoyogames.bms)
## Post #3
- Username: robotnick
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Feb 17, 2008 8:52 pm
- Post datetime: 2014-12-08T18:11:34+00:00
- Post Title: Risk of Rain

> Reply from mertay
>
> robotnick wrote:I'm trying to translate Risk of Rain game but can't find a way to extract data.win content. I've tried with tools like Gamemaker Decompiler and yoyogames script for quickbms but that did'nt work.

Thanks for your help  (sorry for my bad English)

data.win

It's working. http://aluigi.altervista.org/papers/bms/yoyogames.bms

No it's not working. I can find the game text in data.win but not in extracted files. They are useless.
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2014-12-08T19:32:10+00:00
- Post Title: Risk of Rain

the strings chunk is ignored:

```

```


you could start by dumping CHUNK_SIZE and see if it can use the DUMP_ENTRIES function
## Post #5
- Username: robotnick
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Feb 17, 2008 8:52 pm
- Post datetime: 2014-12-08T21:28:40+00:00
- Post Title: Risk of Rain

> Reply from WRS
>
> the strings chunk is ignored:
Code: Select allelif CHUNK_NAME == "STRG"


you could start by dumping CHUNK_SIZE and see if it can use the DUMP_ENTRIES function

Thanks for your help but I don't know how to do that. I don't have programming skills
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-08T23:34:13+00:00
- Post Title: Risk of Rain

replace
    elif CHUNK_NAME == "STRG"

by

```
        math GET_OFFSET = 0
        math GET_NAME   = 1
        math GET_NAME2  = 0
        math GET_SIZE   = 0
        callfunction DUMP_ENTRIES 1
```

will produce many small files containing one zero terminated string only, like
audio_is_playing
pref_name_client
artifact_command
or 
m_update_player

(on extraction filenames have to be replaced manually because some contain a binary 1)

if you add a line in the DUMP_ENTRIES function:
if GET_NAME != 0
 goto NAME_OFF
 get NAME string
string Name i

you'll get text like this one:
A few hours after my crash, I finally decided to investigate the nearby area. As I moved past a particularly large mound of sand, it began to shift and roar. From it erupted a giant crab-like beast,

without renaming required.

But changing the script to get translated text back into data.win, that's not a 15 minutes job.
## Post #7
- Username: robotnick
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Feb 17, 2008 8:52 pm
- Post datetime: 2014-12-09T21:15:48+00:00
- Post Title: Risk of Rain

Thank you shakotay. I'll try to contact the game developers instead
