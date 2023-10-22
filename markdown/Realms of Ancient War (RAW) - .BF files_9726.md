## Post #1
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-10-11T12:19:13+00:00
- Post Title: Realms of Ancient War (RAW) - .BF files

So I pre-ordered this game and came out today, and the texts are probably located in the "BF-string-table.bf" file. If anyone willing to look at it, please PM me.

Thank you!
## Post #2
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2012-10-12T18:01:16+00:00
- Post Title: Realms of Ancient War (RAW) - .BF files

```
#
# R.A.W. - Realms of Ancient War
#
# QuickBMS script for .BF files
#
# created by The Bacter
#
######################################################

get DirTableSize long
get NrOfFiles long

for i = 0 < NrOfFiles
   get unk longlong
   get File_Name string
   get File_StartPos long
   get File_Size long
   log File_Name File_StartPos File_Size
next i

```
## Post #3
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2012-10-13T15:45:34+00:00
- Post Title: Realms of Ancient War (RAW) - .BF files

any ways to make game work with modified files. I tried extracting a file, edit them and reimport, and game crashed at startup.
