## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-02-21T05:08:45+00:00
- Post Title: How do I read a "skewed" image?

I am using TextureFinder and it has a "skew" option.

I'm assuming that is image shearing, but I don't understand how it works on a byte level.
I've read some general explanations about how you transform a rectangle into a...slanted looking one...but how would I take those pixels and transform it back to a normal rectangle?

The image format I am working is RGB24 with a skew value of 3, and I would like my image converter to shear the image correctly.

How do I read pixels that have been "skewed" by some value?
[skew.jpg](https://xentaxbackup.github.io/file/6209_skew.jpg)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-02-21T15:16:50+00:00
- Post Title: How do I read a "skewed" image?

> Reply from finale00
>
> but I don't understand how it works on a byte level.Hah, who will?;-)
You could draw a 32x32 pixels bmp setting 3 pels at 17,15, 16,16 and 15,17.
Then unskew this bmp with TextureFinder (skew: +3) and save it as unskewed.bmp for example.

Load both bmps into a hex editor to compare them (visually) on byte level. Kinda difficult I think.

> ...but how would I take those pixels and transform it back to a normal rectangle?
>
> The image format I am working is RGB24 with a skew value of 3, and I would like my image converter to shear the image correctly.
>
> How do I read pixels that have been "skewed" by some value?
Read this one? [http://stackoverflow.com/questions/2446 ... transforms](http://stackoverflow.com/questions/2446494/skewing-an-image-using-perspective-transforms)
Most important info imho: "If you don't feel like re-inventing the wheel, check out [some graphics] library."

That's what I did: performed a shearing on your swizzeld image (do you remember? )
[](http://www.pic-upload.de/view-18233021/shear.jpg.html)

This is the main part of the code:

```
                SetWindowHandle(hwndDlg);
                InvalidateRect (hwndDlg, &rect, TRUE) ;
                hdc = BeginPaint (hwndDlg, &ps);
                graphics = new Graphics(hdc);
	        {
		       Matrix matrix;
  		       //matrix.Translate(220.0f, 0.0f);            // first a translation
		       //matrix.Rotate(30.0f, MatrixOrderAppend);   // then a rotation
		       // Shear
		       matrix.Shear(2, 1);            // params: horizontal and vertical shear factors 
		       // Apply transformation
		       graphics->SetTransform(&matrix);
	        }
                graphics->DrawImage(ourImage,5,5);
                delete(graphics);
                EndPaint( hwndDlg, &ps );
                break;
```
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-02-21T15:41:56+00:00
- Post Title: How do I read a "skewed" image?

I probably meant pixel level lol
I've already used the shear function that comes with .NET but it just takes whatever pixels I've read into my bitmap and changes THAT picture.

So I'm guessing the issue I have to deal with is to figure out how to actually read the pixels and map them to my rectangular bitmap in the correct order, and not just how to shear a bitmap.

I'll start experimenting with some pictures and see how texfinder saves the skewed output.
## Post #4
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2013-02-21T16:20:16+00:00
- Post Title: How do I read a "skewed" image?

I would look up on shearing computer graphics on google to get a basic understanding of the transformation process. Maybe this example in matlab is useful for you [http://stackoverflow.com/questions/2818 ... -functions](http://stackoverflow.com/questions/2818266/how-do-i-shear-an-image-in-matlab-without-using-built-in-functions)
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-02-21T16:27:21+00:00
- Post Title: How do I read a "skewed" image?

I looked at the easiest explanation I could find from those answers and this is what it looks like to me

```
  shift row i by n * i bytes (loop as needed)

```


So if I want to skew by 1 pixel, then n = 1 and the first row would be shifted by 0 bytes, the second row shifted by 1 byte, the third row shifted by 2 bytes, etc.

Which kind of makes sense, cause in the image I can see the stuff that should be on the right, spilling over to the left.

But that's one of the easy one. The other ones have complicated calculations involved hmm I wonder guess I'll start with the simple row-shifting.
## Post #6
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2013-02-21T16:57:39+00:00
- Post Title: How do I read a "skewed" image?

Yes it's basically a shifting of pixels by a given amount. This link makes the process very clear: [http://cs.fit.edu/~wds/classes/cse5255/ ... shear.html](http://cs.fit.edu/~wds/classes/cse5255/thesis/shear/shear.html) What you mean by 'complicated' calculations could be the angle representation of the shearing matrix explained here: [http://www.cs.colorado.edu/~mcbryan/5229.03/mail/55.htm](http://www.cs.colorado.edu/~mcbryan/5229.03/mail/55.htm)
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-02-21T20:13:29+00:00
- Post Title: How do I read a "skewed" image?

Some images are sheared, while other images aren't.
The image header contains 6 shorts, which sort of look like coordinates (x1, y1) (x2, y2) (x3, y3)

Currently I'm just randomly guessing at when they might be sheared, but maybe I have to do some math involving these three points.

A parallelogram can be represented using 3 points on a plane, and if shearing is mapping pixels from a rectangle to some arbitrary parallelogram, then these would need to be used somehow.

Of course my interpretation of this data may be completely off, but I can't come up with anything sensible based on my existing knowledge.

Here's a sample
[pic530.7z](https://xentaxbackup.github.io/file/6212_pic530.7z)
## Post #8
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2013-02-21T23:02:50+00:00
- Post Title: How do I read a "skewed" image?

If I saw this right only the colour channel (24bpp) appears sheared, the alpha channel (8bpp) looks totally fine. It doesn't make much sense this way. Can you think of any reason an image looks skewed/sheared when you parse it wrong?
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-02-21T23:39:18+00:00
- Post Title: How do I read a "skewed" image?

> Reply from finale00
>
> Of course my interpretation of this data may be completely off, but I can't come up with anything sensible based on my existing knowledge.

Here's a sampleIs an original or your interpretation of data?
I'm seeing this: [](http://www.pic-upload.de/view-18240456/skew18.jpg.html)

edit: with a width of 518 the skew is 0 (pixel format 888)

The header I used:

```

00000 42 4D 36 34 10 00 00 00  00 00 36 00 00 00 28 00
00010 00 00 FE 00 00 00 02 01  00 00 01 00 20 00 00 00
00020 00 00 00 34 10 00 00 00  00 00 00 00 00 00 00 00
00030 00 00 00 00 00 00
```
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-02-22T00:20:12+00:00
- Post Title: How do I read a "skewed" image?

The sample is the original.
I am unable to find a way to accurately determine the skew value.

> Reply from Polefish
>
> If I saw this right only the colour channel (24bpp) appears sheared, the alpha channel (8bpp) looks totally fine. It doesn't make much sense this way. Can you think of any reason an image looks skewed/sheared when you parse it wrong?

Nope...

Well, the background info is that these are sprites used in a game engine and so some frames are stored normally, while some frames are sheared. Performance reasons maybe? Wouldn't know why the alpha and image would not be stored the same way though.

I've packed a bunch of files up if you want to compare.
The format is pretty much always the same (there is one format that isn't RGB24 though and I've sort of just ignored it)
[game.7z](https://xentaxbackup.github.io/file/6213_game.7z)
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-02-22T08:06:41+00:00
- Post Title: How do I read a "skewed" image?

> Reply from finale00
>
> The sample is the original.
I am unable to find a way to accurately determine the skew value.Displaying the image as RGB 888 there is no skew: [](http://www.pic-upload.de/view-18242225/888_noSkew.jpg.html)
edit: same with pic387 (ok, that doesn't help if you need the alpha channel).

Displaying them as RGB 8888 there's always the same skew, isn't it? (Checked 3 pics only.)
So you could get unskewed images by using an "8888 to 888" converter (Fujitsu Bitmap Converter) without knowing the skew. (Ok, alpha lost then).
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-02-22T16:28:02+00:00
- Post Title: How do I read a "skewed" image?

Some images are normal, others are skewed.
Try pic387.

The black/white image you see at the bottom is the alpha mask.
There are 3 formats I have seen so far

-RGB24
-RGB24 + 8-bit mask
-something else

You would start by reading in the image data, and if the format contains an alpha mask, you read that in as well, and then merge that with the image to get your final, transparent image.

The format I have spec'd out so far is

```
int32 ?
int32 ?
int32 size # rgb24 and alpha
int16 width
int16 height
byte ?
byte format # might be just a single int32
byte ?
byte ?

# presumably, some coordinates
int16 ?
int16 ?
int16 ?
int16 ?
int16 ?
int16 ?

if format == 4
  # don't know

byte[width*height*3] pixData

if format == 0x10
   byte[width*height] maskData

```
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-02-22T17:04:57+00:00
- Post Title: How do I read a "skewed" image?

eh, that's weird that one's not skewed lol hold on let me find a skewed one.
As polefish pointed out, a lot of images have only the alphas skewed, but I remember seeing a couple where the whole thing was skewed.

EDIT: found some skewed ones! lol
59 and 63 are skewed. The others are normal.

But the skewed alphas are a little annoying as well, since...then I can't properly apply it over the image.
The integer at offset 4 has a few different numbers that I have seen: 0, 1, 2, 4

I am not sure if this indicates the skew type. For example, 0 = no skew, 1 = alpha mask skewed, 2 = image skewed, 4 = both skewed? don't know.
[skewed.zip](https://xentaxbackup.github.io/file/6214_skewed.zip)
## Post #14
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2013-02-22T18:21:13+00:00
- Post Title: How do I read a "skewed" image?

What game is this actually from? And could you provide the exe/whatever? Format 4 seems to be RLE encoding of some kind, pic422 is 2*5 px in size, image data is 0xA for count, 3 bytes for color then 0 as end tag.
## Post #15
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-02-22T19:04:13+00:00
- Post Title: How do I read a "skewed" image?

Here's the exe: [http://www.mediafire.com/?gshsms49h4y4hph](http://www.mediafire.com/?gshsms49h4y4hph)

Currently I am not particularly worried about the type 4's since skewing seems to be a more interesting problem when it comes to images lol
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-02-22T19:07:24+00:00
- Post Title: Re: How do I read a "skewed" image?

> Reply from finale00
>
> EDIT: found some skewed ones! lol
59 and 63 are skewed.Yep, skew=3 (Format 888 in TextureFinder)

I added a BMP header where color depth at 0x1C is set to 24 (18h).
[](http://www.pic-upload.de/view-18248915/skew_3_shear_0.7.png.html)
A more exakt value would be shear(0.67,0).
## Post #17
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2013-02-22T19:22:10+00:00
- Post Title: Re: How do I read a "skewed" image?

Getting closer, just gotta figure out if RLE images contain alpha data.
[http://sktest.aruarose.com/TgaImages.7z](http://sktest.aruarose.com/TgaImages.7z)


Converter (exe+source):
[http://sktest.aruarose.com/imageconvert.7z](http://sktest.aruarose.com/imageconvert.7z)

You got the skewing in that viewer of yours, because the RGB data width is aligned to 2 and alpha data is aligned to 4.
## Post #18
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-02-22T20:47:45+00:00
- Post Title: Re: How do I read a "skewed" image?

What do you mean by data width is aligned to n?

I'm interpreting that as byte alignment, but not sure how it affects the image.
At first I thought it was shifting pixels over, but if it's byte-alignment that probably isn't the case.

So say I have a 3x3 image at 24bpp.
Each pixel is 3 bytes, and so the first row is stored 9 bytes

r1 g1 b1 r2 g2 b2 r3 g3 b3

Since it's aligned to 2 bytes, does it actually do something like

r1 g1 b1 r2 g2 b2 0 0 0
r3 g3 b3

or maybe

r1 g1 b1 r2 g2 b2 0 0 0
0 0 0 r3 g3 b3

(btw I don't have VS2011 so I can't try the exe. I have 2010 though)
## Post #19
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2013-02-22T20:56:59+00:00
- Post Title: Re: How do I read a "skewed" image?

Say your image is 11 pixels wide, the RGB data for each line actually contains 12 pixels then.

The alpha data has an align of 4, so you need to (width+3)/4*4 for the actual amount of data per line.

Best look at how I do it in FormatDecode_SplitRGB_A in the source.

Get [http://www.microsoft.com/en-us/download ... x?id=30679](http://www.microsoft.com/en-us/download/details.aspx?id=30679) and it should run.
## Post #20
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-02-22T21:25:02+00:00
- Post Title: Re: How do I read a "skewed" image?

Thanks, I understand how it works now. I also see why it looks like pixels from the "end" of the first row are spilling over the second row. If I simply loop over the image height and width, it doesn't really reflect how the data is stored in a single array of bytes..
## Post #21
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2013-02-23T07:53:34+00:00
- Post Title: Re: How do I read a "skewed" image?

> Reply from finale00
>
> Thanks, I understand how it works now. I also see why it looks like pixels from the "end" of the first row are spilling over the second row. If I simply loop over the image height and width, it doesn't really reflect how the data is stored in a single array of bytes..
Looks like I'm the only one who don't understood   

11 pixels wide are 12 pixels now.Where does the other pixel come from? When you write (width+3)/4*4 for an align of 4 what do the 3 and 4*4 means?
## Post #22
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2013-02-23T13:23:07+00:00
- Post Title: Re: How do I read a "skewed" image?

When the image is an odd number of pixels wide (1, 3, 5, etc.), the image data is padded to an even number of pixels per row (so you get 2, 4, 6, etc. pixels of data per row).

And say you have width 2, (2+3)/4*4 -> 5/4*4 -> 1*4 = 4. For width 4 you get (4+3)/4*4 = 4. For 5 you get (5+3)/4*4 = 2. Simple math to align numbers.
## Post #23
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-02-23T16:14:42+00:00
- Post Title: Re: How do I read a "skewed" image?

This is how I understand it.

There is potentially one extra pixel per row (usually black I believe), and if I don't read the data using the correct stride, my pointer will be placed before the actual row begins and start reading pixels from the previous row.

My initial assumption was that a 3x3 image would be stored in such a way that producing a bitmap would lead to

1 2 3 4
5 6 7 8
9 P P P

(for padding P)

But that doesn't make sense since it's no different from a regular RGB except with extra padding at the end, which isn't the case.

So then I thought of it like

1 2 3 P
4 5 6 P
7 8 9 P

And it was clearer.
If I took the naive approach of looping it over as a contiguous array of pixels with stride = width * bpp

```
  for y = 0 to width

```


Then the data I read would be

```
P 4 5
6 P 7
8 9 P

```


And so this is where the skewing comes in: you'll see a nice diagonal black line worth of padding, and the rows seem to be shifted over and spill over to the next row.
