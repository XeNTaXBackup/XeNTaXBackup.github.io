## Post #1
- Username: hgdagon
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Oct 07, 2014 10:39 am
- Post datetime: 2016-02-23T06:54:57+00:00
- Post Title: [REQ] Zanzarah: Mailing Monters Dat (Un)Packer

Hi. I wanted to translate this little game into English. It's a freeware promo thing for Zanzarah: The Hidden Portal, albeit only in German. To do that, I'd probably need both a packer (or the game might work with an unpacked data, but I just wanna play safe) and an unpacker. Could anyone, please, help with that? The dat file is [here](https://cloud.mail.ru/public/Agit/JSEG4oUnL).
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-23T15:07:29+00:00
- Post Title: [REQ] Zanzarah: Mailing Monters Dat (Un)Packer

The format looks very simple. Are there any other files? Strange how there's no file count. Maybe the devs hardcoded it.
## Post #3
- Username: hgdagon
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Oct 07, 2014 10:39 am
- Post datetime: 2016-02-23T19:51:48+00:00
- Post Title: [REQ] Zanzarah: Mailing Monters Dat (Un)Packer

> Reply from Gh0stBlade
>
> The format looks very simple. Are there any other files? Strange how there's no file count. Maybe the devs hardcoded it.
There are no other dat files, if that's what you mean.
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-02-23T20:24:58+00:00
- Post Title: [REQ] Zanzarah: Mailing Monters Dat (Un)Packer

```
# Written by Ekey (h4x0r)
# 
# script for QuickBMS http://quickbms.aluigi.org

idstring "Zanzarah\x20"
goto 0x50
get BASEOFF long
get VERSION long
set FILES long BASEOFF
math FILES -= 584
math FILES /= 96

for i = 0 < FILES
    get ZERO1 long
    get ZERO2 long
    getdstring NAME 80
    get OFFSET long
    get SIZE long
    log NAME OFFSET SIZE
next i
```
## Post #5
- Username: hgdagon
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Oct 07, 2014 10:39 am
- Post datetime: 2016-02-25T06:49:17+00:00
- Post Title: [REQ] Zanzarah: Mailing Monters Dat (Un)Packer

Thanks. Also, I just checked, and, yup, I need a packer. The game doesn't start with unpacked data...
