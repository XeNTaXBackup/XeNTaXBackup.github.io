## Post #1
- Username: frogz2007
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Nov 10, 2014 9:13 am
- Post datetime: 2014-11-30T21:14:37+00:00
- Post Title: Sly Cooper and the Thievius Raccoonus .WAL extractor?

In the E3 demo of Sly Cooper and the Thievius Raccoonus, there is a .WAL file containing, if I'm correct, all of the level/game data. I am wondering: Could somebody try to make a decompressor/rebuilder? I am asking for this because, if opened in a hex editor, the game mentions the first boss fight, which ISN'T playable in the demo and it'd be cool to see if it is functional. It is 103 MB decompressed and 62.9 MB compressed.

Download:

[https://www.mediafire.com/?aygx88w3wk357er](https://www.mediafire.com/?aygx88w3wk357er)
## Post #2
- Username: root670
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Dec 18, 2010 6:11 am
- Post datetime: 2014-12-17T19:27:16+00:00
- Post Title: Sly Cooper and the Thievius Raccoonus .WAL extractor?

I've found the crypt routine in the game's code and wrote a program to encrypt/decrypt the header file (SLY.WAC). It's symmetric, so the algorithm used to decrypt data can also be used to encrypt it. I was working on a file extractor to pull data out of SLY.WAL, but it's not fully stable yet.

Here is the function to decrypt/encrypt SLY.WAC:

```
{
	// 0013B810
	// 0014D1C4
	uint32_t a0;
	uint32_t i = len;
	uint8_t *a2 = buf;
	uint32_t v0 = 0x1DBA1; // Sly 1 Demo
	//uint32_t v0 = 0x7A69; // Sly 2 and Sly 3 demo


	// 0013A834 - Sly 1 Demo
	// 00161FB8 - Sly 3 Demo
	while(i--)
	{
		v0 *= 0x01A3;
		v0 += 0x181D;
		v0 %= 0x7262;

		a0 = v0 << 8;
		a0 -= v0;
		a0 /= 0x7262;

		*a2 ^= a0;
		a2 += 1;
	}
}
```


As you might notice from the comments, the same algorithm is used in the Sly 2 and Sly 3 demos. They use a slightly different format though, where the header is merged with the data in one file. If you run the crypt function over the data file from the Sly 2/3 demo, the header will be revealed in the first few hundred bytes.

Here's how SLY.WAC looks after being decrypted:

It's just a string dump for all the filenames followed by offset+length pairs later in the file.

...And if my understanding of the header format is correct, these should be the proper addresses and sizes of entries in SLY.WAL:

> action_trailer.pss 0 3bd0004
>
> attract 3bd0800 73b160
>
> basm01.vag 430c000 fce0
>
> basm02.vag 431c000 7ec0
>
> basm03.vag 4324000 14720
>
> basm04.vag 4338800 4130
>
> basm05.vag 433d000 6d80
>
> basm07.vag 4344000 c780
>
> basm08.vag 4350800 3380
>
> basm09.vag 4354000 66b0
>
> basm10.vag 435a800 2df0
>
> basm11.vag 435d800 11d30
>
> basm12.vag 436f800 2ce0
>
> basm13.vag 4372800 8da0
>
> basm14.vag 437b800 4430
>
> basm15.vag 4380000 c1f0
>
> cluea01.vag 438c800 2f480
>
> clueb01.vag 43bc000 167f0
>
> clueb03.vag 43d2800 247d0
>
> cluec01.vag 43f7000 1b740
>
> copy.ico 4412800 9668
>
> core.bnk 441c000 ac89c
>
> delete.ico 44c9000 9668
>
> hubral.bnk 44d2800 74f6c
>
> keycel.vag 4547800 1b0f0
>
> libral.bnk 4563000 72268
>
> list.ico 45d5800 9668
>
> outral.bnk 45df000 7453c
>
> secral.bnk 4653800 745b4
>
> splash 46c8000 b3470
>
> uw_bonus_library 477b800 63b6f0
>
> uw_bonus_library\Underwater.bnk 4db7000 8f3cc
>
> uw_bonus_security 4e46800 5a8400
>
> uw_bonus_security\Underwater.bnk 53ef000 8f3cc
>
> uw_exterior_approach 547e800 782120
>
> uw_exterior_approach\Underwater.bnk 5c01000 8f3cc
>
> uw_exterior_boat 5c90800 73ced0
>
> uw_exterior_boat\Underwater.bnk 63cd800 8f3cc
>
> uwai01.vag 645d000 9150
>
> uwai02.vag 6466800 8ee0
>
> uwai03.vag 646f800 128b0
>
> uwai04.vag 6482800 143a0
>
> uwai05.vag 6497000 a230
>
> uwai06.vag 64a1800 13d40
>
> uwai07.vag 64b5800 5f50
>
> uwai08.vag 64bb800 eef0
>
> uwai09.vag 64ca800 11490
>
> uwai10.vag 64dc000 7850
>
> uwal01.vag 64e4000 ca80
>
> uwal02.vag 64f1000 78e0
>
> uwal03.vag 64f9000 149c0
>
> uwal04.vag 650e000 63e0
>
> uwal05.vag 6514800 2a7a0
>
> uwal06.vag 653f000 ebd0
>
> uwal07.vag 654e000 1bcb0
>
> uwal08.vag 656a000 3480
>
> uwal09.vag 656d800 5d60
>
> uwal10.vag 6573800 16e0
>
> uwas01.vag 6575000 116b0
>
> uwas02.vag 6586800 b300
>
> uwas03.vag 6592000 b680
>
> uwas04.vag 659d800 a350
>
> uwas05.vag 65a8000 12050
>
> uwas06.vag 65ba800 9660
>
> uwas07.vag 65c4000 12160
>
> uwas08.vag 65d6800 6630
>
> uwas09.vag 65dd000 122f0
>
> uwas10.vag 65ef800 14ed0
>
> uwbs01.vag 6604800 1e300
>
> uwgn01.vag 6623000 3c80
>
> uwgn03.vag 6627000 18180
>
> uwli01.vag 663f800 6cf0
>
> uwli02.vag 6646800 9c10
>
> uwli03.vag 6650800 5e00
>
> uwli04.vag 6656800 bac0
>
> uwli05.vag 6662800 84d0
>
> uwli06.vag 666b000 4630
>
> uwli07.vag 666f800 e920
>
> uwli08.vag 667e800 6080
>
> uwli09.vag 6685000 6af0
>
> uwli10.vag 668c000 6030
>
> uwli11.vag 6692800 46a0
>
> uwli12.vag 6697000 ac90
>
> uwli13.vag 66a2000 cf20
>
> uwli14.vag 66af000 4000
>
> uwsb01.vag 66b3000 11920
>
> uwsb02.vag 66c5000 2830
>
> uwsb03.vag 66c8000 9e20
>
> uwsn01.vag 66d2000 6930
>
> uwsn02.vag 66d9000 13c0
>
> uwsn03.vag 66da800 6640
>
> uwsn04.vag 66e1000 30ae0
>
> uwsn05.vag 6712000 dfe0
>
> uwsn06.vag 6720000 11af0
>
> uwsn07.vag 6732000 3510
>
> vcom05.vag 6735800 11610
>
> vcom206.vag 6747000 22470
>
> vcom650.vag 6769800 1f080
>
> vgal01.vag 6789000 83c0
>
> vgmo.vag 6791800 a4c0
>
> vgmt.vag 679c000 e040
>
> vgol.vag 67aa800 7c00
>
> vise01.vag 67b2800 16190
>
> vise02.vag 67c9000 105c0
>
> vise03.vag 67d9800 ff10

Would love to see what someone would be able to do with these files.
## Post #3
- Username: frogz2007
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Nov 10, 2014 9:13 am
- Post datetime: 2014-12-28T16:13:49+00:00
- Post Title: Sly Cooper and the Thievius Raccoonus .WAL extractor?

Didn't expect that! Thanks! Is there any way you could upload a compiled version of the program/script?
## Post #4
- Username: root670
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Dec 18, 2010 6:11 am
- Post datetime: 2014-12-28T17:58:42+00:00
- Post Title: Sly Cooper and the Thievius Raccoonus .WAL extractor?

Sure, give this a try: [http://www.mediafire.com/download/jjoou ... ecrypt.exe](http://www.mediafire.com/download/jjoouddkywoaeoz/sly-decrypt.exe) . This will work with the Sly E3 demo.

Usage: sly-decrypt SLY.WAC SLY.WAL. I've figured out what most of the file formats are:

bnk - Music for 989 Sound Driver (989SND.IRX). Note that the same format is used in Jak and Daxter. I replaces a MUS file in the Jak demo and it worked!
ico - Memory card save icon
vag - Voice audio (ADPCM)
pss - Standard PS2 video file

The files without extensions contain level assets.
## Post #5
- Username: frogz2007
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Nov 10, 2014 9:13 am
- Post datetime: 2014-12-28T23:00:20+00:00
- Post Title: Sly Cooper and the Thievius Raccoonus .WAL extractor?

Marvelous work! Now, there's another problem; The full game has the SLY.WAC and SLY.WAL files hidden in the ISO. Example: Open the ISO and they won't be there.
## Post #6
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2015-01-23T21:39:24+00:00
- Post Title: Sly Cooper and the Thievius Raccoonus .WAL extractor?

> Reply from frogz2007
>
> Marvelous work! Now, there's another problem; The full game has the SLY.WAC and SLY.WAL files hidden in the ISO. Example: Open the ISO and they won't be there.
Looks good, I'm sending you a PM
## Post #7
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-01-23T22:09:26+00:00
- Post Title: Sly Cooper and the Thievius Raccoonus .WAL extractor?

decompression routine ported to bms, just because
also completely untested

```
get LEN asize
log MEMORY_FILE 0 LEN

math v0 = 0x1DBA1 # Sly 1 Demo
#math v0 = 0x7A69 # Sly 2 and Sly 3 demo

for i = 0 < LEN

	math v0 *= 0x01A3
	math v0 += 0x181D
	math v0 %= 0x7262
	
	math a0 = v0
	math a0 <<= 8
	math a0 -= v0
	math a0 /= 0x7262

	getvarchr a2 MEMORY_FILE i
	math a2 ^= a0
	putvarchr MEMORY_FILE i a2
next i

# dump it
get NAME basename
string NAME + ".dec"
get LEN asize
log NAME 0 LEN MEMORY_FILE

```
## Post #8
- Username: theclub654
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Oct 14, 2015 8:57 am
- Post datetime: 2015-11-28T15:58:15+00:00
- Post Title: Sly Cooper and the Thievius Raccoonus .WAL extractor?

Is it possible you can make a decryption for the hd version of all the sly games?
