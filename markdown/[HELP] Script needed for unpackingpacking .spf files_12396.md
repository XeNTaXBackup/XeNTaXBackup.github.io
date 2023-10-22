## Post #1
- Username: kuu
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Dec 16, 2014 6:43 am
- Post datetime: 2014-12-15T23:21:26+00:00
- Post Title: [HELP] Script needed for unpacking/packing .spf files

Hi, so I'm currently trying to make sense out of an archive file for a game called Navy Field 2. What I wanted to do was replace the game's voices with my own voices, but I realized that they were all stored in an archive file. I have very little experience with low level programming and hex editing, and I've been spending the entire day trying to make sense out of it and just feel overwhelmed because I'm not getting any leads. If anyone can lend a hand that would be great!!

Here is a background for this game archive format:
The files are .spf extention. They are used for a variety of things to store data, but mainly for storing music and sounds. For example, BGM.spf stores all the bgm the game uses.

Background about the game:
This is a ship game where you choose 1 of 4 nations and play their ships. I play as Japan so I'm dealing with Japanese voices.

My goal is to mod a file called IJN.SPF, which contains all the voices (in .wav) for Japan. 

What I know so far:

I've figured out that there are 154 .wav files in total from using an unpacker tool. These files correspond to these voices in-game:
1. 1-38 Male voices used for all ships (38 total)
2. 39-76 Female voices used for ships ships (38 total)
3. 77-113 Additional male voices for aircraft carriers (37 total)
4. 114-150 Additional female voices for aircraft carriers (34 total)
5. 151-154 4 .wavs that I have no idea what they do, they are distorted voices (4 total)

I used dragon unpacker to find the wav files, and all the offsets and filesizes are given too and i used that as a starting point.

There is a directory, followed by the start of the actual data (.wav files) with no break.

PLEASE IGNORE THE PART IN QUOTES it is pretty much wrong after WRS showed it was encrypted

