## Post #1
- Username: supraEZ
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 12, 2010 12:45 pm
- Post datetime: 2010-10-12T04:55:22+00:00
- Post Title: [Xbox] Crimson Skies .BIN files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-10-12T12:31:41+00:00
- Post Title: [Xbox] Crimson Skies .BIN files

forewarning: i'm getting lazy formatting my threads   


Different formats.


ConfigNames.bin

format:
20-byte header
string pointer table
packed strings

```
get UN long
get STRINGS long
get STRINGS_SIZE long
get UN long
get UN long

get START asize
math START -= STRINGS_SIZE

## parse string pointers and dump strings
for i = 0 < STRINGS

  get STRPTR long
  math STRPTR += START

  savepos POS

  goto STRPTR
  get STR string

  print "%STR%" # if you're feeling brave

  goto POS

next i

```

menu.bin / menu_FR.bin

files are stored in blocks.
the files have a filetype definition, which means the block may be
parsed differently.

few types:

```
1 = x

texture
2 = tga  -- note that some filenames contain '|'
3 = dds

animation
4 = anm

?? (models?)
5 = cin

music
6 = wav

??
7 = d3d

```


for block types > 7 (eg in SH_Tutorial.bin, where there is a 19 value) there seems to be a dump of filenames:
uint32 Length
char Name[ Length ]
not really followed this any further.

rough structure:

```
# if not, the value will be 106
uint32 Files

for each Files:

  uint32 FileType
  uint32 NameLen
  char Name[ NameLen ]
  uint32 BlockSize

  byte Block[ BlockSize ]

next

```


note: this isn't a bms script

in CH_Rescue_Betty.bin there are a few more header values
also, the files value is only 190, when there are actually 2858 file headers


ui_dirty_disc.bin follows an entirely different format.


so there are 3 main formats:

confignames - string tables
menus / default_airplane / others - archive format w/ variable header
ui_disc - other
## Post #3
- Username: Nathan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 23, 2010 10:08 am
- Post datetime: 2010-10-23T02:17:11+00:00
- Post Title: [Xbox] Crimson Skies .BIN files

I am very interested in this also, but not sure what all this means, or how I can use this to modify Crimson Skies High Road to Revenge maps.

I'll be glad to do all the work, but I need some direction.

I'll have ca$h in december, if that helps.

thanks!
