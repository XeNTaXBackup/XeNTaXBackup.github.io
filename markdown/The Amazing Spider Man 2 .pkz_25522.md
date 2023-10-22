## Post #1
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-07-09T06:33:20+00:00
- Post Title: The Amazing Spider Man 2 .pkz

This game's file structure is similar to Spider Man series with pkz archives, but a bit different. Can anyone take a look into this. Hope someone can make a unpacker/packer for it, thanks.
[Antenna_Main.rar](https://xentaxbackup.github.io/file/7560_Antenna_Main.rar)
## Post #2
- Username: SerJar
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 02, 2020 1:10 am
- Post datetime: 2022-06-12T12:05:33+00:00
- Post Title: The Amazing Spider Man 2 .pkz

Hey guys, I really need help with decompressing BaseSpiderMan.pkz file

I tried to do it myself by using this script from chroxx that he made for SMEOT

```
comtype zlib_noerror
get idstring long
get chunksize long
get baseoff long
get unkown long
get files long
get totalzsize long
get totalsize long
get name filename
set offset baseoff
get NAME basename
string NAME += ".pak"
savepos tmp
for i = 0 < files

if i == 0
  get size long
else
  goto tmp
  get old long
  savepos tmp
  get size long
  math size - old
endif

if totalzsize >= 0x8000
  set zsize 0x8000
else
  set zsize totalzsize
endif

clog MEMORY_FILE offset zsize size
append
log name 0 size MEMORY_FILE
append
math offset += 0x8000
math totalzsize - 0x8000

next i
```


This script worked with TASM1 files, but doesn't work with TASM2 because TASM2 has different file structure.

I edited it and this is how it looks, but still doesn't work

```
comtype zlib_noerror
get idstring long
get chunksize long
get baseoff long
get unkown long
get files long
get totalzsize long
get totalsize long
get name filename
set offset baseoff
get NAME basename
string NAME += ".pak"
savepos tmp
for i = 0 < files

if i == 0
  get size long
else
  goto tmp
  get old long
  savepos tmp
  get size long
  math size - old
endif

if totalzsize >= 0x18000
  set zsize 0x18000
else
  set zsize totalzsize
endif

clog MEMORY_FILE offset zsize size
append
log name 0 size MEMORY_FILE
append
math offset += 0x18000
math totalzsize - 0x18000
```


Can anyone help me, please?

Here's the file: [https://www.mediafire.com/file/si17dsfq ... n.zip/file](https://www.mediafire.com/file/si17dsfqtg6b2y7/BaseSpiderMan.zip/file)
## Post #3
- Username: SerJar
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 02, 2020 1:10 am
- Post datetime: 2022-06-12T12:12:53+00:00
- Post Title: The Amazing Spider Man 2 .pkz

also tried to use offzip but it decompresses corrupted file
## Post #4
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-06-12T15:48:54+00:00
- Post Title: The Amazing Spider Man 2 .pkz

I don't think offzip is extract wrongly.

gives me a lot of files, and some of them have DDS DXT5



02b00000@0000000064.png (41.02 KiB) Viewed 151 times
## Post #5
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-06-12T15:49:11+00:00
- Post Title: The Amazing Spider Man 2 .pkz

00000000@0000000112.png (13.53 KiB) Viewed 151 times
## Post #6
- Username: SerJar
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 02, 2020 1:10 am
- Post datetime: 2022-06-24T13:06:23+00:00
- Post Title: The Amazing Spider Man 2 .pkz

> Reply from Rabatini ↑Sun Jun 12, 2022 11:48 pm at Sun Jun 12, 2022 11:48 pm
>
> 
I don't think offzip is extract wrongly.

gives me a lot of files, and some of them have DDS DXT5

02b00000@0000000064.png

Maybe, but when I'm trying to launch the game with decrypted file it crashes.
I don't need the textures, i just need to decompress the file
## Post #7
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-06-24T13:10:01+00:00
- Post Title: The Amazing Spider Man 2 .pkz

> Reply from LolKekAna ↑Fri Jun 24, 2022 9:06 pm at Fri Jun 24, 2022 9:06 pm
>
> 
Rabatini wrote: ↑Sun Jun 12, 2022 11:48 pm
I don't think offzip is extract wrongly.

gives me a lot of files, and some of them have DDS DXT5

02b00000@0000000064.png


Maybe, but when I'm trying to launch the game with decrypted file it crashes.
I don't need the textures, i just need to decompress the file
of course, you need to compress it again.
you cant just put a decompress file in the place of the compressed one.
## Post #8
- Username: SerJar
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 02, 2020 1:10 am
- Post datetime: 2022-06-24T13:17:26+00:00
- Post Title: The Amazing Spider Man 2 .pkz

> Reply from Rabatini ↑Fri Jun 24, 2022 9:10 pm at Fri Jun 24, 2022 9:10 pm
>
> 
LolKekAna wrote: ↑Fri Jun 24, 2022 9:06 pm
Rabatini wrote: ↑Sun Jun 12, 2022 11:48 pm
I don't think offzip is extract wrongly.

gives me a lot of files, and some of them have DDS DXT5

02b00000@0000000064.png


Maybe, but when I'm trying to launch the game with decrypted file it crashes.
I don't need the textures, i just need to decompress the file

of course, you need to compress it again.
you cant just put a decompress file in the place of the compressed one.

Nope, Spider-Man games from Beenox can be launched with decompressed files.
I found decompressed FrontScreen.pkz file and launched the game with it ([https://zenhax.com/viewtopic.php?f=9&t= ... Spider+Man](https://zenhax.com/viewtopic.php?f=9&t=14022&hilit=The+Amazing+Spider+Man)).
## Post #9
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-06-24T15:19:14+00:00
- Post Title: The Amazing Spider Man 2 .pkz

if the file is compressed you have to compress again.
if file is not compressed, you dont need to compress it again.

Because the routine of the program, will try to decompressed the file, and will not "understand" the file, because its already decompressed.
When files is already decompressed, the program routine is progrmmed to find the decompressed file.
Some devs put an if argument, 
If file X is compressed calls program to decompressed else load the file, so, sometimes in some games works with decompressed files instead compressed one.
Ps2 games, is very dificult to have this kind of feature in the dev´s code, PC? maybe.
