## Post #1
- Username: zgfzfmebio
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jul 23, 2012 4:14 pm
- Post datetime: 2012-07-23T15:05:41+00:00
- Post Title: VS SANGUO（VS three kingdoms  )

[http://game.vsa.com.cn/vssg/jsp/comm/download.html](http://game.vsa.com.cn/vssg/jsp/comm/download.html)

IT IS A ORGE3D GAME

I want to extract files from This game，Who can help me？
models， skeletons and textures all in one Package（resource.vsa）
## Post #2
- Username: zgfzfmebio
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jul 23, 2012 4:14 pm
- Post datetime: 2012-08-04T11:19:41+00:00
- Post Title: VS SANGUO（VS three kingdoms  )

This code can't work，Who can tell me what's wrong?


```

goto 0x108
get FileTableLen long
ReverseLong FileTableLen
savepos FileTableLast
//print %FileTableLen%
math FileTablelast += FileTableLen
//print %FileTableLast%

for 
  savepos Address
  //print "%Address%, %FileTableLast%"
  if Address >= FileTableLast
	//print "Exit"
    cleanexit
  endif
  get FILETYPE byte
  get FILEID long
  get FILEIDP long
  get FILENAMELEN long
  getdstring FILENAME FILENAMELEN
  get ZFILESIZE long
  get FILESIZE long
  get FILEOFFSET long
  get a1 byte
  get x1 long
  get x2 long
  get x3 long
  get x4 long
  get y1 long
  get y2 long
  get y3 long
  get y4 long
  get y5 long
  get y6 long
  get y7 long
  get y8 long
  
  //clog FILENAME FILEOFFSET ZFILESIZE FILESIZE
  log FILENAME FILEOFFSET ZFILESIZE
next

```
