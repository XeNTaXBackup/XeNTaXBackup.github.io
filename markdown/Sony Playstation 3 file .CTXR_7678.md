## Post #1
- Username: unlimited32
- Rank: beginner
- Number of posts: 38
- Joined date: Sat Oct 16, 2010 8:27 pm
- Post datetime: 2011-11-13T10:16:22+00:00
- Post Title: Sony Playstation 3 file ".CTXR"

The contents of this post was deleted because of possible forum rules violation.
[japanstudio_720.rar](https://xentaxbackup.github.io/file/4836_japanstudio_720.rar)
## Post #2
- Username: ratanegra
- Rank: n00b
- Number of posts: 17
- Joined date: Wed May 23, 2012 5:12 pm
- Post datetime: 2012-06-11T15:23:00+00:00
- Post Title: Sony Playstation 3 file ".CTXR"

The texture is a gtf format, but with the blocks "changed" ......
You can convert a .ctrx texture to dds, but you must edit the header (64b)

Example of japan_studio:

1º original block (16 bytes):
0200010100384000   0000000100000000
1º edited block : 
020101FF00384000   0000000100000000

2º original block (16 bytes):
0000008000384000  000000FFD2D2D2FF
2º edited block : 
0000008000384000  BE0102000000A9E4

3º original block (16 bytes):
00000000BE010200  0000A9E4050002D0
3º edited block :
050002D000010000  0000000000000000

3º original block (16 bytes):
0001000000001400  00000000FFFF0000
4º edited block :
0000000000000000  0000000000000000

The last step is convert a ctxr file with gtf2dds.exe

[](http://imageshack.us/photo/my-images/201/ctrxtexture.jpg/)

This method is extensible for textures of Metal Gear Solid Snake Eater (HD Collect).
Luck!
## Post #3
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-09-07T07:40:48+00:00
- Post Title: Sony Playstation 3 file ".CTXR"

Hello, I'm sorry to bother you but I have one question, how do we know what to change the values of the ctxr files header to? If I had a ctxr file with different values in the header what is the process for changing them? I looked for a pattern in the file you changed to see if I could find a similar way to do it for a different ctxr file but I'm not having any luck. Sorry, I know it's a really beginner question but I'd just like to learn  thanks!

EDIT: Nevermind, I figured it out eventually. I'm so stupid sometimes :p
## Post #4
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-10-05T10:24:26+00:00
- Post Title: Sony Playstation 3 file ".CTXR"

So I made a simple bms script to convert these ctxr files to ones that can be converted using gtf2dds just to save time

```
get VAL long
get VAL2 long
get VAL3 long
get VAL4 long
goto 0x18
put VAL long
put VAL2 long
put VAL3 long
put VAL4 long
```


and just run quickbms using the command line;

quickbms -w -F "*.ctxr" ctxrconv.txt c:\ctxr

etc
## Post #5
- Username: ratanegra
- Rank: n00b
- Number of posts: 17
- Joined date: Wed May 23, 2012 5:12 pm
- Post datetime: 2012-10-06T05:12:24+00:00
- Post Title: Sony Playstation 3 file ".CTXR"

good job bro.
## Post #6
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2013-02-03T17:26:17+00:00
- Post Title: Sony Playstation 3 file ".CTXR"

> Reply from rman2
>
> So I made a simple bms script to convert these ctxr files to ones that can be converted using gtf2dds just to save time
Code: Select allgoto 0x24
get VAL long
get VAL2 long
get VAL3 long
get VAL4 long
goto 0x18
put VAL long
put VAL2 long
put VAL3 long
put VAL4 long

and just run quickbms using the command line;

quickbms -w -F "*.ctxr" ctxrconv.txt c:\ctxr

etc

Hi

I know this is a pretty old thread, but I'm a little confused, I'm able to get a folder called ctxrconv.txt to appear, but its blank, and then when I run the BMS script (from reimport, which seems to have -w enabled) I'm told that 0 files have been imported in 0 seconds.

If someone could break this down a tiny bit I'd really appreciate it, trying to understand this but not getting very far.
## Post #7
- Username: ratanegra
- Rank: n00b
- Number of posts: 17
- Joined date: Wed May 23, 2012 5:12 pm
- Post datetime: 2013-02-20T10:41:32+00:00
- Post Title: Sony Playstation 3 file ".CTXR"

If you get this, do not worry, you have  the CTXR files prepared to convert them to DDS with GTF2DDS.EXE.

```

QuickBMS generic files extractor and reimporter 0.5.9b
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org

- start the scanning of the input folder: c:\quickbms\ctxr
- open input file c:\quickbms\ctxr\.\snake_tales_ltitlea_alp_ovl.bmp.ctxr
- open script ctxrconv.txt

  offset   filesize   filename
------------------------------

- 0 files found in 0 seconds
- open input file c:\quickbms\ctxr\.\snake_tales_ltitleb_alp_ovl.bmp.ctxr
- open script ctxrconv.txt

C:\quickbms>
```
## Post #8
- Username: cns20
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 10, 2015 10:21 pm
- Post datetime: 2015-06-10T14:58:39+00:00
- Post Title: Sony Playstation 3 file ".CTXR"

Guess I must be doing something wrong. All that comes up is this:

```

C:\Users\username\Downloads\quickbms>quickbms -w -F "*.ctxr" ctxrconv.txt C:\Users\username\Downloads\quickbms

QuickBMS generic files extractor and reimporter 0.6.4
by Luigi Auriemma
e-mail: me@aluigi.org
web:    aluigi.org
        (May 29 2015 - 16:04:52)

                  http://quickbms.aluigi.org
               http://twitter.com/luigi_auriemma
                       http://zenhax.com

- filter string: "filename.ctxr"
  filename.ctxr

-------------------
*EXCEPTION HANDLER*
-------------------
An error or crash occurred:

*EH* ExceptionCode      c0000005 access violation
*EH* ExceptionFlags     00000000
*EH* ExceptionAddress   00fe1f57
                        00FB0000 + 00031f57 quickbms.exe
*EH* NumberParameters   00000002
*EH*                    00000000
*EH*                    00000000

*EH* Stack Trace:
0xfe1f57 : C:\Users\username\Downloads\quickbms\quickbms.exe : [unknown file]
0x148e22a : C:\Users\username\Downloads\quickbms\quickbms.exe : tripledes_LTX__mcrypt
_algorithm_version
0xfb10fd : C:\Users\username\Downloads\quickbms\quickbms.exe : [unknown file]
0x77d1ad1f : C:\WINDOWS\SYSTEM32\ntdll.dll : RtlInitializeExceptionChain
0x77d1acea : C:\WINDOWS\SYSTEM32\ntdll.dll : RtlInitializeExceptionChain

C:\Users\username\Downloads\quickbms>
```


Solutions?
