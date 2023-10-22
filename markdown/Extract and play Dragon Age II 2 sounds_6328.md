## Post #1
- Username: TsunamiZ
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Oct 11, 2006 8:40 pm
- Post datetime: 2011-03-31T06:47:55+00:00
- Post Title: Extract and play Dragon Age II 2 sounds?

Anyone know if it's possible to extract and play Dragon Age II sounds?  If so, what do I need to do?  I just want to extract and play the sound effects from the game. Thanks.
## Post #2
- Username: daywalker03
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 03, 2011 8:13 am
- Post datetime: 2011-04-04T01:39:51+00:00
- Post Title: Extract and play Dragon Age II 2 sounds?

You'll need pyGFF to extract them from the erf file they are stored in; I'm not sure what tool you will need to convert them to a usable ogg vorbis sound file, though.
## Post #3
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2011-04-04T11:10:24+00:00
- Post Title: Extract and play Dragon Age II 2 sounds?

You will need to run

1. Chrrox's Dragon Age II BMS script

```
get off long
get files long
get unk09 long
set mainoff 0x30
math mainoff + off
goto mainoff
comtype inflate
for i = 0 < files
set name i
get null01 long
get unk01 long
get unk02 long
get ext long
if ext == 1131896374
set ext PHY
endif
if ext == 663550188
set ext MMI
endif
if ext == 1048449626
set ext XML
endif
if ext == 1067198654
set ext ANBT
endif
if ext == 1114824674
set ext RML
endif
if ext == 1115560169
set ext MMH
endif
if ext == 395652716
set ext DDS
endif
if ext == 579662031
set ext GAD
endif
if ext == 932389276
set ext EVT
endif
if ext == 1067198645
set ext ANI
endif

string name + .
string name + ext
get offset long
get zsize long
get size long
if ext == 746452407
math offset + 1
math zsize - 1
clog MEMORY_FILE offset zsize size
goto 0x1A0 MEMORY_FILE
get nameoff long MEMORY_FILE
math nameoff + 0x1A0
goto nameoff MEMORY_FILE
get nsize long MEMORY_FILE
math nsize * 2
getdstring UNAME nsize MEMORY_FILE
set NAME unicode UNAME
endif
if zsize == size
log name offset size
else
if ext == 746452407
else
math offset + 1
math zsize - 1
endif
clog name offset zsize size
endif

next i
```


2. Then use Alpha23's Wave Format Scanner script.

```
   FindLoc OFFSET STRING "WAVEfmt" 0 ""
   if OFFSET != ""
      math OFFSET -= 8
      goto OFFSET
      FindLoc DATA STRING "data" 0 ""
      math DATA += 4
      goto DATA
      get SSIZE long
      savepos HEADER
      math HEADER -= OFFSET
      set SIZE HEADER
      math SIZE += SSIZE
      get NAME basename
      string NAME += "_"
      string NAME += i
      string NAME += ".wav"
      log NAME OFFSET SIZE
   else
      cleanexit
   endif
next i
```


3. After that, run HCS's ww2ogg tool which will convert the unlistenable .wav files into .ogg files which you can download on this page

[http://hcs64.com/vgm_ripping.html](http://hcs64.com/vgm_ripping.html)

4. After all that. rename the .ogg files to .logg files and play them back with VGMstream. (This step may or may not be necessary)
## Post #4
- Username: TehOpheliac
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 06, 2011 6:05 am
- Post datetime: 2011-04-05T22:18:19+00:00
- Post Title: Extract and play Dragon Age II 2 sounds?

I've been searching all over! D:

Where do I find, "Chrrox's Dragon Age II BMS script" ?

And also "Alpha23's Wave Format Scanner script"? 

I'd like to convert specific audio files into mp3's. I know it's possible because I did it in Dragon Age: Origins with Aezay's FSB Extractor. ):

Please help me! ♥
## Post #5
- Username: figuresculptor
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jan 07, 2011 4:08 am
- Post datetime: 2011-04-05T22:55:20+00:00
- Post Title: Extract and play Dragon Age II 2 sounds?

> Reply from TehOpheliac
>
> Where do I find, "Chrrox's Dragon Age II BMS script" ?

And also "Alpha23's Wave Format Scanner script"?

Umm… those scripts are hiding in plain site. They're right in brendan19's original post. Those blocks of green text are scripts for QuickBMS. Save them to text files and run them using QuickBMS.

You can find QuickBMS Here: [http://aluigi.org/papers/quickbms.zip](http://aluigi.org/papers/quickbms.zip)
## Post #6
- Username: TehOpheliac
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 06, 2011 6:05 am
- Post datetime: 2011-04-05T23:00:56+00:00
- Post Title: Extract and play Dragon Age II 2 sounds?

Nevermind, I've already figured it all out through another method with less programs~ 

For anyone else who's interested: [http://social.bioware.com/forum/1/topic ... /2#6793978](http://social.bioware.com/forum/1/topic/307/index/6666408/2#6793978)

Thank you, though. 

Sorry, this is my first visit here and I've never done any type of modding... xD I just wanted to make ringtones. >.<
