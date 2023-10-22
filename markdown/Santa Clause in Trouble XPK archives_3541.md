## Post #1
- Username: fifarulez
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-18T20:57:15+00:00
- Post Title: Santa Clause in Trouble XPK archives

By request, I looked into these XPK files from Santa Clause in Trouble. 

```

uint32		Number of resources (Num)

// String Pointer Table (pointers to filename strings)

uint32(Num)	Pointers to start of null-terminated filename strings in the next table
uint32		Pointer to end of last string/start of DataSize variable

// String table

byte(x)		List of null-terminated filenames in order of storage 

// DataSize variable

uint32		Total raw file data stored

// Resource Size table

uint32(Num)	Sizes of all stored files

// Date table

uint32(Num)	DOS_TIME of storage/creation of each stored file

// Resource Offset table

uint32(Num)	Offset of each file stored

```


I've created this MexScript for MultiEx Commander:

```
Get FileNum Long 0;
Set SP Long FileNum;
Math SP *= 4;
Math SP += 4;
GoTo SP 0;
Math SP += 4;
Get LSP Long 0;
SavePos RST 0;
Math RST += LSP;
Math RST += 4;
Set ROT Long 8;
Math ROT *= FileNum;
Math ROT += RST;
For T = 1 To FileNum;
GoTo SP 0;
Get FN String 0;
SavePos SP 0;
GoTo RST 0;
SavePos FSO 0;
Get FS Long 0;
SavePos RST 0;
GoTo ROT 0;
SavePos FOO 0;
Get FO Long 0;
SavePos ROT 0;
Log FN FO FS FOO FSO;
Next T;

```


Here's the compiled .bms:


 xpk.zip
(320 Bytes) Downloaded 70 times


Now listen carefully: You should go to BMS-->Add BMS To MRF...
Then point to the xpk.bms file by browsing (first line of the dialogue). 
Finally, give the name of the game in the second line and click OK. 
Done! Now simply Open a XPK archive with MultiEx Commander. 
You can also replace the contents! 

Examples extracted:



big_font00.jpg (229.89 KiB) Viewed 278 times





dachpeter.jpg (280.91 KiB) Viewed 280 times





nicolaus.jpg (222.39 KiB) Viewed 276 times





rabe.jpg (73.54 KiB) Viewed 277 times





sc.jpg (128.71 KiB) Viewed 274 times



Total table of contents of the XMAS.XPK file:

