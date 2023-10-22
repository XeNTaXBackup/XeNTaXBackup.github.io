## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-09T00:43:15+00:00
- Post Title: Sanjie PAK

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: MrMoonKr
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Oct 16, 2009 2:18 pm
- Post datetime: 2012-02-09T05:42:40+00:00
- Post Title: Sanjie PAK

i think it is a 2D game.
but, i cannot figure out the sprite format ( named blahblah.apg )

( P.S ) 
i guess that apg means archived-jpg ^^;;;
but i don't know how they are compressed

```
// 010 Editor v3.1 Binary Template
//
// File     : SanjieTemplatePAK.bt
// Author   : MrMoonKr
// Revision : 0.1
// Purpose  : Sanjie pak file analyze
// Changes  :  
//
// ( 2012/02/09/Thu )
//          : http://sj.wanku.com/
//
//////////////////////////////////////////////////////////////////////////


//------------------------------------------------------------------------

#include "CommonTemplate.bt"


//------------------------------------------------------------------------

struct PAKHeader ;

typedef struct
{
    char                mFourCC[4] ;
    uint32              mUnknown ;
    uint32              mSize ;
    CCData              mData( mSize ) ;

} PAKData < bgcolor = cLtRed > ;


//------------------------------------------------------------------------

typedef struct ( uint32 baseOffset )
{
    char                mName[32] ;
    uint32              mOffset ;
    uint32              mSize ;
    uint32              mType ;
    uint32              mZero ;

    local uint32 bookMark = FTell() ;

    FSeek( baseOffset + mOffset ) ;
    if ( mType == 1 )
    {
        PAKHeader       mPackage( baseOffset + mOffset ) ;
    }
    else
    {
        //CCData          mData( mSize ) ;
        PAKData         mData ;
    }

    FSeek( bookMark ) ;

} PAKChunk < bgcolor = cLtPurple , read = ReadPAKChunk > ;

string ReadPAKChunk( PAKChunk& chunk )
{
    string s = "(no data)" ;
    SPrintf( s , "( Offset : %d )( Size : %d ) ( Type : %d ) ( %s )" ,
        chunk.mOffset ,
        chunk.mSize ,
        chunk.mType ,
        chunk.mName 
        ) ;
    return s ;
}

//------------------------------------------------------------------------

/**
    archive file header
*/
typedef struct ( uint32 baseOffset )
{
    char                mFourCC[8] ;
    uint32              mSize ;
    uint32              mChunkCount ;
    local uint32 i=0 ;
    for ( i=0 ; i < mChunkCount ; ++i )
    {
        PAKChunk        mChunkArray( baseOffset ) ;
    }
    //PAKChunk            mChunkArray[ mChunkCount ] ; ///< may be bug !!!

} PAKHeader < bgcolor = cLtGray , read = ReadPAKHeader > ;

string ReadPAKHeader( PAKHeader& header )
{
    string s = "(no data)" ;
    SPrintf( s , "( FourCC : %s )" ,
        header.mFourCC
        ) ;
    return s ;
}

//////////////////////////////////////////////////////////////////////////

LittleEndian() ;
//BigEndian() ;


PAKHeader               gHeader( 0 ) ;




```
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-09T06:53:10+00:00
- Post Title: Sanjie PAK

umm well I checked files and is not hard, changed first 8 bytes you can unpack it, thanks for support of finale00. 



> #Sanjie Online PAK Unpacker
>
> 
>
> idstring "PAKF3001"
>
> get FSIZE long
>
> get FILES long
>
> 
>
> set FOLDER_NAME = "/"
>
> for i = 0 < FILES do
>
>    getdstring NAME 32
>
>    get OFFSET long
>
>    get SIZE long
>
>    get IS_FOLDER long
>
>    get unk2 long
>
> 
>
>    if IS_FOLDER = 1
>
>       set FOLDER_NAME = NAME
>
>       string FOLDER_NAME += "/"
>
>    else
>
>       set TEMP = FOLDER_NAME
>
>       string TEMP += NAME
>
>       print %TEMP%
>
>       log TEMP OFFSET SIZE   
>
>    endif
>
> next i
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-09T06:59:58+00:00
- Post Title: Sanjie PAK

Trying unpack UI.pak 138MB   

