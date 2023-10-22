## Post #1
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-04T20:49:23+00:00
- Post Title: VRC PRO - .VRC and .VRH

Does anybody know how to open these? I would like to dig into this game's files, but they're encrypted in these VRC and VRH files.
Samples:
VRC: 
[https://www.mediafire.com/file/rkaculdz ... 1.vrc/file](https://www.mediafire.com/file/rkaculdzhr6pb9r/8_bu_1.vrc/file)
VRH:
[https://www.mediafire.com/file/hwgxd6jm ... 1.vrh/file](https://www.mediafire.com/file/hwgxd6jmfhel2tc/8_bu_1.vrh/file)
Thanks.
## Post #2
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-05T16:55:04+00:00
- Post Title: VRC PRO - .VRC and .VRH

I found a VRC quickbms! Did not expect that since how dead the community of this game is.
But the sad part is, and there's always a sad part, is that "the input file doesn't seem encrypted". ???
## Post #3
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-16T23:01:53+00:00
- Post Title: VRC PRO - .VRC and .VRH

Still looking for info on this subject.
## Post #4
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-04-18T23:34:35+00:00
- Post Title: VRC PRO - .VRC and .VRH

Anybody?
## Post #5
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-08-31T18:38:28+00:00
- Post Title: VRC PRO - .VRC and .VRH

Decryptio.....
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2021-09-24T15:50:43+00:00
- Post Title: VRC PRO - .VRC and .VRH

Well, VRC, VRH, CAR files is encrypted by AES-256-CBC. Output data is a passwored ZIP. So here script for convert this files to normal ZIP

Password for ZIP's -> d17856f1ce

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

get SIZE asize
goto 9
savepos OFFSET
math SIZE -= 9

encryption aes_256_cbc "\xB6\x8E\x4D\x98\xBC\xDB\x62\x1B\x0E\x98\x52\x05\xD0\x07\x5C\xF2\xAA\x53\xC4\x88\xAE\x41\xFD\xC7\xFE\x1D\xA7\xD6\xC7\x6E\xA1\x7F"
log MEMORY_FILE OFFSET SIZE
encryption "" ""

putvarchr MEMORY_FILE 0 0x4034B50 long
putvarchr MEMORY_FILE 4 0x90014 long
putvarchr MEMORY_FILE 8 0x8 long
putvarchr MEMORY_FILE 12 0 long
putvarchr MEMORY_FILE 16 0 long
putvarchr MEMORY_FILE 20 0 short

get NAME basename
string NAME += ".zip"

log NAME 0 SIZE MEMORY_FILE
```


Have fun
## Post #7
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-12-22T17:54:32+00:00
- Post Title: VRC PRO - .VRC and .VRH

The zip it outputs is corrupted...
Nevermind I extracted the VRC instead of VRH
But the password you gave me is incorrect.
## Post #8
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-12-22T18:15:04+00:00
- Post Title: VRC PRO - .VRC and .VRH

Well it is correct for XGB, XML and MEDIA.XML, but not TGA.
