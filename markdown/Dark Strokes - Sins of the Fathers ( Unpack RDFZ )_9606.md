## Post #1
- Username: GARID
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Apr 06, 2011 8:29 pm
- Post datetime: 2012-09-06T13:57:37+00:00
- Post Title: Dark Strokes - Sins of the Fathers ( Unpack RDFZ )

Hello all i have problem with RDFZ decompression and can anyone know how to unpack it ?

It uses zlib compression but when i trying to decompress it using pro called zlibc.exe it not works HELPPPPPP?!?
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-09-07T18:50:25+00:00
- Post Title: Dark Strokes - Sins of the Fathers ( Unpack RDFZ )

try [url=[http://aluigi.altervista.org/mytoolz/offzip.zip](http://aluigi.altervista.org/mytoolz/offzip.zip)]offzip]
## Post #3
- Username: GARID
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Apr 06, 2011 8:29 pm
- Post datetime: 2012-09-08T03:46:14+00:00
- Post Title: Dark Strokes - Sins of the Fathers ( Unpack RDFZ )

> Reply from WRS
>
> try [url=http://aluigi.altervista.org/mytoolz/offzip.zip]offzip

Hello, that tool works but not full correctly it takes some mistakes and can't unzip full data.

   I have uploaded the file, it's only 50mb 

[http://www.mediafire.com/?z5sb7qvm5c87466](http://www.mediafire.com/?z5sb7qvm5c87466)

...?
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-09-08T19:19:08+00:00
- Post Title: Dark Strokes - Sins of the Fathers ( Unpack RDFZ )

there was a filename table

NOTE  the output xml needs reconstructing. i have no incentive to write a reconstructor for that

```
# Written by WRS
idstring "RDFZ"

get strlen long
getdstring str strlen

if str != "Zlib"
  print "Unsure how to handle file header"
  cleanexit
endif

get zsize long # includes the 4-byte 'size'
math zsize -= 4
get size long
savepos offset

clog MEMORY_FILE offset zsize size

math offset += zsize
goto offset

## process header:
  get unknown long MEMORY_FILE # 2
  get unknown long MEMORY_FILE # 0

  get strlen long MEMORY_FILE
  getdstring str strlen MEMORY_FILE # Zlib

  ## read types (array 0)
  get typeCount long MEMORY_FILE

  for i = 0 < typeCount
    get strlen long MEMORY_FILE
    getdstring str strlen MEMORY_FILE
    putarray 0 i str
  next i

  ## read names (array 1)

  get nameCount long MEMORY_FILE

  for i = 0 < nameCount
    get strlen long MEMORY_FILE
    getdstring str strlen MEMORY_FILE
    putarray 1 i str
  next i
## end of header

get filecount long

for f = 0 < filecount
  get pntr long
  get size long
  get tindex long # header array 0
  get nindex long # header array 1
  get flag long

  getarray type 0 tindex
  getarray name 1 nindex
  
  # todo: make name 
  if type == "jpg_texture"
    string fname p= "%s.jpg" name
  elif type == "texture"
    string fname p= "%s.dds" name
  else
    # xml IS .xml
	# webm too
	
    string fname p= "%s.%s" name type
  endif
  
  savepos beforeflag
  
  if flag == 1
    goto pntr
	get zsize long
	savepos offset
	clog MEMORY_FILE2 offset size zsize
    log fname 0 zsize MEMORY_FILE2
	goto beforeflag
  else
    log fname pntr size
  endif

next f

```
