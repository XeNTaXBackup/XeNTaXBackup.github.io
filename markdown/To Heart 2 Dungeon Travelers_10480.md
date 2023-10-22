## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-01T12:57:41+00:00
- Post Title: To Heart 2: Dungeon Travelers

Name:Dungeon Travelers 2: Ouritsu Tokoshan to Mamono no Fuuin
aka To Heart 2: Dungeon Travelers 
Japanese Name:ダンジョントラベラーズ2 王立図書館とマモノの封印
website:[http://aquaplus.jp/dt2/](http://aquaplus.jp/dt2/)
game uses the header 
STFS 2012 STING
Here is an SFS quickbms script for this game

pkw quickbms script

```
savepos tmp
for i = 0 < files
goto tmp
get offset long
savepos tmp
goto offset
get name short
get type short
if type == 4
string name + .at3
else
string name + .vag
endif
get size long
savepos offset
log name offset size
next i

```

ZLB bms

```
goto 0xC
getdstring name 0x14
goto 0x28
get size long
get zsize long
clog name 0x34 zsize size

```


[Dungeon Travelers 2.7z](https://xentaxbackup.github.io/file/6441_Dungeon Travelers 2.7z)
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-06-01T13:08:03+00:00
- Post Title: To Heart 2: Dungeon Travelers

Nice work
