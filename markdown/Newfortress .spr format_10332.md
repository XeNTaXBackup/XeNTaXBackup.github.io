## Post #1
- Username: qogudwnssla
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 13, 2011 12:02 pm
- Post datetime: 2013-04-13T07:48:00+00:00
- Post Title: Newfortress .spr format

this game which luched in 2005 [http://game.donga.com/images/news_image ... 050620.jpg](http://game.donga.com/images/news_images_n/newfortres050620.jpg) 
has filetype called .spr. i think .spr is containing a .GIF file for a sprite of the game.

but i can't open it.
[http://www.mediafire.com/download.php?l9v48x9coqgo6kz](http://www.mediafire.com/download.php?l9v48x9coqgo6kz) - .spr 10kb
[http://www.mediafire.com/download.php?k553xkgap4dhf2y](http://www.mediafire.com/download.php?k553xkgap4dhf2y)    - .spr file 2.45 kb                                                                                                 
[http://www.mediafire.com/download.php?6d8886tldx1tgrd](http://www.mediafire.com/download.php?6d8886tldx1tgrd)  - .spr file which is just 1.56kb (the smallest size on the folder)
I think if .spr file of minimum kb(1.56kb) can be opened rest of them will be opened.

and i found the .pdb file inside the directory.
[http://www.mediafire.com/download.php?69wp9ynll1hj49f](http://www.mediafire.com/download.php?69wp9ynll1hj49f)  - pdb file.

help on extracting graphic files.
[missile_a_fall3.png](https://xentaxbackup.github.io/file/6328_missile_a_fall3.png)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-04-25T08:02:44+00:00
- Post Title: Newfortress .spr format

> Reply from qogudwnssla
>
> i think .spr is containing a .GIF fileMaybe.
Why do you think it's containing a .GIF?
If so you could try to replace the header block.
(infos on GIF header: [http://www.matthewflickinger.com/lab/wh ... _bytes.asp](http://www.matthewflickinger.com/lab/whatsinagif/bits_and_bytes.asp))

> and i found the .pdb file inside the directory.
Hmm, the only valuable info in the pdb seems to be:
std::allocator<CSprImg *>

If it's a PC release you could try to rip textures using DX ripper.
Look for missiles and compare the related files to missile_a_fall.spr
## Post #3
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2013-04-26T23:29:19+00:00
- Post Title: Newfortress .spr format

Here's some info about the .spr file format:

```
00 0D 00 00	?
01 00 00 00	numSprites
for (numSprites) {
60 00 00 00	width
3D 00 00 00	height
30 00 00 00	?
0D 00 00 00	?
19 00 00 00	?
FF FF... (0x100 bytes)	maybe a R5G6R5 color table with 0x80 entries?
C0 2D 00 00	sizeUncompressed (= width*height*2)
F6 07 00 00	sizeCompressed
compressedData
}
...
unknown data at file end
```
But I haven't figured out how the sprites are compressed.
## Post #4
- Username: qogudwnssla
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 13, 2011 12:02 pm
- Post datetime: 2013-04-28T01:20:04+00:00
- Post Title: Newfortress .spr format

Thanks for helping guys
about gif files. In the deveoper's blog, they posted their
sprite works as gif files. so it was just a mere guess.  
([http://postfiles6.naver.net/20121021_53 ... if?type=w2](http://postfiles6.naver.net/20121021_53/ory4860_1350808379074whGyg_GIF/%B7%CE%BA%F3%BD%BA%C5%B3.gif?type=w2))
-from developer's blog

using dx ripper.....
the game can not be played(executable) because it was online game 
but it has been deceased. 
if you need other files i will post them right away.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-04-28T17:51:37+00:00
- Post Title: Newfortress .spr format

> Reply from qogudwnssla
>
> the game can not be played(executable) because it was online game 
but it has been deceased.too bad - then we will not be able to get uncompressed sprites from RAM.
(to compare them with the compressed data to understand how compression is done)

I tried Aluigi's comtype_scan2 on 1125 (0x465) bytes compressedData (see Herbert3000's post) but I didn't get any uncompressed file of size 6944 (0x1B20) bytes as it would be required.

(Maybe you should investigate on sprite compression algos?)
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-04-29T06:23:32+00:00
- Post Title: Newfortress .spr format

> Reply from qogudwnssla
>
> and i found the .pdb file inside the directory.
http://www.mediafire.com/download.php?69wp9ynll1hj49f  - pdb file.
Well from PDB

```
CCompress::Encode
CCompress::Decode
CCompress::SpriteEncode
CCompress::SpriteDecode
CCompress::HuffEncodeStart
CCompress::HuffEncodeEnd
CCompress::HuffDecodeStart
CCompress::HuffDecodeEnd
CCompress::EncodeP
CCompress::DecodeP
CCompress::MakeTable
```


for reverse algo need full game. Or try [this](http://www.codeproject.com/Articles/25088/Huffman-compression-class-in-C)
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-04-29T09:31:08+00:00
- Post Title: Newfortress .spr format

> Reply from Ekey
>
> Or try thisThx.
We could give the compressed data block a header:
48 55 46 46  FF 00 00 00   20 1B 00 00  65 04 00 00
This is "HUFF", number of symbols, uncompressed size, compressed size

Problem is: we don't know the  number of symbols (nofs) in the uncompressed data.
What's a symbol? A byte?
So we'll have to guess; tried different dec. values for nofs: 20, 21, 22, 30, 64, 127, 254, 255.

None of the resullting uncompressed files contained any kind of regular blocks.
(But there are some numbers left...)

edit: hmm, seems that the header also needs a table of the different symbols and their count (starting with the most frequent one).

So this won't lead to a solution imho.
Nevertheless here a sample of an uncompressed file and its Huffman compressed counter part:

```

0000   41 41 41 FF FF FF 41 42  43 44 45 46 47 48 5A 5A
0010   5A 5A 5A 5A
```


```

0000   48 55 46 46 0A 00 00 00  14 00 00 00 4A 00 00 00
0010   06 00 00 00 5A 04 00 00  00 41 03 00 00 00 FF 01
0020   00 00 00 48 01 00 00 00  46 01 00 00 00 45 01 00
0030   00 00 44 01 00 00 00 43  01 00 00 00 42 01 00 00
0040   00 47 A9 25 73 E6 B3 DA  00 00
```


(yes, in this example the compressed file is of bigger size because of the source file being too small.)
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-04-29T10:36:00+00:00
- Post Title: Newfortress .spr format

For correct answer need full game. Maybe used modified HUFF compress method or other algo.
## Post #9
- Username: qogudwnssla
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 13, 2011 12:02 pm
- Post datetime: 2013-04-29T11:25:42+00:00
- Post Title: Newfortress .spr format

Here is the full game. compressed in .zip
[http://www.mediafire.com/download.php?jab9ormpx052pfr](http://www.mediafire.com/download.php?jab9ormpx052pfr)
[1.png](https://xentaxbackup.github.io/file/6368_1.png)
## Post #10
- Username: RayKoopa
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Sep 20, 2021 9:10 pm
- Post datetime: 2021-09-20T13:19:29+00:00
- Post Title: Newfortress .spr format

Sorry for the necro bump. No need for a new thread since most assumptions in this thread are correct and, well, the game didn't change since then .

Here's the format of SPR files; names given as found in PDB (which sadly doesn't line up with the EXE I have):

```
- DWORD probably version (ignored)
- DWORD number of CSprImg (sprite) instances following
For each CSprImg:
- INT m_nWidth
- INT m_nHeight
- INT m_BaseX
- INT m_BaseY
- INT m_PixelFormat (D3DFORMAT, s. below)
- SHORT m_ShareIndex
- CHAR[0xFE] unused (possibly deprecated palette, s. below)
- ULONG OrigSize
- ULONG SourSize
- UCHAR[SourSize] m_pImgData (LZ77 Huffman compressed, s. below)

```


The PixelFormat maps to the D3DFORMAT enum. The SPR files I have only ever use A1R5G5B5 and A4R4G4B4 (the latter only for ready_D).
 There are 0xFE unused bytes which possibly were palette data. However, the game uses no indexed images. Since New Fortress is based on the original Fortress, the original game may indeed have used this for palette data. It now only stores memory trash and is ignored by code.
For compression, the game uses a modified version of Intel's EFI Compression from 2001/2002, s. Appendices H (Compressor) and I (Decompressor). CCR copypasta'd it into their CCompress class and changed globals to become instance data. Newer versions of the compression as found on GitHub are apparently not compatible.
There is more information following the sprites, but I didn't bother about them yet as you probably won't need them to rip sprites.
You can also test your decompression on gsysdata.dat, it stores the decompressed size as a DWORD, and the remainder is compressed data, the output file is a 949 Korea encoded text file consisting of game messages.


I uploaded source code and utility decompressing / converting all sprites [here](https://gitlab.com/Syroot/Fortress).
