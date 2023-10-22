## Post #1
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2015-05-04T21:25:49+00:00
- Post Title: The Mission 1937: SPR1 files

Hi there,
could any of you guys please help me extracting the sprites from the game The Mission 1937 (in Chinese: "1937特种兵")?
Here are some samples: mediafire.com/?qepk5c0r71335s6 (~3MB)

Somebody already told me that the sprites might be 16bit RGB565 run-length encoded bitmaps. But I don't know if that's true.

Any help is appreciated!
Many thanks in advance!
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-05T12:03:13+00:00
- Post Title: The Mission 1937: SPR1 files

Afaik there's RLE-8 for 8-bit bitmaps, for 16 bit uncompressed bitfields are used.

Anyway you could add a header (size: 0x8A bytes) such like this:

```

00000  42 4D 0A 39 01 00 00 00  00 00 8A 00 00 00 7C 00   BM.9......Š...|.
00010  00 00 C8 00 00 00 C8 00  00 00 01 00 08 00 01 00   ..È...È.........
00020  00 00 80 38 01 00 13 0B  00 00 13 0B 00 00 00 00   ..€8............
00030  00 00 00 00 00 00 00 F8  00 00 E0 07 00 00 1F 00   .......ø..à.....
00040  00 00 00 00 00 00 42 47  52 73 00 00 00 00 00 00   ......BGRs......
00050  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00   ................
00060  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00   ................
00070  00 00 00 00 00 00 00 00  00 00 02 00 00 00 00 00   ................
00080  00 00 00 00 00 00 00 00  00 00<02 00 E7 39 20 5B   ............ç9 [
00090  20 1D 0A 41 08 A1 08 41  08 89 A3 A3 49 E3 18 C0    ..A.¡.A.‰££Iã.À
```


and load a faked SPR file into IrfanView for example.
Used 8 bit per pixel and RLE-8 (hopefully) - image size NOT adapted
and dimensions must be different to maybe give better results (or it's not RLE)

(header bytes are different in the below pic so don't be confused.)



RGB565_RLE_header.JPG (159.57 KiB) Viewed 45 times
## Post #3
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2015-05-06T16:42:24+00:00
- Post Title: The Mission 1937: SPR1 files

Thank you, shakotay2.

I used all possible bit count and compression combinations in the BMP header and came to the conclusion that the sprites must be encoded in a custom file format.

Then I took an in-game screenshot of a single tile and saved it as a 16 bit R5G6B5 bitmap with flipped row order.
Now it's possible to compare it with the custom format of the game resources.
mediafire.com/?8sy08xb9cpabjgv

The first few bytes are identical but then the compression starts.
Any suggestions about how to decompress the files?



comparison.png (108.67 KiB) Viewed 36 times
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-06T18:28:38+00:00
- Post Title: The Mission 1937: SPR1 files

> Reply from herbert3000
>
> Any suggestions about how to decompress the files?a (brute force) comtype scan would come into my mind:
[viewtopic.php?f=10&t=12632&p=104305&hil ... an#p104305](http://forum.xentax.com/viewtopic.php?f=10&t=12632&p=104305&hilit=comtype_scan#p104305)

But you should try it out with a known RLE compressed BMP for example to see whether it makes sense.

If you are a coder you might look here:
[http://www.stoimen.com/blog/2012/01/16/ ... h-bitmaps/](http://www.stoimen.com/blog/2012/01/16/computer-algorithms-data-compression-with-bitmaps/)

They present nice code snippets.


btw: for the identical 12 bytes. They are the same for any graphics resource file of the game, aren't they?
(Otherwise it would be a nice finding you've made.  )
