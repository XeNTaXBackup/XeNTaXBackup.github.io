## Post #1
- Username: Gruselgurke
- Rank: advanced
- Number of posts: 72
- Joined date: Sat Mar 31, 2012 1:15 am
- Post datetime: 2012-08-04T15:30:55+00:00
- Post Title: [REQ] Death Rally .bin [Remedy]

A remake of the classic racer from DOS. It's made by Remedy who made Alan Wake.
The game files are all in "DeathRallyData_000.bin" but unlike Alan Wake everything is in the .bin instead of a combination of .bin and .rmdp. The bin files were only a few MB big in Alan Wake, the main data was in the .rmdp.
I can provide chunks of the file via PM if needed.
## Post #2
- Username: jioc01
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Aug 05, 2012 8:14 pm
- Post datetime: 2012-08-05T12:16:12+00:00
- Post Title: [REQ] Death Rally .bin [Remedy]

News for Extract this unknown format?
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-05T15:02:52+00:00
- Post Title: [REQ] Death Rally .bin [Remedy]

Just XORed. Before XORing need rotate to left bytes.

Example for header :

1) Get original bytes - 99 88 B9 F9
2) Rotate to left bytes - 99 88 9B 9F
3) And XOR by 0xDA
4) Result - CRAE

For decrypted file:

```
4 bytes - Version
2 bytes - TotalFiles - 0x380 // ???
```


for each file:

```
String - FileName
4 bytes - FileSize
```


@Edited.

Here script. Thx Haoose for posf code.

```
get VERSION long
get FILES short
math FILES -= 0x380 # ???
math posf = 0xB143

for i = 0 < FILES
   get NSIZE byte
   getdstring NAME NSIZE
   get SIZE long
   log NAME posf SIZE
   math posf += SIZE
next i
```


