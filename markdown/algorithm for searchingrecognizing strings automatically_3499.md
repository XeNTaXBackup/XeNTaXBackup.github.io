## Post #1
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-20T12:11:22+00:00
- Post Title: algorithm for searching/recognizing strings automatically?

Just wondered if there is a way to scan a file for strings, i.e. recognizing "this is not some random binary data, this is a string", just like humans do
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-20T13:26:35+00:00
- Post Title: algorithm for searching/recognizing strings automatically?

the problem is the charset because a wider charset results in tons of false positives.

for example the english charset is basicly composed by the first 127 bytes of the ascii table with the exclusion of some of the first bytes so it's good because you can scan a casual sequence of bytes and saying that it is or it isn't a string enough easily (obviously a string is ever composed by a byte between 1 and 255 chosed by who created it so it's not possible to be sure at 100% of the result... that's logical).

but in other languages are used also other chars, for example the accented letters used in italian, french, spanish and german which are all bytes above 128 and the conseguence is a major number of false positives which become more if we consider the asian languages (practically any byte).

another important thing is the length of the string which should be at least of 4 bytes to decrease the false positives caused by 32bit numbers stored in the file.

if you are interested I worked on this stuff some months ago just for a project of strings recognization.
for avoiding false positives and moreover for allowing the reintroduction of the strings (for example for translating an executable in another language using a new string loooonger than the original) I added the scanning of the assembly instructions in the executable and the checking of the strings linked in these instructions (like "PUSH offset", "mov [eax], offset" and so on).
the tool is called exestringz: [http://aluigi.org/mytoolz.htm#exestringz](http://aluigi.org/mytoolz.htm#exestringz)

obviously it can be used also with the blind binary scanning (-b) of the bytes inside a file without considering the assembly instructions.
hope it helps
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-20T13:49:29+00:00
- Post Title: algorithm for searching/recognizing strings automatically?

Good point.
You could also use some language statistics to match if it is english text and so on, but this obviously also only works well for bigger texts.
I wonder if there is a neural approach to that
## Post #4
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2009-05-20T15:02:09+00:00
- Post Title: algorithm for searching/recognizing strings automatically?

There's a UNIX command called "strings" (which has cygwin and probably even native win32 ports) which does exactly that. It's not foolproof either, but since nothing in this area can really be foolproof (because of codepages, encodings, markings in high-bits, etc.) it's better than nothing.

I use it to quickly "scan" over it's output to see if there's anything interesting in a file or not.

-Darkstar
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-05-20T22:03:31+00:00
- Post Title: algorithm for searching/recognizing strings automatically?

MexScan is a little app I created in 2000 to scan a file for hints that it is an archive of some sorts. I also had a routine searching for strings (and estimate the distance between strings: the program recognizes a certain pattern in the distance between strings, such as archives that store filenames).

It's easy to find standard ASCII strings, just check for repeating instances of the appropriate ascii codes (.e.g. ASC('a') through ASC('z'), ASC('A') through ASC('Z') etc. )  


 PC_Xentax_Mexscan_2000.zip
(29.18 KiB) Downloaded 36 times