```
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org

- GUI mode activated, remember that the tool works also from command-line
  where are available various options like folder scanning, filters and so on

- select the BMS script or plugin to use
- select the input archives/files to extract, type "" for whole folder and subfo
lders
- select the output folder where extracting the files
- open input file D:\Sanjie\ui.pak
- open script D:\Sanjie Online.bms
- set output folder D:\Sanjie\ui

  offset   filesize   filename
------------------------------
- SCRIPT's MESSAGE:
  baobei/block.bmp

  07a4763f 63         baobei/block.bmp
- SCRIPT's MESSAGE:
  baobei/block2.bmp

  07a4767e 62         baobei/block2.bmp
- SCRIPT's MESSAGE:
  item/ItemView.a16

  085071a6 92         item/ItemView.a16
- SCRIPT's MESSAGE:
  msgdlg/NODRAG.tga

  0850fcef 427        msgdlg/NODRAG.tga

- 4 files found in 0 seconds

Press RETURN to quit
```
## Post #5
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-09T07:04:14+00:00
- Post Title: Sanjie PAK

> Reply from Ekey
>
> Trying unpack UI.pak 138MBcan you try upload it? I don't have client yet, I added to queue but you upload it, I try check files.
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-09T07:26:36+00:00
- Post Title: Sanjie PAK

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-09T07:47:45+00:00
- Post Title: Sanjie PAK

> Reply from CriticalError
>
> umm well I checked files and is not hard, changed first 8 bytes you can unpack it, thanks for support of finale00.

I never looked at this lol
## Post #8
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-09T08:41:59+00:00
- Post Title: Sanjie PAK

> Reply from finale00
>
> CriticalError wrote:umm well I checked files and is not hard, changed first 8 bytes you can unpack it, thanks for support of finale00. 

I never looked at this lolyeah but anyway all files have same strings, I check first bytes others files and don't look same, for example.

map.pak

```
0000001F 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 70 00 00 00 00 00 00 00 01 00 00 00 00 00 .................p.............
0000003E 00 00 73 74 61 72 74 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 ..start........................
0000005D 00 00 00 F7 C2 01 00 00 00 00 00 01 00 00 00 00 00 00 00 50 41 4B 46 33 30 30 31 87 C2 01 00 ...................PAKF3001....
0000007C 05 00 00 00 73 6B 79 2E 43 45 4C 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 ....sky.CEL....................
0000009B 00 00 00 00 00 00 01 00 00 28 00 00 00 00 00 00 00 00 00 00 00 73 6B 79 2E 63 6F 72 65 00 00 .........(...........sky.core..

```



ui.pak 

```
0000001F 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 10 0F 00 00 21 4B 2C 02 01 00 00 00 00 00 .....................!K,.......
0000003E 00 00 61 70 6C 61 6E 5F 49 42 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 ..aplan_IB.....................
0000005D 00 00 00 31 5A 2C 02 4E 7D 12 00 01 00 00 00 00 00 00 00 61 70 6C 61 6E 5F 70 72 6F 70 65 72 ...1Z,.N}..........aplan_proper
0000007C 74 79 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 7F D7 3E 02 62 13 0A 00 01 00 00 ty....................>.b......
0000009B 00 00 00 00 00 61 70 6C 61 6E 5F 73 68 6F 70 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 .....aplan_shop................

```


data.pak 726MB

