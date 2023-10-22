## Post #1
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2021-07-24T22:17:20+00:00
- Post Title: [DOS] Street Rod (1989)

You can download the game here: [https://www.streetrodonline.com/downloads/](https://www.streetrodonline.com/downloads/)

The file structure of Street Rod and Street Rod SE are the same. Here is what I have found out so far about the files from SRSE.

HOT_DATA

// driver stats
byte unknown (maybe skill level?)
byte unknown
byte unknown
byte unknown
short sprite_index picture (sprite_index: the first index in the table AC 04 = 1196d, the actual index is 196d, so you have to substract 1000d from each index)
short string_offset name (string_offset: offset of the string chunk starts at file offset 0x76F)
byte preferred car?
@0x0000

```
00 12 0C 00 AA 04 18 05 FF FF FF 00 00 00 00 00 00 00
00 14 0A 00 B9 04 1F 05 FF FF FF 00 00 00 00 00 00 00
00 12 0C 00 AD 04 25 05 FF FF FF 00 00 00 00 00 00 00
01 12 0A 00 AE 04 2B 05 FF FF FF 00 00 00 00 00 00 00
01 12 0C 00 BA 04 32 05 FF FF FF 00 00 00 00 00 00 00
01 12 0A 00 BD 04 39 05 FF FF FF 00 00 00 00 00 00 00
01 12 07 00 AB 04 3F 05 FF FF FF 00 00 00 00 00 00 00
01 12 07 00 B8 04 46 05 FF FF FF 00 00 00 00 00 00 00
01 12 07 00 BB 04 4D 05 FF FF FF 00 00 00 00 00 00 00
01 10 0A 00 B3 04 53 05 FF FF FF 00 00 00 00 00 00 00
02 10 07 00 C0 04 5A 05 FF FF FF 00 00 00 00 00 00 00
02 10 07 00 B2 04 60 05 FF FF FF 00 00 00 00 00 00 00
02 10 07 00 AF 04 65 05 FF FF FF 00 00 00 00 00 00 00
02 10 07 00 B5 04 6E 05 FF FF FF 00 00 00 00 00 00 00
02 0F 07 00 B7 04 76 05 FF FF FF 00 00 00 00 00 00 00
02 0F 05 00 B6 04 7D 05 FF FF FF 00 00 00 00 00 00 00
02 0E 05 00 B4 04 82 05 FF FF FF 00 00 00 00 00 00 00
02 0C 05 00 BC 04 89 05 FF FF FF 00 00 00 00 00 00 00
02 0B 05 00 BE 04 90 05 FF FF FF 00 00 00 00 00 00 00
02 0B 05 00 BF 04 96 05 FF FF FF 00 00 00 00 00 00 00
02 0A 04 00 DC 04 9E 05 19 00 00 00 00 00 08 00 00 00
```


// car stats
short price
byte unknown
byte next in list/order in news letter?
byte transmission/tires/brand (1=GM, 2=Ford, 4=Chrysler)
byte carb/manifold/engine
short string_offset description
short sprite_index chassis

/* something like that:
struct {
   unsigned int transmission : 2;
   unsigned int tires : 2;
   unsigned int brand : 4;
} parts;

struct {
   unsigned int carb : 2;
   unsigned int manifold : 4;
   unsigned int engine : 2;
} engine;
*/
@0x018C

```
41 05 01 02 41 01 30 00 10 04
FC 08 07 03 A1 5A 6B 00 17 04
80 0C 08 04 51 4A AE 00 18 04
98 08 05 05 D1 4A DF 00 1D 04
2E 09 05 06 91 8A 0C 01 1E 04
9F 01 00 07 01 00 43 01 24 04
CA 08 04 08 01 4A 6E 01 25 04
9E 07 04 09 41 49 AF 01 58 04
01 04 03 0A 91 10 D7 01 59 04
CF 03 02 0B 01 01 08 02 5E 04
5A 0A 07 0C 91 4A 3C 02 5F 04
1C 0C 06 0D A2 8A 71 02 66 04
20 08 05 0E 82 A1 A1 02 67 04
61 08 04 0F 12 4A C8 02 6B 04
84 03 02 10 42 00 F8 02 6F 04
A9 01 01 11 02 00 28 03 79 04
74 0E 08 12 E2 A2 5D 03 7D 04
48 0D 06 13 E2 02 96 03 84 04
A3 02 00 14 42 00 CE 03 85 04
6E 0F 08 15 E2 A2 FB 03 8C 04
59 06 02 16 44 01 31 04 8D 04
28 0A 07 17 A4 4A 6F 04 93 04
52 03 01 18 14 10 A3 04 94 04
C4 09 03 FF 54 89 C7 04 9B 04
00 00 08 00 E1 A2 03 05 B1 04
```


//overlay sprite offsets
short index car_shape (back of car during race)
short sprite_index chopped_roof
short sprite_index air_scoop
short sprite_index rear_bumper
short sprite_index front_bumper
@0x0290

```
03 00 13 04 A0 04 11 04 12 04
01 00 16 04 A0 04 15 04 14 04
04 00 28 04 A1 04 1A 04 19 04
01 00 27 04 A0 04 81 04 1B 04
02 00 9F 04 A0 04 1F 04 20 04
02 00 23 04 A1 04 22 04 9C 04
02 00 26 04 A1 04 5A 04 86 04
02 00 57 04 A0 04 1A 04 19 04
01 00 5C 04 A0 04 81 04 5B 04
01 00 5D 04 A0 04 1C 04 69 04
04 00 62 04 9E 04 60 04 61 04
03 00 65 04 9E 04 63 04 64 04
03 00 6A 04 A0 04 68 04 64 04
02 00 6E 04 9E 04 6C 04 6D 04
02 00 78 04 9E 04 70 04 77 04
01 00 7C 04 A1 04 7A 04 7B 04
04 00 80 04 A0 04 7E 04 7F 04
02 00 83 04 A0 04 81 04 82 04
02 00 88 04 A0 04 81 04 87 04
04 00 8B 04 9E 04 89 04 8A 04
03 00 D3 04 9E 04 8F 04 8E 04
02 00 92 04 A0 04 90 04 91 04
01 00 97 04 A1 04 95 04 96 04
01 00 9A 04 A1 04 98 04 99 04
00 00 00 00 00 00 00 00 00 00
```


//sprite positions
positions tires, chopped roof, stripped bumpers, decals
byte offset_x_rear_tire
byte offset_x_front_tire
byte offset_x_driver
byte offset_y_driver
byte offset_x_chopped_roof
byte offset_x_air_scoop
byte offset_y_air_scoop
byte offset_y_rear_bumper
byte offset_x_front_bumper
byte offset_y_front_bumper
byte offset_x_decal
byte offset_y_decal
// offset x: starts from left side of chassis sprite
// offset y: starts from top of chassis sprite
// offset x rear bumper is always 0
// offset y chopped roof  is always 0

@0x0394

```
2A BC 70 13 18 AC 09 28 80 28 67 19
38 CC 7C 12 40 B8 05 1F E8 20 7C 16
2E C8 7D 14 18 B8 06 22 E0 22 73 14
32 C8 78 12 40 B8 07 26 E0 1E 73 15
28 C0 75 12 38 B8 06 1F D8 18 70 14
38 CE 7E 12 40 C0 05 21 E8 1A 76 11
3E E0 90 10 50 C8 05 16 F8 1C 83 12
2E D0 81 13 40 C8 07 23 E8 23 78 16
34 D0 7E 12 48 C0 04 1F F0 1C 7B 10
3C D8 86 12 48 D0 05 1C F0 1C 82 11
32 C4 7C 12 38 B8 05 20 E8 1E 72 11
18 AE 62 16 00 90 0B 28 D0 23 47 18
18 BA 66 14 38 A0 09 25 E0 23 60 1A
2A BE 7A 12 38 B8 07 24 D8 1B 73 16
34 CE 84 12 40 B8 08 28 E8 20 80 19
38 D2 82 12 48 C4 06 22 F0 21 7F 13
38 C8 7B 12 48 C0 06 18 E8 20 76 12
36 CA 7D 12 40 C4 06 20 E8 1E 7C 12
2E C2 77 12 38 B0 06 22 E0 1C 74 11
32 C2 70 12 38 B0 07 12 E0 19 6C 11
24 B2 6D 13 30 A8 07 24 D0 21 67 17
36 CA 7D 12 40 C0 06 18 E8 20 7A 11
32 CE 7F 12 40 C8 06 1D F0 1F 7A 11
32 C6 7F 12 48 C0 04 1B E0 1B 7B 0F
24 B8 57 15 00 00 00 00 00 00 00 00
```


//click boxes garage
// for rear bumper, chopped roof, transmission, engine, front bumper
byte offset_x
byte offset_y
byte width
byte height

@0x04CC

```
00 28 11 0F 18 00 90 0C 88 30 28 0F A0 10 46 0F E0 28 19 0A
00 20 11 0F 40 00 70 0C A0 2C 28 0F B0 0E 46 0F E8 20 19 0A
00 22 11 0F 18 00 9C 0C A0 2A 28 0F B0 0F 46 0F E8 22 19 0A
00 20 11 0F 40 00 70 0C A0 2D 28 0F B0 0F 46 0F E8 20 19 0A
01 20 11 0F 38 00 70 0C 90 2D 28 0F A8 0E 46 0F E0 20 19 0A
00 21 11 0F 40 00 70 0C A0 28 28 0F B0 0C 46 0F E8 1B 19 0A
00 1A 11 0F 50 00 70 0C C0 2C 28 0F C0 0F 46 0F F8 1C 19 0A
00 24 11 0F 40 00 78 0C A8 30 28 0F B8 0F 46 0F E8 24 19 0A
00 1D 11 0F 48 00 68 0C A0 28 28 0F B0 0C 46 0F F0 1C 19 0A
06 1B 11 0F 48 00 70 0C B0 28 28 0F B8 0C 46 0F F8 1B 19 0A
00 20 11 0F 38 00 70 0C 98 28 28 0F B0 0E 46 0F E8 1C 19 0A
00 28 11 0F 00 00 88 0C 70 30 28 0F 88 14 46 0F D0 28 19 0A
01 25 11 0F 38 00 60 0C 80 34 28 0F 98 12 46 0F D8 24 19 0A
00 24 11 0F 38 00 70 0C 98 30 28 0F A8 0A 46 0F D8 25 19 0A
00 28 11 0F 40 00 70 0C A8 32 28 0F B0 10 46 0F F0 20 19 0A
01 24 11 0F 48 00 70 0C A8 28 28 0F B8 0C 46 0F F0 22 19 0A
00 18 11 0F 48 00 60 0C 98 28 28 0F B0 0F 46 0F E8 20 19 0A
00 1F 11 0F 40 00 70 0C A0 28 28 0F B8 0F 46 0F E8 1E 19 0A
00 21 11 0F 40 00 60 0C 98 28 28 0F A8 0C 46 0F E0 1C 19 0A
00 12 11 0F 38 00 68 0C 90 28 28 0F A8 0F 46 0F E0 1A 19 0A
00 26 11 0F 30 00 68 0C 88 32 28 0F 98 0C 46 0F D0 22 19 0A
00 18 11 0F 40 00 70 0C A0 28 28 0F B0 0F 46 0F E8 20 19 0A
00 17 11 0F 40 00 70 0C A0 28 28 0F B8 0E 46 0F F0 1F 19 0A
00 12 11 0F 48 00 68 0C 98 26 28 0F B0 0C 46 0F E0 1B 19 0A
00 24 11 0F 40 00 64 0C 99 28 28 0F B4 12 46 0F E7 25 19 0A
```


// click boxes gas station
// for tank cap, rear windshield, front windshield
byte offset_x
byte offset_y
// width and height are hard-coded

@0x06D4

```
58 20 28 05 90 00
5E 22 40 00 A0 0A
28 1A 18 00 98 00
50 18 48 00 A0 00
40 17 40 05 98 00
68 14 48 04 A8 00
50 14 58 04 B0 00
48 14 48 05 A0 00
60 1C 48 02 A0 00
68 18 48 04 A8 00
50 14 40 04 98 00
28 17 00 00 78 00
48 24 38 04 88 00
50 1C 38 04 98 00
60 26 40 05 A0 00
40 14 50 04 A8 00
60 16 48 03 A0 00
60 17 48 05 A6 00
58 1D 38 04 90 00
58 18 40 02 90 00
50 1A 30 04 90 00
58 19 48 05 A0 00
48 11 40 05 A0 00
48 12 48 01 A0 00
00 00 00 00 00 00
```


// strings
@0x0770

```
2D 64 72 20 63 6F 75 70 65 2E 00 47 6F 6F 64 20  -dr coupe..Good 
77 6F 72 6B 20 63 61 72 2E 20 24 33 38 35 00 02  work car. $385..
31 39 34 36 20 43 68 65 76 72 6F 6C 65 74 20 46  1946 Chevrolet F
6C 65 65 74 6C 69 6E 65 20 53 65 64 61 6E 2E 00  leetline Sedan..
56 2D 38 20 33 73 70 2E 20 72 75 6E 73 20 67 6F  V-8 3sp. runs go
6F 64 2E 20 24 31 33 34 35 00 02 31 39 35 33 20  od. $1345..1953 
42 75 69 63 6B 20 53 6B 79 6C 61 72 6B 20 43 6F  Buick Skylark Co
6E 76 65 72 74 69 62 6C 65 2E 00 34 20 62 72 6C  nvertible..4 brl
2E 20 34 73 70 2E 20 43 61 6C 69 66 6F 72 6E 69  . 4sp. Californi
61 20 63 61 72 2E 20 24 32 33 30 30 00 02 31 39  a car. $2300..19
35 35 20 43 68 65 76 72 6F 6C 65 74 20 4E 6F 6D  55 Chevrolet Nom
61 64 20 57 61 67 6F 6E 2E 00 43 75 73 74 6F 6D  ad Wagon..Custom
2E 20 46 61 73 74 2E 20 24 33 32 30 30 00 02 31  . Fast. $3200..1
39 35 35 20 4F 6C 64 73 6D 6F 62 69 6C 65 20 39  955 Oldsmobile 9
38 2E 00 42 69 67 20 56 2D 38 2E 20 42 69 67 20  8..Big V-8. Big 
63 61 72 2E 20 24 32 32 30 30 00 02 31 39 35 37  car. $2200..1957
20 43 68 65 76 72 6F 6C 65 74 20 42 65 6C 2D 41   Chevrolet Bel-A
69 72 2E 00 4F 6E 65 20 6F 77 6E 65 72 2E 20 4D  ir..One owner. M
61 6E 79 20 65 78 74 72 61 73 2E 20 24 32 33 35  any extras. $235
30 00 02 31 39 35 38 20 42 75 69 63 6B 20 53 70  0..1958 Buick Sp
65 63 69 61 6C 2E 00 52 75 6E 73 2E 20 47 72 65  ecial..Runs. Gre
61 74 20 62 75 79 2E 20 24 34 31 35 00 02 31 39  at buy. $415..19
35 39 20 43 61 64 69 6C 6C 61 63 20 45 6C 64 6F  59 Cadillac Eldo
72 61 64 6F 20 43 6F 6E 76 65 72 74 69 62 6C 65  rado Convertible
2E 00 41 75 74 6F 2E 20 53 75 6E 20 6C 6F 76 65  ..Auto. Sun love
72 73 20 63 61 72 2E 20 24 32 32 35 30 00 02 31  rs car. $2250..1
39 35 35 20 43 68 65 76 72 6F 6C 65 74 20 44 65  955 Chevrolet De
6C 72 61 79 2E 00 56 2D 38 2E 20 33 73 70 2E 20  lray..V-8. 3sp. 
24 31 39 35 30 00 02 31 39 36 31 20 43 68 65 76  $1950..1961 Chev
72 6F 6C 65 74 20 49 6D 70 61 6C 61 2E 00 36 20  rolet Impala..6 
70 61 63 6B 2E 20 4E 65 77 20 74 69 72 65 73 2E  pack. New tires.
20 24 31 30 32 35 00 02 31 39 36 32 20 4F 6C 64   $1025..1962 Old
73 6D 6F 62 69 6C 65 20 53 74 61 72 66 69 72 65  smobile Starfire
2E 00 4D 75 73 74 20 73 65 65 2E 20 4C 69 6B 65  ..Must see. Like
20 6E 65 77 2E 20 24 39 37 35 00 02 31 39 36 33   new. $975..1963
20 42 75 69 63 6B 20 52 69 76 69 65 72 61 2E 00   Buick Riviera..
43 72 75 69 73 65 72 2E 20 42 65 61 75 74 69 66  Cruiser. Beautif
75 6C 2E 20 46 61 73 74 2E 20 24 32 36 35 30 00  ul. Fast. $2650.
02 31 39 33 34 20 46 6F 72 64 20 57 6F 6F 64 69  .1934 Ford Woodi
65 2E 00 46 75 6C 6C 20 72 61 63 65 2E 20 55 6E  e..Full race. Un
62 65 61 74 61 62 6C 65 2E 20 24 33 31 30 30 00  beatable. $3100.
02 31 39 33 36 20 46 6F 72 64 20 43 6F 75 70 65  .1936 Ford Coupe
2E 00 34 73 70 2E 20 56 2D 38 2E 20 48 6F 74 2E  ..4sp. V-8. Hot.
20 24 32 30 38 30 00 02 31 39 35 30 20 46 6F 72   $2080..1950 For
64 20 43 72 65 73 74 6C 69 6E 65 72 2E 00 4F 6E  d Crestliner..On
65 20 6F 77 6E 65 72 2E 20 42 61 62 69 65 64 2E  e owner. Babied.
20 24 32 31 34 35 00 02 31 39 35 31 20 4D 65 72   $2145..1951 Mer
63 75 72 79 20 4D 6F 6E 74 65 72 65 79 2E 00 53  cury Monterey..S
65 65 20 74 6F 20 61 70 70 72 65 63 69 61 74 65  ee to appreciate
2E 20 24 39 30 30 00 02 31 39 35 37 20 4C 69 6E  . $900..1957 Lin
63 6F 6C 6E 20 43 61 70 72 69 2E 00 4E 65 65 64  coln Capri..Need
73 20 77 6F 72 6B 2E 20 48 61 73 20 70 6F 74 65  s work. Has pote
6E 74 69 61 6C 2E 20 24 34 32 35 00 02 31 39 36  ntial. $425..196
30 20 46 6F 72 64 20 54 68 75 6E 64 65 72 62 69  0 Ford Thunderbi
72 64 2E 00 56 65 72 79 20 66 61 73 74 2E 20 4C  rd..Very fast. L
6F 74 73 20 6F 66 20 65 78 74 72 61 73 2E 20 24  ots of extras. $
33 37 30 30 00 02 31 39 36 33 20 46 6F 72 64 20  3700..1963 Ford 
47 61 6C 61 78 69 65 20 35 30 30 58 4C 2E 00 42  Galaxie 500XL..B
69 67 20 56 2D 38 2E 20 52 61 63 69 6E 67 20 73  ig V-8. Racing s
6C 69 63 6B 73 2E 20 24 33 34 30 30 00 02 31 39  licks. $3400..19
36 33 20 46 6F 72 64 20 46 61 6C 63 6F 6E 20 53  63 Ford Falcon S
70 72 69 6E 74 2E 00 44 61 69 6C 79 20 44 72 69  print..Daily Dri
76 65 72 2E 20 24 36 37 35 00 02 31 39 36 33 20  ver. $675..1963 
46 6F 72 64 20 54 2D 62 69 72 64 20 52 6F 61 64  Ford T-bird Road
73 74 65 72 2E 00 55 6C 74 72 61 20 66 61 73 74  ster..Ultra fast
2E 20 53 6C 69 63 6B 73 2E 20 24 33 39 35 30 00  . Slicks. $3950.
02 31 39 34 38 20 43 68 72 79 73 6C 65 72 20 54  .1948 Chrysler T
6F 77 6E 20 26 20 43 6F 75 6E 74 72 79 20 43 6F  own & Country Co
6E 76 2E 00 43 6C 61 73 73 69 63 2E 20 4C 6F 77  nv..Classic. Low
20 6D 69 6C 65 73 2E 20 24 31 36 32 35 00 02 31   miles. $1625..1
39 35 36 20 43 68 72 79 73 6C 65 72 20 4E 65 77  956 Chrysler New
20 59 6F 72 6B 65 72 2E 00 43 75 73 74 6F 6D 2E   Yorker..Custom.
20 42 69 67 20 62 6C 6F 63 6B 2E 20 24 32 36 30   Big block. $260
30 00 02 31 39 35 37 20 50 6C 79 6D 6F 75 74 68  0..1957 Plymouth
20 46 75 72 79 2E 00 4E 69 63 65 20 63 61 72 2E   Fury..Nice car.
20 24 38 35 30 00 02 31 39 36 30 20 50 6C 79 6D   $850..1960 Plym
6F 75 74 68 20 43 6F 6E 76 65 72 74 69 62 6C 65  outh Convertible
2E 00 4E 65 77 20 74 69 72 65 73 2E 20 4E 65 76  ..New tires. Nev
65 72 20 77 72 65 63 6B 65 64 2E 20 24 32 35 30  er wrecked. $250
30 00 01 31 39 36 33 20 43 6F 72 76 65 74 74 65  0..1963 Corvette
00 01 4D 69 6B 65 00 01 52 61 6C 70 68 00 01 4B  ..Mike..Ralph..K
69 72 6B 00 01 42 69 66 66 00 01 42 75 74 63 68  irk..Biff..Butch
00 01 57 61 6C 6C 79 00 01 43 68 69 70 00 01 45  ..Wally..Chip..E
64 64 69 65 00 01 45 72 6E 69 65 00 01 44 69 63  ddie..Ernie..Dic
6B 00 01 53 74 65 76 65 00 01 4A 6F 68 6E 00 01  k..Steve..John..
4A 69 6D 00 01 43 68 61 72 6C 69 65 00 01 47 65  Jim..Charlie..Ge
6F 72 67 65 00 01 43 6C 79 64 65 00 01 54 6F 6D  orge..Clyde..Tom
00 01 45 72 69 63 61 00 01 53 70 69 6B 65 00 01  ..Erica..Spike..
42 69 6C 6C 00 01 56 69 6E 6E 69 65 00 01 54 68  Bill..Vinnie..Th
65 20 4B 69 6E 67 00 01 54 68 65 20 47 65 65 6B  e King..The Geek
00                                               .
```


/* values from above with line breaks
.1939 Pontiac 2-dr coupe..Good work car. $385.
.1946 Chevrolet Fleetline Sedan..V-8 3sp. runs good. $1345.
.1953 Buick Skylark Convertible..4 brl. 4sp. California car. $2300.
.1955 Chevrolet Nomad Wagon..Custom. Fast. $3200.
.1955 Oldsmobile 98..Big V-8. Big car. $2200.
.1957 Chevrolet Bel-Air..One owner. Many extras. $2350.
.1958 Buick Special..Runs. Great buy. $415.
.1959 Cadillac Eldorado Convertible..Auto. Sun lovers car. $2250.
.1955 Chevrolet Delray..V-8. 3sp. $1950.
.1961 Chevrolet Impala..6 pack. New tires. $1025.
.1962 Oldsmobile Starfire..Must see. Like new. $975.
.1963 Buick Riviera..Cruiser. Beautiful. Fast. $2650.
.1934 Ford Woodie..Full race. Unbeatable. $3100.
.1936 Ford Coupe..4sp. V-8. Hot. $2080.
.1950 Ford Crestliner..One owner. Babied. $2145.
.1951 Mercury Monterey..See to appreciate. $900.
.1957 Lincoln Capri..Needs work. Has potential. $425.
.1960 Ford Thunderbird..Very fast. Lots of extras. $3700.
.1963 Ford Galaxie 500XL..Big V-8. Racing slicks. $3400.
.1963 Ford Falcon Sprint..Daily Driver. $675.
.1963 Ford T-bird Roadster..Ultra fast. Slicks. $3950.
.1948 Chrysler Town & Country Conv..Classic. Low miles. $1625.
.1956 Chrysler New Yorker..Custom. Big block. $2600.
.1957 Plymouth Fury..Nice car. $850.
.1960 Plymouth Convertible..New tires. Never wrecked. $2500.
.1963 Corvette.
.Mike.
.Ralph.
.Kirk.
.Biff.
.Butch.
.Wally.
.Chip.
.Eddie.
.Ernie.
.Dick.
.Steve.
.John.
.Jim.
.Charlie.
.George.
.Clyde.
.Tom.
.Erica.
.Spike.
.Bill.
.Vinnie.
.The King.
.The Geek.
*/

// padding/garbage after strings chunk 
@0x0D21

```
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
00 00 00 00 00 00 00 00 00 00 00 FF FF 0E 37 B1  ...........ÿÿ.7±
01 F6 37 DD 1B 00 00 00 00 00 00 00 00 00 00 00  .ö7Ý............
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................
00 BE 10 3B 43 5F 46 49 4C 45 5F 49 4E 46 4F 00  .¾.;C_FILE_INFO.
E8 56 70 02 00 00 00 00 00 00 00 00 00 00 00 00  èVp.............
00 00 A1 19 03 1E 00 00 00 14 00 C1 C1 C1 41 41  ..¡........ÁÁÁAA
01 00 00 00 00 00 00 00 00 00 00 00              ............
```


// decal strings
@0x0EAE

```
27 45 61 67 6C 65 27 00 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E  'Eagle'..................
27 4E 6F 74 20 34 20 73 61 6C 65 27 00 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E  'Not 4 sale'.............
27 56 65 74 65 72 61 6E 27 00 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E  'Veteran'................
27 48 65 6C 6C 27 00 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E  'Hell'...................
27 48 61 77 61 69 69 27 00 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E  'Hawaii'.................
27 42 61 6E 61 6E 61 20 43 6C 75 62 27 00 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E  'Banana Club'............
27 45 78 70 6C 6F 73 69 76 65 27 00 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E 2E        'Explosive'............
```


// unknown
@0x0F74

```
B4 00
96 00
AF 00
96 00
7D 00
8C 00
78 00
64 00
3C 00
2D 00
1E 00
37 00
28 00
14 00
32 00
1E 00
0A 00
28 00
3C 00
5A 00
46 00
41 00
19 00
5A 00
46 00
0F 00
5A 00
23 00
00 00
```


// decal info
short sprite_index decal
short padding left
short padding top
@0x0FB0

```
A8 04 03 00 01 00
A7 04 00 00 03 00
A6 04 06 00 01 00
A5 04 0C 00 02 00
A4 04 02 00 01 00
A2 04 04 00 02 00
A3 04 04 00 01 00
```
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2021-07-24T22:24:40+00:00
- Post Title: [DOS] Street Rod (1989)

Extracted sprites from LIB2
## Post #3
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2021-07-24T22:27:18+00:00
- Post Title: [DOS] Street Rod (1989)

HALL_DAT

short numEntries (= 0x0A)

the remaining bytes are XORed with 0x80

each entry contains two zero-terminated strings
name (16 bytes) and score (7 bytes)

for instance:

```
53 41 4E 59 4F 00 00 00 00 00 00 00 00 00 00 00 31 38 31 35 00 00 00
```

corresponds to 
```
SANYO...........1815...
```
## Post #4
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2021-07-24T23:09:38+00:00
- Post Title: [DOS] Street Rod (1989)

LIB1/LIB2

header:
short numEntries

for each entry:
short width
short height
short lengthDecoded // = width * height / 2
byte type // 0, 1, 2
byte[16] directory
byte alwaysZero
int offset
short lengthEncoded

RLE-encoded sprites:
for each entry:
byte[lengthEncoded] data

in detail:
byte magicWord // = 0xBC

0x00 and 0xFF are run-length encoded
00/FF is followed by the number of occurrences (+ 1)
for instance:
00 02 = 3 occurrences of 00
FF 04 = 5 occurrences of FF

directory:
up to 16 entries
00 indicates end of directory
each occurrence of the entries in the actual pixel data will be replaced with one/multiple 00/FF
according to this table (hard-coded in SR.EXE / SRSE.EXE @ 0x3CA23):
01010203040203050606040707050808
00FF000000FFFF00FF00FFFF00FFFF00
In the first line are the number of times that the value on the second line will be written to memory. 
source: [https://moddingwiki.shikadi.net/wiki/Street_Rod](https://moddingwiki.shikadi.net/wiki/Street_Rod)

color depth: 4 (if type = 0 or 1) or 1 (if type = 2)
each bitmap consists of 4 (or 1) monochrome bitmaps

palette:

```
	(byte) 0x00, (byte) 0x00, (byte) 0x00, (byte) 0x00, (byte) 0x00, (byte) 0x00, (byte) 0x00, (byte) 0x00, 
	(byte) 0x55, (byte) 0x55, (byte) 0x55, (byte) 0x00, (byte) 0xAA, (byte) 0xAA, (byte) 0xAA, (byte) 0x00, 
	(byte) 0xFF, (byte) 0xFF, (byte) 0xFF, (byte) 0x00, (byte) 0xAA, (byte) 0xAA, (byte) 0xAA, (byte) 0x00, 
	(byte) 0xFF, (byte) 0x55, (byte) 0x55, (byte) 0x00, (byte) 0xAA, (byte) 0x00, (byte) 0x00, (byte) 0x00, 
	(byte) 0xAA, (byte) 0xAA, (byte) 0x00, (byte) 0x00, (byte) 0x00, (byte) 0xAA, (byte) 0x00, (byte) 0x00, 
	(byte) 0x00, (byte) 0x00, (byte) 0xAA, (byte) 0x00, (byte) 0x55, (byte) 0x55, (byte) 0xFF, (byte) 0x00, 
	(byte) 0xAA, (byte) 0x00, (byte) 0xAA, (byte) 0x00, (byte) 0x55, (byte) 0xFF, (byte) 0x55, (byte) 0x00, 
	(byte) 0x00, (byte) 0x55, (byte) 0xAA, (byte) 0x00, (byte) 0x55, (byte) 0xFF, (byte) 0xFF, (byte) 0x00
};
if (type == 1) {
	palette[2] = (byte) 0xFF;
	
	palette[12] = (byte) 0xFF;
	palette[13] = (byte) 0x55;
	palette[14] = (byte) 0xFF;
} else if (type == 2) {
	palette[0] = palette[1] = palette[2] = (byte) 0xFF;
}
```
## Post #5
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2021-08-07T19:44:48+00:00
- Post Title: [DOS] Street Rod (1989)

car stats mapping

I decoded the two bytes like this:

```
tires =        (byte) ((data[4] & 0B00110000) >> 4);
brand =        (byte) ((data[4] & 0B00000111));
carb =         (byte) ((data[5] & 0B11000000) >> 6);
manifold =     (byte) ((data[5] & 0B00111000) >> 3);
engine =       (byte) ((data[5] & 0B00000011));
```


// brands: 1 = GM, 2 = Ford, 4 = Chrysler
// engine 0
GM V-6 engine
Ford V-6 engine
Chrysler V-6 engine
// engine 1
GM V-8 engine. 283 cu.in.
Ford V-8 engine. 292 cu.in.
Chrysler V-8 eng 285 cu.in.
// engine 2
GM V-8 engine. 327 cu.in.
Ford V-8 eng 351 cu.in.
Chrysler V-8 eng 340 cu.in.
// transmission 0
Auto Trnsmsn GM.
Auto Trnsmsn Ford
Auto Trnsmsn Chrysler.
// transmission 1
Trnsmsn 3-spd GM.
Trnsmsn 3-spd Ford.
Trnsmsn 3-spd Chrysler.
// transmission 2
Trnsmsn 4-spd. GM.
Trnsmsn 4-spd. Ford.
Trnsmsn 4-spd. Chrysler.
Trnsmsn 4-spd. Fits all.
// transmission 3
Racing 4-spd. GM.
Racing 4-spd. Ford.
Racing 4-spd. Chrysler.
// carb 0
2-brl. carb. Fits all.
// carb 1
4-brl. carb. Fits all.
// carb 2
4-brl racing carb. Fits all models.
// manifold 0
GM 2-brl manifold.
Ford 2-brl manifold.
Chrysler 2-brl manifold.
// manifold 1
GM 4-brl manifold.
Ford 4-brl manifold.
Chrysler 4-brl manifold.
// manifold 3
GM manifold. For 2-4brl.carbs.
Ford manifold. For 2-4brl.carbs.
Chrysler manifold. For 2-4brl.carbs.
// manifold 2
GM manifold. For 3-2brl.carbs.
Ford manifold. For 3-2brl.carbs.
Chrysler manifold. For 3-2brl.carbs.
// manifold 4
GM racing manifold.
Ford racing manifold.
Chrysler racing manifold.
// tires 0
Tires.
// tires 1
Tires. Brand name.
// tires 2
Racing slicks.
## Post #6
- Username: cdoublejj
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Feb 05, 2022 6:00 am
- Post datetime: 2022-02-04T22:03:49+00:00
- Post Title: [DOS] Street Rod (1989)

You pulled sprites!!! Dude that's incredible!
## Post #7
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2022-12-27T05:56:54+00:00
- Post Title: [DOS] Street Rod (1989)

[Download Street Rod Toolkit](https://retrogamesvault.com/streetrod)
## Post #8
- Username: StreetrodRB
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 11, 2023 7:26 pm
- Post datetime: 2023-04-11T11:29:39+00:00
- Post Title: [DOS] Street Rod (1989)

Wow this is amazing!

Does this mean you can freely adjuse the images from SR2? And can you alter the text and background images as well?

Would I be able to do it myself (I am a complete modding noob, so it would have to be very basic)?
## Post #9
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2023-05-19T20:55:49+00:00
- Post Title: [DOS] Street Rod (1989)

> Reply from StreetrodRB ↑Tue Apr 11, 2023 7:29 pm at Tue Apr 11, 2023 7:29 pm
>
> 
Wow this is amazing!

Does this mean you can freely adjuse the images from SR2? And can you alter the text and background images as well?

Would I be able to do it myself (I am a complete modding noob, so it would have to be very basic)?
Hi, the tool only works for Street Rod 1 and only for images.
Text can be found in HOT_DATA, it can be altered with a hex editor.

When you edit an image, don't change its dimensions, color depth or palette.
If you're using GIMP to edit the image, make sure you check this checkbox in the export dialog:
"Compatibility Options: Do not write color space information"
