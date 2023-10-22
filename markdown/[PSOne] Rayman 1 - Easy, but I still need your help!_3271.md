## Post #1
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2008-12-24T09:37:19+00:00
- Post Title: [PSOne] Rayman 1 - Easy, but I still need your help!

Hello there!

The game I'm trying to rip the images from is Rayman 1 for PSOne.
Why is this easy, you might ask? Well, I just thought it was, since the game is quite old (1995! ). I have also scanned some of the files in the attachment for images, and I found some in every file, but they're still... wrong. The following picture explains what I mean.

[](http://imageshack.us)

I've put together a 222KB archive ( it's actually more than 600KB when you extract it ), containing 2 files ( different filetypes ) with backgrounds, and it's right here.


 Rayman 1 PSX images.zip
This is a 222KB archive ( it's actually more than 600KB when you extract it ), containing 2 files ( different filetypes ) with backgrounds from Rayman 1 for PSOne. (221.16 KiB) Downloaded 94 times



And [here's another file](http://www.mediafire.com/?sharekey=e40737c304450204d2db6fb9a8902bda) ( uploaded to mediafire ), this one is 206KB, and contains 2 files with sprites.

So can anybody help? Please?

Thanks,
Droolie.
## Post #2
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2008-12-30T17:47:09+00:00
- Post Title: [PSOne] Rayman 1 - Easy, but I still need your help!

I took a look at the files and they're indeed easy to a certain degree.
First, *.R16:

```
  word        identifier?
  word        totalWidth
  word        totalHeight
  word        ?
  word        first Pixel
  etc
}
```


The unusual thing is that the image itself is cut in "stripes". 
The first stripe, for example, is a part of the image and its size is 64*totalHeight pixels. There are 6 stripes in this image so the total width is 6*64=384 pixels(which equals totalWidth). This 64 bits stripe width is not referenced in the file anywhere and maybe the 4th word has something to do with it.
One pixel word uses the format 1555, that's 1 Alpha bit and 5 bits for blue, green and red respectively.
Since I never worked with something like this I decided to make a little tool in Java (although it assumes that said stripe size is always 64 pixels)


 RaymanViewer.rar
(24.12 KiB) Downloaded 69 times



The other file, *.XXX, is a bit more complicated. Each image uses a custom width, that's not a power of two and I can't find that value anywhere in the image header. E.g. in Vac.XXX, the first image's width is 206, the second 199 and the third 182. If you're using Texturefinder, set it to "1555=15+1" and check these widths.

Oh and, your mediafire link is broken.
## Post #3
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2009-01-01T09:23:13+00:00
- Post Title: [PSOne] Rayman 1 - Easy, but I still need your help!

Woah, thanks, your tool works perfectly! ^^
... Except for the other *.R16 files. I uploaded the other *.R16 files too, [here they are](http://www.box.net/shared/lf4xd7iia3). 
And thanks a lot for looking at it, too, since there isn't a lot of people trying to help, but that's normal, of course. 

By the way, I fixed the mediafire link.
## Post #4
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2009-01-01T13:36:52+00:00
- Post Title: [PSOne] Rayman 1 - Easy, but I still need your help!

Haha, wow. Only NWORLD is structured like that. The other R16 files are images without header(!) and with custom width. Unless there's some kind of file which tells the dimensions of these files, I'm afraid I can't help.
The only thing left is to view them with the texture finder and look for the width, then take a picture <_<
## Post #5
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2009-01-04T19:51:06+00:00
- Post Title: [PSOne] Rayman 1 - Easy, but I still need your help!

Thanks for the help, I managed to get all the images ( with Texture Finder ).
Now, I just need the sprites ( mediafire link in first post ). I can't view them correctly in Texture Finder, because the images use palettes, and you can't select palettes in Texture Finder ( I think ).
