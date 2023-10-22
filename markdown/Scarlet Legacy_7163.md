## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-12T02:01:05+00:00
- Post Title: Scarlet Legacy

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-08-12T13:51:16+00:00
- Post Title: Scarlet Legacy

you know what's annoying? i can parse the entire file - but trying to label one last 2 bytes value which has no obvious purpose .....
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-12T17:00:49+00:00
- Post Title: Scarlet Legacy

Impressive. I was looking at it and going "hmm...so what am I looking at"
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-08-12T21:37:08+00:00
- Post Title: Scarlet Legacy

nice simple example of recursion   

i only downloaded 2 samples - and the login sample contains more compressed data

```
# script for QuickBMS
# WRS, xentax.com

idstring "PAK\0"
get ver byte
getdstring DUMMY 16
get headSize long

get cdOffset long
get cdSize long
get cdZSize long

get dataStart long
get dataSize long

get fileSize long

clog MEMORY_FILE cdOffset cdZSize cdSize

set base string ""

callfunction recursiveDir

cleanexit



startfunction recursiveDir

  get subFils long MEMORY_FILE
  get subDirs long MEMORY_FILE
  get dirName string MEMORY_FILE

  # quick fix for the initial dir

  if dirName != "/"
    string base += /
    string base += dirName
  endif

  for subd = 0 < subDirs
    callfunction recursiveDir
  next subd

  for subf = 0 < subFils
    callfunction extractFile
  next subf

endfunction


startfunction extractFile

  get fileOffs long MEMORY_FILE
  get fileSize long MEMORY_FILE
  get fileName string MEMORY_FILE

  math fileOffs += dataStart

  set filePath string base
  string filePath += /
  string filePath += fileName

  log filePath fileOffs fileSize

endfunction

```
