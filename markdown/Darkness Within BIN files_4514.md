## Post #1
- Username: Sheen
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 03, 2010 2:29 am
- Post datetime: 2010-05-26T19:38:57+00:00
- Post Title: Darkness Within BIN files

Hi,

I would like to translate this game into spanish but i cannot open the bin files. I have tried everything, I think, but nothig. 

There is a some-like BMS script for this game and its bin files?

I have uploaded a Bin file, the smallest one, to Megaupload.

[File](http://www.megaupload.com/?d=Q1HZ43TQ)

Thanks.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-27T13:08:44+00:00
- Post Title: Darkness Within BIN files

```
for FILES = 0
    get DUMMY long
    if DUMMY == 0
        break
    endif
    get SIZE long
    get NAMESZ byte
    getdstring NAME NAMESZ
next FILES

savepos OFFSET
goto 4
for i = 0 < FILES
    get DUMMY long
    get SIZE long
    get NAMESZ byte
    getdstring NAME NAMESZ
    string NAME += _
    string NAME += i
    string NAME += ".lua"
    log NAME OFFSET SIZE
    math OFFSET += SIZE
next i
```
## Post #3
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-05-27T18:47:54+00:00
- Post Title: Darkness Within BIN files

I think, you are looking for the "local.bin" file, whitch has this structure:

```
         NrofFiles : WORD;
         Unknown : WORD; // $1000
   -> Directory: (NrOfFiles * 16 bytes)
       for each file:
       -> FileID : DWORD;
       -> RelativeFilePos : DWORD; // from the Start of The "File Data"
       -> FileSize : DWORD; // size of the file, no compression used
       -> CheckSum : DWORD; // the negative of the data's CRC32 value
   -> File Data...

```

The game text file is the file with FileID 0xFCD0A552

I also created a primitive BIN extractor for the "local.bin" file

Usage: darkeXtr.exe <BIN_File> <TargetDir>
example: darkeXtr.exe local.bin e:\temp\target

A .BIN updater also included!

Usage: darkUpdater.exe <BIN_File> <DataFile_to_Update> <IDnumber>
example: darkUpdater.exe local.bin e:\mytranslation\mytext.txt FCD0A552
## Post #4
- Username: Sheen
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 03, 2010 2:29 am
- Post datetime: 2010-05-30T14:08:05+00:00
- Post Title: Darkness Within BIN files

Firstly, thanks to both for your support.

You're right bacter, this is the file I needed to translate the game. Anyway, always is a good idea to explore all the files to see if there are some files to change as well. Really there are a couple of files out of Local to change but local.bin is what I needed. Really, you're great! with your executable all bin files has been decompressed, except scripts.bin, but without your updater executable an effective translation would have been impossible. Really, you're great!

Best regards!
## Post #5
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-05-30T15:32:46+00:00
- Post Title: Darkness Within BIN files

Important!
I found a bug in the previous version of my BIN updater, so I replaced it with a new,
hopefully bugfree version!
## Post #6
- Username: Zavan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 30, 2010 11:58 am
- Post datetime: 2010-06-30T15:35:54+00:00
- Post Title: Darkness Within BIN files

Hi guys, I have a problem. After updating the file, the game continues in English. So I extracted the local.bin file again and noticed the file FCD0A552 is the same that I translated. Does anyone know why the game was not translated? It is necessary do more than update local.bin? Thanks
## Post #7
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-06-30T21:05:37+00:00
- Post Title: Darkness Within BIN files

I created the GUI version of the BIN extractor,updater. Try that. I hope it's not too hard to use.
See the Darkness Within 2 forum topic: [viewtopic.php?f=10&t=4530&p=40053#p40053](http://forum.xentax.com/viewtopic.php?f=10&t=4530&p=40053#p40053)
## Post #8
- Username: SergioKool
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jun 29, 2010 10:48 pm
- Post datetime: 2010-07-12T19:34:04+00:00
- Post Title: Darkness Within BIN files

hi mate the tool work almost all files but one   and i think the text files are there its the scripts.bin i send a photo of the error that give me :

[http://img682.imageshack.us/img682/7911/erroo.png](http://img682.imageshack.us/img682/7911/erroo.png)

please can you fix this on your tool to read that file ?
## Post #9
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-07-13T03:52:24+00:00
- Post Title: Darkness Within BIN files

Hey!
Why don't you read carefully this topic?

My proggy not supports the scripts.bin file, because it uses a completely different structure, and because there are no useful game resources in that file.
There are no images, text files etc.  It contains only compiled lua scripts. I don't think that anyone wants to edit them.
But, if you REALLY need the files inside the script.bin, you need to use the QuickBMS program.
See the comment of aluigi, (second entry of this topic) posted at: Thu May 27, 2010 2:08 pm
If you are looking for the ingame texts, then see my comment  (third entry of this topic) posted at: Thu May 27, 2010 7:47 pm
## Post #10
- Username: SergioKool
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jun 29, 2010 10:48 pm
- Post datetime: 2010-07-14T13:21:07+00:00
- Post Title: Darkness Within BIN files

tks mate my bad tks a lot for the answer