```
-----------------------------------
C:\Documents and Settings\MIKE\Mijn documenten\xmas.xpk
Number of resources: 177
TOC Created on: 18-6-2009 at 22:38:23
-----------------------------------
Naam	Type	Grootte	Positie
data\elements.txt	txt	12075	5971
effects\fire.txt	txt	324	18046
effects\jumper_air.txt	txt	326	18370
effects\star_miracle_w.txt	txt	339	18696
effects\star_miracle_y.txt	txt	339	19035
effects\white_smoke.txt	txt	337	19374
effects\hurt.txt	txt	327	19711
effects\waypoint.txt	txt	334	20038
effects\extralife.txt	txt	337	20372
effects\vulcan_smoke.txt	txt	338	20709
gfx\turm.x	x	1959	21047
gfx\dach01.x	x	1795	23006
gfx\waypoint.x	x	5430	24801
gfx\dach02.x	x	1915	30231
gfx\sign.x	x	1769	32146
gfx\dach03.x	x	2024	33915
gfx\haus01.x	x	2124	35939
gfx\haus02.x	x	2983	38063
gfx\platt_t.x	x	1894	41046
gfx\kamin.x	x	1636	42940
gfx\plattform01.x	x	2366	44576
gfx\plattform02.x	x	2509	46942
gfx\plattform03.x	x	2359	49451
gfx\plattform04.x	x	2644	51810
gfx\schneemann_000.ani	ani	59128	54454
gfx\platt_t_ice.x	x	2497	113582
gfx\plattform06.x	x	2725	116079
gfx\platt_corner.x	x	2133	118804
gfx\platt_corner_b.x	x	2148	120937
gfx\snow_t.x	x	3277	123085
gfx\platt_cross_b.x	x	1749	126362
gfx\platt_end.x	x	2324	128111
gfx\platt_full.x	x	1180	130435
gfx\hill01.x	x	3626	131615
gfx\platt_single.x	x	2245	135241
gfx\platt_single_b.x	x	2419	137486
gfx\platt_straight.x	x	2159	139905
gfx\platt_straight_b.x	x	2497	142064
gfx\wall_end_a.x	x	2351	144561
gfx\platt_t_b.x	x	2129	146912
gfx\hill02.x	x	3409	149041
gfx\schneemann_000.x	x	19219	152450
gfx\extralive.x	x	19036	171669
gfx\present.x	x	7492	190705
gfx\qmeter.x	x	753	198197
gfx\rectform01.x	x	1039	198950
gfx\tanne01.x	x	3344	199989
gfx\weihnachtsman_000.ani	ani	455557	203333
gfx\weihnachtsman_000.x	x	75569	658890
gfx\haus04.x	x	4210	734459
gfx\haus03.x	x	3507	738669
gfx\winter_troll_000.ani	ani	218792	742176
gfx\winter_troll_000.x	x	32864	960968
gfx\snow_straight_a.x	x	2746	993832
gfx\platt_straight_ice.x	x	2032	996578
gfx\platt_end_ice.x	x	2197	998610
gfx\platt_corner_ice.x	x	2011	1000807
gfx\platt_corner_ground.x	x	2289	1002818
gfx\platt_end_ground.x	x	2511	1005107
gfx\platt_end_b.x	x	2371	1007618
gfx\platt_cross.x	x	1710	1009989
gfx\snow_straight_b.x	x	2773	1011699
gfx\wall_corner_a.x	x	2172	1014472
gfx\himmel.x	x	1379	1016644
gfx\waypoint_000.ani	ani	12033	1018023
gfx\waypoint_000.x	x	5468	1030056
gfx\wall_corner_b.x	x	2175	1035524
gfx\wall_corner_c.x	x	2173	1037699
gfx\wall_end_b.x	x	2362	1039872
gfx\wall_end_c.x	x	2363	1042234
gfx\wall_singel_a.x	x	2603	1044597
gfx\wall_singel_b.x	x	2599	1047200
gfx\wall_singel_c.x	x	2458	1049799
gfx\wall_straight_a.x	x	1898	1052257
gfx\wall_straight_b.x	x	1861	1054155
gfx\wall_straight_c.x	x	1860	1056016
gfx\wall_t_a.x	x	1775	1057876
gfx\wall_t_b.x	x	1773	1059651
gfx\wall_t_c.x	x	1771	1061424
gfx\platt_full_cross_corner.x	x	2333	1063195
gfx\plattform05.x	x	3968	1065528
gfx\platt_cross_ice.x	x	2243	1069496
gfx\snow_corner.x	x	4123	1071739
gfx\platt_full_straight.x	x	1333	1075862
gfx\dummy.x	x	1808	1077195
gfx\plattform04_b.x	x	3669	1079003
gfx\platt_fire.x	x	3243	1082672
gfx\platt_full_corner.x	x	2121	1085915
gfx\sign_down.x	x	2673	1088036
gfx\sign_up.x	x	2677	1090709
gfx\sign_diagonal.x	x	2022	1093386
gfx\platt_full_corner_ice.x	x	2158	1095408
gfx\platt_full_ice.x	x	1209	1097566
gfx\platt_full_straight_ice.x	x	1338	1098775
gfx\rabe_000.ani	ani	26577	1100113
gfx\rabe_000.x	x	21359	1126690
gfx\platt_full_straight_b.x	x	1606	1148049
gfx\platt_end_full.x	x	2554	1149655
gfx\platt_corner_full.x	x	2372	1152209
gfx\platt_straight_full.x	x	2386	1154581
gfx\platt_t_full.x	x	2107	1156967
gfx\snow_cross.x	x	3668	1159074
gfx\snow_end.x	x	3212	1162742
gui\gui_style_big.txt	txt	1469	1165954
gui\gui_style_small.txt	txt	3138	1167423
gui\small_font.txt	txt	8669	1170561
gui\big_font.txt	txt	20802	1179230
levels\001.dat	dat	50944	1200032
levels\010.dat	dat	5104	1250976
levels\100.dat	dat	2584	1256080
levels\005.dat	dat	23344	1258664
levels\003.dat	dat	26764	1282008
levels\007.dat	dat	25504	1308772
levels\demo.dat	dat	12304	1334276
levels\006.dat	dat	46684	1346580
levels\002.dat	dat	43864	1393264
levels\004.dat	dat	30904	1437128
levels\000.dat	dat	27604	1468032
levels\009.dat	dat	33964	1495636
levels\008.dat	dat	49264	1529600
maps\extralive.dds	dds	43818	1578864
maps\objects.dds	dds	2796330	1622682
maps\haus2.dds	dds	699178	4419012
maps\effects.dds	dds	524416	5118190
maps\editgrid.tga	tga	16428	5642606
maps\cdv.dds	dds	174890	5659034
maps\joymania.dds	dds	131200	5833924
maps\gui2.tga	tga	65580	5965124
maps\rabe.dds	dds	174890	6030704
maps\gui_small.tga	tga	262188	6205594
maps\small_font00.dds	dds	131200	6467782
maps\mouse.tga	tga	16428	6598982
maps\sc.dds	dds	1048704	6615410
maps\shadow.dds	dds	11050	7664114
maps\screen002.jpg	jpg	146815	7675164
maps\snow.dds	dds	11050	7821979
maps\star.dds	dds	11050	7833029
maps\screen001.jpg	jpg	154952	7844079
maps\screen003.jpg	jpg	133708	7999031
maps\screen004.jpg	jpg	120430	8132739
maps\big_font00.dds	dds	524416	8253169
maps\dachpeter.dds	dds	699178	8777585
maps\big_font01.dds	dds	524416	9476763
maps\himmel.dds	dds	1399253	10001179
maps\big_font02.dds	dds	524416	11400432
maps\nicolaus.dds	dds	699178	11924848
maps\schneemann.dds	dds	174890	12624026
maps\wintertroll.dds	dds	174890	12798916
maps\misc.dds	dds	699178	12973806
maps\#tanne.dds	dds	699178	13672984
sfx\klick.wav	wav	4604	14372162
sfx\jump01.wav	wav	25844	14376766
sfx\present.wav	wav	72560	14402610
sfx\jumper01.wav	wav	104646	14475170
sfx\snow01.wav	wav	55308	14579816
sfx\dying01.wav	wav	108216	14635124
sfx\score.wav	wav	4032	14743340
sfx\goblin01.wav	wav	192190	14747372
sfx\goblin02.wav	wav	114220	14939562
sfx\goblin03.wav	wav	28758	15053782
sfx\crow01.wav	wav	79290	15082540
sfx\crow02.wav	wav	74614	15161830
sfx\crow03.wav	wav	31024	15236444
sfx\waypoint.wav	wav	40238	15267468
sfx\extralife.wav	wav	66628	15307706
sfx.txt	txt	555	15374334
text00.lib	lib	1214	15374889
text01.lib	lib	1446	15376103
text02.lib	lib	1348	15377549
text04.lib	lib	1238	15378897
text03.lib	lib	1252	15380135
text05.lib	lib	1238	15381387
text06.lib	lib	928	15382625
text07.lib	lib	1226	15383553
text08.lib	lib	1226	15384779
text09.lib	lib	888	15386005
xgl_public.hpp	hpp	2512	15386893
-----------------------------------

```
## Post #2
- Username: dossantos69
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Aug 28, 2018 11:21 pm
- Post datetime: 2018-08-28T15:29:22+00:00
- Post Title: Santa Clause in Trouble XPK archives

Any chance to convert the .lvl and .x files to .obj ?
## Post #3
- Username: ad48hp
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed May 09, 2018 10:47 pm
- Post datetime: 2019-01-08T21:52:19+00:00
- Post Title: Santa Clause in Trouble XPK archives

I tried to import the .x files into Blender with [this](https://github.com/littleneo/directX_blender/tree/master/io_directx_bel) and the 3D Object Converter, with no success so far.
Could someone look into this ?
Here are some of the important files: [https://1drv.ms/u/s!ApTusXylYbesuTi4KUhQtw0sdisZ](https://1drv.ms/u/s!ApTusXylYbesuTi4KUhQtw0sdisZ)
