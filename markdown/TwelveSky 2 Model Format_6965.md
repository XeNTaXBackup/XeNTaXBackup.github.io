## Post #1
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-07-12T23:12:17+00:00
- Post Title: TwelveSky 2 Model Format

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-13T12:57:20+00:00
- Post Title: TwelveSky 2 Model Format

Weird format.

There are a couple of dwords (variable amount, from 2 to 4), followed by a dword that indicates the number of bytes in the following section, and then you come across that many bytes.

And the pattern repeats until the end (there are 8 bytes of nulls at the end) o.O

Maybe there is some significance in those unknown dwords, but nothing looks obviously like face indices. The sections could even be encrypted I suppose.

I wonder if mobject and sobject are the models lol (though there wasn't much other things in the folder..). Maybe multiple files are required to build the model.
## Post #3
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-07-14T20:46:55+00:00
- Post Title: TwelveSky 2 Model Format

Try download the game, maybe this can help, cause i see another files but size are 250 to 300MB
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-14T22:03:55+00:00
- Post Title: TwelveSky 2 Model Format

I don't see any other files (unless I accidentally deleted it).
## Post #5
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-07-15T07:08:15+00:00
- Post Title: TwelveSky 2 Model Format

ummm well I downloading game for try test some files, really graphics are very good, hope see some progress in it.
## Post #6
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-07-20T00:32:06+00:00
- Post Title: TwelveSky 2 Model Format

Yes all the game files samples i Post are very good   .
This its special, and have very good stuff but sounds complicated to decrypt.
## Post #7
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-07-20T02:30:02+00:00
- Post Title: TwelveSky 2 Model Format

> Reply from finale00
>
> I don't see any other files (unless I accidentally deleted it).mate you don't test it? I analize the files but can't be found any information about that :S

SOBJECT files.

```
00000020 22 4D 52 24 8D 4A A8 CE 5A 96 A4 84 A8 54 22 92 B9 94 A9 0C 45 85 4C 29 CD A5 42 99 67 32 0B 9D "MR$.J..Z....T".....E.L)..B.g2..
00000040 B5 3C 1E 32 97 79 96 39 73 E6 59 FC EE 73 7A 7A DF CE FB FF FA EE FF 7B 3D 97 EB 7D 7F BF EB B8 .<.2.y.9s.Y..szz.......{=..}....
00000060 AF FB FE DC 67 7F D6 5E 6B EF 7D EF D6 BC 21 F4 9F F9 47 24 55 5A 0B 7C 75 C0 ED 3E 43 39 F3 8A ....g..^k.}...!...G$UZ.|u..>C9..
00000080 A7 57 EC E3 F9 A9 3B 53 89 F3 85 E5 D4 2A 2D 93 34 9B 1D 5A 34 A5 6D 3A D5 EC B7 0B BF 7A FD 86 .W....;S.....*-.4..Z4.m:.....z..
000000A0 A4 9C 76 23 A3 DF A5 D1 F3 1D 0C 48 6A 57 4D 52 CB FB 13 CB 08 33 E7 E5 E4 AC 74 74 ED A7 2C 6C ..v#.......HjWMR.....3....tt..,l
000000C0 9D 3E 71 68 98 46 5B 46 C6 91 9A E5 5D 8D 30 C5 BA 6D FF 60 2F 3E 79 90 76 91 99 34 70 53 1B B2 .>qh.F[F....].0..m.`/>y.v..4pS..
000000E0 7F 9E 23 D1 93 C5 E0 C2 6E 46 BC AC A7 06 AE 57 2C F0 11 49 E5 78 9F 6F 0E 35 91 EA 92 0D E3 9F ..#.....nF.....W,..I.x.o.5......
00000100 E3 33 65 84 04 DC 78 87 49 7A 5F EC 61 AF C7 47 34 DF 88 CF E8 2F A5 59 2C 5E 29 FF 5B 8E 2B F1 .3e...x.Iz_.a..G4..../.Y,^).[.+.
00000120 97 26 1A DC DD DA 17 F7 77 CB A5 D3 E3 9B 92 C7 EE CB 99 73 85 2B BF 3F 4B 9D 2F B8 E7 8F B5 64 .&......w..........s.+.?K./....d
00000140 A6 7C 2B 97 72 83 A8 74 FA D3 F3 01 2B FB F4 80 A5 2F 0C E2 4F DF B5 65 85 97 FB E2 67 A1 26 AC .|+.r..t....+..../..O..e....g.&.
00000160 EF C3 BE BC C9 D7 34 DA 31 5A 8F DD CF 9A 41 A2 2B 3A 33 A7 98 B6 D8 09 19 60 8F 11 03 D9 B9 36 ......4.1Z....A.+:3......`.....6
00000180 83 F9 A3 90 54 9A A9 7B 4D 56 B3 FC F7 A1 17 A4 ED FA 39 31 AB E1 7D 88 71 F7 1C FA 68 87 AE D2 ....T..{MV........91..}.q...h...
000001A0 F5 19 BD 30 27 E7 A4 C7 D8 86 0E 3F 71 74 56 0E DD 3A AD 8F EC 92 65 07 62 A7 61 4E A6 D5 DD C2 ...0'......?qtV..:....e.b.aN....
000001C0 4A EB 35 24 1E 73 B3 58 8A 85 29 B9 80 B3 E9 46 4D 2A 1D A3 DD 8B FB 3B 37 E4 BD 69 3E FE 1E A1 J.5$.s.X..)....FM*.....;7..i>...
000001E0 43 DA F7 59 C2 EC 9C 96 C9 7E 3A 67 D2 46 A9 71 FC C3 19 5F 99 5E 69 0B 1E 1B E6 C1 9B 3F 2F C6 C..Y.....~:g.F.q..._.^i......?/.
00000200 05 E9 59 32 4B B5 89 4C CE D7 BE 34 8D 6F 30 5E C7 02 75 4C F8 9D A1 36 BC F7 E4 3D F8 5E CE 6E ..Y2K..L...4.o0^..uL...6...=.^.n
00000220 59 6C ED 9D B2 44 F7 74 45 9C 6B 5E DF E3 3B 87 F0 DA EC AB 45 62 F1 13 8B BF 58 7C DF 7F D1 25 Yl...D.tE.k^..;.....Eb....X|...%
00000240 B7 EE 25 50 D7 30 43 D6 6C AF 5E D1 D9 B7 B1 3C A8 5F 4A D1 CE AE 17 F0 B1 91 4F 99 D5 7C 43 B2 ..%P.0C.l.^....<._J.......O..|C.
00000260 35 2A 85 AA 57 EA 4A F7 F4 09 62 C1 73 10 A7 86 BE E4 F2 8E 37 78 25 57 E7 3B 1D 9A 13 77 CF 14 5*..W.J...b.s.......7x%W.;...w..
00000280 FA DA 65 25 DB A1 9B C1 CC 3F C4 CB C2 A6 44 F0 FA 13 2F E0 69 CB 9A 70 AB 37 26 C4 10 E2 1B 18 ..e%.....?....D.../.i..p.7&.....
000002A0 7C 80 BD A8 F3 5C 76 C6 D6 10 2F 37 9A C9 4B 5B 5F C5 E3 1F 58 72 CD 91 8E 24 BF 24 8D 36 8A 1D |....\v.../7..K[_...Xr...$.$.6..
000002C0 8B 3F 7F EF 87 33 27 77 C1 EB E2 A7 91 89 DF D4 C8 82 06 86 7C 4A 9A 0D 31 77 48 A7 7D AD DA 30 .?...3'w............|J..1wH.}..0
000002E0 BB 03 D3 49 A7 60 1D E6 59 AF 3F 1B 28 7B 89 CB B7 99 FE ED F2 1B EB 9A 90 02 EB 14 1A 35 D5 90 ...I.`..Y.?.({...............5..
00000300 AD D8 1C 45 26 94 BD 95 A9 9D 36 65 C2 AD BB 78 E0 81 46 7F FB F9 88 DD 5F A3 AF BA 5C 9E BF 37 ...E&.....6e...x..F....._...\..7
00000320 E4 BF 7E 95 9E D3 69 C8 BF D4 EB 9F F9 9F 73 68 CE E5 F7 57 01 F7 E7 AC 9B 81 2F 7E 8A 97 45 D6 ..~...i.......sh...W....../~..E.
00000340 B8 BF FE F3 0D B9 BC 7C 5B 28 DF CD 3D 08 1F 86 F2 DB D7 28 BF EF 1B 13 2E BF FF 20 B8 FF AF 75 .......|[(..=......(....... ...u
00000360 9E 4B 03 ED 0C 71 56 8D FB B7 1C E9 C8 E5 D7 D7 10 AE 4F BF B2 1F 6B 32 A9 0B DE 5F E3 FA C4 CA .K...qV...........O...k2..._....
00000380 4F 4C B3 E1 F2 F8 04 40 7C 6C 0F 4C E7 65 10 1F A1 46 7C C4 CA D7 D0 35 E1 F2 E7 9F 05 CF 3F 6F OL.....@|l.L.e...F|....5......?o
000003A0 73 14 AF B8 FD 56 76 FB D4 3F 9F BF D8 F5 89 DD BF D8 F3 3D 6A E5 72 E8 F9 DE 14 DA 21 AA 0F F9 s....Vv..?.........=j.r.....!...
000003C0 36 B7 97 DD 5E DB 36 EC 4A C9 2C 6E D8 72 32 D9 44 6C 58 23 A9 0D DF F0 2E 85 FA 1D BF 8D 87 C4 6...^.6.J.,n.r2.DlX#............
000003E0 49 F9 E9 03 AB 64 C3 9E 99 F1 A7 F6 DE E4 47 80 1E 7B E9 DD 81 7B DE 4E A7 CF DC 77 E0 6D 73 7A I....d........G..{...{.N...w.msz
00000400 F1 F0 E8 FA 6C F4 7B 3D 7E 6D 8A 27 31 1D 36 88 F5 6B 67 C8 37 D5 4A A6 96 6D 8B B0 AF DD 23 B6 ....l.{=~m.'1.6..kg.7.J..m....#.
00000420 AB CB 04 36 B5 DE 50 3E DA C2 9B 7C 68 71 5F 66 F5 53 83 6F 6C BA 84 BE ED FB 13 DB CF 2A 66 B7 ...6..P>...|hq_f.S.ol........*f.
00000440 6E 78 F3 A8 07 A5 6C FC C1 00 B2 E2 53 8E 2C 69 86 96 82 EF DD 6F 2B AE F9 F7 FF F4 BE 0F 09 9B nx....l.....S.,i.....o+.........
00000460 BD 48 56 92 5F 8B 3F 8D 5E 4C 8F B6 3F A7 C4 0F 7D 10 40 F6 E8 6C 2E CA D7 29 66 C2 A2 44 5A 74 .HV._.?.^L..?...}.@..l...)f..DZt
00000480 A9 0B 39 65 D4 9D D5 7A 1A C5 EB 19 CD 93 6E 33 19 47 2C 16 65 C8 AC 3E A9 F1 E2 3E 8B A9 FF 1F ..9e...z......n3.G,.e..>...>....
000004A0 B6 4A F5 8B 56 E5 18 D2 CC 7B 5B 11 E9 E6 CD FA 39 27 52 EB 50 77 32 F9 C2 60 D9 99 1B 31 BC F7 .J..V....{[.....9'R.Pw2..`...1..
000004C0 F2 7C D9 4B 3E 91 B8 E4 C5 C9 EE 14 33 76 2D 36 81 FE 5C E0 40 7A 0C 99 A1 B8 06 40 7E DD 69 2C .|.K>.......3v-6..\.@z.....@~.i,
000004E0 79 E6 37 44 76 FB D5 6C A6 6B 9D 40 F7 B0 DE E4 79 9D 1F 8A 3A FA 79 9D 18 EE 3F 3B 94 E8 84 59 y.7Dv..l.k.@....y...:.y...?;...Y
00000500 CB 02 C7 1E 63 C6 F5 16 D3 15 C9 63 95 CA D7 0B 1D 4B C6 6D 37 2A 1A 65 E3 72 C8 5B 23 91 F6 7C ....c......c.....K.m7*.e.r.[#..|
00000520 ED 4B 92 DE C5 EE DD 5B 14 CB 93 53 BB 49 57 EC 9F 4E BE D6 1F 23 9B D7 6D 8E CC 23 21 9E BE B4 .K.....[...S.IW..N...#..m..#!...
00000540 F2 52 3A FF 5E 52 38 39 E7 F0 E9 90 58 7C D3 4F B6 27 F2 F8 7D 81 F8 CD 9F D3 8B 18 42 FC 56 D4 .R:.^R89....X|.O.'..}.......B.V.
00000560 88 DF F6 5D 56 44 1E FF 21 10 7F DB 38 29 79 BF 7F 95 2C B5 46 FC 5F 2D D3 27 F2 F8 7E 31 2A C2 ...]VD..!...8)y...,.F._-.'..~1*.
00000580 71 B6 8F F0 15 FB 09 EC 50 8D F8 BE 8E 50 27 D5 F1 F5 9A 55 8C D5 6E 7A F3 ED F7 FF 19 DF 7B 75 q.......P....P'....U..nz......{u
000005A0 FE C4 F2 F8 70 88 4F 89 51 77 5C 0F E2 53 6A F0 CF F8 F4 68 DC 0F CB 9F 7F 17 78 FE 6E E7 07 4B ....p.O.Qw\..Sj....h......x.n..K
```
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-20T02:35:57+00:00
- Post Title: TwelveSky 2 Model Format

Just nothing makes much sense to me from the format lol
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-20T02:41:35+00:00
- Post Title: TwelveSky 2 Model Format

there are no samples online to look at it.
## Post #10
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-07-20T02:43:25+00:00
- Post Title: TwelveSky 2 Model Format

ok  thanks anyway, and what about ArcheAge? somebody create a topic but nothing there. a 1 file of 24GB wtf? all be there packed in 1 file?
## Post #11
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-07-20T16:47:46+00:00
- Post Title: TwelveSky 2 Model Format

The contents of this post was deleted because of possible forum rules violation.
## Post #12
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-20T17:12:22+00:00
- Post Title: TwelveSky 2 Model Format

The file was deleted
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-20T18:49:48+00:00
- Post Title: TwelveSky 2 Model Format

The contents of this post was deleted because of possible forum rules violation.
## Post #14
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-20T19:27:11+00:00
- Post Title: TwelveSky 2 Model Format

the models are just compressed with zlib
just use offzip to extract them
## Post #15
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-21T02:11:54+00:00
- Post Title: TwelveSky 2 Model Format

What is the command for offzip?

I tried writing a simple bms script for it because I wanted to customize the filename (name_01, name_02, etc) but there doesn't seem to be a way to determine how many files are in the object.

```
get one long
get size long
get csize long
savepos offset
clog test offset csize size
```


This got the first file...but then I didn't know how to continue it.

EDIT:

```

get one long
get one long
get FULLSIZE asize
set x long 1
do
	get name basename
	string name + x
	get size long
	get csize long
	savepos offset
	clog name offset csize size
	math offset += csize
	goto offset
	savepos CURR
	math offset += 4
	goto offset
	math x += 1
while CURR < FULLSIZE
```


This always crashes cause there are 8 bytes of nulls at the end of the file, and some have more data after those 8 bytes so I have to figure out how to use the total filesize and current position properly.

But at least it works (extracts dds images properly and can view them). Though, I wish there was a way to auto assign some extensions after somehow examining the filetype.
[P0030020012.7z](https://xentaxbackup.github.io/file/4523_P0030020012.7z)
## Post #16
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-07-21T02:37:23+00:00
- Post Title: Re: TwelveSky 2 Model Format

The contents of this post was deleted because of possible forum rules violation.
## Post #17
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-21T02:53:37+00:00
- Post Title: Re: TwelveSky 2 Model Format

You don't get any nice filenames with offzip though lol.
I want to at least keep the package name so I know where it came from.

(..without manually renaming them)
## Post #18
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-07-21T02:57:50+00:00
- Post Title: Re: TwelveSky 2 Model Format

> Reply from finale00
>
> You don't get any nice filenames with offzip though lol.
I want to at least keep the package name so I know where it came from.

(..without manually renaming them)well sorry just I try help, i'm not expert in this, just learning mate, and how you get DDS? replacing header of the file? or how?
## Post #19
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-21T03:11:41+00:00
- Post Title: Re: TwelveSky 2 Model Format

just make a bat file for it.
## Post #20
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2011-07-21T11:09:49+00:00
- Post Title: Re: TwelveSky 2 Model Format

I did the full format on Twelve Sky back on 2008. And the formats remain the same in Twelve Sky 2!
Here is the basic struct for the Archive! (*.mobject, *.sobject)
dword      numResource
struct RES
{
<compressed model data>
<compressed Texture data>
}
Here is the bms script to help you decompress the Archive easily!
Good luck!

```
# by fatduck     Jul2011
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

get PRENAME basename
get NUMRES long
savepos OFS_RES
for i = 1 to NUMRES
   goto OFS_RES
   get FLAG1 long
   get USIZE long
   if FLAG1 != 1 
      math FLAG1 -= USIZE
      math FLAG1 *= -1 
   else
      math FLAG1 -= 1
   endif
   get CSIZE long
   savepos OFS_RES
   set RESNAME PRENAME
   string RESNAME += _
   if i < 10 
      string RESNAME += "0"
   endif
   string RESNAME += i
   string RESNAME += .mdl
   if USIZE > 0
      clog RESNAME OFS_RES CSIZE USIZE
   endif
   math OFS_RES += CSIZE
   math OFS_RES += FLAG1

   goto OFS_RES
   get FLAG1 long
   get USIZE long
   if FLAG1 != 1 
      math FLAG1 -= USIZE
      math FLAG1 *= -1 
   else
      math FLAG1 -= 1
   endif
   get CSIZE long
   savepos OFS_RES
   set RESNAME PRENAME
   string RESNAME += _
   if i < 10 
      string RESNAME += "0"
   endif
   string RESNAME += i
   string RESNAME += .dds
   if USIZE > 0
      clog RESNAME OFS_RES CSIZE USIZE
   endif
   math OFS_RES += CSIZE
   math OFS_RES += FLAG1
next i
```
## Post #21
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-07-21T11:44:09+00:00
- Post Title: Re: TwelveSky 2 Model Format

> Reply from fatduck
>
> I did the full format on Twelve Sky back on 2008. And the formats remain the same in Twelve Sky 2!
Here is the basic struct for the Archive! (*.mobject, *.sobject)
dword      numResource
struct RES
{
<compressed model data>
<compressed Texture data>
}
Here is the bms script to help you decompress the Archive easily!
Good luck!
Code: Select all# Game: TwelveSky & TwelveSky 2 (PC)
# by fatduck     Jul2011
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

get PRENAME basename
get NUMRES long
savepos OFS_RES
for i = 1 to NUMRES
   goto OFS_RES
   get FLAG1 long
   get USIZE long
   if FLAG1 != 1 
      math FLAG1 -= USIZE
      math FLAG1 *= -1 
   else
      math FLAG1 -= 1
   endif
   get CSIZE long
   savepos OFS_RES
   set RESNAME PRENAME
   string RESNAME += _
   if i < 10 
      string RESNAME += "0"
   endif
   string RESNAME += i
   string RESNAME += .mdl
   if USIZE > 0
      clog RESNAME OFS_RES CSIZE USIZE
   endif
   math OFS_RES += CSIZE
   math OFS_RES += FLAG1

   goto OFS_RES
   get FLAG1 long
   get USIZE long
   if FLAG1 != 1 
      math FLAG1 -= USIZE
      math FLAG1 *= -1 
   else
      math FLAG1 -= 1
   endif
   get CSIZE long
   savepos OFS_RES
   set RESNAME PRENAME
   string RESNAME += _
   if i < 10 
      string RESNAME += "0"
   endif
   string RESNAME += i
   string RESNAME += .dds
   if USIZE > 0
      clog RESNAME OFS_RES CSIZE USIZE
   endif
   math OFS_RES += CSIZE
   math OFS_RES += FLAG1
next i
wow, really awesome man thanks a lot you are my hero mate grateful.

PD: maybe now somebody can help for Max Importer 

mdl file are same extention like valve of HL2, but ofc the importer don't work to 12Sky xD
[C012014003_01.png](https://xentaxbackup.github.io/file/4524_C012014003_01.png)
## Post #22
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-07-21T16:29:20+00:00
- Post Title: Re: TwelveSky 2 Model Format

Good Work Fatduck, something posibility of extract and run the animation files too  
Also i try with MDL3, MDL4 and MDL5 Import format and cant load the models.
## Post #23
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2011-07-21T17:01:26+00:00
- Post Title: Re: TwelveSky 2 Model Format

mdl is simply for a name of "model", the format is different from other game!   
AFAIK, the format is very easy and effect use vertex animation as well!

I did record some format in my own Chinese forums
[http://gameresearch.5d6d.com/viewthread.php?tid=96](http://gameresearch.5d6d.com/viewthread.php?tid=96)
use guess/guess as user/password

for the animation archive, you have to upload some samples, I don't have both games anymore!
## Post #24
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-21T17:02:50+00:00
- Post Title: Re: TwelveSky 2 Model Format

I changed it to tsmdl so people wouldn't assume it's one of the common mdl formats. Plus it makes it easier for me.

Archiver also works without login: [http://gameresearch.5d6d.com/archiver/tid-96.html](http://gameresearch.5d6d.com/archiver/tid-96.html)
## Post #25
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-07-21T17:20:46+00:00
- Post Title: Re: TwelveSky 2 Model Format

The contents of this post was deleted because of possible forum rules violation.
## Post #26
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-07-21T21:21:37+00:00
- Post Title: Re: TwelveSky 2 Model Format

> Reply from finale00
>
> I changed it to tsmdl so people wouldn't assume it's one of the common mdl formats. Plus it makes it easier for me.

Archiver also works without login: http://gameresearch.5d6d.com/archiver/tid-96.html

Well its not a common mdl but can you write a bms or something importer to load this format? i found this code in the link you post but i cant understand how to use, its this Discuz Archiver 7.0.0 program function to save this MDL to tsmdl?, Regards.
## Post #27
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-21T22:42:14+00:00
- Post Title: Re: TwelveSky 2 Model Format

The model format fatduck reference to is for the 1st Twelve Sky.
The samples uploaded here are for twelve sky 2. Same developer, so maybe that's why same format used for the files, but the model format seems difference I think.

You can get the first game [http://download.mmosite.com/html/1/2252/](http://download.mmosite.com/html/1/2252/)

> to save this MDL to tsmdl?,

Just modify the bms script that appends mdl to the name.
## Post #28
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-07-25T23:45:07+00:00
- Post Title: Re: TwelveSky 2 Model Format

> Reply from finale00
>
> The model format fatduck reference to is for the 1st Twelve Sky.
The samples uploaded here are for twelve sky 2. Same developer, so maybe that's why same format used for the files, but the model format seems difference I think.

You can get the first game http://download.mmosite.com/html/1/2252/
 to save this MDL to tsmdl?,

Thanks fInale i take a look but i see a incomplete model fileformat alson in Twelve Sky 1, fatduck only make the unpacker object files and this works also in Twelve Sky 2, if you know a bms or maxscript to load this models of Twelve sky 1 can be usefull, cheers.
## Post #29
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-08-05T18:23:23+00:00
- Post Title: Re: TwelveSky 2 Model Format

Code wrothed by fatduck for 12sky

```
dword       ??          //header??
float       Emission
float_4     color1
float_4     color2
byte_76     ??
dword       numMatrix
dword       numVerts
dword       ??          //same as numVerts
dword       numFaceIdx
struct Animation {
  float_12  Matrix3X4
  float_4   sphereXYZR
}
struct AnimatedVert {
  float_3   posXYZ
  float_3   normatXYZ
  float_2   texUV
}
struct Face {
  word_3    index123
}
```


Aparently works fine, 


File to test:
[http://gameresearch.5d6d.com/attachment ... 8852&fid=6](http://gameresearch.5d6d.com/attachment.php?aid=156&k=897ef08218e663e7537a8c9e28dbf29e&t=1312568852&fid=6)

Any help to make this in blender or max script?
Regards.
## Post #30
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-06T23:43:53+00:00
- Post Title: Re: TwelveSky 2 Model Format

There are most likely different formats for different model types.
I will post up later when I figure out what the differences are.

EDIT: it appears to be the difference between sobject and mobject. Not too sure.

Also, notice that the words are mirrored. Hmm I wonder how to fix that lol

This is an SOBJECT, and I followed fatduck's format but made minor changes to make it work

```
dword       ??          //model type
float       Emission
float_4     color1
float_4     color2
byte_76     ??
dword       numMatrix
dword       numVerts
dword       ??          
dword       numFaces

byte_40 ???
numVerts vertex {
  float_3   posXYZ
  float_3   normatXYZ
  float_2   texUV
}
numMatrix Animation {
  float_8 ???
}
numFaces Face {
  word_3    index123
}

```


mobject is different, and doesn't seem to follow what is written either. Maybe the format has changed.

Anyways twelve sky and twelve sky 2 SOBJECT are the same format.

ts2 monster:


ts1 object
[12sky_object.jpg](https://xentaxbackup.github.io/file/4587_12sky_object.jpg)
## Post #31
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-08-09T21:36:29+00:00
- Post Title: Re: TwelveSky 2 Model Format

Amazing advance finale   , its good see someone can keep out the models.
## Post #32
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-09-03T17:54:08+00:00
- Post Title: Re: TwelveSky 2 Model Format

Anyone can make the blender or max script to load? This can be usefully    .
## Post #33
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-09-22T00:10:48+00:00
- Post Title: Re: TwelveSky 2 Model Format

I got this from hour good friend Credits Zskaradek 

Quick importer [.mdl]:geometry,uv,weights,no bones
Please check it.
Press in text window alt+p and select mdl file.
If in the same folder :mdl and dds - script make autotexturing.
Work with models exctracted by Fatduck bms. 

[download/file.php?id=4685](http://forum.xentax.com/download/file.php?id=4685)
## Post #34
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-09-22T01:03:27+00:00
- Post Title: Re: TwelveSky 2 Model Format

> Reply from Rimbros
>
> download/file.php?id=4685the attachment not exist
## Post #35
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-09-22T22:37:04+00:00
- Post Title: Re: TwelveSky 2 Model Format

> Reply from CriticalError
>
> Rimbros wrote:download/file.php?id=4685the attachment not exist

Atachment exist, but i test and the script doesnt work fail in one line.
If anyone can help to fix can be nice i think Zskara its very bussy now.
## Post #36
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-09-22T22:53:54+00:00
- Post Title: Re: TwelveSky 2 Model Format

well I try import them and it worked in 12sky 1 and 2.
[12sky2.jpg](https://xentaxbackup.github.io/file/4724_12sky2.jpg)
## Post #37
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-09-22T23:27:17+00:00
- Post Title: Re: TwelveSky 2 Model Format

Fine i changue the phyton and blender version and works now.
## Post #38
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-05T06:08:54+00:00
- Post Title: Re: TwelveSky 2 Model Format

Someone was asking for a blender importer.

I tried writing a noesis plugin and it worked for the SOBJECT but the MOBJECT is completely different.

The attached file contains an unpacked MOBJECT.

First look at the 10 KB file and go to the end of the file. You'll find a couple shorts. In fact, you'll find 6 of them, because there are only 2 faces (it's a rectangle).

So that means there are 4 vertices.

Clearly there's 9000+ bytes of other stuff, which is probably determined by the other integer, but I don't see a pattern.
## Post #39
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-01-05T07:11:02+00:00
- Post Title: Re: TwelveSky 2 Model Format

> Reply from finale00
>
> Someone was asking for a blender importer.

I tried writing a noesis plugin and it worked for the SOBJECT but the MOBJECT is completely different.

The attached file contains an unpacked MOBJECT.

First look at the 10 KB file and go to the end of the file. You'll find a couple shorts. In fact, you'll find 6 of them, because there are only 2 faces (it's a rectangle).

So that means there are 4 vertices.

Clearly there's 9000+ bytes of other stuff, which is probably determined by the other integer, but I don't see a pattern.

Blender importer already exist, the blender master Zskaradek improved this, here the link for blender.
[download/file.php?id=4685](http://forum.xentax.com/download/file.php?id=4685)

Maybe this can help you to made the Noesis blugin more funtionality. regards.

P.D. and finale00 i follow your work with blender and Noesis, good job man, you learn good skills.
## Post #40
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-05T08:12:51+00:00
- Post Title: Re: TwelveSky 2 Model Format

I'm getting a "selected attachment does not exist anymore"

You have good modeling and game modding skills. Maybe you can look at noesis as well.
## Post #41
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-01-10T19:22:55+00:00
- Post Title: Re: TwelveSky 2 Model Format

> Reply from finale00
>
> I'm getting a "selected attachment does not exist anymore"

You have good modeling and game modding skills. Maybe you can look at noesis as well.

Infortunately to mod games i work with reverse files conversions, Noesis its a greath tool to extract models and textures and with your help and the others boys this become the best tool to convert files models from games, but to convert from the extracted to native files Noesis its so far limitated tool.

Also maybe i made one section here in Xentax abouth moding games.
## Post #42
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2012-02-24T06:58:26+00:00
- Post Title: Re: TwelveSky 2 Model Format

> Reply from finale00
>
> I tried writing a noesis plugin and it worked for the SOBJECT but the MOBJECT is completely different.
...
Clearly there's 9000+ bytes of other stuff, which is probably determined by the other integer, but I don't see a pattern.
I think SOBJECT is static object, MOBJECT is moving (or mobile) object, so 9000+ bytes is some sort of animation data.
## Post #43
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-24T17:38:47+00:00
- Post Title: Re: TwelveSky 2 Model Format

I quit all the finale plugins from Noesis, and keep only the fmt_TwelveSky2_mdl.py, but its the same error window abouth sanae3D etc etc.   how i can fix this.
## Post #44
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-24T17:46:12+00:00
- Post Title: Re: TwelveSky 2 Model Format

It might be an older plugin before I started standardizing things.
I'll update it when I get around to it. The plugin is nowhere near complete.
## Post #45
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-25T04:25:57+00:00
- Post Title: Re: TwelveSky 2 Model Format

Thanks finale, please send msg when u updated...
## Post #46
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-26T05:24:06+00:00
- Post Title: Re: TwelveSky 2 Model Format

> Reply from finale00
>
> I'm getting a "selected attachment does not exist anymore"

You have good modeling and game modding skills. Maybe you can look at noesis as well.ok here you have the script for blender.
[import-12sky-2011-09-03.7z](https://xentaxbackup.github.io/file/5109_import-12sky-2011-09-03.7z)
## Post #47
- Username: PoznakSoft
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 10, 2012 6:07 am
- Post datetime: 2012-04-09T22:43:27+00:00
- Post Title: Re: TwelveSky 2 Model Format

If it aint too much trouble could you explain how to actually use that script for blender?
## Post #48
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-15T07:09:47+00:00
- Post Title: Re: TwelveSky 2 Model Format

> Reply from PoznakSoft
>
> If it aint too much trouble could you explain how to actually use that script for blender?
Only need use in Blender Plugin folder and select from menu, the think i not understand its why Finale cant finish this if this works in blender why this not work in Noesis, only he have answer.
## Post #49
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-16T01:38:04+00:00
- Post Title: Re: TwelveSky 2 Model Format

Mostly lazy to look at it lol
## Post #50
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-07-16T02:04:43+00:00
- Post Title: Re: TwelveSky 2 Model Format

I know the feeling.
## Post #51
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-16T02:30:02+00:00
- Post Title: Re: TwelveSky 2 Model Format

The other issue is managing samples.
I move around from time to time, so my collection of samples isn't usually available.

I've been maintaining a folder of samples in my dropbox but that's only with some games I looked at recently.

And then I have to selectively choose a set of "good" samples so that I can capture a variety of different things...

Of course if it's a model of a girl that would go in the folder
## Post #52
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-20T16:58:30+00:00
- Post Title: Re: TwelveSky 2 Model Format

> Reply from finale00
>
> The other issue is managing samples.
I move around from time to time, so my collection of samples isn't usually available.

I've been maintaining a folder of samples in my dropbox but that's only with some games I looked at recently.

And then I have to selectively choose a set of "good" samples so that I can capture a variety of different things...

Of course if it's a model of a girl that would go in the folder

Ok lots of samples are now in repository .SOBJECT and .MOBJECT, good luck my friend.
## Post #53
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2012-11-22T22:11:49+00:00
- Post Title: Re: TwelveSky 2 Model Format

Did anyone succeded to import model in 3d studio max or noesis?
## Post #54
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-11-29T15:35:54+00:00
- Post Title: Re: TwelveSky 2 Model Format

I have not looked at the script but is it made from that szkaradek or what his name is?

Place the .blender file where you have the models. Open the blender file in blender. Press alt+p to run script, there will be a window where you choose model directory/texture directory etc.

This is how he usually does it. I might take a look tonight if I am able to.
## Post #55
- Username: baso
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Mar 30, 2012 11:06 pm
- Post datetime: 2013-03-13T16:03:03+00:00
- Post Title: Re: TwelveSky 2 Model Format

> Reply from pixellegolas
>
> I have not looked at the script but is it made from that szkaradek or what his name is?

Place the .blender file where you have the models. Open the blender file in blender. Press alt+p to run script, there will be a window where you choose model directory/texture directory etc.

This is how he usually does it. I might take a look tonight if I am able to.

the .blend script don't work.. any ideas?
## Post #56
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2013-03-19T18:09:26+00:00
- Post Title: Re: TwelveSky 2 Model Format

> Reply from baso
>
> the .blend script don't work.. any ideas?it's for Blender249 as i recall
## Post #57
- Username: ridack
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Aug 01, 2013 9:26 am
- Post datetime: 2013-08-01T17:24:11+00:00
- Post Title: Re: TwelveSky 2 Model Format

see i have blender 249 and it not work when i import .mdl file why?
## Post #58
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-08-01T18:14:04+00:00
- Post Title: Re: TwelveSky 2 Model Format

rimbros mentioned use blender 2.49b (2.49.2) and update your python.
## Post #59
- Username: LiamMitchell
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 25, 2014 11:47 pm
- Post datetime: 2014-02-20T06:45:54+00:00
- Post Title: Re: TwelveSky 2 Model Format

Thanks for your info on this guys,
Managed to load SOBJECT files into Three.js Will try for MOBJECT and Maps later if bored.
[http://extendedgames.com/TS1ModelViewer/](http://extendedgames.com/TS1ModelViewer/)


Now my friend can hopefully mod in custom character hair and face styles .
## Post #60
- Username: ridack
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Aug 01, 2013 9:26 am
- Post datetime: 2014-06-15T18:32:55+00:00
- Post Title: Re: TwelveSky 2 Model Format

good
