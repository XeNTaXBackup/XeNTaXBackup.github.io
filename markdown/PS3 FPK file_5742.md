## Post #1
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-01-10T06:36:30+00:00
- Post Title: PS3 FPK file

Hi all!
Please help extract FPK file.


Does anyone can help?
## Post #2
- Username: snakemeat
- Rank: advanced
- Number of posts: 45
- Joined date: Wed Jan 28, 2009 12:00 am
- Post datetime: 2011-01-10T17:04:22+00:00
- Post Title: PS3 FPK file

Here's a QuickBMS script for the FPK archive, didn't look too hard at the TSB file.

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms
#
# Tested against "gaw_00.fpk" file 
#

idstring "FPK\x00"
endian big

get FILECOUNT long     # 0x04
get HEADERSIZE long    # 0x08
get DATASTART long     # 0x0C

for i = 0 < FILECOUNT

  # set record start
  set RECORDSTART long 0
  math RECORDSTART += i
  math RECORDSTART *= 0x50
  math RECORDSTART += HEADERSIZE
    
  # get info from current record
  goto RECORDSTART 
  get FILENAME string
  
  # set current offset and size  
  set OFFSETLOC long 0
  set SIZELOC long 0
  
  math OFFSETLOC += RECORDSTART
  math OFFSETLOC += 0x40

  math SIZELOC += RECORDSTART
  math SIZELOC += 0x48
  
  goto OFFSETLOC
  get OFFSETVAL long
  math OFFSETVAL += DATASTART
    
  goto SIZELOC
  get SIZEVAL long

  # extract the file
  log FILENAME OFFSETVAL SIZEVAL
  
next i
```
## Post #3
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-01-11T05:33:33+00:00
- Post Title: PS3 FPK file

> Reply from snakemeat
>
> Here's a QuickBMS script for the FPK archive, didn't look too hard at the TSB file.
Code: Select all# FPK Extractor: Gundam Senki Record UC 0081 (PS3)
# script for QuickBMS http://aluigi.org/papers.htm#quickbms
#
# Tested against "gaw_00.fpk" file 
#

idstring "FPK\x00"
endian big

get FILECOUNT long     # 0x04
get HEADERSIZE long    # 0x08
get DATASTART long     # 0x0C

for i = 0 < FILECOUNT

  # set record start
  set RECORDSTART long 0
  math RECORDSTART += i
  math RECORDSTART *= 0x50
  math RECORDSTART += HEADERSIZE
    
  # get info from current record
  goto RECORDSTART 
  get FILENAME string
  
  # set current offset and size  
  set OFFSETLOC long 0
  set SIZELOC long 0
  
  math OFFSETLOC += RECORDSTART
  math OFFSETLOC += 0x40

  math SIZELOC += RECORDSTART
  math SIZELOC += 0x48
  
  goto OFFSETLOC
  get OFFSETVAL long
  math OFFSETVAL += DATASTART
    
  goto SIZELOC
  get SIZEVAL long

  # extract the file
  log FILENAME OFFSETVAL SIZEVAL
  
next i

I apologize for the late greetings.

I'm enormously grateful for your help.
