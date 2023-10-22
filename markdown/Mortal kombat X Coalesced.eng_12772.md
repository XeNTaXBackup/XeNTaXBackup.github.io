## Post #1
- Username: LinkOFF
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Sep 08, 2014 7:32 am
- Post datetime: 2015-04-15T19:47:06+00:00
- Post Title: Mortal kombat X "Coalesced.eng"

Hi! Is there anybody who can make coder/decoder for the Coalesced files please?
Sample (Coalesced.eng): [http://rghost.ru/6XZw9QXmp](http://rghost.ru/6XZw9QXmp)
## Post #2
- Username: BANDIT
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Sep 13, 2011 4:19 am
- Post datetime: 2015-04-15T23:06:54+00:00
- Post Title: Mortal kombat X "Coalesced.eng"

Try this tool: [http://www.mediafire.com/download/bc2t2 ... ice_AES.7z](http://www.mediafire.com/download/bc2t22asks3t2z2/Injustice_AES.7z)
## Post #3
- Username: ponaromixxx
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Jul 17, 2014 11:52 am
- Post datetime: 2015-04-16T19:43:20+00:00
- Post Title: Mortal kombat X "Coalesced.eng"

1) Encoder: reset the code

Author: aluigi

```
get SIZE asize
get NAME filename
log NAME 0 SIZE
```

2) Unpack: Take the file on which dropped cipher

Author: swuforce

```
get unk long
do
get namesize long
math namesize ^= 0xffffffff
math namesize *= 2
get name unicode
get size long
math size ^= 0xffffffff
math size *= 2
savepos offset
log name offset size
getdstring data size
get null short
savepos pos
while pos < asize
```

3) Repack

```
get cname filename
string cname += "_NEW"
log MEMORY_FILE 0 0
get unk long
put unk long MEMORY_FILE
do
get namesize long
put namesize long MEMORY_FILE
math namesize ^= 0xffffffff
xmath namesize "namesize * 2 + 2"
savepos nameoff
getdstring name namesize
putdstring name namesize MEMORY_FILE
goto nameoff
get name unicode
get size long
math size ^= 0xffffffff
xmath size "size * 2 + 2"
getdstring data size
open FDSE name 1
get asize asize 1
set size asize
math size /= 2
math size ^= 0xffffffff
put size long MEMORY_FILE
append
log MEMORY_FILE 0 asize 1
append
get msize asize MEMORY_FILE
goto msize MEMORY_FILE
put 0 short MEMORY_FILE
savepos pos
while pos < csize
get size asize MEMORY_FILE
log cname 0 size MEMORY_FILE
```



Author: spider91

And here is another script to unpack only

```
math FILES /= 2
for i = 0 < FILES
   get NAME_SZ long
   math NAME_SZ *= -2
   get NAME unicode
   get SIZE long
   math SIZE *= -2
   savepos OFFSET
   log NAME OFFSET SIZE
   math OFFSET += SIZE
   goto OFFSET
next i
```



2) Unpack: settings Coalesced.ini

Author: n97t7f7b57f

```
math FILES /= 2
for i = 0 < FILES
get NSIZE long
getdstring NAME NSIZE
get SIZE long
savepos OFFSET
log NAME OFFSET SIZE
math OFFSET += SIZE
goto OFFSET
next i
```


           Scripts update!!!!!!
## Post #4
- Username: LinkOFF
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Sep 08, 2014 7:32 am
- Post datetime: 2015-04-16T23:24:14+00:00
- Post Title: Mortal kombat X "Coalesced.eng"

ponaromixxx, thanks
## Post #5
- Username: goldenboy78
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Nov 23, 2014 9:07 am
- Post datetime: 2015-04-19T00:05:58+00:00
- Post Title: Mortal kombat X "Coalesced.eng"

How to reimport the two folders $EngineDir$ and $GameDir$ after extracting Coalesced.eng ?

It doesn't work for me... 
In quickbms command line I select the repack script, then I choose the two folders "$EngineDir$" "$GameDir$" and I choose same output folder where the Coalesced.eng was extracted.

