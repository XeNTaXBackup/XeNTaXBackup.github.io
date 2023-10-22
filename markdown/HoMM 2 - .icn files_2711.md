## Post #1
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2007-07-15T19:57:17+00:00
- Post Title: HoMM 2 - .icn files

Hi, friends!

First of all, I love your wiki about game file archives. It helped me a lot to write a program to handle heroes .agg files.

Now, I wonder if any of you has any relevant information about the .icn files that the game uses for grahics or how to convert this images to standard .bmp files.

What I know (or I think I know):

                                           ICN FILES:
// Groups of images, different sizes, bitmap 256 colors,
// not included (taken from palette file kb.pal). Game doesn't use
// images bigger than 640x480 pixels.

typedef struct {
  unsigned int  nImages;                    /* Number images */
  unsigned long longDatos;                    /* File size - 6 */
  struct        index[nImages] {           /* Image index */
    signed   int  posX;                       /* Posit. horiz. image */
    signed   int  posY;                       /* Posit. vert. image */
    unsigned int  width;                      /* Image width */
    unsigned int  height;                       /* Image height */
    unsigned long direction;                  /* Direction-6 inside file */
  };
  unsigned char  data[nImages][variable];  /* The Pixels */
} H1GrpBmp;

// Decodification of image pixels:
// n = Read(byte);
//  n:
//   Case n > 128 { Jump (n - 128) pixels, which are empty or transparent };
//   Case n = 128 { End of image };
//   Case n > 0   { Read n pixels beside };
//   Case n = 0   { End of line };

Can anyone help a bit please? Sorry if my english is not very coherent)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-15T20:58:58+00:00
- Post Title: HoMM 2 - .icn files

You write as if you do know a lot of the ICN fomat already, what are you not sure about?
## Post #3
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2007-07-15T21:23:32+00:00
- Post Title: HoMM 2 - .icn files

Thanks for answering!

