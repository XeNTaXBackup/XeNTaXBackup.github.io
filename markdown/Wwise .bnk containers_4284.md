## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-03-31T19:01:50+00:00
- Post Title: Wwise *.bnk containers

As this may be interesting for many people trying to access the *.bnk containers that contain RIFX wave files (Wwise format), here are the two scripts I've written.

The first one needs a certain txt file containing the ID and the according file names. The script will search for the ID and name all the files correctly. This works with the Army of Two: 40th Day DLC for example. I've attached a sample txt file below.
The second one is to be used when no TXT file is available.

Don't worry if the script gives an error message at the end, the files are extracted properly.

with ID text file:

```
# (c) 03-2010 by AlphaTwentyThree of Xentax

open FDDE BNK 0
FindLoc DIDX string "DIDX" 0 ""
if DIDX == ""
   print "DIDX section missing!"
   cleanexit
endif
math DIDX += 0x08
FindLoc DATA string "DATA" 0 ""
set FILES DATA
math FILES -= DIDX
math FILES /= 12
math DATA += 8
goto DIDX 0

open FDDE TXT 1
FindLoc OFFSET string "In Memory Audio" 1 ""
goto OFFSET 1
FindLoc IDSTART string "\x0d\x0a\x09" 1 ""
math IDSTART += 3
goto IDSTART 1

for i = 1 <= FILES
   goto SEARCH 1
   FindLoc LENGTH string "\x09" 1 ""
   savepos START 1
   math LENGTH -= SEARCH
   getDstring IDS LENGTH 1
   savepos CURR 1
   math CURR += 1
   goto START 1
   callfunction STR2NUM 1
   goto CURR 1
   FindLoc NAMEL string "\x09" 1 ""
   math NAMEL -= CURR
   getDstring NAME NAMEL 1
   string NAME += ".wav"

   goto DIDX 0
   do
      get ID long 0
      reverselong ID
   while ID != IDN
   get OFFSET long 0
   reverselong OFFSET
   math OFFSET += DATA
   get SIZE long 0
   reverselong SIZE
   log NAME OFFSET SIZE 0
   if i != FILES
      FindLoc SEARCH string "\x0d\x0a\x09" 1 ""     # go to new ID
      math SEARCH += 3
   endif
next i

startfunction STR2NUM
   set l LENGTH
   for i = 1 <= LENGTH
      get IDN byte 1
      math IDN -= 0x30
      set POT 1
      for j = 1 < l
         math POT *= 10
      next j
      math l -= 1
      math IDN *= POT
      if i != 1
         math IDN += IDOLD
      endif
      set IDOLD IDN
   next i
endfunction
```


without ID text file:

```
# (c) 03-2010 by AlphaTwentyThree of Xentax

FindLoc DIDX string "DIDX" 0 ""
if DIDX == ""
   print "DIDX section missing!"
   cleanexit
endif
math DIDX += 0x08
FindLoc DATA string "DATA" 0 ""
set FILES DATA
math FILES -= DIDX
math FILES /= 12
math DATA += 8
goto DIDX
get FULLNAME basename
string FULLNAME += "_"

for i = 1 <= FILES
   get ID long
   reverselong ID
   get OFFSET long
   reverselong OFFSET
   math OFFSET += DATA
   get SIZE long
   reverselong SIZE
   set NAME FULLNAME
   string NAME += ID
   string NAME += ".wav"
   log NAME OFFSET SIZE
next i
```

[ID_txt_bnk.7z](https://xentaxbackup.github.io/file/2905_ID_txt_bnk.7z)
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-03-31T19:04:36+00:00
- Post Title: Wwise *.bnk containers

Thanks timo.
## Post #3
- Username: gallopinto
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jan 03, 2012 1:42 pm
- Post datetime: 2012-01-05T20:02:39+00:00
- Post Title: Wwise *.bnk containers

Real newby question, but where do I input these scripts? I have similar file that i would like to extract from these bnk container. its from a wii game
## Post #4
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-01-06T08:50:12+00:00
- Post Title: Wwise *.bnk containers

> Reply from gallopinto
>
> Real newby question, but where do I input these scripts? I have similar file that i would like to extract from these bnk container. its from a wii game
Save as *.bms and open with QuickBMS: [http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)
## Post #5
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2013-09-11T18:35:37+00:00
- Post Title: Wwise *.bnk containers

I used your script to extract the .bnk containers and some .wav files were exported, but the files don't seem to open in any player. Is this normal or is there an error with the files or script perhaps?

Here's a sample from the exported files:

[http://www.sendspace.com/file/5b0fwd](http://www.sendspace.com/file/5b0fwd)
## Post #6
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-09-11T21:11:32+00:00
- Post Title: Wwise *.bnk containers

That's an XMA file.
You need to transform it to standard XMA ([viewtopic.php?f=17&t=9023](http://forum.xentax.com/viewtopic.php?f=17&t=9023)), then decode it with toWAV (download link somewhere in this forum).
## Post #7
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2013-09-11T23:16:41+00:00
- Post Title: Wwise *.bnk containers

Thanks for the information. I used the XMA transform script on the wav file and got the following error.

Error:  there is an error with the decompression 
          the returned output size is negative (-1)

Any insight into what might be causing this error would be appreciated.
## Post #8
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-09-12T07:02:32+00:00
- Post Title: Wwise *.bnk containers

> Reply from mazor
>
> Thanks for the information. I used the XMA transform script on the wav file and got the following error.

Error:  there is an error with the decompression 
          the returned output size is negative (-1)

Any insight into what might be causing this error would be appreciated.
Have you renamed xma_test.exe to xma_parse.exe and put it in the same folder as the xma tranform script?
Also, set the variables to "set BLOCKSIZE 0x8000, set PARSE 1, set XMA 2, set WRITE_UNPARSED 0, set TESTMODE 0".
## Post #9
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2013-09-12T17:18:40+00:00
- Post Title: Wwise *.bnk containers

Thanks, I tried that now and it works perfectly. Superb job on your scripts. It's very impressive. 

Is there any way to transform multiple files at a time? I haven't been able to use the xma  transform script with more than one file at a time. Perhaps a batch operation would suffice.

Any suggestions?
## Post #10
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-09-12T21:44:38+00:00
- Post Title: Wwise *.bnk containers

Um, just select the files you want to process - QuickBMS has a built-in batch feature.
