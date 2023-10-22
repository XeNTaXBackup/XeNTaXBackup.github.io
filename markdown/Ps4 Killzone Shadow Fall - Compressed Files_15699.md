## Post #1
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2017-01-08T21:30:43+00:00
- Post Title: Ps4 Killzone Shadow Fall - Compressed Files?

hello! Finally I have access to some ps4 games so right now I'm analyzing the files from Killzone Shadow Fall but these files instead its predecessors from Kz3 and Kz2 are compressed.

I've seen this compression before. In the files there are text string but with incomplete letters in some cases, also there are indices with a weird order or incomplete patterns. so, I supposed that are compressed.

this is the header structure in all files with respective variants obviouslly. 
The original header of the file is RTTIBin<2.12> so again I suppose that this header represents the compression.



Here are some examples:

[http://www.mediafire.com/file/5uky77vxc ... racter.rar](http://www.mediafire.com/file/5uky77vxcc3wce6/assets_description.characters.hgh_engineer_hgh_engineer_character.rar)

[http://www.mediafire.com/file/sqq4da1v5 ... racter.rar](http://www.mediafire.com/file/sqq4da1v5gd91v8/assets_description.characters.hgh_medic_hgh_medic_character.rar)

[http://www.mediafire.com/file/5cw54krmv ... racter.rar](http://www.mediafire.com/file/5cw54krmvx9bx4z/assets_description.characters.kellan_child_kellan_child_character.rar)

[http://www.mediafire.com/file/gd39oldxm ... _lines.rar](http://www.mediafire.com/file/gd39oldxmz5oct2/localized.lumps.behind_enemy_lines_behind_enemy_lines.rar)

[http://www.mediafire.com/file/98becwe11 ... racter.rar](http://www.mediafire.com/file/98becwe11fae068/assets_description.characters.hgh_commando_hgh_commando_character.rar)

Someone can recognize and figure out the compression?

Thanks!
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2017-01-08T22:04:01+00:00
- Post Title: Ps4 Killzone Shadow Fall - Compressed Files?

How did you get these?
## Post #3
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2017-01-08T22:16:45+00:00
- Post Title: Ps4 Killzone Shadow Fall - Compressed Files?

> Reply from Gh0stBlade
>
> How did you get these?

I can obtain some decrypted games with firmware 1.76 and lower. ( not directly, I have to contact someone to obtain these backups, but I can obtain any game with no problem)
## Post #4
- Username: luxox18
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-01-09T01:54:28+00:00
- Post Title: Ps4 Killzone Shadow Fall - Compressed Files?

> Reply from luxox18
>
> Gh0stBlade wrote:How did you get these?

I can obtain some decrypted games with firmware 1.76 and lower. ( not directly, I have to contact someone to obtain these backups, but I can obtain any game with no problem)

quickbms script

```
get NAME basename
string NAME + .dec
idstring "\x83\xC1\x10\xCB"
get CHUNKSIZE long
get TSIZE longlong
getdstring HASH 0x10
set CCOUNT TSIZE
MATH CCOUNT / CHUNKSIZE
MATH CCOUNT += 1
for i = 0 < CCOUNT
get ZSIZE long
putarray 0 i ZSIZE
next i
savepos OFFSET
append
for i = 0 < CCOUNT
getarray ZSIZE 0 i
if TSIZE > CHUNKSIZE
clog NAME OFFSET ZSIZE CHUNKSIZE
math TSIZE -= CHUNKSIZE
else
clog NAME OFFSET ZSIZE TSIZE
endif
math OFFSET += ZSIZE
next i

```