> Now the hard part, most of the directory is still unknown to me. However, I have figured out a lot already.
>
> The first 3 rows are the header.
>
> Row 1: the same for every .spf file (5C 57 21 5B)
>
> Row 2: bytes 1 and 2 are the same for all voice archives but different for other .spf archives.
>
> Row 3: Always different (I want to say this is the filesize but so far it hasn't matched anything)
>
> 
>
> Entries start at row 4, and have 8 rows.
>
> Row 1: no idea, but the same for every entry (34 9E 71 A8)
>
> Row 2: the first 2 bytes seem to be random, byte 3 is always either 1A, 19, or 18. byte 4 is always 94
>
> Row 3: This row always changes, but there is some order. The first 2 bytes seem to be always different, Byte 3 usually stays on a certain left hex going down the list of entries. (ie. B2, B0, B7, B5, BB, then later A6, A4, A9, AF) Byte 4 starts at F2 but eventually becomes F3 near the end. I think this row is the offset but the numbers have been meaningless so far.
>
> Row 4: always the same (F2 AF 87 C5)
>
> Row 5: always the same (72 DD 2E E9)
>
> Row 6: the row that changes depending on which voice category it is (see above)
>
> Row 7: the first 2 bytes are always the same. the 3rd starts at 83, then 82, 81, 80, and resets when it hits a new voice category. byte 4 is always Cx where x is some number.
>
> Row 8: always the same (DC D8 E6 B3)
>
> 
>
> Example:
>
> 0000002C 34 9E 71 A8
>
> 00000030 E8 E6 19 94
>
> 00000034 B9 29 B2 F2
>
> 00000038 F2 AF 87 C5
>
> 0000003C 72 DD 2E E9
>
> 00000040 76 CD 2B A5
>
> 00000044 5E 42 83 C0
>
> 00000048 DC D8 E6 B3 
>
> 
>
> The entries correspond with the voice categories I just mentioned as well. By comparing Japan's voices archive with another nation's, I learned that there were certain bytes (or maybe rows?) that distinguished which category they were in. From start of directory:
>
> 1-36 contain a row called 76 CD 2B A5 
>
> 37-76 contain a row called 76 CD 2A A5
>
> 77-113 contain 7A CE 28 A1 
>
> 114-150 contain  7A CE 2E A5
>
> the last 4 contain 7A C6 2B A1 
>
> I used this row to determine which category of voices that entry was in.
>
> 
>
> The problem is, I have yet to find any entry that matches with any hint at an offset or filesize. I've looked at this for hours trying to but still nothing. I think I have narrowed it down to rows that have something to do with filesize, but I can't make sense out of these values.
>
> 
>
> The following are the first 4940 bytes I have been analyzing, used with diffchecker. On the left is IJN.SPF (japanese voices) and on the right is KM.SPF (german voices)
>
> Organized by 4-byte rows: https://www.diffchecker.com/pueqei72
>
> Organized by 16-byte rows: https://www.diffchecker.com/ydfu1if0
>
> 
>
> The first 77 entries  (this helped with figuring out the 2B/2A flag):ttps://www.diffchecker.com/4epjfgls
>
> Just checking to see if there were any differences within the first 38 entries: https://www.diffchecker.com/w5hx0x76
>
> 
>
> As you can tell, there are only 2 rows that consistently change. I'm pretty sure these are where the offset values are stored, but the values make no sense, nor do I know how to interpret it. I've tried little endian and big endian, and I've tried adding and subtracting with various other rows and still have nothing.

Sample files to work with: [https://www.mediafire.com/folder/iqd4v36k12er1/nf2](https://www.mediafire.com/folder/iqd4v36k12er1/nf2)
IJN.spf is what i want to mod

KM.spf and option.spf are other spfs to compare to

Offsets can be gotten by running the unknown filetype script in dragon unpacker.

Also extra note:
When I replace a .wav with my own .wav, all the sounds before it are fine but the ones after break. However when I trimmed that custom .wav to be exactly the same size as what I was replacing it worked. (which makes sense if the offset got messed up by inserting my own file while not updating the header)

If anyone can make a script for me please let me know. I can upload the original files if needed. Also if you need more clarifications/pictures i can post them.

Thanks!
## Post #2
- Username: kuu
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Dec 16, 2014 6:43 am
- Post datetime: 2014-12-15T23:34:24+00:00
- Post Title: [HELP] Script needed for unpacking/packing .spf files

delete please
## Post #3
- Username: kuu
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Dec 16, 2014 6:43 am
- Post datetime: 2014-12-15T23:58:17+00:00
- Post Title: [HELP] Script needed for unpacking/packing .spf files

delete please
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2014-12-16T02:10:23+00:00
- Post Title: [HELP] Script needed for unpacking/packing .spf files

tldr; the header is xor'ed with a 32-byte key

i've outlined my thought process as i went   

```
//--- 010 Editor v5.0 Script File
//
// File:
// Author:
// Revision:
// Purpose:
//--------------------------------------


// the header looks like it's been xored
// with some magic bytes

// look at the pattern of bytes, there are lot of
// repeating "rows" of 32 bytes

// first bytes are
// 5c 57 21 5b

// next 32-byte up we have
// 76 ca 2b a5

// then again
// 76 ca 2b a5

// let's this that value

//uint magic = 2771110518L;
//WriteUInt(p, ReadUInt(p) ^ magic);

// that's wrong. ok.

//let's look at the pattern

// 76 CA 2B A5 5E 42 83 C7 DC D8 E6 B3 34 9E 71 A8
// A4 97 19 94 6D 1F BA F2 F2 AF 87 C5 72 DD 2E E9

// what patterns do we have?

// 76 CA 2B A5 5E 42 ?? ?? DC D8 E6 B3 34 9E 71 A8
// ?? ?? ?? 94 ?? ?? ?? F2 F2 AF 87 C5 72 DD 2E E9

// alright.. not too many unknowns

// we need to be looking at for any possible pointers to
// the first wav file, which we know to be 4940

ubyte xor[32] =
{
  0x76, 0xCA, 0x2B, 0xA5, 0x5E, 0x42, 0,    0,
  0xDC, 0xD8, 0xE6, 0xB3, 0x34, 0x9E, 0x71, 0xA8,
  0,    0,    0,    0x94, 0,    0,    0,    0xF2,
  0xF2, 0xAF, 0x87, 0xC5, 0x72, 0xDD, 0x2E, 0xE9
};

uint p = 0;

while(p < 4940)
{
  WriteUByte(p, ReadUByte(p)^xor[p%16]);
  p++;
}

// what we see now if some .wav references!
// a bit more work is required to reverse the actual xor table

// hope it helps!

```
## Post #5
- Username: kuu
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Dec 16, 2014 6:43 am
- Post datetime: 2014-12-16T02:41:52+00:00
- Post Title: [HELP] Script needed for unpacking/packing .spf files

Thank you so much!! Is this a MultiEx script or is it C++? It looks like just C++ to me. Also, why are you using p%16 as the index of the xor table? Wouldn't that mean it would never use the 2nd half the of array and only the first 16 elements?

How would I go about creating a script to do this?

I'm taking a look at this now, so I just need to find the few hidden bytes in the 32-byte key? Do I just have to guess until I get it?
## Post #6
- Username: kuu
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Dec 16, 2014 6:43 am
- Post datetime: 2014-12-16T03:57:06+00:00
- Post Title: [HELP] Script needed for unpacking/packing .spf files

I just tried it with the following C++ code and don't see any references to 4940 (0x134C) yet.

```

using namespace std;

int main() {
	unsigned char xor[32] = { 
		0x76, 0xCA, 0x2B, 0xA5, 0x5E, 0x42, 0,    0,
		0xDC, 0xD8, 0xE6, 0xB3, 0x34, 0x9E, 0x71, 0xA8,
		0,    0,    0,    0x94, 0,    0,    0,    0xF2,
		0xF2, 0xAF, 0x87, 0xC5, 0x72, 0xDD, 0x2E, 0xE9
	};

	unsigned int p = 0;
	unsigned char b; //temporary byte

	ifstream inputfile("IJNoriginal.spf");
	ofstream outputfile;
	outputfile.open("IJN.spf");

	while(p<4940) {
		//read from input file
		inputfile.seekg(p);
		inputfile >> b;
		//b xor key
		b = b ^ xor[p%16];
		//store in output file
		outputfile.seekp(p);
		outputfile << b;
		p++;
	}
	inputfile.close();
	outputfile.close();
}

```


My output is

```
26 7C 57 F2 AC EE EE EE 32 EA 0C BF 8B 15 64 CC
BA 70 5B FE A0 E2 E2 E2 3E E6 00 B3 87 19 68 C0
B6 7C 57 F2 AC EE EE EE 32 EA 0C BF 8B 15 64 CC
BA 70 5B FE A0 E2 E2 E2 3E E6 00 B3 87 19 68 C0
B6 7C 57 F2 AC EE EE EE 32 EA 0C BF 8B 15 64 CC
...

```


Edit:
I still can't get it to work. I also still don't get the concept of encryption or how you found the xor table. 

Could you help with a script for decrypting and re-encrypting? (for the IJN voices, not the KM voices)
Sorry I am not that good at coding 

Please, I would be very grateful!
## Post #7
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2014-12-16T19:02:52+00:00
- Post Title: [HELP] Script needed for unpacking/packing .spf files

sorry, i wasn't very clear - and you spotted a mistake with my code 

(first, i'm using 010 editor - a hex editor with a scriping language similar to c)

so you posted 3 samples files, and 2 are the same size. i'm guessing the header data is xored because there are lot of repeating bytes. i made a guess this was 32 bytes long.

so taking 32 bytes at a time from KM.SPF i built a table of repeating bytes to make this pattern

```
?? ?? ?? 94 ?? ?? ?? F2 F2 AF 87 C5 72 DD 2E E9

```


(where ?? means the pattern is broken)

however, my code did run through 16 of these bytes, but still produced this string ".wavFC_A"!

so maybe the xor isn't 32 bytes, but actually 16.



what i should have shown you next was the filesize:

from KM.SPF i read 4 bytes at a time (8 or so times) and xor that value with the filesize. this gives me these values:

```

```


using the smaller sample (Option.SPF) i can run the xor loop again. if i find the filesize of that file (7717) then we have 1 xor value (or 4 bytes of the table)

so, doing that:

```
// -- code
uint meh[8] = 
{
0x5a6ca5a8, 0x986c0a6b, 0x0dc62cf3, 0xa93c6cc0,
0x955785e4, 0xf3fe93b9, 0xc4ca5d06, 0xe8632f86
};

uint c = 0;
uint val = 0;
while( c < 8 )
{
  val = ReadUInt(c*4) ^ meh[c];
  Printf("%u and %u\n", val, FileSize());
  WriteUInt(c*4, val);
  c++;
}
// -- end code

// we get this:

21885684 and 7717
21885551 and 7717
7717 and 7717
21885674 and 7717
21784099 and 7717
21881234 and 7717
21885684 and 7717
1735193345 and 7717

```


so that third value is correct.

if you open any spf and go to offset 8. if you take 4 bytes as a 32-bit number and xor that with 0x0dc62cf3 you will get the filesize.

as that's a good starting point, have a look in the game itself for that hex string, and you might find the whole xor table.
## Post #8
- Username: kuu
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Dec 16, 2014 6:43 am
- Post datetime: 2014-12-16T19:27:27+00:00
- Post Title: [HELP] Script needed for unpacking/packing .spf files

Can you tell me how i can look into the game? do i need a decompiler, and which one would you recommend if so?

I did a test and ran xor'd the the spf with the 2nd half of the xor table (bytes 17-32) and I got ".wavFC_A" string again except now in the other alternating rows. for example xoring with 1-16 gave the ".wavFC_A" in offsets 10h,30h,50h, etc... and xoring with 17-32 gave ".wavFC_A" in 20h,40h,60h,etc...

And when you say the xor value of 4 bytes, does that mean 4 of the 16 bytes needed for the xor table? Are those the first 4 bytes? i am still very confused about the xor table. the earlier 32 byte table we used is incorrect? do we have to replace that table with the 4 bytes we found just now?

Also a script question, WruteUByte and WriteUInt are built in functions? Does writeuint write the value of 4 bytes into the next 4 bytes of the source that is given as parameter to it?

opening up client in hex editor and searching for 0x0dc62cf3 i did not find anything...

Thanks again
## Post #9
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2014-12-16T20:32:26+00:00
- Post Title: [HELP] Script needed for unpacking/packing .spf files

> Reply from kuu
>
> Can you tell me how i can look into the game? do i need a decompiler, and which one would you recommend if so?

a hex editor is enough to find the rest of this byte sequence. but lets put that on hold.

> Reply from kuu
>
> Also a script question, WruteUByte and WriteUInt are built in functions? Does writeuint write the value of 4 bytes into the next 4 bytes of the source that is given as parameter to it?

yes, and yes   

> Reply from kuu
>
> And when you say the xor value of 4 bytes, does that mean 4 of the 16 bytes needed for the xor table? Are those the first 4 bytes? i am still very confused about the xor table. the earlier 32 byte table we used is incorrect? do we have to replace that table with the 4 bytes we found just now?

sort of.

if you ignore the xor table concept - we only ended up finding 1 magic value (an integer, or 4 bytes) which gave us the filesize.

if you follow what i did to get that value, we can do the same for the first file offset (4940) which will be more helpful to you.

the xor values we get from KM.SPF are:

```
0x941a645c, 0xf2b37201, 0xc587bcbe, 0xe92ece3e

```


and running the loop on Option.SPF we find that the sixth value is 42, which is an offset to a very plain looking value which could be the start of the data.

so we have 2 known xor values which can give us useful info:

0x0dc62cf3 for the filesize, at position 8
0xf2b37201 for the offset, at position 20

for some reason, your code wasn't reading certain bytes correctly (ios::binary??), so here is a slightly different program to print info:

```
#include <stdio.h>

int main(void)
{
  unsigned int file_size_xor = 0x0dc62cf3;
  unsigned int file_offset_xor = 0xf2b37201;

  // gone back to c (sorry)
  FILE* hnl = fopen("Option.SPF", "rb");

  unsigned int offset = 0; // current file pos
  unsigned int first_file = 0; // first file offset

  while ( true )
  {
    // read 32 bytes at a time (8 ints)

    unsigned int buffer[8];
    fread(buffer, 32, 1, hnl);

    // first file:
    if (offset == 0)
    {
      unsigned int file_size = buffer[2] ^ file_size_xor;
      printf("File size: %u\n", file_size);
    }

    // every 32 bytes we have a file header with a file offset:

    unsigned int file_offset = buffer[5] ^ file_offset_xor;
    printf("File offset: %u\n", file_offset);

    // store off the first file offset (which marks the end of header)
    if (offset == 0)
    {
      first_file = file_offset;
    }

    offset += 32;

    // exit the loop when we hit the first file data
    if (offset >= first_file - 32)
    {
      break;
    }
  }
  
  fclose(hnl);  
  return 1;
}

```
## Post #10
- Username: kuu
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Dec 16, 2014 6:43 am
- Post datetime: 2014-12-17T03:37:09+00:00
- Post Title: [HELP] Script needed for unpacking/packing .spf files

I am using 010 editor now

when I xor'd the first 32 bytes of IJN.spf with 
0x5b214410, 0x9921ebd3, 0x0c8bcd4b, 0xa8718d78,
0x941a645c, 0xf2b37201, 0xc587bcbe, 0xe92ece3e

the key that you used to find the offset, I got

4C 13 00 00 4C 13 00 00 D4 18 38 00 4C 13 00 00
0C D2 00 00 4C 13 00 00 4C 13 00 00 4C 13 00 00

which seems right since 4C13 is the start of the offset, but why is it appearing in so many places?

and I still can't find any hex references in the main client
## Post #11
- Username: kuu
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Dec 16, 2014 6:43 am
- Post datetime: 2014-12-17T06:06:32+00:00
- Post Title: [HELP] Script needed for unpacking/packing .spf files

Okay so I found the row that stores the size of each wav file! 

Edit: I found the row with number of files too! It is stored in row 2 of the header.

Now we have filesize, .wav size, .wav offset, and ".wavFC_A" or ".wavFC_O" string. However there are still lots of unknowns. 
Row 1 in header is missing
Row 1, 6, 7, 8 in each wav description is still missing.

Do  you think what i have found so far is enough to recreate a custom .spf file with my own voices? Do you think there is a possibility row 6,7, and 8 are a continuation of row 5? Because maybe FC_A is cut off and it is actually a 16-byte string?

I made a new script and all the .wav sizes and offsets are correct.



```
//--- 010 Editor v5.0.2 Script File
//
// File:
// Author:
// Revision:
// Purpose:
//--------------------------------------
//
//first try xoring km.spf with filesize of km.spf 21,885,684->01 4D F2 F4
//BUT turn it around after getting each xor key
//run it on option.spf
//whatever matches the filesize is the correct row (3rd)
//
//next try xoring km.spf with fileoffset 4940->134c0000
//uint meh = 0x0000134c;
//now we have 8 new keys
//turn each key around
//run it on first 8 rows of option.spf
//look for first offset of option.spf (6th row)
//
//so far
//row 3 filesize 0x0dc62cf3
//row 6 file offset 0xf2b37201
//
//now let's try looking for size of first .wav in km.spf
//100652 -> 00 01 89 2C
//uint meh = 0x0001892c;
//turn around all 8 xor key rows
//0x5b20de70, 0x992071b3, 0x0c8a572b, 0xa8701718,
//0x941bfe3c, 0xf2b2e861, 0xc58626de, 0xe92f545e
//run it on ijn.spf because easier
//found!! 84076 on row 5 (size of 1st wav)
//row 5 wav size 0x941bfe3c
//
//those are all the rows that change
//lets combine it with the xor values that got .wavFC_A earlier
//row 7 0xdcd8e6b3
//row 8 0x349e71a8
//
//lets create a new loop that decrypts the 3rd row in header and every 2nd, 3rd, 4th, 5th row in each file description

uint filesizekey = 0x0dc62cf3; //filesize
uint row2 = 0x941bfe3c; //wav size
uint row3 = 0xf2b37201; //wav offset
//uint row4 = 0xdcd8e6b3; //".wav" string
//uint row5 = 0x349e71a8; //"FC_A" string

//".wavFC_A" string
uint wavstring[8] = {
  0xDC, 0xD8, 0xE6, 0xB3, 0x34, 0x9E, 0x71, 0xA8
};

uint val = 0;

val = ReadUInt(2*4) ^ filesizekey;
WriteUInt(2*4, val);

//c=3 is beginning of first file description (skip first 3 rows)
uint c = 3;
uint p = 0;
val = 0;
uint r2;
uint r3;
uint r4;
uint c2 = 24;

while( c < 1232 )
{
  r2 = c+1;
  r3 = c+2;


  val = ReadUInt(r2*4) ^ row2;
  WriteUInt(r2*4, val);

  val = ReadUInt(r3*4) ^ row3;
  WriteUInt(r3*4, val);


  p = 0;
  while ( p < 8 ) {
    r4 = c2 + p;
    WriteUByte(r4, ReadUByte(r4) ^ wavstring[p]);
    p++;
  }

  c+=8; //move 8 rows ahead
  c2+=32;
}

```
## Post #12
- Username: kuu
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Dec 16, 2014 6:43 am
- Post datetime: 2014-12-17T12:04:53+00:00
- Post Title: [HELP] Script needed for unpacking/packing .spf files

I successfully modded the file. Thanks for all the help WRS!
