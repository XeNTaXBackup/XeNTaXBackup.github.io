## Post #1
- Username: LeviathenX
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Aug 23, 2011 12:57 pm
- Post datetime: 2011-08-23T05:04:43+00:00
- Post Title: Doujin Game (.DAT) Extraction (audio)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2011-08-24T11:30:32+00:00
- Post Title: Doujin Game (.DAT) Extraction (audio)

The contents of this post was deleted because of possible forum rules violation.
## Post #3
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2011-08-28T20:13:18+00:00
- Post Title: Doujin Game (.DAT) Extraction (audio)

gs00.dat - gs04.dat

2 Byte = numFiles
4 Byte = size of FileTable

The (decrypted) Filetable: 
4 byte = offset
4 byte = size
1 byte = length
x byte = name

decryption of FileTable:

```
open griefsyndrome.exe in ollydbg,
enter cf97e in advanced CTRL+G to go to that offset

2. Step: 
place breakpoint on
XOR BYTE PTR DS:[ESI+EBX],AL
and press F9
(ESI+EBX = pointer to decrypted FileTable)

3. Step: 
remove breakpoint, set new breakpoint on
XOR EAX,EAX
press F9

4. Step:
ESI+EBX should now contain the decrypted Table, dump it from memory
and redo the steps for the other 3 dat files.
```


the encryption itself is a 3 step xor encryption

the files have a simple 1 byte xor encryption, but i don't know yet how the game detects what byte to use, 
every file uses a different byte for decryption, but it's easy to find out.

audio files are mdk_*.ogg (data) + mdk_*.sfl (Playlist)
just xor the first byte with 0x4F, to find the decrypt byte

i attached the decrypted file tables + quickbms script for extraction
[griefsyndrome_ft.7z](https://xentaxbackup.github.io/file/4671_griefsyndrome_ft.7z)
## Post #4
- Username: KiyomizuYoshiki
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Aug 30, 2011 3:28 pm
- Post datetime: 2011-08-30T20:23:22+00:00
- Post Title: Doujin Game (.DAT) Extraction (audio)

Sorry to bother you, Falo, but as you seem to be the only one to have cracked it (or at least to have made that knowledge public), could you give me a bit more help?  I'm not new to programming by any means, and I understand your terminology just find, but I'm kind of new to the whole thing of using a debugger (much less one like OllyDbg), so I'm a bit lost...

First, the debugger can't find "cf97e" in CTRL+G or CTRL+F.  What do you mean by "advanced CTRL+G", and are you sure you got the offset right?

Next, how are you doing the XOR decryption?  Are you letting Griefsyndrome.exe handle that for you?  If so, then that ties right in with my first problem, being that I can't get the debugger to do anything useful.  Sure, I can put in the breakpoints, but I can't dump from memory, or even find where I'm supposed to put the breakpoints, meaning it's entirely impossible.

If you could help clear that up, I'd be really grateful.

Thanks in advance,
Kiyo (Hanna)