Attached decryptor. Just copy in game folder and run DRBINDecrypt.bat. Wait until the decrypting is finished.
Output file -> DeathRallyData_000.bin.dec. After use script for unpack files .
[DRBINDecrypt.rar](https://xentaxbackup.github.io/file/5635_DRBINDecrypt.rar)
## Post #4
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2012-08-05T15:38:56+00:00
- Post Title: [REQ] Death Rally .bin [Remedy]

> Reply from Ekey
>
> Attached decryptor. Just copy in game folder and run DRBINDecrypt.bat. Wait until the decrypting is finished.
Output file -> DeathRallyData_000.bin.dec. You can use any rippers to get graphic / sound .ect. files
BAT FIX.  

```
color a
DRBINDecrypt.exe DeathRallyData_000.bin DeathRallyData_000.bin.dec
pause
```
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-05T15:42:14+00:00
- Post Title: [REQ] Death Rally .bin [Remedy]

Ops yeah forgot add DRBINDecrypt
## Post #6
- Username: jioc01
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Aug 05, 2012 8:14 pm
- Post datetime: 2012-08-05T16:44:54+00:00
- Post Title: [REQ] Death Rally .bin [Remedy]

Thank you very much!!     
Well, can i ask which software/ripper i will use for extract the DeathRallyData_000.bin.dec?

Sorry but i'm very newbie!
## Post #7
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-05T17:25:52+00:00
- Post Title: [REQ] Death Rally .bin [Remedy]

Nova Software Extractor 2.5
Game Extractor
Dragon Unpacker
Ravioli Game Tools v2.5

Choose
## Post #8
- Username: Ekey
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2012-08-05T17:48:30+00:00
- Post Title: [REQ] Death Rally .bin [Remedy]

Unpacker for DeathRallyData_000.bin.dec

[http://www.mediafire.com/?e57im1ooi2d4rab](http://www.mediafire.com/?e57im1ooi2d4rab)

UPD:

```
get VERSION long
get FILES short
math FILES -= 0x380 # ???
math posf = 0xB143

for i = 0 < FILES
   get NSIZE byte
   getdstring NAME NSIZE
   get SIZE long
   log NAME posf SIZE
   math posf += SIZE
next i
```
## Post #9
- Username: jioc01
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Aug 05, 2012 8:14 pm
- Post datetime: 2012-08-05T18:03:38+00:00
- Post Title: [REQ] Death Rally .bin [Remedy]

> Reply from Haoose
>
> Unpacker for DeathRallyData_000.bin.dec

http://www.mediafire.com/?e57im1ooi2d4rab

OMG    you are a god. Thanks a LOT.

> Reply from Ekey
>
> Nova Software Extractor 2.5
Game Extractor
Dragon Unpacker
Ravioli Game Tools v2.5

Choose

Thank you very much
## Post #10
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-05T18:14:31+00:00
- Post Title: [REQ] Death Rally .bin [Remedy]

> Reply from Haoose
>
> 
Code: Select allidstring "CRAE"
get VERSION long
get FILES short
math FILES -= 0x380 # ???
math posf = 0xB143

for i = 0 < FILES
   get NSIZE byte
   getdstring NAME NSIZE
   get SIZE long
   log NAME posf SIZE
   math posf += SIZE
next i

Nice
## Post #11
- Username: jioc01
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Aug 05, 2012 8:14 pm
- Post datetime: 2012-08-05T18:34:30+00:00
- Post Title: [REQ] Death Rally .bin [Remedy]

> for i = 0 < FILES
>
>    get NSIZE byte
>
>    getdstring NAME NSIZE
>
>    get SIZE long
>
>    log NAME posf SIZE
>
>    math posf += SIZE
>
> next i

What programming language it's?
## Post #12
- Username: jioc01
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2012-08-05T18:43:41+00:00
- Post Title: [REQ] Death Rally .bin [Remedy]

jioc01 QuickBMS
## Post #13
- Username: jioc01
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Aug 05, 2012 8:14 pm
- Post datetime: 2012-08-05T18:51:08+00:00
- Post Title: [REQ] Death Rally .bin [Remedy]

> Reply from Haoose
>
> jioc01 QuickBMS

aluigi.altervista.org/quickbms.htm <--- This?!?

I'm a very and big newbie!! lol
## Post #14
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-05T19:19:13+00:00
- Post Title: [REQ] Death Rally .bin [Remedy]

> Reply from jioc01
>
> 
aluigi.altervista.org/quickbms.htm <--- This?!?

I'm a very and big newbie!! lol
Yep
## Post #15
- Username: Gruselgurke
- Rank: advanced
- Number of posts: 72
- Joined date: Sat Mar 31, 2012 1:15 am
- Post datetime: 2012-08-05T19:41:16+00:00
- Post Title: [REQ] Death Rally .bin [Remedy]

Thanks a lot you two!
## Post #16
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2012-08-06T09:54:47+00:00
- Post Title: Re: [REQ] Death Rally .bin [Remedy]

Are you going to write a repacker?  I would love it!
And is there anybody who know which program can edit the font files?
## Post #17
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-06T13:21:35+00:00
- Post Title: Re: [REQ] Death Rally .bin [Remedy]

Edited! Ops my bad
## Post #18
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2012-08-06T13:53:17+00:00
- Post Title: Re: [REQ] Death Rally .bin [Remedy]

Sorry, but i don't get it, how can i use these keys and all...
## Post #19
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-06T14:06:21+00:00
- Post Title: Re: [REQ] Death Rally .bin [Remedy]

> Reply from hunpatrik
>
> Sorry, but i don't get it, how can i use these keys and all...

Never mind my bad. Not for this game posted  ..

> Reply from hunpatrik
>
> And is there anybody who know which program can edit the font files?

I think PNG or TGA format.
## Post #20
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2012-08-06T14:11:58+00:00
- Post Title: Re: [REQ] Death Rally .bin [Remedy]

Yes, the chars in .tga but the coordinates in the .font. So i must edit the font file, to add new letters. (then make the chars graphic in the .tga)
## Post #21
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-06T16:46:35+00:00
- Post Title: Re: [REQ] Death Rally .bin [Remedy]

TGA files just compressed with ZLIB. Use [OffZip](http://aluigi.altervista.org/mytoolz.htm) for decompress.
## Post #22
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2012-08-06T18:43:32+00:00
- Post Title: Re: [REQ] Death Rally .bin [Remedy]

You didn't get me.

I converted the .bin to .dec then decompressed the .dec.
Now in the Risourse\graphics folder there are 2 font and 2 tga files named:
NasalizationSmall.font
NasalizationSmall.tga
Nasalization.font
Nasalization.tga

I can simply open the .tga files with photoshop. But there isn't enough chars to edit for Hungarian translation (i need: öüóőúéáűí)
There are only english alphabets and punctuation marks. So i need to edit the .font file to add more character spaces.
