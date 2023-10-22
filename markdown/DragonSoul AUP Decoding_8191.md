## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-05T17:59:19+00:00
- Post Title: DragonSoul AUP Decoding

All files not packed it looks like this 

```
map\10000\000-000.dds.aup
model\mount\chongdengzuoqi\armoredhorses\armoredhorses_black.mdl.bin.aup
texture\character\assassin\a040_00_00\a040_00_00_chest.dds.aup
ui\textnamepic\zs\bawangzhuiji.tga.aup
```


but encrypted. Need help for decrypting.

Executables and simpe AUP files : [here](http://www.mediafire.com/?x9tx8coxjsrb3bb)

Functions that are used (in order):

```
0076E920 ; void __thiscall halo__resource__File__Create(halo::resource::File *this, const char *szFileName, int iLength)
0076E150 ; int __thiscall halo__resource__Chunk__Create(halo::resource::Chunk *this, _iobuf *fp, int iLength)
0076E230 ; void __thiscall halo__resource__Chunk__Decode(halo::resource::Chunk *this, halo::resource::File *pFile)

```


Thanks advance
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-05T19:07:41+00:00
- Post Title: DragonSoul AUP Decoding

Game looks nice.
Hope someone looks into it.

My first guess is that it's compressed, considering the integer at the beginning of each file relative to the size of the file.
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-05T20:42:57+00:00
- Post Title: DragonSoul AUP Decoding

it's a lzss algorithm that uses a bit by bit flag instead of one of 8 bits each time.
the problem is that I don't know the exact parameters, I have already made some scans but none so I guess that I need to dump the function from the executable... I will keep you update if I continue
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-05T21:41:28+00:00
- Post Title: DragonSoul AUP Decoding

Thanks aluigi will wait for good news
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-05T21:57:41+00:00
- Post Title: DragonSoul AUP Decoding

no good news, I have abandoned.

if you are interested in the main algorithm, it's that simple function at the end of src\libs\tdcb\lzss.c in quickbms.zip
if you set the first 2 #define constants to 13 and 5 you start to get something interesting but still not correct.
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-06T14:53:34+00:00
- Post Title: DragonSoul AUP Decoding

Sad. Thanks you that tried to help.
