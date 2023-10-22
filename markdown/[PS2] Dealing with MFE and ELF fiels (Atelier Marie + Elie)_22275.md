## Post #1
- Username: Flamel
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jun 13, 2020 3:50 am
- Post datetime: 2020-06-13T13:17:30+00:00
- Post Title: [PS2] Dealing with MFE and ELF fiels (Atelier Marie + Elie)

Hello everyone,

I would like to translate the game Atelier Marie + Elie from English to French (the original game was only in Japanese, but some group going by the name AtelierTraduction made an english patch). Nevertheless, I am quite stuck: after extracting the content of the ISO, I have the following files:

ATL.MFE (1491294 KB)
SLPM_661.40 (1761 KB)
SYSTEM.CNF (1 KB)

As well as a MODULEs folder which contains many IRX files.
From what I understood (I am sorry, I am quite new to the field), the SYSTEM.CNF is a standard boot file in PS2 ISO, and a quick look using Hex Workshop has shown me that SLPM_661.40 is the ELF file. It so happens that going quickly through the files, the only ones that seem to contain text dialogues/menus/objects/etc. are SLPM_661.40 and ATL.MFE. I know that the game is quite old (and a kind of repack of two PS1 games to top it all), but does someone know if there is a way to extract properly resources from the ELF file or how to deal with this MFE file? I would like to avoid if possible direct manipulation in particular of the latter one in hexadecimal editors because it is quite heavy to handle and a little bit painful, so any suggestion about some tools/techniques would be very helpful.
