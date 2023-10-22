## Post #1
- Username: Insanius
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Apr 01, 2010 11:51 am
- Post datetime: 2011-01-07T05:41:48+00:00
- Post Title: Dark Awake .msf Audio Files

Using a new tool released on PSGroove I've extracted files from the PS3 PSN game Dark Awake and I've come across audio with an identifier string MSFC

I've looked on this forum and I saw a few posts that involved converting the header to .at3 and installing the ATRAC3 codec but it did not work.  I also tried playing it as is using the vgmstream plugin for foobar2000 but that also failed.

The header is 64 bytes and seems to have filler (0xff) for 40 of them.
[bgm.zip](https://xentaxbackup.github.io/file/3776_bgm.zip)
## Post #2
- Username: mauzerX
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jul 01, 2010 8:48 pm
- Post datetime: 2011-01-08T05:57:02+00:00
- Post Title: Dark Awake .msf Audio Files

> Reply from Insanius
>
> Using a new tool released on PSGroove I've extracted files from the PS3 PSN game Dark Awake and I've come across audio with an identifier string MSFC

I've looked on this forum and I saw a few posts that involved converting the header to .at3 and installing the ATRAC3 codec but it did not work.  I also tried playing it as is using the vgmstream plugin for foobar2000 but that also failed.

The header is 64 bytes and seems to have filler (0xff) for 40 of them.
try [QuickBMS](http://aluigi.altervista.org/papers.htm#quickbms) with  [script by AlphaTwentyThree](http://forum.xentax.com/viewtopic.php?f=13&p=43570#p43570)
## Post #3
- Username: buckybean
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 17, 2011 12:01 pm
- Post datetime: 2011-01-17T04:19:55+00:00
- Post Title: Dark Awake .msf Audio Files

I was having similiar problems and wound up here. I was able to quickBMS+alpha's script with Insanius' two .msf file, but not mine... hehe. The file is from PS3 Atelier Totori's SE folder with same MSFC header.
[BAKUHA04.zip](https://xentaxbackup.github.io/file/3810_BAKUHA04.zip)
## Post #4
- Username: mauzerX
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jul 01, 2010 8:48 pm
- Post datetime: 2011-01-17T07:53:46+00:00
- Post Title: Dark Awake .msf Audio Files

> Reply from buckybean
>
> I was having similiar problems and wound up here. I was able to quickBMS+alpha's script with Insanius' two .msf file, but not mine... hehe. The file is from PS3 Atelier Totori's SE folder with same MSFC header.
try old script,it's playble,but non perfect

```
# written by AlphaTwentyThree of XeNTaX
# converts PS3 *.msf containers to playable Atrac files

IDstring MSF
set MEMORY_FILE binary "\x52\x49\x46\x46\x88\xb3\x6d\x0\x57\x41\x56\x45\x66\x6d\x74\x20\x20\x0\x0\x0\x70\x2\x2\x0\x80\xbb\x0\x0\x9a\x40\x0\x0\x80\x1\x0\x0\xe\x0\x1\x0\x0\x10\x0\x0\x0\x0\x0\x0\x1\x0\x0\x0\x66\x61\x63\x74\x8\x0\x0\x0\x91\x81\x24\x1\x1b\x4\x0\x0\x64\x61\x74\x61\x88\xb3\x6d\x0"
endian big
get SIGN byte
get BITSIGN long
get UNK long
get SIZE long
get FREQ long
set SKIP 0x40
get NAME basename
get SIZE asize
math SIZE -= SKIP
string NAME += ".at3"
set RIFFSIZE SIZE
math RIFFSIZE += 0x44

endian little
putVarChr MEMORY_FILE 0x04 RIFFSIZE long
putVarChr MEMORY_FILE 0x18 FREQ long
putVarChr MEMORY_FILE 0x48 SIZE long
if BITSIGN == 4 # 66 kbps
      putVarChr MEMORY_FILE 0x1c 0x204d long
      putVarChr MEMORY_FILE 0x20 0xc0 long
elif BITSIGN == 5 # 105 kbps
      putVarChr MEMORY_FILE 0x1c 0x3324 long
      putVarChr MEMORY_FILE 0x20 0x130 long
elif BITSIGN == 6 # 132 kbps
      putVarChr MEMORY_FILE 0x1c 0x409a long
      putVarChr MEMORY_FILE 0x20 0x180 long
endif

append
log MEMORY_FILE SKIP SIZE
append
math SIZE += 0x4c
log NAME 0 SIZE MEMORY_FILE
```
## Post #5
- Username: buckybean
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 17, 2011 12:01 pm
- Post datetime: 2011-01-17T12:55:17+00:00
- Post Title: Dark Awake .msf Audio Files

Thanks a bunch for the suggestion mauserX; it worked out fine. The older script worked for all 96 soundeffect .msf files. Yay!
## Post #6
- Username: Crash
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 27, 2021 3:37 am
- Post datetime: 2021-03-13T00:57:35+00:00
- Post Title: Dark Awake .msf Audio Files

I know this post very old so sorry to bump it again, is there a way to repack the .at3 file into a .msf? I've been trying but I keep running into errors with the file header being a RIF not MSF and am unsure of the fix.
