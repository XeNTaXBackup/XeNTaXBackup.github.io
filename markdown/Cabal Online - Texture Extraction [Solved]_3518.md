## Post #1
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-06-01T20:22:14+00:00
- Post Title: Cabal Online - Texture Extraction [Solved]

Hello to all,

I'm hoping this is a quick process since most of the tools are already created, courtesy of RageZone.com site.

Anyway, here is the issue, just like some games which use GamEbryo in Nif format, which have 'embedded' textures, Cabal Online is the same. It uses EBM files which have embedded textures. There is a blender script which allows you import EBM files + Textures, but cannot export them.

WIP Paint Program for extraction (doesn't extract all the files, only a few select): [http://forum.ragezone.com/f458/mr-paint ... ta-542094/](http://forum.ragezone.com/f458/mr-paint-1-0-beta-542094/)

EBM Blender Importer: [http://forum.ragezone.com/f458/ebm-blen ... er-449555/](http://forum.ragezone.com/f458/ebm-blender-importer-449555/)

> If you want to modify a texture inside an EBM/ECH, just open the file in a hex editor. 
>
> 
>
> Then, find the name of the texture (*.dds), place you cursor before the following "DDS |", select until the end of the file, and then click on File -> Save selection as... 
>
> 
>
> (NOTE: This is how you do it in Hex Workshop, but shouldn't be much different from any other hex editor).

Anyone could create a quick and dirty batch extractor for EBM files?
## Post #2
- Username: AceAngel
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-06-02T00:29:40+00:00
- Post Title: Cabal Online - Texture Extraction [Solved]

This is the best I could figure out while keeping the name.
quick BMS script

```
get FILES short
#I can't find the file num so just add "math FILES += X"
#without the "" and replace X with how many dds files over 3 you want to check for.
goto 0x12
for i = 0 < FILES
getdstring NULL 0x5E
get NLENGTH short
getdstring NAME NLENGTH
get SIZE long
savepos OFFSET
log NAME OFFSET SIZE
getdstring DDS 0x3
if DDS == "DDS" then
math OFFSET += SIZE
goto OFFSET
next i
else
cleanexit
endif
```


I can write  a script to extract that could be better but would loose the names.
## Post #3
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-06-02T13:03:13+00:00
- Post Title: Cabal Online - Texture Extraction [Solved]

Wow, that was quick, thanks ^^

I'm no expert, so how I can I use the code? BMS is kinda a new word for me, hehe.
## Post #4
- Username: AceAngel
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-06-02T21:25:51+00:00
- Post Title: Cabal Online - Texture Extraction [Solved]

just download it from here and follow the instructions.
[http://aluigi.org/papers.htm#quickbms](http://aluigi.org/papers.htm#quickbms)
## Post #5
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-06-07T20:29:43+00:00
- Post Title: Cabal Online - Texture Extraction [Solved]

Thank you mate, much appreciated =D

PS: Sorry for the delay in response...
## Post #6
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-06-12T19:41:47+00:00
- Post Title: Cabal Online - Texture Extraction [Solved]

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: AceAngel
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-06-12T20:11:46+00:00
- Post Title: Cabal Online - Texture Extraction [Solved]

Sorry here is a better script.

```
findloc RES_START string "X9´;"
goto RES_START
savepos RES_START
math FILES += 0xFFF

for i = 0 < FILES
getdstring NULL1 0x14
get NSIZE short
getdstring NAME NSIZE
get SIZE long
savepos OFFSET
log NAME OFFSET SIZE
math RES_START += SIZE
goto RES_START
findloc RES_START string "X9´;"
goto RES_START

next i
```

if you want them to be extracted into a folder named what the compressed file is let me know.
## Post #8
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-06-12T20:35:42+00:00
- Post Title: Cabal Online - Texture Extraction [Solved]

Hey, thanks for the new script.

I tried it, but here is what happens:

Models that have only 1 .dds texture = no extract
Models that have more than 1 .dds texture = extract only first texture.

Is the script broken by any chance? Because it feels like the last part is missing.

Anyway, take your time. It's not an emergency to make it right now
## Post #9
- Username: AceAngel
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-06-12T20:50:48+00:00
- Post Title: Cabal Online - Texture Extraction [Solved]

I just did this on the sample file you gave me and it extracted all 3 files
what version of quickbms are you using?

```
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org

- open input file barlog_s.ebm
- open script test.bms
- set output folder New Folder

  offset   filesize   filename
------------------------------
  00000085 65664      balog_blade.dds
  00010174 524416     balog_a.dds
  00090263 65664      balog_b.dds

- 3 files found
```
## Post #10
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-06-12T21:14:03+00:00
- Post Title: Cabal Online - Texture Extraction [Solved]

Ooops, my mistake, didn't download the latest version. 

Yes, the latest script does extract the textures from Balrog, but I tried a few other models and no go. It says "0 files found".

The old script does work however for these models, but not the Balrog.

PS: Uploaded a sample model.
[alug.rar](https://xentaxbackup.github.io/file/2102_alug.rar)
