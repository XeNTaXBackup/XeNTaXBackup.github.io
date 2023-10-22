## Post #1
- Username: patr0805
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 09, 2012 4:48 pm
- Post datetime: 2014-02-22T11:56:29+00:00
- Post Title: A strange variation of CG GIM image that I cant decode

I am doing a translation project for the game called Little Busters! for PSP (close to completion), but I am having trouble with some GIM files (image files). Some of the GIM's work, however sometimes a GIM file appears that neiter puyotools or GimConv can handle (Those that works and those that doesn't are a little different as discribed below).
I know its a GIM file because it starts with: MIG.00.1PSP, though to be exact, its a little different and written like this:

[integer equals 16] [integer equals 131792] [MIG.00.1PSP, but where a 00 HEX is placed between each hex byte]
like this: 10 00 00 00 D0 02 02 00 4D 00 49 00 47 00 2E 00 30 00 30 00
2E 00 31 00 50 00 53 00 50 00 00 00

Each of the GIM files starts with these two integers values (that is to say, all those I am having trouble with). I have allready tried removing these two integers and also tried replacing M(00)I(00)G(00).(00)0(00)0(00).(00)1(00)P(00)S(00)P(00), with simply MIG.00.1PSP, but that just ended up making GIMConv saying: wrong chunk data.

Also I have tried analysing the file with signsrch and TrID to look for compressions of some sort, but signsrch finds nothing and TrID only finds: "100 .0% (.) LTAC compressed audio (v1.61) (1001/2)"

Also, I have found that after MIG.00.1PSP, in those I can convert, there is an integer value equals the size of the file minus 16. When comparing two image files I cant convert, I find that what should have contained this integer is not there. Simply speaking, about 100+ bytes are the same in both the files I compared and yet they have a much different size. This make me believe that this may not be a GIM file at all or that some strange compression/encryption I cant figure out is at work. What kind of compression could cause MIG.00.1PSP to become paired with zeros?
^It seems that bytes are diffferent when comparing files of different resolution (I can compare them with the png's of the PC version).

Also, I have found that HEX pairs such as 0C 01, 0D 01 etc. appears randomly everywhere.. everything mostly consists of a hex followed by a 01 or 00. When what I believe is the start of the pixels, this starts ranging between 0-27 (not the case with the image files I am able to convert).. 

Update: I have found that 0C 01 can be extending by 0C 01 infinite times without damaging the file, but removing the 0C 01 results in gamecrash.

Below is the file called: black.gim


Below is a random CG: 


Below is a standard gim file for refference (a file I can convert and view just fine).




Update: I am starting to believe this is some kind of lz compression, but I haven't figured out which one yet. Tried lzss, lz01,lz00,lz10,lz11. It seems to me that it begins with a 10 byte like lz, it makes MIG.001.PSP become seperated by 00, due to the compression relying on value, key pair, where I believe the key 0 means that values should be directly send to the output.

Since the game is copyright, I can't upload a sample to this website, however tell me if I am not being informative enough.

I'll be really happy if anybody could give me some input or lead:)
