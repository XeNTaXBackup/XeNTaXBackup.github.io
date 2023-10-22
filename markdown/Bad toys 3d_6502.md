## Post #1
- Username: smokeTH
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Apr 26, 2011 5:33 am
- Post datetime: 2011-04-25T21:43:16+00:00
- Post Title: Bad toys 3d

Here is a tough one. The program itself is 16bit wolfenstein-like game which i belive was made for originally win 3.2 (but because of good coding it works even under win7 32bit). 
Basically i need to unpack its data archive. Hyper-ripper from dragon unpacker was able to extract only wav and some bmp files, but not sprites, neither tiles. Halp!  

This is main game archive  (i believe it is).
[http://dl.dropbox.com/u/9288177/data.pck](http://dl.dropbox.com/u/9288177/data.pck)

P.S.  This file is not any pck that Internet knows. It was made in ~ 1993 or a bit later years...

UPG:  

Resources have been released via zdoom forums. 
[http://forum.zdoom.org/viewtopic.php?f=37&t=49998](http://forum.zdoom.org/viewtopic.php?f=37&t=49998)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-25T23:39:59+00:00
- Post Title: Bad toys 3d

script for QuickBMS:

```
getdstring NAME NAMESZ
get OFFSET long
get FILES long
goto OFFSET
for i = 0 < FILES
    getdstring NAME 8
    get OFFSET long
    get SIZE long
    log NAME OFFSET SIZE
next i
```
## Post #3
- Username: smokeTH
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Apr 26, 2011 5:33 am
- Post datetime: 2011-04-25T23:42:27+00:00
- Post Title: Bad toys 3d

oops..wait i'll see. if this is completed script...then....
## Post #4
- Username: smokeTH
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Apr 26, 2011 5:33 am
- Post datetime: 2011-04-26T01:04:53+00:00
- Post Title: Bad toys 3d

another question.... how can i define file types? BM its bitmap, SND is Wav pcm..another ones is.....*confused*
What i got is that those bmp files named in archive after their hexadecimal headers.
## Post #5
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-04-26T18:34:11+00:00
- Post Title: Bad toys 3d

For Bad Toys 3D I believe not all data is contained in the pck but in the EXE, such as sprites and textures. Am I correct? 


Edit: Apparently so.
## Post #6
- Username: smokeTH
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Apr 26, 2011 5:33 am
- Post datetime: 2011-04-26T21:26:27+00:00
- Post Title: Bad toys 3d

i don't think so. ya see - there is around half of that pck file with unknown files. and there is also PAL file means it using palette....so basically i believe there is images (self-made file format) only with palette links but without palettes themselves. (just like images in red alert 2 to example). Well, if you was able to find and convert some sprites and tiles in default formats (png/bmp) please pack them and post 'em there. I'll be much appreciated.
## Post #7
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-04-26T22:09:09+00:00
- Post Title: Bad toys 3d

BM - BMPs, like numbers and screens.
HS - Help Screens, BMP.
M - BMPs, map icons?
SND - WAVs

DEM - Demo recorded gameplay
MAP - Self explanatory.

Will look into what the others are.

VEC and VOS seem to be a kind of encrypted image format, worth checking into?
## Post #8
- Username: smokeTH
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Apr 26, 2011 5:33 am
- Post datetime: 2011-04-28T18:59:08+00:00
- Post Title: Bad toys 3d

why not? Pack of not-bad sprites and tiles. you see - i kinda wanted to make zdoom-skulltag wad based on this game.That's why i tried unpack it myself with few apps and after that found this forum.
## Post #9
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-04-28T22:08:52+00:00
- Post Title: Bad toys 3d

Well, not sure what they are, and the BT_PAL is suggested to be a palette but can't seem to get that to work. All the other files I do not know their purpose, aside from CREDITS and README of course. But some cracking of VOS and VEC is needed, anyone game for checking these file types?
## Post #10
- Username: smokeTH
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Apr 26, 2011 5:33 am
- Post datetime: 2011-04-29T08:41:19+00:00
- Post Title: Bad toys 3d

i can suggest you find good 16-bit NE (not PE) disassembler to find-out how game engine itself is reading those files.... what about me - i can't clearly say what type of algorythm does it uses...that was around 95 year when that game was released - basically in that time every devs fapped like they wanted to, there was no standards in graphics packaging.
## Post #11
- Username: smokeTH
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Apr 26, 2011 5:33 am
- Post datetime: 2011-04-30T15:07:09+00:00
- Post Title: Bad toys 3d

i really interested in topic...and in accomplishing this task so BUMP.
## Post #12
- Username: skaman86
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 04, 2011 1:58 am
- Post datetime: 2011-10-03T19:45:37+00:00
- Post Title: Bad toys 3d

Sorry, I pm'd a some of you about this already. I just really am Interested to find out if this has been accomplished? I tried with Dragon UnPACKer, it seems maybe the previous posters hace had more success than I have with this issue. Any help is appreciated.
## Post #13
- Username: smokeTH
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Apr 26, 2011 5:33 am
- Post datetime: 2015-11-26T07:34:43+00:00
- Post Title: Bad toys 3d

Ok. Time to resurrect this post.

So, i decided to try it again. Basically VEC/VOC/BLB/PRK/RBT etc are all same kind of graphic. A buddy of mine on #openapoc channel on freenode (check them out, they are trying to bring xcom apocalypse back) helped a great deal in deciphering the format. 

As it turns out it is a basic paletted image, column-major one, with 256 byte header, header consisting of 2 packs of uint16_t pairs, each 64 size, which control column begins/ends.
I'll attach linux sourcecode for the converter and some results. 

Now, looks like wall/floor/ceiling textures themselves were embedded into .exe after all.



```
#include <fstream>
#include <cstdint>
#include <string>
#include <memory>
#include <array>
#include <algorithm>
#include <cstring>
#include <png++/png.hpp>

struct data_pair
{
	uint8_t row_skip;
	uint8_t copy_count;
};

static_assert(sizeof(data_pair) == 2, "data_pair wrong size");

struct image
{
	std::array<uint16_t,64> offsets;
	std::array<data_pair,64> data_pairs;
	uint8_t data[];
};
static_assert(sizeof(image) == 256, "image wrong size");

struct colour
{
	uint8_t r, g, b;
};
static_assert(sizeof(colour) == 3, "colour wrong size");

struct palette
{
	colour c[256];
};
static_assert(sizeof(palette) == 256*3, "palette wrong size");

int main(int argc, char **argv)
{
	if (argc != 3)
	{
		std::cerr << "Must specify input and palette files\nTo example:\n vec_decode.exe VEC_1 BT_PAL\n";
		return 1;
	}

	std::ifstream inFile(argv[1]);
	if (!inFile)
	{
		std::cerr << "Failed to open \"" << argv[1] << "\"\n";
		return 1;
	}


	inFile.seekg(0, inFile.end);
	size_t length = inFile.tellg();
	inFile.seekg(0, inFile.beg);

	std::unique_ptr<char[]> data(new char[length]);

	if (!inFile.read(data.get(), length))
	{
		std::cerr << "Failed to read " << length << " bytes from \"" << argv[1] << "\"\n";
		return 1;
	}
	std::cerr << "Read " << length << " bytes from \"" << argv[1] << "\"\n";

	palette p;
	std::ifstream inPalette(argv[2]);
	if (!inPalette)
	{
		std::cerr << "Failed to open palette \"" << argv[2] << "\"\n";
		return 1;
	}

	if (!inPalette.read(reinterpret_cast<char*>(&p), sizeof(p)))
	{
		std::cerr << "Failed to read palette from \"" << argv[2] << "\"\n";
		return 1;
	}

	struct image *img = reinterpret_cast<struct image*>(data.get());

	int sizeX = 64;
	int sizeY = 64;

	png::image<png::rgba_pixel> png(sizeX,sizeY);

	//Each record describes a single column
	for (int record = 0; record < 64; record++)
	{
		//There are 'copy_count' pixels in each column, starting after skipping 'row_skip' transparent pixels
		for (int b = 0; b < img->data_pairs[record].copy_count; b++)
		{
			int offset = img->offsets[record] + b;
			//The offset is in the file, but the data[] array starts at the end of the (256-byte) header, so take the header size off the offset
			offset -= 256;
			assert (offset < length);
			uint8_t idx = img->data[offset];
			png::rgba_pixel pix;
			//index 255 is transparent
			if (idx == 255)
				pix = {0,0,0,0};
			else
				pix = {p.c[idx].r, p.c[idx].g, p.c[idx].b, 255};

			int y = img->data_pairs[record].row_skip + b;
			int x = record;
			png[y][x] = pix;
		}
		//Any pixels after a column's 'copy_count' are transparent too
	}
	png.write("out.png");




	return 0;
}

```
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-26T20:47:11+00:00
- Post Title: Bad toys 3d

> Reply from smokeTH
>
> Ok. Time to resurrect this post.hello, rider of dead horses!  
(Try to revive a horse, that's dead since 4 years?)

Anyway, thanks for the code.

I managed to compile it on Windows after some struggeling (nasty strerror_r() problem).

Here's a resulting png (uploaded as jpeg): 



vec_104.jpg (3.94 KiB) Viewed 49 times


(Thought it were cut on the righthanded side. Then realized that it needs to be combined with another pic.)
## Post #15
- Username: smokeTH
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Apr 26, 2011 5:33 am
- Post datetime: 2015-11-26T22:43:35+00:00
- Post Title: Bad toys 3d

> Reply from shakotay2
>
> smokeTH wrote:Ok. Time to resurrect this post.hello, rider of dead horses!  
(Try to revive a horse, that's dead since 4 years?)

Anyway, thanks for the code.

I managed to compile it on Windows after some struggeling (nasty strerror_r() problem).

Here's a resulting png (uploaded as jpeg): 
vec_104.jpg
(Thought it were cut on the righthanded side. Then realized that it needs to be combined with another pic.)
Dude! Sick! Post windows version of the code as well. C: Also, you're welcome to help searching for wall textures within exe file (i've brokened my heaeaead today trying to find traces of them    )
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-26T22:58:57+00:00
- Post Title: Re: Bad toys 3d

There's a small change only to make it work with CodeBlocks/MinGW:
in error.hpp (from png++)
add
#include <sstream>
and replace the strerror_r() call like such:

#ifdef HAVE_STRERROR_S
            strerror_s(buf, ERRBUF_SIZE, errnum);
            return std::string(buf);
#else
            std::stringstream ss;
             ss << errnum;
             return ss.str();
            //strerror_r(errnum, buf, ERRBUF_SIZE);
            //return std::string(buf);
#endif

(because MinGW's string.h doesn't contain strerror_r() in CodeBlocks 13.12)

btw: I don't have that exe with textures
## Post #17
- Username: smokeTH
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Apr 26, 2011 5:33 am
- Post datetime: 2015-11-27T07:29:28+00:00
- Post Title: Re: Bad toys 3d

> Reply from shakotay2
>
> There's a small change only to make it work with CodeBlocks/MinGW:

btw: I don't have that exe with textures

there you go. all the info you need. 
[http://www.tibo.cz/archive/bt3dsetup.exe](http://www.tibo.cz/archive/bt3dsetup.exe) installer. (works only if ntvdm present on system, so no 64bit windows), otherwise unpack it via 7-zip. 
[http://www.theisozone.com/downloads/pc/ ... d-toys-3d/](http://www.theisozone.com/downloads/pc/windows-games/bad-toys-3d/) keys.
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-27T10:03:57+00:00
- Post Title: Re: Bad toys 3d

thx - talking about this 153 kB bt3d.exe? If so we could expect 10 pics contained (5 kB each) so that about 100 kB would remain for code (just a wild guess).

You should think about a RAM snapshot.
For pc there are tools to read the RAM (WinHex, menu Tools\RAM editor). Or with some coding skills you could use ReadProcessMemory () in your own tool.

Do you plan to create new maps?



BT3D_map_1.jpg (165.44 KiB) Viewed 38 times
## Post #19
- Username: smokeTH
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Apr 26, 2011 5:33 am
- Post datetime: 2015-11-27T10:48:19+00:00
- Post Title: Re: Bad toys 3d

> Reply from shakotay2
>
> thx - talking about this 153 kB bt3d.exe? If so we could expect 10 pics contained (5 kB each) so that about 100 kB would remain for code (just a wild guess).

You should think about a RAM snapshot.
For pc there are tools to read the RAM (WinHex, menu Tools\RAM editor). Or with some coding skills you could use ReadProcessMemory () in your own tool.

Do you plan to create new maps?
BT3D_map_1.jpg
Yep, we're talking about exe. I were looking through it via IDAPRO and mostly found procedures. then again ida can be a real idiot when it comes to deciphering turbo pascal executables.
I don't know about maps, for me endgoal was a complete spriterip+texture rip, i'll post it onto zdoom forums, after that - i'll create a TC for either gzdoom or zandronum
## Post #20
- Username: smokeTH
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Apr 26, 2011 5:33 am
- Post datetime: 2015-11-27T12:56:49+00:00
- Post Title: Re: Bad toys 3d

Here's the main problem with ram snapshotting - it uses ntvdm (on xp at least), so only way to snapshot is to snapshot the whole thing..but..what do i do after with it? I don't have header signatures at had, because if textures use same graphic as walls -  they have none and distancing 256byte piece of random data from anything else is quiet above my skillset.
EDIT: Nevermind! HxD got installed onto win98 virtual and snapshotted the damn thing itself. it should be a lil bit easier now
## Post #21
- Username: smokeTH
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Apr 26, 2011 5:33 am
- Post datetime: 2015-11-27T17:09:28+00:00
- Post Title: Re: Bad toys 3d

SONOFTHEBITCH! I FOUND EM!
They are at the tail of data.pck, completely unmarked.
## Post #22
- Username: smokeTH
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Apr 26, 2011 5:33 am
- Post datetime: 2015-11-27T17:47:25+00:00
- Post Title: Re: Bad toys 3d

Resources released via zdoom forums. 
[http://forum.zdoom.org/viewtopic.php?f=37&t=49998](http://forum.zdoom.org/viewtopic.php?f=37&t=49998)
