## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-08T01:10:32+00:00
- Post Title: Cyberberbykes/Shadow Racer VR (BIN, encrypted files?)

I know I have made several requests in the past, but this one is more of professional assitance as it isn't a hard format.

I have already proven that Cyberbykes bypasses internal files for extracted ones making modding relatively simple. I got this game WAAAY back in my childhood and even though it isn't a super game was fun all the same to fiddle around with.

What has been successfully extracted is the text files for enemies, turrets, etc as well as the background bitmaps and their list text file. Other successful extracts are the mission text files and etc. HOWEVER In the file: POLY.BIN (provided) there are two text LST files which are corrupted (PRIZE.LST and POLY.LST) and all PLY files (simple polygonal 3D files) are also corrupted.

Tell me what you find. It is an old game so it may not be very difficult to crack.

Darkfox
[Poly.rar](https://xentaxbackup.github.io/file/1048_Poly.rar)
## Post #2
- Username: Matsy
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Aug 21, 2006 3:12 pm
- Post datetime: 2007-02-08T07:06:38+00:00
- Post Title: Cyberberbykes/Shadow Racer VR (BIN, encrypted files?)

Okay. I found out something.
Might not be of a large use, but mkay

After the file name, Like the first, Arrow.ply
You see this:

0100 | 2000 | 0000 | 4414 | 0000 | 4706 | 0000

The first 3 longs, are probably some weird version number, I dont know
But the second, long, 4414, has a value of 5188, which is the position of the file data, and the long after that, 4706 has a value of 1607, which'd be the file length.

So 12 bytes after the file name, there is the Position, and the length.


Which also works out for the next of the files.
## Post #3
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-08T07:23:13+00:00
- Post Title: Cyberberbykes/Shadow Racer VR (BIN, encrypted files?)

Indeed.

Perhaps the first three determine how the file is processed or file type? Not sure. But I think that is what Elbereth got. The problem is though that the files other than ENEMY.LST and MOBILE.LST are possibly using a form of compression. Given the age of the game it could possibly be a uncomplex form and perhaps used just to make the game smaller, computers at the time did not have 30GB+ of space, not cheap ones anyways.
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-02-08T07:28:33+00:00
- Post Title: Cyberberbykes/Shadow Racer VR (BIN, encrypted files?)

Well, if it's of any help, here's a MexScript for it:

```
# By Mr.Mouse
# http://www.xentax.com
ImpType Standard ;
Get FC Long 0 ;
For T = 1 To FC ;
GetDString FN 16 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Log FN FO FS FOO FSO ;
Next T ;

```


And the files in question are attached.
[lstfiles.zip](https://xentaxbackup.github.io/file/1049_lstfiles.zip)
## Post #5
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-08T07:36:06+00:00
- Post Title: Cyberberbykes/Shadow Racer VR (BIN, encrypted files?)

Thats as far as Elbereth got. If you look at POLY.LST and PRIZE.LST there is somthing screwy going on with them as compared to ENEMY.LST and MOBILE.LST.

I think... well... obviously they used some form of compression. Either common or of their own makeing is uncertain to me.

Mhm mhm

If not a compression could be an encryption scheme. But it would seem pointless to encrypt a few a few and leave others wide open. So far I believe all PLY files use this encryption/compression as when I extract them the game crashes where the object would be. (And much sooner with PRIZE and POLY LST files)
## Post #6
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-09T09:33:31+00:00
- Post Title: Cyberberbykes/Shadow Racer VR (BIN, encrypted files?)

In the files:

POLY.LST
PRIZE.LST

and the PLY files

Can it be confirmed if indeed they are compressed or use a kind of encryption?
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-02-09T10:30:07+00:00
- Post Title: Cyberberbykes/Shadow Racer VR (BIN, encrypted files?)

This might be a nice task for people like john_doe or Deniz Oezmen. Perhaps they can reverse engineer the executable to see what's going on. you might want to PM them about it. The game can be downloaded at the Home of the Underdogs site .
## Post #8
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-09T10:41:19+00:00
- Post Title: Cyberberbykes/Shadow Racer VR (BIN, encrypted files?)

You know that is a bright idea. Thanks.
## Post #9
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-02-11T18:20:00+00:00
- Post Title: Cyberberbykes/Shadow Racer VR (BIN, encrypted files?)

> Reply from Mr.Mouse
>
> Perhaps they can reverse engineer the executable to see what's going on.
Yeah that's the best approach for encryption/compression.
## Post #10
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-11T20:43:23+00:00
- Post Title: Cyberberbykes/Shadow Racer VR (BIN, encrypted files?)

Yeah, it'll have to wait till the beginning of March. Both have a tight schedule for now.
## Post #11
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-02-11T20:49:53+00:00
- Post Title: Cyberberbykes/Shadow Racer VR (BIN, encrypted files?)

same here. exams til end of February...
## Post #12
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-03-06T11:39:23+00:00
- Post Title: Cyberberbykes/Shadow Racer VR (BIN, encrypted files?)

Some updates with current working theories ...

- The files are most probably organized in big-endian notation.
- There might be several compression techniques used in the extracted files. If that is the case, the first int32 probably indicates the method used to compress the file. The following observations apply to those files starting with 0x00000001.
- Starting from offset 4, there is a large area consisting of mostly zeros. The format of this area might be a list of three-byte-values. The fact that this area is almost exactly large enough to keep 256 of these triplets (i. e. at least 768 bytes, but eventually two bytes more) leads to the assumption that each of those three bytes maps to one 8-bit value. If we assume these to be ASCII codes, we can see that only those ASCII codes that have a relevance in text files are assigned a non-zero value. This leads to the conclusion that the area might be a histogram of the character frequency distribution in the original file.

Now, since we already have a histogram, entropy coding naturally comes to mind. Does anybody have a working (let's say) Huffman framework to test this theory?

The following is a list of the ASCII character frequencies (as interpreted above) of poly.lst (only non-zero values displayed). If you look closely at it (and compare it to the known uncompressed files), you will see that this is too good to be wrong. 

```
09  <Tab>  10
0A  <LF>  141
0D  <CR>  141
20  <Sp>  208
22  "     616
27  '       3
28  (       1
29  )       1
2B  +       1
2C  ,     623
2D  -      39
2E  .     110
2F  /      18
30  0     293
31  1      87
32  2      38
33  3      28
34  4      30
35  5      67
36  6      23
37  7      21
38  8      20
39  9      12
3A  :       4
3C  <       7
3D  =       4
3E  >       7
41  A      16
42  B      27
43  C      19
44  D      13
45  E       7
46  F      21
47  G       7
48  H       2
49  I       5
4A  J       1
4C  L      19
4D  M       9
50  P      19
51  Q       3
52  R      25
53  S      38
54  T      12
57  W      14
5F  _      27
61  a     117
62  b      28
63  c      67
64  d      90
65  e     271
66  f      24
67  g      60
68  h      61
69  i     160
6B  k      18
6C  l     218
6D  m      26
6E  n     164
6F  o     136
70  p     147
71  q      11
72  r     181
73  s      84
74  t     148
75  u      61
76  v      25
77  w      43
78  x       4
79  y     118
7A  z       1
```
## Post #13
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-03-08T05:53:47+00:00
- Post Title: Cyberberbykes/Shadow Racer VR (BIN, encrypted files?)

When playing Cyberbykes I came across an oddity. I noticed there are some tmp and a CYBER.EXT that is loaded. Not sure if there is any relevence there but it seemed a bit odd. I haven't been able to find this EXT file though.
## Post #14
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-11-08T06:13:36+00:00
- Post Title: Cyberberbykes/Shadow Racer VR (BIN, encrypted files?)

I realize it has been a long time but I have made a recent discovery:

Ok, I have managed to get a partially decrypted poly.lst file using DosBox's memory dump. It is messy but is enough to make out what it is. It's an encrypted script telling what does what to some extent.

The full Memory Dump can be found here: [http://www.sendspace.com/file/nktyw2](http://www.sendspace.com/file/nktyw2)
[PartiallyDecryptedPolyLST.rar](https://xentaxbackup.github.io/file/1730_PartiallyDecryptedPolyLST.rar)
