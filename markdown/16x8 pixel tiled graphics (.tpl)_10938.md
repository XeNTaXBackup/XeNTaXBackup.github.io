## Post #1
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2013-11-08T20:19:22+00:00
- Post Title: 16x8 pixel tiled graphics (.tpl)

I'm moving my questions into the graphics section now as it appears my initial thought about these files was completely off and they are indeed not compressed, nor encrypted.

original thread [here](http://forum.xentax.com/viewtopic.php?f=21&t=9738)

the .tpl files are 16x8 pixel tiled graphics with a 256 color RGBA palette.

here's pretty much what i do know.






0x00: number of files
0x04: table start address
0x08: first file entry address
0x0C: palette entry address
0x10: second file entry address

0x18: vertical resolution (first file) [2byte value]
0x1A: horizontal resolution (first file) [2byte value]
0x1C: horizontal resolution (first file) [2byte value]

0x20: start address (first file)

0x2C: vertical resolution (second file) [2byte value]
0x2E: horizontal resolution (second file) [2byte value]
0x30: horizontal resolution (second file) [2byte value]

0x34: start address (second file)

0x40: palette color count [2byte value]
0x44: palette address


my goal is to get these files into a format i can actually edit, and then get the edited graphic back into the game.

could use any help possible as im at my very limits with this. My programming knowledge is a total ZERO, and this is the first time i've worked with tiled graphics.

grab the example file; egbg00 from [HERE](http://mce.do.am/dev/psp/egbg00.rar)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-09T10:36:20+00:00
- Post Title: 16x8 pixel tiled graphics (.tpl)

> Reply from mugi
>
> here's pretty much what i do know.How did you get that pic? Which app, which params?

(Maybe in your formats description you should mention palette color count being a WORD value.)

I created a BM file header (360x480), appended the 1024 bytes palette and the first files data but the resulting bitmap looked scrambled again.
## Post #3
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2013-11-09T12:08:53+00:00
- Post Title: 16x8 pixel tiled graphics (.tpl)

added indicators for value sizes in first post 

as for the image, i used tilemolester.

1-dimensional mode
8bpp linear 
32bpp RGB palette (888)
offset 0x50
60x45 tiles (480x360 pixels resolution)

it looks distorted because tilemolester only allows using 8x8 tiles and the tiles in this format are 16x8 pixels.

edit: lol it appears i mixed up vertical and horizontal resolutions between eachother. Fixed this in first post too

my apologies, english isnt my first language
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-09T13:49:58+00:00
- Post Title: 16x8 pixel tiled graphics (.tpl)

your posts are fairly readable (though I'm not a native speaker, too  )

But still I won't get it. Set codec to 8bpp linear, mode 1-D, canvas 60x45.
Always have a colored pic without the "fence" structure of yours. 

The molester seems to reset palette format to 24 RGB (888) when loading the egbg00 file.

Where to set the offset? (I just tried a copy of egbg00 with the first 0x50 bytes cut off.)

Molester version is 0.16?
## Post #5
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2013-11-09T14:12:22+00:00
- Post Title: 16x8 pixel tiled graphics (.tpl)

i dont know, maybe my copy of tilemolester is just bad  (version.... 0.16 lol)

here's how it looks on my end.

[/click for image](http://mce.do.am/dev/psp/egbg00_tmsettings.png)

the settings are just as you put them, so it should look the same.

can you post an image of how it looks on your end ?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-09T15:54:02+00:00
- Post Title: 16x8 pixel tiled graphics (.tpl)

this is what I get: [](http://www.pic-upload.de/view-21280767/allesSoSchoenBuntHier.jpg.html)

I'm pretty sure my copy of tm.jar is outdated (1/11/2005).

How do you get the dialogue window? I used every menu point: in vain.
## Post #7
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2013-11-09T16:02:10+00:00
- Post Title: 16x8 pixel tiled graphics (.tpl)

yours looks like a palette issue really, i get the same result without loading a palette.
and i see you dont have it loaded (correctly atleast) on your screenshot either. 

use: [palette] -> [import from...] -> [this file]
to bring out the dialogue window for the palette. (you can see the settings on my picture, the address of the palette is entered as DEC)

i noticed that using the selections in the palette menu directly dont work 99% of the time.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-09T17:55:24+00:00
- Post Title: 16x8 pixel tiled graphics (.tpl)

aah, yep. Thx!  

(The dialogue title "Import internal palette" is missing from your screenshot, is it?  )

Interesting that the palette address is without the offset of 0x50.

Sadly when saving this the settings are not applied to the data. The saved file simply being a copy of egbg00.

(then I realized that you can use Edit Copy To...)

btw: how the hell did you figure out the settings? There are hundreds of possibilities...
## Post #9
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2013-11-09T18:09:30+00:00
- Post Title: 16x8 pixel tiled graphics (.tpl)

i looked at the data and concluded that the values can't be anything else, and since then i got the resolution of the image from the data, and it started to shape up like an image a little.

a friend of mine looked at it and realized it's 16x8pixel tiles, and that's why it doesnt display correctly.
i dont understand tiled graphics at all so i wouldn't have ever figured that out by myself.

the rest was just raw data analyzing though. when you stare at it with hex editor enough, it'll start making sense.

im sort of hoping someone at the forum who knows their thing with stuff like this would whip up some kind of a converter for this format
(i noticed that a 256 color .tga uses an RGBA palette identical to this file)

i've been doing a ton of work on this, and the text regarding this game really. Since this morning i succesfully located, decompressed and reverse engineered the event scripts of the game too, and im very soon at the point where only thing preventing me from fully translating this game is the graphics that i yet, cant rebuild (or even extract correctly)

edit: 

i found this: [http://wiki.tockdom.com/wiki/TPL_%28File_Format%29](http://wiki.tockdom.com/wiki/TPL_%28File_Format%29)

the tpl format used on wii seem largely similar, however,  i noticed that atleast the image mode flags differ.
and that the tpl files i have at hand are completely void of file signature.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-11T12:02:05+00:00
- Post Title: 16x8 pixel tiled graphics (.tpl)

> Reply from mugi
>
> [...]and that the tpl files i have at hand are completely void of file signature.The format ID (05?) doesn't fit either.

How the data is organized in your sample?
We have 8 bits per pixel = one byte per pixel (256 colors mode).
Is it B0, B1, B2,..,B15 means 16 bytes for the first line of a 16x8 tile?
So it's 
AAAAAAAAAAAAAAAA (16 bytes per tile row)
BBBBBBBBBBBBBBBB
..
PPPPPPPPPPPPPPPPPPPP (8th row)
And it's read as B0,B1,B2,..,B7, B0,B1,B2,...,B7 by the Molester? (8x8 tiles)
AAAAAAAA
AAAAAAAA
BBBBBBBB
BBBBBBBB
...
But this doesn't refer to the pic we get.
(As a test I moved every odd 8 pixel colum 8 pixels down thus getting a more smooth image but the vertical structure getting worse.)[](http://www.pic-upload.de/view-21302006/egbg00_hmm.png.html)

As the Molester's java code is a little bit complex I would prefer reorganizing the sample's structure a little bit.
AAAAAAAABBBBBBBB etc.

But before I'm bothering myself with this the underlying problem must be clear.
## Post #11
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2013-11-11T15:53:29+00:00
- Post Title: 16x8 pixel tiled graphics (.tpl)

this here is the part where i run out of skills really...


i have no idea how the pixel tiles are structured and whatnot, 
graphics editing im decent at, but graphics formats, i really have no clue about, hence i believe i can no longer be of any further assistance myself.
(which is why i asked for help to begin with.)

in any case, here's a tiny bit of code that allows taking the raw data out of the example file, and aligning it so that it works.
a freind of mine, Paulguy wrote this for me as an attempt to get closer to how these files are built, but i never actually tested it as i dont have a compiler handy.

```
#include <stdlib.h>

#define TILE_WIDTH (16)
#define TILE_HEIGHT (8)

int main(int argc, char **argv) {
	int offset, width, height, paloffset;
	long filesize;
	FILE *infile;
	char buffer[TILE_WIDTH];
	char palbuffer[1024];
	int i, j, k;

	if(argc < 6) {
		fprintf(stderr, "USAGE: %s <filename> <offset> <width> <height> <paloffset>\n"\
		                "\tOutput goes to standard output.\n", argv[0]);
		exit(EXIT_FAILURE);
	}

	offset = atoi(argv[2]);
	width = atoi(argv[3]);
	height = atoi(argv[4]);
	paloffset = atoi(argv[5]);

	if(offset < 0) {
		fprintf(stderr, "Offset must be positive.\n");
		exit(EXIT_FAILURE);
	}
	if(width < TILE_WIDTH || width % TILE_WIDTH != 0) {
		fprintf(stderr, "Width must be greater than 0 and a multiple of %i.", TILE_WIDTH);
		exit(EXIT_FAILURE);
	}
	if(height < TILE_HEIGHT || height % TILE_HEIGHT != 0) {
		fprintf(stderr, "Height must be greater than 0 and a multiple of %i.", TILE_HEIGHT);
		exit(EXIT_FAILURE);
	}

	infile = fopen(argv[1], "r");
	if(infile == NULL) {
		fprintf(stderr, "Failed to open %s.", argv[1]);
		exit(EXIT_FAILURE);
	}

	fseek(infile, 0, SEEK_END);
	filesize = ftell(infile);
	fseek(infile, 0, SEEK_SET);

	if(width * height + offset > filesize) {
		fprintf(stderr, "Read with set width(%i), height(%i) and offset(%i) would go past the end of the file.\n", width, height, offset);
		fclose(infile);
		exit(EXIT_FAILURE);
	}
	if(paloffset < 0 || paloffset + 1024 > filesize) {
		fprintf(stderr, "Palette offset must be a positive value and within 1024 bytes from the end of the file.\n");
		fclose(infile);
		exit(EXIT_FAILURE);
	}

	for(i = 0; i < height; i += TILE_HEIGHT) {
		for(j = 0; j < TILE_HEIGHT; j++) {
			for(k = 0; k < width; k += TILE_WIDTH) {
				fseek(infile, offset + (i * width) + (j * TILE_WIDTH) + (k * TILE_HEIGHT), SEEK_SET);
				fread(buffer, TILE_WIDTH, 1, infile);
				fwrite(buffer, TILE_WIDTH, 1, stdout);
			}
		}
	}

	fseek(infile, paloffset, SEEK_SET);
	fread(palbuffer, 1024, 1, infile);
	fwrite(palbuffer, 1024, 1, stdout);
	fprintf(stderr, "Palette written to %i.\n", width * height);

	fclose(infile);
	exit(EXIT_SUCCESS);
}

```


this bit of code realigns the data so that it can be displayed correctly with conventional means.

another piece of code below, encodes back to tiled format. Again, not tested by me as i still dont have a compiler set up.

i dont see the guy much who writes these so i never had the chance to ask how exactly they do their job, but as far as i understood, they take the raw pixel data and just realign it.

here's what he wrote:

- I wrote the program that can encode back in to the tiled format.
- but it still doesn't work with any image format.
- it'll work on the output of the original decoder.
- if you know the palette and data offsets of a TGA it should just work as-is though.

```
#include <stdlib.h>

#define TILE_WIDTH (16)
#define TILE_HEIGHT (8)

int main(int argc, char **argv) {
	int offset, width, height, paloffset;
	long filesize;
	FILE *infile;
	char buffer[TILE_WIDTH];
	char palbuffer[1024];
	int i, j, k;

	if(argc < 6) {
		fprintf(stderr, "USAGE: %s <filename> <offset> <width> <height> <paloffset>\n"\
		                "\tOutput goes to standard output.\n", argv[0]);
		exit(EXIT_FAILURE);
	}

	offset = atoi(argv[2]);
	width = atoi(argv[3]);
	height = atoi(argv[4]);
	paloffset = atoi(argv[5]);

	if(offset < 0) {
		fprintf(stderr, "Offset must be positive.\n");
		exit(EXIT_FAILURE);
	}
	if(width < TILE_WIDTH || width % TILE_WIDTH != 0) {
		fprintf(stderr, "Width must be greater than 0 and a multiple of %i.", TILE_WIDTH);
		exit(EXIT_FAILURE);
	}
	if(height < TILE_HEIGHT || height % TILE_HEIGHT != 0) {
		fprintf(stderr, "Height must be greater than 0 and a multiple of %i.", TILE_HEIGHT);
		exit(EXIT_FAILURE);
	}

	infile = fopen(argv[1], "r");
	if(infile == NULL) {
		fprintf(stderr, "Failed to open %s.", argv[1]);
		exit(EXIT_FAILURE);
	}

	fseek(infile, 0, SEEK_END);
	filesize = ftell(infile);
	fseek(infile, 0, SEEK_SET);

	if(width * height + offset > filesize) {
		fprintf(stderr, "Read with set width(%i), height(%i) and offset(%i) would go past the end of the file.\n", width, height, offset);
		fclose(infile);
		exit(EXIT_FAILURE);
	}
	if(paloffset < 0 || paloffset + 1024 > filesize) {
		fprintf(stderr, "Palette offset must be a positive value and within 1024 bytes from the end of the file.\n");
		fclose(infile);
		exit(EXIT_FAILURE);
	}

	for(i = 0; i < height; i += TILE_HEIGHT) {
		for(j = 0; j < width; j += TILE_WIDTH) {
			for(k = 0; k < TILE_HEIGHT; k++) {
				fseek(infile, offset + (i * width) + j + (k * width), SEEK_SET);
				fread(buffer, TILE_WIDTH, 1, infile);
				fwrite(buffer, TILE_WIDTH, 1, stdout);
			}
		}
	}

	fseek(infile, paloffset, SEEK_SET);
	fread(palbuffer, 1024, 1, infile);
	fwrite(palbuffer, 1024, 1, stdout);
	fprintf(stderr, "Palette written to %i.\n", width * height);

	fclose(infile);
	exit(EXIT_SUCCESS);
}

```


hopefully it'll be of assistance.

i am currently examining wiht him the possibility to convert to a 256-color TGA with an RGBA palette (ps2 graphics artists tool supports this format, even though i failed to get it to display right on paint shop pro and photoshop)

we chose the TGA as target format due to it's significant similarity to the "corrected" TPL file.
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-11T19:33:05+00:00
- Post Title: 16x8 pixel tiled graphics (.tpl)

> Reply from mugi
>
> this here is the part where i run out of skills really...

i have no idea how the pixel tiles are structured and whatnot,mugi, you're too modest. I like that.

> graphics editing im decent at,I'm pretty sure, you are.  

> i really have no clue about, hence i believe i can no longer be of any further assistance myself.
I don't think so. You could hack the egbg00 file for example. Look at this pic to see what I mean:

[](http://www.pic-upload.de/view-21306737/egbg_hacking.jpg.html)

> , but i never actually tested it as i dont have a compiler handy.
Thx for the code. I'll check it in codeblocks (IDE with mingw, gcc compiler for windows)

> we chose the TGA as target format due to it's significant similarity to the "corrected" TPL file.
Good idea, though I think this might be the 2nd step after hacking (see above).
## Post #13
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2013-11-11T20:03:12+00:00
- Post Title: 16x8 pixel tiled graphics (.tpl)

well, as soon as i get the code from the previous post functioning correctly, there's no need for any hacking.



it's pretty much figured out that a TGA can be used to contain the data after realigning it.

the issue i really have with these files is the fact that they contain multiple images within one file (up to 20 in some extreme cases) and as you found out yourself earlier too
the data format isnt always the same (there's that 160x224 pixel "thumpnail" there that's raw RGBA data)

hence why i need a programmer, it will be plain maddness to decompile and reassemble these files by hand so in order to continue my translation project, i will need an application, capable of rewriting the tpl files and converting back and forth between the 3 formats (the tiled main graphic, the RGBA raw thumbnail and TGA to edit)

i REALLY want this project done. and im willing to pay for someone to code such a tool.
i can dump more examples (or even all of them) if need be.
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-11T21:39:49+00:00
- Post Title: 16x8 pixel tiled graphics (.tpl)

Again I'm stuck. How did you display the pic?
I used these params egbg00 80 480 360 172880 > out.bin with the compiled exe of your first code sample.

As the resulting bin has no header what did you do to display it (as TGA, I guess)?

Just added a binary TGA header? Maybe upload it cause I don't have the time to build one for myself.

last question: why again the pic looks distorted. Is this caused by the zoom?
very last question: How does it look ingame?

This is what I get using TextureFinder:
[](http://www.pic-upload.de/view-21308364/egbg00_PaulGuy_texturefinder.jpg.html)
(Strangely the width 480 isn't good, so I used 240 on format 8888, nothing other suitable in this tool.)
## Post #15
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2013-11-11T22:00:57+00:00
- Post Title: 16x8 pixel tiled graphics (.tpl)

haent tried them ingame yet.
i'll do that once i get them to extract and rebuild the way i want.

i trust data, so once its' verified that the data is fine, i'll start doing in-game implementations.

as for tga header.

use: 0001 0100 0000 0120 0000 0000 E001 6801 0800
as the header, paste the palette after the header, and the data after the palette.

if you want the code to write the palette before the data, just move the bit of code at the end regarding writing the palette, to before writing the pixel data.

the image is distorted because the code is not working as it should. Paulguy had it display the image correctly, but i haven't gotten it to do that yet. Reason for this is currently unknown.
We are working on it. (it looks like for some reason the output randomly generates an extra "0A" bytes to the data, several can be seen at the first 10 entries of the palette, the rest somewhere in the data.) 

note: the tga you will generate with this header is a 256-color indexed (RGBA palette) TGA. a good deal of graphics editors do not display it correctly at all.
it is also worth a note that due to the way TGA is being read, theimage output will be flipped both horizontally and vertically

when the code works as it should, this is what it does. (paulguy's raw output as a test. I just screenshotted it )
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-11T22:49:27+00:00
- Post Title: Re: 16x8 pixel tiled graphics (.tpl)

> Reply from mugi
>
> as for tga header.

use: 0001 0100 0000 0120 0000 0000 E001 6801 0800Just to be sure: no typo?
This is my header, palette start marked by the short line:
[](http://www.pic-upload.de/view-21308656/indexed_tga_header.jpg.html)

> if you want the code to write the palette before the data, just move the bit of code at the end regarding writing the palette, to before writing the pixel data.I know that, thx.  

> We are working on it. (it looks like for some reason the output randomly generates an extra "0A" bytes to the data, several can be seen at the first 10 entries of the palette, the rest somewhere in the data.)With the original I had  additional 251 bytes before the palette. But I don't see an error in the code so far.
(Added a +1 to the buffer sizes, inserted a fclose(stdout) to be sure but that should not be required.)

> note: the tga you will generate with this header is a 256-color indexed (RGBA palette) TGA. a good deal of graphics editors do not display it correctly at all.Yep, got this prob with gimp. Although I switched to indexed image mode it doesn't seem to load it as such. Or the above header is wrong?

edit: could be an issue with the file mode, binary versa ASCII.
## Post #17
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2013-11-11T22:53:43+00:00
- Post Title: Re: 16x8 pixel tiled graphics (.tpl)

the header is correct, but this is a TGA tailored for console game use and hence barely ever seen with pc's.
i use ps2 graphics artists tools to generate them.
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-11T23:14:58+00:00
- Post Title: Re: 16x8 pixel tiled graphics (.tpl)

yes, each 0A is extended to 0D 0A. Don't know how this could work for paulguy. Maybe he's on a UNIX machine?
Don't remeber exactly how it's handled there.

An outfile has to be opened in binary mode ("wb").
## Post #19
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2013-11-11T23:18:05+00:00
- Post Title: Re: 16x8 pixel tiled graphics (.tpl)

he doesnt use windows as far as i know.
i'll see what i can do for that. As i'e stated many times to this point, my programming is a zero. i have no idea what's going on in that code 

edit: SUCCESS!!

you are a genius 

i ran the .tpl though the decoder, opened in hex editor and replaced 0D0A with 0A.
then wrote a TGA header for it, result below:



there are still few minor distortions, but that's propably due to the poking it with hex editor 
i'll try and have the code fixed sometime soonish~
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-11T23:47:27+00:00
- Post Title: Re: 16x8 pixel tiled graphics (.tpl)

> Reply from mugi
>
> 

edit: SUCCESS!!

you are a geniusNope, I surely know I'm not.  
But you are on your way to. Since you're young (I guess) and talented.

> i'll try and have the code fixed sometime soonish~
Here's the exe. As soon as you confirm it working properly I'll upload the updated code, if required.
[PaulGuy_cons.zip](http://www.uploadmb.com/dw.php?id=1384213226)

edit: hmm, well. the header has fixed values for width, height - this should be changed in next version.
## Post #21
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2013-11-12T00:08:21+00:00
- Post Title: Re: 16x8 pixel tiled graphics (.tpl)

it works perfectly even.
im not talented though, nor young 

now that this problem is out of the way, im on my way to the next one.

it appears the developers were complete asses when making these files. i looked up at a character render; 
yuz01.tpl which is one image, 42kB in size, and according to it's header the resolution is 512x128.

obviously it isnt so because there isnt enough data to draw that much x_x

is there a way to calculate the how many tiles an image of certain resolution would take ? 
it could be used to estimate the resolution since it seems that the header data is just bogus. (i'll also have to test in-game does the resolution actually affect anything even, since it's obviously incorrect.)

uploaded yuz01.tpl for you if you want to take a look at it. Grab it [Here](http://mce.do.am/dev/psp/yuz01.rar)
i'll have to call it a day now, gotta get up to work in 6 hours 

thanks again though, even as incomplete as this extraction routine currently is, looking at the whole thing, i should be able to start testing things with it now.
## Post #22
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-12T09:01:08+00:00
- Post Title: Re: 16x8 pixel tiled graphics (.tpl)

> Reply from mugi
>
> it appears the developers were complete asses when making these files.hehehe, it appears someone is not very thankful to the developers who just try to earn money by providing us with nice games...  

> is there a way to calculate the how many tiles an image of certain resolution would take ?
Since a 16x8 tile has 128 pixels just divide (width x height) by 128. But I don't see how this could help.

This is the closest hit I had (TextureFinder, width: 128, Format: 8888):
[](http://www.pic-upload.de/view-21310234/yuz01_512x80--128.jpg.html)
by using PaulGuy_cons yuz01.tpl 48 512 80 41008
512x80= 40960 is the pic data size in bytes (resp. pixels in 256 color mode).
## Post #23
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2013-11-12T10:02:29+00:00
- Post Title: Re: 16x8 pixel tiled graphics (.tpl)

im at work atm so cant really check much at the time, but i ran it with few different settings before going to bed last night and i got it to display pretty close with 128x360 / 128x360 / 128/256 or something along these lines. i had issues testing different settings because the application does checks to not allow resolutions that exceed the data size and/or resolutions that arent multiple of 8/16.

i'll do some research and get some screenshots later today to see the approximate sizes of the files.

the reason i was thinking about calculating approximate resolution based on data size is exactly because it has to be dividable with 8/16,
 so there arent TOO many possible sizes to test with images this small.

> Reply from shakotay2
>
> hehehe, it appears someone is not very thankful to the developers who just try to earn money by providing us with nice games...
well, it's more like i think it's just illogical. why go through all the trouble of using something like this when the SDK provides a ready to use library for gim that supports alpha and whatnot, or just use some other standard format ? 

makes me wonder if they do things like this just to annoy hackers sometimes. 
Either way, i dont really mind since i enjoy reversing silly fileformats.
## Post #24
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-12T12:01:05+00:00
- Post Title: Re: 16x8 pixel tiled graphics (.tpl)

> Reply from mugi
>
> [...]i had issues testing different settings because the application does checks to not allow resolutions that exceed the data size and/or resolutions that arent multiple of 8/16.I append a CodeBlocks project where such things will be allowed. Nevertheless it doesn't makes sense to read past the filesize. The width/height sizes must be adapted in this case.
[PaulGuy_cons.zip](http://www.uploadmb.com/dw.php?id=1384256713)
(Hopefully I didn't mess up anything.)

On another note: on the page before you wrote:

> Reply from mugi
>
> another piece of code below, encodes back to tiled format. Again, not tested by me as i still dont have a compiler set up.
I'm not sure but seems this is just another un-tiling code: (upps, nope, it's indeed the encoder)

```
>>>		for(j = 0; j < width; j += TILE_WIDTH) {
>>>			for(k = 0; k < TILE_HEIGHT; k++) {
>>>				fseek(infile, offset + (i * width) + j + (k * width), SEEK_SET);
				fread(buffer, TILE_WIDTH, 1, infile);
				fwrite(buffer, TILE_WIDTH, 1, stdout);
			}
		}
	}
```
because the lines marked by ">>>" are the only ones that are different.
## Post #25
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2013-11-12T16:27:51+00:00
- Post Title: Re: 16x8 pixel tiled graphics (.tpl)

i'll test out the tile encoder and see if it works, but i'd assume it does.
dont really see any reason why he'd write 2 un-tiling apps 

it'slikely that the tile encoder has the same bug than the decoder though, where it changes 0A to 0D0A :/
need to check that out.
## Post #26
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-12T17:02:32+00:00
- Post Title: Re: 16x8 pixel tiled graphics (.tpl)

> Reply from mugi
>
> i'll test out the tile encoder and see if it works, but i'd assume it does.
dont really see any reason why he'd write 2 un-tiling appsThe original files having the palette near the end
the decoded (tgas) have it near the beginning, right?
So I'm confused why both original codes place the palette near the end.

(edit: this is a bug with the first code maybe you should edit it to not confuse other users.)

> it'slikely that the tile encoder has the same bug than the decoder though, where it changes 0A to 0D0A :/
>
> need to check that out.It doesn't write in binary mode  so it surely will. (It's not a bug it's the wrong OS I guess.)

So here the slightly modified encoder from paulguy:
(compile it to paulguy_enc.exe for example)

```
#include <stdlib.h>
#include <windows.h>

#define TILE_WIDTH (16)
#define TILE_HEIGHT (8)

int main(int argc, char **argv) {
	int offset, width, height, paloffset;
	long delta, filesize;
	FILE *infile, *outfile;
	char buffer[TILE_WIDTH+1];                       // you can delete the +1 I guess, just debugging remains
	char outfileName[256], palbuffer[1024+1];
	int i, j, k;
    	bool bErr= false ;

	if(argc < 6) {
		fprintf(stderr, "USAGE: %s <infileName> <offset> <width> <height> <paloffset>\n"\
		                "\tOutput goes to infileName+'.tga'.\n", argv[0]);
		exit(EXIT_FAILURE);
	}

	offset = atoi(argv[2]);
	width = atoi(argv[3]);
	height = atoi(argv[4]);
	paloffset = atoi(argv[5]);

	if (offset < 0) {
		fprintf(stderr, "Offset must be positive.\n");
		bErr= true;
	}
	if (width < TILE_WIDTH) {
		fprintf(stderr, "Width must be greater than TILE_WIDTH (%d).", TILE_WIDTH);
		bErr= true;
	}
	if (height < TILE_HEIGHT ) {
		fprintf(stderr, "Height must be greater than TILE_HEIGHT (%d).", TILE_HEIGHT);
		bErr= true;
	}
        if (bErr) exit(EXIT_FAILURE) ;

    	if (width % TILE_WIDTH != 0)
            fprintf(stderr, "WARNING: width should be a multiple of %d.\n", TILE_WIDTH);
    	if (height % TILE_HEIGHT != 0)
            fprintf(stderr, "WARNING: height should be a multiple of %d.\n", TILE_HEIGHT);

	infile = fopen(argv[1], "rb");
	if(infile == NULL) {
		fprintf(stderr, "Failed to open %s.", argv[1]);
		exit(EXIT_FAILURE);
	}

	strcpy(outfileName, argv[1]) ; //strcat(outfileName, ".tga") ;
	strcat(outfileName, ".tpl") ;
	outfile = fopen(outfileName, "wb");
	if(outfile == NULL) {
		fprintf(stderr, "Failed to open %s", outfileName);
		fclose(infile) ;
		exit(EXIT_FAILURE);
	}

	fseek(infile, 0, SEEK_END);
	filesize = ftell(infile);

	if(offset > filesize) {
		fprintf(stderr, "*** Don't set the offset past the filesize (%d)!\n", filesize);
        fclose(infile); fclose(outfile) ;
		exit(EXIT_FAILURE);
	}
	delta= filesize - offset ;
	if(width * height + offset > filesize) {
		fprintf(stderr, "Read with set width:%i, height:%i and offset:%i would go past the end of the file.\n\n>>> change w to %d or h to %d\n", width, height, offset, delta/height, delta/width);
		bErr= true ;
	}
	if(paloffset < 0 || paloffset + 1024 > filesize) {
		fprintf(stderr, "Palette offset must be a positive value and within 1024 bytes from the end of the file.\n");
        bErr= true ;
	}
    	if (bErr) {
        	fclose(infile); fclose(outfile) ;
		exit(EXIT_FAILURE);
    	}

	fseek(infile, 0, SEEK_SET);
	for(i = 0; i < height; i += TILE_HEIGHT) {
		for(j = 0; j < width; j += TILE_WIDTH) {
			for(k = 0; k < TILE_HEIGHT; k++) {
				fseek(infile, offset + (i * width) + j + (k * width), SEEK_SET);
				fread(buffer, TILE_WIDTH, 1, infile);
				fwrite(buffer, TILE_WIDTH, 1, outfile);
			}
		}
	}
    	fprintf(stderr, "%d B. pic data written\n", width * height);

	fseek(infile, paloffset, SEEK_SET);
	fread(palbuffer, 1024, 1, infile);
	fwrite(palbuffer, 1024, 1, outfile);
	fprintf(stderr, "Palette written\n");

	fclose(infile); fclose(outfile);
	exit(EXIT_SUCCESS);
}
```

Now it's rather simple to test: decode a .tpl then encode the resulting file. If you get the same as the original, well, then it's an encoder. 

edit: yes, it works.
Use this cmd line: PaulGuy_enc egbg00.tga 1042 480 360 18
(We have an offset of +18 to the pixel data start (1042=1024+18) and the palette start (18=0+18) 
because of the tga header in the egbg00.tga)
## Post #27
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2013-11-12T17:42:02+00:00
- Post Title: Re: 16x8 pixel tiled graphics (.tpl)

it should work on the background files like egbg00 we tested things out with.

however, i've been analyzing the yuz01, along with few other character renders and it seems it's using a different type of encoding (mode flags maybe, which is yet another reason for me to believe that the file header in TPL is actually just a bogus)

i worked on aru01, which according to the header is 64x512 pixels, and in-game the character render is 151x208 pixels, meaning the image is either exactly that, or somewhat larger.
Another thing with these renders is that it seems that yellowish colors (skin tone and yuzuha's yellow clothes) somehow manage to turn blue, even though the rest of the palette is working properly.

also, i went though tons of horizontal resolution values starting from 64 all the way up to 256 and it seems that the 128 is the only one that doesnt distort the image too badly.
with this though as some blocks align just right, there's a 1-pixel wide line of data that's not on it's place between every row of pixel blocks.

if i'd have to guess, it means that the blocksize isnt the same as it is on the background images.

edit: the reason the original code places the palette at the end is because it was made before the idea of using TGA came along.

edit2: can you compile the executables please, i cant seem to get the code to build wiht TCC (i'll get a proper compiler at some point)
## Post #28
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-12T19:57:34+00:00
- Post Title: Re: 16x8 pixel tiled graphics (.tpl)

[PaulGuy_decEnc.zip](http://www.uploadmb.com/dw.php?id=1384285948)

Maybe we've got a little problem here concerning the recalculating of proposed width/height when 
the user chosen values cause an EOF crosssing. For the decoder delta should be filesize-1024-offset.

Also the palette size is not always 1024 (0x400). Tell me if you face a problem so far.
Maybe it should become another param in the command line?
## Post #29
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2013-11-12T20:58:49+00:00
- Post Title: Re: 16x8 pixel tiled graphics (.tpl)

currently my only issue is these alpha channeled character renders (i dont actually have to edit these, but they're built hte same way as the menu files that do contain text)
it would appear that:

- the resolution values of these images are complete nonsense.
- i assembled aru02.tpl from the decoded blocks by hand to get the picture, and there are not enough tiles to form a full image.
there might be some tile reordering code involved which somehow dumps dublicate tiles to save space or whatever. The tiles are also seemingly not in any sane order.

- the palette on these character renders is 0x400 in size, but goes completely bonkers when used. it's sort of like half negative image and half negative colors (blues turn reds, yellows to blues, etc)
i checked and the palette data is identical to original TPL, so it does not corrupt on converting.

TL;DR: we have a problem.

edit: tested out the encoder and it seems to work fine on the background images.
propably it works fine with the other images too, but that isnt helping much until i figure out how read them correctly 

  

Edit: d'oh.. I think the palette is actually BGRA, not RGBA.
The background image with the girl threw me off because the rocks look "normal" on it, but after i slept over it i realized tha the colors are off in that picture too.. The scene is inside a cave, so the rocks are actually supposed to be dark blueish color.

If you wish to experiment with this particular render, its aru02.tpl. Should be included in the \ch folder on the examples i posted in the original thread.
Actual image dimensions are 176x208 pixels/11x26 tiles. The data is missing 30 tiles worth of data.

edit2: could you implement this for decoder and encoder please?

BGRA<->RGBA decode

```
j = palbuffer[i];
palbuffer[i] = palbuffer[i + 2]
palbuffer[i + 2] = j;
}

```


corrected output:


still cant compile the code myself 
i'll try and get a proper compiler setup today so that i can do small modifications like this myself.
## Post #30
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-15T20:43:27+00:00
- Post Title: Re: 16x8 pixel tiled graphics (.tpl)

Didn't see your 2nd edit; is your compiler setup ok now?
## Post #31
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2013-11-16T10:10:19+00:00
- Post Title: Re: 16x8 pixel tiled graphics (.tpl)

Not yet, i've been pretty busy with work all week.
Havent had much time to sit at my pc.
I'll get back home later oday and hoping to get to work on this more again.

Also been looking into the scripts of the game too.
## Post #32
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-16T12:42:23+00:00
- Post Title: Re: 16x8 pixel tiled graphics (.tpl)

So here's the changed files:
[PaulGuy.zip](http://www.uploadmb.com/dw.php?id=1384603957)

There are three additional params:
PaulGuy_cons d egbg00 80 480 360 172880 256 0
Decoding was o.k.
PaulGuy_cons e egbg00.tga 1042 480 360 18 256 0
Encoding too. So it's one app now with 'd' for decoding and 'e' for encoding.

Didn't test other than 256 palEntries. Last param='1' (for BGRA-RGBA change) also untested.
## Post #33
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2013-11-16T18:49:17+00:00
- Post Title: Re: 16x8 pixel tiled graphics (.tpl)

i tested it out and the BGRA<->RGBA works perfectly 
didnt test the palette size yet, but im pretty sure it works just fine too anyway 

here's a decoded file against an in-game screenshot:

  

this'll be hopefully all i need regarding the basic image format.
now all my issues are with those alpha channeled images that make no sense whatsoever.

im gonna start doing testing with them starting tomorrow. (been having a rough week so im just gonna get to bed )
can't thank you enough though, the graphics were pretty much the go or no-go of my project, whatever else i can pretty much go around or through with 

i'll keep you updated regarding what else i find, but im not quite sure the format itself holds any more secrets on itself.
the tile layout data for the renders and whatnot is propably just located elsewhere.

edit: oh great, my site is down (again)
it's been shit for a while now so if images dont display, they'll come back eventually. 

edit2: well, decoding the picture with a palette size of 16 works great too (it imports it correctly) but another issue came up with it.

a picture using 16 color palette seems to have a different imagestructure alltogether.
i did some calculations and an image with resolution of 512x512 would take 2048 tiles (32x64 16x8pixel tiles) which in data would be 0x40000. but the image i have at hand is only 0x20000 in size.
i got it to somewhat display, but it's not exactly correct. The decoder aligns it right but it becomes a mess since trying to use 512x512 as resolution is not possible since it goes way over the filesize.

also, the TGA header needs to be modified for the 16-color images.

256-color header: 
0001 0100 0000 0120 0000 0000 8001 8001 
0800

16-color header: 
0001 0100 0010 0020 0000 0000 0001 0001
0800

edit3: disregard. Problem solved. TPLencdec updated. (no 16-color encode support yet.)

started versioning the code to keep track of it now, i have like 20 different versions and no clue what is what 

output:
