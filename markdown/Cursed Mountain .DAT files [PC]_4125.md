## Post #1
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2010-02-07T13:22:58+00:00
- Post Title: Cursed Mountain .DAT files [PC]

Need help to unpack KTM_pc_lang.dat
[KTM_pc_lang.rar](https://xentaxbackup.github.io/file/2773_KTM_pc_lang.rar)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-02-07T15:01:05+00:00
- Post Title: Cursed Mountain .DAT files [PC]

*updated script*

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

get SIGN long   # 0xd2f17e00
getdstring DAT_NAME 32
get FILES long
get EVER1 long
get BASE_OFF long
get ENTRY_SIZE long
get INFO_OFF long

math NAMESZ = ENTRY_SIZE
math NAMESZ -= 24
set FOLDER_OFF long 0x40
math INFO_OFF += FOLDER_OFF
math BASE_OFF += INFO_OFF

goto INFO_OFF
for i = 0 < FILES
    savepos TMP
    get CRC long
    get FOLDER long
    get OFFSET long
    get ZSIZE long
    get SIZE long
    get ZIP long
    getdstring NAME NAMESZ

    savepos TMP
    math FOLDER += FOLDER_OFF
    goto FOLDER
    get FULLNAME string
    goto TMP
    string FULLNAME += NAME
    math OFFSET += BASE_OFF

    if ZIP == 0
        log FULLNAME OFFSET SIZE
    else
        clog FULLNAME OFFSET ZSIZE SIZE
    endif
next i
```
## Post #3
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2010-02-07T15:56:56+00:00
- Post Title: Cursed Mountain .DAT files [PC]

Not working with other files.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-02-07T15:59:39+00:00
- Post Title: Cursed Mountain .DAT files [PC]

can you upload one of them (if there is one small) or the first 2 megabytes of one of them?
## Post #5
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2010-02-07T16:14:16+00:00
- Post Title: Cursed Mountain .DAT files [PC]

Here is L01.dat [6mb] [http://multi-up.com/216545](http://multi-up.com/216545)
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-02-07T19:15:59+00:00
- Post Title: Cursed Mountain .DAT files [PC]

well done, I have updated the script of the previous post
## Post #7
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2010-02-07T20:16:50+00:00
- Post Title: Cursed Mountain .DAT files [PC]

Good work Aluigi, you are the best.   
Any way to pack it all back?
## Post #8
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2010-02-09T11:46:10+00:00
- Post Title: Cursed Mountain .DAT files [PC]

just a tiny thing, if you want to use this script on wii files, just type

```
endian big
```


at the beginning of the script.
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-02-09T14:05:55+00:00
- Post Title: Cursed Mountain .DAT files [PC]

what are the first 4 bytes of the wii files?
if the signature is ever the same is possible to use it for guessing the endianess automatically
## Post #10
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2010-02-09T16:58:39+00:00
- Post Title: Cursed Mountain .DAT files [PC]

Nope, it's the same...i tried this morning...I just knew that wii is in BE because it's a PPC.
## Post #11
- Username: aureliocorreia
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Feb 12, 2008 10:52 am
- Post datetime: 2010-05-13T21:18:23+00:00
- Post Title: Cursed Mountain .DAT files [PC]

Hi, can you help me aluigi?

Its back the file?

Tks...
## Post #12
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-13T21:28:43+00:00
- Post Title: Cursed Mountain .DAT files [PC]

what help?
the script is finished and works, there is nothing else to do.
## Post #13
- Username: aureliocorreia
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Feb 12, 2008 10:52 am
- Post datetime: 2010-05-13T21:32:39+00:00
- Post Title: Cursed Mountain .DAT files [PC]

How to put the modified file right back in the original?
## Post #14
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-05-14T06:53:02+00:00
- Post Title: Cursed Mountain .DAT files [PC]

This is basic knowledge:
unpack the dat, and rename/delete the original dat file, so the game'll read from the unpacked files.

And you can't repack the files, just if you make a repacker.
## Post #15
- Username: aureliocorreia
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Feb 12, 2008 10:52 am
- Post datetime: 2010-05-14T14:44:15+00:00
- Post Title: Cursed Mountain .DAT files [PC]

Thank you. But that part I'm having trouble, I can not do the repack.

Could you help me create one?

Tks
## Post #16
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-05-14T15:25:06+00:00
- Post Title: Re: Cursed Mountain .DAT files [PC]

Like I sad: You can't repack the files. No one can repack this. Moreover, no need to repack.
Don't wasting your time.
## Post #17
- Username: aureliocorreia
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Feb 12, 2008 10:52 am
- Post datetime: 2010-05-14T19:33:02+00:00
- Post Title: Re: Cursed Mountain .DAT files [PC]

I will change the language of the game for the Portuguese, as it does to run the game?