```
0000001F ED 02 3E 4B 2D 70 14 CB AE 4E AC 78 15 14 AE B1 70 91 9F C3 32 2A 4E BB 34 66 67 EC C6 A8 8A ..>K-p...N.x....p...2*N.4fg....
0000003E 48 A9 88 E5 14 A8 2A CD 69 10 6B 7A 85 4B A3 BE BD 0C C8 8C 21 2A 40 0A 99 46 1A 9C 11 B5 99 H.....*.i.kz.K......!*@..F.....
0000005D C9 78 ED C7 BF 4E BD BA 55 D0 4E 7F D0 5E 01 97 76 C9 BA DE C2 95 67 5B 48 96 0E 5D 11 6A 84 .x...N..U.N..^..v.....g[H..].j.
0000007C 39 BE 5B D8 3F E0 21 37 5E 41 C8 CA 28 A5 ED 76 BE 6D E5 BD FC 43 6F 88 3D 77 BC A9 9B FE 0C 9.[.?.!7^A..(..v.m...Co.=w.....
0000009B 3C 02 F5 AF 80 63 22 2F C8 07 CA 70 31 85 A3 FD 74 E8 A6 13 F7 CF 61 33 7B BA 15 99 8E 0D C4 <....c"/...p1...t.....a3{......
000000BA A4 F8 77 24 9D 1F AB A1 B5 49 6D CC 8C 70 94 A9 1D 94 AB 47 DB B2 97 72 B7 46 BB A0 E8 92 77 ..w$.....Im..p.....G...r.F....w
000000D9 CD 00 B5 DC 0A 53 00 AA 37 42 7E C8 BB 9E 46 26 EE 8D 7A 15 50 AE 43 AA 91 E8 C6 4E 0B B2 CE .....S..7B~...F&..z.P.C....N...
000000F8 D0 9C 2C E0 A0 50 92 3A D6 CE 41 7B 59 BE 01 43 5E 61 3A 5E FD 95 FD 46 E7 04 09 3D 19 3B A3 ..,..P.:..A{Y..C^a:^...F...=.;.
00000117 00 43 2B F9 2B 45 B4 F0 9D 68 53 8A 6F 03 56 29 9D 54 73 47 61 8F EC 80 1A 04 36 D0 08 93 10 .C+.+E...hS.o.V).TsGa.....6....
00000136 E8 B7 78 DC A5 A4 63 E9 D2 4A 8F B6 42 C6 91 D6 26 EA 88 AD 23 20 DE 9A A7 A4 19 0D 6E 26 32 ..x...c..J..B...&...# ......n&2
00000155 41 CE 1B 79 27 09 30 DB 9B F8 66 06 D0 7A 15 00 8E 95 3E 45 A7 8E 2D 3E B6 BD F4 5D 61 D3 54 A..y'.0...f..z....>E..->...]a.T
00000174 FC 4F 0A 9D 2B 5E 14 6F 86 FD D6 68 67 9A 6E D5 40 55 9E 91 2D 72 2B DF DE 98 C2 45 19 DF 89 .O..+^.o...hg.n.@U..-r+....E...
00000193 5B DC C0 F2 B4 3F FC 9A 08 E8 2B 3A 15 42 EF 80 E7 EF 97 DF AC C2 7B C5 DC BB 5F AB CD F5 80 [....?....+:.B........{..._....
000001B2 AE B6 62 D8 6E B1 6A 96 C4 17 E3 3B 3A 28 FC 7D A3 82 C8 D2 35 50 ED E4 AF 73 D0 6E 88 CF 94 ..b.n.j....;:(.}....5P...s.n...
000001D1 48 8E 40 95 80 FB 17 8A 80 8D 34 28 6F D6 3E F7 BC 5B 20 31 63 49 57 B8 56 B3 43 DA E5 08 70 H.@.......4(o.>..[ 1cIW.V.C...p
000001F0 F1 48 BA F5 E7 87 4C EF CF 0D 34 88 3A AE AE A9 CD 9D 9A 4A 29 7D 24 09 36 FE D5 12 22 08 A5 .H....L...4.:......J)}$.6..."..
0000020F E9 5D A5 C4 D2 0B EE 61 4D 99 74 5C 63 0B 36 61 E6 93 9E 2C A3 EE 35 E7 6C 00 DC 93 5C A0 C8 .].....aM.t\c.6a...,..5.l...\..
0000022E BE 0B F0 32 C7 76 E3 96 5F 9C A7 AB A8 07 B4 37 15 F0 6B 27 D6 5A 4A 19 E0 9F 1C A2 45 77 5B ...2.v.._......7..k'.ZJ.....Ew[
0000024D 3E 5B 96 04 4C 63 55 59 41 27 F7 47 1D 8A 91 F5 BF 82 4B FE FE 99 3C 18 12 5E 2B 02 71 0D 02 >[..LcUYA'.G......K...<..^+.q..
0000026C C9 ED CC 44 B3 F9 70 B2 C4 9C D7 08 91 19 EB C5 BA 8E 69 CE C4 AA E2 9C DB 4F B1 52 AE F1 A2 ...D..p...........i......O.R...
0000028B C0 EF 88 D4 21 70 64 E5 ED 33 1F CD 3B 6B 52 2F F7 F1 C7 3A 4E B2 3B 76 0C 94 BF AD 4A FC 60 ....!pd..3..;kR/...:N.;v....J.`
000002AA FC CD 4E BF C9 1F 0C 0E E4 07 C2 F3 D3 E8 95 B3 E9 F4 58 6B D4 0F 54 23 4C BA 88 9F 6E CC E9 ..N...............Xk..T#L...n..
000002C9 8A 20 A3 E9 AF B2 1F 82 45 5A 21 18 58 33 4D 31 41 F0 7B 02 30 BA 66 6C 14 87 C2 8B 13 31 59 . ......EZ!.X3M1A.{.0.fl.....1Y
000002E8 0E 08 44 75 CB 69 9C 6D FA F3 D2 58 7D D1 01 23 DB EA AA F6 6E 88 12 BE 16 05 6C 5D 84 17 80 ..Du.i.m...X}..#....n.....l]...
00000307 C9 1C E0 C4 A7 AA BA 66 34 FA 6C FE E6 E3 BA 19 07 D7 16 63 74 06 B5 4C 6F F9 3F B5 9C A6 97 .......f4.l........ct..Lo.?....
00000326 15 CB F7 88 BE 84 1E 96 84 D1 77 9C A0 20 6D 9E 76 41 3E EA 90 4D 52 FF 8E 40 50 32 F6 CC 95 ..........w.. m.vA>..MR..@P2...
00000345 DF 44 0F 2E 96 CE 6D C9 1D A8 3D 2D 55 77 F0 2F C6 BE 8C 91 FF 15 E8 D0 02 F5 8E 86 3C FE 74 .D....m...=-Uw./............<.t
00000364 C6 B0 3F 13 83 E9 52 09 65 1C 6B D8 84 B3 E6 1E 66 84 1A 05 C5 35 14 A3 14 89 34 48 B1 BC 30 ..?...R.e.k.....f....5....4H..0
00000383 43 47 4C D6 2A C3 D9 0B 6A AF 95 CA A7 EB 54 AE 4D 35 41 1B 0A CC 2E 5D 1D 03 DB A0 A6 14 F8 CGL.*...j.....T.M5A....].......
000003A2 C2 FC 4B 48 97 1C A8 09 A2 17 59 E6 EF ED 5A 7C 88 16 65 43 BA 51 CA C9 08 B7 D2 34 73 3C A4 ..KH......Y...Z|..eC.Q.....4s<.
000003C1 B9 28 98 B6 E0 C3 10 F6 A3 FF 30 03 84 07 6D 4E 56 F0 9F 14 AA 15 5B CE 60 75 B7 6E CF 8B A4 .(........0...mNV.....[.`u.n...
000003E0 AB 4A F1 9B 2C 50 C2 4A BD FE 19 A0 39 D2 9F B4 D6 63 3A 5D 24 4E E5 3B 2F 5A A8 7B CB 1F CE .J..,P.J....9....c:]$N.;/Z.{...
000003FF 77 68 44 58 DB 92 3E 0A B9 F1 44 24 36 DB 78 D8 09 35 89 EA 43 EB 82 B5 62 5F 59 84 C0 D6 BC whDX..>...D$6.x..5..C...b_Y....
0000041E EF 65 10 B2 BE B0 B9 DD B9 6A 04 D4 CD 9D 17 AC BE C2 30 BE 11 EE 8F 9B 86 61 19 BA 55 74 B2 .e.......j........0......a..Ut.
0000043D 3E 1F 2D F4 70 35 A2 F9 00 54 0B 1C 9D 29 BF 8C E8 BB FA E7 42 37 99 AE 2B D7 99 12 30 6E 2A >.-.p5...T...)......B7..+...0n*
0000045C B9 E5 7C 26 CE 45 06 BB E7 04 99 3C EE 52 5C 43 27 BC 0E 91 A2 89 3A 06 15 61 5F 11 9E 96 12 ..|&.E.....<.R\C'.....:..a_....
0000047B 54 D9 68 E8 F1 F4 C1 30 9B CE 10 30 66 C0 1A EB F6 B3 A5 22 ED 28 77 72 CB 98 F3 F2 86 99 6A T.h....0...0f......".(wr......j
0000049A 52 3C 0D 61 4F 65 B2 28 B1 F7 73 D1 C9 CD 7B 1A 01 E3 4E A6 68 A7 E1 48 E3 6B 6D F1 A1 FD F1 R<.aOe.(..s...{...N.h..H.km....
000004B9 9A 03 A6 AB 2A 91 B7 07 9F 39 61 B8 1C EE 3C 7D 29 00 B4 D6 AC 0C 7D 83 F7 29 A9 29 9E 49 AF ....*....9a...<}).....}..).).I.
000004D8 4F 83 3D 27 5C 74 3D CE 32 10 B0 54 AE B3 FC E6 E9 E4 06 00 C0 6D A3 2D 4A 62 2F 48 3B 67 9E O.='\t=.2..T.........m.-Jb/H;g.
000004F7 BF 55 9D 8B 81 89 14 C0 01 8B AF 52 C7 20 BF 65 ED 7E C2 B9 79 C5 C3 4A 3B 85 09 D9 7C 18 A8 .U.........R. .e.~..y..J;...|..
00000516 89 9E 1F DC 75 4D 26 84 F5 35 14 DB EE 81 D3 18 18 CE 19 24 C0 FE B5 29 24 29 E3 0F A8 D3 09 ....uM&..5.........$...)$).....
00000535 7D 3C A7 18 20 D0 93 76 B8 AA 2D F1 91 15 6F A8 76 17 36 87 57 24 11 BA F6 06 41 3E 7B DD 54 }<.. ..v..-...o.v.6.W$....A>{.T
00000554 DC 6A FE 47 40 3D EC CD 45 6D 3C 89 16 6E B2 52 7D 65 1B 05 CE 87 18 D8 B1 D7 08 F4 DC C6 93 .j.G@=..Em<..n.R}e.............
00000573 82 70 6B 02 1E A2 9E E2 91 91 0E 97 17 BB 1F 03 1A 4F 39 08 0D 8D F1 BC F0 66 31 BF 23 D5 DC .pk..............O9......f1.#..
00000592 97 B4 83 C9 91 F6 48 DE C5 64 B9 8A 84 A1 4C 32 E3 4E B0 29 21 6A F6 57 4D D1 AA 6A 2C 53 F0 ......H..d....L2.N.)!j.WM..j,S.
000005B1 E7 A1 CE 14 A9 DF ED A1 77 75 C6 77 F4 A6 7D 7E 00 D5 98 14 CC 75 AF 59 BB A5 65 46 D9 0A 70 ........wu.w..}~.....u.Y..eF..p
000005D0 E9 27 77 33 25 A5 55 65 F3 43 A4 3B E9 23 9B A4 C3 FF BD 19 3D D4 C4 36 13 8D 4C E9 1E D1 08 .'w3%.Ue.C.;.#......=..6..L....
000005EF 1F 32 50 4D 66 9D 0E 43 FA A2 E9 69 A9 AA E6 A0 B1 06 CA 23 41 4D B7 81 BA AB 20 27 5F 6F 6C .2PMf..C...i.......#AM.... '_ol
0000060E A2 48 B7 1D E5 EB BA A9 8A 8D C2 68 00 48 1E F9 82 D3 AC 87 7F F4 EE DB D2 9A 02 E0 62 BB 2D .H.........h.H..............b.-
0000062D 18 78 C4 CB AA 3A 8A D3 62 FD F5 AA 34 18 DD E7 0A 03 8F 3C 17 38 96 9D 56 E4 DC C8 B2 3C 76 .x...:..b...4......<.8..V....<v
0000064C D9 C4 0D 0D 7B AD DF 41 E4 99 B3 56 3E 3C 1A D8 91 C0 94 F7 45 F5 2F 43 B4 EA BC 97 78 3D 46 ....{..A...V><......E./C....x=F
0000066B 09 5D F3 EB DD 35 CF 5A 96 D4 E6 CF 96 54 CB 06 6E BC 22 BB D1 48 EE B8 69 FD 9B F4 39 6F 22 .]...5.Z.....T..n."..H..i...9o"
0000068A F3 E5 E8 4D 1F E8 3E 84 CA 4C BD 52 32 53 17 55 56 7E 5D A4 34 42 2E 32 60 AC B4 EA F3 60 AB ...M..>..L.R2S.UV~].4B.2`....`.
000006A9 90 C3 29 78 60 78 A2 C7 9D 99 D8 53 C7 B9 8C 4A 57 EC 0C BA 71 D6 2D 3B 54 BA E1 DD B0 5C CE ..)x`x.....S...JW...q.-;T....\.
000006C8 84 B4 FD 69 20 E2 C6 5F 21 69 9B 20 74 E9 70 E9 0B 4E 3C B6 3A B1 AD 47 6D FC 78 58 71 07 1D ...i .._!i. t.p..N<.:..Gm.xXq..
000006E7 7F 7D 11 7E F7 A2 85 5B 8B F0 1A B7 61 97 27 E8 AF B0 81 A0 F5 BB 54 E1 BE 30 0D E2 EC AA 68 .}.~...[....a.'.......T..0....h
00000706 77 50 56 F8 52 50 2B 82 5C 1D 64 95 5C 26 A9 FC 2F EB 3E 9C 20 05 B1 FD BE 48 0F A9 73 32 DB wPV.RP+.\.d.\&../.>. ....H..s2.
00000725 AC B3 FE BE 1D 47 4D 47 B6 F2 C8 BA 19 6A CE E7 FF 1A CA F9 86 28 EE 34 CE B3 0D 51 83 DF 62 .....GMG.....j.......(.4...Q..b
00000744 67 55 12 D8 EE 9C 2E 5A D4 94 8E E6 B7 A7 0C 10 A1 98 33 EA 61 B9 8C FA 4A B9 C6 1F D4 AE 49 gU.....Z..........3.a...J.....I
00000763 00 AE D5 4C 01 58 66 A3 17 94 C1 83 70 4A 6D A8 E7 44 1C F7 B3 A3 F0 B9 E9 84 59 1C 35 0B F2 ...L.Xf.....pJm..D........Y.5..
00000782 C3 26 A3 71 F7 97 B4 FD 88 79 6B 65 9B 1D 06 E5 CA A5 AB C4 FE 46 2C 18 CB 2F 40 C5 A7 23 8A .&.q.....yke.........F,../@..#.
000007A1 E5 91 A5 83 37 2D 22 7B 00 95 15 05 99 F6 E4 7D 37 FD 5F F1 F3 2F DC D9 7E 4D C7 31 70 97 17 ....7-"{.......}7._../..~M.1p..
000007C0 57 76 8F B4 34 A8 FC A6 2D B9 0D 58 90 09 B0 E0 FF D4 B0 A3 66 EC E2 B3 80 D8 A3 92 EF C1 1F Wv..4...-..X........f..........
000007DF 27 EE B1 19 75 48 A6 2E B9 32 13 53 99 92 89 49 75 1D AF 85 C6 F4 95 25 FF 6E 29 D4 D7 90 C7 '...uH...2.S...Iu......%.n)....
000007FE F0 2E C8 AB 2C 5D A4 89 CB 7B 3A 7E 28 6A 47 D1 E6 EC 83 BB 21 DE FB 50 23 87 BB 3E A3 E5 C5 ....,]...{:~(jG.....!..P#..>...
0000081D 01 D6 A5 94 BC 2F 33 2C 1B D9 7B 5B BC C2 BD 13 51 62 96 9A 59 94 4D 2F 30 02 29 10 E1 BE DC ...../3,..{[....Qb..Y.M/0.)....
0000083C 3C 0C A7 9D 89 82 99 BB C8 CC 27 75 BB 52 FC BB 1D CA 42 37 10 A3 30 CF A0 B4 6B 15 F4 5E B8 <.........'u.R....B7..0...k..^.
0000085B 77 8C 42 DA 8C 86 55 82 D7 02 4D 63 78 C4 6E 10 51 40 60 7F A8 92 1B C9 25 13 1A F0 C6 F5 31 w.B...U...Mcx.n.Q@`.....%.....1
0000087A 58 66 BA 2D B5 31 32 EF 0A DD 54 6B B0 6A 05 C9 1F F0 AD DF 71 01 73 45 63 9D 7C A2 67 0F 84 Xf.-.12...Tk.j......q.sEc.|.g..
00000899 1A F6 83 2E A2 8B C8 E7 75 4F 21 37 19 EE 7C A8 BD 73 DE DC 64 64 AB 58 43 38 C2 AA FC 4A 15 ........uO!7..|..s..dd.XC8...J.
000008B8 08 EC 30 25 30 6F B3 8E 51 04 8B B2 57 82 B7 FE 7B 51 51 C6 4D 8B 4B D2 2B F8 81 E0 5E DF A4 ..0%0o..Q...W...{QQ.M.K.+...^..
000008D7 89 3E CE F3 A3 74 38 55 DC BC E6 5C E2 A7 51 65 9B 08 9C 8A 98 C4 08 48 8F DD D9 C8 E1 1E 02 .>...t8U...\..Qe.......H.......
000008F6 BC 2C 03 98 09 0F 98 59 2E 41 36 33 1F 1F 59 A1 F7 2D E4 AC 83 A6 02 CE 0B 38 31 12 81 B4 12 .,.....Y.A63..Y..-.......81....
00000915 49 2A B7 37 4D A2 6E 5B 22 6B 62 99 72 6E F5 0F 28 4A F4 22 92 0E 59 D5 47 E1 55 01 28 B7 2C I*.7M.n["kb.rn..(J."..Y.G.U.(.,
00000934 6D 2B 3F C1 AD 4C 22 4E 52 93 E4 87 1F 0F 1F CA 6A 30 B0 10 CC 34 41 7C 01 1F CA B0 EC 6E 04 m+?..L"NR.......j0...4A|.....n.
00000953 35 A6 C2 22 86 13 51 70 8C BD 74 DC 33 88 23 7F 52 4B DE A6 BF 13 0D 15 BD C4 B6 E8 4B BB 9F 5.."..Qp..t.3.#.RK..........K..
00000972 BD A0 86 61 78 1D 20 6D 48 4D AA 43 B3 5F E7 BF 38 C1 10 A7 D7 08 23 72 D2 2B 73 DC 43 63 6F ...ax. mHM.C._..8.....#r.+s.Cco
00000991 70 46 3F FE 89 51 A3 AB 80 C0 8D 6B F4 BD 61 83 86 E7 B2 05 49 7D 46 42 20 AE C5 EA 59 59 99 pF?..Q.....k..a.....I}FB ...YY.
000009B0 FD 8B A8 AD EF 6A 95 4C 0A 97 8B 10 8D 9A AE CE D4 EA 7B C1 6E 4C E2 85 0D BA 6F F4 50 32 DD .....j.L..........{.nL....o.P2.
000009CF 15 24 6E E8 14 A0 75 7A E9 21 23 A2 5C FF 24 47 C2 1C F6 50 FB 16 ED 57 4A CF 12 3E 0F 97 14 .$n...uz.!#.\.$G...P...WJ..>...
000009EE EE 82 8A 13 7D A1 63 FF F5 9F 33 BE 90 42 33 BD 58 C0 4D B6 64 51 75 AC 5C C0 B0 9E 65 21 32 ....}.c...3..B3.X.M.dQu.\...e!2
00000A0D 7C 51 8C 18 06 A4 6D 43 58 22 1B CD 62 BF D3 89 3F 5C FE 26 CE 57 BD 20 2E FB B5 22 31 19 CE |Q....mCX"..b...?\.&.W. ..."1..
00000A2C 28 61 58 FF B6 99 DA 31 89 48 B4 E3 47 49 6F 5D 4D 42 64 9D 6A EA F7 05 03 22 B0 C3 D3 52 72 (aX....1.H..GIo]MBd.j...."...Rr
00000A4B E3 C5 98 76 60 83 32 DB 4A 9B 8E 1A BA 0E 36 6D AA 28 FB 75 C5 B1 40 31 80 CD C1 1E 32 B4 9D ...v`.2.J.....6m.(.u..@1....2..
00000A6A 97 A4 47 76 06 67 CC 86 C3 A9 96 F1 71 0E A3 EB 17 95 A1 F9 E4 7E 06 E4 7A 67 58 7E 6A F5 9E ..Gv.g......q........~..zgX~j..
00000A89 CC 99 9B 0C 27 DE 33 01 F8 A5 46 80 71 DF DC 57 F2 03 B6 5F 8D BB 73 D8 19 59 E5 F3 83 7D 69 ....'.3...F.q..W..._..s..Y...}i
00000AA8 2E 7A D6 82 ED AE 1A 10 2A A7 28 E7 BD 78 DA 21 23 78 BF A3 D7 87 79 6A 0F C0 2D 58 BC B2 16 .z......*.(..x.!#x....yj..-X...
00000AC7 78 24 33 64 11 9B BD FB CE 1E 3A 99 2D 94 17 F7 4D 8E 63 A1 C2 19 BC E8 1E 21 1B 4A 9C 1E 59 x$3d......:.-...M.c......!.J..Y
00000AE6 F5 BA CF 4F 4E AC 73 38 84 81 E7 1E 13 69 16 6A DE CA 93 ED 8C A8 D7 46 D6 9F 2A 1D E4 98 62 ...ON.s8.....i.j.......F..*...b
00000B05 6A 66 32 8E 15 1B FA F7 9E 63 A0 A2 A6 6B EF 6C 44 AF 3A B1 F7 65 E3 8D 4C E7 C1 3C A2 19 BA jf2......c...k.lD.:..e..L..<...
00000B24 08 64 1B F2 5F BF 85 8E 3B 31 E3 40 F3 F5 AE BE 8F 5E DD 8E E0 5B 39 BD 63 F9 F3 D5 CC E0 88 .d.._...;1.@.....^...[9.c......
00000B43 AD 80 C9 87 4A CE 5C 06 B1 70 6C 96 FE 92 39 7E AD DD B6 20 E8 E0 2F E3 91 94 C3 09 05 11 63 ....J.\..pl...9~... ../.......c
00000B62 12 F8 2A D5 A6 C2 0A 15 95 41 04 1A 69 D2 B3 4B 82 81 24 FD 3B BF 90 D2 DA CA 1F BC DE B3 3B ..*......A..i..K..$.;.........;
00000B81 A0 68 3B E6 BA 95 D7 77 7E D6 7A 1E C3 E0 FB AF 02 C4 CF D0 DF 82 9E C4 55 0F 09 B2 DA 79 60 .h;....w~.z.............U....y`

```
## Post #9
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-09T12:35:44+00:00
- Post Title: Sanjie PAK

You can fix script  ?
## Post #10
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-02-09T12:50:23+00:00
- Post Title: Sanjie PAK

the problem is he has it listed as is folder when the flag is set to 1 it actually means its a pac inside the pac and needs to be extracted again.
also the compression is figured out it is COMP_LZO1X
here is a extracted csv file.
[monsters.rar](https://xentaxbackup.github.io/file/5048_monsters.rar)
## Post #11
- Username: MrMoonKr
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Oct 16, 2009 2:18 pm
- Post datetime: 2012-02-10T09:43:44+00:00
- Post Title: Sanjie PAK

For pak file

```
get FSIZE long 
get FILES long 

for i = 0 < FILES do 
    getdstring NAME 32 
    get OFFSET long 
    get SIZE long 
    get IS_FOLDER long 
    get unk2 long 

    if IS_FOLDER = 1 
        get FOLDER_NAME basename
        string FOLDER_NAME += "/"
        string FOLDER_NAME += NAME 
        string FOLDER_NAME += ".pak"
        print %FOLDER_NAME% 
        log FOLDER_NAME OFFSET SIZE 
    else 
        get TEMP basename
        string TEMP += "/"
        string TEMP += NAME 
        print %TEMP% 
        log TEMP OFFSET SIZE  
    endif 
next i  


```


For asset file

```

get NAME basename
#get NAME filename
get EXTNAME extension
print %NAME%
string NAME += ".unpacked."
string NAME += EXTNAME
print %NAME%

idstring "NZ\x0B\x00"
get FSIZE long
get SIZE long
print %FSIZE% 
print %SIZE%

clog NAME 12 SIZE FSIZE

```


Uncompressed apg file format

```
// 010 Editor v3.1 Binary Template
//
// File     : SanjieTemplateAPG.bt
// Author   : MrMoonKr
// Revision : 0.1
// Purpose  : Sanjie pak file analyze
// Changes  :  
//
// ( 2012/02/10/Fri )
//          : refactoring
//          : http://sj.wanku.com/
//
//////////////////////////////////////////////////////////////////////////


//------------------------------------------------------------------------

//#include "CommonTemplate.bt"


//------------------------------------------------------------------------

struct APGHeader ;

typedef struct ( uint32 size )
{
    char                mFourCC[4] ;        ///< "AP\x18\x00"
    char                mData[size-4] ;     ///< 

} APGData < bgcolor = cLtRed , read = ReadAPGData > ;

string ReadAPGData( APGData& data )
{
    string s = "(no data)" ;
    SPrintf( s , "( FourCC : %s )" ,
        data.mFourCC 
        ) ;
    return s ;
}

//------------------------------------------------------------------------

typedef struct 
{
    uint32              mIndex ;
    uint32              mSize ;

} APGChunk < bgcolor = cLtPurple , read = ReadAPGChunk > ;

string ReadAPGChunk( APGChunk& chunk )
{
    string s = "(no data)" ;
    SPrintf( s , "( Size : %d )( Index : %d )" ,
        chunk.mSize ,
        chunk.mIndex
        ) ;
    return s ;
}

//------------------------------------------------------------------------

/**
    archive file header
*/
typedef struct
{
    char                mFourCC[4] ;        ///< "AG\x48\x00"
    uint32              mChunkCount ;
    local uint32 i=0 ;
    for ( i=0 ; i < mChunkCount ; ++i )
    {
        APGChunk        mChunkArray ;
    }
    
    local uint32 bookMark = FTell() ;
    local uint32 nextMark = bookMark ;
    for ( i=0 ; i < mChunkCount ; ++i )
    {
        APGData         mChunkDataArray( mChunkArray[i].mSize ) ;

        nextMark        += mChunkArray[i].mSize ;

    }

} APGHeader < bgcolor = cLtGray , read = ReadAPGHeader > ;

string ReadAPGHeader( APGHeader& header )
{
    string s = "(no data)" ;
    SPrintf( s , "( FourCC : %s )" ,
        header.mFourCC
        ) ;
    return s ;
}

//////////////////////////////////////////////////////////////////////////

LittleEndian() ;
//BigEndian() ;


APGHeader               gHeader ;


```


i cannot figure out APGData , help me ^^;;;
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-10T10:04:55+00:00
- Post Title: Sanjie PAK

That method for unpacking the nested archives doesn't work in general.
For this particular game, they store the size of the archive.

For their other game, like
[viewtopic.php?p=66559#p66559](http://forum.xentax.com/viewtopic.php?p=66559#p66559)

They no longer store the size of the archive but you will still need to unpack it.
They're both the same format...except one just forces you to use recursion.
