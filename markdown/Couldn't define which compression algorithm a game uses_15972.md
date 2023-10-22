## Post #1
- Username: fygonzalo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 02, 2016 3:25 pm
- Post datetime: 2017-03-08T17:17:26+00:00
- Post Title: Couldn't define which compression algorithm a game uses

Hello guys.

I am working to reverse the protocol of a mmorpg. I have already patched the encryption and now I am facing a compression algorithm that I could not define which one of the standars is (if is a standard).

I am almost sure that is a LZ77 variant (maybe a propietary one) but still didn't found the correct one.

The game doesn't compress anything but decompress packets received from server, so I am working over the decompression process.

I have already tried:
- Extensions for IDA PRO to find algorithm constants - No result
    Those extensions found parts of deflate, lzx, zinflate, zlib, etc, etc, but none of those fits what the decompression method does.
- Already tried compress and decompress a known stream using Deflate, Gzip and Zlib but the results are far of what the game does.

What I already know:
- The decompression algorithm uses two-bytes pointers that defines the offset and length of bytes from the already wrote bytes on the output stream to copie to the actual posicion of output stream.
- Those two-bytes aren't just offset-length, they work at bit level. But the offset bits always defines how many positions must go back from the actual position of the output stream to find the "uncompressed" bytes.
- The decompression only works over the input stream and output stream, there isn't another structures involved.
- As I saw, the decompression process is necessary sequential, there is no way to find a pointer without analyzing the pointers behind.
- The input stream that I analized starts with 2 bytes that indicates to the decompression algorithm how to start.

The algorithm on pseudocode:
I am gonna try to explain easly as I can. If you wanna see the hex rays output here is it: [https://gist.github.com/FYGonzalo/a4118 ... 3d5aa48e6d](https://gist.github.com/FYGonzalo/a4118d35620d48bacea2253d5aa48e6d)
Later I will describe the process of a real input stream decompression.

First of all the algorithm reads the first byte.
If it is bigger than 0x11 copies plain bytes from input stream to output stream, and later do a operation that I didn't analized yet.

Now, after that, reads two bytes: "firstByte" and "secondByte".
If firstByte is less than 0x10 then it means that we gotta copie plain bytes from input stream to output stream. Depending on the value of firstByte and later of secondByte we will know how many bytes we should copy.

After that it enters on a while loop.
It reads again a pair of bytes: "firstByte" and "secondByte".
Now if:
------------------------------------------------------------
firstByte is bigger than 0x40, it indicates many things:
Three of it bits are used to indicate part of the offset to go back. For example, on 4C it is: 0100 1100
But its not that all, it adds 1 to that value and also adds the result of (secondByte * 8 ). This operation indicates the offset of bytes to go back on the output stream to find the uncompressed value.

The three bits of the left indicates the number of bytes to copy: 0100 1100.
But not as plain, the number of bytes to copy is default 2 added to those 3 bits minus 1.
2 + 2 (010) - 1. = 3.

Also, the two bits of the right indicates if there are plain bytes to copie from the input stream: 0100 1100.
In this case we don't need to copy anymore, so we jump to the start (where all begins) and continues the same process.

If there is at least 1 byte to copy then it copy it and go back to the start of this loop
--------------------------------------------------------------
firstByte is less than 0x20 it breaks the loop and end writting the output stream and ends the process.
--------------------------------------------------------------
firstByte is equal or bigger than 0x20 (and obviously less than 0x40).
In this case it changes the mean of the pair.
Now uses the secondByte to get the offset and firstByte to get the number of bytes to copy.

The offset is the 6 bits of the left of secondByte + 1.
The number of bytes to copy is represented by the right 5 bits of firstByte:

An example is: (2A, C8)
2A = 0010 1010 => 0010 1010
C8 =  1100 1000 => 1100 1000

And, the last two bits of the right of secondByte means the number of plain bytes to copy from the input stream to the output stream (same as the two right bits of firstByte when firstByte is bigger than 0x40).

** In this case, when firstByte is bigger than 0x20, the next byte to the par (in the input stream) isn't used. The algorithm jump that position to the next.
---------------------------------------------------------------


That is not the full algorithm but the most descriptive part that may help to find the standard used.

---------------------------------------------------------

Here you can see the process of decompression of a real packet.
[https://imgur.com/a/kuQkl](https://imgur.com/a/kuQkl)


Sorry but english is not my native language. If you need I will traduce also the text of imgur.

---------------------------------------------------------

Thats all information I found analizing the algorithm with ida pro.

Additional information: The game is made by a taiwan company and released to pc on 2006.


Thank you all!.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2017-03-11T22:48:38+00:00
- Post Title: Couldn't define which compression algorithm a game uses

Can you post some samples? i'm not transcribing hex data from screenshots
## Post #3
- Username: fygonzalo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 02, 2016 3:25 pm
- Post datetime: 2017-03-12T04:28:54+00:00
- Post Title: Couldn't define which compression algorithm a game uses

LOL, just 0x2c6 bytes, its nothing man!

Anyway, already found the algorithm. Its LZO. The game is on PS3 and a friend was searching and found that it works on PS3 too so I searched a bit and works.
Here you can see how it works [https://www.kernel.org/doc/Documentation/lzo.txt](https://www.kernel.org/doc/Documentation/lzo.txt) 
Also, the source code is online on [http://www.oberhumer.com/opensource/lzo/](http://www.oberhumer.com/opensource/lzo/)

Now I am trying to implement it on C# (using p/invoke) like the native DeflateStream and GZipStream of .NET.
