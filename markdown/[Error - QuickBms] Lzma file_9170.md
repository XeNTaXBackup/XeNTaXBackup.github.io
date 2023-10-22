## Post #1
- Username: Noobie
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 30, 2012 2:02 am
- Post datetime: 2012-06-29T18:06:39+00:00
- Post Title: [Error - QuickBms] Lzma file

Hello xentax comunity!
I'm having an error while trying to reimport few files, the error is this one:

As you can see, the file is smaller than the original, so i don't know why this is happening.
I'm using this script:

```
# script for QuickBMS http://quickbms.aluigi.org

comtype lzma
open FDDE "cfp"
getdstring TYPE 2
get DUMMY longlong
get OFFSET longlong
goto OFFSET
set PATH string ""
set NAME string ""
math VAL1 = 0
math VAL2 = 0
callfunction ENTRY 1
callfunction EXTRACT

startfunction EXTRACT
    string PATH += NAME
    string PATH += /

    math FOLDERS = VAL1
    math FILES = VAL2
    for i = 0 < FOLDERS
        callfunction ENTRY 1
        callfunction EXTRACT
    next i
    for i = 0 < FILES
        callfunction ENTRY 1
        set FNAME string PATH
        string FNAME += NAME
        savepos TMP
        goto VAL1
        get SIZE long
        get ZSIZE long
        savepos OFFSET
        goto TMP
        math ZSIZE += 5
        clog FNAME OFFSET ZSIZE SIZE
    next i
endfunction

startfunction ENTRY
    getdstring TYPE 2
    get VAL1 long
    get VAL2 long
    get NAMESZ short
    math NAMESZ *- 2
    getdstring NAME NAMESZ
    set NAME unicode NAME
endfunction

```

It was created by aluigi in another topic, a guy asking for extracting .cfp files.
Note: Few files are sucessfully reimported, but most part fail.


Thanks for any help.

Noobie!
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-06-30T02:47:04+00:00
- Post Title: [Error - QuickBms] Lzma file

the bad thing I see there is that your new file is smaller than the original (correct) but its compressed size is bigger.
I use lzma with maximum compression so similar things should never happen but are you sure you have not increased the "complexity" of the original file?

because for reaching that situation (small file -> bigger compressed file) the only hypothesis is that  there are many different chars.
## Post #3
- Username: Noobie
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 30, 2012 2:02 am
- Post datetime: 2012-06-30T03:53:17+00:00
- Post Title: [Error - QuickBms] Lzma file

In fact this may be the reason, since they`r audio files.
But the diference isn`t that big, is just a HYAAA.
The original file got 850 kb, this file only 230kb both files are from the original game devolper.
so i don`t know whats happening.


thanks aluigi.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-06-30T12:29:00+00:00
- Post Title: [Error - QuickBms] Lzma file

upload both the original and modified audio file, I want to make some tests to know if I can improve the compression ratio or it's already at its max
## Post #5
- Username: Noobie
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 30, 2012 2:02 am
- Post datetime: 2012-06-30T16:13:03+00:00
- Post Title: [Error - QuickBms] Lzma file

You mean the package or the audio files?
If you mean the audio files, here is:
Original:[http://www.sendspace.com/file/lh5yu2](http://www.sendspace.com/file/lh5yu2)
Modified:[http://www.sendspace.com/file/u7ulso](http://www.sendspace.com/file/u7ulso)

The packages are 500mb, i can't upload they.


Thanks for the support


@edit
i tryed extract the modded file and i got an error about invalid compression size.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-06-30T20:08:23+00:00
- Post Title: [Error - QuickBms] Lzma file

checked and is exactly as I said, your new file is smaller but is more complex (more different bytes), that's why it takes more space when compressed.
so it's all correct, quickbms is ok.
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-30T20:42:59+00:00
- Post Title: [Error - QuickBms] Lzma file

Don't know much about audio but is there only way to produce wav files? Or are there various different types and formats?

Maybe the wav should be encoded in a specific format so that it matches the one used in the game, so you'd have to then do some more research into what kind of techniques they've used aside from just figuring out how they packaged the data.
