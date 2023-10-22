## Post #1
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-08-16T20:02:02+00:00
- Post Title: Aurora Watching

hello

iam need script for, this file 

thx
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-08-17T03:34:12+00:00
- Post Title: Aurora Watching

Hi mate,

I did this game a while back - the format is the following...

```
| Gorky Zero: Aurora Watching *.zap |
+-----------------------------------+

// Unknown compression used for this archive?

// FILE DATA
  // for each file
    X - File Data

// DIRECTORY
  4 - Unknown
  4 - Unknown

  // for each file
    4 - Unknown ID (usually 1)
    1 - Filename Length
    if (filename starts with a null){
      // skip over filenameLength-1 bytes, then...
      1 - Filename Length
      }
    X - Filename
    4 - File Offset?
    4 - Decompressed Length
    4 - Compressed Length
    4 - Directory ID (for the directory the file belongs to)???
    4 - null

// ARCHIVE END DATA    
  4 - Unknown
  4 - Offset To Directory Start

  X - Unknown Data

  4 - Pointer to Unknown
  4 - Unknown
  4 - Unknown (4)
  4 - Pointer To Directory End
  4 - Pointer to Unknown
  4 - Unknown
```


However, as the code says, I don't know what compression is used, so the archive is practically unusable.

We can see about a script anyway if you really want one.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-08-17T04:09:48+00:00
- Post Title: Aurora Watching

OK here is a script for you...

```
Math endOffPos -= 12 ;
GoTo endOffPos 0 ;
Get endDirPos Long 0 ;
Set endDir Long endDirPos ;
Math endDirPos += 4 ;
GoTo endDirPos 0 ;
Get startDirPos Long 0 ;
Math startDirPos += 8 ;
GoTo startDirPos 0 ;
SavePos curPos 0 ;
Do ;
Get DummyL Long 0 ;
Get FNLen Byte 0 ;
SavePos FNPos 0 ;
Get FNTest Byte 0 ;
If FNTest = 0 ;
Math FNPos += FNLen ;
Math FNPos -= 1 ;
EndIf ;
GoTo FNPos 0 ;
GetDString FN FNLen 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
Get Decomp Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
SavePos curPos 0 ;
Math curPos += 8 ;
Log FN FO FOO FS FSO ;
While curPos < endDir ;


```


And attached is the compiled script. I hope it works - it uses some of the new 4.1 script commands so you might need the latest MexCom to use it. It also might not work correctly in some cases cause its kinda a dodgy format, but see what happens. Good luck.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[zap.zip](https://xentaxbackup.github.io/file/403_zap.zip)
## Post #4
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-08-17T17:56:37+00:00
- Post Title: Aurora Watching

hello mr watto

thank you for script

but, when open archive show error message : "run-time error 9  subscript out of range:

iam use multiex 4.1.0
thank you again
## Post #5
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-08-17T22:30:55+00:00
- Post Title: Aurora Watching

OK, will have to get Mr Mouse to take a look at it - I've never used the Do-While and If-Else statements in MexScript before so am not sure exactly how its all programmed. Also will need to check single byte reading - not sure if that works either.

Thanks anyway - I tried 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
