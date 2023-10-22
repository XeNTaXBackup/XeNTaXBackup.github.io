## Post #1
- Username: Eggtooth
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jun 06, 2010 2:20 am
- Post datetime: 2010-11-04T14:06:26+00:00
- Post Title: Painkiller 2004 PL Demo PAK File Unpack

Hello! 

I tried everything (MultiEX, Painful) to unpack first Painkiller Polish demo from 2004 (Three levels).
Why i need it? Because there is a Windowed option that i need to the New Painkiller Redemption (I am a Developer).
So if someone know how to unpack this file, please help me  PainFull and Multi EX giving me error: Archive not identified. Please some one unpack this file, or give me a soft to unpack it. I need scripts from this PAK file.

There you can download this file: [http://www29.zippyshare.com/v/83629131/file.html](http://www29.zippyshare.com/v/83629131/file.html)

Please help
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-11-04T20:39:39+00:00
- Post Title: Painkiller 2004 PL Demo PAK File Unpack

format is very simple but the compression is unknown by me.
zip archive or w/e:

```
file headers - for each record: 20-bytes + length of filename + size of compressed data + 10-bytes
central directory - for each record: 46-bytes + length of filename
end of central directory - 22 bytes

```


my current setup is too bad to do much more. hopefully i can write a bms script for tomorrow.

edit:
1432 records. 
see attachment for file name dump (1327 records) - the others are folder names.
[pain filelist.txt.zip](https://xentaxbackup.github.io/file/3582_pain filelist.txt.zip)
## Post #3
- Username: Eggtooth
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jun 06, 2010 2:20 am
- Post datetime: 2010-11-05T11:54:47+00:00
- Post Title: Painkiller 2004 PL Demo PAK File Unpack

Yeah, that's the files i need.
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-11-05T16:20:01+00:00
- Post Title: Painkiller 2004 PL Demo PAK File Unpack

deflate algorithm. it is a zip file....   


quick note on my last attachment - it's wrong as some folders do have different checksums. not that it matters..


```

get EOCDRP asize
math EOCDRP -= 22
goto EOCDRP

# end of central directory record
# no need to parse the cdr

idstring "PAIN"
get IGNORING long
get FILES short
goto 0xA

comtype deflate # 8

for i = 1 to FILES

  get UNKNOWN long # some sort of checksum
  get UNKNOWN long
  get ZSIZE long
  get SIZE long
  get FNLEN long
  getdstring FNAME FNLEN

  savepos DATASTART

  if ZSIZE > 0
    if ZSIZE == SIZE
      log FNAME DATASTART ZSIZE
      print "WARNING: No compression on last file"
    else 
      clog FNAME DATASTART ZSIZE SIZE
    endif
  endif

  math DATASTART += ZSIZE
  goto DATASTART
  getdstring UNKNOWN 10

next i

```


also found a reference to a windowed mode option in English.txt:

> # video config
>
> 225: The higher resolutions, the faster PC and 3D card is required
>
> 226: Set to low if you have performance issues
>
> 227: Uncheck if you want to run the game in window mode

leave a comment!
## Post #5
- Username: Eggtooth
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jun 06, 2010 2:20 am
- Post datetime: 2010-11-06T00:10:28+00:00
- Post Title: Painkiller 2004 PL Demo PAK File Unpack

Can u just unpack file? I need it quick. But thanks for help. Yea, checksums are different but i tried several programs to unpack. Can u do it? I need a scripts from the archive  Is it possible to unpack?
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-11-06T11:10:46+00:00
- Post Title: Painkiller 2004 PL Demo PAK File Unpack

> Reply from Eggtooth
>
> Can u just unpack file? I need it quick. I need a scripts from the archive  Is it possible to unpack?

i posted a bms script to unpack it for you.

download quickbms to run it on your file - [http://aluigi.org/papers.htm#quickbms](http://aluigi.org/papers.htm#quickbms)
