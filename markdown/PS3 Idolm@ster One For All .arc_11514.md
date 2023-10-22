## Post #1
- Username: mikulover39
- Rank: advanced
- Number of posts: 61
- Joined date: Tue Nov 22, 2011 5:55 pm
- Post datetime: 2014-05-17T15:43:37+00:00
- Post Title: PS3 Idolm@ster One For All .arc

Could someone take a look at this archive please.
It has a file table in the .bin file and the data in the .arc file
here's a sample of one of the archives [http://www.mediafire.com/download/qwe8i ... /IMO4A.rar](http://www.mediafire.com/download/qwe8inahl3i80nc/IMO4A.rar)
## Post #2
- Username: mikulover39
- Rank: advanced
- Number of posts: 61
- Joined date: Tue Nov 22, 2011 5:55 pm
- Post datetime: 2014-05-18T16:48:16+00:00
- Post Title: PS3 Idolm@ster One For All .arc

I made a script do extract the files but they seem to be compressed or encrypted.
If someone could help with this that would be great.
A bit of a messy bms script but it extracts lol

```
open FDDE ARC 0
open FDDE BIN 1
get null1 long 1
get null2 long 1
get files long 1
goto 0x10 1
get fileoff long 1
goto fileoff 1
savepos ntablestart1 1
goto 0x20 1
savepos ntablestart2 1
for i = 0 < files
goto ntablestart2 1
get nameoff long 1
get size long 1
get unk2 long 1
get unk3 long 1
savepos ntablestart2 1
goto ntablestart1 1
get offset long 1
savepos ntablestart1 1
goto nameoff 1
get name string 1
log name offset size 0
next i
```
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-05-18T17:29:47+00:00
- Post Title: PS3 Idolm@ster One For All .arc

they are encrypted with most likely aes someone will have to dump the key.
its the same for all of the idolmaster games after the first one.
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-18T18:29:45+00:00
- Post Title: PS3 Idolm@ster One For All .arc

We can try to find key if encryption is AES. Just share eboot
## Post #5
- Username: mikulover39
- Rank: advanced
- Number of posts: 61
- Joined date: Tue Nov 22, 2011 5:55 pm
- Post datetime: 2014-05-18T18:37:28+00:00
- Post Title: PS3 Idolm@ster One For All .arc

here's the eboot [http://www.mediafire.com/download/cv9sf ... IMO4AE.rar](http://www.mediafire.com/download/cv9sfsdwdp99qhf/IMO4AE.rar)
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-18T21:20:35+00:00
- Post Title: PS3 Idolm@ster One For All .arc

Well signsrch did not find AES signatures but found Blowfish.

```
007b3168 206  Blowfish ks0 table [32.be.1024]
007b3568 208  Blowfish ks1 table [32.be.1024]
007b3968 210  Blowfish ks2 table [32.be.1024]
007b3d68 212  Blowfish ks3 table [32.be.1024]
007b3168 1620 Blowfish_s_init [32.be.4096]
```
## Post #7
- Username: mikulover39
- Rank: advanced
- Number of posts: 61
- Joined date: Tue Nov 22, 2011 5:55 pm
- Post datetime: 2014-05-19T06:40:12+00:00
- Post Title: PS3 Idolm@ster One For All .arc

Oh so it uses a different type of encryption, do you think we would be able to find the key for it?
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-19T13:06:43+00:00
- Post Title: PS3 Idolm@ster One For All .arc

Not confirmed that encryption is Blowfish. Probably but not sure.
## Post #9
- Username: mikulover39
- Rank: advanced
- Number of posts: 61
- Joined date: Tue Nov 22, 2011 5:55 pm
- Post datetime: 2014-05-19T16:58:38+00:00
- Post Title: PS3 Idolm@ster One For All .arc

Well looking at this eboot and the one for the previous game they do both contain the same line about AES encryption "nuscDecryptAES"
