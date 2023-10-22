## Post #1
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2019-10-11T06:31:17+00:00
- Post Title: American Girls Premiere .MDT

Can anyone look into extracting these?: [https://archive.org/download/american-g ... GP3DAT.MDT](https://archive.org/download/american-girls-premiere_2nd-ed/American%20Girls%20Premiere%2C%20The%20-%202nd%20Edition%20%281998%29%28Learning%20Company%29%28Disc%201%20of%202%29%5BMac-PC%5D.iso/DATA%2FAMGP3DAT.MDT)
## Post #2
- Username: AlastairCook
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 12, 2019 3:12 am
- Post datetime: 2019-10-12T10:32:00+00:00
- Post Title: American Girls Premiere .MDT

> Reply from Puterboy1 ↑Fri Oct 11, 2019 2:31 pm at Fri Oct 11, 2019 2:31 pm
>
> 
Can anyone look into extracting these?: https://archive.org/download/american-g ... TA%2FAMGP3DAT.MDT

We used to play this game back in 2000-2001 when i was a young kid. now a days looking to find out similar educative games for my daughters.
## Post #3
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2019-10-12T20:33:13+00:00
- Post Title: American Girls Premiere .MDT

> Reply from AlastairCook ↑Sat Oct 12, 2019 6:32 pm at Sat Oct 12, 2019 6:32 pm
>
> 
We used to play this game back in 2000-2001 when i was a young kid. now a days looking to find out similar educative games for my daughters.

That is very nice but can you find a way of extracting these?
## Post #4
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2019-10-13T00:05:40+00:00
- Post Title: American Girls Premiere .MDT

> Reply from Puterboy1 ↑Sun Oct 13, 2019 4:33 am at Sun Oct 13, 2019 4:33 am
>
> 
AlastairCook wrote: ↑Sat Oct 12, 2019 6:32 pm
We used to play this game back in 2000-2001 when i was a young kid. now a days looking to find out similar educative games for my daughters.


That is very nice but can you find a way of extracting these?

Probably not; that account has all the looks of a spambot without actually having spammed yet.
## Post #5
- Username: AlastairCook
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 12, 2019 3:12 am
- Post datetime: 2019-10-13T14:37:16+00:00
- Post Title: American Girls Premiere .MDT

> Reply from Dinoguy1000 ↑Sun Oct 13, 2019 8:05 am at Sun Oct 13, 2019 8:05 am
>
> 
Puterboy1 wrote: ↑Sun Oct 13, 2019 4:33 am
AlastairCook wrote: ↑Sat Oct 12, 2019 6:32 pm
We used to play this game back in 2000-2001 when i was a young kid. now a days looking to find out similar educative games for my daughters.


That is very nice but can you find a way of extracting these?


Probably not; that account has all the looks of a spambot without actually having spammed yet.

Surely I am not a spammer dear. I am really looking for some good educative games for my kids. if you can help by suggesting some name that will be helpful too.
## Post #6
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2019-10-13T22:22:46+00:00
- Post Title: American Girls Premiere .MDT

> Reply from AlastairCook ↑Sun Oct 13, 2019 10:37 pm at Sun Oct 13, 2019 10:37 pm
>
> 
Dinoguy1000 wrote: ↑Sun Oct 13, 2019 8:05 am
Puterboy1 wrote: ↑Sun Oct 13, 2019 4:33 am


That is very nice but can you find a way of extracting these?


Probably not; that account has all the looks of a spambot without actually having spammed yet.


Surely I am not a spammer dear. I am really looking for some good educative games for my kids. if you can help by suggesting some name that will be helpful too.

I apologize for the misunderstanding, then. We've been having issues with spambots, and your account and posts up to that point tracked pretty closely with characteristics of a lot of them. That being said, it'd be better to create a separate topic for your request, rather than posting in mostly-unrelated topics.
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-10-14T00:18:35+00:00
- Post Title: American Girls Premiere .MDT

```
#quickbms script by chrrox
goto 0xC
idstring "The American Girls Premiere"
goto 0x4C
endian big
getdstring TAG 4
get NULL long
get TBLCOUNT long
get FILES long
for i = 0 < TBLCOUNT
getdstring TAG 4
get NULL long
get ENTCOUNT long
get ENTFILES long
#print "%TAG% %ENTCOUNT% %ENTFILES%"
next i
for i = 0 < FILES
getdstring TAG 4
get NULL long
get UNK long
get SIZE long
get OFFSET long
string NAME p "%08x." i
string NAME + TAG
#print "%TAG% %UNK|x% %SIZE|x% %OFFSET|x%"
log NAME OFFSET SIZE
next i

```

No clue about the actual data but this extracts it.