Well, I do not have advanced knowledge in programming (I just can't stand c++) so I changed to C#. All it's great, but I don't know what functions should I use for reading data in this language, and evenmore I have never written soft to work with images, so I'm just blocked. If someone could make a little diagram of a programa to do something like this in C# or even in C++ I'd be very pleased... cause I've been working so long on this game, (more than a year all weekends, and I didn't know you have already identified .agg files)
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-07-16T10:35:39+00:00
- Post Title: HoMM 2 - .icn files

A compact class for writing bmps can be found here: [http://www.smalleranimals.com/jpegfile.htm](http://www.smalleranimals.com/jpegfile.htm)
The coding style isn't really good imo, but it does its job.
You just have to provide the write function with the correct data.

If you can't stand C++, try [D](http://www.digitalmars.com/d/)!
## Post #5
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-07-16T10:36:19+00:00
- Post Title: HoMM 2 - .icn files

```
	unsigned int nImages;
	unsigned long longDatos;
};
struct ImageHeader {
	signed int posX;
	signed int posY;
	unsigned int width;
	unsigned int height;
	unsigned long direction;
};
Header fh;
ImageHeader ih;
FILE* hFile = fopen(filename, "rb")
fread(&fh, sizeof(Header), 1, hFile)
for(int i=0; i<fh.nImages; i++)
{
	fread(&ih, sizeof(ImageHeader), 1, hFile)
	// etc. fseek..fread data..save as bmp...
}

```

some code..
## Post #6
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2007-07-16T11:40:57+00:00
- Post Title: HoMM 2 - .icn files

Lots of thanks Rheini, I'll try that out this evening. If I get it to work I'll post here so other people can use it too.

Thanks again.
## Post #7
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2007-07-26T00:26:15+00:00
- Post Title: HoMM 2 - .icn files

Well, at the end I wasn't able to do anything, when I checked the structure on the .icn it just dind't match with the info I had.

Here's a sample file with the palette if someone wants to help:

[download.php?id=1288](http://forum.xentax.com/download.php?id=1288)

Thanks anyway!
## Post #8
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-29T13:00:55+00:00
- Post Title: HoMM 2 - .icn files

Okay, I think we will first start with the basics before delving into the actual format. You wanted to know how palettized images work, so let's begin with this:

There are several imaginable ways to store the colour information for an image in a file. First of all, a suitable way to represent a single colour has to be found. On computer systems, one popluar method consists of decomposing a colour into red, green and blue components, which are then often stored as single bytes, allowing the values 0 .. 255 for each component. This leads to 256^3 = 16,777,216 possible colours.

However, storing three bytes of information (namely the RGB components of the colour) for each pixel ultimately leads to quite large image files. Usually, a single image will not contain all of the 16+ million colurs at once, so we might think of more efficient storage methods. (Some games, especially older ones, also need this data reduction for various other reasons mostly found in technical limitations).

Imagine that the pixels of our proposed image are coloured within the full RGB spectrum (as described above), but only 256 (or less) different colours are used in the whole image. In that case, we can match each used colour to a number between 0 and 255 and save this number (as one byte) instead of three bytes for the whole RGB triple. Obviously, we need to store this matching (the "palette") as well, for example as an array of 256 entries, where each entry is a three-byte RGB triple. (That is why palette files for older games are often 256 * 3 = 768 bytes in size.)

To summarize, palettized images do not directly store the colour information together with the pixels, but rather an index into a table, which then contains the actual colour data.

Feel free to ask if you still have questions ...
## Post #9
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-01T00:40:24+00:00
- Post Title: HoMM 2 - .icn files

Just as an addendum: The basic header structure you described in your first post is almost right (given the example you uploaded): Another byte of yet unknown purpose has to be inserted into the image headers between the height and the offset ("direction").

Additonally (to make matters worse), the decompression scheme is definitely more complicated than described above. It is indeed opcode-based and part of the original description is still true. However, to reliably decode the format, reverse-engineering the executable would be in order.

Is there a demo of the game available somewhere?
## Post #10
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-01T16:38:05+00:00
- Post Title: HoMM 2 - .icn files

Nevermind, I found some [interesting code](http://fheroes2.svn.sourceforge.net/viewvc/fheroes2/trunk/fheroes2/sprite.cpp?view=markup) on the web. It doesn't seem to be fully correct, but was a good starting point. Maybe you can try [this tool](http://www.xentax.com/uploads/author/denizoezmen/_ICN2TGA.zip). I'm not sure about the correct alpha channel, so I've guessed a bit:

```
ICN2TGA *.icn kb.pal
```
## Post #11
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2007-08-08T12:49:41+00:00
- Post Title: HoMM 2 - .icn files

Unfortunately the tool closes when I open it without any error message. Maybe it's not compatible with Vista. Anyway, lots of thanks for the code, I'll work on that and I'll see if I can get it to work.

I didn't answer these days because I changed to Vista and I was setting all things up once again. It's not as bad as I expected. The bad thing is that my directx applications which I compiled here require now Directx 10, which is not available for XP, I think, so the compatibility is very limited. I'll have to change directx sdk to 9.0c I think.

But first of all I'll concentrate on this issue with .icn files. The game engine will be useless if I can't convert those. Changing topic, that project which you shown me looks promissing. Do you think that those pieces of code can be useful? I say because some parts I've examined looked very strange to me (even more with comments in russian).

See you friend! 

Edited: Here a demo of the game if you think it'll be useful: [http://heroes.mycomport.com/maphaven/heroes2.html](http://heroes.mycomport.com/maphaven/heroes2.html)
## Post #12
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-08T15:16:27+00:00
- Post Title: HoMM 2 - .icn files

> Reply from Balder
>
> Unfortunately the tool closes when I open it without any error message. Maybe it's not compatible with Vista.
It's a console application, you have to run it from the command prompt (which still exists in Vista ).

> Reply from Balder
>
> I'll have to change directx sdk to 9.0c I think.
You are indeed right about DirectX 10 not being available for systems other than Vista (beside some private projects aiming at forcing downward-compatibility), so you actually might want to consider using a previous DirectX SDK.

> Reply from Balder
>
> Changing topic, that project which you shown me looks promissing. Do you think that those pieces of code can be useful?
I haven't looked at it in detail, but as far as I can tell, this project's aims are comparable to yours. I have briefly run the demo with the project's engine. The main menu basically worked, but I haven't tried out much more than that. You could eventually try and contact the developers ...
## Post #13
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2007-08-11T13:59:29+00:00
- Post Title: HoMM 2 - .icn files

When I run the application from the console it says: "Incorrect number of parameters", when I type ICN2TGA.exe being already in it's directory.

I've been looking (trying to look) at the code this days. It seems to complicated for my C++ understanding, and SDL library just adds extra difficulty because I have null knowledge about it. 

I don't know, I think it would be better to write something from scratch in C# but the problem it's still the same I haven't ever done any soft for image handling. If you have any info, tutorial or something like that for working with pixels, images and all the stuff It would be very handy for me to write something using the structure we have.

Any idea?
## Post #14
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-11T14:52:20+00:00
- Post Title: HoMM 2 - .icn files

> Reply from Balder
>
> When I run the application from the console it says: "Incorrect number of parameters", when I type ICN2TGA.exe being already in it's directory.
That's why I quoted the following line in my post above:

```
ICN2TGA *.icn kb.pal
```

ICN2TGA needs two parameters: The first one is the file name of the image you want to convert, the second one is the palette (usually kb.pal). To convert "image.icn", you would type:

```
ICN2TGA image.icn kb.pal
```


> Reply from Balder
>
> I've been looking (trying to look) at the code this days. It seems to complicated for my C++ understanding, and SDL library just adds extra difficulty because I have null knowledge about it.
I remember from my (albeit very limited) experiments with SDL that it is not too hard to work with, but maybe this is not exactly the best place to start. If you want tutorials about that topic, though, you might want to look around [http://libsdl.org/](http://libsdl.org/).
On the other hand, if you want to understand the ICN format first (which I would recommend you to do), ignore the SDL commands and concentrate on that part of the code which processes the image data. You'll see basic imperative code that should be very familiar for you if you have some C# experience. (Alternatively, you can take a look at the source code of the ICN2TGA program, located in ICN2TGA.dpr and SaveTGA.pas.)

> Reply from Balder
>
> I don't know, I think it would be better to write something from scratch in C# but the problem it's still the same I haven't ever done any soft for image handling. If you have any info, tutorial or something like that for working with pixels, images and all the stuff It would be very handy for me to write something using the structure we have.
Well, I cannot give you hints regarding tutorials as such ...

In general, I'd suggest you try to gain experience in working with file formats and the inner workings of data structures first. Get general information about what digital images are about. Try [http://en.wikipedia.org/wiki/Raster_graphics](http://en.wikipedia.org/wiki/Raster_graphics) as a starting point. Then, for example, you might want to write your own program to convert ICN files to BMP, TGA or whatever format you like. Look up the specifications for these file types (resources like [http://www.wotsit.org/](http://www.wotsit.org/) or good old web search engines are useful).

Please note that programming a game engine is not an easy thing to do. You need working knowledge from various domains in computer science, not only graphics formats. This is not meant to discourage you, but to make clear that the way to a reimplementation of this particular game's engine is long. You should probably start with basic things and work onward form there.
## Post #15
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2007-08-11T16:19:22+00:00
- Post Title: HoMM 2 - .icn files

It worked now, converted archer.icn and extracted all archer images in .tga format. Sorry for my incompetence with the console, I didn't live in the msdos ages and never used console for advanced things.

I'll look on that code then again and again. Furthermore, I'll read my c++ tutorials again, which I abandoned because c# was a better language for self teaching.


> Please note that programming a game engine is not an easy thing to do. You need working knowledge from various domains in computer science, not only graphics formats. This is not meant to discourage you, but to make clear that the way to a reimplementation of this particular game's engine is long. You should probably start with basic things and work onward form there.

I know that my knowledge on programming isn't enough to write a game nor a complex application, but I've been working on this as a kind of motivation to continue learning about programming. I've never thought of finnishing this, but I hope I'll learn with it. The reason is that this game marked my childhood and I don't get bored when I work on it, extracting it's resources is like entering in the heaven for me.

Anyway, I have much time and I enjoy learning so I won't lose my hopes.
As you're a professional programmer, do you recommend me to use other languages than c# or c++? or maybe other graphic framework than directx more suitable for begginners?
Doesn't matter, I'm very grateful for all the help I received from you, best regards!
## Post #16
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-11T20:17:26+00:00
- Post Title: 

> Reply from Balder
>
> I didn't live in the msdos ages and never used console for advanced things.
No worries, that's the case for most people. You might want to keep an eye on it, though. It can be useful at times, especially when you need to repair your system.

> Reply from Balder
>
> I'll look on that code then again and again. Furthermore, I'll read my c++ tutorials again, which I abandoned because c# was a better language for self teaching.
I don't think you need to delve into C++ too much, at least not for the ICN handling code. (I didn't take a closer look at the rest of the project, though.)

> Reply from Balder
>
> I know that my knowledge on programming isn't enough to write a game nor a complex application, but I've been working on this as a kind of motivation to continue learning about programming.
That's a very good approach. Having a specific goal is much more useful than simply reading about syntax and semantics. Just keep going, you'll eventually get there ...

If you feel that C# works for you, stay with it. Once you get the hang of the general concepts, switching between different languages becomes easier anyway.

> Reply from Balder
>
> As you're a professional programmer, do you recommend me to use other languages than c# or c++?
I'm not a professional, but just a hobby programmer myself. But nevertheless I'd advise you to choose a language you're comfortable with. Don't buy statements telling you that language X is in every regard superior to language Y. All of them have their advantages and their disadvantages as well as their specific fields of application they're most useful in.

> Reply from Balder
>
> or maybe other graphic framework than directx more suitable for begginners?
My experience in graphical programming is limited, so I can't help you there. A general hint: Whether you choose to access DirectX or OpenGL directly or whether you choose to use a middle layer like SDL, always be sure to read the documentation and specifications.

Anyway, good luck with your projects -- and you know where to come when you have file format issues.
