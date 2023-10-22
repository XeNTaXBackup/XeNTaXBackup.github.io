## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-01T19:09:22+00:00
- Post Title: Star Wars: Episode III: Revenge of the Sith *.hsh/*.pk2

Hi everybody!
I just wrote a script that extracts the files from the two big PK2 containers using the HSH information file. Use the script on the HSH.
Hope I could help someone with this. 

```
open FDSE "PS2PAK_1.PK2" 2

get FSIZE asize
DO
    getCT NAME string 0x20
    getDstring FILE 1
    get DUMMY byte
    getCT SIZE string 0x20
    set NUM SIZE
    callfunction STR2NUM 1
    set SIZE NUM
    getCT OFFSET string 0x0D
    set NUM OFFSET
    callfunction STR2NUM 1
    set OFFSET NUM
    get DUMMY byte
    savepos MYOFF
    if FILE == "0"
        log NAME OFFSET SIZE 1
    elseif FILE == "1"
        log NAME OFFSET SIZE 2
    endif
WHILE MYOFF != FSIZE

startfunction STR2NUM
    set TONUM 0
    strlen l NUM
    for i = 0 < l
        set EXP l
        math EXP -= i
        math EXP -= 1
        set B 0xA
        math B p EXP
        getVarChr T NUM i
        math T -= 0x30
        math T *= B
        math TONUM += T
    next i
    set NUM TONUM
endfunction
```
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2010-10-03T03:33:11+00:00
- Post Title: Star Wars: Episode III: Revenge of the Sith *.hsh/*.pk2

Thanks for sharing your script but how do you use it?
Does it do the same thing as the tool Jockel released [HERE](http://www.ps3news.com/forums/ps2-dvd-rip-news/star-wars-episode-iii-ext-reb-relinker-1311.html) about 5 years ago?
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-03T08:12:19+00:00
- Post Title: Star Wars: Episode III: Revenge of the Sith *.hsh/*.pk2

This is a QuickBMS script. Save it in a text file as *.bms and open with QuickBMS ([http://aluigi.altervista.org/papers.htm#quickbms](http://aluigi.altervista.org/papers.htm#quickbms))
I don't know about the other tools.
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2010-10-08T05:18:33+00:00
- Post Title: Star Wars: Episode III: Revenge of the Sith *.hsh/*.pk2

> Reply from AlphaTwentyThree
>
> This is a QuickBMS script
Okay Thanks, i wasn't 100% sure.   

Jockel's tool can extract, rebuild and relink the files.
## Post #5
- Username: ginev
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Feb 15, 2016 6:53 pm
- Post datetime: 2016-10-05T19:06:46+00:00
- Post Title: Star Wars: Episode III: Revenge of the Sith *.hsh/*.pk2

Ok i extracted the pk2 files.Now how to open the pak files since i think this files contain the models.Waht to do now?
## Post #6
- Username: StrangeUsernames
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jan 09, 2020 11:34 am
- Post datetime: 2020-01-11T02:13:02+00:00
- Post Title: Star Wars: Episode III: Revenge of the Sith *.hsh/*.pk2

Can you share with me all the textures and models you got.  How did you get them? I tried using NinjaRipper running pcsx2 and don't want to go through the hassel.
