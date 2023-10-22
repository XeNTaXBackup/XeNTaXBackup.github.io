## Post #1
- Username: PowerBlade
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jul 19, 2007 3:37 am
- Post datetime: 2007-07-24T15:33:53+00:00
- Post Title: ZLIB RFC 1951 problems..

Hey

I have the following file which I'm 100% sure is compressed using ZLIB, but its lacking the headers and footers and checksum, and thus is a RFC 1951 compressed file.
I tried to decompress it using the ZLIB library, but to no help. Even when setting the windowbits to -MAX_WBITS, I only get the first 4 bytes decompressed and then i get an error "invalid distance too far back"
I also tried with .NET's DeflateStream with a little more luck! The only problem is I'm missing data in the result. There is some 0x00 bytes in the middle of the names and such making the data hard to read.

Anyone have some suggestions on how to decompress this data properly? Any help would be nice, though i would prefer a way to do it in C/C++.

(I zipped the file because the .bin extension is not allowed, so remember to extract it first!)
[packet.zip](https://xentaxbackup.github.io/file/1284_packet.zip)
## Post #2
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-07-24T16:41:29+00:00
- Post Title: ZLIB RFC 1951 problems..

Could it be the file is compressed with Deflate64?
It's almost identical to the standard deflate but with some improvements.
## Post #3
- Username: PowerBlade
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jul 19, 2007 3:37 am
- Post datetime: 2007-07-25T04:06:04+00:00
- Post Title: ZLIB RFC 1951 problems..

Do you know of any Deflate64 libraries?
A search on Google didn't yield any interesting stuff for me..
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-07-25T05:16:48+00:00
- Post Title: ZLIB RFC 1951 problems..

7-zip should support it.
## Post #5
- Username: PowerBlade
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jul 19, 2007 3:37 am
- Post datetime: 2007-07-25T05:45:36+00:00
- Post Title: ZLIB RFC 1951 problems..

I tried 7-zip, but it packs the file with a zip header.
Im looking into a way to decompress the raw bytestring
## Post #6
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-07-25T05:52:19+00:00
- Post Title: ZLIB RFC 1951 problems..

So get 7-zip source code and have a look at the deflate64 functions.
## Post #7
- Username: PowerBlade
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jul 19, 2007 3:37 am
- Post datetime: 2007-07-25T06:37:22+00:00
- Post Title: ZLIB RFC 1951 problems..

I also tried that. I've spent hours looking through the 7-zip source code to figure out how it works.
It's so big and confusing.

I figured out the handling is done in DeflateDecoder.cpp, where there is a CCoder object in the namespace NCompress::NDeflate::NDecoder. You have to feed it by an object derived from the ISequentialInStream interface..

The code is so confusing and i haven't found any documentation on it.

Isn't there a simple implementation like ZLIB or an application which can read a raw stream of data?
## Post #8
- Username: PowerBlade
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jul 19, 2007 3:37 am
- Post datetime: 2007-07-25T16:57:20+00:00
- Post Title: ZLIB RFC 1951 problems..

I found a trial version of the Xceed library which can extract Deflate64 encoded data. 
I receive exactly the same result as with the normal deflate function (I tried both using the library)
So i guess its not Deflate64 encoded.

1 thing i noticed is, i can only decompress the data if i choose NOT to decompress it in a single block, not matter what function i use.

It has to be something about the decompression which is the problem. The final result has weird repeating holes in the textlines. If a word eg. "Test" is shown as "T.st" (where . is a 0x00) its shown as that everywhere in the file.

Any ideas?
## Post #9
- Username: PowerBlade
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jul 19, 2007 3:37 am
- Post datetime: 2007-07-26T09:29:52+00:00
- Post Title: ZLIB RFC 1951 problems..

Some more info..
Processing the file with ZLIB 1.1.4 lets me extract the same amount of information as the .NET DeflateStream object.
After digging into the source code, the problem lies in the distance bits.
The distance bits is used to point back into the result for letters that are already extracted.
In the packet, there is some distance bits which are very big. 1125, 26070, 1177, 26198 and similar. They point the x number of bytes back in the result. Because the result is not big enough, ZLIB 1.2.3 throws up an error. ZLIB 1.1.4 just try to read the memory, and gets some 0x00 data.
Apart from the distance bits, the rest of the data is fine. 
So did anyone hear about any deflater which does like this? And why would it point so much back into the memory?
## Post #10
- Username: juskrey
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 01, 2008 5:50 pm
- Post datetime: 2008-04-01T11:48:38+00:00
- Post Title: ZLIB RFC 1951 problems..

Though last bytes are looking normal for deflate, first bytes of your file are really strange.
Are you sure you havent missed the beginnig of the compressed block?
If no, first bytes seem to be be encrypted.
