## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-10-02T18:39:34+00:00
- Post Title: HockeyDash

Hello guys, well this time I come with this old hockey game, I got this script made by fatduck but after try unpack files, I got error and can't unpack nothing, so maybe somebody can take a look into this format ERS? appreciate help and thanks for support guys.

> # Game: HockeyDash
>
>     # by Fatduck     Jun2010
>
>     # script for QuickBMS http://aluigi.org/papers.htm#quickbms
>
>     get DIRNAME basename
>
>     get NUMRES long
>
>     savepos OFSRES
>
>     for i = 0 < NUMRES
>
>        goto OFSRES
>
>        filexor 0x10
>
>        get UKN01 long
>
>        get SIZERES long
>
>        get UKN02 long
>
>        getdstring RESNAME 60
>
>        filexor ""
>
>        savepos OFSRES
>
>        set OUTNAME DIRNAME
>
>        string OUTNAME += /
>
>        string OUTNAME += RESNAME
>
>        log OUTNAME OFSRES SIZERES
>
>        math OFSRES += SIZERES
>
>     next i

Samples

[http://puu.sh/bWCC7/06775f70a7.7z](http://puu.sh/bWCC7/06775f70a7.7z)
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-10-02T19:28:33+00:00
- Post Title: HockeyDash

Script can be used only on ERes??.ers files. EData??.ers have different structure.
