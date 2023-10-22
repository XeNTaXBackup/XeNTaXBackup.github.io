## Post #1
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-11-03T09:58:33+00:00
- Post Title: CryptoSys API

I very searched for a tool that can compress data with coustom options (for example compress a plain text only with deflate method or only with gzip , base64 , lzss , ... )
I found only an interface with this ability :
[http://www.cryptosys.net/compression.html](http://www.cryptosys.net/compression.html)
but when i downloaded demo of it , it contains only samples and no any usable software !
what is your idea about this interface , do you know any solution for my request ?
-----------------------------------------------
Features :
Interfaces for VB6/VBA, C/C++, C#, VB.NET and VBScript/COM/ASP programmers.
Block cipher encryption with AES, DES, Triple DES and Blowfish algorithms.
Key wrap with AES and Triple DES.
Galois/Counter Mode (GCM) authenticated encryption with AES (AES-GCM) and GMAC authentication.
SHA-1, SHA-224, SHA-256, SHA-384, SHA-512, MD5 and RIPEMD-160 message digest hash algorithms.
HMAC message authentication.
CMAC message authentication (OMAC1).
Data compression and decompression algorithms.
Password-based key derivation function (PKCS #5 PBKDF2).
Secure random number generator compliant with FIPS-140-2 and X9.31/X9.17.
PC1 stream cipher encryption compatible with RC4.
CRC-32 checksum functions
Carry out encryption and hash digest operations in one-off manner or in repeated blocks.
Input data as a hex string, byte array or directly from a file.
Built-in hexdecimal and base64 encoding and decoding functions.
Small executable footprint.
Runs on any Win32 operating system: 95/98/NT4/2K/XP/2003/Vista. X64 version also available.
Independent of Microsoft Cryptographic API.
Does not use COM or Active-X or require registering with RegSvr32 to use (except optional ActiveX interface).
A Linux Version is available separately.
Thread-safe operation in all modes.
Automatic self-checking of software integrity and key functions on start up.
------------------------------------------------------------
[http://www.cryptosys.net/](http://www.cryptosys.net/)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-05T20:43:44+00:00
- Post Title: CryptoSys API

No, but would be interested to know if someone has such a tool. I use a number of compressors whenever I want to compare (e.g. WinACE, 7z, RAR), but if there's one tool that does a whole lot it would be appreciated.
## Post #3
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-11-09T12:44:49+00:00
- Post Title: CryptoSys API

I bet , you never saw fountain of compression tools ! , hundred compression methods plus executable and source ! follow the sublinks too !
[http://cs.fit.edu/~mmahoney/compression/text.html#6445](http://cs.fit.edu/~mmahoney/compression/text.html#6445)
whether anyone has ability to make an ATOMIC compressor ?
is it possible to combine these individual exes and sourcecodes to montage the comprehensive compressor ?
for example by batch files !
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-10T11:43:00+00:00
- Post Title: CryptoSys API

in the last days I have practically seen any compression algorithm existent and the conclusion is that... it's all a chaos.

practically the algorithms that have better results in the benchmarks "seem" to be those of the PAQ and PPMd family but the problem is that they are not a standard but are continuos evolutions and obviously their performances change due to the type of input file.
imagine them like a new program each time and not a new version, because the subsequents are incompatible with the previouses.

then the majority of the compression algorithms are implemented to work as file2file and so they can't be used for doing a memory2memory job like a library (zlib, lzma, bzip2 and so on) except if you modify them manually.
for example the ppmdi1 algorithm is implemented as file2file but it's officially used in the ZIP file format (method 98), that's why I needed to convert it to memory2memory for using it in quickbms.

yesterday I used 7-zip to compress a set of files as a test and the result was that the lzma algorithm compressed them better than the ppmd one (both at maximum level), so if you are looking for the best compression... good luck :)

while I have not understood what is the reason of having all of them collected in one tool.
I see this useful only for their decompression mode and indeed it's exactly what I did with quickbms (later I will write a post about a new function of the tool that I'm sure many of you will like) but I don't see it useful for the compression mode.
## Post #5
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-11-11T08:11:52+00:00
- Post Title: CryptoSys API

so kudos Luigi Auriemma
your comments are definitive , you disabuse me , because my expert about prgramming and such algorithms is very low !
i thought each of them is individual ! but i know the truth now !
i propound this subject because i pry why the "78 9c" is repeated in most of  game archives , that is the header of deflate method (if i am right) , but when i decided to compress data in famous archiver with various option none of them can't generate "78 9c" header (why ? please guide me) and my search reached to this chaos !
realy thanks ...
anyway i have a request that you add the ability of data compression to next versions of QBMS !
1: useful for repacking 
2: assay for recognizing and comparsion of methods !
3: if you have the source code for comperession algorithms , why should left that great potential frustrated ?
anyway you know better than me ! thanks a lot ......
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-11T11:37:46+00:00
- Post Title: CryptoSys API

practically zlib (positive windowbits) and deflate (negative windowbits) are the same thing/algorithm, the difference is that zlib adds this 2 bytes header to the compressed data containing some informations like the level of compression used and so on which are stored in these 16 bits (you can check them in the zlib source code).

now the problem is that other exist some custom fields for applying the compression to a data and they are visible in defalteInit2 in zlib.h:
- level
- method,
- memLevel,
- strategy

and obviously the result changes a bit varying them.
and it's not finished yet because the deflate algorithm can be implemented in various more and less optimized ways, that's why the same data compressed with the zlib library is bigger than the one compressed by 7-zip or winzip.

but this is not a problem because any of the compressed data obtained with these implementations and custom parameters is EVER compatible with the decompression function, so doesn't matter what you use because it can be decompressed perfectly EVER.

about quickbms, the recompression is absolutely out of question for various reasons included the fact that in many implemented algorithms doesn't exist a compression function (for example those reversed by me and others) or some of them have been converted from file2file to memory2memory and I have just removed any reference to the compression functions for making them smaller and easier to handle.

the recognization is an hard thing, you can read about it in this post that you already know [viewtopic.php?p=33056#p33056](http://forum.xentax.com/viewtopic.php?p=33056#p33056).

for the third question, all the source code is public and obviously it's in quickbms so you can find anything I have used in src\compression
## Post #7
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-11-11T14:20:57+00:00
- Post Title: CryptoSys API

thanks for your instructions , excuse me if i bother you !
