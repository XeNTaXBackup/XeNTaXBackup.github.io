## Post #1
- Username: masrawy2
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Jan 07, 2016 8:15 am
- Post datetime: 2023-03-03T00:41:50+00:00
- Post Title: decrypt pak file

Hello guys,
I have an android game with pak file 
I need to decrypt it, I have tried to use many QuickBMS scripts but doesn't work
could anyone help me please to decrypt it
## Post #2
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2023-03-03T04:02:50+00:00
- Post Title: decrypt pak file

try this.

The file pak is a container with a lot of files compressed with zlib

If you want to unpack without decompress use the sript below, but if you want unpack decompressed uses the second script

Unpack files compressed

```
# Dragonborn knight (.PAK)
# Version 0.1b

get unk long
get entries long
do
get zeros long
savepos temp
while zeros == 0
xmath temp "(temp -4)"
goto temp
xmath entries "(entries - 10)"
for rip = 1 to entries
getdstring name 0x40
get offset long
get unk long
get size long
get oneone long

log name offset size
next rip

```


Unpack files decompressed

```
# Dragonborn knight (.PAK)
# Version 0.1b 
# zlib decompressed

get unk long
get entries long
do
get zeros long
savepos temp
while zeros == 0
xmath temp "(temp -4)"
goto temp
xmath entries "(entries - 10)"

for rip = 1 to entries

getdstring name 0x40
get offset long
get unk long
get size long
get oneone long
get ZSIZE asize
math ZSIZE -= OFFSET

clog name offset size zsize
next rip

```
## Post #3
- Username: masrawy2
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Jan 07, 2016 8:15 am
- Post datetime: 2023-03-03T13:39:45+00:00
- Post Title: decrypt pak file

Thank you mate for help 
do you know how to import these files from same game 
(.skin,.skel ,mesh,anim)


 3d.rar
(10.85 KiB) Downloaded 19 times
## Post #4
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2023-03-03T15:02:56+00:00
- Post Title: decrypt pak file

Do you want to import theses specific files?
You can compress them, and uses reimport function from quickbms.
## Post #5
- Username: masrawy2
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Jan 07, 2016 8:15 am
- Post datetime: 2023-03-03T15:08:07+00:00
- Post Title: decrypt pak file

> Reply from Rabatini ↑Fri Mar 03, 2023 11:02 pm at Fri Mar 03, 2023 11:02 pm
>
> 
Do you want to import theses specific files?
You can compress them, and uses reimport function from quickbms.
they should be 3d models and animation files
do you know script could import them in noesis or something like it
## Post #6
- Username: masrawy2
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Jan 07, 2016 8:15 am
- Post datetime: 2023-03-04T11:17:51+00:00
- Post Title: decrypt pak file

> Reply from Rabatini ↑Fri Mar 03, 2023 12:02 pm at Fri Mar 03, 2023 12:02 pm
>
> 
try this.

The file pak is a container with a lot of files compressed with zlib

If you want to unpack without decompress use the sript below, but if you want unpack decompressed uses the second script

Unpack files compressed
Code: Select all# Script by Rabatini (Luke)
# Dragonborn knight (.PAK)
# Version 0.1b

get unk long
get entries long
do
get zeros long
savepos temp
while zeros == 0
xmath temp "(temp -4)"
goto temp
xmath entries "(entries - 10)"
for rip = 1 to entries
getdstring name 0x40
get offset long
get unk long
get size long
get oneone long

log name offset size
next rip


Unpack files decompressed
Code: Select all# Script by Rabatini (Luke)
# Dragonborn knight (.PAK)
# Version 0.1b 
# zlib decompressed

get unk long
get entries long
do
get zeros long
savepos temp
while zeros == 0
xmath temp "(temp -4)"
goto temp
xmath entries "(entries - 10)"

for rip = 1 to entries

getdstring name 0x40
get offset long
get unk long
get size long
get oneone long
get ZSIZE asize
math ZSIZE -= OFFSET

clog name offset size zsize
next rip

i have used the decompressed script with zlib but i think there a problem with the texture file(.tga)
it's doesn't working


 tex.rar
(135.44 KiB) Downloaded 16 times
## Post #7
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2023-03-04T12:30:38+00:00
- Post Title: decrypt pak file

> Reply from masrawy2 ↑Sat Mar 04, 2023 7:17 pm at Sat Mar 04, 2023 7:17 pm
>
> 
Rabatini wrote: ↑Fri Mar 03, 2023 12:02 pm
try this.

The file pak is a container with a lot of files compressed with zlib

If you want to unpack without decompress use the sript below, but if you want unpack decompressed uses the second script

Unpack files compressed
Code: Select all# Script by Rabatini (Luke)
# Dragonborn knight (.PAK)
# Version 0.1b

get unk long
get entries long
do
get zeros long
savepos temp
while zeros == 0
xmath temp "(temp -4)"
goto temp
xmath entries "(entries - 10)"
for rip = 1 to entries
getdstring name 0x40
get offset long
get unk long
get size long
get oneone long

log name offset size
next rip


Unpack files decompressed
Code: Select all# Script by Rabatini (Luke)
# Dragonborn knight (.PAK)
# Version 0.1b 
# zlib decompressed

get unk long
get entries long
do
get zeros long
savepos temp
while zeros == 0
xmath temp "(temp -4)"
goto temp
xmath entries "(entries - 10)"

for rip = 1 to entries

getdstring name 0x40
get offset long
get unk long
get size long
get oneone long
get ZSIZE asize
math ZSIZE -= OFFSET

clog name offset size zsize
next rip



i have used the decompressed script with zlib but i think there a problem with the texture file(.tga)
it's doesn't working
tex.rar

the texture is pvr.

is not the script, is the format of these tga, you will need help with someone is expert in graphics stuffs
