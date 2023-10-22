## Post #1
- Username: Jille
- Rank: VIP member
- Number of posts: 38
- Joined date: Mon Aug 29, 2005 10:07 pm
- Post datetime: 2016-07-06T13:30:44+00:00
- Post Title: [help needed] Extracting Infotainment image archives

Hi all,

It's been a LOOOOONG time since I've last been here... but I finally found myself a new challenge, in the shape of.... my car infotainment graphics   
Something different from the regular stuff, but I thought it would be worth a try to mess around with them and customize.

There are 3 files for each skin:
- images.mif (aka Multiple Image File, that's filled with png files)
- imageidmap.res (directorystructure and filenames for each of the images)
- mapping.txt (some mapping file)

I've spend several days in Hex Workshop, trying to get my head around these files, but so far, I haven't been able to get any useful stuff from images.mif, and that's frustrating me   
So that's why I dropped by here, to see if you guys have any ideas and can help me with this challenge!

I uploaded my files to dropbox:
[https://www.dropbox.com/sh/ud2eetds05fd ... DnI8a?dl=0](https://www.dropbox.com/sh/ud2eetds05fdqic/AAAN4U3QK9dWWLyLg1c8DnI8a?dl=0)
Included are: 
3 different sets of skin files (two of them have 49 images, the other has 50 images)
My Hex Workshop bookmarks and color mappings. Bookmarks are based on the files in directory 0203070900.


I really hope someone wants to have a look at this with me. Thanks in advance for helping out!
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-07-31T22:13:42+00:00
- Post Title: [help needed] Extracting Infotainment image archives

hey

the .mif files have valid zlib chunks which you can extract with offzip:

```

```


there are some texture chunks which look car like:
## Post #3
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-08-01T17:14:54+00:00
- Post Title: [help needed] Extracting Infotainment image archives

Yep, the *.dat files seem to be images. 



The *.neo seem to be overlay pieces that get overlaid onto the main images to *change* features.



and the *.fnc are maybe 'functional' overlays?



Kinda neat though. what kind of car is this?  *EDIT* Nevermind, I see from the images ;p
## Post #4
- Username: Jille
- Rank: VIP member
- Number of posts: 38
- Joined date: Mon Aug 29, 2005 10:07 pm
- Post datetime: 2016-08-01T19:00:57+00:00
- Post Title: [help needed] Extracting Infotainment image archives

Thanks guys, this was the push in the right direction I needed!

I extracted most of the image archives from the car now. It's about the Volkswagen Golf. I drive a GTE (Hybrid version of the GTI), and for some reason VW chose not to give us a GTE-graphic in the vehicle status menu, so I have the default image of a regular Golf. The E-Golf one is closest to the the GTE when it comes to looks. But when I chose for the E-Golf skin in the headunit's software, certain GTE specific views get messed up. So now I got a little closer to creating my own custom car graphic.

Thanks guys!!!

Image to clarify my feelings   



golf.jpg (215.88 KiB) Viewed 105 times
## Post #5
- Username: Jille
- Rank: VIP member
- Number of posts: 38
- Joined date: Mon Aug 29, 2005 10:07 pm
- Post datetime: 2016-08-04T16:46:29+00:00
- Post Title: [help needed] Extracting Infotainment image archives

Update:

I can now extract data from the MIF file without offzip.
It's pretty straightforward. 

The archive is built like this:
Archive Header, containing amount of files and a unique ID that is being referred to in mapping.txt as well. 

Header for file 1:
CD01		0000 A001 		0000 04 		0000 		5979 		0000 		789C
Width 		Height		unknown			Length of data 		Start of data
Data of File 1 (being zlib compressed RGBA data)

**RGB data*
Header for file 2
Data for file 2

et cetera.


Footer
Containing a hash or checksum for each of the files.


I haven't been able to determine the hash/checksum in the footer, but I'll walk through the DGTEFF again to get some renewed inspiration. With a bit of luck I'll be able to modify files in the archive soon!
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-08-04T22:37:33+00:00
- Post Title: [help needed] Extracting Infotainment image archives

there are no hashes or checksums i can see.

images.mif format:

```
uint footer_offset;

// [..]

struct data
{
  uint width, height, byte_pp;
  uint zsize;

  ubyte data[zsize];
};

FSeek(footer_offset);

uint num;

struct
{
  uint index; // 0-based
  uint offset;
} offset_table[ num ];

int uid // mapping.txt stores this as a signed integer

uint meta_name_len;
char meta_name[meta_name_len];

uint meta_author_len;
char meta_author[meta_author_len];

Assert(FEof());

```


mapping.txt

plaintext format of imageidmap.res
UID is the same as the images.mif number (signed int)

the "mappings" just converts the images to filenames

imageidmap.res

binary format of mapping.txt which just stores the filenames as wide strings:

```
char magic[4]; // "Skr0"

int uid; // should match mapping.txt

uint un_1;

uint image_count;

struct
{
  uint zero;
  uint len;
  wchar_t original_filename[len];
} images[ image_count ] <optimize=false>;

uint un_5;
uint mifId_count;

uint mifIds[ mifId_count ];

Assert(FEof());

```


summary: there are no checksums - just make sure the offsets are updated when you patch the images
## Post #7
- Username: Jille
- Rank: VIP member
- Number of posts: 38
- Joined date: Mon Aug 29, 2005 10:07 pm
- Post datetime: 2016-08-05T06:21:54+00:00
- Post Title: [help needed] Extracting Infotainment image archives

> Reply from WRS
>
> there are no hashes or checksums i can see.
summary: there are no checksums - just make sure the offsets are updated when you patch the images

haha I discovered the same thing last night   it's a pretty straightforward file!

Thanks for the extensive information and inspiration!!
Let's see if I can upload some new graphics to the device today
## Post #8
- Username: Jille
- Rank: VIP member
- Number of posts: 38
- Joined date: Mon Aug 29, 2005 10:07 pm
- Post datetime: 2016-08-05T11:43:15+00:00
- Post Title: [help needed] Extracting Infotainment image archives

Update:

- Modified image
- Converted to RGBA
- Zlib compressed
- Deleted binary data from old image from mif file
- Inserted binary data from new image into the mif file in the exact same location.
- Changed the values of the offsets at the bottom of the file. They are correct. Going to the offsets manually ends up in the right place.
- Saved the file and replaced old mif file on the device.

None of the files in the archive was showing. So this leads me to believe one of the following things happened:
- I messed up (but... I've went over my actions several times now, I highly doubt that is the case)
- converting from png to RGBA with imagemagick went wrong (but... I checked the converting process by converting the original files back and comparing them to the original: 100% identical)
- zlib compression differences (comparing the original zlib chunk to a recompressed file tells me there are a few differences. But expanding it leads to the same file again, so shouldn't be a problem).
- there's a checksum somewhere else in the system that checks the integrity of the archive.

Ideas are welcome!
## Post #9
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-08-05T21:13:56+00:00
- Post Title: [help needed] Extracting Infotainment image archives

> Reply from Jille
>
> - Changed the values of the offsets at the bottom of the file. They are correct. Going to the offsets manually ends up in the right place.

did you update the footer offset in the header? if your compressed data changed size, this will need updating too   

see

```
uint footer_offset;

...

```
## Post #10
- Username: Jille
- Rank: VIP member
- Number of posts: 38
- Joined date: Mon Aug 29, 2005 10:07 pm
- Post datetime: 2016-08-07T10:23:09+00:00
- Post Title: [help needed] Extracting Infotainment image archives

> Reply from WRS
>
> Jille wrote:- Changed the values of the offsets at the bottom of the file. They are correct. Going to the offsets manually ends up in the right place.

did you update the footer offset in the header? if your compressed data changed size, this will need updating too   

see
Code: Select alluchar magic[6]; // ESOMIF
uint footer_offset;

...

*facepalm*
You are right (again).
Fixed it, and this is the result:
## Post #11
- Username: Jille
- Rank: VIP member
- Number of posts: 38
- Joined date: Mon Aug 29, 2005 10:07 pm
- Post datetime: 2016-12-08T22:29:15+00:00
- Post Title: [help needed] Extracting Infotainment image archives

Update!

I began working on some other infotainment-related file formats as well...


This one should parse most of the MCF file format, as found in this file:
[https://www.dropbox.com/s/sdwvwm8hzru5a ... s.mcf?dl=0](https://www.dropbox.com/s/sdwvwm8hzru5a5s/images.mcf?dl=0)

However, there are still some values I couldn't determine... those are probably checksums or something that I didn't think about yet. Do you guys have any idea?

```
//--- 010 Editor v5.0 Binary Template
//
// File:        mcf.bt
// Author:      Jille
// Revision:    8
// Purpose:     Discover Pro MIB2 images.mcf file parser
// Comments:    Each of the marked files in this archive is ZLIB-compressed RGBA data
//--------------------------------------

////////////////////////////////////////////////////////////
uchar magic[4]; // ‰MCF
uint header_unk_1;     //these 4 ints are always the same in all files
uint header_unk_2;     //at least, for the ones I've checked.
uint header_unk_3;     //so this is also always the same
uint header_unk_4;     //as well as this


uint toc_header; //"TOC " This is where the table of contents starts.
uint divider_5; //always 0. Divider?
uint unknown_6; //always 4. I don't know why.
uint size_of_TOC; //the size of the table of contents. This table starts after num_of_files
uint size_of_TOC_copy; //== always identical to 7
uint divider_9; //always 0. Divider?
uint unknown_10; //some kind of checksum?

uint num_of_files;  // the number of files in this archive. After this, size_of_TOC is going to count.


// first, it's displaying a list of files, their ID, the offset where it starts
struct    
{
    uchar filetype[4];  // always "IMG "
    uint file_id;
    uint offset;
    uint size;
} toc [num_of_files];

uint unknown_11;  //unknown data


local int i;
for(i = 0; i < num_of_files; i++)
struct
{
    uchar filetype[4];      //always "IMG "
    uint file_id;           //the unique number of the file. Be aware, it starts at 1, while this array starts numbering at 0;

    uint pixel_depth;        // this seems to be always 0x08 00 00 00
    
    uint zipped_size;
    uint unzipped_size;
    uint bool_compression;        // always 1. Possibly a boolean for compression on/off?

    uint unknown_16;        //don't know... some kind of checksum?
    short width;    //speaks for itself
    short height;   //speaks for itself
    short unknown_17;      // this is sometimes 0x0411(4356), sometimes 0x0010(4096)
    short divider_18;     //always 00
    uint data[ (toc[i].size/4)-9 ]; // Zlib data

} contents;

Assert(FEof());
```