After that it tells me.:
error ins src\file.c line 220:fdnum_open()
Error:Permission denied

Anyone can help?

Greets
## Post #6
- Username: ponaromixxx
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Jul 17, 2014 11:52 am
- Post datetime: 2015-04-19T14:30:25+00:00
- Post Title: Mortal kombat X "Coalesced.eng"

> Reply from goldenboy78
>
> How to reimport the two folders $EngineDir$ and $GameDir$ after extracting Coalesced.eng ?

It doesn't work for me... 
In quickbms command line I select the repack script, then I choose the two folders "$EngineDir$" "$GameDir$" and I choose same output folder where the Coalesced.eng was extracted.

After that it tells me.:
error ins src\file.c line 220:fdnum_open()
Error:Permission denied

Anyone can help?

Greets


Here are promptly inserted in a hurry!

Вот накидал на скорую руку!

	English

1) Throw our Coalesced.ENG in Original-Output
2) Press the Extract.bat
3) Start to edit something that Extract\$EngineDir$\Localization\ENG and Extract\$GameDir$\Localization\eng
4) How PUSH finished Repack.bat and repacked all your file is in the Original-Output

If you need a different file such Coalesced.RUS or Coalesced.FRA etc, then open a text document Extract.bat and Repack.bat and replace them all with Coalesced.ENG on Coalesced.RUS or any other.


	Russian

1) Закинуть наш Coalesced.ENG в Original-Output
2) Нажать Extract.bat
3) Начинаем редактировать то что в Extract\$EngineDir$\Localization\ENG  и  Extract\$GameDir$\Localization\eng
4) Как закончил жми Repack.bat и все твой файл перепакован, находится в Original-Output

Если надо другой файл например Coalesced.RUS или Coalesced.FRA и т.д, тогда открой текстовым документом Extract.bat и Repack.bat и замени в них везде с Coalesced.ENG на Coalesced.RUS или какой другой.


[https://yadi.sk/d/G4dFQEmwg6LAi](https://yadi.sk/d/G4dFQEmwg6LAi)
## Post #7
- Username: goldenboy78
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Nov 23, 2014 9:07 am
- Post datetime: 2015-04-20T02:25:56+00:00
- Post Title: Mortal kombat X "Coalesced.eng"

Thanks very much ponaromixxx, it works now!
## Post #8
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2015-05-16T23:31:06+00:00
- Post Title: Mortal kombat X "Coalesced.eng"

> Reply from ponaromixxx
>
> goldenboy78 wrote:How to reimport the two folders $EngineDir$ and $GameDir$ after extracting Coalesced.eng ?

It doesn't work for me... 
In quickbms command line I select the repack script, then I choose the two folders "$EngineDir$" "$GameDir$" and I choose same output folder where the Coalesced.eng was extracted.

After that it tells me.:
error ins src\file.c line 220:fdnum_open()
Error:Permission denied

Anyone can help?

Greets


Here are promptly inserted in a hurry!

Вот накидал на скорую руку!

	English

1) Throw our Coalesced.ENG in Original-Output
2) Press the Extract.bat
3) Start to edit something that Extract\$EngineDir$\Localization\ENG and Extract\$GameDir$\Localization\eng
4) How PUSH finished Repack.bat and repacked all your file is in the Original-Output

If you need a different file such Coalesced.RUS or Coalesced.FRA etc, then open a text document Extract.bat and Repack.bat and replace them all with Coalesced.ENG on Coalesced.RUS or any other.


	Russian

1) Закинуть наш Coalesced.ENG в Original-Output
2) Нажать Extract.bat
3) Начинаем редактировать то что в Extract\$EngineDir$\Localization\ENG  и  Extract\$GameDir$\Localization\eng
4) Как закончил жми Repack.bat и все твой файл перепакован, находится в Original-Output

Если надо другой файл например Coalesced.RUS или Coalesced.FRA и т.д, тогда открой текстовым документом Extract.bat и Repack.bat и замени в них везде с Coalesced.ENG на Coalesced.RUS или какой другой.


https://yadi.sk/d/G4dFQEmwg6LAi

I could not repack
I do not have anything repack.bat click on.
