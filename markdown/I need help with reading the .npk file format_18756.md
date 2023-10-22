## Post #1
- Username: dangtuan9x
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Sep 01, 2018 1:51 pm
- Post datetime: 2018-09-01T06:04:27+00:00
- Post Title: I need help with reading the .npk file format

In the zip file is the .npk file that I do not know how to open
I need help
It is taken from the game data file of Rules of Survival
help me 
link file[https://drive.google.com/open?id=16gjpu ... 39ymWkiIsQ](https://drive.google.com/open?id=16gjpupbW3TkTjFJhr1zqfl39ymWkiIsQ)
## Post #2
- Username: hyndai
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Jun 04, 2008 4:55 am
- Post datetime: 2020-02-04T22:59:35+00:00
- Post Title: I need help with reading the .npk file format

There are bms script for that : 

[https://aluigi.altervista.org/bms/nxpk.bms](https://aluigi.altervista.org/bms/nxpk.bms)

CeeYa.
## Post #3
- Username: CDHacker
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Oct 07, 2020 12:16 pm
- Post datetime: 2020-10-11T08:28:46+00:00
- Post Title: I need help with reading the .npk file format

> Reply from hyndai ↑Wed Feb 05, 2020 6:59 am at Wed Feb 05, 2020 6:59 am
>
> 
There are bms script for that : 

https://aluigi.altervista.org/bms/nxpk.bms

CeeYa.

Hello. Can this same script be used to reimport the modified files? If yes could you tell me how. I am new to modding.
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-10-11T14:51:12+00:00
- Post Title: I need help with reading the .npk file format

Yeah, in most cases it can be used for reimport.
Everything is explained in documentation [https://aluigi.altervista.org/papers/quickbms.txt](https://aluigi.altervista.org/papers/quickbms.txt)
## Post #5
- Username: CDHacker
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Oct 07, 2020 12:16 pm
- Post datetime: 2020-10-11T18:09:38+00:00
- Post Title: I need help with reading the .npk file format

> Reply from ikskoks ↑Sun Oct 11, 2020 10:51 pm at Sun Oct 11, 2020 10:51 pm
>
> 
Yeah, in most cases it can be used for reimport.
Everything is explained in documentation https://aluigi.altervista.org/papers/quickbms.txt

but it doesn't that's the issue. it says "script invalid for reimporting, it uses MEMORY_Files." Any solution?
## Post #6
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-10-11T18:15:31+00:00
- Post Title: I need help with reading the .npk file format

> if the original archive uses complex encryptions that require the
>
>   usage of MEMORY_FILEs to perform temporary decryption, then it's NOT
>
>   supported and the same is valid for chunked content (like those
>
>   scripts that use the command Append)
>
>   From version 0.6.6, QuickBMS has an experimental mode for reimporting
>
>   chunked files, it works very well with files saved directly to disk
>
>   and less well with those that use MEMORY_FILEs (most of my scripts).
>
>   In my opinion this feature is great but don't expect too much, with
>
>   some scripts you can have success but many others may not work.

I would suggest to use reimport2 mode or re-write the script to not use memory files.
