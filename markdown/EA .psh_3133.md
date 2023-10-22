## Post #1
- Username: sinkillerj
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 17, 2008 11:13 pm
- Post datetime: 2008-08-17T18:10:35+00:00
- Post Title: EA .psh

I need help editing .psh images. Ive attached one. It is a image format used by ea games on the playstation 1 and one psh can contain multiple images. I found a program called [PSicture](http://www.zophar.net/fileuploads/1/3280svgnh/PSicture-101.zip) that allows you to view the files but it does not modify them. Quote from a file included with PSicture 
> PSH is a Electronic Arts specific format.
>
> I've found PSH files in The Need For Speed, NBA Live 97 and FIFA 2000.
>
> However, it seems some files are compressed, and they are not 
>
> supported.
The ones i need to modify do not seam to be compressed.
[PSH.zip](https://xentaxbackup.github.io/file/1609_PSH.zip)
## Post #2
- Username: RonHayter
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Aug 01, 2008 5:22 am
- Post datetime: 2008-08-20T04:16:15+00:00
- Post Title: EA .psh

What sort of help are you looking for? If you want to just replace an image in a PSH file, I should be able to do that for you. The PSH format is very straightforward.

Ron
## Post #3
- Username: sinkillerj
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 17, 2008 11:13 pm
- Post datetime: 2008-08-22T22:42:52+00:00
- Post Title: EA .psh

I would like to create a image in a standard format like bmp, convert it to the proper format, and use it to replace a image in the psh. For the project i am working on it would be best to have a program i can use to replace them myself since i will be replacing a large amount of images.
## Post #4
- Username: RonHayter
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Aug 01, 2008 5:22 am
- Post datetime: 2008-08-23T23:42:48+00:00
- Post Title: EA .psh

I'll see what I can do in the next few days.

By the way, if you don't already have it, you'll need to install [Java 6](http://www.java.com/). Is that a problem? (Hint: The correct answer is: "It's no problem at all.")
## Post #5
- Username: Jamesuminator
- Rank: advanced
- Number of posts: 41
- Joined date: Sun Mar 02, 2008 7:13 am
- Post datetime: 2008-08-24T19:23:46+00:00
- Post Title: EA .psh

Java programmers, never trust 'em.

But yeah, this format is really simple. I just came in to say that, lol.
## Post #6
- Username: RonHayter
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Aug 01, 2008 5:22 am
- Post datetime: 2008-08-24T20:23:05+00:00
- Post Title: EA .psh

> Reply from Jamesuminator
>
>   Java programmers, never trust 'em.
A troublemaker, eh?   


OK, here's the first step: a program to extract all images from a PSH file.

Unzip it, then double-click the JAR file to run it. (I'm assuming you've already installed [Java 6](http://www.java.com/).)

Create a folder in your "My Documents" folder, call it something like "PSH Explosions", and choose it as the extracted file folder in ExplodePSH. Choose a PSH file, click the Extract Files button, choose another PSH file, extract again, and repeat as often as you like. ExplodePSH will create a subfolder within "PSH Explosions" for each PSH file. Click the Save Transcript button to write the messages from ExplodePSH into a text file.

The output of ExplodePSH should be a set of BMP images for each PSH file, plus a DIR file. The DIR file contains the directory part of the PSH file as well as some information about each image. The DIR file will be used later in step two -- ImplodePSH -- which will reassemble a PSH file, incorporating any images that have been modified.

Please try ExplodePSH on as many PSH files as possible. Let me know if you see any unusual messages. I only have one PSH file to test with, so I may have made some incorrect assumptions. Please send me (a private message is probably best) a transcript from ExplodePSH and all DIR files you generate so that I can make sure I haven't missed something.

Ron
[ExplodePSH.jar.zip](https://xentaxbackup.github.io/file/1611_ExplodePSH.jar.zip)
## Post #7
- Username: sinkillerj
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 17, 2008 11:13 pm
- Post datetime: 2008-08-27T00:43:00+00:00
- Post Title: EA .psh

Thanks for taking the time to do this. Might be a few days before i can try but i will PM you when i can.
## Post #8
- Username: RonHayter
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Aug 01, 2008 5:22 am
- Post datetime: 2008-09-01T16:26:52+00:00
- Post Title: EA .psh

Thanks to sinkillerj and the information he sent me, I have a new version of ExplodePSH that is greatly improved.

It appears that there are 4 different image formats in the various PSH files he has, as identified by the first byte of the image. The simplest -- type 0x42 -- is the only type used in ALBUM1.PSH, and therefore the only one handled in version 1 of ExplodePSH. Elsewhere, it's used rarely except (no surprise) in ALBUM2.PSH. Type 0x42 uses 16 bits per pixel.

Version 2 of ExplodePSH handles two other types. Type 0x40 is by far the most common, using 4 bits per pixel as indexes into a 16-entry palette of 16-bit colours. Type 0x43 is only used for one image in all of those PSH files. It uses 24 bits per pixel.

The fourth image format is type 0xC0. I haven't yet studied this type. My guess, though, is that it is similar to type 0x40 (i.e., 4 bits per pixel, plus a palette) but, judging by the file size, compressed in some fashion.

By the way, some of the images have a 1-bit alpha channel, i.e., they have some transparent pixels. If the image extracted by ExplodePSH is a BMP file, there are no transparent pixels. If there are any transparent pixels, ExplodePSH instead creates a PNG file, since BMP does not support an alpha channel. I considered extracting all images as PNG files but maybe it's useful to know if there is an alpha channel.

I'll describe what I've learned about the PSH file format in more detail in a separate post.

Ron
[ExplodePSH.jar.zip](https://xentaxbackup.github.io/file/1625_ExplodePSH.jar.zip)
## Post #9
- Username: RonHayter
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Aug 01, 2008 5:22 am
- Post datetime: 2008-09-02T00:00:41+00:00
- Post Title: EA .psh

The PSH file format used in this game (which is [ReBoot](http://psx.ign.com/objects/002/002109.html), by the way) is very simple. All values are little-endian. First, the 16-byte header:

```
uint32 {4} - Length of the PSH file, including this header
uint32 {4} - Number of directory entries
char {4} - "GIMX"
```

Following this are the N directory entries, each 8 bytes long:

```
uint32 {4} - Offset to start of the image
```

The length of each image is implied by the starting offset of the next one or, in the case of the last image, by the end of the PSH file.

Each image begins with a 16-byte header:

```
byte {3} - Unknown
uint16 {2} - Width
uint16 {2} - Height
uint16 {2} - Unknown
uint16 {2} - Unknown
uint16 {2} - Unknown
uint16 {2} - Unknown
```

Immediately after the header are the pixels.

The bottom 2 bits of the image type byte specify the bit depth of the image:
0 - 4-bit indexed colour
2 - 16-bit direct colour
3 - 24-bit direct colour

There aren't any images of type 0x41 in any of the PSH files in this game but presumably they would be 8-bit indexed colour.

If the bottom 2 bits also specify the bit depth of type 0xC0 images, these should be 4-bit indexed colour. As I mentioned in my previous post, type 0xC0 images are smaller than expected, so perhaps the 0x80 bit means they are compressed.

The pixels are arranged in left-to-right, top-to-bottom order. Each row of pixels must occupy an even number of bytes, so there may be a pad byte at the end of a row, depending on the bit depth and image width.

For 4-bit pixels, there are, of course, two pixels per byte. Each 4-bit value is used as an index into a palette of 16-bit colours. The pixel in the low 4 bits of the byte appears to the left of the pixel in the high 4 bits of the byte. As an example, here is the pixel ordering and row padding of an image that is 5 pixels wide:

10 32 X4 XX

The row is 4 bytes long. Half of the third byte is unused, and the fourth byte is needed to make the row an even number of bytes long. Each X is generally zero.

16-bit pixels and palette entries share a common format. The high bit of the little-endian uint16 specifies transparency (T). The next 5 bits are for blue, the next 5 for green, and the low 5 for red.

The transparency bit is a little odd. If the colour is black (R=0, G=0, B=0) and T=0, the pixel is transparent. If the colour is not black, the pixel is transparent if T is not 0. In other words, by default (i.e., T=0), black is transparent and every other colour is not. When T=1, every colour is transparent, except black.

For 24-bit pixels, the 3 bytes are red, green, and blue, respectively. From the single 24-bit example we have, it appears that black is transparent, as with 16-bit colours. If the image width is odd, there is a pad byte at the end of each row.

In the case of 4-bit pixels (and also, presumably, 8-bit pixels), there is a palette following the pixel values. Sometimes the palette immediately follows the pixels but sometimes there are 2, 4, or 6 unknown bytes in between. The palette header is distinctive, so ExplodePSH searches for it.

The palette in type 0x40 images begins with a 16-byte header:

```
uint16 {2} - Palette width (always 16)
uint16 {2} - Palette height (always 1)
uint16 {2} - Number of palette entries (always 16)
uint16 {2} - Unknown (always 0)
uint16 {2} - Unknown (always 0)
uint16 {2} - Unknown (often 240, sometimes 0)
```

Following the header are the 16 uint16 colours as described above.

In many images, there are no bytes after the pixels and, in type 0x40 images, the palette. In roughly half of the images, however, there are extra bytes whose purpose is unknown. Often there are only a few extra bytes but there are some images with hundreds of bytes added.

Ron
## Post #10
- Username: mayfly
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Mar 20, 2009 6:15 am
- Post datetime: 2009-11-05T16:19:35+00:00
- Post Title: EA .psh

just downloaded the exploder. works with the EA .psh files I tested. Did this ever advance into being able to repace the psh files after extracted?
## Post #11
- Username: EriolGaurhoth
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 02, 2019 10:54 pm
- Post datetime: 2019-05-03T12:37:57+00:00
- Post Title: EA .psh

I'm replying to this topic over a decade later, but as a shot in the dark, has anyone done any work on the "ImplodePSH" java program to reassemble a PSH file?  I realize it's been a very very long time, but the ExplodePSH still works like a charm, I just was wondering if the ImplodePSH still exists...or ever existed.
## Post #12
- Username: jlnhlfan
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Dec 10, 2020 4:00 am
- Post datetime: 2021-01-24T21:49:40+00:00
- Post Title: EA .psh

I was wondering the same thing. But because of how helpful it could be to me, it likely never existed.
