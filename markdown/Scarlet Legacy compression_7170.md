## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-12T21:58:55+00:00
- Post Title: Scarlet Legacy compression

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-12T22:33:49+00:00
- Post Title: Scarlet Legacy compression

looks like the header is xored with the alphabit or something like ABCDEFGHIJKLMNOPQRSTUVWXYZ 
but thats not needed for these files just run offzip on them and you get the decompressed files.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-13T00:57:07+00:00
- Post Title: Scarlet Legacy compression

So I wrote a bms script for it
It replaces the original compressed file with the new one (with -o option), but right now it leaves the uncompressed size as the first 4 bytes for some reason. How can I modify this script so that will delete the leftover?

The uncompressed size was at the end, so maybe that's why it is included in the output? offzip also did the same.

```

goto 0x40
get name FILENAME
get filesize asize
math filesize -= 4
get csize long
savepos offset
goto filesize
get size long
clog name offset csize size

```

[size.jpg](https://xentaxbackup.github.io/file/4621_size.jpg)
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-13T01:33:27+00:00
- Post Title: Scarlet Legacy compression

save it to a memory file first.
then just get the memory file size - 4 and log the file starting from the offset 4.



get name FILENAME
string name +.dec
goto -4
get size long
goto 0x40
get zsize long
clog MEMORY_FILE 0x44 zsize size
get size asize MEMORY_FILE
math size - 4
log name 4 size MEMORY_FILE
## Post #5
- Username: Antaler
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Dec 02, 2011 8:46 am
- Post datetime: 2011-12-02T15:39:57+00:00
- Post Title: Scarlet Legacy compression

Work the script?
## Post #6
- Username: Antaler
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Dec 02, 2011 8:46 am
- Post datetime: 2011-12-12T01:34:23+00:00
- Post Title: Scarlet Legacy compression

Nothing yet?
## Post #7
- Username: wimmeke001
- Rank: n00b
- Number of posts: 11
- Joined date: Sun May 13, 2012 2:23 am
- Post datetime: 2012-08-24T07:08:05+00:00
- Post Title: Scarlet Legacy compression

qbmbs script unpack pak files

# Scarlet Legacy PAK files 
# script for QuickBMS 


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

how to get models out of the pkt files
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-24T08:50:39+00:00
- Post Title: Scarlet Legacy compression

The pkt files are just compressed textures.
How do you figure pkt contains models?
## Post #9
- Username: wimmeke001
- Rank: n00b
- Number of posts: 11
- Joined date: Sun May 13, 2012 2:23 am
- Post datetime: 2012-08-25T08:49:44+00:00
- Post Title: Scarlet Legacy compression

witch file have models xd
