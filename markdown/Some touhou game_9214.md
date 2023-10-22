## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-06T04:45:05+00:00
- Post Title: Some touhou game

Got a request for graphic reversal for some touhou game.
It doesn't seem to be compressed, so I went through texture finder.

And got something that I at least recognize from the franchise.







The file seems to be split into three parts.
First, you have the header, which is 40 bytes.
Then, there's some stuff after the header, which is unknown size.
Finally, you have what I guess is the pixel data, where the size is the 2nd integer * 3rd integer in the header.

So for example, this file is 240896 in size, which looks like a nice rounded number

```
   int32 header size
   int32 width
   int32 height
   ...
}

The unknown data takes up 856 bytes, where the pattern in the data then changes.
Including the header, this is the first 896 bytes of the file, followed by the other 240000 bytes for the pixel data.

There are some other files that are just plain RGB24, but the one I posted isn't.

Anyone want to give a shot?

EDIT: lol turns out it's a mahjong game. I just found some tiles
```

[00000000.zip](https://xentaxbackup.github.io/file/5545_00000000.zip)
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-07-06T06:59:54+00:00
- Post Title: Some touhou game

Did you try a 214 color palette? Are all values after 0x380 less than D6?

Edit:
Yeah, looks like a 214 color palette. Kind of odd to use 214 lol.
## Post #3
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-07-06T07:09:09+00:00
- Post Title: Some touhou game

This is what I got...
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-06T07:18:04+00:00
- Post Title: Some touhou game

It's probably just for that particular file. Other files have less colors in the palette.

EDIT: ya, at offset 32 that integer tells you how many colors there are.

Guess it's time to go figure out how to work with palettes in noesis.
## Post #5
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-07-06T07:22:32+00:00
- Post Title: Some touhou game

lol

if noesis can save 32-bit BMP/TGA, just iterate through the pixels converting 8-bit pixel data to 32-bit pixel data using the table. i doubt rich would have anything to save images with arbitrary-length palettes.

another thing you could do is if noesis supports 256-color bitmaps is to just do that and fill whatever palette colors are leftover with zeroes.
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-06T07:49:59+00:00
- Post Title: Some touhou game

Ya I think there was something about creating a palette of some size and then passing in the color map down and out pops an rgba image.
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-06T20:47:27+00:00
- Post Title: Some touhou game

Alright got it working in noesis. Just had to call imageDecodeRawPal and pass in the map and the palette.
Though, some of the colors seem to be off.

Script: [http://db.tt/F5m2QCf7](http://db.tt/F5m2QCf7)

 

Some images seem kind of weird as well.
It's the same character, but a cropped version (probably for message windows and stuff.



They have the palette, but there seems to be more indices in the map than there are pixels in the actual image (numBytes > width * height)

I can't come up with what the issue might be. I tried doing some random offsetting into the data but it didn't do anything.

I can't come up with a way to visually "reconstruct" the image in my head either lol it's like the image was tilted on its side and then chopped into pieces.
[00000081.7z](https://xentaxbackup.github.io/file/5552_00000081.7z)
## Post #8
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-07-07T01:39:04+00:00
- Post Title: Some touhou game

image is 150 x 154... probably a pitch thing. does noesis have a data-alignment parameter?
## Post #9
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-07-07T01:46:32+00:00
- Post Title: Some touhou game

yeah, works fine for me...



Actual data starts at 0x3E8. Pitch is 32-bit aligned. I don't think TGA uses data alignment. I don't know what you're saving to, but you should be either saving to DDS or BMP.

To test, you can use MSPAINT. Create a blank 150 x 154 image in MSPAINT. Save as 256 color bitmap. Load in hex editor. At offset 0x36, delete the next 0x400 bytes (the default color table). Paste in your own 0x3?? + padding (to make 0x400 bytes) color table. Then at 0x436, delete everything from there to the end. Paste in the color data from dat file.

BTW, the other image is like that. Swizzled in some kind of way maybe? Not sure.
