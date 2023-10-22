## Post #1
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-08-19T17:57:44+00:00
- Post Title: Help with TGA with palette and alpha channel

I'm having difficulty writing a proper header for this variant of TGA file. It's a 32-bit TGA file with 256 colour map (palette) entries.

This is how I'm writing the header right now:

```
	tgaHeader->ColormapType=1;
	tgaHeader->ImageType=1;
	tgaHeader->ColormapSpecification1=0;
	tgaHeader->ColormapSpecification2=256;
	tgaHeader->ColormapSpecification3=32;
	tgaHeader->XOrigin=0;
	tgaHeader->YOrigin=0;
	tgaHeader->ImageWidth=pssHeader->width;
	tgaHeader->ImageHeight=pssHeader->height;
	tgaHeader->PixelDepth=8;
	tgaHeader->ImageDescriptor=0;
	tgaHeader->ImageDescriptor|=DESCRIPT6; //vertical flip
```


Here's an example TGA file. If you use an hex editor, you can see that there's a fourth byte for each colour map entry which is the alpha channel. But I've tried several programs, and they never show an alpha channel.

Edit: After doing some more tests and research, I think I've come to the conclusion that TGA doesn't actually support palette with alpha channel (despite it allowing 4 bytes per colour map entry), and there's actually no formats which supports this. I'd like to be proven wrong though. If anyone knows of an image program and a format which supports saving this, let me know.

Edit 2: After doing some more research I got to know that PNG (perhaps unofficially) supports this but the biggest problem is finding image programs which supports indexed image files with alpha channel. Oddly enough, most browsers supports reading this variant of PNG files, but most image programs (even a big one like photoshop) does not.
[john_1_1.pss.rar](https://xentaxbackup.github.io/file/5690_john_1_1.pss.rar)
