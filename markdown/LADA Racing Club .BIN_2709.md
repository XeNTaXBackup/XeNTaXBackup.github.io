## Post #1
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2007-07-13T22:45:17+00:00
- Post Title: LADA Racing Club *.BIN

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Infinity
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Sep 09, 2006 11:42 pm
- Post datetime: 2007-07-13T23:30:04+00:00
- Post Title: LADA Racing Club *.BIN

The contents of this post was deleted because of possible forum rules violation.
## Post #3
- Username: Acewell
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-14T19:29:34+00:00
- Post Title: LADA Racing Club *.BIN

.PACK archives: 

```
# By Mr.Mouse July 2007
# Standard imporation type (offsets and sizes are in the archive).
ImpType Standard ;

# --- GET HEADER ---
# MAGIC word {8}
# Number of files {4}
# Relative offset of Resource Tables 
Get MW1 Long 0;
Get MW2 Long 0 ;
Get FNum Long 0 ;
Get RDPos Long 0 ;
SavePos INPos 0 ;

# --- PREPARE VARIABLES ---
# Calculate the actual offset (include header size)
Math RDPos += 16 ;
# Calculate the offset of the filename string table
Set FNPos Long FNum ;
Math FNPos *= 16 ;
Math FNPos += RDPos ;
# Go there because we need to get the size of that baby to...
GoTo FNPos 0 ;
Get RNSize Long 0 ;
# ...calculate the offset of the Relative FilenameOffset Table 
SavePos FNStart 0 ;
Set FNT Long FNStart ;
Math FNT += RNSize ;

# --- MAIN LOOP ---
For T = 1 To FNum ;
# For each file in the archive:
# Go to the main resource table and get: 
# 1. Offset of internal file marker in the list (comes after the header)
# 2. Absolute Offset of the file (save the position of this variable too)
# 3. Size of the file (save the position of this variable too)
# 4. A reserved 32-bit variable 
# Then go to the filename offset table and get the relative offset 
# of the filename in the filename string table
# Calculate the absolute offset 
# Go there and get the null-terminated string at this location
# All set, log the important variables for MexCom. 
GoTo RDPos 0 ;
Get IOff Long 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Get Reserved Long 0 ;
SavePos RDPos 0 ;
GoTo FNT 0 ;
Get RFNOff Long 0 ;
Math RFNOff += FNStart ;
GoTo FNStart 0 ;
Get FN String 0 ;
SavePos FNStart 0 ;
Log FN FO FS FOO FSO ;
Next T ;

```

[2.JPG](https://xentaxbackup.github.io/file/1267_2.JPG)

[1.JPG](https://xentaxbackup.github.io/file/1266_1.JPG)

[lada_racing_pack_mexscript.zip](https://xentaxbackup.github.io/file/1265_lada_racing_pack_mexscript.zip)
## Post #4
- Username: Acewell
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-14T19:45:15+00:00
- Post Title: LADA Racing Club *.BIN

For PAK format (e.g. moscow.pak)

```
# By Mr.Mouse July 2007
# Standard imporation type (offsets and sizes are in the archive).
ImpType Standard ;

# --- GET HEADER ---
# MAGIC word {4}
# Size of tables {4}
# Number of files
Get MW1 Long 0;
Get TSize Long 0 ;
Get FNum Long 0 ;
SavePos RDPos 0 ;

# --- MAIN LOOP ---
For T = 1 To FNum ;
# For each file in the archive:
# Go to the main resource table and get: 
# 1. Relative Offset of the filename string 
# 2. Absolute Offset of the file (save the position of this variable too)
# 3. Size of the file (save the position of this variable too)
# Then go to the filename string table and get a null-terminated string
# All set, log the important variables for MexCom. 
GoTo RDPos 0 ;
Get FNOff Long 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
SavePos RDPos 0 ;
# Add the headersize (12) to get the absolute offset 
Math FNOff += 12 ;
GoTo FNOff 0 ;
Get FN String 0 ;
Log FN FO FS FOO FSO ;
Next T ;

```

[lada_racing_pak_mexscript.zip](https://xentaxbackup.github.io/file/1268_lada_racing_pak_mexscript.zip)
## Post #5
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2007-07-17T19:23:51+00:00
- Post Title: LADA Racing Club *.BIN

WoW  Respect Mr.Mouse
