## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-10-04T18:14:20+00:00
- Post Title: Kritika Online

Hello how are you, well today I try unpack files from this game, and got error with script, so well maybe somebody can take look into format? the format are in .alp, so well maybe somebody can support it? many thanks for all guys, really grateful for help.

BMS

> #Kritika Online alp extractor
>
> #Quickbms script by chrrox
>
> comtype MSF
>
> get TSIZE asize
>
> idstring "GKPA"
>
> get VERSION short
>
> get FTABLE long
>
> goto FTABLE
>
> Do
>
> filexor ""
>
> savepos TMP
>
> get TBLSIZE long
>
> savepos TMP
>
> filexor "\xDF\x97\x6F\x03" TMP
>
> getdstring MAGIC 4
>
> #print "%MAGIC%"
>
> if MAGIC == "DGKP"
>
> getdstring NULL 0xA
>
> get NSIZE short
>
> math NSIZE * 2
>
> getdstring UNAME NSIZE
>
> set DIRNAME unicode UNAME
>
> else
>
> getdstring NULL 0x7
>
> get OFFSET long
>
> get SIZE long
>
> get ZSIZE long
>
> getdstring NULL 0xC
>
> get NSIZE short
>
> math NSIZE * 2
>
> getdstring UNAME NSIZE
>
> set NAME2 unicode UNAME
>
> set NAME DIRNAME
>
> string NAME + \
>
> string NAME + NAME2
>
> filexor "\xDF\x97\x6F\x03" OFFSET
>
> clog NAME OFFSET ZSIZE SIZE
>
> endif
>
> While TMP < TSIZE
[http://puu.sh/bZ66K/f874ebc50c.7z](http://puu.sh/bZ66K/f874ebc50c.7z)
## Post #2
- Username: skylab
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-10-05T00:01:51+00:00
- Post Title: Kritika Online

looks like they split the archive into 2 pieces a file table and the data.
xor key seems to be the same. yeah its definitely the same.
Got a file extracted.
[https://www.sendspace.com/file/4tfynn](https://www.sendspace.com/file/4tfynn)

client link

[http://kritika-dl-gameon.nefficient.jp/ ... 141001.exe](http://kritika-dl-gameon.nefficient.jp/kritika/client/KRITIKA_JP_20141001.exe)

[http://aluigi.altervista.org/papers/bms ... ritika.bms](http://aluigi.altervista.org/papers/bms/others/kritika.bms)
