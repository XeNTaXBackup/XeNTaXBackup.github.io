## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-28T00:48:17+00:00
- Post Title: What's wrong with this bitmap export code

I'm writing a simple bitmap export in python to get an idea of how to write such an exporter.
It is the uncompressed 24-bit bmp.

I have the header down, and here's how I'm doing the pixel array

```
for x in range(pic.width):
   for y in range(pic.height - 1, 0, -1):
      pixel = pic.get_pixel(x, y)
      pix += pixel.red()
      pix += pixel.green()
      pix += pixel.blue()
f.write(struct.pack("%dB" %pic.width*pic.height*3, pix))

```


But the picture's all messed up lol



It's like the pixels are not drawn in the right spots (everything shifted over by a bunch of pixels)

Following the specs on wiki, it should be 4-byte aligned.

My image is 544x416. Shouldn't have an issue with byte-alignment right?
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-28T00:59:35+00:00
- Post Title: What's wrong with this bitmap export code

Try it with y in the outer loop.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-28T01:06:53+00:00
- Post Title: What's wrong with this bitmap export code

Oh hey it worked.
Except now it's flipped o.O

EDIT: oh, now that I look at the array more carefully, (0,0) is at the bottom-left and not the upper-left -_-
Now I loop down to 0 for the rows and it's right-side up lol
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-28T01:19:33+00:00
- Post Title: What's wrong with this bitmap export code

Correct. Bitmaps are stored upside down.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-28T03:39:27+00:00
- Post Title: What's wrong with this bitmap export code

lol is there some reason to store it that way? Optimization?
Especially the 4-byte alignment padding stuff...
## Post #6
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-28T05:05:41+00:00
- Post Title: What's wrong with this bitmap export code

Yeah, that kind of alignment nowadays probably doesn't help much, but back in the old days, say windows 3.1 days, it made a hell of a difference. I don't remember if bmp predates windows 3.1, but I remember looking at porn (look, back in 1993 all there was were porn sites lol) on dos 3. The picture would load pixel by pixel on the screen. You could literally count the pixels as they loaded lol. The hard drive was only 25 mb too and images were in 16-bit color. Ever see tits in 16-bits? Hahaha.
## Post #7
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2012-04-28T16:48:43+00:00
- Post Title: What's wrong with this bitmap export code

> Reply from howfie
>
> (look, back in 1993 all there was were porn sites lol)

You're dating yourself   

> Reply from howfie
>
> Ever see tits in 16-bits? Hahaha.

How about ascii tits on a BBS with a Commodore 64?
## Post #8
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-28T21:22:12+00:00
- Post Title: What's wrong with this bitmap export code

Lol,bigger question is now, did you masturbate to ASCII tits ?
