## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-03T21:18:10+00:00
- Post Title: Debonosu works

Here's an unpacker for games developed by DebonosuWorks

```
# written by Tsukihime
# script for QuickBMS http://quickbms.aluigi.org

comtype deflate
idstring "PAK\x00"
get unk short
get unk short
get null long
get null long
get headerSize long
get null long
get unk long

# decompress file table
get SIZE long
get ZSIZE long
get null long
savepos OFFSET
clog MEMORY_FILE OFFSET ZSIZE SIZE

math DAT_START = OFFSET
math DAT_START += ZSIZE

get TABLE_SIZE asize MEMORY_FILE
string FOLDER_NAME = ""
for i = 0
  get OFFSET long MEMORY_FILE
  get null long MEMORY_FILE
  get SIZE long MEMORY_FILE
  get null long MEMORY_FILE
  get ZSIZE long MEMORY_FILE
  get null long MEMORY_FILE
  get type long MEMORY_FILE
  getdstring unks 24 MEMORY_FILE
  get NAME string MEMORY_FILE
  
  math OFFSET += DAT_START
  if zsize > 0
    string OUT_NAME = FOLDER_NAME
    string OUT_NAME += "/"
    string OUT_NAME += NAME
    clog OUT_NAME OFFSET ZSIZE SIZE
    #print %OUT_NAME%
  else
    string FOLDER_NAME = NAME
    #print "%i% %NAME%"
  endif
  
  savepos curr MEMORY_FILE
  if curr == TABLE_SIZE
    break
  endif
next i

```
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-08-03T21:52:16+00:00
- Post Title: Debonosu works

I've always been curious... why do you call yourself moon princess ?
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-04T02:23:29+00:00
- Post Title: Debonosu works

Don't know, just started throwing that name on my works and didn't feel like changing it.
## Post #4
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-08-04T16:15:28+00:00
- Post Title: Debonosu works

thanks a lot for your work buddy but what about clients? I found web site but no download links? can give me via private clients? thanks a lot for support.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-04T18:11:36+00:00
- Post Title: Debonosu works

They're PC games.
